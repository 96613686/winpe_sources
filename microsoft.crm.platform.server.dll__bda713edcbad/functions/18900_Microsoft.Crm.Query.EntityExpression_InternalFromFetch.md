# Microsoft.Crm.Query.EntityExpression::InternalFromFetch

- ea: `0x18900`
- end: `0x18951`
- name: `Microsoft.Crm.Query.EntityExpression::InternalFromFetch`
- size: `81`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x188c0`
- `0x188d0`
- `0x188e0`
- `0x188f0`

## callees

- `0x18860`
- `0x18900`
- `0x190b0`
- `0x195b0`
- `0x19720`

## string_xrefs

- `0x18901`: `fetchXml`
- `0x1891d`: `Entity Name was not specified in FetchXml String.`

## pseudocode

```c

```

## disassembly

```asm
0x18900  ldarg.0
0x18901  ldstr    aFetchxml// "fetchXml"
0x18906  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfEmpty(string, string)
0x1890b  ldarg.0
0x1890c  ldnull
0x1890d  ldarg.1
0x1890e  ldarg.2
0x1890f  call     string Microsoft.Crm.Query.EntityExpression::PlatformEntityNameFromFetchXml(string fetchXml, class [System.Xml.Linq]System.Xml.Linq.XElement element, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache dynamicCache, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext)
0x18914  stloc.0
0x18915  ldloc.0
0x18916  brtrue.s loc_18938
0x18918  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1891d  ldstr    aEntityNameWasN// "Entity Name was not specified in FetchX"...
0x18922  ldc.i4.0
0x18923  newarr   [mscorlib]System.Object
0x18928  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1892d  ldc.i4   0x80041102
0x18932  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x18937  throw
0x18938  ldloc.0
0x18939  ldarg.1
0x1893a  ldarg.2
0x1893b  newobj   instance void Microsoft.Crm.Query.EntityExpression::.ctor(string entityPlatformName, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache dynamicCache, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext userAndOrganizationContext)
0x18940  dup
0x18941  ldarg.0
0x18942  ldarg.3
0x18943  ldarg.s  4
0x18945  callvirt instance void Microsoft.Crm.Query.EntityExpression::InternalDeserializeFromFetchXml(string xmlInfo, valuetype Microsoft.Crm.Query.ParsingConditionValuesOption parsingOption, [opt] bool skipMissingAttributes)
0x1894a  dup
0x1894b  callvirt instance void Microsoft.Crm.Query.EntityExpression::ValidateExpressionValidForRead()
0x18950  ret
```
