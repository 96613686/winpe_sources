# Microsoft.Crm.Common.Application.Platform.Queue::Delete

- ea: `0x47a0`
- end: `0x47df`
- name: `Microsoft.Crm.Common.Application.Platform.Queue::Delete`
- size: `63`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x47a0`
- `0x47e0`

## string_xrefs

- `0x47ae`: `Cannot delete fax queue.`

## pseudocode

```c

```

## disassembly

```asm
0x47a0  ldarg.0
0x47a1  ldarg.0
0x47a2  call     instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Id()
0x47a7  call     instance bool Microsoft.Crm.Common.Application.Platform.Queue::IsFaxQueue(string id)
0x47ac  brfalse.s loc_47BE
0x47ae  ldstr    aCannotDeleteFa// "Cannot delete fax queue."
0x47b3  ldc.i4   0x80631107
0x47b8  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x47bd  throw
0x47be  ldstr    aQueue// "queue"
0x47c3  ldarg.0
0x47c4  call     instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Id()
0x47c9  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x47ce  ldarg.0
0x47cf  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_EntityType()
0x47d4  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_Context()
0x47d9  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Delete(string, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x47de  ret
```
