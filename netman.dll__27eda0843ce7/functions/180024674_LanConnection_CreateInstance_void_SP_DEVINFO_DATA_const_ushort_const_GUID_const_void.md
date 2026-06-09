# LanConnection::CreateInstance(void *,_SP_DEVINFO_DATA const &,ushort const *,_GUID const &,void * *)

- ea: `0x180024674`
- end: `0x180024756`
- name: `?CreateInstance@LanConnection@@SAJPEAXAEBU_SP_DEVINFO_DATA@@PEBGAEBU_GUID@@PEAPEAX@Z`
- size: `226`
- prototype: `__int64 __usercall@<rax>(HDEVINFO DeviceInfoSet@<rcx>, const struct _SP_DEVINFO_DATA *@<rdx>, const unsigned __int16 *@<r8>, const struct _GUID *@<r9>, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x18001e6c8`

## callees

- `0x18000538c`
- `0x18002459c`
- `0x180024674`
- `0x180025ab4`
- `0x180036010`

## import_xrefs

- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x180024714`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x180024714`

## pseudocode

```c

```
