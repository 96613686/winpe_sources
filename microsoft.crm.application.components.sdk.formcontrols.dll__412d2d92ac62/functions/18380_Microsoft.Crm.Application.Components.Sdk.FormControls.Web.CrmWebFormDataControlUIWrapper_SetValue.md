# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::SetValue

- ea: `0x18380`
- end: `0x18422`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::SetValue`
- size: `162`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x182b0`
- `0x182e0`
- `0x20e30`

## callees

- `0x17990`
- `0x182d0`
- `0x18380`
- `0x18540`
- `0x185d0`
- `0x185e0`

## pseudocode

```c

```

## disassembly

```asm
0x18380  ldarg.0
0x18381  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_DataSource()
0x18386  brfalse  loc_18421
0x1838b  ldarg.0
0x1838c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x18391  brfalse  loc_18421
0x18396  ldarg.0
0x18397  ldarg.0
0x18398  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_DataSource()
0x1839d  ldarg.0
0x1839e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x183a3  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x183a8  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x183ad  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Value(object value)
0x183b2  ldarg.0
0x183b3  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_DataSource()
0x183b8  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_IsNew()
0x183bd  brfalse.s loc_1841B
0x183bf  ldarg.0
0x183c0  callvirt instance object Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::get_Value()
0x183c5  brtrue.s loc_1841B
0x183c7  ldarg.0
0x183c8  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x183cd  brfalse.s loc_1840A
0x183cf  ldarg.0
0x183d0  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x183d5  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::get_ClientVars()
0x183da  brfalse.s loc_1840A
0x183dc  ldarg.0
0x183dd  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x183e2  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::get_ClientVars()
0x183e7  ldstr    aIsWorkflowEdit// "IS_WORKFLOW_EDITOR"
0x183ec  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x183f1  ldstr    aTrue_1// "'TRUE'"
0x183f6  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x183fb  brtrue.s loc_1840A
0x183fd  ldarg.0
0x183fe  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x18403  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_IsCustomField()
0x18408  brtrue.s loc_1841B
0x1840a  ldarg.0
0x1840b  ldarg.0
0x1840c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x18411  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_DefaultValueAsObject()
0x18416  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Value(object value)
0x1841b  ldarg.0
0x1841c  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::SetControlState()
0x18421  ret
```
