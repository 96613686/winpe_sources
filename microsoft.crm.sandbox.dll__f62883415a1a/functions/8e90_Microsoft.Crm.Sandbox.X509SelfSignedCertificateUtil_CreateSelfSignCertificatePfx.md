# Microsoft.Crm.Sandbox.X509SelfSignedCertificateUtil::CreateSelfSignCertificatePfx

- ea: `0x8e90`
- end: `0x8e9a`
- name: `Microsoft.Crm.Sandbox.X509SelfSignedCertificateUtil::CreateSelfSignCertificatePfx`
- size: `10`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x8f00`

## pseudocode

```c

```

## disassembly

```asm
0x8e90  ldarg.0
0x8e91  ldarg.1
0x8e92  ldarg.2
0x8e93  ldnull
0x8e94  call     unsigned int8[] Microsoft.Crm.Sandbox.X509SelfSignedCertificateUtil::CreateSelfSignCertificatePfx(string x500, valuetype [mscorlib]System.DateTime startTime, valuetype [mscorlib]System.DateTime endTime, class [mscorlib]System.Security.SecureString password)
0x8e99  ret
```
