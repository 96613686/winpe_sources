# Microsoft.Crm.Sandbox.SandboxUtility::BasePackagePath

- ea: `0x2d70`
- end: `0x2d87`
- name: `Microsoft.Crm.Sandbox.SandboxUtility::BasePackagePath`
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
0x2d70  ldc.i4.s 0xC
0x2d72  call     string Microsoft.Crm.Sandbox.SandboxUtility::SandboxFilesPath()
0x2d77  call     T0x2B000009
0x2d7c  ldstr    aCrmworkerproce// "CRMWorkerProcess"
0x2d81  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x2d86  ret
```
