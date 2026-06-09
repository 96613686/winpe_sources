# RetrieveOutlookAppsGridDataForEligibleUsersPending::DecorateQuery

- ea: `0xa1bf0`
- end: `0xa1df3`
- name: `RetrieveOutlookAppsGridDataForEligibleUsersPending::DecorateQuery`
- size: `515`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x9cba0`

## string_xrefs

- `0xa1c41`: `incomingemailstatus`
- `0xa1da9`: `incomingemailstatus`
- `0xa1d46`: `incomingemaildeliverymethod`
- `0xa1c60`: `privilege`
- `0xa1c21`: `officeappsdeploymentscheduled`
- `0xa1d88`: `officeappsdeploymentscheduled`
- `0xa1c5b`: `roleprivileges`
- `0xa1c9b`: `roleprivileges`
- `0xa1c65`: `privilegeid`
- `0xa1c6a`: `privilegeid`

## pseudocode

```c

```

## disassembly

```asm
0xa1bf0  ldstr    aMailbox// "mailbox"
0xa1bf5  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::.ctor(string)
0xa1bfa  stloc.0
0xa1bfb  ldloc.0
0xa1bfc  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_ColumnSet()
0xa1c01  ldstr    aMailboxid// "mailboxid"
0xa1c06  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::AddColumn(string)
0xa1c0b  ldloc.0
0xa1c0c  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_ColumnSet()
0xa1c11  ldstr    aOwnerid// "ownerid"
0xa1c16  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::AddColumn(string)
0xa1c1b  ldloc.0
0xa1c1c  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_ColumnSet()
0xa1c21  ldstr    aOfficeappsdepl// "officeappsdeploymentscheduled"
0xa1c26  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::AddColumn(string)
0xa1c2b  ldloc.0
0xa1c2c  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_ColumnSet()
0xa1c31  ldstr    aOfficeappsdepl_0// "officeappsdeploymentstatus"
0xa1c36  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::AddColumn(string)
0xa1c3b  ldloc.0
0xa1c3c  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_ColumnSet()
0xa1c41  ldstr    aIncomingemails// "incomingemailstatus"
0xa1c46  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::AddColumn(string)
0xa1c4b  ldloc.0
0xa1c4c  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_ColumnSet()
0xa1c51  ldstr    aActstatus// "actstatus"
0xa1c56  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::AddColumn(string)
0xa1c5b  ldstr    aRoleprivileges_0// "roleprivileges"
0xa1c60  ldstr    aPrivilege_0// "privilege"
0xa1c65  ldstr    aPrivilegeid_0// "privilegeid"
0xa1c6a  ldstr    aPrivilegeid_0// "privilegeid"
0xa1c6f  ldc.i4.0
0xa1c70  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity::.ctor(string, string, string, string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.JoinOperator)
0xa1c75  stloc.1
0xa1c76  ldloc.1
0xa1c77  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity::get_LinkCriteria()
0xa1c7c  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::get_Conditions()
0xa1c81  ldstr    aName// "name"
0xa1c86  ldc.i4.0
0xa1c87  ldstr    aPrvuseofficeap// "prvUseOfficeApps"
0xa1c8c  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0xa1c91  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression>::Add(var<u1>)
0xa1c96  ldstr    aSystemuserrole_0// "systemuserroles"
0xa1c9b  ldstr    aRoleprivileges_0// "roleprivileges"
0xa1ca0  ldstr    aRoleid// "roleid"
0xa1ca5  ldstr    aRoleid// "roleid"
0xa1caa  ldc.i4.0
0xa1cab  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity::.ctor(string, string, string, string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.JoinOperator)
0xa1cb0  stloc.2
0xa1cb1  ldloc.2
0xa1cb2  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity::get_LinkEntities()
0xa1cb7  ldloc.1
0xa1cb8  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity>::Add(var<u1>)
0xa1cbd  ldstr    aMailbox// "mailbox"
0xa1cc2  ldstr    aSystemuserrole_0// "systemuserroles"
0xa1cc7  ldstr    aOwnerid// "ownerid"
0xa1ccc  ldstr    aSystemuserid// "systemuserid"
0xa1cd1  ldc.i4.0
0xa1cd2  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity::.ctor(string, string, string, string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.JoinOperator)
0xa1cd7  stloc.3
0xa1cd8  ldloc.3
0xa1cd9  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity::get_LinkEntities()
0xa1cde  ldloc.2
0xa1cdf  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity>::Add(var<u1>)
0xa1ce4  ldstr    aMailbox// "mailbox"
0xa1ce9  ldstr    aEmailserverpro// "emailserverprofile"
0xa1cee  ldstr    aEmailserverpro// "emailserverprofile"
0xa1cf3  ldstr    aEmailserverpro_0// "emailserverprofileid"
0xa1cf8  ldc.i4.0
0xa1cf9  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity::.ctor(string, string, string, string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.JoinOperator)
0xa1cfe  stloc.s  4
0xa1d00  ldloc.s  4
0xa1d02  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity::get_LinkCriteria()
0xa1d07  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::get_Conditions()
0xa1d0c  ldstr    aServertype// "servertype"
0xa1d11  ldc.i4.1
0xa1d12  ldc.i4.1
0xa1d13  box      [mscorlib]System.Int32
0xa1d18  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0xa1d1d  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression>::Add(var<u1>)
0xa1d22  ldloc.0
0xa1d23  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_LinkEntities()
0xa1d28  ldloc.3
0xa1d29  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity>::Add(var<u1>)
0xa1d2e  ldloc.0
0xa1d2f  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_LinkEntities()
0xa1d34  ldloc.s  4
0xa1d36  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity>::Add(var<u1>)
0xa1d3b  ldloc.0
0xa1d3c  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0xa1d41  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::get_Conditions()
0xa1d46  ldstr    aIncomingemaild// "incomingemaildeliverymethod"
0xa1d4b  ldc.i4.0
0xa1d4c  ldc.i4.2
0xa1d4d  box      [mscorlib]System.Int32
0xa1d52  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0xa1d57  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression>::Add(var<u1>)
0xa1d5c  ldloc.0
0xa1d5d  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0xa1d62  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::get_Conditions()
0xa1d67  ldstr    aStatuscode// "statuscode"
0xa1d6c  ldc.i4.0
0xa1d6d  ldc.i4.1
0xa1d6e  box      [mscorlib]System.Int32
0xa1d73  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0xa1d78  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression>::Add(var<u1>)
0xa1d7d  ldloc.0
0xa1d7e  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0xa1d83  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::get_Conditions()
0xa1d88  ldstr    aOfficeappsdepl// "officeappsdeploymentscheduled"
0xa1d8d  ldc.i4.0
0xa1d8e  ldc.i4.1
0xa1d8f  box      [mscorlib]System.Boolean
0xa1d94  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0xa1d99  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression>::Add(var<u1>)
0xa1d9e  ldloc.0
0xa1d9f  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0xa1da4  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::get_Conditions()
0xa1da9  ldstr    aIncomingemails// "incomingemailstatus"
0xa1dae  ldc.i4.0
0xa1daf  ldc.i4.1
0xa1db0  box      [mscorlib]System.Int32
0xa1db5  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0xa1dba  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression>::Add(var<u1>)
0xa1dbf  ldloc.0
0xa1dc0  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0xa1dc5  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::get_Conditions()
0xa1dca  ldstr    aRegardingobjec// "regardingobjecttypecode"
0xa1dcf  ldc.i4.1
0xa1dd0  ldc.i4   0x7E4
0xa1dd5  box      [mscorlib]System.Int32
0xa1dda  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0xa1ddf  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression>::Add(var<u1>)
0xa1de4  ldloc.0
0xa1de5  ldc.i4.1
0xa1de6  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::set_Distinct(bool)
0xa1deb  ldarg.0
0xa1dec  ldloc.0
0xa1ded  call     instance void ApiCommand::set_CurrentQueryExpression(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression value)
0xa1df2  ret
```
