# Microsoft.Crm.ObjectModel.MailboxServiceInternal`1::CreateDefaultMailbox

- ea: `0x125a80`
- end: `0x125f9d`
- name: `Microsoft.Crm.ObjectModel.MailboxServiceInternal`1::CreateDefaultMailbox`
- size: `1309`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x122ef0`
- `0x122f10`
- `0x123000`
- `0x123010`
- `0x123090`
- `0x123150`
- `0x125a80`
- `0x129030`

## string_xrefs

- `0x125c3c`: `createdby`
- `0x125b5d`: `incomingemaildeliverymethod`
- `0x125bc2`: `emailrouteraccessapproval`
- `0x125d34`: `emailrouteraccessapproval`
- `0x125e57`: `emailrouteraccessapproval`
- `0x125e92`: `enabledforincomingemail`
- `0x125f31`: `enabledforincomingemail`
- `0x125f12`: `issyncwithdirectory`
- `0x125f1f`: `issyncwithdirectory`

## pseudocode

```c

```

## disassembly

```asm
0x125a80  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.ObjectModel.DefaultMailboxAttribute>::.ctor()
0x125a85  stloc.0
0x125a86  ldstr    aName// "name"
0x125a8b  ldarg.2
0x125a8c  ldarg.1
0x125a8d  callvirt instance string class Microsoft.Crm.ObjectModel.ReferencingEntityMailboxSynchronizerContext`1<var<u1>>::get_Name()
0x125a92  call     class Microsoft.Crm.ObjectModel.DefaultMailboxAttribute Microsoft.Crm.ObjectModel.DefaultMailboxAttributeFactory::Create(string mailboxAttributeName, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity sourceEntity, string sourceAttributeName)
0x125a97  stloc.1
0x125a98  ldloc.1
0x125a99  callvirt instance object Microsoft.Crm.ObjectModel.DefaultMailboxAttribute::get_AttributeValue()
0x125a9e  castclass [mscorlib]System.String
0x125aa3  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x125aa8  brfalse.s loc_125AF1
0x125aaa  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserDataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserDataCache::Instance()
0x125aaf  ldarg.3
0x125ab0  ldarg.s  6
0x125ab2  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser>::LookupEntry(void, var<u1>)
0x125ab7  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_LanguageId()
0x125abc  stloc.s  5
0x125abe  ldarg.s  6
0x125ac0  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_MetadataCache()
0x125ac5  ldc.i4   0x2586
0x125aca  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0x125acf  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LocalizedName()
0x125ad4  ldloc.s  5
0x125ad6  ldarg.s  6
0x125ad8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::GetLabel(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x125add  stloc.s  6
0x125adf  ldstr    aName// "name"
0x125ae4  ldloc.s  6
0x125ae6  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::get_Description()
0x125aeb  call     class Microsoft.Crm.ObjectModel.DefaultMailboxAttribute Microsoft.Crm.ObjectModel.DefaultMailboxAttributeFactory::Create(string attributeName, object value)
0x125af0  stloc.1
0x125af1  ldloc.0
0x125af2  ldloc.1
0x125af3  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.ObjectModel.DefaultMailboxAttribute>::Add(var<u1>)
0x125af8  ldloc.0
0x125af9  ldstr    aOwnerid// "ownerid"
0x125afe  ldarg.3
0x125aff  box      [mscorlib]System.Guid
0x125b04  call     class Microsoft.Crm.ObjectModel.DefaultMailboxAttribute Microsoft.Crm.ObjectModel.DefaultMailboxAttributeFactory::Create(string attributeName, object value)
0x125b09  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.ObjectModel.DefaultMailboxAttribute>::Add(var<u1>)
0x125b0e  ldloc.0
0x125b0f  ldstr    aOwneridtype// "owneridtype"
0x125b14  ldarg.s  4
0x125b16  box      [mscorlib]System.Int32
0x125b1b  call     class Microsoft.Crm.ObjectModel.DefaultMailboxAttribute Microsoft.Crm.ObjectModel.DefaultMailboxAttributeFactory::Create(string attributeName, object value)
0x125b20  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.ObjectModel.DefaultMailboxAttribute>::Add(var<u1>)
0x125b25  ldloc.0
0x125b26  ldstr    aRegardingobjec_0// "regardingobjectid"
0x125b2b  ldarg.s  5
0x125b2d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x125b32  box      [mscorlib]System.Guid
0x125b37  call     class Microsoft.Crm.ObjectModel.DefaultMailboxAttribute Microsoft.Crm.ObjectModel.DefaultMailboxAttributeFactory::Create(string attributeName, object value)
0x125b3c  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.ObjectModel.DefaultMailboxAttribute>::Add(var<u1>)
0x125b41  ldloc.0
0x125b42  ldstr    aRegardingobjec_1// "regardingobjecttypecode"
0x125b47  ldarg.1
0x125b48  callvirt instance int32 class Microsoft.Crm.ObjectModel.ReferencingEntityMailboxSynchronizerContext`1<var<u1>>::get_ObjectTypeCode()
0x125b4d  box      [mscorlib]System.Int32
0x125b52  call     class Microsoft.Crm.ObjectModel.DefaultMailboxAttribute Microsoft.Crm.ObjectModel.DefaultMailboxAttributeFactory::Create(string attributeName, object value)
0x125b57  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.ObjectModel.DefaultMailboxAttribute>::Add(var<u1>)
0x125b5c  ldloc.0
0x125b5d  ldstr    aIncomingemaild// "incomingemaildeliverymethod"
0x125b62  ldarg.2
0x125b63  ldarg.1
0x125b64  callvirt instance string class Microsoft.Crm.ObjectModel.ReferencingEntityMailboxSynchronizerContext`1<var<u1>>::get_IncomingMailDeliveryMethod()
0x125b69  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x125b6e  call     class Microsoft.Crm.ObjectModel.DefaultMailboxAttribute Microsoft.Crm.ObjectModel.DefaultMailboxAttributeFactory::Create(string attributeName, object value)
0x125b73  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.ObjectModel.DefaultMailboxAttribute>::Add(var<u1>)
0x125b78  ldloc.0
0x125b79  ldstr    aOutgoingemaild// "outgoingemaildeliverymethod"
0x125b7e  ldarg.2
0x125b7f  ldarg.1
0x125b80  callvirt instance string class Microsoft.Crm.ObjectModel.ReferencingEntityMailboxSynchronizerContext`1<var<u1>>::get_OutgoingMailDeliveryMethod()
0x125b85  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x125b8a  call     class Microsoft.Crm.ObjectModel.DefaultMailboxAttribute Microsoft.Crm.ObjectModel.DefaultMailboxAttributeFactory::Create(string attributeName, object value)
0x125b8f  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.ObjectModel.DefaultMailboxAttribute>::Add(var<u1>)
0x125b94  ldloc.0
0x125b95  ldstr    aIsforwardmailb// "isforwardmailbox"
0x125b9a  ldc.i4.0
0x125b9b  box      [mscorlib]System.Boolean
0x125ba0  call     class Microsoft.Crm.ObjectModel.DefaultMailboxAttribute Microsoft.Crm.ObjectModel.DefaultMailboxAttributeFactory::Create(string attributeName, object value)
0x125ba5  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.ObjectModel.DefaultMailboxAttribute>::Add(var<u1>)
0x125baa  ldloc.0
0x125bab  ldstr    aEmailaddress// "emailaddress"
0x125bb0  ldarg.2
0x125bb1  ldarg.1
0x125bb2  callvirt instance string class Microsoft.Crm.ObjectModel.ReferencingEntityMailboxSynchronizerContext`1<var<u1>>::get_EmailAddressKey()
0x125bb7  call     class Microsoft.Crm.ObjectModel.DefaultMailboxAttribute Microsoft.Crm.ObjectModel.DefaultMailboxAttributeFactory::Create(string mailboxAttributeName, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity sourceEntity, string sourceAttributeName)
0x125bbc  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.ObjectModel.DefaultMailboxAttribute>::Add(var<u1>)
0x125bc1  ldloc.0
0x125bc2  ldstr    aEmailrouteracc// "emailrouteraccessapproval"
0x125bc7  ldarg.2
0x125bc8  ldarg.1
0x125bc9  callvirt instance string class Microsoft.Crm.ObjectModel.ReferencingEntityMailboxSynchronizerContext`1<var<u1>>::get_EmailRouterAccessApprovalKey()
0x125bce  call     class Microsoft.Crm.ObjectModel.DefaultMailboxAttribute Microsoft.Crm.ObjectModel.DefaultMailboxAttributeFactory::Create(string mailboxAttributeName, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity sourceEntity, string sourceAttributeName)
0x125bd3  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.ObjectModel.DefaultMailboxAttribute>::Add(var<u1>)
0x125bd8  ldloc.0
0x125bd9  ldstr    aPostponemailbo// "postponemailboxprocessinguntil"
0x125bde  ldsfld   valuetype [mscorlib]System.DateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::MaxValue
0x125be3  ldc.i4.1
0x125be4  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::FromUniversal(valuetype [mscorlib]System.DateTime, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Behavior)
0x125be9  call     class Microsoft.Crm.ObjectModel.DefaultMailboxAttribute Microsoft.Crm.ObjectModel.DefaultMailboxAttributeFactory::Create(string attributeName, object value)
0x125bee  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.ObjectModel.DefaultMailboxAttribute>::Add(var<u1>)
0x125bf3  ldarg.0
0x125bf4  call     instance bool class Microsoft.Crm.ObjectModel.ProvisionedEntity`1<var<u1>>::get_Provisioning()
0x125bf9  brfalse.s loc_125C33
0x125bfb  ldloc.0
0x125bfc  ldstr    aOrganizationid_1// "organizationid"
0x125c01  ldarg.s  6
0x125c03  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x125c08  box      [mscorlib]System.Guid
0x125c0d  call     class Microsoft.Crm.ObjectModel.DefaultMailboxAttribute Microsoft.Crm.ObjectModel.DefaultMailboxAttributeFactory::Create(string attributeName, object value)
0x125c12  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.ObjectModel.DefaultMailboxAttribute>::Add(var<u1>)
0x125c17  ldloc.0
0x125c18  ldstr    aOwningbusiness// "owningbusinessunit"
0x125c1d  ldarg.2
0x125c1e  ldarg.1
0x125c1f  callvirt instance string class Microsoft.Crm.ObjectModel.ReferencingEntityMailboxSynchronizerContext`1<var<u1>>::get_OwningBusinessUnitKey()
0x125c24  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x125c29  call     class Microsoft.Crm.ObjectModel.DefaultMailboxAttribute Microsoft.Crm.ObjectModel.DefaultMailboxAttributeFactory::Create(string attributeName, object value)
0x125c2e  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.ObjectModel.DefaultMailboxAttribute>::Add(var<u1>)
0x125c33  ldarg.s  6
0x125c35  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x125c3a  pop
0x125c3b  ldloc.0
0x125c3c  ldstr    aCreatedby// "createdby"
0x125c41  ldarg.s  6
0x125c43  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x125c48  box      [mscorlib]System.Guid
0x125c4d  call     class Microsoft.Crm.ObjectModel.DefaultMailboxAttribute Microsoft.Crm.ObjectModel.DefaultMailboxAttributeFactory::Create(string attributeName, object value)
0x125c52  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.ObjectModel.DefaultMailboxAttribute>::Add(var<u1>)
0x125c57  ldloc.0
0x125c58  ldstr    aModifiedby_0// "modifiedby"
0x125c5d  ldarg.s  6
0x125c5f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x125c64  box      [mscorlib]System.Guid
0x125c69  call     class Microsoft.Crm.ObjectModel.DefaultMailboxAttribute Microsoft.Crm.ObjectModel.DefaultMailboxAttributeFactory::Create(string attributeName, object value)
0x125c6e  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.ObjectModel.DefaultMailboxAttribute>::Add(var<u1>)
0x125c73  ldarg.s  6
0x125c75  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x125c7a  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Mailbox::.ctor(valuetype [mscorlib]System.Guid)
0x125c7f  stloc.2
0x125c80  ldloc.0
0x125c81  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Crm.ObjectModel.DefaultMailboxAttribute>::GetEnumerator()
0x125c86  stloc.s  7
0x125c88  br.s     loc_125CA7
0x125c8a  ldloc.s  7
0x125c8c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Crm.ObjectModel.DefaultMailboxAttribute>::get_Current()
0x125c91  stloc.s  8
0x125c93  ldloc.2
0x125c94  ldloc.s  8
0x125c96  callvirt instance string Microsoft.Crm.ObjectModel.DefaultMailboxAttribute::get_AttributeName()
0x125c9b  ldloc.s  8
0x125c9d  callvirt instance object Microsoft.Crm.ObjectModel.DefaultMailboxAttribute::get_AttributeValue()
0x125ca2  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x125ca7  ldloc.s  7
0x125ca9  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x125cae  brtrue.s loc_125C8A
0x125cb0  leave.s  loc_125CBE
0x125cb2  ldloc.s  7
0x125cb4  brfalse.s loc_125CBD
0x125cb6  ldloc.s  7
0x125cb8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x125cbd  endfinally
0x125cbe  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x125cc3  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x125cc8  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_SSSReliabilityAutoApprove()
0x125ccd  ldarg.s  6
0x125ccf  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x125cd4  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x125cd9  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x125cde  brfalse  loc_125D84
0x125ce3  ldc.i4.2
0x125ce4  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x125ce9  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x125cee  bne.un   loc_125D84
0x125cf3  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationMetadataProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationMetadataProvider::get_Instance()
0x125cf8  ldarg.s  6
0x125cfa  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x125cff  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationMetadataProvider::IsOsdpOrganization(valuetype [mscorlib]System.Guid)
0x125d04  brfalse.s loc_125D84
0x125d06  ldarg.2
0x125d07  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_PlatformName()
0x125d0c  ldstr    aQueue// "Queue"
0x125d11  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x125d16  brfalse.s loc_125D84
0x125d18  ldarg.2
0x125d19  ldarg.s  6
0x125d1b  call     bool class Microsoft.Crm.ObjectModel.MailboxServiceInternal`1<var<u1>>::ShouldIsEmailApprovedByO365AdminBeUpdated(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x125d20  brfalse.s loc_125D46
0x125d22  ldloc.2
0x125d23  ldstr    aIsemailaddress// "isemailaddressapprovedbyo365admin"
0x125d28  ldc.i4.1
0x125d29  box      [mscorlib]System.Boolean
0x125d2e  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x125d33  ldloc.2
0x125d34  ldstr    aEmailrouteracc// "emailrouteraccessapproval"
0x125d39  ldc.i4.1
0x125d3a  box      [mscorlib]System.Int32
0x125d3f  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x125d44  br.s     loc_125D84
0x125d46  ldarg.s  6
0x125d48  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x125d4d  ldc.i4.s 0x11
0x125d4f  ldstr    aEmailIsNotAppr// "Email is not approved for the mailbox. "...
0x125d54  ldc.i4.3
0x125d55  newarr   [mscorlib]System.Object
0x125d5a  dup
0x125d5b  ldc.i4.0
0x125d5c  ldloc.2
0x125d5d  ldstr    aEmailaddress// "emailaddress"
0x125d62  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x125d67  stelem.ref
0x125d68  dup
0x125d69  ldc.i4.1
0x125d6a  ldarg.3
0x125d6b  box      [mscorlib]System.Guid
0x125d70  stelem.ref
0x125d71  dup
0x125d72  ldc.i4.2
0x125d73  ldarg.0
0x125d74  call     instance bool class Microsoft.Crm.ObjectModel.ProvisionedEntity`1<var<u1>>::get_Provisioning()
0x125d79  box      [mscorlib]System.Boolean
0x125d7e  stelem.ref
0x125d7f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x125d84  ldnull
0x125d85  stloc.3
0x125d86  ldloc.2
0x125d87  ldarg.s  6
0x125d89  ldarg.0
0x125d8a  call     instance bool class Microsoft.Crm.ObjectModel.ProvisionedEntity`1<var<u1>>::get_Provisioning()
0x125d8f  call     class Microsoft.Crm.ObjectModel.IDefaultEmailSettings Microsoft.Crm.ObjectModel.DefaultEmailSettingsFactory::GetDefaultEmailSettings(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, bool isProvisioning)
0x125d94  stloc.s  4
0x125d96  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x125d9b  ldloc.s  4
0x125d9d  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.ObjectModel.IDefaultEmailSettings::get_EmailServerProfileId()
0x125da2  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x125da7  brfalse.s loc_125DBD
0x125da9  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.EmailServerProfileCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.EmailServerProfileCache::Instance()
0x125dae  ldloc.s  4
0x125db0  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.ObjectModel.IDefaultEmailSettings::get_EmailServerProfileId()
0x125db5  ldarg.s  6
0x125db7  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IEmailServerProfile>::LookupEntry(void, var<u1>)
0x125dbc  stloc.3
0x125dbd  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x125dc2  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x125dc7  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_SSSExchangeSubscriptionCheck()
0x125dcc  ldarg.s  6
0x125dce  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x125dd3  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x125dd8  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x125ddd  brfalse  loc_125EE8
0x125de2  ldc.i4.2
0x125de3  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x125de8  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x125ded  bne.un   loc_125EE8
0x125df2  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationMetadataProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationMetadataProvider::get_Instance()
0x125df7  ldarg.s  6
0x125df9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x125dfe  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationMetadataProvider::IsOsdpOrganization(valuetype [mscorlib]System.Guid)
0x125e03  brfalse  loc_125EE8
0x125e08  ldarg.2
0x125e09  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_PlatformName()
0x125e0e  ldstr    aQueue// "Queue"
0x125e13  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x125e18  brfalse  loc_125EE8
0x125e1d  ldloc.3
0x125e1e  brfalse  loc_125EE8
0x125e23  ldloc.3
0x125e24  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CredentialRetrievalMethod [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IEmailServerProfile::get_IncomingCredentialRetrievalMethod()
0x125e29  ldc.i4.2
0x125e2a  bne.un   loc_125EE8
0x125e2f  ldloc.3
0x125e30  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.EmailServerType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IEmailServerProfile::get_ServerType()
0x125e35  brtrue   loc_125EE8
0x125e3a  ldarg.2
0x125e3b  ldarg.s  6
0x125e3d  ldnull
0x125e3e  call     bool Microsoft.Crm.ObjectModel.MailboxUtil::CheckIfUserhasExchangeSubscriptions([opt] class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, [opt] class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, [opt] string mailboxEmailAddress)
0x125e43  brfalse.s loc_125E69
0x125e45  ldloc.2
0x125e46  ldstr    aIsemailaddress// "isemailaddressapprovedbyo365admin"
0x125e4b  ldc.i4.1
0x125e4c  box      [mscorlib]System.Boolean
0x125e51  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x125e56  ldloc.2
0x125e57  ldstr    aEmailrouteracc// "emailrouteraccessapproval"
0x125e5c  ldc.i4.1
0x125e5d  box      [mscorlib]System.Int32
0x125e62  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x125e67  br.s     loc_125EE8
0x125e69  ldloc.2
0x125e6a  ldstr    aIsemailaddress// "isemailaddressapprovedbyo365admin"
0x125e6f  ldarg.2
0x125e70  ldarg.1
0x125e71  callvirt instance string class Microsoft.Crm.ObjectModel.ReferencingEntityMailboxSynchronizerContext`1<var<u1>>::get_IsEmailAddressApprovedByO365AdminKey()
0x125e76  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x125e7b  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
  ... truncated ...
```
