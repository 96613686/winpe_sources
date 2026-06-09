# Microsoft.Crm.Service.Dialogs.DefaultSlaConfirmationDialogPage::OnPostBack

- ea: `0x24c0`
- end: `0x2628`
- name: `Microsoft.Crm.Service.Dialogs.DefaultSlaConfirmationDialogPage::OnPostBack`
- size: `360`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x2410`

## callees

- `0x24c0`
- `0x2630`

## string_xrefs

- `0x2592`: `text/xml`

## pseudocode

```c

```

## disassembly

```asm
0x24c0  ldstr    aSla// "sla"
0x24c5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x24ca  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x24cf  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x24d4  stloc.0
0x24d5  ldstr    aSla// "sla"
0x24da  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::.ctor(string)
0x24df  dup
0x24e0  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::get_ColumnSet()
0x24e5  ldstr    aIsdefault// "isdefault"
0x24ea  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumn(string)
0x24ef  dup
0x24f0  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0x24f5  ldstr    aIsdefault// "isdefault"
0x24fa  ldc.i4.0
0x24fb  ldc.i4.1
0x24fc  box      [mscorlib]System.Boolean
0x2501  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x2506  dup
0x2507  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::get_ColumnSet()
0x250c  ldstr    aSlaid// "slaid"
0x2511  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumn(string)
0x2516  ldloca.s 1
0x2518  ldarg.0
0x2519  ldfld    string Microsoft.Crm.Service.Dialogs.DefaultSlaConfirmationDialogPage::oldDefaultSlaId
0x251e  call     instance void [mscorlib]System.Guid::.ctor(string)
0x2523  dup
0x2524  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0x2529  ldstr    aSlaid// "slaid"
0x252e  ldc.i4.0
0x252f  ldloc.1
0x2530  box      [mscorlib]System.Guid
0x2535  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x253a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x253f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::RetrieveMultiple(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2544  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::GetEnumerator()
0x2549  stloc.3
0x254a  br.s     loc_2578
0x254c  ldloc.3
0x254d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Current()
0x2552  stloc.s  4
0x2554  ldloc.0
0x2555  ldloc.s  4
0x2557  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Id()
0x255c  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Id(string)
0x2561  ldloc.0
0x2562  ldstr    aIsdefault// "isdefault"
0x2567  ldc.i4.0
0x2568  box      [mscorlib]System.Boolean
0x256d  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x2572  ldloc.0
0x2573  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::Update()
0x2578  ldloc.3
0x2579  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x257e  brtrue.s loc_254C
0x2580  leave.s  loc_258C
0x2582  ldloc.3
0x2583  brfalse.s loc_258B
0x2585  ldloc.3
0x2586  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x258b  endfinally
0x258c  ldarg.0
0x258d  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x2592  ldstr    aTextXml// "text/xml"
0x2597  callvirt instance void [System.Web]System.Web.HttpResponse::set_ContentType(string)
0x259c  ldarg.0
0x259d  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x25a2  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x25a7  ldstr    aIid// "iId"
0x25ac  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x25b1  stloc.2
0x25b2  ldstr    aSla// "sla"
0x25b7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x25bc  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x25c1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x25c6  dup
0x25c7  ldloc.2
0x25c8  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Id(string)
0x25cd  dup
0x25ce  ldstr    aIsdefault// "isdefault"
0x25d3  ldc.i4.1
0x25d4  box      [mscorlib]System.Boolean
0x25d9  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x25de  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x25e3  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Update(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x25e8  leave.s  loc_2621
0x25ea  call     class [mscorlib]System.Exception [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::CreateXmlException(class [mscorlib]System.Exception)
0x25ef  throw
0x25f0  stloc.s  5
0x25f2  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x25f7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x25fc  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0x2601  ldstr    a0_0// "{0}"
0x2606  ldc.i4.1
0x2607  newarr   [mscorlib]System.Object
0x260c  dup
0x260d  ldc.i4.0
0x260e  ldstr    aErrorEncounter// "Error encountered in post back of Confi"...
0x2613  stelem.ref
0x2614  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2619  ldloc.s  5
0x261b  call     class [mscorlib]System.Exception [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::CreateXmlException(class [mscorlib]System.Exception)
0x2620  throw
0x2621  ldarg.0
0x2622  call     instance void Microsoft.Crm.Service.Dialogs.DefaultSlaConfirmationDialogPage::SendOK()
0x2627  ret
```
