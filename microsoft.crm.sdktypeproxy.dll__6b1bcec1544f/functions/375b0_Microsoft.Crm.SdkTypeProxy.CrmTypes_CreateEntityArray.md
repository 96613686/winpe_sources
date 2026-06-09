# Microsoft.Crm.SdkTypeProxy.CrmTypes::CreateEntityArray

- ea: `0x375b0`
- end: `0x375d6`
- name: `Microsoft.Crm.SdkTypeProxy.CrmTypes::CreateEntityArray`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x375b0`

## pseudocode

```c

```

## disassembly

```asm
0x375b0  ldarg.1
0x375b1  newarr   [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity
0x375b6  stloc.0
0x375b7  ldc.i4.0
0x375b8  stloc.1
0x375b9  br.s     loc_375D0
0x375bb  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity::.ctor()
0x375c0  stloc.2
0x375c1  ldloc.2
0x375c2  ldarg.0
0x375c3  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity::set_Name(string)
0x375c8  ldloc.0
0x375c9  ldloc.1
0x375ca  ldloc.2
0x375cb  stelem.ref
0x375cc  ldloc.1
0x375cd  ldc.i4.1
0x375ce  add
0x375cf  stloc.1
0x375d0  ldloc.1
0x375d1  ldarg.1
0x375d2  blt.s    loc_375BB
0x375d4  ldloc.0
0x375d5  ret
```
