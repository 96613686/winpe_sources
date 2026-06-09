# SvrImpl_FWEnumConnectionSecurityRules2_20(void *,void *,ulong,ulong,ushort,ulong *,_tag_FW_CS_RULE * *)

- ea: `0x18009b2e0`
- end: `0x18009b6a5`
- name: `?SvrImpl_FWEnumConnectionSecurityRules2_20@@YAKPEAX0KKGPEAKPEAPEAU_tag_FW_CS_RULE@@@Z`
- size: `965`
- prototype: `unsigned int __usercall@<eax>(void *@<rcx>, void *@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, unsigned __int16, unsigned int *, struct _tag_FW_CS_RULE **)`
- caller_count: `3`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800c16b0`
- `0x1800c17b0`
- `0x1800c18b0`

## callees

- `0x180003bc8`
- `0x180008618`
- `0x180009460`
- `0x180009720`
- `0x18000a0c0`
- `0x18000ae9c`
- `0x18000af3c`
- `0x18000cdf8`
- `0x180017110`
- `0x180055750`
- `0x18009b2e0`
- `0x1800a1730`

## import_xrefs

- `fwbase!FwHResultToWindowsError` at `0x18009b655`
- `fwbase!FwHResultToWindowsError` at `0x18009b68e`
- `fwbase!FwHResultToWindowsError` at `0x18009b655`
- `fwbase!FwHResultToWindowsError` at `0x18009b68e`
- `FWPolicyIOMgr!FwReduceObjectsToVersion` at `0x18009b56c`
- `FWPolicyIOMgr!FwReduceObjectsToVersion` at `0x18009b56c`
- `FWPolicyIOMgr!FWResolveGPONames` at `0x18009b5c5`
- `FWPolicyIOMgr!FWResolveGPONames` at `0x18009b5c5`
- `FWPolicyIOMgr!FWGPUnlockEx` at `0x18009b5fe`
- `FWPolicyIOMgr!FWGPUnlockEx` at `0x18009b5fe`
- `FWPolicyIOMgr!FwEnumRules` at `0x18009b43e`
- `FWPolicyIOMgr!FwEnumRules` at `0x18009b43e`
- `FWPolicyIOMgr!FWGPLock` at `0x18009b354`
- `FWPolicyIOMgr!FWGPLock` at `0x18009b354`

## string_xrefs

- `0x18009b32f`: `SvrImpl_FWEnumConnectionSecurityRules2_20`
- `0x18009b5d9`: `SvrImpl_FWEnumConnectionSecurityRules2_20`
- `0x18009b5f4`: `SvrImpl_FWEnumConnectionSecurityRules2_20`
- `0x18009b680`: `SvrImpl_FWEnumConnectionSecurityRules2_20`

## pseudocode

```c

```
