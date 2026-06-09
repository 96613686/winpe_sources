# Microsoft.Crm.Authentication.Claims.IdentityConfigurationProvider::InitializeConfiguration

- ea: `0xa340`
- end: `0xa389`
- name: `Microsoft.Crm.Authentication.Claims.IdentityConfigurationProvider::InitializeConfiguration`
- size: `73`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0xa440`

## callees

- `0x78e0`
- `0xa340`

## string_xrefs

- `0xa36a`: `IdentityConfigurationProvider.InitializeConfiguration`

## pseudocode

```c

```

## disassembly

```asm
0xa340  ldsfld   bool Microsoft.Crm.Authentication.Claims.IdentityConfigurationProvider::s_InitializedAlready
0xa345  brfalse.s loc_A348
0xa347  ret
0xa348  ldsfld   object Microsoft.Crm.Authentication.Claims.IdentityConfigurationProvider::s_lock
0xa34d  stloc.0
0xa34e  ldc.i4.0
0xa34f  stloc.1
0xa350  ldloc.0
0xa351  ldloca.s 1
0xa353  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0xa358  ldsfld   bool Microsoft.Crm.Authentication.Claims.IdentityConfigurationProvider::s_InitializedAlready
0xa35d  brfalse.s loc_A361
0xa35f  leave.s  loc_A388
0xa361  nop
0xa362  ldarg.0
0xa363  callvirt instance void [mscorlib]System.Action::Invoke()
0xa368  leave.s  loc_A376
0xa36a  ldstr    aIdentityconfig// "IdentityConfigurationProvider.Initializ"...
0xa36f  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::LogException(class [mscorlib]System.Exception exception, [opt] string context)
0xa374  rethrow
0xa376  ldc.i4.1
0xa377  stsfld   bool Microsoft.Crm.Authentication.Claims.IdentityConfigurationProvider::s_InitializedAlready
0xa37c  leave.s  loc_A388
0xa37e  ldloc.1
0xa37f  brfalse.s loc_A387
0xa381  ldloc.0
0xa382  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0xa387  endfinally
0xa388  ret
```
