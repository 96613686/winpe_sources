# Microsoft.Crm.Asynchronous.FlowNotificationService::GetTabularEntityFromCrmEntity

- ea: `0x1b80`
- end: `0x1d92`
- name: `Microsoft.Crm.Asynchronous.FlowNotificationService::GetTabularEntityFromCrmEntity`
- size: `530`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1990`

## callees

- `0xe70`
- `0xf10`
- `0x1b80`
- `0x1da0`

## pseudocode

```c

```

## disassembly

```asm
0x1b80  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x1b85  stloc.0
0x1b86  ldarg.0
0x1b87  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x1b8c  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0>> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::GetEnumerator()
0x1b91  stloc.1
0x1b92  br       loc_1D79
0x1b97  ldloc.1
0x1b98  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>>::get_Current()
0x1b9d  stloc.2
0x1b9e  ldarg.1
0x1b9f  ldloca.s 2
0x1ba1  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Key()
0x1ba6  ldloca.s 3
0x1ba8  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata>::TryGetValue(var<u1>, !!T0)
0x1bad  brfalse  loc_1D79
0x1bb2  ldloc.3
0x1bb3  isinst   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.LookupAttributeMetadata
0x1bb8  brfalse.s loc_1C2C
0x1bba  ldloca.s 2
0x1bbc  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Value()
0x1bc1  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x1bc6  stloc.s  6
0x1bc8  ldloc.0
0x1bc9  ldstr    asc_1AAF6// "_"
0x1bce  ldloca.s 2
0x1bd0  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Key()
0x1bd5  ldstr    aValue_0// "_value"
0x1bda  call     string [mscorlib]System.String::Concat(string, string, string)
0x1bdf  ldloc.s  6
0x1be1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x1be6  stloc.s  8
0x1be8  ldloca.s 8
0x1bea  constrained. [mscorlib]System.Guid
0x1bf0  callvirt instance string [mscorlib]System.Object::ToString()
0x1bf5  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::Add(var<u1>, !!T0)
0x1bfa  ldloc.s  6
0x1bfc  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_LogicalName()
0x1c01  stloc.s  7
0x1c03  ldloc.0
0x1c04  ldstr    asc_1AAF6// "_"
0x1c09  ldloca.s 2
0x1c0b  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Key()
0x1c10  ldstr    aType// "_type"
0x1c15  call     string [mscorlib]System.String::Concat(string, string, string)
0x1c1a  ldloc.s  7
0x1c1c  ldarg.3
0x1c1d  call     string Microsoft.Crm.Asynchronous.FlowNotificationService::GetEntityTableName(string entityLogicalName, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache metadataCache)
0x1c22  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::Add(var<u1>, !!T0)
0x1c27  br       loc_1D79
0x1c2c  ldloc.3
0x1c2d  isinst   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EnumAttributeMetadata
0x1c32  brfalse  loc_1D42
0x1c37  ldloc.3
0x1c38  ldloca.s 2
0x1c3a  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Value()
0x1c3f  ldstr    aInteger// "integer"
0x1c44  ldnull
0x1c45  call     object Microsoft.Crm.Asynchronous.TabularDataConverter::ConvertSytemObjectToTabluarType(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata attribute, object systemObject, string dataType, string expectedDataFormat)
0x1c4a  stloc.s  9
0x1c4c  ldloc.0
0x1c4d  ldstr    asc_1AAF6// "_"
0x1c52  ldloca.s 2
0x1c54  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Key()
0x1c59  ldstr    aValue_0// "_value"
0x1c5e  call     string [mscorlib]System.String::Concat(string, string, string)
0x1c63  ldloc.s  9
0x1c65  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::Add(var<u1>, !!T0)
0x1c6a  ldloc.s  9
0x1c6c  brtrue.s loc_1C85
0x1c6e  ldloc.0
0x1c6f  ldloca.s 2
0x1c71  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Key()
0x1c76  ldsfld   string [mscorlib]System.String::Empty
0x1c7b  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::Add(var<u1>, !!T0)
0x1c80  br       loc_1D79
0x1c85  ldsfld   string [mscorlib]System.String::Empty
0x1c8a  stloc.s  0xA
0x1c8c  ldloc.3
0x1c8d  isinst   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EnumAttributeMetadata
0x1c92  stloc.s  0xB
0x1c94  ldloc.s  0xB
0x1c96  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.OptionSetMetadata [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EnumAttributeMetadata::get_OptionSet()
0x1c9b  brfalse  loc_1D31
0x1ca0  ldloc.s  0xB
0x1ca2  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.OptionSetMetadata [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EnumAttributeMetadata::get_OptionSet()
0x1ca7  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.OptionMetadataCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.OptionSetMetadata::get_Options()
0x1cac  callvirt instance var<u1>[] class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.OptionMetadata>::ToArray()
0x1cb1  stloc.s  0xC
0x1cb3  ldc.i4.0
0x1cb4  stloc.s  0xD
0x1cb6  br.s     loc_1D29
0x1cb8  ldloc.s  0xC
0x1cba  ldloc.s  0xD
0x1cbc  ldelem.ref
0x1cbd  stloc.s  0xE
0x1cbf  ldloc.s  0xE
0x1cc1  callvirt instance valuetype [mscorlib]System.Nullable`1<int32> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.OptionMetadata::get_Value()
0x1cc6  stloc.s  0x10
0x1cc8  ldloca.s 0x10
0x1cca  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0x1ccf  ldloc.s  9
0x1cd1  unbox.any valuetype [mscorlib]System.Nullable`1<int32>
0x1cd6  stloc.s  0xF
0x1cd8  ldloca.s 0xF
0x1cda  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::GetValueOrDefault()
0x1cdf  beq.s    loc_1CE4
0x1ce1  ldc.i4.0
0x1ce2  br.s     loc_1CEB
0x1ce4  ldloca.s 0xF
0x1ce6  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x1ceb  brfalse.s loc_1D23
0x1ced  ldloc.s  0xE
0x1cef  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Label [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.OptionMetadata::get_Label()
0x1cf4  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.LocalizedLabel [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Label::get_UserLocalizedLabel()
0x1cf9  dup
0x1cfa  brtrue.s loc_1D00
0x1cfc  pop
0x1cfd  ldnull
0x1cfe  br.s     loc_1D05
0x1d00  call     instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.LocalizedLabel::get_Label()
0x1d05  dup
0x1d06  brtrue.s loc_1D1F
0x1d08  pop
0x1d09  ldloc.s  0xE
0x1d0b  callvirt instance valuetype [mscorlib]System.Nullable`1<int32> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.OptionMetadata::get_Value()
0x1d10  stloc.s  0xF
0x1d12  ldloca.s 0xF
0x1d14  constrained. valuetype [mscorlib]System.Nullable`1<int32>
0x1d1a  callvirt instance string [mscorlib]System.Object::ToString()
0x1d1f  stloc.s  0xA
0x1d21  br.s     loc_1D31
0x1d23  ldloc.s  0xD
0x1d25  ldc.i4.1
0x1d26  add
0x1d27  stloc.s  0xD
0x1d29  ldloc.s  0xD
0x1d2b  ldloc.s  0xC
0x1d2d  ldlen
0x1d2e  conv.i4
0x1d2f  blt.s    loc_1CB8
0x1d31  ldloc.0
0x1d32  ldloca.s 2
0x1d34  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Key()
0x1d39  ldloc.s  0xA
0x1d3b  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::Add(var<u1>, !!T0)
0x1d40  br.s     loc_1D79
0x1d42  ldloca.s 2
0x1d44  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Value()
0x1d49  brfalse.s loc_1D79
0x1d4b  ldnull
0x1d4c  stloc.s  4
0x1d4e  ldnull
0x1d4f  stloc.s  5
0x1d51  ldloc.3
0x1d52  ldloca.s 4
0x1d54  ldloca.s 5
0x1d56  call     void Microsoft.Crm.Asynchronous.TabularDataConverter::GetTabularDataTypeAndFormatForAttribute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata attribute, [out] string& dataType, [out] string& dataFormat)
0x1d5b  ldloc.0
0x1d5c  ldloca.s 2
0x1d5e  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Key()
0x1d63  ldloc.3
0x1d64  ldloca.s 2
0x1d66  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Value()
0x1d6b  ldloc.s  4
0x1d6d  ldloc.s  5
0x1d6f  call     object Microsoft.Crm.Asynchronous.TabularDataConverter::ConvertSytemObjectToTabluarType(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata attribute, object systemObject, string dataType, string expectedDataFormat)
0x1d74  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::Add(var<u1>, !!T0)
0x1d79  ldloc.1
0x1d7a  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1d7f  brtrue   loc_1B97
0x1d84  leave.s  loc_1D90
0x1d86  ldloc.1
0x1d87  brfalse.s loc_1D8F
0x1d89  ldloc.1
0x1d8a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1d8f  endfinally
0x1d90  ldloc.0
0x1d91  ret
```
