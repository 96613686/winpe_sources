# AslPathClean

- ea: `0x18000e278`
- end: `0x18000e4b7`
- name: `AslPathClean`
- size: `575`
- prototype: `__int64 __fastcall(wchar_t *String1, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800186d4`

## callees

- `0x1800027e2`
- `0x18000e278`
- `0x1800191c6`

## import_xrefs

- `msvcrt!wcschr` at `0x18000e2b9`
- `msvcrt!wcschr` at `0x18000e30b`
- `msvcrt!wcschr` at `0x18000e2b9`
- `msvcrt!wcschr` at `0x18000e30b`

## pseudocode

```c
__int64 __fastcall AslPathClean(wchar_t *String1, void *a2)
{
  unsigned __int64 v2; // rsi
  wchar_t *v6; // rbx
  unsigned __int64 v7; // rbx
  unsigned __int64 v8; // rdx
  unsigned __int64 v9; // rcx
  unsigned __int64 v10; // r8
  wchar_t v11; // ax
  unsigned __int64 v12; // rax
  wchar_t v13; // ax
  __int16 v14; // cx
  __int16 v15; // cx
  unsigned __int64 v16; // rax
  wchar_t v17; // ax

  v2 = -1;
  do
    ++v2;
  while ( String1[v2] );
  if ( v2 + 1 > 0x104 )
    return 3221225507LL;
  v6 = wcschr(String1, 0x3Au);
  if ( v6 )
    goto LABEL_10;
  v7 = 4;
  if ( !wcsncmp_0(String1, L"\\??\\", 4u) )
    goto LABEL_12;
  if ( !wcsncmp_0(String1, L"\\\\", 2u) )
  {
    v7 = 2;
    goto LABEL_12;
  }
  v6 = wcschr(String1, 0x5Cu);
  if ( v6 )
LABEL_10:
    v7 = ((unsigned __int64)((char *)v6 - (char *)String1) >> 1) + 1;
  else
    v7 = 1;
LABEL_12:
  memmove_0(a2, String1, 2 * v7);
  v8 = v7;
  v9 = v7;
  if ( v7 < v2 )
  {
    while ( 1 )
    {
      if ( String1[v9] == 92 || String1[v9] == 47 )
      {
        if ( !v8 || *((_WORD *)a2 + v8 - 1) != 92 )
          *((_WORD *)a2 + v8++) = 92;
        goto LABEL_54;
      }
      if ( String1[v9] != 46 )
        break;
      v10 = v9 + 1;
      if ( v9 + 1 == v2 )
        goto LABEL_55;
      v11 = String1[v9 + 1];
      if ( v11 == 92 || v11 == 47 )
      {
        ++v9;
        goto LABEL_54;
      }
      if ( v11 == 46 )
      {
        v12 = v9 + 2;
        if ( v9 + 2 == v2 || String1[v12] == 92 || String1[v12] == 47 )
        {
          while ( v8 >= v7 )
          {
            v14 = *((_WORD *)a2 + v8);
            *((_WORD *)a2 + v8) = 0;
            if ( v14 == 92 )
            {
              do
              {
                v15 = *((_WORD *)a2 + v8);
                *((_WORD *)a2 + v8) = 0;
                if ( v15 == 92 )
                  break;
                --v8;
              }
              while ( v8 >= v7 );
              break;
            }
            --v8;
          }
          v16 = v8 + 1;
          v9 = v10;
          if ( v8 >= v7 )
            v16 = v8;
          v8 = v16;
          goto LABEL_54;
        }
      }
      if ( String1[v9 + 2] != 92 && String1[v9 + 2] != 47 )
      {
        while ( v9 < v2 )
        {
          v17 = String1[v9];
          if ( v17 == 92 || v17 == 47 )
            goto LABEL_31;
          *((_WORD *)a2 + v8++) = v17;
          ++v9;
        }
LABEL_35:
        --v9;
      }
LABEL_54:
      if ( ++v9 >= v2 )
        goto LABEL_55;
    }
    while ( v9 < v2 )
    {
      v13 = String1[v9];
      if ( v13 == 92 || v13 == 47 )
      {
LABEL_31:
        if ( v8 >= 2 && *((_WORD *)a2 + v8 - 1) == 46 && *((_WORD *)a2 + v8 - 2) != 46 )
          --v8;
        goto LABEL_35;
      }
      *((_WORD *)a2 + v8++) = v13;
      ++v9;
    }
    goto LABEL_35;
  }
LABEL_55:
  *((_WORD *)a2 + v8) = 0;
  return 0;
}

```

