# Microsoft.Crm.Asynchronous.ImportDataAccess::RetrieveMaxLength

- ea: `0x4ab0`
- end: `0x4b55`
- name: `Microsoft.Crm.Asynchronous.ImportDataAccess::RetrieveMaxLength`
- size: `165`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1cf60`

## callees

- `0x4ab0`
- `0x1fe30`

## pseudocode

```c

```

## disassembly

```asm
0x4ab0  newobj   instance void <>c__DisplayClass34_0::.ctor()
0x4ab5  stloc.0
0x4ab6  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x4abb  stloc.1
0x4abc  ldarg.s  5
0x4abe  brfalse.s loc_4AFA
0x4ac0  ldloc.1
0x4ac1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4ac6  ldstr    aSelectMaxDatal// "SELECT MAX(DATALENGTH(A.{0})) FROM {1} "...
0x4acb  ldc.i4.3
0x4acc  newarr   [mscorlib]System.Object
0x4ad1  dup
0x4ad2  ldc.i4.0
0x4ad3  ldarg.2
0x4ad4  stelem.ref
0x4ad5  dup
0x4ad6  ldc.i4.1
0x4ad7  ldarg.1
0x4ad8  stelem.ref
0x4ad9  dup
0x4ada  ldc.i4.2
0x4adb  ldarg.s  4
0x4add  box      [mscorlib]System.Int32
0x4ae2  stelem.ref
0x4ae3  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x4ae8  pop
0x4ae9  ldarg.3
0x4aea  brfalse.s loc_4B19
0x4aec  ldloc.1
0x4aed  ldstr    aAndAIsexisting// " AND A.IsExistingRecord='0'"
0x4af2  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4af7  pop
0x4af8  br.s     loc_4B19
0x4afa  ldloc.1
0x4afb  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4b00  ldstr    aSelectMaxDatal_0// "SELECT MAX(DATALENGTH({0})) FROM {1}"
0x4b05  ldc.i4.2
0x4b06  newarr   [mscorlib]System.Object
0x4b0b  dup
0x4b0c  ldc.i4.0
0x4b0d  ldarg.2
0x4b0e  stelem.ref
0x4b0f  dup
0x4b10  ldc.i4.1
0x4b11  ldarg.1
0x4b12  stelem.ref
0x4b13  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x4b18  pop
0x4b19  ldloc.0
0x4b1a  ldc.i4.0
0x4b1b  stfld    int32 <>c__DisplayClass34_0::maxLength
0x4b20  ldloc.1
0x4b21  callvirt instance string [mscorlib]System.Object::ToString()
0x4b26  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand(string)
0x4b2b  stloc.2
0x4b2c  ldarg.0
0x4b2d  ldloc.2
0x4b2e  ldloc.0
0x4b2f  ldftn    instance void <>c__DisplayClass34_0::<RetrieveMaxLength>b__0(object[] values)
0x4b35  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor::.ctor(object, native int)
0x4b3a  call     instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteSqlCommandAndProcessRecords(class [System.Data]System.Data.IDbCommand, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor)
0x4b3f  pop
0x4b40  leave.s  loc_4B4C
0x4b42  ldloc.2
0x4b43  brfalse.s loc_4B4B
0x4b45  ldloc.2
0x4b46  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4b4b  endfinally
0x4b4c  ldloc.0
0x4b4d  ldfld    int32 <>c__DisplayClass34_0::maxLength
0x4b52  ldc.i4.2
0x4b53  div
0x4b54  ret
```
