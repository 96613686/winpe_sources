# Microsoft.Crm.Sdk.Metadata.SdkMetadataChangeTrackingHelper::MarkAsChanged

- ea: `0x10080`
- end: `0x1011b`
- name: `Microsoft.Crm.Sdk.Metadata.SdkMetadataChangeTrackingHelper::MarkAsChanged`
- size: `155`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x413e0`
- `0x52490`
- `0x575a0`

## callees

- `0x10080`

## string_xrefs

- `0x1009b`: `UPDATE {0} SET {1} = {1} WHERE {1} = @metadataId AND OverwriteTime = 0 AND ComponentState = 0`
- `0x10103`: `D:\a\1\s\src\Core\ObjectModel\Metadata\MetadataService\SDK\SdkMetadataChangeTrackingHelper.cs`

## pseudocode

```c

```

## disassembly

```asm
0x10080  ldarg.0
0x10081  ldstr    aMetadatamonike// "metadataMoniker"
0x10086  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1008b  ldarg.1
0x1008c  ldstr    aContext// "context"
0x10091  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x10096  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1009b  ldstr    aUpdate0Set11Wh// "UPDATE {0} SET {1} = {1} WHERE {1} = @m"...
0x100a0  ldc.i4.2
0x100a1  newarr   [mscorlib]System.Object
0x100a6  dup
0x100a7  ldc.i4.0
0x100a8  ldarg.0
0x100a9  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityMoniker::get_MetadataEntityMetadata()
0x100ae  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata::get_TableName()
0x100b3  stelem.ref
0x100b4  dup
0x100b5  ldc.i4.1
0x100b6  ldarg.0
0x100b7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityMoniker::get_MetadataEntityMetadata()
0x100bc  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata::get_PrimaryIdAttribute()
0x100c1  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeMetadata::get_PhysicalName()
0x100c6  stelem.ref
0x100c7  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x100cc  stloc.0
0x100cd  ldarg.1
0x100ce  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext::get_Connection()
0x100d3  ldloc.0
0x100d4  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand(string)
0x100d9  stloc.1
0x100da  ldloc.1
0x100db  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x100e0  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x100e5  ldstr    aMetadataid// "@metadataId"
0x100ea  ldarg.0
0x100eb  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityMoniker::get_Id()
0x100f0  box      [mscorlib]System.Guid
0x100f5  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x100fa  pop
0x100fb  ldloc.1
0x100fc  ldc.i4.s 0x19
0x100fe  ldstr    aMarkaschanged// "MarkAsChanged"
0x10103  ldstr    aDA1SSrcCoreObj_1// "D:\\a\\1\\s\\src\\Core\\ObjectModel\\Me"...
0x10108  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x1010d  pop
0x1010e  leave.s  loc_1011A
0x10110  ldloc.1
0x10111  brfalse.s loc_10119
0x10113  ldloc.1
0x10114  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x10119  endfinally
0x1011a  ret
```
