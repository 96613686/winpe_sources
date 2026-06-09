# Microsoft.Crm.Asynchronous.ParsedDataRow::get_Item

- ea: `0x58f0`
- end: `0x5906`
- name: `Microsoft.Crm.Asynchronous.ParsedDataRow::get_Item`
- size: `22`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x17130`
- `0x17eb0`
- `0x19370`
- `0x1ab00`
- `0x1ab90`
- `0x1b470`
- `0x1baf0`
- `0x1c810`

## callees

- `0x58f0`

## pseudocode

```c

```

## disassembly

```asm
0x58f0  ldarg.1
0x58f1  ldarg.0
0x58f2  ldfld    class Microsoft.Crm.Asynchronous.ParsedDataObject[] Microsoft.Crm.Asynchronous.ParsedDataRow::_parsedDataObjects
0x58f7  ldlen
0x58f8  conv.i4
0x58f9  bge.s    loc_5904
0x58fb  ldarg.0
0x58fc  ldfld    class Microsoft.Crm.Asynchronous.ParsedDataObject[] Microsoft.Crm.Asynchronous.ParsedDataRow::_parsedDataObjects
0x5901  ldarg.1
0x5902  ldelem.ref
0x5903  ret
0x5904  ldnull
0x5905  ret
```
