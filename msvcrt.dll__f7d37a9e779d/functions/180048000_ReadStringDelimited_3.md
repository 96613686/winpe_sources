# ReadStringDelimited_3

- ea: `0x180048000`
- end: `0x18004817c`
- name: `ReadStringDelimited_3`
- size: `380`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180048248`

## callees

- `0x180007f00`
- `0x18001d300`
- `0x18001d568`
- `0x180047e44`
- `0x180048000`
- `0x18007d030`

## pseudocode

```c
__int64 __fastcall ReadStringDelimited_3(
        char a1,
        unsigned __int16 **a2,
        wint_t *a3,
        _DWORD *a4,
        char **a5,
        int a6,
        __int64 a7,
        _DWORD *a8)
{
  _BYTE *v12; // rax
  _BYTE *v13; // rdi
  unsigned __int16 *v15; // rcx
  unsigned __int16 *v16; // r9
  unsigned __int16 v17; // ax
  unsigned __int16 *v18; // r9
  unsigned __int16 v19; // r8
  unsigned __int16 v20; // cx
  unsigned __int16 v21; // r10
  unsigned __int16 v22; // ax
  unsigned int String_3; // ebx

  v12 = (_BYTE *)malloc_crt(0x2000u);
  v13 = v12;
  if ( v12 )
  {
    memset_thunk_772440563353939046(v12, 0, 0x2000u);
    v15 = *a2;
    v16 = *a2 + 1;
    *a2 = v16;
    if ( *v16 == 94 )
    {
      v17 = v16[1];
      a1 |= 8u;
    }
    else
    {
      v17 = *v16;
    }
    if ( *v16 != 94 )
      v16 = v15;
    v18 = v16 + 1;
    if ( v17 != 93 )
      goto LABEL_18;
    v19 = 93;
    v13[11] = 32;
    ++v18;
    while ( 1 )
    {
      v22 = *v18;
      if ( *v18 == 93 )
        break;
      ++v18;
      if ( v22 == 45 && v19 && (v20 = *v18, *v18 != 93) )
      {
        ++v18;
        v21 = v20;
        if ( v19 >= v20 )
        {
          v21 = v19;
          v19 = v20;
        }
        while ( v19 <= v21 )
        {
          v13[(unsigned __int64)v19 >> 3] |= 1 << (v19 & 7);
          ++v19;
        }
LABEL_18:
        v19 = 0;
      }
      else
      {
        v19 = v22;
        v13[(unsigned __int64)v22 >> 3] |= 1 << (v22 & 7);
      }
    }
    *a2 = v18;
    String_3 = ReadString_3(a1, (__int64)v13, a3, a4, a5, a6, a7, a8);
    free(v13);
    return String_3;
  }
  else
  {
    *errno() = 12;
    return 12;
  }
}

