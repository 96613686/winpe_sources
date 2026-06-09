# CWinHttpProxyHandler::SetNamedProxyServerOption(wchar_t const *,ulong,bool,void * *,std::shared_ptr<std::tuple<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,ulong,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,ulong,ulong>> &)

- ea: `0x1800f2084`
- end: `0x1800f222a`
- name: `?SetNamedProxyServerOption@CWinHttpProxyHandler@@AEAAKPEB_WK_NPEAPEAXAEAV?$shared_ptr@V?$tuple@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@KV12@V12@KK@std@@@std@@@Z`
- size: `422`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1800f1a50`

## callees

- `0x18000adf0`
- `0x1800258b4`
- `0x18003e690`
- `0x180063814`
- `0x1800f2084`
- `0x1800f2c54`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800f2144`
- `KERNEL32!GetLastError` at `0x1800f217e`
- `KERNEL32!GetLastError` at `0x1800f2144`
- `KERNEL32!GetLastError` at `0x1800f217e`
- `WINHTTP!WinHttpSetOption` at `0x1800f2136`
- `WINHTTP!WinHttpSetOption` at `0x1800f2136`

## string_xrefs

- `0x1800f21c6`: `Error: InitSession failed in WinHttpOpen with named proxy`

## pseudocode

```c

```
