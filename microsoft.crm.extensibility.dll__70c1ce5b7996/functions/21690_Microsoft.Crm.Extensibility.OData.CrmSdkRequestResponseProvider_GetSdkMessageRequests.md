# Microsoft.Crm.Extensibility.OData.CrmSdkRequestResponseProvider::GetSdkMessageRequests

- ea: `0x21690`
- end: `0x21854`
- name: `Microsoft.Crm.Extensibility.OData.CrmSdkRequestResponseProvider::GetSdkMessageRequests`
- size: `452`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1a480`
- `0x215c0`

## callees

- `0x21690`
- `0x24aa0`
- `0x24ec0`
- `0x24ed0`

## string_xrefs

- `0x2171f`: `template`

## pseudocode

```c

```

## disassembly

```asm
0x21690  ldnull
0x21691  stloc.0
0x21692  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::CreateCrmExecutionContext()
0x21697  stloc.1
0x21698  ldloc.1
0x21699  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Extensibility.OData.OrganizationServiceFactory::GetCurrentUserId()
0x2169e  ldc.i4.0
0x2169f  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnBeginRequest(valuetype [mscorlib]System.Guid, bool)
0x216a4  ldstr    aSdkmessagerequ_0// "SdkMessageRequest"
0x216a9  ldloc.1
0x216aa  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x216af  stloc.2
0x216b0  ldloc.2
0x216b1  ldc.i4.1
0x216b2  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::set_Distinct(bool)
0x216b7  ldloc.2
0x216b8  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x216bd  ldc.i4.2
0x216be  newarr   [mscorlib]System.String
0x216c3  dup
0x216c4  ldc.i4.0
0x216c5  ldstr    aSdkmessagerequ// "sdkmessagerequestid"
0x216ca  stelem.ref
0x216cb  dup
0x216cc  ldc.i4.1
0x216cd  ldstr    aName// "name"
0x216d2  stelem.ref
0x216d3  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x216d8  ldloc.2
0x216d9  ldstr    aSdkmessagepair// "SdkMessagePair"
0x216de  ldstr    aSdkmessagepair_0// "sdkmessagepairid"
0x216e3  ldstr    aSdkmessagepair_0// "sdkmessagepairid"
0x216e8  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::AddLinkEntity(string, string, string)
0x216ed  dup
0x216ee  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::get_LinkCriteria()
0x216f3  ldstr    aEndpoint// "endpoint"
0x216f8  ldc.i4.0
0x216f9  ldstr    aApiData_0// "api/data"
0x216fe  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x21703  pop
0x21704  ldstr    aSdkmessage// "SdkMessage"
0x21709  ldstr    aSdkmessageid// "sdkmessageid"
0x2170e  ldstr    aSdkmessageid// "sdkmessageid"
0x21713  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::AddLinkEntity(string, string, string)
0x21718  stloc.3
0x21719  ldloc.3
0x2171a  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::get_LinkCriteria()
0x2171f  ldstr    aTemplate// "template"
0x21724  ldc.i4.0
0x21725  ldc.i4.0
0x21726  box      [mscorlib]System.Boolean
0x2172b  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x21730  pop
0x21731  ldloc.1
0x21732  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x21737  call     class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.SolutionHelper::GetSystemAndInternalSystemConvertedSolutionIds(class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext)
0x2173c  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::ToArray()
0x21741  stloc.s  4
0x21743  ldloc.1
0x21744  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x21749  call     class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.SolutionHelper::GetInternalSystemConvertedSolutionIds(class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext)
0x2174e  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::ToArray()
0x21753  stloc.s  5
0x21755  ldarga.s 0
0x21757  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.CustomizationLevel>::get_HasValue()
0x2175c  brfalse  loc_2180E
0x21761  ldarg.0
0x21762  stloc.s  7
0x21764  ldc.i4.0
0x21765  stloc.s  8
0x21767  ldloca.s 7
0x21769  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.CustomizationLevel>::GetValueOrDefault()
0x2176e  ldloc.s  8
0x21770  ceq
0x21772  ldloca.s 7
0x21774  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.CustomizationLevel>::get_HasValue()
0x21779  and
0x2177a  brfalse.s loc_217B2
0x2177c  ldloc.3
0x2177d  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::get_LinkCriteria()
0x21782  ldstr    aSolutionid// "solutionid"
0x21787  ldc.i4.0
0x21788  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::SystemSolutionId
0x2178d  box      [mscorlib]System.Guid
0x21792  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x21797  pop
0x21798  ldloc.3
0x21799  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::get_LinkCriteria()
0x2179e  ldstr    aIsactive// "isactive"
0x217a3  ldc.i4.1
0x217a4  ldc.i4.0
0x217a5  box      [mscorlib]System.Boolean
0x217aa  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x217af  pop
0x217b0  br.s     loc_2180E
0x217b2  ldloc.3
0x217b3  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::get_LinkCriteria()
0x217b8  ldc.i4.1
0x217b9  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddFilter(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LogicalOperator)
0x217be  dup
0x217bf  ldc.i4.0
0x217c0  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddFilter(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LogicalOperator)
0x217c5  dup
0x217c6  ldstr    aSolutionid// "solutionid"
0x217cb  ldc.i4.s 9
0x217cd  ldloc.s  4
0x217cf  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, class [mscorlib]System.Array)
0x217d4  pop
0x217d5  ldstr    aIsactive// "isactive"
0x217da  ldc.i4.0
0x217db  ldc.i4.1
0x217dc  box      [mscorlib]System.Boolean
0x217e1  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x217e6  pop
0x217e7  ldc.i4.0
0x217e8  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddFilter(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LogicalOperator)
0x217ed  dup
0x217ee  ldstr    aSolutionid// "solutionid"
0x217f3  ldc.i4.8
0x217f4  ldloc.s  5
0x217f6  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, class [mscorlib]System.Array)
0x217fb  pop
0x217fc  ldstr    aIsactive// "isactive"
0x21801  ldc.i4.1
0x21802  ldc.i4.0
0x21803  box      [mscorlib]System.Boolean
0x21808  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x2180d  pop
0x2180e  ldstr    aSdkmessagerequ_0// "SdkMessageRequest"
0x21813  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Extensibility.OData.OrganizationServiceFactory::GetOrganizationId()
0x21818  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ServiceClassFactory::CreateInstance(string, valuetype [mscorlib]System.Guid)
0x2181d  stloc.s  6
0x2181f  ldloc.1
0x21820  ldc.i4.0
0x21821  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SystemUserContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, bool)
0x21826  stloc.s  9
0x21828  ldloc.s  6
0x2182a  ldloc.2
0x2182b  ldloc.1
0x2182c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x21831  stloc.0
0x21832  leave.s  loc_21840
0x21834  ldloc.s  9
0x21836  brfalse.s loc_2183F
0x21838  ldloc.s  9
0x2183a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2183f  endfinally
0x21840  ldloc.1
0x21841  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnEndRequest()
0x21846  leave.s  loc_21852
0x21848  ldloc.1
0x21849  brfalse.s loc_21851
0x2184b  ldloc.1
0x2184c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x21851  endfinally
0x21852  ldloc.0
0x21853  ret
```
