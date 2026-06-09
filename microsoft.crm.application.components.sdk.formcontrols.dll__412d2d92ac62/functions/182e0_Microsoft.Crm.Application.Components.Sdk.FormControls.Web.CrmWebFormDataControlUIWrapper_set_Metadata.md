# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Metadata

- ea: `0x182e0`
- end: `0x18337`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Metadata`
- size: `87`
- prototype: ``
- caller_count: `10`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1ab30`
- `0x1ae40`
- `0x1f820`
- `0x21dc0`
- `0x22e20`
- `0x22f00`
- `0x23640`
- `0x24590`
- `0x2a7b0`
- `0x2aa30`

## callees

- `0x182e0`
- `0x18380`

## pseudocode

```c

```

## disassembly

```asm
0x182e0  ldarg.0
0x182e1  ldarg.1
0x182e2  stfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::_metadata
0x182e7  ldarg.0
0x182e8  ldarg.0
0x182e9  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::_metadata
0x182ee  brfalse.s loc_18311
0x182f0  ldc.i4.2
0x182f1  ldarg.0
0x182f2  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::_metadata
0x182f7  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeRequiredLevel [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_AttributeRequiredLevelId()
0x182fc  beq.s    loc_1830E
0x182fe  ldc.i4.1
0x182ff  ldarg.0
0x18300  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::_metadata
0x18305  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeRequiredLevel [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_AttributeRequiredLevelId()
0x1830a  ceq
0x1830c  br.s     loc_18312
0x1830e  ldc.i4.1
0x1830f  br.s     loc_18312
0x18311  ldc.i4.0
0x18312  stfld    bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::_required
0x18317  ldarg.0
0x18318  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::_metadata
0x1831d  brfalse.s loc_18330
0x1831f  ldarg.0
0x18320  ldarg.0
0x18321  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::_metadata
0x18326  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeIMEMode [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_AttributeImeModeId()
0x1832b  stfld    valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeIMEMode Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::_imeMode
0x18330  ldarg.0
0x18331  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::SetValue()
0x18336  ret
```
