# IdMappingForBookableResourceQuery::Retrieve

- ea: `0x151e0`
- end: `0x15236`
- name: `IdMappingForBookableResourceQuery::Retrieve`
- size: `86`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x151e0`
- `0x15ed0`

## string_xrefs

- `0x151e0`: `<fetch version='1.0' mapping='logical' distinct='true'>\n					<entity name = 'bookableresourcebookingexchangesyncidmapping'>\n						<attribute name = 'bookableresourcebookingexchangesyncidmappingid'/>\n						<attribute name = 'bookableresourcebookingid'/>\n						<attribute name = 'exchangeentryid'/>\n						<attribute name = 'syncversionnumber'/>\n						<attribute name = 'syncstatus'/>\n						<attribute name = 'retries'/>\n						<attribute name = 'isdeletedinexchange'/>\n						<attribute`

## pseudocode

```c

```

## disassembly

```asm
0x151e0  ldstr    aFetchVersion10// "<fetch version='1.0' mapping='logical' "...
0x151e5  ldarg.0
0x151e6  ldfld    valuetype [mscorlib]System.Guid IdMappingForBookableResourceQuery::bookableResourceBookingId
0x151eb  box      [mscorlib]System.Guid
0x151f0  ldarg.0
0x151f1  ldfld    bool IdMappingForBookableResourceQuery::includeDeletedInExchange
0x151f6  brtrue.s loc_151FB
0x151f8  ldc.i4.0
0x151f9  br.s     loc_151FC
0x151fb  ldc.i4.1
0x151fc  box      [mscorlib]System.Int32
0x15201  call     string [mscorlib]System.String::Format(string, object, object)
0x15206  stloc.0
0x15207  ldarg.0
0x15208  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService IdMappingForBookableResourceQuery::service
0x1520d  ldloc.0
0x1520e  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection FetchXml::RetrieveMultiple(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService service, string fetchXml)
0x15213  stloc.1
0x15214  ldloc.1
0x15215  brfalse.s loc_1522D
0x15217  ldloc.1
0x15218  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x1521d  brfalse.s loc_1522D
0x1521f  ldloc.1
0x15220  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x15225  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Count()
0x1522a  ldc.i4.0
0x1522b  bgt.s    loc_1522F
0x1522d  ldnull
0x1522e  ret
0x1522f  ldloc.1
0x15230  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x15235  ret
```
