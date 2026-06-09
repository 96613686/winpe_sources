# Microsoft.Crm.RegistryValueDefaults::get_defaultValues

- ea: `0x22c10`
- end: `0x22cf7`
- name: `Microsoft.Crm.RegistryValueDefaults::get_defaultValues`
- size: `231`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x22d10`

## callees

- `0x22c10`

## string_xrefs

- `0x22c29`: `NumThreadsForIndexCreation`
- `0x22c60`: `SortInTempDB`
- `0x22cb7`: `SortInTempDB`
- `0x22c75`: `BatchAddAttributeUpdates`
- `0x22ccc`: `BatchAddAttributeUpdates`
- `0x22c8a`: `NumThreadsForParallelMerge`
- `0x22ce1`: `NumThreadsForParallelMerge`

## pseudocode

```c

```

## disassembly

```asm
0x22c10  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.RegistryValueDefaults::_defaultValues
0x22c15  brtrue   loc_22CF1
0x22c1a  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x22c1f  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.RegistryValueDefaults::_defaultValues
0x22c24  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.RegistryValueDefaults::_defaultValues
0x22c29  ldstr    aNumthreadsfori// "NumThreadsForIndexCreation"
0x22c2e  ldc.i4.1
0x22c2f  box      [mscorlib]System.Int32
0x22c34  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x22c39  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x22c3e  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x22c43  ldc.i4.2
0x22c44  beq.s    loc_22C9D
0x22c46  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.RegistryValueDefaults::_defaultValues
0x22c4b  ldstr    aMaxdopforindex// "MaxDopForIndexCreation"
0x22c50  ldc.i4.4
0x22c51  box      [mscorlib]System.Int32
0x22c56  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x22c5b  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.RegistryValueDefaults::_defaultValues
0x22c60  ldstr    aSortintempdb// "SortInTempDB"
0x22c65  ldc.i4.1
0x22c66  box      [mscorlib]System.Int32
0x22c6b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x22c70  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.RegistryValueDefaults::_defaultValues
0x22c75  ldstr    aBatchaddattrib// "BatchAddAttributeUpdates"
0x22c7a  ldc.i4.1
0x22c7b  box      [mscorlib]System.Int32
0x22c80  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x22c85  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.RegistryValueDefaults::_defaultValues
0x22c8a  ldstr    aNumthreadsforp// "NumThreadsForParallelMerge"
0x22c8f  ldc.i4.s 0xA
0x22c91  box      [mscorlib]System.Int32
0x22c96  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x22c9b  br.s     loc_22CF1
0x22c9d  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.RegistryValueDefaults::_defaultValues
0x22ca2  ldstr    aMaxdopforindex// "MaxDopForIndexCreation"
0x22ca7  ldc.i4.1
0x22ca8  box      [mscorlib]System.Int32
0x22cad  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x22cb2  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.RegistryValueDefaults::_defaultValues
0x22cb7  ldstr    aSortintempdb// "SortInTempDB"
0x22cbc  ldc.i4.0
0x22cbd  box      [mscorlib]System.Int32
0x22cc2  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x22cc7  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.RegistryValueDefaults::_defaultValues
0x22ccc  ldstr    aBatchaddattrib// "BatchAddAttributeUpdates"
0x22cd1  ldc.i4.0
0x22cd2  box      [mscorlib]System.Int32
0x22cd7  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x22cdc  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.RegistryValueDefaults::_defaultValues
0x22ce1  ldstr    aNumthreadsforp// "NumThreadsForParallelMerge"
0x22ce6  ldc.i4.5
0x22ce7  box      [mscorlib]System.Int32
0x22cec  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x22cf1  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.RegistryValueDefaults::_defaultValues
0x22cf6  ret
```
