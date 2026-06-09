# Microsoft.Crm.Sandbox.SandboxUtility::SandboxWorkerCertificatePath

- ea: `0x2db0`
- end: `0x2dd5`
- name: `Microsoft.Crm.Sandbox.SandboxUtility::SandboxWorkerCertificatePath`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x2d10`
- `0x2db0`

## pseudocode

```c

```

## disassembly

```asm
0x2db0  ldarg.0
0x2db1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2db6  brtrue.s loc_2DBB
0x2db8  ldarg.0
0x2db9  br.s     loc_2DC0
0x2dbb  call     string Microsoft.Crm.Sandbox.SandboxUtility::SandboxFilesPath()
0x2dc0  starg.s  0
0x2dc2  ldc.i4.s 0xC
0x2dc4  ldarg.0
0x2dc5  call     T0x2B000009
0x2dca  ldstr    aCertificatesSa_0// "Certificates\\SandboxWorker"
0x2dcf  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x2dd4  ret
```
