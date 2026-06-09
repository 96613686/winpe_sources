# Microsoft.Crm.Asynchronous.DataAccessSharedBase::ExecuteSqlCommand

- ea: `0xe200`
- end: `0xe289`
- name: `Microsoft.Crm.Asynchronous.DataAccessSharedBase::ExecuteSqlCommand`
- size: `137`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0xe170`
- `0xe180`
- `0xe200`
- `0xe3e0`

## pseudocode

```c

```

## disassembly

```asm
0xe200  ldarg.0
0xe201  ldarg.1
0xe202  ldloca.s 0
0xe204  call     instance int32 Microsoft.Crm.Asynchronous.DataAccessSharedBase::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand command, [out] string& databaseName)
0xe209  stloc.1
0xe20a  ldarga.s 2
0xe20c  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0xe211  brfalse.s loc_E287
0xe213  ldloc.1
0xe214  ldarga.s 2
0xe216  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0xe21b  beq.s    loc_E287
0xe21d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xe222  ldstr    a0UnexpectedNum_1// "{0}: Unexpected number of records affec"...
0xe227  ldc.i4.7
0xe228  newarr   [mscorlib]System.Object
0xe22d  dup
0xe22e  ldc.i4.0
0xe22f  ldarg.0
0xe230  callvirt instance string Microsoft.Crm.Asynchronous.DataAccessSharedBase::get_Name()
0xe235  stelem.ref
0xe236  dup
0xe237  ldc.i4.1
0xe238  ldarga.s 2
0xe23a  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0xe23f  box      [mscorlib]System.Int32
0xe244  stelem.ref
0xe245  dup
0xe246  ldc.i4.2
0xe247  ldloc.1
0xe248  box      [mscorlib]System.Int32
0xe24d  stelem.ref
0xe24e  dup
0xe24f  ldc.i4.3
0xe250  ldarg.1
0xe251  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0xe256  stelem.ref
0xe257  dup
0xe258  ldc.i4.4
0xe259  ldloc.0
0xe25a  stelem.ref
0xe25b  dup
0xe25c  ldc.i4.5
0xe25d  ldarg.1
0xe25e  callvirt instance int32 [System.Data]System.Data.IDbCommand::get_CommandTimeout()
0xe263  box      [mscorlib]System.Int32
0xe268  stelem.ref
0xe269  dup
0xe26a  ldc.i4.6
0xe26b  ldarg.0
0xe26c  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.DataAccessSharedBase::get_OrganizationId()
0xe271  box      [mscorlib]System.Guid
0xe276  stelem.ref
0xe277  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xe27c  ldc.i4   0x80040216
0xe281  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0xe286  throw
0xe287  ldloc.1
0xe288  ret
```
