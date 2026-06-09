# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SfaTabsControl::CreateActivitiesControl

- ea: `0x28af0`
- end: `0x28b78`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SfaTabsControl::CreateActivitiesControl`
- size: `136`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x28820`

## callees

- `0x17930`
- `0x17950`
- `0x28480`
- `0x28640`
- `0x28800`
- `0x28af0`
- `0x290e0`
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
0x28af0  ldarg.1
0x28af1  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_HasActivities()
0x28af6  brfalse.s loc_28B77
0x28af8  ldarg.0
0x28af9  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SfaTabsControl::get_IsRefreshForm()
0x28afe  brfalse.s loc_28B77
0x28b00  ldarg.0
0x28b01  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SfaTabsControl::get_EmailConversationView()
0x28b06  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::SetIsEmailConversationViewFeatureAvailable(bool)
0x28b0b  ldarg.0
0x28b0c  ldarg.2
0x28b0d  ldarg.0
0x28b0e  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SfaTabsControl::get_IsControlReadOnly()
0x28b13  brtrue.s loc_28B1D
0x28b15  ldarg.0
0x28b16  call     instance valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormFactor [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppControl::get_FormFactor()
0x28b1b  br.s     loc_28B1E
0x28b1d  ldc.i4.2
0x28b1e  ldarg.0
0x28b1f  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x28b24  ldarg.0
0x28b25  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_CurrentForm()
0x28b2a  ldarg.0
0x28b2b  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormDescriptor Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_CurrentFormDescriptor()
0x28b30  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.ControlActivator::CreateControl(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormFactor, string, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormDescriptor)
0x28b35  castclass [System.Web]System.Web.UI.Control
0x28b3a  stfld    class [System.Web]System.Web.UI.Control Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SfaTabsControl::controlActivity
0x28b3f  ldarg.0
0x28b40  call     instance class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabDataContainer> Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabsControl::get_Items()
0x28b45  newobj   instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabDataContainer::.ctor()
0x28b4a  dup
0x28b4b  ldstr    aActivitiestab// "ActivitiesTab"
0x28b50  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabDataContainer::set_TabId(string value)
0x28b55  dup
0x28b56  ldarg.0
0x28b57  ldfld    class [System.Web]System.Web.UI.Control Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SfaTabsControl::controlActivity
0x28b5c  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabDataContainer::set_Control(class [System.Web]System.Web.UI.Control value)
0x28b61  dup
0x28b62  ldarg.0
0x28b63  ldstr    aActivitypointe_1// "activitypointer"
0x28b68  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SfaTabsControl::GetTabName(string entityTypeName)
0x28b6d  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabDataContainer::set_TabName(string value)
0x28b72  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabDataContainer>::Add(var<u1>)
0x28b77  ret
```
