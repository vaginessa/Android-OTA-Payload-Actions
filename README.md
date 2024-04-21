# Payload Actions

This GitHub Actions workflow allows you to automatically extract and release specific files from a ROM URL.

## Inputs

The following inputs are required when triggering the workflow:

-   `ROM_URL`: The URL of the ROM file to be extracted and released.
-   `DEVICE_NAME`: The name of the device for which the ROM is intended.
-   `EXTRACTED_FILES`: A comma-separated list of files to be extracted from the ROM and included in the release. Available files may include:

## comment by vaginessa: _I use ```*.img``` or even better ```*.*``` to extract ALL partitions!!_

## Steps

The workflow is composed of the following steps:

1. Checkout code: Check out the repository code.
2. Download file: Download the file specified by the ROM_URL input.
3. Extract Payload: Extract the payload from the downloaded file and output it to the current directory. Additionally, files larger than 2GB will be automatically deleted to comply with GitHub release restrictions, as files larger than 2GB are not allowed.
4. Upload to Release: Uploads specified files to a GitHub release.

## Usage

1. Fork this repository to your GitHub account.
2. Go to the "Actions" tab in your forked repository.
3. Enable GitHub Actions for the repository if it's not already enabled.
4. Select the workflow named "Extract and Release" from the list of workflows.
5. Click on the "Run workflow" dropdown button and select the "Run workflow" option.
6. Enter the required inputs:
    - `ROM_URL`: The URL of the ROM file to be extracted and released.
    - `DEVICE_NAME`: The name of the device for which the ROM is intended.
    - `EXTRACTED_FILES`: A comma-separated list of files to be extracted from the ROM and included in the release (e.g., "boot.img, dtbo.img, product.img").
7. Click the "Run workflow" button to trigger the workflow with the provided inputs.

## Note

The OTA Extractor package that is used in this workflow is taken from https://github.com/tobyxdd/android-ota-payload-extractor.
