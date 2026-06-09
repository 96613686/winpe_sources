# Microsoft.Crm.Asynchronous.ResourceBookingSyncService::GetIdMappingsForBookableResourceBooking

- ea: `0x8730`
- end: `0x8775`
- name: `Microsoft.Crm.Asynchronous.ResourceBookingSyncService::GetIdMappingsForBookableResourceBooking`
- size: `69`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x83a0`
- `0x8600`

## callees

- `0x8a90`
- `0x142c0`
- `0x151b0`
- `0x16260`
- `0x16390`
- `0x163e0`

## pseudocode

```c

```

## disassembly

```asm
0x8730  ldarg.0
0x8731  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x8736  ldstr    aMethodgetidmap// "MethodGetIdMappingsForBookableResourceB"...
0x873b  callvirt instance void Metrics::StartTimer(string name)
0x8740  ldarg.0
0x8741  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x8746  ldstr    aMethodgetidmap_0// "MethodGetIdMappingsForBookableResourceB"...
0x874b  ldc.i4.1
0x874c  callvirt instance int32 Metrics::IncrementValue(string name, int32 increment)
0x8751  pop
0x8752  ldarg.0
0x8753  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Asynchronous.ResourceBookingSyncService::get_SystemService()
0x8758  ldarg.1
0x8759  ldarg.2
0x875a  newobj   instance void IdMappingForBookableResourceQuery::.ctor(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService service, valuetype [mscorlib]System.Guid bookableResourceBookingId, bool includeDeletedInExchange)
0x875f  call     instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> NonPagedQuery::Next()
0x8764  ldarg.0
0x8765  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x876a  ldstr    aMethodgetidmap// "MethodGetIdMappingsForBookableResourceB"...
0x876f  callvirt instance void Metrics::StopTimer(string name)
0x8774  ret
```
