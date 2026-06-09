# Microsoft.Crm.SharedDatabase.DatabaseService::InternalExecuteCreateCommand

- ea: `0x621e0`
- end: `0x62432`
- name: `Microsoft.Crm.SharedDatabase.DatabaseService::InternalExecuteCreateCommand`
- size: `594`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x62120`

## callees

- `0xd5f0`
- `0xdac0`
- `0x444f0`
- `0x5f120`
- `0x60800`
- `0x621e0`
- `0x630a0`
- `0x630e0`
- `0x63350`
- `0x63da0`
- `0x63e20`
- `0x64060`
- `0x64580`

## string_xrefs

- `0x622b3`: `D:\a\1\s\src\Platform\Core\DataServices\ObjectModel\DatabaseService.cs`
- `0x623eb`: `D:\a\1\s\src\Platform\Core\DataServices\ObjectModel\DatabaseService.cs`
- `0x622ae`: `InternalExecuteCreateCommand`
- `0x623e6`: `InternalExecuteCreateCommand`

## pseudocode

```c

```

## disassembly

```asm
0x621e0  ldarg.3
0x621e1  ldarg.0
0x621e2  ldftn    instance bool Microsoft.Crm.SharedDatabase.DatabaseService::<InternalExecuteCreateCommand>b__69_0(valuetype Microsoft.Crm.Data.PropertyEntry p)
0x621e8  newobj   instance void class [mscorlib]System.Func`2<valuetype Microsoft.Crm.Data.PropertyEntry, bool>::.ctor(object, native int)
0x621ed  call     T0x2B00011B
0x621f2  call     T0x2B000119
0x621f7  stloc.0
0x621f8  ldloc.0
0x621f9  call     T0x2B00011C
0x621fe  brfalse  loc_622CA
0x62203  ldarg.2
0x62204  callvirt instance class [System.Data]System.Data.IDbCommand Microsoft.Crm.CrmDbConnection::CreateCommand()
0x62209  stloc.2
0x6220a  ldarg.0
0x6220b  ldc.i4   0x80
0x62210  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(int32)
0x62215  stfld    class [mscorlib]System.Text.StringBuilder Microsoft.Crm.SharedDatabase.DatabaseService::_baseSqlBuilder
0x6221a  ldarg.0
0x6221b  ldc.i4   0x80
0x62220  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(int32)
0x62225  stfld    class [mscorlib]System.Text.StringBuilder Microsoft.Crm.SharedDatabase.DatabaseService::_propertiesSqlBuilder
0x6222a  ldarg.0
0x6222b  ldc.i4   0x80
0x62230  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(int32)
0x62235  stfld    class [mscorlib]System.Text.StringBuilder Microsoft.Crm.SharedDatabase.DatabaseService::_preSqlBuilder
0x6223a  ldarg.0
0x6223b  ldc.i4   0x80
0x62240  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(int32)
0x62245  stfld    class [mscorlib]System.Text.StringBuilder Microsoft.Crm.SharedDatabase.DatabaseService::_postSqlBuilder
0x6224a  ldarg.0
0x6224b  ldloc.2
0x6224c  stfld    class [System.Data]System.Data.IDbCommand Microsoft.Crm.SharedDatabase.DatabaseService::_baseCommand
0x62251  ldarg.0
0x62252  ldloc.0
0x62253  call     instance void Microsoft.Crm.SharedDatabase.DatabaseService::BuildBaseInsertSql(class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.Crm.Data.PropertyEntry> columnSet)
0x62258  ldarg.0
0x62259  call     instance void Microsoft.Crm.SharedDatabase.DatabaseService::BuildOpenSymmetricKeySql()
0x6225e  ldarg.0
0x6225f  call     instance void Microsoft.Crm.SharedDatabase.DatabaseService::BuildCloseSymmetricKeySql()
0x62264  ldloc.2
0x62265  ldc.i4.3
0x62266  newarr   [mscorlib]System.String
0x6226b  dup
0x6226c  ldc.i4.0
0x6226d  ldarg.0
0x6226e  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.Crm.SharedDatabase.DatabaseService::_preSqlBuilder
0x62273  callvirt instance string [mscorlib]System.Object::ToString()
0x62278  stelem.ref
0x62279  dup
0x6227a  ldc.i4.1
0x6227b  ldarg.0
0x6227c  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.Crm.SharedDatabase.DatabaseService::_baseSqlBuilder
0x62281  callvirt instance string [mscorlib]System.Object::ToString()
0x62286  stelem.ref
0x62287  dup
0x62288  ldc.i4.2
0x62289  ldarg.0
0x6228a  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.Crm.SharedDatabase.DatabaseService::_postSqlBuilder
0x6228f  callvirt instance string [mscorlib]System.Object::ToString()
0x62294  stelem.ref
0x62295  call     string Microsoft.Crm.SharedDatabase.DatabaseService::BuildSql(string[] sqlStatements)
0x6229a  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x6229f  ldarg.0
0x622a0  ldc.i4.1
0x622a1  ldloc.2
0x622a2  call     instance void Microsoft.Crm.SharedDatabase.DatabaseService::InstrumentQuery(valuetype Microsoft.Crm.InstrumentationOperationType type, class [System.Data]System.Data.IDbCommand command)
0x622a7  ldloc.2
0x622a8  ldc.i4.1
0x622a9  ldc.i4   0x4ED
0x622ae  ldstr    aInternalexecut// "InternalExecuteCreateCommand"
0x622b3  ldstr    aDA1SSrcPlatfor_44// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x622b8  call     int32 Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand command, bool impersonate, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x622bd  pop
0x622be  leave.s  loc_622CA
0x622c0  ldloc.2
0x622c1  brfalse.s loc_622C9
0x622c3  ldloc.2
0x622c4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x622c9  endfinally
0x622ca  ldarg.3
0x622cb  ldarg.0
0x622cc  ldftn    instance bool Microsoft.Crm.SharedDatabase.DatabaseService::<InternalExecuteCreateCommand>b__69_1(valuetype Microsoft.Crm.Data.PropertyEntry p)
0x622d2  newobj   instance void class [mscorlib]System.Func`2<valuetype Microsoft.Crm.Data.PropertyEntry, bool>::.ctor(object, native int)
0x622d7  call     T0x2B00011B
0x622dc  call     T0x2B000119
0x622e1  stloc.1
0x622e2  ldloc.1
0x622e3  call     T0x2B00011C
0x622e8  brfalse  loc_62431
0x622ed  ldarg.0
0x622ee  callvirt instance bool Microsoft.Crm.SharedDatabase.DatabaseService::get_HasPropertiesColumns()
0x622f3  brfalse  loc_62431
0x622f8  ldc.i4.0
0x622f9  stloc.3
0x622fa  ldloc.3
0x622fb  ldc.i4.s 0x64
0x622fd  mul
0x622fe  stloc.s  4
0x62300  ldloc.1
0x62301  ldloc.s  4
0x62303  call     T0x2B00011D
0x62308  ldc.i4.s 0x64
0x6230a  call     T0x2B00011E
0x6230f  call     T0x2B000119
0x62314  stloc.s  5
0x62316  ldarg.1
0x62317  ldarg.0
0x62318  ldfld    class Microsoft.Crm.SharedDatabase.Table Microsoft.Crm.SharedDatabase.DatabaseService::_table
0x6231d  callvirt instance class Microsoft.Crm.SharedDatabase.Column Microsoft.Crm.SharedDatabase.Table::get_PrimaryKey()
0x62322  callvirt instance string Microsoft.Crm.SharedDatabase.Column::get_Name()
0x62327  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0x6232c  stloc.s  6
0x6232e  br       loc_62424
0x62333  ldarg.2
0x62334  callvirt instance class [System.Data]System.Data.IDbCommand Microsoft.Crm.CrmDbConnection::CreateCommand()
0x62339  stloc.s  7
0x6233b  ldarg.0
0x6233c  ldc.i4   0x80
0x62341  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(int32)
0x62346  stfld    class [mscorlib]System.Text.StringBuilder Microsoft.Crm.SharedDatabase.DatabaseService::_baseSqlBuilder
0x6234b  ldarg.0
0x6234c  ldc.i4   0x80
0x62351  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(int32)
0x62356  stfld    class [mscorlib]System.Text.StringBuilder Microsoft.Crm.SharedDatabase.DatabaseService::_propertiesSqlBuilder
0x6235b  ldarg.0
0x6235c  ldc.i4   0x80
0x62361  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(int32)
0x62366  stfld    class [mscorlib]System.Text.StringBuilder Microsoft.Crm.SharedDatabase.DatabaseService::_preSqlBuilder
0x6236b  ldarg.0
0x6236c  ldc.i4   0x80
0x62371  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(int32)
0x62376  stfld    class [mscorlib]System.Text.StringBuilder Microsoft.Crm.SharedDatabase.DatabaseService::_postSqlBuilder
0x6237b  ldarg.0
0x6237c  ldloc.s  7
0x6237e  stfld    class [System.Data]System.Data.IDbCommand Microsoft.Crm.SharedDatabase.DatabaseService::_baseCommand
0x62383  ldarg.0
0x62384  ldloc.s  5
0x62386  ldloc.s  6
0x62388  call     instance void Microsoft.Crm.SharedDatabase.DatabaseService::BuildPropertiesInsertSql(class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.Crm.Data.PropertyEntry> columnSet, object primaryKeyValue)
0x6238d  ldarg.0
0x6238e  call     instance void Microsoft.Crm.SharedDatabase.DatabaseService::BuildOpenSymmetricKeySql()
0x62393  ldarg.0
0x62394  call     instance void Microsoft.Crm.SharedDatabase.DatabaseService::BuildCloseSymmetricKeySql()
0x62399  ldloc.s  7
0x6239b  ldc.i4.3
0x6239c  newarr   [mscorlib]System.String
0x623a1  dup
0x623a2  ldc.i4.0
0x623a3  ldarg.0
0x623a4  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.Crm.SharedDatabase.DatabaseService::_preSqlBuilder
0x623a9  callvirt instance string [mscorlib]System.Object::ToString()
0x623ae  stelem.ref
0x623af  dup
0x623b0  ldc.i4.1
0x623b1  ldarg.0
0x623b2  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.Crm.SharedDatabase.DatabaseService::_baseSqlBuilder
0x623b7  callvirt instance string [mscorlib]System.Object::ToString()
0x623bc  stelem.ref
0x623bd  dup
0x623be  ldc.i4.2
0x623bf  ldarg.0
0x623c0  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.Crm.SharedDatabase.DatabaseService::_postSqlBuilder
0x623c5  callvirt instance string [mscorlib]System.Object::ToString()
0x623ca  stelem.ref
0x623cb  call     string Microsoft.Crm.SharedDatabase.DatabaseService::BuildSql(string[] sqlStatements)
0x623d0  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x623d5  ldarg.0
0x623d6  ldc.i4.1
0x623d7  ldloc.s  7
0x623d9  call     instance void Microsoft.Crm.SharedDatabase.DatabaseService::InstrumentQuery(valuetype Microsoft.Crm.InstrumentationOperationType type, class [System.Data]System.Data.IDbCommand command)
0x623de  ldloc.s  7
0x623e0  ldc.i4.1
0x623e1  ldc.i4   0x51A
0x623e6  ldstr    aInternalexecut// "InternalExecuteCreateCommand"
0x623eb  ldstr    aDA1SSrcPlatfor_44// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x623f0  call     int32 Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand command, bool impersonate, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x623f5  pop
0x623f6  leave.s  loc_62404
0x623f8  ldloc.s  7
0x623fa  brfalse.s loc_62403
0x623fc  ldloc.s  7
0x623fe  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x62403  endfinally
0x62404  ldloc.3
0x62405  ldc.i4.1
0x62406  add
0x62407  stloc.3
0x62408  ldloc.3
0x62409  ldc.i4.s 0x64
0x6240b  mul
0x6240c  stloc.s  4
0x6240e  ldloc.1
0x6240f  ldloc.s  4
0x62411  call     T0x2B00011D
0x62416  ldc.i4.s 0x64
0x62418  call     T0x2B00011E
0x6241d  call     T0x2B000119
0x62422  stloc.s  5
0x62424  ldloc.s  5
0x62426  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.Crm.Data.PropertyEntry>::get_Count()
0x6242b  ldc.i4.0
0x6242c  bgt      loc_62333
0x62431  ret
```
