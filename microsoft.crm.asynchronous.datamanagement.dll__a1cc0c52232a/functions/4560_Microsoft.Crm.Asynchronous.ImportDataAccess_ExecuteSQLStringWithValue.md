# Microsoft.Crm.Asynchronous.ImportDataAccess::ExecuteSQLStringWithValue

- ea: `0x4560`
- end: `0x459b`
- name: `Microsoft.Crm.Asynchronous.ImportDataAccess::ExecuteSQLStringWithValue`
- size: `59`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xba70`

## callees

- `0x4560`

## pseudocode

```c

```

## disassembly

```asm
0x4560  ldnull
0x4561  stloc.0
0x4562  ldarg.1
0x4563  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand(string)
0x4568  stloc.2
0x4569  ldarg.0
0x456a  ldloc.2
0x456b  call     instance object [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::ExecuteSqlCommand(class [System.Data]System.Data.IDbCommand)
0x4570  stloc.0
0x4571  leave.s  loc_457D
0x4573  ldloc.2
0x4574  brfalse.s loc_457C
0x4576  ldloc.2
0x4577  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x457c  endfinally
0x457d  ldloc.0
0x457e  callvirt instance string [mscorlib]System.Object::ToString()
0x4583  stloc.1
0x4584  ldloc.1
0x4585  callvirt instance int32 [mscorlib]System.String::get_Length()
0x458a  ldc.i4.0
0x458b  ble.s    loc_4599
0x458d  ldloc.1
0x458e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4593  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x4598  ret
0x4599  ldc.i4.0
0x459a  ret
```
