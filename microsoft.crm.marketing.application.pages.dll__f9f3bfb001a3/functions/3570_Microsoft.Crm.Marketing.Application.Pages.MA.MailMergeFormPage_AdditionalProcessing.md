# Microsoft.Crm.Marketing.Application.Pages.MA.MailMergeFormPage::AdditionalProcessing

- ea: `0x3570`
- end: `0x3702`
- name: `Microsoft.Crm.Marketing.Application.Pages.MA.MailMergeFormPage::AdditionalProcessing`
- size: `402`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x33a0`

## callees

- `0x3570`

## pseudocode

```c

```

## disassembly

```asm
0x3570  ldarg.0
0x3571  ldfld    int32 Microsoft.Crm.Marketing.Application.Pages.MA.MailMergeFormPage::objectTypeCode
0x3576  stloc.0
0x3577  ldloc.0
0x3578  ldc.i4   0x10CC
0x357d  beq      loc_36B1
0x3582  ldloc.0
0x3583  ldc.i4   0x1132
0x3588  bne.un   loc_3701
0x358d  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::.ctor()
0x3592  stloc.1
0x3593  ldloc.1
0x3594  ldstr    aList// "list"
0x3599  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x359e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x35a3  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0x35a8  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::set_EntityName(string)
0x35ad  ldloc.1
0x35ae  ldc.i4.1
0x35af  newarr   [mscorlib]System.String
0x35b4  dup
0x35b5  ldc.i4.0
0x35b6  ldstr    aMembertype// "membertype"
0x35bb  stelem.ref
0x35bc  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSet::.ctor(string[])
0x35c1  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::set_ColumnSet(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase)
0x35c6  ldloc.1
0x35c7  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::.ctor()
0x35cc  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::set_Criteria(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression)
0x35d1  ldloc.1
0x35d2  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::get_EntityName()
0x35d7  ldstr    aCampaignactivi_3// "campaignactivityitem"
0x35dc  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x35e1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x35e6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0x35eb  ldstr    aListid// "listid"
0x35f0  ldstr    aItemid// "itemid"
0x35f5  ldc.i4.0
0x35f6  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.LinkEntity::.ctor(string, string, string, string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.JoinOperator)
0x35fb  stloc.2
0x35fc  ldloc.1
0x35fd  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_LinkEntities()
0x3602  ldloc.2
0x3603  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x3608  pop
0x3609  ldloc.2
0x360a  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.LinkEntity::get_LinkCriteria()
0x360f  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::get_Conditions()
0x3614  ldstr    aCampaignactivi_4// "campaignactivityid"
0x3619  ldc.i4.0
0x361a  ldarg.0
0x361b  ldfld    string Microsoft.Crm.Marketing.Application.Pages.MA.MailMergeFormPage::objectId
0x3620  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x3625  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x362a  pop
0x362b  ldloc.1
0x362c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x3631  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::RetrieveMultiple(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3636  dup
0x3637  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Count()
0x363c  ldc.i4.0
0x363d  bgt.s    loc_364A
0x363f  ldstr    aNoMarketingLis// "No marketing list associated with the i"...
0x3644  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x3649  throw
0x364a  dup
0x364b  ldc.i4.0
0x364c  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Item(!!T0)
0x3651  ldstr    aMembertype// "membertype"
0x3656  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x365b  unbox.any [mscorlib]System.Int32
0x3660  stloc.3
0x3661  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::GetEnumerator()
0x3666  stloc.s  5
0x3668  br.s     loc_3692
0x366a  ldloc.s  5
0x366c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Current()
0x3671  stloc.s  6
0x3673  ldloc.3
0x3674  ldloc.s  6
0x3676  ldstr    aMembertype// "membertype"
0x367b  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x3680  unbox.any [mscorlib]System.Int32
0x3685  beq.s    loc_3692
0x3687  ldstr    aAssociatedMark// "Associated marketing lists are not of s"...
0x368c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x3691  throw
0x3692  ldloc.s  5
0x3694  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x3699  brtrue.s loc_366A
0x369b  leave.s  loc_36A9
0x369d  ldloc.s  5
0x369f  brfalse.s loc_36A8
0x36a1  ldloc.s  5
0x36a3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x36a8  endfinally
0x36a9  ldarg.0
0x36aa  ldloc.3
0x36ab  stfld    int32 Microsoft.Crm.Marketing.Application.Pages.MA.MailMergeFormPage::lookupObjectTypeCode
0x36b0  ret
0x36b1  ldstr    aList// "list"
0x36b6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x36bb  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x36c0  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0x36c5  ldarg.0
0x36c6  ldfld    string Microsoft.Crm.Marketing.Application.Pages.MA.MailMergeFormPage::objectId
0x36cb  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x36d0  ldc.i4.1
0x36d1  newarr   [mscorlib]System.String
0x36d6  dup
0x36d7  ldc.i4.0
0x36d8  ldstr    aMembertype// "membertype"
0x36dd  stelem.ref
0x36de  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x36e3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Retrieve(string, valuetype [mscorlib]System.Guid, string[], class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x36e8  stloc.s  4
0x36ea  ldarg.0
0x36eb  ldloc.s  4
0x36ed  ldstr    aMembertype// "membertype"
0x36f2  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x36f7  unbox.any [mscorlib]System.Int32
0x36fc  stfld    int32 Microsoft.Crm.Marketing.Application.Pages.MA.MailMergeFormPage::lookupObjectTypeCode
0x3701  ret
```
