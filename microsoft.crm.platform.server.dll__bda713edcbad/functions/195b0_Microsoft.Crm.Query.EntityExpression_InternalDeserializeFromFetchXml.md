# Microsoft.Crm.Query.EntityExpression::InternalDeserializeFromFetchXml

- ea: `0x195b0`
- end: `0x19668`
- name: `Microsoft.Crm.Query.EntityExpression::InternalDeserializeFromFetchXml`
- size: `184`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18900`
- `0x195a0`

## callees

- `0x165b0`
- `0x195b0`
- `0x19710`
- `0x19b70`
- `0x19e60`
- `0x1a860`
- `0x1a8f0`
- `0x1a920`
- `0x52db0`

## string_xrefs

- `0x195fc`: `Entity Name was not specified in FetchXml String or on EntityExpression`
- `0x1962a`: `Entity Name specified in FetchXml does not match the entity name in the EntityExpression`

## pseudocode

```c

```

## disassembly

```asm
0x195b0  ldarg.1
0x195b1  brfalse.s loc_195BB
0x195b3  ldarg.1
0x195b4  callvirt instance int32 [mscorlib]System.String::get_Length()
0x195b9  brtrue.s loc_195BC
0x195bb  ret
0x195bc  ldnull
0x195bd  stloc.0
0x195be  ldarg.1
0x195bf  call     class [System.Xml.Linq]System.Xml.Linq.XElement Microsoft.Crm.Platform.Server.Utility.XmlHelper::LoadXmlInfo(string xmlInfo)
0x195c4  stloc.0
0x195c5  leave.s  loc_195D8
0x195c7  ldc.i4   0x80040201
0x195cc  ldc.i4.0
0x195cd  newarr   [mscorlib]System.Object
0x195d2  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(class [mscorlib]System.Exception, int32, object[])
0x195d7  throw
0x195d8  ldarg.1
0x195d9  ldloc.0
0x195da  ldarg.0
0x195db  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Query.Expression::get_Cache()
0x195e0  ldarg.0
0x195e1  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Query.Expression::get_OrganizationId()
0x195e6  call     string Microsoft.Crm.Query.EntityExpression::PlatformEntityNameFromFetchXml(string fetchXml, class [System.Xml.Linq]System.Xml.Linq.XElement element, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache dynamicCache, valuetype [mscorlib]System.Guid organizationId)
0x195eb  stloc.1
0x195ec  ldloc.1
0x195ed  brtrue.s loc_19617
0x195ef  ldarg.0
0x195f0  ldfld    string Microsoft.Crm.Query.EntityExpression::platformName
0x195f5  brtrue.s loc_19617
0x195f7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x195fc  ldstr    aEntityNameWasN_1// "Entity Name was not specified in FetchX"...
0x19601  ldc.i4.0
0x19602  newarr   [mscorlib]System.Object
0x19607  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1960c  ldc.i4   0x80041102
0x19611  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x19616  throw
0x19617  ldloc.1
0x19618  ldarg.0
0x19619  ldfld    string Microsoft.Crm.Query.EntityExpression::platformName
0x1961e  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x19623  brfalse.s loc_19645
0x19625  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1962a  ldstr    aEntityNameSpec// "Entity Name specified in FetchXml does "...
0x1962f  ldc.i4.0
0x19630  newarr   [mscorlib]System.Object
0x19635  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1963a  ldc.i4   0x80041128
0x1963f  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x19644  throw
0x19645  ldarg.0
0x19646  ldarg.0
0x19647  ldfld    string Microsoft.Crm.Query.EntityExpression::platformName
0x1964c  call     instance void Microsoft.Crm.Query.EntityExpression::Init(string entityPlatformName)
0x19651  ldloc.0
0x19652  ldarg.2
0x19653  ldarg.0
0x19654  call     instance bool Microsoft.Crm.Query.EntityExpression::get_IsInReportingContext()
0x19659  ldarg.3
0x1965a  newobj   instance void Microsoft.Crm.Query.DeserializeFetchVisitor::.ctor(class [System.Xml.Linq]System.Xml.Linq.XElement element, valuetype Microsoft.Crm.Query.ParsingConditionValuesOption parsingValuesOption, bool isReportContext, bool skipMissingAttributes)
0x1965f  stloc.2
0x19660  ldarg.0
0x19661  ldloc.2
0x19662  callvirt instance void Microsoft.Crm.Query.Expression::Deserialize(class Microsoft.Crm.Query.ExpressionVisitor visitor)
0x19667  ret
```
