# build_tree

- ea: `0x18000ced0`
- end: `0x18000d222`
- name: `build_tree`
- size: `850`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18000cd6c`
- `0x18000de3c`

## callees

- `0x18000ced0`
- `0x18000d230`
- `0x18000df78`
- `0x18000e150`

## pseudocode

```c
__int64 __fastcall build_tree(_DWORD *a1, __int64 *a2)
{
  int v2; // r14d
  __int64 v4; // rdi
  __int64 v6; // r9
  int v7; // r13d
  __int64 v8; // rdx
  int v9; // edx
  int i; // r10d
  int v11; // eax
  __int64 v12; // r8
  int v13; // r8d
  __int64 v14; // rcx
  int v15; // r15d
  __int64 v16; // rsi
  __int64 v17; // r11
  int v18; // eax
  int v19; // ecx
  bool v20; // cc
  __int64 v21; // r8
  __int64 v22; // r9
  unsigned __int16 v23; // dx
  __int64 v24; // r8
  unsigned __int16 v25; // ax
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // r9
  int v29; // r10d
  __int64 v30; // rcx
  __int64 v31; // r8
  __int64 v32; // rcx
  _WORD *v33; // r11
  unsigned __int8 v34; // dl
  char *v35; // rsi
  int v36; // ecx
  int v37; // eax
  bool v38; // cc
  __int64 v39; // r8
  __int64 v40; // r9
  unsigned __int16 v41; // dx
  __int64 v42; // r8
  __int64 v43; // rax
  __int64 v44; // rax
  __int64 v45; // rcx
  __int64 v47; // rcx
  int v48; // ecx
  int v49; // r8d
  __int64 v50; // rax
  __int64 v51; // rcx

  v2 = *((_DWORD *)a2 + 7);
  v4 = *a2;
  v6 = a2[1];
  v7 = -1;
  v8 = 0;
  a1[22] = 0;
  for ( a1[23] = 573; (int)v8 < v2; v8 = (unsigned int)(v8 + 1) )
  {
    if ( *(_WORD *)(v4 + 4 * v8) )
    {
      v47 = (int)a1[22];
      v7 = v8;
      a1[22] = v47 + 1;
      a1[v47 + 1060] = v8;
      *((_BYTE *)a1 + v8 + 6528) = 0;
    }
    else
    {
      *(_WORD *)(v4 + 4 * v8 + 2) = 0;
    }
  }
  v9 = a1[22];
  for ( i = 1; v9 < 2; v7 = v49 )
  {
    v48 = v7 + 1;
    v49 = v7 + 1;
    if ( v7 >= 2 )
    {
      v49 = v7;
      v48 = 0;
    }
    a1[22] = v9 + 1;
    a1[v9 + 1060] = v48;
    v50 = v48;
    v51 = 4LL * v48;
    *(_WORD *)(v51 + v4) = 1;
    *((_BYTE *)a1 + v50 + 6528) = 0;
    --a1[26];
    if ( v6 )
      a1[27] -= *(unsigned __int16 *)(v51 + v6 + 2);
    v9 = a1[22];
  }
  *((_DWORD *)a2 + 9) = v7;
  v11 = a1[22] / 2;
  v12 = (unsigned int)v11;
  if ( v11 >= 1 )
  {
    do
    {
      pqdownheap(a1, v4, v12, v6);
      v12 = (unsigned int)(v13 - 1);
    }
    while ( (int)v12 >= 1 );
    i = 1;
  }
  do
  {
    v14 = (int)a1[22];
    v15 = v2;
    v16 = (int)a1[1060];
    v17 = (int)a1[v14 + 1059];
    v18 = v14 - 1;
    v19 = 2;
    a1[1060] = v17;
    a1[22] = v18;
    v20 = v18 > 2;
    if ( v18 >= 2 )
    {
      do
      {
        if ( v20 )
        {
          v21 = (int)a1[v19 + 1060];
          v22 = (int)a1[v19 + 1059];
          v23 = *(_WORD *)(v4 + 4 * v21);
          if ( v23 < *(_WORD *)(v4 + 4 * v22)
            || v23 == *(_WORD *)(v4 + 4 * v22) && *((_BYTE *)a1 + v21 + 6528) <= *((_BYTE *)a1 + v22 + 6528) )
          {
            ++v19;
          }
        }
        v24 = (int)a1[v19 + 1059];
        v25 = *(_WORD *)(v4 + 4 * v17);
        if ( v25 < *(_WORD *)(v4 + 4 * v24)
          || v25 == *(_WORD *)(v4 + 4 * v24) && *((_BYTE *)a1 + v17 + 6528) <= *((_BYTE *)a1 + v24 + 6528) )
        {
          break;
        }
        v26 = i;
        i = v19;
        v19 *= 2;
        a1[v26 + 1059] = v24;
        LODWORD(v26) = a1[22];
        v20 = v19 < (int)v26;
      }
      while ( v19 <= (int)v26 );
    }
    v27 = i;
    v28 = 4 * v16;
    v29 = 1;
    a1[v27 + 1059] = v17;
    v30 = (int)a1[23];
    v31 = (int)a1[1060];
    a1[23] = v30 - 1;
    a1[v30 + 1058] = v16;
    v32 = (int)a1[23];
    a1[23] = v32 - 1;
    a1[v32 + 1058] = v31;
    *(_WORD *)(v4 + 4LL * v2) = *(_WORD *)(4 * v16 + v4) + *(_WORD *)(v4 + 4 * v31);
    v33 = (_WORD *)(v4 + 4LL * v2);
    v34 = *((_BYTE *)a1 + v16 + 6528);
    v35 = (char *)a1 + v2;
    v36 = 2;
    if ( v34 < *((_BYTE *)a1 + v31 + 6528) )
      v34 = *((_BYTE *)a1 + v31 + 6528);
    v35[6528] = v34 + 1;
    *(_WORD *)(v4 + 4 * v31 + 2) = v2;
    *(_WORD *)(v28 + v4 + 2) = v2;
    a1[1060] = v2++;
    v37 = a1[22];
    v38 = v37 > 2;
    if ( v37 >= 2 )
    {
      do
      {
        if ( v38 )
        {
          v39 = (int)a1[v36 + 1060];
          v40 = (int)a1[v36 + 1059];
          v41 = *(_WORD *)(v4 + 4 * v39);
          if ( v41 < *(_WORD *)(v4 + 4 * v40)
            || v41 == *(_WORD *)(v4 + 4 * v40) && *((_BYTE *)a1 + v39 + 6528) <= *((_BYTE *)a1 + v40 + 6528) )
          {
            ++v36;
          }
        }
        v42 = (int)a1[v36 + 1059];
        if ( *v33 < *(_WORD *)(v4 + 4 * v42)
          || *v33 == *(_WORD *)(v4 + 4 * v42) && (unsigned __int8)v35[6528] <= *((_BYTE *)a1 + v42 + 6528) )
        {
          break;
        }
        v43 = v29;
        v29 = v36;
        v36 *= 2;
        a1[v43 + 1059] = v42;
        LODWORD(v43) = a1[22];
        v38 = v36 < (int)v43;
      }
      while ( v36 <= (int)v43 );
    }
    v44 = v29;
    i = 1;
    a1[v44 + 1059] = v15;
  }
  while ( (int)a1[22] >= 2 );
  v45 = (int)a1[23];
  a1[23] = v45 - 1;
  a1[v45 + 1058] = a1[1060];
  gen_bitlen(a1, a2);
  return gen_codes(a1, v4, (unsigned int)v7);
}

