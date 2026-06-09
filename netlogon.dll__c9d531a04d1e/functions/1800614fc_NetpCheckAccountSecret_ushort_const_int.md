# NetpCheckAccountSecret(ushort const *,int)

- ea: `0x1800614fc`
- end: `0x1800615e7`
- name: `?NetpCheckAccountSecret@@YAJPEBGH@Z`
- size: `235`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180062bb8`

## callees

- `0x1800614fc`
- `0x1800615f0`

## import_xrefs

- `LSASRV!LsarClose` at `0x1800615d4`
- `LSASRV!LsarClose` at `0x1800615d4`
- `LSASRV!LsarOpenSecret` at `0x18006159f`
- `LSASRV!LsarOpenSecret` at `0x18006159f`
- `ntdll!RtlLeaveCriticalSection` at `0x1800615ae`
- `ntdll!RtlLeaveCriticalSection` at `0x1800615ae`
- `ntdll!RtlEnterCriticalSection` at `0x18006157e`
- `ntdll!RtlEnterCriticalSection` at `0x18006157e`
- `ntdll!RtlInitUnicodeString` at `0x180061571`
- `ntdll!RtlInitUnicodeString` at `0x180061571`
- `netutils!NetApiBufferFree` at `0x1800615c1`
- `netutils!NetApiBufferFree` at `0x1800615c1`

## pseudocode

```c

```
