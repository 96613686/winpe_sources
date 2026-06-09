# WBDBOpenTable(x,x,x,x,x)

- ea: `0x10029550`
- end: `0x10029584`
- name: `_WBDBOpenTable@20`
- size: `52`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1002b3b3`
- `0x1002bee0`

## callees

- `0x10029068`
- `0x10029550`
- `0x1002aaa4`

## pseudocode

```c
int __stdcall WBDBOpenTable(int a1, int a2, _DWORD *a3, int a4, int a5)
{
  int v5; // eax

  v5 = ISAMDBFindDatabaseUser(a1, a2);
  if ( v5 )
    return OpenTable(*(_DWORD *)(v5 + 8), v5, a3, a4, a5, 0);
  else
    return -1010;
}

```

## disassembly

```asm
0x10029550  mov     edi, edi
0x10029552  push    ebp
0x10029553  mov     ebp, esp
0x10029555  mov     ecx, [ebp+arg_0]
0x10029558  mov     edx, [ebp+arg_4]
0x1002955b  call    _ISAMDBFindDatabaseUser@8; ISAMDBFindDatabaseUser(x,x)
0x10029560  test    eax, eax
0x10029562  jnz     short loc_1002956B
0x10029564  mov     eax, 0FFFFFC0Eh
0x10029569  jmp     short loc_10029580
0x1002956b  mov     ecx, [eax+8]
0x1002956e  mov     edx, eax
0x10029570  push    0
0x10029572  push    [ebp+arg_10]
0x10029575  push    [ebp+arg_C]
0x10029578  push    [ebp+arg_8]
0x1002957b  call    OpenTable
0x10029580  pop     ebp
0x10029581  retn    14h
```
