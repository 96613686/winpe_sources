# Microsoft.Crm.Extensibility.CrmODataComplexTypeDeserializer::Read

- ea: `0x1fe0`
- end: `0x208d`
- name: `Microsoft.Crm.Extensibility.CrmODataComplexTypeDeserializer::Read`
- size: `173`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1fe0`
- `0x291b0`

## string_xrefs

- `0x1ff9`: `ArgumentNull readContext`
- `0x2031`: `PathEdmType should be IEdmComplexType`

## pseudocode

```c

```

## disassembly

```asm
0x1fe0  ldarg.2
0x1fe1  ldtoken  [mscorlib]System.Object
0x1fe6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1feb  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x1ff0  brfalse  loc_2083
0x1ff5  ldarg.3
0x1ff6  ldnull
0x1ff7  cgt.un
0x1ff9  ldstr    aArgumentnullRe// "ArgumentNull readContext"
0x1ffe  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x2003  ldarg.2
0x2004  ldnull
0x2005  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x200a  ldstr    aArgumentnullTy// "ArgumentNull type"
0x200f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x2014  ldarg.3
0x2015  callvirt instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.OData]System.Web.OData.Formatter.Deserialization.ODataDeserializerContext::get_Request()
0x201a  call     class [System.Web.OData]System.Web.OData.Extensions.HttpRequestMessageProperties [System.Web.OData]System.Web.OData.Extensions.HttpRequestMessageExtensions::ODataProperties(class [System.Net.Http]System.Net.Http.HttpRequestMessage)
0x201f  callvirt instance class [System.Web.OData]System.Web.OData.Routing.ODataPath [System.Web.OData]System.Web.OData.Extensions.HttpRequestMessageProperties::get_Path()
0x2024  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmType [System.Web.OData]System.Web.OData.Routing.ODataPath::get_EdmType()
0x2029  isinst   [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmComplexType
0x202e  ldnull
0x202f  cgt.un
0x2031  ldstr    aPathedmtypeSho// "PathEdmType should be IEdmComplexType"
0x2036  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x203b  ldarg.3
0x203c  callvirt instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.OData]System.Web.OData.Formatter.Deserialization.ODataDeserializerContext::get_Request()
0x2041  call     class [System.Web.OData]System.Web.OData.Extensions.HttpRequestMessageProperties [System.Web.OData]System.Web.OData.Extensions.HttpRequestMessageExtensions::ODataProperties(class [System.Net.Http]System.Net.Http.HttpRequestMessage)
0x2046  callvirt instance class [System.Web.OData]System.Web.OData.Routing.ODataPath [System.Web.OData]System.Web.OData.Extensions.HttpRequestMessageProperties::get_Path()
0x204b  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmType [System.Web.OData]System.Web.OData.Routing.ODataPath::get_EdmType()
0x2050  ldc.i4.1
0x2051  call     class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::ToEdmTypeReference(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmType edmType, bool isNullable)
0x2056  castclass [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmComplexTypeReference
0x205b  stloc.0
0x205c  ldarg.3
0x205d  ldtoken  [System.Web.OData]System.Web.OData.EdmComplexObject
0x2062  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2067  callvirt instance void [System.Web.OData]System.Web.OData.Formatter.Deserialization.ODataDeserializerContext::set_ResourceType(class [mscorlib]System.Type)
0x206c  ldarg.1
0x206d  ldloc.0
0x206e  callvirt instance class [Microsoft.OData.Core]Microsoft.OData.ODataProperty [Microsoft.OData.Core]Microsoft.OData.ODataMessageReader::ReadProperty(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference)
0x2073  stloc.1
0x2074  ldarg.0
0x2075  ldloc.1
0x2076  callvirt instance object [Microsoft.OData.Core]Microsoft.OData.ODataProperty::get_Value()
0x207b  ldloc.0
0x207c  ldarg.3
0x207d  callvirt instance object [System.Web.OData]System.Web.OData.Formatter.Deserialization.ODataEdmTypeDeserializer::ReadInline(object, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference, class [System.Web.OData]System.Web.OData.Formatter.Deserialization.ODataDeserializerContext)
0x2082  ret
0x2083  ldarg.0
0x2084  ldarg.1
0x2085  ldarg.2
0x2086  ldarg.3
0x2087  call     instance object [System.Web.OData]System.Web.OData.Formatter.Deserialization.ODataResourceDeserializer::Read(class [Microsoft.OData.Core]Microsoft.OData.ODataMessageReader, class [mscorlib]System.Type, class [System.Web.OData]System.Web.OData.Formatter.Deserialization.ODataDeserializerContext)
0x208c  ret
```
