# __scrt_is_nonwritable_in_current_image

- ea: `0x18000177c`
- end: `0x180001814`
- name: `__scrt_is_nonwritable_in_current_image`
- size: `152`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800010e8`

## callees

- `0x18000177c`

## pseudocode

```c
bool __fastcall _scrt_is_nonwritable_in_current_image(__int64 a1)
{
  _DWORD *v2; // rcx
  unsigned __int64 v3; // r8
  _DWORD *v4; // rdx
  _DWORD *v5; // r9
  unsigned __int64 v6; // rcx

  if ( MEMORY[0x180000000] != 23117 )
    return 0;
  v2 = (_DWORD *)(0x180000000LL + MEMORY[0x18000003C]);
  if ( *v2 != 17744 || *(_WORD *)(0x180000018LL + MEMORY[0x18000003C]) != 523 )
    return 0;
  v3 = a1 - 0x180000000LL;
  v4 = (_DWORD *)((char *)v2 + *(unsigned __int16 *)(0x180000014LL + MEMORY[0x18000003C]) + 24);
  v5 = &v4[10 * *(unsigned __int16 *)(0x180000006LL + MEMORY[0x18000003C])];
  while ( v4 != v5 )
  {
    v6 = (unsigned int)v4[3];
    if ( v3 >= v6 && v3 < (unsigned int)(v6 + v4[2]) )
      return v4 && v4[9] >= 0;
    v4 += 10;
  }
  v4 = 0;
  return v4 && v4[9] >= 0;
}

```

## disassembly

```asm
0x18000177c  sub     rsp, 18h
0x180001780  mov     r8, rcx
0x180001783  mov     eax, 5A4Dh
0x180001788  cmp     cs:180000000h, ax
0x18000178f  jnz     short loc_180001809
0x180001791  movsxd  rcx, dword ptr cs:18000003Ch
0x180001798  lea     rdx, cs:180000000h
0x18000179f  add     rcx, rdx
0x1800017a2  cmp     dword ptr [rcx], 4550h
0x1800017a8  jnz     short loc_180001809
0x1800017aa  mov     eax, 20Bh
0x1800017af  cmp     [rcx+18h], ax
0x1800017b3  jnz     short loc_180001809
0x1800017b5  sub     r8, rdx
0x1800017b8  movzx   edx, word ptr [rcx+14h]
0x1800017bc  add     rdx, 18h
0x1800017c0  add     rdx, rcx
0x1800017c3  movzx   eax, word ptr [rcx+6]
0x1800017c7  lea     rcx, [rax+rax*4]
0x1800017cb  lea     r9, [rdx+rcx*8]
0x1800017cf  mov     [rsp+18h+var_18], rdx
0x1800017d3  cmp     rdx, r9
0x1800017d6  jz      short loc_1800017F0
0x1800017d8  mov     ecx, [rdx+0Ch]
0x1800017db  cmp     r8, rcx
0x1800017de  jb      short loc_1800017EA
0x1800017e0  mov     eax, [rdx+8]
0x1800017e3  add     eax, ecx
0x1800017e5  cmp     r8, rax
0x1800017e8  jb      short loc_1800017F2
0x1800017ea  add     rdx, 28h ; '('
0x1800017ee  jmp     short loc_1800017CF
0x1800017f0  xor     edx, edx
0x1800017f2  test    rdx, rdx
0x1800017f5  jnz     short loc_1800017FB
0x1800017f7  xor     al, al
0x1800017f9  jmp     short loc_18000180F
0x1800017fb  cmp     dword ptr [rdx+24h], 0
0x1800017ff  jge     short loc_180001805
0x180001801  xor     al, al
0x180001803  jmp     short loc_18000180F
0x180001805  mov     al, 1
0x180001807  jmp     short loc_18000180F
0x180001809  xor     al, al
0x18000180b  jmp     short loc_18000180F
0x18000180d  xor     al, al
0x18000180f  add     rsp, 18h
0x180001813  retn
0x1800035b8  push    rbp
0x1800035ba  mov     rbp, rdx
0x1800035bd  mov     rax, [rcx]
0x1800035c0  xor     ecx, ecx
0x1800035c2  cmp     dword ptr [rax], 0C0000005h
0x1800035c8  setz    cl
0x1800035cb  mov     eax, ecx
0x1800035cd  pop     rbp
0x1800035ce  retn
```
