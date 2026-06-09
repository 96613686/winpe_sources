# RegOpenKeyExInternalW

- ea: `0x18005e320`
- end: `0x18005e7d6`
- name: `RegOpenKeyExInternalW`
- size: `1206`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, PCWSTR SourceString@<rdx>, PHANDLE, __int64)`
- caller_count: `42`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x180014b30`
- `0x18002ecb4`
- `0x180034380`
- `0x180035ca0`
- `0x1800543b0`
- `0x1800579c0`
- `0x180058240`
- `0x18005b480`
- `0x18005c0f0`
- `0x18005e2f0`
- `0x180088558`
- `0x1800a1190`
- `0x1800a1c08`
- `0x1800a37f0`
- `0x1800a3c00`
- `0x1800a3ef0`
- `0x1800a4384`
- `0x1800a5010`
- `0x1800a5620`
- `0x1800a5af0`
- `0x1800a7fec`
- `0x1800a85ec`
- `0x1800ac600`
- `0x1800ad890`
- `0x1800bfdb0`
- `0x1800e0fa0`
- `0x1800e45f0`
- `0x1800e4a60`
- `0x1800e608c`
- `0x1800fe37c`
- `0x18010b270`
- `0x180110680`
- `0x180114f10`
- `0x18012dbb0`
- `0x18012dcbc`
- `0x18013cc80`
- `0x18013cf50`
- `0x18014c974`
- `0x18015ab5c`
- `0x180162b5c`
- `0x18017f018`
- `0x18018d3d8`

## callees

- `0x18002e0c4`
- `0x18005e040`
- `0x18005e320`
- `0x18005e7e0`
- `0x18005ebc0`
- `0x180060124`
- `0x180136e28`

## import_xrefs

- `ntdll!RtlEnterCriticalSection` at `0x18005e4ce`
- `ntdll!RtlEnterCriticalSection` at `0x18005e4ce`
- `ntdll!RtlLeaveCriticalSection` at `0x18005e504`
- `ntdll!RtlLeaveCriticalSection` at `0x18005e504`
- `ntdll!RtlNtStatusToDosError` at `0x18005e6ce`
- `ntdll!RtlNtStatusToDosError` at `0x18005e7a1`
- `ntdll!RtlNtStatusToDosError` at `0x18005e6ce`
- `ntdll!RtlNtStatusToDosError` at `0x18005e7a1`
- `ntdll!RtlRunOnceExecuteOnce` at `0x18005e4b6`
- `ntdll!RtlRunOnceExecuteOnce` at `0x18005e4b6`
- `ntdll!RtlInitUnicodeStringEx` at `0x18005e40b`
- `ntdll!RtlInitUnicodeStringEx` at `0x18005e40b`
- `ntdll!NtClose` at `0x18005e515`
- `ntdll!NtClose` at `0x18005e515`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18005e5a7`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18005e5a7`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18005e5de`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18005e5de`
- `ntdll!RtlFreeHeap` at `0x18005e58f`
- `ntdll!RtlFreeHeap` at `0x18005e60d`
- `ntdll!RtlFreeHeap` at `0x18005e58f`
- `ntdll!RtlFreeHeap` at `0x18005e60d`
- `ext-ms-win-advapi32-registry-l1-1-0!BaseRegGetVersion` at `0x18005e765`
- `ext-ms-win-advapi32-registry-l1-1-0!BaseRegGetVersion` at `0x18005e765`
- `ext-ms-win-advapi32-registry-l1-1-0!PerfRegCloseKey` at `0x18005e673`
- `ext-ms-win-advapi32-registry-l1-1-0!PerfRegCloseKey` at `0x18005e673`
- `ext-ms-win-advapi32-registry-l1-1-0!BaseRegOpenKey` at `0x18005e719`
- `ext-ms-win-advapi32-registry-l1-1-0!BaseRegOpenKey` at `0x18005e719`

## pseudocode

```c

```
