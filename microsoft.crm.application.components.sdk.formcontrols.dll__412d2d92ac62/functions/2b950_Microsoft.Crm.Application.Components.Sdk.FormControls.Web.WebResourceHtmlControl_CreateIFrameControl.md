# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.WebResourceHtmlControl::CreateIFrameControl

- ea: `0x2b950`
- end: `0x2b9e5`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.WebResourceHtmlControl::CreateIFrameControl`
- size: `149`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `broker_com_uri`

## callers

- `0x2b920`

## callees

- `0x17990`
- `0x179a0`
- `0x17a10`
- `0x17a20`
- `0x1bff0`
- `0x1c050`
- `0x1c070`
- `0x1c0a0`
- `0x1c0d0`
- `0x1c110`
- `0x1c120`
- `0x1c670`
- `0x2b300`
- `0x2b750`
- `0x2b770`
- `0x2b7b0`
- `0x2b7d0`
- `0x2b7f0`
- `0x2b950`

## pseudocode

```c

```

## disassembly

```asm
0x2b950  newobj   instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControl::.ctor()
0x2b955  stloc.0
0x2b956  ldloc.0
0x2b957  ldarg.0
0x2b958  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x2b95d  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x2b962  ldloc.0
0x2b963  ldarg.0
0x2b964  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.WebResourceHtmlControl::get_PassParameters()
0x2b969  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControl::set_PassParameters(bool value)
0x2b96e  ldloc.0
0x2b96f  ldarg.0
0x2b970  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Application.Components.Sdk.FormControls.Web.WebResourcesControlBase::GetWebResourceUrl()
0x2b975  callvirt instance string [mscorlib]System.Object::ToString()
0x2b97a  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControl::set_Url(string value)
0x2b97f  ldloc.0
0x2b980  ldarg.0
0x2b981  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.WebResourceHtmlControl::get_Border()
0x2b986  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControl::set_Border(bool value)
0x2b98b  ldloc.0
0x2b98c  ldarg.0
0x2b98d  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.WebResourceHtmlControl::get_Security()
0x2b992  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControl::set_Security(bool value)
0x2b997  ldloc.0
0x2b998  ldarg.0
0x2b999  callvirt instance int32 Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_TabIndex()
0x2b99e  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::set_TabIndex(int32 value)
0x2b9a3  ldloc.0
0x2b9a4  ldarg.0
0x2b9a5  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.WebResourceHtmlControl::get_Scrolling()
0x2b9aa  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControl::set_Scrolling(string value)
0x2b9af  ldloc.0
0x2b9b0  ldarg.0
0x2b9b1  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.WebResourceHtmlControl::get_Preload()
0x2b9b6  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControl::set_Preload(bool value)
0x2b9bb  ldloc.0
0x2b9bc  ldarg.0
0x2b9bd  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_DataSource()
0x2b9c2  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::set_DataSource(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity value)
0x2b9c7  ldloc.0
0x2b9c8  ldc.i4.1
0x2b9c9  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControl::set_SkipClientControlCreation(bool value)
0x2b9ce  ldarg.0
0x2b9cf  ldloc.0
0x2b9d0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::ConfigureChildControl(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase)
0x2b9d5  ldloc.0
0x2b9d6  stloc.1
0x2b9d7  leave.s  loc_2B9E3
0x2b9d9  ldloc.0
0x2b9da  brfalse.s loc_2B9E2
0x2b9dc  ldloc.0
0x2b9dd  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2b9e2  endfinally
0x2b9e3  ldloc.1
0x2b9e4  ret
```
