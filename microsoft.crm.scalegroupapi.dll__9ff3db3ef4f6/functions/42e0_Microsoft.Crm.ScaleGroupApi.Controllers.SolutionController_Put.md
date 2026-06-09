# Microsoft.Crm.ScaleGroupApi.Controllers.SolutionController::Put

- ea: `0x42e0`
- end: `0x448f`
- name: `Microsoft.Crm.ScaleGroupApi.Controllers.SolutionController::Put`
- size: `431`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0xe80`
- `0xeb0`
- `0x1850`
- `0x18d0`
- `0x18f0`
- `0x1950`
- `0x1970`
- `0x19d0`
- `0x3dd0`
- `0x42e0`
- `0x4a70`

## string_xrefs

- `0x4311`: `value.Initiator.DirectoryObjectId`
- `0x4378`: `No CrmUserId found for DirectoryObjectId : `

## pseudocode

```c

```

## disassembly

```asm
0x42e0  ldarg.1
0x42e1  ldstr    aOrganizationid// "organizationId"
0x42e6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x42eb  ldarg.2
0x42ec  ldstr    aValue// "value"
0x42f1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x42f6  ldarg.2
0x42f7  callvirt instance class Microsoft.Crm.ScaleGroupApi.Models.SGUserContext Microsoft.Crm.ScaleGroupApi.Models.SGSolution::get_Initiator()
0x42fc  ldstr    aValueInitiator// "value.Initiator"
0x4301  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x4306  ldarg.2
0x4307  callvirt instance class Microsoft.Crm.ScaleGroupApi.Models.SGUserContext Microsoft.Crm.ScaleGroupApi.Models.SGSolution::get_Initiator()
0x430c  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.ScaleGroupApi.Models.SGUserContext::get_DirectoryObjectId()
0x4311  ldstr    aValueInitiator_0// "value.Initiator.DirectoryObjectId"
0x4316  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x431b  ldarg.2
0x431c  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.ScaleGroupApi.Models.SGSolution::get_SolutionId()
0x4321  ldstr    aValueSolutioni// "value.SolutionId"
0x4326  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x432b  ldarg.2
0x432c  callvirt instance string Microsoft.Crm.ScaleGroupApi.Models.SGSolution::get_PackageUrl()
0x4331  ldstr    aValuePackageur// "value.PackageUrl"
0x4336  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x433b  ldarg.2
0x433c  callvirt instance string Microsoft.Crm.ScaleGroupApi.Models.SGSolution::get_UniqueName()
0x4341  ldstr    aValueUniquenam// "value.UniqueName"
0x4346  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x434b  ldarg.2
0x434c  callvirt instance string Microsoft.Crm.ScaleGroupApi.Models.SGSolution::get_Version()
0x4351  ldstr    aValueVersion// "value.Version"
0x4356  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x435b  ldarg.1
0x435c  ldarg.2
0x435d  callvirt instance class Microsoft.Crm.ScaleGroupApi.Models.SGUserContext Microsoft.Crm.ScaleGroupApi.Models.SGSolution::get_Initiator()
0x4362  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.ScaleGroupApi.Models.SGUserContext::get_DirectoryObjectId()
0x4367  call     valuetype [mscorlib]System.Guid Microsoft.Crm.ScaleGroupApi.Controllers.UserController::GetCrmUserId(valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid directoryObjectId)
0x436c  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x4371  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x4376  brfalse.s loc_43A1
0x4378  ldstr    aNoCrmuseridFou// "No CrmUserId found for DirectoryObjectI"...
0x437d  ldarg.2
0x437e  callvirt instance class Microsoft.Crm.ScaleGroupApi.Models.SGUserContext Microsoft.Crm.ScaleGroupApi.Models.SGSolution::get_Initiator()
0x4383  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.ScaleGroupApi.Models.SGUserContext::get_DirectoryObjectId()
0x4388  stloc.0
0x4389  ldloca.s 0
0x438b  constrained. [mscorlib]System.Guid
0x4391  callvirt instance string [mscorlib]System.Object::ToString()
0x4396  call     string [mscorlib]System.String::Concat(string, string)
0x439b  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x43a0  throw
0x43a1  ldarg.1
0x43a2  call     class Microsoft.Crm.ScaleGroupApi.OrganizationSdkProvider Microsoft.Crm.ScaleGroupApi.OrganizationSdkProvider::CreateInstance(valuetype [mscorlib]System.Guid orgId)
0x43a7  stloc.1
0x43a8  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor()
0x43ad  stloc.2
0x43ae  ldloc.2
0x43af  ldstr    aUniquename// "uniquename"
0x43b4  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::set_AttributeName(string)
0x43b9  ldloc.2
0x43ba  ldc.i4.0
0x43bb  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::set_Operator(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator)
0x43c0  ldloc.2
0x43c1  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<object> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::get_Values()
0x43c6  ldarg.2
0x43c7  callvirt instance string Microsoft.Crm.ScaleGroupApi.Models.SGSolution::get_UniqueName()
0x43cc  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<object>::Add(var<u1>)
0x43d1  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor()
0x43d6  stloc.3
0x43d7  ldloc.3
0x43d8  ldstr    aVersion// "version"
0x43dd  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::set_AttributeName(string)
0x43e2  ldloc.3
0x43e3  ldc.i4.3
0x43e4  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::set_Operator(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator)
0x43e9  ldloc.3
0x43ea  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<object> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::get_Values()
0x43ef  ldarg.2
0x43f0  callvirt instance string Microsoft.Crm.ScaleGroupApi.Models.SGSolution::get_Version()
0x43f5  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<object>::Add(var<u1>)
0x43fa  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::.ctor()
0x43ff  stloc.s  4
0x4401  ldloc.s  4
0x4403  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::get_Conditions()
0x4408  ldloc.2
0x4409  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression>::Add(var<u1>)
0x440e  ldloc.s  4
0x4410  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::get_Conditions()
0x4415  ldloc.3
0x4416  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression>::Add(var<u1>)
0x441b  ldloc.s  4
0x441d  ldc.i4.0
0x441e  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::set_FilterOperator(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LogicalOperator)
0x4423  ldstr    aSolution_0// "solution"
0x4428  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::.ctor(string)
0x442d  stloc.s  5
0x442f  ldloc.s  5
0x4431  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_ColumnSet()
0x4436  ldc.i4.1
0x4437  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::set_AllColumns(bool)
0x443c  ldloc.s  5
0x443e  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0x4443  ldloc.s  4
0x4445  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::AddFilter(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression)
0x444a  ldloc.1
0x444b  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.ScaleGroupApi.OrganizationSdkProvider::get_Sdk()
0x4450  ldloc.s  5
0x4452  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::RetrieveMultiple(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryBase)
0x4457  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x445c  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Count()
0x4461  brtrue.s loc_4479
0x4463  ldstr    aNoSolutionFoun// "No solution found for Upgrade: "
0x4468  ldarg.2
0x4469  callvirt instance string Microsoft.Crm.ScaleGroupApi.Models.SGSolution::get_UniqueName()
0x446e  call     string [mscorlib]System.String::Concat(string, string)
0x4473  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x4478  throw
0x4479  leave.s  loc_4485
0x447b  ldloc.1
0x447c  brfalse.s loc_4484
0x447e  ldloc.1
0x447f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4484  endfinally
0x4485  ldarg.0
0x4486  ldarg.1
0x4487  ldarg.2
0x4488  call     instance string Microsoft.Crm.ScaleGroupApi.Controllers.SolutionController::Post(valuetype [mscorlib]System.Guid organizationId, class Microsoft.Crm.ScaleGroupApi.Models.SGSolution value)
0x448d  pop
0x448e  ret
```
