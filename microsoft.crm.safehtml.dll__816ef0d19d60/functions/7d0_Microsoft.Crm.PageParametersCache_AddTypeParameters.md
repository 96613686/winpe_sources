# Microsoft.Crm.PageParametersCache::AddTypeParameters

- ea: `0x7d0`
- end: `0x807`
- name: `Microsoft.Crm.PageParametersCache::AddTypeParameters`
- size: `55`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x7a0`
- `0x810`

## callees

- `0x6a0`
- `0x7d0`

## pseudocode

```c

```

## disassembly

```asm
0x7d0  ldarg.2
0x7d1  ldtoken  Microsoft.Crm.WebParameterAttribute
0x7d6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7db  ldc.i4.1
0x7dc  callvirt instance object[] [mscorlib]System.Reflection.MemberInfo::GetCustomAttributes(class [mscorlib]System.Type, bool)
0x7e1  castclass class Microsoft.Crm.WebParameterAttribute[]
0x7e6  stloc.0
0x7e7  ldc.i4.0
0x7e8  stloc.1
0x7e9  br.s     loc_800
0x7eb  ldloc.0
0x7ec  ldloc.1
0x7ed  ldelem.ref
0x7ee  stloc.2
0x7ef  ldarg.1
0x7f0  ldloc.2
0x7f1  ldarg.2
0x7f2  callvirt instance string [mscorlib]System.Type::get_FullName()
0x7f7  call     void Microsoft.Crm.PageParametersCache::ReadParameterType(class Microsoft.Crm.PageParameters pageParameters, class Microsoft.Crm.WebParameterAttribute attribute, string associatedControl)
0x7fc  ldloc.1
0x7fd  ldc.i4.1
0x7fe  add
0x7ff  stloc.1
0x800  ldloc.1
0x801  ldloc.0
0x802  ldlen
0x803  conv.i4
0x804  blt.s    loc_7EB
0x806  ret
```
