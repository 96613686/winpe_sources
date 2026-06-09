# Microsoft.Crm.SyncAttributeMappingConstants::.cctor

- ea: `0x17900`
- end: `0x17a5c`
- name: `Microsoft.Crm.SyncAttributeMappingConstants::.cctor`
- size: `348`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## string_xrefs

- `0x17989`: `iscomputed`
- `0x17a29`: `iscomputed`
- `0x17993`: `computedproperties`
- `0x17a33`: `computedproperties`

## pseudocode

```c

```

## disassembly

```asm
0x17900  ldstr    aCaad0cc7D8fd46// "{CAAD0CC7-D8FD-466F-B327-C3BEC07D03CC}"
0x17905  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1790a  stsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.SyncAttributeMappingConstants::AdminProfileGuid
0x1790f  ldstr    a03ee81a307df45// "{03EE81A3-07DF-4514-9CC3-FA807BCBFFB2}"
0x17914  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x17919  stsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.SyncAttributeMappingConstants::SysAdminPrincipalId
0x1791e  ldc.i4.s 0x2C
0x17920  stsfld   char Microsoft.Crm.SyncAttributeMappingConstants::ComputedPropertiesListDelimiterChar
0x17925  ldstr    aSyncattributem// "syncattributemappingprofileid"
0x1792a  stsfld   string Microsoft.Crm.SyncAttributeMappingConstants::SyncAttributeMappingProfileProfileId
0x1792f  ldstr    aSyncattributem_0// "syncattributemappingprofileidunique"
0x17934  stsfld   string Microsoft.Crm.SyncAttributeMappingConstants::SyncAttributeMappingProfileProfileIdUnique
0x17939  ldstr    aPrincipalsynca// "principalsyncattributemapid"
0x1793e  stsfld   string Microsoft.Crm.SyncAttributeMappingConstants::PrincipalSyncAttrMapPrincipalSyncMappingId
0x17943  ldstr    aMappingname// "mappingname"
0x17948  stsfld   string Microsoft.Crm.SyncAttributeMappingConstants::PrincipalSyncAttrMapMappingName
0x1794d  ldstr    aAttributeexcha// "attributeexchangename"
0x17952  stsfld   string Microsoft.Crm.SyncAttributeMappingConstants::PrincipalSyncAttrMapAttrExchName
0x17957  ldstr    aAttributecrmna// "attributecrmname"
0x1795c  stsfld   string Microsoft.Crm.SyncAttributeMappingConstants::PrincipalSyncAttrMapAttrCrmName
0x17961  ldstr    aEntitytypecode// "entitytypecode"
0x17966  stsfld   string Microsoft.Crm.SyncAttributeMappingConstants::PrincipalSyncAttrMapEntityTypeCode
0x1796b  ldstr    aSyncdirection// "syncdirection"
0x17970  stsfld   string Microsoft.Crm.SyncAttributeMappingConstants::PrincipalSyncAttrMapSyncDirection
0x17975  ldstr    aDefaultsyncdir// "defaultsyncdirection"
0x1797a  stsfld   string Microsoft.Crm.SyncAttributeMappingConstants::PrincipalSyncAttrMapDefaultSyncDirection
0x1797f  ldstr    aAllowedsyncdir// "allowedsyncdirection"
0x17984  stsfld   string Microsoft.Crm.SyncAttributeMappingConstants::PrincipalSyncAttrMapAllowedSyncDirection
0x17989  ldstr    aIscomputed// "iscomputed"
0x1798e  stsfld   string Microsoft.Crm.SyncAttributeMappingConstants::PrincipalSyncAttrMapIsComputed
0x17993  ldstr    aComputedproper// "computedproperties"
0x17998  stsfld   string Microsoft.Crm.SyncAttributeMappingConstants::PrincipalSyncAttrMapComputedProperties
0x1799d  ldstr    aPrincipalid// "principalid"
0x179a2  stsfld   string Microsoft.Crm.SyncAttributeMappingConstants::PrincipalSyncAttrMapPrincipalId
0x179a7  ldstr    aParentprincipa// "parentprincipalsyncattributemappingid"
0x179ac  stsfld   string Microsoft.Crm.SyncAttributeMappingConstants::PrincipalSyncAttrMapParentPrincipalSyncMappingId
0x179b1  ldstr    aAttributeid// "attributeid"
0x179b6  stsfld   string Microsoft.Crm.SyncAttributeMappingConstants::PrincipalSyncAttrMapAttributeId
0x179bb  ldstr    aAttributecrmdi// "attributecrmdisplayname"
0x179c0  stsfld   string Microsoft.Crm.SyncAttributeMappingConstants::PrincipalSyncAttrMapAttrCrmDispName
0x179c5  ldstr    aAttributeexcha_0// "attributeexchangedisplayname"
0x179ca  stsfld   string Microsoft.Crm.SyncAttributeMappingConstants::PrincipalSyncAttrMapAttrExchangeDispName
0x179cf  ldstr    aSyncattributem_1// "syncattributemappingid"
0x179d4  stsfld   string Microsoft.Crm.SyncAttributeMappingConstants::SyncAttributeMappingSyncMappingId
0x179d9  ldstr    aSyncattributem_2// "syncattributemappingidunique"
0x179de  stsfld   string Microsoft.Crm.SyncAttributeMappingConstants::SyncAttributeMappingSyncMappingIdUnique
0x179e3  ldstr    aMappingname// "mappingname"
0x179e8  stsfld   string Microsoft.Crm.SyncAttributeMappingConstants::SyncAttributeMappingMappingName
0x179ed  ldstr    aAttributeexcha// "attributeexchangename"
0x179f2  stsfld   string Microsoft.Crm.SyncAttributeMappingConstants::SyncAttributeMappingAttrExchName
0x179f7  ldstr    aAttributecrmna// "attributecrmname"
0x179fc  stsfld   string Microsoft.Crm.SyncAttributeMappingConstants::SyncAttributeMappingAttrCrmName
0x17a01  ldstr    aEntitytypecode// "entitytypecode"
0x17a06  stsfld   string Microsoft.Crm.SyncAttributeMappingConstants::SyncAttributeMappingEntityTypeCode
0x17a0b  ldstr    aSyncdirection// "syncdirection"
0x17a10  stsfld   string Microsoft.Crm.SyncAttributeMappingConstants::SyncAttributeMappingSyncDirection
0x17a15  ldstr    aDefaultsyncdir// "defaultsyncdirection"
0x17a1a  stsfld   string Microsoft.Crm.SyncAttributeMappingConstants::SyncAttributeMappingDefaultSyncDirection
0x17a1f  ldstr    aAllowedsyncdir// "allowedsyncdirection"
0x17a24  stsfld   string Microsoft.Crm.SyncAttributeMappingConstants::SyncAttributeMappingAllowedSyncDirection
0x17a29  ldstr    aIscomputed// "iscomputed"
0x17a2e  stsfld   string Microsoft.Crm.SyncAttributeMappingConstants::SyncAttributeMappingIsComputed
0x17a33  ldstr    aComputedproper// "computedproperties"
0x17a38  stsfld   string Microsoft.Crm.SyncAttributeMappingConstants::SyncAttributeMappingComputedProperties
0x17a3d  ldstr    aSyncattributem// "syncattributemappingprofileid"
0x17a42  stsfld   string Microsoft.Crm.SyncAttributeMappingConstants::SyncAttributeMappingSyncAttrMappingProfileId
0x17a47  ldstr    aAttributecrmdi// "attributecrmdisplayname"
0x17a4c  stsfld   string Microsoft.Crm.SyncAttributeMappingConstants::SyncAttrMappingAttrCrmDispName
0x17a51  ldstr    aAttributeexcha_0// "attributeexchangedisplayname"
0x17a56  stsfld   string Microsoft.Crm.SyncAttributeMappingConstants::SyncAttrMappingAttrExchangeDispName
0x17a5b  ret
```
