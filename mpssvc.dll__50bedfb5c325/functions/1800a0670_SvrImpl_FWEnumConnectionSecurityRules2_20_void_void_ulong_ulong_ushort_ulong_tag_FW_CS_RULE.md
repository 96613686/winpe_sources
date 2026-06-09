# SvrImpl_FWEnumConnectionSecurityRules2_20(void *,void *,ulong,ulong,ushort,ulong *,_tag_FW_CS_RULE * *)

- ea: `0x1800a0670`
- end: `0x1800a0a60`
- name: `?SvrImpl_FWEnumConnectionSecurityRules2_20@@YAKPEAX0KKGPEAKPEAPEAU_tag_FW_CS_RULE@@@Z`
- size: `1008`
- prototype: `unsigned int __usercall@<eax>(void *@<rcx>, void *@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, unsigned __int16, unsigned int *, struct _tag_FW_CS_RULE **)`
- caller_count: `3`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800c8600`
- `0x1800c8710`
- `0x1800c8820`

## callees

- `0x180003da4`
- `0x180007b58`
- `0x180008a80`
- `0x180008d60`
- `0x1800097b0`
- `0x18000a66c`
- `0x18000a710`
- `0x18000c6c0`
- `0x1800192e0`
- `0x180059ac8`
- `0x1800a0670`
- `0x1800a6ec8`

## import_xrefs

- `fwbase!FwHResultToWindowsError` at `0x1800a0a03`
- `fwbase!FwHResultToWindowsError` at `0x1800a0a42`
- `fwbase!FwHResultToWindowsError` at `0x1800a0a03`
- `fwbase!FwHResultToWindowsError` at `0x1800a0a42`
- `FWPolicyIOMgr!FwReduceObjectsToVersion` at `0x1800a0908`
- `FWPolicyIOMgr!FwReduceObjectsToVersion` at `0x1800a0908`
- `FWPolicyIOMgr!FWResolveGPONames` at `0x1800a0967`
- `FWPolicyIOMgr!FWResolveGPONames` at `0x1800a0967`
- `FWPolicyIOMgr!FWGPUnlockEx` at `0x1800a09a6`
- `FWPolicyIOMgr!FWGPUnlockEx` at `0x1800a09a6`
- `FWPolicyIOMgr!FwEnumRules` at `0x1800a07d4`
- `FWPolicyIOMgr!FwEnumRules` at `0x1800a07d4`
- `FWPolicyIOMgr!FWGPLock` at `0x1800a06e4`
- `FWPolicyIOMgr!FWGPLock` at `0x1800a06e4`

## string_xrefs

- `0x1800a06bf`: `SvrImpl_FWEnumConnectionSecurityRules2_20`
- `0x1800a0981`: `SvrImpl_FWEnumConnectionSecurityRules2_20`
- `0x1800a099c`: `SvrImpl_FWEnumConnectionSecurityRules2_20`
- `0x1800a0a34`: `SvrImpl_FWEnumConnectionSecurityRules2_20`

## pseudocode

```c

```
