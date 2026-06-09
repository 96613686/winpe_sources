# NT_SERVICE::RunService(ulong,ulong)

- ea: `0x180006978`
- end: `0x180006bee`
- name: `?RunService@NT_SERVICE@@QEAAJKK@Z`
- size: `630`
- prototype: `__int64 __fastcall(NT_SERVICE *__hidden this, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180005940`

## callees

- `0x1800064c8`
- `0x18000660c`
- `0x1800066a0`
- `0x180006978`
- `0x180049010`

## import_xrefs

- `KERNEL32!WaitForMultipleObjects` at `0x180006a59`
- `KERNEL32!WaitForMultipleObjects` at `0x180006ac3`
- `KERNEL32!WaitForMultipleObjects` at `0x180006a59`
- `KERNEL32!WaitForMultipleObjects` at `0x180006ac3`
- `iisutil!PuDbgPrint` at `0x180006b94`
- `iisutil!PuDbgPrint` at `0x180006bdc`
- `iisutil!PuDbgPrint` at `0x180006b94`
- `iisutil!PuDbgPrint` at `0x180006bdc`

## string_xrefs

- `0x18000699b`: `inetsrv\iis\iisrearc\ftp\server\core\nt_service.cxx`
- `0x1800069bd`: `Error in NT_SERVICE::Initialize().  hr = %x\n`
- `0x180006992`: `NT_SERVICE::RunService`
- `0x1800069f3`: `Error in NT_SERVICE::IndicatePending().  hr = %x\n`
- `0x180006b5f`: `Error in NT_SERVICE::IndicateComplete().  hr = %x\n`
- `0x180006bcd`: `Error in IndicateComplete().  hr = %x\n`

## pseudocode

```c

```
