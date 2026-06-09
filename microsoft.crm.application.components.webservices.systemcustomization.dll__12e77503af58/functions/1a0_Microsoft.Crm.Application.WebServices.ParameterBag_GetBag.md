# Microsoft.Crm.Application.WebServices.ParameterBag::GetBag

- ea: `0x1a0`
- end: `0x1bd`
- name: `Microsoft.Crm.Application.WebServices.ParameterBag::GetBag`
- size: `29`
- prototype: ``
- caller_count: `21`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x430`
- `0xbe0`
- `0x1000`
- `0x1a10`
- `0x20e0`
- `0x2220`
- `0x26f0`
- `0x3450`
- `0x37d0`
- `0x3a00`
- `0x3e40`
- `0x3eb0`
- `0x3f20`
- `0x9850`
- `0x9a10`
- `0x9bd0`
- `0x9fe0`
- `0xa0c0`
- `0xa6b0`
- `0xa7f0`
- `0xaac0`

## callees

- `0x10`
- `0x70`
- `0x1a0`

## pseudocode

```c

```

## disassembly

```asm
0x1a0  ldarg.0
0x1a1  ldarg.1
0x1a2  call     instance class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Application.WebServices.ParameterBag::GetNode(string name)
0x1a7  dup
0x1a8  brtrue.s loc_1B6
0x1aa  ldstr    aExpectedAParam// "Expected a parameter bag."
0x1af  ldarg.1
0x1b0  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x1b5  throw
0x1b6  ldarg.1
0x1b7  newobj   instance void Microsoft.Crm.Application.WebServices.ParameterBag::.ctor(class [System.Xml]System.Xml.XmlNode parameterBag, string name)
0x1bc  ret
```
