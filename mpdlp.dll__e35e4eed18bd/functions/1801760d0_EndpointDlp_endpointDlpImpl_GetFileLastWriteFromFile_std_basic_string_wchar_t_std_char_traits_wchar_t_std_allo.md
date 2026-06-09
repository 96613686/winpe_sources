# EndpointDlp::endpointDlpImpl::GetFileLastWriteFromFile(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,unsigned __int64 &)

- ea: `0x1801760d0`
- end: `0x180176267`
- name: `?GetFileLastWriteFromFile@endpointDlpImpl@EndpointDlp@@AEBAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEA_K@Z`
- size: `407`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18017e1a0`

## callees

- `0x180006980`
- `0x1800301a0`
- `0x180103fec`
- `0x18010cb40`
- `0x1801760d0`

## import_xrefs

- `KERNEL32!GetFileInformationByHandleEx` at `0x1801761d1`
- `KERNEL32!GetFileInformationByHandleEx` at `0x1801761d1`
- `KERNEL32!GetLastError` at `0x1801761db`
- `KERNEL32!GetLastError` at `0x1801761db`
- `KERNEL32!CloseHandle` at `0x18017619f`
- `KERNEL32!CloseHandle` at `0x180176240`
- `KERNEL32!CloseHandle` at `0x18017619f`
- `KERNEL32!CloseHandle` at `0x180176240`

## string_xrefs

- `0x180176160`: `GetFileLastWriteTimeFromEA: Failed to get last modification time from file attribute`
- `0x18017620b`: `GetFileLastWriteTimeFromEA: Failed to get last modification time from file attribute`

## pseudocode

```c

```
