# Microsoft.Crm.Asynchronous.UpdateKnowledgeArticleStatesOperation::ExpireKnowledgeArticles

- ea: `0xa990`
- end: `0xac53`
- name: `Microsoft.Crm.Asynchronous.UpdateKnowledgeArticleStatesOperation::ExpireKnowledgeArticles`
- size: `707`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0xa7b0`

## callees

- `0xa990`
- `0xaea0`

## string_xrefs

- `0xaa46`: `expirationstatusid`
- `0xaae7`: `expirationstatusid`
- `0xab2b`: `expirationstatusid`
- `0xac13`: `expirationstatusid`
- `0xac28`: `expirationstatusid`
- `0xab83`: `Error in AsyncHandler::UpdateKnowledgeArticleStatesOperation::ExpireKnowledgeArticles() for knowledgearticleid {0} - {1}`
- `0xabc7`: `Warning in AsyncHandler::UpdateKnowledgeArticleStatesOperation::ExpireKnowledgeArticles() for knowledgearticleid {0} . ExpirayStateId ExpiryStatusId combination is not present. ExpirayStateId:{1} ExpiryStatusId:{2} `

## pseudocode

```c

```

## disassembly

```asm
0xa990  ldarg.0
0xa991  call     instance bool Microsoft.Crm.Asynchronous.UpdateKnowledgeArticleStatesOperation::HasJobBeenAbortedOrPaused()
0xa996  brtrue   loc_AC52
0xa99b  ldstr    aStatecode// "statecode"
0xa9a0  ldc.i4.0
0xa9a1  ldc.i4.1
0xa9a2  newarr   [mscorlib]System.Object
0xa9a7  dup
0xa9a8  ldc.i4.0
0xa9a9  ldc.i4.3
0xa9aa  box      [mscorlib]System.Int32
0xa9af  stelem.ref
0xa9b0  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object[])
0xa9b5  stloc.0
0xa9b6  ldstr    aExpirationdate// "expirationdate"
0xa9bb  ldc.i4.s 0xD
0xa9bd  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator)
0xa9c2  stloc.1
0xa9c3  ldstr    aExpirationdate// "expirationdate"
0xa9c8  ldc.i4.5
0xa9c9  ldc.i4.1
0xa9ca  newarr   [mscorlib]System.Object
0xa9cf  dup
0xa9d0  ldc.i4.0
0xa9d1  ldarg.0
0xa9d2  ldfld    valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.UpdateKnowledgeArticleStatesOperation::_now
0xa9d7  call     class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime::FromUniversal(valuetype [mscorlib]System.DateTime)
0xa9dc  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime::get_Value()
0xa9e1  stelem.ref
0xa9e2  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object[])
0xa9e7  stloc.2
0xa9e8  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::.ctor()
0xa9ed  stloc.3
0xa9ee  ldloc.3
0xa9ef  ldc.i4.0
0xa9f0  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::set_FilterOperator(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LogicalOperator)
0xa9f5  ldloc.3
0xa9f6  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::get_Conditions()
0xa9fb  ldloc.0
0xa9fc  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression>::Add(var<u1>)
0xaa01  ldloc.3
0xaa02  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::get_Conditions()
0xaa07  ldloc.1
0xaa08  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression>::Add(var<u1>)
0xaa0d  ldloc.3
0xaa0e  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::get_Conditions()
0xaa13  ldloc.2
0xaa14  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression>::Add(var<u1>)
0xaa19  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::.ctor()
0xaa1e  stloc.s  4
0xaa20  ldloc.s  4
0xaa22  ldstr    aKnowledgeartic// "knowledgearticle"
0xaa27  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::set_EntityName(string)
0xaa2c  ldloc.s  4
0xaa2e  ldc.i4.3
0xaa2f  newarr   [mscorlib]System.String
0xaa34  dup
0xaa35  ldc.i4.0
0xaa36  ldstr    aKnowledgeartic_0// "knowledgearticleid"
0xaa3b  stelem.ref
0xaa3c  dup
0xaa3d  ldc.i4.1
0xaa3e  ldstr    aExpirationstat// "expirationstateid"
0xaa43  stelem.ref
0xaa44  dup
0xaa45  ldc.i4.2
0xaa46  ldstr    aExpirationstat_0// "expirationstatusid"
0xaa4b  stelem.ref
0xaa4c  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::.ctor(string[])
0xaa51  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::set_ColumnSet(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet)
0xaa56  ldloc.s  4
0xaa58  ldloc.3
0xaa59  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::set_Criteria(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression)
0xaa5e  ldarg.0
0xaa5f  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Asynchronous.UpdateKnowledgeArticleStatesOperation::_sdkService
0xaa64  ldloc.s  4
0xaa66  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::RetrieveMultiple(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryBase)
0xaa6b  stloc.s  5
0xaa6d  ldloc.s  5
0xaa6f  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0xaa74  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Count()
0xaa79  ldc.i4.0
0xaa7a  ble      loc_AC52
0xaa7f  ldloc.s  5
0xaa81  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0xaa86  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::GetEnumerator()
0xaa8b  stloc.s  6
0xaa8d  br       loc_AC38
0xaa92  ldloc.s  6
0xaa94  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Current()
0xaa99  stloc.s  7
0xaa9b  ldarg.0
0xaa9c  call     instance bool Microsoft.Crm.Asynchronous.UpdateKnowledgeArticleStatesOperation::HasJobBeenAbortedOrPaused()
0xaaa1  brtrue   loc_AC44
0xaaa6  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.UpdateRequest::.ctor()
0xaaab  stloc.s  8
0xaaad  ldstr    aKnowledgeartic// "knowledgearticle"
0xaab2  ldloc.s  7
0xaab4  ldstr    aKnowledgeartic_0// "knowledgearticleid"
0xaab9  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0xaabe  unbox.any [mscorlib]System.Guid
0xaac3  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string, valuetype [mscorlib]System.Guid)
0xaac8  stloc.s  9
0xaaca  ldloc.s  7
0xaacc  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0xaad1  ldstr    aExpirationstat// "expirationstateid"
0xaad6  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0xaadb  brfalse  loc_ABBA
0xaae0  ldloc.s  7
0xaae2  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0xaae7  ldstr    aExpirationstat_0// "expirationstatusid"
0xaaec  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0xaaf1  brfalse  loc_ABBA
0xaaf6  ldloc.s  9
0xaaf8  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0xaafd  ldstr    aStatecode// "statecode"
0xab02  ldloc.s  7
0xab04  ldstr    aExpirationstat// "expirationstateid"
0xab09  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0xab0e  unbox.any [mscorlib]System.Int32
0xab13  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::.ctor(int32)
0xab18  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Add(var<u1>, !!T0)
0xab1d  ldloc.s  9
0xab1f  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0xab24  ldstr    aStatuscode// "statuscode"
0xab29  ldloc.s  7
0xab2b  ldstr    aExpirationstat_0// "expirationstatusid"
0xab30  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0xab35  unbox.any [mscorlib]System.Int32
0xab3a  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::.ctor(int32)
0xab3f  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Add(var<u1>, !!T0)
0xab44  ldloc.s  9
0xab46  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0xab4b  ldstr    aExpirationdate// "expirationdate"
0xab50  ldnull
0xab51  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Add(var<u1>, !!T0)
0xab56  ldloc.s  8
0xab58  ldloc.s  9
0xab5a  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.UpdateRequest::set_Target(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity)
0xab5f  ldarg.0
0xab60  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Asynchronous.UpdateKnowledgeArticleStatesOperation::_sdkService
0xab65  ldloc.s  8
0xab67  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0xab6c  pop
0xab6d  leave    loc_AC38
0xab72  stloc.s  0xA
0xab74  ldloc.s  0xA
0xab76  ldarg.0
0xab77  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.UpdateKnowledgeArticleStatesOperation::_asyncEvent
0xab7c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0xab81  ldc.i4.s 0x15
0xab83  ldstr    aErrorInAsyncha_4// "Error in AsyncHandler::UpdateKnowledgeA"...
0xab88  ldc.i4.2
0xab89  newarr   [mscorlib]System.Object
0xab8e  dup
0xab8f  ldc.i4.0
0xab90  ldloc.s  8
0xab92  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.UpdateRequest::get_Target()
0xab97  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0xab9c  box      [mscorlib]System.Guid
0xaba1  stelem.ref
0xaba2  dup
0xaba3  ldc.i4.1
0xaba4  ldloc.s  0xA
0xaba6  callvirt instance string [mscorlib]System.Exception::get_Message()
0xabab  stelem.ref
0xabac  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xabb1  ldarg.0
0xabb2  ldc.i4.1
0xabb3  stfld    bool Microsoft.Crm.Asynchronous.UpdateKnowledgeArticleStatesOperation::_errorOccured
0xabb8  leave.s  loc_AC38
0xabba  ldarg.0
0xabbb  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.UpdateKnowledgeArticleStatesOperation::_asyncEvent
0xabc0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0xabc5  ldc.i4.s 0x15
0xabc7  ldstr    aWarningInAsync// "Warning in AsyncHandler::UpdateKnowledg"...
0xabcc  ldc.i4.3
0xabcd  newarr   [mscorlib]System.Object
0xabd2  dup
0xabd3  ldc.i4.0
0xabd4  ldloc.s  9
0xabd6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0xabdb  box      [mscorlib]System.Guid
0xabe0  stelem.ref
0xabe1  dup
0xabe2  ldc.i4.1
0xabe3  ldloc.s  7
0xabe5  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0xabea  ldstr    aExpirationstat// "expirationstateid"
0xabef  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0xabf4  brtrue.s loc_ABFD
0xabf6  ldstr    aUndefined// "Undefined"
0xabfb  br.s     loc_AC09
0xabfd  ldloc.s  7
0xabff  ldstr    aExpirationstat// "expirationstateid"
0xac04  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0xac09  stelem.ref
0xac0a  dup
0xac0b  ldc.i4.2
0xac0c  ldloc.s  7
0xac0e  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0xac13  ldstr    aExpirationstat_0// "expirationstatusid"
0xac18  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0xac1d  brtrue.s loc_AC26
0xac1f  ldstr    aUndefined// "Undefined"
0xac24  br.s     loc_AC32
0xac26  ldloc.s  7
0xac28  ldstr    aExpirationstat_0// "expirationstatusid"
0xac2d  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0xac32  stelem.ref
0xac33  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xac38  ldloc.s  6
0xac3a  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xac3f  brtrue   loc_AA92
0xac44  leave.s  loc_AC52
0xac46  ldloc.s  6
0xac48  brfalse.s loc_AC51
0xac4a  ldloc.s  6
0xac4c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xac51  endfinally
0xac52  ret
```
