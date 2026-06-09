# FrsContentSetInfo::InvokeGetStatus(ATL::CComPtr<IWbemClassObject> &,ATL::CComPtr<IWbemContext> &,ATL::CComPtr<IWbemObjectSink> &)

- ea: `0x1400e2be8`
- end: `0x1400e30a4`
- name: `?InvokeGetStatus@FrsContentSetInfo@@IEAAJAEAV?$CComPtr@UIWbemClassObject@@@ATL@@AEAV?$CComPtr@UIWbemContext@@@3@AEAV?$CComPtr@UIWbemObjectSink@@@3@@Z`
- size: `1212`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400ddbb0`

## callees

- `0x1400036a0`
- `0x14000be44`
- `0x14000c910`
- `0x14000e34c`
- `0x14000ee94`
- `0x140010680`
- `0x14001c31c`
- `0x140029974`
- `0x14005c110`
- `0x1400d20ac`
- `0x1400d2304`
- `0x1400e2be8`
- `0x1400ebff4`
- `0x1401b3d14`
- `0x1401b9494`
- `0x140223010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1400e2d63`
- `KERNEL32!GetCurrentThreadId` at `0x1400e2dcc`
- `KERNEL32!GetCurrentThreadId` at `0x1400e2e46`
- `KERNEL32!GetCurrentThreadId` at `0x1400e2d63`
- `KERNEL32!GetCurrentThreadId` at `0x1400e2dcc`
- `KERNEL32!GetCurrentThreadId` at `0x1400e2e46`
- `OLEAUT32!__imp_VariantInit` at `0x1400e2f15`
- `OLEAUT32!__imp_VariantInit` at `0x1400e2f26`
- `OLEAUT32!__imp_VariantInit` at `0x1400e2f15`
- `OLEAUT32!__imp_VariantInit` at `0x1400e2f26`
- `OLEAUT32!__imp_VariantClear` at `0x1400e2cf0`
- `OLEAUT32!__imp_VariantClear` at `0x1400e3003`
- `OLEAUT32!__imp_VariantClear` at `0x1400e3014`
- `OLEAUT32!__imp_VariantClear` at `0x1400e2cf0`
- `OLEAUT32!__imp_VariantClear` at `0x1400e3003`
- `OLEAUT32!__imp_VariantClear` at `0x1400e3014`
- `OLEAUT32!__imp_VariantChangeType` at `0x1400e2f52`
- `OLEAUT32!__imp_VariantChangeType` at `0x1400e2fab`
- `OLEAUT32!__imp_VariantChangeType` at `0x1400e2f52`
- `OLEAUT32!__imp_VariantChangeType` at `0x1400e2fab`

## string_xrefs

- `0x1400e2d3e`: `[CLUSTER] Processing WMI call to DfsrReplicatedFolderInfo::GetStatus(). csId:%?`
- `0x1400e2ecf`: `[CLUSTER] Failed to query content set's status. csId:%? Error:%?`

## pseudocode

```c

```
