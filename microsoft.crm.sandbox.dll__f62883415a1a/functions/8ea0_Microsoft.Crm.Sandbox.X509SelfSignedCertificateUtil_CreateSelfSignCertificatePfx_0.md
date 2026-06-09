# Microsoft.Crm.Sandbox.X509SelfSignedCertificateUtil::CreateSelfSignCertificatePfx_0

- ea: `0x8ea0`
- end: `0x8ef2`
- name: `Microsoft.Crm.Sandbox.X509SelfSignedCertificateUtil::CreateSelfSignCertificatePfx_0`
- size: `82`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x8ea0`
- `0x8f00`

## pseudocode

```c

```

## disassembly

```asm
0x8ea0  ldnull
0x8ea1  stloc.1
0x8ea2  ldarg.3
0x8ea3  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x8ea8  brtrue.s loc_8EDA
0x8eaa  newobj   instance void [mscorlib]System.Security.SecureString::.ctor()
0x8eaf  stloc.1
0x8eb0  ldarg.3
0x8eb1  stloc.2
0x8eb2  ldc.i4.0
0x8eb3  stloc.3
0x8eb4  br.s     loc_8ECB
0x8eb6  ldloc.2
0x8eb7  ldloc.3
0x8eb8  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x8ebd  stloc.s  4
0x8ebf  ldloc.1
0x8ec0  ldloc.s  4
0x8ec2  callvirt instance void [mscorlib]System.Security.SecureString::AppendChar(char)
0x8ec7  ldloc.3
0x8ec8  ldc.i4.1
0x8ec9  add
0x8eca  stloc.3
0x8ecb  ldloc.3
0x8ecc  ldloc.2
0x8ecd  callvirt instance int32 [mscorlib]System.String::get_Length()
0x8ed2  blt.s    loc_8EB6
0x8ed4  ldloc.1
0x8ed5  callvirt instance void [mscorlib]System.Security.SecureString::MakeReadOnly()
0x8eda  ldarg.0
0x8edb  ldarg.1
0x8edc  ldarg.2
0x8edd  ldloc.1
0x8ede  call     unsigned int8[] Microsoft.Crm.Sandbox.X509SelfSignedCertificateUtil::CreateSelfSignCertificatePfx(string x500, valuetype [mscorlib]System.DateTime startTime, valuetype [mscorlib]System.DateTime endTime, class [mscorlib]System.Security.SecureString password)
0x8ee3  stloc.0
0x8ee4  leave.s  loc_8EF0
0x8ee6  ldloc.1
0x8ee7  brfalse.s loc_8EEF
0x8ee9  ldloc.1
0x8eea  callvirt instance void [mscorlib]System.Security.SecureString::Dispose()
0x8eef  endfinally
0x8ef0  ldloc.0
0x8ef1  ret
```
