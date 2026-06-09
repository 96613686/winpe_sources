# Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::IsSLAStateActive

- ea: `0xcdb0`
- end: `0xcde0`
- name: `Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::IsSLAStateActive`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0xcb80`

## callees

- `0xcdb0`

## pseudocode

```c

```

## disassembly

```asm
0xcdb0  ldarg.1
0xcdb1  brfalse.s loc_CDDE
0xcdb3  ldarg.1
0xcdb4  ldstr    aStatecode// "statecode"
0xcdb9  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xcdbe  brfalse.s loc_CDDE
0xcdc0  ldarg.1
0xcdc1  ldstr    aStatecode// "statecode"
0xcdc6  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xcdcb  callvirt instance string [mscorlib]System.Object::ToString()
0xcdd0  ldstr    aActive// "Active"
0xcdd5  call     bool [mscorlib]System.String::op_Equality(string, string)
0xcdda  brfalse.s loc_CDDE
0xcddc  ldc.i4.1
0xcddd  ret
0xcdde  ldc.i4.0
0xcddf  ret
```
