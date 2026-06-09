# Microsoft.Crm.Service.ObjectModel.IncidentService::CloseIncidentWithContract

- ea: `0x2c00`
- end: `0x2cf0`
- name: `Microsoft.Crm.Service.ObjectModel.IncidentService::CloseIncidentWithContract`
- size: `240`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1980`

## callees

- `0x20d0`
- `0x2200`
- `0x2c00`
- `0x2cf0`
- `0x2e10`
- `0x2eb0`
- `0x3630`

## pseudocode

```c

```

## disassembly

```asm
0x2c00  ldarg.1
0x2c01  ldstr    aIncidentid// "incidentid"
0x2c06  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2c0b  unbox.any [mscorlib]System.Guid
0x2c10  ldarg.1
0x2c11  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Metadata()
0x2c16  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x2c1b  ldarg.s  4
0x2c1d  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2c22  stloc.0
0x2c23  ldarg.1
0x2c24  ldstr    aContractid// "contractid"
0x2c29  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2c2e  unbox.any [mscorlib]System.Guid
0x2c33  ldstr    aContract// "Contract"
0x2c38  ldarg.s  4
0x2c3a  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2c3f  stloc.1
0x2c40  newobj   instance void Microsoft.Crm.Service.ObjectModel.ContractService::.ctor()
0x2c45  stloc.2
0x2c46  ldc.i4.1
0x2c47  newarr   [mscorlib]System.String
0x2c4c  dup
0x2c4d  ldc.i4.0
0x2c4e  ldstr    aAllotmenttypec// "allotmenttypecode"
0x2c53  stelem.ref
0x2c54  stloc.3
0x2c55  ldstr    aContract// "Contract"
0x2c5a  ldarg.s  4
0x2c5c  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x2c61  stloc.s  4
0x2c63  ldloc.s  4
0x2c65  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x2c6a  ldloc.3
0x2c6b  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x2c70  ldnull
0x2c71  stloc.s  5
0x2c73  ldarg.s  4
0x2c75  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SystemUserContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x2c7a  stloc.s  7
0x2c7c  ldloc.2
0x2c7d  ldloc.1
0x2c7e  ldloc.s  4
0x2c80  ldarg.s  4
0x2c82  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Retrieve(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x2c87  castclass [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.Contract
0x2c8c  stloc.s  5
0x2c8e  leave.s  loc_2C9C
0x2c90  ldloc.s  7
0x2c92  brfalse.s loc_2C9B
0x2c94  ldloc.s  7
0x2c96  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2c9b  endfinally
0x2c9c  ldc.i4.0
0x2c9d  stloc.s  6
0x2c9f  ldarg.0
0x2ca0  ldarg.1
0x2ca1  ldarg.2
0x2ca2  ldloc.s  5
0x2ca4  ldarg.s  4
0x2ca6  call     instance int32 Microsoft.Crm.Service.ObjectModel.IncidentService::CalculateAllotmentToDecrement(class [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.Incident incident, class [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.IncidentResolution incidentResolution, class [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.Contract contract, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x2cab  stloc.s  6
0x2cad  ldloc.s  6
0x2caf  brfalse.s loc_2CCB
0x2cb1  ldarg.0
0x2cb2  ldarg.1
0x2cb3  ldstr    aContractdetail// "contractdetailid"
0x2cb8  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2cbd  unbox.any [mscorlib]System.Guid
0x2cc2  ldloc.s  6
0x2cc4  ldarg.s  4
0x2cc6  call     instance void Microsoft.Crm.Service.ObjectModel.IncidentService::DecrementAllotment(valuetype [mscorlib]System.Guid contractDetailId, int32 requestedAllotment, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x2ccb  ldarg.0
0x2ccc  ldarg.2
0x2ccd  ldarg.s  4
0x2ccf  call     instance void Microsoft.Crm.Service.ObjectModel.IncidentService::CreateIncidentResolutionActivity(class [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.IncidentResolution incidentResolution, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x2cd4  ldarg.0
0x2cd5  ldloc.0
0x2cd6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x2cdb  ldc.i4.1
0x2cdc  ldarg.s  4
0x2cde  call     instance void Microsoft.Crm.Service.ObjectModel.IncidentService::BillIncidentResolutionActivities(valuetype [mscorlib]System.Guid incidentId, int32 activityState, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x2ce3  ldarg.0
0x2ce4  ldloc.0
0x2ce5  ldc.i4.1
0x2ce6  ldarg.3
0x2ce7  ldarg.s  4
0x2ce9  call     instance bool Microsoft.Crm.Service.ObjectModel.IncidentService::SetStateInternal(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker moniker, int32 newState, int32 newStatusCode, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x2cee  pop
0x2cef  ret
```
