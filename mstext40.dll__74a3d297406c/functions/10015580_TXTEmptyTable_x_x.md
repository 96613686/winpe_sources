# TXTEmptyTable(x,x)

- ea: `0x10015580`
- end: `0x1001559e`
- name: `_TXTEmptyTable@8`
- size: `30`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x10014460`

## pseudocode

```c
int __stdcall TXTEmptyTable(int a1, int a2)
{
  return ISAMDBFindCursor(a1, a2) != 0 ? -5410 : -1310;
}

```

## disassembly

```asm
0x10015580  push    [esp+arg_4]
0x10015584  push    [esp+4+arg_0]
0x10015588  call    _ISAMDBFindCursor@8; ISAMDBFindCursor(x,x)
0x1001558d  neg     eax
0x1001558f  sbb     eax, eax
0x10015591  and     eax, 0FFFFEFFCh
0x10015596  add     eax, 0FFFFFAE2h
0x1001559b  retn    8
```
