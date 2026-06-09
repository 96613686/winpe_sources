# Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::CreateParentDirectoryIfNotExist

- ea: `0x13f40`
- end: `0x13f6b`
- name: `Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::CreateParentDirectoryIfNotExist`
- size: `43`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x13580`
- `0x13bc0`

## callees

- `0x13f40`

## string_xrefs

- `0x13f4f`: `Creating directory {0}`

## pseudocode

```c

```

## disassembly

```asm
0x13f40  ldarg.0
0x13f41  call     string [mscorlib]System.IO.Path::GetDirectoryName(string)
0x13f46  stloc.0
0x13f47  ldloc.0
0x13f48  call     bool [mscorlib]System.IO.Directory::Exists(string)
0x13f4d  brtrue.s loc_13F6A
0x13f4f  ldstr    aCreatingDirect// "Creating directory {0}"
0x13f54  ldc.i4.1
0x13f55  newarr   [mscorlib]System.Object
0x13f5a  dup
0x13f5b  ldc.i4.0
0x13f5c  ldloc.0
0x13f5d  stelem.ref
0x13f5e  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x13f63  ldloc.0
0x13f64  call     class [mscorlib]System.IO.DirectoryInfo [mscorlib]System.IO.Directory::CreateDirectory(string)
0x13f69  pop
0x13f6a  ret
```
