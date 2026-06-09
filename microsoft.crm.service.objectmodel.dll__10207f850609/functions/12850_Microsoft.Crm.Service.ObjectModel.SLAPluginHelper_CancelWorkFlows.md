# Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::CancelWorkFlows

- ea: `0x12850`
- end: `0x1298b`
- name: `Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::CancelWorkFlows`
- size: `315`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x12350`
- `0x12fe0`

## callees

- `0x123a0`
- `0x12850`
- `0x13780`

## string_xrefs

- `0x128d7`: `completedon`

## pseudocode

```c

```

## disassembly

```asm
0x12850  ldarg.0
0x12851  brfalse  loc_12983
0x12856  ldarg.0
0x12857  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x1285c  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Count()
0x12861  ldc.i4.0
0x12862  ble      loc_12983
0x12867  ldnull
0x12868  stloc.0
0x12869  ldarg.0
0x1286a  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x1286f  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::GetEnumerator()
0x12874  stloc.1
0x12875  br       loc_12953
0x1287a  ldloc.1
0x1287b  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Current()
0x12880  stloc.2
0x12881  ldloc.2
0x12882  ldstr    aStatecode// "statecode"
0x12887  ldc.i4.3
0x12888  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::.ctor(int32)
0x1288d  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x12892  ldloc.2
0x12893  ldstr    aStatuscode// "statuscode"
0x12898  ldc.i4.s 0x20
0x1289a  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::.ctor(int32)
0x1289f  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x128a4  call     class [Microsoft.Crm]Microsoft.Crm.AsyncOperationTypeMetadataProvider [Microsoft.Crm]Microsoft.Crm.AsyncOperationTypeMetadataProvider::get_Instance()
0x128a9  ldc.i4.s 0xA
0x128ab  callvirt instance bool [Microsoft.Crm]Microsoft.Crm.AsyncOperationTypeMetadataProvider::CanClearDataWhenCompleted(int32)
0x128b0  brfalse.s loc_128BE
0x128b2  ldloc.2
0x128b3  ldstr    aData// "data"
0x128b8  ldnull
0x128b9  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x128be  ldloc.2
0x128bf  ldstr    aWorkflowstate// "workflowstate"
0x128c4  ldnull
0x128c5  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x128ca  ldloc.2
0x128cb  ldstr    aWorkflowisbloc// "workflowisblocked"
0x128d0  ldnull
0x128d1  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x128d6  ldloc.2
0x128d7  ldstr    aCompletedon// "completedon"
0x128dc  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x128e1  box      [mscorlib]System.DateTime
0x128e6  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x128eb  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AsyncOperationService::.ctor()
0x128f0  ldloc.2
0x128f1  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x128f6  ldstr    aAsyncoperation// "asyncoperationid"
0x128fb  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x12900  callvirt instance string [mscorlib]System.Object::ToString()
0x12905  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1290a  ldc.i4.s 0x20
0x1290c  ldarg.2
0x1290d  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x12912  castclass [Microsoft.Crm.Core]Microsoft.Crm.SqlExecutionContext
0x12917  callvirt instance void class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AsyncOperationServiceInternal`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.UpgradingOff>::RemoveDataForCompletedOperation(valuetype [mscorlib]System.Guid, int32, class [Microsoft.Crm.Core]Microsoft.Crm.SqlExecutionContext)
0x1291c  ldarg.1
0x1291d  ldloc.2
0x1291e  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Update(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity)
0x12923  ldloc.0
0x12924  ldstr    asc_2379E// "'"
0x12929  ldloc.2
0x1292a  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x1292f  ldstr    aWorkflowWorkfl// "Workflow.workflowid"
0x12934  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x12939  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AliasedValue
0x1293e  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AliasedValue::get_Value()
0x12943  callvirt instance string [mscorlib]System.Object::ToString()
0x12948  ldstr    asc_237CA// "',"
0x1294d  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x12952  stloc.0
0x12953  ldloc.1
0x12954  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x12959  brtrue   loc_1287A
0x1295e  leave.s  loc_1296A
0x12960  ldloc.1
0x12961  brfalse.s loc_12969
0x12963  ldloc.1
0x12964  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x12969  endfinally
0x1296a  ldarg.2
0x1296b  ldarg.3
0x1296c  ldloc.0
0x1296d  ldc.i4.1
0x1296e  newarr   [mscorlib]System.Char
0x12973  dup
0x12974  ldc.i4.0
0x12975  ldc.i4.s 0x2C
0x12977  stelem.i2
0x12978  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x1297d  call     bool Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::ClearCaseTimeStampedAttributes(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, valuetype [mscorlib]System.Guid incidentId, string workflowIds)
0x12982  pop
0x12983  ldarg.2
0x12984  ldarg.3
0x12985  call     void Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::UpdateSlaKpiInstanceStatus(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, valuetype [mscorlib]System.Guid incidentId)
0x1298a  ret
```
