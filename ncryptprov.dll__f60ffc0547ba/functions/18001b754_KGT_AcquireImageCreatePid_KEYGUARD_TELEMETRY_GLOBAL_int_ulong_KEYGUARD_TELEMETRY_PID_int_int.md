# KGT_AcquireImageCreatePid(KEYGUARD_TELEMETRY_GLOBAL *,int,ulong,KEYGUARD_TELEMETRY_PID * *,int *,int *)

- ea: `0x18001b754`
- end: `0x18001b9e7`
- name: `?KGT_AcquireImageCreatePid@@YAPEAUKEYGUARD_TELEMETRY_IMAGE_T@@PEAUKEYGUARD_TELEMETRY_GLOBAL@@HKPEAPEAUKEYGUARD_TELEMETRY_PID@@PEAH2@Z`
- size: `659`
- prototype: `struct KEYGUARD_TELEMETRY_IMAGE_T *__usercall@<rax>(struct KEYGUARD_TELEMETRY_GLOBAL *@<rcx>, int@<edx>, unsigned int@<r8d>, struct KEYGUARD_TELEMETRY_PID **@<r9>, int *, int *)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting`

## callers

- `0x180028d5c`

## callees

- `0x18001b754`
- `0x18001ba54`
- `0x18001baf8`
- `0x18001c088`
- `0x18001c220`
- `0x18001c318`
- `0x18001c784`
- `0x180027aec`
- `0x180035fc8`
- `0x180040d2c`
- `0x180040e24`
- `0x180062310`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18001b7c4`
- `ntdll!RtlLeaveCriticalSection` at `0x18001b878`
- `ntdll!RtlLeaveCriticalSection` at `0x18001b91a`
- `ntdll!RtlLeaveCriticalSection` at `0x18001b9a4`
- `ntdll!RtlLeaveCriticalSection` at `0x18001b7c4`
- `ntdll!RtlLeaveCriticalSection` at `0x18001b878`
- `ntdll!RtlLeaveCriticalSection` at `0x18001b91a`
- `ntdll!RtlLeaveCriticalSection` at `0x18001b9a4`
- `ntdll!RtlEnterCriticalSection` at `0x18001b7a7`
- `ntdll!RtlEnterCriticalSection` at `0x18001b85b`
- `ntdll!RtlEnterCriticalSection` at `0x18001b8a7`
- `ntdll!RtlEnterCriticalSection` at `0x18001b96a`
- `ntdll!RtlEnterCriticalSection` at `0x18001b7a7`
- `ntdll!RtlEnterCriticalSection` at `0x18001b85b`
- `ntdll!RtlEnterCriticalSection` at `0x18001b8a7`
- `ntdll!RtlEnterCriticalSection` at `0x18001b96a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b804`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b9b8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b804`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b9b8`

## pseudocode

```c

```
