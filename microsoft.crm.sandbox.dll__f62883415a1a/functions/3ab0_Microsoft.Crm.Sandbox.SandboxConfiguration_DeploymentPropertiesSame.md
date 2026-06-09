# Microsoft.Crm.Sandbox.SandboxConfiguration::DeploymentPropertiesSame

- ea: `0x3ab0`
- end: `0x3b32`
- name: `Microsoft.Crm.Sandbox.SandboxConfiguration::DeploymentPropertiesSame`
- size: `130`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x3ab0`

## pseudocode

```c

```

## disassembly

```asm
0x3ab0  ldarg.0
0x3ab1  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32> Microsoft.Crm.Sandbox.SandboxConfiguration::_dictionary
0x3ab6  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32>::get_Count()
0x3abb  ldarg.1
0x3abc  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32> Microsoft.Crm.Sandbox.SandboxConfiguration::_dictionary
0x3ac1  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32>::get_Count()
0x3ac6  beq.s    loc_3ACA
0x3ac8  ldc.i4.0
0x3ac9  ret
0x3aca  ldarg.0
0x3acb  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32> Microsoft.Crm.Sandbox.SandboxConfiguration::_dictionary
0x3ad0  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32>::get_Keys()
0x3ad5  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<int32, int32>::GetEnumerator()
0x3ada  stloc.0
0x3adb  br.s     loc_3B15
0x3add  ldloca.s 0
0x3adf  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<int32, int32>::get_Current()
0x3ae4  stloc.1
0x3ae5  ldarg.1
0x3ae6  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32> Microsoft.Crm.Sandbox.SandboxConfiguration::_dictionary
0x3aeb  ldloc.1
0x3aec  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32>::ContainsKey(var<u1>)
0x3af1  brtrue.s loc_3AF7
0x3af3  ldc.i4.0
0x3af4  stloc.2
0x3af5  leave.s  loc_3B30
0x3af7  ldarg.0
0x3af8  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32> Microsoft.Crm.Sandbox.SandboxConfiguration::_dictionary
0x3afd  ldloc.1
0x3afe  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32>::get_Item(void)
0x3b03  ldarg.1
0x3b04  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32> Microsoft.Crm.Sandbox.SandboxConfiguration::_dictionary
0x3b09  ldloc.1
0x3b0a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32>::get_Item(void)
0x3b0f  beq.s    loc_3B15
0x3b11  ldc.i4.0
0x3b12  stloc.2
0x3b13  leave.s  loc_3B30
0x3b15  ldloca.s 0
0x3b17  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<int32, int32>::MoveNext()
0x3b1c  brtrue.s loc_3ADD
0x3b1e  leave.s  loc_3B2E
0x3b20  ldloca.s 0
0x3b22  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<int32, int32>
0x3b28  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3b2d  endfinally
0x3b2e  ldc.i4.1
0x3b2f  ret
0x3b30  ldloc.2
0x3b31  ret
```
