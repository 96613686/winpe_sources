# Microsoft.Crm.Setup.Common.Utility.SystemComponentName::get_IndexingService

- ea: `0x11f40`
- end: `0x11f60`
- name: `Microsoft.Crm.Setup.Common.Utility.SystemComponentName::get_IndexingService`
- size: `32`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x11f40`

## string_xrefs

- `0x11f54`: `Indexing-Service`
- `0x11f5a`: `FS-Indexing-Service`

## pseudocode

```c

```

## disassembly

```asm
0x11f40  call     bool [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Win32Utility::get_IsWindowsServer2012OrLater()
0x11f45  brfalse.s loc_11F4D
0x11f47  ldsfld   string [mscorlib]System.String::Empty
0x11f4c  ret
0x11f4d  call     bool [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Win32Utility::IsWebEditionServer()
0x11f52  brfalse.s loc_11F5A
0x11f54  ldstr    aIndexingServic// "Indexing-Service"
0x11f59  ret
0x11f5a  ldstr    aFsIndexingServ// "FS-Indexing-Service"
0x11f5f  ret
```
