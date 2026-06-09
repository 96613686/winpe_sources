# TXDBRenameTable(x,x,x,x)

- ea: `0x10011d70`
- end: `0x10011d8c`
- name: `_TXDBRenameTable@16`
- size: `28`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x100145a0`

## pseudocode

```c
int __stdcall TXDBRenameTable(int a1, int a2, int a3, int a4)
{
  return ISAMDBFindDatabaseUser(a1, a2) != 0 ? -1001 : -1010;
}

```

## disassembly

```asm
0x10011d70  push    [esp+arg_4]
0x10011d74  push    [esp+4+arg_0]
0x10011d78  call    _ISAMDBFindDatabaseUser@8; ISAMDBFindDatabaseUser(x,x)
0x10011d7d  neg     eax
0x10011d7f  sbb     eax, eax
0x10011d81  and     eax, 9
0x10011d84  add     eax, 0FFFFFC0Eh
0x10011d89  retn    10h
```
