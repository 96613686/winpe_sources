# Microsoft.Crm.Application.Components.UI.CrmUIControlBase::OnLoadInternal

- ea: `0x23df0`
- end: `0x23eef`
- name: `Microsoft.Crm.Application.Components.UI.CrmUIControlBase::OnLoadInternal`
- size: `255`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x23d30`

## callees

- `0x17e50`
- `0x17e60`
- `0x18010`
- `0x239c0`
- `0x23d90`
- `0x23da0`
- `0x23db0`
- `0x23de0`
- `0x23df0`

## pseudocode

```c

```

## disassembly

```asm
0x23df0  ldarg.0
0x23df1  call     instance bool Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_IsHostedOnFlatUIPage()
0x23df6  brtrue.s loc_23E00
0x23df8  ldarg.0
0x23df9  ldc.i4.0
0x23dfa  stfld    bool Microsoft.Crm.Application.Components.UI.CrmUIControlBase::EnableEventManagerSupport
0x23dff  ret
0x23e00  ldarg.0
0x23e01  ldfld    bool Microsoft.Crm.Application.Components.UI.CrmUIControlBase::EnableEventManagerSupport
0x23e06  brfalse  loc_23EEE
0x23e0b  ldarg.0
0x23e0c  call     instance class Microsoft.Crm.Application.Components.UI.EventManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_EventManager()
0x23e11  brtrue   loc_23EDD
0x23e16  ldnull
0x23e17  stloc.0
0x23e18  ldarg.0
0x23e19  callvirt instance class [System.Web]System.Web.UI.Control [System.Web]System.Web.UI.Control::get_Parent()
0x23e1e  stloc.1
0x23e1f  br.s     loc_23E32
0x23e21  ldloc.1
0x23e22  isinst   Microsoft.Crm.Application.Components.UI.ICrmFlatUIControl
0x23e27  stloc.0
0x23e28  ldloc.0
0x23e29  brtrue.s loc_23E35
0x23e2b  ldloc.1
0x23e2c  callvirt instance class [System.Web]System.Web.UI.Control [System.Web]System.Web.UI.Control::get_Parent()
0x23e31  stloc.1
0x23e32  ldloc.1
0x23e33  brtrue.s loc_23E21
0x23e35  ldarg.0
0x23e36  ldfld    bool Microsoft.Crm.Application.Components.UI.CrmUIControlBase::UseParentEventManager
0x23e3b  brfalse.s loc_23E4E
0x23e3d  ldloc.0
0x23e3e  brfalse.s loc_23E4B
0x23e40  ldloc.0
0x23e41  callvirt instance class Microsoft.Crm.Application.Components.UI.EventManager Microsoft.Crm.Application.Components.UI.ICrmFlatUIControl::get_EventManager()
0x23e46  ldnull
0x23e47  cgt.un
0x23e49  br.s     loc_23E4F
0x23e4b  ldc.i4.0
0x23e4c  br.s     loc_23E4F
0x23e4e  ldc.i4.1
0x23e4f  ldstr    aControlIsUsing// "Control is using parent's eventmanager,"...
0x23e54  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x23e59  ldarg.0
0x23e5a  ldfld    bool Microsoft.Crm.Application.Components.UI.CrmUIControlBase::UseParentEventManager
0x23e5f  brfalse.s loc_23E64
0x23e61  ldloc.0
0x23e62  brtrue.s loc_23ED1
0x23e64  ldarg.0
0x23e65  newobj   instance void Microsoft.Crm.Application.Components.UI.EventManager::.ctor()
0x23e6a  call     instance void Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_EventManager(class Microsoft.Crm.Application.Components.UI.EventManager value)
0x23e6f  ldarg.0
0x23e70  call     instance class Microsoft.Crm.Application.Components.UI.EventManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_EventManager()
0x23e75  ldarg.0
0x23e76  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x23e7b  ldarg.0
0x23e7c  call     instance char [System.Web]System.Web.UI.Control::get_ClientIDSeparator()
0x23e81  stloc.2
0x23e82  ldloca.s 2
0x23e84  call     instance string [mscorlib]System.Char::ToString()
0x23e89  ldstr    aCrmeventmanage// "crmEventManager"
0x23e8e  call     string [mscorlib]System.String::Concat(string, string, string)
0x23e93  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x23e98  ldloc.0
0x23e99  brfalse.s loc_23EDD
0x23e9b  ldloc.0
0x23e9c  callvirt instance class Microsoft.Crm.Application.Components.UI.EventManager Microsoft.Crm.Application.Components.UI.ICrmFlatUIControl::get_EventManager()
0x23ea1  brfalse.s loc_23EDD
0x23ea3  ldarg.0
0x23ea4  call     instance class Microsoft.Crm.Application.Components.UI.EventManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_EventManager()
0x23ea9  ldloc.0
0x23eaa  callvirt instance class Microsoft.Crm.Application.Components.UI.EventManager Microsoft.Crm.Application.Components.UI.ICrmFlatUIControl::get_EventManager()
0x23eaf  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x23eb4  callvirt instance void Microsoft.Crm.Application.Components.UI.EventManager::set_ParentEventManagerId(string value)
0x23eb9  ldloc.0
0x23eba  callvirt instance class Microsoft.Crm.Application.Components.UI.EventManager Microsoft.Crm.Application.Components.UI.ICrmFlatUIControl::get_EventManager()
0x23ebf  ldarg.0
0x23ec0  call     instance class Microsoft.Crm.Application.Components.UI.EventManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_EventManager()
0x23ec5  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x23eca  callvirt instance void Microsoft.Crm.Application.Components.UI.EventManager::RegisterChildEventManagerId(string childControlId)
0x23ecf  br.s     loc_23EDD
0x23ed1  ldarg.0
0x23ed2  ldloc.0
0x23ed3  callvirt instance class Microsoft.Crm.Application.Components.UI.EventManager Microsoft.Crm.Application.Components.UI.ICrmFlatUIControl::get_EventManager()
0x23ed8  call     instance void Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_EventManager(class Microsoft.Crm.Application.Components.UI.EventManager value)
0x23edd  ldarg.0
0x23ede  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<int32>::.ctor()
0x23ee3  stfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<int32> Microsoft.Crm.Application.Components.UI.CrmUIControlBase::subscribedEvents
0x23ee8  ldarg.0
0x23ee9  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControlBase::RegisterSubscribedEvents()
0x23eee  ret
```
