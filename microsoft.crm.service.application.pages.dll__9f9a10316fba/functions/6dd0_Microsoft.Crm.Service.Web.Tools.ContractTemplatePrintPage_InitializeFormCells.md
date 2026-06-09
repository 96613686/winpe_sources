# Microsoft.Crm.Service.Web.Tools.ContractTemplatePrintPage::InitializeFormCells

- ea: `0x6dd0`
- end: `0x6e69`
- name: `Microsoft.Crm.Service.Web.Tools.ContractTemplatePrintPage::InitializeFormCells`
- size: `153`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x6d60`

## callees

- `0x6dd0`

## pseudocode

```c

```

## disassembly

```asm
0x6dd0  ldarg.1
0x6dd1  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x6dd6  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Web]System.Web.UI.ControlCollection::GetEnumerator()
0x6ddb  stloc.0
0x6ddc  br.s     loc_6E4D
0x6dde  ldloc.0
0x6ddf  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x6de4  castclass [System.Web]System.Web.UI.Control
0x6de9  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormCell
0x6dee  stloc.1
0x6def  ldloc.1
0x6df0  brfalse.s loc_6E4D
0x6df2  ldloc.1
0x6df3  ldc.i4.0
0x6df4  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CompositeControl::set_RenderMode(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormControlRenderMode)
0x6df9  ldloc.1
0x6dfa  ldc.i4.1
0x6dfb  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormControlWithLabel::set_ShowLabel(bool)
0x6e00  ldloc.1
0x6e01  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x6e06  callvirt instance int32 [System.Web]System.Web.UI.ControlCollection::get_Count()
0x6e0b  ldc.i4.0
0x6e0c  ble.s    loc_6E4D
0x6e0e  ldloc.1
0x6e0f  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x6e14  ldc.i4.0
0x6e15  callvirt instance class [System.Web]System.Web.UI.Control [System.Web]System.Web.UI.ControlCollection::get_Item(int32)
0x6e1a  isinst   [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmDataControl
0x6e1f  stloc.2
0x6e20  ldloc.2
0x6e21  brfalse.s loc_6E4D
0x6e23  ldloc.1
0x6e24  ldloc.2
0x6e25  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.IAttributeMetadataAwareControl::get_Metadata()
0x6e2a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_DisplayNames()
0x6e2f  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x6e34  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x6e39  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x6e3e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::GetLabel(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x6e43  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::get_Description()
0x6e48  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormControlWithLabel::set_Label(string)
0x6e4d  ldloc.0
0x6e4e  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x6e53  brtrue.s loc_6DDE
0x6e55  leave.s  loc_6E68
0x6e57  ldloc.0
0x6e58  isinst   [mscorlib]System.IDisposable
0x6e5d  stloc.3
0x6e5e  ldloc.3
0x6e5f  brfalse.s loc_6E67
0x6e61  ldloc.3
0x6e62  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6e67  endfinally
0x6e68  ret
```
