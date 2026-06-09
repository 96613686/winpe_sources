# Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::Render

- ea: `0x3ec0`
- end: `0x407d`
- name: `Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::Render`
- size: `445`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x1330`
- `0x3570`
- `0x3590`
- `0x3ec0`
- `0x4120`
- `0x4150`
- `0x4c50`
- `0x5e90`
- `0x5eb0`
- `0x5f10`
- `0x5f30`
- `0x6000`

## pseudocode

```c

```

## disassembly

```asm
0x3ec0  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x3ec5  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x3eca  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x3ecf  ldstr    aEtc// "etc"
0x3ed4  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x3ed9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3ede  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x3ee3  stloc.0
0x3ee4  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3ee9  stloc.1
0x3eea  ldarg.0
0x3eeb  callvirt instance class [System.Web]System.Web.HttpContext [System.Web]System.Web.UI.Control::get_Context()
0x3ef0  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x3ef5  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x3efa  ldstr    aProcess// "process"
0x3eff  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x3f04  stloc.2
0x3f05  ldloc.2
0x3f06  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3f0b  brtrue.s loc_3F15
0x3f0d  ldloca.s 1
0x3f0f  ldloc.2
0x3f10  call     instance void [mscorlib]System.Guid::.ctor(string)
0x3f15  ldarg.0
0x3f16  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormControlBase::get_CurrentForm()
0x3f1b  brfalse.s loc_3F2A
0x3f1d  ldarg.0
0x3f1e  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormControlBase::get_CurrentForm()
0x3f23  callvirt instance bool [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended::get_IsTurboForm()
0x3f28  br.s     loc_3F2B
0x3f2a  ldc.i4.0
0x3f2b  stloc.3
0x3f2c  ldloc.3
0x3f2d  brtrue.s loc_3F60
0x3f2f  ldloc.1
0x3f30  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3f35  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x3f3a  brfalse.s loc_3F53
0x3f3c  ldarg.0
0x3f3d  ldloc.1
0x3f3e  ldloc.0
0x3f3f  call     instance void Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::InitializeSpecificProcess(valuetype [mscorlib]System.Guid processId, int32 entityTypeCode)
0x3f44  ldarg.1
0x3f45  ldarg.0
0x3f46  ldloc.0
0x3f47  ldloc.3
0x3f48  call     instance string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::RenderProcessControl(int32 entityTypeCode, bool isTurboForm)
0x3f4d  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x3f52  ret
0x3f53  ldarg.1
0x3f54  ldarg.0
0x3f55  call     instance string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::RenderEmptyWarningBar()
0x3f5a  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x3f5f  ret
0x3f60  ldarg.0
0x3f61  callvirt instance class [System.Web]System.Web.HttpContext [System.Web]System.Web.UI.Control::get_Context()
0x3f66  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x3f6b  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x3f70  ldstr    aProcessts// "processts"
0x3f75  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x3f7a  stloc.s  4
0x3f7c  ldloc.1
0x3f7d  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3f82  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x3f87  brfalse.s loc_3FAF
0x3f89  ldarg.0
0x3f8a  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::_processId
0x3f8f  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3f94  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x3f99  brfalse.s loc_3FA8
0x3f9b  ldarg.1
0x3f9c  ldarg.0
0x3f9d  call     instance string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::RenderEmptyWarningBar()
0x3fa2  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x3fa7  ret
0x3fa8  ldarg.0
0x3fa9  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::_processId
0x3fae  stloc.1
0x3faf  call     class Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControlProcessLayoutCache Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControlProcessLayoutCache::Instance()
0x3fb4  stloc.s  5
0x3fb6  ldloca.s 8
0x3fb8  initobj  Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControlInnerCacheKey
0x3fbe  ldloca.s 8
0x3fc0  ldloc.0
0x3fc1  call     instance void Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControlInnerCacheKey::set_EntityTypeCode(int32 value)
0x3fc6  ldloca.s 8
0x3fc8  ldarg.0
0x3fc9  call     instance int32 Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::get_ClientLanguageCode()
0x3fce  call     instance void Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControlInnerCacheKey::set_UserLanguageCode(int32 value)
0x3fd3  ldloc.s  8
0x3fd5  stloc.s  6
0x3fd7  ldloc.s  5
0x3fd9  ldloc.1
0x3fda  ldarg.0
0x3fdb  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::get_OrganizationContext()
0x3fe0  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControlInnerCacheKey, class Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControlLayout>>::LookupEntry(void, var<u1>)
0x3fe5  stloc.s  7
0x3fe7  ldloc.s  7
0x3fe9  brfalse.s loc_4020
0x3feb  ldloc.s  7
0x3fed  ldloc.s  6
0x3fef  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControlInnerCacheKey, class Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControlLayout>::ContainsKey(var<u1>)
0x3ff4  brfalse.s loc_4020
0x3ff6  ldloc.s  7
0x3ff8  ldloc.s  6
0x3ffa  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControlInnerCacheKey, class Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControlLayout>::get_Item(void)
0x3fff  callvirt instance string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControlLayout::get_LayoutString()
0x4004  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x4009  brtrue.s loc_4020
0x400b  ldarg.1
0x400c  ldloc.s  7
0x400e  ldloc.s  6
0x4010  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControlInnerCacheKey, class Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControlLayout>::get_Item(void)
0x4015  callvirt instance string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControlLayout::get_LayoutString()
0x401a  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x401f  ret
0x4020  ldarg.0
0x4021  ldloc.1
0x4022  ldloc.0
0x4023  call     instance void Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::InitializeSpecificProcess(valuetype [mscorlib]System.Guid processId, int32 entityTypeCode)
0x4028  ldarg.0
0x4029  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::Process
0x402e  brfalse.s loc_4070
0x4030  ldarg.0
0x4031  ldloc.0
0x4032  ldloc.3
0x4033  call     instance string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::RenderProcessControl(int32 entityTypeCode, bool isTurboForm)
0x4038  stloc.s  9
0x403a  ldarg.1
0x403b  ldloc.s  9
0x403d  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x4042  ldloc.s  7
0x4044  brtrue.s loc_404D
0x4046  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControlInnerCacheKey, class Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControlLayout>::.ctor()
0x404b  stloc.s  7
0x404d  ldloc.s  7
0x404f  ldloc.s  6
0x4051  ldloc.s  9
0x4053  ldloc.s  4
0x4055  newobj   instance void Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControlLayout::.ctor(string layout, string pts)
0x405a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControlInnerCacheKey, class Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControlLayout>::set_Item(var<u1>, !!T0)
0x405f  ldloc.s  5
0x4061  ldloc.1
0x4062  ldloc.s  7
0x4064  ldarg.0
0x4065  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::get_OrganizationContext()
0x406a  callvirt instance void class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCache`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControlInnerCacheKey, class Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControlLayout>>::AddEntry(var<u1>, !!T0, var<u1>)
0x406f  ret
0x4070  ldarg.1
0x4071  ldarg.0
0x4072  call     instance string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::RenderEmptyWarningBar()
0x4077  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x407c  ret
```
