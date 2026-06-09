# Microsoft.Crm.Tools.Unzip.XCeedUnzip::OnItemException

- ea: `0xd70`
- end: `0xda7`
- name: `Microsoft.Crm.Tools.Unzip.XCeedUnzip::OnItemException`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0xd70`

## pseudocode

```c

```

## disassembly

```asm
0xd70  ldarg.1
0xd71  callvirt instance class [Xceed.FileSystem]Xceed.FileSystem.FileSystemItem [Xceed.FileSystem]Xceed.FileSystem.FileSystemEventArgs::get_CurrentItem()
0xd76  isinst   [Xceed.Zip]Xceed.Zip.ZippedFile
0xd7b  brfalse.s loc_DA6
0xd7d  ldarg.1
0xd7e  callvirt instance class [mscorlib]System.Exception [Xceed.FileSystem]Xceed.FileSystem.ItemExceptionEventArgs::get_Exception()
0xd83  isinst   [Xceed.Zip]Xceed.Zip.InvalidDecryptionPasswordException
0xd88  brfalse.s loc_DA6
0xd8a  ldstr    a0HasBeenSkippe// "{0} has been skipped due to an invalid "...
0xd8f  ldarg.1
0xd90  callvirt instance class [Xceed.FileSystem]Xceed.FileSystem.FileSystemItem [Xceed.FileSystem]Xceed.FileSystem.FileSystemEventArgs::get_CurrentItem()
0xd95  callvirt instance string [Xceed.FileSystem]Xceed.FileSystem.FileSystemItem::get_Name()
0xd9a  call     void [mscorlib]System.Console::WriteLine(string, object)
0xd9f  ldarg.1
0xda0  ldc.i4.0
0xda1  callvirt instance void [Xceed.FileSystem]Xceed.FileSystem.ItemExceptionEventArgs::set_Action(valuetype [Xceed.FileSystem]Xceed.FileSystem.ItemExceptionAction)
0xda6  ret
```
