# Microsoft.Crm.PageParametersCache::ReadPageParametersFromAttributes

- ea: `0x7a0`
- end: `0x7c9`
- name: `Microsoft.Crm.PageParametersCache::ReadPageParametersFromAttributes`
- size: `41`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x480`

## callees

- `0x300`
- `0x7a0`
- `0x7d0`
- `0x810`

## pseudocode

```c

```

## disassembly

```asm
0x7a0  newobj   instance void Microsoft.Crm.PageParameters::.ctor()
0x7a5  stloc.0
0x7a6  ldarg.1
0x7a7  isinst   [System.Web]System.Web.UI.Page
0x7ac  stloc.1
0x7ad  ldloc.1
0x7ae  brfalse.s loc_7BA
0x7b0  ldarg.0
0x7b1  ldloc.0
0x7b2  ldloc.1
0x7b3  call     instance void Microsoft.Crm.PageParametersCache::AddControlParameters(class Microsoft.Crm.PageParameters pageParameters, class [System.Web]System.Web.UI.Control control)
0x7b8  br.s     loc_7C7
0x7ba  ldarg.0
0x7bb  ldloc.0
0x7bc  ldarg.1
0x7bd  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x7c2  call     instance void Microsoft.Crm.PageParametersCache::AddTypeParameters(class Microsoft.Crm.PageParameters pageParameters, class [mscorlib]System.Type controlType)
0x7c7  ldloc.0
0x7c8  ret
```
