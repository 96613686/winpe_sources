# Microsoft.Crm.WebServices.MetadataWebService::GetAppMetadataForEntity

- ea: `0xf2e0`
- end: `0xf448`
- name: `Microsoft.Crm.WebServices.MetadataWebService::GetAppMetadataForEntity`
- size: `360`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0xf230`
- `0xf250`
- `0xf270`
- `0xf280`
- `0xf2e0`

## string_xrefs

- `0xf322`: `Select FieldXml from OrganizationUI where ObjectTypeCode = @ObjectTypeCode and InProduction = 1`
- `0xf358`: `D:\a\1\s\src\Core\ObjectModel\WebServices\MetadataCache\Metadata.asmx.cs`
- `0xf399`: `FieldXml`

## pseudocode

```c

```

## disassembly

```asm
0xf2e0  ldarg.1
0xf2e1  ldc.i4.0
0xf2e2  bgt.s    loc_F30D
0xf2e4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf2e9  ldstr    aInvalidObjectT// "Invalid Object Type Code: {0} specified"
0xf2ee  ldc.i4.1
0xf2ef  newarr   [mscorlib]System.Object
0xf2f4  dup
0xf2f5  ldc.i4.0
0xf2f6  ldarg.1
0xf2f7  box      [mscorlib]System.Int32
0xf2fc  stelem.ref
0xf2fd  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xf302  ldc.i4   0x80040203
0xf307  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0xf30c  throw
0xf30d  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::GetOrganizationGuid()
0xf312  stloc.0
0xf313  ldloc.0
0xf314  ldc.i4.0
0xf315  ldc.i4.0
0xf316  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0xf31b  stloc.1
0xf31c  ldloc.1
0xf31d  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0xf322  ldstr    aSelectFieldxml// "Select FieldXml from OrganizationUI whe"...
0xf327  stloc.2
0xf328  ldloc.1
0xf329  ldloc.2
0xf32a  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand(string)
0xf32f  dup
0xf330  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0xf335  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0xf33a  ldstr    aObjecttypecode// "@ObjectTypeCode"
0xf33f  ldarg.1
0xf340  box      [mscorlib]System.Int32
0xf345  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xf34a  pop
0xf34b  newobj   instance void Microsoft.Crm.WebServices.AppMetadata::.ctor()
0xf350  stloc.3
0xf351  ldc.i4.s 0x78
0xf353  ldstr    aGetappmetadata// "GetAppMetadataForEntity"
0xf358  ldstr    aDA1SSrcCoreObj// "D:\\a\\1\\s\\src\\Core\\ObjectModel\\We"...
0xf35d  call     class [System.Data]System.Data.IDataReader [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteReader(class [System.Data]System.Data.IDbCommand, int32, string, string)
0xf362  stloc.s  7
0xf364  ldloc.s  7
0xf366  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0xf36b  brtrue.s loc_F396
0xf36d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf372  ldstr    aNoAppMetadataE// "No App Metadata Exists for Entity with "...
0xf377  ldc.i4.1
0xf378  newarr   [mscorlib]System.Object
0xf37d  dup
0xf37e  ldc.i4.0
0xf37f  ldarg.1
0xf380  box      [mscorlib]System.Int32
0xf385  stelem.ref
0xf386  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xf38b  ldc.i4   0x80040203
0xf390  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0xf395  throw
0xf396  ldloc.3
0xf397  ldloc.s  7
0xf399  ldstr    aFieldxml// "FieldXml"
0xf39e  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0xf3a3  castclass [mscorlib]System.String
0xf3a8  callvirt instance void Microsoft.Crm.WebServices.AppMetadata::set_FieldXml(string value)
0xf3ad  leave.s  loc_F3BB
0xf3af  ldloc.s  7
0xf3b1  brfalse.s loc_F3BA
0xf3b3  ldloc.s  7
0xf3b5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xf3ba  endfinally
0xf3bb  ldloc.0
0xf3bc  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0xf3c1  stloc.s  4
0xf3c3  ldloc.s  4
0xf3c5  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xf3ca  dup
0xf3cb  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::get_LanguageCode()
0xf3d0  stloc.s  5
0xf3d2  dup
0xf3d3  ldarg.1
0xf3d4  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0xf3d9  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LocalizedName()
0xf3de  ldloc.s  5
0xf3e0  ldloc.s  4
0xf3e2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::GetLabel(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xf3e7  stloc.s  6
0xf3e9  ldloc.3
0xf3ea  ldloc.s  6
0xf3ec  brfalse.s loc_F3F7
0xf3ee  ldloc.s  6
0xf3f0  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::get_Description()
0xf3f5  br.s     loc_F3FC
0xf3f7  ldsfld   string [mscorlib]System.String::Empty
0xf3fc  callvirt instance void Microsoft.Crm.WebServices.AppMetadata::set_LocalizedName(string value)
0xf401  ldarg.1
0xf402  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0xf407  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LocalizedCollectionName()
0xf40c  ldloc.s  5
0xf40e  ldloc.s  4
0xf410  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::GetLabel(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xf415  stloc.s  6
0xf417  ldloc.3
0xf418  ldloc.s  6
0xf41a  brfalse.s loc_F425
0xf41c  ldloc.s  6
0xf41e  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::get_Description()
0xf423  br.s     loc_F42A
0xf425  ldsfld   string [mscorlib]System.String::Empty
0xf42a  callvirt instance void Microsoft.Crm.WebServices.AppMetadata::set_LocalizedCollectionName(string value)
0xf42f  ldloc.3
0xf430  stloc.s  8
0xf432  leave.s  loc_F445
0xf434  ldloc.1
0xf435  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Close()
0xf43a  endfinally
0xf43b  ldloc.1
0xf43c  brfalse.s loc_F444
0xf43e  ldloc.1
0xf43f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xf444  endfinally
0xf445  ldloc.s  8
0xf447  ret
```
