# appIsolation::EnterpriseDomainProtection::FwMoneisCreateEnterpriseIdRule(_tag_FW_RULE * *,ushort const *,ushort const *,unsigned __int64,_tag_FW_DIRECTION)

- ea: `0x1800c3110`
- end: `0x1800c3401`
- name: `?FwMoneisCreateEnterpriseIdRule@EnterpriseDomainProtection@appIsolation@@AEAAKPEAPEAU_tag_FW_RULE@@PEBG1_KW4_tag_FW_DIRECTION@@@Z`
- size: `753`
- prototype: `unsigned int __high(struct _tag_FW_RULE **, const unsigned __int16 *, const unsigned __int16 *, unsigned __int64, enum _tag_FW_DIRECTION)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800c3ea0`

## callees

- `0x18003d990`
- `0x18006c8ac`
- `0x1800729c0`
- `0x180073488`
- `0x1800c3110`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800c3339`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800c3339`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800c335e`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800c335e`
- `fwbase!FwAlloc` at `0x1800c31c9`
- `fwbase!FwAlloc` at `0x1800c31f9`
- `fwbase!FwAlloc` at `0x1800c32c3`
- `fwbase!FwAlloc` at `0x1800c331b`
- `fwbase!FwAlloc` at `0x1800c337b`
- `fwbase!FwAlloc` at `0x1800c31c9`
- `fwbase!FwAlloc` at `0x1800c31f9`
- `fwbase!FwAlloc` at `0x1800c32c3`
- `fwbase!FwAlloc` at `0x1800c331b`
- `fwbase!FwAlloc` at `0x1800c337b`
- `FWPolicyIOMgr!FwFreeWFRule` at `0x1800c3219`
- `FWPolicyIOMgr!FwFreeWFRule` at `0x1800c3219`

## pseudocode

```c

```
