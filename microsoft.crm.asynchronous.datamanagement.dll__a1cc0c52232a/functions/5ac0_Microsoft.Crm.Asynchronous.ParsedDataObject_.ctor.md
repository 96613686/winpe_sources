# Microsoft.Crm.Asynchronous.ParsedDataObject::.ctor

- ea: `0x5ac0`
- end: `0x5adc`
- name: `Microsoft.Crm.Asynchronous.ParsedDataObject::.ctor`
- size: `28`
- prototype: ``
- caller_count: `9`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x5b10`
- `0x17130`
- `0x18840`
- `0x1ab90`
- `0x1b470`
- `0x1c810`
- `0x1fcb0`
- `0x1fea0`
- `0x1ff30`

## pseudocode

```c

```

## disassembly

```asm
0x5ac0  ldarg.0
0x5ac1  call     instance void [mscorlib]System.Object::.ctor()
0x5ac6  ldarg.0
0x5ac7  ldarg.1
0x5ac8  stfld    string Microsoft.Crm.Asynchronous.ParsedDataObject::_columnValue
0x5acd  ldarg.0
0x5ace  ldarg.2
0x5acf  stfld    string Microsoft.Crm.Asynchronous.ParsedDataObject::_columnName
0x5ad4  ldarg.0
0x5ad5  ldc.i4.0
0x5ad6  stfld    bool Microsoft.Crm.Asynchronous.ParsedDataObject::_oldColumnValuePresent
0x5adb  ret
```
