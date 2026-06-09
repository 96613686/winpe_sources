# GetDeviceIDString(CConfigServiceProvider2Impl *,ushort * *)

- ea: `0x18003f3d4`
- end: `0x18003f6ea`
- name: `?GetDeviceIDString@@YAJPEAVCConfigServiceProvider2Impl@@PEAPEAG@Z`
- size: `790`
- prototype: `__int64 __fastcall(struct CConfigServiceProvider2Impl *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, service_task`

## callers

- `0x180033640`
- `0x180037b70`

## callees

- `0x180008de0`
- `0x18000caf4`
- `0x18000d4d4`
- `0x1800384d0`
- `0x18003f3a0`
- `0x18003f3d4`
- `0x18003f6f0`
- `0x1800d11a4`
- `0x1800d157c`
- `0x180107010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003f693`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003f693`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003f67f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003f67f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003f46c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003f46c`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18003f57b`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18003f57b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003f54c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003f54c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003f44a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003f44a`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18003f493`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18003f493`
- `DMCmnUtils!BinaryToHexString` at `0x18003f6ce`
- `DMCmnUtils!BinaryToHexString` at `0x18003f6ce`
- `DMCfgUtils!SyncGetDeviceUniqueID` at `0x18003f617`
- `DMCfgUtils!SyncGetDeviceUniqueID` at `0x18003f64c`
- `DMCfgUtils!SyncGetDeviceUniqueID` at `0x18003f617`
- `DMCfgUtils!SyncGetDeviceUniqueID` at `0x18003f64c`

## pseudocode

```c

```
