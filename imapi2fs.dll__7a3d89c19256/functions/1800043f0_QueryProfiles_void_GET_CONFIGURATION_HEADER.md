# QueryProfiles(void *,_GET_CONFIGURATION_HEADER * *)

- ea: `0x1800043f0`
- end: `0x180004752`
- name: `?QueryProfiles@@YAEPEAXPEAPEAU_GET_CONFIGURATION_HEADER@@@Z`
- size: `866`
- prototype: `unsigned __int8 __fastcall(HANDLE FileHandle, struct _GET_CONFIGURATION_HEADER **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x1800042d0`

## callees

- `0x1800043f0`
- `0x1800063b8`
- `0x180028568`
- `0x18008170e`

## import_xrefs

- `ntdll!NtDeviceIoControlFile` at `0x1800044ec`
- `ntdll!NtDeviceIoControlFile` at `0x18000464c`
- `ntdll!NtDeviceIoControlFile` at `0x1800044ec`
- `ntdll!NtDeviceIoControlFile` at `0x18000464c`
- `ntdll!RtlFreeHeap` at `0x1800045b0`
- `ntdll!RtlFreeHeap` at `0x180004720`
- `ntdll!RtlFreeHeap` at `0x1800045b0`
- `ntdll!RtlFreeHeap` at `0x180004720`
- `ntdll!RtlAllocateHeap` at `0x180004439`
- `ntdll!RtlAllocateHeap` at `0x1800045c8`
- `ntdll!RtlAllocateHeap` at `0x180004439`
- `ntdll!RtlAllocateHeap` at `0x1800045c8`

## pseudocode

```c

```
