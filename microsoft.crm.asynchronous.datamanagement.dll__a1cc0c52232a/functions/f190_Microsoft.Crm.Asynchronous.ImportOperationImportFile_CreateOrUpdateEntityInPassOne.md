# Microsoft.Crm.Asynchronous.ImportOperationImportFile::CreateOrUpdateEntityInPassOne

- ea: `0xf190`
- end: `0xfcf5`
- name: `Microsoft.Crm.Asynchronous.ImportOperationImportFile::CreateOrUpdateEntityInPassOne`
- size: `2917`
- prototype: ``
- caller_count: `1`
- callee_count: `49`
- tags: `installer_update, broker_com_uri`

## callers

- `0xe550`

## callees

- `0x3b80`
- `0x3c70`
- `0x45a0`
- `0x4670`
- `0x51d0`
- `0x51f0`
- `0x5be0`
- `0x5c00`
- `0x5c30`
- `0x5c50`
- `0x5c60`
- `0x5c80`
- `0x5ed0`
- `0x5ee0`
- `0x5ef0`
- `0x5f20`
- `0x5f40`
- `0x5f50`
- `0x5fb0`
- `0x5fc0`
- `0x5ff0`
- `0x6000`
- `0x6030`
- `0x60c0`
- `0x6190`
- `0x61d0`
- `0x8f30`
- `0x8f40`
- `0x8f70`
- `0xea10`
- `0xee20`
- `0xf190`
- `0xfd00`
- `0xfd90`
- `0x100c0`
- `0x10100`
- `0x10620`
- `0x11690`
- `0x11a20`
- `0x12610`
- `0x128c0`
- `0x12ce0`
- `0x12d00`
- `0x133e0`
- `0x13990`
- `0x13b80`
- `0x13bc0`
- `0x13dd0`
- `0x13ee0`

## string_xrefs

- `0xf2ed`: `Entity {0}:{1} has possibly been deleted from CRM`
- `0xfa2f`: `UPDATE {0} SET {1}='{2}' WHERE {3}='{4}'`

## pseudocode

```c

```

## disassembly

