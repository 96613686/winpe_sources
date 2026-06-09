# NetrServerGetTrustInfo

- ea: `0x18005e700`
- end: `0x18005eaeb`
- name: `NetrServerGetTrustInfo`
- size: `1003`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18005f150`

## callees

- `0x18000bd98`
- `0x18000e270`
- `0x180025708`
- `0x18002601c`
- `0x1800354d8`
- `0x18005378c`
- `0x18005e700`
- `0x18005f524`
- `0x180060b08`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18005e7d8`
- `ntdll!RtlLeaveCriticalSection` at `0x18005e808`
- `ntdll!RtlLeaveCriticalSection` at `0x18005e83a`
- `ntdll!RtlLeaveCriticalSection` at `0x18005e7d8`
- `ntdll!RtlLeaveCriticalSection` at `0x18005e808`
- `ntdll!RtlLeaveCriticalSection` at `0x18005e83a`
- `ntdll!RtlEnterCriticalSection` at `0x18005e7bc`
- `ntdll!RtlEnterCriticalSection` at `0x18005e7bc`
- `ntdll!RtlInitUnicodeString` at `0x18005e948`
- `ntdll!RtlInitUnicodeString` at `0x18005e948`
- `netutils!NetApiBufferFree` at `0x18005ea96`
- `netutils!NetApiBufferFree` at `0x18005ea96`
- `netutils!NetApiBufferAllocate` at `0x18005e9b5`
- `netutils!NetApiBufferAllocate` at `0x18005e9b5`
- `CRYPTSP!SystemFunction007` at `0x18005e956`
- `CRYPTSP!SystemFunction007` at `0x18005e956`

## string_xrefs

- `0x18005eaa0`: `NetrServerPasswordGet: Comp=%ws Acc=%ws returns 0x%lX\n`

## pseudocode

```c

```
