# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SfaTabsControl::CreateOneNoteControl

- ea: `0x28a70`
- end: `0x28ae7`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SfaTabsControl::CreateOneNoteControl`
- size: `119`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x28820`

## callees

- `0x22000`
- `0x22350`
- `0x28a70`
- `0x29e70`
- `0x29e90`
- `0x29eb0`
- `0x29f00`
- `0x29f60`

## pseudocode

```c

```

## disassembly

```asm
0x28a70  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x28a75  ldarg.1
0x28a76  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsOneNoteIntegrationEnabledForEntity(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata)
0x28a7b  brfalse.s loc_28AE6
0x28a7d  newobj   instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.OneNoteControl::.ctor()
0x28a82  dup
0x28a83  ldstr    aOnenotecontrol// "onenotecontrol_"
0x28a88  ldarg.0
0x28a89  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x28a8e  call     string [mscorlib]System.String::Concat(string, string)
0x28a93  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x28a98  dup
0x28a99  ldarg.0
0x28a9a  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x28a9f  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.OneNoteControl::set_MasterComponentId(string value)
0x28aa4  stloc.0
0x28aa5  ldarg.0
0x28aa6  call     instance class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabDataContainer> Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabsControl::get_Items()
0x28aab  newobj   instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabDataContainer::.ctor()
0x28ab0  dup
0x28ab1  ldstr    aOnenotetab// "OneNoteTab"
0x28ab6  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabDataContainer::set_TabId(string value)
0x28abb  dup
0x28abc  ldloc.0
0x28abd  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabDataContainer::set_Control(class [System.Web]System.Web.UI.Control value)
0x28ac2  dup
0x28ac3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x28ac8  ldstr    aWebToolsFormed_0// "Web.Tools.FormEditor.Dialogs.field.onen"...
0x28acd  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x28ad2  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x28ad7  callvirt instance string [mscorlib]System.String::ToUpper(class [mscorlib]System.Globalization.CultureInfo)
0x28adc  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabDataContainer::set_TabName(string value)
0x28ae1  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabDataContainer>::Add(var<u1>)
0x28ae6  ret
```
