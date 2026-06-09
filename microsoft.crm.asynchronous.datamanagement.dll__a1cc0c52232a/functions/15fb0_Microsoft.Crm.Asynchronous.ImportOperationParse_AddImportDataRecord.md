# Microsoft.Crm.Asynchronous.ImportOperationParse::AddImportDataRecord

- ea: `0x15fb0`
- end: `0x16155`
- name: `Microsoft.Crm.Asynchronous.ImportOperationParse::AddImportDataRecord`
- size: `421`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x15220`
- `0x15b80`
- `0x15d20`

## callees

- `0x15f40`
- `0x15fb0`

## string_xrefs

- `0x1607a`: `CreatedBy`
- `0x1612f`: `CreatedOn`

## pseudocode

```c

```

## disassembly

```asm
0x15fb0  ldarg.0
0x15fb1  ldfld    class [System.Data]System.Data.DataTable Microsoft.Crm.Asynchronous.ImportOperationParse::__importDataBaseColumnsDataTable
0x15fb6  brfalse.s loc_15FCF
0x15fb8  ldarg.0
0x15fb9  ldfld    class [System.Data]System.Data.DataTable Microsoft.Crm.Asynchronous.ImportOperationParse::__importDataBaseColumnsDataTable
0x15fbe  callvirt instance class [System.Data]System.Data.DataRowCollection [System.Data]System.Data.DataTable::get_Rows()
0x15fc3  callvirt instance int32 [System.Data]System.Data.InternalDataCollectionBase::get_Count()
0x15fc8  ldc.i4   0x1388
0x15fcd  blt.s    loc_16041
0x15fcf  ldarg.0
0x15fd0  call     instance void Microsoft.Crm.Asynchronous.ImportOperationParse::FlushImportDataTable()
0x15fd5  ldarg.0
0x15fd6  ldstr    aImportdatabase// "ImportDataBase"
0x15fdb  newobj   instance void [System.Data]System.Data.DataTable::.ctor(string)
0x15fe0  stfld    class [System.Data]System.Data.DataTable Microsoft.Crm.Asynchronous.ImportOperationParse::__importDataBaseColumnsDataTable
0x15fe5  ldarg.0
0x15fe6  ldfld    class [System.Data]System.Data.DataTable Microsoft.Crm.Asynchronous.ImportOperationParse::__importDataBaseColumnsDataTable
0x15feb  ldarg.0
0x15fec  ldfld    class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Asynchronous.ImportOperationParse::_orgCultureInfo
0x15ff1  callvirt instance void [System.Data]System.Data.DataTable::set_Locale(class [mscorlib]System.Globalization.CultureInfo)
0x15ff6  ldc.i4.0
0x15ff7  stloc.1
0x15ff8  br.s     loc_16036
0x15ffa  newobj   instance void [System.Data]System.Data.DataColumn::.ctor()
0x15fff  stloc.2
0x16000  ldloc.2
0x16001  ldarg.0
0x16002  ldfld    string[] Microsoft.Crm.Asynchronous.ImportOperationParse::_importDataBaseColumns
0x16007  ldloc.1
0x16008  ldelem.ref
0x16009  callvirt instance void [System.Data]System.Data.DataColumn::set_ColumnName(string)
0x1600e  ldloc.2
0x1600f  ldarg.0
0x16010  ldfld    string[] Microsoft.Crm.Asynchronous.ImportOperationParse::_importDataBaseColumnTypes
0x16015  ldloc.1
0x16016  ldelem.ref
0x16017  call     class [mscorlib]System.Type [mscorlib]System.Type::GetType(string)
0x1601c  callvirt instance void [System.Data]System.Data.DataColumn::set_DataType(class [mscorlib]System.Type)
0x16021  ldarg.0
0x16022  ldfld    class [System.Data]System.Data.DataTable Microsoft.Crm.Asynchronous.ImportOperationParse::__importDataBaseColumnsDataTable
0x16027  callvirt instance class [System.Data]System.Data.DataColumnCollection [System.Data]System.Data.DataTable::get_Columns()
0x1602c  ldloc.2
0x1602d  callvirt instance void [System.Data]System.Data.DataColumnCollection::Add(class [System.Data]System.Data.DataColumn)
0x16032  ldloc.1
0x16033  ldc.i4.1
0x16034  add
0x16035  stloc.1
0x16036  ldloc.1
0x16037  ldarg.0
0x16038  ldfld    string[] Microsoft.Crm.Asynchronous.ImportOperationParse::_importDataBaseColumns
0x1603d  ldlen
0x1603e  conv.i4
0x1603f  blt.s    loc_15FFA
0x16041  ldarg.0
0x16042  ldfld    class [System.Data]System.Data.DataTable Microsoft.Crm.Asynchronous.ImportOperationParse::__importDataBaseColumnsDataTable
0x16047  callvirt instance class [System.Data]System.Data.DataRow [System.Data]System.Data.DataTable::NewRow()
0x1604c  stloc.0
0x1604d  ldloc.0
0x1604e  ldstr    aOwnerid_2// "OwnerId"
0x16053  ldarg.0
0x16054  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ImportOperation::_contextUserId
0x16059  box      [mscorlib]System.Guid
0x1605e  callvirt instance void [System.Data]System.Data.DataRow::set_Item(string, object)
0x16063  ldloc.0
0x16064  ldstr    aOwningbusiness_1// "OwningBusinessUnit"
0x16069  ldarg.0
0x1606a  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ImportOperation::_contextUserBusinessUnitId
0x1606f  box      [mscorlib]System.Guid
0x16074  callvirt instance void [System.Data]System.Data.DataRow::set_Item(string, object)
0x16079  ldloc.0
0x1607a  ldstr    aCreatedby_1// "CreatedBy"
0x1607f  ldarg.0
0x16080  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ImportOperation::_contextUserId
0x16085  box      [mscorlib]System.Guid
0x1608a  callvirt instance void [System.Data]System.Data.DataRow::set_Item(string, object)
0x1608f  ldloc.0
0x16090  ldstr    aStatuscode_2// "StatusCode"
0x16095  ldc.i4.0
0x16096  box      [mscorlib]System.Int32
0x1609b  callvirt instance void [System.Data]System.Data.DataRow::set_Item(string, object)
0x160a0  ldloc.0
0x160a1  ldstr    aModifiedby_1// "ModifiedBy"
0x160a6  ldarg.0
0x160a7  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ImportOperation::_contextUserId
0x160ac  box      [mscorlib]System.Guid
0x160b1  callvirt instance void [System.Data]System.Data.DataRow::set_Item(string, object)
0x160b6  ldloc.0
0x160b7  ldstr    aStatecode_2// "StateCode"
0x160bc  ldc.i4.0
0x160bd  box      [mscorlib]System.Int32
0x160c2  callvirt instance void [System.Data]System.Data.DataRow::set_Item(string, object)
0x160c7  ldloc.0
0x160c8  ldstr    aImportdataid_2// "ImportDataId"
0x160cd  ldarg.2
0x160ce  box      [mscorlib]System.Guid
0x160d3  callvirt instance void [System.Data]System.Data.DataRow::set_Item(string, object)
0x160d8  ldloc.0
0x160d9  ldstr    aRecordid_0// "RecordId"
0x160de  ldarg.3
0x160df  box      [mscorlib]System.Guid
0x160e4  callvirt instance void [System.Data]System.Data.DataRow::set_Item(string, object)
0x160e9  ldloc.0
0x160ea  ldstr    aImportfileid_3// "ImportFileId"
0x160ef  ldarg.1
0x160f0  box      [mscorlib]System.Guid
0x160f5  callvirt instance void [System.Data]System.Data.DataRow::set_Item(string, object)
0x160fa  ldloc.0
0x160fb  ldstr    aData_1// "Data"
0x16100  ldarg.s  4
0x16102  callvirt instance void [System.Data]System.Data.DataRow::set_Item(string, object)
0x16107  ldloc.0
0x16108  ldstr    aLinenumber_0// "LineNumber"
0x1610d  ldarg.s  5
0x1610f  box      [mscorlib]System.Int64
0x16114  callvirt instance void [System.Data]System.Data.DataRow::set_Item(string, object)
0x16119  ldloc.0
0x1611a  ldstr    aModifiedon_1// "ModifiedOn"
0x1611f  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x16124  box      [mscorlib]System.DateTime
0x16129  callvirt instance void [System.Data]System.Data.DataRow::set_Item(string, object)
0x1612e  ldloc.0
0x1612f  ldstr    aCreatedon_0// "CreatedOn"
0x16134  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x16139  box      [mscorlib]System.DateTime
0x1613e  callvirt instance void [System.Data]System.Data.DataRow::set_Item(string, object)
0x16143  ldarg.0
0x16144  ldfld    class [System.Data]System.Data.DataTable Microsoft.Crm.Asynchronous.ImportOperationParse::__importDataBaseColumnsDataTable
0x16149  callvirt instance class [System.Data]System.Data.DataRowCollection [System.Data]System.Data.DataTable::get_Rows()
0x1614e  ldloc.0
0x1614f  callvirt instance void [System.Data]System.Data.DataRowCollection::Add(class [System.Data]System.Data.DataRow)
0x16154  ret
```
