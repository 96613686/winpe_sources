# Microsoft.Crm.Application.Components.UI.CrmUIControlBase::RegisterClientAjaxComponent_0

- ea: `0x23f20`
- end: `0x23fed`
- name: `Microsoft.Crm.Application.Components.UI.CrmUIControlBase::RegisterClientAjaxComponent_0`
- size: `205`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x23f10`

## callees

- `0x2d50`
- `0xbf50`
- `0x23b60`
- `0x23d90`
- `0x23ef0`
- `0x23f20`

## pseudocode

```c

```

## disassembly

```asm
0x23f20  ldarg.0
0x23f21  call     instance bool Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_AutoRegisterClientComponent()
0x23f26  brtrue.s loc_23F29
0x23f28  ret
0x23f29  ldarg.2
0x23f2a  brtrue.s loc_23F33
0x23f2c  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x23f31  starg.s  2
0x23f33  ldarg.0
0x23f34  ldfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<int32> Microsoft.Crm.Application.Components.UI.CrmUIControlBase::subscribedEvents
0x23f39  brfalse.s loc_23F5A
0x23f3b  ldarg.0
0x23f3c  ldfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<int32> Microsoft.Crm.Application.Components.UI.CrmUIControlBase::subscribedEvents
0x23f41  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<int32>::get_Count()
0x23f46  ldc.i4.0
0x23f47  ble.s    loc_23F5A
0x23f49  ldarg.2
0x23f4a  ldstr    aSubscribedeven// "subscribedEvents"
0x23f4f  ldarg.0
0x23f50  ldfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<int32> Microsoft.Crm.Application.Components.UI.CrmUIControlBase::subscribedEvents
0x23f55  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x23f5a  ldarg.s  4
0x23f5c  brtrue.s loc_23F65
0x23f5e  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x23f63  starg.s  4
0x23f65  ldarg.0
0x23f66  call     instance class Microsoft.Crm.Application.Components.UI.EventManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_EventManager()
0x23f6b  brfalse.s loc_23FB1
0x23f6d  ldarg.s  4
0x23f6f  ldstr    aEventmanager// "eventManager"
0x23f74  ldarg.0
0x23f75  call     instance class Microsoft.Crm.Application.Components.UI.EventManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_EventManager()
0x23f7a  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x23f7f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x23f84  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x23f89  callvirt instance class [System.Web]System.Web.IHttpHandler [System.Web]System.Web.HttpContext::get_CurrentHandler()
0x23f8e  isinst   Microsoft.Crm.Controls.UIPage
0x23f93  stloc.0
0x23f94  ldloc.0
0x23f95  brfalse.s loc_23FB1
0x23f97  ldloc.0
0x23f98  callvirt instance bool Microsoft.Crm.Controls.UIPage::get_IsFlatUIPage()
0x23f9d  brfalse.s loc_23FB1
0x23f9f  ldarg.s  4
0x23fa1  ldstr    aRootmanager// "rootManager"
0x23fa6  ldloc.0
0x23fa7  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x23fac  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x23fb1  ldarg.s  5
0x23fb3  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x23fb8  brfalse.s loc_23FD8
0x23fba  ldarg.2
0x23fbb  ldstr    aId// "id"
0x23fc0  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x23fc5  brtrue.s loc_23FD8
0x23fc7  ldarg.2
0x23fc8  ldstr    aId// "id"
0x23fcd  ldarg.0
0x23fce  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x23fd3  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x23fd8  ldarg.0
0x23fd9  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x23fde  ldarg.1
0x23fdf  ldarg.2
0x23fe0  ldarg.3
0x23fe1  ldarg.s  4
0x23fe3  ldarg.s  5
0x23fe5  ldarg.s  6
0x23fe7  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::CreateClientAjaxComponent(string componentTypeName, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> events, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> references, string elementId, bool deferredCreate)
0x23fec  ret
```
