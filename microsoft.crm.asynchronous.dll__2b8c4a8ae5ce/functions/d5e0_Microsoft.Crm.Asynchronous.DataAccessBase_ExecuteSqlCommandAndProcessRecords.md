# Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteSqlCommandAndProcessRecords

- ea: `0xd5e0`
- end: `0xd654`
- name: `Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteSqlCommandAndProcessRecords`
- size: `116`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0xd5e0`
- `0xd9b0`
- `0xe170`
- `0xe180`

## pseudocode

```c

```

## disassembly

```asm
0xd5e0  ldarg.0
0xd5e1  ldarg.1
0xd5e2  ldarg.2
0xd5e3  ldloca.s 0
0xd5e5  call     instance int32 Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteSqlCommandAndProcessRecords(class [System.Data]System.Data.IDbCommand command, class RecordProcessor recordProcessor, [out] string& databaseName)
0xd5ea  stloc.1
0xd5eb  ldloc.1
0xd5ec  ldarg.3
0xd5ed  beq.s    loc_D653
0xd5ef  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xd5f4  ldstr    a0UnexpectedNum// "{0}: Unexpected number of records selec"...
0xd5f9  ldc.i4.7
0xd5fa  newarr   [mscorlib]System.Object
0xd5ff  dup
0xd600  ldc.i4.0
0xd601  ldarg.0
0xd602  callvirt instance string Microsoft.Crm.Asynchronous.DataAccessSharedBase::get_Name()
0xd607  stelem.ref
0xd608  dup
0xd609  ldc.i4.1
0xd60a  ldarg.3
0xd60b  box      [mscorlib]System.Int32
0xd610  stelem.ref
0xd611  dup
0xd612  ldc.i4.2
0xd613  ldloc.1
0xd614  box      [mscorlib]System.Int32
0xd619  stelem.ref
0xd61a  dup
0xd61b  ldc.i4.3
0xd61c  ldarg.1
0xd61d  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0xd622  stelem.ref
0xd623  dup
0xd624  ldc.i4.4
0xd625  ldloc.0
0xd626  stelem.ref
0xd627  dup
0xd628  ldc.i4.5
0xd629  ldarg.1
0xd62a  callvirt instance int32 [System.Data]System.Data.IDbCommand::get_CommandTimeout()
0xd62f  box      [mscorlib]System.Int32
0xd634  stelem.ref
0xd635  dup
0xd636  ldc.i4.6
0xd637  ldarg.0
0xd638  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.DataAccessSharedBase::get_OrganizationId()
0xd63d  box      [mscorlib]System.Guid
0xd642  stelem.ref
0xd643  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xd648  ldc.i4   0x80040216
0xd64d  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0xd652  throw
0xd653  ret
```
