# Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::ShouldUseSLAKPI

- ea: `0xccc0`
- end: `0xcce3`
- name: `Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::ShouldUseSLAKPI`
- size: `35`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0xcb80`

## callees

- `0xccc0`

## pseudocode

```c

```

## disassembly

```asm
0xccc0  ldarg.1
0xccc1  ldstr    aSlatype// "slatype"
0xccc6  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::HasAttribute(string)
0xcccb  brfalse.s loc_CCE1
0xcccd  ldarg.1
0xccce  ldstr    aSlatype// "slatype"
0xccd3  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xccd8  unbox.any [mscorlib]System.Int32
0xccdd  ldc.i4.1
0xccde  ceq
0xcce0  ret
0xcce1  ldc.i4.0
0xcce2  ret
```
