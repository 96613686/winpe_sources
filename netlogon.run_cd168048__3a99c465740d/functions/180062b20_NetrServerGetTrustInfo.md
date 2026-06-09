# NetrServerGetTrustInfo

- ea: `0x180062b20`
- end: `0x180062f3c`
- name: `NetrServerGetTrustInfo`
- size: `1052`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800635c0`

## callees

- `0x18000c440`
- `0x18000e910`
- `0x1800267ec`
- `0x1800271d4`
- `0x1800374dc`
- `0x180057174`
- `0x180062b20`
- `0x1800639bc`
- `0x18006507c`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180062bfe`
- `ntdll!RtlLeaveCriticalSection` at `0x180062c34`
- `ntdll!RtlLeaveCriticalSection` at `0x180062c6c`
- `ntdll!RtlLeaveCriticalSection` at `0x180062bfe`
- `ntdll!RtlLeaveCriticalSection` at `0x180062c34`
- `ntdll!RtlLeaveCriticalSection` at `0x180062c6c`
- `ntdll!RtlEnterCriticalSection` at `0x180062bdc`
- `ntdll!RtlEnterCriticalSection` at `0x180062bdc`
- `ntdll!RtlInitUnicodeString` at `0x180062d80`
- `ntdll!RtlInitUnicodeString` at `0x180062d80`
- `netutils!NetApiBufferFree` at `0x180062ee0`
- `netutils!NetApiBufferFree` at `0x180062ee0`
- `netutils!NetApiBufferAllocate` at `0x180062df9`
- `netutils!NetApiBufferAllocate` at `0x180062df9`
- `CRYPTSP!SystemFunction007` at `0x180062d94`
- `CRYPTSP!SystemFunction007` at `0x180062d94`

## string_xrefs

- `0x180062ef0`: `NetrServerPasswordGet: Comp=%ws Acc=%ws returns 0x%lX\n`

## pseudocode

```c

```
