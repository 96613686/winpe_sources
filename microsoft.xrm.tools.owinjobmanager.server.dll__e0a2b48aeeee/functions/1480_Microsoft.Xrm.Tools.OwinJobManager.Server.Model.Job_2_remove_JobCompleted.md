# Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2::remove_JobCompleted

- ea: `0x1480`
- end: `0x14a9`
- name: `Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2::remove_JobCompleted`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1480`

## pseudocode

```c

```

## disassembly

```asm
0x1480  ldarg.0
0x1481  ldfld    class [mscorlib]System.EventHandler class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0>::JobCompleted
0x1486  stloc.0
0x1487  ldloc.0
0x1488  stloc.1
0x1489  ldloc.1
0x148a  ldarg.1
0x148b  call     class [mscorlib]System.Delegate [mscorlib]System.Delegate::Remove(class [mscorlib]System.Delegate, class [mscorlib]System.Delegate)
0x1490  castclass [mscorlib]System.EventHandler
0x1495  stloc.2
0x1496  ldarg.0
0x1497  ldflda   class [mscorlib]System.EventHandler class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0>::JobCompleted
0x149c  ldloc.2
0x149d  ldloc.1
0x149e  call     T0x2B00000B
0x14a3  stloc.0
0x14a4  ldloc.0
0x14a5  ldloc.1
0x14a6  bne.un.s loc_1487
0x14a8  ret
```
