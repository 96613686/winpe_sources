# Microsoft.Crm.XmlStringParameterAttribute::IsValidXml

- ea: `0x19a0`
- end: `0x19d1`
- name: `Microsoft.Crm.XmlStringParameterAttribute::IsValidXml`
- size: `49`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x9e0`
- `0xa00`
- `0x19a0`
- `0x19e0`

## pseudocode

```c

```

## disassembly

```asm
0x19a0  ldarg.1
0x19a1  ldstr    aUndefined// "undefined"
0x19a6  ldc.i4.5
0x19a7  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x19ac  brfalse.s loc_19B5
0x19ae  ldc.i4.1
0x19af  newobj   instance void Microsoft.Crm.ParameterValidationResult::.ctor(bool isValid)
0x19b4  ret
0x19b5  nop
0x19b6  ldarg.0
0x19b7  ldarg.1
0x19b8  call     instance class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.XmlStringParameterAttribute::CreateXmlDocument(string xml)
0x19bd  pop
0x19be  leave.s  loc_19C8
0x19c0  newobj   instance void Microsoft.Crm.ParameterValidationResult::.ctor(class [mscorlib]System.Exception exception)
0x19c5  stloc.0
0x19c6  leave.s  loc_19CF
0x19c8  ldc.i4.1
0x19c9  newobj   instance void Microsoft.Crm.ParameterValidationResult::.ctor(bool isValid)
0x19ce  ret
0x19cf  ldloc.0
0x19d0  ret
```
