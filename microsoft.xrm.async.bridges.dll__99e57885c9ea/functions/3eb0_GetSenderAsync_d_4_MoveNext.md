# <GetSenderAsync>d__4::MoveNext

- ea: `0x3eb0`
- end: `0x4040`
- name: `<GetSenderAsync>d__4::MoveNext`
- size: `400`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x1080`
- `0x1fb0`
- `0x1fc0`
- `0x1fd0`
- `0x2090`
- `0x23b0`
- `0x2990`
- `0x3eb0`

## pseudocode

```c

```

## disassembly

```asm
0x3eb0  ldarg.0
0x3eb1  ldfld    int32 <GetSenderAsync>d__4::<>1__state
0x3eb6  stloc.0
0x3eb7  ldloc.0
0x3eb8  brfalse.s loc_3EBC
0x3eba  ldnull
0x3ebb  stloc.2
0x3ebc  nop
0x3ebd  ldloc.0
0x3ebe  brfalse  loc_3F51
0x3ec3  ldarg.0
0x3ec4  ldflda   valuetype Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.SenderOptions <GetSenderAsync>d__4::senderOptions
0x3ec9  call     instance class [System]System.Uri Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.SenderOptions::get_AudienceUri()
0x3ece  ldnull
0x3ecf  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0x3ed4  brfalse  loc_3FA2
0x3ed9  ldarg.0
0x3eda  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.AuthenticatedHttpSenderFactory <GetSenderAsync>d__4::<>4__this
0x3edf  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.IAuthProviderEvents Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.AuthenticatedHttpSenderFactory::events
0x3ee4  ldarg.0
0x3ee5  ldflda   valuetype Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.SenderOptions <GetSenderAsync>d__4::senderOptions
0x3eea  call     instance class [System]System.Uri Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.SenderOptions::get_AudienceUri()
0x3eef  ldstr    aAuthenticatedh// "AuthenticatedHttpSenderFactory"
0x3ef4  callvirt instance void Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.IAuthProviderEvents::OnBeginGetAuthProvider(class [System]System.Uri audienceUri, string callerType)
0x3ef9  ldarg.0
0x3efa  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.AuthenticatedHttpSenderFactory <GetSenderAsync>d__4::<>4__this
0x3eff  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommonAuth.IOAuthTokenProviderFactory Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.AuthenticatedHttpSenderFactory::tokenProviderFactory
0x3f04  ldarg.0
0x3f05  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.AuthenticatedHttpSenderFactory <GetSenderAsync>d__4::<>4__this
0x3f0a  ldfld    string Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.AuthenticatedHttpSenderFactory::connectionStringSecretKey
0x3f0f  ldarg.0
0x3f10  ldflda   valuetype Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.SenderOptions <GetSenderAsync>d__4::senderOptions
0x3f15  call     instance class [System]System.Uri Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.SenderOptions::get_AudienceUri()
0x3f1a  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class Microsoft.Xrm.Async.Bridges.FromCommonAuth.IAuthProvider> Microsoft.Xrm.Async.Bridges.FromCommonAuth.IOAuthTokenProviderFactory::CreateAsync(string connectionStringKey, [opt] class [System]System.Uri audienceUri)
0x3f1f  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class Microsoft.Xrm.Async.Bridges.FromCommonAuth.IAuthProvider>::GetAwaiter()
0x3f24  stloc.3
0x3f25  ldloca.s 3
0x3f27  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class Microsoft.Xrm.Async.Bridges.FromCommonAuth.IAuthProvider>::get_IsCompleted()
0x3f2c  brtrue.s loc_3F6D
0x3f2e  ldarg.0
0x3f2f  ldc.i4.0
0x3f30  dup
0x3f31  stloc.0
0x3f32  stfld    int32 <GetSenderAsync>d__4::<>1__state
0x3f37  ldarg.0
0x3f38  ldloc.3
0x3f39  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class Microsoft.Xrm.Async.Bridges.FromCommonAuth.IAuthProvider> <GetSenderAsync>d__4::<>u__1
0x3f3e  ldarg.0
0x3f3f  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpMessageInvoker> <GetSenderAsync>d__4::<>t__builder
0x3f44  ldloca.s 3
0x3f46  ldarg.0
0x3f47  call     T0x2B000084
0x3f4c  leave    loc_403F
0x3f51  ldarg.0
0x3f52  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class Microsoft.Xrm.Async.Bridges.FromCommonAuth.IAuthProvider> <GetSenderAsync>d__4::<>u__1
0x3f57  stloc.3
0x3f58  ldarg.0
0x3f59  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class Microsoft.Xrm.Async.Bridges.FromCommonAuth.IAuthProvider> <GetSenderAsync>d__4::<>u__1
0x3f5e  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class Microsoft.Xrm.Async.Bridges.FromCommonAuth.IAuthProvider>
0x3f64  ldarg.0
0x3f65  ldc.i4.m1
0x3f66  dup
0x3f67  stloc.0
0x3f68  stfld    int32 <GetSenderAsync>d__4::<>1__state
0x3f6d  ldloca.s 3
0x3f6f  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class Microsoft.Xrm.Async.Bridges.FromCommonAuth.IAuthProvider>::GetResult()
0x3f74  ldloca.s 3
0x3f76  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class Microsoft.Xrm.Async.Bridges.FromCommonAuth.IAuthProvider>
0x3f7c  newobj   instance void Microsoft.Xrm.Async.Bridges.FromCommonAuth.AuthenticatingHandler::.ctor(class Microsoft.Xrm.Async.Bridges.FromCommonAuth.IAuthProvider authProvider)
0x3f81  stloc.2
0x3f82  ldarg.0
0x3f83  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.AuthenticatedHttpSenderFactory <GetSenderAsync>d__4::<>4__this
0x3f88  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.IAuthProviderEvents Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.AuthenticatedHttpSenderFactory::events
0x3f8d  ldarg.0
0x3f8e  ldflda   valuetype Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.SenderOptions <GetSenderAsync>d__4::senderOptions
0x3f93  call     instance class [System]System.Uri Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.SenderOptions::get_AudienceUri()
0x3f98  ldstr    aAuthenticatedh// "AuthenticatedHttpSenderFactory"
0x3f9d  callvirt instance void Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.IAuthProviderEvents::OnCompleteGetAuthProvider(class [System]System.Uri audienceUri, string callerType)
0x3fa2  ldloc.2
0x3fa3  brfalse.s loc_3FAD
0x3fa5  ldloc.2
0x3fa6  newobj   instance void [System.Net.Http]System.Net.Http.HttpClient::.ctor(class [System.Net.Http]System.Net.Http.HttpMessageHandler)
0x3fab  br.s     loc_3FB2
0x3fad  newobj   instance void [System.Net.Http]System.Net.Http.HttpClient::.ctor()
0x3fb2  stloc.1
0x3fb3  leave.s  loc_402B
0x3fb5  isinst   [mscorlib]System.Exception
0x3fba  dup
0x3fbb  brtrue.s loc_3FC1
0x3fbd  pop
0x3fbe  ldc.i4.0
0x3fbf  br.s     loc_3FE8
0x3fc1  stloc.s  4
0x3fc3  ldarg.0
0x3fc4  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.AuthenticatedHttpSenderFactory <GetSenderAsync>d__4::<>4__this
0x3fc9  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.IAuthProviderEvents Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.AuthenticatedHttpSenderFactory::events
0x3fce  ldstr    aAuthenticatedh// "AuthenticatedHttpSenderFactory"
0x3fd3  ldarg.0
0x3fd4  ldflda   valuetype Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.SenderOptions <GetSenderAsync>d__4::senderOptions
0x3fd9  call     instance class [System]System.Uri Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.SenderOptions::get_AudienceUri()
0x3fde  ldloc.s  4
0x3fe0  callvirt instance bool Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.IAuthProviderEvents::OnFailedGetAuthProvider(string callerType, class [System]System.Uri audienceUri, class [mscorlib]System.Exception exception)
0x3fe5  ldc.i4.0
0x3fe6  cgt.un
0x3fe8  endfilter
0x3fea  pop
0x3feb  ldarg.0
0x3fec  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.AuthenticatedHttpSenderFactory <GetSenderAsync>d__4::<>4__this
0x3ff1  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.IAuthProviderEvents Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.AuthenticatedHttpSenderFactory::events
0x3ff6  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3ffb  callvirt instance string [mscorlib]System.Type::get_FullName()
0x4000  ldstr    aOnfailedgetaut// ".OnFailedGetAuthProvider"
0x4005  call     string [mscorlib]System.String::Concat(string, string)
0x400a  ldloc.s  4
0x400c  newobj   instance void Microsoft.Xrm.Async.Bridges.FromCommon.ExceptionFilterContractViolationException::.ctor(string filterMemberFullName, class [mscorlib]System.Exception innerException)
0x4011  throw
0x4012  stloc.s  5
0x4014  ldarg.0
0x4015  ldc.i4.s 0xFE
0x4017  stfld    int32 <GetSenderAsync>d__4::<>1__state
0x401c  ldarg.0
0x401d  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpMessageInvoker> <GetSenderAsync>d__4::<>t__builder
0x4022  ldloc.s  5
0x4024  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpMessageInvoker>::SetException(class [mscorlib]System.Exception)
0x4029  leave.s  loc_403F
0x402b  ldarg.0
0x402c  ldc.i4.s 0xFE
0x402e  stfld    int32 <GetSenderAsync>d__4::<>1__state
0x4033  ldarg.0
0x4034  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpMessageInvoker> <GetSenderAsync>d__4::<>t__builder
0x4039  ldloc.1
0x403a  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpMessageInvoker>::SetResult(var<u1>)
0x403f  ret
```
