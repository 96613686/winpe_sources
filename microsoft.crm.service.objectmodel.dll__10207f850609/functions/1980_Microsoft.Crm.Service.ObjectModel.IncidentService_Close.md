# Microsoft.Crm.Service.ObjectModel.IncidentService::Close

- ea: `0x1980`
- end: `0x1b29`
- name: `Microsoft.Crm.Service.ObjectModel.IncidentService::Close`
- size: `425`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1da0`

## callees

- `0x1980`
- `0x1e90`
- `0x2360`
- `0x2bc0`
- `0x2c00`

## pseudocode

```c

```

## disassembly

```asm
0x1980  ldarg.3
0x1981  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1986  ldstr    aIncident// "Incident"
0x198b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string)
0x1990  stloc.0
0x1991  ldarg.1
0x1992  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PrimaryKey()
0x1997  brtrue.s loc_19A0
0x1999  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x199e  br.s     loc_19AB
0x19a0  ldarg.1
0x19a1  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PrimaryKey()
0x19a6  unbox.any [mscorlib]System.Guid
0x19ab  stloc.1
0x19ac  ldloc.0
0x19ad  ldc.i4.1
0x19ae  ldarg.2
0x19af  ldloc.1
0x19b0  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.StatusCodeValidator::Validate(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, int32, int32, valuetype [mscorlib]System.Guid)
0x19b5  ldarg.3
0x19b6  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SoapContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SoapPacket()
0x19bb  ldarg.1
0x19bc  ldarg.1
0x19bd  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Metadata()
0x19c2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryKey()
0x19c7  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_PlatformName()
0x19cc  ldarg.3
0x19cd  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SoapContext::InitializeGuidFromOfflineData(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x19d2  ldarg.1
0x19d3  ldstr    aActualend// "actualend"
0x19d8  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x19dd  brtrue.s loc_19EF
0x19df  ldarg.1
0x19e0  ldstr    aActualend// "actualend"
0x19e5  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::get_UniversalNow()
0x19ea  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x19ef  ldarg.1
0x19f0  ldstr    aIncidentid// "incidentid"
0x19f5  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x19fa  brfalse.s loc_1A0D
0x19fc  ldc.i4   0x80044409
0x1a01  ldc.i4.0
0x1a02  newarr   [mscorlib]System.Object
0x1a07  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x1a0c  throw
0x1a0d  ldarg.1
0x1a0e  ldstr    aIncidentid// "incidentid"
0x1a13  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1a18  unbox.any [mscorlib]System.Guid
0x1a1d  ldloc.0
0x1a1e  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x1a23  ldarg.3
0x1a24  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1a29  stloc.2
0x1a2a  ldc.i4.3
0x1a2b  newarr   [mscorlib]System.String
0x1a30  dup
0x1a31  ldc.i4.0
0x1a32  ldstr    aStatecode// "statecode"
0x1a37  stelem.ref
0x1a38  dup
0x1a39  ldc.i4.1
0x1a3a  ldstr    aContractid// "contractid"
0x1a3f  stelem.ref
0x1a40  dup
0x1a41  ldc.i4.2
0x1a42  ldstr    aContractdetail// "contractdetailid"
0x1a47  stelem.ref
0x1a48  stloc.3
0x1a49  ldarg.3
0x1a4a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x1a4f  newobj   instance void [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.Incident::.ctor(valuetype [mscorlib]System.Guid)
0x1a54  stloc.s  4
0x1a56  ldloc.s  4
0x1a58  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Metadata()
0x1a5d  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x1a62  ldarg.3
0x1a63  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x1a68  stloc.s  5
0x1a6a  ldloc.s  5
0x1a6c  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x1a71  ldloc.3
0x1a72  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x1a77  ldarg.3
0x1a78  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SystemUserContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1a7d  stloc.s  6
0x1a7f  ldarg.0
0x1a80  ldloc.2
0x1a81  ldloc.s  5
0x1a83  ldarg.3
0x1a84  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Retrieve(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1a89  castclass [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.Incident
0x1a8e  stloc.s  4
0x1a90  ldarg.0
0x1a91  ldloc.s  4
0x1a93  ldarg.3
0x1a94  ldc.i4.1
0x1a95  call     instance void Microsoft.Crm.Service.ObjectModel.IncidentService::ChangeActivitiesStatus(class [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.Incident incident, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, int32 newState)
0x1a9a  leave.s  loc_1AA8
0x1a9c  ldloc.s  6
0x1a9e  brfalse.s loc_1AA7
0x1aa0  ldloc.s  6
0x1aa2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1aa7  endfinally
0x1aa8  nop
0x1aa9  ldloc.s  4
0x1aab  ldstr    aContractid// "contractid"
0x1ab0  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x1ab5  brfalse.s loc_1AC4
0x1ab7  ldarg.0
0x1ab8  ldloc.s  4
0x1aba  ldarg.1
0x1abb  ldarg.2
0x1abc  ldarg.3
0x1abd  call     instance void Microsoft.Crm.Service.ObjectModel.IncidentService::CloseIncidentWithNoContract(class [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.Incident originalIncident, class [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.IncidentResolution incidentResolution, int32 status, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1ac2  br.s     loc_1ACF
0x1ac4  ldarg.0
0x1ac5  ldloc.s  4
0x1ac7  ldarg.1
0x1ac8  ldarg.2
0x1ac9  ldarg.3
0x1aca  call     instance void Microsoft.Crm.Service.ObjectModel.IncidentService::CloseIncidentWithContract(class [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.Incident originalIncident, class [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.IncidentResolution incidentResolution, int32 status, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1acf  ldarg.0
0x1ad0  ldloc.2
0x1ad1  ldarg.1
0x1ad2  ldc.i4.1
0x1ad3  ldarg.2
0x1ad4  ldarg.3
0x1ad5  call     instance void Microsoft.Crm.Service.ObjectModel.IncidentService::PerformCascadeUpdate(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker moniker, class [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.IncidentResolution incidentResolution, int32 newState, int32 newStatusCode, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1ada  leave.s  loc_1B28
0x1adc  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_ErrorCode()
0x1ae1  ldc.i4   0x8004F00E
0x1ae6  bne.un.s loc_1B26
0x1ae8  ldarg.3
0x1ae9  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SoapContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SoapPacket()
0x1aee  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SoapContext::get_Request()
0x1af3  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_RequestName()
0x1af8  ldstr    aMerge// "Merge"
0x1afd  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1b02  brfalse.s loc_1B15
0x1b04  ldc.i4   0x8004F457
0x1b09  ldc.i4.0
0x1b0a  newarr   [mscorlib]System.Object
0x1b0f  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x1b14  throw
0x1b15  ldc.i4   0x8006074
0x1b1a  ldc.i4.0
0x1b1b  newarr   [mscorlib]System.Object
0x1b20  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x1b25  throw
0x1b26  rethrow
0x1b28  ret
```
