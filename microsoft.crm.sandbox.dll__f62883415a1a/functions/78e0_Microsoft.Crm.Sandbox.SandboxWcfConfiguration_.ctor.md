# Microsoft.Crm.Sandbox.SandboxWcfConfiguration::.ctor

- ea: `0x78e0`
- end: `0x7a9c`
- name: `Microsoft.Crm.Sandbox.SandboxWcfConfiguration::.ctor`
- size: `444`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2800`
- `0x5680`

## callees

- `0x14d0`
- `0x78e0`

## string_xrefs

- `0x7a58`: `SandboxWcfConfiguration: Override from registry: {0}{1}: {2}`

## pseudocode

```c

```

## disassembly

```asm
0x78e0  ldarg.0
0x78e1  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32>::.ctor()
0x78e6  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32> Microsoft.Crm.Sandbox.SandboxWcfConfiguration::_registryProperties
0x78eb  ldarg.0
0x78ec  call     instance void [mscorlib]System.Object::.ctor()
0x78f1  ldarg.0
0x78f2  ldarga.s 1
0x78f4  constrained. Microsoft.Crm.Sandbox.SandboxPropertyPrefix
0x78fa  callvirt instance string [mscorlib]System.Object::ToString()
0x78ff  stfld    string Microsoft.Crm.Sandbox.SandboxWcfConfiguration::_propertyPrefix
0x7904  ldtoken  Microsoft.Crm.Sandbox.SandboxWcfProperty
0x7909  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x790e  call     class [mscorlib]System.Array [mscorlib]System.Enum::GetValues(class [mscorlib]System.Type)
0x7913  castclass valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty[]
0x7918  stloc.0
0x7919  ldarg.1
0x791a  ldc.i4.4
0x791b  sub
0x791c  switch   loc_793E, loc_79C9, loc_797E, loc_7955, loc_79B5, loc_7992
0x7939  br       loc_79DB
0x793e  ldarg.0
0x793f  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32> Microsoft.Crm.Sandbox.SandboxWcfConfiguration::_registryProperties
0x7944  ldc.i4.s 0xC
0x7946  ldc.i4   0x7B00000
0x794b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32>::set_Item(var<u1>, !!T0)
0x7950  br       loc_79DB
0x7955  ldarg.0
0x7956  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32> Microsoft.Crm.Sandbox.SandboxWcfConfiguration::_registryProperties
0x795b  ldc.i4.s 0xC
0x795d  ldc.i4   0x7B00000
0x7962  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32>::set_Item(var<u1>, !!T0)
0x7967  ldarg.0
0x7968  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32> Microsoft.Crm.Sandbox.SandboxWcfConfiguration::_registryProperties
0x796d  ldc.i4.s 0xB
0x796f  ldc.i4.s 0x64
0x7971  call     int32 [mscorlib]System.Environment::get_ProcessorCount()
0x7976  mul
0x7977  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32>::set_Item(var<u1>, !!T0)
0x797c  br.s     loc_79DB
0x797e  ldarg.0
0x797f  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32> Microsoft.Crm.Sandbox.SandboxWcfConfiguration::_registryProperties
0x7984  ldc.i4.s 0xC
0x7986  ldc.i4   0x7B00000
0x798b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32>::set_Item(var<u1>, !!T0)
0x7990  br.s     loc_79DB
0x7992  ldarg.0
0x7993  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32> Microsoft.Crm.Sandbox.SandboxWcfConfiguration::_registryProperties
0x7998  ldc.i4.s 0xC
0x799a  ldc.i4   0x7B00000
0x799f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32>::set_Item(var<u1>, !!T0)
0x79a4  ldarg.0
0x79a5  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32> Microsoft.Crm.Sandbox.SandboxWcfConfiguration::_registryProperties
0x79aa  ldc.i4.s 0xB
0x79ac  ldc.i4.s 0x64
0x79ae  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32>::set_Item(var<u1>, !!T0)
0x79b3  br.s     loc_79DB
0x79b5  ldarg.0
0x79b6  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32> Microsoft.Crm.Sandbox.SandboxWcfConfiguration::_registryProperties
0x79bb  ldc.i4.s 0xC
0x79bd  ldc.i4   0x7B00000
0x79c2  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32>::set_Item(var<u1>, !!T0)
0x79c7  br.s     loc_79DB
0x79c9  ldarg.0
0x79ca  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32> Microsoft.Crm.Sandbox.SandboxWcfConfiguration::_registryProperties
0x79cf  ldc.i4.s 0xC
0x79d1  ldc.i4   0x7B00000
0x79d6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32>::set_Item(var<u1>, !!T0)
0x79db  ldarg.0
0x79dc  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32> Microsoft.Crm.Sandbox.SandboxWcfConfiguration::_registryProperties
0x79e1  ldc.i4.s 0x10
0x79e3  ldc.i4   0xC8
0x79e8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32>::set_Item(var<u1>, !!T0)
0x79ed  ldloc.0
0x79ee  stloc.1
0x79ef  ldc.i4.0
0x79f0  stloc.2
0x79f1  br       loc_7A92
0x79f6  ldloc.1
0x79f7  ldloc.2
0x79f8  ldelem.i4
0x79f9  stloc.3
0x79fa  ldloc.3
0x79fb  ldc.i4.s 0xD
0x79fd  beq      loc_7A8E
0x7a02  ldloc.3
0x7a03  ldc.i4.s 0xE
0x7a05  beq      loc_7A8E
0x7a0a  ldloc.3
0x7a0b  ldc.i4.s 0xF
0x7a0d  beq.s    loc_7A8E
0x7a0f  ldarg.0
0x7a10  ldfld    string Microsoft.Crm.Sandbox.SandboxWcfConfiguration::_propertyPrefix
0x7a15  ldloc.3
0x7a16  box      Microsoft.Crm.Sandbox.SandboxWcfProperty
0x7a1b  call     string [mscorlib]System.String::Concat(object, object)
0x7a20  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string)
0x7a25  stloc.s  4
0x7a27  ldloc.s  4
0x7a29  brfalse.s loc_7A8E
0x7a2b  ldloc.s  4
0x7a2d  isinst   [mscorlib]System.Int32
0x7a32  brfalse.s loc_7A8E
0x7a34  ldloc.s  4
0x7a36  unbox.any [mscorlib]System.Int32
0x7a3b  ldc.i4.0
0x7a3c  ble.s    loc_7A8E
0x7a3e  ldarg.0
0x7a3f  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32> Microsoft.Crm.Sandbox.SandboxWcfConfiguration::_registryProperties
0x7a44  ldloc.3
0x7a45  ldloc.s  4
0x7a47  unbox.any [mscorlib]System.Int32
0x7a4c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32>::set_Item(var<u1>, !!T0)
0x7a51  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x7a56  ldc.i4.s 0x26
0x7a58  ldstr    aSandboxwcfconf// "SandboxWcfConfiguration: Override from "...
0x7a5d  ldc.i4.3
0x7a5e  newarr   [mscorlib]System.Object
0x7a63  dup
0x7a64  ldc.i4.0
0x7a65  ldarg.0
0x7a66  ldfld    string Microsoft.Crm.Sandbox.SandboxWcfConfiguration::_propertyPrefix
0x7a6b  stelem.ref
0x7a6c  dup
0x7a6d  ldc.i4.1
0x7a6e  ldloc.3
0x7a6f  box      Microsoft.Crm.Sandbox.SandboxWcfProperty
0x7a74  stelem.ref
0x7a75  dup
0x7a76  ldc.i4.2
0x7a77  ldarg.0
0x7a78  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32> Microsoft.Crm.Sandbox.SandboxWcfConfiguration::_registryProperties
0x7a7d  ldloc.3
0x7a7e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32>::get_Item(void)
0x7a83  box      [mscorlib]System.Int32
0x7a88  stelem.ref
0x7a89  call     void Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x7a8e  ldloc.2
0x7a8f  ldc.i4.1
0x7a90  add
0x7a91  stloc.2
0x7a92  ldloc.2
0x7a93  ldloc.1
0x7a94  ldlen
0x7a95  conv.i4
0x7a96  blt      loc_79F6
0x7a9b  ret
```
