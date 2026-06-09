# Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2::add_JobCompleted

- ea: `0x1450`
- end: `0x1479`
- name: `Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2::add_JobCompleted`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1450`

## pseudocode

```c

```

## disassembly

```asm
0x1450  ldarg.0
0x1451  ldfld    class [mscorlib]System.EventHandler class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0>::JobCompleted
0x1456  stloc.0
0x1457  ldloc.0
0x1458  stloc.1
0x1459  ldloc.1
0x145a  ldarg.1
0x145b  call     class [mscorlib]System.Delegate [mscorlib]System.Delegate::Combine(class [mscorlib]System.Delegate, class [mscorlib]System.Delegate)
0x1460  castclass [mscorlib]System.EventHandler
0x1465  stloc.2
0x1466  ldarg.0
0x1467  ldflda   class [mscorlib]System.EventHandler class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0>::JobCompleted
0x146c  ldloc.2
0x146d  ldloc.1
0x146e  call     T0x2B00000B
0x1473  stloc.0
0x1474  ldloc.0
0x1475  ldloc.1
0x1476  bne.un.s loc_1457
0x1478  ret
```
