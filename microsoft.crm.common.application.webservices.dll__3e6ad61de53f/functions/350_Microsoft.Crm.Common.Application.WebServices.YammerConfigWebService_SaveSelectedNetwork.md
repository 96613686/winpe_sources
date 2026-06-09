# Microsoft.Crm.Common.Application.WebServices.YammerConfigWebService::SaveSelectedNetwork

- ea: `0x350`
- end: `0x433`
- name: `Microsoft.Crm.Common.Application.WebServices.YammerConfigWebService::SaveSelectedNetwork`
- size: `227`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x350`
- `0x520`
- `0x1110`

## string_xrefs

- `0x3d0`: `yammeroauthaccesstokenexpired`
- `0x3e1`: `yammernetworkpermalink`
- `0x405`: `yammernetworkpermalink`

## pseudocode

```c

```

## disassembly

```asm
0x350  newobj   instance void <>c__DisplayClass19_0::.ctor()
0x355  stloc.0
0x356  ldloc.0
0x357  ldarg.1
0x358  stfld    int64 <>c__DisplayClass19_0::networkId
0x35d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x362  call     void [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Yammer.YammerState::EnsureUserCanConfigureYammer(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation)
0x367  ldarg.0
0x368  call     instance class [Microsoft.Crm.YammerIntegration]Microsoft.Crm.YammerIntegration.YammerProxy Microsoft.Crm.Common.Application.WebServices.YammerConfigWebService::GetProxy()
0x36d  stloc.1
0x36e  ldloc.0
0x36f  ldfld    int64 <>c__DisplayClass19_0::networkId
0x374  brfalse.s loc_38F
0x376  ldloc.1
0x377  callvirt instance class [Microsoft.Crm.YammerIntegration]Microsoft.Crm.YammerIntegration.NetworkToken[] [Microsoft.Crm.YammerIntegration]Microsoft.Crm.YammerIntegration.YammerProxy::GetTokens()
0x37c  ldloc.0
0x37d  ldftn    instance bool <>c__DisplayClass19_0::<SaveSelectedNetwork>b__0(class [Microsoft.Crm.YammerIntegration]Microsoft.Crm.YammerIntegration.NetworkToken t)
0x383  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Crm.YammerIntegration]Microsoft.Crm.YammerIntegration.NetworkToken, bool>::.ctor(object, native int)
0x388  call     T0x2B000004
0x38d  br.s     loc_390
0x38f  ldnull
0x390  stloc.2
0x391  ldstr    aOrganization// "organization"
0x396  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x39b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3a0  stloc.3
0x3a1  ldloc.3
0x3a2  ldstr    aOrganizationid// "organizationid"
0x3a7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x3ac  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x3b1  box      [mscorlib]System.Guid
0x3b6  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x3bb  ldloc.2
0x3bc  brfalse.s loc_404
0x3be  ldloc.3
0x3bf  ldstr    aDisabledreason// "disabledreason"
0x3c4  ldloc.2
0x3c5  callvirt instance string [Microsoft.Crm.YammerIntegration]Microsoft.Crm.YammerIntegration.NetworkToken::get_Token()
0x3ca  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x3cf  ldloc.3
0x3d0  ldstr    aYammeroauthacc// "yammeroauthaccesstokenexpired"
0x3d5  ldc.i4.0
0x3d6  box      [mscorlib]System.Boolean
0x3db  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x3e0  ldloc.3
0x3e1  ldstr    aYammernetworkp// "yammernetworkpermalink"
0x3e6  ldloc.2
0x3e7  callvirt instance string [Microsoft.Crm.YammerIntegration]Microsoft.Crm.YammerIntegration.NetworkToken::get_Permalink()
0x3ec  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x3f1  ldloc.3
0x3f2  ldstr    aYammergroupid// "yammergroupid"
0x3f7  ldc.i4.0
0x3f8  box      [mscorlib]System.Int32
0x3fd  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x402  br.s     loc_421
0x404  ldloc.3
0x405  ldstr    aYammernetworkp// "yammernetworkpermalink"
0x40a  ldnull
0x40b  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x410  ldloc.3
0x411  ldstr    aYammergroupid// "yammergroupid"
0x416  ldc.i4.0
0x417  box      [mscorlib]System.Int32
0x41c  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x421  ldloc.3
0x422  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x427  newobj   instance void [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Components.Platform.ServiceCommands.UpdateYammerPropertiesCommand::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x42c  callvirt instance class [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Messages.Internal.UpdateYammerPropertiesResponse [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Components.Platform.ServiceCommands.UpdateYammerPropertiesCommand::Execute()
0x431  pop
0x432  ret
```
