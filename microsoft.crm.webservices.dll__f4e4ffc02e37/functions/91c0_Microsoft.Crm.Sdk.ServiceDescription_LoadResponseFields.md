# Microsoft.Crm.Sdk.ServiceDescription::LoadResponseFields

- ea: `0x91c0`
- end: `0x92a2`
- name: `Microsoft.Crm.Sdk.ServiceDescription::LoadResponseFields`
- size: `226`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x8fa0`

## callees

- `0xf00`
- `0x63b0`
- `0x91c0`
- `0x92b0`
- `0x93a0`

## pseudocode

```c

```

## disassembly

```asm
0x91c0  ldarg.1
0x91c1  callvirt instance class [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.FieldsType [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageResponseType::get_Fields()
0x91c6  dup
0x91c7  callvirt instance int32 [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.FieldsType::get_Count()
0x91cc  newarr   Microsoft.Crm.Sdk.ResponseFieldDescription
0x91d1  stloc.0
0x91d2  ldc.i4.0
0x91d3  stloc.1
0x91d4  callvirt instance class [mscorlib]System.Collections.IEnumerator [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.FieldsType::GetEnumerator()
0x91d9  stloc.2
0x91da  br       loc_927F
0x91df  ldloc.2
0x91e0  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x91e5  castclass [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.FieldType
0x91ea  stloc.3
0x91eb  ldloc.3
0x91ec  callvirt instance string [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.FieldType::get_Name()
0x91f1  stloc.s  4
0x91f3  ldarg.0
0x91f4  ldloc.3
0x91f5  callvirt instance string [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.FieldType::get_PublicName()
0x91fa  ldloc.s  4
0x91fc  call     instance object Microsoft.Crm.Sdk.ServiceDescription::GetOptionalValue(object value, object defaultValue)
0x9201  callvirt instance string [mscorlib]System.Object::ToString()
0x9206  stloc.s  5
0x9208  ldarg.0
0x9209  ldloc.3
0x920a  callvirt instance string [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.FieldType::get_Value()
0x920f  ldarg.2
0x9210  call     instance class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.ConversionDescription Microsoft.Crm.Sdk.ServiceDescription::LoadConversionDescription(string text, class [mscorlib]System.Collections.Generic.IDictionary`2<string, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.IConverter> convertersMap)
0x9215  stloc.s  6
0x9217  ldloc.3
0x9218  callvirt instance string [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.FieldType::get_ClrFormatter()
0x921d  stloc.s  7
0x921f  ldnull
0x9220  stloc.s  8
0x9222  ldloc.s  7
0x9224  brfalse.s loc_922F
0x9226  ldloc.s  7
0x9228  callvirt instance int32 [mscorlib]System.String::get_Length()
0x922d  brtrue.s loc_925C
0x922f  ldloc.3
0x9230  callvirt instance string [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.FieldType::get_Formatter()
0x9235  stloc.s  9
0x9237  ldarg.3
0x9238  ldloc.s  9
0x923a  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x923f  isinst   Microsoft.Crm.Sdk.IFieldFormatter
0x9244  stloc.s  8
0x9246  ldloc.s  8
0x9248  brtrue.s loc_9265
0x924a  ldstr    aUnknownFormatt// "Unknown formatter: "
0x924f  ldloc.s  9
0x9251  call     string [mscorlib]System.String::Concat(string, string)
0x9256  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x925b  throw
0x925c  ldloc.s  7
0x925e  newobj   instance void Microsoft.Crm.Sdk.ClrTypeFormatter::.ctor(string partialTypeName)
0x9263  stloc.s  8
0x9265  ldloc.0
0x9266  ldloc.1
0x9267  ldloc.s  4
0x9269  ldloc.s  5
0x926b  ldloc.3
0x926c  callvirt instance string [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.FieldType::get_Value()
0x9271  ldloc.s  6
0x9273  ldloc.s  8
0x9275  newobj   instance void Microsoft.Crm.Sdk.ResponseFieldDescription::.ctor(string name, string publicName, string value, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.ConversionDescription conversionDescription, class Microsoft.Crm.Sdk.IFieldFormatter formatter)
0x927a  stelem.ref
0x927b  ldloc.1
0x927c  ldc.i4.1
0x927d  add
0x927e  stloc.1
0x927f  ldloc.2
0x9280  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x9285  brtrue   loc_91DF
0x928a  leave.s  loc_92A0
0x928c  ldloc.2
0x928d  isinst   [mscorlib]System.IDisposable
0x9292  stloc.s  0xA
0x9294  ldloc.s  0xA
0x9296  brfalse.s loc_929F
0x9298  ldloc.s  0xA
0x929a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x929f  endfinally
0x92a0  ldloc.0
0x92a1  ret
```
