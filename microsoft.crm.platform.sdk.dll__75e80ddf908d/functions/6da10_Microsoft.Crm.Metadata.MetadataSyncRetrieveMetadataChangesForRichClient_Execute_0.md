# Microsoft.Crm.Metadata.MetadataSyncRetrieveMetadataChangesForRichClient::Execute_0

- ea: `0x6da10`
- end: `0x6db42`
- name: `Microsoft.Crm.Metadata.MetadataSyncRetrieveMetadataChangesForRichClient::Execute_0`
- size: `306`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x6d9f0`

## callees

- `0x52340`
- `0x6d900`
- `0x6d920`
- `0x6d940`
- `0x6d960`
- `0x6d980`
- `0x6d9a0`
- `0x6d9c0`
- `0x6d9d0`
- `0x6da10`
- `0x6e4a0`
- `0x6e6d0`

## string_xrefs

- `0x6daf4`: `AddedOrUpdatedLocalizedLabelMetadata`
- `0x6db05`: `AddedOrUpdatedOtherMetadata`
- `0x6db16`: `DeletedMetadata`

## pseudocode

```c

```

## disassembly

```asm
0x6da10  ldarg.s  4
0x6da12  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy Microsoft.Crm.Metadata.Helpers::CreateOrganizationService(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x6da17  stloc.s  4
0x6da19  ldstr    aRetrievemetada_1// "RetrieveMetadataChangesForRichClient"
0x6da1e  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::.ctor(string)
0x6da23  stloc.s  5
0x6da25  ldloc.s  5
0x6da27  ldstr    aLasttimestamp// "LastTimestamp"
0x6da2c  ldarg.0
0x6da2d  box      [mscorlib]System.Int64
0x6da32  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::set_Item(string, object)
0x6da37  ldloc.s  5
0x6da39  ldstr    aLastsynctime// "LastSyncTime"
0x6da3e  ldarg.1
0x6da3f  box      [mscorlib]System.DateTime
0x6da44  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::set_Item(string, object)
0x6da49  ldloc.s  5
0x6da4b  ldstr    aLastuserlangua// "LastUserLanguage"
0x6da50  ldarg.2
0x6da51  box      [mscorlib]System.Int32
0x6da56  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::set_Item(string, object)
0x6da5b  ldloc.s  5
0x6da5d  ldstr    aMetadataversio// "MetadataVersion"
0x6da62  ldarg.3
0x6da63  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::set_Item(string, object)
0x6da68  ldloc.s  4
0x6da6a  ldloc.s  5
0x6da6c  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x6da71  stloc.0
0x6da72  leave.s  loc_6DA80
0x6da74  ldloc.s  4
0x6da76  brfalse.s loc_6DA7F
0x6da78  ldloc.s  4
0x6da7a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6da7f  endfinally
0x6da80  newobj   instance void Microsoft.Crm.Metadata.MetadataSyncRetrieveMetadataChangesForRichClientResponse::.ctor()
0x6da85  dup
0x6da86  ldloc.0
0x6da87  ldstr    aSynctype// "SyncType"
0x6da8c  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Item(string)
0x6da91  unbox.any [mscorlib]System.Byte
0x6da96  callvirt instance void Microsoft.Crm.Metadata.MetadataSyncRetrieveMetadataChangesForRichClientResponse::set_SyncType(unsigned int8 value)
0x6da9b  dup
0x6da9c  ldloc.0
0x6da9d  ldstr    aNewtimestamp// "NewTimestamp"
0x6daa2  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Item(string)
0x6daa7  unbox.any [mscorlib]System.Int64
0x6daac  callvirt instance void Microsoft.Crm.Metadata.MetadataSyncRetrieveMetadataChangesForRichClientResponse::set_NewTimestamp(int64 value)
0x6dab1  dup
0x6dab2  ldloc.0
0x6dab3  ldstr    aNewsynctime// "NewSyncTime"
0x6dab8  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Item(string)
0x6dabd  unbox.any [mscorlib]System.DateTime
0x6dac2  callvirt instance void Microsoft.Crm.Metadata.MetadataSyncRetrieveMetadataChangesForRichClientResponse::set_NewSyncTime(valuetype [mscorlib]System.DateTime value)
0x6dac7  dup
0x6dac8  ldloc.0
0x6dac9  ldstr    aNewuserlanguag// "NewUserLanguage"
0x6dace  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Item(string)
0x6dad3  unbox.any [mscorlib]System.Int32
0x6dad8  callvirt instance void Microsoft.Crm.Metadata.MetadataSyncRetrieveMetadataChangesForRichClientResponse::set_NewUserLanguage(int32 value)
0x6dadd  dup
0x6dade  ldloc.0
0x6dadf  ldstr    aNewcalculatedt// "NewCalculatedTimestamp"
0x6dae4  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Item(string)
0x6dae9  castclass [mscorlib]System.String
0x6daee  callvirt instance void Microsoft.Crm.Metadata.MetadataSyncRetrieveMetadataChangesForRichClientResponse::set_NewCalculatedTimestamp(string value)
0x6daf3  ldloc.0
0x6daf4  ldstr    aAddedorupdated// "AddedOrUpdatedLocalizedLabelMetadata"
0x6daf9  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Item(string)
0x6dafe  castclass unsigned int8[]
0x6db03  stloc.1
0x6db04  ldloc.0
0x6db05  ldstr    aAddedorupdated_0// "AddedOrUpdatedOtherMetadata"
0x6db0a  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Item(string)
0x6db0f  castclass unsigned int8[]
0x6db14  stloc.2
0x6db15  ldloc.0
0x6db16  ldstr    aDeletedmetadat// "DeletedMetadata"
0x6db1b  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Item(string)
0x6db20  castclass unsigned int8[]
0x6db25  stloc.3
0x6db26  dup
0x6db27  ldloc.1
0x6db28  ldloc.2
0x6db29  ldarg.s  4
0x6db2b  call     class [mscorlib]System.Collections.Generic.IDictionary`2<valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode, class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.Metadata.IMetadataDescriptionPropertyBag>> Microsoft.Crm.Metadata.R8AddedOrUpdatedMetadataSerializer::DeserializeFromBytes(unsigned int8[] addedOrUpdatedLocalizedLabelMetadata, unsigned int8[] addedOrUpdatedOtherMetadata, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x6db30  callvirt instance void Microsoft.Crm.Metadata.MetadataSyncRetrieveMetadataChangesForRichClientResponse::set_AddedOrUpdatedMetadata(class [mscorlib]System.Collections.Generic.IDictionary`2<valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode, class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.Metadata.IMetadataDescriptionPropertyBag>> value)
0x6db35  dup
0x6db36  ldloc.3
0x6db37  call     class [mscorlib]System.Collections.Generic.IDictionary`2<valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode, class [mscorlib]System.Collections.Generic.ICollection`1<valuetype [mscorlib]System.Guid>> Microsoft.Crm.Metadata.R8DeletedMetadataSerializer::DeserializeFromBytes(unsigned int8[] deletedMetadata)
0x6db3c  callvirt instance void Microsoft.Crm.Metadata.MetadataSyncRetrieveMetadataChangesForRichClientResponse::set_DeletedMetadata(class [mscorlib]System.Collections.Generic.IDictionary`2<valuetype Microsoft.Crm.Metadata.MetadataObjectTypeCode, class [mscorlib]System.Collections.Generic.ICollection`1<valuetype [mscorlib]System.Guid>> value)
0x6db41  ret
```
