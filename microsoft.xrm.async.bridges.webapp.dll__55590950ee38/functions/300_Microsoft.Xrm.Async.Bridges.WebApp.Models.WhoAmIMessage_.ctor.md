# Microsoft.Xrm.Async.Bridges.WebApp.Models.WhoAmIMessage::.ctor

- ea: `0x300`
- end: `0x360`
- name: `Microsoft.Xrm.Async.Bridges.WebApp.Models.WhoAmIMessage::.ctor`
- size: `96`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x410`

## callees

- `0x300`

## pseudocode

```c

```

## disassembly

```asm
0x300  ldarg.0
0x301  call     instance void [mscorlib]System.Object::.ctor()
0x306  ldarg.0
0x307  ldarg.1
0x308  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Security.Claims.Claim> [mscorlib]System.Security.Claims.ClaimsPrincipal::get_Claims()
0x30d  ldsfld   class [mscorlib]System.Func`2<class [mscorlib]System.Security.Claims.Claim, bool> <>c::<>9__2_0
0x312  dup
0x313  brtrue.s loc_32C
0x315  pop
0x316  ldsfld   class <>c <>c::<>9
0x31b  ldftn    instance bool <>c::<.ctor>b__2_0(class [mscorlib]System.Security.Claims.Claim c)
0x321  newobj   instance void class [mscorlib]System.Func`2<class [mscorlib]System.Security.Claims.Claim, bool>::.ctor(object, native int)
0x326  dup
0x327  stsfld   class [mscorlib]System.Func`2<class [mscorlib]System.Security.Claims.Claim, bool> <>c::<>9__2_0
0x32c  call     T0x2B00000C
0x331  ldsfld   class [mscorlib]System.Func`2<class [mscorlib]System.Security.Claims.Claim, class Microsoft.Xrm.Async.Bridges.WebApp.Models.ClaimInfo> <>c::<>9__2_1
0x336  dup
0x337  brtrue.s loc_350
0x339  pop
0x33a  ldsfld   class <>c <>c::<>9
0x33f  ldftn    instance class Microsoft.Xrm.Async.Bridges.WebApp.Models.ClaimInfo <>c::<.ctor>b__2_1(class [mscorlib]System.Security.Claims.Claim c)
0x345  newobj   instance void class [mscorlib]System.Func`2<class [mscorlib]System.Security.Claims.Claim, class Microsoft.Xrm.Async.Bridges.WebApp.Models.ClaimInfo>::.ctor(object, native int)
0x34a  dup
0x34b  stsfld   class [mscorlib]System.Func`2<class [mscorlib]System.Security.Claims.Claim, class Microsoft.Xrm.Async.Bridges.WebApp.Models.ClaimInfo> <>c::<>9__2_1
0x350  call     T0x2B00000D
0x355  call     T0x2B00000E
0x35a  stfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Async.Bridges.WebApp.Models.ClaimInfo> Microsoft.Xrm.Async.Bridges.WebApp.Models.WhoAmIMessage::<Claims>k__BackingField
0x35f  ret
```
