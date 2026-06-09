# Microsoft.Crm.Setup.Common.Utility.SystemComponentName::get_SearchService

- ea: `0x11f60`
- end: `0x11f80`
- name: `Microsoft.Crm.Setup.Common.Utility.SystemComponentName::get_SearchService`
- size: `32`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x11f60`

## string_xrefs

- `0x11f74`: `Search-Service`
- `0x11f7a`: `FS-Search-Service`

## pseudocode

```c

```

## disassembly

```asm
0x11f60  call     bool [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Win32Utility::IsWebEditionServer()
0x11f65  brfalse.s loc_11F6D
0x11f67  ldsfld   string [mscorlib]System.String::Empty
0x11f6c  ret
0x11f6d  call     bool [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Win32Utility::get_IsWindowsServer2012OrLater()
0x11f72  brfalse.s loc_11F7A
0x11f74  ldstr    aSearchService// "Search-Service"
0x11f79  ret
0x11f7a  ldstr    aFsSearchServic// "FS-Search-Service"
0x11f7f  ret
```
