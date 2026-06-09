# DecompressQueryFmt

- ea: `0x180007020`
- end: `0x180007074`
- name: `DecompressQueryFmt`
- size: `84`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180006d14`
- `0x180006dd8`
- `0x180006e8c`

## callees

- `0x180007020`
- `0x1800072d0`

## pseudocode

```c
__int64 __fastcall DecompressQueryFmt(__int64 a1, __int64 a2)
{
  if ( a2
    && (unsigned int)ValidateBitmapInfoHeader(a2)
    && ((*(_WORD *)(a2 + 14) - 8) & 0xFFF7) == 0
    && *(_WORD *)(a2 + 12) == 1
    && (*(_DWORD *)(a2 + 16) == 1129730893 || *(_DWORD *)(a2 + 16) == 1296126531) )
  {
    return 0;
  }
  else
  {
    return 4294967294LL;
  }
}

```

## disassembly

```asm
0x180007020  push    rbx
0x180007022  sub     rsp, 20h
0x180007026  mov     rbx, rdx
0x180007029  test    rdx, rdx
0x18000702c  jz      short loc_180007069
0x18000702e  mov     rcx, rdx
0x180007031  call    ValidateBitmapInfoHeader
0x180007036  test    eax, eax
0x180007038  jz      short loc_180007069
0x18000703a  movzx   eax, word ptr [rbx+0Eh]
0x18000703e  mov     ecx, 0FFF7h
0x180007043  sub     ax, 8
0x180007047  test    cx, ax
0x18000704a  jnz     short loc_180007069
0x18000704c  cmp     word ptr [rbx+0Ch], 1
0x180007051  jnz     short loc_180007069
0x180007053  cmp     dword ptr [rbx+10h], 4356534Dh
0x18000705a  jz      short loc_180007065
0x18000705c  cmp     dword ptr [rbx+10h], 4D415243h
0x180007063  jnz     short loc_180007069
0x180007065  xor     eax, eax
0x180007067  jmp     short loc_18000706E
0x180007069  mov     eax, 0FFFFFFFEh
0x18000706e  add     rsp, 20h
0x180007072  pop     rbx
0x180007073  retn
```
