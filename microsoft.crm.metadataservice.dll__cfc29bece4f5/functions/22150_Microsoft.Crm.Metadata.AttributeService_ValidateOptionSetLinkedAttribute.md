# Microsoft.Crm.Metadata.AttributeService::ValidateOptionSetLinkedAttribute

- ea: `0x22150`
- end: `0x22455`
- name: `Microsoft.Crm.Metadata.AttributeService::ValidateOptionSetLinkedAttribute`
- size: `773`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x21d50`

## callees

- `0x18440`
- `0x18490`
- `0x18530`
- `0x22150`
- `0x40f10`
- `0x4ab20`
- `0x4ab70`
- `0x4c2b0`

## string_xrefs

- `0x2217e`: `Invalid option set id found in linked attribute {0}`
- `0x2224e`: `Option set missmatch found in linked attribute {0}`
- `0x22312`: `Options mismatch found with linked attribute for attribute {0}`
- `0x223c4`: `Options mismatch found with linked attribute for attribute {0}`
- `0x22430`: `Options mismatch found with linked attribute for attribute {0}`

## pseudocode

```c

```

## disassembly

```asm
0x22150  ldarg.1
0x22151  ldstr    aOptionsetid// "optionsetid"
0x22156  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x2215b  brfalse.s loc_22179
0x2215d  ldarg.1
0x2215e  ldstr    aOptionsetid// "optionsetid"
0x22163  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x22168  unbox.any [mscorlib]System.Guid
0x2216d  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x22172  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x22177  brfalse.s loc_221AC
0x22179  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2217e  ldstr    aInvalidOptionS// "Invalid option set id found in linked a"...
0x22183  ldc.i4.1
0x22184  newarr   [mscorlib]System.Object
0x22189  dup
0x2218a  ldc.i4.0
0x2218b  ldarg.1
0x2218c  ldstr    aName// "name"
0x22191  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x22196  castclass [mscorlib]System.String
0x2219b  stelem.ref
0x2219c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x221a1  ldc.i4   0x8004F0FC
0x221a6  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x221ab  throw
0x221ac  ldarg.0
0x221ad  callvirt instance string Microsoft.Crm.Metadata.AttributeInfo::get_TypeName()
0x221b2  ldstr    aPicklist// "picklist"
0x221b7  call     bool [mscorlib]System.String::op_Equality(string, string)
0x221bc  brtrue.s loc_221D3
0x221be  ldarg.0
0x221bf  callvirt instance string Microsoft.Crm.Metadata.AttributeInfo::get_TypeName()
0x221c4  ldstr    aMultiselectpic// "multiselectpicklist"
0x221c9  call     bool [mscorlib]System.String::op_Equality(string, string)
0x221ce  brfalse  loc_2227C
0x221d3  call     class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::get_Instance()
0x221d8  ldarg.1
0x221d9  ldstr    aOptionsetid// "optionsetid"
0x221de  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x221e3  unbox.any [mscorlib]System.Guid
0x221e8  ldstr    aOptionset_0// "OptionSet"
0x221ed  ldc.i4.1
0x221ee  newarr   [mscorlib]System.String
0x221f3  dup
0x221f4  ldc.i4.0
0x221f5  ldstr    aIsglobal// "isglobal"
0x221fa  stelem.ref
0x221fb  ldarg.2
0x221fc  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::RetrieveMetadataEntity(valuetype [mscorlib]System.Guid, string, string[], class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x22201  ldarg.0
0x22202  callvirt instance class Microsoft.Crm.Metadata.OptionSetInfo Microsoft.Crm.Metadata.EnumAttributeInfo::get_OptionSet()
0x22207  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag Microsoft.Crm.Metadata.OptionSetInfo::get_OptionSetDescription()
0x2220c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag::get_InnerEntityData()
0x22211  ldstr    aIsglobal// "isglobal"
0x22216  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x2221b  ldc.i4.0
0x2221c  ceq
0x2221e  ldstr    aIsglobalProper// "IsGlobal property can't be null"
0x22223  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x22228  ldstr    aIsglobal// "isglobal"
0x2222d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x22232  unbox.any [mscorlib]System.Boolean
0x22237  ldarg.0
0x22238  callvirt instance class Microsoft.Crm.Metadata.OptionSetInfo Microsoft.Crm.Metadata.EnumAttributeInfo::get_OptionSet()
0x2223d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag Microsoft.Crm.Metadata.OptionSetInfo::get_OptionSetDescription()
0x22242  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescription::get_IsGlobal()
0x22247  beq.s    loc_2227C
0x22249  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2224e  ldstr    aOptionSetMissm// "Option set missmatch found in linked at"...
0x22253  ldc.i4.1
0x22254  newarr   [mscorlib]System.Object
0x22259  dup
0x2225a  ldc.i4.0
0x2225b  ldarg.1
0x2225c  ldstr    aName// "name"
0x22261  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x22266  castclass [mscorlib]System.String
0x2226b  stelem.ref
0x2226c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x22271  ldc.i4   0x8004F0FC
0x22276  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x2227b  throw
0x2227c  ldarg.1
0x2227d  ldstr    aOptionsetid// "optionsetid"
0x22282  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x22287  unbox.any [mscorlib]System.Guid
0x2228c  ldc.i4.3
0x2228d  ldarg.2
0x2228e  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x22293  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOptionByValueDictionary Microsoft.Crm.Metadata.OptionSetService::GetExistingAttributePicklistValues(valuetype [mscorlib]System.Guid optionSetId, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.OptionSetType optionSetType, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context)
0x22298  stloc.0
0x22299  ldarg.0
0x2229a  callvirt instance class Microsoft.Crm.Metadata.OptionSetInfo Microsoft.Crm.Metadata.EnumAttributeInfo::get_OptionSet()
0x2229f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOptionByValueDictionary Microsoft.Crm.Metadata.OptionSetInfo::get_Options()
0x222a4  stloc.1
0x222a5  ldloc.1
0x222a6  brtrue.s loc_222EA
0x222a8  ldc.i4.1
0x222a9  newarr   [mscorlib]System.String
0x222ae  dup
0x222af  ldc.i4.0
0x222b0  ldstr    aOptionsetid// "optionsetid"
0x222b5  stelem.ref
0x222b6  stloc.2
0x222b7  call     class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::get_Instance()
0x222bc  ldarg.0
0x222bd  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.AttributeInfo::get_AttributeId()
0x222c2  ldstr    aAttribute// "Attribute"
0x222c7  ldloc.2
0x222c8  ldarg.2
0x222c9  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::RetrieveMetadataEntity(valuetype [mscorlib]System.Guid, string, string[], class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x222ce  ldstr    aOptionsetid// "optionsetid"
0x222d3  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x222d8  unbox.any [mscorlib]System.Guid
0x222dd  ldc.i4.3
0x222de  ldarg.2
0x222df  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x222e4  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOptionByValueDictionary Microsoft.Crm.Metadata.OptionSetService::GetExistingAttributePicklistValues(valuetype [mscorlib]System.Guid optionSetId, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.OptionSetType optionSetType, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context)
0x222e9  stloc.1
0x222ea  ldarg.0
0x222eb  callvirt instance class Microsoft.Crm.Metadata.OptionSetInfo Microsoft.Crm.Metadata.EnumAttributeInfo::get_OptionSet()
0x222f0  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag Microsoft.Crm.Metadata.OptionSetInfo::get_OptionSetDescription()
0x222f5  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescription::get_IsGlobal()
0x222fa  brtrue   loc_22404
0x222ff  ldloc.0
0x22300  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption>::get_Count()
0x22305  ldloc.1
0x22306  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption>::get_Count()
0x2230b  beq.s    loc_22336
0x2230d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x22312  ldstr    aOptionsMismatc// "Options mismatch found with linked attr"...
0x22317  ldc.i4.1
0x22318  newarr   [mscorlib]System.Object
0x2231d  dup
0x2231e  ldc.i4.0
0x2231f  ldarg.0
0x22320  callvirt instance string Microsoft.Crm.Metadata.AttributeInfo::get_Name()
0x22325  stelem.ref
0x22326  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2232b  ldc.i4   0x8004F0FC
0x22330  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x22335  throw
0x22336  ldloc.0
0x22337  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption>::get_Values()
0x2233c  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<int32, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption>::GetEnumerator()
0x22341  stloc.3
0x22342  br       loc_223E8
0x22347  ldloca.s 3
0x22349  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<int32, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption>::get_Current()
0x2234e  stloc.s  4
0x22350  ldloc.1
0x22351  ldloc.s  4
0x22353  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption::get_Value()
0x22358  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption>::get_Item(void)
0x2235d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption::get_Labels()
0x22362  ldarg.2
0x22363  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::GetLabelCollection(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x22368  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection
0x2236d  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label> [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection::get_ActualLabels()
0x22372  ldc.i4.0
0x22373  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label>::get_Item(!!T0)
0x22378  stloc.s  5
0x2237a  ldloc.s  4
0x2237c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption::get_Labels()
0x22381  ldarg.2
0x22382  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::GetLabelCollection(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x22387  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection
0x2238c  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label> [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection::get_ActualLabels()
0x22391  ldc.i4.0
0x22392  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label>::get_Item(!!T0)
0x22397  stloc.s  6
0x22399  ldloc.s  5
0x2239b  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::get_LanguageCode()
0x223a0  ldloc.s  6
0x223a2  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::get_LanguageCode()
0x223a7  bne.un.s loc_223BF
0x223a9  ldloc.s  5
0x223ab  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::get_Description()
0x223b0  ldloc.s  6
0x223b2  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::get_Description()
0x223b7  ldc.i4.0
0x223b8  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x223bd  brfalse.s loc_223E8
0x223bf  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x223c4  ldstr    aOptionsMismatc// "Options mismatch found with linked attr"...
0x223c9  ldc.i4.1
0x223ca  newarr   [mscorlib]System.Object
0x223cf  dup
0x223d0  ldc.i4.0
0x223d1  ldarg.0
0x223d2  callvirt instance string Microsoft.Crm.Metadata.AttributeInfo::get_Name()
0x223d7  stelem.ref
0x223d8  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x223dd  ldc.i4   0x8004F0FC
0x223e2  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x223e7  throw
0x223e8  ldloca.s 3
0x223ea  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<int32, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption>::MoveNext()
0x223ef  brtrue   loc_22347
0x223f4  leave.s  loc_22454
0x223f6  ldloca.s 3
0x223f8  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<int32, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption>
0x223fe  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x22403  endfinally
0x22404  ldarg.1
0x22405  ldstr    aOptionsetid// "optionsetid"
0x2240a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x2240f  unbox.any [mscorlib]System.Guid
0x22414  ldarg.0
0x22415  callvirt instance class Microsoft.Crm.Metadata.OptionSetInfo Microsoft.Crm.Metadata.EnumAttributeInfo::get_OptionSet()
0x2241a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag Microsoft.Crm.Metadata.OptionSetInfo::get_OptionSetDescription()
0x2241f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescription::get_OptionSetId()
0x22424  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x22429  brfalse.s loc_22454
0x2242b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x22430  ldstr    aOptionsMismatc// "Options mismatch found with linked attr"...
0x22435  ldc.i4.1
0x22436  newarr   [mscorlib]System.Object
0x2243b  dup
0x2243c  ldc.i4.0
0x2243d  ldarg.0
0x2243e  callvirt instance string Microsoft.Crm.Metadata.AttributeInfo::get_Name()
0x22443  stelem.ref
0x22444  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x22449  ldc.i4   0x8004F0FC
0x2244e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x22453  throw
0x22454  ret
```
