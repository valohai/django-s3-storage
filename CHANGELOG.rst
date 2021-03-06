django-s3-storage changelog
===========================

0.11.1 - Development
--------------------

- Raising ``OSError`` instead of ``IOError`` if S3 storage throws an error. On Python 3 it makes no difference, but on Python 2 it's what collectstatic expects.
- Fixed issue with ``s3_sync_meta`` where a race condition or key name normalization could cause an ``OSError`` to be raised.


0.11.0
------

- *Breaking:* All S3 keys are normalized to use unix-style path separators, and resolve relative paths.


0.10.0
------

- Switched to `boto3`-based implementation.
- Added `AWS_S3_CONTENT_DISPOSITION` and `AWS_S3_CONTENT_LANGUAGE` settings.
- Added `AWS_S3_CONTENT_DISPOSITION_STATIC` and `AWS_S3_CONTENT_LANGUAGE_STATIC` settings.
- *Breaking:* Setting Content-Disposition and Content-Language headers via `AWS_S3_METADATA` setting no longer supported.
- *Breaking:* `AWS_S3_HOST` setting refactored to `AWS_S3_ENDPOINT_URL`.
- *Breaking:* `AWS_S3_HOST_STATIC` setting refactored to `AWS_S3_ENDPOINT_URL_STATIC`.
- *Breaking:* `AWS_S3_CALLING_FORMAT` setting refactored to `AWS_S3_ADDRESSING_STYLE`.
- *Breaking:* `AWS_S3_CALLING_FORMAT_STATIC` setting refactored to `AWS_S3_ADDRESSING_STYLE_STATIC`.


0.9.11
------

- Added support for server-side encryption (@aaugustin).
- Allowed S3 files to be re-opened once closed (@etianen).
- Bugfixes (@Moraga, @etianen).


0.9.10
------

- Fixing regression with accessing legacy S3 keys with non-normalized path names (@etianen).


0.9.9
-----

- Added settings for disabling gzip compression (@leonsmith)
- Bug fix for relative upload paths (@leonsmith)
- Bug fix for detecting empty directories (@etianen).
- Automatic conversion of windows path separators on upload (@etianen).


0.9.8
-----

- Added support for custom metadata associated with a file (@etianen).


0.9.7
-----

- Added support for non-S3 hosts (@philippbosch, @heldinz).
- Added support for reduced redundancy storage class (@aaugustin).
- Minor bugfixes and documentation improvements (@leonsim, @alexkahn, @etianen).


0.9.6
-----

- Added settings for customizing S3 public URLs (@etianen).
- Added settings for customizing S3 calling format (@etianen).


0.9.5
-----

- Compressing javascript files on upload to S3 (@etianen).


0.9.4
-----

- Using a temporary file buffer for compressing and encoding large file uploads (@etianen).
- Eplicitly closing temporary file buffers, rather than relying on the GC (@etianen).


0.9.3
-----

- Fixed issue with s3_sync_meta management command not being included in source distribution (@etianen).


0.9.2
-----

- Added settings for fine-grained control over browser caching (@etianen).
- Added settings for adding a prefix to all keys (@etianen).


0.9.1
-----

- Added `AWS_S3_MAX_AGE_SECONDS` setting (@kasajei).
- Added option to connect S3 without AWS key/secret (@achiku).


0.9.0
-----

- First production release (@etianen).
