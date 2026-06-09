# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::SetControlState

- ea: `0x18540`
- end: `0x185c1`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::SetControlState`
- size: `129`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18380`

## callees

- `0x17990`
- `0x17a80`
- `0x182d0`
- `0x18480`
- `0x184c0`
- `0x18540`

## pseudocode

```c

```

## disassembly

```asm
0x18540  ldarg.0
0x18541  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_DataSource()
0x18546  brfalse.s loc_185C0
0x18548  ldarg.0
0x18549  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x1854e  brfalse.s loc_185C0
0x18550  ldarg.0
0x18551  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_DataSource()
0x18556  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Disabled()
0x1855b  brfalse.s loc_18565
0x1855d  ldarg.0
0x1855e  ldc.i4.1
0x1855f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool)
0x18564  ret
0x18565  ldarg.0
0x18566  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_DataSource()
0x1856b  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_IsNew()
0x18570  brfalse.s loc_18587
0x18572  ldarg.0
0x18573  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x18578  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_ValidForCreate()
0x1857d  brfalse.s loc_185A9
0x1857f  ldarg.0
0x18580  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::get_IsSecuredCreate()
0x18585  brtrue.s loc_185A9
0x18587  ldarg.0
0x18588  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_DataSource()
0x1858d  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_IsNew()
0x18592  brtrue.s loc_185C0
0x18594  ldarg.0
0x18595  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x1859a  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_ValidForUpdate()
0x1859f  brfalse.s loc_185A9
0x185a1  ldarg.0
0x185a2  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::get_IsSecuredUpdate()
0x185a7  brfalse.s loc_185C0
0x185a9  ldarg.0
0x185aa  ldc.i4.1
0x185ab  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool)
0x185b0  ldarg.0
0x185b1  ldstr    aDonotsubmit// "DoNotSubmit"
0x185b6  ldstr    a1_0// "1"
0x185bb  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::AddExpando(string name, string value)
0x185c0  ret
```
