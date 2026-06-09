# Microsoft.Crm.Asynchronous.ImportOperationImportFile::SetStateForIncident

- ea: `0x13300`
- end: `0x133d7`
- name: `Microsoft.Crm.Asynchronous.ImportOperationImportFile::SetStateForIncident`
- size: `215`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x12d00`

## callees

- `0x51f0`
- `0x8f80`
- `0x13300`
- `0x13670`

## string_xrefs

- `0x13378`: `The record was created but the state could not be changed to target value: `

## pseudocode

```c

```

## disassembly

```asm
0x13300  ldarg.s  5
0x13302  switch   loc_13318, loc_1332D, loc_1331A
0x13313  br       loc_133C3
0x13318  ldc.i4.1
0x13319  ret
0x1331a  ldarg.0
0x1331b  ldarg.1
0x1331c  ldarg.2
0x1331d  ldarg.3
0x1331e  ldarg.s  4
0x13320  ldarg.s  5
0x13322  ldc.i4.6
0x13323  ldarg.s  7
0x13325  ldarg.s  8
0x13327  call     instance bool Microsoft.Crm.Asynchronous.ImportOperationImportFile::SWSSetState(valuetype [mscorlib]System.Guid organizationId, string entityName, valuetype [mscorlib]System.Guid entityId, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StateAttributeMetadata stateMetadata, int32 stateCodeValue, int32 statusCode, valuetype [mscorlib]System.Guid importFileId, valuetype [mscorlib]System.Guid importDataId)
0x1332c  ret
0x1332d  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x13332  stloc.0
0x13333  ldarg.0
0x13334  ldfld    class Microsoft.Crm.Asynchronous.ImportHelperData Microsoft.Crm.Asynchronous.ImportOperation::_importDataStructure
0x13339  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid> Microsoft.Crm.Asynchronous.ImportHelperData::get_SourceEntityToImportFileIdDictionary()
0x1333e  ldstr    aIncidentResolu// "Incident Resolution"
0x13343  ldloca.s 0
0x13345  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::TryGetValue(var<u1>, !!T0)
0x1334a  pop
0x1334b  ldloc.0
0x1334c  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x13351  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x13356  brfalse.s loc_1335A
0x13358  ldc.i4.1
0x13359  ret
0x1335a  ldnull
0x1335b  ldarg.1
0x1335c  ldc.i4.s 0x18
0x1335e  ldstr    aMissingInciden// "Missing Incident Resolution Import file"...
0x13363  ldc.i4.1
0x13364  newarr   [mscorlib]System.Object
0x13369  dup
0x1336a  ldc.i4.0
0x1336b  ldarg.s  8
0x1336d  box      [mscorlib]System.Guid
0x13372  stelem.ref
0x13373  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x13378  ldstr    aTheRecordWasCr// "The record was created but the state co"...
0x1337d  stloc.1
0x1337e  ldarg.0
0x1337f  ldfld    class Microsoft.Crm.Asynchronous.ImportDataAccess Microsoft.Crm.Asynchronous.ImportOperation::_importDataAccess
0x13384  ldarg.0
0x13385  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ImportOperation::_contextUserId
0x1338a  ldarg.0
0x1338b  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ImportOperation::_contextUserBusinessUnitId
0x13390  ldarg.s  7
0x13392  ldarg.s  8
0x13394  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0x13399  ldarg.0
0x1339a  ldfld    valuetype PassPhase Microsoft.Crm.Asynchronous.ImportOperationImportFile::_passPhase
0x1339f  ldc.i4.2
0x133a0  beq.s    loc_133A5
0x133a2  ldc.i4.2
0x133a3  br.s     loc_133A6
0x133a5  ldc.i4.3
0x133a6  ldsfld   string [mscorlib]System.String::Empty
0x133ab  ldsfld   string [mscorlib]System.String::Empty
0x133b0  ldc.i4   0x80040357
0x133b5  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x133ba  ldloc.1
0x133bb  ldc.i4.1
0x133bc  callvirt instance void Microsoft.Crm.Asynchronous.ImportDataAccess::CreateImportLogRow(valuetype [mscorlib]System.Guid ownerId, valuetype [mscorlib]System.Guid businessUnitId, valuetype [mscorlib]System.Guid importFileId, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> importDataId, int32 logPhaseCode, string headerColumn, string columnValue, valuetype [mscorlib]System.Nullable`1<int32> errorNumber, string additionalInfo, int32 errorType)
0x133c1  ldc.i4.0
0x133c2  ret
0x133c3  ldarg.0
0x133c4  ldarg.1
0x133c5  ldarg.2
0x133c6  ldarg.3
0x133c7  ldarg.s  4
0x133c9  ldarg.s  5
0x133cb  ldarg.s  6
0x133cd  ldarg.s  7
0x133cf  ldarg.s  8
0x133d1  call     instance bool Microsoft.Crm.Asynchronous.ImportOperationImportFile::SWSSetState(valuetype [mscorlib]System.Guid organizationId, string entityName, valuetype [mscorlib]System.Guid entityId, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StateAttributeMetadata stateMetadata, int32 stateCodeValue, int32 statusCode, valuetype [mscorlib]System.Guid importFileId, valuetype [mscorlib]System.Guid importDataId)
0x133d6  ret
```
