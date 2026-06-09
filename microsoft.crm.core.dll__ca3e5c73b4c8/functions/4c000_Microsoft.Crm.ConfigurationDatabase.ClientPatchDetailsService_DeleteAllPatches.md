# Microsoft.Crm.ConfigurationDatabase.ClientPatchDetailsService::DeleteAllPatches

- ea: `0x4c000`
- end: `0x4c054`
- name: `Microsoft.Crm.ConfigurationDatabase.ClientPatchDetailsService::DeleteAllPatches`
- size: `84`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x4c000`
- `0x625b0`

## string_xrefs

- `0x4c039`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\ObjectModel\ClientPatchDetails.cs`
- `0x4c034`: `DeleteAllPatches`

## pseudocode

```c

```

## disassembly

```asm
0x4c000  ldc.i4.3
0x4c001  newarr   [mscorlib]System.String
0x4c006  dup
0x4c007  ldc.i4.0
0x4c008  ldstr    aClientpatchdet// "ClientPatchDetails"
0x4c00d  stelem.ref
0x4c00e  dup
0x4c00f  ldc.i4.1
0x4c010  ldstr    aClientpatchreq// "ClientPatchRequiredInfo"
0x4c015  stelem.ref
0x4c016  dup
0x4c017  ldc.i4.2
0x4c018  ldstr    aClientpatchcon// "ClientPatchContainedInfo"
0x4c01d  stelem.ref
0x4c01e  stloc.0
0x4c01f  ldc.i4.0
0x4c020  stloc.1
0x4c021  br.s     loc_4C04D
0x4c023  ldloc.0
0x4c024  ldloc.1
0x4c025  ldelem.ref
0x4c026  stloc.2
0x4c027  ldarg.0
0x4c028  ldfld    class Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService Microsoft.Crm.ConfigurationDatabase.ClientPatchDetailsService::_configService
0x4c02d  ldloc.2
0x4c02e  ldnull
0x4c02f  ldc.i4   0x1AF
0x4c034  ldstr    aDeleteallpatch// "DeleteAllPatches"
0x4c039  ldstr    aDA1SSrcPlatfor_35// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x4c03e  callvirt instance int32 Microsoft.Crm.SharedDatabase.DatabaseService::Delete(string tableName, class Microsoft.Crm.Data.PropertyBag[] conditions, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x4c043  pop
0x4c044  leave.s  loc_4C049
0x4c046  pop
0x4c047  leave.s  loc_4C049
0x4c049  ldloc.1
0x4c04a  ldc.i4.1
0x4c04b  add
0x4c04c  stloc.1
0x4c04d  ldloc.1
0x4c04e  ldloc.0
0x4c04f  ldlen
0x4c050  conv.i4
0x4c051  blt.s    loc_4C023
0x4c053  ret
```
