# Microsoft.Crm.Authentication.Claims.IdentityConfigurationProvider::InitializeApplication

- ea: `0xa3d0`
- end: `0xa43f`
- name: `Microsoft.Crm.Authentication.Claims.IdentityConfigurationProvider::InitializeApplication`
- size: `111`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0xc6a0`

## callees

- `0x7670`
- `0x78e0`
- `0xa3d0`

## string_xrefs

- `0xa41c`: `Unloaded AppDomain since exception occurred in Application_OnStart IdentityConfigurationProvider.InitializeApplication`
- `0xa432`: `Unloaded AppDomain since exception occurred in Application_OnStart IdentityConfigurationProvider.InitializeApplication`

## pseudocode

```c

```

## disassembly

```asm
0xa3d0  call     bool [Microsoft.Crm.Core]Microsoft.Crm.CrmAuthenticationContext::get_ClaimsEnabled()
0xa3d5  brfalse.s loc_A3FB
0xa3d7  ldsfld   class [mscorlib]System.EventHandler`1<class [System.IdentityModel.Services]System.IdentityModel.Services.Configuration.FederationConfigurationCreatedEventArgs> <>c::<>9__8_0
0xa3dc  dup
0xa3dd  brtrue.s loc_A3F6
0xa3df  pop
0xa3e0  ldsfld   class <>c <>c::<>9
0xa3e5  ldftn    instance void <>c::<InitializeApplication>b__8_0(object o, class [System.IdentityModel.Services]System.IdentityModel.Services.Configuration.FederationConfigurationCreatedEventArgs args)
0xa3eb  newobj   instance void class [mscorlib]System.EventHandler`1<class [System.IdentityModel.Services]System.IdentityModel.Services.Configuration.FederationConfigurationCreatedEventArgs>::.ctor(object, native int)
0xa3f0  dup
0xa3f1  stsfld   class [mscorlib]System.EventHandler`1<class [System.IdentityModel.Services]System.IdentityModel.Services.Configuration.FederationConfigurationCreatedEventArgs> <>c::<>9__8_0
0xa3f6  call     void [System.IdentityModel.Services]System.IdentityModel.Services.FederatedAuthentication::add_FederationConfigurationCreated(class [mscorlib]System.EventHandler`1<class [System.IdentityModel.Services]System.IdentityModel.Services.Configuration.FederationConfigurationCreatedEventArgs>)
0xa3fb  leave.s  loc_A43E
0xa3fd  stloc.0
0xa3fe  call     void [System.Web]System.Web.HttpRuntime::UnloadAppDomain()
0xa403  ldc.i4.1
0xa404  ldc.i4   0xC0004335
0xa409  conv.u8
0xa40a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa40f  ldstr    a0Exception1// "{0}:, Exception: {1}"
0xa414  ldc.i4.2
0xa415  newarr   [mscorlib]System.Object
0xa41a  dup
0xa41b  ldc.i4.0
0xa41c  ldstr    aUnloadedAppdom// "Unloaded AppDomain since exception occu"...
0xa421  stelem.ref
0xa422  dup
0xa423  ldc.i4.1
0xa424  ldloc.0
0xa425  stelem.ref
0xa426  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xa42b  ldnull
0xa42c  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::WriteEventLog(valuetype [System]System.Diagnostics.EventLogEntryType errorLevel, int64 eventId, string context, [opt] class [mscorlib]System.Exception exception)
0xa431  ldloc.0
0xa432  ldstr    aUnloadedAppdom// "Unloaded AppDomain since exception occu"...
0xa437  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::LogException(class [mscorlib]System.Exception exception, [opt] string context)
0xa43c  rethrow
0xa43e  ret
```
