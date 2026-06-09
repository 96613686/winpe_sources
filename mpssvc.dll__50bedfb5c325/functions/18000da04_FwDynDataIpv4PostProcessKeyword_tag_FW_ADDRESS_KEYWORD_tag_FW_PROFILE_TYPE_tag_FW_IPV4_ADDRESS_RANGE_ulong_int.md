# FwDynDataIpv4PostProcessKeyword(_tag_FW_ADDRESS_KEYWORD,_tag_FW_PROFILE_TYPE,_tag_FW_IPV4_ADDRESS_RANGE * *,ulong *,int)

- ea: `0x18000da04`
- end: `0x18000deef`
- name: `?FwDynDataIpv4PostProcessKeyword@@YAXW4_tag_FW_ADDRESS_KEYWORD@@W4_tag_FW_PROFILE_TYPE@@PEAPEAU_tag_FW_IPV4_ADDRESS_RANGE@@PEAKH@Z`
- size: `1259`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18000bb00`

## callees

- `0x18000a710`
- `0x18000da04`
- `0x18000e1bc`
- `0x1800729c0`
- `0x180073488`
- `0x180076d72`

## import_xrefs

- `fwbase!FwSortAddresses` at `0x18000dd27`
- `fwbase!FwSortAddresses` at `0x18000dd27`
- `fwbase!FwSizeTMultiply` at `0x18000daea`
- `fwbase!FwSizeTMultiply` at `0x18000daea`
- `fwbase!FwAlloc` at `0x18000dbc4`
- `fwbase!FwAlloc` at `0x18000dbc4`
- `fwbase!FwCriticalSectionEnter` at `0x18000da6e`
- `fwbase!FwCriticalSectionEnter` at `0x18000da81`
- `fwbase!FwCriticalSectionEnter` at `0x18000da6e`
- `fwbase!FwCriticalSectionEnter` at `0x18000da81`
- `fwbase!FwCriticalSectionLeave` at `0x18000dcb3`
- `fwbase!FwCriticalSectionLeave` at `0x18000dcc6`
- `fwbase!FwCriticalSectionLeave` at `0x18000dcb3`
- `fwbase!FwCriticalSectionLeave` at `0x18000dcc6`
- `fwbase!FwFree` at `0x18000dd89`
- `fwbase!FwFree` at `0x18000ddd5`
- `fwbase!FwFree` at `0x18000dd89`
- `fwbase!FwFree` at `0x18000ddd5`
- `FWPolicyIOMgr!Isv4Orv6AddressesEmpty` at `0x18000dd4e`
- `FWPolicyIOMgr!Isv4Orv6AddressesEmpty` at `0x18000deac`
- `FWPolicyIOMgr!Isv4Orv6AddressesEmpty` at `0x18000ded0`
- `FWPolicyIOMgr!Isv4Orv6AddressesEmpty` at `0x18000dd4e`
- `FWPolicyIOMgr!Isv4Orv6AddressesEmpty` at `0x18000deac`
- `FWPolicyIOMgr!Isv4Orv6AddressesEmpty` at `0x18000ded0`
- `FWPolicyIOMgr!FwRemoveDuplicateAddresses` at `0x18000dd38`
- `FWPolicyIOMgr!FwRemoveDuplicateAddresses` at `0x18000dd38`
- `FWPolicyIOMgr!FwNegateAddresses` at `0x18000dc2e`
- `FWPolicyIOMgr!FwNegateAddresses` at `0x18000dc2e`
- `FWPolicyIOMgr!FwSubtractAddresses` at `0x18000de27`
- `FWPolicyIOMgr!FwSubtractAddresses` at `0x18000de27`
- `FWPolicyIOMgr!FwPolioMergeAddresses` at `0x18000db6a`
- `FWPolicyIOMgr!FwPolioMergeAddresses` at `0x18000dc13`
- `FWPolicyIOMgr!FwPolioMergeAddresses` at `0x18000dc7c`
- `FWPolicyIOMgr!FwPolioMergeAddresses` at `0x18000db6a`
- `FWPolicyIOMgr!FwPolioMergeAddresses` at `0x18000dc13`
- `FWPolicyIOMgr!FwPolioMergeAddresses` at `0x18000dc7c`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x18000de42`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x18000de42`

## pseudocode

```c

```
