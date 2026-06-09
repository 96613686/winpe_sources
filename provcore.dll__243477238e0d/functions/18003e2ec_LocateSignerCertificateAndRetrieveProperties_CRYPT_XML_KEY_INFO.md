# LocateSignerCertificateAndRetrieveProperties(_CRYPT_XML_KEY_INFO *)

- ea: `0x18003e2ec`
- end: `0x18003e731`
- name: `?LocateSignerCertificateAndRetrieveProperties@@YA?AU?$pair@V?$shared_ptr@X@std@@V?$shared_ptr@USignatureInfo@Signature@@@2@@std@@PEAU_CRYPT_XML_KEY_INFO@@@Z`
- size: `1093`
- prototype: `std::pair<std::shared_ptr<void>,std::shared_ptr<Signature::SignatureInfo> > *__fastcall(std::pair<std::shared_ptr<void>,std::shared_ptr<Signature::SignatureInfo> > *result, _CRYPT_XML_KEY_INFO *pKeyInfo)`
- caller_count: `1`
- callee_count: `24`
- tags: `registry_config`

## callers

- `0x18003e8fc`

## callees

- `0x180002790`
- `0x180002b9c`
- `0x1800032f4`
- `0x18000b144`
- `0x18000b8c0`
- `0x18000fa6c`
- `0x180011844`
- `0x180011cfc`
- `0x180012748`
- `0x180012770`
- `0x1800127cc`
- `0x180012bc8`
- `0x180013bdc`
- `0x18003cf98`
- `0x18003d058`
- `0x18003d1c4`
- `0x18003d768`
- `0x18003d878`
- `0x18003dab8`
- `0x18003db44`
- `0x18003deac`
- `0x18003dffc`
- `0x18003e2ec`
- `0x18003e738`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e3db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e3db`
- `CRYPT32!CertFreeCertificateContext` at `0x18003e399`
- `CRYPT32!CryptImportPublicKeyInfoEx2` at `0x18003e3d1`
- `CRYPT32!CryptImportPublicKeyInfoEx2` at `0x18003e3d1`
- `bcrypt!BCryptDestroyKey` at `0x18003e444`

## pseudocode

```c

```
