# Microsoft.Crm.Common.Application.Platform.ServiceCommands.QualifyLeadCommand::.ctor_0

- ea: `0x5e60`
- end: `0x6026`
- name: `Microsoft.Crm.Common.Application.Platform.ServiceCommands.QualifyLeadCommand::.ctor_0`
- size: `454`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x2560`

## callees

- `0x5e60`
- `0x6030`

## string_xrefs

- `0x5e94`: `companyname`
- `0x5f89`: `companyname`
- `0x5fca`: `companyname`
- `0x6008`: `Opportunity Parent Id and Opportunity Parent Type should be present when create account/contact are false`

## pseudocode

```c

```

## disassembly

```asm
0x5e60  ldarg.0
0x5e61  ldstr    aLead// "lead"
0x5e66  ldarg.s  4
0x5e68  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5e6d  ldarg.s  4
0x5e6f  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.PlatformCommand::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5e74  ldc.i4.5
0x5e75  newarr   [mscorlib]System.String
0x5e7a  dup
0x5e7b  ldc.i4.0
0x5e7c  ldstr    aStatecode// "statecode"
0x5e81  stelem.ref
0x5e82  dup
0x5e83  ldc.i4.1
0x5e84  ldstr    aParentaccounti// "parentaccountid"
0x5e89  stelem.ref
0x5e8a  dup
0x5e8b  ldc.i4.2
0x5e8c  ldstr    aParentcontacti// "parentcontactid"
0x5e91  stelem.ref
0x5e92  dup
0x5e93  ldc.i4.3
0x5e94  ldstr    aCompanyname// "companyname"
0x5e99  stelem.ref
0x5e9a  dup
0x5e9b  ldc.i4.4
0x5e9c  ldstr    aTransactioncur// "transactioncurrencyid"
0x5ea1  stelem.ref
0x5ea2  stloc.0
0x5ea3  ldstr    aLead// "lead"
0x5ea8  ldarg.1
0x5ea9  ldloc.0
0x5eaa  ldarg.s  4
0x5eac  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Retrieve(string, valuetype [mscorlib]System.Guid, string[], class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5eb1  stloc.1
0x5eb2  ldtoken  [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.LeadState
0x5eb7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x5ebc  ldloc.1
0x5ebd  ldstr    aStatecode// "statecode"
0x5ec2  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x5ec7  castclass [mscorlib]System.String
0x5ecc  ldc.i4.1
0x5ecd  call     object [mscorlib]System.Enum::Parse(class [mscorlib]System.Type, string, bool)
0x5ed2  unbox.any [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.LeadState
0x5ed7  brfalse.s loc_5EEA
0x5ed9  ldc.i4   0x80040519
0x5ede  ldc.i4.0
0x5edf  newarr   [mscorlib]System.Object
0x5ee4  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x5ee9  throw
0x5eea  ldc.i4.0
0x5eeb  stloc.2
0x5eec  ldc.i4.0
0x5eed  stloc.3
0x5eee  ldsfld   string [mscorlib]System.String::Empty
0x5ef3  stloc.s  4
0x5ef5  ldsfld   string [mscorlib]System.String::Empty
0x5efa  stloc.s  5
0x5efc  ldc.i4.m1
0x5efd  stloc.s  6
0x5eff  ldloc.1
0x5f00  ldstr    aTransactioncur// "transactioncurrencyid"
0x5f05  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::HasAttribute(string)
0x5f0a  brfalse.s loc_5F25
0x5f0c  ldloc.1
0x5f0d  ldstr    aTransactioncur// "transactioncurrencyid"
0x5f12  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x5f17  isinst   [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue
0x5f1c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::get_ID()
0x5f21  stloc.s  4
0x5f23  br.s     loc_5F36
0x5f25  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x5f2a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::ObtainDefaultCurrency(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5f2f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::get_ID()
0x5f34  stloc.s  4
0x5f36  ldloc.1
0x5f37  ldstr    aParentaccounti// "parentaccountid"
0x5f3c  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::HasAttribute(string)
0x5f41  brfalse.s loc_5F5F
0x5f43  ldloc.1
0x5f44  ldstr    aParentaccounti// "parentaccountid"
0x5f49  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x5f4e  isinst   [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue
0x5f53  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::get_ID()
0x5f58  stloc.s  5
0x5f5a  ldc.i4.1
0x5f5b  stloc.s  6
0x5f5d  br.s     loc_5F9D
0x5f5f  ldloc.1
0x5f60  ldstr    aParentcontacti// "parentcontactid"
0x5f65  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::HasAttribute(string)
0x5f6a  brfalse.s loc_5F88
0x5f6c  ldloc.1
0x5f6d  ldstr    aParentcontacti// "parentcontactid"
0x5f72  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x5f77  isinst   [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue
0x5f7c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::get_ID()
0x5f81  stloc.s  5
0x5f83  ldc.i4.2
0x5f84  stloc.s  6
0x5f86  br.s     loc_5F9D
0x5f88  ldloc.1
0x5f89  ldstr    aCompanyname// "companyname"
0x5f8e  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::HasAttribute(string)
0x5f93  brfalse.s loc_5F9B
0x5f95  ldc.i4.1
0x5f96  stloc.3
0x5f97  ldc.i4.1
0x5f98  stloc.2
0x5f99  br.s     loc_5F9D
0x5f9b  ldc.i4.1
0x5f9c  stloc.3
0x5f9d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x5fa2  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5fa7  ldc.i4.4
0x5fa8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0x5fad  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserDataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserDataCache::Instance()
0x5fb2  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x5fb7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_UserId()
0x5fbc  ldarg.s  4
0x5fbe  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser>::LookupEntry(void, var<u1>)
0x5fc3  stloc.s  7
0x5fc5  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AttributesByName()
0x5fca  ldstr    aCompanyname// "companyname"
0x5fcf  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataHashtable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata>::get_Item(!!T0)
0x5fd4  stloc.s  8
0x5fd6  ldloc.s  8
0x5fd8  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_IsSecured()
0x5fdd  brfalse.s loc_5FF1
0x5fdf  ldloc.s  7
0x5fe1  ldloc.s  8
0x5fe3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Id()
0x5fe8  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::HasAttributeReadPrivilege(valuetype [mscorlib]System.Guid)
0x5fed  brtrue.s loc_5FF1
0x5fef  ldc.i4.1
0x5ff0  stloc.2
0x5ff1  ldloc.2
0x5ff2  brtrue.s loc_6012
0x5ff4  ldloc.3
0x5ff5  brtrue.s loc_6012
0x5ff7  ldloc.s  5
0x5ff9  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5ffe  brtrue.s loc_6007
0x6000  ldloc.s  6
0x6002  ldc.i4.0
0x6003  cgt
0x6005  br.s     loc_6008
0x6007  ldc.i4.0
0x6008  ldstr    aOpportunityPar// "Opportunity Parent Id and Opportunity P"...
0x600d  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x6012  ldarg.0
0x6013  ldarg.1
0x6014  ldarg.3
0x6015  ldc.i4.1
0x6016  ldloc.2
0x6017  ldloc.3
0x6018  ldloc.s  5
0x601a  ldloc.s  6
0x601c  ldloc.s  4
0x601e  ldarg.2
0x601f  ldc.i4.1
0x6020  call     instance void Microsoft.Crm.Common.Application.Platform.ServiceCommands.QualifyLeadCommand::InitializeRequest(valuetype [mscorlib]System.Guid entityId, int32 newStatus, bool createOpportunity, bool createAccount, bool createContact, string opportunityParentId, int32 opportunityParentType, string opportunityCurrencyId, string campaignId, bool suppressDuplicateDetection)
0x6025  ret
```
