# Microsoft.Crm.Asynchronous.ImportDataAccess::EliminateduplicatesInParseTable

- ea: `0x5660`
- end: `0x5890`
- name: `Microsoft.Crm.Asynchronous.ImportDataAccess::EliminateduplicatesInParseTable`
- size: `560`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14bc0`

## callees

- `0x3f90`
- `0x4540`
- `0x5660`

## string_xrefs

- `0x5810`: `UPDATE ImportFileBase SET ParsedTableName = @parsedTableName WHERE ImportFileId = @importFileId`

## pseudocode

```c

```

## disassembly

```asm
0x5660  ldarg.1
0x5661  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5666  brtrue.s loc_5671
0x5668  ldarg.s  4
0x566a  ldlen
0x566b  brfalse.s loc_5671
0x566d  ldarg.3
0x566e  ldc.i4.0
0x566f  bgt.s    loc_5672
0x5671  ret
0x5672  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5677  ldstr    aSelectSnIstran// "SELECT  SN, IsTransformed, ImportDataId"...
0x567c  ldc.i4.1
0x567d  newarr   [mscorlib]System.Object
0x5682  dup
0x5683  ldc.i4.0
0x5684  ldarg.2
0x5685  stelem.ref
0x5686  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x568b  stloc.0
0x568c  ldloc.0
0x568d  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(string)
0x5692  stloc.1
0x5693  ldc.i4.1
0x5694  stloc.2
0x5695  br.s     loc_56C4
0x5697  ldloc.1
0x5698  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x569d  ldstr    a01// ",{0}{1}"
0x56a2  ldc.i4.2
0x56a3  newarr   [mscorlib]System.Object
0x56a8  dup
0x56a9  ldc.i4.0
0x56aa  ldarg.2
0x56ab  stelem.ref
0x56ac  dup
0x56ad  ldc.i4.1
0x56ae  ldloc.2
0x56af  box      [mscorlib]System.Int32
0x56b4  stelem.ref
0x56b5  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x56ba  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x56bf  pop
0x56c0  ldloc.2
0x56c1  ldc.i4.1
0x56c2  add
0x56c3  stloc.2
0x56c4  ldloc.2
0x56c5  ldarg.3
0x56c6  ble.s    loc_5697
0x56c8  ldloc.1
0x56c9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x56ce  ldstr    aIntoDbo0Dedupe// " INTO dbo.{0}_DeDupe"
0x56d3  ldc.i4.1
0x56d4  newarr   [mscorlib]System.Object
0x56d9  dup
0x56da  ldc.i4.0
0x56db  ldarg.1
0x56dc  stelem.ref
0x56dd  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x56e2  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x56e7  pop
0x56e8  ldloc.1
0x56e9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x56ee  ldstr    aFromSelectSnIs// " FROM (SELECT SN, IsTransformed, Import"...
0x56f3  ldc.i4.1
0x56f4  newarr   [mscorlib]System.Object
0x56f9  dup
0x56fa  ldc.i4.0
0x56fb  ldarg.2
0x56fc  stelem.ref
0x56fd  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x5702  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x5707  pop
0x5708  ldc.i4.1
0x5709  stloc.3
0x570a  br.s     loc_5739
0x570c  ldloc.1
0x570d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5712  ldstr    a01// ",{0}{1}"
0x5717  ldc.i4.2
0x5718  newarr   [mscorlib]System.Object
0x571d  dup
0x571e  ldc.i4.0
0x571f  ldarg.2
0x5720  stelem.ref
0x5721  dup
0x5722  ldc.i4.1
0x5723  ldloc.3
0x5724  box      [mscorlib]System.Int32
0x5729  stelem.ref
0x572a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x572f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x5734  pop
0x5735  ldloc.3
0x5736  ldc.i4.1
0x5737  add
0x5738  stloc.3
0x5739  ldloc.3
0x573a  ldarg.3
0x573b  ble.s    loc_570C
0x573d  ldloc.1
0x573e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5743  ldstr    aRowNumberOverP// ",ROW_NUMBER() OVER (PARTITION BY "
0x5748  ldc.i4.0
0x5749  newarr   [mscorlib]System.Object
0x574e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x5753  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x5758  pop
0x5759  ldc.i4.0
0x575a  stloc.s  4
0x575c  br.s     loc_5788
0x575e  ldloc.1
0x575f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5764  ldstr    a0_2// "{0},"
0x5769  ldc.i4.1
0x576a  newarr   [mscorlib]System.Object
0x576f  dup
0x5770  ldc.i4.0
0x5771  ldarg.s  4
0x5773  ldloc.s  4
0x5775  ldelem.ref
0x5776  stelem.ref
0x5777  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x577c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x5781  pop
0x5782  ldloc.s  4
0x5784  ldc.i4.1
0x5785  add
0x5786  stloc.s  4
0x5788  ldloc.s  4
0x578a  ldarg.s  4
0x578c  ldlen
0x578d  conv.i4
0x578e  ldc.i4.1
0x578f  sub
0x5790  blt.s    loc_575E
0x5792  ldloc.1
0x5793  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5798  ldstr    a0_3// "{0} "
0x579d  ldc.i4.1
0x579e  newarr   [mscorlib]System.Object
0x57a3  dup
0x57a4  ldc.i4.0
0x57a5  ldarg.s  4
0x57a7  ldarg.s  4
0x57a9  ldlen
0x57aa  conv.i4
0x57ab  ldc.i4.1
0x57ac  sub
0x57ad  ldelem.ref
0x57ae  stelem.ref
0x57af  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x57b4  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x57b9  pop
0x57ba  ldloc.1
0x57bb  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x57c0  ldstr    aOrderBySnRownu// "ORDER BY SN) rownum FROM {0}) tbl WHERE"...
0x57c5  ldc.i4.1
0x57c6  newarr   [mscorlib]System.Object
0x57cb  dup
0x57cc  ldc.i4.0
0x57cd  ldarg.1
0x57ce  stelem.ref
0x57cf  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x57d4  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x57d9  pop
0x57da  ldloc.1
0x57db  ldstr    asc_28120// "\n"
0x57e0  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x57e5  pop
0x57e6  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x57eb  stloc.s  5
0x57ed  ldloc.s  5
0x57ef  ldloc.1
0x57f0  callvirt instance string [mscorlib]System.Object::ToString()
0x57f5  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x57fa  ldarg.0
0x57fb  ldloc.s  5
0x57fd  call     instance void Microsoft.Crm.Asynchronous.ImportDataAccess::ExecuteSqlCommandWithNoExpectedRecords(class [System.Data]System.Data.IDbCommand sqlCommand)
0x5802  leave.s  loc_5810
0x5804  ldloc.s  5
0x5806  brfalse.s loc_580F
0x5808  ldloc.s  5
0x580a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x580f  endfinally
0x5810  ldstr    aUpdateImportfi_5// "UPDATE ImportFileBase SET ParsedTableNa"...
0x5815  stloc.0
0x5816  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x581b  stloc.s  6
0x581d  ldloc.s  6
0x581f  ldloc.0
0x5820  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x5825  ldloc.s  6
0x5827  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x582c  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x5831  stloc.s  7
0x5833  ldloc.s  7
0x5835  ldstr    aParsedtablenam// "@parsedTableName"
0x583a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x583f  ldstr    a0Dedupe// "{0}_DeDupe"
0x5844  ldc.i4.1
0x5845  newarr   [mscorlib]System.Object
0x584a  dup
0x584b  ldc.i4.0
0x584c  ldarg.1
0x584d  stelem.ref
0x584e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x5853  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x5858  pop
0x5859  ldloc.s  7
0x585b  ldstr    aImportfileid_0// "@importFileId"
0x5860  ldarga.s 5
0x5862  ldstr    aD_0// "D"
0x5867  call     instance string [mscorlib]System.Guid::ToString(string)
0x586c  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x5871  pop
0x5872  ldarg.0
0x5873  ldloc.s  6
0x5875  call     instance void Microsoft.Crm.Asynchronous.ImportDataAccess::ExecuteSqlCommandWithNoExpectedRecords(class [System.Data]System.Data.IDbCommand sqlCommand)
0x587a  leave.s  loc_5888
0x587c  ldloc.s  6
0x587e  brfalse.s loc_5887
0x5880  ldloc.s  6
0x5882  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5887  endfinally
0x5888  ldarg.0
0x5889  ldarg.1
0x588a  call     instance void Microsoft.Crm.Asynchronous.ImportDataAccess::DropParsedTable(string parsedTableName)
0x588f  ret
```
