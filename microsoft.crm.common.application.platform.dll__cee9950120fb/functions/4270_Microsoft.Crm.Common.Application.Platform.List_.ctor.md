# Microsoft.Crm.Common.Application.Platform.List::.ctor

- ea: `0x4270`
- end: `0x42bc`
- name: `Microsoft.Crm.Common.Application.Platform.List::.ctor`
- size: `76`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x2c70`

## string_xrefs

- `0x428e`: `createdfromcode`

## pseudocode

```c

```

## disassembly

```asm
0x4270  ldarg.0
0x4271  ldarg.1
0x4272  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x4277  ldarg.0
0x4278  call     instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::get_RequiredColumns()
0x427d  ldstr    aStatecode// "statecode"
0x4282  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x4287  pop
0x4288  ldarg.0
0x4289  call     instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::get_RequiredColumns()
0x428e  ldstr    aCreatedfromcod// "createdfromcode"
0x4293  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x4298  pop
0x4299  ldarg.0
0x429a  call     instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::get_RequiredColumns()
0x429f  ldstr    aType// "type"
0x42a4  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x42a9  pop
0x42aa  ldarg.0
0x42ab  call     instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::get_RequiredColumns()
0x42b0  ldstr    aLockstatus// "lockstatus"
0x42b5  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x42ba  pop
0x42bb  ret
```
