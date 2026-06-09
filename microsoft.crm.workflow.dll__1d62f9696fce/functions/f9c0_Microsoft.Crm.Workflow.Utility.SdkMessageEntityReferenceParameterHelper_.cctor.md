# Microsoft.Crm.Workflow.Utility.SdkMessageEntityReferenceParameterHelper::.cctor

- ea: `0xf9c0`
- end: `0xfa6b`
- name: `Microsoft.Crm.Workflow.Utility.SdkMessageEntityReferenceParameterHelper::.cctor`
- size: `171`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## string_xrefs

- `0xf9f7`: `SETWORDTEMPLATE_SelectedTemplate`
- `0xfa1f`: `SETWORDTEMPLATE_SelectedTemplate`
- `0xfa47`: `SETWORDTEMPLATE_SelectedTemplate`
- `0xfa0b`: `ADDUSERTORECORDTEAM_TeamTemplateId`

## pseudocode

```c

```

## disassembly

```asm
0xf9c0  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0xf9c5  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Workflow.Utility.SdkMessageEntityReferenceParameterHelper::_lookupDefaultViewHelper
0xf9ca  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0xf9cf  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Workflow.Utility.SdkMessageEntityReferenceParameterHelper::_disableViewPickerHelper
0xf9d4  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0xf9d9  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Workflow.Utility.SdkMessageEntityReferenceParameterHelper::_defaultTypeHelper
0xf9de  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Workflow.Utility.SdkMessageEntityReferenceParameterHelper::_lookupDefaultViewHelper
0xf9e3  ldstr    aSetprocessNewp// "SETPROCESS_NewProcess"
0xf9e8  ldstr    a4418f0e2737244// "4418F0E2-7372-44C4-BFA1-2B4CEFB576C7"
0xf9ed  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xf9f2  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Workflow.Utility.SdkMessageEntityReferenceParameterHelper::_lookupDefaultViewHelper
0xf9f7  ldstr    aSetwordtemplat_0// "SETWORDTEMPLATE_SelectedTemplate"
0xf9fc  ldstr    a7c0d687b361442// "7C0D687B-3614-429E-BFD6-D1D618C662D7"
0xfa01  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xfa06  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Workflow.Utility.SdkMessageEntityReferenceParameterHelper::_lookupDefaultViewHelper
0xfa0b  ldstr    aAddusertorecor_0// "ADDUSERTORECORDTEAM_TeamTemplateId"
0xfa10  ldstr    a532fa9d4C6be42// "532FA9D4-C6BE-427B-94F2-7CF1151B2495"
0xfa15  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xfa1a  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Workflow.Utility.SdkMessageEntityReferenceParameterHelper::_defaultTypeHelper
0xfa1f  ldstr    aSetwordtemplat_0// "SETWORDTEMPLATE_SelectedTemplate"
0xfa24  ldstr    a9940// "9940"
0xfa29  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xfa2e  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Workflow.Utility.SdkMessageEntityReferenceParameterHelper::_defaultTypeHelper
0xfa33  ldstr    aSetprocessNewp// "SETPROCESS_NewProcess"
0xfa38  ldstr    a4703// "4703"
0xfa3d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xfa42  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Workflow.Utility.SdkMessageEntityReferenceParameterHelper::_disableViewPickerHelper
0xfa47  ldstr    aSetwordtemplat_0// "SETWORDTEMPLATE_SelectedTemplate"
0xfa4c  ldstr    a1// "1"
0xfa51  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xfa56  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Workflow.Utility.SdkMessageEntityReferenceParameterHelper::_disableViewPickerHelper
0xfa5b  ldstr    aSetprocessNewp// "SETPROCESS_NewProcess"
0xfa60  ldstr    a1// "1"
0xfa65  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xfa6a  ret
```
