# Microsoft.Crm.Application.Controls.SystemCustomization.SysCustomizationGridDataProvider::ProcessDataToDataTable

- ea: `0xcae40`
- end: `0xcb13e`
- name: `Microsoft.Crm.Application.Controls.SystemCustomization.SysCustomizationGridDataProvider::ProcessDataToDataTable`
- size: `766`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0xcad70`

## callees

- `0xcae40`
- `0xcb140`
- `0xcb170`
- `0xcb260`

## string_xrefs

- `0xcb06f`: `RowComponentSubcode`
- `0xcb096`: `RowComponentSubcode`
- `0xcb100`: `RowComponentSubcode_Hidden`

## pseudocode

```c

```

## disassembly

```asm
0xcae40  ldarg.0
0xcae41  ldfld    class Row[] Microsoft.Crm.Application.Controls.SystemCustomization.SysCustomizationGridDataProvider::_dataSet
0xcae46  ldlen
0xcae47  brfalse.s loc_CAE57
0xcae49  ldarg.0
0xcae4a  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridData [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Results()
0xcae4f  ldc.i4.3
0xcae50  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridData::set_DataType(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataType)
0xcae55  br.s     loc_CAE63
0xcae57  ldarg.0
0xcae58  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridData [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Results()
0xcae5d  ldc.i4.2
0xcae5e  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridData::set_DataType(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataType)
0xcae63  ldarg.0
0xcae64  ldarg.0
0xcae65  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.View [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_CurrentView()
0xcae6a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.View::get_IdColumnName()
0xcae6f  call     instance int32 Microsoft.Crm.Application.Controls.SystemCustomization.SysCustomizationGridDataProvider::GetColumnIndex(string columnName)
0xcae74  stloc.0
0xcae75  ldarg.0
0xcae76  ldstr    aMoid// "moid"
0xcae7b  call     instance int32 Microsoft.Crm.Application.Controls.SystemCustomization.SysCustomizationGridDataProvider::GetColumnIndex(string columnName)
0xcae80  stloc.1
0xcae81  ldarg.0
0xcae82  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.ColumnCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Columns()
0xcae87  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0xcae8c  newarr   [mscorlib]System.Int32
0xcae91  stloc.2
0xcae92  ldc.i4.0
0xcae93  stloc.3
0xcae94  ldarg.0
0xcae95  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.ColumnCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Columns()
0xcae9a  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0xcae9f  stloc.s  5
0xcaea1  br.s     loc_CAEC5
0xcaea3  ldloc.s  5
0xcaea5  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xcaeaa  castclass [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.Column
0xcaeaf  stloc.s  6
0xcaeb1  ldloc.2
0xcaeb2  ldloc.3
0xcaeb3  dup
0xcaeb4  ldc.i4.1
0xcaeb5  add
0xcaeb6  stloc.3
0xcaeb7  ldarg.0
0xcaeb8  ldloc.s  6
0xcaeba  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.Column::get_Name()
0xcaebf  call     instance int32 Microsoft.Crm.Application.Controls.SystemCustomization.SysCustomizationGridDataProvider::GetColumnIndex(string columnName)
0xcaec4  stelem.i4
0xcaec5  ldloc.s  5
0xcaec7  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xcaecc  brtrue.s loc_CAEA3
0xcaece  leave.s  loc_CAEE5
0xcaed0  ldloc.s  5
0xcaed2  isinst   [mscorlib]System.IDisposable
0xcaed7  stloc.s  7
0xcaed9  ldloc.s  7
0xcaedb  brfalse.s loc_CAEE4
0xcaedd  ldloc.s  7
0xcaedf  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xcaee4  endfinally
0xcaee5  ldarg.0
0xcaee6  ldarg.0
0xcaee7  ldfld    class Row[] Microsoft.Crm.Application.Controls.SystemCustomization.SysCustomizationGridDataProvider::_dataSet
0xcaeec  ldlen
0xcaeed  conv.i4
0xcaeee  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::set_TotalRecordCount(int32)
0xcaef3  ldarg.0
0xcaef4  call     instance void Microsoft.Crm.Application.Controls.SystemCustomization.SysCustomizationGridDataProvider::SetPaging()
0xcaef9  ldarg.0
0xcaefa  ldfld    class Row[] Microsoft.Crm.Application.Controls.SystemCustomization.SysCustomizationGridDataProvider::_dataSet
0xcaeff  stloc.s  8
0xcaf01  ldc.i4.0
0xcaf02  stloc.s  9
0xcaf04  br       loc_CB036
0xcaf09  ldloc.s  8
0xcaf0b  ldloc.s  9
0xcaf0d  ldelem.ref
0xcaf0e  stloc.s  0xA
0xcaf10  ldarg.0
0xcaf11  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridData [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Results()
0xcaf16  callvirt instance class [System.Data]System.Data.DataTable [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridData::get_Data()
0xcaf1b  callvirt instance class [System.Data]System.Data.DataRow [System.Data]System.Data.DataTable::NewRow()
0xcaf20  stloc.s  0xB
0xcaf22  ldloc.s  0xB
0xcaf24  ldstr    aRowid// "RowId"
0xcaf29  ldloc.s  0xA
0xcaf2b  ldfld    string[] Row::columns
0xcaf30  ldloc.0
0xcaf31  ldelem.ref
0xcaf32  callvirt instance void [System.Data]System.Data.DataRow::set_Item(string, object)
0xcaf37  ldloc.1
0xcaf38  ldc.i4.m1
0xcaf39  ble.s    loc_CAF50
0xcaf3b  ldloc.s  0xB
0xcaf3d  ldstr    aRowtype// "RowType"
0xcaf42  ldloc.s  0xA
0xcaf44  ldfld    string[] Row::columns
0xcaf49  ldloc.1
0xcaf4a  ldelem.ref
0xcaf4b  callvirt instance void [System.Data]System.Data.DataRow::set_Item(string, object)
0xcaf50  ldc.i4.0
0xcaf51  stloc.s  0xC
0xcaf53  ldarg.0
0xcaf54  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.ColumnCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Columns()
0xcaf59  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0xcaf5e  stloc.s  5
0xcaf60  br       loc_CAFF6
0xcaf65  ldloc.s  5
0xcaf67  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xcaf6c  castclass [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.Column
0xcaf71  stloc.s  0xD
0xcaf73  ldloc.s  0xB
0xcaf75  ldloc.s  0xD
0xcaf77  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.Column::get_Name()
0xcaf7c  ldloc.s  0xA
0xcaf7e  ldfld    string[] Row::columns
0xcaf83  ldloc.2
0xcaf84  ldloc.s  0xC
0xcaf86  dup
0xcaf87  ldc.i4.1
0xcaf88  add
0xcaf89  stloc.s  0xC
0xcaf8b  ldelem.i4
0xcaf8c  ldelem.ref
0xcaf8d  callvirt instance void [System.Data]System.Data.DataRow::set_Item(string, object)
0xcaf92  ldloc.s  0xB
0xcaf94  ldloc.s  0xD
0xcaf96  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.Column::get_Name()
0xcaf9b  ldstr    aValue_3// "_Value"
0xcafa0  call     string [mscorlib]System.String::Concat(string, string)
0xcafa5  ldnull
0xcafa6  callvirt instance void [System.Data]System.Data.DataRow::set_Item(string, object)
0xcafab  ldloc.s  0xD
0xcafad  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.ColumnUIInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.Column::get_UIInfo()
0xcafb2  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.ColumnUIInfo::get_IsHidden()
0xcafb7  brfalse.s loc_CAFF6
0xcafb9  ldarg.0
0xcafba  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridData [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Results()
0xcafbf  callvirt instance class [System.Data]System.Data.DataTable [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridData::get_Data()
0xcafc4  ldloc.s  0xD
0xcafc6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.Column::get_Name()
0xcafcb  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridData::AddHiddenColumnToDataTable(class [System.Data]System.Data.DataTable, string)
0xcafd0  ldloc.s  0xB
0xcafd2  ldloc.s  0xD
0xcafd4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.Column::get_Name()
0xcafd9  ldstr    aHidden_2// "_Hidden"
0xcafde  call     string [mscorlib]System.String::Concat(string, string)
0xcafe3  ldloc.s  0xB
0xcafe5  ldloc.s  0xD
0xcafe7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.Column::get_Name()
0xcafec  callvirt instance object [System.Data]System.Data.DataRow::get_Item(string)
0xcaff1  callvirt instance void [System.Data]System.Data.DataRow::set_Item(string, object)
0xcaff6  ldloc.s  5
0xcaff8  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xcaffd  brtrue   loc_CAF65
0xcb002  leave.s  loc_CB019
0xcb004  ldloc.s  5
0xcb006  isinst   [mscorlib]System.IDisposable
0xcb00b  stloc.s  7
0xcb00d  ldloc.s  7
0xcb00f  brfalse.s loc_CB018
0xcb011  ldloc.s  7
0xcb013  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xcb018  endfinally
0xcb019  ldarg.0
0xcb01a  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridData [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Results()
0xcb01f  callvirt instance class [System.Data]System.Data.DataTable [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridData::get_Data()
0xcb024  callvirt instance class [System.Data]System.Data.DataRowCollection [System.Data]System.Data.DataTable::get_Rows()
0xcb029  ldloc.s  0xB
0xcb02b  callvirt instance void [System.Data]System.Data.DataRowCollection::Add(class [System.Data]System.Data.DataRow)
0xcb030  ldloc.s  9
0xcb032  ldc.i4.1
0xcb033  add
0xcb034  stloc.s  9
0xcb036  ldloc.s  9
0xcb038  ldloc.s  8
0xcb03a  ldlen
0xcb03b  conv.i4
0xcb03c  blt      loc_CAF09
0xcb041  ldloca.s 4
0xcb043  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0xcb049  ldarg.0
0xcb04a  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> Microsoft.Crm.Application.Controls.SystemCustomization.SysCustomizationGridDataProvider::_rowIdComponentSubcode
0xcb04f  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::get_Count()
0xcb054  ldc.i4.0
0xcb055  cgt
0xcb057  brfalse.s loc_CB0A0
0xcb059  ldsfld   string [mscorlib]System.String::Empty
0xcb05e  ldc.i4.0
0xcb05f  ldsfld   string [mscorlib]System.String::Empty
0xcb064  ldc.i4.0
0xcb065  ldc.i4.1
0xcb066  ldnull
0xcb067  ldnull
0xcb068  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.ColumnUIInfo::.ctor(string, unsigned int32, string, bool, bool, string, string)
0xcb06d  stloc.s  0xE
0xcb06f  ldstr    aRowcomponentsu// "RowComponentSubcode"
0xcb074  ldloc.s  0xE
0xcb076  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.Column [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.Column::CreateNonMetadataBoundColumn(string, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.ColumnUIInfo)
0xcb07b  stloc.s  0xF
0xcb07d  ldarg.0
0xcb07e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.ColumnCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Columns()
0xcb083  ldloc.s  0xF
0xcb085  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.ColumnCollection::Add(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.Column)
0xcb08a  pop
0xcb08b  ldarg.0
0xcb08c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridData [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Results()
0xcb091  callvirt instance class [System.Data]System.Data.DataTable [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridData::get_Data()
0xcb096  ldstr    aRowcomponentsu// "RowComponentSubcode"
0xcb09b  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridData::AddHiddenColumnToDataTable(class [System.Data]System.Data.DataTable, string)
0xcb0a0  ldarg.0
0xcb0a1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridData [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Results()
0xcb0a6  callvirt instance class [System.Data]System.Data.DataTable [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridData::get_Data()
0xcb0ab  callvirt instance class [System.Data]System.Data.DataRowCollection [System.Data]System.Data.DataTable::get_Rows()
0xcb0b0  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Data]System.Data.InternalDataCollectionBase::GetEnumerator()
0xcb0b5  stloc.s  5
0xcb0b7  br.s     loc_CB116
0xcb0b9  ldloc.s  5
0xcb0bb  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xcb0c0  castclass [System.Data]System.Data.DataRow
0xcb0c5  stloc.s  0x10
0xcb0c7  ldarg.0
0xcb0c8  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> Microsoft.Crm.Application.Controls.SystemCustomization.SysCustomizationGridDataProvider::_rowIdComponentSubcode
0xcb0cd  ldloc.s  0x10
0xcb0cf  ldstr    aRowid// "RowId"
0xcb0d4  callvirt instance object [System.Data]System.Data.DataRow::get_Item(string)
0xcb0d9  callvirt instance string [mscorlib]System.Object::ToString()
0xcb0de  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::ContainsKey(var<u1>)
0xcb0e3  brfalse.s loc_CB116
0xcb0e5  ldarg.0
0xcb0e6  ldloc.s  0x10
0xcb0e8  ldstr    aRowid// "RowId"
0xcb0ed  callvirt instance object [System.Data]System.Data.DataRow::get_Item(string)
0xcb0f2  callvirt instance string [mscorlib]System.Object::ToString()
0xcb0f7  call     instance valuetype [mscorlib]System.Nullable`1<int32> Microsoft.Crm.Application.Controls.SystemCustomization.SysCustomizationGridDataProvider::GetRowSubcode(string rowId)
0xcb0fc  stloc.s  4
0xcb0fe  ldloc.s  0x10
0xcb100  ldstr    aRowcomponentsu_0// "RowComponentSubcode_Hidden"
0xcb105  ldloca.s 4
0xcb107  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0xcb10c  box      [mscorlib]System.Int32
0xcb111  callvirt instance void [System.Data]System.Data.DataRow::set_Item(string, object)
0xcb116  ldloc.s  5
0xcb118  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xcb11d  brtrue.s loc_CB0B9
0xcb11f  leave.s  loc_CB136
0xcb121  ldloc.s  5
0xcb123  isinst   [mscorlib]System.IDisposable
0xcb128  stloc.s  7
0xcb12a  ldloc.s  7
0xcb12c  brfalse.s loc_CB135
0xcb12e  ldloc.s  7
0xcb130  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xcb135  endfinally
0xcb136  ldarg.0
0xcb137  ldc.i4.0
0xcb138  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::set_TotalRecordCountLimitExceeded(bool)
0xcb13d  ret
```
