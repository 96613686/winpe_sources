# Microsoft.Crm.Sdk.InProcessLegacySdkAdapter::ConvertToLegacyMetadataResponse

- ea: `0x3ea0`
- end: `0x3f75`
- name: `Microsoft.Crm.Sdk.InProcessLegacySdkAdapter::ConvertToLegacyMetadataResponse`
- size: `213`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xfe40`

## callees

- `0x3ea0`

## string_xrefs

- `0x3ec7`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3eaf`: `Microsoft.Crm.SdkTypeProxy.Metadata.MetadataServiceResponse, Microsoft.Crm.SdkTypeProxy, Version=4.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35`

## pseudocode

```c

```

## disassembly

```asm
0x3ea0  ldarg.0
0x3ea1  ldfld    class [mscorlib]System.Type Microsoft.Crm.Sdk.InProcessLegacySdkAdapter::_metadataResponseBaseType
0x3ea6  ldnull
0x3ea7  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x3eac  brfalse.s loc_3EBF
0x3eae  ldarg.0
0x3eaf  ldstr    aMicrosoftCrmSd_8// "Microsoft.Crm.SdkTypeProxy.Metadata.Met"...
0x3eb4  ldc.i4.1
0x3eb5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetType(string, bool)
0x3eba  stfld    class [mscorlib]System.Type Microsoft.Crm.Sdk.InProcessLegacySdkAdapter::_metadataResponseBaseType
0x3ebf  ldnull
0x3ec0  stloc.0
0x3ec1  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x3ec6  stloc.1
0x3ec7  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/crm/2007/W"...
0x3ecc  stloc.2
0x3ecd  ldtoken  Microsoft.Crm.Sdk.Crm2007.MetadataServiceResponse
0x3ed2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3ed7  stloc.3
0x3ed8  call     class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.SerializerCache [Microsoft.Crm.Core.Extensions]Microsoft.Crm.SerializerCache::get_Instance()
0x3edd  ldloc.3
0x3ede  ldloc.3
0x3edf  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x3ee4  ldloc.2
0x3ee5  ldloc.3
0x3ee6  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0x3eeb  ldloc.3
0x3eec  callvirt instance class [System.Xml]System.Xml.Serialization.XmlSerializer [Microsoft.Crm.Core.Extensions]Microsoft.Crm.SerializerCache::GetSerializer(class [mscorlib]System.Type, string, string, class [mscorlib]System.Reflection.Assembly, class [mscorlib]System.Type)
0x3ef1  stloc.s  4
0x3ef3  ldloc.1
0x3ef4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3ef9  newobj   instance void [mscorlib]System.IO.StringWriter::.ctor(class [mscorlib]System.Text.StringBuilder, class [mscorlib]System.IFormatProvider)
0x3efe  stloc.s  6
0x3f00  ldloc.s  4
0x3f02  ldloc.s  6
0x3f04  ldarg.1
0x3f05  callvirt instance void [System.Xml]System.Xml.Serialization.XmlSerializer::Serialize(class [mscorlib]System.IO.TextWriter, object)
0x3f0a  ldloc.s  6
0x3f0c  callvirt instance void [mscorlib]System.IO.TextWriter::Flush()
0x3f11  leave.s  loc_3F1F
0x3f13  ldloc.s  6
0x3f15  brfalse.s loc_3F1E
0x3f17  ldloc.s  6
0x3f19  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3f1e  endfinally
0x3f1f  call     class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.SerializerCache [Microsoft.Crm.Core.Extensions]Microsoft.Crm.SerializerCache::get_Instance()
0x3f24  ldarg.0
0x3f25  ldfld    class [mscorlib]System.Type Microsoft.Crm.Sdk.InProcessLegacySdkAdapter::_metadataResponseBaseType
0x3f2a  ldarg.0
0x3f2b  ldfld    class [mscorlib]System.Type Microsoft.Crm.Sdk.InProcessLegacySdkAdapter::_metadataResponseBaseType
0x3f30  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x3f35  ldloc.2
0x3f36  ldarg.0
0x3f37  ldfld    class [mscorlib]System.Type Microsoft.Crm.Sdk.InProcessLegacySdkAdapter::_metadataResponseBaseType
0x3f3c  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0x3f41  ldarg.0
0x3f42  ldfld    class [mscorlib]System.Type Microsoft.Crm.Sdk.InProcessLegacySdkAdapter::_metadataResponseBaseType
0x3f47  callvirt instance class [System.Xml]System.Xml.Serialization.XmlSerializer [Microsoft.Crm.Core.Extensions]Microsoft.Crm.SerializerCache::GetSerializer(class [mscorlib]System.Type, string, string, class [mscorlib]System.Reflection.Assembly, class [mscorlib]System.Type)
0x3f4c  stloc.s  5
0x3f4e  ldloc.1
0x3f4f  callvirt instance string [mscorlib]System.Object::ToString()
0x3f54  newobj   instance void [mscorlib]System.IO.StringReader::.ctor(string)
0x3f59  stloc.s  7
0x3f5b  ldloc.s  5
0x3f5d  ldloc.s  7
0x3f5f  callvirt instance object [System.Xml]System.Xml.Serialization.XmlSerializer::Deserialize(class [mscorlib]System.IO.TextReader)
0x3f64  stloc.0
0x3f65  leave.s  loc_3F73
0x3f67  ldloc.s  7
0x3f69  brfalse.s loc_3F72
0x3f6b  ldloc.s  7
0x3f6d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3f72  endfinally
0x3f73  ldloc.0
0x3f74  ret
```
