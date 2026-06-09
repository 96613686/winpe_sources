# Microsoft.Crm.Metadata.SiteMapUtility::RetrieveSiteMapXml

- ea: `0x2a7e0`
- end: `0x2a85a`
- name: `Microsoft.Crm.Metadata.SiteMapUtility::RetrieveSiteMapXml`
- size: `122`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2a520`

## callees

- `0x2a7e0`

## string_xrefs

- `0x2a800`: `sitemapxml`
- `0x2a848`: `sitemapxml`

## pseudocode

```c

```

## disassembly

```asm
0x2a7e0  ldsfld   string [mscorlib]System.String::Empty
0x2a7e5  stloc.0
0x2a7e6  ldstr    aSitemap// "SiteMap"
0x2a7eb  ldarg.1
0x2a7ec  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x2a7f1  stloc.1
0x2a7f2  ldloc.1
0x2a7f3  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x2a7f8  ldc.i4.2
0x2a7f9  newarr   [mscorlib]System.String
0x2a7fe  dup
0x2a7ff  ldc.i4.0
0x2a800  ldstr    aSitemapxml// "sitemapxml"
0x2a805  stelem.ref
0x2a806  dup
0x2a807  ldc.i4.1
0x2a808  ldstr    aIsappaware// "isappaware"
0x2a80d  stelem.ref
0x2a80e  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x2a813  ldloc.1
0x2a814  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x2a819  ldstr    aIsappaware// "isappaware"
0x2a81e  ldc.i4.0
0x2a81f  ldc.i4.0
0x2a820  box      [mscorlib]System.Boolean
0x2a825  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x2a82a  pop
0x2a82b  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SiteMapService::.ctor()
0x2a830  ldloc.1
0x2a831  ldarg.1
0x2a832  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x2a837  stloc.2
0x2a838  ldloc.2
0x2a839  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x2a83e  ldc.i4.0
0x2a83f  ble.s    loc_2A858
0x2a841  ldloc.2
0x2a842  ldc.i4.0
0x2a843  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x2a848  ldstr    aSitemapxml// "sitemapxml"
0x2a84d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2a852  castclass [mscorlib]System.String
0x2a857  stloc.0
0x2a858  ldloc.0
0x2a859  ret
```
