# Microsoft.Crm.Service.Dialogs.DecrementEntitlementTermDialogPage::OnPostBack

- ea: `0x2d80`
- end: `0x2e1c`
- name: `Microsoft.Crm.Service.Dialogs.DecrementEntitlementTermDialogPage::OnPostBack`
- size: `156`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x2c10`

## callees

- `0x2d80`
- `0x2e20`

## string_xrefs

- `0x2d86`: `text/xml`

## pseudocode

```c

```

## disassembly

```asm
0x2d80  ldarg.0
0x2d81  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x2d86  ldstr    aTextXml// "text/xml"
0x2d8b  callvirt instance void [System.Web]System.Web.HttpResponse::set_ContentType(string)
0x2d90  ldarg.0
0x2d91  ldfld    string Microsoft.Crm.Service.Dialogs.DecrementEntitlementTermDialogPage::reasonType
0x2d96  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2d9b  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0x2da0  ldc.i4.1
0x2da1  beq.s    loc_2DDE
0x2da3  ldstr    aIncident// "incident"
0x2da8  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x2dad  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2db2  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x2db7  dup
0x2db8  ldarg.0
0x2db9  ldfld    string Microsoft.Crm.Service.Dialogs.DecrementEntitlementTermDialogPage::incidentId
0x2dbe  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Id(string)
0x2dc3  dup
0x2dc4  ldstr    aDecremententit// "decremententitlementterm"
0x2dc9  ldc.i4.0
0x2dca  box      [mscorlib]System.Boolean
0x2dcf  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x2dd4  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x2dd9  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Update(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2dde  leave.s  loc_2E15
0x2de0  call     class [mscorlib]System.Exception [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::CreateXmlException(class [mscorlib]System.Exception)
0x2de5  throw
0x2de6  stloc.0
0x2de7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x2dec  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x2df1  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0x2df6  ldstr    a0_0// "{0}"
0x2dfb  ldc.i4.1
0x2dfc  newarr   [mscorlib]System.Object
0x2e01  dup
0x2e02  ldc.i4.0
0x2e03  ldstr    aErrorEncounter_0// "Error encountered in post back of Merge"...
0x2e08  stelem.ref
0x2e09  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2e0e  ldloc.0
0x2e0f  call     class [mscorlib]System.Exception [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::CreateXmlException(class [mscorlib]System.Exception)
0x2e14  throw
0x2e15  ldarg.0
0x2e16  call     instance void Microsoft.Crm.Service.Dialogs.DecrementEntitlementTermDialogPage::SendOK()
0x2e1b  ret
```
