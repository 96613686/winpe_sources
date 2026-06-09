# CWinHttpProxyHandler::AutomaticProxyConfiguration(wchar_t const *,wchar_t const *,ulong,bool,void * *,std::shared_ptr<std::tuple<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,ulong,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,ulong,ulong>> &,bool &)

- ea: `0x1800f12f0`
- end: `0x1800f166b`
- name: `?AutomaticProxyConfiguration@CWinHttpProxyHandler@@AEAAKPEB_W0K_NPEAPEAXAEAV?$shared_ptr@V?$tuple@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@KV12@V12@KK@std@@@std@@AEA_N@Z`
- size: `891`
- prototype: `__int64 __usercall@<rax>(CWinHttpProxyHandler *this@<rcx>, LPCWSTR lpcwszUrl@<rdx>, char, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800f1a50`

## callees

- `0x18000adf0`
- `0x18000c2dc`
- `0x1800258b4`
- `0x18003aa9c`
- `0x18003e690`
- `0x180063814`
- `0x1800d157c`
- `0x1800d6e88`
- `0x1800f120c`
- `0x1800f12f0`
- `0x1800f17e0`
- `0x1800f1f90`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800f163c`
- `KERNEL32!GetLastError` at `0x1800f163c`
- `WINHTTP!WinHttpGetProxyForUrl` at `0x1800f149b`
- `WINHTTP!WinHttpGetProxyForUrl` at `0x1800f149b`
- `WINHTTP!WinHttpSetOption` at `0x1800f1632`
- `WINHTTP!WinHttpSetOption` at `0x1800f1632`

## string_xrefs

- `0x1800f13fe`: `InitSession detected proxy, and auto config URL`

## pseudocode

```c

```
