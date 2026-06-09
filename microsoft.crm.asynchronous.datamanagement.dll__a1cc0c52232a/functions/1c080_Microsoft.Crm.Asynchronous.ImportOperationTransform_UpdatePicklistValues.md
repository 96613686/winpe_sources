# Microsoft.Crm.Asynchronous.ImportOperationTransform::UpdatePicklistValues

- ea: `0x1c080`
- end: `0x1c175`
- name: `Microsoft.Crm.Asynchronous.ImportOperationTransform::UpdatePicklistValues`
- size: `245`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1b860`

## callees

- `0x3b80`
- `0x5ed0`
- `0x8f70`
- `0xba70`
- `0xbcb0`
- `0x1c080`
- `0x1c180`

## pseudocode

```c

```

## disassembly

```asm
0x1c080  ldnull
0x1c081  stloc.0
0x1c082  ldarg.0
0x1c083  ldfld    class Microsoft.Crm.Asynchronous.ImportHelperData Microsoft.Crm.Asynchronous.ImportOperation::_importDataStructure
0x1c088  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.ImportFileHelperData> Microsoft.Crm.Asynchronous.ImportHelperData::get_ImportFileIdToImportFileHelperDataDictionary()
0x1c08d  ldarg.1
0x1c08e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.ImportFileHelperData>::get_Item(void)
0x1c093  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.ImportFileHelperData::get_ImportFile()
0x1c098  ldstr    aParsedtablenam_0// "parsedtablename"
0x1c09d  call     string Microsoft.Crm.Asynchronous.DataManagementHelper::GetStringFromDynamicEntity(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity de, string propertyName)
0x1c0a2  stloc.1
0x1c0a3  ldarg.0
0x1c0a4  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IConfiguration Microsoft.Crm.Asynchronous.ImportOperation::_configuration
0x1c0a9  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IImportConfiguration::get_BatchSize()
0x1c0ae  stloc.2
0x1c0af  ldc.i4.1
0x1c0b0  conv.i8
0x1c0b1  stloc.3
0x1c0b2  ldarg.0
0x1c0b3  ldloc.1
0x1c0b4  call     instance int32 Microsoft.Crm.Asynchronous.ImportOperation::GetTotalNumberOfRecords(string tableName)
0x1c0b9  conv.i8
0x1c0ba  stloc.s  4
0x1c0bc  ldloc.2
0x1c0bd  conv.i8
0x1c0be  stloc.s  5
0x1c0c0  ldarg.0
0x1c0c1  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_Configuration()
0x1c0c6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x1c0cb  ldc.i4   0x12C
0x1c0d0  ldc.i4.0
0x1c0d1  ldc.i4.0
0x1c0d2  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid, int32, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x1c0d7  stloc.s  6
0x1c0d9  ldloc.s  6
0x1c0db  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0x1c0e0  ldloc.s  6
0x1c0e2  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand()
0x1c0e7  stloc.s  7
0x1c0e9  br.s     loc_1C151
0x1c0eb  ldloc.s  6
0x1c0ed  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection)
0x1c0f2  stloc.s  8
0x1c0f4  ldloc.s  8
0x1c0f6  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction::StartTransaction()
0x1c0fb  ldarg.0
0x1c0fc  ldarg.1
0x1c0fd  ldarg.2
0x1c0fe  ldloc.s  7
0x1c100  ldloc.3
0x1c101  ldloc.s  5
0x1c103  call     instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncHandlerResult Microsoft.Crm.Asynchronous.ImportOperationTransform::UpdatePicklistValuesInBatches(valuetype [mscorlib]System.Guid importFileId, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.PicklistValueMappings> valueMappingsCollection, class [System.Data]System.Data.IDbCommand command, int64 lowerCount, int64 upperCount)
0x1c108  stloc.0
0x1c109  ldloc.0
0x1c10a  brfalse.s loc_1C119
0x1c10c  ldloc.s  8
0x1c10e  ldc.i4.0
0x1c10f  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction::RollbackTransaction(bool)
0x1c114  ldloc.0
0x1c115  stloc.s  9
0x1c117  leave.s  loc_1C172
0x1c119  ldarg.0
0x1c11a  call     instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncHandlerResult Microsoft.Crm.Asynchronous.ImportOperation::HasJobBeenAbortedOrPaused()
0x1c11f  dup
0x1c120  stloc.0
0x1c121  brfalse.s loc_1C130
0x1c123  ldloc.s  8
0x1c125  ldc.i4.0
0x1c126  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction::RollbackTransaction(bool)
0x1c12b  ldloc.0
0x1c12c  stloc.s  9
0x1c12e  leave.s  loc_1C172
0x1c130  ldloc.s  8
0x1c132  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction::CommitTransaction()
0x1c137  ldloc.3
0x1c138  ldloc.2
0x1c139  conv.i8
0x1c13a  add
0x1c13b  stloc.3
0x1c13c  ldloc.s  5
0x1c13e  ldloc.2
0x1c13f  conv.i8
0x1c140  add
0x1c141  stloc.s  5
0x1c143  leave.s  loc_1C151
0x1c145  ldloc.s  8
0x1c147  brfalse.s loc_1C150
0x1c149  ldloc.s  8
0x1c14b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1c150  endfinally
0x1c151  ldloc.3
0x1c152  ldloc.s  4
0x1c154  ble.s    loc_1C0EB
0x1c156  leave.s  loc_1C170
0x1c158  ldloc.s  7
0x1c15a  brfalse.s loc_1C163
0x1c15c  ldloc.s  7
0x1c15e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1c163  endfinally
0x1c164  ldloc.s  6
0x1c166  brfalse.s loc_1C16F
0x1c168  ldloc.s  6
0x1c16a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1c16f  endfinally
0x1c170  ldloc.0
0x1c171  ret
0x1c172  ldloc.s  9
0x1c174  ret
```
