# Microsoft.Crm.Service.Application.Pages.SM.AppointmentDetailedForm::ConfigureForm

- ea: `0x115f0`
- end: `0x11713`
- name: `Microsoft.Crm.Service.Application.Pages.SM.AppointmentDetailedForm::ConfigureForm`
- size: `291`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x115f0`

## pseudocode

```c

```

## disassembly

```asm
0x115f0  ldarg.0
0x115f1  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x115f6  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x115fb  ldstr    aType// "type"
0x11600  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x11605  stloc.0
0x11606  ldarg.0
0x11607  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1160c  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x11611  ldstr    aTabid// "tabID"
0x11616  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1161b  stloc.1
0x1161c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x11621  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x11626  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0x1162b  ldstr    aSmCustomizable// "/SM/CustomizableForm.aspx parameters: t"...
0x11630  ldc.i4.3
0x11631  newarr   [mscorlib]System.Object
0x11636  dup
0x11637  ldc.i4.0
0x11638  ldloc.0
0x11639  stelem.ref
0x1163a  dup
0x1163b  ldc.i4.1
0x1163c  ldloc.1
0x1163d  stelem.ref
0x1163e  dup
0x1163f  ldc.i4.2
0x11640  ldarg.0
0x11641  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x11646  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1164b  ldstr    aId// "id"
0x11650  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x11655  stelem.ref
0x11656  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1165b  ldloc.0
0x1165c  brfalse  loc_11712
0x11661  ldloc.0
0x11662  callvirt instance int32 [mscorlib]System.String::get_Length()
0x11667  ldc.i4.0
0x11668  ble      loc_11712
0x1166d  ldloc.0
0x1166e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x11673  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x11678  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1167d  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::.ctor(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x11682  stloc.2
0x11683  ldloc.2
0x11684  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x11689  stloc.3
0x1168a  ldloc.3
0x1168b  brfalse  loc_11712
0x11690  ldarg.0
0x11691  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x11696  castclass [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CrudForm
0x1169b  dup
0x1169c  ldc.i4.0
0x1169d  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended::set_SetInitialFocus(bool)
0x116a2  dup
0x116a3  ldloc.3
0x116a4  ldc.i4.0
0x116a5  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableForm::ExecuteForFormType(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormType)
0x116aa  ldarg.0
0x116ab  ldloc.2
0x116ac  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::set_CurrentType(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x116b1  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormBody [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended::get_FormBody()
0x116b6  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x116bb  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Web]System.Web.UI.ControlCollection::GetEnumerator()
0x116c0  stloc.s  4
0x116c2  br.s     loc_116F2
0x116c4  ldloc.s  4
0x116c6  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x116cb  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormTab
0x116d0  stloc.s  5
0x116d2  ldloc.s  5
0x116d4  brfalse.s loc_116F2
0x116d6  ldloc.s  5
0x116d8  ldc.i4.1
0x116d9  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CompositeControl::set_ReadOnly(bool)
0x116de  ldloc.s  5
0x116e0  ldloc.s  5
0x116e2  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x116e7  ldloc.1
0x116e8  call     bool [mscorlib]System.String::op_Equality(string, string)
0x116ed  callvirt instance void [System.Web]System.Web.UI.Control::set_Visible(bool)
0x116f2  ldloc.s  4
0x116f4  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x116f9  brtrue.s loc_116C4
0x116fb  leave.s  loc_11712
0x116fd  ldloc.s  4
0x116ff  isinst   [mscorlib]System.IDisposable
0x11704  stloc.s  6
0x11706  ldloc.s  6
0x11708  brfalse.s loc_11711
0x1170a  ldloc.s  6
0x1170c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x11711  endfinally
0x11712  ret
```
