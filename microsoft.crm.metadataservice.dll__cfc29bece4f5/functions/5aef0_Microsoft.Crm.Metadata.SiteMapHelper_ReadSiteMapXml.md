# Microsoft.Crm.Metadata.SiteMapHelper::ReadSiteMapXml

- ea: `0x5aef0`
- end: `0x5af69`
- name: `Microsoft.Crm.Metadata.SiteMapHelper::ReadSiteMapXml`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x5aa70`

## string_xrefs

- `0x5af10`: `sitemapxml`
- `0x5af54`: `sitemapxml`

## pseudocode

```c

```

## disassembly

```asm
0x5aef0  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SiteMapService::.ctor()
0x5aef5  stloc.0
0x5aef6  ldstr    aSitemap// "SiteMap"
0x5aefb  ldarg.0
0x5aefc  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x5af01  stloc.1
0x5af02  ldloc.1
0x5af03  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x5af08  ldc.i4.1
0x5af09  newarr   [mscorlib]System.String
0x5af0e  dup
0x5af0f  ldc.i4.0
0x5af10  ldstr    aSitemapxml// "sitemapxml"
0x5af15  stelem.ref
0x5af16  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x5af1b  ldloc.1
0x5af1c  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x5af21  ldstr    aSitemapid// "sitemapid"
0x5af26  ldc.i4.0
0x5af27  ldarg.1
0x5af28  box      [mscorlib]System.Guid
0x5af2d  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x5af32  pop
0x5af33  ldloc.0
0x5af34  ldloc.1
0x5af35  ldarg.0
0x5af36  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveUnpublishedMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x5af3b  dup
0x5af3c  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x5af41  ldc.i4.1
0x5af42  ceq
0x5af44  ldstr    aASystemSitemap// "A system sitemap must exists"
0x5af49  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x5af4e  ldc.i4.0
0x5af4f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x5af54  ldstr    aSitemapxml// "sitemapxml"
0x5af59  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5af5e  castclass [mscorlib]System.String
0x5af63  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x5af68  ret
```
