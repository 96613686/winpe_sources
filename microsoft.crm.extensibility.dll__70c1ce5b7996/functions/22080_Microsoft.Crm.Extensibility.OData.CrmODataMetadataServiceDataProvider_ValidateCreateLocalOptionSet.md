# Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::ValidateCreateLocalOptionSet

- ea: `0x22080`
- end: `0x2223e`
- name: `Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::ValidateCreateLocalOptionSet`
- size: `446`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x21f90`

## callees

- `0x1f210`
- `0x22080`
- `0x22240`

## string_xrefs

- `0x2213b`: `Only Local option set can be created through the attribute create. IsGlobal flag must be set to 'false'.`
- `0x2216a`: `Only Local option set can be created through the attribute create. IsGlobal flag must be set to 'false'.`
- `0x22201`: `Only Local boolean option set can be created through the attribute create. IsGlobal flag must be set to 'false'.`
- `0x2222d`: `Only Local boolean option set can be created through the attribute create. IsGlobal flag must be set to 'false'.`

## pseudocode

```c

```

## disassembly

```asm
0x22080  ldarg.1
0x22081  ldstr    aGlobaloptionse_0// "GlobalOptionSet"
0x22086  ldloca.s 0
0x22088  callvirt instance bool [System.Web.OData]System.Web.OData.Delta::TryGetPropertyValue(string, object&)
0x2208d  pop
0x2208e  ldloc.0
0x2208f  brfalse.s loc_220A3
0x22091  ldarg.1
0x22092  ldstr    aIsglobal// "IsGlobal"
0x22097  ldc.i4.1
0x22098  box      [mscorlib]System.Boolean
0x2209d  callvirt instance bool [System.Web.OData]System.Web.OData.Delta::TrySetPropertyValue(string, object)
0x220a2  pop
0x220a3  ldarg.1
0x220a4  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<string> [System.Web.OData]System.Web.OData.Delta::GetChangedPropertyNames()
0x220a9  ldstr    aGlobaloptionse_0// "GlobalOptionSet"
0x220ae  call     T0x2B00001F
0x220b3  stloc.1
0x220b4  ldarg.0
0x220b5  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x220ba  callvirt instance class [mscorlib]System.Type [mscorlib]System.Type::get_BaseType()
0x220bf  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EnumAttributeMetadata
0x220c4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x220c9  callvirt instance bool [mscorlib]System.Type::Equals(class [mscorlib]System.Type)
0x220ce  brfalse  loc_2217A
0x220d3  ldarg.0
0x220d4  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EnumAttributeMetadata
0x220d9  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.OptionSetMetadata [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EnumAttributeMetadata::get_OptionSet()
0x220de  brfalse  loc_2217A
0x220e3  ldarg.0
0x220e4  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EnumAttributeMetadata
0x220e9  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.OptionSetMetadata [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EnumAttributeMetadata::get_OptionSet()
0x220ee  stloc.2
0x220ef  ldloc.2
0x220f0  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.OptionSetMetadataBase::get_IsGlobal()
0x220f5  stloc.3
0x220f6  ldloc.2
0x220f7  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataBase::get_MetadataId()
0x220fc  stloc.s  5
0x220fe  ldloca.s 5
0x22100  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x22105  brtrue.s loc_2210A
0x22107  ldnull
0x22108  br.s     loc_22123
0x2210a  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Extensibility.OData.CrmODataUtilities::GetMetadataCache()
0x2210f  ldloc.2
0x22110  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataBase::get_MetadataId()
0x22115  stloc.s  5
0x22117  ldloca.s 5
0x22119  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0x2211e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetOptionSet(valuetype [mscorlib]System.Guid)
0x22123  stloc.s  4
0x22125  ldloca.s 3
0x22127  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x2212c  brfalse.s loc_2214B
0x2212e  ldloca.s 3
0x22130  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x22135  brfalse.s loc_2214B
0x22137  ldloc.s  4
0x22139  brtrue.s loc_2214B
0x2213b  ldstr    aOnlyLocalOptio// "Only Local option set can be created th"...
0x22140  ldc.i4   0x80048403
0x22145  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x2214a  throw
0x2214b  ldloca.s 3
0x2214d  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x22152  brfalse.s loc_2215D
0x22154  ldloca.s 3
0x22156  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x2215b  br.s     loc_2215E
0x2215d  ldc.i4.0
0x2215e  ldloc.1
0x2215f  ldloc.0
0x22160  call     bool Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::ValidateGlobalOptionSetCreateValue(bool isGlobal, bool isGlobalOptionSetPropertyNamePresent, object optionsetValue)
0x22165  brfalse  loc_2223D
0x2216a  ldstr    aOnlyLocalOptio// "Only Local option set can be created th"...
0x2216f  ldc.i4   0x80048403
0x22174  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x22179  throw
0x2217a  ldarg.0
0x2217b  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x22180  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.BooleanAttributeMetadata
0x22185  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2218a  callvirt instance bool [mscorlib]System.Type::Equals(class [mscorlib]System.Type)
0x2218f  brfalse  loc_2223D
0x22194  ldarg.0
0x22195  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.BooleanAttributeMetadata
0x2219a  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.BooleanOptionSetMetadata [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.BooleanAttributeMetadata::get_OptionSet()
0x2219f  brfalse  loc_2223D
0x221a4  ldarg.0
0x221a5  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.BooleanAttributeMetadata
0x221aa  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.BooleanOptionSetMetadata [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.BooleanAttributeMetadata::get_OptionSet()
0x221af  stloc.s  6
0x221b1  ldloc.s  6
0x221b3  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.OptionSetMetadataBase::get_IsGlobal()
0x221b8  stloc.s  7
0x221ba  ldloc.s  6
0x221bc  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataBase::get_MetadataId()
0x221c1  stloc.s  5
0x221c3  ldloca.s 5
0x221c5  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x221ca  brtrue.s loc_221CF
0x221cc  ldnull
0x221cd  br.s     loc_221E9
0x221cf  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Extensibility.OData.CrmODataUtilities::GetMetadataCache()
0x221d4  ldloc.s  6
0x221d6  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataBase::get_MetadataId()
0x221db  stloc.s  5
0x221dd  ldloca.s 5
0x221df  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0x221e4  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetOptionSet(valuetype [mscorlib]System.Guid)
0x221e9  stloc.s  8
0x221eb  ldloca.s 7
0x221ed  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x221f2  brfalse.s loc_22211
0x221f4  ldloca.s 7
0x221f6  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x221fb  brfalse.s loc_22211
0x221fd  ldloc.s  8
0x221ff  brtrue.s loc_22211
0x22201  ldstr    aOnlyLocalBoole// "Only Local boolean option set can be cr"...
0x22206  ldc.i4   0x80048403
0x2220b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x22210  throw
0x22211  ldloca.s 7
0x22213  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x22218  brfalse.s loc_22223
0x2221a  ldloca.s 7
0x2221c  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x22221  br.s     loc_22224
0x22223  ldc.i4.0
0x22224  ldloc.1
0x22225  ldloc.0
0x22226  call     bool Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::ValidateGlobalOptionSetCreateValue(bool isGlobal, bool isGlobalOptionSetPropertyNamePresent, object optionsetValue)
0x2222b  brfalse.s loc_2223D
0x2222d  ldstr    aOnlyLocalBoole// "Only Local boolean option set can be cr"...
0x22232  ldc.i4   0x80048403
0x22237  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x2223c  throw
0x2223d  ret
```
