# <>c::<GetIdentityConfiguration>b__9_0

- ea: `0x14930`
- end: `0x1499b`
- name: `<>c::<GetIdentityConfiguration>b__9_0`
- size: `107`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x149b0`

## string_xrefs

- `0x14936`: `GetidentityConfiguration - Initialization:\n`

## pseudocode

```c

```

## disassembly

```asm
0x14930  newobj   instance void <>c__DisplayClass9_0::.ctor()
0x14935  dup
0x14936  ldstr    aGetidentitycon// "GetidentityConfiguration - Initializati"...
0x1493b  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(string)
0x14940  stfld    class [mscorlib]System.Text.StringBuilder <>c__DisplayClass9_0::messageBuilder
0x14945  dup
0x14946  ldfld    class [mscorlib]System.Text.StringBuilder <>c__DisplayClass9_0::messageBuilder
0x1494b  ldstr    aHost0// "Host: {0}\n"
0x14950  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x14955  call     string [Microsoft.Crm.Core]Microsoft.Crm.AuthenticationContextExtensions::CurrentHost(class [System.Web]System.Web.HttpContext)
0x1495a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0x1495f  pop
0x14960  dup
0x14961  ldfld    class [mscorlib]System.Text.StringBuilder <>c__DisplayClass9_0::messageBuilder
0x14966  ldstr    aRequestUrl0// "Request Url: {0}\n"
0x1496b  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x14970  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x14975  callvirt instance class [System]System.Uri [System.Web]System.Web.HttpRequest::get_Url()
0x1497a  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x1497f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0x14984  pop
0x14985  ldftn    instance class [System.IdentityModel]System.IdentityModel.Configuration.IdentityConfiguration <>c__DisplayClass9_0::<GetIdentityConfiguration>b__1()
0x1498b  newobj   instance void class [mscorlib]System.Func`1<class [System.IdentityModel]System.IdentityModel.Configuration.IdentityConfiguration>::.ctor(object, native int)
0x14990  call     T0x2B00002B
0x14995  stsfld   class [System.IdentityModel]System.IdentityModel.Configuration.IdentityConfiguration Microsoft.Crm.Authentication.Claims.IdentityConfigurationProvider::_identityConfiguration
0x1499a  ret
```
