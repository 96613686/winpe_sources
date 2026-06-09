# Microsoft.Crm.Metadata.EvaluationContext::.ctor

- ea: `0x2a9a0`
- end: `0x2aa07`
- name: `Microsoft.Crm.Metadata.EvaluationContext::.ctor`
- size: `103`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1f330`
- `0x22b30`
- `0x22fc0`

## callees

- `0x2a9a0`
- `0x2aa20`
- `0x2aa40`
- `0x2aa50`
- `0x2aa60`

## string_xrefs

- `0x2a9d6`: `MetadataHelper cannot be null and MetadataCache should be null when EvaluationMode is Create/Update`
- `0x2a9fc`: `MetadataCache cannot be null and MetadataHelper should be null when EvaluationMode is Upgrade/Validate`

## pseudocode

```c

```

## disassembly

```asm
0x2a9a0  ldarg.0
0x2a9a1  call     instance void [mscorlib]System.Object::.ctor()
0x2a9a6  ldarg.0
0x2a9a7  ldarg.1
0x2a9a8  call     instance void Microsoft.Crm.Metadata.EvaluationContext::set_MetadataCache(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache value)
0x2a9ad  ldarg.0
0x2a9ae  ldarg.2
0x2a9af  call     instance void Microsoft.Crm.Metadata.EvaluationContext::set_MetadataHelper(class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper value)
0x2a9b4  ldarg.0
0x2a9b5  ldarg.3
0x2a9b6  call     instance void Microsoft.Crm.Metadata.EvaluationContext::set_EvaluationMode(valuetype Microsoft.Crm.Metadata.EvaluationMode value)
0x2a9bb  ldarg.0
0x2a9bc  call     instance valuetype Microsoft.Crm.Metadata.EvaluationMode Microsoft.Crm.Metadata.EvaluationContext::get_EvaluationMode()
0x2a9c1  brfalse.s loc_2A9CC
0x2a9c3  ldarg.0
0x2a9c4  call     instance valuetype Microsoft.Crm.Metadata.EvaluationMode Microsoft.Crm.Metadata.EvaluationContext::get_EvaluationMode()
0x2a9c9  ldc.i4.1
0x2a9ca  bne.un.s loc_2A9E0
0x2a9cc  ldarg.2
0x2a9cd  brfalse.s loc_2A9D5
0x2a9cf  ldarg.1
0x2a9d0  ldnull
0x2a9d1  ceq
0x2a9d3  br.s     loc_2A9D6
0x2a9d5  ldc.i4.0
0x2a9d6  ldstr    aMetadatahelper_0// "MetadataHelper cannot be null and Metad"...
0x2a9db  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x2a9e0  ldarg.0
0x2a9e1  call     instance valuetype Microsoft.Crm.Metadata.EvaluationMode Microsoft.Crm.Metadata.EvaluationContext::get_EvaluationMode()
0x2a9e6  ldc.i4.2
0x2a9e7  beq.s    loc_2A9F2
0x2a9e9  ldarg.0
0x2a9ea  call     instance valuetype Microsoft.Crm.Metadata.EvaluationMode Microsoft.Crm.Metadata.EvaluationContext::get_EvaluationMode()
0x2a9ef  ldc.i4.3
0x2a9f0  bne.un.s loc_2AA06
0x2a9f2  ldarg.1
0x2a9f3  brfalse.s loc_2A9FB
0x2a9f5  ldarg.2
0x2a9f6  ldnull
0x2a9f7  ceq
0x2a9f9  br.s     loc_2A9FC
0x2a9fb  ldc.i4.0
0x2a9fc  ldstr    aMetadatacacheC// "MetadataCache cannot be null and Metada"...
0x2aa01  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x2aa06  ret
```
