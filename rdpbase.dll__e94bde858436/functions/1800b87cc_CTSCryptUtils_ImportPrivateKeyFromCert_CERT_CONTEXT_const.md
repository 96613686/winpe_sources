# CTSCryptUtils::ImportPrivateKeyFromCert(_CERT_CONTEXT const *)

- ea: `0x1800b87cc`
- end: `0x1800b8a3c`
- name: `?ImportPrivateKeyFromCert@CTSCryptUtils@@QEAAJPEBU_CERT_CONTEXT@@@Z`
- size: `624`
- prototype: `int(CTSCryptUtils *__hidden this, const struct _CERT_CONTEXT *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800ecc38`

## callees

- `0x180004970`
- `0x180071a60`
- `0x1800923f8`
- `0x1800b8504`
- `0x1800b87cc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b8888`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b896b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b8888`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b896b`
- `CRYPT32!CryptAcquireCertificatePrivateKey` at `0x1800b887a`
- `CRYPT32!CryptAcquireCertificatePrivateKey` at `0x1800b887a`
- `ncrypt!NCryptFreeObject` at `0x1800b8a1f`
- `ncrypt!NCryptFreeObject` at `0x1800b8a1f`
- `ncrypt!NCryptIsKeyHandle` at `0x1800b892d`
- `ncrypt!NCryptIsKeyHandle` at `0x1800b8a11`
- `ncrypt!NCryptIsKeyHandle` at `0x1800b892d`
- `ncrypt!NCryptIsKeyHandle` at `0x1800b8a11`
- `CRYPTSP!CryptReleaseContext` at `0x1800b8a29`
- `CRYPTSP!CryptReleaseContext` at `0x1800b8a29`
- `CRYPTSP!CryptGetUserKey` at `0x1800b895d`
- `CRYPTSP!CryptGetUserKey` at `0x1800b895d`

## string_xrefs

- `0x1800b88c9`: `onecore\termsrv\rdpplatform\common\cryptutil\base\tscryptutils.cpp`
- `0x1800b89a8`: `onecore\termsrv\rdpplatform\common\cryptutil\base\tscryptutils.cpp`

## pseudocode

```c

```
