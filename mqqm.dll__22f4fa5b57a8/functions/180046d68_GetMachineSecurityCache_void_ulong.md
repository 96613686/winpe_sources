# GetMachineSecurityCache(void *,ulong *)

- ea: `0x180046d68`
- end: `0x180046f29`
- name: `?GetMachineSecurityCache@@YAJPEAXPEAK@Z`
- size: `449`
- prototype: `__int64 __fastcall(void *Src, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180047070`

## callees

- `0x180009924`
- `0x18000d1f0`
- `0x18002c61c`
- `0x180046d68`
- `0x18009bd1c`
- `0x1800d6e3e`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180046dcc`
- `KERNEL32!LeaveCriticalSection` at `0x180046df0`
- `KERNEL32!LeaveCriticalSection` at `0x180046e7d`
- `KERNEL32!LeaveCriticalSection` at `0x180046eda`
- `KERNEL32!LeaveCriticalSection` at `0x180046f10`
- `KERNEL32!LeaveCriticalSection` at `0x180046dcc`
- `KERNEL32!LeaveCriticalSection` at `0x180046df0`
- `KERNEL32!LeaveCriticalSection` at `0x180046e7d`
- `KERNEL32!LeaveCriticalSection` at `0x180046eda`
- `KERNEL32!LeaveCriticalSection` at `0x180046f10`
- `mqsec!GetFalconKeyValue` at `0x180046e17`
- `mqsec!GetFalconKeyValue` at `0x180046e17`

## string_xrefs

- `0x180046e10`: `DsSecurityCache`

## pseudocode

```c

```
