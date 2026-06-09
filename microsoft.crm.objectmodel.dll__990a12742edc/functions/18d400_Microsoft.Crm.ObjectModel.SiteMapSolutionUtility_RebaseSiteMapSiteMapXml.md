# Microsoft.Crm.ObjectModel.SiteMapSolutionUtility::RebaseSiteMapSiteMapXml

- ea: `0x18d400`
- end: `0x18d550`
- name: `Microsoft.Crm.ObjectModel.SiteMapSolutionUtility::RebaseSiteMapSiteMapXml`
- size: `336`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18d320`

## callees

- `0x18d400`
- `0x18d550`
- `0x18de00`

## string_xrefs

- `0x18d4d8`: `sitemapxml`
- `0x18d401`: `baseXml`
- `0x18d40c`: `componentInstance`
- `0x18d430`: `sitemapxmlmanaged`
- `0x18d4ea`: `sitemapxmlmanaged`
- `0x18d467`: `Managed siteMap xml diff after handling modified URLs: {0}`
- `0x18d4a3`: `Updating siteMap instance {0} with new xml as : {1}`

## pseudocode

```c

```

## disassembly

```asm
0x18d400  ldarg.0
0x18d401  ldstr    aBasexml// "baseXml"
0x18d406  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x18d40b  ldarg.1
0x18d40c  ldstr    aComponentinsta// "componentInstance"
0x18d411  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x18d416  ldnull
0x18d417  stloc.0
0x18d418  ldarg.1
0x18d419  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentInstance::get_Entity()
0x18d41e  isinst   [Microsoft.Crm.Entities]Microsoft.Crm.Entities.SiteMap
0x18d423  stloc.1
0x18d424  ldloc.1
0x18d425  ldstr    aSitemapentity// "siteMapEntity"
0x18d42a  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x18d42f  ldloc.1
0x18d430  ldstr    aSitemapxmlmana// "sitemapxmlmanaged"
0x18d435  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x18d43a  isinst   [mscorlib]System.String
0x18d43f  stloc.2
0x18d440  ldarg.3
0x18d441  brfalse.s loc_18D481
0x18d443  ldloc.2
0x18d444  brfalse.s loc_18D481
0x18d446  ldloc.2
0x18d447  call     string Microsoft.Crm.ObjectModel.SiteMapSolutionUtility::UpdateCustomizedXMLDiffWithURL(string xmlDiffString)
0x18d44c  stloc.2
0x18d44d  ldarg.2
0x18d44e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x18d453  ldc.i4.s 0x11
0x18d455  ldstr    a0_0// "{0}"
0x18d45a  ldc.i4.1
0x18d45b  newarr   [mscorlib]System.Object
0x18d460  dup
0x18d461  ldc.i4.0
0x18d462  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x18d467  ldstr    aManagedSitemap// "Managed siteMap xml diff after handling"...
0x18d46c  ldc.i4.1
0x18d46d  newarr   [mscorlib]System.Object
0x18d472  dup
0x18d473  ldc.i4.0
0x18d474  ldloc.2
0x18d475  stelem.ref
0x18d476  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x18d47b  stelem.ref
0x18d47c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x18d481  ldarg.0
0x18d482  ldloc.2
0x18d483  call     string Microsoft.Crm.ObjectModel.SiteMapSolutionUtility::MergeSiteMapXmlDiff(string siteMapXmlOld, string siteMapXmlDiff)
0x18d488  stloc.0
0x18d489  ldarg.2
0x18d48a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x18d48f  ldc.i4.s 0x11
0x18d491  ldstr    a0_0// "{0}"
0x18d496  ldc.i4.1
0x18d497  newarr   [mscorlib]System.Object
0x18d49c  dup
0x18d49d  ldc.i4.0
0x18d49e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x18d4a3  ldstr    aUpdatingSitema// "Updating siteMap instance {0} with new "...
0x18d4a8  ldc.i4.2
0x18d4a9  newarr   [mscorlib]System.Object
0x18d4ae  dup
0x18d4af  ldc.i4.0
0x18d4b0  ldarg.1
0x18d4b1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_RowGuidId()
0x18d4b6  box      [mscorlib]System.Guid
0x18d4bb  stelem.ref
0x18d4bc  dup
0x18d4bd  ldc.i4.1
0x18d4be  ldloc.0
0x18d4bf  stelem.ref
0x18d4c0  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x18d4c5  stelem.ref
0x18d4c6  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x18d4cb  ldstr    aSitemap// "SiteMap"
0x18d4d0  ldarg.2
0x18d4d1  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::.ctor(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x18d4d6  stloc.3
0x18d4d7  ldloc.3
0x18d4d8  ldstr    aSitemapxml// "sitemapxml"
0x18d4dd  ldloc.0
0x18d4de  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string, object)
0x18d4e3  ldarg.3
0x18d4e4  brfalse.s loc_18D4F5
0x18d4e6  ldloc.2
0x18d4e7  brfalse.s loc_18D4F5
0x18d4e9  ldloc.3
0x18d4ea  ldstr    aSitemapxmlmana// "sitemapxmlmanaged"
0x18d4ef  ldloc.2
0x18d4f0  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string, object)
0x18d4f5  ldstr    aSitemap// "SiteMap"
0x18d4fa  ldarg.2
0x18d4fb  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::.ctor(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x18d500  stloc.s  4
0x18d502  ldloc.s  4
0x18d504  ldstr    aSitemapid// "sitemapid"
0x18d509  ldc.i4.0
0x18d50a  ldloc.1
0x18d50b  ldstr    aSitemapid// "sitemapid"
0x18d510  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x18d515  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x18d51a  pop
0x18d51b  ldloc.s  4
0x18d51d  ldstr    aSolutionid// "solutionid"
0x18d522  ldc.i4.0
0x18d523  ldloc.1
0x18d524  ldstr    aSolutionid// "solutionid"
0x18d529  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x18d52e  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x18d533  pop
0x18d534  ldstr    aSitemap// "SiteMap"
0x18d539  ldloc.3
0x18d53a  ldloc.s  4
0x18d53c  ldarg.2
0x18d53d  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.UpdatePlan::.ctor(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x18d542  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.QueryPlan::get_Command()
0x18d547  ldarg.2
0x18d548  call     int32 [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x18d54d  pop
0x18d54e  ldloc.0
0x18d54f  ret
```
