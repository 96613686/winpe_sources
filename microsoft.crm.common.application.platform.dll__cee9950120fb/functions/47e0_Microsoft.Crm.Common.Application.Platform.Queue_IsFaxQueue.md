# Microsoft.Crm.Common.Application.Platform.Queue::IsFaxQueue

- ea: `0x47e0`
- end: `0x482a`
- name: `Microsoft.Crm.Common.Application.Platform.Queue::IsFaxQueue`
- size: `74`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x47a0`

## callees

- `0x47e0`

## pseudocode

```c

```

## disassembly

```asm
0x47e0  ldloca.s 0
0x47e2  ldarg.1
0x47e3  call     instance void [mscorlib]System.Guid::.ctor(string)
0x47e8  ldc.i4.1
0x47e9  newarr   [mscorlib]System.String
0x47ee  dup
0x47ef  ldc.i4.0
0x47f0  ldstr    aIsfaxqueue// "isfaxqueue"
0x47f5  stelem.ref
0x47f6  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSet::.ctor(string[])
0x47fb  stloc.1
0x47fc  ldstr    aQueue// "queue"
0x4801  ldloc.0
0x4802  ldloc.1
0x4803  ldarg.0
0x4804  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_EntityType()
0x4809  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_Context()
0x480e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Retrieve(string, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x4813  ldstr    aIsfaxqueue// "isfaxqueue"
0x4818  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x481d  stloc.2
0x481e  ldloc.2
0x481f  brfalse.s loc_4828
0x4821  ldloc.2
0x4822  unbox.any [mscorlib]System.Boolean
0x4827  ret
0x4828  ldc.i4.0
0x4829  ret
```
