# IPolicyWriter::WriteLocalFwRule(_tag_FW_RULE *,_LIST_ENTRY *,_tag_FW_OBJECT_METADATA *)

- ea: `0x180026230`
- end: `0x18002683e`
- name: `?WriteLocalFwRule@IPolicyWriter@@QEAAJPEAU_tag_FW_RULE@@PEAU_LIST_ENTRY@@PEAU_tag_FW_OBJECT_METADATA@@@Z`
- size: `1550`
- prototype: `int(IPolicyWriter *__hidden this, struct _tag_FW_RULE *, struct _LIST_ENTRY *, struct _tag_FW_OBJECT_METADATA *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180026210`

## callees

- `0x180026230`
- `0x180026850`
- `0x18002dcc0`
- `0x1800ec010`

## import_xrefs

- `fwbase!IsRuleOldAuthApp` at `0x180026363`
- `fwbase!IsRuleOldAuthApp` at `0x180026363`
- `fwbase!FwMetaDataAddEnforcementState` at `0x18002632a`
- `fwbase!FwMetaDataAddEnforcementState` at `0x1800264bd`
- `fwbase!FwMetaDataAddEnforcementState` at `0x1800265b3`
- `fwbase!FwMetaDataAddEnforcementState` at `0x1800265dc`
- `fwbase!FwMetaDataAddEnforcementState` at `0x180026622`
- `fwbase!FwMetaDataAddEnforcementState` at `0x180026665`
- `fwbase!FwMetaDataAddEnforcementState` at `0x1800266a8`
- `fwbase!FwMetaDataAddEnforcementState` at `0x1800266e7`
- `fwbase!FwMetaDataAddEnforcementState` at `0x18002672a`
- `fwbase!FwMetaDataAddEnforcementState` at `0x18002676d`
- `fwbase!FwMetaDataAddEnforcementState` at `0x1800267c6`
- `fwbase!FwMetaDataAddEnforcementState` at `0x1800267fc`
- `fwbase!FwMetaDataAddEnforcementState` at `0x18002682d`
- `fwbase!FwMetaDataAddEnforcementState` at `0x18002632a`
- `fwbase!FwMetaDataAddEnforcementState` at `0x1800264bd`
- `fwbase!FwMetaDataAddEnforcementState` at `0x1800265b3`
- `fwbase!FwMetaDataAddEnforcementState` at `0x1800265dc`
- `fwbase!FwMetaDataAddEnforcementState` at `0x180026622`
- `fwbase!FwMetaDataAddEnforcementState` at `0x180026665`
- `fwbase!FwMetaDataAddEnforcementState` at `0x1800266a8`
- `fwbase!FwMetaDataAddEnforcementState` at `0x1800266e7`
- `fwbase!FwMetaDataAddEnforcementState` at `0x18002672a`
- `fwbase!FwMetaDataAddEnforcementState` at `0x18002676d`
- `fwbase!FwMetaDataAddEnforcementState` at `0x1800267c6`
- `fwbase!FwMetaDataAddEnforcementState` at `0x1800267fc`
- `fwbase!FwMetaDataAddEnforcementState` at `0x18002682d`
- `fwbase!IsRuleOldGlobalOpenPort` at `0x180026351`
- `fwbase!IsRuleOldGlobalOpenPort` at `0x180026351`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x18002628f`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x1800262ba`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x1800262e3`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x180026374`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x1800263a4`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x1800263b9`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x1800263ea`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x1800263fd`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x180026431`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x18002645d`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x18002647b`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x180026497`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x180026536`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x18002654b`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x180026568`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x180026606`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x180026649`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x18002668c`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x1800266cb`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x18002670e`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x180026751`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x1800267aa`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x1800267e0`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x180026811`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x18002628f`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x1800262ba`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x1800262e3`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x180026374`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x1800263a4`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x1800263b9`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x1800263ea`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x1800263fd`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x180026431`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x18002645d`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x18002647b`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x180026497`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x180026536`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x18002654b`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x180026568`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x180026606`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x180026649`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x18002668c`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x1800266cb`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x18002670e`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x180026751`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x1800267aa`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x1800267e0`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x180026811`

## pseudocode

```c

```
