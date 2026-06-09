# Microsoft.Crm.Metadata.MetadataEntityNamesPlural::.cctor

- ea: `0x70c90`
- end: `0x70e26`
- name: `Microsoft.Crm.Metadata.MetadataEntityNamesPlural::.cctor`
- size: `406`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x70c90`

## string_xrefs

- `0x70d29`: `Privileges`
- `0x70d3a`: `PrivilegeObjectTypeCodes`
- `0x70d4b`: `RoleTemplatePrivileges`

## pseudocode

```c

```

## disassembly

```asm
0x70c90  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode>::.ctor()
0x70c95  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode> Microsoft.Crm.Metadata.MetadataEntityNamesPlural::_fromNameToTypeCode
0x70c9a  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode, string>::.ctor()
0x70c9f  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode, string> Microsoft.Crm.Metadata.MetadataEntityNamesPlural::_fromTypeCodeToName
0x70ca4  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode> Microsoft.Crm.Metadata.MetadataEntityNamesPlural::_fromNameToTypeCode
0x70ca9  ldstr    aEntities_0// "Entities"
0x70cae  ldc.i4.1
0x70caf  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode>::Add(var<u1>, !!T0)
0x70cb4  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode> Microsoft.Crm.Metadata.MetadataEntityNamesPlural::_fromNameToTypeCode
0x70cb9  ldstr    aAttributes_0// "Attributes"
0x70cbe  ldc.i4.2
0x70cbf  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode>::Add(var<u1>, !!T0)
0x70cc4  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode> Microsoft.Crm.Metadata.MetadataEntityNamesPlural::_fromNameToTypeCode
0x70cc9  ldstr    aRelationships_0// "Relationships"
0x70cce  ldc.i4.3
0x70ccf  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode>::Add(var<u1>, !!T0)
0x70cd4  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode> Microsoft.Crm.Metadata.MetadataEntityNamesPlural::_fromNameToTypeCode
0x70cd9  ldstr    aAttributepickl_3// "AttributePicklistValues"
0x70cde  ldc.i4.4
0x70cdf  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode>::Add(var<u1>, !!T0)
0x70ce4  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode> Microsoft.Crm.Metadata.MetadataEntityNamesPlural::_fromNameToTypeCode
0x70ce9  ldstr    aAttributelooku_6// "AttributeLookupValues"
0x70cee  ldc.i4.5
0x70cef  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode>::Add(var<u1>, !!T0)
0x70cf4  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode> Microsoft.Crm.Metadata.MetadataEntityNamesPlural::_fromNameToTypeCode
0x70cf9  ldstr    aViewattributes// "ViewAttributes"
0x70cfe  ldc.i4.6
0x70cff  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode>::Add(var<u1>, !!T0)
0x70d04  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode> Microsoft.Crm.Metadata.MetadataEntityNamesPlural::_fromNameToTypeCode
0x70d09  ldstr    aLocalizedlabel_12// "LocalizedLabels"
0x70d0e  ldc.i4.7
0x70d0f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode>::Add(var<u1>, !!T0)
0x70d14  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode> Microsoft.Crm.Metadata.MetadataEntityNamesPlural::_fromNameToTypeCode
0x70d19  ldstr    aRelationshipex_8// "RelationshipExtraConditions"
0x70d1e  ldc.i4.8
0x70d1f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode>::Add(var<u1>, !!T0)
0x70d24  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode> Microsoft.Crm.Metadata.MetadataEntityNamesPlural::_fromNameToTypeCode
0x70d29  ldstr    aPrivileges_0// "Privileges"
0x70d2e  ldc.i4.s 9
0x70d30  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode>::Add(var<u1>, !!T0)
0x70d35  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode> Microsoft.Crm.Metadata.MetadataEntityNamesPlural::_fromNameToTypeCode
0x70d3a  ldstr    aPrivilegeobjec_6// "PrivilegeObjectTypeCodes"
0x70d3f  ldc.i4.s 0xA
0x70d41  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode>::Add(var<u1>, !!T0)
0x70d46  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode> Microsoft.Crm.Metadata.MetadataEntityNamesPlural::_fromNameToTypeCode
0x70d4b  ldstr    aRoletemplatepr_9// "RoleTemplatePrivileges"
0x70d50  ldc.i4.s 0xB
0x70d52  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode>::Add(var<u1>, !!T0)
0x70d57  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode> Microsoft.Crm.Metadata.MetadataEntityNamesPlural::_fromNameToTypeCode
0x70d5c  ldstr    aEntityrelation_23// "EntityRelationships"
0x70d61  ldc.i4.s 0xC
0x70d63  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode>::Add(var<u1>, !!T0)
0x70d68  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode> Microsoft.Crm.Metadata.MetadataEntityNamesPlural::_fromNameToTypeCode
0x70d6d  ldstr    aEntityrelation_22// "EntityRelationshipRoles"
0x70d72  ldc.i4.s 0xD
0x70d74  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode>::Add(var<u1>, !!T0)
0x70d79  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode> Microsoft.Crm.Metadata.MetadataEntityNamesPlural::_fromNameToTypeCode
0x70d7e  ldstr    aEntityrelation_6// "EntityRelationshipRelationships"
0x70d83  ldc.i4.s 0xE
0x70d85  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode>::Add(var<u1>, !!T0)
0x70d8a  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode> Microsoft.Crm.Metadata.MetadataEntityNamesPlural::_fromNameToTypeCode
0x70d8f  ldstr    aOptionsets_0// "OptionSets"
0x70d94  ldc.i4.s 0xF
0x70d96  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode>::Add(var<u1>, !!T0)
0x70d9b  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode> Microsoft.Crm.Metadata.MetadataEntityNamesPlural::_fromNameToTypeCode
0x70da0  ldstr    aManagedpropert_24// "ManagedProperties"
0x70da5  ldc.i4.s 0x10
0x70da7  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode>::Add(var<u1>, !!T0)
0x70dac  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode> Microsoft.Crm.Metadata.MetadataEntityNamesPlural::_fromNameToTypeCode
0x70db1  ldstr    aOrganizations_0// "Organizations"
0x70db6  ldc.i4.s 0x11
0x70db8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode>::Add(var<u1>, !!T0)
0x70dbd  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode> Microsoft.Crm.Metadata.MetadataEntityNamesPlural::_fromNameToTypeCode
0x70dc2  ldstr    aEntitykeys// "EntityKeys"
0x70dc7  ldc.i4.s 0x12
0x70dc9  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode>::Add(var<u1>, !!T0)
0x70dce  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode> Microsoft.Crm.Metadata.MetadataEntityNamesPlural::_fromNameToTypeCode
0x70dd3  ldstr    aEntitykeyattri_9// "EntityKeyAttributes"
0x70dd8  ldc.i4.s 0x13
0x70dda  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode>::Add(var<u1>, !!T0)
0x70ddf  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode> Microsoft.Crm.Metadata.MetadataEntityNamesPlural::_fromNameToTypeCode
0x70de4  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode>::GetEnumerator()
0x70de9  stloc.0
0x70dea  br.s     loc_70E0C
0x70dec  ldloca.s 0
0x70dee  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode>::get_Current()
0x70df3  stloc.1
0x70df4  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode, string> Microsoft.Crm.Metadata.MetadataEntityNamesPlural::_fromTypeCodeToName
0x70df9  ldloca.s 1
0x70dfb  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode>::get_Value()
0x70e00  ldloca.s 1
0x70e02  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode>::get_Key()
0x70e07  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode, string>::Add(var<u1>, !!T0)
0x70e0c  ldloca.s 0
0x70e0e  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode>::MoveNext()
0x70e13  brtrue.s loc_70DEC
0x70e15  leave.s  loc_70E25
0x70e17  ldloca.s 0
0x70e19  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode>
0x70e1f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x70e24  endfinally
0x70e25  ret
```
