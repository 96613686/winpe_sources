# Microsoft.Crm.Asynchronous.ImportDataAccess::RetrieveParsedDataForFullName

- ea: `0x4ca0`
- end: `0x4e1a`
- name: `Microsoft.Crm.Asynchronous.ImportDataAccess::RetrieveParsedDataForFullName`
- size: `378`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1a2a0`

## callees

- `0x4ca0`
- `0x1ff20`

## pseudocode

```c

```

## disassembly

```asm
0x4ca0  newobj   instance void <>c__DisplayClass36_0::.ctor()
0x4ca5  stloc.0
0x4ca6  ldloc.0
0x4ca7  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.ParsedDataRow>::.ctor()
0x4cac  stfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.ParsedDataRow> <>c__DisplayClass36_0::parsedDataRowArray
0x4cb1  ldarg.s  6
0x4cb3  brfalse.s loc_4CBA
0x4cb5  ldarg.s  6
0x4cb7  ldlen
0x4cb8  brtrue.s loc_4CC1
0x4cba  ldloc.0
0x4cbb  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.ParsedDataRow> <>c__DisplayClass36_0::parsedDataRowArray
0x4cc0  ret
0x4cc1  ldarg.3
0x4cc2  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4cc7  brfalse.s loc_4CE2
0x4cc9  ldarg.s  5
0x4ccb  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4cd0  brfalse.s loc_4CE2
0x4cd2  ldarg.s  4
0x4cd4  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4cd9  brfalse.s loc_4CE2
0x4cdb  ldloc.0
0x4cdc  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.ParsedDataRow> <>c__DisplayClass36_0::parsedDataRowArray
0x4ce1  ret
0x4ce2  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x4ce7  stloc.1
0x4ce8  ldc.i4.0
0x4ce9  stloc.2
0x4cea  br.s     loc_4D1B
0x4cec  ldloc.1
0x4ced  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4cf2  ldstr    aKey0// "@Key{0}, "
0x4cf7  ldc.i4.1
0x4cf8  newarr   [mscorlib]System.Object
0x4cfd  dup
0x4cfe  ldc.i4.0
0x4cff  ldloca.s 2
0x4d01  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4d06  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x4d0b  stelem.ref
0x4d0c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4d11  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4d16  pop
0x4d17  ldloc.2
0x4d18  ldc.i4.1
0x4d19  add
0x4d1a  stloc.2
0x4d1b  ldloc.2
0x4d1c  ldarg.s  6
0x4d1e  ldlen
0x4d1f  conv.i4
0x4d20  ldc.i4.1
0x4d21  sub
0x4d22  blt.s    loc_4CEC
0x4d24  ldloc.1
0x4d25  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4d2a  ldstr    aKey0_0// "@Key{0}"
0x4d2f  ldc.i4.1
0x4d30  newarr   [mscorlib]System.Object
0x4d35  dup
0x4d36  ldc.i4.0
0x4d37  ldloca.s 2
0x4d39  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4d3e  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x4d43  stelem.ref
0x4d44  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4d49  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4d4e  pop
0x4d4f  ldarg.0
0x4d50  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0x4d55  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationSettings()
0x4d5a  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_FullNameConventionCode()
0x4d5f  ldarg.3
0x4d60  ldarg.s  4
0x4d62  ldarg.s  5
0x4d64  call     string [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.FullNameGenerator::GenerateFullNameSqlClause(valuetype [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.FullNameConventionCode, string, string, string)
0x4d69  stloc.3
0x4d6a  ldstr    aSelectImportda_0// "SELECT ImportDataId, {0}0, IsExistingRe"...
0x4d6f  stloc.s  4
0x4d71  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4d76  ldloc.s  4
0x4d78  ldc.i4.5
0x4d79  newarr   [mscorlib]System.Object
0x4d7e  dup
0x4d7f  ldc.i4.0
0x4d80  ldarg.2
0x4d81  stelem.ref
0x4d82  dup
0x4d83  ldc.i4.1
0x4d84  ldloc.3
0x4d85  stelem.ref
0x4d86  dup
0x4d87  ldc.i4.2
0x4d88  ldarg.1
0x4d89  stelem.ref
0x4d8a  dup
0x4d8b  ldc.i4.3
0x4d8c  ldloc.3
0x4d8d  stelem.ref
0x4d8e  dup
0x4d8f  ldc.i4.4
0x4d90  ldloc.1
0x4d91  callvirt instance string [mscorlib]System.Object::ToString()
0x4d96  stelem.ref
0x4d97  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4d9c  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand(string)
0x4da1  stloc.s  5
0x4da3  ldloc.s  5
0x4da5  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x4daa  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x4daf  stloc.s  6
0x4db1  ldc.i4.0
0x4db2  stloc.2
0x4db3  br.s     loc_4DE9
0x4db5  ldloc.s  6
0x4db7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4dbc  ldstr    aKey0_0// "@Key{0}"
0x4dc1  ldc.i4.1
0x4dc2  newarr   [mscorlib]System.Object
0x4dc7  dup
0x4dc8  ldc.i4.0
0x4dc9  ldloca.s 2
0x4dcb  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4dd0  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x4dd5  stelem.ref
0x4dd6  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4ddb  ldarg.s  6
0x4ddd  ldloc.2
0x4dde  ldelem.ref
0x4ddf  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x4de4  pop
0x4de5  ldloc.2
0x4de6  ldc.i4.1
0x4de7  add
0x4de8  stloc.2
0x4de9  ldloc.2
0x4dea  ldarg.s  6
0x4dec  ldlen
0x4ded  conv.i4
0x4dee  blt.s    loc_4DB5
0x4df0  ldarg.0
0x4df1  ldloc.s  5
0x4df3  ldloc.0
0x4df4  ldftn    instance void <>c__DisplayClass36_0::<RetrieveParsedDataForFullName>b__0(object[] values)
0x4dfa  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor::.ctor(object, native int)
0x4dff  call     instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteSqlCommandAndProcessRecords(class [System.Data]System.Data.IDbCommand, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor)
0x4e04  pop
0x4e05  leave.s  loc_4E13
0x4e07  ldloc.s  5
0x4e09  brfalse.s loc_4E12
0x4e0b  ldloc.s  5
0x4e0d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4e12  endfinally
0x4e13  ldloc.0
0x4e14  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.ParsedDataRow> <>c__DisplayClass36_0::parsedDataRowArray
0x4e19  ret
```