```

## disassembly

```asm
0x18000ced0  push    rbx
0x18000ced2  push    rbp
0x18000ced3  push    rsi
0x18000ced4  push    rdi
0x18000ced5  push    r12
0x18000ced7  push    r13
0x18000ced9  push    r14
0x18000cedb  push    r15
0x18000cedd  sub     rsp, 28h
0x18000cee1  mov     r14d, [rdx+1Ch]
0x18000cee5  mov     r12, rdx
0x18000cee8  mov     rdi, [rdx]
0x18000ceeb  mov     rbx, rcx
0x18000ceee  mov     r9, [rdx+8]
0x18000cef2  mov     r13d, 0FFFFFFFFh
0x18000cef8  xor     edx, edx
0x18000cefa  mov     dword ptr [rcx+58h], 0
0x18000cf01  mov     dword ptr [rcx+5Ch], 23Dh
0x18000cf08  test    r14d, r14d
0x18000cf0b  jle     short loc_18000CF29
0x18000cf0d  nop     dword ptr [rax]
0x18000cf10  cmp     word ptr [rdi+rdx*4], 0
0x18000cf15  jnz     loc_18000D16A
0x18000cf1b  xor     eax, eax
0x18000cf1d  mov     [rdi+rdx*4+2], ax
0x18000cf22  inc     edx
0x18000cf24  cmp     edx, r14d
0x18000cf27  jl      short loc_18000CF10
0x18000cf29  mov     edx, [rbx+58h]
0x18000cf2c  mov     r10d, 1
0x18000cf32  cmp     edx, 2
0x18000cf35  jl      loc_18000D1C1
0x18000cf3b  mov     [r12+24h], r13d
0x18000cf40  mov     eax, [rbx+58h]
0x18000cf43  cdq
0x18000cf44  sub     eax, edx
0x18000cf46  sar     eax, 1
0x18000cf48  mov     r8d, eax
0x18000cf4b  cmp     eax, r10d
0x18000cf4e  jl      short loc_18000CF70
0x18000cf50  mov     rdx, rdi
0x18000cf53  mov     rcx, rbx
0x18000cf56  call    pqdownheap
0x18000cf5b  dec     r8d
0x18000cf5e  cmp     r8d, 1
0x18000cf62  jge     short loc_18000CF50
0x18000cf64  mov     r10d, 1
0x18000cf6a  nop     word ptr [rax+rax+00h]
0x18000cf70  movsxd  rcx, dword ptr [rbx+58h]
0x18000cf74  mov     r15d, r14d
0x18000cf77  movsxd  rsi, dword ptr [rbx+1090h]
0x18000cf7e  movsxd  r11, dword ptr [rbx+rcx*4+108Ch]
0x18000cf86  lea     eax, [rcx-1]
0x18000cf89  mov     ecx, 2
0x18000cf8e  mov     [rbx+1090h], r11d
0x18000cf95  mov     [rbx+58h], eax
0x18000cf98  cmp     ecx, eax
0x18000cf9a  jg      short loc_18000D008
0x18000cf9c  jge     short loc_18000CFD4
0x18000cf9e  movsxd  rax, ecx
0x18000cfa1  movsxd  r8, dword ptr [rbx+rax*4+1090h]
0x18000cfa9  movsxd  r9, dword ptr [rbx+rax*4+108Ch]
0x18000cfb1  movzx   edx, word ptr [rdi+r8*4]
0x18000cfb6  cmp     dx, [rdi+r9*4]
0x18000cfbb  jb      short loc_18000CFD2
0x18000cfbd  jnz     short loc_18000CFD4
0x18000cfbf  movzx   eax, byte ptr [r9+rbx+1980h]
0x18000cfc8  cmp     [r8+rbx+1980h], al
0x18000cfd0  ja      short loc_18000CFD4
0x18000cfd2  inc     ecx
0x18000cfd4  movsxd  rax, ecx
0x18000cfd7  movsxd  r8, dword ptr [rbx+rax*4+108Ch]
0x18000cfdf  movzx   eax, word ptr [rdi+r11*4]
0x18000cfe4  cmp     ax, [rdi+r8*4]
0x18000cfe9  jb      short loc_18000D008
0x18000cfeb  jz      loc_18000D18B
0x18000cff1  movsxd  rax, r10d
0x18000cff4  mov     r10d, ecx
0x18000cff7  add     ecx, ecx
0x18000cff9  mov     [rbx+rax*4+108Ch], r8d
0x18000d001  mov     eax, [rbx+58h]
0x18000d004  cmp     ecx, eax
0x18000d006  jle     short loc_18000CF9C
0x18000d008  movsxd  rax, r10d
0x18000d00b  lea     r9, ds:0[rsi*4]
0x18000d013  mov     r10d, 1
0x18000d019  mov     [rbx+rax*4+108Ch], r11d
0x18000d021  movsxd  rdx, dword ptr [rbx+1090h]
0x18000d028  movsxd  rcx, dword ptr [rbx+5Ch]
0x18000d02c  mov     r8, rdx
0x18000d02f  lea     eax, [rcx-1]
0x18000d032  mov     [rbx+5Ch], eax
0x18000d035  mov     [rbx+rcx*4+1088h], esi
0x18000d03c  movsxd  rcx, dword ptr [rbx+5Ch]
0x18000d040  lea     eax, [rcx-1]
0x18000d043  mov     [rbx+5Ch], eax
0x18000d046  mov     [rbx+rcx*4+1088h], edx
0x18000d04d  movzx   eax, word ptr [rdi+rdx*4]
0x18000d051  add     ax, [r9+rdi]
0x18000d056  movsxd  rcx, r14d
0x18000d059  mov     [rdi+rcx*4], ax
0x18000d05d  lea     r11, [rdi+rcx*4]
0x18000d061  movzx   eax, byte ptr [rbx+rdx+1980h]
0x18000d069  movzx   edx, byte ptr [rbx+rsi+1980h]
0x18000d071  cmp     dl, al
0x18000d073  lea     rsi, [rbx+rcx]
0x18000d077  mov     ecx, 2
0x18000d07c  cmovb   edx, eax
0x18000d07f  inc     dl
0x18000d081  mov     [rsi+1980h], dl
0x18000d087  mov     [rdi+r8*4+2], r14w
0x18000d08d  mov     [r9+rdi+2], r14w
0x18000d093  mov     [rbx+1090h], r14d
0x18000d09a  inc     r14d
0x18000d09d  mov     eax, [rbx+58h]
0x18000d0a0  cmp     ecx, eax
0x18000d0a2  jg      short loc_18000D10F
0x18000d0a4  jge     short loc_18000D0DC
0x18000d0a6  movsxd  rax, ecx
0x18000d0a9  movsxd  r8, dword ptr [rbx+rax*4+1090h]
0x18000d0b1  movsxd  r9, dword ptr [rbx+rax*4+108Ch]
0x18000d0b9  movzx   edx, word ptr [rdi+r8*4]
0x18000d0be  cmp     dx, [rdi+r9*4]
0x18000d0c3  jb      short loc_18000D0DA
0x18000d0c5  jnz     short loc_18000D0DC
0x18000d0c7  movzx   eax, byte ptr [r9+rbx+1980h]
0x18000d0d0  cmp     [r8+rbx+1980h], al
0x18000d0d8  ja      short loc_18000D0DC
0x18000d0da  inc     ecx
0x18000d0dc  movsxd  rax, ecx
0x18000d0df  movsxd  r8, dword ptr [rbx+rax*4+108Ch]
0x18000d0e7  movzx   eax, word ptr [r11]
0x18000d0eb  cmp     ax, [rdi+r8*4]
0x18000d0f0  jb      short loc_18000D10F
0x18000d0f2  jz      loc_18000D1A7
0x18000d0f8  movsxd  rax, r10d
0x18000d0fb  mov     r10d, ecx
0x18000d0fe  add     ecx, ecx
0x18000d100  mov     [rbx+rax*4+108Ch], r8d
0x18000d108  mov     eax, [rbx+58h]
0x18000d10b  cmp     ecx, eax
0x18000d10d  jle     short loc_18000D0A4
0x18000d10f  movsxd  rax, r10d
0x18000d112  mov     r10d, 1
0x18000d118  mov     [rbx+rax*4+108Ch], r15d
0x18000d120  cmp     dword ptr [rbx+58h], 2
0x18000d124  jge     loc_18000CF70
0x18000d12a  movsxd  rcx, dword ptr [rbx+5Ch]
0x18000d12e  mov     rdx, r12
0x18000d131  lea     eax, [rcx-1]
0x18000d134  mov     [rbx+5Ch], eax
0x18000d137  mov     eax, [rbx+1090h]
0x18000d13d  mov     [rbx+rcx*4+1088h], eax
0x18000d144  mov     rcx, rbx
0x18000d147  call    gen_bitlen
0x18000d14c  mov     r8d, r13d
0x18000d14f  mov     rdx, rdi
0x18000d152  mov     rcx, rbx
0x18000d155  add     rsp, 28h
0x18000d159  pop     r15
0x18000d15b  pop     r14
0x18000d15d  pop     r13
0x18000d15f  pop     r12
0x18000d161  pop     rdi
0x18000d162  pop     rsi
0x18000d163  pop     rbp
0x18000d164  pop     rbx
0x18000d165  jmp     gen_codes
0x18000d16a  movsxd  rcx, dword ptr [rbx+58h]
0x18000d16e  mov     r13d, edx
0x18000d171  lea     eax, [rcx+1]
0x18000d174  mov     [rbx+58h], eax
0x18000d177  mov     [rbx+rcx*4+1090h], edx
0x18000d17e  mov     byte ptr [rbx+rdx+1980h], 0
0x18000d186  jmp     loc_18000CF22
0x18000d18b  movzx   eax, byte ptr [r8+rbx+1980h]
0x18000d194  cmp     [rbx+r11+1980h], al
0x18000d19c  jbe     loc_18000D008
0x18000d1a2  jmp     loc_18000CFF1
0x18000d1a7  movzx   eax, byte ptr [r8+rbx+1980h]
0x18000d1b0  cmp     [rsi+1980h], al
0x18000d1b6  jbe     loc_18000D10F
0x18000d1bc  jmp     loc_18000D0F8
0x18000d1c1  lea     ecx, [r13+1]
0x18000d1c5  cmp     r13d, 2
0x18000d1c9  mov     r8d, ecx
0x18000d1cc  cmovge  r8d, r13d
0x18000d1d0  xor     eax, eax
0x18000d1d2  cmp     r13d, 2
0x18000d1d6  cmovge  ecx, eax
0x18000d1d9  lea     eax, [rdx+1]
0x18000d1dc  mov     [rbx+58h], eax
0x18000d1df  movsxd  rax, edx
0x18000d1e2  mov     [rbx+rax*4+1090h], ecx
0x18000d1e9  movsxd  rax, ecx
0x18000d1ec  lea     rcx, ds:0[rax*4]
0x18000d1f4  mov     [rcx+rdi], r10w
0x18000d1f9  mov     byte ptr [rbx+rax+1980h], 0
0x18000d201  dec     dword ptr [rbx+68h]
0x18000d204  test    r9, r9
0x18000d207  jz      short loc_18000D212
0x18000d209  movzx   eax, word ptr [rcx+r9+2]
0x18000d20f  sub     [rbx+6Ch], eax
0x18000d212  mov     edx, [rbx+58h]
0x18000d215  mov     r13d, r8d
0x18000d218  cmp     edx, 2
0x18000d21b  jl      short loc_18000D1C1
0x18000d21d  jmp     loc_18000CF3B
```
