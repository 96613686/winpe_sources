# Microsoft.Crm.Application.Pages.SocialInsight.Configuration.ConfigureSocialInsightsPage::.cctor

- ea: `0xee470`
- end: `0xee4bb`
- name: `Microsoft.Crm.Application.Pages.SocialInsight.Configuration.ConfigureSocialInsightsPage::.cctor`
- size: `75`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## string_xrefs

- `0xee47b`: `Spinner.CommonTitle`
- `0xee486`: `LOCID_NETBREEZE_COMMUNICATING`
- `0xee48b`: `NetBreeze.SpinnerCommunicating`
- `0xee49b`: `NetBreeze.Config.SpinnerSaveAction`
- `0xee4ab`: `ConfigureSocialInsightsWizard.MslSignInPage.CheckingSignInStatus`

## pseudocode

```c

```

## disassembly

```asm
0xee470  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0xee475  dup
0xee476  ldstr    aLocidNetbreeze_4// "LOCID_NETBREEZE_WAIT_TITLE"
0xee47b  ldstr    aSpinnerCommont// "Spinner.CommonTitle"
0xee480  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0xee485  dup
0xee486  ldstr    aLocidNetbreeze_5// "LOCID_NETBREEZE_COMMUNICATING"
0xee48b  ldstr    aNetbreezeSpinn// "NetBreeze.SpinnerCommunicating"
0xee490  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0xee495  dup
0xee496  ldstr    aLocidNetbreeze_6// "LOCID_NETBREEZE_SAVING_WIDGETS"
0xee49b  ldstr    aNetbreezeConfi// "NetBreeze.Config.SpinnerSaveAction"
0xee4a0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0xee4a5  dup
0xee4a6  ldstr    aLocidNetbreeze_7// "LOCID_NETBREEZE_SPINNER_SIGNIN"
0xee4ab  ldstr    aConfiguresocia_0// "ConfigureSocialInsightsWizard.MslSignIn"...
0xee4b0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0xee4b5  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Application.Pages.SocialInsight.Configuration.ConfigureSocialInsightsPage::spinnerStrings
0xee4ba  ret
```
