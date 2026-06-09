# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.WebResourceHtmlControl::CreateIFrameControlForReadForm

- ea: `0x2b9f0`
- end: `0x2ba7e`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.WebResourceHtmlControl::CreateIFrameControlForReadForm`
- size: `142`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `broker_com_uri`

## callers

- `0x2b920`

## callees

- `0x12a0`
- `0x12c0`
- `0x2330`
- `0x2350`
- `0x2370`
- `0x23a0`
- `0x23d0`
- `0x2410`
- `0x2430`
- `0x27e0`
- `0x17990`
- `0x17a10`
- `0x2b300`
- `0x2b750`
- `0x2b770`
- `0x2b7b0`
- `0x2b7d0`
- `0x2b7f0`
- `0x2b9f0`

## pseudocode

```c

```

## disassembly

```asm
0x2b9f0  newobj   instance void Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.FrameControl::.ctor()
0x2b9f5  stloc.0
0x2b9f6  ldloc.0
0x2b9f7  ldarg.0
0x2b9f8  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x2b9fd  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x2ba02  ldloc.0
0x2ba03  ldarg.0
0x2ba04  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.WebResourceHtmlControl::get_PassParameters()
0x2ba09  callvirt instance void Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.FrameControl::set_PassParameters(bool value)
0x2ba0e  ldloc.0
0x2ba0f  ldarg.0
0x2ba10  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Application.Components.Sdk.FormControls.Web.WebResourcesControlBase::GetWebResourceUrl()
0x2ba15  callvirt instance string [mscorlib]System.Object::ToString()
0x2ba1a  callvirt instance void Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.FrameControl::set_Url(string value)
0x2ba1f  ldloc.0
0x2ba20  ldarg.0
0x2ba21  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.WebResourceHtmlControl::get_Border()
0x2ba26  callvirt instance void Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.FrameControl::set_Border(bool value)
0x2ba2b  ldloc.0
0x2ba2c  ldarg.0
0x2ba2d  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.WebResourceHtmlControl::get_Security()
0x2ba32  callvirt instance void Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.FrameControl::set_Security(bool value)
0x2ba37  ldloc.0
0x2ba38  ldarg.0
0x2ba39  callvirt instance int32 Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_TabIndex()
0x2ba3e  callvirt instance void Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormControlBase::set_TabIndex(int32 value)
0x2ba43  ldloc.0
0x2ba44  ldarg.0
0x2ba45  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.WebResourceHtmlControl::get_Scrolling()
0x2ba4a  callvirt instance void Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.FrameControl::set_Scrolling(string value)
0x2ba4f  ldloc.0
0x2ba50  ldarg.0
0x2ba51  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.WebResourceHtmlControl::get_Preload()
0x2ba56  callvirt instance void Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.FrameControl::set_Preload(bool value)
0x2ba5b  ldloc.0
0x2ba5c  ldarg.0
0x2ba5d  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_DataSource()
0x2ba62  callvirt instance void Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormControlBase::set_DataSource(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity value)
0x2ba67  ldloc.0
0x2ba68  ldc.i4.1
0x2ba69  callvirt instance void Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.FrameControl::set_IsWebResourceControl(bool value)
0x2ba6e  ldloc.0
0x2ba6f  stloc.1
0x2ba70  leave.s  loc_2BA7C
0x2ba72  ldloc.0
0x2ba73  brfalse.s loc_2BA7B
0x2ba75  ldloc.0
0x2ba76  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2ba7b  endfinally
0x2ba7c  ldloc.1
0x2ba7d  ret
```
