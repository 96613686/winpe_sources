# Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteNonQuery

- ea: `0xd7c0`
- end: `0xd86d`
- name: `Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteNonQuery`
- size: `173`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x3c30`
- `0x17040`
- `0x17090`
- `0x170e0`
- `0x17130`
- `0x171e0`
- `0x172d0`

## callees

- `0xd7c0`
- `0xe170`

## pseudocode

```c

```

## disassembly

```asm
0xd7c0  ldarg.3
0xd7c1  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xd7c6  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xd7cb  brfalse.s loc_D7E7
0xd7cd  ldsfld   class [Microsoft.Crm.Core]Microsoft.Crm.Core.DataServices.Connection.CrmSqlAccesserFactory [Microsoft.Crm.Core]Microsoft.Crm.Core.DataServices.Connection.CrmSqlAccesserFactory::DefaultInstance
0xd7d2  ldarg.3
0xd7d3  ldc.i4.0
0xd7d4  ldc.i4.0
0xd7d5  ldc.i4.0
0xd7d6  ldnull
0xd7d7  ldc.i4.0
0xd7d8  ldc.i4.0
0xd7d9  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.ISqlDataAccess [Microsoft.Crm.Core]Microsoft.Crm.Core.DataServices.Connection.CrmSqlAccesserFactory::Get(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ConnectionAccessType, int32, string, bool, int32)
0xd7de  ldarg.1
0xd7df  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.ISqlDataAccess::ExecuteNonQuery(class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo)
0xd7e4  stloc.0
0xd7e5  br.s     loc_D7F2
0xd7e7  ldstr    aInputParameter// "Input parameter OrganizationId is Empty"...
0xd7ec  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0xd7f1  throw
0xd7f2  ldarga.s 2
0xd7f4  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0xd7f9  brfalse.s loc_D86B
0xd7fb  ldloc.0
0xd7fc  ldarga.s 2
0xd7fe  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0xd803  beq.s    loc_D86B
0xd805  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xd80a  ldstr    a0UnexpectedNum_0// "{0}: Unexpected number of records affec"...
0xd80f  ldc.i4.6
0xd810  newarr   [mscorlib]System.Object
0xd815  dup
0xd816  ldc.i4.0
0xd817  ldarg.0
0xd818  callvirt instance string Microsoft.Crm.Asynchronous.DataAccessSharedBase::get_Name()
0xd81d  stelem.ref
0xd81e  dup
0xd81f  ldc.i4.1
0xd820  ldarga.s 2
0xd822  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0xd827  box      [mscorlib]System.Int32
0xd82c  stelem.ref
0xd82d  dup
0xd82e  ldc.i4.2
0xd82f  ldloc.0
0xd830  box      [mscorlib]System.Int32
0xd835  stelem.ref
0xd836  dup
0xd837  ldc.i4.3
0xd838  ldarg.3
0xd839  box      [mscorlib]System.Guid
0xd83e  stelem.ref
0xd83f  dup
0xd840  ldc.i4.4
0xd841  ldarg.1
0xd842  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::get_CommandTimeout()
0xd847  box      [mscorlib]System.Int32
0xd84c  stelem.ref
0xd84d  dup
0xd84e  ldc.i4.5
0xd84f  ldarg.1
0xd850  callvirt instance class [System.Data]System.Data.SqlClient.SqlCommand [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::get_Command()
0xd855  callvirt instance string [System.Data]System.Data.Common.DbCommand::get_CommandText()
0xd85a  stelem.ref
0xd85b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xd860  ldc.i4   0x80040216
0xd865  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0xd86a  throw
0xd86b  ldloc.0
0xd86c  ret
```
