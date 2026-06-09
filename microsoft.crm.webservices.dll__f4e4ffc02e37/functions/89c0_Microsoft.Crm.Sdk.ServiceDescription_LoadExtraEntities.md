# Microsoft.Crm.Sdk.ServiceDescription::LoadExtraEntities

- ea: `0x89c0`
- end: `0x89ff`
- name: `Microsoft.Crm.Sdk.ServiceDescription::LoadExtraEntities`
- size: `63`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x88e0`

## callees

- `0x89c0`
- `0x8a00`
- `0x9480`

## pseudocode

```c

```

## disassembly

```asm
0x89c0  ldc.i4.s 0xB
0x89c2  newarr   [mscorlib]System.Int32
0x89c7  dup
0x89c8  ldtoken  valuetype __StaticArrayInitTypeSize=44 <PrivateImplementationDetails>::E5CA5A63CFF7A8F7F8947F3D63FFCC830B725FC2
0x89cd  call     void [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::InitializeArray(class [mscorlib]System.Array, valuetype [mscorlib]System.RuntimeFieldHandle)
0x89d2  stloc.0
0x89d3  ldc.i4.0
0x89d4  stloc.1
0x89d5  br.s     loc_89F8
0x89d7  ldloc.0
0x89d8  ldloc.1
0x89d9  ldelem.i4
0x89da  stloc.2
0x89db  ldarg.0
0x89dc  ldfld    class Microsoft.Crm.Sdk.EntityMetadatas Microsoft.Crm.Sdk.ServiceDescription::_entityMetadatas
0x89e1  ldloc.2
0x89e2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Sdk.EntityMetadatas::GetEntity(int32 objectTypeCode)
0x89e7  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x89ec  stloc.3
0x89ed  ldarg.0
0x89ee  ldloc.3
0x89ef  call     instance void Microsoft.Crm.Sdk.ServiceDescription::LoadExtraEntity(string logicalName)
0x89f4  ldloc.1
0x89f5  ldc.i4.1
0x89f6  add
0x89f7  stloc.1
0x89f8  ldloc.1
0x89f9  ldloc.0
0x89fa  ldlen
0x89fb  conv.i4
0x89fc  blt.s    loc_89D7
0x89fe  ret
```
