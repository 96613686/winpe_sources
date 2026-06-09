# Microsoft.Crm.Core.DataServices.Connection.CrmAccessTokenRetriever::AcquireTokenFromAuthority

- ea: `0x5a980`
- end: `0x5ab0c`
- name: `Microsoft.Crm.Core.DataServices.Connection.CrmAccessTokenRetriever::AcquireTokenFromAuthority`
- size: `396`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x5a910`
- `0x5a980`
- `0x5abc0`

## callees

- `0x1a890`
- `0x5a950`
- `0x5a980`
- `0x5ab10`
- `0x5ac70`
- `0x5acb0`
- `0x5acf0`
- `0x5ad30`
- `0x5ad80`
- `0x5b590`

## string_xrefs

- `0x5a9d3`: `Exception attempting to retrieve AAD token, will retry with context refresh : `
- `0x5aa1e`: `Exception when attempting to retrieve Azure Authentication Token: `

## pseudocode

```c

```

## disassembly

```asm
0x5a980  ldnull
0x5a981  stloc.0
0x5a982  call     class [System]System.Diagnostics.Stopwatch [System]System.Diagnostics.Stopwatch::StartNew()
0x5a987  stloc.1
0x5a988  ldarg.1
0x5a989  brfalse.s loc_5A991
0x5a98b  ldarg.0
0x5a98c  call     instance void Microsoft.Crm.Core.DataServices.Connection.CrmAccessTokenRetriever::InitializeAuthenticationContext()
0x5a991  nop
0x5a992  ldarg.0
0x5a993  ldfld    class [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.AuthenticationContext Microsoft.Crm.Core.DataServices.Connection.CrmAccessTokenRetriever::_authenticationContext
0x5a998  callvirt instance class [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.TokenCache [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.AuthenticationContext::get_TokenCache()
0x5a99d  callvirt instance void [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.TokenCache::Clear()
0x5a9a2  ldarg.0
0x5a9a3  call     instance class Microsoft.Crm.Authentication.Azure.AuthenticationToken Microsoft.Crm.Core.DataServices.Connection.CrmAccessTokenRetriever::AcquireAuthenticationTokenFromTokenSource()
0x5a9a8  stloc.0
0x5a9a9  leave    loc_5AB08
0x5a9ae  stloc.2
0x5a9af  ldarg.1
0x5a9b0  brtrue.s loc_5A9FD
0x5a9b2  call     class Microsoft.Crm.Core.DataServices.Connection.CrmConnectionInfoEventSource Microsoft.Crm.Core.DataServices.Connection.CrmConnectionInfoEventSource::get_Instance()
0x5a9b7  ldarg.0
0x5a9b8  ldfld    class Microsoft.Crm.Core.DataServices.Connection.CrmAuthenticationDetails Microsoft.Crm.Core.DataServices.Connection.CrmAccessTokenRetriever::_authenticationDetails
0x5a9bd  callvirt instance string Microsoft.Crm.Core.DataServices.Connection.CrmAuthenticationDetails::get_Resource()
0x5a9c2  ldarg.0
0x5a9c3  ldfld    class Microsoft.Crm.Core.DataServices.Connection.CrmAuthenticationDetails Microsoft.Crm.Core.DataServices.Connection.CrmAccessTokenRetriever::_authenticationDetails
0x5a9c8  callvirt instance string Microsoft.Crm.Core.DataServices.Connection.CrmAuthenticationDetails::get_Authority()
0x5a9cd  ldloc.1
0x5a9ce  callvirt instance int64 [System]System.Diagnostics.Stopwatch::get_ElapsedMilliseconds()
0x5a9d3  ldstr    aExceptionAttem// "Exception attempting to retrieve AAD to"...
0x5a9d8  ldloc.2
0x5a9d9  callvirt instance string [mscorlib]System.Exception::get_Message()
0x5a9de  call     string [mscorlib]System.String::Concat(string, string)
0x5a9e3  ldloc.2
0x5a9e4  callvirt instance string [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.AdalException::get_ErrorCode()
0x5a9e9  callvirt instance void Microsoft.Crm.Core.DataServices.Connection.CrmConnectionInfoEventSource::AcquireTokenFromAuthorityInfo(string resource, string authority, int64 elapsedMilliseconds, string message, string errorCode)
0x5a9ee  ldarg.0
0x5a9ef  ldc.i4.1
0x5a9f0  call     instance class Microsoft.Crm.Authentication.Azure.AuthenticationToken Microsoft.Crm.Core.DataServices.Connection.CrmAccessTokenRetriever::AcquireTokenFromAuthority([opt] bool refreshContext)
0x5a9f5  stloc.0
0x5a9f6  ldloc.0
0x5a9f7  stloc.3
0x5a9f8  leave    loc_5AB0A
0x5a9fd  call     class Microsoft.Crm.Core.DataServices.Connection.CrmConnectionInfoEventSource Microsoft.Crm.Core.DataServices.Connection.CrmConnectionInfoEventSource::get_Instance()
0x5aa02  ldarg.0
0x5aa03  ldfld    class Microsoft.Crm.Core.DataServices.Connection.CrmAuthenticationDetails Microsoft.Crm.Core.DataServices.Connection.CrmAccessTokenRetriever::_authenticationDetails
0x5aa08  callvirt instance string Microsoft.Crm.Core.DataServices.Connection.CrmAuthenticationDetails::get_Resource()
0x5aa0d  ldarg.0
0x5aa0e  ldfld    class Microsoft.Crm.Core.DataServices.Connection.CrmAuthenticationDetails Microsoft.Crm.Core.DataServices.Connection.CrmAccessTokenRetriever::_authenticationDetails
0x5aa13  callvirt instance string Microsoft.Crm.Core.DataServices.Connection.CrmAuthenticationDetails::get_Authority()
0x5aa18  ldloc.1
0x5aa19  callvirt instance int64 [System]System.Diagnostics.Stopwatch::get_ElapsedMilliseconds()
0x5aa1e  ldstr    aExceptionWhenA_1// "Exception when attempting to retrieve A"...
0x5aa23  ldloc.2
0x5aa24  callvirt instance string [mscorlib]System.Exception::get_Message()
0x5aa29  ldstr    aInnerexception_2// ", innerException: "
0x5aa2e  ldloc.2
0x5aa2f  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0x5aa34  dup
0x5aa35  brtrue.s loc_5AA3B
0x5aa37  pop
0x5aa38  ldnull
0x5aa39  br.s     loc_5AA40
0x5aa3b  callvirt instance string [mscorlib]System.Exception::get_Message()
0x5aa40  dup
0x5aa41  brtrue.s loc_5AA49
0x5aa43  pop
0x5aa44  ldstr    aNull_0// "null"
0x5aa49  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x5aa4e  ldloc.2
0x5aa4f  callvirt instance string [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.AdalException::get_ErrorCode()
0x5aa54  callvirt instance void Microsoft.Crm.Core.DataServices.Connection.CrmConnectionInfoEventSource::AcquireTokenFromAuthorityError(string resource, string authority, int64 elapsedMilliseconds, string message, string errorCode)
0x5aa59  ldloc.2
0x5aa5a  callvirt instance string [mscorlib]System.Exception::get_Message()
0x5aa5f  ldloc.2
0x5aa60  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0x5aa65  newobj   instance void Microsoft.Crm.CrmException::.ctor(string message, class [mscorlib]System.Exception innerException)
0x5aa6a  throw
0x5aa6b  stloc.s  4
0x5aa6d  call     class Microsoft.Crm.Core.DataServices.Connection.CrmConnectionInfoEventSource Microsoft.Crm.Core.DataServices.Connection.CrmConnectionInfoEventSource::get_Instance()
0x5aa72  ldarg.0
0x5aa73  ldfld    class Microsoft.Crm.Core.DataServices.Connection.CrmAuthenticationDetails Microsoft.Crm.Core.DataServices.Connection.CrmAccessTokenRetriever::_authenticationDetails
0x5aa78  callvirt instance string Microsoft.Crm.Core.DataServices.Connection.CrmAuthenticationDetails::get_Resource()
0x5aa7d  ldarg.0
0x5aa7e  ldfld    class Microsoft.Crm.Core.DataServices.Connection.CrmAuthenticationDetails Microsoft.Crm.Core.DataServices.Connection.CrmAccessTokenRetriever::_authenticationDetails
0x5aa83  callvirt instance string Microsoft.Crm.Core.DataServices.Connection.CrmAuthenticationDetails::get_Authority()
0x5aa88  ldloc.1
0x5aa89  callvirt instance int64 [System]System.Diagnostics.Stopwatch::get_ElapsedMilliseconds()
0x5aa8e  ldloc.s  4
0x5aa90  callvirt instance string [mscorlib]System.Object::ToString()
0x5aa95  ldsfld   string [mscorlib]System.String::Empty
0x5aa9a  callvirt instance void Microsoft.Crm.Core.DataServices.Connection.CrmConnectionInfoEventSource::AcquireTokenFromAuthorityError(string resource, string authority, int64 elapsedMilliseconds, string message, string errorCode)
0x5aa9f  rethrow
0x5aaa1  ldloc.0
0x5aaa2  brtrue.s loc_5AAC0
0x5aaa4  ldarg.0
0x5aaa5  ldfld    class Microsoft.Crm.Core.DataServices.Connection.CrmTokenRefreshScheduler Microsoft.Crm.Core.DataServices.Connection.CrmAccessTokenRetriever::_tokenRefreshScheduler
0x5aaaa  ldarg.0
0x5aaab  ldfld    class Microsoft.Crm.Authentication.Azure.AuthenticationToken[] Microsoft.Crm.Core.DataServices.Connection.CrmAccessTokenRetriever::_cachedTokens
0x5aab0  ldarg.0
0x5aab1  volatile.
0x5aab3  ldfld    modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) int32 Microsoft.Crm.Core.DataServices.Connection.CrmAccessTokenRetriever::_cachedTokenIdx
0x5aab8  ldelem.ref
0x5aab9  callvirt instance int64 Microsoft.Crm.Core.DataServices.Connection.CrmTokenRefreshScheduler::GetNextTokenRefreshTimeInSeconds(class Microsoft.Crm.Authentication.Azure.AuthenticationToken token)
0x5aabe  br.s     loc_5AACC
0x5aac0  ldarg.0
0x5aac1  ldfld    class Microsoft.Crm.Core.DataServices.Connection.CrmTokenRefreshScheduler Microsoft.Crm.Core.DataServices.Connection.CrmAccessTokenRetriever::_tokenRefreshScheduler
0x5aac6  ldloc.0
0x5aac7  callvirt instance int64 Microsoft.Crm.Core.DataServices.Connection.CrmTokenRefreshScheduler::GetNextTokenRefreshTimeInSeconds(class Microsoft.Crm.Authentication.Azure.AuthenticationToken token)
0x5aacc  stloc.s  5
0x5aace  ldarg.1
0x5aacf  brtrue.s loc_5AB07
0x5aad1  ldarg.0
0x5aad2  ldfld    class [mscorlib]System.Threading.Timer Microsoft.Crm.Core.DataServices.Connection.CrmAccessTokenRetriever::_updateAuthTokenTimer
0x5aad7  brfalse.s loc_5AAE4
0x5aad9  ldarg.0
0x5aada  ldfld    class [mscorlib]System.Threading.Timer Microsoft.Crm.Core.DataServices.Connection.CrmAccessTokenRetriever::_updateAuthTokenTimer
0x5aadf  callvirt instance void [mscorlib]System.Threading.Timer::Dispose()
0x5aae4  ldarg.0
0x5aae5  ldarg.0
0x5aae6  ldftn    instance void Microsoft.Crm.Core.DataServices.Connection.CrmAccessTokenRetriever::<AcquireTokenFromAuthority>b__17_0(object x)
0x5aaec  newobj   instance void [mscorlib]System.Threading.TimerCallback::.ctor(object, native int)
0x5aaf1  ldnull
0x5aaf2  ldloc.s  5
0x5aaf4  ldc.i4   0x3E8
0x5aaf9  conv.i8
0x5aafa  mul
0x5aafb  ldc.i4.m1
0x5aafc  conv.i8
0x5aafd  newobj   instance void [mscorlib]System.Threading.Timer::.ctor(class [mscorlib]System.Threading.TimerCallback, object, int64, int64)
0x5ab02  stfld    class [mscorlib]System.Threading.Timer Microsoft.Crm.Core.DataServices.Connection.CrmAccessTokenRetriever::_updateAuthTokenTimer
0x5ab07  endfinally
0x5ab08  ldloc.0
0x5ab09  ret
0x5ab0a  ldloc.3
0x5ab0b  ret
```
