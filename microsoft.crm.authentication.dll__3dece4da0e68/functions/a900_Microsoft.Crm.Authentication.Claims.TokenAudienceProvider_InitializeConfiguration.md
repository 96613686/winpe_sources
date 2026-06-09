# Microsoft.Crm.Authentication.Claims.TokenAudienceProvider::InitializeConfiguration

- ea: `0xa900`
- end: `0xa949`
- name: `Microsoft.Crm.Authentication.Claims.TokenAudienceProvider::InitializeConfiguration`
- size: `73`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0xa870`

## callees

- `0x78e0`
- `0xa900`

## string_xrefs

- `0xa92a`: `TokenAudienceProvider.InitializeConfiguration`

## pseudocode

```c

```

## disassembly

```asm
0xa900  ldsfld   bool Microsoft.Crm.Authentication.Claims.TokenAudienceProvider::s_InitializedAlready
0xa905  brfalse.s loc_A908
0xa907  ret
0xa908  ldsfld   object Microsoft.Crm.Authentication.Claims.TokenAudienceProvider::s_lock
0xa90d  stloc.0
0xa90e  ldc.i4.0
0xa90f  stloc.1
0xa910  ldloc.0
0xa911  ldloca.s 1
0xa913  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0xa918  ldsfld   bool Microsoft.Crm.Authentication.Claims.TokenAudienceProvider::s_InitializedAlready
0xa91d  brfalse.s loc_A921
0xa91f  leave.s  loc_A948
0xa921  nop
0xa922  ldarg.0
0xa923  callvirt instance void [mscorlib]System.Action::Invoke()
0xa928  leave.s  loc_A936
0xa92a  ldstr    aTokenaudiencep// "TokenAudienceProvider.InitializeConfigu"...
0xa92f  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::LogException(class [mscorlib]System.Exception exception, [opt] string context)
0xa934  rethrow
0xa936  ldc.i4.1
0xa937  stsfld   bool Microsoft.Crm.Authentication.Claims.TokenAudienceProvider::s_InitializedAlready
0xa93c  leave.s  loc_A948
0xa93e  ldloc.1
0xa93f  brfalse.s loc_A947
0xa941  ldloc.0
0xa942  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0xa947  endfinally
0xa948  ret
```
