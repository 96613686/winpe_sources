# Microsoft.Crm.Application.WebServices.ParameterBag::GetBagArray

- ea: `0x1c0`
- end: `0x1fc`
- name: `Microsoft.Crm.Application.WebServices.ParameterBag::GetBagArray`
- size: `60`
- prototype: ``
- caller_count: `8`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0xbe0`
- `0x1000`
- `0x1a10`
- `0x2220`
- `0x2b10`
- `0x9850`
- `0x9a10`
- `0x9bd0`

## callees

- `0x10`
- `0x110`
- `0x1c0`

## pseudocode

```c

```

## disassembly

```asm
0x1c0  ldarg.0
0x1c1  ldarg.1
0x1c2  call     instance class [System.Xml]System.Xml.XmlNode[] Microsoft.Crm.Application.WebServices.ParameterBag::GetNodeArray(string name)
0x1c7  stloc.0
0x1c8  ldloc.0
0x1c9  brtrue.s loc_1D7
0x1cb  ldstr    aExpectedParame// "Expected parameter bags."
0x1d0  ldarg.1
0x1d1  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x1d6  throw
0x1d7  ldloc.0
0x1d8  ldlen
0x1d9  conv.i4
0x1da  newarr   Microsoft.Crm.Application.WebServices.ParameterBag
0x1df  stloc.1
0x1e0  ldc.i4.0
0x1e1  stloc.2
0x1e2  br.s     loc_1F4
0x1e4  ldloc.1
0x1e5  ldloc.2
0x1e6  ldloc.0
0x1e7  ldloc.2
0x1e8  ldelem.ref
0x1e9  ldarg.1
0x1ea  newobj   instance void Microsoft.Crm.Application.WebServices.ParameterBag::.ctor(class [System.Xml]System.Xml.XmlNode parameterBag, string name)
0x1ef  stelem.ref
0x1f0  ldloc.2
0x1f1  ldc.i4.1
0x1f2  add
0x1f3  stloc.2
0x1f4  ldloc.2
0x1f5  ldloc.0
0x1f6  ldlen
0x1f7  conv.i4
0x1f8  blt.s    loc_1E4
0x1fa  ldloc.1
0x1fb  ret
```
