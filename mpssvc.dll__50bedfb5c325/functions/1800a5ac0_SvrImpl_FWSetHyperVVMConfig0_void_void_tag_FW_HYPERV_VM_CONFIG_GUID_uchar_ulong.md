# SvrImpl_FWSetHyperVVMConfig0(void *,void *,_tag_FW_HYPERV_VM_CONFIG,_GUID,uchar *,ulong)

- ea: `0x1800a5ac0`
- end: `0x1800a5f93`
- name: `?SvrImpl_FWSetHyperVVMConfig0@@YAKPEAX0W4_tag_FW_HYPERV_VM_CONFIG@@U_GUID@@PEAEK@Z`
- size: `1235`
- prototype: `unsigned int __high(void *, void *, enum _tag_FW_HYPERV_VM_CONFIG, struct _GUID, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting`

## callers

- `0x1800cc470`

## callees

- `0x180007b58`
- `0x180008d60`
- `0x18000a710`
- `0x180011098`
- `0x180011100`
- `0x1800192e0`
- `0x180059714`
- `0x18006a710`
- `0x1800729c0`
- `0x180076d66`
- `0x18008462c`
- `0x1800917f4`
- `0x1800a5ac0`
- `0x1800a7b68`

## import_xrefs

- `fwbase!FwHResultToWindowsError` at `0x1800a5ee1`
- `fwbase!FwHResultToWindowsError` at `0x1800a5f66`
- `fwbase!FwHResultToWindowsError` at `0x1800a5ee1`
- `fwbase!FwHResultToWindowsError` at `0x1800a5f66`
- `fwbase!FwGetRpcCallersProcessImageName` at `0x1800a5bc9`
- `fwbase!FwGetRpcCallersProcessImageName` at `0x1800a5bc9`
- `fwbase!FwFree` at `0x1800a5f3c`
- `fwbase!FwFree` at `0x1800a5f4c`
- `fwbase!FwFree` at `0x1800a5f3c`
- `fwbase!FwFree` at `0x1800a5f4c`
- `FWPolicyIOMgr!FwSetHyperVVMConfigInRegistry` at `0x1800a5d0d`
- `FWPolicyIOMgr!FwSetHyperVVMConfigInRegistry` at `0x1800a5d0d`

## string_xrefs

- `0x1800a5cd1`: `mpssvc.dll`
- `0x1800a5b39`: `SvrImpl_FWSetHyperVVMConfig0`
- `0x1800a5f58`: `SvrImpl_FWSetHyperVVMConfig0`

## pseudocode

```c

```
