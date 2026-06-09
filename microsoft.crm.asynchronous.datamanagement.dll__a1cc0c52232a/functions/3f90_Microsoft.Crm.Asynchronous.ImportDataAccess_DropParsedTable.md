# Microsoft.Crm.Asynchronous.ImportDataAccess::DropParsedTable

- ea: `0x3f90`
- end: `0x3fc3`
- name: `Microsoft.Crm.Asynchronous.ImportDataAccess::DropParsedTable`
- size: `51`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x5660`
- `0x14370`

## callees

- `0x3f90`
- `0x4540`

## pseudocode

```c

```

## disassembly

```asm
0x3f90  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3f95  ldstr    aIfExistsSelect_0// "IF EXISTS (SELECT 1 FROM dbo.sysobjects"...
0x3f9a  ldc.i4.1
0x3f9b  newarr   [mscorlib]System.Object
0x3fa0  dup
0x3fa1  ldc.i4.0
0x3fa2  ldarg.1
0x3fa3  stelem.ref
0x3fa4  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3fa9  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand(string)
0x3fae  stloc.0
0x3faf  ldarg.0
0x3fb0  ldloc.0
0x3fb1  call     instance void Microsoft.Crm.Asynchronous.ImportDataAccess::ExecuteSqlCommandWithNoExpectedRecords(class [System.Data]System.Data.IDbCommand sqlCommand)
0x3fb6  leave.s  loc_3FC2
0x3fb8  ldloc.0
0x3fb9  brfalse.s loc_3FC1
0x3fbb  ldloc.0
0x3fbc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3fc1  endfinally
0x3fc2  ret
```
