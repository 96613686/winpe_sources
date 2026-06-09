# Microsoft.Crm.Asynchronous.UpdateKnowledgeArticleStatesOperation::PublishKnowledgeArticles

- ea: `0xac60`
- end: `0xae5f`
- name: `Microsoft.Crm.Asynchronous.UpdateKnowledgeArticleStatesOperation::PublishKnowledgeArticles`
- size: `511`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0xa7b0`

## callees

- `0xac60`
- `0xaea0`

## string_xrefs

- `0xac8d`: `publishstatusid`
- `0xad8e`: `publishstatusid`
- `0xada7`: `publishstatusid`
- `0xae15`: `Error in AsyncHandler::UpdateKnowledgeArticleStatesOperation::PublishKnowledgeArticles() for knowledgearticleid {0} - {1}`

## pseudocode

```c

```

## disassembly

```asm
0xac60  ldarg.0
0xac61  call     instance bool Microsoft.Crm.Asynchronous.UpdateKnowledgeArticleStatesOperation::HasJobBeenAbortedOrPaused()
0xac66  brtrue   loc_AE5E
0xac6b  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::.ctor()
0xac70  stloc.0
0xac71  ldloc.0
0xac72  ldstr    aKnowledgeartic// "knowledgearticle"
0xac77  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::set_EntityName(string)
0xac7c  ldloc.0
0xac7d  ldc.i4.2
0xac7e  newarr   [mscorlib]System.String
0xac83  dup
0xac84  ldc.i4.0
0xac85  ldstr    aKnowledgeartic_0// "knowledgearticleid"
0xac8a  stelem.ref
0xac8b  dup
0xac8c  ldc.i4.1
0xac8d  ldstr    aPublishstatusi// "publishstatusid"
0xac92  stelem.ref
0xac93  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::.ctor(string[])
0xac98  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::set_ColumnSet(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet)
0xac9d  ldloc.0
0xac9e  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::.ctor()
0xaca3  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::set_Criteria(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression)
0xaca8  ldloc.0
0xaca9  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0xacae  ldc.i4.0
0xacaf  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::set_FilterOperator(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LogicalOperator)
0xacb4  ldloc.0
0xacb5  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0xacba  ldstr    aStatecode// "statecode"
0xacbf  ldc.i4.0
0xacc0  ldc.i4.2
0xacc1  box      [mscorlib]System.Int32
0xacc6  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0xaccb  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::AddCondition(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression)
0xacd0  ldloc.0
0xacd1  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0xacd6  ldstr    aPublishon// "publishon"
0xacdb  ldc.i4.s 0xD
0xacdd  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator)
0xace2  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::AddCondition(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression)
0xace7  ldloc.0
0xace8  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0xaced  ldstr    aPublishon// "publishon"
0xacf2  ldc.i4.5
0xacf3  ldarg.0
0xacf4  ldfld    valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.UpdateKnowledgeArticleStatesOperation::_now
0xacf9  call     class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime::FromUniversal(valuetype [mscorlib]System.DateTime)
0xacfe  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime::get_Value()
0xad03  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0xad08  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::AddCondition(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression)
0xad0d  ldarg.0
0xad0e  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Asynchronous.UpdateKnowledgeArticleStatesOperation::_sdkService
0xad13  ldloc.0
0xad14  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::RetrieveMultiple(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryBase)
0xad19  stloc.1
0xad1a  ldloc.1
0xad1b  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0xad20  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Count()
0xad25  ldc.i4.0
0xad26  ble      loc_AE5E
0xad2b  ldloc.1
0xad2c  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0xad31  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::GetEnumerator()
0xad36  stloc.2
0xad37  br       loc_AE47
0xad3c  ldloc.2
0xad3d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Current()
0xad42  stloc.3
0xad43  ldarg.0
0xad44  call     instance bool Microsoft.Crm.Asynchronous.UpdateKnowledgeArticleStatesOperation::HasJobBeenAbortedOrPaused()
0xad49  brtrue   loc_AE52
0xad4e  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.UpdateRequest::.ctor()
0xad53  stloc.s  4
0xad55  ldstr    aKnowledgeartic// "knowledgearticle"
0xad5a  ldloc.3
0xad5b  ldstr    aKnowledgeartic_0// "knowledgearticleid"
0xad60  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0xad65  unbox.any [mscorlib]System.Guid
0xad6a  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string, valuetype [mscorlib]System.Guid)
0xad6f  stloc.s  5
0xad71  ldloc.s  5
0xad73  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0xad78  ldstr    aStatecode// "statecode"
0xad7d  ldc.i4.3
0xad7e  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::.ctor(int32)
0xad83  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Add(var<u1>, !!T0)
0xad88  ldloc.3
0xad89  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0xad8e  ldstr    aPublishstatusi// "publishstatusid"
0xad93  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::ContainsKey(var<u1>)
0xad98  brfalse.s loc_ADC2
0xad9a  ldloc.s  5
0xad9c  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0xada1  ldstr    aStatuscode// "statuscode"
0xada6  ldloc.3
0xada7  ldstr    aPublishstatusi// "publishstatusid"
0xadac  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0xadb1  unbox.any [mscorlib]System.Int32
0xadb6  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::.ctor(int32)
0xadbb  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Add(var<u1>, !!T0)
0xadc0  br.s     loc_ADD9
0xadc2  ldloc.s  5
0xadc4  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0xadc9  ldstr    aStatuscode// "statuscode"
0xadce  ldc.i4.m1
0xadcf  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::.ctor(int32)
0xadd4  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Add(var<u1>, !!T0)
0xadd9  ldloc.s  5
0xaddb  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0xade0  ldstr    aPublishon// "publishon"
0xade5  ldnull
0xade6  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Add(var<u1>, !!T0)
0xadeb  ldloc.s  4
0xaded  ldloc.s  5
0xadef  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.UpdateRequest::set_Target(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity)
0xadf4  ldarg.0
0xadf5  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Asynchronous.UpdateKnowledgeArticleStatesOperation::_sdkService
0xadfa  ldloc.s  4
0xadfc  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0xae01  pop
0xae02  leave.s  loc_AE47
0xae04  stloc.s  6
0xae06  ldloc.s  6
0xae08  ldarg.0
0xae09  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.UpdateKnowledgeArticleStatesOperation::_asyncEvent
0xae0e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0xae13  ldc.i4.s 0x15
0xae15  ldstr    aErrorInAsyncha_5// "Error in AsyncHandler::UpdateKnowledgeA"...
0xae1a  ldc.i4.2
0xae1b  newarr   [mscorlib]System.Object
0xae20  dup
0xae21  ldc.i4.0
0xae22  ldloc.s  5
0xae24  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0xae29  box      [mscorlib]System.Guid
0xae2e  stelem.ref
0xae2f  dup
0xae30  ldc.i4.1
0xae31  ldloc.s  6
0xae33  callvirt instance string [mscorlib]System.Exception::get_Message()
0xae38  stelem.ref
0xae39  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xae3e  ldarg.0
0xae3f  ldc.i4.1
0xae40  stfld    bool Microsoft.Crm.Asynchronous.UpdateKnowledgeArticleStatesOperation::_errorOccured
0xae45  leave.s  loc_AE47
0xae47  ldloc.2
0xae48  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xae4d  brtrue   loc_AD3C
0xae52  leave.s  loc_AE5E
0xae54  ldloc.2
0xae55  brfalse.s loc_AE5D
0xae57  ldloc.2
0xae58  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xae5d  endfinally
0xae5e  ret
```
