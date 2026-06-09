# Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando

- ea: `0x24210`
- end: `0x24253`
- name: `Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando`
- size: `67`
- prototype: ``
- caller_count: `25`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xe900`
- `0xf7b0`
- `0x101a0`
- `0x10990`
- `0x10f60`
- `0x11d80`
- `0x158a0`
- `0x17a30`
- `0x1a6c0`
- `0x1a6d0`
- `0x1e140`
- `0x1ec60`
- `0x1f5c0`
- `0x1f810`
- `0x1fdf0`
- `0x216c0`
- `0x21830`
- `0x22ac0`
- `0x25ab0`
- `0x26160`
- `0x26850`
- `0x27980`
- `0x27be0`
- `0x29330`
- `0x294e0`

## callees

- `0x24210`

## pseudocode

```c

```

## disassembly

```asm
0x24210  ldarg.1
0x24211  brtrue.s loc_2421E
0x24213  ldstr    aAttributeNameC// "Attribute name cannot be null."
0x24218  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x2421d  throw
0x2421e  ldarg.2
0x2421f  brtrue.s loc_2423D
0x24221  ldarg.0
0x24222  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Application.Components.UI.CrmUIControl::_expandos
0x24227  ldarg.1
0x24228  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x2422d  brfalse.s loc_24252
0x2422f  ldarg.0
0x24230  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Application.Components.UI.CrmUIControl::_expandos
0x24235  ldarg.1
0x24236  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Remove(var<u1>)
0x2423b  pop
0x2423c  ret
0x2423d  ldarg.1
0x2423e  callvirt instance int32 [mscorlib]System.String::get_Length()
0x24243  brfalse.s loc_24252
0x24245  ldarg.0
0x24246  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Application.Components.UI.CrmUIControl::_expandos
0x2424b  ldarg.1
0x2424c  ldarg.2
0x2424d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x24252  ret
```
