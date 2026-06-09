# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SfaTabsControl::CreateChildControls

- ea: `0x28820`
- end: `0x289c9`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SfaTabsControl::CreateChildControls`
- size: `425`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x17930`
- `0x17950`
- `0x28640`
- `0x28650`
- `0x28800`
- `0x28820`
- `0x289d0`
- `0x28a70`
- `0x28af0`
- `0x28b80`
- `0x28c00`
- `0x28d50`
- `0x28e10`
- `0x29f40`
- `0x29f60`
- `0x2a1b0`

## string_xrefs

- `0x28858`: `CreateChildControls`
- `0x288fa`: `<control id="{0}" classid="{1}" disabled="false"><parameters><IsControlReadOnly>{2}</IsControlReadOnly><MasterComponentId>{3}</MasterComponentId></parameters></control>`

## pseudocode

```c

```

## disassembly

```asm
0x28820  ldnull
0x28821  stloc.0
0x28822  ldnull
0x28823  stloc.1
0x28824  ldnull
0x28825  stloc.2
0x28826  ldarg.0
0x28827  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormDescriptor Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_CurrentFormDescriptor()
0x2882c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormDescriptor::get_EntityMetadata()
0x28831  stloc.3
0x28832  ldloc.3
0x28833  brtrue.s loc_28847
0x28835  ldnull
0x28836  ldstr    aNotAbleToRetri_1// "Not able to retrieve EntityMetadaData f"...
0x2883b  ldc.i4.0
0x2883c  newarr   [mscorlib]System.Object
0x28841  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::Error(class [mscorlib]System.Exception, string, object[])
0x28846  ret
0x28847  ldarg.0
0x28848  ldloc.3
0x28849  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SfaTabsControl::DecideDefaultTab(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entityMetadata)
0x2884e  call     class [Microsoft.Crm.Core]Microsoft.Crm.MetricsReporting [Microsoft.Crm.Core]Microsoft.Crm.MetricsReporting::get_Instance()
0x28853  ldstr    aSfatabsInitial// "SFATabs.Initialization"
0x28858  ldstr    aCreatechildcon// "CreateChildControls"
0x2885d  ldnull
0x2885e  ldloca.s 4
0x28860  initobj  [mscorlib]System.DateTime
0x28866  ldloc.s  4
0x28868  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x2886d  dup
0x2886e  ldstr    aInitialtab// "initialTab"
0x28873  ldarg.0
0x28874  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabsControl::get_DefaultTabId()
0x28879  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x2887e  dup
0x2887f  ldstr    aForm// "form"
0x28884  ldarg.0
0x28885  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_CurrentForm()
0x2888a  brfalse.s loc_28899
0x2888c  ldarg.0
0x2888d  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_CurrentForm()
0x28892  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x28897  br.s     loc_2889A
0x28899  ldnull
0x2889a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x2889f  dup
0x288a0  ldstr    aEntity_0// "entity"
0x288a5  ldarg.0
0x288a6  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_CurrentForm()
0x288ab  brfalse.s loc_288BA
0x288ad  ldarg.0
0x288ae  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_CurrentForm()
0x288b3  callvirt instance string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::get_EntityLogicalName()
0x288b8  br.s     loc_288BB
0x288ba  ldnull
0x288bb  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x288c0  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Core.Diagnostics.Metrics.Metric [Microsoft.Crm.Core]Microsoft.Crm.MetricsReporting::AddMetric(string, string, string, valuetype [mscorlib]System.DateTime, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>)
0x288c5  pop
0x288c6  ldarg.0
0x288c7  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x288cc  ldstr    aCasesconversat// "casesconversations"
0x288d1  callvirt instance bool [mscorlib]System.String::Contains(string)
0x288d6  brfalse.s loc_288DF
0x288d8  ldarg.0
0x288d9  ldc.i4.1
0x288da  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SfaTabsControl::set_IsControlReadOnly(bool value)
0x288df  ldloc.3
0x288e0  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_HasActivities()
0x288e5  brfalse  loc_28983
0x288ea  ldarg.0
0x288eb  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SfaTabsControl::get_IsRefreshForm()
0x288f0  brfalse  loc_28983
0x288f5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x288fa  ldstr    aControlId0Clas// "<control id=\"{0}\" classid=\"{1}\" dis"...
0x288ff  ldc.i4.4
0x28900  newarr   [mscorlib]System.Object
0x28905  dup
0x28906  ldc.i4.0
0x28907  ldstr    aActivitycontai_5// "activityContainer_"
0x2890c  ldarg.0
0x2890d  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x28912  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmXmlAttributeEncode(string)
0x28917  call     string [mscorlib]System.String::Concat(string, string)
0x2891c  stelem.ref
0x2891d  dup
0x2891e  ldc.i4.1
0x2891f  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.FormControlClassId::ActivitiesContainerControl
0x28924  stloc.s  5
0x28926  ldloca.s 5
0x28928  constrained. [mscorlib]System.Guid
0x2892e  callvirt instance string [mscorlib]System.Object::ToString()
0x28933  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmXmlAttributeEncode(string)
0x28938  stelem.ref
0x28939  dup
0x2893a  ldc.i4.2
0x2893b  ldarg.0
0x2893c  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SfaTabsControl::get_IsControlReadOnly()
0x28941  box      [mscorlib]System.Boolean
0x28946  stelem.ref
0x28947  dup
0x28948  ldc.i4.3
0x28949  ldarg.0
0x2894a  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x2894f  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmXmlAttributeEncode(string)
0x28954  stelem.ref
0x28955  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2895a  stloc.0
0x2895b  ldloc.2
0x2895c  brtrue.s loc_28983
0x2895e  ldloc.0
0x2895f  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x28964  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_FirstChild()
0x28969  stloc.2
0x2896a  ldloc.2
0x2896b  ldnull
0x2896c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x28971  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor::.ctor(class [System.Xml]System.Xml.XmlNode, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x28976  stloc.1
0x28977  ldarg.0
0x28978  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor> Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SfaTabsControl::_controlDescriptors
0x2897d  ldloc.1
0x2897e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor>::Add(var<u1>)
0x28983  ldarg.0
0x28984  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_CurrentForm()
0x28989  brfalse.s loc_289C2
0x2898b  ldarg.0
0x2898c  call     instance class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabDataContainer> Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabsControl::get_Items()
0x28991  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabDataContainer>::get_Count()
0x28996  brtrue.s loc_289C2
0x28998  ldarg.0
0x28999  ldloc.3
0x2899a  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SfaTabsControl::CreateYammerControls(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entityMetadata)
0x2899f  ldarg.0
0x289a0  ldloc.3
0x289a1  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SfaTabsControl::CreateActionHubControl(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entityMetadata)
0x289a6  ldarg.0
0x289a7  ldloc.3
0x289a8  ldloc.1
0x289a9  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SfaTabsControl::CreateActivitiesControl(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entityMetadata, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor activityControlDescriptor)
0x289ae  ldarg.0
0x289af  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SfaTabsControl::CreateSearchControl()
0x289b4  ldarg.0
0x289b5  ldloc.3
0x289b6  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SfaTabsControl::CreateNotesControl(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entityMetadata)
0x289bb  ldarg.0
0x289bc  ldloc.3
0x289bd  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SfaTabsControl::CreateOneNoteControl(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entityMetadata)
0x289c2  ldarg.0
0x289c3  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabsControl::CreateChildControls()
0x289c8  ret
```
