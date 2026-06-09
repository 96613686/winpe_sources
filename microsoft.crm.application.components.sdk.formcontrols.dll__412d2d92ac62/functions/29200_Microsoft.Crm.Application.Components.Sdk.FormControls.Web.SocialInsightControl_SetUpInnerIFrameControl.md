# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SocialInsightControl::SetUpInnerIFrameControl

- ea: `0x29200`
- end: `0x29278`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SocialInsightControl::SetUpInnerIFrameControl`
- size: `120`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x291e0`

## callees

- `0x1bff0`
- `0x1c050`
- `0x1c070`
- `0x1c0a0`
- `0x1c0d0`
- `0x1c150`
- `0x1c670`
- `0x29150`
- `0x29180`
- `0x291b0`
- `0x291c0`
- `0x291d0`

## pseudocode

```c

```

## disassembly

```asm
0x29200  ldarg.0
0x29201  newobj   instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControl::.ctor()
0x29206  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SocialInsightControl::set_InnerFrameControl(class Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControl value)
0x2920b  ldarg.0
0x2920c  call     instance class Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SocialInsightControl::get_InnerFrameControl()
0x29211  ldarg.0
0x29212  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SocialInsightControl::get_PassParameters()
0x29217  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControl::set_PassParameters(bool value)
0x2921c  ldarg.0
0x2921d  call     instance class Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SocialInsightControl::get_InnerFrameControl()
0x29222  ldc.i4.0
0x29223  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControl::set_Security(bool value)
0x29228  ldarg.0
0x29229  call     instance class Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SocialInsightControl::get_InnerFrameControl()
0x2922e  ldarg.0
0x2922f  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SocialInsightControl::get_Scrolling()
0x29234  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControl::set_Scrolling(string value)
0x29239  ldarg.0
0x2923a  call     instance class Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SocialInsightControl::get_InnerFrameControl()
0x2923f  ldarg.0
0x29240  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SocialInsightControl::get_Border()
0x29245  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControl::set_Border(bool value)
0x2924a  ldarg.0
0x2924b  call     instance class Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SocialInsightControl::get_InnerFrameControl()
0x29250  ldstr    aAboutBlank// "about:blank"
0x29255  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControl::set_Url(string value)
0x2925a  ldarg.0
0x2925b  call     instance class Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SocialInsightControl::get_InnerFrameControl()
0x29260  ldc.i4.1
0x29261  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControl::set_UseDelayInitialize(bool value)
0x29266  ldarg.0
0x29267  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x2926c  ldarg.0
0x2926d  call     instance class Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SocialInsightControl::get_InnerFrameControl()
0x29272  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x29277  ret
```
