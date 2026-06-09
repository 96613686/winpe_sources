# LsapDomainRenameHandlerForLogonSessions

- ea: `0x1800ceb10`
- end: `0x1800ced98`
- name: `LsapDomainRenameHandlerForLogonSessions`
- size: `648`
- prototype: `__int64 __fastcall(PCUNICODE_STRING String1)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x180003890`
- `0x180003afc`
- `0x180007268`
- `0x18000c300`
- `0x18000d3b0`
- `0x1800ceb10`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800cecc6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800cecc6`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800cebb9`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800cebb9`
- `ntdll!RtlReleaseResource` at `0x1800ced00`
- `ntdll!RtlReleaseResource` at `0x1800ced1c`
- `ntdll!RtlReleaseResource` at `0x1800ced41`
- `ntdll!RtlReleaseResource` at `0x1800ced57`
- `ntdll!RtlReleaseResource` at `0x1800ced00`
- `ntdll!RtlReleaseResource` at `0x1800ced1c`
- `ntdll!RtlReleaseResource` at `0x1800ced41`
- `ntdll!RtlReleaseResource` at `0x1800ced57`
- `ntdll!RtlAcquireResourceShared` at `0x1800ceb75`
- `ntdll!RtlAcquireResourceShared` at `0x1800ceb75`
- `ntdll!RtlEqualUnicodeString` at `0x1800cebe5`
- `ntdll!RtlEqualUnicodeString` at `0x1800cec2a`
- `ntdll!RtlEqualUnicodeString` at `0x1800cebe5`
- `ntdll!RtlEqualUnicodeString` at `0x1800cec2a`

## pseudocode

```c

```
