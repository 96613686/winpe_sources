# Microsoft.Crm.Authentication.AuthenticationStep::Authenticate

- ea: `0x3d30`
- end: `0x3ddd`
- name: `Microsoft.Crm.Authentication.AuthenticationStep::Authenticate`
- size: `173`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x3d30`
- `0x3de0`
- `0x40a0`
- `0x4870`
- `0x78e0`

## string_xrefs

- `0x3d48`: `AUTH: AuthenticationProvider [{0}] will be attempted.`

## pseudocode

```c

```

## disassembly

```asm
0x3d30  ldarg.0
0x3d31  ldfld    class Microsoft.Crm.Authentication.IAuthenticationPredicate Microsoft.Crm.Authentication.AuthenticationStep::_predicate
0x3d36  ldarg.1
0x3d37  callvirt instance bool Microsoft.Crm.Authentication.IAuthenticationPredicate::Evaluate(class [System.Web]System.Web.HttpApplication application)
0x3d3c  brfalse  loc_3DCB
0x3d41  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x3d46  ldc.i4.s 0x14
0x3d48  ldstr    aAuthAuthentica// "AUTH: AuthenticationProvider [{0}] will"...
0x3d4d  ldc.i4.1
0x3d4e  newarr   [mscorlib]System.Object
0x3d53  dup
0x3d54  ldc.i4.0
0x3d55  ldarg.0
0x3d56  ldfld    class Microsoft.Crm.Authentication.IAuthenticationProvider Microsoft.Crm.Authentication.AuthenticationStep::_provider
0x3d5b  stelem.ref
0x3d5c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3d61  ldarg.0
0x3d62  ldfld    class Microsoft.Crm.Authentication.IAuthenticationProvider Microsoft.Crm.Authentication.AuthenticationStep::_provider
0x3d67  brtrue.s loc_3D7B
0x3d69  ldarg.0
0x3d6a  ldarg.0
0x3d6b  ldarg.0
0x3d6c  ldfld    class Microsoft.Crm.Authentication.AuthenticationProviderXml Microsoft.Crm.Authentication.AuthenticationStep::_providerXml
0x3d71  call     instance class Microsoft.Crm.Authentication.IAuthenticationProvider Microsoft.Crm.Authentication.AuthenticationStep::LoadProvider(class Microsoft.Crm.Authentication.AuthenticationProviderXml providerXml)
0x3d76  stfld    class Microsoft.Crm.Authentication.IAuthenticationProvider Microsoft.Crm.Authentication.AuthenticationStep::_provider
0x3d7b  ldarg.0
0x3d7c  ldfld    class Microsoft.Crm.Authentication.IAuthenticationProvider Microsoft.Crm.Authentication.AuthenticationStep::_provider
0x3d81  ldarg.1
0x3d82  callvirt instance bool Microsoft.Crm.Authentication.IAuthenticationProvider::Authenticate(class [System.Web]System.Web.HttpApplication application)
0x3d87  stloc.0
0x3d88  ldloc.0
0x3d89  brfalse.s loc_3DC7
0x3d8b  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x3d90  ldc.i4.s 0x16
0x3d92  ldstr    aAuthAuthentica_0// "AUTH: AuthenticationProvider [{0}] hand"...
0x3d97  ldc.i4.3
0x3d98  newarr   [mscorlib]System.Object
0x3d9d  dup
0x3d9e  ldc.i4.0
0x3d9f  ldarg.0
0x3da0  ldfld    class Microsoft.Crm.Authentication.IAuthenticationProvider Microsoft.Crm.Authentication.AuthenticationStep::_provider
0x3da5  stelem.ref
0x3da6  dup
0x3da7  ldc.i4.1
0x3da8  ldarg.1
0x3da9  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpApplication::get_Request()
0x3dae  callvirt instance class [System]System.Uri [System.Web]System.Web.HttpRequest::get_Url()
0x3db3  stelem.ref
0x3db4  dup
0x3db5  ldc.i4.2
0x3db6  ldarg.1
0x3db7  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpApplication::get_Request()
0x3dbc  callvirt instance string [System.Web]System.Web.HttpRequest::get_UserHostAddress()
0x3dc1  stelem.ref
0x3dc2  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3dc7  ldloc.0
0x3dc8  stloc.1
0x3dc9  leave.s  loc_3DDB
0x3dcb  ldc.i4.0
0x3dcc  stloc.1
0x3dcd  leave.s  loc_3DDB
0x3dcf  ldstr    aAuthentication// "AuthenticationStep.Authenticate()"
0x3dd4  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::LogException(class [mscorlib]System.Exception exception, [opt] string context)
0x3dd9  rethrow
0x3ddb  ldloc.1
0x3ddc  ret
```
