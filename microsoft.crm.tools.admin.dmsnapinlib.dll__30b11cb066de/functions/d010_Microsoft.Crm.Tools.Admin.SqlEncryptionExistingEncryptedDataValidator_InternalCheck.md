# Microsoft.Crm.Tools.Admin.SqlEncryptionExistingEncryptedDataValidator::InternalCheck

- ea: `0xd010`
- end: `0xd1a5`
- name: `Microsoft.Crm.Tools.Admin.SqlEncryptionExistingEncryptedDataValidator::InternalCheck`
- size: `405`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x22e0`
- `0x84f0`
- `0x8720`
- `0x8a30`
- `0x8bf0`
- `0x8cd0`
- `0x92d0`
- `0xd010`
- `0x16940`

## string_xrefs

- `0xd059`: `select \n	a.TableColumnName EncryptedAttributeColumnName, \n	case a.IsStoredOnPrimaryTable\n		when 1 then e.BaseTableName\n		else e.ExtensionTableName\n	end as TableName\nfrom EntityView e \ninner join AttributeView a on e.EntityId = a.EntityId\nwhere a.IsEncrypted = 1 \n`

## pseudocode

```c

```

## disassembly

```asm
0xd010  ldarg.1
0xd011  newobj   instance void Microsoft.Crm.Tools.Admin.OrganizationInfo::.ctor(class [mscorlib]System.Collections.IDictionary data)
0xd016  stloc.0
0xd017  ldloc.0
0xd018  callvirt instance class [mscorlib]System.Version Microsoft.Crm.Tools.Admin.OrganizationInfo::get_ExistingDatabaseVersion()
0xd01d  callvirt instance int32 [mscorlib]System.Version::get_Major()
0xd022  ldc.i4.5
0xd023  bgt.s    loc_D047
0xd025  ldloc.0
0xd026  callvirt instance bool Microsoft.Crm.Tools.Admin.OrganizationInfo::get_IsImportAndUpgrade()
0xd02b  brtrue.s loc_D040
0xd02d  ldloc.0
0xd02e  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_SqlServerName()
0xd033  ldloc.0
0xd034  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_DatabaseName()
0xd039  call     bool Microsoft.Crm.Tools.Admin.OrganizationUpgrader::IsOrganizationVersionSupportedForUpgrade(string sqlServerName, string organizationDatabaseName)
0xd03e  brtrue.s loc_D047
0xd040  ldc.i4.3
0xd041  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResultInfo::.ctor(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResult)
0xd046  ret
0xd047  ldloc.0
0xd048  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_ConnectionString()
0xd04d  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDirectSqlConnection::.ctor(string)
0xd052  stloc.1
0xd053  ldloc.1
0xd054  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0xd059  ldstr    aSelectATableco// "select \r\n\ta.TableColumnName Encrypte"...
0xd05e  stloc.2
0xd05f  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<string, string>>::.ctor()
0xd064  stloc.3
0xd065  ldloc.1
0xd066  ldloc.2
0xd067  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand(string)
0xd06c  stloc.s  5
0xd06e  ldloc.s  5
0xd070  callvirt instance class [System.Data]System.Data.IDataReader [System.Data]System.Data.IDbCommand::ExecuteReader()
0xd075  stloc.s  6
0xd077  br.s     loc_D0AE
0xd079  ldloc.s  6
0xd07b  ldstr    aEncryptedattri// "EncryptedAttributeColumnName"
0xd080  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0xd085  castclass [mscorlib]System.String
0xd08a  stloc.s  7
0xd08c  ldloc.s  6
0xd08e  ldstr    aTablename_0// "TableName"
0xd093  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0xd098  castclass [mscorlib]System.String
0xd09d  stloc.s  8
0xd09f  ldloc.3
0xd0a0  ldloc.s  7
0xd0a2  ldloc.s  8
0xd0a4  newobj   instance void class [mscorlib]System.Tuple`2<string, string>::.ctor(var<u1>, !!T0)
0xd0a9  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<string, string>>::Add(var<u1>)
0xd0ae  ldloc.s  6
0xd0b0  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0xd0b5  brtrue.s loc_D079
0xd0b7  leave.s  loc_D0D1
0xd0b9  ldloc.s  6
0xd0bb  brfalse.s loc_D0C4
0xd0bd  ldloc.s  6
0xd0bf  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xd0c4  endfinally
0xd0c5  ldloc.s  5
0xd0c7  brfalse.s loc_D0D0
0xd0c9  ldloc.s  5
0xd0cb  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xd0d0  endfinally
0xd0d1  ldstr    aIfExistsSelect_0// "if (exists(select * from {0} where {1} "...
0xd0d6  stloc.s  4
0xd0d8  ldloc.3
0xd0d9  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<string, string>>::GetEnumerator()
0xd0de  stloc.s  9
0xd0e0  br       loc_D16D
0xd0e5  ldloca.s 9
0xd0e7  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [mscorlib]System.Tuple`2<string, string>>::get_Current()
0xd0ec  dup
0xd0ed  callvirt instance var<u1> class [mscorlib]System.Tuple`2<string, string>::get_Item1()
0xd0f2  stloc.s  0xA
0xd0f4  callvirt instance var<u1> class [mscorlib]System.Tuple`2<string, string>::get_Item2()
0xd0f9  stloc.s  0xB
0xd0fb  ldloc.1
0xd0fc  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand()
0xd101  stloc.s  0xC
0xd103  ldloc.s  0xC
0xd105  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xd10a  ldloc.s  4
0xd10c  ldc.i4.2
0xd10d  newarr   [mscorlib]System.Object
0xd112  dup
0xd113  ldc.i4.0
0xd114  ldloc.s  0xB
0xd116  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::SqlIdentifierEncode(string)
0xd11b  stelem.ref
0xd11c  dup
0xd11d  ldc.i4.1
0xd11e  ldloc.s  0xA
0xd120  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::SqlIdentifierEncode(string)
0xd125  stelem.ref
0xd126  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xd12b  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0xd130  ldloc.s  0xC
0xd132  callvirt instance object [System.Data]System.Data.IDbCommand::ExecuteScalar()
0xd137  unbox.any [mscorlib]System.Int32
0xd13c  stloc.s  0xD
0xd13e  ldc.i4.1
0xd13f  ldloc.s  0xD
0xd141  ceq
0xd143  brfalse.s loc_D15F
0xd145  ldc.i4.1
0xd146  ldstr    aSqlencryptione// "SqlEncryptionExistingEncryptedDataValid"...
0xd14b  ldc.i4.0
0xd14c  newarr   [mscorlib]System.Object
0xd151  call     string Microsoft.Crm.Tools.Admin.DMSnapInLibResource::GetString(string name, object[] args)
0xd156  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResultInfo::.ctor(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResult, string)
0xd15b  stloc.s  0xE
0xd15d  leave.s  loc_D1A2
0xd15f  leave.s  loc_D16D
0xd161  ldloc.s  0xC
0xd163  brfalse.s loc_D16C
0xd165  ldloc.s  0xC
0xd167  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xd16c  endfinally
0xd16d  ldloca.s 9
0xd16f  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [mscorlib]System.Tuple`2<string, string>>::MoveNext()
0xd174  brtrue   loc_D0E5
0xd179  leave.s  loc_D189
0xd17b  ldloca.s 9
0xd17d  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [mscorlib]System.Tuple`2<string, string>>
0xd183  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xd188  endfinally
0xd189  ldloc.1
0xd18a  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Close()
0xd18f  leave.s  loc_D19B
0xd191  ldloc.1
0xd192  brfalse.s loc_D19A
0xd194  ldloc.1
0xd195  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xd19a  endfinally
0xd19b  ldc.i4.0
0xd19c  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResultInfo::.ctor(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResult)
0xd1a1  ret
0xd1a2  ldloc.s  0xE
0xd1a4  ret
```
