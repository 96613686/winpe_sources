# Microsoft.Crm.Caching.MailboxWebServiceCacheLoader::LoadCacheData_0

- ea: `0x13680`
- end: `0x136e3`
- name: `Microsoft.Crm.Caching.MailboxWebServiceCacheLoader::LoadCacheData_0`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x13670`

## callees

- `0x127e0`
- `0x59e30`

## string_xrefs

- `0x1369d`: `emailrouteraccessapproval`
- `0x136b3`: `incomingemailstatus`

## pseudocode

```c

```

## disassembly

```asm
0x13680  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::.ctor()
0x13685  stloc.0
0x13686  ldloc.0
0x13687  ldstr    aActdeliverymet// "actdeliverymethod"
0x1368c  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::AddColumn(string)
0x13691  ldloc.0
0x13692  ldstr    aStatecode// "statecode"
0x13697  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::AddColumn(string)
0x1369c  ldloc.0
0x1369d  ldstr    aEmailrouteracc// "emailrouteraccessapproval"
0x136a2  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::AddColumn(string)
0x136a7  ldloc.0
0x136a8  ldstr    aActstatus// "actstatus"
0x136ad  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::AddColumn(string)
0x136b2  ldloc.0
0x136b3  ldstr    aIncomingemails// "incomingemailstatus"
0x136b8  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::AddColumn(string)
0x136bd  ldstr    aMailbox// "mailbox"
0x136c2  ldarg.1
0x136c3  ldloc.0
0x136c4  ldarg.2
0x136c5  call     class Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Platform.DataSource::Retrieve(string entityName, valuetype [mscorlib]System.Guid entityId, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet columnSet, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x136ca  newobj   instance void Microsoft.Crm.Caching.CacheApplicationEntityWrapper::.ctor(class Microsoft.Crm.Application.Platform.Entity entity)
0x136cf  stloc.1
0x136d0  ldarg.2
0x136d1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x136d6  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.MailboxCacheData::.ctor(valuetype [mscorlib]System.Guid)
0x136db  dup
0x136dc  ldloc.1
0x136dd  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.MailboxCacheData::Initialize(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ICacheEntityWrapper)
0x136e2  ret
```
