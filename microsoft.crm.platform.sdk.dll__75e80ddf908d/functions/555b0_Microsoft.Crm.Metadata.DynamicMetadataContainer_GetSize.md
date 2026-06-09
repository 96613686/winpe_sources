# Microsoft.Crm.Metadata.DynamicMetadataContainer::GetSize

- ea: `0x555b0`
- end: `0x55955`
- name: `Microsoft.Crm.Metadata.DynamicMetadataContainer::GetSize`
- size: `933`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x54ae0`
- `0x54b00`
- `0x54b20`
- `0x54b40`
- `0x54bc0`
- `0x54be0`
- `0x54c00`
- `0x54c60`
- `0x54c80`
- `0x54cc0`
- `0x54ce0`
- `0x54d00`
- `0x54d20`
- `0x54d40`
- `0x54d60`
- `0x54d80`
- `0x54fa0`
- `0x555b0`
- `0xa94d0`

## string_xrefs

- `0x557f6`: `Privilege`
- `0x5578d`: `PrivilegeObjectTypeCode`
- `0x557a2`: `RoleTemplatePrivilege`

## pseudocode

```c

```

## disassembly

```asm
0x555b0  ldarg.1
0x555b1  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0x555b6  stloc.0
0x555b7  ldloc.0
0x555b8  ldc.i4   0x6E61547A
0x555bd  bgt.un   loc_55646
0x555c2  ldloc.0
0x555c3  ldc.i4   0x2FB17EF0
0x555c8  bgt.un.s loc_55608
0x555ca  ldloc.0
0x555cb  ldc.i4   0x1D72D1E6
0x555d0  bgt.un.s loc_555ED
0x555d2  ldloc.0
0x555d3  ldc.i4   0x1ACCD85B
0x555d8  beq      loc_5574D
0x555dd  ldloc.0
0x555de  ldc.i4   0x1D72D1E6
0x555e3  beq      loc_557A1
0x555e8  br       loc_55936
0x555ed  ldloc.0
0x555ee  ldc.i4   0x21E27D10
0x555f3  beq      loc_557CB
0x555f8  ldloc.0
0x555f9  ldc.i4   0x2FB17EF0
0x555fe  beq      loc_55762
0x55603  br       loc_55936
0x55608  ldloc.0
0x55609  ldc.i4   0x4F6B9560
0x5560e  bgt.un.s loc_5562B
0x55610  ldloc.0
0x55611  ldc.i4   0x3578225F
0x55616  beq      loc_55723
0x5561b  ldloc.0
0x5561c  ldc.i4   0x4F6B9560
0x55621  beq      loc_557B6
0x55626  br       loc_55936
0x5562b  ldloc.0
0x5562c  ldc.i4   0x62FA988F
0x55631  beq      loc_556F9
0x55636  ldloc.0
0x55637  ldc.i4   0x6E61547A
0x5563c  beq      loc_5578C
0x55641  br       loc_55936
0x55646  ldloc.0
0x55647  ldc.i4   0x9F56E047
0x5564c  bgt.un.s loc_55689
0x5564e  ldloc.0
0x5564f  ldc.i4   0x80D2874B
0x55654  bgt.un.s loc_55671
0x55656  ldloc.0
0x55657  ldc.i4   0x7B5DF6A6
0x5565c  beq      loc_5570E
0x55661  ldloc.0
0x55662  ldc.i4   0x80D2874B
0x55667  beq      loc_5581F
0x5566c  br       loc_55936
0x55671  ldloc.0
0x55672  ldc.i4   0x946992DC
0x55677  beq.s    loc_556E4
0x55679  ldloc.0
0x5567a  ldc.i4   0x9F56E047
0x5567f  beq      loc_557E0
0x55684  br       loc_55936
0x55689  ldloc.0
0x5568a  ldc.i4   0xC0670678
0x5568f  bgt.un.s loc_556AC
0x55691  ldloc.0
0x55692  ldc.i4   0xA6468091
0x55697  beq      loc_5580A
0x5569c  ldloc.0
0x5569d  ldc.i4   0xC0670678
0x556a2  beq      loc_55777
0x556a7  br       loc_55936
0x556ac  ldloc.0
0x556ad  ldc.i4   0xC09B32FA
0x556b2  beq      loc_55738
0x556b7  ldloc.0
0x556b8  ldc.i4   0xCEEE0703
0x556bd  beq.s    loc_556CF
0x556bf  ldloc.0
0x556c0  ldc.i4   0xF92D43AC
0x556c5  beq      loc_557F5
0x556ca  br       loc_55936
0x556cf  ldarg.1
0x556d0  ldstr    aManagedpropert_5// "ManagedProperty"
0x556d5  call     bool [mscorlib]System.String::op_Equality(string, string)
0x556da  brtrue   loc_55834
0x556df  br       loc_55936
0x556e4  ldarg.1
0x556e5  ldstr    aOptionset_0// "OptionSet"
0x556ea  call     bool [mscorlib]System.String::op_Equality(string, string)
0x556ef  brtrue   loc_55840
0x556f4  br       loc_55936
0x556f9  ldarg.1
0x556fa  ldstr    aAttribute// "Attribute"
0x556ff  call     bool [mscorlib]System.String::op_Equality(string, string)
0x55704  brtrue   loc_5584C
0x55709  br       loc_55936
0x5570e  ldarg.1
0x5570f  ldstr    aAttributelooku// "AttributeLookupValue"
0x55714  call     bool [mscorlib]System.String::op_Equality(string, string)
0x55719  brtrue   loc_55858
0x5571e  br       loc_55936
0x55723  ldarg.1
0x55724  ldstr    aAttributepickl// "AttributePicklistValue"
0x55729  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5572e  brtrue   loc_55864
0x55733  br       loc_55936
0x55738  ldarg.1
0x55739  ldstr    aEntity_0// "Entity"
0x5573e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x55743  brtrue   loc_55870
0x55748  br       loc_55936
0x5574d  ldarg.1
0x5574e  ldstr    aRelationship_0// "Relationship"
0x55753  call     bool [mscorlib]System.String::op_Equality(string, string)
0x55758  brtrue   loc_5587C
0x5575d  br       loc_55936
0x55762  ldarg.1
0x55763  ldstr    aRelationshipex_0// "RelationshipExtraCondition"
0x55768  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5576d  brtrue   loc_55888
0x55772  br       loc_55936
0x55777  ldarg.1
0x55778  ldstr    aViewattribute// "ViewAttribute"
0x5577d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x55782  brtrue   loc_55894
0x55787  br       loc_55936
0x5578c  ldarg.1
0x5578d  ldstr    aPrivilegeobjec// "PrivilegeObjectTypeCode"
0x55792  call     bool [mscorlib]System.String::op_Equality(string, string)
0x55797  brtrue   loc_558A0
0x5579c  br       loc_55936
0x557a1  ldarg.1
0x557a2  ldstr    aRoletemplatepr// "RoleTemplatePrivilege"
0x557a7  call     bool [mscorlib]System.String::op_Equality(string, string)
0x557ac  brtrue   loc_558AC
0x557b1  br       loc_55936
0x557b6  ldarg.1
0x557b7  ldstr    aEntityrelation_0// "EntityRelationship"
0x557bc  call     bool [mscorlib]System.String::op_Equality(string, string)
0x557c1  brtrue   loc_558B8
0x557c6  br       loc_55936
0x557cb  ldarg.1
0x557cc  ldstr    aEntityrelation_4// "EntityRelationshipRole"
0x557d1  call     bool [mscorlib]System.String::op_Equality(string, string)
0x557d6  brtrue   loc_558C4
0x557db  br       loc_55936
0x557e0  ldarg.1
0x557e1  ldstr    aEntityrelation_6// "EntityRelationshipRelationships"
0x557e6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x557eb  brtrue   loc_558D0
0x557f0  br       loc_55936
0x557f5  ldarg.1
0x557f6  ldstr    aPrivilege// "Privilege"
0x557fb  call     bool [mscorlib]System.String::op_Equality(string, string)
0x55800  brtrue   loc_558DC
0x55805  br       loc_55936
0x5580a  ldarg.1
0x5580b  ldstr    aEntitykey_0// "EntityKey"
0x55810  call     bool [mscorlib]System.String::op_Equality(string, string)
0x55815  brtrue   loc_5591E
0x5581a  br       loc_55936
0x5581f  ldarg.1
0x55820  ldstr    aEntitykeyattri// "EntityKeyAttribute"
0x55825  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5582a  brtrue   loc_5592A
0x5582f  br       loc_55936
0x55834  ldarg.0
0x55835  call     instance class Microsoft.Crm.Metadata.ManagedPropertyByIdDictionary Microsoft.Crm.Metadata.DynamicMetadataContainer::get_ManagedProperties()
0x5583a  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.ManagedPropertyMetadata>::get_Count()
0x5583f  ret
0x55840  ldarg.0
0x55841  call     instance class Microsoft.Crm.Metadata.OptionSetByIdDictionary Microsoft.Crm.Metadata.DynamicMetadataContainer::get_OptionSets()
0x55846  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.OptionSetMetadata>::get_Count()
0x5584b  ret
0x5584c  ldarg.0
0x5584d  call     instance class Microsoft.Crm.Metadata.AttributeMetadataDictionary Microsoft.Crm.Metadata.DynamicMetadataContainer::get_Attributes()
0x55852  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.AttributeMetadata>::get_Count()
0x55857  ret
0x55858  ldarg.0
0x55859  call     instance class Microsoft.Crm.Metadata.AttributeLookupValueDictionary Microsoft.Crm.Metadata.DynamicMetadataContainer::get_LookupValues()
0x5585e  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.AttributeLookupValue>::get_Count()
0x55863  ret
0x55864  ldarg.0
0x55865  call     instance class Microsoft.Crm.Metadata.EnumOptionDictionary Microsoft.Crm.Metadata.DynamicMetadataContainer::get_PicklistValues()
0x5586a  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.EnumOption>::get_Count()
0x5586f  ret
0x55870  ldarg.0
0x55871  call     instance class Microsoft.Crm.Metadata.EntityMetadataDictionary Microsoft.Crm.Metadata.DynamicMetadataContainer::get_Entities()
0x55876  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.EntityMetadata>::get_Count()
0x5587b  ret
0x5587c  ldarg.0
0x5587d  call     instance class Microsoft.Crm.Metadata.RelationshipHashtable Microsoft.Crm.Metadata.DynamicMetadataContainer::get_Relationships()
0x55882  callvirt instance int32 [mscorlib]System.Collections.Hashtable::get_Count()
0x55887  ret
0x55888  ldarg.0
0x55889  call     instance class Microsoft.Crm.Metadata.RelationshipExtraConditionDictionary Microsoft.Crm.Metadata.DynamicMetadataContainer::get_RelationshipExtraConditions()
0x5588e  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.RelationshipExtraCondition>::get_Count()
0x55893  ret
0x55894  ldarg.0
0x55895  call     instance class Microsoft.Crm.Metadata.ViewAttributeDictionary Microsoft.Crm.Metadata.DynamicMetadataContainer::get_ViewAttributes()
0x5589a  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.ViewInfo>::get_Count()
0x5589f  ret
0x558a0  ldarg.0
0x558a1  call     instance class Microsoft.Crm.Metadata.PrivilegeObjectTypeCodeDictionary Microsoft.Crm.Metadata.DynamicMetadataContainer::get_PrivilegeObjectTypeCodes()
0x558a6  callvirt instance int32 [mscorlib]System.Collections.Hashtable::get_Count()
0x558ab  ret
0x558ac  ldarg.0
0x558ad  call     instance class Microsoft.Crm.Metadata.RoleTemplatePrivilegeDictionary Microsoft.Crm.Metadata.DynamicMetadataContainer::get_RoleTemplatePrivileges()
0x558b2  callvirt instance int32 [mscorlib]System.Collections.Hashtable::get_Count()
0x558b7  ret
0x558b8  ldarg.0
0x558b9  call     instance class Microsoft.Crm.Metadata.EntityRelationshipByIdDictionary Microsoft.Crm.Metadata.DynamicMetadataContainer::get_EntityRelationships()
0x558be  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.EntityRelationship>::get_Count()
0x558c3  ret
0x558c4  ldarg.0
0x558c5  call     instance class Microsoft.Crm.Metadata.EntityRelationshipRoleDictionary Microsoft.Crm.Metadata.DynamicMetadataContainer::get_EntityRelationshipRoles()
0x558ca  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.EntityRelationshipRole>::get_Count()
0x558cf  ret
0x558d0  ldarg.0
0x558d1  call     instance class Microsoft.Crm.Metadata.EntityRelationshipRelationshipsDictionary Microsoft.Crm.Metadata.DynamicMetadataContainer::get_EntityRelationshipRelationships()
0x558d6  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.EntityRelationshipRelationships>::get_Count()
0x558db  ret
0x558dc  ldc.i4.0
0x558dd  stloc.1
0x558de  ldarg.0
0x558df  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Metadata.PrivilegeCollection> Microsoft.Crm.Metadata.DynamicMetadataContainer::get_privilegesByOtc()
0x558e4  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Metadata.PrivilegeCollection>::GetEnumerator()
0x558e9  stloc.2
0x558ea  br.s     loc_55903
0x558ec  ldloca.s 2
0x558ee  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<int32, class Microsoft.Crm.Metadata.PrivilegeCollection>::get_Current()
0x558f3  stloc.3
0x558f4  ldloc.1
0x558f5  ldloca.s 3
0x558f7  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<int32, class Microsoft.Crm.Metadata.PrivilegeCollection>::get_Value()
0x558fc  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x55901  add
0x55902  stloc.1
0x55903  ldloca.s 2
0x55905  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<int32, class Microsoft.Crm.Metadata.PrivilegeCollection>::MoveNext()
0x5590a  brtrue.s loc_558EC
0x5590c  leave.s  loc_5591C
0x5590e  ldloca.s 2
0x55910  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<int32, class Microsoft.Crm.Metadata.PrivilegeCollection>
0x55916  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5591b  endfinally
0x5591c  ldloc.1
0x5591d  ret
0x5591e  ldarg.0
0x5591f  call     instance class Microsoft.Crm.Metadata.EntityKeyByIdCollection Microsoft.Crm.Metadata.DynamicMetadataContainer::get_EntityKeys()
0x55924  callvirt instance int32 [mscorlib]System.Collections.Hashtable::get_Count()
0x55929  ret
0x5592a  ldarg.0
0x5592b  call     instance class Microsoft.Crm.Metadata.EntityKeyAttributeMetadataDictionary Microsoft.Crm.Metadata.DynamicMetadataContainer::get_EntityKeyAttributes()
0x55930  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.EntityKeyAttributeMetadata>::get_Count()
0x55935  ret
0x55936  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5593b  ldstr    aMetadataentity_1// "MetadataEntityName {0} is not valid"
0x55940  ldc.i4.1
0x55941  newarr   [mscorlib]System.Object
0x55946  dup
0x55947  ldc.i4.0
0x55948  ldarg.1
0x55949  stelem.ref
0x5594a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x5594f  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x55954  throw
```
