# WBDBRenameTable(x,x,x,x)

- ea: `0x10029f50`
- end: `0x10029f70`
- name: `_WBDBRenameTable@16`
- size: `32`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1002aaa4`

## pseudocode

```c
int __stdcall WBDBRenameTable(int a1, int a2, int a3, int a4)
{
  return ISAMDBFindDatabaseUser(a1, a2) != 0 ? -1001 : -1010;
}

```

## disassembly

```asm
0x10029f50  mov     edi, edi
0x10029f52  push    ebp
0x10029f53  mov     ebp, esp
0x10029f55  mov     ecx, [ebp+arg_0]
0x10029f58  mov     edx, [ebp+arg_4]
0x10029f5b  call    _ISAMDBFindDatabaseUser@8; ISAMDBFindDatabaseUser(x,x)
0x10029f60  neg     eax
0x10029f62  sbb     eax, eax
0x10029f64  and     eax, 9
0x10029f67  add     eax, 0FFFFFC0Eh
0x10029f6c  pop     ebp
0x10029f6d  retn    10h
```
