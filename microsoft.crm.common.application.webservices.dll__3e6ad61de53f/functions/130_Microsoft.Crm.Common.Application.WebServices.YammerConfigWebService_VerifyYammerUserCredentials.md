# Microsoft.Crm.Common.Application.WebServices.YammerConfigWebService::VerifyYammerUserCredentials

- ea: `0x130`
- end: `0x176`
- name: `Microsoft.Crm.Common.Application.WebServices.YammerConfigWebService::VerifyYammerUserCredentials`
- size: `70`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x130`
- `0x180`
- `0x580`

## pseudocode

```c

```

## disassembly

```asm
0x130  ldarg.0
0x131  ldarg.1
0x132  ldarg.2
0x133  call     instance class [Microsoft.Crm.YammerIntegration]Microsoft.Crm.YammerIntegration.AccessTokenResponse Microsoft.Crm.Common.Application.WebServices.YammerConfigWebService::AuthenticateYammerUser(string userEmail, string userPassword)
0x138  stloc.0
0x139  ldloc.0
0x13a  brfalse.s loc_144
0x13c  ldloc.0
0x13d  callvirt instance class [Microsoft.Crm.YammerIntegration]Microsoft.Crm.YammerIntegration.AuthenticatedUser [Microsoft.Crm.YammerIntegration]Microsoft.Crm.YammerIntegration.AccessTokenResponse::get_User()
0x142  brtrue.s loc_148
0x144  ldc.i4.0
0x145  stloc.1
0x146  leave.s  loc_174
0x148  ldarg.0
0x149  ldarg.1
0x14a  ldloc.0
0x14b  callvirt instance class [Microsoft.Crm.YammerIntegration]Microsoft.Crm.YammerIntegration.AuthenticatedUser [Microsoft.Crm.YammerIntegration]Microsoft.Crm.YammerIntegration.AccessTokenResponse::get_User()
0x150  callvirt instance int32 [Microsoft.Crm.YammerIntegration]Microsoft.Crm.YammerIntegration.AuthenticatedUser::get_Id()
0x155  stloc.2
0x156  ldloca.s 2
0x158  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x15d  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x162  call     instance void Microsoft.Crm.Common.Application.WebServices.YammerConfigWebService::SaveEmailAndUserId(string yammerEmailAddress, string yammerUserId)
0x167  ldc.i4.1
0x168  stloc.1
0x169  leave.s  loc_174
0x16b  stloc.3
0x16c  ldarg.0
0x16d  ldloc.3
0x16e  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x173  throw
0x174  ldloc.1
0x175  ret
```
