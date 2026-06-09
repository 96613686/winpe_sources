# HNS::Service::SharedMemory::RegistryStore::EnumerateSubStore(Vml::VmRegistryKey &,bool,std::function<void (wil::basic_zstring_view<ushort>,bool,uchar *,ulong const &)> const &)

- ea: `0x1801a3fa8`
- end: `0x1801a4207`
- name: `?EnumerateSubStore@RegistryStore@SharedMemory@Service@HNS@@AEAAXAEAVVmRegistryKey@Vml@@_NAEBV?$function@$$A6AXV?$basic_zstring_view@G@wil@@_NPEAEAEBK@Z@std@@@Z`
- size: `607`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1801a1080`

## callees

- `0x18005f0c0`
- `0x18006c530`
- `0x18007cbc8`
- `0x18007df4c`
- `0x180088908`
- `0x1801a3fa8`
- `0x1801a44ec`
- `0x1801a4610`
- `0x1802b7010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1801a41a1`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1801a41a1`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1801a409a`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1801a409a`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1801a4046`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1801a418e`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1801a4046`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1801a418e`

## string_xrefs

- `0x1801a41dc`: `onecore\vm\common\vml\VmRegistry.h`
- `0x1801a41f5`: `onecore\vm\common\vml\VmRegistry.h`

## pseudocode

```c

```
