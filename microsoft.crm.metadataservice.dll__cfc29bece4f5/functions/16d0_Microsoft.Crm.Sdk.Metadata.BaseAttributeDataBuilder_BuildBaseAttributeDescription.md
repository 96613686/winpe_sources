# Microsoft.Crm.Sdk.Metadata.BaseAttributeDataBuilder::BuildBaseAttributeDescription

- ea: `0x16d0`
- end: `0x1b21`
- name: `Microsoft.Crm.Sdk.Metadata.BaseAttributeDataBuilder::BuildBaseAttributeDescription`
- size: `1105`
- prototype: ``
- caller_count: `23`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x2130`
- `0x2150`
- `0x21a0`
- `0x2360`
- `0x24d0`
- `0x25a0`
- `0x2660`
- `0x2730`
- `0x2b60`
- `0x2c60`
- `0x2d40`
- `0x2dc0`
- `0x2e10`
- `0x2f20`
- `0x3020`
- `0x3190`
- `0x3320`
- `0x3460`
- `0x35c0`
- `0x3710`
- `0x3880`
- `0x3980`
- `0x3aa0`

## callees

- `0x16d0`
- `0x1b30`
- `0x1d00`
- `0x1d40`
- `0x8ad0`
- `0xa940`

## string_xrefs

- `0x19f1`: `linkedattributeid`
- `0x1b04`: `isrenameable`

## pseudocode

```c

