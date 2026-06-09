# CWinHttpProxyHandler::OpenWinhttpSessionWithoutProxy(wchar_t const *,ulong,bool,void * *,std::shared_ptr<std::tuple<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,ulong,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,ulong,ulong>> &)

- ea: `0x1800f1f90`
- end: `0x1800f2084`
- name: `?OpenWinhttpSessionWithoutProxy@CWinHttpProxyHandler@@AEAAKPEB_WK_NPEAPEAXAEAV?$shared_ptr@V?$tuple@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@KV12@V12@KK@std@@@std@@@Z`
- size: `244`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800f12f0`
- `0x1800f1a50`

## callees

- `0x18000adf0`
- `0x1800258b4`
- `0x18003e690`
- `0x1800f1f90`
- `0x1800f2c54`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800f1fee`
- `KERNEL32!GetLastError` at `0x1800f2059`
- `KERNEL32!GetLastError` at `0x1800f1fee`
- `KERNEL32!GetLastError` at `0x1800f2059`

## string_xrefs

- `0x1800f2020`: `Failed in WinHttpOpen with no proxy`

## pseudocode

```c

```
