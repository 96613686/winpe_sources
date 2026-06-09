# CGenerateMSI::AddRemoteApplication(_GUID const &,ushort const *,ushort const *,ulong)

- ea: `0x18002cae0`
- end: `0x18002cc4d`
- name: `?AddRemoteApplication@CGenerateMSI@@UEAAJAEBU_GUID@@PEBG1K@Z`
- size: `365`
- prototype: `__int64 __fastcall(const unsigned __int16 **this, GUID *rguid, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180009ee0`
- `0x18002cae0`
- `0x18002dda8`
- `0x18002e428`
- `0x18002e620`
- `0x180050fd8`
- `0x180055550`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18002cc08`
- `msvcrt!_wcsicmp` at `0x18002cc08`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002cc22`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002cc22`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002cb1d`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002cb1d`

## pseudocode

```c

```
