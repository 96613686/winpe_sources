# Microsoft.Crm.Common.Application.WebServices.YammerConfigWebService::GetProxy

- ea: `0x520`
- end: `0x57e`
- name: `Microsoft.Crm.Common.Application.WebServices.YammerConfigWebService::GetProxy`
- size: `94`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x310`
- `0x350`
- `0x740`

## callees

- `0x90`
- `0x520`

## pseudocode

```c

```

## disassembly

```asm
0x520  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x525  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x52a  call     class [mscorlib]System.Security.SecureString [Microsoft.Crm.Yammer]Microsoft.Crm.Yammer.YammerServiceUtility::GetYammerOAuthAccessToken(valuetype [mscorlib]System.Guid)
0x52f  stloc.0
0x530  ldloc.0
0x531  brtrue.s loc_544
0x533  ldc.i4   0x8005F109
0x538  ldc.i4.0
0x539  newarr   [mscorlib]System.Object
0x53e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x543  throw
0x544  ldloc.0
0x545  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmKeyService::GetStringFromSecureString(class [mscorlib]System.Security.SecureString)
0x54a  stloc.1
0x54b  ldloc.1
0x54c  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x551  brfalse.s loc_564
0x553  ldc.i4   0x8005F110
0x558  ldc.i4.0
0x559  newarr   [mscorlib]System.Object
0x55e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x563  throw
0x564  ldloc.1
0x565  call     valuetype [mscorlib]System.TimeSpan Microsoft.Crm.Common.Application.WebServices.YammerConfigWebService::get_YammerConnectionTimeout()
0x56a  newobj   instance void [Microsoft.Crm.YammerIntegration]Microsoft.Crm.YammerIntegration.YammerProxy::.ctor(string, valuetype [mscorlib]System.TimeSpan)
0x56f  stloc.2
0x570  leave.s  loc_57C
0x572  ldloc.0
0x573  brfalse.s loc_57B
0x575  ldloc.0
0x576  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x57b  endfinally
0x57c  ldloc.2
0x57d  ret
```
