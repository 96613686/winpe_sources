# Microsoft.Crm.Setup.Common.ClientVersionHistory::GetVersionComponentPath

- ea: `0x1050`
- end: `0x1080`
- name: `Microsoft.Crm.Setup.Common.ClientVersionHistory::GetVersionComponentPath`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `reparse_path, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1050`

## string_xrefs

- `0x1051`: `PFiles\MSCRM\Client\bin\crmverclient.dll`
- `0x1065`: `Client\bin\crmverclient.dll`
- `0x1078`: `crmverclient.dll`

## pseudocode

```c

```

## disassembly

```asm
0x1050  ldarg.1
0x1051  ldstr    aPfilesMscrmCli// "PFiles\\MSCRM\\Client\\bin\\crmverclien"...
0x1056  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x105b  stloc.0
0x105c  ldloc.0
0x105d  call     bool [mscorlib]System.IO.File::Exists(string)
0x1062  brtrue.s loc_107E
0x1064  ldarg.1
0x1065  ldstr    aClientBinCrmve// "Client\\bin\\crmverclient.dll"
0x106a  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x106f  stloc.0
0x1070  ldloc.0
0x1071  call     bool [mscorlib]System.IO.File::Exists(string)
0x1076  brtrue.s loc_107E
0x1078  ldstr    aCrmverclientDl// "crmverclient.dll"
0x107d  ret
0x107e  ldloc.0
0x107f  ret
```
