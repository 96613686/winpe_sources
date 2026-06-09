# Microsoft.Crm.CrmLive.ConfigDB.ConfigDBSproc::SetLastAccessTime

- ea: `0x46230`
- end: `0x4636d`
- name: `Microsoft.Crm.CrmLive.ConfigDB.ConfigDBSproc::SetLastAccessTime`
- size: `317`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0xd620`
- `0x46230`
- `0x47f30`
- `0x47fc0`
- `0x48070`
- `0x48090`
- `0x48590`

## string_xrefs

- `0x462de`: `@LastAccessTime`
- `0x46321`: `@LastAccessServer`
- `0x46236`: `p_SetLastAccessTime`

## pseudocode

```c

```

## disassembly

```asm
0x46230  ldarg.0
0x46231  call     instance class Microsoft.Crm.CrmDbConnection Microsoft.Crm.CrmLive.ConfigDB.SprocBase::get_Connection()
0x46236  ldstr    aPSetlastaccess// "p_SetLastAccessTime"
0x4623b  callvirt instance class [System.Data]System.Data.IDbCommand Microsoft.Crm.CrmDbConnection::CreateCommand(string commandText)
0x46240  stloc.0
0x46241  ldloc.0
0x46242  ldc.i4.4
0x46243  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandType(valuetype [System.Data]System.Data.CommandType)
0x46248  ldloc.0
0x46249  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x4624e  newobj   instance void [System.Data]System.Data.SqlClient.SqlParameter::.ctor()
0x46253  stloc.1
0x46254  ldloc.1
0x46255  ldc.i4.1
0x46256  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Direction(valuetype [System.Data]System.Data.ParameterDirection)
0x4625b  ldloc.1
0x4625c  ldstr    aOrganizationid_2// "@OrganizationId"
0x46261  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_ParameterName(string)
0x46266  ldloc.1
0x46267  ldc.i4.0
0x46268  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Size(int32)
0x4626d  ldloc.1
0x4626e  ldc.i4.s 0xE
0x46270  callvirt instance void [System.Data]System.Data.SqlClient.SqlParameter::set_SqlDbType(valuetype [System.Data]System.Data.SqlDbType)
0x46275  ldloc.1
0x46276  ldarg.0
0x46277  ldarg.1
0x46278  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x4627d  call     instance object Microsoft.Crm.CrmLive.ConfigDB.SprocBase::Guid2Value(valuetype [mscorlib]System.Guid value, object default)
0x46282  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x46287  dup
0x46288  ldloc.1
0x46289  callvirt instance int32 [mscorlib]System.Collections.IList::Add(object)
0x4628e  pop
0x4628f  newobj   instance void [System.Data]System.Data.SqlClient.SqlParameter::.ctor()
0x46294  stloc.2
0x46295  ldloc.2
0x46296  ldc.i4.1
0x46297  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Direction(valuetype [System.Data]System.Data.ParameterDirection)
0x4629c  ldloc.2
0x4629d  ldstr    aCrmuserid_1// "@CrmUserId"
0x462a2  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_ParameterName(string)
0x462a7  ldloc.2
0x462a8  ldc.i4.0
0x462a9  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Size(int32)
0x462ae  ldloc.2
0x462af  ldc.i4.s 0xE
0x462b1  callvirt instance void [System.Data]System.Data.SqlClient.SqlParameter::set_SqlDbType(valuetype [System.Data]System.Data.SqlDbType)
0x462b6  ldloc.2
0x462b7  ldarg.0
0x462b8  ldarg.2
0x462b9  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x462be  call     instance object Microsoft.Crm.CrmLive.ConfigDB.SprocBase::Guid2Value(valuetype [mscorlib]System.Guid value, object default)
0x462c3  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x462c8  dup
0x462c9  ldloc.2
0x462ca  callvirt instance int32 [mscorlib]System.Collections.IList::Add(object)
0x462cf  pop
0x462d0  newobj   instance void [System.Data]System.Data.SqlClient.SqlParameter::.ctor()
0x462d5  stloc.3
0x462d6  ldloc.3
0x462d7  ldc.i4.1
0x462d8  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Direction(valuetype [System.Data]System.Data.ParameterDirection)
0x462dd  ldloc.3
0x462de  ldstr    aLastaccesstime_0// "@LastAccessTime"
0x462e3  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_ParameterName(string)
0x462e8  ldloc.3
0x462e9  ldc.i4.0
0x462ea  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Size(int32)
0x462ef  ldloc.3
0x462f0  ldc.i4.4
0x462f1  callvirt instance void [System.Data]System.Data.SqlClient.SqlParameter::set_SqlDbType(valuetype [System.Data]System.Data.SqlDbType)
0x462f6  ldloc.3
0x462f7  ldarg.0
0x462f8  ldarg.3
0x462f9  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x462fe  call     instance object Microsoft.Crm.CrmLive.ConfigDB.SprocBase::DateTime2Value(valuetype [mscorlib]System.DateTime value, object default)
0x46303  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x46308  dup
0x46309  ldloc.3
0x4630a  callvirt instance int32 [mscorlib]System.Collections.IList::Add(object)
0x4630f  pop
0x46310  newobj   instance void [System.Data]System.Data.SqlClient.SqlParameter::.ctor()
0x46315  stloc.s  4
0x46317  ldloc.s  4
0x46319  ldc.i4.1
0x4631a  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Direction(valuetype [System.Data]System.Data.ParameterDirection)
0x4631f  ldloc.s  4
0x46321  ldstr    aLastaccessserv// "@LastAccessServer"
0x46326  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_ParameterName(string)
0x4632b  ldloc.s  4
0x4632d  ldc.i4.0
0x4632e  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Size(int32)
0x46333  ldloc.s  4
0x46335  ldc.i4.s 0xC
0x46337  callvirt instance void [System.Data]System.Data.SqlClient.SqlParameter::set_SqlDbType(valuetype [System.Data]System.Data.SqlDbType)
0x4633c  ldloc.s  4
0x4633e  ldarg.0
0x4633f  ldarg.s  4
0x46341  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x46346  call     instance object Microsoft.Crm.CrmLive.ConfigDB.SprocBase::String2Value(string value, object default)
0x4634b  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x46350  ldloc.s  4
0x46352  callvirt instance int32 [mscorlib]System.Collections.IList::Add(object)
0x46357  pop
0x46358  ldarg.0
0x46359  ldloc.0
0x4635a  call     instance int32 Microsoft.Crm.CrmLive.ConfigDB.SprocBase::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand command)
0x4635f  pop
0x46360  leave.s  loc_4636C
0x46362  ldloc.0
0x46363  brfalse.s loc_4636B
0x46365  ldloc.0
0x46366  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4636b  endfinally
0x4636c  ret
```
