# Microsoft.Crm.Setup.Common.OnlinePackageSupport.LockedFileHandler::ScheduleMoveOnReboot

- ea: `0x144d0`
- end: `0x14506`
- name: `Microsoft.Crm.Setup.Common.OnlinePackageSupport.LockedFileHandler::ScheduleMoveOnReboot`
- size: `54`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x144b0`

## callees

- `0x14010`
- `0x144d0`

## string_xrefs

- `0x144e5`: `ScheduleMoveOnReboot - failure attempting to schedule move. Exception: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x144d0  ldc.i4.4
0x144d1  stloc.0
0x144d2  ldarg.2
0x144d3  brfalse.s loc_144D9
0x144d5  ldloc.0
0x144d6  ldc.i4.1
0x144d7  or
0x144d8  stloc.0
0x144d9  nop
0x144da  ldarg.0
0x144db  ldarg.1
0x144dc  ldloc.0
0x144dd  call     void Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::MoveFileEx(string existingFileName, string newFileName, valuetype Microsoft.Crm.Setup.Common.OnlinePackageSupport.MoveFileExFlags flags)
0x144e2  leave.s  loc_14505
0x144e4  stloc.1
0x144e5  ldstr    aSchedulemoveon// "ScheduleMoveOnReboot - failure attempti"...
0x144ea  ldc.i4.1
0x144eb  newarr   [mscorlib]System.Object
0x144f0  dup
0x144f1  ldc.i4.0
0x144f2  ldloc.1
0x144f3  callvirt instance string [mscorlib]System.Exception::get_Message()
0x144f8  stelem.ref
0x144f9  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Helpers.StringExtensions::FormatInvariant(string, object[])
0x144fe  ldloc.1
0x144ff  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, class [mscorlib]System.Exception)
0x14504  throw
0x14505  ret
```
