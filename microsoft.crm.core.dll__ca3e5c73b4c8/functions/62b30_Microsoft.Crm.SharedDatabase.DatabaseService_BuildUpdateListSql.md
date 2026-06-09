# Microsoft.Crm.SharedDatabase.DatabaseService::BuildUpdateListSql

- ea: `0x62b30`
- end: `0x62d07`
- name: `Microsoft.Crm.SharedDatabase.DatabaseService::BuildUpdateListSql`
- size: `471`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x62b10`

## callees

- `0x1a880`
- `0x1be80`
- `0x44800`
- `0x44d80`
- `0x44da0`
- `0x5f120`
- `0x5f130`
- `0x5f140`
- `0x5f6e0`
- `0x607f0`
- `0x60820`
- `0x62b30`
- `0x63e60`
- `0x63ec0`
- `0x640b0`
- `0x64980`
- `0x649f0`

## string_xrefs

- `0x62be4`: `UPDATE {0} SET `

## pseudocode

```c

```

## disassembly

```asm
0x62b30  ldarg.1
0x62b31  ldstr    aColumnset// "columnSet"
0x62b36  call     void Microsoft.Crm.Exceptions::ThrowIfNull(object parameter, string name)
0x62b3b  ldarg.0
0x62b3c  ldfld    class [System.Data]System.Data.IDbCommand Microsoft.Crm.SharedDatabase.DatabaseService::_baseCommand
0x62b41  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x62b46  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x62b4b  stloc.0
0x62b4c  ldc.i4.1
0x62b4d  stloc.1
0x62b4e  ldarg.1
0x62b4f  callvirt instance class [mscorlib]System.Collections.IEnumerable Microsoft.Crm.Data.PropertyBag::get_PropertyEntries()
0x62b54  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x62b59  stloc.2
0x62b5a  br       loc_62CE5
0x62b5f  ldloc.2
0x62b60  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x62b65  unbox.any Microsoft.Crm.Data.PropertyEntry
0x62b6a  stloc.3
0x62b6b  ldnull
0x62b6c  stloc.s  4
0x62b6e  ldarg.0
0x62b6f  ldfld    class Microsoft.Crm.SharedDatabase.Table Microsoft.Crm.SharedDatabase.DatabaseService::_table
0x62b74  callvirt instance class Microsoft.Crm.SharedDatabase.ColumnCollection Microsoft.Crm.SharedDatabase.Table::get_Columns()
0x62b79  ldloca.s 3
0x62b7b  call     instance string Microsoft.Crm.Data.PropertyEntry::get_Name()
0x62b80  ldloca.s 4
0x62b82  callvirt instance bool class [System]System.Collections.Generic.SortedDictionary`2<string, class Microsoft.Crm.SharedDatabase.Column>::TryGetValue(var<u1>, !!T0)
0x62b87  brtrue.s loc_62BC1
0x62b89  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x62b8e  ldstr    aColumn0DoesNot// "Column '{0}' does not exist on Table '{"...
0x62b93  ldc.i4.2
0x62b94  newarr   [mscorlib]System.Object
0x62b99  dup
0x62b9a  ldc.i4.0
0x62b9b  ldloca.s 3
0x62b9d  call     instance string Microsoft.Crm.Data.PropertyEntry::get_Name()
0x62ba2  stelem.ref
0x62ba3  dup
0x62ba4  ldc.i4.1
0x62ba5  ldarg.0
0x62ba6  ldfld    class Microsoft.Crm.SharedDatabase.Table Microsoft.Crm.SharedDatabase.DatabaseService::_table
0x62bab  callvirt instance string Microsoft.Crm.SharedDatabase.Table::get_Name()
0x62bb0  stelem.ref
0x62bb1  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x62bb6  ldc.i4   0x80040216
0x62bbb  newobj   instance void Microsoft.Crm.CrmException::.ctor(string message, int32 errorCode)
0x62bc0  throw
0x62bc1  ldloc.s  4
0x62bc3  callvirt instance valuetype Microsoft.Crm.SharedDatabase.ConfigSchemaType Microsoft.Crm.SharedDatabase.Column::get_SchemaType()
0x62bc8  brtrue   loc_62CE5
0x62bcd  ldarg.0
0x62bce  ldloc.s  4
0x62bd0  ldloc.3
0x62bd1  call     instance void Microsoft.Crm.SharedDatabase.DatabaseService::Validate(class Microsoft.Crm.SharedDatabase.Column column, valuetype Microsoft.Crm.Data.PropertyEntry propertyEntry)
0x62bd6  ldloc.1
0x62bd7  brfalse.s loc_62C03
0x62bd9  ldarg.0
0x62bda  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.Crm.SharedDatabase.DatabaseService::_baseSqlBuilder
0x62bdf  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x62be4  ldstr    aUpdate0Set// "UPDATE {0} SET "
0x62be9  ldc.i4.1
0x62bea  newarr   [mscorlib]System.Object
0x62bef  dup
0x62bf0  ldc.i4.0
0x62bf1  ldarg.0
0x62bf2  ldfld    class Microsoft.Crm.SharedDatabase.Table Microsoft.Crm.SharedDatabase.DatabaseService::_table
0x62bf7  callvirt instance string Microsoft.Crm.SharedDatabase.Table::get_Name()
0x62bfc  stelem.ref
0x62bfd  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x62c02  pop
0x62c03  ldloca.s 3
0x62c05  call     instance object Microsoft.Crm.Data.PropertyEntry::get_Value()
0x62c0a  call     bool Microsoft.Crm.SharedDatabase.SqlHelpers::IsNull(object value)
0x62c0f  brtrue   loc_62CAB
0x62c14  ldloc.s  4
0x62c16  callvirt instance string Microsoft.Crm.SharedDatabase.Column::get_Name()
0x62c1b  ldarg.0
0x62c1c  ldarg.0
0x62c1d  ldfld    int32 Microsoft.Crm.SharedDatabase.DatabaseService::_parameterCount
0x62c22  stloc.s  6
0x62c24  ldloc.s  6
0x62c26  ldc.i4.1
0x62c27  add
0x62c28  stfld    int32 Microsoft.Crm.SharedDatabase.DatabaseService::_parameterCount
0x62c2d  ldloc.s  6
0x62c2f  call     string Microsoft.Crm.SharedDatabase.SqlHelpers::GetParameterName(string name, int32 suffix)
0x62c34  stloc.s  5
0x62c36  ldarg.0
0x62c37  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.Crm.SharedDatabase.DatabaseService::_baseSqlBuilder
0x62c3c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x62c41  ldstr    a012_3// "{0}{1} = {2}"
0x62c46  ldc.i4.3
0x62c47  newarr   [mscorlib]System.Object
0x62c4c  dup
0x62c4d  ldc.i4.0
0x62c4e  ldloc.1
0x62c4f  brtrue.s loc_62C58
0x62c51  ldstr    asc_78ADC// ", "
0x62c56  br.s     loc_62C5D
0x62c58  ldstr    asc_7195A// ""
0x62c5d  stelem.ref
0x62c5e  dup
0x62c5f  ldc.i4.1
0x62c60  ldloc.s  4
0x62c62  callvirt instance string Microsoft.Crm.SharedDatabase.Column::get_Name()
0x62c67  stelem.ref
0x62c68  dup
0x62c69  ldc.i4.2
0x62c6a  ldarg.0
0x62c6b  ldloc.s  4
0x62c6d  ldloc.s  5
0x62c6f  ldarg.0
0x62c70  ldfld    class Microsoft.Crm.SharedDatabase.EncryptionConfiguration Microsoft.Crm.SharedDatabase.DatabaseService::_encryptionConfiguration
0x62c75  callvirt instance bool Microsoft.Crm.SharedDatabase.EncryptionConfiguration::get_Enabled()
0x62c7a  call     instance string Microsoft.Crm.SharedDatabase.DatabaseService::GetEncryptedParameter(class Microsoft.Crm.SharedDatabase.Column column, string parameterName, bool encryptionEnabled)
0x62c7f  stelem.ref
0x62c80  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x62c85  pop
0x62c86  ldloc.0
0x62c87  ldloc.s  5
0x62c89  ldarg.0
0x62c8a  ldloc.s  4
0x62c8c  ldloca.s 3
0x62c8e  call     instance object Microsoft.Crm.Data.PropertyEntry::get_Value()
0x62c93  call     instance object Microsoft.Crm.SharedDatabase.DatabaseService::GetSqlObjectValue(class Microsoft.Crm.SharedDatabase.Column column, object value)
0x62c98  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x62c9d  ldloc.s  4
0x62c9f  callvirt instance valuetype [System.Data]System.Data.SqlDbType Microsoft.Crm.SharedDatabase.Column::get_SqlType()
0x62ca4  callvirt instance void [System.Data]System.Data.SqlClient.SqlParameter::set_SqlDbType(valuetype [System.Data]System.Data.SqlDbType)
0x62ca9  br.s     loc_62CE3
0x62cab  ldarg.0
0x62cac  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.Crm.SharedDatabase.DatabaseService::_baseSqlBuilder
0x62cb1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x62cb6  ldstr    a01Null// "{0}{1} = NULL"
0x62cbb  ldc.i4.2
0x62cbc  newarr   [mscorlib]System.Object
0x62cc1  dup
0x62cc2  ldc.i4.0
0x62cc3  ldloc.1
0x62cc4  brtrue.s loc_62CCD
0x62cc6  ldstr    asc_78ADC// ", "
0x62ccb  br.s     loc_62CD2
0x62ccd  ldstr    asc_7195A// ""
0x62cd2  stelem.ref
0x62cd3  dup
0x62cd4  ldc.i4.1
0x62cd5  ldloc.s  4
0x62cd7  callvirt instance string Microsoft.Crm.SharedDatabase.Column::get_Name()
0x62cdc  stelem.ref
0x62cdd  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x62ce2  pop
0x62ce3  ldc.i4.0
0x62ce4  stloc.1
0x62ce5  ldloc.2
0x62ce6  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x62ceb  brtrue   loc_62B5F
0x62cf0  leave.s  loc_62D06
0x62cf2  ldloc.2
0x62cf3  isinst   [mscorlib]System.IDisposable
0x62cf8  stloc.s  7
0x62cfa  ldloc.s  7
0x62cfc  brfalse.s loc_62D05
0x62cfe  ldloc.s  7
0x62d00  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x62d05  endfinally
0x62d06  ret
```
