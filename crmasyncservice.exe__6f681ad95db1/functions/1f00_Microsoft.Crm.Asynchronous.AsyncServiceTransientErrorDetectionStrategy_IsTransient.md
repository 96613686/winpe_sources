# Microsoft.Crm.Asynchronous.AsyncServiceTransientErrorDetectionStrategy::IsTransient

- ea: `0x1f00`
- end: `0x1f41`
- name: `Microsoft.Crm.Asynchronous.AsyncServiceTransientErrorDetectionStrategy::IsTransient`
- size: `65`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1f00`

## pseudocode

```c

```

## disassembly

```asm
0x1f00  ldarg.1
0x1f01  isinst   [System.Data]System.Data.SqlClient.SqlException
0x1f06  stloc.0
0x1f07  ldloc.0
0x1f08  brtrue.s loc_1F0C
0x1f0a  ldc.i4.0
0x1f0b  ret
0x1f0c  ldsfld   class [mscorlib]System.Lazy`1<class [mscorlib]System.Collections.Generic.Dictionary`2<int32, bool>> Microsoft.Crm.Asynchronous.AsyncServiceTransientErrorDetectionStrategy::asyncSqlExceptionRetryStrategy
0x1f11  callvirt instance var<u1> class [mscorlib]System.Lazy`1<class [mscorlib]System.Collections.Generic.Dictionary`2<int32, bool>>::get_Value()
0x1f16  ldloc.0
0x1f17  callvirt instance int32 [System.Data]System.Data.SqlClient.SqlException::get_Number()
0x1f1c  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<int32, bool>::ContainsKey(var<u1>)
0x1f21  brfalse.s loc_1F39
0x1f23  ldsfld   class [mscorlib]System.Lazy`1<class [mscorlib]System.Collections.Generic.Dictionary`2<int32, bool>> Microsoft.Crm.Asynchronous.AsyncServiceTransientErrorDetectionStrategy::asyncSqlExceptionRetryStrategy
0x1f28  callvirt instance var<u1> class [mscorlib]System.Lazy`1<class [mscorlib]System.Collections.Generic.Dictionary`2<int32, bool>>::get_Value()
0x1f2d  ldloc.0
0x1f2e  callvirt instance int32 [System.Data]System.Data.SqlClient.SqlException::get_Number()
0x1f33  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<int32, bool>::get_Item(void)
0x1f38  ret
0x1f39  ldarg.0
0x1f3a  ldarg.1
0x1f3b  call     instance bool [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.TransientErrorDetectionStrategy::IsTransient(class [mscorlib]System.Exception)
0x1f40  ret
```
