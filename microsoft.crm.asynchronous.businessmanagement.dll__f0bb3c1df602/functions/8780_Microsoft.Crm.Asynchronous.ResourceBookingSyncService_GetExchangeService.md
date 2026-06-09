# Microsoft.Crm.Asynchronous.ResourceBookingSyncService::GetExchangeService

- ea: `0x8780`
- end: `0x8831`
- name: `Microsoft.Crm.Asynchronous.ResourceBookingSyncService::GetExchangeService`
- size: `177`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x62c0`
- `0x74e0`

## callees

- `0x8780`
- `0x8ab0`
- `0x8af0`
- `0x14020`
- `0x15300`
- `0x15330`
- `0x16260`
- `0x16270`
- `0x16390`
- `0x163e0`
- `0x17930`

## string_xrefs

- `0x8786`: `MethodGetExchangeServiceCallCount`
- `0x87c0`: `MethodGetExchangeService`
- `0x8805`: `MethodGetExchangeService`

## pseudocode

```c

```

## disassembly

```asm
0x8780  ldarg.0
0x8781  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x8786  ldstr    aMethodgetexcha// "MethodGetExchangeServiceCallCount"
0x878b  ldc.i4.1
0x878c  callvirt instance int32 Metrics::IncrementValue(string name, int32 increment)
0x8791  pop
0x8792  ldarg.1
0x8793  ldarg.2
0x8794  callvirt instance class CacheData BookableResourceCache::GetByUserId(valuetype [mscorlib]System.Guid userId)
0x8799  stloc.0
0x879a  ldloc.0
0x879b  brtrue.s loc_87A4
0x879d  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x87a2  br.s     loc_87AA
0x87a4  ldloc.0
0x87a5  callvirt instance valuetype [mscorlib]System.Guid CacheData::get_MailboxId()
0x87aa  stloc.1
0x87ab  ldnull
0x87ac  stloc.2
0x87ad  ldloc.1
0x87ae  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x87b3  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x87b8  brfalse.s loc_882F
0x87ba  ldarg.0
0x87bb  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x87c0  ldstr    aMethodgetexcha_0// "MethodGetExchangeService"
0x87c5  callvirt instance void Metrics::StartTimer(string name)
0x87ca  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ExchangeServiceFactory::.ctor()
0x87cf  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ResourceBookingSyncService::get_OrganizationId()
0x87d4  newobj   instance void OrganizationServiceProvider::.ctor(valuetype [mscorlib]System.Guid organizationId)
0x87d9  ldarg.0
0x87da  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Asynchronous.ResourceBookingSyncService::get_Context()
0x87df  ldloc.1
0x87e0  callvirt instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExchangeService [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ExchangeServiceFactory::Create(class [Microsoft.Crm.ExchangeProxy]Microsoft.Crm.ExchangeProxy.IOrganizationServiceProvider, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, valuetype [mscorlib]System.Guid)
0x87e5  stloc.2
0x87e6  leave.s  loc_882F
0x87e8  pop
0x87e9  ldarg.0
0x87ea  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x87ef  ldstr    aNumberofusersw// "NumberOfUsersWithMailboxExceptions"
0x87f4  ldc.i4.1
0x87f5  ldc.i4.s 0xA
0x87f7  callvirt instance int32 Metrics::IncrementValue(string name, int32 increment, int32 traceInterval)
0x87fc  pop
0x87fd  leave.s  loc_882F
0x87ff  ldarg.0
0x8800  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x8805  ldstr    aMethodgetexcha_0// "MethodGetExchangeService"
0x880a  callvirt instance void Metrics::StopTimer(string name)
0x880f  ldloc.2
0x8810  brtrue.s loc_882E
0x8812  ldarg.1
0x8813  ldarg.2
0x8814  callvirt instance bool BookableResourceCache::RemoveByUserId(valuetype [mscorlib]System.Guid userId)
0x8819  pop
0x881a  ldarg.0
0x881b  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x8820  ldstr    aNumberofusersw_0// "NumberOfUsersWithInvalidMailbox"
0x8825  ldc.i4.1
0x8826  ldc.i4.s 0x32
0x8828  callvirt instance int32 Metrics::IncrementValue(string name, int32 increment, int32 traceInterval)
0x882d  pop
0x882e  endfinally
0x882f  ldloc.2
0x8830  ret
```
