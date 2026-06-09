# Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::DeleteNavigationResource

- ea: `0x225f0`
- end: `0x227d2`
- name: `Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::DeleteNavigationResource`
- size: `482`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x12e90`

## callees

- `0x1f210`
- `0x1f280`
- `0x214c0`
- `0x225f0`
- `0x23b70`
- `0x23bb0`
- `0x23d10`
- `0x23d50`
- `0x23ec0`
- `0x24570`
- `0x245d0`
- `0x24620`
- `0x336c0`

## string_xrefs

- `0x2264d`: `Delete on Navigation Property is only supported on Contained Metadata Entities.`

## pseudocode

```c

```

## disassembly

```asm
0x225f0  ldarg.3
0x225f1  ldloca.s 0
0x225f3  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0x225f8  ldc.i4.0
0x225f9  ceq
0x225fb  stloc.2
0x225fc  ldarg.s  5
0x225fe  ldloca.s 1
0x22600  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0x22605  ldc.i4.0
0x22606  ceq
0x22608  stloc.3
0x22609  ldnull
0x2260a  stloc.s  4
0x2260c  ldnull
0x2260d  stloc.s  5
0x2260f  ldarg.2
0x22610  ldarg.0
0x22611  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::edmModel
0x22616  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata Microsoft.Crm.Extensibility.OData.CrmODataMetadataUtilities::GetCrmMetadataEntityMetadataFromEdmEntityName(string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x2261b  dup
0x2261c  callvirt instance class [mscorlib]System.Type [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata::get_ClrType()
0x22621  stloc.s  6
0x22623  ldarg.s  4
0x22625  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata Microsoft.Crm.Extensibility.OData.CrmODataMetadataUtilities::GetXrmEntityMetadataOfNavigationPropertyName(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata xrmEntityMetadata, string edmNavigationPropertyName)
0x2262a  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Extensibility.OData.CrmODataUtilities::GetMetadataCache()
0x2262f  stloc.s  7
0x22631  dup
0x22632  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ODataV4NameFormatter::GetEdmEntityNameForMetadataEntity(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata)
0x22637  stloc.s  8
0x22639  dup
0x2263a  callvirt instance class [mscorlib]System.Type [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata::get_ClrType()
0x2263f  stloc.s  9
0x22641  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntitiesCache Microsoft.Crm.Extensibility.OData.CrmODataUtilities::GetMetadataForMetadataCache()
0x22646  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEdmEntityProvider::IsContainedEntity(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntityMetadata, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntitiesCache)
0x2264b  brtrue.s loc_2265D
0x2264d  ldstr    aDeleteOnNaviga// "Delete on Navigation Property is only s"...
0x22652  ldstr    aGet_0// "GET"
0x22657  call     class [Microsoft.Crm.Core]Microsoft.Crm.CrmHttpException Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::CreateExceptionDataMethodNotAllowed(string exceptionMessage, string allowedMethods)
0x2265c  throw
0x2265d  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection::.ctor()
0x22662  stloc.s  0xA
0x22664  ldloc.2
0x22665  brfalse.s loc_22689
0x22667  ldarg.3
0x22668  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Extensibility.OData.CrmODataUtilities::ParseAlternateKeys(string key)
0x2266d  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Values()
0x22672  call     T0x2B00008E
0x22677  stloc.s  4
0x22679  ldloc.s  7
0x2267b  ldloc.s  4
0x2267d  ldc.i4.1
0x2267e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x22683  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Id()
0x22688  stloc.0
0x22689  ldloc.3
0x2268a  brfalse.s loc_2269F
0x2268c  ldarg.s  5
0x2268e  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Extensibility.OData.CrmODataUtilities::ParseAlternateKeys(string key)
0x22693  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Values()
0x22698  call     T0x2B00008E
0x2269d  stloc.s  5
0x2269f  ldloc.s  6
0x226a1  call     bool Microsoft.Crm.Extensibility.OData.CrmODataMetadataUtilities::IsOptionSetMetadata(class [mscorlib]System.Type crmType)
0x226a6  brfalse.s loc_2271C
0x226a8  newobj   instance void <>c__DisplayClass20_0::.ctor()
0x226ad  stloc.s  0xB
0x226af  ldloc.s  7
0x226b1  ldloc.0
0x226b2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetOptionSet(valuetype [mscorlib]System.Guid)
0x226b7  stloc.s  0xC
0x226b9  ldloc.s  0xB
0x226bb  ldarg.s  5
0x226bd  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x226c2  stfld    valuetype [mscorlib]System.Guid <>c__DisplayClass20_0::optionId
0x226c7  ldloc.s  0xC
0x226c9  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEnumOptionByValueDictionary [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetMetadata::get_Options()
0x226ce  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<var<u1>> class [mscorlib]System.Collections.Generic.IDictionary`2<int32, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption>::get_Values()
0x226d3  ldloc.s  0xB
0x226d5  ldftn    instance bool <>c__DisplayClass20_0::<DeleteNavigationResource>b__0(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption a)
0x226db  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption, bool>::.ctor(object, native int)
0x226e0  call     T0x2B0000C8
0x226e5  call     T0x2B0000C9
0x226ea  stloc.s  0xD
0x226ec  ldloc.s  0xA
0x226ee  ldstr    aOptionsetname// "OptionSetName"
0x226f3  ldloc.s  0xC
0x226f5  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetMetadata::get_Name()
0x226fa  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Add(var<u1>, !!T0)
0x226ff  ldloc.s  0xA
0x22701  ldstr    aValue_0// "Value"
0x22706  ldloc.s  0xD
0x22708  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption::get_Value()
0x2270d  box      [mscorlib]System.Int32
0x22712  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Add(var<u1>, !!T0)
0x22717  br       loc_227B4
0x2271c  ldloc.2
0x2271d  brfalse.s loc_2272B
0x2271f  ldloc.s  7
0x22721  ldloc.s  4
0x22723  ldc.i4.1
0x22724  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x22729  br.s     loc_22733
0x2272b  ldloc.s  7
0x2272d  ldloc.0
0x2272e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetEntity(valuetype [mscorlib]System.Guid)
0x22733  stloc.s  0xE
0x22735  ldloc.s  0xA
0x22737  ldstr    aEntitylogicaln// "EntityLogicalName"
0x2273c  ldloc.s  0xE
0x2273e  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x22743  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Add(var<u1>, !!T0)
0x22748  ldloc.s  9
0x2274a  call     bool Microsoft.Crm.Extensibility.OData.CrmODataMetadataUtilities::IsAttributeMetadata(class [mscorlib]System.Type xrmType)
0x2274f  brfalse.s loc_2277F
0x22751  ldloc.3
0x22752  brfalse.s loc_22760
0x22754  ldloc.s  0xE
0x22756  ldloc.s  5
0x22758  ldc.i4.1
0x22759  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::TryGetAttribute(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x2275e  br.s     loc_22768
0x22760  ldloc.s  7
0x22762  ldloc.1
0x22763  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetAttribute(valuetype [mscorlib]System.Guid)
0x22768  stloc.s  0xF
0x2276a  ldloc.s  0xA
0x2276c  ldstr    aLogicalname// "LogicalName"
0x22771  ldloc.s  0xF
0x22773  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x22778  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Add(var<u1>, !!T0)
0x2277d  br.s     loc_227B4
0x2277f  ldloc.s  9
0x22781  call     bool Microsoft.Crm.Extensibility.OData.CrmODataMetadataUtilities::IsEntityKeyMetadata(class [mscorlib]System.Type xrmType)
0x22786  brfalse.s loc_227B4
0x22788  ldloc.3
0x22789  brfalse.s loc_22797
0x2278b  ldloc.s  0xE
0x2278d  ldloc.s  5
0x2278f  ldc.i4.1
0x22790  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityKeyMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::TryGetEntityKey(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x22795  br.s     loc_2279F
0x22797  ldloc.s  7
0x22799  ldloc.1
0x2279a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityKeyMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetEntityKey(valuetype [mscorlib]System.Guid)
0x2279f  stloc.s  0x10
0x227a1  ldloc.s  0xA
0x227a3  ldstr    aName_0// "Name"
0x227a8  ldloc.s  0x10
0x227aa  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityKeyMetadata::get_LogicalName()
0x227af  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Add(var<u1>, !!T0)
0x227b4  ldloc.3
0x227b5  brtrue.s loc_227C5
0x227b7  ldarg.0
0x227b8  ldarg.1
0x227b9  ldloc.s  8
0x227bb  ldloc.1
0x227bc  ldloc.s  0xA
0x227be  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::ExecuteMetadataDelete(class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context, string edmEntityName, valuetype [mscorlib]System.Guid metadataId, [opt] class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection boundParameterCollection)
0x227c3  pop
0x227c4  ret
0x227c5  ldarg.0
0x227c6  ldarg.1
0x227c7  ldloc.s  8
0x227c9  ldloc.s  0xA
0x227cb  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::ExecuteMetadataDeleteAlternateKey(class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context, string edmEntityName, [opt] class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection boundParameterCollection)
0x227d0  pop
0x227d1  ret
```