## disassembly

```asm
0x18000e278  push    rbx
0x18000e27a  push    rbp
0x18000e27b  push    rsi
0x18000e27c  push    rdi
0x18000e27d  push    r12
0x18000e27f  push    r14
0x18000e281  push    r15
0x18000e283  sub     rsp, 20h
0x18000e287  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000e28b  mov     r14, rdx
0x18000e28e  xor     r15d, r15d
0x18000e291  mov     rdi, rcx
0x18000e294  inc     rsi
0x18000e297  cmp     [rcx+rsi*2], r15w
0x18000e29c  jnz     short loc_18000E294
0x18000e29e  lea     rax, [rsi+1]
0x18000e2a2  cmp     rax, 104h
0x18000e2a8  jbe     short loc_18000E2B4
0x18000e2aa  mov     eax, 0C0000023h
0x18000e2af  jmp     loc_18000E4A8
0x18000e2b4  mov     edx, 3Ah ; ':'; Ch
0x18000e2b9  call    cs:__imp_wcschr
0x18000e2bf  mov     ebp, 1
0x18000e2c4  mov     rbx, rax
0x18000e2c7  lea     r12d, [rbp+5Bh]
0x18000e2cb  test    rax, rax
0x18000e2ce  jnz     short loc_18000E319
0x18000e2d0  lea     ebx, [rax+4]
0x18000e2d3  mov     rcx, rdi; String1
0x18000e2d6  mov     r8d, ebx; MaxCount
0x18000e2d9  lea     rdx, asc_180021150; "\\??\\"
0x18000e2e0  call    wcsncmp_0
0x18000e2e5  test    eax, eax
0x18000e2e7  jz      short loc_18000E327
0x18000e2e9  lea     r8d, [rbp+1]; MaxCount
0x18000e2ed  mov     rcx, rdi; String1
0x18000e2f0  lea     rdx, asc_18002115C; "\\\\"
0x18000e2f7  call    wcsncmp_0
0x18000e2fc  test    eax, eax
0x18000e2fe  jnz     short loc_18000E305
0x18000e300  lea     ebx, [rbp+1]
0x18000e303  jmp     short loc_18000E327
0x18000e305  mov     edx, r12d; Ch
0x18000e308  mov     rcx, rdi; Str
0x18000e30b  call    cs:__imp_wcschr
0x18000e311  mov     rbx, rax
0x18000e314  test    rax, rax
0x18000e317  jz      short loc_18000E324
0x18000e319  sub     rbx, rdi
0x18000e31c  shr     rbx, 1
0x18000e31f  add     rbx, rbp
0x18000e322  jmp     short loc_18000E327
0x18000e324  mov     rbx, rbp
0x18000e327  lea     r8, [rbx+rbx]; Size
0x18000e32b  mov     rdx, rdi; Src
0x18000e32e  mov     rcx, r14; void *
0x18000e331  call    memmove_0
0x18000e336  mov     rdx, rbx
0x18000e339  mov     rcx, rbx
0x18000e33c  cmp     rbx, rsi
0x18000e33f  jnb     loc_18000E4A0
0x18000e345  mov     r10w, 2Fh ; '/'
0x18000e34a  mov     r9w, 2Eh ; '.'
0x18000e34f  cmp     [rdi+rcx*2], r12w
0x18000e354  jz      loc_18000E47F
0x18000e35a  cmp     [rdi+rcx*2], r10w
0x18000e35f  jz      loc_18000E47F
0x18000e365  cmp     [rdi+rcx*2], r9w
0x18000e36a  jnz     short loc_18000E3EB
0x18000e36c  lea     r8, [rcx+1]
0x18000e370  cmp     r8, rsi
0x18000e373  jz      loc_18000E4A0
0x18000e379  movzx   eax, word ptr [rdi+rcx*2+2]
0x18000e37e  cmp     ax, r12w
0x18000e382  jz      loc_18000E47A
0x18000e388  cmp     ax, r10w
0x18000e38c  jz      loc_18000E47A
0x18000e392  cmp     ax, r9w
0x18000e396  jnz     short loc_18000E3B3
0x18000e398  lea     rax, [rcx+2]
0x18000e39c  cmp     rax, rsi
0x18000e39f  jz      loc_18000E426
0x18000e3a5  cmp     [rdi+rax*2], r12w
0x18000e3aa  jz      short loc_18000E426
0x18000e3ac  cmp     [rdi+rax*2], r10w
0x18000e3b1  jz      short loc_18000E426
0x18000e3b3  cmp     [rdi+rcx*2+4], r12w
0x18000e3b9  jz      loc_18000E494
0x18000e3bf  cmp     [rdi+rcx*2+4], r10w
0x18000e3c5  jz      loc_18000E494
0x18000e3cb  jmp     loc_18000E473
0x18000e3d0  movzx   eax, word ptr [rdi+rcx*2]
0x18000e3d4  cmp     ax, r12w
0x18000e3d8  jz      short loc_18000E3F2
0x18000e3da  cmp     ax, r10w
0x18000e3de  jz      short loc_18000E3F2
0x18000e3e0  mov     [r14+rdx*2], ax
0x18000e3e5  add     rdx, rbp
0x18000e3e8  add     rcx, rbp
0x18000e3eb  cmp     rcx, rsi
0x18000e3ee  jb      short loc_18000E3D0
0x18000e3f0  jmp     short loc_18000E40B
0x18000e3f2  cmp     rdx, 2
0x18000e3f6  jb      short loc_18000E40B
0x18000e3f8  cmp     [r14+rdx*2-2], r9w
0x18000e3fe  jnz     short loc_18000E40B
0x18000e400  cmp     [r14+rdx*2-4], r9w
0x18000e406  jz      short loc_18000E40B
0x18000e408  sub     rdx, rbp
0x18000e40b  sub     rcx, rbp
0x18000e40e  jmp     loc_18000E494
0x18000e413  movzx   ecx, word ptr [r14+rdx*2]
0x18000e418  mov     [r14+rdx*2], r15w
0x18000e41d  cmp     cx, r12w
0x18000e421  jz      short loc_18000E42D
0x18000e423  sub     rdx, rbp
0x18000e426  cmp     rdx, rbx
0x18000e429  jnb     short loc_18000E413
0x18000e42b  jmp     short loc_18000E445
0x18000e42d  movzx   ecx, word ptr [r14+rdx*2]
0x18000e432  mov     [r14+rdx*2], r15w
0x18000e437  cmp     cx, r12w
0x18000e43b  jz      short loc_18000E445
0x18000e43d  sub     rdx, rbp
0x18000e440  cmp     rdx, rbx
0x18000e443  jnb     short loc_18000E42D
0x18000e445  cmp     rdx, rbx
0x18000e448  lea     rax, [rdx+1]
0x18000e44c  mov     rcx, r8
0x18000e44f  cmovnb  rax, rdx
0x18000e453  mov     rdx, rax
0x18000e456  jmp     short loc_18000E494
0x18000e458  movzx   eax, word ptr [rdi+rcx*2]
0x18000e45c  cmp     ax, r12w
0x18000e460  jz      short loc_18000E3F2
0x18000e462  cmp     ax, r10w
0x18000e466  jz      short loc_18000E3F2
0x18000e468  mov     [r14+rdx*2], ax
0x18000e46d  add     rdx, rbp
0x18000e470  add     rcx, rbp
0x18000e473  cmp     rcx, rsi
0x18000e476  jb      short loc_18000E458
0x18000e478  jmp     short loc_18000E40B
0x18000e47a  mov     rcx, r8
0x18000e47d  jmp     short loc_18000E494
0x18000e47f  test    rdx, rdx
0x18000e482  jz      short loc_18000E48C
0x18000e484  cmp     [r14+rdx*2-2], r12w
0x18000e48a  jz      short loc_18000E494
0x18000e48c  mov     [r14+rdx*2], r12w
0x18000e491  add     rdx, rbp
0x18000e494  add     rcx, rbp
0x18000e497  cmp     rcx, rsi
0x18000e49a  jb      loc_18000E34F
0x18000e4a0  mov     [r14+rdx*2], r15w
0x18000e4a5  mov     eax, r15d
0x18000e4a8  add     rsp, 20h
0x18000e4ac  pop     r15
0x18000e4ae  pop     r14
0x18000e4b0  pop     r12
0x18000e4b2  pop     rdi
0x18000e4b3  pop     rsi
0x18000e4b4  pop     rbp
0x18000e4b5  pop     rbx
0x18000e4b6  retn
```
