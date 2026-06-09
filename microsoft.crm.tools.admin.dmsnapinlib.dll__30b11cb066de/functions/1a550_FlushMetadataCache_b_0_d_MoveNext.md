# <<FlushMetadataCache>b__0>d::MoveNext

- ea: `0x1a550`
- end: `0x1a6a4`
- name: `<<FlushMetadataCache>b__0>d::MoveNext`
- size: `340`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18630`
- `0x18650`
- `0x1a550`

## string_xrefs

- `0x1a580`: `http://localhost:{0}/api/cache/{1}/flush`
- `0x1a634`: `Failed to flush metadata cache in MTPD using {0}`

## pseudocode

```c

```

## disassembly

```asm
0x1a550  ldarg.0
0x1a551  ldfld    int32 <<FlushMetadataCache>b__0>d::<>1__state
0x1a556  stloc.0
0x1a557  ldloc.0
0x1a558  brfalse.s loc_1A565
0x1a55a  ldarg.0
0x1a55b  newobj   instance void [System.Net.Http]System.Net.Http.HttpClient::.ctor()
0x1a560  stfld    class [System.Net.Http]System.Net.Http.HttpClient <<FlushMetadataCache>b__0>d::<httpClient>5__2
0x1a565  nop
0x1a566  ldloc.0
0x1a567  brfalse.s loc_1A5A9
0x1a569  ldarg.0
0x1a56a  ldfld    class [System.Net.Http]System.Net.Http.HttpClient <<FlushMetadataCache>b__0>d::<httpClient>5__2
0x1a56f  call     int32 Microsoft.Crm.Tools.Admin.DMSnapinLib.Organization.PdWebApi.PdWebApiHelper::GetApiTimeout()
0x1a574  conv.r8
0x1a575  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromSeconds(float64)
0x1a57a  callvirt instance void [System.Net.Http]System.Net.Http.HttpClient::set_Timeout(valuetype [mscorlib]System.TimeSpan)
0x1a57f  ldarg.0
0x1a580  ldstr    aHttpLocalhost0_0// "http://localhost:{0}/api/cache/{1}/flus"...
0x1a585  call     int32 Microsoft.Crm.Tools.Admin.DMSnapinLib.Organization.PdWebApi.PdWebApiHelper::GetApiPort()
0x1a58a  box      [mscorlib]System.Int32
0x1a58f  ldarg.0
0x1a590  ldfld    class <>c__DisplayClass6_0 <<FlushMetadataCache>b__0>d::<>4__this
0x1a595  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass6_0::orgId
0x1a59a  box      [mscorlib]System.Guid
0x1a59f  call     string [mscorlib]System.String::Format(string, object, object)
0x1a5a4  stfld    string <<FlushMetadataCache>b__0>d::<url>5__1
0x1a5a9  nop
0x1a5aa  ldloc.0
0x1a5ab  brfalse.s loc_1A5FA
0x1a5ad  ldarg.0
0x1a5ae  ldfld    class [System.Net.Http]System.Net.Http.HttpClient <<FlushMetadataCache>b__0>d::<httpClient>5__2
0x1a5b3  ldarg.0
0x1a5b4  ldfld    string <<FlushMetadataCache>b__0>d::<url>5__1
0x1a5b9  ldnull
0x1a5ba  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> [System.Net.Http]System.Net.Http.HttpClient::PostAsync(string, class [System.Net.Http]System.Net.Http.HttpContent)
0x1a5bf  ldc.i4.0
0x1a5c0  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage>::ConfigureAwait(!!T0)
0x1a5c5  stloc.2
0x1a5c6  ldloca.s 2
0x1a5c8  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage>::GetAwaiter()
0x1a5cd  stloc.1
0x1a5ce  ldloca.s 1
0x1a5d0  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [System.Net.Http]System.Net.Http.HttpResponseMessage>::get_IsCompleted()
0x1a5d5  brtrue.s loc_1A616
0x1a5d7  ldarg.0
0x1a5d8  ldc.i4.0
0x1a5d9  dup
0x1a5da  stloc.0
0x1a5db  stfld    int32 <<FlushMetadataCache>b__0>d::<>1__state
0x1a5e0  ldarg.0
0x1a5e1  ldloc.1
0x1a5e2  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [System.Net.Http]System.Net.Http.HttpResponseMessage> <<FlushMetadataCache>b__0>d::<>u__1
0x1a5e7  ldarg.0
0x1a5e8  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <<FlushMetadataCache>b__0>d::<>t__builder
0x1a5ed  ldloca.s 1
0x1a5ef  ldarg.0
0x1a5f0  call     T0x2B000025
0x1a5f5  leave    loc_1A6A3
0x1a5fa  ldarg.0
0x1a5fb  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [System.Net.Http]System.Net.Http.HttpResponseMessage> <<FlushMetadataCache>b__0>d::<>u__1
0x1a600  stloc.1
0x1a601  ldarg.0
0x1a602  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [System.Net.Http]System.Net.Http.HttpResponseMessage> <<FlushMetadataCache>b__0>d::<>u__1
0x1a607  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [System.Net.Http]System.Net.Http.HttpResponseMessage>
0x1a60d  ldarg.0
0x1a60e  ldc.i4.m1
0x1a60f  dup
0x1a610  stloc.0
0x1a611  stfld    int32 <<FlushMetadataCache>b__0>d::<>1__state
0x1a616  ldloca.s 1
0x1a618  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [System.Net.Http]System.Net.Http.HttpResponseMessage>::GetResult()
0x1a61d  pop
0x1a61e  ldloca.s 1
0x1a620  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [System.Net.Http]System.Net.Http.HttpResponseMessage>
0x1a626  leave.s  loc_1A64F
0x1a628  ldarg.0
0x1a629  ldfld    class <>c__DisplayClass6_0 <<FlushMetadataCache>b__0>d::<>4__this
0x1a62e  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass6_0::orgId
0x1a633  ldc.i4.6
0x1a634  ldstr    aFailedToFlushM// "Failed to flush metadata cache in MTPD "...
0x1a639  ldc.i4.1
0x1a63a  newarr   [mscorlib]System.Object
0x1a63f  dup
0x1a640  ldc.i4.0
0x1a641  ldarg.0
0x1a642  ldfld    string <<FlushMetadataCache>b__0>d::<url>5__1
0x1a647  stelem.ref
0x1a648  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1a64d  leave.s  loc_1A64F
0x1a64f  ldarg.0
0x1a650  ldnull
0x1a651  stfld    string <<FlushMetadataCache>b__0>d::<url>5__1
0x1a656  leave.s  loc_1A670
0x1a658  ldloc.0
0x1a659  ldc.i4.0
0x1a65a  bge.s    loc_1A66F
0x1a65c  ldarg.0
0x1a65d  ldfld    class [System.Net.Http]System.Net.Http.HttpClient <<FlushMetadataCache>b__0>d::<httpClient>5__2
0x1a662  brfalse.s loc_1A66F
0x1a664  ldarg.0
0x1a665  ldfld    class [System.Net.Http]System.Net.Http.HttpClient <<FlushMetadataCache>b__0>d::<httpClient>5__2
0x1a66a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1a66f  endfinally
0x1a670  ldarg.0
0x1a671  ldnull
0x1a672  stfld    class [System.Net.Http]System.Net.Http.HttpClient <<FlushMetadataCache>b__0>d::<httpClient>5__2
0x1a677  leave.s  loc_1A690
0x1a679  stloc.3
0x1a67a  ldarg.0
0x1a67b  ldc.i4.s 0xFE
0x1a67d  stfld    int32 <<FlushMetadataCache>b__0>d::<>1__state
0x1a682  ldarg.0
0x1a683  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <<FlushMetadataCache>b__0>d::<>t__builder
0x1a688  ldloc.3
0x1a689  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetException(class [mscorlib]System.Exception)
0x1a68e  leave.s  loc_1A6A3
0x1a690  ldarg.0
0x1a691  ldc.i4.s 0xFE
0x1a693  stfld    int32 <<FlushMetadataCache>b__0>d::<>1__state
0x1a698  ldarg.0
0x1a699  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <<FlushMetadataCache>b__0>d::<>t__builder
0x1a69e  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetResult()
0x1a6a3  ret
```
