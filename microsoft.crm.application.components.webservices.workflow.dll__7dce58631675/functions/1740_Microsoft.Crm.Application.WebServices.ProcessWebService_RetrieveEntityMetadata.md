# Microsoft.Crm.Application.WebServices.ProcessWebService::RetrieveEntityMetadata

- ea: `0x1740`
- end: `0x1896`
- name: `Microsoft.Crm.Application.WebServices.ProcessWebService::RetrieveEntityMetadata`
- size: `342`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1740`

## pseudocode

```c

```

## disassembly

```asm
0x1740  ldarg.1
0x1741  call     T0x2B000007
0x1746  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x174b  stloc.0
0x174c  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.ProcessDesigner.ProcessEntityMetadataBuilder::.ctor()
0x1751  stloc.1
0x1752  stloc.3
0x1753  ldc.i4.0
0x1754  stloc.s  4
0x1756  br.s     loc_1775
0x1758  ldloc.3
0x1759  ldloc.s  4
0x175b  ldelem.ref
0x175c  stloc.s  5
0x175e  ldloc.0
0x175f  ldloc.s  5
0x1761  ldloc.1
0x1762  ldloc.s  5
0x1764  ldarg.2
0x1765  callvirt instance class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.EntityMetadataJsonWrapper [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.ProcessDesigner.ProcessEntityMetadataBuilder::Build(string, int32)
0x176a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x176f  ldloc.s  4
0x1771  ldc.i4.1
0x1772  add
0x1773  stloc.s  4
0x1775  ldloc.s  4
0x1777  ldloc.3
0x1778  ldlen
0x1779  conv.i4
0x177a  blt.s    loc_1758
0x177c  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Type>::.ctor()
0x1781  stloc.2
0x1782  ldloc.2
0x1783  ldtoken  [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.TextAttributeMetadataJsonWrapper
0x1788  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x178d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Type>::Add(var<u1>)
0x1792  ldloc.2
0x1793  ldtoken  [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.PicklistAttributeMetadataJsonWrapper
0x1798  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x179d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Type>::Add(var<u1>)
0x17a2  ldloc.2
0x17a3  ldtoken  [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.PicklistStatusAttributeMetadataJsonWrapper
0x17a8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17ad  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Type>::Add(var<u1>)
0x17b2  ldloc.2
0x17b3  ldtoken  [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.EnumOptionJsonWrapper
0x17b8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17bd  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Type>::Add(var<u1>)
0x17c2  ldloc.2
0x17c3  ldtoken  [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.LookupAttributeMetadataJsonWrapper
0x17c8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17cd  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Type>::Add(var<u1>)
0x17d2  ldloc.2
0x17d3  ldtoken  [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.NumberAttributeMetadataJsonWrapper
0x17d8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17dd  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Type>::Add(var<u1>)
0x17e2  ldloc.2
0x17e3  ldtoken  [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.MoneyAttributeMetadataJsonWrapper
0x17e8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17ed  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Type>::Add(var<u1>)
0x17f2  ldloc.2
0x17f3  ldtoken  [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.DateTimeAttributeMetadataJsonWrapper
0x17f8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17fd  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Type>::Add(var<u1>)
0x1802  ldloc.2
0x1803  ldtoken  [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.EntityMetadataJsonWrapper
0x1808  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x180d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Type>::Add(var<u1>)
0x1812  ldloc.2
0x1813  ldtoken  [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.ProcessDesigner.RelationshipJsonWrapper
0x1818  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x181d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Type>::Add(var<u1>)
0x1822  ldloc.2
0x1823  ldtoken  [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.ProcessDesigner.EntityAdditionalMetadataJsonWrapper
0x1828  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x182d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Type>::Add(var<u1>)
0x1832  ldstr    aFor// "for(;;);"
0x1837  ldloc.0
0x1838  ldloc.2
0x1839  call     string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.JsonConverter::ConvertDictionaryToJson(class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Type>)
0x183e  call     string [mscorlib]System.String::Concat(string, string)
0x1843  stloc.s  6
0x1845  leave.s  loc_1893
0x1847  stloc.s  7
0x1849  ldloc.s  7
0x184b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1850  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x1855  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0x185a  ldstr    a0// "{0}"
0x185f  ldc.i4.1
0x1860  newarr   [mscorlib]System.Object
0x1865  dup
0x1866  ldc.i4.0
0x1867  ldstr    aErrorEncounter// "Error encountered while retrieveing met"...
0x186c  ldloc.s  7
0x186e  callvirt instance string [mscorlib]System.Exception::get_Message()
0x1873  call     string [mscorlib]System.String::Concat(string, string)
0x1878  stelem.ref
0x1879  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x187e  ldstr    aFor// "for(;;);"
0x1883  ldloc.s  7
0x1885  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.InlineEdit.InlineEditJsonConverter::ReturnJsonException(class [mscorlib]System.Exception)
0x188a  call     string [mscorlib]System.String::Concat(string, string)
0x188f  stloc.s  6
0x1891  leave.s  loc_1893
0x1893  ldloc.s  6
0x1895  ret
```
