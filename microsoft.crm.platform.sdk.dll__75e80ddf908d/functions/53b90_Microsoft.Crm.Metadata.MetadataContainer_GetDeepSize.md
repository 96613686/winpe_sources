# Microsoft.Crm.Metadata.MetadataContainer::GetDeepSize

- ea: `0x53b90`
- end: `0x53d23`
- name: `Microsoft.Crm.Metadata.MetadataContainer::GetDeepSize`
- size: `403`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x53b50`

## callees

- `0x53b90`
- `0x53d30`
- `0x5e4f0`
- `0x5ed80`

## string_xrefs

- `0x53c34`: `ContainerPrivilegeOTCs`
- `0x53c46`: `ContainerRoleTemplatePrivileges`
- `0x53cc3`: `ContainerPrivileges`

## pseudocode

```c

```

## disassembly

```asm
0x53b90  ldarg.0
0x53b91  ldarg.1
0x53b92  ldstr    aContaineroptio// "ContainerOptionSets"
0x53b97  ldarg.0
0x53b98  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription> Microsoft.Crm.Metadata.MetadataContainer::_optionSets
0x53b9d  call     instance void Microsoft.Crm.Metadata.MetadataContainer::AddDictionarySizeToCollector(class Microsoft.Crm.Metadata.IMetadataCacheSizeCollector collector, string type, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription> values)
0x53ba2  ldarg.0
0x53ba3  ldarg.1
0x53ba4  ldstr    aContainerentit// "ContainerEntities"
0x53ba9  ldarg.0
0x53baa  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription> Microsoft.Crm.Metadata.MetadataContainer::_entities
0x53baf  call     instance void Microsoft.Crm.Metadata.MetadataContainer::AddDictionarySizeToCollector(class Microsoft.Crm.Metadata.IMetadataCacheSizeCollector collector, string type, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription> values)
0x53bb4  ldarg.0
0x53bb5  ldarg.1
0x53bb6  ldstr    aContainerattri// "ContainerAttributes"
0x53bbb  ldarg.0
0x53bbc  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription> Microsoft.Crm.Metadata.MetadataContainer::_attributes
0x53bc1  call     instance void Microsoft.Crm.Metadata.MetadataContainer::AddDictionarySizeToCollector(class Microsoft.Crm.Metadata.IMetadataCacheSizeCollector collector, string type, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription> values)
0x53bc6  ldarg.0
0x53bc7  ldarg.1
0x53bc8  ldstr    aContainerpickl// "ContainerPicklistValues"
0x53bcd  ldarg.0
0x53bce  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription> Microsoft.Crm.Metadata.MetadataContainer::_picklistValues
0x53bd3  call     instance void Microsoft.Crm.Metadata.MetadataContainer::AddDictionarySizeToCollector(class Microsoft.Crm.Metadata.IMetadataCacheSizeCollector collector, string type, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription> values)
0x53bd8  ldarg.0
0x53bd9  ldarg.1
0x53bda  ldstr    aContainerlocal// "ContainerLocalizedLabels"
0x53bdf  ldarg.0
0x53be0  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription> Microsoft.Crm.Metadata.MetadataContainer::_localizedLabels
0x53be5  call     instance void Microsoft.Crm.Metadata.MetadataContainer::AddDictionarySizeToCollector(class Microsoft.Crm.Metadata.IMetadataCacheSizeCollector collector, string type, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription> values)
0x53bea  ldarg.0
0x53beb  ldarg.1
0x53bec  ldstr    aContainerlooku// "ContainerLookupValues"
0x53bf1  ldarg.0
0x53bf2  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription> Microsoft.Crm.Metadata.MetadataContainer::_lookupValues
0x53bf7  call     instance void Microsoft.Crm.Metadata.MetadataContainer::AddDictionarySizeToCollector(class Microsoft.Crm.Metadata.IMetadataCacheSizeCollector collector, string type, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription> values)
0x53bfc  ldarg.0
0x53bfd  ldarg.1
0x53bfe  ldstr    aContainerrelat// "ContainerRelationships"
0x53c03  ldarg.0
0x53c04  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription> Microsoft.Crm.Metadata.MetadataContainer::_relationships
0x53c09  call     instance void Microsoft.Crm.Metadata.MetadataContainer::AddDictionarySizeToCollector(class Microsoft.Crm.Metadata.IMetadataCacheSizeCollector collector, string type, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription> values)
0x53c0e  ldarg.0
0x53c0f  ldarg.1
0x53c10  ldstr    aContainerviewa// "ContainerViewAttributes"
0x53c15  ldarg.0
0x53c16  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription> Microsoft.Crm.Metadata.MetadataContainer::_viewAttributes
0x53c1b  call     instance void Microsoft.Crm.Metadata.MetadataContainer::AddDictionarySizeToCollector(class Microsoft.Crm.Metadata.IMetadataCacheSizeCollector collector, string type, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription> values)
0x53c20  ldarg.0
0x53c21  ldarg.1
0x53c22  ldstr    aContainermanag// "ContainerManagedProperties"
0x53c27  ldarg.0
0x53c28  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription> Microsoft.Crm.Metadata.MetadataContainer::_managedProperties
0x53c2d  call     instance void Microsoft.Crm.Metadata.MetadataContainer::AddDictionarySizeToCollector(class Microsoft.Crm.Metadata.IMetadataCacheSizeCollector collector, string type, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription> values)
0x53c32  ldarg.0
0x53c33  ldarg.1
0x53c34  ldstr    aContainerprivi// "ContainerPrivilegeOTCs"
0x53c39  ldarg.0
0x53c3a  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription> Microsoft.Crm.Metadata.MetadataContainer::_privilegesObjectTypeCodes
0x53c3f  call     instance void Microsoft.Crm.Metadata.MetadataContainer::AddDictionarySizeToCollector(class Microsoft.Crm.Metadata.IMetadataCacheSizeCollector collector, string type, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription> values)
0x53c44  ldarg.0
0x53c45  ldarg.1
0x53c46  ldstr    aContainerrolet// "ContainerRoleTemplatePrivileges"
0x53c4b  ldarg.0
0x53c4c  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription> Microsoft.Crm.Metadata.MetadataContainer::_roleTemplatePrivileges
0x53c51  call     instance void Microsoft.Crm.Metadata.MetadataContainer::AddDictionarySizeToCollector(class Microsoft.Crm.Metadata.IMetadataCacheSizeCollector collector, string type, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription> values)
0x53c56  ldarg.0
0x53c57  ldarg.1
0x53c58  ldstr    aContainerentit_0// "ContainerEntityRelationships"
0x53c5d  ldarg.0
0x53c5e  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription> Microsoft.Crm.Metadata.MetadataContainer::_entityRelationships
0x53c63  call     instance void Microsoft.Crm.Metadata.MetadataContainer::AddDictionarySizeToCollector(class Microsoft.Crm.Metadata.IMetadataCacheSizeCollector collector, string type, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription> values)
0x53c68  ldarg.0
0x53c69  ldarg.1
0x53c6a  ldstr    aContainerentit_1// "ContainerEntityRelationshipRoles"
0x53c6f  ldarg.0
0x53c70  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription> Microsoft.Crm.Metadata.MetadataContainer::_entityRelationshipRoles
0x53c75  call     instance void Microsoft.Crm.Metadata.MetadataContainer::AddDictionarySizeToCollector(class Microsoft.Crm.Metadata.IMetadataCacheSizeCollector collector, string type, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription> values)
0x53c7a  ldarg.0
0x53c7b  ldarg.1
0x53c7c  ldstr    aContainerrelat_0// "ContainerRelationshipExtraConditions"
0x53c81  ldarg.0
0x53c82  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription> Microsoft.Crm.Metadata.MetadataContainer::_relationshipExtraConditions
0x53c87  call     instance void Microsoft.Crm.Metadata.MetadataContainer::AddDictionarySizeToCollector(class Microsoft.Crm.Metadata.IMetadataCacheSizeCollector collector, string type, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription> values)
0x53c8c  ldarg.0
0x53c8d  ldarg.1
0x53c8e  ldstr    aContainerentit_2// "ContainerEntityRelationshipRelationship"...
0x53c93  ldarg.0
0x53c94  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription> Microsoft.Crm.Metadata.MetadataContainer::_entityRelationshipRelationships
0x53c99  call     instance void Microsoft.Crm.Metadata.MetadataContainer::AddDictionarySizeToCollector(class Microsoft.Crm.Metadata.IMetadataCacheSizeCollector collector, string type, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription> values)
0x53c9e  ldarg.0
0x53c9f  ldarg.1
0x53ca0  ldstr    aContainerentit_3// "ContainerEntityKeys"
0x53ca5  ldarg.0
0x53ca6  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription> Microsoft.Crm.Metadata.MetadataContainer::_entityKeys
0x53cab  call     instance void Microsoft.Crm.Metadata.MetadataContainer::AddDictionarySizeToCollector(class Microsoft.Crm.Metadata.IMetadataCacheSizeCollector collector, string type, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription> values)
0x53cb0  ldarg.0
0x53cb1  ldarg.1
0x53cb2  ldstr    aContainerentit_4// "ContainerEntityKeyAttributes"
0x53cb7  ldarg.0
0x53cb8  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription> Microsoft.Crm.Metadata.MetadataContainer::_entityKeyAttributes
0x53cbd  call     instance void Microsoft.Crm.Metadata.MetadataContainer::AddDictionarySizeToCollector(class Microsoft.Crm.Metadata.IMetadataCacheSizeCollector collector, string type, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription> values)
0x53cc2  ldarg.1
0x53cc3  ldstr    aContainerprivi_0// "ContainerPrivileges"
0x53cc8  ldarg.0
0x53cc9  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Metadata.Privilege> Microsoft.Crm.Metadata.MetadataContainer::_privileges
0x53cce  call     T0x2B000084
0x53cd3  callvirt instance void Microsoft.Crm.Metadata.IMetadataCacheSizeCollector::AddCollectionSize(string type, int64 size)
0x53cd8  ldarg.0
0x53cd9  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Metadata.Privilege> Microsoft.Crm.Metadata.MetadataContainer::_privileges
0x53cde  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Metadata.Privilege>::GetEnumerator()
0x53ce3  stloc.0
0x53ce4  br.s     loc_53CF4
0x53ce6  ldloca.s 0
0x53ce8  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Metadata.Privilege>::get_Current()
0x53ced  ldarg.1
0x53cee  ldc.i4.1
0x53cef  callvirt instance void Microsoft.Crm.Metadata.MetadataSizeCollectable::GetSize(class Microsoft.Crm.Metadata.IMetadataCacheSizeCollector collector, bool collectDeep)
0x53cf4  ldloca.s 0
0x53cf6  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Metadata.Privilege>::MoveNext()
0x53cfb  brtrue.s loc_53CE6
0x53cfd  leave.s  loc_53D0D
0x53cff  ldloca.s 0
0x53d01  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Metadata.Privilege>
0x53d07  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x53d0c  endfinally
0x53d0d  ldarg.0
0x53d0e  ldfld    class Microsoft.Crm.Metadata.Organization Microsoft.Crm.Metadata.MetadataContainer::_organizationSettings
0x53d13  brfalse.s loc_53D22
0x53d15  ldarg.0
0x53d16  ldfld    class Microsoft.Crm.Metadata.Organization Microsoft.Crm.Metadata.MetadataContainer::_organizationSettings
0x53d1b  ldarg.1
0x53d1c  ldc.i4.1
0x53d1d  callvirt instance void Microsoft.Crm.Metadata.MetadataSizeCollectable::GetSize(class Microsoft.Crm.Metadata.IMetadataCacheSizeCollector collector, bool collectDeep)
0x53d22  ret
```
