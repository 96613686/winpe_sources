# Microsoft.Crm.Common.Application.WebServices.YammerConfigWebService::AuthenticateYammerUser

- ea: `0x180`
- end: `0x217`
- name: `Microsoft.Crm.Common.Application.WebServices.YammerConfigWebService::AuthenticateYammerUser`
- size: `151`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xb0`
- `0x130`

## callees

- `0x90`
- `0x180`
- `0x780`

## pseudocode

```c

```

## disassembly

```asm
0x180  ldarg.0
0x181  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.Common.Application.WebServices.YammerConfigWebService::ReadKeys()
0x186  dup
0x187  ldstr    aApplicationid// "ApplicationId"
0x18c  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x191  castclass [mscorlib]System.String
0x196  stloc.0
0x197  ldstr    aApplicationsec// "ApplicationSecret"
0x19c  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x1a1  castclass [mscorlib]System.Security.SecureString
0x1a6  stloc.1
0x1a7  ldloc.1
0x1a8  brtrue.s loc_1AD
0x1aa  ldnull
0x1ab  br.s     loc_1B3
0x1ad  ldloc.1
0x1ae  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmKeyService::GetStringFromSecureString(class [mscorlib]System.Security.SecureString)
0x1b3  stloc.2
0x1b4  ldloc.0
0x1b5  brfalse.s loc_1BA
0x1b7  ldloc.2
0x1b8  brtrue.s loc_1CB
0x1ba  ldc.i4   0x80044170
0x1bf  ldc.i4.0
0x1c0  newarr   [mscorlib]System.Object
0x1c5  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x1ca  throw
0x1cb  nop
0x1cc  ldloc.0
0x1cd  ldloc.2
0x1ce  ldarg.1
0x1cf  ldarg.2
0x1d0  call     valuetype [mscorlib]System.TimeSpan Microsoft.Crm.Common.Application.WebServices.YammerConfigWebService::get_YammerConnectionTimeout()
0x1d5  call     class [Microsoft.Crm.YammerIntegration]Microsoft.Crm.YammerIntegration.AccessTokenResponse [Microsoft.Crm.YammerIntegration]Microsoft.Crm.YammerIntegration.YammerProxy::ReadAccessToken(string, string, string, string, valuetype [mscorlib]System.TimeSpan)
0x1da  stloc.3
0x1db  leave.s  loc_215
0x1dd  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0x1e2  isinst   [System]System.Net.WebException
0x1e7  stloc.s  4
0x1e9  ldloc.s  4
0x1eb  brfalse.s loc_213
0x1ed  ldloc.s  4
0x1ef  callvirt instance valuetype [System]System.Net.WebExceptionStatus [System]System.Net.WebException::get_Status()
0x1f4  ldc.i4.7
0x1f5  bne.un.s loc_213
0x1f7  ldloc.s  4
0x1f9  callvirt instance class [System]System.Net.WebResponse [System]System.Net.WebException::get_Response()
0x1fe  castclass [System]System.Net.HttpWebResponse
0x203  callvirt instance valuetype [System]System.Net.HttpStatusCode [System]System.Net.HttpWebResponse::get_StatusCode()
0x208  ldc.i4   0x191
0x20d  bne.un.s loc_213
0x20f  ldnull
0x210  stloc.3
0x211  leave.s  loc_215
0x213  rethrow
0x215  ldloc.3
0x216  ret
```
