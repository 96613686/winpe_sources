# Microsoft.Crm.ObjectModel.AsyncXrmLogger::GetCustomProperties

- ea: `0xc0dc0`
- end: `0xc1085`
- name: `Microsoft.Crm.ObjectModel.AsyncXrmLogger::GetCustomProperties`
- size: `709`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x236ba0`

## callees

- `0xc0dc0`
- `0xc1100`
- `0xc1110`
- `0xc1120`
- `0xc1130`
- `0xc1140`
- `0xc1150`
- `0xc1160`
- `0xc1170`
- `0xc1180`
- `0xc1190`
- `0xc11a0`
- `0xc11b0`
- `0xc11c0`
- `0xc11d0`
- `0xc11e0`
- `0xc11f0`
- `0xc1200`
- `0xc1210`
- `0xc1220`
- `0xc1230`
- `0xc1240`
- `0xc1250`
- `0xc1260`

## string_xrefs

- `0xc0e7d`: `OwningExtensionId`
- `0xc0e9c`: `OwningExtensionName`
- `0xc0eb6`: `OwningExtensionTypeCode`
- `0xc0ecf`: `OwningExtensionType`
- `0xc0f55`: `CreatedOn`
- `0xc0fbe`: `CorrelationTokenId`
- `0xc0fdd`: `CorrelationTokenParentPluginExecutionId`

## pseudocode

```c

