# Microsoft.Crm.Application.Platform.Grid.DataProcessorEntity::ProcessData

- ea: `0x83740`
- end: `0x839e2`
- name: `Microsoft.Crm.Application.Platform.Grid.DataProcessorEntity::ProcessData`
- size: `674`
- prototype: ``
- caller_count: `0`
- callee_count: `23`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x58f0`
- `0x577b0`
- `0x577c0`
- `0x577d0`
- `0x577e0`
- `0x5bac0`
- `0x5be50`
- `0x5c6f0`
- `0x5e3f0`
- `0x6a0d0`
- `0x828a0`
- `0x82a00`
- `0x82a10`
- `0x82a20`
- `0x82a40`
- `0x82a70`
- `0x83740`
- `0x839f0`
- `0x83a40`
- `0x83a90`
- `0x83bd0`
- `0x83be0`
- `0x87260`

## string_xrefs

- `0x83942`: `processid`
- `0x83966`: `processid`
- `0x8396c`: `processid`
- `0x8397c`: `processidworkflowworkflowid.versionnumber`
- `0x83994`: `processidworkflowworkflowid.versionnumber`
- `0x839af`: `processidworkflowworkflowid.versionnumber`

## pseudocode

```c

```

## disassembly

```asm
0x83740  ldarg.2
0x83741  brtrue.s loc_83744
0x83743  ret
0x83744  ldarg.0
0x83745  ldarg.2
0x83746  callvirt instance bool Microsoft.Crm.Application.Platform.ApplicationEntityCollection::get_MoreRecords()
0x8374b  ldarg.2
0x8374c  callvirt instance string Microsoft.Crm.Application.Platform.ApplicationEntityCollection::get_PagingCookie()
0x83751  ldarg.2
0x83752  callvirt instance int32 Microsoft.Crm.Application.Platform.ApplicationEntityCollection::get_TotalRecordCount()
0x83757  ldarg.2
0x83758  callvirt instance bool Microsoft.Crm.Application.Platform.ApplicationEntityCollection::get_TotalRecordCountLimitExceeded()
0x8375d  call     instance void class Microsoft.Crm.Application.Platform.Grid.DataProcessor`1<class Microsoft.Crm.Application.Platform.ApplicationEntityCollection>::SetPagingInformation(bool, string, int32, bool)
0x83762  ldarg.2
0x83763  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Application.Platform.Entity>::get_Count()
0x83768  brtrue.s loc_8376B
0x8376a  ret
0x8376b  ldarg.3
0x8376c  brfalse.s loc_837C9
0x8376e  ldarg.3
0x8376f  callvirt instance string Microsoft.Crm.View::get_ObjectType()
0x83774  brfalse.s loc_837C9
0x83776  ldarg.3
0x83777  callvirt instance string Microsoft.Crm.View::get_ObjectType()
0x8377c  callvirt instance int32 [mscorlib]System.String::get_Length()
0x83781  ldc.i4.0
0x83782  ble.s    loc_837C9
0x83784  ldarg.3
0x83785  callvirt instance string Microsoft.Crm.View::get_ObjectType()
0x8378a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8378f  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x83794  stloc.0
0x83795  ldloc.0
0x83796  ldc.i4   0x232A
0x8379b  beq.s    loc_837C9
0x8379d  ldloc.0
0x8379e  brfalse.s loc_837C9
0x837a0  ldloc.0
0x837a1  ldc.i4   0x23F6
0x837a6  beq.s    loc_837C9
0x837a8  ldarg.0
0x837a9  ldarg.0
0x837aa  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache class Microsoft.Crm.Application.Platform.Grid.DataProcessor`1<class Microsoft.Crm.Application.Platform.ApplicationEntityCollection>::get_DataProcessorMetadataCache()
0x837af  ldarg.3
0x837b0  callvirt instance string Microsoft.Crm.View::get_ObjectType()
0x837b5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x837ba  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x837bf  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0x837c4  stfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Application.Platform.Grid.DataProcessorEntity::viewEntityMetadata
0x837c9  ldarg.2
0x837ca  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Application.Platform.Entity>::GetEnumerator()
0x837cf  stloc.1
0x837d0  br       loc_839CA
0x837d5  ldloc.1
0x837d6  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Crm.Application.Platform.Entity>::get_Current()
0x837db  stloc.2
0x837dc  ldarg.1
0x837dd  callvirt instance class [System.Data]System.Data.DataRow [System.Data]System.Data.DataTable::NewRow()
0x837e2  stloc.3
0x837e3  ldarg.0
0x837e4  ldloc.3
0x837e5  ldarg.3
0x837e6  ldloc.2
0x837e7  callvirt instance void Microsoft.Crm.Application.Platform.Grid.DataProcessorEntity::FillRowIdAndType(class [System.Data]System.Data.DataRow row, class Microsoft.Crm.View view, class Microsoft.Crm.Application.Platform.Entity entity)
0x837ec  ldarg.s  4
0x837ee  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x837f3  stloc.s  4
0x837f5  br       loc_838F9
0x837fa  ldloc.s  4
0x837fc  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x83801  castclass Microsoft.Crm.Application.Platform.Grid.Column
0x83806  stloc.s  5
0x83808  ldloc.s  5
0x8380a  callvirt instance bool Microsoft.Crm.Application.Platform.Grid.Column::get_IsFromRelatedEntity()
0x8380f  brfalse.s loc_8382C
0x83811  ldloc.s  5
0x83813  callvirt instance string Microsoft.Crm.Application.Platform.Grid.Column::get_EntityName()
0x83818  ldarg.0
0x83819  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext class Microsoft.Crm.Application.Platform.Grid.DataProcessor`1<class Microsoft.Crm.Application.Platform.ApplicationEntityCollection>::get_Context()
0x8381e  newobj   instance void Microsoft.Crm.Application.Platform.EntityType::.ctor(string logicalName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x83823  call     class Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(class Microsoft.Crm.Application.Platform.EntityType entityType)
0x83828  stloc.s  6
0x8382a  br.s     loc_8382F
0x8382c  ldloc.2
0x8382d  stloc.s  6
0x8382f  ldarg.0
0x83830  ldloc.s  5
0x83832  callvirt instance string Microsoft.Crm.Application.Platform.Grid.Column::get_FieldName()
0x83837  ldloc.s  6
0x83839  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Platform.Grid.DataProcessorEntity::GetAttributeMetadata(string columnName, class Microsoft.Crm.Application.Platform.Entity entity)
0x8383e  stloc.s  7
0x83840  ldarg.0
0x83841  ldloc.s  5
0x83843  callvirt instance string Microsoft.Crm.Application.Platform.Grid.Column::get_Name()
0x83848  ldloc.2
0x83849  ldloc.s  7
0x8384b  callvirt instance class Microsoft.Crm.Application.Platform.Grid.IGridDataProperty Microsoft.Crm.Application.Platform.Grid.DataProcessorEntity::GetProperty(string attributeName, class Microsoft.Crm.Application.Platform.Entity entity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata attributeMetadata)
0x83850  stloc.s  8
0x83852  ldarg.0
0x83853  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Application.Platform.Grid.Column> Microsoft.Crm.Application.Platform.Grid.DataProcessorEntity::columnMap
0x83858  ldloc.s  5
0x8385a  callvirt instance string Microsoft.Crm.Application.Platform.Grid.Column::get_Name()
0x8385f  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Application.Platform.Grid.Column>::ContainsKey(var<u1>)
0x83864  brtrue.s loc_8387A
0x83866  ldarg.0
0x83867  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Application.Platform.Grid.Column> Microsoft.Crm.Application.Platform.Grid.DataProcessorEntity::columnMap
0x8386c  ldloc.s  5
0x8386e  callvirt instance string Microsoft.Crm.Application.Platform.Grid.Column::get_Name()
0x83873  ldloc.s  5
0x83875  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Application.Platform.Grid.Column>::Add(var<u1>, !!T0)
0x8387a  ldarg.0
0x8387b  ldloc.s  7
0x8387d  ldloc.s  5
0x8387f  callvirt instance void Microsoft.Crm.Application.Platform.Grid.DataProcessorEntity::UpdateColumnRendererType(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata attributeMetadata, class Microsoft.Crm.Application.Platform.Grid.Column column)
0x83884  ldarg.0
0x83885  ldloc.s  8
0x83887  ldloc.2
0x83888  ldloc.s  5
0x8388a  ldloc.3
0x8388b  callvirt instance string Microsoft.Crm.Application.Platform.Grid.DataProcessorEntity::ProcessFormattedValue(class Microsoft.Crm.Application.Platform.Grid.IGridDataProperty recordProperty, class Microsoft.Crm.Application.Platform.Entity entity, class Microsoft.Crm.Application.Platform.Grid.Column column, class [System.Data]System.Data.DataRow row)
0x83890  stloc.s  9
0x83892  ldloc.s  5
0x83894  callvirt instance class Microsoft.Crm.Application.Platform.Grid.ColumnUIInfo Microsoft.Crm.Application.Platform.Grid.Column::get_UIInfo()
0x83899  callvirt instance bool Microsoft.Crm.Application.Platform.Grid.ColumnUIInfo::get_IsHidden()
0x8389e  brfalse.s loc_838F9
0x838a0  ldarg.1
0x838a1  ldloc.s  5
0x838a3  callvirt instance string Microsoft.Crm.Application.Platform.Grid.Column::get_Name()
0x838a8  call     void Microsoft.Crm.Application.Platform.Grid.GridData::AddHiddenColumnToDataTable(class [System.Data]System.Data.DataTable dt, string columnName)
0x838ad  ldloc.s  7
0x838af  brfalse.s loc_838BA
0x838b1  ldloc.s  5
0x838b3  callvirt instance bool Microsoft.Crm.Application.Platform.Grid.Column::get_IsFromRelatedEntity()
0x838b8  brfalse.s loc_838D5
0x838ba  ldloc.3
0x838bb  ldloc.s  5
0x838bd  callvirt instance string Microsoft.Crm.Application.Platform.Grid.Column::get_Name()
0x838c2  ldstr    aHidden// "_Hidden"
0x838c7  call     string [mscorlib]System.String::Concat(string, string)
0x838cc  ldloc.s  9
0x838ce  callvirt instance void [System.Data]System.Data.DataRow::set_Item(string, object)
0x838d3  br.s     loc_838F9
0x838d5  ldloc.3
0x838d6  ldloc.s  5
0x838d8  callvirt instance string Microsoft.Crm.Application.Platform.Grid.Column::get_Name()
0x838dd  ldstr    aHidden// "_Hidden"
0x838e2  call     string [mscorlib]System.String::Concat(string, string)
0x838e7  ldloc.2
0x838e8  ldloc.s  5
0x838ea  callvirt instance string Microsoft.Crm.Application.Platform.Grid.Column::get_Name()
0x838ef  callvirt instance string Microsoft.Crm.Application.Platform.EntityProxy::GetPropertyValue(string name)
0x838f4  callvirt instance void [System.Data]System.Data.DataRow::set_Item(string, object)
0x838f9  ldloc.s  4
0x838fb  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x83900  brtrue   loc_837FA
0x83905  leave.s  loc_8391C
0x83907  ldloc.s  4
0x83909  isinst   [mscorlib]System.IDisposable
0x8390e  stloc.s  0xA
0x83910  ldloc.s  0xA
0x83912  brfalse.s loc_8391B
0x83914  ldloc.s  0xA
0x83916  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8391b  endfinally
0x8391c  ldarg.0
0x8391d  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Application.Platform.Grid.DataProcessorEntity::viewEntityMetadata
0x83922  brfalse  loc_839BE
0x83927  ldarg.0
0x83928  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Application.Platform.Grid.DataProcessorEntity::viewEntityMetadata
0x8392d  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsBusinessProcessEnabled()
0x83932  brfalse  loc_839BE
0x83937  ldloc.3
0x83938  callvirt instance class [System.Data]System.Data.DataTable [System.Data]System.Data.DataRow::get_Table()
0x8393d  callvirt instance class [System.Data]System.Data.DataColumnCollection [System.Data]System.Data.DataTable::get_Columns()
0x83942  ldstr    aProcessid// "processid"
0x83947  callvirt instance bool [System.Data]System.Data.DataColumnCollection::Contains(string)
0x8394c  brfalse.s loc_839BE
0x8394e  ldloc.3
0x8394f  callvirt instance class [System.Data]System.Data.DataTable [System.Data]System.Data.DataRow::get_Table()
0x83954  callvirt instance class [System.Data]System.Data.DataColumnCollection [System.Data]System.Data.DataTable::get_Columns()
0x83959  ldstr    aProcessts// "processts"
0x8395e  callvirt instance bool [System.Data]System.Data.DataColumnCollection::Contains(string)
0x83963  brfalse.s loc_839BE
0x83965  ldloc.3
0x83966  ldstr    aProcessid// "processid"
0x8396b  ldloc.2
0x8396c  ldstr    aProcessid// "processid"
0x83971  callvirt instance string Microsoft.Crm.Application.Platform.EntityProxy::GetPropertyValue(string name)
0x83976  callvirt instance void [System.Data]System.Data.DataRow::set_Item(string, object)
0x8397b  ldloc.2
0x8397c  ldstr    aProcessidworkf_0// "processidworkflowworkflowid.versionnumb"...
0x83981  callvirt instance bool Microsoft.Crm.Application.Platform.EntityBase::HasAttribute(string name)
0x83986  brfalse.s loc_839BE
0x83988  ldloc.3
0x83989  ldstr    aProcessts// "processts"
0x8398e  ldloc.2
0x8398f  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> Microsoft.Crm.Application.Platform.EntityBase::get_Properties()
0x83994  ldstr    aProcessidworkf_0// "processidworkflowworkflowid.versionnumb"...
0x83999  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::get_Item(void)
0x8399e  callvirt instance void [System.Data]System.Data.DataRow::set_Item(string, object)
0x839a3  ldloc.3
0x839a4  ldstr    aProcesstsHidde// "processts_Hidden"
0x839a9  ldloc.2
0x839aa  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> Microsoft.Crm.Application.Platform.EntityBase::get_Properties()
0x839af  ldstr    aProcessidworkf_0// "processidworkflowworkflowid.versionnumb"...
0x839b4  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::get_Item(void)
0x839b9  callvirt instance void [System.Data]System.Data.DataRow::set_Item(string, object)
0x839be  ldarg.1
0x839bf  callvirt instance class [System.Data]System.Data.DataRowCollection [System.Data]System.Data.DataTable::get_Rows()
0x839c4  ldloc.3
0x839c5  callvirt instance void [System.Data]System.Data.DataRowCollection::Add(class [System.Data]System.Data.DataRow)
0x839ca  ldloc.1
0x839cb  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x839d0  brtrue   loc_837D5
0x839d5  leave.s  loc_839E1
0x839d7  ldloc.1
0x839d8  brfalse.s loc_839E0
0x839da  ldloc.1
0x839db  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x839e0  endfinally
0x839e1  ret
```
