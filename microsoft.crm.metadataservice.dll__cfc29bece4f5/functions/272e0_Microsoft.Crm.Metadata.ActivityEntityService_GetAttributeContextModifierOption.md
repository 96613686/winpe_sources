# Microsoft.Crm.Metadata.ActivityEntityService::GetAttributeContextModifierOption

- ea: `0x272e0`
- end: `0x2747f`
- name: `Microsoft.Crm.Metadata.ActivityEntityService::GetAttributeContextModifierOption`
- size: `415`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x26b20`
- `0x28eb0`
- `0x31340`

## callees

- `0x272e0`

## string_xrefs

- `0x27436`: `TraversedPath`
- `0x27410`: `ProcessId`

## pseudocode

```c

```

## disassembly

```asm
0x272e0  ldarg.0
0x272e1  ldstr    aDescription_0// "description"
0x272e6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x272eb  ldarg.1
0x272ec  ldstr    aContext// "context"
0x272f1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x272f6  ldarg.1
0x272f7  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x272fc  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::get_SolutionId()
0x27301  ldarg.1
0x27302  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.SolutionHelper::IsSystemOrInternalSystemConvertedSolution(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x27307  brfalse.s loc_2730B
0x27309  ldc.i4.0
0x2730a  ret
0x2730b  ldarg.0
0x2730c  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeDescription::get_IsLogical()
0x27311  brtrue   loc_2747B
0x27316  ldarg.0
0x27317  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeDescription::get_AttributeOf()
0x2731c  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x27321  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x27326  brfalse.s loc_2734C
0x27328  ldarg.0
0x27329  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeDescription::get_AttributeTypeId()
0x2732e  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeDictionary [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypes::get_AttributeTypesByName()
0x27333  ldstr    aImage// "image"
0x27338  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeDictionary::get_Item(object)
0x2733d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_Id()
0x27342  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x27347  brtrue   loc_2747B
0x2734c  ldarg.0
0x2734d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeDescription::get_AttributeTypeId()
0x27352  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeDictionary [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypes::get_AttributeTypesByName()
0x27357  ldstr    aPrimarykey// "primarykey"
0x2735c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeDictionary::get_Item(object)
0x27361  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_Id()
0x27366  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x2736b  brtrue   loc_2747B
0x27370  ldarg.0
0x27371  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeDescription::get_AttributeTypeId()
0x27376  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeDictionary [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypes::get_AttributeTypesByName()
0x2737b  ldstr    aLookup// "lookup"
0x27380  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeDictionary::get_Item(object)
0x27385  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_Id()
0x2738a  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x2738f  brtrue   loc_2747B
0x27394  ldarg.0
0x27395  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeDescription::get_AttributeTypeId()
0x2739a  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeDictionary [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypes::get_AttributeTypesByName()
0x2739f  ldstr    aTimestamp_1// "timestamp"
0x273a4  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeDictionary::get_Item(object)
0x273a9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_Id()
0x273ae  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x273b3  brtrue   loc_2747B
0x273b8  ldarg.0
0x273b9  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeDescription::get_PhysicalName()
0x273be  ldstr    aOwnerid_0// "OwnerId"
0x273c3  call     bool [mscorlib]System.String::op_Equality(string, string)
0x273c8  brtrue   loc_2747B
0x273cd  ldarg.0
0x273ce  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeDescription::get_PhysicalName()
0x273d3  ldstr    aOwneridtype// "OwnerIdType"
0x273d8  call     bool [mscorlib]System.String::op_Equality(string, string)
0x273dd  brtrue   loc_2747B
0x273e2  ldarg.0
0x273e3  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeDescription::get_PhysicalName()
0x273e8  ldstr    aExchangerate// "ExchangeRate"
0x273ed  call     bool [mscorlib]System.String::op_Equality(string, string)
0x273f2  brtrue   loc_2747B
0x273f7  ldarg.0
0x273f8  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeDescription::get_PhysicalName()
0x273fd  ldstr    aStageid// "StageId"
0x27402  ldc.i4.5
0x27403  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x27408  brtrue.s loc_2747B
0x2740a  ldarg.0
0x2740b  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeDescription::get_PhysicalName()
0x27410  ldstr    aProcessid// "ProcessId"
0x27415  ldc.i4.5
0x27416  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x2741b  brtrue.s loc_2747B
0x2741d  ldarg.0
0x2741e  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeDescription::get_PhysicalName()
0x27423  ldstr    aActivestageid// "ActiveStageId"
0x27428  ldc.i4.5
0x27429  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x2742e  brtrue.s loc_2747B
0x27430  ldarg.0
0x27431  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeDescription::get_PhysicalName()
0x27436  ldstr    aTraversedpath// "TraversedPath"
0x2743b  ldc.i4.5
0x2743c  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x27441  brtrue.s loc_2747B
0x27443  ldarg.0
0x27444  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeDescription::get_PhysicalName()
0x27449  ldstr    aOnholdtime// "OnHoldTime"
0x2744e  ldc.i4.5
0x2744f  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x27454  brtrue.s loc_2747B
0x27456  ldarg.0
0x27457  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeDescription::get_PhysicalName()
0x2745c  ldstr    aLastonholdtime// "LastOnHoldTime"
0x27461  ldc.i4.5
0x27462  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x27467  brtrue.s loc_2747B
0x27469  ldarg.0
0x2746a  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeDescription::get_PhysicalName()
0x2746f  ldstr    aTransactioncur// "TransactionCurrencyId"
0x27474  call     bool [mscorlib]System.String::op_Equality(string, string)
0x27479  brfalse.s loc_2747D
0x2747b  ldc.i4.1
0x2747c  ret
0x2747d  ldc.i4.0
0x2747e  ret
```
