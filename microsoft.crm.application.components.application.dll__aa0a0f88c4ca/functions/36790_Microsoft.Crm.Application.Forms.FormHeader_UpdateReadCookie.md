# Microsoft.Crm.Application.Forms.FormHeader::UpdateReadCookie

- ea: `0x36790`
- end: `0x36a06`
- name: `Microsoft.Crm.Application.Forms.FormHeader::UpdateReadCookie`
- size: `630`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x36a70`

## callees

- `0x26210`
- `0x36790`
- `0x36a10`
- `0x8cd30`
- `0x8ceb0`

## string_xrefs

- `0x367b9`: `ReadNotifications`
- `0x367d7`: `ReadNotifications`
- `0x367ff`: `ReadNotifications`
- `0x368e7`: `ReadNotifications`
- `0x36905`: `ReadNotifications`
- `0x36938`: `ReadNotifications`
- `0x3695b`: `ReadNotifications`
- `0x3698d`: `ReadNotifications`
- `0x369d0`: `ReadNotifications`

## pseudocode

```c

```

## disassembly

```asm
0x36790  ldc.i4.0
0x36791  stloc.0
0x36792  ldarg.0
0x36793  ldfld    class Microsoft.Crm.Application.Forms.EndUserForm Microsoft.Crm.Application.Forms.FormHeader::_form
0x36798  callvirt instance class Microsoft.Crm.Application.Controls.AppNotifications Microsoft.Crm.Application.Forms.AppForm::get_Notifications()
0x3679d  brfalse  loc_36A04
0x367a2  ldarg.0
0x367a3  ldfld    class Microsoft.Crm.Application.Forms.EndUserForm Microsoft.Crm.Application.Forms.FormHeader::_form
0x367a8  callvirt instance class Microsoft.Crm.Application.Controls.AppNotifications Microsoft.Crm.Application.Forms.AppForm::get_Notifications()
0x367ad  callvirt instance int32 Microsoft.Crm.Application.Controls.AppNotifications::get_Count()
0x367b2  ldc.i4.0
0x367b3  ble      loc_36A04
0x367b8  ldarg.0
0x367b9  ldstr    aReadnotificati// "ReadNotifications"
0x367be  call     instance bool Microsoft.Crm.Application.Forms.FormHeader::CheckReadCookieExists(string cookieName)
0x367c3  brfalse  loc_36A04
0x367c8  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x367cd  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x367d2  callvirt instance class [System.Web]System.Web.HttpCookieCollection [System.Web]System.Web.HttpRequest::get_Cookies()
0x367d7  ldstr    aReadnotificati// "ReadNotifications"
0x367dc  callvirt instance class [System.Web]System.Web.HttpCookie [System.Web]System.Web.HttpCookieCollection::get_Item(string)
0x367e1  callvirt instance string [System.Web]System.Web.HttpCookie::get_Value()
0x367e6  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x367eb  brtrue   loc_36A04
0x367f0  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x367f5  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x367fa  callvirt instance class [System.Web]System.Web.HttpCookieCollection [System.Web]System.Web.HttpRequest::get_Cookies()
0x367ff  ldstr    aReadnotificati// "ReadNotifications"
0x36804  callvirt instance class [System.Web]System.Web.HttpCookie [System.Web]System.Web.HttpCookieCollection::get_Item(string)
0x36809  callvirt instance string [System.Web]System.Web.HttpCookie::get_Value()
0x3680e  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_Default()
0x36813  call     string [System.Web]System.Web.HttpUtility::UrlDecode(string, class [mscorlib]System.Text.Encoding)
0x36818  ldc.i4.1
0x36819  newarr   [mscorlib]System.Char
0x3681e  dup
0x3681f  ldc.i4.0
0x36820  ldc.i4.s 0x7C
0x36822  stelem.i2
0x36823  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x36828  stloc.1
0x36829  ldloc.1
0x3682a  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x3682f  stloc.2
0x36830  ldc.i4.0
0x36831  stloc.3
0x36832  br       loc_368BD
0x36837  ldloc.2
0x36838  ldloc.3
0x36839  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<string>::get_Item(!!T0)
0x3683e  ldc.i4.1
0x3683f  newarr   [mscorlib]System.Char
0x36844  dup
0x36845  ldc.i4.0
0x36846  ldc.i4.s 0x3A
0x36848  stelem.i2
0x36849  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x3684e  stloc.s  4
0x36850  ldarg.0
0x36851  ldfld    class Microsoft.Crm.Application.Forms.EndUserForm Microsoft.Crm.Application.Forms.FormHeader::_form
0x36856  callvirt instance class Microsoft.Crm.Application.Controls.AppNotifications Microsoft.Crm.Application.Forms.AppForm::get_Notifications()
0x3685b  ldstr    asc_12FE0A// ":"
0x36860  ldloc.s  4
0x36862  ldc.i4.1
0x36863  ldloc.s  4
0x36865  ldlen
0x36866  conv.i4
0x36867  ldc.i4.1
0x36868  sub
0x36869  call     string [mscorlib]System.String::Join(string, string[], int32, int32)
0x3686e  callvirt instance string Microsoft.Crm.Application.Controls.AppNotifications::GetIdBasedonText(string text)
0x36873  stloc.s  5
0x36875  ldloc.s  5
0x36877  brfalse.s loc_368AE
0x36879  ldloc.s  5
0x3687b  ldloc.s  4
0x3687d  ldc.i4.0
0x3687e  ldelem.ref
0x3687f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x36884  brtrue.s loc_368B9
0x36886  ldloc.s  5
0x36888  ldloc.s  4
0x3688a  ldc.i4.0
0x3688b  ldelem.ref
0x3688c  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x36891  brfalse.s loc_368B9
0x36893  ldloc.s  4
0x36895  ldc.i4.0
0x36896  ldloc.s  5
0x36898  stelem.ref
0x36899  ldloc.2
0x3689a  ldloc.3
0x3689b  ldstr    asc_12FE0A// ":"
0x368a0  ldloc.s  4
0x368a2  call     string [mscorlib]System.String::Join(string, string[])
0x368a7  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::set_Item(int32, var<u1>)
0x368ac  br.s     loc_368B9
0x368ae  ldloc.2
0x368af  ldloc.3
0x368b0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::RemoveAt(int32)
0x368b5  ldloc.3
0x368b6  ldc.i4.1
0x368b7  sub
0x368b8  stloc.3
0x368b9  ldloc.3
0x368ba  ldc.i4.1
0x368bb  add
0x368bc  stloc.3
0x368bd  ldloc.3
0x368be  ldloc.2
0x368bf  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<string>::get_Count()
0x368c4  bge.s    loc_368CD
0x368c6  ldloc.3
0x368c7  ldc.i4.m1
0x368c8  bgt      loc_36837
0x368cd  ldloc.2
0x368ce  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<string>::ToArray()
0x368d3  stloc.1
0x368d4  ldloc.1
0x368d5  ldlen
0x368d6  conv.i4
0x368d7  stloc.0
0x368d8  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x368dd  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x368e2  callvirt instance class [System.Web]System.Web.HttpCookieCollection [System.Web]System.Web.HttpResponse::get_Cookies()
0x368e7  ldstr    aReadnotificati// "ReadNotifications"
0x368ec  callvirt instance class [System.Web]System.Web.HttpCookie [System.Web]System.Web.HttpCookieCollection::get_Item(string)
0x368f1  brfalse  loc_3697E
0x368f6  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x368fb  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x36900  callvirt instance class [System.Web]System.Web.HttpCookieCollection [System.Web]System.Web.HttpResponse::get_Cookies()
0x36905  ldstr    aReadnotificati// "ReadNotifications"
0x3690a  callvirt instance class [System.Web]System.Web.HttpCookie [System.Web]System.Web.HttpCookieCollection::get_Item(string)
0x3690f  ldstr    asc_12FE0E// "|"
0x36914  ldloc.1
0x36915  call     string [mscorlib]System.String::Join(string, string[])
0x3691a  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_Default()
0x3691f  call     string [System.Web]System.Web.HttpUtility::UrlEncode(string, class [mscorlib]System.Text.Encoding)
0x36924  callvirt instance void [System.Web]System.Web.HttpCookie::set_Value(string)
0x36929  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x3692e  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x36933  callvirt instance class [System.Web]System.Web.HttpCookieCollection [System.Web]System.Web.HttpResponse::get_Cookies()
0x36938  ldstr    aReadnotificati// "ReadNotifications"
0x3693d  callvirt instance class [System.Web]System.Web.HttpCookie [System.Web]System.Web.HttpCookieCollection::get_Item(string)
0x36942  ldstr    asc_1207FC// "/"
0x36947  callvirt instance void [System.Web]System.Web.HttpCookie::set_Path(string)
0x3694c  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x36951  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x36956  callvirt instance class [System.Web]System.Web.HttpCookieCollection [System.Web]System.Web.HttpResponse::get_Cookies()
0x3695b  ldstr    aReadnotificati// "ReadNotifications"
0x36960  callvirt instance class [System.Web]System.Web.HttpCookie [System.Web]System.Web.HttpCookieCollection::get_Item(string)
0x36965  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x3696a  stloc.s  6
0x3696c  ldloca.s 6
0x3696e  ldc.i4.1
0x3696f  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddYears(int32)
0x36974  callvirt instance void [System.Web]System.Web.HttpCookie::set_Expires(valuetype [mscorlib]System.DateTime)
0x36979  br       loc_36A04
0x3697e  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x36983  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x36988  callvirt instance class [System.Web]System.Web.HttpCookieCollection [System.Web]System.Web.HttpRequest::get_Cookies()
0x3698d  ldstr    aReadnotificati// "ReadNotifications"
0x36992  callvirt instance class [System.Web]System.Web.HttpCookie [System.Web]System.Web.HttpCookieCollection::get_Item(string)
0x36997  stloc.s  7
0x36999  ldloc.s  7
0x3699b  ldstr    asc_12FE0E// "|"
0x369a0  ldloc.1
0x369a1  call     string [mscorlib]System.String::Join(string, string[])
0x369a6  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_Default()
0x369ab  call     string [System.Web]System.Web.HttpUtility::UrlEncode(string, class [mscorlib]System.Text.Encoding)
0x369b0  callvirt instance void [System.Web]System.Web.HttpCookie::set_Value(string)
0x369b5  ldloc.s  7
0x369b7  ldstr    asc_1207FC// "/"
0x369bc  callvirt instance void [System.Web]System.Web.HttpCookie::set_Path(string)
0x369c1  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x369c6  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x369cb  callvirt instance class [System.Web]System.Web.HttpCookieCollection [System.Web]System.Web.HttpResponse::get_Cookies()
0x369d0  ldstr    aReadnotificati// "ReadNotifications"
0x369d5  callvirt instance class [System.Web]System.Web.HttpCookie [System.Web]System.Web.HttpCookieCollection::get_Item(string)
0x369da  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x369df  stloc.s  6
0x369e1  ldloca.s 6
0x369e3  ldc.i4.1
0x369e4  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddYears(int32)
0x369e9  callvirt instance void [System.Web]System.Web.HttpCookie::set_Expires(valuetype [mscorlib]System.DateTime)
0x369ee  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x369f3  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x369f8  callvirt instance class [System.Web]System.Web.HttpCookieCollection [System.Web]System.Web.HttpResponse::get_Cookies()
0x369fd  ldloc.s  7
0x369ff  callvirt instance void [System.Web]System.Web.HttpCookieCollection::Add(class [System.Web]System.Web.HttpCookie)
0x36a04  ldloc.0
0x36a05  ret
```
