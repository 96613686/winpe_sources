# wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)

- ea: `0x180009cb0`
- end: `0x180009d08`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z`
- size: `88`
- prototype: `void __fastcall(HKEY *, HKEY)`
- caller_count: `5`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180009488`
- `0x180009bcc`
- `0x180009c04`
- `0x18000ebe0`
- `0x1800123ac`

## callees

- `0x180009cb0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009ce5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009ce5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009cf8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009cf8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009cf0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009cf0`

## pseudocode

```c

```
