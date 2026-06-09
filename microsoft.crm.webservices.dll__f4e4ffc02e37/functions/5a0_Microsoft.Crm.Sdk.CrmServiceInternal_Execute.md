# Microsoft.Crm.Sdk.CrmServiceInternal::Execute

- ea: `0x5a0`
- end: `0x671`
- name: `Microsoft.Crm.Sdk.CrmServiceInternal::Execute`
- size: `209`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x2e20`
- `0xaa70`

## callees

- `0x5a0`
- `0xa40`
- `0xaa0`
- `0xb40`
- `0xb70`
- `0x45f0`
- `0x4610`
- `0x46f0`
- `0x4710`
- `0x49c0`
- `0x4a40`
- `0x4a80`
- `0x6350`

## pseudocode

```c

```

## disassembly

```asm
0x5a0  ldarg.0
0x5a1  ldarg.1
0x5a2  callvirt instance class Microsoft.Crm.Sdk.IRequestBuilder Microsoft.Crm.Sdk.RequestBase::get_RequestBuilder()
0x5a7  call     instance void Microsoft.Crm.Sdk.CrmServiceInternal::ThrowIfMessageNotSupported(class Microsoft.Crm.Sdk.IRequestBuilder requestBuilder)
0x5ac  ldsfld   string [mscorlib]System.String::Empty
0x5b1  stloc.0
0x5b2  ldarg.1
0x5b3  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Sdk.RequestBase::get_PrimaryEntity()
0x5b8  brfalse.s loc_5C6
0x5ba  ldarg.1
0x5bb  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Sdk.RequestBase::get_PrimaryEntity()
0x5c0  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x5c5  stloc.0
0x5c6  ldarg.1
0x5c7  callvirt instance class Microsoft.Crm.Sdk.IRequestBuilder Microsoft.Crm.Sdk.RequestBase::get_RequestBuilder()
0x5cc  callvirt instance string Microsoft.Crm.Sdk.IRequestBuilder::get_RequestName()
0x5d1  ldloc.0
0x5d2  ldarg.1
0x5d3  callvirt instance class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.SdkMessageFilter Microsoft.Crm.Sdk.RequestBase::get_TargetFilter()
0x5d8  call     void Microsoft.Crm.Sdk.CrmServiceInternal::ThrowIfFilterNotSet(string methodName, string entityName, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.SdkMessageFilter filter)
0x5dd  ldarg.1
0x5de  callvirt instance class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.SdkMessageFilter Microsoft.Crm.Sdk.RequestBase::get_TargetFilter()
0x5e3  ldstr    aPrimaryobjectt// "primaryobjecttypecode"
0x5e8  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5ed  unbox.any [mscorlib]System.Int32
0x5f2  stloc.1
0x5f3  ldloc.1
0x5f4  ldc.i4.0
0x5f5  ble.s    loc_640
0x5f7  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::GetOrganizationGuid()
0x5fc  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x601  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x606  ldloc.1
0x607  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0x60c  stloc.3
0x60d  ldloc.3
0x60e  ldarg.1
0x60f  callvirt instance class Microsoft.Crm.Sdk.IRequestBuilder Microsoft.Crm.Sdk.RequestBase::get_RequestBuilder()
0x614  callvirt instance string Microsoft.Crm.Sdk.IRequestBuilder::get_MessageName()
0x619  ldloc.3
0x61a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityDescription [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_EntityInfo()
0x61f  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityDescription::get_LogicalName()
0x624  call     void Microsoft.Crm.Sdk.CrmServiceInternal::ThrowIfEntityNotFound(object entityDescriptor, string methodName, string entityName)
0x629  ldloc.3
0x62a  ldarg.1
0x62b  callvirt instance class Microsoft.Crm.Sdk.IRequestBuilder Microsoft.Crm.Sdk.RequestBase::get_RequestBuilder()
0x630  callvirt instance string Microsoft.Crm.Sdk.IRequestBuilder::get_MessageName()
0x635  ldarg.1
0x636  callvirt instance class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.SdkMessageFilter Microsoft.Crm.Sdk.RequestBase::get_TargetFilter()
0x63b  call     void Microsoft.Crm.Sdk.CrmServiceInternal::ThrowIfMethodNotSupported(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entityDescriptor, string methodName, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.SdkMessageFilter filter)
0x640  ldarg.1
0x641  ldarg.s  5
0x643  ldarg.s  4
0x645  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.UserAuth::get_OrganizationId()
0x64a  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection Microsoft.Crm.Sdk.RequestBase::ConvertToEntityBase(valuetype [mscorlib]System.Guid userId, valuetype [mscorlib]System.Guid organizationId)
0x64f  stloc.2
0x650  ldarg.1
0x651  ldarg.2
0x652  ldarg.3
0x653  ldarg.s  4
0x655  ldarg.s  5
0x657  ldloc.2
0x658  ldarg.0
0x659  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sdk.CrmServiceInternal::_transactionContextId
0x65e  callvirt instance class Microsoft.Crm.Sdk.ResponseBase Microsoft.Crm.Sdk.RequestBase::Process(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CorrelationToken correlationToken, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOriginToken originToken, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.UserAuth userAuth, valuetype [mscorlib]System.Guid callerId, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection parameters, valuetype [mscorlib]System.Guid transactionContextId)
0x663  dup
0x664  ldarg.s  4
0x666  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.UserAuth::get_OrganizationId()
0x66b  callvirt instance void Microsoft.Crm.Sdk.ResponseBase::ConvertToDynamicEntityBase(valuetype [mscorlib]System.Guid organizationId)
0x670  ret
```
