# <>c::<ExecuteCommand>b__3_0

- ea: `0x1160`
- end: `0x1171`
- name: `<>c::<ExecuteCommand>b__3_0`
- size: `17`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x1160  ldarg.1
0x1161  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_LogicalName()
0x1166  ldstr    aOpportunity// "opportunity"
0x116b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1170  ret
```
