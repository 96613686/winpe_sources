# Microsoft.Crm.Common.Application.Platform.List::RetrieveListMemberType

- ea: `0x42c0`
- end: `0x4323`
- name: `Microsoft.Crm.Common.Application.Platform.List::RetrieveListMemberType`
- size: `99`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x42c0`

## string_xrefs

- `0x42c8`: `createdfromcode`
- `0x42f1`: `createdfromcode`

## pseudocode

```c

```

## disassembly

```asm
0x42c0  ldc.i4.1
0x42c1  newarr   [mscorlib]System.String
0x42c6  dup
0x42c7  ldc.i4.0
0x42c8  ldstr    aCreatedfromcod// "createdfromcode"
0x42cd  stelem.ref
0x42ce  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSet::.ctor(string[])
0x42d3  stloc.0
0x42d4  ldarg.0
0x42d5  call     instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::get_EntityName()
0x42da  ldarg.1
0x42db  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x42e0  ldloc.0
0x42e1  ldarg.0
0x42e2  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_EntityType()
0x42e7  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_Context()
0x42ec  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Retrieve(string, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x42f1  ldstr    aCreatedfromcod// "createdfromcode"
0x42f6  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x42fb  unbox.any [mscorlib]System.Int32
0x4300  stloc.1
0x4301  ldloc.1
0x4302  ldc.i4.1
0x4303  sub
0x4304  switch   loc_431B, loc_431D, loc_4321, loc_431F
0x4319  br.s     loc_4321
0x431b  ldc.i4.1
0x431c  ret
0x431d  ldc.i4.2
0x431e  ret
0x431f  ldc.i4.4
0x4320  ret
0x4321  ldc.i4.0
0x4322  ret
```
