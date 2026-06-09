# Microsoft.Crm.Authentication.Claims.XrmJwtSecurityTokenHandlerBase::InitializeConfiguration

- ea: `0x9fd0`
- end: `0xa01d`
- name: `Microsoft.Crm.Authentication.Claims.XrmJwtSecurityTokenHandlerBase::InitializeConfiguration`
- size: `77`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x9f50`

## callees

- `0x78e0`
- `0x9fd0`

## string_xrefs

- `0x9ffd`: `XrmJwtSecurityTokenHandler.InitializeConfiguration`

## pseudocode

```c

```

## disassembly

```asm
0x9fd0  ldarg.0
0x9fd1  ldfld    bool Microsoft.Crm.Authentication.Claims.XrmJwtSecurityTokenHandlerBase::initializedAlready
0x9fd6  brfalse.s loc_9FD9
0x9fd8  ret
0x9fd9  ldarg.0
0x9fda  ldfld    object Microsoft.Crm.Authentication.Claims.XrmJwtSecurityTokenHandlerBase::lockObject
0x9fdf  stloc.0
0x9fe0  ldc.i4.0
0x9fe1  stloc.1
0x9fe2  ldloc.0
0x9fe3  ldloca.s 1
0x9fe5  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x9fea  ldarg.0
0x9feb  ldfld    bool Microsoft.Crm.Authentication.Claims.XrmJwtSecurityTokenHandlerBase::initializedAlready
0x9ff0  brfalse.s loc_9FF4
0x9ff2  leave.s  loc_A01C
0x9ff4  nop
0x9ff5  ldarg.1
0x9ff6  callvirt instance void [mscorlib]System.Action::Invoke()
0x9ffb  leave.s  loc_A009
0x9ffd  ldstr    aXrmjwtsecurity// "XrmJwtSecurityTokenHandler.InitializeCo"...
0xa002  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::LogException(class [mscorlib]System.Exception exception, [opt] string context)
0xa007  rethrow
0xa009  ldarg.0
0xa00a  ldc.i4.1
0xa00b  stfld    bool Microsoft.Crm.Authentication.Claims.XrmJwtSecurityTokenHandlerBase::initializedAlready
0xa010  leave.s  loc_A01C
0xa012  ldloc.1
0xa013  brfalse.s loc_A01B
0xa015  ldloc.0
0xa016  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0xa01b  endfinally
0xa01c  ret
```
