# RegistrationCertHelper::IsValidDeviceJoinAutoSigningCert(uchar const *,ulong,ushort const *,int *,_CERT_CONTEXT const * *)

- ea: `0x18005e314`
- end: `0x18005e5fb`
- name: `?IsValidDeviceJoinAutoSigningCert@RegistrationCertHelper@@SAJPEBEKPEBGPEAHPEAPEBU_CERT_CONTEXT@@@Z`
- size: `743`
- prototype: `__int64 __fastcall(BYTE *pbCertEncoded, DWORD cbCertEncoded, const unsigned __int16 *, int *, const struct _CERT_CONTEXT **)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18004acc8`

## callees

- `0x1800084f4`
- `0x180008530`
- `0x18000bac0`
- `0x1800307c4`
- `0x18003334c`
- `0x180043ef8`
- `0x18004654c`
- `0x18005e314`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005e560`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005e560`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e421`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e480`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e4c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e421`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e480`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e4c9`
- `CRYPT32!CertGetNameStringW` at `0x18005e4bc`
- `CRYPT32!CertGetNameStringW` at `0x18005e54b`
- `CRYPT32!CertGetNameStringW` at `0x18005e4bc`
- `CRYPT32!CertGetNameStringW` at `0x18005e54b`
- `CRYPT32!CertOpenStore` at `0x18005e413`
- `CRYPT32!CertOpenStore` at `0x18005e413`
- `CRYPT32!CertCloseStore` at `0x18005e595`
- `CRYPT32!CertCloseStore` at `0x18005e595`
- `CRYPT32!CertAddEncodedCertificateToStore` at `0x18005e476`
- `CRYPT32!CertAddEncodedCertificateToStore` at `0x18005e476`
- `CRYPT32!CertFreeCertificateContext` at `0x18005e58a`
- `CRYPT32!CertFreeCertificateContext` at `0x18005e58a`

## string_xrefs

- `0x18005e430`: `CertOpenStore`

## pseudocode

```c

```
