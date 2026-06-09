# Microsoft.Crm.SharedDatabase.DatabaseService::BuildDeleteSql

- ea: `0x63000`
- end: `0x6309b`
- name: `Microsoft.Crm.SharedDatabase.DatabaseService::BuildDeleteSql`
- size: `155`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x63cd0`

## callees

- `0x5f120`
- `0x607f0`
- `0x60800`
- `0x61120`
- `0x629a0`
- `0x629c0`
- `0x63000`

## string_xrefs

- `0x63013`: `DELETE FROM {0}Properties WHERE {1} IN (SELECT {1} FROM {0} `
- `0x63074`: `DELETE FROM {0} `

## pseudocode

```c

```

## disassembly

```asm
0x63000  ldarg.0
0x63001  callvirt instance bool Microsoft.Crm.SharedDatabase.DatabaseService::IsSettingsTableEnabled()
0x63006  brfalse.s loc_63069
0x63008  ldarg.0
0x63009  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.Crm.SharedDatabase.DatabaseService::_propertiesSqlBuilder
0x6300e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x63013  ldstr    aDeleteFrom0Pro// "DELETE FROM {0}Properties WHERE {1} IN "...
0x63018  ldc.i4.2
0x63019  newarr   [mscorlib]System.Object
0x6301e  dup
0x6301f  ldc.i4.0
0x63020  ldarg.0
0x63021  ldfld    class Microsoft.Crm.SharedDatabase.Table Microsoft.Crm.SharedDatabase.DatabaseService::_table
0x63026  callvirt instance string Microsoft.Crm.SharedDatabase.Table::get_Name()
0x6302b  stelem.ref
0x6302c  dup
0x6302d  ldc.i4.1
0x6302e  ldarg.0
0x6302f  ldfld    class Microsoft.Crm.SharedDatabase.Table Microsoft.Crm.SharedDatabase.DatabaseService::_table
0x63034  callvirt instance class Microsoft.Crm.SharedDatabase.Column Microsoft.Crm.SharedDatabase.Table::get_PrimaryKey()
0x63039  callvirt instance string Microsoft.Crm.SharedDatabase.Column::get_Name()
0x6303e  stelem.ref
0x6303f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x63044  pop
0x63045  ldarg.0
0x63046  ldarg.1
0x63047  ldarg.0
0x63048  ldfld    class [System.Data]System.Data.IDbCommand Microsoft.Crm.SharedDatabase.DatabaseService::_propertiesCommand
0x6304d  ldarg.0
0x6304e  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.Crm.SharedDatabase.DatabaseService::_propertiesSqlBuilder
0x63053  call     instance void Microsoft.Crm.SharedDatabase.DatabaseService::BuildWhereClauseSql(class Microsoft.Crm.Data.PropertyBag[] conditions, class [System.Data]System.Data.IDbCommand command, class [mscorlib]System.Text.StringBuilder sqlBuilder)
0x63058  ldarg.0
0x63059  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.Crm.SharedDatabase.DatabaseService::_propertiesSqlBuilder
0x6305e  ldstr    asc_78AE2// ")"
0x63063  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x63068  pop
0x63069  ldarg.0
0x6306a  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.Crm.SharedDatabase.DatabaseService::_baseSqlBuilder
0x6306f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x63074  ldstr    aDeleteFrom0// "DELETE FROM {0} "
0x63079  ldc.i4.1
0x6307a  newarr   [mscorlib]System.Object
0x6307f  dup
0x63080  ldc.i4.0
0x63081  ldarg.0
0x63082  ldfld    class Microsoft.Crm.SharedDatabase.Table Microsoft.Crm.SharedDatabase.DatabaseService::_table
0x63087  callvirt instance string Microsoft.Crm.SharedDatabase.Table::get_Name()
0x6308c  stelem.ref
0x6308d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x63092  pop
0x63093  ldarg.0
0x63094  ldarg.1
0x63095  call     instance void Microsoft.Crm.SharedDatabase.DatabaseService::BuildWhereClauseSql(class Microsoft.Crm.Data.PropertyBag[] conditions)
0x6309a  ret
```
