# DdmModernDevice::SetFramingEx(_RAS_FRAMING_INFO *)

- ea: `0x180044df0`
- end: `0x180045016`
- name: `?SetFramingEx@DdmModernDevice@@UEAAKPEAU_RAS_FRAMING_INFO@@@Z`
- size: `550`
- prototype: `unsigned int __fastcall(DdmModernDevice *__hidden this, struct _RAS_FRAMING_INFO *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180007c50`
- `0x180044df0`
- `0x180071cec`
- `0x18008c5f2`
- `0x18008c630`

## import_xrefs

- `msvcrt!_itow_s` at `0x180044e92`
- `msvcrt!_itow_s` at `0x180044fa3`
- `msvcrt!_itow_s` at `0x180044e92`
- `msvcrt!_itow_s` at `0x180044fa3`
- `KERNEL32!DeviceIoControl` at `0x180044f64`
- `KERNEL32!DeviceIoControl` at `0x180044f64`
- `KERNEL32!GetLastError` at `0x180044f72`
- `KERNEL32!GetLastError` at `0x180044f72`

## string_xrefs

- `0x180044fac`: `IOCTL_NDISWAN_SET_LINK_INFO failed with error 0x%x`

## pseudocode

```c

```
