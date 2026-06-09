# Microsoft.Xrm.Tools.OwinJobManager.Client.Helpers.ExceptionHelper::InnerMostExceptionIs

- ea: `0x810`
- end: `0x82f`
- name: `Microsoft.Xrm.Tools.OwinJobManager.Client.Helpers.ExceptionHelper::InnerMostExceptionIs`
- size: `31`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x810`
- `0x830`

## pseudocode

```c

```

## disassembly

```asm
0x810  ldarg.0
0x811  call     class [mscorlib]System.Exception Microsoft.Xrm.Tools.OwinJobManager.Client.Helpers.ExceptionHelper::GetInnerMostException(class [mscorlib]System.Exception ex)
0x816  starg.s  0
0x818  ldarg.0
0x819  isinst   mvar<u1>
0x81e  brfalse.s loc_82D
0x820  ldarg.1
0x821  ldarg.0
0x822  unbox.any mvar<u1>
0x827  callvirt instance var<u1> class [mscorlib]System.Func`2<mvar<u1>, !!T0>::Invoke(void)
0x82c  ret
0x82d  ldc.i4.0
0x82e  ret
```
