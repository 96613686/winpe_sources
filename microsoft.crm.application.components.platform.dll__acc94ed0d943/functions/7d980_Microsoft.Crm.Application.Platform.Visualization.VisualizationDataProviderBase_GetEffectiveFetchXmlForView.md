# Microsoft.Crm.Application.Platform.Visualization.VisualizationDataProviderBase::GetEffectiveFetchXmlForView

- ea: `0x7d980`
- end: `0x7d9d7`
- name: `Microsoft.Crm.Application.Platform.Visualization.VisualizationDataProviderBase::GetEffectiveFetchXmlForView`
- size: `87`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x7d550`

## callees

- `0x1290`
- `0x1510`
- `0x16b0`
- `0x17b0`
- `0x2fb90`
- `0x7d980`
- `0x84e00`

## string_xrefs

- `0x7d9a4`: `isFetchXmlNotFinal`
- `0x7d9cc`: `effectiveFetchXml`

## pseudocode

```c

```

## disassembly

```asm
0x7d980  ldarg.1
0x7d981  call     class Microsoft.Crm.Application.Security.UserInformation Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x7d986  newobj   instance void Microsoft.Crm.ApplicationQuery::.ctor(class Microsoft.Crm.View view, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x7d98b  stloc.0
0x7d98c  ldloc.0
0x7d98d  ldarg.0
0x7d98e  call     instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Parameters()
0x7d993  callvirt instance void Microsoft.Crm.ApplicationQuery::AddParameters(class [System]System.Collections.Specialized.NameValueCollection parameters)
0x7d998  ldloc.0
0x7d999  callvirt instance void Microsoft.Crm.ApplicationQuery::BuildQuery()
0x7d99e  ldloc.0
0x7d99f  callvirt instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.ApplicationQuery::get_Parameters()
0x7d9a4  ldstr    aIsfetchxmlnotf// "isFetchXmlNotFinal"
0x7d9a9  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x7d9ae  call     bool [mscorlib]System.Boolean::Parse(string)
0x7d9b3  brfalse.s loc_7D9C6
0x7d9b5  ldc.i4   0x8004E01E
0x7d9ba  ldc.i4.0
0x7d9bb  newarr   [mscorlib]System.Object
0x7d9c0  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x7d9c5  throw
0x7d9c6  ldloc.0
0x7d9c7  callvirt instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.ApplicationQuery::get_Parameters()
0x7d9cc  ldstr    aEffectivefetch// "effectiveFetchXml"
0x7d9d1  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x7d9d6  ret
```
