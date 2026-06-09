# Microsoft.Crm.Application.Utility.WebUtility::IsThereAnyEmailPendingForApproval

- ea: `0x468a0`
- end: `0x46d7d`
- name: `Microsoft.Crm.Application.Utility.WebUtility::IsThereAnyEmailPendingForApproval`
- size: `1245`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x468a0`

## string_xrefs

- `0x468a4`: `Basic level is not supported for the email approval privilege`
- `0x468f0`: `emailrouteraccessapproval`
- `0x4691d`: `emailrouteraccessapproval`
- `0x46af6`: `emailrouteraccessapproval`
- `0x46d1d`: `emailrouteraccessapproval`
- `0x46954`: `incomingemaildeliverymethod`
- `0x46966`: `incomingemaildeliverymethod`
- `0x46c23`: `incomingemaildeliverymethod`
- `0x46c36`: `incomingemaildeliverymethod`
- `0x469bd`: `subbusinessid`
- `0x46a1a`: `subbusinessid`
- `0x469d4`: `businessid`
- `0x46c01`: `incomingemailstatus`

## pseudocode

```c

```

## disassembly

```asm
0x468a0  ldarg.1
0x468a1  ldc.i4.0
0x468a2  cgt.un
0x468a4  ldstr    aBasicLevelIsNo// "Basic level is not supported for the em"...
0x468a9  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x468ae  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::.ctor()
0x468b3  stloc.0
0x468b4  ldloc.0
0x468b5  ldarg.0
0x468b6  brtrue.s loc_468CE
0x468b8  ldstr    aQueue// "queue"
0x468bd  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x468c2  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x468c7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0x468cc  br.s     loc_468E2
0x468ce  ldstr    aSystemuser// "systemuser"
0x468d3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x468d8  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x468dd  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0x468e2  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::set_EntityName(string)
0x468e7  ldloc.0
0x468e8  ldc.i4.1
0x468e9  newarr   [mscorlib]System.String
0x468ee  dup
0x468ef  ldc.i4.0
0x468f0  ldstr    aEmailrouteracc// "emailrouteraccessapproval"
0x468f5  stelem.ref
0x468f6  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSet::.ctor(string[])
0x468fb  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::set_ColumnSet(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase)
0x46900  ldloc.0
0x46901  ldc.i4.1
0x46902  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x46907  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::set_TopCount(valuetype [mscorlib]System.Nullable`1<int32>)
0x4690c  ldloc.0
0x4690d  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::.ctor()
0x46912  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::set_Criteria(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression)
0x46917  ldloc.0
0x46918  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0x4691d  ldstr    aEmailrouteracc// "emailrouteraccessapproval"
0x46922  ldc.i4.0
0x46923  ldc.i4.2
0x46924  box      [mscorlib]System.Int32
0x46929  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x4692e  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::.ctor()
0x46933  stloc.1
0x46934  ldloc.1
0x46935  ldstr    aOutgoingemaild// "outgoingemaildeliverymethod"
0x4693a  ldc.i4.0
0x4693b  ldc.i4.2
0x4693c  box      [mscorlib]System.Int32
0x46941  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x46946  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::.ctor()
0x4694b  stloc.2
0x4694c  ldloc.2
0x4694d  ldc.i4.1
0x4694e  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::set_FilterOperator(valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.LogicalOperator)
0x46953  ldloc.2
0x46954  ldstr    aIncomingemaild// "incomingemaildeliverymethod"
0x46959  ldc.i4.0
0x4695a  ldc.i4.2
0x4695b  box      [mscorlib]System.Int32
0x46960  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x46965  ldloc.2
0x46966  ldstr    aIncomingemaild// "incomingemaildeliverymethod"
0x4696b  ldc.i4.0
0x4696c  ldc.i4.3
0x4696d  box      [mscorlib]System.Int32
0x46972  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x46977  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::.ctor()
0x4697c  stloc.3
0x4697d  ldloc.3
0x4697e  ldloc.1
0x4697f  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddFilter(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression)
0x46984  ldloc.3
0x46985  ldloc.2
0x46986  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddFilter(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression)
0x4698b  ldloc.3
0x4698c  ldc.i4.1
0x4698d  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::set_FilterOperator(valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.LogicalOperator)
0x46992  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0x46997  stloc.s  4
0x46999  ldc.i4.2
0x4699a  ldarg.1
0x4699b  bne.un   loc_46A6F
0x469a0  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::.ctor()
0x469a5  stloc.s  6
0x469a7  ldloc.s  6
0x469a9  ldstr    aBusinessunitma// "businessunitmap"
0x469ae  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::set_EntityName(string)
0x469b3  ldloc.s  6
0x469b5  ldc.i4.1
0x469b6  newarr   [mscorlib]System.String
0x469bb  dup
0x469bc  ldc.i4.0
0x469bd  ldstr    aSubbusinessid// "subbusinessid"
0x469c2  stelem.ref
0x469c3  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSet::.ctor(string[])
0x469c8  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::set_ColumnSet(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase)
0x469cd  ldloc.s  6
0x469cf  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0x469d4  ldstr    aBusinessid// "businessid"
0x469d9  ldc.i4.0
0x469da  ldarg.2
0x469db  box      [mscorlib]System.Guid
0x469e0  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x469e5  ldloc.s  6
0x469e7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x469ec  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::RetrieveMultiple(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x469f1  dup
0x469f2  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Count()
0x469f7  ldc.i4.0
0x469f8  cgt
0x469fa  ldstr    aAtLeastOneBusi// "At least one business unit record (for "...
0x469ff  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x46a04  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::GetEnumerator()
0x46a09  stloc.s  8
0x46a0b  br.s     loc_46A2E
0x46a0d  ldloc.s  8
0x46a0f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Current()
0x46a14  stloc.s  9
0x46a16  ldloc.s  4
0x46a18  ldloc.s  9
0x46a1a  ldstr    aSubbusinessid// "subbusinessid"
0x46a1f  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x46a24  unbox.any [mscorlib]System.Guid
0x46a29  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x46a2e  ldloc.s  8
0x46a30  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x46a35  brtrue.s loc_46A0D
0x46a37  leave.s  loc_46A45
0x46a39  ldloc.s  8
0x46a3b  brfalse.s loc_46A44
0x46a3d  ldloc.s  8
0x46a3f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x46a44  endfinally
0x46a45  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::.ctor()
0x46a4a  stloc.s  7
0x46a4c  ldloc.s  7
0x46a4e  ldstr    aBusinessunitid// "businessunitid"
0x46a53  ldc.i4.8
0x46a54  ldloc.s  4
0x46a56  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::ToArray()
0x46a5b  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, class [mscorlib]System.Array)
0x46a60  ldloc.0
0x46a61  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0x46a66  ldloc.s  7
0x46a68  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddFilter(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression)
0x46a6d  br.s     loc_46A9A
0x46a6f  ldc.i4.1
0x46a70  ldarg.1
0x46a71  bne.un.s loc_46A9A
0x46a73  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::.ctor()
0x46a78  stloc.s  0xA
0x46a7a  ldloc.s  0xA
0x46a7c  ldstr    aBusinessunitid// "businessunitid"
0x46a81  ldc.i4.0
0x46a82  ldarg.2
0x46a83  box      [mscorlib]System.Guid
0x46a88  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x46a8d  ldloc.0
0x46a8e  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0x46a93  ldloc.s  0xA
0x46a95  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddFilter(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression)
0x46a9a  ldloc.0
0x46a9b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0x46aa0  ldloc.3
0x46aa1  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddFilter(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression)
0x46aa6  ldloc.0
0x46aa7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x46aac  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::RetrieveMultiple(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x46ab1  stloc.s  5
0x46ab3  ldloc.s  5
0x46ab5  brfalse.s loc_46AC3
0x46ab7  ldloc.s  5
0x46ab9  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Count()
0x46abe  ldc.i4.0
0x46abf  ble.s    loc_46AC3
0x46ac1  ldc.i4.1
0x46ac2  ret
0x46ac3  ldarg.0
0x46ac4  brfalse  loc_46D7B
0x46ac9  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x46ace  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x46ad3  ldc.i4.2
0x46ad4  bne.un   loc_46D7B
0x46ad9  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::.ctor()
0x46ade  stloc.s  0xB
0x46ae0  ldloc.s  0xB
0x46ae2  ldstr    aMailbox// "mailbox"
0x46ae7  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::set_EntityName(string)
0x46aec  ldloc.s  0xB
0x46aee  ldc.i4.1
0x46aef  newarr   [mscorlib]System.String
0x46af4  dup
0x46af5  ldc.i4.0
0x46af6  ldstr    aEmailrouteracc// "emailrouteraccessapproval"
0x46afb  stelem.ref
0x46afc  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSet::.ctor(string[])
0x46b01  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::set_ColumnSet(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase)
0x46b06  ldloc.s  0xB
0x46b08  ldc.i4.1
0x46b09  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x46b0e  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::set_TopCount(valuetype [mscorlib]System.Nullable`1<int32>)
0x46b13  ldloc.s  0xB
0x46b15  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::.ctor()
0x46b1a  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::set_Criteria(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression)
0x46b1f  ldloc.s  0xB
0x46b21  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0x46b26  ldstr    aIsemailaddress// "isemailaddressapprovedbyo365admin"
0x46b2b  ldc.i4.0
0x46b2c  ldc.i4.0
0x46b2d  box      [mscorlib]System.Boolean
0x46b32  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x46b37  ldc.i4.2
0x46b38  ldarg.1
0x46b39  bne.un.s loc_46B99
0x46b3b  ldstr    aMailbox// "mailbox"
0x46b40  ldstr    aSystemuser// "systemuser"
0x46b45  ldstr    aMailboxid// "mailboxid"
0x46b4a  ldstr    aDefaultmailbox// "defaultmailbox"
0x46b4f  ldc.i4.0
0x46b50  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.LinkEntity::.ctor(string, string, string, string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.JoinOperator)
0x46b55  stloc.s  0x16
0x46b57  ldloc.s  0xB
0x46b59  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_LinkEntities()
0x46b5e  ldloc.s  0x16
0x46b60  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x46b65  pop
0x46b66  ldloc.s  0x16
0x46b68  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.LinkEntity::get_LinkCriteria()
0x46b6d  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::get_Conditions()
0x46b72  ldstr    aBusinessunitid// "businessunitid"
0x46b77  ldc.i4.8
0x46b78  ldloc.s  4
0x46b7a  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::ToArray()
0x46b7f  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, class [mscorlib]System.Array)
0x46b84  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x46b89  pop
0x46b8a  ldloc.s  0x16
0x46b8c  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.LinkEntity::get_LinkCriteria()
0x46b91  ldc.i4.0
0x46b92  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::set_FilterOperator(valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.LogicalOperator)
0x46b97  br.s     loc_46BF8
0x46b99  ldc.i4.1
0x46b9a  ldarg.1
0x46b9b  bne.un.s loc_46BF8
0x46b9d  ldstr    aMailbox// "mailbox"
0x46ba2  ldstr    aSystemuser// "systemuser"
0x46ba7  ldstr    aMailboxid// "mailboxid"
0x46bac  ldstr    aDefaultmailbox// "defaultmailbox"
0x46bb1  ldc.i4.0
0x46bb2  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.LinkEntity::.ctor(string, string, string, string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.JoinOperator)
0x46bb7  stloc.s  0x17
0x46bb9  ldloc.s  0xB
0x46bbb  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_LinkEntities()
0x46bc0  ldloc.s  0x17
0x46bc2  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x46bc7  pop
0x46bc8  ldloc.s  0x17
0x46bca  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.LinkEntity::get_LinkCriteria()
0x46bcf  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::get_Conditions()
0x46bd4  ldstr    aBusinessunitid// "businessunitid"
0x46bd9  ldc.i4.0
0x46bda  ldarg.2
0x46bdb  box      [mscorlib]System.Guid
0x46be0  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x46be5  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x46bea  pop
0x46beb  ldloc.s  0x17
0x46bed  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.LinkEntity::get_LinkCriteria()
0x46bf2  ldc.i4.0
0x46bf3  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::set_FilterOperator(valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.LogicalOperator)
0x46bf8  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::.ctor()
0x46bfd  stloc.s  0xC
0x46bff  ldloc.s  0xC
0x46c01  ldstr    aIncomingemails// "incomingemailstatus"
0x46c06  ldc.i4.1
0x46c07  ldc.i4.0
0x46c08  box      [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.MailboxAccessStatus
0x46c0d  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x46c12  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::.ctor()
0x46c17  stloc.s  0xD
0x46c19  ldloc.s  0xD
0x46c1b  ldc.i4.1
0x46c1c  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::set_FilterOperator(valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.LogicalOperator)
0x46c21  ldloc.s  0xD
0x46c23  ldstr    aIncomingemaild// "incomingemaildeliverymethod"
0x46c28  ldc.i4.0
0x46c29  ldc.i4.2
0x46c2a  box      [mscorlib]System.Int32
0x46c2f  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x46c34  ldloc.s  0xD
0x46c36  ldstr    aIncomingemaild// "incomingemaildeliverymethod"
0x46c3b  ldc.i4.0
0x46c3c  ldc.i4.3
0x46c3d  box      [mscorlib]System.Int32
0x46c42  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x46c47  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::.ctor()
0x46c4c  stloc.s  0xE
0x46c4e  ldloc.s  0xE
  ... truncated ...
```
