# Microsoft.Crm.Common.Application.Dialogs.SM.ActivitySchedulingDialog::SetCustomizableLabels

- ea: `0x10470`
- end: `0x1054c`
- name: `Microsoft.Crm.Common.Application.Dialogs.SM.ActivitySchedulingDialog::SetCustomizableLabels`
- size: `220`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x10250`

## callees

- `0xfdf0`
- `0x10550`

## string_xrefs

- `0x104a7`: `serviceid`

## pseudocode

```c

```

## disassembly

```asm
0x10470  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x10475  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1047a  ldc.i4   0x1076
0x1047f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0x10484  stloc.0
0x10485  ldarg.0
0x10486  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType Microsoft.Crm.Common.Application.Dialogs.SM.ActivitySchedulingDialog::get_ActivityType()
0x1048b  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_TypeCode()
0x10490  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x10495  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormDescriptor [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Forms.FormDescriptorCache::GetFormDescriptor(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1049a  stloc.1
0x1049b  ldarg.0
0x1049c  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormCell Microsoft.Crm.Common.Application.Dialogs.SM.ActivitySchedulingDialog::ServiceCell
0x104a1  ldloc.1
0x104a2  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormDescriptor::get_Controls()
0x104a7  ldstr    aServiceid// "serviceid"
0x104ac  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlCollection::get_Item(string)
0x104b1  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.CellDescriptor [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor::get_ParentCellDescriptor()
0x104b6  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormCell::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.CellDescriptor)
0x104bb  callvirt instance string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormControlWithLabel::get_Label()
0x104c0  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormControlWithLabel::set_Label(string)
0x104c5  ldarg.0
0x104c6  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormCell Microsoft.Crm.Common.Application.Dialogs.SM.ActivitySchedulingDialog::ResourcesCell
0x104cb  ldloc.1
0x104cc  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormDescriptor::get_Controls()
0x104d1  ldstr    aResources// "resources"
0x104d6  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlCollection::get_Item(string)
0x104db  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.CellDescriptor [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor::get_ParentCellDescriptor()
0x104e0  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormCell::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.CellDescriptor)
0x104e5  callvirt instance string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormControlWithLabel::get_Label()
0x104ea  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormControlWithLabel::set_Label(string)
0x104ef  ldarg.0
0x104f0  ldloc.1
0x104f1  ldloc.0
0x104f2  ldstr    aCustomers// "customers"
0x104f7  ldarg.0
0x104f8  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormCell Microsoft.Crm.Common.Application.Dialogs.SM.ActivitySchedulingDialog::CustomersCell
0x104fd  call     instance void Microsoft.Crm.Common.Application.Dialogs.SM.ActivitySchedulingDialog::SetCustomizableLabel(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormDescriptor formDescriptor, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata serviceActivityMetadata, string attributeName, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormCell formCell)
0x10502  ldarg.0
0x10503  ldloc.1
0x10504  ldloc.0
0x10505  ldstr    aSiteid// "siteid"
0x1050a  ldarg.0
0x1050b  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormCell Microsoft.Crm.Common.Application.Dialogs.SM.ActivitySchedulingDialog::SiteCell
0x10510  call     instance void Microsoft.Crm.Common.Application.Dialogs.SM.ActivitySchedulingDialog::SetCustomizableLabel(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormDescriptor formDescriptor, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata serviceActivityMetadata, string attributeName, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormCell formCell)
0x10515  ldarg.0
0x10516  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormCell Microsoft.Crm.Common.Application.Dialogs.SM.ActivitySchedulingDialog::StartTimeCell
0x1051b  ldarg.0
0x1051c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x10521  ldstr    aFormLabelStart// "Form_Label_StartTime"
0x10526  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1052b  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormControlWithLabel::set_Label(string)
0x10530  ldarg.0
0x10531  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormCell Microsoft.Crm.Common.Application.Dialogs.SM.ActivitySchedulingDialog::StartDateCell
0x10536  ldarg.0
0x10537  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1053c  ldstr    aFormLabelStart_0// "Form_Label_StartDate"
0x10541  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x10546  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormControlWithLabel::set_Label(string)
0x1054b  ret
```
