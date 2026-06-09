# Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::RetrieveFetchXmlForEntity

- ea: `0x1ed10`
- end: `0x1ee69`
- name: `Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::RetrieveFetchXmlForEntity`
- size: `345`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1d750`
- `0x1e010`

## callees

- `0xfde0`
- `0xfdf0`
- `0x1ed10`
- `0x247a0`
- `0x24c80`
- `0x24e10`

## string_xrefs

- `0x1ed39`: `fetchXml`
- `0x1ed20`: `odata.include-annotations=Microsoft.Dynamics.CRM.fetchxmlpagingcookie`
- `0x1edb4`: `fetchxml`
- `0x1ee42`: `fetchxml`
- `0x1ee54`: `Fetchxml of the Query View can not be null.`

## pseudocode

```c

```

## disassembly

```asm
0x1ed10  ldarg.1
0x1ed11  callvirt instance class [System.Net.Http]System.Net.Http.HttpRequestMessage Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_Request()
0x1ed16  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpRequestHeaders [System.Net.Http]System.Net.Http.HttpRequestMessage::get_Headers()
0x1ed1b  ldstr    aPrefer// "Prefer"
0x1ed20  ldstr    aOdataIncludeAn_0// "odata.include-annotations=Microsoft.Dyn"...
0x1ed25  callvirt instance void [System.Net.Http]System.Net.Http.Headers.HttpHeaders::Add(string, string)
0x1ed2a  ldarg.3
0x1ed2b  callvirt instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string> Microsoft.Crm.Extensibility.OData.CustomQueryOptions::get_CustomQueryParameter()
0x1ed30  stloc.s  6
0x1ed32  ldloca.s 6
0x1ed34  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Key()
0x1ed39  ldstr    aFetchxml// "fetchXml"
0x1ed3e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1ed43  brfalse.s loc_1ED8B
0x1ed45  ldarg.3
0x1ed46  callvirt instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string> Microsoft.Crm.Extensibility.OData.CustomQueryOptions::get_CustomQueryParameter()
0x1ed4b  stloc.s  6
0x1ed4d  ldloca.s 6
0x1ed4f  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Value()
0x1ed54  stloc.s  7
0x1ed56  ldloc.s  7
0x1ed58  call     class [System.Xml]System.Xml.XmlReader [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlReader(string)
0x1ed5d  stloc.s  8
0x1ed5f  ldloc.s  8
0x1ed61  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0x1ed66  pop
0x1ed67  ldloc.s  7
0x1ed69  stloc.s  9
0x1ed6b  leave    loc_1EE66
0x1ed70  ldloc.s  8
0x1ed72  brfalse.s loc_1ED7B
0x1ed74  ldloc.s  8
0x1ed76  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1ed7b  endfinally
0x1ed7c  pop
0x1ed7d  ldloc.s  7
0x1ed7f  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmUrlDecode(string)
0x1ed84  stloc.s  9
0x1ed86  leave    loc_1EE66
0x1ed8b  ldarg.3
0x1ed8c  callvirt instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string> Microsoft.Crm.Extensibility.OData.CustomQueryOptions::get_CustomQueryParameter()
0x1ed91  stloc.s  6
0x1ed93  ldloca.s 6
0x1ed95  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Key()
0x1ed9a  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Extensibility.OData.EdmUtilities::GetXrmEntityMetadataFromEntityName(string crmEntityPlatformName)
0x1ed9f  stloc.0
0x1eda0  ldarg.2
0x1eda1  ldarg.0
0x1eda2  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::edmModel
0x1eda7  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Extensibility.OData.EdmUtilities::GetXrmEntityMetadataFromEdmEntitySetName(string entitySetName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x1edac  stloc.1
0x1edad  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::.ctor()
0x1edb2  stloc.2
0x1edb3  ldloc.2
0x1edb4  ldstr    aFetchxml_0// "fetchxml"
0x1edb9  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::AddColumn(string)
0x1edbe  ldloc.2
0x1edbf  ldstr    aReturnedtypeco// "returnedtypecode"
0x1edc4  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::AddColumn(string)
0x1edc9  ldarg.1
0x1edca  ldloc.0
0x1edcb  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityDescription [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_EntityInfo()
0x1edd0  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityDescription::get_LogicalName()
0x1edd5  ldarg.3
0x1edd6  callvirt instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string> Microsoft.Crm.Extensibility.OData.CustomQueryOptions::get_CustomQueryParameter()
0x1eddb  stloc.s  6
0x1eddd  ldloca.s 6
0x1eddf  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Value()
0x1ede4  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1ede9  ldloc.2
0x1edea  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::Retrieve(string entityName, valuetype [mscorlib]System.Guid id, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet columnSet)
0x1edef  stloc.3
0x1edf0  ldnull
0x1edf1  stloc.s  4
0x1edf3  ldloc.3
0x1edf4  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x1edf9  ldstr    aReturnedtypeco// "returnedtypecode"
0x1edfe  ldloca.s 4
0x1ee00  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::TryGetValue(var<u1>, !!T0)
0x1ee05  pop
0x1ee06  ldloc.s  4
0x1ee08  brfalse.s loc_1EE23
0x1ee0a  ldloc.1
0x1ee0b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityDescription [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_EntityInfo()
0x1ee10  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityDescription::get_LogicalName()
0x1ee15  ldloc.s  4
0x1ee17  castclass [mscorlib]System.String
0x1ee1c  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x1ee21  brfalse.s loc_1EE39
0x1ee23  ldc.i4   0x190
0x1ee28  ldstr    aNoQueryViewExi// "No Query View exists with the Given Que"...
0x1ee2d  ldc.i4.0
0x1ee2e  newarr   [mscorlib]System.Object
0x1ee33  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmHttpException::.ctor(valuetype [System]System.Net.HttpStatusCode, string, object[])
0x1ee38  throw
0x1ee39  ldnull
0x1ee3a  stloc.s  5
0x1ee3c  ldloc.3
0x1ee3d  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x1ee42  ldstr    aFetchxml_0// "fetchxml"
0x1ee47  ldloca.s 5
0x1ee49  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::TryGetValue(var<u1>, !!T0)
0x1ee4e  pop
0x1ee4f  ldloc.s  5
0x1ee51  ldnull
0x1ee52  cgt.un
0x1ee54  ldstr    aFetchxmlOfTheQ// "Fetchxml of the Query View can not be n"...
0x1ee59  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x1ee5e  ldloc.s  5
0x1ee60  castclass [mscorlib]System.String
0x1ee65  ret
0x1ee66  ldloc.s  9
0x1ee68  ret
```