```asm
0xf190  ldarg.0
0xf191  ldfld    class Microsoft.Crm.Asynchronous.ImportHelperData Microsoft.Crm.Asynchronous.ImportOperation::_importDataStructure
0xf196  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.ImportFileHelperData> Microsoft.Crm.Asynchronous.ImportHelperData::get_ImportFileIdToImportFileHelperDataDictionary()
0xf19b  ldarg.2
0xf19c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.ImportFileHelperData>::get_Item(void)
0xf1a1  stloc.0
0xf1a2  ldarg.0
0xf1a3  ldarg.2
0xf1a4  call     instance int32 Microsoft.Crm.Asynchronous.ImportOperationImportFile::GetImportFileType(valuetype [mscorlib]System.Guid importFileId)
0xf1a9  stloc.1
0xf1aa  ldloc.0
0xf1ab  callvirt instance string Microsoft.Crm.Asynchronous.ImportFileHelperData::get_TargetEntityName()
0xf1b0  stloc.2
0xf1b1  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor()
0xf1b6  stloc.3
0xf1b7  ldloc.3
0xf1b8  ldloc.2
0xf1b9  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_LogicalName(string)
0xf1be  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xf1c3  stloc.s  4
0xf1c5  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xf1ca  stloc.s  5
0xf1cc  ldc.i4.0
0xf1cd  stloc.s  6
0xf1cf  newobj   instance void Microsoft.Crm.Asynchronous.StateStatusHelper::.ctor()
0xf1d4  stloc.s  7
0xf1d6  ldsfld   string [mscorlib]System.String::Empty
0xf1db  stloc.s  8
0xf1dd  ldsfld   string [mscorlib]System.String::Empty
0xf1e2  stloc.s  9
0xf1e4  ldarg.1
0xf1e5  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0xf1ea  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xf1ef  ldloc.2
0xf1f0  ldc.i4.1
0xf1f1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0xf1f6  stloc.s  0xA
0xf1f8  ldloc.s  0xA
0xf1fa  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0xf1ff  ldstr    aOpportunity// "opportunity"
0xf204  ldc.i4.4
0xf205  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0xf20a  stloc.s  0xB
0xf20c  ldloc.s  0xA
0xf20e  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0xf213  ldstr    aIncidentresolu// "incidentresolution"
0xf218  ldc.i4.4
0xf219  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0xf21e  stloc.s  0xC
0xf220  ldloc.s  0xA
0xf222  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0xf227  ldstr    aDynamicpropert// "dynamicpropertyoptionsetitem"
0xf22c  ldc.i4.4
0xf22d  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0xf232  stloc.s  0xD
0xf234  ldsfld   string [mscorlib]System.String::Empty
0xf239  stloc.s  0xE
0xf23b  ldsfld   string [mscorlib]System.String::Empty
0xf240  stloc.s  0xF
0xf242  ldloc.0
0xf243  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.ImportFileHelperData::get_ImportFile()
0xf248  ldstr    aDatadelimiterc// "datadelimitercode"
0xf24d  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0xf252  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue
0xf257  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::get_Value()
0xf25c  call     string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CsvDataParser::GetDataDelimiter(int32)
0xf261  stloc.s  0x10
0xf263  ldloc.s  0xA
0xf265  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_HasStateCode()
0xf26a  brfalse.s loc_F28F
0xf26c  ldloc.s  0xA
0xf26e  ldstr    aStatecode// "statecode"
0xf273  ldc.i4.1
0xf274  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0xf279  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StateAttributeMetadata
0xf27e  stloc.s  0x15
0xf280  ldloc.s  7
0xf282  ldloc.s  0x15
0xf284  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StateAttributeMetadata::get_DefaultValue()
0xf289  ldc.i4.m1
0xf28a  callvirt instance void Microsoft.Crm.Asynchronous.StateStatusHelper::SetStateStatus(int32 stateCode, int32 statusCode)
0xf28f  ldsfld   string [mscorlib]System.String::Empty
0xf294  stloc.s  0x11
0xf296  ldc.i4.0
0xf297  stloc.s  0x12
0xf299  ldarg.3
0xf29a  ldc.i4.2
0xf29b  ldelem.ref
0xf29c  unbox.any [mscorlib]System.Guid
0xf2a1  stloc.s  4
0xf2a3  ldarg.3
0xf2a4  ldc.i4.3
0xf2a5  ldelem.ref
0xf2a6  unbox.any [mscorlib]System.Boolean
0xf2ab  stloc.s  6
0xf2ad  ldarg.3
0xf2ae  ldc.i4.4
0xf2af  ldelem.ref
0xf2b0  unbox.any [mscorlib]System.Guid
0xf2b5  stloc.s  5
0xf2b7  ldloc.s  6
0xf2b9  brfalse.s loc_F2D0
0xf2bb  ldarg.0
0xf2bc  ldfld    class Microsoft.Crm.Asynchronous.ImportHelperData Microsoft.Crm.Asynchronous.ImportOperation::_importDataStructure
0xf2c1  callvirt instance int32 Microsoft.Crm.Asynchronous.ImportHelperData::get_ImportMode()
0xf2c6  brtrue.s loc_F2D0
0xf2c8  ldc.i4.1
0xf2c9  stloc.s  0x17
0xf2cb  leave    loc_FCF2
0xf2d0  ldnull
0xf2d1  stloc.s  0x16
0xf2d3  ldloc.s  6
0xf2d5  brfalse  loc_F44E
0xf2da  ldarg.s  4
0xf2dc  brfalse.s loc_F2E9
0xf2de  ldarg.s  4
0xf2e0  ldloc.s  5
0xf2e2  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::ContainsKey(var<u1>)
0xf2e7  brtrue.s loc_F363
0xf2e9  ldnull
0xf2ea  ldarg.1
0xf2eb  ldc.i4.s 0x18
0xf2ed  ldstr    aEntity01HasPos// "Entity {0}:{1} has possibly been delete"...
0xf2f2  ldc.i4.2
0xf2f3  newarr   [mscorlib]System.Object
0xf2f8  dup
0xf2f9  ldc.i4.0
0xf2fa  ldloc.2
0xf2fb  stelem.ref
0xf2fc  dup
0xf2fd  ldc.i4.1
0xf2fe  ldloc.s  5
0xf300  box      [mscorlib]System.Guid
0xf305  stelem.ref
0xf306  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xf30b  ldloc.0
0xf30c  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.ImportFileHelperData::get_PrimaryKeyColumnMapping()
0xf311  ldstr    aSourceattribut// "sourceattributename"
0xf316  call     string Microsoft.Crm.Asynchronous.DataManagementHelper::GetStringFromDynamicEntity(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity de, string propertyName)
0xf31b  stloc.s  8
0xf31d  ldarg.0
0xf31e  ldfld    class Microsoft.Crm.Asynchronous.ImportDataAccess Microsoft.Crm.Asynchronous.ImportOperation::_importDataAccess
0xf323  ldarg.0
0xf324  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ImportOperation::_contextUserId
0xf329  ldarg.0
0xf32a  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ImportOperation::_contextUserBusinessUnitId
0xf32f  ldarg.2
0xf330  ldloc.s  4
0xf332  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0xf337  ldc.i4.3
0xf338  ldloc.s  8
0xf33a  ldloca.s 5
0xf33c  constrained. [mscorlib]System.Guid
0xf342  callvirt instance string [mscorlib]System.Object::ToString()
0xf347  ldc.i4   0x8004F603
0xf34c  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0xf351  ldsfld   string [mscorlib]System.String::Empty
0xf356  callvirt instance void Microsoft.Crm.Asynchronous.ImportDataAccess::CreateImportLogRow(valuetype [mscorlib]System.Guid ownerId, valuetype [mscorlib]System.Guid businessUnitId, valuetype [mscorlib]System.Guid importFileId, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> importDataId, int32 logPhaseCode, string headerColumn, string columnValue, valuetype [mscorlib]System.Nullable`1<int32> errorNumber, string additionalInfo)
0xf35b  ldc.i4.0
0xf35c  stloc.s  0x17
0xf35e  leave    loc_FCF2
0xf363  ldarg.s  4
0xf365  ldloc.s  5
0xf367  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Item(void)
0xf36c  stloc.s  0x16
0xf36e  ldarg.0
0xf36f  ldarg.3
0xf370  ldc.i4.7
0xf371  ldelem.ref
0xf372  castclass [mscorlib]System.String
0xf377  ldloc.s  0x16
0xf379  ldloc.1
0xf37a  call     instance bool Microsoft.Crm.Asynchronous.ImportOperationImportFile::ValidateModifiedOnForUpdate(string attributeValue, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity originalEntity, int32 fileTypeCode)
0xf37f  brtrue.s loc_F3EE
0xf381  ldnull
0xf382  ldarg.1
0xf383  ldc.i4.s 0x18
0xf385  ldstr    aModifiedOnFiel// "Modified on field of record {0}:{1} in "...
0xf38a  ldc.i4.2
0xf38b  newarr   [mscorlib]System.Object
0xf390  dup
0xf391  ldc.i4.0
0xf392  ldloc.2
0xf393  stelem.ref
0xf394  dup
0xf395  ldc.i4.1
0xf396  ldloc.s  5
0xf398  box      [mscorlib]System.Guid
0xf39d  stelem.ref
0xf39e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xf3a3  ldloc.0
0xf3a4  callvirt instance string[] Microsoft.Crm.Asynchronous.ImportFileHelperData::get_HeaderColumns()
0xf3a9  ldc.i4.2
0xf3aa  ldelem.ref
0xf3ab  stloc.s  8
0xf3ad  ldarg.0
0xf3ae  ldfld    class Microsoft.Crm.Asynchronous.ImportDataAccess Microsoft.Crm.Asynchronous.ImportOperation::_importDataAccess
0xf3b3  ldarg.0
0xf3b4  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ImportOperation::_contextUserId
0xf3b9  ldarg.0
0xf3ba  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ImportOperation::_contextUserBusinessUnitId
0xf3bf  ldarg.2
0xf3c0  ldloc.s  4
0xf3c2  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0xf3c7  ldc.i4.3
0xf3c8  ldloc.s  8
0xf3ca  ldarg.3
0xf3cb  ldc.i4.7
0xf3cc  ldelem.ref
0xf3cd  castclass [mscorlib]System.String
0xf3d2  ldc.i4   0x80040376
0xf3d7  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0xf3dc  ldsfld   string [mscorlib]System.String::Empty
0xf3e1  callvirt instance void Microsoft.Crm.Asynchronous.ImportDataAccess::CreateImportLogRow(valuetype [mscorlib]System.Guid ownerId, valuetype [mscorlib]System.Guid businessUnitId, valuetype [mscorlib]System.Guid importFileId, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> importDataId, int32 logPhaseCode, string headerColumn, string columnValue, valuetype [mscorlib]System.Nullable`1<int32> errorNumber, string additionalInfo)
0xf3e6  ldc.i4.0
0xf3e7  stloc.s  0x17
0xf3e9  leave    loc_FCF2
0xf3ee  ldloc.s  0x16
0xf3f0  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0xf3f5  ldstr    aStatecode// "statecode"
0xf3fa  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0xf3ff  brfalse.s loc_F41E
0xf401  ldloc.s  7
0xf403  ldloc.s  0x16
0xf405  ldstr    aStatecode// "statecode"
0xf40a  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0xf40f  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue
0xf414  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::get_Value()
0xf419  callvirt instance void Microsoft.Crm.Asynchronous.StateStatusHelper::set_OldStateCode(int32 value)
0xf41e  ldloc.s  0x16
0xf420  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0xf425  ldstr    aStatuscode// "statuscode"
0xf42a  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0xf42f  brfalse.s loc_F44E
0xf431  ldloc.s  7
0xf433  ldloc.s  0x16
0xf435  ldstr    aStatuscode// "statuscode"
0xf43a  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0xf43f  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue
0xf444  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::get_Value()
0xf449  callvirt instance void Microsoft.Crm.Asynchronous.StateStatusHelper::set_OldStatusCode(int32 value)
0xf44e  leave.s  loc_F4BC
0xf450  stloc.s  0x18
0xf452  ldloc.s  0x18
0xf454  ldarg.1
0xf455  ldc.i4.s 0x18
0xf457  ldstr    aAnExceptionOcc_3// "An exception occurred in validating the"...
0xf45c  ldc.i4.1
0xf45d  newarr   [mscorlib]System.Object
0xf462  dup
0xf463  ldc.i4.0
0xf464  ldloc.s  0x18
0xf466  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0xf46b  stelem.ref
0xf46c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xf471  ldloc.0
0xf472  callvirt instance string[] Microsoft.Crm.Asynchronous.ImportFileHelperData::get_HeaderColumns()
0xf477  ldc.i4.2
0xf478  ldelem.ref
0xf479  stloc.s  8
0xf47b  ldarg.0
0xf47c  ldfld    class Microsoft.Crm.Asynchronous.ImportDataAccess Microsoft.Crm.Asynchronous.ImportOperation::_importDataAccess
0xf481  ldarg.0
0xf482  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ImportOperation::_contextUserId
0xf487  ldarg.0
0xf488  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ImportOperation::_contextUserBusinessUnitId
0xf48d  ldarg.2
0xf48e  ldloc.s  4
0xf490  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0xf495  ldc.i4.2
0xf496  ldloc.s  8
0xf498  ldarg.3
0xf499  ldc.i4.7
0xf49a  ldelem.ref
0xf49b  castclass [mscorlib]System.String
0xf4a0  ldloca.s 0x19
0xf4a2  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0xf4a8  ldloc.s  0x19
0xf4aa  ldsfld   string [mscorlib]System.String::Empty
0xf4af  callvirt instance void Microsoft.Crm.Asynchronous.ImportDataAccess::CreateImportLogRow(valuetype [mscorlib]System.Guid ownerId, valuetype [mscorlib]System.Guid businessUnitId, valuetype [mscorlib]System.Guid importFileId, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> importDataId, int32 logPhaseCode, string headerColumn, string columnValue, valuetype [mscorlib]System.Nullable`1<int32> errorNumber, string additionalInfo)
0xf4b4  ldc.i4.0
0xf4b5  stloc.s  0x17
0xf4b7  leave    loc_FCF2
0xf4bc  ldloc.3
0xf4bd  ldloc.0
0xf4be  callvirt instance string Microsoft.Crm.Asynchronous.ImportFileHelperData::get_PrimaryKeyName()
0xf4c3  ldloc.s  5
0xf4c5  box      [mscorlib]System.Guid
0xf4ca  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0xf4cf  ldloc.s  6
0xf4d1  brtrue.s loc_F4EE
0xf4d3  ldloc.3
0xf4d4  ldstr    aImportsequence// "importsequencenumber"
0xf4d9  ldarg.0
0xf4da  ldfld    class Microsoft.Crm.Asynchronous.ImportHelperData Microsoft.Crm.Asynchronous.ImportOperation::_importDataStructure
0xf4df  callvirt instance int32 Microsoft.Crm.Asynchronous.ImportHelperData::get_Sequence()
0xf4e4  box      [mscorlib]System.Int32
0xf4e9  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0xf4ee  ldarg.s  5
0xf4f0  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::GetEnumerator()
  ... truncated ...
```
