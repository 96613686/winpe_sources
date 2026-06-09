# Microsoft.Crm.Asynchronous.ImportOperationTransform::UpdatePicklistValuesInBatches

- ea: `0x1c180`
- end: `0x1c3a9`
- name: `Microsoft.Crm.Asynchronous.ImportOperationTransform::UpdatePicklistValuesInBatches`
- size: `553`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1c080`

## callees

- `0x3b80`
- `0x4420`
- `0x5b70`
- `0x5b80`
- `0x5b90`
- `0x5ed0`
- `0x8f70`
- `0xbcb0`
- `0x1c180`
- `0x1c3b0`
- `0x1c450`
- `0x1c520`
- `0x1c5c0`

## string_xrefs

- `0x1c361`: `UPDATE {0} SET IsTransformed = {1} WHERE SN BETWEEN {2} AND {3}`

## pseudocode

```c

```

## disassembly

```asm
0x1c180  ldnull
0x1c181  stloc.0
0x1c182  ldarg.0
0x1c183  ldfld    class Microsoft.Crm.Asynchronous.ImportHelperData Microsoft.Crm.Asynchronous.ImportOperation::_importDataStructure
0x1c188  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.ImportFileHelperData> Microsoft.Crm.Asynchronous.ImportHelperData::get_ImportFileIdToImportFileHelperDataDictionary()
0x1c18d  ldarg.1
0x1c18e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.ImportFileHelperData>::get_Item(void)
0x1c193  dup
0x1c194  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.ImportFileHelperData::get_ImportFile()
0x1c199  ldstr    aParsedtablenam_0// "parsedtablename"
0x1c19e  call     string Microsoft.Crm.Asynchronous.DataManagementHelper::GetStringFromDynamicEntity(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity de, string propertyName)
0x1c1a3  stloc.1
0x1c1a4  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.ImportFileHelperData::get_ImportFile()
0x1c1a9  ldstr    aParsedtablecol// "parsedtablecolumnprefix"
0x1c1ae  call     string Microsoft.Crm.Asynchronous.DataManagementHelper::GetStringFromDynamicEntity(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity de, string propertyName)
0x1c1b3  pop
0x1c1b4  ldarg.2
0x1c1b5  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.PicklistValueMappings>::get_Count()
0x1c1ba  ldc.i4.0
0x1c1bb  bgt.s    loc_1C1E9
0x1c1bd  ldarg.0
0x1c1be  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_Configuration()
0x1c1c3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x1c1c8  ldc.i4.s 0x18
0x1c1ca  ldstr    aNoValuesFoundF_1// "No values found for updating picklist c"...
0x1c1cf  ldc.i4.2
0x1c1d0  newarr   [mscorlib]System.Object
0x1c1d5  dup
0x1c1d6  ldc.i4.0
0x1c1d7  ldloc.1
0x1c1d8  stelem.ref
0x1c1d9  dup
0x1c1da  ldc.i4.1
0x1c1db  ldarg.1
0x1c1dc  box      [mscorlib]System.Guid
0x1c1e1  stelem.ref
0x1c1e2  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1c1e7  ldloc.0
0x1c1e8  ret
0x1c1e9  ldarg.0
0x1c1ea  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IConfiguration Microsoft.Crm.Asynchronous.ImportOperation::_configuration
0x1c1ef  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IImportConfiguration::get_PickListBatchSize()
0x1c1f4  stloc.2
0x1c1f5  ldarg.2
0x1c1f6  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.PicklistValueMappings>::GetEnumerator()
0x1c1fb  stloc.3
0x1c1fc  br       loc_1C334
0x1c201  ldloca.s 3
0x1c203  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Asynchronous.PicklistValueMappings>::get_Current()
0x1c208  stloc.s  4
0x1c20a  ldloc.s  4
0x1c20c  callvirt instance class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Asynchronous.PicklistValueMappings::get_SourceValues()
0x1c211  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<string>::get_Count()
0x1c216  stloc.s  5
0x1c218  ldloc.2
0x1c219  ldloc.s  5
0x1c21b  bge.s    loc_1C236
0x1c21d  ldarg.0
0x1c21e  ldloc.s  4
0x1c220  callvirt instance class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Asynchronous.PicklistValueMappings::get_SourceValues()
0x1c225  ldloc.s  4
0x1c227  callvirt instance class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Asynchronous.PicklistValueMappings::get_TargetValues()
0x1c22c  call     instance bool Microsoft.Crm.Asynchronous.ImportOperationTransform::FindCyclicReferencesInData(class [mscorlib]System.Collections.Generic.List`1<string> sourceValueArray, class [mscorlib]System.Collections.Generic.List`1<string> crmValueArray)
0x1c231  brfalse.s loc_1C236
0x1c233  ldloc.s  5
0x1c235  stloc.2
0x1c236  ldc.i4.0
0x1c237  stloc.s  6
0x1c239  ldc.i4.0
0x1c23a  stloc.s  7
0x1c23c  br       loc_1C32B
0x1c241  ldarg.3
0x1c242  ldsfld   string [mscorlib]System.String::Empty
0x1c247  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x1c24c  ldarg.3
0x1c24d  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x1c252  callvirt instance void [mscorlib]System.Collections.IList::Clear()
0x1c257  ldloc.s  5
0x1c259  ldloc.s  6
0x1c25b  ldloc.2
0x1c25c  add
0x1c25d  bgt.s    loc_1C265
0x1c25f  ldloc.s  5
0x1c261  stloc.s  7
0x1c263  br.s     loc_1C26B
0x1c265  ldloc.s  6
0x1c267  ldloc.2
0x1c268  add
0x1c269  stloc.s  7
0x1c26b  ldarg.0
0x1c26c  ldloc.1
0x1c26d  ldloc.s  4
0x1c26f  callvirt instance string Microsoft.Crm.Asynchronous.PicklistValueMappings::get_ParsedTableColumnName()
0x1c274  ldloc.s  6
0x1c276  ldloc.s  7
0x1c278  call     instance string Microsoft.Crm.Asynchronous.ImportOperationTransform::GetValueUpdateSqlString(string tableName, string columnName, int32 lowerBound, int32 upperBound)
0x1c27d  stloc.s  8
0x1c27f  ldarg.3
0x1c280  ldarg.0
0x1c281  ldloc.s  8
0x1c283  ldloc.1
0x1c284  ldarg.s  4
0x1c286  ldarg.s  5
0x1c288  call     instance string Microsoft.Crm.Asynchronous.ImportOperationTransform::UpdateSqlWithPagingConditionPickList(string strSQL, string tableName, int64 countNumber, int64 maxLimit)
0x1c28d  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x1c292  ldarg.3
0x1c293  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x1c298  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x1c29d  stloc.s  9
0x1c29f  ldloc.s  6
0x1c2a1  stloc.s  0xA
0x1c2a3  br.s     loc_1C303
0x1c2a5  ldloc.s  9
0x1c2a7  ldstr    aOldval// "@oldVal"
0x1c2ac  ldloca.s 0xA
0x1c2ae  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1c2b3  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x1c2b8  call     string [mscorlib]System.String::Concat(string, string)
0x1c2bd  ldloc.s  4
0x1c2bf  callvirt instance class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Asynchronous.PicklistValueMappings::get_SourceValues()
0x1c2c4  ldloc.s  0xA
0x1c2c6  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<string>::get_Item(!!T0)
0x1c2cb  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1c2d0  pop
0x1c2d1  ldloc.s  9
0x1c2d3  ldstr    aNewval// "@newVal"
0x1c2d8  ldloca.s 0xA
0x1c2da  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1c2df  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x1c2e4  call     string [mscorlib]System.String::Concat(string, string)
0x1c2e9  ldloc.s  4
0x1c2eb  callvirt instance class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Asynchronous.PicklistValueMappings::get_TargetValues()
0x1c2f0  ldloc.s  0xA
0x1c2f2  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<string>::get_Item(!!T0)
0x1c2f7  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1c2fc  pop
0x1c2fd  ldloc.s  0xA
0x1c2ff  ldc.i4.1
0x1c300  add
0x1c301  stloc.s  0xA
0x1c303  ldloc.s  0xA
0x1c305  ldloc.s  7
0x1c307  blt.s    loc_1C2A5
0x1c309  ldarg.0
0x1c30a  ldarg.3
0x1c30b  ldloc.1
0x1c30c  ldloc.s  4
0x1c30e  callvirt instance string Microsoft.Crm.Asynchronous.PicklistValueMappings::get_ParsedTableColumnName()
0x1c313  call     instance void Microsoft.Crm.Asynchronous.ImportOperationTransform::ExecuteSQLWithErrorHandling(class [System.Data]System.Data.IDbCommand sqlCommand, string tableName, string columnName)
0x1c318  ldarg.0
0x1c319  call     instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncHandlerResult Microsoft.Crm.Asynchronous.ImportOperation::HasJobBeenAbortedOrPaused()
0x1c31e  dup
0x1c31f  stloc.0
0x1c320  brfalse.s loc_1C327
0x1c322  ldloc.0
0x1c323  stloc.s  0xB
0x1c325  leave.s  loc_1C3A6
0x1c327  ldloc.s  7
0x1c329  stloc.s  6
0x1c32b  ldloc.s  6
0x1c32d  ldloc.s  5
0x1c32f  blt      loc_1C241
0x1c334  ldloca.s 3
0x1c336  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Asynchronous.PicklistValueMappings>::MoveNext()
0x1c33b  brtrue   loc_1C201
0x1c340  leave.s  loc_1C350
0x1c342  ldloca.s 3
0x1c344  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Asynchronous.PicklistValueMappings>
0x1c34a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1c34f  endfinally
0x1c350  ldarg.3
0x1c351  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x1c356  callvirt instance void [mscorlib]System.Collections.IList::Clear()
0x1c35b  ldarg.3
0x1c35c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1c361  ldstr    aUpdate0SetIstr_0// "UPDATE {0} SET IsTransformed = {1} WHER"...
0x1c366  ldc.i4.4
0x1c367  newarr   [mscorlib]System.Object
0x1c36c  dup
0x1c36d  ldc.i4.0
0x1c36e  ldloc.1
0x1c36f  stelem.ref
0x1c370  dup
0x1c371  ldc.i4.1
0x1c372  ldc.i4.s 9
0x1c374  box      [mscorlib]System.Int32
0x1c379  stelem.ref
0x1c37a  dup
0x1c37b  ldc.i4.2
0x1c37c  ldarg.s  4
0x1c37e  box      [mscorlib]System.Int64
0x1c383  stelem.ref
0x1c384  dup
0x1c385  ldc.i4.3
0x1c386  ldarg.s  5
0x1c388  box      [mscorlib]System.Int64
0x1c38d  stelem.ref
0x1c38e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1c393  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x1c398  ldarg.0
0x1c399  ldfld    class Microsoft.Crm.Asynchronous.ImportDataAccess Microsoft.Crm.Asynchronous.ImportOperation::_importDataAccess
0x1c39e  ldarg.3
0x1c39f  callvirt instance void Microsoft.Crm.Asynchronous.ImportDataAccess::ExecuteSQLCommandWithExtendedTimeout(class [System.Data]System.Data.IDbCommand command)
0x1c3a4  ldloc.0
0x1c3a5  ret
0x1c3a6  ldloc.s  0xB
0x1c3a8  ret
```
