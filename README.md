-   Detect it easy downloaded through github

    -   ![](images/media/image3.png){width="4.092332677165355in"
        height="3.0364588801399823in"}

-   First we will be looking at the not packed file:

    -   ![](images/media/image1.png){width="3.7619925634295712in"
        height="2.740334645669291in"}

    -   By clicking on signatures we get this:

    -   ![](images/media/image5.png){width="4.2607983377077865in"
        height="2.1406255468066493in"}

    -   By clicking on advanced \> entropy we get this:

    -   

    -   Analyzing this we can see that,

        -   the file type is an executable here (PE32 top left).

        -   The file is not packed (as shown in the signatures)

        -   The file has low relatively low entropy which means that it
            is not packed (avg entropy: 6.326, anything above 7.5 means
            it is most likely packed)

-   Now looking at the packed file

-   Download UPX from github latest release and unzip it

-   went into the directory of where I downloaded UPX

-   unpacked the packed file with UPX

    -   ![](images/media/image6.png){width="5.067708880139983in"
        height="3.029255249343832in"}

    -   We can see that the ratio is 65.28% and the format is of
        win32/pe

-   Let\'s look at it inside of DIE

    -   ![](images/media/image4.png){width="4.398265529308836in"
        height="2.2343755468066493in"}

    -   Unfortunately, I was not able to look at the packed file before
        I unpacked it. However, looking at the entropy levels we do get
        a higher level than when we looked at the unpacked version.

**Final key conclusions**

-   **Packing obfuscates executables by compressing sections, increasing
    entropy, and making static analysis harder.**

-   **Detect It Easy (DIE) can identify packers, but sometimes packer
    signatures may be missing due to signature stripping or
    modification.**

-   **Entropy analysis is a key technique in determining whether a file
    is packed, with high entropy suggesting compression or encryption.**

-   **UPX is a common packer, and unpacking with upx -d successfully
    restores the original executable.**

-   **Static analysis tools and antivirus software often flag packed
    executables as suspicious, even when they are harmless.**
