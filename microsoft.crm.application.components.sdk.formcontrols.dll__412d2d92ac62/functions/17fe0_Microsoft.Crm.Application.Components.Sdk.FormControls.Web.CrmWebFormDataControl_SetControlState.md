# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControl::SetControlState

- ea: `0x17fe0`
- end: `0x18061`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControl::SetControlState`
- size: `129`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x17f80`

## callees

- `0x17990`
- `0x17a80`
- `0x17e80`
- `0x17ef0`
- `0x17f30`
- `0x17fe0`

## pseudocode

```c

```

## disassembly

```asm
0x17fe0  ldarg.0
0x17fe1  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_DataSource()
0x17fe6  brfalse.s loc_18060
0x17fe8  ldarg.0
0x17fe9  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControl::get_Metadata()
0x17fee  brfalse.s loc_18060
0x17ff0  ldarg.0
0x17ff1  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_DataSource()
0x17ff6  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Disabled()
0x17ffb  brfalse.s loc_18005
0x17ffd  ldarg.0
0x17ffe  ldc.i4.1
0x17fff  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool)
0x18004  ret
0x18005  ldarg.0
0x18006  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_DataSource()
0x1800b  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_IsNew()
0x18010  brfalse.s loc_18027
0x18012  ldarg.0
0x18013  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControl::get_Metadata()
0x18018  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_ValidForCreate()
0x1801d  brfalse.s loc_18049
0x1801f  ldarg.0
0x18020  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControl::get_IsSecuredCreate()
0x18025  brtrue.s loc_18049
0x18027  ldarg.0
0x18028  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_DataSource()
0x1802d  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_IsNew()
0x18032  brtrue.s loc_18060
0x18034  ldarg.0
0x18035  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControl::get_Metadata()
0x1803a  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_ValidForUpdate()
0x1803f  brfalse.s loc_18049
0x18041  ldarg.0
0x18042  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControl::get_IsSecuredUpdate()
0x18047  brfalse.s loc_18060
0x18049  ldarg.0
0x1804a  ldc.i4.1
0x1804b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool)
0x18050  ldarg.0
0x18051  ldstr    aDonotsubmit// "DoNotSubmit"
0x18056  ldstr    a1_0// "1"
0x1805b  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::AddExpando(string name, string value)
0x18060  ret
```
