# CRDPENCNATHelper::GenerateExternalPortNumber(long *)

- ea: `0x140074460`
- end: `0x140074754`
- name: `?GenerateExternalPortNumber@CRDPENCNATHelper@@IEAAJPEAJ@Z`
- size: `756`
- prototype: `__int64 __fastcall(CRDPENCNATHelper *__hidden this, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1400741dc`

## callees

- `0x140001b00`
- `0x14000b7d8`
- `0x14000cfb0`
- `0x140074460`
- `0x140112010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400744b3`
- `KERNEL32!GetLastError` at `0x1400746af`
- `KERNEL32!GetLastError` at `0x1400744b3`
- `KERNEL32!GetLastError` at `0x1400746af`
- `ADVAPI32!CryptAcquireContextW` at `0x1400744a9`
- `ADVAPI32!CryptAcquireContextW` at `0x1400744a9`
- `ADVAPI32!CryptGenRandom` at `0x14007452d`
- `ADVAPI32!CryptGenRandom` at `0x14007452d`
- `ADVAPI32!CryptReleaseContext` at `0x14007471b`
- `ADVAPI32!CryptReleaseContext` at `0x14007471b`

## string_xrefs

- `0x14007459c`: `Port %d already mapped`

## pseudocode

```c

```
