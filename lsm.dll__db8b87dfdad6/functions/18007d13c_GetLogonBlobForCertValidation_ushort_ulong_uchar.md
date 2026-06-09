# GetLogonBlobForCertValidation(ushort *,ulong *,uchar *)

- ea: `0x18007d13c`
- end: `0x18007d5c1`
- name: `?GetLogonBlobForCertValidation@@YAJPEAGPEAKPEAE@Z`
- size: `1157`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18007d8f0`

## callees

- `0x180025070`
- `0x180025890`
- `0x18004bf44`
- `0x18007cebc`
- `0x18007d13c`
- `0x18009404c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18007d57f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18007d57f`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18007d335`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18007d335`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d262`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d262`
- `api-ms-win-security-credentials-l1-1-0!CredUnmarshalCredentialW` at `0x18007d196`
- `api-ms-win-security-credentials-l1-1-0!CredUnmarshalCredentialW` at `0x18007d196`
- `CRYPT32!CertFreeCertificateContext` at `0x18007d59e`
- `CRYPT32!CertFreeCertificateContext` at `0x18007d59e`
- `CRYPT32!CertFindCertificateInStore` at `0x18007d24e`
- `CRYPT32!CertFindCertificateInStore` at `0x18007d24e`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18007d2ef`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18007d382`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18007d2ef`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18007d382`
- `CRYPT32!CertCloseStore` at `0x18007d590`
- `CRYPT32!CertCloseStore` at `0x18007d590`
- `CRYPT32!CertOpenStore` at `0x18007d210`
- `CRYPT32!CertOpenStore` at `0x18007d210`

## pseudocode

```c

```
