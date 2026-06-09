# MQpDeviceIoControl(void *,ulong,void *,ulong,void *,ulong,_OVERLAPPED *)

- ea: `0x1800056e8`
- end: `0x18000574d`
- name: `?MQpDeviceIoControl@@YAJPEAXK0K0KPEAU_OVERLAPPED@@@Z`
- size: `101`
- prototype: `int(void *, unsigned int, void *, unsigned int, void *, unsigned int, struct _OVERLAPPED *)`
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180008550`
- `0x18000a8b8`
- `0x18000dc48`
- `0x18001ba48`
- `0x18001cbb0`
- `0x18001d138`

## import_xrefs

- `ntdll!NtDeviceIoControlFile` at `0x180005741`
- `ntdll!NtDeviceIoControlFile` at `0x180005741`

## pseudocode

```c

```
