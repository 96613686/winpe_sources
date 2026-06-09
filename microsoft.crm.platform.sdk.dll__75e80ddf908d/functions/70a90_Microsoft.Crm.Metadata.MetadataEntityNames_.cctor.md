# Microsoft.Crm.Metadata.MetadataEntityNames::.cctor

- ea: `0x70a90`
- end: `0x70c3f`
- name: `Microsoft.Crm.Metadata.MetadataEntityNames::.cctor`
- size: `431`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x70a90`

## string_xrefs

- `0x70b29`: `Privilege`
- `0x70b3a`: `PrivilegeObjectTypeCode`
- `0x70b4b`: `RoleTemplatePrivilege`

## pseudocode

```c

```

## disassembly

```asm
0x70a90  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode>::.ctor()
0x70a95  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode> Microsoft.Crm.Metadata.MetadataEntityNames::_fromNameToTypeCode
0x70a9a  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode, string>::.ctor()
0x70a9f  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode, string> Microsoft.Crm.Metadata.MetadataEntityNames::_fromTypeCodeToName
0x70aa4  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode> Microsoft.Crm.Metadata.MetadataEntityNames::_fromNameToTypeCode
0x70aa9  ldstr    aEntity_0// "Entity"
0x70aae  ldc.i4.1
0x70aaf  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode>::Add(var<u1>, !!T0)
0x70ab4  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode> Microsoft.Crm.Metadata.MetadataEntityNames::_fromNameToTypeCode
0x70ab9  ldstr    aAttribute// "Attribute"
0x70abe  ldc.i4.2
0x70abf  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode>::Add(var<u1>, !!T0)
0x70ac4  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode> Microsoft.Crm.Metadata.MetadataEntityNames::_fromNameToTypeCode
0x70ac9  ldstr    aRelationship_0// "Relationship"
0x70ace  ldc.i4.3
0x70acf  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode>::Add(var<u1>, !!T0)
0x70ad4  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode> Microsoft.Crm.Metadata.MetadataEntityNames::_fromNameToTypeCode
0x70ad9  ldstr    aAttributepickl// "AttributePicklistValue"
0x70ade  ldc.i4.4
0x70adf  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode>::Add(var<u1>, !!T0)
0x70ae4  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode> Microsoft.Crm.Metadata.MetadataEntityNames::_fromNameToTypeCode
0x70ae9  ldstr    aAttributelooku// "AttributeLookupValue"
0x70aee  ldc.i4.5
0x70aef  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode>::Add(var<u1>, !!T0)
0x70af4  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode> Microsoft.Crm.Metadata.MetadataEntityNames::_fromNameToTypeCode
0x70af9  ldstr    aViewattribute// "ViewAttribute"
0x70afe  ldc.i4.6
0x70aff  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode>::Add(var<u1>, !!T0)
0x70b04  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode> Microsoft.Crm.Metadata.MetadataEntityNames::_fromNameToTypeCode
0x70b09  ldstr    aLocalizedlabel// "LocalizedLabel"
0x70b0e  ldc.i4.7
0x70b0f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode>::Add(var<u1>, !!T0)
0x70b14  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode> Microsoft.Crm.Metadata.MetadataEntityNames::_fromNameToTypeCode
0x70b19  ldstr    aRelationshipex_0// "RelationshipExtraCondition"
0x70b1e  ldc.i4.8
0x70b1f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode>::Add(var<u1>, !!T0)
0x70b24  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode> Microsoft.Crm.Metadata.MetadataEntityNames::_fromNameToTypeCode
0x70b29  ldstr    aPrivilege// "Privilege"
0x70b2e  ldc.i4.s 9
0x70b30  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode>::Add(var<u1>, !!T0)
0x70b35  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode> Microsoft.Crm.Metadata.MetadataEntityNames::_fromNameToTypeCode
0x70b3a  ldstr    aPrivilegeobjec// "PrivilegeObjectTypeCode"
0x70b3f  ldc.i4.s 0xA
0x70b41  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode>::Add(var<u1>, !!T0)
0x70b46  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode> Microsoft.Crm.Metadata.MetadataEntityNames::_fromNameToTypeCode
0x70b4b  ldstr    aRoletemplatepr// "RoleTemplatePrivilege"
0x70b50  ldc.i4.s 0xB
0x70b52  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode>::Add(var<u1>, !!T0)
0x70b57  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode> Microsoft.Crm.Metadata.MetadataEntityNames::_fromNameToTypeCode
0x70b5c  ldstr    aEntityrelation_0// "EntityRelationship"
0x70b61  ldc.i4.s 0xC
0x70b63  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode>::Add(var<u1>, !!T0)
0x70b68  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode> Microsoft.Crm.Metadata.MetadataEntityNames::_fromNameToTypeCode
0x70b6d  ldstr    aEntityrelation_4// "EntityRelationshipRole"
0x70b72  ldc.i4.s 0xD
0x70b74  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode>::Add(var<u1>, !!T0)
0x70b79  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode> Microsoft.Crm.Metadata.MetadataEntityNames::_fromNameToTypeCode
0x70b7e  ldstr    aEntityrelation_6// "EntityRelationshipRelationships"
0x70b83  ldc.i4.s 0xE
0x70b85  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode>::Add(var<u1>, !!T0)
0x70b8a  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode> Microsoft.Crm.Metadata.MetadataEntityNames::_fromNameToTypeCode
0x70b8f  ldstr    aOptionset_0// "OptionSet"
0x70b94  ldc.i4.s 0xF
0x70b96  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode>::Add(var<u1>, !!T0)
0x70b9b  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode> Microsoft.Crm.Metadata.MetadataEntityNames::_fromNameToTypeCode
0x70ba0  ldstr    aManagedpropert_5// "ManagedProperty"
0x70ba5  ldc.i4.s 0x10
0x70ba7  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode>::Add(var<u1>, !!T0)
0x70bac  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode> Microsoft.Crm.Metadata.MetadataEntityNames::_fromNameToTypeCode
0x70bb1  ldstr    aOrganization// "Organization"
0x70bb6  ldc.i4.s 0x11
0x70bb8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode>::Add(var<u1>, !!T0)
0x70bbd  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode> Microsoft.Crm.Metadata.MetadataEntityNames::_fromNameToTypeCode
0x70bc2  ldstr    aEntitykey_0// "EntityKey"
0x70bc7  ldc.i4.s 0x12
0x70bc9  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode>::Add(var<u1>, !!T0)
0x70bce  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode> Microsoft.Crm.Metadata.MetadataEntityNames::_fromNameToTypeCode
0x70bd3  ldstr    aEntitykeyattri// "EntityKeyAttribute"
0x70bd8  ldc.i4.s 0x13
0x70bda  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode>::Add(var<u1>, !!T0)
0x70bdf  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode> Microsoft.Crm.Metadata.MetadataEntityNames::_fromNameToTypeCode
0x70be4  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode>::GetEnumerator()
0x70be9  stloc.0
0x70bea  br.s     loc_70C0C
0x70bec  ldloca.s 0
0x70bee  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode>::get_Current()
0x70bf3  stloc.1
0x70bf4  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode, string> Microsoft.Crm.Metadata.MetadataEntityNames::_fromTypeCodeToName
0x70bf9  ldloca.s 1
0x70bfb  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode>::get_Value()
0x70c00  ldloca.s 1
0x70c02  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode>::get_Key()
0x70c07  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode, string>::Add(var<u1>, !!T0)
0x70c0c  ldloca.s 0
0x70c0e  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode>::MoveNext()
0x70c13  brtrue.s loc_70BEC
0x70c15  leave.s  loc_70C25
0x70c17  ldloca.s 0
0x70c19  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode>
0x70c1f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x70c24  endfinally
0x70c25  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode> Microsoft.Crm.Metadata.MetadataEntityNames::_fromNameToTypeCode
0x70c2a  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode>::get_Keys()
0x70c2f  call     T0x2B000003
0x70c34  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<var<u1>> class [mscorlib]System.Collections.Generic.List`1<string>::AsReadOnly()
0x70c39  stsfld   class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<string> Microsoft.Crm.Metadata.MetadataEntityNames::<MetadataEntityNamesList>k__BackingField
0x70c3e  ret
```
