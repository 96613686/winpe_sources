# Microsoft.Crm.Common.Application.Commands.ApplicationCommand::ConvertActivity

- ea: `0x1cb0`
- end: `0x20aa`
- name: `Microsoft.Crm.Common.Application.Commands.ApplicationCommand::ConvertActivity`
- size: `1018`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1cb0`
- `0x20b0`

## pseudocode

```c

```

## disassembly

```asm
0x1cb0  ldarg.s  4
0x1cb2  brfalse.s loc_1CC5
0x1cb4  ldarg.s  4
0x1cb6  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1cbb  brfalse.s loc_1CC5
0x1cbd  ldarg.s  5
0x1cbf  brfalse.s loc_1CC5
0x1cc1  ldarg.s  6
0x1cc3  brtrue.s loc_1CCB
0x1cc5  ldsfld   string [mscorlib]System.String::Empty
0x1cca  ret
0x1ccb  ldsfld   string [mscorlib]System.String::Empty
0x1cd0  stloc.0
0x1cd1  ldarg.0
0x1cd2  brfalse.s loc_1CDC
0x1cd4  ldarg.0
0x1cd5  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1cda  brtrue.s loc_1CE4
0x1cdc  ldsfld   string [mscorlib]System.String::Empty
0x1ce1  stloc.0
0x1ce2  br.s     loc_1CE6
0x1ce4  ldarg.0
0x1ce5  stloc.0
0x1ce6  ldstr    aOpportunity// "opportunity"
0x1ceb  ldarg.s  0xC
0x1ced  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1cf2  stloc.1
0x1cf3  ldloc.1
0x1cf4  ldstr    aName// "name"
0x1cf9  ldloc.0
0x1cfa  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x1cff  ldarg.s  0xC
0x1d01  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1d06  ldarg.s  5
0x1d08  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0x1d0d  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x1d12  stloc.2
0x1d13  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::.ctor()
0x1d18  stloc.3
0x1d19  ldloc.3
0x1d1a  ldarg.s  4
0x1d1c  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::set_ID(string)
0x1d21  ldloc.3
0x1d22  ldloc.2
0x1d23  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::set_Type(int32)
0x1d28  ldloc.1
0x1d29  ldstr    aCustomerid// "customerid"
0x1d2e  ldloc.3
0x1d2f  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x1d34  ldloc.1
0x1d35  ldstr    aTransactioncur// "transactioncurrencyid"
0x1d3a  ldarg.s  6
0x1d3c  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1d41  box      [mscorlib]System.Guid
0x1d46  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x1d4b  ldarg.s  8
0x1d4d  ldc.i4   0x1130
0x1d52  bne.un   loc_1DE2
0x1d57  ldarg.s  7
0x1d59  brfalse  loc_1DE2
0x1d5e  ldarg.s  7
0x1d60  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1d65  ldc.i4.0
0x1d66  ble.s    loc_1DE2
0x1d68  ldloc.1
0x1d69  ldstr    aCampaignid// "campaignid"
0x1d6e  ldarg.s  7
0x1d70  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1d75  box      [mscorlib]System.Guid
0x1d7a  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x1d7f  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_ReadCampaign()
0x1d84  ldarg.s  0xC
0x1d86  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1d8b  brfalse.s loc_1DE2
0x1d8d  ldc.i4.1
0x1d8e  newarr   [mscorlib]System.String
0x1d93  dup
0x1d94  ldc.i4.0
0x1d95  ldstr    aPricelistid// "pricelistid"
0x1d9a  stelem.ref
0x1d9b  stloc.s  9
0x1d9d  ldstr    aCampaign// "campaign"
0x1da2  ldarg.s  7
0x1da4  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1da9  ldloc.s  9
0x1dab  ldarg.s  0xC
0x1dad  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Retrieve(string, valuetype [mscorlib]System.Guid, string[], class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1db2  stloc.s  0xA
0x1db4  ldloc.s  0xA
0x1db6  ldstr    aPricelistid// "pricelistid"
0x1dbb  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::HasAttribute(string)
0x1dc0  brfalse.s loc_1DE2
0x1dc2  ldloc.s  0xA
0x1dc4  ldstr    aPricelistid// "pricelistid"
0x1dc9  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x1dce  castclass [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue
0x1dd3  stloc.s  0xB
0x1dd5  ldloc.1
0x1dd6  ldstr    aPricelevelid// "pricelevelid"
0x1ddb  ldloc.s  0xB
0x1ddd  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x1de2  ldarg.3
0x1de3  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1de8  brtrue.s loc_1DF6
0x1dea  ldloc.1
0x1deb  ldstr    aOriginatinglea// "originatingleadid"
0x1df0  ldarg.3
0x1df1  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x1df6  ldloc.1
0x1df7  ldstr    aIsrevenuesyste// "isrevenuesystemcalculated"
0x1dfc  ldarg.s  0xC
0x1dfe  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1e03  ldc.i4.3
0x1e04  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0x1e09  ldstr    aIsrevenuesyste// "isrevenuesystemcalculated"
0x1e0e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string)
0x1e13  isinst   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.BooleanAttributeMetadata
0x1e18  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.BooleanAttributeMetadata::get_DefaultValue()
0x1e1d  box      [mscorlib]System.Boolean
0x1e22  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x1e27  ldloc.1
0x1e28  ldstr    aOpportunityrat// "opportunityratingcode"
0x1e2d  ldarg.s  0xC
0x1e2f  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1e34  ldc.i4.3
0x1e35  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0x1e3a  ldstr    aOpportunityrat// "opportunityratingcode"
0x1e3f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string)
0x1e44  isinst   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PicklistAttributeMetadata
0x1e49  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PicklistAttributeMetadata::get_DefaultValue()
0x1e4e  box      [mscorlib]System.Int32
0x1e53  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x1e58  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::.ctor()
0x1e5d  stloc.s  4
0x1e5f  ldloc.s  4
0x1e61  ldarg.s  0xB
0x1e63  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::set_Type(int32)
0x1e68  ldloc.s  4
0x1e6a  ldarg.s  0xA
0x1e6c  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::set_ID(string)
0x1e71  ldloc.1
0x1e72  ldstr    aOwnerid// "ownerid"
0x1e77  ldloc.s  4
0x1e79  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x1e7e  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.SequentialGuid::CreateGuid()
0x1e83  stloc.s  5
0x1e85  ldloc.1
0x1e86  ldloc.s  5
0x1e88  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::Create(valuetype [mscorlib]System.Guid)
0x1e8d  ldarg.s  9
0x1e8f  brfalse  loc_1FDD
0x1e94  ldstr    aCampaignrespon// "campaignresponse"
0x1e99  ldarg.s  0xC
0x1e9b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1ea0  ldstr    aActivityparty// "activityparty"
0x1ea5  ldarg.s  0xC
0x1ea7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1eac  stloc.s  0xC
0x1eae  ldloc.s  0xC
0x1eb0  ldstr    aPartyid// "partyid"
0x1eb5  ldarg.s  4
0x1eb7  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1ebc  box      [mscorlib]System.Guid
0x1ec1  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x1ec6  ldloc.s  0xC
0x1ec8  ldstr    aPartyobjecttyp// "partyobjecttypecode"
0x1ecd  ldarg.s  5
0x1ecf  box      [mscorlib]System.Int32
0x1ed4  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x1ed9  ldc.i4.1
0x1eda  newarr   [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity
0x1edf  dup
0x1ee0  ldc.i4.0
0x1ee1  ldloc.s  0xC
0x1ee3  stelem.ref
0x1ee4  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>)
0x1ee9  stloc.s  0xD
0x1eeb  dup
0x1eec  ldstr    aCustomer// "customer"
0x1ef1  ldloc.s  0xD
0x1ef3  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x1ef8  dup
0x1ef9  ldstr    aRegardingobjec// "regardingobjectid"
0x1efe  ldarg.s  7
0x1f00  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1f05  box      [mscorlib]System.Guid
0x1f0a  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x1f0f  dup
0x1f10  ldstr    aRegardingobjec_0// "regardingobjecttypecode"
0x1f15  ldarg.s  8
0x1f17  box      [mscorlib]System.Int32
0x1f1c  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x1f21  dup
0x1f22  ldstr    aOriginatingact// "originatingactivityid"
0x1f27  ldarg.1
0x1f28  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1f2d  box      [mscorlib]System.Guid
0x1f32  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x1f37  dup
0x1f38  ldarg.1
0x1f39  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1f3e  ldarg.2
0x1f3f  ldarg.s  0xC
0x1f41  call     void Microsoft.Crm.Common.Application.Commands.ApplicationCommand::FillResponseObject(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity campaignResponse, valuetype [mscorlib]System.Guid sourceEntityId, int32 activityType, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x1f46  dup
0x1f47  ldstr    aResponsecode// "responsecode"
0x1f4c  ldarg.s  0xC
0x1f4e  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1f53  ldc.i4   0x1131
0x1f58  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0x1f5d  ldstr    aResponsecode// "responsecode"
0x1f62  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string)
0x1f67  isinst   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PicklistAttributeMetadata
0x1f6c  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PicklistAttributeMetadata::get_DefaultValue()
0x1f71  box      [mscorlib]System.Int32
0x1f76  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x1f7b  dup
0x1f7c  ldstr    aOwnerid// "ownerid"
0x1f81  ldloc.s  4
0x1f83  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x1f88  dup
0x1f89  ldstr    aReceivedon// "receivedon"
0x1f8e  call     valuetype [mscorlib]System.DateTime [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_LocalDateTime()
0x1f93  stloc.s  0xF
0x1f95  ldloca.s 0xF
0x1f97  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Date()
0x1f9c  box      [mscorlib]System.DateTime
0x1fa1  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x1fa6  ldc.i4.0
0x1fa7  ldloc.s  5
0x1fa9  ldarg.s  0xC
0x1fab  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Create(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy, bool, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1fb0  stloc.s  0xE
0x1fb2  ldstr    aCampaignrespon// "campaignresponse"
0x1fb7  ldloc.s  0xE
0x1fb9  ldc.i4.1
0x1fba  stloc.s  0x10
0x1fbc  ldloca.s 0x10
0x1fbe  constrained. [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.CampaignResponseState
0x1fc4  callvirt instance string [mscorlib]System.Object::ToString()
0x1fc9  ldarg.s  0xC
0x1fcb  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.SetStateCommand::.ctor(string, valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1fd0  dup
0x1fd1  ldloc.s  5
0x1fd3  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.PlatformCommand::SetAuditingTransactionId(valuetype [mscorlib]System.Guid)
0x1fd8  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.SetStateCommand::Execute()
0x1fdd  ldarg.3
0x1fde  brfalse.s loc_202A
0x1fe0  ldarg.3
0x1fe1  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1fe6  ldc.i4.0
0x1fe7  ble.s    loc_202A
0x1fe9  ldloca.s 0x11
0x1feb  ldarg.3
0x1fec  call     instance void [mscorlib]System.Guid::.ctor(string)
0x1ff1  ldloc.s  0x11
0x1ff3  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1ff8  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1ffd  brfalse.s loc_202A
0x1fff  ldstr    aLead// "lead"
0x2004  ldloc.s  0x11
0x2006  ldc.i4.1
0x2007  stloc.s  0x12
0x2009  ldloca.s 0x12
0x200b  constrained. [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.LeadState
0x2011  callvirt instance string [mscorlib]System.Object::ToString()
0x2016  ldarg.s  0xC
0x2018  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.SetStateCommand::.ctor(string, valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x201d  dup
0x201e  ldloc.s  5
0x2020  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.PlatformCommand::SetAuditingTransactionId(valuetype [mscorlib]System.Guid)
0x2025  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.SetStateCommand::Execute()
0x202a  ldarg.s  0xC
0x202c  brfalse.s loc_2032
0x202e  ldarg.s  0xC
0x2030  br.s     loc_203B
0x2032  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x2037  stloc.s  0x13
0x2039  ldloc.s  0x13
0x203b  stloc.s  6
0x203d  ldloc.s  6
0x203f  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2044  ldarg.2
0x2045  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0x204a  ldloca.s 7
0x204c  ldarg.1
0x204d  call     instance void [mscorlib]System.Guid::.ctor(string)
0x2052  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x2057  ldloc.s  6
0x2059  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x205e  dup
0x205f  ldstr    aActivityid// "activityid"
0x2064  ldloc.s  7
0x2066  box      [mscorlib]System.Guid
0x206b  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x2070  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::.ctor()
0x2075  stloc.s  8
0x2077  ldloc.s  8
0x2079  ldloc.1
0x207a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Id()
  ... truncated ...
```
