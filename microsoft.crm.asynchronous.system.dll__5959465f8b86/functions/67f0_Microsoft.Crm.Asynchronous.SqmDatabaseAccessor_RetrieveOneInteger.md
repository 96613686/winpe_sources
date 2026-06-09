# Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::RetrieveOneInteger

- ea: `0x67f0`
- end: `0x6826`
- name: `Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::RetrieveOneInteger`
- size: `54`
- prototype: ``
- caller_count: `12`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x6700`
- `0x6720`
- `0x6740`
- `0x6760`
- `0x6780`
- `0x67b0`
- `0x67d0`
- `0x6a70`
- `0x6a90`
- `0x6ab0`
- `0x6ad0`
- `0x6b40`

## callees

- `0x67f0`

## pseudocode

```c

```

## disassembly

```asm
0x67f0  ldc.i4.0
0x67f1  stloc.0
0x67f2  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x67f7  stloc.1
0x67f8  ldloc.1
0x67f9  ldarg.1
0x67fa  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x67ff  ldloc.1
0x6800  ldarg.2
0x6801  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandType(valuetype [System.Data]System.Data.CommandType)
0x6806  ldarg.0
0x6807  ldloc.1
0x6808  call     instance object [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::ExecuteSqlCommand(class [System.Data]System.Data.IDbCommand)
0x680d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6812  call     int32 [mscorlib]System.Convert::ToInt32(object, class [mscorlib]System.IFormatProvider)
0x6817  stloc.0
0x6818  leave.s  loc_6824
0x681a  ldloc.1
0x681b  brfalse.s loc_6823
0x681d  ldloc.1
0x681e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6823  endfinally
0x6824  ldloc.0
0x6825  ret
```
