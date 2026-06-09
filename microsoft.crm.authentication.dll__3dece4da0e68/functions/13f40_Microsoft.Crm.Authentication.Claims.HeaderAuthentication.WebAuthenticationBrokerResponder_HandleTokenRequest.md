# Microsoft.Crm.Authentication.Claims.HeaderAuthentication.WebAuthenticationBrokerResponder::HandleTokenRequest

- ea: `0x13f40`
- end: `0x14051`
- name: `Microsoft.Crm.Authentication.Claims.HeaderAuthentication.WebAuthenticationBrokerResponder::HandleTokenRequest`
- size: `273`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0xcc40`

## callees

- `0x7d90`
- `0x13e50`
- `0x13f40`

## pseudocode

```c

```

## disassembly

```asm
0x13f40  ldarg.0
0x13f41  call     bool Microsoft.Crm.Authentication.Common.AuthenticationContextExtensions::IsWabRequest(class [System.Web]System.Web.HttpContext context)
0x13f46  brtrue.s loc_13F4A
0x13f48  ldc.i4.0
0x13f49  ret
0x13f4a  ldsfld   string [mscorlib]System.String::Empty
0x13f4f  stloc.0
0x13f50  ldarg.0
0x13f51  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x13f56  ldstr    aWctx// "wctx"
0x13f5b  callvirt instance string [System.Web]System.Web.HttpRequest::get_Item(string)
0x13f60  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x13f65  brtrue.s loc_13F7D
0x13f67  ldarg.0
0x13f68  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x13f6d  ldstr    aWctx// "wctx"
0x13f72  callvirt instance string [System.Web]System.Web.HttpRequest::get_Item(string)
0x13f77  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmUrlDecode(string)
0x13f7c  stloc.0
0x13f7d  ldloc.0
0x13f7e  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x13f83  brfalse.s loc_13F87
0x13f85  ldc.i4.0
0x13f86  ret
0x13f87  ldloc.0
0x13f88  call     class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpUtility::ParseQueryString(string)
0x13f8d  stloc.1
0x13f8e  ldloc.1
0x13f8f  callvirt instance class [System]System.Collections.Specialized.NameObjectCollectionBase/KeysCollection [System]System.Collections.Specialized.NameObjectCollectionBase::get_Keys()
0x13f94  callvirt instance class [mscorlib]System.Collections.IEnumerator [System]System.Collections.Specialized.NameObjectCollectionBase/KeysCollection::GetEnumerator()
0x13f99  stloc.s  4
0x13f9b  br.s     loc_13FBA
0x13f9d  ldloc.s  4
0x13f9f  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x13fa4  castclass [mscorlib]System.String
0x13fa9  stloc.s  5
0x13fab  ldloc.s  5
0x13fad  brtrue.s loc_13FBA
0x13faf  ldloc.1
0x13fb0  ldloc.s  5
0x13fb2  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x13fb7  stloc.0
0x13fb8  leave.s  loc_13FDA
0x13fba  ldloc.s  4
0x13fbc  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x13fc1  brtrue.s loc_13F9D
0x13fc3  leave.s  loc_13FDA
0x13fc5  ldloc.s  4
0x13fc7  isinst   [mscorlib]System.IDisposable
0x13fcc  stloc.s  6
0x13fce  ldloc.s  6
0x13fd0  brfalse.s loc_13FD9
0x13fd2  ldloc.s  6
0x13fd4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x13fd9  endfinally
0x13fda  ldloc.0
0x13fdb  ldc.i4.1
0x13fdc  newarr   [mscorlib]System.String
0x13fe1  dup
0x13fe2  ldc.i4.0
0x13fe3  ldstr    asc_1636A// ";"
0x13fe8  stelem.ref
0x13fe9  ldc.i4.1
0x13fea  callvirt instance string[] [mscorlib]System.String::Split(string[], valuetype [mscorlib]System.StringSplitOptions)
0x13fef  ldc.i4.0
0x13ff0  ldelem.ref
0x13ff1  stloc.2
0x13ff2  ldarg.0
0x13ff3  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x13ff8  ldstr    aWresult// "wresult"
0x13ffd  callvirt instance string [System.Web]System.Web.HttpRequest::get_Item(string)
0x14002  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x14007  stloc.3
0x14008  ldloc.3
0x14009  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x1400e  brfalse.s loc_14012
0x14010  ldc.i4.0
0x14011  ret
0x14012  ldloc.2
0x14013  call     bool Microsoft.Crm.Authentication.Claims.HeaderAuthentication.KnownContextUrls::IsKnownWabUrl(string url)
0x14018  brfalse.s loc_1404F
0x1401a  ldarg.0
0x1401b  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x14020  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x14025  ldstr    aHtmlHeadTitleW// "<html><head><title>Working...</title></"...
0x1402a  ldc.i4.2
0x1402b  newarr   [mscorlib]System.Object
0x14030  dup
0x14031  ldc.i4.0
0x14032  ldloc.2
0x14033  stelem.ref
0x14034  dup
0x14035  ldc.i4.1
0x14036  ldloc.3
0x14037  stelem.ref
0x14038  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1403d  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x14042  ldarg.0
0x14043  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x14048  callvirt instance void [System.Web]System.Web.HttpResponse::End()
0x1404d  ldc.i4.1
0x1404e  ret
0x1404f  ldc.i4.0
0x14050  ret
```
