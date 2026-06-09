# Microsoft.Crm.Setup.Common.CA.DismWrapper::get_GetExePath

- ea: `0x176c0`
- end: `0x176e5`
- name: `Microsoft.Crm.Setup.Common.CA.DismWrapper::get_GetExePath`
- size: `37`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x17180`
- `0x171b0`
- `0x17210`
- `0x17300`
- `0x17360`

## callees

- `0x176a0`
- `0x176c0`

## pseudocode

```c

```

## disassembly

```asm
0x176c0  ldarg.0
0x176c1  call     instance bool Microsoft.Crm.Setup.Common.CA.DismWrapper::IsWoWProcess()
0x176c6  brfalse.s loc_176DD
0x176c8  ldstr    aWindir// "WINDIR"
0x176cd  call     string [mscorlib]System.Environment::GetEnvironmentVariable(string)
0x176d2  ldstr    aSysnative// "sysnative"
0x176d7  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x176dc  ret
0x176dd  ldc.i4.s 0x25
0x176df  call     string [mscorlib]System.Environment::GetFolderPath(valuetype [mscorlib]System.Environment/SpecialFolder)
0x176e4  ret
```
