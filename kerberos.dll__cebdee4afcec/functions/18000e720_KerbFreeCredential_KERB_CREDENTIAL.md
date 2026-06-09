# KerbFreeCredential(_KERB_CREDENTIAL *)

- ea: `0x18000e720`
- end: `0x18000e823`
- name: `?KerbFreeCredential@@YAXPEAU_KERB_CREDENTIAL@@@Z`
- size: `259`
- prototype: `void __fastcall(HLOCAL hMem)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1800474d8`

## callees

- `0x1800068d0`
- `0x1800069a0`
- `0x18000e720`
- `0x1800305ac`
- `0x18006517c`
- `0x1800f5010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e7df`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e7e7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e7df`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e7e7`
- `ntdll!NtClose` at `0x18000e764`
- `ntdll!NtClose` at `0x18000e764`
- `CRYPT32!CertFreeCertificateContext` at `0x18000e813`
- `CRYPT32!CertFreeCertificateContext` at `0x18000e813`
- `LSASRV!LsaIFreeSupplementalTokenInfo` at `0x18000e755`
- `LSASRV!LsaIFreeSupplementalTokenInfo` at `0x18000e755`

## pseudocode

```c

```
