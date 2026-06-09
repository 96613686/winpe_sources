# <<SendAsync>b__0>d::MoveNext

- ea: `0x35330`
- end: `0x3553d`
- name: `<<SendAsync>b__0>d::MoveNext`
- size: `525`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x191d0`
- `0x24e60`
- `0x287b0`
- `0x28830`
- `0x288b0`
- `0x35330`

## string_xrefs

- `0x3542e`: `Cache-Control`
- `0x3546c`: `Access-Control-Allow-Origin`

## pseudocode

```c

```

## disassembly

```asm
0x35330  ldarg.0
0x35331  ldfld    int32 <<SendAsync>b__0>d::<>1__state
0x35336  stloc.0
0x35337  ldarg.0
0x35338  ldfld    class <>c__DisplayClass1_0 <<SendAsync>b__0>d::<>4__this
0x3533d  stloc.1
0x3533e  ldloc.0
0x3533f  brfalse.s loc_3539D
0x35341  ldloc.1
0x35342  ldfld    class Microsoft.Crm.Extensibility.ODataV4.CrmDelegatingHandler <>c__DisplayClass1_0::<>4__this
0x35347  ldloc.1
0x35348  ldfld    class [System.Net.Http]System.Net.Http.HttpRequestMessage <>c__DisplayClass1_0::request
0x3534d  call     instance void Microsoft.Crm.Extensibility.ODataV4.CrmDelegatingHandler::AddRequestInfoToTelemetry(class [System.Net.Http]System.Net.Http.HttpRequestMessage request)
0x35352  ldloc.1
0x35353  ldfld    class Microsoft.Crm.Extensibility.ODataV4.CrmDelegatingHandler <>c__DisplayClass1_0::<>4__this
0x35358  ldloc.1
0x35359  ldfld    class [System.Net.Http]System.Net.Http.HttpRequestMessage <>c__DisplayClass1_0::request
0x3535e  ldloc.1
0x3535f  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <>c__DisplayClass1_0::cancellationToken
0x35364  call     instance class [mscorlib]System.Threading.Tasks.Task`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> Microsoft.Crm.Extensibility.ODataV4.CrmDelegatingHandler::<>n__0(class [System.Net.Http]System.Net.Http.HttpRequestMessage request, valuetype [mscorlib]System.Threading.CancellationToken cancellationToken)
0x35369  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage>::GetAwaiter()
0x3536e  stloc.s  6
0x35370  ldloca.s 6
0x35372  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage>::get_IsCompleted()
0x35377  brtrue.s loc_353BA
0x35379  ldarg.0
0x3537a  ldc.i4.0
0x3537b  dup
0x3537c  stloc.0
0x3537d  stfld    int32 <<SendAsync>b__0>d::<>1__state
0x35382  ldarg.0
0x35383  ldloc.s  6
0x35385  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> <<SendAsync>b__0>d::<>u__1
0x3538a  ldarg.0
0x3538b  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> <<SendAsync>b__0>d::<>t__builder
0x35390  ldloca.s 6
0x35392  ldarg.0
0x35393  call     T0x2B000149
0x35398  leave    loc_3553C
0x3539d  ldarg.0
0x3539e  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> <<SendAsync>b__0>d::<>u__1
0x353a3  stloc.s  6
0x353a5  ldarg.0
0x353a6  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> <<SendAsync>b__0>d::<>u__1
0x353ab  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage>
0x353b1  ldarg.0
0x353b2  ldc.i4.m1
0x353b3  dup
0x353b4  stloc.0
0x353b5  stfld    int32 <<SendAsync>b__0>d::<>1__state
0x353ba  ldloca.s 6
0x353bc  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage>::GetResult()
0x353c1  stloc.3
0x353c2  ldloc.1
0x353c3  ldfld    class [System.Net.Http]System.Net.Http.HttpRequestMessage <>c__DisplayClass1_0::request
0x353c8  callvirt instance class [System]System.Uri [System.Net.Http]System.Net.Http.HttpRequestMessage::get_RequestUri()
0x353cd  callvirt instance string [System]System.Uri::get_Query()
0x353d2  stloc.s  4
0x353d4  ldloc.s  4
0x353d6  ldstr    aClientmetadata// "@ClientMetadataQuery"
0x353db  callvirt instance bool [mscorlib]System.String::Contains(string)
0x353e0  brfalse.s loc_3543D
0x353e2  ldloc.s  4
0x353e4  ldstr    a22metadatatype// "%22MetadataType%22:%22metadataversion%2"...
0x353e9  callvirt instance bool [mscorlib]System.String::Contains(string)
0x353ee  brtrue.s loc_3543D
0x353f0  ldloc.s  4
0x353f2  ldstr    aUmv// "&umv="
0x353f7  callvirt instance bool [mscorlib]System.String::Contains(string)
0x353fc  brfalse.s loc_3543D
0x353fe  ldloc.s  4
0x35400  ldstr    aUmv1// "&umv=-1"
0x35405  callvirt instance bool [mscorlib]System.String::Contains(string)
0x3540a  brtrue.s loc_3543D
0x3540c  ldloc.s  4
0x3540e  ldstr    aMv// "&mv="
0x35413  callvirt instance bool [mscorlib]System.String::Contains(string)
0x35418  brfalse.s loc_3543D
0x3541a  ldloc.s  4
0x3541c  ldstr    aMv1// "&mv=-1"
0x35421  callvirt instance bool [mscorlib]System.String::Contains(string)
0x35426  brtrue.s loc_3543D
0x35428  ldloc.3
0x35429  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpResponseHeaders [System.Net.Http]System.Net.Http.HttpResponseMessage::get_Headers()
0x3542e  ldstr    aCacheControl// "Cache-Control"
0x35433  ldstr    aPrivateMaxAge3// "private,max-age=31536000"
0x35438  callvirt instance void [System.Net.Http]System.Net.Http.Headers.HttpHeaders::Add(string, string)
0x3543d  ldloc.1
0x3543e  ldfld    class [System.Net.Http]System.Net.Http.HttpRequestMessage <>c__DisplayClass1_0::request
0x35443  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpRequestHeaders [System.Net.Http]System.Net.Http.HttpRequestMessage::get_Headers()
0x35448  callvirt instance class [System.Net.Http]System.Net.Http.Headers.AuthenticationHeaderValue [System.Net.Http]System.Net.Http.Headers.HttpRequestHeaders::get_Authorization()
0x3544d  stloc.s  5
0x3544f  ldloc.s  5
0x35451  brfalse.s loc_35466
0x35453  ldloc.s  5
0x35455  callvirt instance string [System.Net.Http]System.Net.Http.Headers.AuthenticationHeaderValue::get_Scheme()
0x3545a  ldstr    aBearer// "Bearer"
0x3545f  callvirt instance bool [mscorlib]System.String::Contains(string)
0x35464  brtrue.s loc_35477
0x35466  ldloc.3
0x35467  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpResponseHeaders [System.Net.Http]System.Net.Http.HttpResponseMessage::get_Headers()
0x3546c  ldstr    aAccessControlA// "Access-Control-Allow-Origin"
0x35471  callvirt instance bool [System.Net.Http]System.Net.Http.Headers.HttpHeaders::Remove(string)
0x35476  pop
0x35477  ldloc.3
0x35478  callvirt instance bool [System.Net.Http]System.Net.Http.HttpResponseMessage::get_IsSuccessStatusCode()
0x3547d  brfalse  loc_35505
0x35482  ldloc.1
0x35483  ldfld    class [System.Net.Http]System.Net.Http.HttpRequestMessage <>c__DisplayClass1_0::request
0x35488  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpRequestHeaders [System.Net.Http]System.Net.Http.HttpRequestMessage::get_Headers()
0x3548d  ldstr    aPrefer// "Prefer"
0x35492  ldloca.s 7
0x35494  callvirt instance bool [System.Net.Http]System.Net.Http.Headers.HttpHeaders::TryGetValues(string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>&)
0x35499  brfalse.s loc_35505
0x3549b  ldloc.1
0x3549c  ldfld    class [System.Net.Http]System.Net.Http.HttpRequestMessage <>c__DisplayClass1_0::request
0x354a1  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> [System.Net.Http]System.Net.Http.HttpRequestMessage::get_Properties()
0x354a6  ldstr    aCrmodatacontex// "CrmODataContext"
0x354ab  ldloca.s 8
0x354ad  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::TryGetValue(var<u1>, !!T0)
0x354b2  brfalse.s loc_35505
0x354b4  ldloc.3
0x354b5  callvirt instance class [System.Net.Http]System.Net.Http.HttpContent [System.Net.Http]System.Net.Http.HttpResponseMessage::get_Content()
0x354ba  brfalse.s loc_354E4
0x354bc  ldloc.3
0x354bd  callvirt instance class [System.Net.Http]System.Net.Http.HttpContent [System.Net.Http]System.Net.Http.HttpResponseMessage::get_Content()
0x354c2  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders [System.Net.Http]System.Net.Http.HttpContent::get_Headers()
0x354c7  ldstr    aPreferenceAppl_0// "Preference-Applied"
0x354cc  ldloc.s  8
0x354ce  castclass Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext
0x354d3  callvirt instance class Microsoft.Crm.Extensibility.OData.CrmODataHeaders Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_Headers()
0x354d8  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.Crm.Extensibility.OData.CrmODataHeaders::get_PreferencesApplied()
0x354dd  callvirt instance void [System.Net.Http]System.Net.Http.Headers.HttpHeaders::Add(string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>)
0x354e2  br.s     loc_35505
0x354e4  ldloc.3
0x354e5  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpResponseHeaders [System.Net.Http]System.Net.Http.HttpResponseMessage::get_Headers()
0x354ea  ldstr    aPreferenceAppl_0// "Preference-Applied"
0x354ef  ldloc.s  8
0x354f1  castclass Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext
0x354f6  callvirt instance class Microsoft.Crm.Extensibility.OData.CrmODataHeaders Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_Headers()
0x354fb  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.Crm.Extensibility.OData.CrmODataHeaders::get_PreferencesApplied()
0x35500  callvirt instance void [System.Net.Http]System.Net.Http.Headers.HttpHeaders::Add(string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>)
0x35505  ldloc.3
0x35506  call     void Microsoft.Crm.Extensibility.ODataV4.CrmDelegatingHandler::AddResponseInfoToTelemetry(class [System.Net.Http]System.Net.Http.HttpResponseMessage responseMessage)
0x3550b  ldloc.3
0x3550c  stloc.2
0x3550d  leave.s  loc_35528
0x3550f  stloc.s  9
0x35511  ldarg.0
0x35512  ldc.i4.s 0xFE
0x35514  stfld    int32 <<SendAsync>b__0>d::<>1__state
0x35519  ldarg.0
0x3551a  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> <<SendAsync>b__0>d::<>t__builder
0x3551f  ldloc.s  9
0x35521  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage>::SetException(class [mscorlib]System.Exception)
0x35526  leave.s  loc_3553C
0x35528  ldarg.0
0x35529  ldc.i4.s 0xFE
0x3552b  stfld    int32 <<SendAsync>b__0>d::<>1__state
0x35530  ldarg.0
0x35531  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> <<SendAsync>b__0>d::<>t__builder
0x35536  ldloc.2
0x35537  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage>::SetResult(var<u1>)
0x3553c  ret
```