```

## disassembly

```asm
0xc0dc0  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0xc0dc5  stloc.0
0xc0dc6  ldloc.0
0xc0dc7  ldstr    aAsyncmanagerna// "AsyncManagerNames"
0xc0dcc  ldarg.2
0xc0dcd  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xc0dd2  ldarg.1
0xc0dd3  brfalse  loc_C1083
0xc0dd8  ldloc.0
0xc0dd9  ldstr    aAsyncoperation// "AsyncOperationId"
0xc0dde  ldarg.1
0xc0ddf  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.ObjectModel.IAsyncExecutionUnit::get_AsyncOperationId()
0xc0de4  stloc.1
0xc0de5  ldloca.s 1
0xc0de7  constrained. [mscorlib]System.Guid
0xc0ded  callvirt instance string [mscorlib]System.Object::ToString()
0xc0df2  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xc0df7  ldloc.0
0xc0df8  ldstr    aOperationtype_0// "OperationType"
0xc0dfd  ldarg.1
0xc0dfe  callvirt instance int32 Microsoft.Crm.ObjectModel.IAsyncExecutionUnit::get_OperationType()
0xc0e03  stloc.2
0xc0e04  ldloca.s 2
0xc0e06  call     instance string [mscorlib]System.Int32::ToString()
0xc0e0b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xc0e10  ldloc.0
0xc0e11  ldstr    aRegardingobjec// "RegardingObjectId"
0xc0e16  ldarg.1
0xc0e17  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.ObjectModel.IAsyncExecutionUnit::get_RegardingObjectId()
0xc0e1c  stloc.1
0xc0e1d  ldloca.s 1
0xc0e1f  constrained. [mscorlib]System.Guid
0xc0e25  callvirt instance string [mscorlib]System.Object::ToString()
0xc0e2a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xc0e2f  ldloc.0
0xc0e30  ldstr    aRegardingobjec_4// "RegardingObjectName"
0xc0e35  ldarg.1
0xc0e36  callvirt instance string Microsoft.Crm.ObjectModel.IAsyncExecutionUnit::get_RegardingObjectName()
0xc0e3b  dup
0xc0e3c  brtrue.s loc_C0E44
0xc0e3e  pop
0xc0e3f  ldsfld   string [mscorlib]System.String::Empty
0xc0e44  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xc0e49  ldloc.0
0xc0e4a  ldstr    aRegardingobjec_5// "RegardingObjectTypeCode"
0xc0e4f  ldarg.1
0xc0e50  callvirt instance int32 Microsoft.Crm.ObjectModel.IAsyncExecutionUnit::get_RegardingObjectTypeCode()
0xc0e55  stloc.2
0xc0e56  ldloca.s 2
0xc0e58  call     instance string [mscorlib]System.Int32::ToString()
0xc0e5d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xc0e62  ldloc.0
0xc0e63  ldstr    aRegardingobjec_6// "RegardingObjectType"
0xc0e68  ldarg.1
0xc0e69  callvirt instance string Microsoft.Crm.ObjectModel.IAsyncExecutionUnit::get_RegardingObjectType()
0xc0e6e  dup
0xc0e6f  brtrue.s loc_C0E77
0xc0e71  pop
0xc0e72  ldsfld   string [mscorlib]System.String::Empty
0xc0e77  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xc0e7c  ldloc.0
0xc0e7d  ldstr    aOwningextensio// "OwningExtensionId"
0xc0e82  ldarg.1
0xc0e83  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.ObjectModel.IAsyncExecutionUnit::get_OwningExtensionId()
0xc0e88  stloc.1
0xc0e89  ldloca.s 1
0xc0e8b  constrained. [mscorlib]System.Guid
0xc0e91  callvirt instance string [mscorlib]System.Object::ToString()
0xc0e96  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xc0e9b  ldloc.0
0xc0e9c  ldstr    aOwningextensio_0// "OwningExtensionName"
0xc0ea1  ldarg.1
0xc0ea2  callvirt instance string Microsoft.Crm.ObjectModel.IAsyncExecutionUnit::get_OwningExtensionName()
0xc0ea7  dup
0xc0ea8  brtrue.s loc_C0EB0
0xc0eaa  pop
0xc0eab  ldsfld   string [mscorlib]System.String::Empty
0xc0eb0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xc0eb5  ldloc.0
0xc0eb6  ldstr    aOwningextensio_1// "OwningExtensionTypeCode"
0xc0ebb  ldarg.1
0xc0ebc  callvirt instance int32 Microsoft.Crm.ObjectModel.IAsyncExecutionUnit::get_OwningExtensionTypeCode()
0xc0ec1  stloc.2
0xc0ec2  ldloca.s 2
0xc0ec4  call     instance string [mscorlib]System.Int32::ToString()
0xc0ec9  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xc0ece  ldloc.0
0xc0ecf  ldstr    aOwningextensio_2// "OwningExtensionType"
0xc0ed4  ldarg.1
0xc0ed5  callvirt instance string Microsoft.Crm.ObjectModel.IAsyncExecutionUnit::get_OwningExtensionType()
0xc0eda  dup
0xc0edb  brtrue.s loc_C0EE3
0xc0edd  pop
0xc0ede  ldsfld   string [mscorlib]System.String::Empty
0xc0ee3  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xc0ee8  ldloc.0
0xc0ee9  ldstr    aMessagename_1// "MessageName"
0xc0eee  ldarg.1
0xc0eef  callvirt instance string Microsoft.Crm.ObjectModel.IAsyncExecutionUnit::get_MessageName()
0xc0ef4  dup
0xc0ef5  brtrue.s loc_C0EFD
0xc0ef7  pop
0xc0ef8  ldsfld   string [mscorlib]System.String::Empty
0xc0efd  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xc0f02  ldloc.0
0xc0f03  ldstr    aOwnerid_0// "OwnerId"
0xc0f08  ldarg.1
0xc0f09  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.ObjectModel.IAsyncExecutionUnit::get_OwnerId()
0xc0f0e  stloc.1
0xc0f0f  ldloca.s 1
0xc0f11  constrained. [mscorlib]System.Guid
0xc0f17  callvirt instance string [mscorlib]System.Object::ToString()
0xc0f1c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xc0f21  ldloc.0
0xc0f22  ldstr    aRecurrencepatt_0// "RecurrencePattern"
0xc0f27  ldarg.1
0xc0f28  callvirt instance string Microsoft.Crm.ObjectModel.IAsyncExecutionUnit::get_RecurrencePattern()
0xc0f2d  dup
0xc0f2e  brtrue.s loc_C0F36
0xc0f30  pop
0xc0f31  ldsfld   string [mscorlib]System.String::Empty
0xc0f36  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xc0f3b  ldloc.0
0xc0f3c  ldstr    aRecurrencestar_0// "RecurrenceStartTime"
0xc0f41  ldarg.1
0xc0f42  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.ObjectModel.IAsyncExecutionUnit::get_RecurrenceStartTime()
0xc0f47  stloc.3
0xc0f48  ldloca.s 3
0xc0f4a  call     instance string [mscorlib]System.DateTime::ToString()
0xc0f4f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xc0f54  ldloc.0
0xc0f55  ldstr    aCreatedon_0// "CreatedOn"
0xc0f5a  ldarg.1
0xc0f5b  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.ObjectModel.IAsyncExecutionUnit::get_CreatedOn()
0xc0f60  stloc.3
0xc0f61  ldloca.s 3
0xc0f63  call     instance string [mscorlib]System.DateTime::ToString()
0xc0f68  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xc0f6d  ldloc.0
0xc0f6e  ldstr    aModifiedon_1// "ModifiedOn"
0xc0f73  ldarg.1
0xc0f74  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.ObjectModel.IAsyncExecutionUnit::get_ModifiedOn()
0xc0f79  stloc.3
0xc0f7a  ldloca.s 3
0xc0f7c  call     instance string [mscorlib]System.DateTime::ToString()
0xc0f81  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xc0f86  ldloc.0
0xc0f87  ldstr    aPostponeuntil_1// "PostponeUntil"
0xc0f8c  ldarg.1
0xc0f8d  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> Microsoft.Crm.ObjectModel.IAsyncExecutionUnit::get_PostponeUntil()
0xc0f92  stloc.s  4
0xc0f94  ldloca.s 4
0xc0f96  dup
0xc0f97  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_HasValue()
0xc0f9c  brtrue.s loc_C0FA2
0xc0f9e  pop
0xc0f9f  ldnull
0xc0fa0  br.s     loc_C0FAF
0xc0fa2  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::GetValueOrDefault()
0xc0fa7  stloc.3
0xc0fa8  ldloca.s 3
0xc0faa  call     instance string [mscorlib]System.DateTime::ToString()
0xc0faf  dup
0xc0fb0  brtrue.s loc_C0FB8
0xc0fb2  pop
0xc0fb3  ldsfld   string [mscorlib]System.String::Empty
0xc0fb8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xc0fbd  ldloc.0
0xc0fbe  ldstr    aCorrelationtok_1// "CorrelationTokenId"
0xc0fc3  ldarg.1
0xc0fc4  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.ObjectModel.IAsyncExecutionUnit::get_CorrelationTokenId()
0xc0fc9  stloc.1
0xc0fca  ldloca.s 1
0xc0fcc  constrained. [mscorlib]System.Guid
0xc0fd2  callvirt instance string [mscorlib]System.Object::ToString()
0xc0fd7  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xc0fdc  ldloc.0
0xc0fdd  ldstr    aCorrelationtok_2// "CorrelationTokenParentPluginExecutionId"
0xc0fe2  ldarg.1
0xc0fe3  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.ObjectModel.IAsyncExecutionUnit::get_CorrelationTokenParentPluginExecutionId()
0xc0fe8  stloc.1
0xc0fe9  ldloca.s 1
0xc0feb  constrained. [mscorlib]System.Guid
0xc0ff1  callvirt instance string [mscorlib]System.Object::ToString()
0xc0ff6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xc0ffb  ldloc.0
0xc0ffc  ldstr    aRetrycount_0// "RetryCount"
0xc1001  ldarg.1
0xc1002  callvirt instance int32 Microsoft.Crm.ObjectModel.IAsyncExecutionUnit::get_RetryCount()
0xc1007  stloc.2
0xc1008  ldloca.s 2
0xc100a  call     instance string [mscorlib]System.Int32::ToString()
0xc100f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xc1014  ldloc.0
0xc1015  ldstr    aRequestid_0// "RequestId"
0xc101a  ldarg.1
0xc101b  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.ObjectModel.IAsyncExecutionUnit::get_RequestId()
0xc1020  stloc.s  5
0xc1022  ldloca.s 5
0xc1024  dup
0xc1025  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0xc102a  brtrue.s loc_C1030
0xc102c  pop
0xc102d  ldnull
0xc102e  br.s     loc_C1043
0xc1030  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::GetValueOrDefault()
0xc1035  stloc.1
0xc1036  ldloca.s 1
0xc1038  constrained. [mscorlib]System.Guid
0xc103e  callvirt instance string [mscorlib]System.Object::ToString()
0xc1043  dup
0xc1044  brtrue.s loc_C104C
0xc1046  pop
0xc1047  ldsfld   string [mscorlib]System.String::Empty
0xc104c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xc1051  ldloc.0
0xc1052  ldstr    aSubtype_0// "SubType"
0xc1057  ldarg.1
0xc1058  callvirt instance int32 Microsoft.Crm.ObjectModel.IAsyncExecutionUnit::get_SubType()
0xc105d  stloc.2
0xc105e  ldloca.s 2
0xc1060  call     instance string [mscorlib]System.Int32::ToString()
0xc1065  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xc106a  ldloc.0
0xc106b  ldstr    aDepth_0// "Depth"
0xc1070  ldarg.1
0xc1071  callvirt instance int32 Microsoft.Crm.ObjectModel.IAsyncExecutionUnit::get_Depth()
0xc1076  stloc.2
0xc1077  ldloca.s 2
0xc1079  call     instance string [mscorlib]System.Int32::ToString()
0xc107e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xc1083  ldloc.0
0xc1084  ret
```
