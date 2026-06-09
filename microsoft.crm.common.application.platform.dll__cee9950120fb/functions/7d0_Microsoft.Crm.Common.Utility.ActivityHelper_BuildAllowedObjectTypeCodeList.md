# Microsoft.Crm.Common.Utility.ActivityHelper::BuildAllowedObjectTypeCodeList

- ea: `0x7d0`
- end: `0x836`
- name: `Microsoft.Crm.Common.Utility.ActivityHelper::BuildAllowedObjectTypeCodeList`
- size: `102`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x840`

## callees

- `0x7d0`

## pseudocode

```c

```

## disassembly

```asm
0x7d0  ldarg.0
0x7d1  ldlen
0x7d2  conv.i4
0x7d3  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor(int32)
0x7d8  stloc.0
0x7d9  ldarg.0
0x7da  stloc.2
0x7db  ldc.i4.0
0x7dc  stloc.3
0x7dd  br.s     loc_81B
0x7df  ldloc.2
0x7e0  ldloc.3
0x7e1  ldelem.i4
0x7e2  stloc.s  4
0x7e4  ldc.i4   0x40000000
0x7e9  stloc.s  5
0x7eb  ldloc.s  4
0x7ed  ldc.i4.8
0x7ee  beq.s    loc_7F4
0x7f0  ldc.i4.s 0x10
0x7f2  stloc.s  5
0x7f4  ldloc.s  5
0x7f6  ldc.i4   0x40000000
0x7fb  beq.s    loc_809
0x7fd  ldloc.s  4
0x7ff  ldloc.s  5
0x801  ldarg.1
0x802  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.PrivilegeId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x807  brfalse.s loc_817
0x809  ldloc.0
0x80a  ldloc.s  4
0x80c  box      [mscorlib]System.Int32
0x811  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x816  pop
0x817  ldloc.3
0x818  ldc.i4.1
0x819  add
0x81a  stloc.3
0x81b  ldloc.3
0x81c  ldloc.2
0x81d  ldlen
0x81e  conv.i4
0x81f  blt.s    loc_7DF
0x821  ldloc.0
0x822  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x827  newarr   [mscorlib]System.Int32
0x82c  stloc.1
0x82d  ldloc.0
0x82e  ldloc.1
0x82f  callvirt instance void [mscorlib]System.Collections.ArrayList::CopyTo(class [mscorlib]System.Array)
0x834  ldloc.1
0x835  ret
```
