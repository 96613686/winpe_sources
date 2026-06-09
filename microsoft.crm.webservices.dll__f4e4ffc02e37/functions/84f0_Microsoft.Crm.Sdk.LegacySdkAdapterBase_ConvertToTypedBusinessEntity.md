# Microsoft.Crm.Sdk.LegacySdkAdapterBase::ConvertToTypedBusinessEntity

- ea: `0x84f0`
- end: `0x8591`
- name: `Microsoft.Crm.Sdk.LegacySdkAdapterBase::ConvertToTypedBusinessEntity`
- size: `161`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x4230`
- `0xfcc0`
- `0xfd00`

## callees

- `0x84f0`
- `0xa940`

## string_xrefs

- `0x8544`: `Microsoft.Crm.SdkTypeProxy, Version=4.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35`

## pseudocode

```c

```

## disassembly

```asm
0x84f0  ldarg.1
0x84f1  ldc.i4.1
0x84f2  newobj   instance void Microsoft.Crm.Sdk.Crm2007.BusinessEntity::.ctor(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity entity, bool skipOuterNode)
0x84f7  stloc.0
0x84f8  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x84fd  stloc.1
0x84fe  call     class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.SerializerCache [Microsoft.Crm.Core.Extensions]Microsoft.Crm.SerializerCache::get_Instance()
0x8503  ldloc.0
0x8504  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x8509  ldnull
0x850a  ldnull
0x850b  callvirt instance class [System.Xml]System.Xml.Serialization.XmlSerializer [Microsoft.Crm.Core.Extensions]Microsoft.Crm.SerializerCache::GetSerializer(class [mscorlib]System.Type, string, string)
0x8510  stloc.2
0x8511  ldloc.1
0x8512  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8517  newobj   instance void [mscorlib]System.IO.StringWriter::.ctor(class [mscorlib]System.Text.StringBuilder, class [mscorlib]System.IFormatProvider)
0x851c  stloc.3
0x851d  ldloc.2
0x851e  ldloc.3
0x851f  ldloc.0
0x8520  callvirt instance void [System.Xml]System.Xml.Serialization.XmlSerializer::Serialize(class [mscorlib]System.IO.TextWriter, object)
0x8525  ldloc.3
0x8526  callvirt instance void [mscorlib]System.IO.TextWriter::Flush()
0x852b  leave.s  loc_8537
0x852d  ldloc.3
0x852e  brfalse.s loc_8536
0x8530  ldloc.3
0x8531  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8536  endfinally
0x8537  ldloc.1
0x8538  callvirt instance string [mscorlib]System.Object::ToString()
0x853d  newobj   instance void [mscorlib]System.IO.StringReader::.ctor(string)
0x8542  stloc.s  4
0x8544  ldstr    aMicrosoftCrmSd_0// "Microsoft.Crm.SdkTypeProxy, Version=4.0"...
0x8549  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::Load(string)
0x854e  stloc.s  5
0x8550  call     class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.SerializerCache [Microsoft.Crm.Core.Extensions]Microsoft.Crm.SerializerCache::get_Instance()
0x8555  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.BusinessEntity
0x855a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x855f  ldnull
0x8560  ldnull
0x8561  ldloc.s  5
0x8563  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.BusinessEntity
0x8568  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x856d  callvirt instance class [System.Xml]System.Xml.Serialization.XmlSerializer [Microsoft.Crm.Core.Extensions]Microsoft.Crm.SerializerCache::GetSerializer(class [mscorlib]System.Type, string, string, class [mscorlib]System.Reflection.Assembly, class [mscorlib]System.Type)
0x8572  ldloc.s  4
0x8574  callvirt instance object [System.Xml]System.Xml.Serialization.XmlSerializer::Deserialize(class [mscorlib]System.IO.TextReader)
0x8579  castclass [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.BusinessEntity
0x857e  stloc.s  6
0x8580  leave.s  loc_858E
0x8582  ldloc.s  4
0x8584  brfalse.s loc_858D
0x8586  ldloc.s  4
0x8588  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x858d  endfinally
0x858e  ldloc.s  6
0x8590  ret
```
