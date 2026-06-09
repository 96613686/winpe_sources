# appIsolation::EnterpriseDomainProtection::FwMoneisCreateEnterpriseIdRule(_tag_FW_RULE * *,ushort const *,ushort const *,unsigned __int64,_tag_FW_DIRECTION)

- ea: `0x1800bbe30`
- end: `0x1800bc0f9`
- name: `?FwMoneisCreateEnterpriseIdRule@EnterpriseDomainProtection@appIsolation@@AEAAKPEAPEAU_tag_FW_RULE@@PEBG1_KW4_tag_FW_DIRECTION@@@Z`
- size: `713`
- prototype: `unsigned int __high(struct _tag_FW_RULE **, const unsigned __int16 *, const unsigned __int16 *, unsigned __int64, enum _tag_FW_DIRECTION)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800bcae0`

## callees

- `0x18003d5b0`
- `0x180069bb4`
- `0x18006f520`
- `0x18006ffc8`
- `0x1800bbe30`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800bc043`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800bc043`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800bc062`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800bc062`
- `fwbase!FwAlloc` at `0x1800bbee9`
- `fwbase!FwAlloc` at `0x1800bbf13`
- `fwbase!FwAlloc` at `0x1800bbfd3`
- `fwbase!FwAlloc` at `0x1800bc02b`
- `fwbase!FwAlloc` at `0x1800bc079`
- `fwbase!FwAlloc` at `0x1800bbee9`
- `fwbase!FwAlloc` at `0x1800bbf13`
- `fwbase!FwAlloc` at `0x1800bbfd3`
- `fwbase!FwAlloc` at `0x1800bc02b`
- `fwbase!FwAlloc` at `0x1800bc079`
- `FWPolicyIOMgr!FwFreeWFRule` at `0x1800bbf2d`
- `FWPolicyIOMgr!FwFreeWFRule` at `0x1800bbf2d`

## pseudocode

```c

```
