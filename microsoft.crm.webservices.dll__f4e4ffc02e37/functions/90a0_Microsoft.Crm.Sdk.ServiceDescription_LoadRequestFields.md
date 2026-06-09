# Microsoft.Crm.Sdk.ServiceDescription::LoadRequestFields

- ea: `0x90a0`
- end: `0x91b9`
- name: `Microsoft.Crm.Sdk.ServiceDescription::LoadRequestFields`
- size: `281`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x8fd0`

## callees

- `0x1670`
- `0x5ce0`
- `0x90a0`
- `0x93a0`

## pseudocode

```c

```

## disassembly

```asm
0x90a0  ldarg.2
0x90a1  ldstr    aRequest_0// "request"
0x90a6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x90ab  ldarg.2
0x90ac  callvirt instance class [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.FieldsType [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageRequestType::get_Fields()
0x90b1  dup
0x90b2  callvirt instance int32 [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.FieldsType::get_Count()
0x90b7  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sdk.RequestFieldDescription>::.ctor(int32)
0x90bc  stloc.0
0x90bd  callvirt instance class [mscorlib]System.Collections.IEnumerator [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.FieldsType::GetEnumerator()
0x90c2  stloc.1
0x90c3  br       loc_9191
0x90c8  ldloc.1
0x90c9  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x90ce  castclass [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.FieldType
0x90d3  stloc.2
0x90d4  ldloc.2
0x90d5  callvirt instance bool [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.FieldType::get_Optional()
0x90da  brtrue   loc_9191
0x90df  ldloc.2
0x90e0  callvirt instance string [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.FieldType::get_Name()
0x90e5  stloc.3
0x90e6  ldarg.0
0x90e7  ldloc.2
0x90e8  callvirt instance string [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.FieldType::get_PublicName()
0x90ed  ldloc.2
0x90ee  callvirt instance string [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.FieldType::get_Name()
0x90f3  call     instance object Microsoft.Crm.Sdk.ServiceDescription::GetOptionalValue(object value, object defaultValue)
0x90f8  callvirt instance string [mscorlib]System.Object::ToString()
0x90fd  stloc.s  4
0x90ff  ldarg.0
0x9100  ldloc.2
0x9101  callvirt instance bool [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.FieldType::get_Optional()
0x9106  box      [mscorlib]System.Boolean
0x910b  ldc.i4.0
0x910c  box      [mscorlib]System.Boolean
0x9111  call     instance object Microsoft.Crm.Sdk.ServiceDescription::GetOptionalValue(object value, object defaultValue)
0x9116  unbox.any [mscorlib]System.Boolean
0x911b  stloc.s  5
0x911d  ldloc.s  4
0x911f  ldstr    aCategoryname// "{CategoryName}"
0x9124  ldarg.1
0x9125  callvirt instance string [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageType::get_CategoryName()
0x912a  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x912f  stloc.s  4
0x9131  ldloc.2
0x9132  callvirt instance string [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.FieldType::get_ClrParser()
0x9137  stloc.s  6
0x9139  ldnull
0x913a  stloc.s  7
0x913c  ldloc.s  6
0x913e  brfalse.s loc_9149
0x9140  ldloc.s  6
0x9142  callvirt instance int32 [mscorlib]System.String::get_Length()
0x9147  brtrue.s loc_9176
0x9149  ldloc.2
0x914a  callvirt instance string [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.FieldType::get_Parser()
0x914f  stloc.s  8
0x9151  ldarg.3
0x9152  ldloc.s  8
0x9154  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x9159  isinst   Microsoft.Crm.Sdk.IFieldParser
0x915e  stloc.s  7
0x9160  ldloc.s  7
0x9162  brtrue.s loc_917F
0x9164  ldstr    aUnknownParser// "Unknown parser: "
0x9169  ldloc.s  8
0x916b  call     string [mscorlib]System.String::Concat(string, string)
0x9170  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x9175  throw
0x9176  ldloc.s  6
0x9178  newobj   instance void Microsoft.Crm.Sdk.ClrTypeParser::.ctor(string partialTypeName)
0x917d  stloc.s  7
0x917f  ldloc.0
0x9180  ldloc.3
0x9181  ldloc.s  4
0x9183  ldloc.s  7
0x9185  ldloc.s  5
0x9187  newobj   instance void Microsoft.Crm.Sdk.RequestFieldDescription::.ctor(string name, string publicName, class Microsoft.Crm.Sdk.IFieldParser parser, bool optional)
0x918c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sdk.RequestFieldDescription>::Add(var<u1>)
0x9191  ldloc.1
0x9192  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x9197  brtrue   loc_90C8
0x919c  leave.s  loc_91B2
0x919e  ldloc.1
0x919f  isinst   [mscorlib]System.IDisposable
0x91a4  stloc.s  9
0x91a6  ldloc.s  9
0x91a8  brfalse.s loc_91B1
0x91aa  ldloc.s  9
0x91ac  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x91b1  endfinally
0x91b2  ldloc.0
0x91b3  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sdk.RequestFieldDescription>::ToArray()
0x91b8  ret
```
