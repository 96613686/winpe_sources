# RegistrationCertStatus::GetCertificateDeviceAndTenantId(ushort const *,ushort * *,ushort * *)

- ea: `0x180093f00`
- end: `0x180094191`
- name: `?GetCertificateDeviceAndTenantId@RegistrationCertStatus@@SAJPEBGPEAPEAG1@Z`
- size: `657`
- prototype: `__int64 __fastcall(LPCWSTR pszString, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `7`
- tags: ``

## callers

- `0x1800439d4`
- `0x180053630`
- `0x180053e94`

## callees

- `0x1800084f4`
- `0x18000bac0`
- `0x18000c550`
- `0x18000cc2c`
- `0x1800307c4`
- `0x18003334c`
- `0x180093f00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180094003`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800940b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009413a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180094003`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800940b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009413a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180094037`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180094037`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180094122`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180094122`
- `CRYPT32!CryptStringToBinaryW` at `0x180093ff9`
- `CRYPT32!CryptStringToBinaryW` at `0x18009408b`
- `CRYPT32!CryptStringToBinaryW` at `0x180093ff9`
- `CRYPT32!CryptStringToBinaryW` at `0x18009408b`
- `CRYPT32!CertCreateCertificateContext` at `0x1800940a9`
- `CRYPT32!CertCreateCertificateContext` at `0x1800940a9`
- `CRYPT32!CertFreeCertificateContext` at `0x180094130`
- `CRYPT32!CertFreeCertificateContext` at `0x180094130`

## string_xrefs

- `0x1800940cc`: `CertCreateCertificateContext`

## pseudocode

```c

```
