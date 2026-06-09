# __scrt_is_nonwritable_in_current_image

- ea: `0x1400014b8`
- end: `0x140001550`
- name: `__scrt_is_nonwritable_in_current_image`
- size: `152`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400011d0`

## callees

- `0x1400014b8`

## pseudocode

```c
bool __fastcall _scrt_is_nonwritable_in_current_image(__int64 a1)
{
  _DWORD *v2; // rcx
  unsigned __int64 v3; // r8
  _DWORD *v4; // rdx
  _DWORD *v5; // r9
  unsigned __int64 v6; // rcx

  if ( LOWORD(MEMORY[0x140000000].unused) != 23117 )
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
0x1400014b8  sub     rsp, 18h
0x1400014bc  mov     r8, rcx
0x1400014bf  mov     eax, 5A4Dh
0x1400014c4  cmp     cs:140000000h, ax
0x1400014cb  jnz     short loc_140001545
0x1400014cd  movsxd  rcx, dword ptr cs:14000003Ch
0x1400014d4  lea     rdx, cs:140000000h
0x1400014db  add     rcx, rdx
0x1400014de  cmp     dword ptr [rcx], 4550h
0x1400014e4  jnz     short loc_140001545
0x1400014e6  mov     eax, 20Bh
0x1400014eb  cmp     [rcx+18h], ax
0x1400014ef  jnz     short loc_140001545
0x1400014f1  sub     r8, rdx
0x1400014f4  movzx   edx, word ptr [rcx+14h]
0x1400014f8  add     rdx, 18h
0x1400014fc  add     rdx, rcx
0x1400014ff  movzx   eax, word ptr [rcx+6]
0x140001503  lea     rcx, [rax+rax*4]
0x140001507  lea     r9, [rdx+rcx*8]
0x14000150b  mov     [rsp+18h+var_18], rdx
0x14000150f  cmp     rdx, r9
0x140001512  jz      short loc_14000152C
0x140001514  mov     ecx, [rdx+0Ch]
0x140001517  cmp     r8, rcx
0x14000151a  jb      short loc_140001526
0x14000151c  mov     eax, [rdx+8]
0x14000151f  add     eax, ecx
0x140001521  cmp     r8, rax
0x140001524  jb      short loc_14000152E
0x140001526  add     rdx, 28h ; '('
0x14000152a  jmp     short loc_14000150B
0x14000152c  xor     edx, edx
0x14000152e  test    rdx, rdx
0x140001531  jnz     short loc_140001537
0x140001533  xor     al, al
0x140001535  jmp     short loc_14000154B
0x140001537  cmp     dword ptr [rdx+24h], 0
0x14000153b  jge     short loc_140001541
0x14000153d  xor     al, al
0x14000153f  jmp     short loc_14000154B
0x140001541  mov     al, 1
0x140001543  jmp     short loc_14000154B
0x140001545  xor     al, al
0x140001547  jmp     short loc_14000154B
0x140001549  xor     al, al
0x14000154b  add     rsp, 18h
0x14000154f  retn
0x140003340  push    rbp
0x140003342  mov     rbp, rdx
0x140003345  mov     rax, [rcx]
0x140003348  xor     ecx, ecx
0x14000334a  cmp     dword ptr [rax], 0C0000005h
0x140003350  setz    cl
0x140003353  mov     eax, ecx
0x140003355  pop     rbp
0x140003356  retn
```
