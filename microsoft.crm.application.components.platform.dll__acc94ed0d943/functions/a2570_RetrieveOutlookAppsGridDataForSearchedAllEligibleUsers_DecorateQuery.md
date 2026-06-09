# RetrieveOutlookAppsGridDataForSearchedAllEligibleUsers::DecorateQuery

- ea: `0xa2570`
- end: `0xa2717`
- name: `RetrieveOutlookAppsGridDataForSearchedAllEligibleUsers::DecorateQuery`
- size: `423`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x9cb20`
- `0x9cba0`

## string_xrefs

- `0xa25d2`: `incomingemailstatus`
- `0xa26d1`: `incomingemailstatus`
- `0xa268f`: `incomingemaildeliverymethod`
- `0xa25f1`: `privilege`
- `0xa25b2`: `officeappsdeploymentscheduled`
- `0xa25ec`: `roleprivileges`
- `0xa262c`: `roleprivileges`
- `0xa25f6`: `privilegeid`
- `0xa25fb`: `privilegeid`

## pseudocode

```c

```

## disassembly

```asm
0xa2570  ldarg.0
0xa2571  call     instance class [System]System.Collections.Specialized.NameValueCollection ApiCommand::get_Parameters()
0xa2576  ldstr    aQuickfind// "quickFind"
0xa257b  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xa2580  stloc.0
0xa2581  ldstr    aMailbox// "mailbox"
0xa2586  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::.ctor(string)
0xa258b  stloc.1
0xa258c  ldloc.1
0xa258d  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_ColumnSet()
0xa2592  ldstr    aMailboxid// "mailboxid"
0xa2597  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::AddColumn(string)
0xa259c  ldloc.1
0xa259d  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_ColumnSet()
0xa25a2  ldstr    aOwnerid// "ownerid"
0xa25a7  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::AddColumn(string)
0xa25ac  ldloc.1
0xa25ad  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_ColumnSet()
0xa25b2  ldstr    aOfficeappsdepl// "officeappsdeploymentscheduled"
0xa25b7  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::AddColumn(string)
0xa25bc  ldloc.1
0xa25bd  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_ColumnSet()
0xa25c2  ldstr    aOfficeappsdepl_0// "officeappsdeploymentstatus"
0xa25c7  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::AddColumn(string)
0xa25cc  ldloc.1
0xa25cd  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_ColumnSet()
0xa25d2  ldstr    aIncomingemails// "incomingemailstatus"
0xa25d7  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::AddColumn(string)
0xa25dc  ldloc.1
0xa25dd  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_ColumnSet()
0xa25e2  ldstr    aActstatus// "actstatus"
0xa25e7  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::AddColumn(string)
0xa25ec  ldstr    aRoleprivileges_0// "roleprivileges"
0xa25f1  ldstr    aPrivilege_0// "privilege"
0xa25f6  ldstr    aPrivilegeid_0// "privilegeid"
0xa25fb  ldstr    aPrivilegeid_0// "privilegeid"
0xa2600  ldc.i4.0
0xa2601  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity::.ctor(string, string, string, string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.JoinOperator)
0xa2606  stloc.2
0xa2607  ldloc.2
0xa2608  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity::get_LinkCriteria()
0xa260d  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::get_Conditions()
0xa2612  ldstr    aName// "name"
0xa2617  ldc.i4.0
0xa2618  ldstr    aPrvuseofficeap// "prvUseOfficeApps"
0xa261d  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0xa2622  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression>::Add(var<u1>)
0xa2627  ldstr    aSystemuserrole_0// "systemuserroles"
0xa262c  ldstr    aRoleprivileges_0// "roleprivileges"
0xa2631  ldstr    aRoleid// "roleid"
0xa2636  ldstr    aRoleid// "roleid"
0xa263b  ldc.i4.0
0xa263c  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity::.ctor(string, string, string, string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.JoinOperator)
0xa2641  stloc.3
0xa2642  ldloc.3
0xa2643  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity::get_LinkEntities()
0xa2648  ldloc.2
0xa2649  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity>::Add(var<u1>)
0xa264e  ldstr    aMailbox// "mailbox"
0xa2653  ldstr    aSystemuserrole_0// "systemuserroles"
0xa2658  ldstr    aOwnerid// "ownerid"
0xa265d  ldstr    aSystemuserid// "systemuserid"
0xa2662  ldc.i4.0
0xa2663  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity::.ctor(string, string, string, string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.JoinOperator)
0xa2668  stloc.s  4
0xa266a  ldloc.s  4
0xa266c  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity::get_LinkEntities()
0xa2671  ldloc.3
0xa2672  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity>::Add(var<u1>)
0xa2677  ldloc.1
0xa2678  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_LinkEntities()
0xa267d  ldloc.s  4
0xa267f  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity>::Add(var<u1>)
0xa2684  ldloc.1
0xa2685  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0xa268a  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::get_Conditions()
0xa268f  ldstr    aIncomingemaild// "incomingemaildeliverymethod"
0xa2694  ldc.i4.0
0xa2695  ldc.i4.2
0xa2696  box      [mscorlib]System.Int32
0xa269b  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0xa26a0  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression>::Add(var<u1>)
0xa26a5  ldloc.1
0xa26a6  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0xa26ab  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::get_Conditions()
0xa26b0  ldstr    aStatuscode// "statuscode"
0xa26b5  ldc.i4.0
0xa26b6  ldc.i4.1
0xa26b7  box      [mscorlib]System.Int32
0xa26bc  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0xa26c1  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression>::Add(var<u1>)
0xa26c6  ldloc.1
0xa26c7  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0xa26cc  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::get_Conditions()
0xa26d1  ldstr    aIncomingemails// "incomingemailstatus"
0xa26d6  ldc.i4.0
0xa26d7  ldc.i4.1
0xa26d8  box      [mscorlib]System.Int32
0xa26dd  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0xa26e2  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression>::Add(var<u1>)
0xa26e7  ldloc.1
0xa26e8  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0xa26ed  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::get_Conditions()
0xa26f2  ldstr    aName// "name"
0xa26f7  ldc.i4.6
0xa26f8  ldloc.0
0xa26f9  call     string [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.QueryHelper::ConvertUserFindToLike(string)
0xa26fe  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0xa2703  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression>::Add(var<u1>)
0xa2708  ldloc.1
0xa2709  ldc.i4.1
0xa270a  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::set_Distinct(bool)
0xa270f  ldarg.0
0xa2710  ldloc.1
0xa2711  call     instance void ApiCommand::set_CurrentQueryExpression(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression value)
0xa2716  ret
```
