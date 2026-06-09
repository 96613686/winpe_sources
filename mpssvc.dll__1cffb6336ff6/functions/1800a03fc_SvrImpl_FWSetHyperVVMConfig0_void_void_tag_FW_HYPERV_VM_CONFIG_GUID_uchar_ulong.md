# SvrImpl_FWSetHyperVVMConfig0(void *,void *,_tag_FW_HYPERV_VM_CONFIG,_GUID,uchar *,ulong)

- ea: `0x1800a03fc`
- end: `0x1800a08aa`
- name: `?SvrImpl_FWSetHyperVVMConfig0@@YAKPEAX0W4_tag_FW_HYPERV_VM_CONFIG@@U_GUID@@PEAEK@Z`
- size: `1198`
- prototype: `unsigned int __high(void *, void *, enum _tag_FW_HYPERV_VM_CONFIG, struct _GUID, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting`

## callers

- `0x1800c5140`

## callees

- `0x180008618`
- `0x180009720`
- `0x18000af3c`
- `0x180017110`
- `0x1800384a4`
- `0x180038504`
- `0x18005441c`
- `0x1800670c0`
- `0x18006f520`
- `0x1800738a6`
- `0x180080568`
- `0x18008cf10`
- `0x1800a03fc`
- `0x1800a2378`

## import_xrefs

- `fwbase!FwGetRpcCallersProcessImageName` at `0x1800a0505`
- `fwbase!FwGetRpcCallersProcessImageName` at `0x1800a0505`
- `fwbase!FwHResultToWindowsError` at `0x1800a0811`
- `fwbase!FwHResultToWindowsError` at `0x1800a0884`
- `fwbase!FwHResultToWindowsError` at `0x1800a0811`
- `fwbase!FwHResultToWindowsError` at `0x1800a0884`
- `fwbase!FwFree` at `0x1800a0866`
- `fwbase!FwFree` at `0x1800a0870`
- `fwbase!FwFree` at `0x1800a0866`
- `fwbase!FwFree` at `0x1800a0870`
- `FWPolicyIOMgr!FwSetHyperVVMConfigInRegistry` at `0x1800a0643`
- `FWPolicyIOMgr!FwSetHyperVVMConfigInRegistry` at `0x1800a0643`

## string_xrefs

- `0x1800a0607`: `mpssvc.dll`
- `0x1800a0475`: `SvrImpl_FWSetHyperVVMConfig0`
- `0x1800a0876`: `SvrImpl_FWSetHyperVVMConfig0`

## pseudocode

```c

```
