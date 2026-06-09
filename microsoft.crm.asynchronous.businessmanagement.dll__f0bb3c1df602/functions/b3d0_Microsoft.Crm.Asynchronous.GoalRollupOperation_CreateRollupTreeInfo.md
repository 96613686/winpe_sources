# Microsoft.Crm.Asynchronous.GoalRollupOperation::CreateRollupTreeInfo

- ea: `0xb3d0`
- end: `0xb64c`
- name: `Microsoft.Crm.Asynchronous.GoalRollupOperation::CreateRollupTreeInfo`
- size: `636`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xb650`

## callees

- `0xb3d0`

## string_xrefs

- `0xb61e`: `amountdatatype`
- `0xb60c`: `isamount`

## pseudocode

```c

```

## disassembly

```asm
0xb3d0  ldstr    aRollupfield// "rollupfield"
0xb3d5  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::.ctor(string)
0xb3da  stloc.0
0xb3db  ldloc.0
0xb3dc  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_ColumnSet()
0xb3e1  ldc.i4.8
0xb3e2  newarr   [mscorlib]System.String
0xb3e7  dup
0xb3e8  ldc.i4.0
0xb3e9  ldstr    aSourceentity// "sourceentity"
0xb3ee  stelem.ref
0xb3ef  dup
0xb3f0  ldc.i4.1
0xb3f1  ldstr    aSourceattribut// "sourceattribute"
0xb3f6  stelem.ref
0xb3f7  dup
0xb3f8  ldc.i4.2
0xb3f9  ldstr    aDateattribute// "dateattribute"
0xb3fe  stelem.ref
0xb3ff  dup
0xb400  ldc.i4.3
0xb401  ldstr    aEntityfordatea// "entityfordateattribute"
0xb406  stelem.ref
0xb407  dup
0xb408  ldc.i4.4
0xb409  ldstr    aGoalattribute// "goalattribute"
0xb40e  stelem.ref
0xb40f  dup
0xb410  ldc.i4.5
0xb411  ldstr    aSourcestate// "sourcestate"
0xb416  stelem.ref
0xb417  dup
0xb418  ldc.i4.6
0xb419  ldstr    aSourcestatus// "sourcestatus"
0xb41e  stelem.ref
0xb41f  dup
0xb420  ldc.i4.7
0xb421  ldstr    aIsstateparente// "isstateparententityattribute"
0xb426  stelem.ref
0xb427  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::AddColumns(string[])
0xb42c  ldloc.0
0xb42d  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0xb432  ldstr    aMetricid// "metricid"
0xb437  ldc.i4.0
0xb438  ldc.i4.1
0xb439  newarr   [mscorlib]System.Object
0xb43e  dup
0xb43f  ldc.i4.0
0xb440  ldarg.1
0xb441  ldstr    aMetricid// "metricid"
0xb446  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0xb44b  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0xb450  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0xb455  box      [mscorlib]System.Guid
0xb45a  stelem.ref
0xb45b  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object[])
0xb460  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0xb465  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.GoalManagement.RollupFieldInfo>::.ctor(class [mscorlib]System.Collections.Generic.IEqualityComparer`1<var<u1>>)
0xb46a  stloc.1
0xb46b  ldarg.0
0xb46c  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Asynchronous.GoalRollupOperation::_orgService
0xb471  ldloc.0
0xb472  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.GoalManagement.PagedEntityEnumerator::.ctor(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression)
0xb477  stloc.s  6
0xb479  br       loc_B5BA
0xb47e  ldloc.s  6
0xb480  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Current()
0xb485  stloc.s  7
0xb487  ldloc.s  7
0xb489  ldstr    aSourceentity// "sourceentity"
0xb48e  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0xb493  castclass [mscorlib]System.String
0xb498  ldloc.s  7
0xb49a  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0xb49f  ldstr    aSourceattribut// "sourceattribute"
0xb4a4  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0xb4a9  brtrue.s loc_B4AE
0xb4ab  ldnull
0xb4ac  br.s     loc_B4BF
0xb4ae  ldloc.s  7
0xb4b0  ldstr    aSourceattribut// "sourceattribute"
0xb4b5  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0xb4ba  castclass [mscorlib]System.String
0xb4bf  stloc.s  8
0xb4c1  ldloc.s  7
0xb4c3  ldstr    aDateattribute// "dateattribute"
0xb4c8  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0xb4cd  castclass [mscorlib]System.String
0xb4d2  stloc.s  9
0xb4d4  dup
0xb4d5  ldloc.s  7
0xb4d7  ldstr    aEntityfordatea// "entityfordateattribute"
0xb4dc  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0xb4e1  castclass [mscorlib]System.String
0xb4e6  ldc.i4.5
0xb4e7  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0xb4ec  ldc.i4.0
0xb4ed  ceq
0xb4ef  stloc.s  0xA
0xb4f1  ldloc.s  7
0xb4f3  ldstr    aGoalattribute// "goalattribute"
0xb4f8  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0xb4fd  castclass [mscorlib]System.String
0xb502  stloc.s  0xB
0xb504  ldloc.s  7
0xb506  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0xb50b  ldstr    aSourcestate// "sourcestate"
0xb510  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0xb515  brtrue.s loc_B523
0xb517  ldloca.s 0x10
0xb519  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0xb51f  ldloc.s  0x10
0xb521  br.s     loc_B534
0xb523  ldloc.s  7
0xb525  ldstr    aSourcestate// "sourcestate"
0xb52a  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0xb52f  unbox.any valuetype [mscorlib]System.Nullable`1<int32>
0xb534  stloc.s  0xC
0xb536  ldloc.s  7
0xb538  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0xb53d  ldstr    aSourcestatus// "sourcestatus"
0xb542  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0xb547  brtrue.s loc_B555
0xb549  ldloca.s 0x10
0xb54b  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0xb551  ldloc.s  0x10
0xb553  br.s     loc_B566
0xb555  ldloc.s  7
0xb557  ldstr    aSourcestatus// "sourcestatus"
0xb55c  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0xb561  unbox.any valuetype [mscorlib]System.Nullable`1<int32>
0xb566  stloc.s  0xD
0xb568  ldc.i4.0
0xb569  stloc.s  0xE
0xb56b  ldloca.s 0xC
0xb56d  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0xb572  brtrue.s loc_B57D
0xb574  ldloca.s 0xD
0xb576  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0xb57b  brfalse.s loc_B590
0xb57d  ldloc.s  7
0xb57f  ldstr    aIsstateparente// "isstateparententityattribute"
0xb584  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0xb589  unbox.any [mscorlib]System.Boolean
0xb58e  stloc.s  0xE
0xb590  ldloc.s  8
0xb592  ldloc.s  0xB
0xb594  ldloc.s  9
0xb596  ldloc.s  0xA
0xb598  ldloc.s  0xC
0xb59a  ldloc.s  0xD
0xb59c  ldloc.s  0xE
0xb59e  ldarg.0
0xb59f  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_Configuration()
0xb5a4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0xb5a9  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.GoalManagement.RollupFieldInfo::.ctor(string, string, string, string, bool, valuetype [mscorlib]System.Nullable`1<int32>, valuetype [mscorlib]System.Nullable`1<int32>, bool, valuetype [mscorlib]System.Guid)
0xb5ae  stloc.s  0xF
0xb5b0  ldloc.1
0xb5b1  ldloc.s  0xB
0xb5b3  ldloc.s  0xF
0xb5b5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.GoalManagement.RollupFieldInfo>::Add(var<u1>, !!T0)
0xb5ba  ldloc.s  6
0xb5bc  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xb5c1  brtrue   loc_B47E
0xb5c6  leave.s  loc_B5D4
0xb5c8  ldloc.s  6
0xb5ca  brfalse.s loc_B5D3
0xb5cc  ldloc.s  6
0xb5ce  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xb5d3  endfinally
0xb5d4  ldarg.1
0xb5d5  ldstr    aTreeid// "treeid"
0xb5da  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0xb5df  unbox.any [mscorlib]System.Guid
0xb5e4  stloc.2
0xb5e5  ldarg.1
0xb5e6  ldstr    aGoalstartdate// "goalstartdate"
0xb5eb  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0xb5f0  unbox.any [mscorlib]System.DateTime
0xb5f5  stloc.3
0xb5f6  ldarg.1
0xb5f7  ldstr    aGoalenddate// "goalenddate"
0xb5fc  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0xb601  unbox.any [mscorlib]System.DateTime
0xb606  stloc.s  4
0xb608  ldc.i4.3
0xb609  stloc.s  5
0xb60b  ldarg.1
0xb60c  ldstr    aIsamount// "isamount"
0xb611  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0xb616  unbox.any [mscorlib]System.Boolean
0xb61b  brfalse.s loc_B634
0xb61d  ldarg.1
0xb61e  ldstr    aAmountdatatype// "amountdatatype"
0xb623  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0xb628  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue
0xb62d  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::get_Value()
0xb632  stloc.s  5
0xb634  ldarg.0
0xb635  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_Configuration()
0xb63a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0xb63f  ldloc.2
0xb640  ldloc.3
0xb641  ldloc.s  4
0xb643  ldloc.s  5
0xb645  ldloc.1
0xb646  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.GoalManagement.RollupTreeInfo::.ctor(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime, valuetype [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.GoalManagement.GoalRollupType, class [mscorlib]System.Collections.Generic.IDictionary`2<string, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.GoalManagement.RollupFieldInfo>)
0xb64b  ret
```
