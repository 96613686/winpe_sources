# Microsoft.Crm.Tools.Admin.InstallDynamicsSolutionsAction::SetSolutionVisibilityInternal

- ea: `0x6850`
- end: `0x68c3`
- name: `Microsoft.Crm.Tools.Admin.InstallDynamicsSolutionsAction::SetSolutionVisibilityInternal`
- size: `115`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x6710`

## callees

- `0x6850`

## string_xrefs

- `0x6850`: `UPDATE SolutionBase SET IsVisible = @Value WHERE UniqueName IN (`
- `0x68ab`: `d:\dbs\sh\dccm2\1101_190851\cmd\44\src\Tools2\DMSnapin\lib\Organization\InstallDynamicsSolutions.cs`

## pseudocode

```c

```

## disassembly

```asm
0x6850  ldstr    aUpdateSolution// "UPDATE SolutionBase SET IsVisible = @Va"...
0x6855  ldarg.0
0x6856  ldstr    asc_1FC1E// ")"
0x685b  call     string [mscorlib]System.String::Concat(string, string, string)
0x6860  stloc.0
0x6861  ldarg.1
0x6862  brtrue.s loc_6867
0x6864  ldc.i4.1
0x6865  br.s     loc_6868
0x6867  ldc.i4.0
0x6868  stloc.1
0x6869  ldarg.2
0x686a  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::CreateCommand()
0x686f  stloc.2
0x6870  ldloc.2
0x6871  ldloc.0
0x6872  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x6877  ldloc.2
0x6878  ldc.i4.1
0x6879  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandType(valuetype [System.Data]System.Data.CommandType)
0x687e  ldloc.2
0x687f  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x6884  ldstr    aValue// "@Value"
0x6889  ldloca.s 1
0x688b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6890  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x6895  newobj   instance void [System.Data]System.Data.SqlClient.SqlParameter::.ctor(string, object)
0x689a  callvirt instance int32 [mscorlib]System.Collections.IList::Add(object)
0x689f  pop
0x68a0  ldloc.2
0x68a1  ldc.i4   0x23F
0x68a6  ldstr    aSetsolutionvis_0// "SetSolutionVisibilityInternal"
0x68ab  ldstr    aDDbsShDccm2110_3// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\4"...
0x68b0  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x68b5  pop
0x68b6  leave.s  loc_68C2
0x68b8  ldloc.2
0x68b9  brfalse.s loc_68C1
0x68bb  ldloc.2
0x68bc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x68c1  endfinally
0x68c2  ret
```
