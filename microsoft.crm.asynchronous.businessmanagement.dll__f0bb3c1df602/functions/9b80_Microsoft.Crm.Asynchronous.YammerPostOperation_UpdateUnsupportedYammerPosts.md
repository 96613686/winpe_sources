# Microsoft.Crm.Asynchronous.YammerPostOperation::UpdateUnsupportedYammerPosts

- ea: `0x9b80`
- end: `0x9c9e`
- name: `Microsoft.Crm.Asynchronous.YammerPostOperation::UpdateUnsupportedYammerPosts`
- size: `286`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x9240`

## callees

- `0x9b80`

## string_xrefs

- `0x9b8c`: `Update [dbo].[PostBase] set [PostToYammer] = 0 where [PostId] IN ( {0} )`
- `0x9c77`: `UpdateUnsupportedYammerPosts`

## pseudocode

```c

```

## disassembly

```asm
0x9b80  ldarg.1
0x9b81  brfalse.s loc_9B8B
0x9b83  ldarg.1
0x9b84  call     T0x2B00001E
0x9b89  brtrue.s loc_9B8C
0x9b8b  ret
0x9b8c  ldstr    aUpdateDboPostb// "Update [dbo].[PostBase] set [PostToYamm"...
0x9b91  stloc.0
0x9b92  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x9b97  stloc.1
0x9b98  ldarg.0
0x9b99  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.YammerPostOperation::_organizationId
0x9b9e  ldc.i4.0
0x9b9f  ldc.i4.0
0x9ba0  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x9ba5  stloc.2
0x9ba6  ldloc.2
0x9ba7  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0x9bac  ldloc.2
0x9bad  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand()
0x9bb2  stloc.3
0x9bb3  ldloc.3
0x9bb4  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x9bb9  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x9bbe  stloc.s  4
0x9bc0  ldc.i4.0
0x9bc1  stloc.s  6
0x9bc3  ldarg.1
0x9bc4  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Guid>::GetEnumerator()
0x9bc9  stloc.s  7
0x9bcb  br.s     loc_9C2A
0x9bcd  ldloc.s  7
0x9bcf  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Guid>::get_Current()
0x9bd4  stloc.s  8
0x9bd6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9bdb  ldstr    aPostid0// "@postId{0}"
0x9be0  ldc.i4.1
0x9be1  newarr   [mscorlib]System.Object
0x9be6  dup
0x9be7  ldc.i4.0
0x9be8  ldloc.s  6
0x9bea  box      [mscorlib]System.Int32
0x9bef  stelem.ref
0x9bf0  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x9bf5  stloc.s  5
0x9bf7  ldloc.1
0x9bf8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9bfd  ldstr    a0_2// "{0},"
0x9c02  ldc.i4.1
0x9c03  newarr   [mscorlib]System.Object
0x9c08  dup
0x9c09  ldc.i4.0
0x9c0a  ldloc.s  5
0x9c0c  stelem.ref
0x9c0d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x9c12  pop
0x9c13  ldloc.s  4
0x9c15  ldloc.s  5
0x9c17  ldloc.s  8
0x9c19  box      [mscorlib]System.Guid
0x9c1e  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x9c23  pop
0x9c24  ldloc.s  6
0x9c26  ldc.i4.1
0x9c27  add
0x9c28  stloc.s  6
0x9c2a  ldloc.s  7
0x9c2c  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x9c31  brtrue.s loc_9BCD
0x9c33  leave.s  loc_9C41
0x9c35  ldloc.s  7
0x9c37  brfalse.s loc_9C40
0x9c39  ldloc.s  7
0x9c3b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x9c40  endfinally
0x9c41  ldloc.1
0x9c42  ldloc.1
0x9c43  callvirt instance int32 [mscorlib]System.Text.StringBuilder::get_Length()
0x9c48  ldc.i4.1
0x9c49  sub
0x9c4a  ldc.i4.1
0x9c4b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Remove(int32, int32)
0x9c50  pop
0x9c51  ldloc.3
0x9c52  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9c57  ldloc.0
0x9c58  ldc.i4.1
0x9c59  newarr   [mscorlib]System.Object
0x9c5e  dup
0x9c5f  ldc.i4.0
0x9c60  ldloc.1
0x9c61  callvirt instance string [mscorlib]System.Object::ToString()
0x9c66  stelem.ref
0x9c67  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x9c6c  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x9c71  ldloc.3
0x9c72  ldc.i4   0x301
0x9c77  ldstr    aUpdateunsuppor// "UpdateUnsupportedYammerPosts"
0x9c7c  ldstr    aDDbsShDccm2110_2// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0x9c81  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x9c86  pop
0x9c87  leave.s  loc_9C9D
0x9c89  ldloc.3
0x9c8a  brfalse.s loc_9C92
0x9c8c  ldloc.3
0x9c8d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x9c92  endfinally
0x9c93  ldloc.2
0x9c94  brfalse.s loc_9C9C
0x9c96  ldloc.2
0x9c97  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x9c9c  endfinally
0x9c9d  ret
```
