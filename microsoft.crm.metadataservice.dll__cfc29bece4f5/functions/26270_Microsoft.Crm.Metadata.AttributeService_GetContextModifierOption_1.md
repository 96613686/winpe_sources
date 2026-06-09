# Microsoft.Crm.Metadata.AttributeService::GetContextModifierOption_1

- ea: `0x26270`
- end: `0x26385`
- name: `Microsoft.Crm.Metadata.AttributeService::GetContextModifierOption_1`
- size: `277`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1da60`
- `0x261d0`
- `0x31340`

## callees

- `0x26270`

## string_xrefs

- `0x26304`: `TraversedPath`
- `0x26317`: `ProcessId`

## pseudocode

```c

```

## disassembly

```asm
0x26270  ldarg.0
0x26271  ldstr    aDescription_0// "description"
0x26276  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x2627b  ldarg.0
0x2627c  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeDescription::get_IsLogical()
0x26281  ldarg.1
0x26282  or
0x26283  brtrue   loc_26381
0x26288  ldarg.0
0x26289  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeDescription::get_AttributeOf()
0x2628e  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x26293  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x26298  brfalse.s loc_262BE
0x2629a  ldarg.0
0x2629b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeDescription::get_AttributeTypeId()
0x262a0  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeDictionary [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypes::get_AttributeTypesByName()
0x262a5  ldstr    aImage// "image"
0x262aa  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeDictionary::get_Item(object)
0x262af  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_Id()
0x262b4  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x262b9  brtrue   loc_26381
0x262be  ldarg.0
0x262bf  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeDescription::get_PhysicalName()
0x262c4  ldstr    aOwneridtype// "OwnerIdType"
0x262c9  call     bool [mscorlib]System.String::op_Equality(string, string)
0x262ce  brtrue   loc_26381
0x262d3  ldarg.0
0x262d4  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeDescription::get_PhysicalName()
0x262d9  ldstr    aEmailaddress// "EmailAddress"
0x262de  call     bool [mscorlib]System.String::op_Equality(string, string)
0x262e3  brtrue   loc_26381
0x262e8  ldarg.0
0x262e9  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeDescription::get_PhysicalName()
0x262ee  ldstr    aStageid// "StageId"
0x262f3  ldc.i4.5
0x262f4  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x262f9  brtrue   loc_26381
0x262fe  ldarg.0
0x262ff  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeDescription::get_PhysicalName()
0x26304  ldstr    aTraversedpath// "TraversedPath"
0x26309  ldc.i4.5
0x2630a  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x2630f  brtrue.s loc_26381
0x26311  ldarg.0
0x26312  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeDescription::get_PhysicalName()
0x26317  ldstr    aProcessid// "ProcessId"
0x2631c  ldc.i4.5
0x2631d  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x26322  brtrue.s loc_26381
0x26324  ldarg.0
0x26325  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeDescription::get_PhysicalName()
0x2632a  ldstr    aActivestageid// "ActiveStageId"
0x2632f  ldc.i4.5
0x26330  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x26335  brtrue.s loc_26381
0x26337  ldarg.0
0x26338  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeDescription::get_PhysicalName()
0x2633d  ldstr    aExchangerate// "ExchangeRate"
0x26342  call     bool [mscorlib]System.String::op_Equality(string, string)
0x26347  brtrue.s loc_26381
0x26349  ldarg.0
0x2634a  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeDescription::get_PhysicalName()
0x2634f  ldstr    aOnholdtime// "OnHoldTime"
0x26354  ldc.i4.5
0x26355  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x2635a  brtrue.s loc_26381
0x2635c  ldarg.0
0x2635d  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeDescription::get_PhysicalName()
0x26362  ldstr    aLastonholdtime// "LastOnHoldTime"
0x26367  ldc.i4.5
0x26368  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x2636d  brtrue.s loc_26381
0x2636f  ldarg.0
0x26370  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeDescription::get_PhysicalName()
0x26375  ldstr    aTransactioncur// "TransactionCurrencyId"
0x2637a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2637f  brfalse.s loc_26383
0x26381  ldc.i4.1
0x26382  ret
0x26383  ldc.i4.0
0x26384  ret
```
