# BaseRegEnumKeyOld

- ea: `0x180062d50`
- end: `0x180063c54`
- name: `BaseRegEnumKeyOld`
- size: `3844`
- prototype: `__int64 __usercall@<rax>(HANDLE KeyHandle@<rcx>, ULONG Index@<edx>, __int64)`
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800a41b0`
- `0x1801059d0`

## callees

- `0x180060124`
- `0x180061d14`
- `0x1800621e0`
- `0x180062230`
- `0x180062d50`
- `0x180063c60`
- `0x180063f98`
- `0x1800642b0`
- `0x1800642d8`
- `0x180136e28`
- `0x180194eb9`
- `0x180194ec5`
- `0x180194f10`

## import_xrefs

- `ntdll!RtlEnterCriticalSection` at `0x180062f8a`
- `ntdll!RtlEnterCriticalSection` at `0x1800633f8`
- `ntdll!RtlEnterCriticalSection` at `0x180062f8a`
- `ntdll!RtlEnterCriticalSection` at `0x1800633f8`
- `ntdll!RtlLeaveCriticalSection` at `0x18006359b`
- `ntdll!RtlLeaveCriticalSection` at `0x1800635ae`
- `ntdll!RtlLeaveCriticalSection` at `0x18006359b`
- `ntdll!RtlLeaveCriticalSection` at `0x1800635ae`
- `ntdll!RtlNtStatusToDosError` at `0x180062eb0`
- `ntdll!RtlNtStatusToDosError` at `0x180062eb0`
- `ntdll!NtEnumerateKey` at `0x180062e05`
- `ntdll!NtEnumerateKey` at `0x180063276`
- `ntdll!NtEnumerateKey` at `0x180063476`
- `ntdll!NtEnumerateKey` at `0x1800638e3`
- `ntdll!NtEnumerateKey` at `0x180063a6d`
- `ntdll!NtEnumerateKey` at `0x180063b28`
- `ntdll!NtEnumerateKey` at `0x180062e05`
- `ntdll!NtEnumerateKey` at `0x180063276`
- `ntdll!NtEnumerateKey` at `0x180063476`
- `ntdll!NtEnumerateKey` at `0x1800638e3`
- `ntdll!NtEnumerateKey` at `0x180063a6d`
- `ntdll!NtEnumerateKey` at `0x180063b28`
- `ntdll!RtlRunOnceExecuteOnce` at `0x180062f6e`
- `ntdll!RtlRunOnceExecuteOnce` at `0x180063bf5`
- `ntdll!RtlRunOnceExecuteOnce` at `0x180062f6e`
- `ntdll!RtlRunOnceExecuteOnce` at `0x180063bf5`
- `ntdll!RtlCompareUnicodeString` at `0x180063173`
- `ntdll!RtlCompareUnicodeString` at `0x180063173`
- `ntdll!RtlFreeHeap` at `0x180062ea2`
- `ntdll!RtlFreeHeap` at `0x180063206`
- `ntdll!RtlFreeHeap` at `0x1800634ff`
- `ntdll!RtlFreeHeap` at `0x180063619`
- `ntdll!RtlFreeHeap` at `0x180062ea2`
- `ntdll!RtlFreeHeap` at `0x180063206`
- `ntdll!RtlFreeHeap` at `0x1800634ff`
- `ntdll!RtlFreeHeap` at `0x180063619`
- `ntdll!RtlAllocateHeap` at `0x180062f2e`
- `ntdll!RtlAllocateHeap` at `0x180063a28`
- `ntdll!RtlAllocateHeap` at `0x180063a98`
- `ntdll!RtlAllocateHeap` at `0x180062f2e`
- `ntdll!RtlAllocateHeap` at `0x180063a28`
- `ntdll!RtlAllocateHeap` at `0x180063a98`
- `ext-ms-win-advapi32-registry-l1-1-0!PerfRegEnumKey` at `0x180062f0a`
- `ext-ms-win-advapi32-registry-l1-1-0!PerfRegEnumKey` at `0x180062f0a`

## pseudocode

```c

```
