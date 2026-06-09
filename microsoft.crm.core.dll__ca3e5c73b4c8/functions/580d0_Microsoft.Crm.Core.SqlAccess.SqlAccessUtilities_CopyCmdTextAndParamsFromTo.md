# Microsoft.Crm.Core.SqlAccess.SqlAccessUtilities::CopyCmdTextAndParamsFromTo

- ea: `0x580d0`
- end: `0x581ca`
- name: `Microsoft.Crm.Core.SqlAccess.SqlAccessUtilities::CopyCmdTextAndParamsFromTo`
- size: `250`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xe9a0`
- `0xe9e0`
- `0x580b0`

## callees

- `0x580d0`

## string_xrefs

- `0x580d1`: `dbSourceCommand`
- `0x580dc`: `dbDestinationCommand`

## pseudocode

```c

```

## disassembly

```asm
0x580d0  ldarg.0
0x580d1  ldstr    aDbsourcecomman// "dbSourceCommand"
0x580d6  call     T0x2B000044
0x580db  ldarg.1
0x580dc  ldstr    aDbdestinationc// "dbDestinationCommand"
0x580e1  call     T0x2B000044
0x580e6  ldarg.1
0x580e7  ldarg.0
0x580e8  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0x580ed  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x580f2  ldarg.1
0x580f3  ldarg.0
0x580f4  callvirt instance valuetype [System.Data]System.Data.CommandType [System.Data]System.Data.IDbCommand::get_CommandType()
0x580f9  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandType(valuetype [System.Data]System.Data.CommandType)
0x580fe  ldarg.0
0x580ff  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x58104  isinst   [System.Data]System.Data.SqlClient.SqlParameterCollection
0x58109  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Data]System.Data.Common.DbParameterCollection::GetEnumerator()
0x5810e  stloc.0
0x5810f  br       loc_581AB
0x58114  ldloc.0
0x58115  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x5811a  castclass [System.Data]System.Data.SqlClient.SqlParameter
0x5811f  stloc.1
0x58120  newobj   instance void [System.Data]System.Data.SqlClient.SqlParameter::.ctor()
0x58125  dup
0x58126  ldloc.1
0x58127  callvirt instance string [System.Data]System.Data.Common.DbParameter::get_ParameterName()
0x5812c  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_ParameterName(string)
0x58131  dup
0x58132  ldloc.1
0x58133  callvirt instance valuetype [System.Data]System.Data.SqlDbType [System.Data]System.Data.SqlClient.SqlParameter::get_SqlDbType()
0x58138  callvirt instance void [System.Data]System.Data.SqlClient.SqlParameter::set_SqlDbType(valuetype [System.Data]System.Data.SqlDbType)
0x5813d  dup
0x5813e  ldloc.1
0x5813f  callvirt instance int32 [System.Data]System.Data.Common.DbParameter::get_Size()
0x58144  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Size(int32)
0x58149  dup
0x5814a  ldloc.1
0x5814b  callvirt instance string [System.Data]System.Data.Common.DbParameter::get_SourceColumn()
0x58150  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_SourceColumn(string)
0x58155  dup
0x58156  ldloc.1
0x58157  callvirt instance object [System.Data]System.Data.Common.DbParameter::get_Value()
0x5815c  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x58161  dup
0x58162  ldloc.1
0x58163  callvirt instance valuetype [System.Data]System.Data.ParameterDirection [System.Data]System.Data.Common.DbParameter::get_Direction()
0x58168  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Direction(valuetype [System.Data]System.Data.ParameterDirection)
0x5816d  dup
0x5816e  ldloc.1
0x5816f  callvirt instance int32 [System.Data]System.Data.SqlClient.SqlParameter::get_Offset()
0x58174  callvirt instance void [System.Data]System.Data.SqlClient.SqlParameter::set_Offset(int32)
0x58179  dup
0x5817a  ldloc.1
0x5817b  callvirt instance valuetype [System.Data]System.Data.DataRowVersion [System.Data]System.Data.Common.DbParameter::get_SourceVersion()
0x58180  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_SourceVersion(valuetype [System.Data]System.Data.DataRowVersion)
0x58185  dup
0x58186  ldloc.1
0x58187  callvirt instance bool [System.Data]System.Data.Common.DbParameter::get_SourceColumnNullMapping()
0x5818c  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_SourceColumnNullMapping(bool)
0x58191  dup
0x58192  ldloc.1
0x58193  callvirt instance bool [System.Data]System.Data.Common.DbParameter::get_IsNullable()
0x58198  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_IsNullable(bool)
0x5819d  stloc.2
0x5819e  ldarg.1
0x5819f  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x581a4  ldloc.2
0x581a5  callvirt instance int32 [mscorlib]System.Collections.IList::Add(object)
0x581aa  pop
0x581ab  ldloc.0
0x581ac  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x581b1  brtrue   loc_58114
0x581b6  leave.s  loc_581C9
0x581b8  ldloc.0
0x581b9  isinst   [mscorlib]System.IDisposable
0x581be  stloc.3
0x581bf  ldloc.3
0x581c0  brfalse.s loc_581C8
0x581c2  ldloc.3
0x581c3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x581c8  endfinally
0x581c9  ret
```
