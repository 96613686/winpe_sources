# QDIResetDecompression

- ea: `0x180015d84`
- end: `0x180015dcb`
- name: `QDIResetDecompression`
- size: `71`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000936c`

## callees

- `0x180015d84`
- `0x180016070`

## pseudocode

```c
__int64 __fastcall QDIResetDecompression(__int64 a1)
{
  char v2; // dl

  if ( *(_DWORD *)a1 != 1128875089 )
    return 2;
  v2 = *(_BYTE *)(a1 + 396);
  *(_QWORD *)(a1 + 360) = *(_QWORD *)(a1 + 344);
  *(_DWORD *)(a1 + 368) = 0;
  *(_DWORD *)(a1 + 400) = 0;
  Lz_Init((_DWORD *)a1, v2);
  return 0;
}

```

## disassembly

```asm
0x180015d84  sub     rsp, 28h
0x180015d88  cmp     dword ptr [rcx], 43494451h
0x180015d8e  jz      short loc_180015D97
0x180015d90  mov     eax, 2
0x180015d95  jmp     short loc_180015DC6
0x180015d97  mov     rax, [rcx+158h]
0x180015d9e  mov     dl, [rcx+18Ch]
0x180015da4  mov     [rcx+168h], rax
0x180015dab  mov     dword ptr [rcx+170h], 0
0x180015db5  mov     dword ptr [rcx+190h], 0
0x180015dbf  call    Lz_Init
0x180015dc4  xor     eax, eax
0x180015dc6  add     rsp, 28h
0x180015dca  retn
```
