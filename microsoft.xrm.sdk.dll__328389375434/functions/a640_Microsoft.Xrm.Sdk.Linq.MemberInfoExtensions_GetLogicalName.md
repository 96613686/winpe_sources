# Microsoft.Xrm.Sdk.Linq.MemberInfoExtensions::GetLogicalName

- ea: `0xa640`
- end: `0xa675`
- name: `Microsoft.Xrm.Sdk.Linq.MemberInfoExtensions::GetLogicalName`
- size: `53`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0xd950`
- `0xdb00`

## callees

- `0x24a0`
- `0x7450`
- `0xa640`
- `0x130d0`

## pseudocode

```c

```

## disassembly

```asm
0xa640  ldarg.0
0xa641  call     T0x2B000020
0xa646  stloc.0
0xa647  ldloc.0
0xa648  brfalse.s loc_A651
0xa64a  ldloc.0
0xa64b  callvirt instance string Microsoft.Xrm.Sdk.AttributeLogicalNameAttribute::get_LogicalName()
0xa650  ret
0xa651  ldarg.0
0xa652  call     T0x2B000021
0xa657  stloc.1
0xa658  ldloc.1
0xa659  brfalse.s loc_A662
0xa65b  ldloc.1
0xa65c  callvirt instance string Microsoft.Xrm.Sdk.Client.EntityLogicalNameAttribute::get_LogicalName()
0xa661  ret
0xa662  ldarg.0
0xa663  call     T0x2B000022
0xa668  stloc.2
0xa669  ldloc.2
0xa66a  brfalse.s loc_A673
0xa66c  ldloc.2
0xa66d  callvirt instance string Microsoft.Xrm.Sdk.RelationshipSchemaNameAttribute::get_SchemaName()
0xa672  ret
0xa673  ldnull
0xa674  ret
```
