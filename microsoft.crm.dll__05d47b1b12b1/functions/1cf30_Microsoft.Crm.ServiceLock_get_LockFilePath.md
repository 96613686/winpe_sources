# Microsoft.Crm.ServiceLock::get_LockFilePath

- ea: `0x1cf30`
- end: `0x1cf60`
- name: `Microsoft.Crm.ServiceLock::get_LockFilePath`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1cf60`

## callees

- `0x1cf30`

## string_xrefs

- `0x1cf4a`: `StartupService.lock`

## pseudocode

```c

```

## disassembly

```asm
0x1cf30  ldarg.0
0x1cf31  ldfld    string Microsoft.Crm.ServiceLock::_lockFilePath
0x1cf36  brtrue.s loc_1CF59
0x1cf38  ldarg.0
0x1cf39  ldc.i4.s 0x23
0x1cf3b  call     string [mscorlib]System.Environment::GetFolderPath(valuetype [mscorlib]System.Environment/SpecialFolder)
0x1cf40  ldstr    aMicrosoft// "Microsoft"
0x1cf45  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x1cf4a  ldstr    aStartupservice// "StartupService.lock"
0x1cf4f  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x1cf54  stfld    string Microsoft.Crm.ServiceLock::_lockFilePath
0x1cf59  ldarg.0
0x1cf5a  ldfld    string Microsoft.Crm.ServiceLock::_lockFilePath
0x1cf5f  ret
```
