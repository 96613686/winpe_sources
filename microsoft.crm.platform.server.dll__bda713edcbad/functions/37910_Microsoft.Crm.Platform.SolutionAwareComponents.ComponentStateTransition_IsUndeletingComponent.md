# Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::IsUndeletingComponent

- ea: `0x37910`
- end: `0x3793d`
- name: `Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransition::IsUndeletingComponent`
- size: `45`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x3dd90`
- `0x3e4e0`

## callees

- `0x37910`
- `0x66ff0`

## string_xrefs

- `0x37916`: `originatesfromundelete`
- `0x37928`: `originatesfromundelete`

## pseudocode

```c

```

## disassembly

```asm
0x37910  ldarg.1
0x37911  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.BusinessEntities.ExecutionContext::get_InternalContextVariables()
0x37916  ldstr    aOriginatesfrom// "originatesfromundelete"
0x3791b  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x37920  brfalse.s loc_3793B
0x37922  ldarg.1
0x37923  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.BusinessEntities.ExecutionContext::get_InternalContextVariables()
0x37928  ldstr    aOriginatesfrom// "originatesfromundelete"
0x3792d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x37932  unbox.any [mscorlib]System.Boolean
0x37937  brfalse.s loc_3793B
0x37939  ldc.i4.1
0x3793a  ret
0x3793b  ldc.i4.0
0x3793c  ret
```
