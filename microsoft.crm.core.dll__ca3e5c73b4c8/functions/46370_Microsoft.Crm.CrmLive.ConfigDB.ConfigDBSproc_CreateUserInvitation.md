# Microsoft.Crm.CrmLive.ConfigDB.ConfigDBSproc::CreateUserInvitation

- ea: `0x46370`
- end: `0x467dd`
- name: `Microsoft.Crm.CrmLive.ConfigDB.ConfigDBSproc::CreateUserInvitation`
- size: `1133`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callees

- `0xd620`
- `0x46370`
- `0x47f30`
- `0x47fc0`
- `0x48070`
- `0x48090`
- `0x480b0`
- `0x480d0`
- `0x48590`

## string_xrefs

- `0x46376`: `p_CreateUserInvitation`
- `0x464aa`: `@InvitationToken`

## pseudocode

```c

```

## disassembly

```asm
0x46370  ldarg.0
0x46371  call     instance class Microsoft.Crm.CrmDbConnection Microsoft.Crm.CrmLive.ConfigDB.SprocBase::get_Connection()
0x46376  ldstr    aPCreateuserinv// "p_CreateUserInvitation"
0x4637b  callvirt instance class [System.Data]System.Data.IDbCommand Microsoft.Crm.CrmDbConnection::CreateCommand(string commandText)
0x46380  stloc.0
0x46381  ldloc.0
0x46382  ldc.i4.4
0x46383  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandType(valuetype [System.Data]System.Data.CommandType)
0x46388  ldloc.0
0x46389  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x4638e  newobj   instance void [System.Data]System.Data.SqlClient.SqlParameter::.ctor()
0x46393  stloc.1
0x46394  ldloc.1
0x46395  ldc.i4.1
0x46396  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Direction(valuetype [System.Data]System.Data.ParameterDirection)
0x4639b  ldloc.1
0x4639c  ldstr    aId_1// "@Id"
0x463a1  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_ParameterName(string)
0x463a6  ldloc.1
0x463a7  ldc.i4.0
0x463a8  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Size(int32)
0x463ad  ldloc.1
0x463ae  ldc.i4.s 0xE
0x463b0  callvirt instance void [System.Data]System.Data.SqlClient.SqlParameter::set_SqlDbType(valuetype [System.Data]System.Data.SqlDbType)
0x463b5  ldloc.1
0x463b6  ldarg.0
0x463b7  ldarg.1
0x463b8  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x463bd  call     instance object Microsoft.Crm.CrmLive.ConfigDB.SprocBase::Guid2Value(valuetype [mscorlib]System.Guid value, object default)
0x463c2  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x463c7  dup
0x463c8  ldloc.1
0x463c9  callvirt instance int32 [mscorlib]System.Collections.IList::Add(object)
0x463ce  pop
0x463cf  newobj   instance void [System.Data]System.Data.SqlClient.SqlParameter::.ctor()
0x463d4  stloc.2
0x463d5  ldloc.2
0x463d6  ldc.i4.1
0x463d7  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Direction(valuetype [System.Data]System.Data.ParameterDirection)
0x463dc  ldloc.2
0x463dd  ldstr    aStatus// "@Status"
0x463e2  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_ParameterName(string)
0x463e7  ldloc.2
0x463e8  ldc.i4.0
0x463e9  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Size(int32)
0x463ee  ldloc.2
0x463ef  ldc.i4.8
0x463f0  callvirt instance void [System.Data]System.Data.SqlClient.SqlParameter::set_SqlDbType(valuetype [System.Data]System.Data.SqlDbType)
0x463f5  ldloc.2
0x463f6  ldarg.0
0x463f7  ldarg.2
0x463f8  ldc.i4.0
0x463f9  box      [mscorlib]System.Int32
0x463fe  call     instance object Microsoft.Crm.CrmLive.ConfigDB.SprocBase::Int2Value(int32 value, object default)
0x46403  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x46408  dup
0x46409  ldloc.2
0x4640a  callvirt instance int32 [mscorlib]System.Collections.IList::Add(object)
0x4640f  pop
0x46410  newobj   instance void [System.Data]System.Data.SqlClient.SqlParameter::.ctor()
0x46415  stloc.3
0x46416  ldloc.3
0x46417  ldc.i4.1
0x46418  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Direction(valuetype [System.Data]System.Data.ParameterDirection)
0x4641d  ldloc.3
0x4641e  ldstr    aEmailstatus// "@EmailStatus"
0x46423  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_ParameterName(string)
0x46428  ldloc.3
0x46429  ldc.i4.0
0x4642a  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Size(int32)
0x4642f  ldloc.3
0x46430  ldc.i4.8
0x46431  callvirt instance void [System.Data]System.Data.SqlClient.SqlParameter::set_SqlDbType(valuetype [System.Data]System.Data.SqlDbType)
0x46436  ldloc.3
0x46437  ldarg.0
0x46438  ldarg.3
0x46439  ldc.i4.0
0x4643a  box      [mscorlib]System.Int32
0x4643f  call     instance object Microsoft.Crm.CrmLive.ConfigDB.SprocBase::Int2Value(int32 value, object default)
0x46444  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x46449  dup
0x4644a  ldloc.3
0x4644b  callvirt instance int32 [mscorlib]System.Collections.IList::Add(object)
0x46450  pop
0x46451  newobj   instance void [System.Data]System.Data.SqlClient.SqlParameter::.ctor()
0x46456  stloc.s  4
0x46458  ldloc.s  4
0x4645a  ldc.i4.1
0x4645b  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Direction(valuetype [System.Data]System.Data.ParameterDirection)
0x46460  ldloc.s  4
0x46462  ldstr    aExpirationdate// "@ExpirationDate"
0x46467  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_ParameterName(string)
0x4646c  ldloc.s  4
0x4646e  ldc.i4.0
0x4646f  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Size(int32)
0x46474  ldloc.s  4
0x46476  ldc.i4.4
0x46477  callvirt instance void [System.Data]System.Data.SqlClient.SqlParameter::set_SqlDbType(valuetype [System.Data]System.Data.SqlDbType)
0x4647c  ldloc.s  4
0x4647e  ldarg.0
0x4647f  ldarg.s  4
0x46481  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x46486  call     instance object Microsoft.Crm.CrmLive.ConfigDB.SprocBase::DateTime2Value(valuetype [mscorlib]System.DateTime value, object default)
0x4648b  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x46490  dup
0x46491  ldloc.s  4
0x46493  callvirt instance int32 [mscorlib]System.Collections.IList::Add(object)
0x46498  pop
0x46499  newobj   instance void [System.Data]System.Data.SqlClient.SqlParameter::.ctor()
0x4649e  stloc.s  5
0x464a0  ldloc.s  5
0x464a2  ldc.i4.1
0x464a3  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Direction(valuetype [System.Data]System.Data.ParameterDirection)
0x464a8  ldloc.s  5
0x464aa  ldstr    aInvitationtoke// "@InvitationToken"
0x464af  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_ParameterName(string)
0x464b4  ldloc.s  5
0x464b6  ldc.i4.s 0x28
0x464b8  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Size(int32)
0x464bd  ldloc.s  5
0x464bf  ldc.i4.s 0xC
0x464c1  callvirt instance void [System.Data]System.Data.SqlClient.SqlParameter::set_SqlDbType(valuetype [System.Data]System.Data.SqlDbType)
0x464c6  ldloc.s  5
0x464c8  ldarg.0
0x464c9  ldarg.s  5
0x464cb  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x464d0  call     instance object Microsoft.Crm.CrmLive.ConfigDB.SprocBase::String2Value(string value, object default)
0x464d5  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x464da  dup
0x464db  ldloc.s  5
0x464dd  callvirt instance int32 [mscorlib]System.Collections.IList::Add(object)
0x464e2  pop
0x464e3  newobj   instance void [System.Data]System.Data.SqlClient.SqlParameter::.ctor()
0x464e8  stloc.s  6
0x464ea  ldloc.s  6
0x464ec  ldc.i4.1
0x464ed  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Direction(valuetype [System.Data]System.Data.ParameterDirection)
0x464f2  ldloc.s  6
0x464f4  ldstr    aUserid_1// "@UserId"
0x464f9  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_ParameterName(string)
0x464fe  ldloc.s  6
0x46500  ldc.i4.0
0x46501  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Size(int32)
0x46506  ldloc.s  6
0x46508  ldc.i4.s 0xE
0x4650a  callvirt instance void [System.Data]System.Data.SqlClient.SqlParameter::set_SqlDbType(valuetype [System.Data]System.Data.SqlDbType)
0x4650f  ldloc.s  6
0x46511  ldarg.0
0x46512  ldarg.s  6
0x46514  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x46519  call     instance object Microsoft.Crm.CrmLive.ConfigDB.SprocBase::Guid2Value(valuetype [mscorlib]System.Guid value, object default)
0x4651e  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x46523  dup
0x46524  ldloc.s  6
0x46526  callvirt instance int32 [mscorlib]System.Collections.IList::Add(object)
0x4652b  pop
0x4652c  newobj   instance void [System.Data]System.Data.SqlClient.SqlParameter::.ctor()
0x46531  stloc.s  7
0x46533  ldloc.s  7
0x46535  ldc.i4.1
0x46536  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Direction(valuetype [System.Data]System.Data.ParameterDirection)
0x4653b  ldloc.s  7
0x4653d  ldstr    aUseremail_1// "@UserEmail"
0x46542  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_ParameterName(string)
0x46547  ldloc.s  7
0x46549  ldc.i4   0x100
0x4654e  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Size(int32)
0x46553  ldloc.s  7
0x46555  ldc.i4.s 0xC
0x46557  callvirt instance void [System.Data]System.Data.SqlClient.SqlParameter::set_SqlDbType(valuetype [System.Data]System.Data.SqlDbType)
0x4655c  ldloc.s  7
0x4655e  ldarg.0
0x4655f  ldarg.s  7
0x46561  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x46566  call     instance object Microsoft.Crm.CrmLive.ConfigDB.SprocBase::String2Value(string value, object default)
0x4656b  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x46570  dup
0x46571  ldloc.s  7
0x46573  callvirt instance int32 [mscorlib]System.Collections.IList::Add(object)
0x46578  pop
0x46579  newobj   instance void [System.Data]System.Data.SqlClient.SqlParameter::.ctor()
0x4657e  stloc.s  8
0x46580  ldloc.s  8
0x46582  ldc.i4.1
0x46583  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Direction(valuetype [System.Data]System.Data.ParameterDirection)
0x46588  ldloc.s  8
0x4658a  ldstr    aUserfirstname// "@UserFirstName"
0x4658f  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_ParameterName(string)
0x46594  ldloc.s  8
0x46596  ldc.i4.s 0x40
0x46598  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Size(int32)
0x4659d  ldloc.s  8
0x4659f  ldc.i4.s 0xC
0x465a1  callvirt instance void [System.Data]System.Data.SqlClient.SqlParameter::set_SqlDbType(valuetype [System.Data]System.Data.SqlDbType)
0x465a6  ldloc.s  8
0x465a8  ldarg.0
0x465a9  ldarg.s  8
0x465ab  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x465b0  call     instance object Microsoft.Crm.CrmLive.ConfigDB.SprocBase::String2Value(string value, object default)
0x465b5  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x465ba  dup
0x465bb  ldloc.s  8
0x465bd  callvirt instance int32 [mscorlib]System.Collections.IList::Add(object)
0x465c2  pop
0x465c3  newobj   instance void [System.Data]System.Data.SqlClient.SqlParameter::.ctor()
0x465c8  stloc.s  9
0x465ca  ldloc.s  9
0x465cc  ldc.i4.1
0x465cd  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Direction(valuetype [System.Data]System.Data.ParameterDirection)
0x465d2  ldloc.s  9
0x465d4  ldstr    aUserlastname// "@UserLastName"
0x465d9  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_ParameterName(string)
0x465de  ldloc.s  9
0x465e0  ldc.i4.s 0x40
0x465e2  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Size(int32)
0x465e7  ldloc.s  9
0x465e9  ldc.i4.s 0xC
0x465eb  callvirt instance void [System.Data]System.Data.SqlClient.SqlParameter::set_SqlDbType(valuetype [System.Data]System.Data.SqlDbType)
0x465f0  ldloc.s  9
0x465f2  ldarg.0
0x465f3  ldarg.s  9
0x465f5  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x465fa  call     instance object Microsoft.Crm.CrmLive.ConfigDB.SprocBase::String2Value(string value, object default)
0x465ff  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x46604  dup
0x46605  ldloc.s  9
0x46607  callvirt instance int32 [mscorlib]System.Collections.IList::Add(object)
0x4660c  pop
0x4660d  newobj   instance void [System.Data]System.Data.SqlClient.SqlParameter::.ctor()
0x46612  stloc.s  0xA
0x46614  ldloc.s  0xA
0x46616  ldc.i4.1
0x46617  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Direction(valuetype [System.Data]System.Data.ParameterDirection)
0x4661c  ldloc.s  0xA
0x4661e  ldstr    aInitiatoruseri// "@InitiatorUserId"
0x46623  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_ParameterName(string)
0x46628  ldloc.s  0xA
0x4662a  ldc.i4.0
0x4662b  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Size(int32)
0x46630  ldloc.s  0xA
0x46632  ldc.i4.s 0xE
0x46634  callvirt instance void [System.Data]System.Data.SqlClient.SqlParameter::set_SqlDbType(valuetype [System.Data]System.Data.SqlDbType)
0x46639  ldloc.s  0xA
0x4663b  ldarg.0
0x4663c  ldarg.s  0xA
0x4663e  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x46643  call     instance object Microsoft.Crm.CrmLive.ConfigDB.SprocBase::Guid2Value(valuetype [mscorlib]System.Guid value, object default)
0x46648  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x4664d  dup
0x4664e  ldloc.s  0xA
0x46650  callvirt instance int32 [mscorlib]System.Collections.IList::Add(object)
0x46655  pop
0x46656  newobj   instance void [System.Data]System.Data.SqlClient.SqlParameter::.ctor()
0x4665b  stloc.s  0xB
0x4665d  ldloc.s  0xB
0x4665f  ldc.i4.1
0x46660  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Direction(valuetype [System.Data]System.Data.ParameterDirection)
0x46665  ldloc.s  0xB
0x46667  ldstr    aInitiatoremail// "@InitiatorEmail"
0x4666c  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_ParameterName(string)
0x46671  ldloc.s  0xB
0x46673  ldc.i4   0x100
0x46678  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Size(int32)
0x4667d  ldloc.s  0xB
0x4667f  ldc.i4.s 0xC
0x46681  callvirt instance void [System.Data]System.Data.SqlClient.SqlParameter::set_SqlDbType(valuetype [System.Data]System.Data.SqlDbType)
0x46686  ldloc.s  0xB
0x46688  ldarg.0
0x46689  ldarg.s  0xB
0x4668b  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x46690  call     instance object Microsoft.Crm.CrmLive.ConfigDB.SprocBase::String2Value(string value, object default)
0x46695  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x4669a  dup
0x4669b  ldloc.s  0xB
0x4669d  callvirt instance int32 [mscorlib]System.Collections.IList::Add(object)
0x466a2  pop
0x466a3  newobj   instance void [System.Data]System.Data.SqlClient.SqlParameter::.ctor()
0x466a8  stloc.s  0xC
0x466aa  ldloc.s  0xC
0x466ac  ldc.i4.1
0x466ad  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Direction(valuetype [System.Data]System.Data.ParameterDirection)
0x466b2  ldloc.s  0xC
0x466b4  ldstr    aInitiatorfirst// "@InitiatorFirstName"
0x466b9  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_ParameterName(string)
0x466be  ldloc.s  0xC
0x466c0  ldc.i4.s 0x40
0x466c2  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Size(int32)
0x466c7  ldloc.s  0xC
0x466c9  ldc.i4.s 0xC
0x466cb  callvirt instance void [System.Data]System.Data.SqlClient.SqlParameter::set_SqlDbType(valuetype [System.Data]System.Data.SqlDbType)
0x466d0  ldloc.s  0xC
0x466d2  ldarg.0
0x466d3  ldarg.s  0xC
0x466d5  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x466da  call     instance object Microsoft.Crm.CrmLive.ConfigDB.SprocBase::String2Value(string value, object default)
0x466df  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x466e4  dup
0x466e5  ldloc.s  0xC
0x466e7  callvirt instance int32 [mscorlib]System.Collections.IList::Add(object)
0x466ec  pop
  ... truncated ...
```
