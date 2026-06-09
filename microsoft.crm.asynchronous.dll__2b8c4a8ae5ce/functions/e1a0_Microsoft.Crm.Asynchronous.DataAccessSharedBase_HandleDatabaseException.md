# Microsoft.Crm.Asynchronous.DataAccessSharedBase::HandleDatabaseException

- ea: `0xe1a0`
- end: `0xe1e8`
- name: `Microsoft.Crm.Asynchronous.DataAccessSharedBase::HandleDatabaseException`
- size: `72`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0xda20`
- `0xe2a0`
- `0xe390`
- `0xe3e0`

## pseudocode

```c

```

## disassembly

```asm
0xe1a0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xe1a5  ldarg.3
0xe1a6  ldc.i4.1
0xe1a7  newarr   [mscorlib]System.Object
0xe1ac  dup
0xe1ad  ldc.i4.0
0xe1ae  ldarg.s  4
0xe1b0  box      [mscorlib]System.Guid
0xe1b5  stelem.ref
0xe1b6  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xe1bb  starg.s  3
0xe1bd  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xe1c2  ldstr    a01_0// "{0}: {1}"
0xe1c7  ldc.i4.2
0xe1c8  newarr   [mscorlib]System.Object
0xe1cd  dup
0xe1ce  ldc.i4.0
0xe1cf  ldarg.s  5
0xe1d1  stelem.ref
0xe1d2  dup
0xe1d3  ldc.i4.1
0xe1d4  ldarg.3
0xe1d5  stelem.ref
0xe1d6  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xe1db  stloc.0
0xe1dc  ldarg.1
0xe1dd  ldarg.2
0xe1de  ldloc.0
0xe1df  ldc.i4.s 0x15
0xe1e1  ldc.i4.1
0xe1e2  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::HandleException(class [mscorlib]System.Exception, class [System.Data]System.Data.IDbCommand, string, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, valuetype [System]System.Diagnostics.TraceLevel)
0xe1e7  ret
```
