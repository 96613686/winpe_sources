# CMsRdpClientShell::LaunchClientProcess(void)

- ea: `0x1803ec240`
- end: `0x1803ecaa6`
- name: `?LaunchClientProcess@CMsRdpClientShell@@AEAAJXZ`
- size: `2150`
- prototype: `__int64 __fastcall(CMsRdpClientShell *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1803ebfe0`

## callees

- `0x180039c98`
- `0x180039ce4`
- `0x1800d1db0`
- `0x1800dafe4`
- `0x1800e9b1c`
- `0x1800ebae0`
- `0x1803eba00`
- `0x1803ebc20`
- `0x1803ec240`
- `0x1804a9e54`
- `0x1804ab10c`
- `0x180688fc0`
- `0x18068c010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1803ec4fc`
- `KERNEL32!GetLastError` at `0x1803ec4fc`
- `KERNEL32!LocalFree` at `0x1803ec753`
- `KERNEL32!LocalFree` at `0x1803ec763`
- `KERNEL32!LocalFree` at `0x1803ec753`
- `KERNEL32!LocalFree` at `0x1803ec763`
- `USER32!AllowSetForegroundWindow` at `0x1803ec4e4`
- `USER32!AllowSetForegroundWindow` at `0x1803ec4e4`
- `OLEAUT32!__imp_SysAllocString` at `0x1803ec68f`
- `OLEAUT32!__imp_SysAllocString` at `0x1803ec8c9`
- `OLEAUT32!__imp_SysAllocString` at `0x1803ec931`
- `OLEAUT32!__imp_SysAllocString` at `0x1803ec96c`
- `OLEAUT32!__imp_SysAllocString` at `0x1803ec68f`
- `OLEAUT32!__imp_SysAllocString` at `0x1803ec8c9`
- `OLEAUT32!__imp_SysAllocString` at `0x1803ec931`
- `OLEAUT32!__imp_SysAllocString` at `0x1803ec96c`
- `OLEAUT32!__imp_SysFreeString` at `0x1803ec703`
- `OLEAUT32!__imp_SysFreeString` at `0x1803ec715`
- `OLEAUT32!__imp_SysFreeString` at `0x1803ec723`
- `OLEAUT32!__imp_SysFreeString` at `0x1803ec735`
- `OLEAUT32!__imp_SysFreeString` at `0x1803ec743`
- `OLEAUT32!__imp_SysFreeString` at `0x1803ec703`
- `OLEAUT32!__imp_SysFreeString` at `0x1803ec715`
- `OLEAUT32!__imp_SysFreeString` at `0x1803ec723`
- `OLEAUT32!__imp_SysFreeString` at `0x1803ec735`
- `OLEAUT32!__imp_SysFreeString` at `0x1803ec743`
- `OLE32!CoCreateInstance` at `0x1803ec3fe`
- `OLE32!CoCreateInstance` at `0x1803ec3fe`

## string_xrefs

- `0x1803ec7dc`: `WriteRdpFileContentsToDisk failed`
- `0x1803ec4d4`: `spMSTSWebProxy->GetProcessId failed!`
- `0x1803ec43f`: `CoCreateInstance failed!`
- `0x1803ec876`: `CreateCommandLine failed`

## pseudocode

```c

```
