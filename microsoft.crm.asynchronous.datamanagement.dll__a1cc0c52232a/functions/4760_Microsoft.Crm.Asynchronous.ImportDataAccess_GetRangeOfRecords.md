# Microsoft.Crm.Asynchronous.ImportDataAccess::GetRangeOfRecords

- ea: `0x4760`
- end: `0x47d5`
- name: `Microsoft.Crm.Asynchronous.ImportDataAccess::GetRangeOfRecords`
- size: `117`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0xe550`
- `0x10b00`

## callees

- `0x4760`
- `0x1fc60`

## pseudocode

```c

```

## disassembly

```asm
0x4760  newobj   instance void <>c__DisplayClass28_0::.ctor()
0x4765  stloc.0
0x4766  ldloc.0
0x4767  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<object[]>::.ctor()
0x476c  stfld    class [mscorlib]System.Collections.Generic.List`1<object[]> <>c__DisplayClass28_0::recList
0x4771  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4776  ldstr    aSelectAFrom0As// "SELECT A.* FROM {0} as A, ImportDataBas"...
0x477b  ldc.i4.3
0x477c  newarr   [mscorlib]System.Object
0x4781  dup
0x4782  ldc.i4.0
0x4783  ldarg.1
0x4784  stelem.ref
0x4785  dup
0x4786  ldc.i4.1
0x4787  ldarga.s 2
0x4789  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x478e  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x4793  stelem.ref
0x4794  dup
0x4795  ldc.i4.2
0x4796  ldarga.s 3
0x4798  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x479d  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x47a2  stelem.ref
0x47a3  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x47a8  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand(string)
0x47ad  stloc.1
0x47ae  ldarg.0
0x47af  ldloc.1
0x47b0  ldloc.0
0x47b1  ldftn    instance void <>c__DisplayClass28_0::<GetRangeOfRecords>b__0(object[] values)
0x47b7  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor::.ctor(object, native int)
0x47bc  call     instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteSqlCommandAndProcessRecords(class [System.Data]System.Data.IDbCommand, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor)
0x47c1  pop
0x47c2  leave.s  loc_47CE
0x47c4  ldloc.1
0x47c5  brfalse.s loc_47CD
0x47c7  ldloc.1
0x47c8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x47cd  endfinally
0x47ce  ldloc.0
0x47cf  ldfld    class [mscorlib]System.Collections.Generic.List`1<object[]> <>c__DisplayClass28_0::recList
0x47d4  ret
```