```

## disassembly

```asm
0x16d0  ldstr    aAttribute// "Attribute"
0x16d5  ldarg.0
0x16d6  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Sdk.Metadata.BaseAttributeDataBuilder::_orgContext
0x16db  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x16e0  stloc.0
0x16e1  ldloc.0
0x16e2  ldstr    aEntityid// "entityid"
0x16e7  ldarg.1
0x16e8  box      [mscorlib]System.Guid
0x16ed  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0x16f2  ldarg.2
0x16f3  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataBase::get_MetadataId()
0x16f8  stloc.2
0x16f9  ldloca.s 2
0x16fb  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x1700  brfalse.s loc_171C
0x1702  ldarg.2
0x1703  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataBase::get_MetadataId()
0x1708  stloc.2
0x1709  ldloca.s 2
0x170b  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0x1710  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1715  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x171a  brfalse.s loc_1759
0x171c  ldarg.3
0x171d  ldc.i4   0x1000
0x1722  and
0x1723  ldc.i4   0x1000
0x1728  bne.un.s loc_173C
0x172a  ldarg.2
0x172b  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1730  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0x1735  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataBase::set_MetadataId(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>)
0x173a  br.s     loc_1759
0x173c  ldarg.2
0x173d  ldarg.0
0x173e  ldfld    class Microsoft.Crm.Sdk.Metadata.MetadataConverter Microsoft.Crm.Sdk.Metadata.BaseAttributeDataBuilder::_converter
0x1743  ldarg.1
0x1744  ldarg.2
0x1745  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::get_LogicalName()
0x174a  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sdk.Metadata.MetadataConverter::GetAttributeIdFromAttributeLogicalName(valuetype [mscorlib]System.Guid entityId, string attributeLogicalName)
0x174f  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0x1754  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataBase::set_MetadataId(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>)
0x1759  ldloc.0
0x175a  ldstr    aAttributeid// "attributeid"
0x175f  ldarg.2
0x1760  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataBase::get_MetadataId()
0x1765  stloc.2
0x1766  ldloca.s 2
0x1768  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0x176d  box      [mscorlib]System.Guid
0x1772  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0x1777  ldloca.s 1
0x1779  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x177f  ldarg.2
0x1780  isinst   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.ImageAttributeMetadata
0x1785  brfalse.s loc_17A7
0x1787  ldloca.s 1
0x1789  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeDictionary [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypes::get_AttributeTypesByName()
0x178e  ldstr    aImage// "image"
0x1793  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeDictionary::get_Item(object)
0x1798  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_Id()
0x179d  call     instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0x17a2  br       loc_1846
0x17a7  ldarg.2
0x17a8  isinst   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MultiSelectPicklistAttributeMetadata
0x17ad  brfalse.s loc_17CC
0x17af  ldloca.s 1
0x17b1  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeDictionary [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypes::get_AttributeTypesByName()
0x17b6  ldstr    aMultiselectpic// "multiselectpicklist"
0x17bb  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeDictionary::get_Item(object)
0x17c0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_Id()
0x17c5  call     instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0x17ca  br.s     loc_1846
0x17cc  ldarg.2
0x17cd  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeTypeCode> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::get_AttributeType()
0x17d2  stloc.3
0x17d3  ldloca.s 3
0x17d5  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeTypeCode>::get_HasValue()
0x17da  brfalse.s loc_1846
0x17dc  ldarg.2
0x17dd  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeTypeCode> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::get_AttributeType()
0x17e2  stloc.3
0x17e3  ldloca.s 3
0x17e5  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeTypeCode>::get_HasValue()
0x17ea  brfalse.s loc_1846
0x17ec  ldarg.2
0x17ed  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::get_IsPrimaryId()
0x17f2  stloc.s  4
0x17f4  ldloca.s 4
0x17f6  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x17fb  brfalse.s loc_182B
0x17fd  ldarg.2
0x17fe  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::get_IsPrimaryId()
0x1803  stloc.s  4
0x1805  ldloca.s 4
0x1807  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x180c  brfalse.s loc_182B
0x180e  ldloca.s 1
0x1810  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeDictionary [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypes::get_AttributeTypesByName()
0x1815  ldstr    aPrimarykey// "primarykey"
0x181a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeDictionary::get_Item(object)
0x181f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_Id()
0x1824  call     instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0x1829  br.s     loc_1846
0x182b  ldloca.s 1
0x182d  ldarg.0
0x182e  ldarg.2
0x182f  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeTypeCode> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::get_AttributeType()
0x1834  stloc.3
0x1835  ldloca.s 3
0x1837  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeTypeCode>::get_Value()
0x183c  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sdk.Metadata.BaseAttributeDataBuilder::GetAttributeTypeId(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeTypeCode attributeType)
0x1841  call     instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0x1846  ldloc.0
0x1847  ldstr    aAttributetypei// "attributetypeid"
0x184c  ldloc.1
0x184d  box      valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x1852  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0x1857  ldloc.0
0x1858  ldstr    aPhysicalname// "physicalname"
0x185d  ldarg.2
0x185e  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::get_SchemaName()
0x1863  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0x1868  ldloc.0
0x1869  ldstr    aExternalname// "externalname"
0x186e  ldarg.2
0x186f  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::get_ExternalName()
0x1874  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0x1879  ldarg.2
0x187a  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeRequiredLevelManagedProperty [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::get_RequiredLevel()
0x187f  brfalse.s loc_18B7
0x1881  ldloc.0
0x1882  ldstr    aAttributerequi// "attributerequiredlevelid"
0x1887  ldarg.2
0x1888  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeRequiredLevelManagedProperty [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::get_RequiredLevel()
0x188d  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ManagedProperty`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeRequiredLevel>::get_Value()
0x1892  call     string Microsoft.Crm.Sdk.Metadata.BaseAttributeDataBuilder::GetRequiredLevelId(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeRequiredLevel attributeRequiredLevel)
0x1897  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0x189c  ldloc.0
0x189d  ldstr    aCanmodifyrequi// "canmodifyrequirementlevelsettings"
0x18a2  ldarg.2
0x18a3  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeRequiredLevelManagedProperty [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::get_RequiredLevel()
0x18a8  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ManagedProperty`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeRequiredLevel>::get_CanBeChanged()
0x18ad  box      [mscorlib]System.Boolean
0x18b2  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0x18b7  ldarg.2
0x18b8  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::get_IsPrimaryName()
0x18bd  stloc.s  4
0x18bf  ldloca.s 4
0x18c1  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x18c6  brtrue.s loc_18D8
0x18c8  ldarg.2
0x18c9  isinst   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityNameAttributeMetadata
0x18ce  brtrue.s loc_18D8
0x18d0  ldarg.2
0x18d1  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BooleanManagedProperty [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::get_IsValidForAdvancedFind()
0x18d6  brfalse.s loc_1911
0x18d8  ldloc.0
0x18d9  ldstr    aDisplaymask// "displaymask"
0x18de  ldarg.2
0x18df  call     valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DisplayMasks Microsoft.Crm.Sdk.Metadata.BaseAttributeDataBuilder::GetDisplayMask(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata attributeMetadata)
0x18e4  box      [mscorlib]System.Int32
0x18e9  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0x18ee  ldarg.2
0x18ef  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BooleanManagedProperty [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::get_IsValidForAdvancedFind()
0x18f4  brfalse.s loc_1911
0x18f6  ldloc.0
0x18f7  ldstr    aCanmodifysearc// "canmodifysearchsettings"
0x18fc  ldarg.2
0x18fd  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BooleanManagedProperty [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::get_IsValidForAdvancedFind()
0x1902  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ManagedProperty`1<bool>::get_CanBeChanged()
0x1907  box      [mscorlib]System.Boolean
0x190c  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0x1911  ldarg.2
0x1912  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::get_IsSecured()
0x1917  stloc.s  4
0x1919  ldloca.s 4
0x191b  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x1920  brfalse.s loc_1941
0x1922  ldloc.0
0x1923  ldstr    aIssecured// "issecured"
0x1928  ldarg.2
0x1929  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::get_IsSecured()
0x192e  stloc.s  4
0x1930  ldloca.s 4
0x1932  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x1937  box      [mscorlib]System.Boolean
0x193c  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0x1941  ldarg.2
0x1942  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BooleanManagedProperty [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::get_IsGlobalFilterEnabled()
0x1947  brfalse.s loc_197F
0x1949  ldloc.0
0x194a  ldstr    aIsglobalfilter// "isglobalfilterenabled"
0x194f  ldarg.2
0x1950  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BooleanManagedProperty [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::get_IsGlobalFilterEnabled()
0x1955  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ManagedProperty`1<bool>::get_Value()
0x195a  box      [mscorlib]System.Boolean
0x195f  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0x1964  ldloc.0
0x1965  ldstr    aCanmodifygloba// "canmodifyglobalfiltersettings"
0x196a  ldarg.2
0x196b  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BooleanManagedProperty [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::get_IsGlobalFilterEnabled()
0x1970  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ManagedProperty`1<bool>::get_CanBeChanged()
0x1975  box      [mscorlib]System.Boolean
0x197a  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0x197f  ldarg.2
0x1980  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BooleanManagedProperty [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::get_IsSortableEnabled()
0x1985  brfalse.s loc_19BD
0x1987  ldloc.0
0x1988  ldstr    aIssortableenab// "issortableenabled"
0x198d  ldarg.2
0x198e  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BooleanManagedProperty [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::get_IsSortableEnabled()
0x1993  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ManagedProperty`1<bool>::get_Value()
0x1998  box      [mscorlib]System.Boolean
0x199d  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0x19a2  ldloc.0
0x19a3  ldstr    aCanmodifyissor// "canmodifyissortablesettings"
0x19a8  ldarg.2
0x19a9  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BooleanManagedProperty [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::get_IsSortableEnabled()
0x19ae  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ManagedProperty`1<bool>::get_CanBeChanged()
0x19b3  box      [mscorlib]System.Boolean
0x19b8  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0x19bd  ldarg.2
0x19be  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BooleanManagedProperty [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::get_IsAuditEnabled()
0x19c3  brfalse.s loc_19E0
0x19c5  ldloc.0
0x19c6  ldstr    aIsauditenabled// "isauditenabled"
0x19cb  ldarg.2
0x19cc  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BooleanManagedProperty [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::get_IsAuditEnabled()
0x19d1  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ManagedProperty`1<bool>::get_Value()
0x19d6  box      [mscorlib]System.Boolean
0x19db  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0x19e0  ldarg.2
0x19e1  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::get_LinkedAttributeId()
0x19e6  stloc.2
0x19e7  ldloca.s 2
0x19e9  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x19ee  brfalse.s loc_1A0E
0x19f0  ldloc.0
0x19f1  ldstr    aLinkedattribut// "linkedattributeid"
0x19f6  ldarg.2
0x19f7  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::get_LinkedAttributeId()
0x19fc  stloc.2
0x19fd  ldloca.s 2
0x19ff  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0x1a04  box      [mscorlib]System.Guid
0x1a09  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0x1a0e  ldarg.2
0x1a0f  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::get_IntroducedVersion()
0x1a14  brfalse.s loc_1A2C
0x1a16  ldloc.0
0x1a17  ldstr    aIntroducedvers// "introducedversion"
0x1a1c  ldarg.2
0x1a1d  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::get_IntroducedVersion()
0x1a22  callvirt instance string [mscorlib]System.Object::ToString()
0x1a27  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0x1a2c  ldarg.2
0x1a2d  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::get_IsSearchable()
0x1a32  stloc.s  4
0x1a34  ldloca.s 4
0x1a36  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x1a3b  brfalse.s loc_1A5C
0x1a3d  ldloc.0
0x1a3e  ldstr    aIssearchable// "issearchable"
0x1a43  ldarg.2
0x1a44  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::get_IsSearchable()
0x1a49  stloc.s  4
0x1a4b  ldloca.s 4
0x1a4d  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x1a52  box      [mscorlib]System.Boolean
0x1a57  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0x1a5c  ldarg.2
0x1a5d  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::get_IsFilterable()
0x1a62  stloc.s  4
0x1a64  ldloca.s 4
0x1a66  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x1a6b  brfalse.s loc_1A8C
0x1a6d  ldloc.0
0x1a6e  ldstr    aIsfilterable// "isfilterable"
0x1a73  ldarg.2
0x1a74  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::get_IsFilterable()
0x1a79  stloc.s  4
0x1a7b  ldloca.s 4
0x1a7d  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x1a82  box      [mscorlib]System.Boolean
0x1a87  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0x1a8c  ldarg.2
0x1a8d  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::get_IsRetrievable()
0x1a92  stloc.s  4
0x1a94  ldloca.s 4
0x1a96  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x1a9b  brfalse.s loc_1ABC
0x1a9d  ldloc.0
0x1a9e  ldstr    aIsretrievable// "isretrievable"
0x1aa3  ldarg.2
0x1aa4  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::get_IsRetrievable()
0x1aa9  stloc.s  4
0x1aab  ldloca.s 4
0x1aad  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
  ... truncated ...
```
