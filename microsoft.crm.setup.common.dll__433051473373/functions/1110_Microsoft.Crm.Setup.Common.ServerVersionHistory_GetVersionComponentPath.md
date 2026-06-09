# Microsoft.Crm.Setup.Common.ServerVersionHistory::GetVersionComponentPath

- ea: `0x1110`
- end: `0x1140`
- name: `Microsoft.Crm.Setup.Common.ServerVersionHistory::GetVersionComponentPath`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `reparse_path, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1110`

## string_xrefs

- `0x1111`: `PFiles\MSCRM\Server\bin\crmverserver.dll`
- `0x1125`: `Server\bin\crmverserver.dll`
- `0x1138`: `crmverserver.dll`

## pseudocode

```c

```

## disassembly

```asm
0x1110  ldarg.1
0x1111  ldstr    aPfilesMscrmSer// "PFiles\\MSCRM\\Server\\bin\\crmverserve"...
0x1116  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x111b  stloc.0
0x111c  ldloc.0
0x111d  call     bool [mscorlib]System.IO.File::Exists(string)
0x1122  brtrue.s loc_113E
0x1124  ldarg.1
0x1125  ldstr    aServerBinCrmve// "Server\\bin\\crmverserver.dll"
0x112a  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x112f  stloc.0
0x1130  ldloc.0
0x1131  call     bool [mscorlib]System.IO.File::Exists(string)
0x1136  brtrue.s loc_113E
0x1138  ldstr    aCrmverserverDl// "crmverserver.dll"
0x113d  ret
0x113e  ldloc.0
0x113f  ret
```
