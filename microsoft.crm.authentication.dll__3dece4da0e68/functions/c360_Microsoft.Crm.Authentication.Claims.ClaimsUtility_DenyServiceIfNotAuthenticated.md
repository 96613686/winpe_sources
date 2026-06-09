# Microsoft.Crm.Authentication.Claims.ClaimsUtility::DenyServiceIfNotAuthenticated

- ea: `0xc360`
- end: `0xc3d6`
- name: `Microsoft.Crm.Authentication.Claims.ClaimsUtility::DenyServiceIfNotAuthenticated`
- size: `118`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x14150`

## callees

- `0xc360`
- `0x14c80`

## pseudocode

```c

```

## disassembly

```asm
0xc360  ldarg.0
0xc361  brfalse.s loc_C3D2
0xc363  ldarg.0
0xc364  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0xc369  brfalse.s loc_C3D2
0xc36b  ldsfld   class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Authentication.Claims.ClaimsUtility::denyTheseServicesIfNotAuthenticated
0xc370  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<string>::GetEnumerator()
0xc375  stloc.0
0xc376  br.s     loc_C3B7
0xc378  newobj   instance void <>c__DisplayClass36_0::.ctor()
0xc37d  stloc.1
0xc37e  ldloc.1
0xc37f  ldloca.s 0
0xc381  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::get_Current()
0xc386  stfld    string <>c__DisplayClass36_0::excludedService
0xc38b  ldarg.0
0xc38c  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0xc391  callvirt instance class [System]System.Uri [System.Web]System.Web.HttpRequest::get_Url()
0xc396  callvirt instance string[] [System]System.Uri::get_Segments()
0xc39b  ldloc.1
0xc39c  ldftn    instance bool <>c__DisplayClass36_0::<DenyServiceIfNotAuthenticated>b__0(string t)
0xc3a2  newobj   instance void class [mscorlib]System.Func`2<string, bool>::.ctor(object, native int)
0xc3a7  call     T0x2B00001E
0xc3ac  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xc3b1  brtrue.s loc_C3B7
0xc3b3  ldc.i4.1
0xc3b4  stloc.2
0xc3b5  leave.s  loc_C3D4
0xc3b7  ldloca.s 0
0xc3b9  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::MoveNext()
0xc3be  brtrue.s loc_C378
0xc3c0  leave.s  loc_C3D0
0xc3c2  ldloca.s 0
0xc3c4  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>
0xc3ca  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xc3cf  endfinally
0xc3d0  ldc.i4.0
0xc3d1  ret
0xc3d2  ldc.i4.0
0xc3d3  ret
0xc3d4  ldloc.2
0xc3d5  ret
```
