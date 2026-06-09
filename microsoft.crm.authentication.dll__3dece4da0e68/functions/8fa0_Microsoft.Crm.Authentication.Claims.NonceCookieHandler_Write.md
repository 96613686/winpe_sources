# Microsoft.Crm.Authentication.Claims.NonceCookieHandler::Write

- ea: `0x8fa0`
- end: `0x9058`
- name: `Microsoft.Crm.Authentication.Claims.NonceCookieHandler::Write`
- size: `184`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x8fa0`
- `0x9090`
- `0x90e0`
- `0x9800`

## pseudocode

```c

```

## disassembly

```asm
0x8fa0  ldarg.3
0x8fa1  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x8fa6  callvirt instance class [System.Web]System.Web.HttpCookieCollection [System.Web]System.Web.HttpResponse::get_Cookies()
0x8fab  stloc.0
0x8fac  ldarg.0
0x8fad  call     instance class [mscorlib]System.Tuple`2<string, string> Microsoft.Crm.Authentication.Claims.NonceCookieHandler::GenerateCookieSettings()
0x8fb2  stloc.1
0x8fb3  ldarg.0
0x8fb4  ldfld    class Microsoft.Crm.Authentication.Claims.INonceProvider Microsoft.Crm.Authentication.Claims.NonceCookieHandler::_nonceProvider
0x8fb9  callvirt instance string Microsoft.Crm.Authentication.Claims.INonceProvider::GetNoncePrefix()
0x8fbe  stloc.2
0x8fbf  ldarg.3
0x8fc0  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x8fc5  callvirt instance class [System.Web]System.Web.HttpCookieCollection [System.Web]System.Web.HttpRequest::get_Cookies()
0x8fca  callvirt instance string[] [System.Web]System.Web.HttpCookieCollection::get_AllKeys()
0x8fcf  stloc.s  4
0x8fd1  ldc.i4.0
0x8fd2  stloc.s  5
0x8fd4  br.s     loc_900D
0x8fd6  ldloc.s  4
0x8fd8  ldloc.s  5
0x8fda  ldelem.ref
0x8fdb  stloc.s  6
0x8fdd  ldloc.s  6
0x8fdf  ldloc.2
0x8fe0  ldc.i4.5
0x8fe1  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x8fe6  brfalse.s loc_9007
0x8fe8  ldarg.0
0x8fe9  ldloc.s  6
0x8feb  ldloc.1
0x8fec  callvirt instance var<u1> class [mscorlib]System.Tuple`2<string, string>::get_Item1()
0x8ff1  ldloc.1
0x8ff2  callvirt instance var<u1> class [mscorlib]System.Tuple`2<string, string>::get_Item2()
0x8ff7  ldarg.3
0x8ff8  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x8ffd  callvirt instance class [System.Web]System.Web.HttpCookieCollection [System.Web]System.Web.HttpResponse::get_Cookies()
0x9002  call     instance void Microsoft.Crm.Authentication.Claims.NonceCookieHandler::Delete(string name, string path, string domain, class [System.Web]System.Web.HttpCookieCollection responseCookies)
0x9007  ldloc.s  5
0x9009  ldc.i4.1
0x900a  add
0x900b  stloc.s  5
0x900d  ldloc.s  5
0x900f  ldloc.s  4
0x9011  ldlen
0x9012  conv.i4
0x9013  blt.s    loc_8FD6
0x9015  ldarg.2
0x9016  ldarg.1
0x9017  newobj   instance void [System.Web]System.Web.HttpCookie::.ctor(string, string)
0x901c  dup
0x901d  ldc.i4.1
0x901e  callvirt instance void [System.Web]System.Web.HttpCookie::set_Secure(bool)
0x9023  dup
0x9024  ldc.i4.1
0x9025  callvirt instance void [System.Web]System.Web.HttpCookie::set_HttpOnly(bool)
0x902a  dup
0x902b  ldloc.1
0x902c  callvirt instance var<u1> class [mscorlib]System.Tuple`2<string, string>::get_Item1()
0x9031  callvirt instance void [System.Web]System.Web.HttpCookie::set_Path(string)
0x9036  stloc.3
0x9037  ldloc.1
0x9038  callvirt instance var<u1> class [mscorlib]System.Tuple`2<string, string>::get_Item2()
0x903d  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x9042  brtrue.s loc_9050
0x9044  ldloc.3
0x9045  ldloc.1
0x9046  callvirt instance var<u1> class [mscorlib]System.Tuple`2<string, string>::get_Item2()
0x904b  callvirt instance void [System.Web]System.Web.HttpCookie::set_Domain(string)
0x9050  ldloc.0
0x9051  ldloc.3
0x9052  callvirt instance void [System.Web]System.Web.HttpCookieCollection::Set(class [System.Web]System.Web.HttpCookie)
0x9057  ret
```
