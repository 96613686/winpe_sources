# Microsoft.Crm.Asynchronous.AsyncThrottle::UpdateMaximumCount

- ea: `0x13aa0`
- end: `0x13ada`
- name: `Microsoft.Crm.Asynchronous.AsyncThrottle::UpdateMaximumCount`
- size: `58`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x139e0`
- `0x13a50`

## callees

- `0x12170`
- `0x13aa0`

## pseudocode

```c

```

## disassembly

```asm
0x13aa0  ldarg.0
0x13aa1  ldfld    int32 Microsoft.Crm.Asynchronous.AsyncThrottle::_maxCount
0x13aa6  stloc.0
0x13aa7  ldarg.0
0x13aa8  ldfld    class Microsoft.Crm.Asynchronous.IThrottlingScope Microsoft.Crm.Asynchronous.AsyncThrottle::_throttlingScope
0x13aad  callvirt instance valuetype [mscorlib]System.Nullable`1<int32> Microsoft.Crm.Asynchronous.IThrottlingScope::get_CurrentThrottlingLimit()
0x13ab2  stloc.1
0x13ab3  ldarg.0
0x13ab4  ldloca.s 1
0x13ab6  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x13abb  brtrue.s loc_13AC4
0x13abd  ldc.i4   0x7FFFFFFF
0x13ac2  br.s     loc_13ACB
0x13ac4  ldloca.s 1
0x13ac6  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0x13acb  stfld    int32 Microsoft.Crm.Asynchronous.AsyncThrottle::_maxCount
0x13ad0  ldarg.0
0x13ad1  ldfld    int32 Microsoft.Crm.Asynchronous.AsyncThrottle::_maxCount
0x13ad6  ldloc.0
0x13ad7  cgt
0x13ad9  ret
```
