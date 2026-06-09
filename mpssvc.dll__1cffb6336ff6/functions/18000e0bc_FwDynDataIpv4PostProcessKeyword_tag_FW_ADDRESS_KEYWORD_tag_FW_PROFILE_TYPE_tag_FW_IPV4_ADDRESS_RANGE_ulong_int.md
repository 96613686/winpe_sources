# FwDynDataIpv4PostProcessKeyword(_tag_FW_ADDRESS_KEYWORD,_tag_FW_PROFILE_TYPE,_tag_FW_IPV4_ADDRESS_RANGE * *,ulong *,int)

- ea: `0x18000e0bc`
- end: `0x18000e534`
- name: `?FwDynDataIpv4PostProcessKeyword@@YAXW4_tag_FW_ADDRESS_KEYWORD@@W4_tag_FW_PROFILE_TYPE@@PEAPEAU_tag_FW_IPV4_ADDRESS_RANGE@@PEAKH@Z`
- size: `1144`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18000c260`

## callees

- `0x18000af3c`
- `0x18000e0bc`
- `0x18000f02c`
- `0x18006f520`
- `0x18006ffc8`
- `0x1800738b2`

## import_xrefs

- `fwbase!FwSortAddresses` at `0x18000e3a2`
- `fwbase!FwSortAddresses` at `0x18000e3a2`
- `fwbase!FwSizeTMultiply` at `0x18000e196`
- `fwbase!FwSizeTMultiply` at `0x18000e196`
- `fwbase!FwAlloc` at `0x18000e263`
- `fwbase!FwAlloc` at `0x18000e263`
- `fwbase!FwCriticalSectionEnter` at `0x18000e126`
- `fwbase!FwCriticalSectionEnter` at `0x18000e133`
- `fwbase!FwCriticalSectionEnter` at `0x18000e126`
- `fwbase!FwCriticalSectionEnter` at `0x18000e133`
- `fwbase!FwCriticalSectionLeave` at `0x18000e33a`
- `fwbase!FwCriticalSectionLeave` at `0x18000e347`
- `fwbase!FwCriticalSectionLeave` at `0x18000e33a`
- `fwbase!FwCriticalSectionLeave` at `0x18000e347`
- `fwbase!FwFree` at `0x18000e3f2`
- `fwbase!FwFree` at `0x18000e438`
- `fwbase!FwFree` at `0x18000e3f2`
- `fwbase!FwFree` at `0x18000e438`
- `FWPolicyIOMgr!Isv4Orv6AddressesEmpty` at `0x18000e3bd`
- `FWPolicyIOMgr!Isv4Orv6AddressesEmpty` at `0x18000e4fd`
- `FWPolicyIOMgr!Isv4Orv6AddressesEmpty` at `0x18000e51b`
- `FWPolicyIOMgr!Isv4Orv6AddressesEmpty` at `0x18000e3bd`
- `FWPolicyIOMgr!Isv4Orv6AddressesEmpty` at `0x18000e4fd`
- `FWPolicyIOMgr!Isv4Orv6AddressesEmpty` at `0x18000e51b`
- `FWPolicyIOMgr!FwRemoveDuplicateAddresses` at `0x18000e3ad`
- `FWPolicyIOMgr!FwRemoveDuplicateAddresses` at `0x18000e3ad`
- `FWPolicyIOMgr!FwNegateAddresses` at `0x18000e2c1`
- `FWPolicyIOMgr!FwNegateAddresses` at `0x18000e2c1`
- `FWPolicyIOMgr!FwSubtractAddresses` at `0x18000e484`
- `FWPolicyIOMgr!FwSubtractAddresses` at `0x18000e484`
- `FWPolicyIOMgr!FwPolioMergeAddresses` at `0x18000e210`
- `FWPolicyIOMgr!FwPolioMergeAddresses` at `0x18000e2ac`
- `FWPolicyIOMgr!FwPolioMergeAddresses` at `0x18000e309`
- `FWPolicyIOMgr!FwPolioMergeAddresses` at `0x18000e210`
- `FWPolicyIOMgr!FwPolioMergeAddresses` at `0x18000e2ac`
- `FWPolicyIOMgr!FwPolioMergeAddresses` at `0x18000e309`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x18000e499`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x18000e499`

## pseudocode

```c

```
