# Microsoft.Crm.Service.Application.Pages.SM.Services.ServerEntityPage::CustomForm_ObjectModelReady

- ea: `0x123a0`
- end: `0x12414`
- name: `Microsoft.Crm.Service.Application.Pages.SM.Services.ServerEntityPage::CustomForm_ObjectModelReady`
- size: `116`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x123a0`

## string_xrefs

- `0x123e4`: `Scheduled`

## pseudocode

```c

```

## disassembly

```asm
0x123a0  ldarg.2
0x123a1  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CrmFormEventArgs::get_Form()
0x123a6  ldstr    aInitialstatusc// "initialstatuscode"
0x123ab  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm::get_Item(string)
0x123b0  isinst   [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistStatusControl
0x123b5  stloc.0
0x123b6  ldloc.0
0x123b7  brfalse.s loc_12413
0x123b9  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x123be  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x123c3  ldc.i4   0x1076
0x123c8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0x123cd  stloc.1
0x123ce  ldloc.0
0x123cf  ldloc.1
0x123d0  ldstr    aStatuscode// "statuscode"
0x123d5  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::TryGetAttribute(string)
0x123da  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistStatusControl::set_OptionsMetadata(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata)
0x123df  ldstr    aActivitypointe// "activitypointer"
0x123e4  ldstr    aScheduled// "Scheduled"
0x123e9  call     int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::ConvertStateToNumber(string, string)
0x123ee  stloc.2
0x123ef  ldstr    aActivitypointe// "activitypointer"
0x123f4  ldstr    aOpen// "Open"
0x123f9  call     int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::ConvertStateToNumber(string, string)
0x123fe  stloc.3
0x123ff  ldloc.0
0x12400  ldc.i4.2
0x12401  newarr   [mscorlib]System.Int32
0x12406  dup
0x12407  ldc.i4.0
0x12408  ldloc.2
0x12409  stelem.i4
0x1240a  dup
0x1240b  ldc.i4.1
0x1240c  ldloc.3
0x1240d  stelem.i4
0x1240e  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistStatusControl::set_States(int32[])
0x12413  ret
```
