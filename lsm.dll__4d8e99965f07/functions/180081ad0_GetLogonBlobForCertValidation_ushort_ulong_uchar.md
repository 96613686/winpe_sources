# GetLogonBlobForCertValidation(ushort *,ulong *,uchar *)

- ea: `0x180081ad0`
- end: `0x180081f92`
- name: `?GetLogonBlobForCertValidation@@YAJPEAGPEAKPEAE@Z`
- size: `1218`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800822f0`

## callees

- `0x18002701c`
- `0x18002772c`
- `0x18004f354`
- `0x180081848`
- `0x180081ad0`
- `0x18009959c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180081f3d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180081f3d`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180081ce7`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180081ce7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180081c08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180081c08`
- `api-ms-win-security-credentials-l1-1-0!CredUnmarshalCredentialW` at `0x180081b2a`
- `api-ms-win-security-credentials-l1-1-0!CredUnmarshalCredentialW` at `0x180081b2a`
- `CRYPT32!CertFreeCertificateContext` at `0x180081f68`
- `CRYPT32!CertFreeCertificateContext` at `0x180081f68`
- `CRYPT32!CertFindCertificateInStore` at `0x180081bee`
- `CRYPT32!CertFindCertificateInStore` at `0x180081bee`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180081c9b`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180081d3a`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180081c9b`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180081d3a`
- `CRYPT32!CertCloseStore` at `0x180081f54`
- `CRYPT32!CertCloseStore` at `0x180081f54`
- `CRYPT32!CertOpenStore` at `0x180081baa`
- `CRYPT32!CertOpenStore` at `0x180081baa`

## pseudocode

```c

```
