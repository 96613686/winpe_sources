# SvrImpl_FWSetFirewallRule2_33(void *,void *,_tag_FW_RULE *,_tag_FW_RULE_STATUS *)

- ea: `0x1800558ec`
- end: `0x180055e34`
- name: `?SvrImpl_FWSetFirewallRule2_33@@YAKPEAX0PEAU_tag_FW_RULE@@PEAW4_tag_FW_RULE_STATUS@@@Z`
- size: `1352`
- prototype: `__int64 __fastcall(void *, struct _tag_FW_BLOB_REPO **, struct _tag_FW_RULE *, enum _tag_FW_RULE_STATUS *)`
- caller_count: `11`
- callee_count: `18`
- tags: `registry_config`

## callers

- `0x180055820`
- `0x180078a80`
- `0x18009e5b4`
- `0x18009e6bc`
- `0x18009e794`
- `0x18009e884`
- `0x18009e96c`
- `0x18009ea5c`
- `0x18009eb54`
- `0x18009ec5c`
- `0x1800b5000`

## callees

- `0x180008618`
- `0x180009460`
- `0x180009720`
- `0x18000a0c0`
- `0x18000af3c`
- `0x180017110`
- `0x180026e70`
- `0x180027624`
- `0x18003e798`
- `0x180043234`
- `0x180049928`
- `0x180051620`
- `0x18005441c`
- `0x1800558ec`
- `0x18006f520`
- `0x18007f9b4`
- `0x1800a1a18`
- `0x1800a2378`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180055bcb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180055c5c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180055bcb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180055c5c`
- `fwbase!FwGetRpcCallersProcessImageName` at `0x180055a06`
- `fwbase!FwGetRpcCallersProcessImageName` at `0x180055a06`
- `fwbase!FwResolveIndirectString` at `0x180055a9a`
- `fwbase!FwResolveIndirectString` at `0x180055a9a`
- `fwbase!FwChangeSourceSignal` at `0x180055d03`
- `fwbase!FwChangeSourceSignal` at `0x180055d03`
- `fwbase!FwHResultToWindowsError` at `0x180055d0b`
- `fwbase!FwHResultToWindowsError` at `0x180055d8b`
- `fwbase!FwHResultToWindowsError` at `0x180055ddd`
- `fwbase!FwHResultToWindowsError` at `0x180055d0b`
- `fwbase!FwHResultToWindowsError` at `0x180055d8b`
- `fwbase!FwHResultToWindowsError` at `0x180055ddd`
- `fwbase!FwStringCopy` at `0x180055a8c`
- `fwbase!FwStringCopy` at `0x180055a8c`
- `fwbase!FwFree` at `0x180055dc1`
- `fwbase!FwFree` at `0x180055dcb`
- `fwbase!FwFree` at `0x180055dd5`
- `fwbase!FwFree` at `0x180055dc1`
- `fwbase!FwFree` at `0x180055dcb`
- `fwbase!FwFree` at `0x180055dd5`
- `FWPolicyIOMgr!FwSetRule` at `0x180055b94`
- `FWPolicyIOMgr!FwSetRule` at `0x180055b94`
- `FWPolicyIOMgr!FwVerifyWFRuleSemantics` at `0x180055abd`
- `FWPolicyIOMgr!FwVerifyWFRuleSemantics` at `0x180055abd`

## pseudocode

```c

```
