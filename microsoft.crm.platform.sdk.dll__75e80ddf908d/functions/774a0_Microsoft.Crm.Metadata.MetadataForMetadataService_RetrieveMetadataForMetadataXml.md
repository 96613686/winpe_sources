# Microsoft.Crm.Metadata.MetadataForMetadataService::RetrieveMetadataForMetadataXml

- ea: `0x774a0`
- end: `0x7751b`
- name: `Microsoft.Crm.Metadata.MetadataForMetadataService::RetrieveMetadataForMetadataXml`
- size: `123`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x709e0`

## callees

- `0x774a0`

## string_xrefs

- `0x774a8`: `SELECT MetadataForMetadataXml as [MetadataForMetadataXml] FROM dbo.MetadataForMetadata`
- `0x774b5`: `RetrieveMetadataForMetadataXml`
- `0x774ba`: `D:\a\1\s\src\ManagedPlatform\SDK\MetadataEntities\MetadataForMetadataService.cs`
- `0x774ce`: `MetadataForMetadataXml`

## pseudocode

```c

```

## disassembly

```asm
0x774a0  ldarg.1
0x774a1  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext::CreateSqlCommand()
0x774a6  stloc.1
0x774a7  ldloc.1
0x774a8  ldstr    aSelectMetadata_0// "SELECT MetadataForMetadataXml as [Metad"...
0x774ad  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x774b2  ldloc.1
0x774b3  ldc.i4.s 0x11
0x774b5  ldstr    aRetrievemetada_2// "RetrieveMetadataForMetadataXml"
0x774ba  ldstr    aDA1SSrcManaged_10// "D:\\a\\1\\s\\src\\ManagedPlatform\\SDK"...
0x774bf  call     class [System.Data]System.Data.IDataReader [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteReader(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x774c4  stloc.2
0x774c5  ldloc.2
0x774c6  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x774cb  brfalse.s loc_774EE
0x774cd  ldloc.2
0x774ce  ldstr    aMetadataformet_1// "MetadataForMetadataXml"
0x774d3  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x774d8  stloc.3
0x774d9  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x774de  ldloc.3
0x774df  bne.un.s loc_774E5
0x774e1  ldnull
0x774e2  stloc.0
0x774e3  br.s     loc_774F0
0x774e5  ldloc.3
0x774e6  castclass [mscorlib]System.String
0x774eb  stloc.0
0x774ec  br.s     loc_774F0
0x774ee  ldnull
0x774ef  stloc.0
0x774f0  ldloc.2
0x774f1  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x774f6  brfalse.s loc_77503
0x774f8  ldstr    aMetadataformet_2// "MetadataForMetadata table should not ha"...
0x774fd  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmInvalidOperationException::.ctor(string)
0x77502  throw
0x77503  leave.s  loc_77519
0x77505  ldloc.2
0x77506  brfalse.s loc_7750E
0x77508  ldloc.2
0x77509  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7750e  endfinally
0x7750f  ldloc.1
0x77510  brfalse.s loc_77518
0x77512  ldloc.1
0x77513  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x77518  endfinally
0x77519  ldloc.0
0x7751a  ret
```
