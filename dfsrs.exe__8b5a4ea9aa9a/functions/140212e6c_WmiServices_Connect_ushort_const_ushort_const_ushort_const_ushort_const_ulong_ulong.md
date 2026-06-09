# WmiServices::Connect(ushort const *,ushort const *,ushort const *,ushort const *,ulong,ulong)

- ea: `0x140212e6c`
- end: `0x140213097`
- name: `?Connect@WmiServices@@QEAAPEAVFrsStatus@@PEBG000KK@Z`
- size: `555`
- prototype: `struct FrsStatus *__fastcall(WmiServices *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x1401fd168`

## callees

- `0x14000be44`
- `0x14005c01c`
- `0x1401b9494`
- `0x140212cdc`
- `0x140212e6c`
- `0x1402134b0`
- `0x140223010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140212fb7`
- `KERNEL32!GetCurrentThreadId` at `0x140213034`
- `KERNEL32!GetCurrentThreadId` at `0x140212fb7`
- `KERNEL32!GetCurrentThreadId` at `0x140213034`
- `ole32!CoCreateInstance` at `0x140212eaf`
- `ole32!CoCreateInstance` at `0x140212eaf`
- `OLEAUT32!__imp_SysFreeString` at `0x140213004`
- `OLEAUT32!__imp_SysFreeString` at `0x140213015`
- `OLEAUT32!__imp_SysFreeString` at `0x140213026`
- `OLEAUT32!__imp_SysFreeString` at `0x140213004`
- `OLEAUT32!__imp_SysFreeString` at `0x140213015`
- `OLEAUT32!__imp_SysFreeString` at `0x140213026`
- `OLEAUT32!__imp_SysStringLen` at `0x140212f2d`
- `OLEAUT32!__imp_SysStringLen` at `0x140212f46`
- `OLEAUT32!__imp_SysStringLen` at `0x140212f5f`
- `OLEAUT32!__imp_SysStringLen` at `0x140212f2d`
- `OLEAUT32!__imp_SysStringLen` at `0x140212f46`
- `OLEAUT32!__imp_SysStringLen` at `0x140212f5f`

## string_xrefs

- `0x140212fd5`: `WmiServices::Connect`
- `0x140213052`: `WmiServices::Connect`

## pseudocode

```c

```
