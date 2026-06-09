# Microsoft.Crm.Asynchronous.BulkDeleteOperation::GetFetchXmlFromQuerySet

- ea: `0x17f0`
- end: `0x1872`
- name: `Microsoft.Crm.Asynchronous.BulkDeleteOperation::GetFetchXmlFromQuerySet`
- size: `130`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1f350`

## callees

- `0x17f0`

## pseudocode

```c

```

## disassembly

```asm
0x17f0  ldarg.0
0x17f1  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression> Microsoft.Crm.Asynchronous.BulkDeleteOperation::_globalQueryExpList
0x17f6  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression>::get_Count()
0x17fb  newarr   [mscorlib]System.String
0x1800  stloc.0
0x1801  newobj   instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.QueryExpressionToFetchXmlRequest::.ctor()
0x1806  stloc.1
0x1807  ldnull
0x1808  stloc.2
0x1809  ldc.i4.0
0x180a  stloc.s  4
0x180c  br.s     loc_1843
0x180e  ldloc.1
0x180f  ldarg.0
0x1810  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression> Microsoft.Crm.Asynchronous.BulkDeleteOperation::_globalQueryExpList
0x1815  ldloc.s  4
0x1817  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression>::get_Item(!!T0)
0x181c  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.QueryExpressionToFetchXmlRequest::set_Query(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryBase)
0x1821  ldarg.0
0x1822  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Asynchronous.BulkDeleteOperation::_crmService
0x1827  ldloc.1
0x1828  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x182d  castclass [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.QueryExpressionToFetchXmlResponse
0x1832  stloc.2
0x1833  ldloc.0
0x1834  ldloc.s  4
0x1836  ldloc.2
0x1837  callvirt instance string [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.QueryExpressionToFetchXmlResponse::get_FetchXml()
0x183c  stelem.ref
0x183d  ldloc.s  4
0x183f  ldc.i4.1
0x1840  add
0x1841  stloc.s  4
0x1843  ldloc.s  4
0x1845  ldloc.0
0x1846  ldlen
0x1847  conv.i4
0x1848  blt.s    loc_180E
0x184a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x184f  newobj   instance void [mscorlib]System.IO.StringWriter::.ctor(class [mscorlib]System.IFormatProvider)
0x1854  stloc.3
0x1855  ldtoken  string[]
0x185a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x185f  newobj   instance void [System.Xml]System.Xml.Serialization.XmlSerializer::.ctor(class [mscorlib]System.Type)
0x1864  ldloc.3
0x1865  ldloc.0
0x1866  callvirt instance void [System.Xml]System.Xml.Serialization.XmlSerializer::Serialize(class [mscorlib]System.IO.TextWriter, object)
0x186b  ldloc.3
0x186c  callvirt instance string [mscorlib]System.Object::ToString()
0x1871  ret
```
