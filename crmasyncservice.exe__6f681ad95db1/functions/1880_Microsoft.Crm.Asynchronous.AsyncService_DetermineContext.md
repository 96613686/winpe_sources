# Microsoft.Crm.Asynchronous.AsyncService::DetermineContext

- ea: `0x1880`
- end: `0x18bf`
- name: `Microsoft.Crm.Asynchronous.AsyncService::DetermineContext`
- size: `63`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xd80`
- `0x1a80`

## callees

- `0x1880`

## pseudocode

```c

```

## disassembly

```asm
0x1880  ldarg.0
0x1881  ldc.i4.s 0x24
0x1883  callvirt instance int32 [mscorlib]System.String::IndexOf(char)
0x1888  ldc.i4.m1
0x1889  beq.s    loc_18AC
0x188b  ldarg.0
0x188c  ldc.i4.1
0x188d  newarr   [mscorlib]System.Char
0x1892  dup
0x1893  ldc.i4.0
0x1894  ldc.i4.s 0x24
0x1896  stelem.i2
0x1897  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x189c  ldc.i4.1
0x189d  ldelem.ref
0x189e  ldstr    aMaintenance// "maintenance"
0x18a3  call     bool [mscorlib]System.String::op_Equality(string, string)
0x18a8  brfalse.s loc_18AC
0x18aa  ldc.i4.1
0x18ab  ret
0x18ac  ldarg.0
0x18ad  ldstr    aDebug// "debug"
0x18b2  ldc.i4.5
0x18b3  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0x18b8  ldc.i4.0
0x18b9  blt.s    loc_18BD
0x18bb  ldc.i4.3
0x18bc  ret
0x18bd  ldc.i4.0
0x18be  ret
```
