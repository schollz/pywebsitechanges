# websitechanges

A simple python script to email you whenever a website changes.

## Install

First install Node and Python on your system if you don't already. Then you will need the required packages which can be installed with `pip`:

	pip install click numpy loguru scikit-image opencv-python

Then get the script:


And now run it whever - in a folder, in a cron, etc.

## Usage

```bash
$ python3 websitechanges.py --help
Usage: websitechanges.py [OPTIONS]

Options:
  --url TEXT         url to watch  [required]
  --folder TEXT      directory to store data
  --css TEXT         CSS selector of element to watch, default full page
  --to TEXT          email address of person to alert
  --smtpemail TEXT   SMTP email address
  --smtppass TEXT    SMTP email password
  --threshold FLOAT  threshold for sending email
```

The `url` is the specified URL.

The `folder` specifies where to store all the data and puppeteer information.

### Example

The simplest way to run is:

	python3 websitechanges.py --url SOMEURL

This will automatically download puppeteer, which is used to gather the screenshot. It will also download a HOSTS file to block ads so that the website can be shown reproducibly. 

To be alerted you will need to set `to` (the email to alert), `smtpemail` (the email sign-in for the SMTP), and `smtppass` (the password for the SMTP). You can easily setup a Gmail account to be used as an SMTP provider. 

Every alert will send you an image of the latest image.

## License

MIT