# Microsoft.Crm.Sandbox.SandboxUtility::CrashFilePath

- ea: `0x2de0`
- end: `0x2e16`
- name: `Microsoft.Crm.Sandbox.SandboxUtility::CrashFilePath`
- size: `54`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x2e20`

## callees

- `0x2d10`
- `0x2de0`

## pseudocode

```c

```

## disassembly

```asm
0x2de0  ldarg.0
0x2de1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2de6  brtrue.s loc_2DEB
0x2de8  ldarg.0
0x2de9  br.s     loc_2DF0
0x2deb  call     string Microsoft.Crm.Sandbox.SandboxUtility::SandboxFilesPath()
0x2df0  starg.s  0
0x2df2  ldc.i4.s 0xD
0x2df4  ldarg.0
0x2df5  call     T0x2B000009
0x2dfa  ldstr    aFiles// "Files"
0x2dff  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x2e04  stloc.0
0x2e05  ldloc.0
0x2e06  call     bool [mscorlib]System.IO.Directory::Exists(string)
0x2e0b  brtrue.s loc_2E14
0x2e0d  ldloc.0
0x2e0e  call     class [mscorlib]System.IO.DirectoryInfo [mscorlib]System.IO.Directory::CreateDirectory(string)
0x2e13  pop
0x2e14  ldloc.0
0x2e15  ret
```
