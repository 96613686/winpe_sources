# Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::GetPathRelativeToTarget

- ea: `0x13f70`
- end: `0x13f91`
- name: `Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::GetPathRelativeToTarget`
- size: `33`
- prototype: ``
- caller_count: `7`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## callers

- `0x13bc0`
- `0x13cb0`
- `0x13e50`
- `0x156e0`
- `0x15700`
- `0x15a10`
- `0x16030`

## pseudocode

```c

```

## disassembly

```asm
0x13f70  ldarg.0
0x13f71  ldarg.1
0x13f72  callvirt instance int32 [mscorlib]System.String::get_Length()
0x13f77  callvirt instance string [mscorlib]System.String::Substring(int32)
0x13f7c  stloc.0
0x13f7d  ldloc.0
0x13f7e  ldsfld   char[] Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::_directoryDelimiter
0x13f83  callvirt instance string [mscorlib]System.String::TrimStart(char[])
0x13f88  stloc.0
0x13f89  ldarg.2
0x13f8a  ldloc.0
0x13f8b  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x13f90  ret
```
