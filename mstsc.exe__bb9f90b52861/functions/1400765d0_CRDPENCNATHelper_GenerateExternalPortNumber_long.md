# CRDPENCNATHelper::GenerateExternalPortNumber(long *)

- ea: `0x1400765d0`
- end: `0x1400768c4`
- name: `?GenerateExternalPortNumber@CRDPENCNATHelper@@IEAAJPEAJ@Z`
- size: `756`
- prototype: `__int64 __fastcall(CRDPENCNATHelper *__hidden this, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14007634c`

## callees

- `0x140001b00`
- `0x14000b7d8`
- `0x14000cfb0`
- `0x1400765d0`
- `0x140114010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140076623`
- `KERNEL32!GetLastError` at `0x14007681f`
- `KERNEL32!GetLastError` at `0x140076623`
- `KERNEL32!GetLastError` at `0x14007681f`
- `ADVAPI32!CryptAcquireContextW` at `0x140076619`
- `ADVAPI32!CryptAcquireContextW` at `0x140076619`
- `ADVAPI32!CryptGenRandom` at `0x14007669d`
- `ADVAPI32!CryptGenRandom` at `0x14007669d`
- `ADVAPI32!CryptReleaseContext` at `0x14007688b`
- `ADVAPI32!CryptReleaseContext` at `0x14007688b`

## string_xrefs

- `0x14007670c`: `Port %d already mapped`

## pseudocode

```c

```
