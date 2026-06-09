# CredpAcquirePrivateKeyForCertCred(_LUID *,_CANONICAL_CREDENTIAL *,_CERT_CONTEXT const * *,unsigned __int64 *,ulong *,int *)

- ea: `0x1800c3b00`
- end: `0x1800c3f32`
- name: `?CredpAcquirePrivateKeyForCertCred@@YAJPEAU_LUID@@PEAU_CANONICAL_CREDENTIAL@@PEAPEBU_CERT_CONTEXT@@PEA_KPEAKPEAH@Z`
- size: `1074`
- prototype: `__int64 __fastcall(struct _LUID *, struct _CANONICAL_CREDENTIAL *, const struct _CERT_CONTEXT **, unsigned __int64 *, unsigned int *pdwKeySpec, int *ThreadInformation)`
- caller_count: `3`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180041390`
- `0x1800422f0`
- `0x180096434`

## callees

- `0x180011278`
- `0x18003a848`
- `0x180081810`
- `0x18008e360`
- `0x1800c3b00`
- `0x1800c3f38`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c3b96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c3d14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c3daf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c3b96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c3d14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c3daf`
- `ntdll!NtSetInformationThread` at `0x1800c3f0b`
- `ntdll!NtSetInformationThread` at `0x1800c3f0b`
- `api-ms-win-security-credentials-l1-1-0!CredFree` at `0x1800c3edc`
- `api-ms-win-security-credentials-l1-1-0!CredFree` at `0x1800c3edc`
- `api-ms-win-security-credentials-l1-1-0!CredUnmarshalCredentialW` at `0x1800c3b86`
- `api-ms-win-security-credentials-l1-1-0!CredUnmarshalCredentialW` at `0x1800c3b86`
- `CRYPT32!CertCloseStore` at `0x1800c3ec7`
- `CRYPT32!CertCloseStore` at `0x1800c3ec7`
- `CRYPT32!CertFreeCertificateContext` at `0x1800c3eaf`
- `CRYPT32!CertFreeCertificateContext` at `0x1800c3eaf`
- `CRYPT32!CertFindCertificateInStore` at `0x1800c3d9b`
- `CRYPT32!CertFindCertificateInStore` at `0x1800c3d9b`
- `CRYPT32!CertOpenStore` at `0x1800c3d00`
- `CRYPT32!CertOpenStore` at `0x1800c3d00`

## pseudocode

```c

```