```

## disassembly

```asm
0x180048000  push    rbx
0x180048002  push    rbp
0x180048003  push    rsi
0x180048004  push    rdi
0x180048005  push    r14
0x180048007  push    r15
0x180048009  sub     rsp, 48h
0x18004800d  mov     ebx, ecx
0x18004800f  mov     rbp, r9
0x180048012  mov     ecx, 2000h; Size
0x180048017  mov     r14, r8
0x18004801a  mov     rsi, rdx
0x18004801d  call    _malloc_crt
0x180048022  xor     r15d, r15d
0x180048025  mov     rdi, rax
0x180048028  test    rax, rax
0x18004802b  jnz     short loc_18004803E
0x18004802d  call    _errno
0x180048032  lea     ecx, [rdi+0Ch]
0x180048035  mov     [rax], ecx
0x180048037  mov     eax, ecx
0x180048039  jmp     loc_18004816F
0x18004803e  xor     edx, edx; Val
0x180048040  mov     r8d, 2000h; Size
0x180048046  mov     rcx, rdi; void *
0x180048049  call    memset$thunk$772440563353939046
0x18004804e  mov     rcx, [rsi]
0x180048051  mov     edx, 5Eh ; '^'
0x180048056  lea     r9, [rcx+2]
0x18004805a  mov     [rsi], r9
0x18004805d  cmp     dx, [r9]
0x180048061  jnz     short loc_18004806D
0x180048063  movzx   eax, word ptr [r9+2]
0x180048068  or      ebx, 8
0x18004806b  jmp     short loc_180048071
0x18004806d  movzx   eax, word ptr [r9]
0x180048071  cmp     dx, [r9]
0x180048075  mov     r11d, 5Dh ; ']'
0x18004807b  cmovnz  r9, rcx
0x18004807f  add     r9, 2
0x180048083  cmp     r11w, ax
0x180048087  jnz     short loc_1800480F0
0x180048089  movzx   r8d, r11w
0x18004808d  mov     byte ptr [rdi+0Bh], 20h ; ' '
0x180048091  add     r9, 2
0x180048095  jmp     short loc_180048110
0x180048097  add     r9, 2
0x18004809b  mov     ecx, 2Dh ; '-'
0x1800480a0  cmp     cx, ax
0x1800480a3  jnz     short loc_1800480F5
0x1800480a5  test    r8w, r8w
0x1800480a9  jz      short loc_1800480F5
0x1800480ab  movzx   ecx, word ptr [r9]
0x1800480af  cmp     r11w, cx
0x1800480b3  jz      short loc_1800480F5
0x1800480b5  add     r9, 2
0x1800480b9  movzx   r10d, cx
0x1800480bd  cmp     r8w, cx
0x1800480c1  cmovnb  r10w, r8w
0x1800480c6  cmovnb  r8w, cx
0x1800480cb  jmp     short loc_1800480EA
0x1800480cd  movzx   edx, r8w
0x1800480d1  shr     rdx, 3
0x1800480d5  movzx   eax, r8w
0x1800480d9  and     eax, 7
0x1800480dc  movsx   ecx, byte ptr [rdx+rdi]
0x1800480e0  bts     ecx, eax
0x1800480e3  mov     [rdx+rdi], cl
0x1800480e6  inc     r8w
0x1800480ea  cmp     r8w, r10w
0x1800480ee  jbe     short loc_1800480CD
0x1800480f0  mov     r8d, r15d
0x1800480f3  jmp     short loc_180048110
0x1800480f5  movzx   edx, ax
0x1800480f8  movzx   r8d, ax
0x1800480fc  shr     rdx, 3
0x180048100  movzx   eax, ax
0x180048103  and     eax, 7
0x180048106  movsx   ecx, byte ptr [rdx+rdi]
0x18004810a  bts     ecx, eax
0x18004810d  mov     [rdx+rdi], cl
0x180048110  movzx   eax, word ptr [r9]
0x180048114  cmp     r11w, ax
0x180048118  jnz     loc_180048097
0x18004811e  mov     rax, [rsp+78h+arg_38]
0x180048126  mov     r8, r14
0x180048129  mov     [rsp+78h+var_40], rax
0x18004812e  mov     rdx, rdi
0x180048131  mov     rax, [rsp+78h+arg_30]
0x180048139  mov     ecx, ebx
0x18004813b  mov     [rsp+78h+var_48], rax
0x180048140  mov     eax, [rsp+78h+arg_28]
0x180048147  mov     [rsp+78h+var_50], eax
0x18004814b  mov     rax, [rsp+78h+arg_20]
0x180048153  mov     [rsi], r9
0x180048156  mov     r9, rbp
0x180048159  mov     [rsp+78h+var_58], rax
0x18004815e  call    ReadString_3
0x180048163  mov     rcx, rdi; Block
0x180048166  mov     ebx, eax
0x180048168  call    free
0x18004816d  mov     eax, ebx
0x18004816f  add     rsp, 48h
0x180048173  pop     r15
0x180048175  pop     r14
0x180048177  pop     rdi
0x180048178  pop     rsi
0x180048179  pop     rbp
0x18004817a  pop     rbx
0x18004817b  retn
```
