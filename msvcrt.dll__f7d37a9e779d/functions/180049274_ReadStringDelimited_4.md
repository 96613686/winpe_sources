# ReadStringDelimited_4

- ea: `0x180049274`
- end: `0x1800493fd`
- name: `ReadStringDelimited_4`
- size: `393`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180049404`

## callees

- `0x180007f00`
- `0x18001d300`
- `0x18001d568`
- `0x180049070`
- `0x180049274`
- `0x18007d030`

## pseudocode

```c
__int64 __fastcall ReadStringDelimited_4(
        char a1,
        unsigned __int16 **a2,
        wint_t *a3,
        _DWORD *a4,
        char **a5,
        int a6,
        rsize_t SizeConverted,
        int a8,
        _DWORD *a9)
{
  _BYTE *v13; // rax
  _BYTE *v14; // rdi
  unsigned __int16 *v16; // rcx
  unsigned __int16 *v17; // r9
  unsigned __int16 v18; // ax
  unsigned __int16 *v19; // r9
  unsigned __int16 v20; // r8
  unsigned __int16 v21; // cx
  unsigned __int16 v22; // r10
  unsigned __int16 v23; // ax
  unsigned int String_4; // ebx

  v13 = (_BYTE *)malloc_crt(0x2000u);
  v14 = v13;
  if ( v13 )
  {
    memset_thunk_772440563353939046(v13, 0, 0x2000u);
    v16 = *a2;
    v17 = *a2 + 1;
    *a2 = v17;
    if ( *v17 == 94 )
    {
      v18 = v17[1];
      a1 |= 8u;
    }
    else
    {
      v18 = *v17;
    }
    if ( *v17 != 94 )
      v17 = v16;
    v19 = v17 + 1;
    if ( v18 != 93 )
      goto LABEL_18;
    v20 = 93;
    v14[11] = 32;
    ++v19;
    while ( 1 )
    {
      v23 = *v19;
      if ( *v19 == 93 )
        break;
      ++v19;
      if ( v23 == 45 && v20 && (v21 = *v19, *v19 != 93) )
      {
        ++v19;
        v22 = v21;
        if ( v20 >= v21 )
        {
          v22 = v20;
          v20 = v21;
        }
        while ( v20 <= v22 )
        {
          v14[(unsigned __int64)v20 >> 3] |= 1 << (v20 & 7);
          ++v20;
        }
LABEL_18:
        v20 = 0;
      }
      else
      {
        v20 = v23;
        v14[(unsigned __int64)v23 >> 3] |= 1 << (v23 & 7);
      }
    }
    *a2 = v19;
    String_4 = ReadString_4(a1, (__int64)v14, a3, a4, a5, a6, SizeConverted, a8, a9);
    free(v14);
    return String_4;
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
0x180049274  push    rbx
0x180049276  push    rbp
0x180049277  push    rsi
0x180049278  push    rdi
0x180049279  push    r14
0x18004927b  push    r15
0x18004927d  sub     rsp, 58h
0x180049281  mov     ebx, ecx
0x180049283  mov     rbp, r9
0x180049286  mov     ecx, 2000h; Size
0x18004928b  mov     r14, r8
0x18004928e  mov     rsi, rdx
0x180049291  call    _malloc_crt
0x180049296  xor     r15d, r15d
0x180049299  mov     rdi, rax
0x18004929c  test    rax, rax
0x18004929f  jnz     short loc_1800492B2
0x1800492a1  call    _errno
0x1800492a6  lea     ecx, [rdi+0Ch]
0x1800492a9  mov     [rax], ecx
0x1800492ab  mov     eax, ecx
0x1800492ad  jmp     loc_1800493F0
0x1800492b2  xor     edx, edx; Val
0x1800492b4  mov     r8d, 2000h; Size
0x1800492ba  mov     rcx, rdi; void *
0x1800492bd  call    memset$thunk$772440563353939046
0x1800492c2  mov     rcx, [rsi]
0x1800492c5  mov     edx, 5Eh ; '^'
0x1800492ca  lea     r9, [rcx+2]
0x1800492ce  mov     [rsi], r9
0x1800492d1  cmp     dx, [r9]
0x1800492d5  jnz     short loc_1800492E1
0x1800492d7  movzx   eax, word ptr [r9+2]
0x1800492dc  or      ebx, 8
0x1800492df  jmp     short loc_1800492E5
0x1800492e1  movzx   eax, word ptr [r9]
0x1800492e5  cmp     dx, [r9]
0x1800492e9  mov     r11d, 5Dh ; ']'
0x1800492ef  cmovnz  r9, rcx
0x1800492f3  add     r9, 2
0x1800492f7  cmp     r11w, ax
0x1800492fb  jnz     short loc_180049364
0x1800492fd  movzx   r8d, r11w
0x180049301  mov     byte ptr [rdi+0Bh], 20h ; ' '
0x180049305  add     r9, 2
0x180049309  jmp     short loc_180049384
0x18004930b  add     r9, 2
0x18004930f  mov     ecx, 2Dh ; '-'
0x180049314  cmp     cx, ax
0x180049317  jnz     short loc_180049369
0x180049319  test    r8w, r8w
0x18004931d  jz      short loc_180049369
0x18004931f  movzx   ecx, word ptr [r9]
0x180049323  cmp     r11w, cx
0x180049327  jz      short loc_180049369
0x180049329  add     r9, 2
0x18004932d  movzx   r10d, cx
0x180049331  cmp     r8w, cx
0x180049335  cmovnb  r10w, r8w
0x18004933a  cmovnb  r8w, cx
0x18004933f  jmp     short loc_18004935E
0x180049341  movzx   edx, r8w
0x180049345  shr     rdx, 3
0x180049349  movzx   eax, r8w
0x18004934d  and     eax, 7
0x180049350  movsx   ecx, byte ptr [rdx+rdi]
0x180049354  bts     ecx, eax
0x180049357  mov     [rdx+rdi], cl
0x18004935a  inc     r8w
0x18004935e  cmp     r8w, r10w
0x180049362  jbe     short loc_180049341
0x180049364  mov     r8d, r15d
0x180049367  jmp     short loc_180049384
0x180049369  movzx   edx, ax
0x18004936c  movzx   r8d, ax
0x180049370  shr     rdx, 3
0x180049374  movzx   eax, ax
0x180049377  and     eax, 7
0x18004937a  movsx   ecx, byte ptr [rdx+rdi]
0x18004937e  bts     ecx, eax
0x180049381  mov     [rdx+rdi], cl
0x180049384  movzx   eax, word ptr [r9]
0x180049388  cmp     r11w, ax
0x18004938c  jnz     loc_18004930B
0x180049392  mov     rax, [rsp+88h+arg_40]
0x18004939a  mov     r8, r14; int
0x18004939d  mov     [rsp+88h+var_48], rax; __int64
0x1800493a2  mov     rdx, rdi; int
0x1800493a5  mov     rax, qword ptr [rsp+88h+arg_38]
0x1800493ad  mov     ecx, ebx; int
0x1800493af  mov     qword ptr [rsp+88h+var_50], rax; int
0x1800493b4  mov     rax, [rsp+88h+arg_30]
0x1800493bc  mov     qword ptr [rsp+88h+SizeConverted], rax; SizeConverted
0x1800493c1  mov     eax, [rsp+88h+arg_28]
0x1800493c8  mov     [rsp+88h+var_60], eax; int
0x1800493cc  mov     rax, [rsp+88h+arg_20]
0x1800493d4  mov     [rsi], r9
0x1800493d7  mov     r9, rbp; int
0x1800493da  mov     [rsp+88h+var_68], rax; __int64
0x1800493df  call    ReadString_4
0x1800493e4  mov     rcx, rdi; Block
0x1800493e7  mov     ebx, eax
0x1800493e9  call    free
0x1800493ee  mov     eax, ebx
0x1800493f0  add     rsp, 58h
0x1800493f4  pop     r15
0x1800493f6  pop     r14
0x1800493f8  pop     rdi
0x1800493f9  pop     rsi
0x1800493fa  pop     rbp
0x1800493fb  pop     rbx
0x1800493fc  retn
```
