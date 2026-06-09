# Microsoft.Crm.Tools.Admin.CleanupOptinSolutionAction::MoveCustomizedOptInComponentsToSystem

- ea: `0xe440`
- end: `0xe58b`
- name: `Microsoft.Crm.Tools.Admin.CleanupOptinSolutionAction::MoveCustomizedOptInComponentsToSystem`
- size: `331`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0xe3e0`

## callees

- `0xe440`

## string_xrefs

- `0xe54e`: `d:\dbs\sh\dccm2\1101_190851\cmd\44\src\Tools2\DMSnapin\lib\Organization\BusinessConfiguration.cs`
- `0xe4bb`: `\nWITH customizedComponents\nAS\n(SELECT {0}, \nROW_NUMBER() OVER(PARTITION BY {1} ORDER BY OverwriteTime) as OrderId, SolutionId\nFROM {2} \nWHERE OverwriteTime !=0 \nAND {1} IN \n(SELECT {1} FROM {2} WHERE  SolutionId IN (@fall12OptInSolutionId, @leoOptinSolutionId)) )\n\nUPDATE {2} SET SolutionId=@systemSolutionId WHERE {0} in \n(SELECT {0} FROM customizedComponents WHERE OrderId=1 and SolutionId IN (@fall12OptInSolutionId, @leoOptinSolutionId))\n`
- `0xe549`: `MoveCustomizedOptInComponentsToSystem`

## pseudocode

```c

```

## disassembly

```asm
0xe440  ldstr    aFormidunique// "FormIdUnique"
0xe445  ldstr    aFormid// "FormId"
0xe44a  ldstr    aSystemformbase// "SystemFormBase"
0xe44f  call     T0x2B000014
0xe454  stloc.0
0xe455  ldstr    aSavedqueryidun// "SavedQueryIdUnique"
0xe45a  ldstr    aSavedqueryid// "SavedQueryId"
0xe45f  ldstr    aSavedquerybase// "SavedQueryBase"
0xe464  call     T0x2B000014
0xe469  stloc.1
0xe46a  ldstr    aLocalizedlabel// "LocalizedLabelRowId"
0xe46f  ldstr    aLocalizedlabel_0// "LocalizedLabelId"
0xe474  ldstr    aMetadataschema// "MetadataSchema.LocalizedLabel"
0xe479  call     T0x2B000014
0xe47e  stloc.2
0xe47f  ldarg.1
0xe480  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::GetInstallConnectionTimeout()
0xe485  ldc.i4.0
0xe486  ldc.i4.0
0xe487  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid, int32, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0xe48c  stloc.3
0xe48d  ldloc.3
0xe48e  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0xe493  ldc.i4.3
0xe494  newarr   class [mscorlib]System.Tuple`3<string, string, string>
0xe499  dup
0xe49a  ldc.i4.0
0xe49b  ldloc.0
0xe49c  stelem.ref
0xe49d  dup
0xe49e  ldc.i4.1
0xe49f  ldloc.1
0xe4a0  stelem.ref
0xe4a1  dup
0xe4a2  ldc.i4.2
0xe4a3  ldloc.2
0xe4a4  stelem.ref
0xe4a5  stloc.s  4
0xe4a7  ldc.i4.0
0xe4a8  stloc.s  5
0xe4aa  br       loc_E56D
0xe4af  ldloc.s  4
0xe4b1  ldloc.s  5
0xe4b3  ldelem.ref
0xe4b4  stloc.s  6
0xe4b6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xe4bb  ldstr    aWithCustomized// "\r\nWITH customizedComponents\r\nAS\r\n"...
0xe4c0  ldc.i4.3
0xe4c1  newarr   [mscorlib]System.Object
0xe4c6  dup
0xe4c7  ldc.i4.0
0xe4c8  ldloc.s  6
0xe4ca  callvirt instance var<u1> class [mscorlib]System.Tuple`3<string, string, string>::get_Item1()
0xe4cf  stelem.ref
0xe4d0  dup
0xe4d1  ldc.i4.1
0xe4d2  ldloc.s  6
0xe4d4  callvirt instance var<u1> class [mscorlib]System.Tuple`3<string, string, string>::get_Item2()
0xe4d9  stelem.ref
0xe4da  dup
0xe4db  ldc.i4.2
0xe4dc  ldloc.s  6
0xe4de  callvirt instance var<u1> class [mscorlib]System.Tuple`3<string, string, string>::get_Item3()
0xe4e3  stelem.ref
0xe4e4  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xe4e9  stloc.s  7
0xe4eb  ldloc.3
0xe4ec  ldloc.s  7
0xe4ee  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand(string)
0xe4f3  stloc.s  8
0xe4f5  ldloc.s  8
0xe4f7  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0xe4fc  isinst   [System.Data]System.Data.SqlClient.SqlParameterCollection
0xe501  dup
0xe502  ldstr    aFall12optinsol// "@fall12OptInSolutionId"
0xe507  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.OptInSolutionConstants::Fall12OptInSolutionId
0xe50c  box      [mscorlib]System.Guid
0xe511  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xe516  pop
0xe517  dup
0xe518  ldstr    aLeooptinsoluti// "@leoOptInSolutionId"
0xe51d  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.OptInSolutionConstants::LeoOptInSolutionId
0xe522  box      [mscorlib]System.Guid
0xe527  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xe52c  pop
0xe52d  ldstr    aSystemsolution// "@systemSolutionId"
0xe532  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::SystemSolutionId
0xe537  box      [mscorlib]System.Guid
0xe53c  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xe541  pop
0xe542  ldloc.s  8
0xe544  ldc.i4   0x47E
0xe549  ldstr    aMovecustomized// "MoveCustomizedOptInComponentsToSystem"
0xe54e  ldstr    aDDbsShDccm2110_8// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\4"...
0xe553  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0xe558  pop
0xe559  leave.s  loc_E567
0xe55b  ldloc.s  8
0xe55d  brfalse.s loc_E566
0xe55f  ldloc.s  8
0xe561  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xe566  endfinally
0xe567  ldloc.s  5
0xe569  ldc.i4.1
0xe56a  add
0xe56b  stloc.s  5
0xe56d  ldloc.s  5
0xe56f  ldloc.s  4
0xe571  ldlen
0xe572  conv.i4
0xe573  blt      loc_E4AF
0xe578  ldloc.3
0xe579  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Close()
0xe57e  leave.s  loc_E58A
0xe580  ldloc.3
0xe581  brfalse.s loc_E589
0xe583  ldloc.3
0xe584  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xe589  endfinally
0xe58a  ret
```
