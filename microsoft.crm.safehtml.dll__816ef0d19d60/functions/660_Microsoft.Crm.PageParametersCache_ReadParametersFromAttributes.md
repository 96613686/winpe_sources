# Microsoft.Crm.PageParametersCache::ReadParametersFromAttributes

- ea: `0x660`
- end: `0x699`
- name: `Microsoft.Crm.PageParametersCache::ReadParametersFromAttributes`
- size: `57`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x640`

## callees

- `0x300`
- `0x660`
- `0x6a0`

## pseudocode

```c

```

## disassembly

```asm
0x660  ldarg.1
0x661  ldtoken  Microsoft.Crm.WebParameterAttribute
0x666  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x66b  ldc.i4.1
0x66c  callvirt instance object[] [mscorlib]System.Reflection.ICustomAttributeProvider::GetCustomAttributes(class [mscorlib]System.Type, bool)
0x671  castclass class Microsoft.Crm.WebParameterAttribute[]
0x676  newobj   instance void Microsoft.Crm.PageParameters::.ctor()
0x67b  stloc.0
0x67c  stloc.1
0x67d  ldc.i4.0
0x67e  stloc.2
0x67f  br.s     loc_691
0x681  ldloc.1
0x682  ldloc.2
0x683  ldelem.ref
0x684  stloc.3
0x685  ldloc.0
0x686  ldloc.3
0x687  ldnull
0x688  call     void Microsoft.Crm.PageParametersCache::ReadParameterType(class Microsoft.Crm.PageParameters pageParameters, class Microsoft.Crm.WebParameterAttribute attribute, string associatedControl)
0x68d  ldloc.2
0x68e  ldc.i4.1
0x68f  add
0x690  stloc.2
0x691  ldloc.2
0x692  ldloc.1
0x693  ldlen
0x694  conv.i4
0x695  blt.s    loc_681
0x697  ldloc.0
0x698  ret
```
