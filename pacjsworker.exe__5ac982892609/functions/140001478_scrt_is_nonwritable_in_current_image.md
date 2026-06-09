# __scrt_is_nonwritable_in_current_image

- ea: `0x140001478`
- end: `0x140001510`
- name: `__scrt_is_nonwritable_in_current_image`
- size: `152`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140001180`

## callees

- `0x140001478`

## pseudocode

```c
bool __fastcall _scrt_is_nonwritable_in_current_image(__int64 a1)
{
  _DWORD *v2; // rcx
  unsigned __int64 v3; // r8
  _DWORD *v4; // rdx
  _DWORD *v5; // r9
  unsigned __int64 v6; // rcx

  if ( MEMORY[0x140000000] != 23117 )
    return 0;
  v2 = (_DWORD *)(0x140000000LL + MEMORY[0x14000003C]);
  if ( *v2 != 17744 || *(_WORD *)(0x140000018LL + MEMORY[0x14000003C]) != 523 )
    return 0;
  v3 = a1 - 0x140000000LL;
  v4 = (_DWORD *)((char *)v2 + *(unsigned __int16 *)(0x140000014LL + MEMORY[0x14000003C]) + 24);
  v5 = &v4[10 * *(unsigned __int16 *)(0x140000006LL + MEMORY[0x14000003C])];
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
0x140001478  sub     rsp, 18h
0x14000147c  mov     r8, rcx
0x14000147f  mov     eax, 5A4Dh
0x140001484  cmp     cs:140000000h, ax
0x14000148b  jnz     short loc_140001505
0x14000148d  movsxd  rcx, dword ptr cs:14000003Ch
0x140001494  lea     rdx, cs:140000000h
0x14000149b  add     rcx, rdx
0x14000149e  cmp     dword ptr [rcx], 4550h
0x1400014a4  jnz     short loc_140001505
0x1400014a6  mov     eax, 20Bh
0x1400014ab  cmp     [rcx+18h], ax
0x1400014af  jnz     short loc_140001505
0x1400014b1  sub     r8, rdx
0x1400014b4  movzx   edx, word ptr [rcx+14h]
0x1400014b8  add     rdx, 18h
0x1400014bc  add     rdx, rcx
0x1400014bf  movzx   eax, word ptr [rcx+6]
0x1400014c3  lea     rcx, [rax+rax*4]
0x1400014c7  lea     r9, [rdx+rcx*8]
0x1400014cb  mov     [rsp+18h+var_18], rdx
0x1400014cf  cmp     rdx, r9
0x1400014d2  jz      short loc_1400014EC
0x1400014d4  mov     ecx, [rdx+0Ch]
0x1400014d7  cmp     r8, rcx
0x1400014da  jb      short loc_1400014E6
0x1400014dc  mov     eax, [rdx+8]
0x1400014df  add     eax, ecx
0x1400014e1  cmp     r8, rax
0x1400014e4  jb      short loc_1400014EE
0x1400014e6  add     rdx, 28h ; '('
0x1400014ea  jmp     short loc_1400014CB
0x1400014ec  xor     edx, edx
0x1400014ee  test    rdx, rdx
0x1400014f1  jnz     short loc_1400014F7
0x1400014f3  xor     al, al
0x1400014f5  jmp     short loc_14000150B
0x1400014f7  cmp     dword ptr [rdx+24h], 0
0x1400014fb  jge     short loc_140001501
0x1400014fd  xor     al, al
0x1400014ff  jmp     short loc_14000150B
0x140001501  mov     al, 1
0x140001503  jmp     short loc_14000150B
0x140001505  xor     al, al
0x140001507  jmp     short loc_14000150B
0x140001509  xor     al, al
0x14000150b  add     rsp, 18h
0x14000150f  retn
0x140001d60  push    rbp
0x140001d62  mov     rbp, rdx
0x140001d65  mov     rax, [rcx]
0x140001d68  xor     ecx, ecx
0x140001d6a  cmp     dword ptr [rax], 0C0000005h
0x140001d70  setz    cl
0x140001d73  mov     eax, ecx
0x140001d75  pop     rbp
0x140001d76  retn
```
