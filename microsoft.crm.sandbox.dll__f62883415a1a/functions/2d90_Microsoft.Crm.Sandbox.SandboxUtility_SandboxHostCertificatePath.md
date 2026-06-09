# Microsoft.Crm.Sandbox.SandboxUtility::SandboxHostCertificatePath

- ea: `0x2d90`
- end: `0x2da7`
- name: `Microsoft.Crm.Sandbox.SandboxUtility::SandboxHostCertificatePath`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x2d10`

## pseudocode

```c

```

## disassembly

```asm
0x2d90  ldc.i4.s 0xC
0x2d92  call     string Microsoft.Crm.Sandbox.SandboxUtility::SandboxFilesPath()
0x2d97  call     T0x2B000009
0x2d9c  ldstr    aCertificatesSa// "Certificates\\SandboxHost"
0x2da1  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x2da6  ret
```
