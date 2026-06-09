# Microsoft.Crm.OnlineOnlyFileManager::UndoUpdate_0

- ea: `0x16170`
- end: `0x1620e`
- name: `Microsoft.Crm.OnlineOnlyFileManager::UndoUpdate_0`
- size: `158`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x16030`

## callees

- `0x16170`
- `0x162c0`

## string_xrefs

- `0x1617c`: `updateIndentifier`
- `0x161b3`: `Backup path found at {0}`
- `0x161f4`: `Backup path NOT found at {0}`

## pseudocode

```c

```

## disassembly

```asm
0x16170  ldarg.0
0x16171  ldstr    aCrmserverfolde// "crmServerFolder"
0x16176  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x1617b  ldarg.1
0x1617c  ldstr    aUpdateindentif// "updateIndentifier"
0x16181  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x16186  ldarg.0
0x16187  ldarg.2
0x16188  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x1618d  newobj   instance void [mscorlib]System.IO.DirectoryInfo::.ctor(string)
0x16192  stloc.0
0x16193  ldarg.0
0x16194  ldstr    aBackup// "Backup_"
0x16199  ldarg.1
0x1619a  call     string [mscorlib]System.String::Concat(string, string)
0x1619f  ldarg.2
0x161a0  call     string [mscorlib]System.IO.Path::Combine(string, string, string)
0x161a5  newobj   instance void [mscorlib]System.IO.DirectoryInfo::.ctor(string)
0x161aa  stloc.1
0x161ab  ldloc.1
0x161ac  callvirt instance bool [mscorlib]System.IO.FileSystemInfo::get_Exists()
0x161b1  brfalse.s loc_161F4
0x161b3  ldstr    aBackupPathFoun// "Backup path found at {0}"
0x161b8  ldc.i4.1
0x161b9  newarr   [mscorlib]System.Object
0x161be  dup
0x161bf  ldc.i4.0
0x161c0  ldloc.1
0x161c1  callvirt instance string [mscorlib]System.Object::ToString()
0x161c6  stelem.ref
0x161c7  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0x161cc  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x161d1  stloc.2
0x161d2  ldloc.1
0x161d3  ldloc.0
0x161d4  ldloc.2
0x161d5  call     void Microsoft.Crm.OnlineOnlyFileManager::CopyAll(class [mscorlib]System.IO.DirectoryInfo source, class [mscorlib]System.IO.DirectoryInfo target, class [mscorlib]System.Collections.Generic.List`1<string> errorList)
0x161da  ldloc.2
0x161db  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<string>::get_Count()
0x161e0  ldc.i4.0
0x161e1  ble.s    loc_1620D
0x161e3  ldstr    asc_62D76// "[!!!]"
0x161e8  ldloc.2
0x161e9  call     string [mscorlib]System.String::Join(string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>)
0x161ee  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x161f3  throw
0x161f4  ldstr    aBackupPathNotF// "Backup path NOT found at {0}"
0x161f9  ldc.i4.1
0x161fa  newarr   [mscorlib]System.Object
0x161ff  dup
0x16200  ldc.i4.0
0x16201  ldloc.1
0x16202  callvirt instance string [mscorlib]System.Object::ToString()
0x16207  stelem.ref
0x16208  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0x1620d  ret
```
