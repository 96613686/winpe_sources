# Microsoft.Crm.Tools.Admin.MappingFileGenerator::CompleteUserMapping

- ea: `0x12be0`
- end: `0x12c17`
- name: `Microsoft.Crm.Tools.Admin.MappingFileGenerator::CompleteUserMapping`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x122a0`
- `0x12be0`
- `0x12c30`

## string_xrefs

- `0x12c01`: `GenerateMappingFile completed`

## pseudocode

```c

```

## disassembly

```asm
0x12be0  ldarg.0
0x12be1  ldarg.0
0x12be2  ldftn    instance void Microsoft.Crm.Tools.Admin.MappingFileGenerator::<CompleteUserMapping>b__23_0()
0x12be8  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x12bed  call     instance void Microsoft.Crm.Tools.Admin.MappingFileGenerator::ExceptionHandler(class [mscorlib]System.Action action)
0x12bf2  ldarg.0
0x12bf3  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.MapUsersResult Microsoft.Crm.Tools.Admin.ImportUserMapper::get_MappingResult()
0x12bf8  brfalse.s loc_12C01
0x12bfa  ldarg.0
0x12bfb  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.MapUsersResult Microsoft.Crm.Tools.Admin.ImportUserMapper::get_MappingResult()
0x12c00  ret
0x12c01  ldstr    aGeneratemappin_0// "GenerateMappingFile completed"
0x12c06  ldc.i4.0
0x12c07  newarr   [mscorlib]System.Object
0x12c0c  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::Write(string, object[])
0x12c11  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.MapSuccess::.ctor()
0x12c16  ret
```
