# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SocialInsightControl::SetClientVariables

- ea: `0x29a70`
- end: `0x29afd`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SocialInsightControl::SetClientVariables`
- size: `141`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x29280`

## callees

- `0x17950`
- `0x29380`
- `0x29a70`

## string_xrefs

- `0x29a8b`: `_SocialInsightControlJsonData`

## pseudocode

```c

```

## disassembly

```asm
0x29a70  ldstr    aFor_0// "for(;;);"
0x29a75  call     class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.SocialInsightControlJsonWrapper [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Core.SocialInsights.SocialInsightsJsonWrapperBuilder::Build()
0x29a7a  call     string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.JsonConverter::GetJsonString(object)
0x29a7f  call     string [mscorlib]System.String::Concat(string, string)
0x29a84  stloc.0
0x29a85  ldarg.0
0x29a86  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x29a8b  ldstr    aSocialinsightc// "_SocialInsightControlJsonData"
0x29a90  ldloc.0
0x29a91  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x29a96  ldarg.0
0x29a97  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x29a9c  ldstr    aIssocialinsigh// "_IsSocialInsightsInstanceAvailable"
0x29aa1  ldarg.0
0x29aa2  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Core.SocialInsights.ISocialInsightsState Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SocialInsightControl::_instanceState
0x29aa7  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Core.SocialInsights.ISocialInsightsState::get_IsSocialInsightsInstanceAvailable()
0x29aac  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0x29ab1  ldarg.0
0x29ab2  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x29ab7  ldstr    aAresocialinsig// "_AreSocialInsightsEnabled"
0x29abc  ldarg.0
0x29abd  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Core.SocialInsights.ISocialInsightsState Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SocialInsightControl::_instanceState
0x29ac2  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Core.SocialInsights.ISocialInsightsState::get_AreSocialInsightsEnabled()
0x29ac7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0x29acc  ldarg.0
0x29acd  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x29ad2  ldstr    aFormtype// "FormType"
0x29ad7  ldarg.0
0x29ad8  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormDescriptor Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_CurrentFormDescriptor()
0x29add  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormDescriptor::get_IsUserForm()
0x29ae2  brtrue.s loc_29AEB
0x29ae4  ldc.i4   0x406
0x29ae9  br.s     loc_29AF0
0x29aeb  ldc.i4   0x407
0x29af0  conv.i8
0x29af1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0x29af6  ldarg.0
0x29af7  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SocialInsightControl::PassLocalizedStrings()
0x29afc  ret
```
