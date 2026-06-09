# Microsoft.Crm.Asynchronous.ImportDataAccess::RetrieveParsedDataWithCondition

- ea: `0x4b60`
- end: `0x4c9d`
- name: `Microsoft.Crm.Asynchronous.ImportDataAccess::RetrieveParsedDataWithCondition`
- size: `317`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x19ee0`

## callees

- `0x4b60`
- `0x1fe90`

## pseudocode

```c

```

## disassembly

```asm
0x4b60  newobj   instance void <>c__DisplayClass35_0::.ctor()
0x4b65  stloc.0
0x4b66  ldloc.0
0x4b67  ldarg.3
0x4b68  stfld    string <>c__DisplayClass35_0::columnName
0x4b6d  ldloc.0
0x4b6e  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.ParsedDataRow>::.ctor()
0x4b73  stfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.ParsedDataRow> <>c__DisplayClass35_0::parsedDataRowArray
0x4b78  ldarg.s  4
0x4b7a  brfalse.s loc_4B81
0x4b7c  ldarg.s  4
0x4b7e  ldlen
0x4b7f  brtrue.s loc_4B88
0x4b81  ldloc.0
0x4b82  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.ParsedDataRow> <>c__DisplayClass35_0::parsedDataRowArray
0x4b87  ret
0x4b88  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x4b8d  stloc.1
0x4b8e  ldc.i4.0
0x4b8f  stloc.2
0x4b90  br.s     loc_4BC1
0x4b92  ldloc.1
0x4b93  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4b98  ldstr    aKey0// "@Key{0}, "
0x4b9d  ldc.i4.1
0x4b9e  newarr   [mscorlib]System.Object
0x4ba3  dup
0x4ba4  ldc.i4.0
0x4ba5  ldloca.s 2
0x4ba7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4bac  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x4bb1  stelem.ref
0x4bb2  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4bb7  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4bbc  pop
0x4bbd  ldloc.2
0x4bbe  ldc.i4.1
0x4bbf  add
0x4bc0  stloc.2
0x4bc1  ldloc.2
0x4bc2  ldarg.s  4
0x4bc4  ldlen
0x4bc5  conv.i4
0x4bc6  ldc.i4.1
0x4bc7  sub
0x4bc8  blt.s    loc_4B92
0x4bca  ldloc.1
0x4bcb  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4bd0  ldstr    aKey0_0// "@Key{0}"
0x4bd5  ldc.i4.1
0x4bd6  newarr   [mscorlib]System.Object
0x4bdb  dup
0x4bdc  ldc.i4.0
0x4bdd  ldloca.s 2
0x4bdf  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4be4  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x4be9  stelem.ref
0x4bea  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4bef  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4bf4  pop
0x4bf5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4bfa  ldstr    aSelectImportda// "SELECT ImportDataId, {3}0, IsExistingRe"...
0x4bff  ldc.i4.4
0x4c00  newarr   [mscorlib]System.Object
0x4c05  dup
0x4c06  ldc.i4.0
0x4c07  ldloc.0
0x4c08  ldfld    string <>c__DisplayClass35_0::columnName
0x4c0d  stelem.ref
0x4c0e  dup
0x4c0f  ldc.i4.1
0x4c10  ldarg.1
0x4c11  stelem.ref
0x4c12  dup
0x4c13  ldc.i4.2
0x4c14  ldloc.1
0x4c15  callvirt instance string [mscorlib]System.Object::ToString()
0x4c1a  stelem.ref
0x4c1b  dup
0x4c1c  ldc.i4.3
0x4c1d  ldarg.2
0x4c1e  stelem.ref
0x4c1f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4c24  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand(string)
0x4c29  stloc.3
0x4c2a  ldloc.3
0x4c2b  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x4c30  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x4c35  stloc.s  4
0x4c37  ldc.i4.0
0x4c38  stloc.2
0x4c39  br.s     loc_4C6F
0x4c3b  ldloc.s  4
0x4c3d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4c42  ldstr    aKey0_0// "@Key{0}"
0x4c47  ldc.i4.1
0x4c48  newarr   [mscorlib]System.Object
0x4c4d  dup
0x4c4e  ldc.i4.0
0x4c4f  ldloca.s 2
0x4c51  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4c56  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x4c5b  stelem.ref
0x4c5c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4c61  ldarg.s  4
0x4c63  ldloc.2
0x4c64  ldelem.ref
0x4c65  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x4c6a  pop
0x4c6b  ldloc.2
0x4c6c  ldc.i4.1
0x4c6d  add
0x4c6e  stloc.2
0x4c6f  ldloc.2
0x4c70  ldarg.s  4
0x4c72  ldlen
0x4c73  conv.i4
0x4c74  blt.s    loc_4C3B
0x4c76  ldarg.0
0x4c77  ldloc.3
0x4c78  ldloc.0
0x4c79  ldftn    instance void <>c__DisplayClass35_0::<RetrieveParsedDataWithCondition>b__0(object[] values)
0x4c7f  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor::.ctor(object, native int)
0x4c84  call     instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteSqlCommandAndProcessRecords(class [System.Data]System.Data.IDbCommand, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor)
0x4c89  pop
0x4c8a  leave.s  loc_4C96
0x4c8c  ldloc.3
0x4c8d  brfalse.s loc_4C95
0x4c8f  ldloc.3
0x4c90  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4c95  endfinally
0x4c96  ldloc.0
0x4c97  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.ParsedDataRow> <>c__DisplayClass35_0::parsedDataRowArray
0x4c9c  ret
```
