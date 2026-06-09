# Microsoft.Crm.Common.Application.WebServices.YammerConfigWebService::GetAdminNetworks

- ea: `0x310`
- end: `0x34f`
- name: `Microsoft.Crm.Common.Application.WebServices.YammerConfigWebService::GetAdminNetworks`
- size: `63`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x310`
- `0x520`

## pseudocode

```c

```

## disassembly

```asm
0x310  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x315  call     void [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Yammer.YammerState::EnsureUserCanConfigureYammer(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation)
0x31a  ldarg.0
0x31b  call     instance class [Microsoft.Crm.YammerIntegration]Microsoft.Crm.YammerIntegration.YammerProxy Microsoft.Crm.Common.Application.WebServices.YammerConfigWebService::GetProxy()
0x320  callvirt instance class [Microsoft.Crm.YammerIntegration]Microsoft.Crm.YammerIntegration.Network[] [Microsoft.Crm.YammerIntegration]Microsoft.Crm.YammerIntegration.YammerProxy::GetNetworks()
0x325  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.YammerIntegration]Microsoft.Crm.YammerIntegration.Network, bool> <>c::<>9__18_0
0x32a  dup
0x32b  brtrue.s loc_344
0x32d  pop
0x32e  ldsfld   class <>c <>c::<>9
0x333  ldftn    instance bool <>c::<GetAdminNetworks>b__18_0(class [Microsoft.Crm.YammerIntegration]Microsoft.Crm.YammerIntegration.Network n)
0x339  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Crm.YammerIntegration]Microsoft.Crm.YammerIntegration.Network, bool>::.ctor(object, native int)
0x33e  dup
0x33f  stsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.YammerIntegration]Microsoft.Crm.YammerIntegration.Network, bool> <>c::<>9__18_0
0x344  call     T0x2B000002
0x349  call     T0x2B000003
0x34e  ret
```
