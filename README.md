Credits & Adapted from  : https://github.com/rufuspollock/s3-bucket-listing

Provides tabular listing of contents from S3 bucket.

## Usage

Modify the script to replace the following parameters.
* BUCKET_NAME
* ACCESS_KEY
* ACCESS_SECRET
* REGION

Once set, run the script directly in browser. Few sample urls:
..../s3list.html/prefix=    : This will list all the keys in your bucket
..../s3list.html/prefix=dir : List all keys that begins with dir

Since there is no concept of folder/directory in S3, entire key is listed. To download any file, click on the listed element, file would be downloaded with actual name of the file ignoring all the nested directories from keyname(if any).

## How it works

The script uses amazon sdk to fetch the bucket`s metadata and generate signed urls to download the object in S3 directly from the browser.

This script uses AWS access credentials to access the s3 information so the bucket doesn`t need to open to public.

If your bucket is/can be public read, you should look at https://github.com/rufuspollock/s3-bucket-listing

Note : Since script runs in browser, access credentials are exposed to anyone using this script. Because of this public usage of this script is not recommended. 
##

## S3 Bucket setup

For this script to work, following configuration has to be done on your S3 bucket.

* Assign LIST & READ access to the read user to be used in the script.
* Uploaded objects must have PUBLIC_READ acl.
* Content-disposition should be attachment for a file, if you want to download it using the script.
* CORS policy should be configured as 

```
<CORSConfiguration>
 <CORSRule>
   <AllowedOrigin>*</AllowedOrigin>
   <AllowedMethod>GET</AllowedMethod>
   <AllowedHeader>*</AllowedHeader>
 </CORSRule>
</CORSConfiguration>
```

## Copyright

This script is modified from the https://github.com/rufuspollock/s3-bucket-listing having same copyright and licensing terms as mentioned there.


