# NetpCheckAccountSecret(ushort const *,int)

- ea: `0x180065ad4`
- end: `0x180065be4`
- name: `?NetpCheckAccountSecret@@YAJPEBGH@Z`
- size: `272`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180067400`

## callees

- `0x180065ad4`
- `0x180065bec`

## import_xrefs

- `LSASRV!LsarClose` at `0x180065bca`
- `LSASRV!LsarClose` at `0x180065bca`
- `LSASRV!LsarOpenSecret` at `0x180065b83`
- `LSASRV!LsarOpenSecret` at `0x180065b83`
- `ntdll!RtlLeaveCriticalSection` at `0x180065b98`
- `ntdll!RtlLeaveCriticalSection` at `0x180065b98`
- `ntdll!RtlEnterCriticalSection` at `0x180065b5c`
- `ntdll!RtlEnterCriticalSection` at `0x180065b5c`
- `ntdll!RtlInitUnicodeString` at `0x180065b49`
- `ntdll!RtlInitUnicodeString` at `0x180065b49`
- `netutils!NetApiBufferFree` at `0x180065bb1`
- `netutils!NetApiBufferFree` at `0x180065bb1`

## pseudocode

```c

```
