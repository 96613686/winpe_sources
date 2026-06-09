# Microsoft.Crm.Service.Dialogs.DefaultEntitlementConfirmationDialogPage::OnPostBack

- ea: `0x29c0`
- end: `0x2b19`
- name: `Microsoft.Crm.Service.Dialogs.DefaultEntitlementConfirmationDialogPage::OnPostBack`
- size: `345`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x28d0`

## callees

- `0x29c0`
- `0x2b20`

## string_xrefs

- `0x2a83`: `text/xml`

## pseudocode

```c

```

## disassembly

```asm
0x29c0  ldstr    aEntitlement// "entitlement"
0x29c5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x29ca  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x29cf  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x29d4  stloc.0
0x29d5  ldstr    aEntitlement// "entitlement"
0x29da  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::.ctor(string)
0x29df  dup
0x29e0  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::get_ColumnSet()
0x29e5  ldstr    aIsdefault// "isdefault"
0x29ea  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumn(string)
0x29ef  dup
0x29f0  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0x29f5  ldstr    aIsdefault// "isdefault"
0x29fa  ldc.i4.0
0x29fb  ldc.i4.1
0x29fc  box      [mscorlib]System.Boolean
0x2a01  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x2a06  dup
0x2a07  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::get_ColumnSet()
0x2a0c  ldstr    aCustomerid_0// "customerid"
0x2a11  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumn(string)
0x2a16  dup
0x2a17  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0x2a1c  ldstr    aCustomerid_0// "customerid"
0x2a21  ldc.i4.0
0x2a22  ldarg.0
0x2a23  ldfld    string Microsoft.Crm.Service.Dialogs.DefaultEntitlementConfirmationDialogPage::customerId
0x2a28  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x2a2d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x2a32  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::RetrieveMultiple(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2a37  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::GetEnumerator()
0x2a3c  stloc.2
0x2a3d  br.s     loc_2A69
0x2a3f  ldloc.2
0x2a40  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Current()
0x2a45  stloc.3
0x2a46  ldloc.0
0x2a47  ldloc.3
0x2a48  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Id()
0x2a4d  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Id(string)
0x2a52  ldloc.0
0x2a53  ldstr    aIsdefault// "isdefault"
0x2a58  ldc.i4.0
0x2a59  box      [mscorlib]System.Boolean
0x2a5e  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x2a63  ldloc.0
0x2a64  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::Update()
0x2a69  ldloc.2
0x2a6a  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2a6f  brtrue.s loc_2A3F
0x2a71  leave.s  loc_2A7D
0x2a73  ldloc.2
0x2a74  brfalse.s loc_2A7C
0x2a76  ldloc.2
0x2a77  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2a7c  endfinally
0x2a7d  ldarg.0
0x2a7e  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x2a83  ldstr    aTextXml// "text/xml"
0x2a88  callvirt instance void [System.Web]System.Web.HttpResponse::set_ContentType(string)
0x2a8d  ldarg.0
0x2a8e  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x2a93  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x2a98  ldstr    aIid// "iId"
0x2a9d  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x2aa2  stloc.1
0x2aa3  ldstr    aEntitlement// "entitlement"
0x2aa8  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x2aad  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2ab2  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x2ab7  dup
0x2ab8  ldloc.1
0x2ab9  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Id(string)
0x2abe  dup
0x2abf  ldstr    aIsdefault// "isdefault"
0x2ac4  ldc.i4.1
0x2ac5  box      [mscorlib]System.Boolean
0x2aca  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x2acf  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x2ad4  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Update(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2ad9  leave.s  loc_2B12
0x2adb  call     class [mscorlib]System.Exception [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::CreateXmlException(class [mscorlib]System.Exception)
0x2ae0  throw
0x2ae1  stloc.s  4
0x2ae3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x2ae8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x2aed  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0x2af2  ldstr    a0_0// "{0}"
0x2af7  ldc.i4.1
0x2af8  newarr   [mscorlib]System.Object
0x2afd  dup
0x2afe  ldc.i4.0
0x2aff  ldstr    aErrorEncounter_0// "Error encountered in post back of Merge"...
0x2b04  stelem.ref
0x2b05  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2b0a  ldloc.s  4
0x2b0c  call     class [mscorlib]System.Exception [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::CreateXmlException(class [mscorlib]System.Exception)
0x2b11  throw
0x2b12  ldarg.0
0x2b13  call     instance void Microsoft.Crm.Service.Dialogs.DefaultEntitlementConfirmationDialogPage::SendOK()
0x2b18  ret
```
