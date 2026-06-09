# I_CryptCAPI1VerifyCertificateSignedContent(uint,uint,ulong,ulong,unsigned __int64,ulong,_CERT_PUBLIC_KEY_INFO *,_CERT_SIGNED_CONTENT_INFO *,ulong,void *)

- ea: `0x1800959d4`
- end: `0x180095c7d`
- name: `?I_CryptCAPI1VerifyCertificateSignedContent@@YAHIIKK_KKPEAU_CERT_PUBLIC_KEY_INFO@@PEAU_CERT_SIGNED_CONTENT_INFO@@KPEAX@Z`
- size: `681`
- prototype: `__int64 __usercall@<rax>(ALG_ID Algid@<ecx>, unsigned int@<edx>, unsigned int@<r8d>, unsigned int@<r9d>, HCRYPTPROV hCryptProv, unsigned int, struct _CERT_PUBLIC_KEY_INFO *, struct _CERT_SIGNED_CONTENT_INFO *, unsigned int, void *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18002f6f0`

## callees

- `0x180008720`
- `0x180027460`
- `0x1800275a0`
- `0x18003e1b0`
- `0x1800959d4`
- `0x180095c84`
- `0x180095cd0`
- `0x1800bec20`
- `0x1801150c4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095b5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095b5c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180095b96`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18011c5f3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180095b96`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18011c5f3`
- `CRYPTSP!CryptHashData` at `0x180095aea`
- `CRYPTSP!CryptHashData` at `0x180095aea`
- `CRYPTSP!CryptGetHashParam` at `0x180095c3d`
- `CRYPTSP!CryptGetHashParam` at `0x180095c3d`
- `CRYPTSP!CryptDestroyHash` at `0x180095b7c`
- `CRYPTSP!CryptDestroyHash` at `0x180095b7c`
- `CRYPTSP!CryptDestroyKey` at `0x180095b6d`
- `CRYPTSP!CryptDestroyKey` at `0x180095b6d`
- `CRYPTSP!CryptReleaseContext` at `0x180095c72`
- `CRYPTSP!CryptReleaseContext` at `0x180095c72`
- `CRYPTSP!CryptCreateHash` at `0x180095ace`
- `CRYPTSP!CryptCreateHash` at `0x180095ace`
- `CRYPTSP!CryptAcquireContextA` at `0x180095bf0`
- `CRYPTSP!CryptAcquireContextA` at `0x180095bf0`
- `CRYPTSP!CryptVerifySignatureA` at `0x180095b52`
- `CRYPTSP!CryptVerifySignatureA` at `0x180095b52`

## pseudocode

```c

```
