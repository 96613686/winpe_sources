# Microsoft.Xrm.Async.Bridges.FromCommonAuth.AadAuthConnectionString::ToConnectionString

- ea: `0x21d0`
- end: `0x226f`
- name: `Microsoft.Xrm.Async.Bridges.FromCommonAuth.AadAuthConnectionString::ToConnectionString`
- size: `159`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x2130`
- `0x2150`
- `0x2170`
- `0x2190`
- `0x21b0`
- `0x21d0`

## string_xrefs

- `0x2213`: `AppUri`

## pseudocode

```c

```

## disassembly

```asm
0x21d0  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x21d5  dup
0x21d6  ldstr    a01_0// "{0}={1};"
0x21db  ldstr    aClientid// "ClientId"
0x21e0  ldarg.0
0x21e1  call     instance string Microsoft.Xrm.Async.Bridges.FromCommonAuth.AadAuthConnectionString::get_ClientId()
0x21e6  call     string [mscorlib]System.String::Format(string, object, object)
0x21eb  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x21f0  pop
0x21f1  dup
0x21f2  ldstr    a01_0// "{0}={1};"
0x21f7  ldstr    aAuthorityurl// "AuthorityUrl"
0x21fc  ldarg.0
0x21fd  call     instance string Microsoft.Xrm.Async.Bridges.FromCommonAuth.AadAuthConnectionString::get_AuthorityUrl()
0x2202  call     string [mscorlib]System.String::Format(string, object, object)
0x2207  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x220c  pop
0x220d  dup
0x220e  ldstr    a01_0// "{0}={1};"
0x2213  ldstr    aAppuri// "AppUri"
0x2218  ldarg.0
0x2219  call     instance string Microsoft.Xrm.Async.Bridges.FromCommonAuth.AadAuthConnectionString::get_AppUri()
0x221e  call     string [mscorlib]System.String::Format(string, object, object)
0x2223  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2228  pop
0x2229  dup
0x222a  ldarg.0
0x222b  call     instance string Microsoft.Xrm.Async.Bridges.FromCommonAuth.AadAuthConnectionString::get_CertThumbprint()
0x2230  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x2235  brtrue.s loc_224E
0x2237  ldstr    a01_0// "{0}={1};"
0x223c  ldstr    aCertthumbprint// "CertThumbprint"
0x2241  ldarg.0
0x2242  call     instance string Microsoft.Xrm.Async.Bridges.FromCommonAuth.AadAuthConnectionString::get_CertThumbprint()
0x2247  call     string [mscorlib]System.String::Format(string, object, object)
0x224c  br.s     loc_2263
0x224e  ldstr    a01_0// "{0}={1};"
0x2253  ldstr    aAppkey// "AppKey"
0x2258  ldarg.0
0x2259  call     instance string Microsoft.Xrm.Async.Bridges.FromCommonAuth.AadAuthConnectionString::get_AppKey()
0x225e  call     string [mscorlib]System.String::Format(string, object, object)
0x2263  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2268  pop
0x2269  callvirt instance string [mscorlib]System.Object::ToString()
0x226e  ret
```
