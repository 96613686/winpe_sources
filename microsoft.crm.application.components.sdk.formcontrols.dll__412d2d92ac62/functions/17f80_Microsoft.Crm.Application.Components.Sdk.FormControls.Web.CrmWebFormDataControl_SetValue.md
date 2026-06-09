# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControl::SetValue

- ea: `0x17f80`
- end: `0x17fd9`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControl::SetValue`
- size: `89`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x17e60`
- `0x17e90`

## callees

- `0x17990`
- `0x17e80`
- `0x17f80`
- `0x17fe0`
- `0x18070`
- `0x18080`

## pseudocode

```c

```

## disassembly

```asm
0x17f80  ldarg.0
0x17f81  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_DataSource()
0x17f86  brfalse.s loc_17FD8
0x17f88  ldarg.0
0x17f89  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControl::get_Metadata()
0x17f8e  brfalse.s loc_17FD8
0x17f90  ldarg.0
0x17f91  ldarg.0
0x17f92  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_DataSource()
0x17f97  ldarg.0
0x17f98  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControl::get_Metadata()
0x17f9d  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x17fa2  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x17fa7  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControl::set_Value(object value)
0x17fac  ldarg.0
0x17fad  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_DataSource()
0x17fb2  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_IsNew()
0x17fb7  brfalse.s loc_17FD2
0x17fb9  ldarg.0
0x17fba  callvirt instance object Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControl::get_Value()
0x17fbf  brtrue.s loc_17FD2
0x17fc1  ldarg.0
0x17fc2  ldarg.0
0x17fc3  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControl::get_Metadata()
0x17fc8  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_DefaultValueAsObject()
0x17fcd  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControl::set_Value(object value)
0x17fd2  ldarg.0
0x17fd3  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControl::SetControlState()
0x17fd8  ret
```
