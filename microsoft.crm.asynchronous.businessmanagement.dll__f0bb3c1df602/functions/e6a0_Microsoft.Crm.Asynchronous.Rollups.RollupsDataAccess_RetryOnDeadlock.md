# Microsoft.Crm.Asynchronous.Rollups.RollupsDataAccess::RetryOnDeadlock

- ea: `0xe6a0`
- end: `0xe6d7`
- name: `Microsoft.Crm.Asynchronous.Rollups.RollupsDataAccess::RetryOnDeadlock`
- size: `55`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xdee0`
- `0xdf00`
- `0xdf20`
- `0xdf40`
- `0xdf60`

## callees

- `0xe6a0`

## pseudocode

```c

```

## disassembly

```asm
0xe6a0  ldarg.0
0xe6a1  ldc.i4.1
0xe6a2  ldc.i4   0x7FFFFFFF
0xe6a7  ldstr    aTrycount// "tryCount"
0xe6ac  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfOutOfRange(int32, int32, int32, string)
0xe6b1  ldc.i4.6
0xe6b2  stloc.0
0xe6b3  br.s     loc_E6D1
0xe6b5  ldarg.1
0xe6b6  callvirt instance var<u1> class [mscorlib]System.Func`1<valuetype Microsoft.Crm.Asynchronous.Rollups.SqlCommandResult>::Invoke()
0xe6bb  stloc.0
0xe6bc  ldloc.0
0xe6bd  ldc.i4.4
0xe6be  beq.s    loc_E6C8
0xe6c0  ldloc.0
0xe6c1  ldc.i4.3
0xe6c2  beq.s    loc_E6C8
0xe6c4  ldloc.0
0xe6c5  ldc.i4.6
0xe6c6  bne.un.s loc_E6CF
0xe6c8  ldarg.0
0xe6c9  ldc.i4.1
0xe6ca  sub
0xe6cb  starg.s  0
0xe6cd  br.s     loc_E6D1
0xe6cf  ldloc.0
0xe6d0  ret
0xe6d1  ldarg.0
0xe6d2  ldc.i4.0
0xe6d3  bgt.s    loc_E6B5
0xe6d5  ldloc.0
0xe6d6  ret
```
