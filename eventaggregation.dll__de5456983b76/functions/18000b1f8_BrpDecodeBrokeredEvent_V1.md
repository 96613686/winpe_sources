# BrpDecodeBrokeredEvent_V1

- ea: `0x18000b1f8`
- end: `0x18000b786`
- name: `BrpDecodeBrokeredEvent_V1`
- size: `1422`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180008fc0`

## callees

- `0x18000b1f8`
- `0x18000bcd0`
- `0x18000bcf8`
- `0x18000bde9`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18000b300`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18000b574`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18000b300`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18000b574`

## pseudocode

```c
__int64 __fastcall BrpDecodeBrokeredEvent_V1(__int64 a1, unsigned __int16 a2, USHORT a3, __int64 a4, USHORT *a5)
{
  size_t v5; // r9
  USHORT v7; // cx
  unsigned __int16 v8; // r8
  int v9; // r11d
  int v10; // r12d
  unsigned __int16 v11; // si
  __int64 v12; // r14
  int v13; // r10d
  int v14; // ebx
  unsigned __int16 *v15; // rdi
  unsigned __int16 i; // r13
  _OWORD *v17; // rax
  unsigned __int64 v18; // rsi
  __int64 v19; // rcx
  const void *v20; // rbx
  size_t v21; // rax
  __int64 v22; // r9
  _DWORD *v23; // rdi
  int v24; // eax
  unsigned __int16 *v25; // rdi
  int v26; // eax
  int v27; // eax
  int v28; // eax
  size_t v29; // rbx
  __int64 v30; // r10
  __int64 v31; // r9
  __int64 v32; // rbx
  __int64 v33; // rcx
  __int64 v34; // r9
  USHORT v35; // dx
  __int64 v36; // rcx
  const void *v37; // rbx
  size_t v38; // rax
  __int64 v39; // r9
  __int64 v40; // rax
  int v41; // eax
  USHORT v42; // r11
  int v43; // r10d
  USHORT v45[2]; // [rsp+20h] [rbp-20h] BYREF
  USHORT pusResult[2]; // [rsp+24h] [rbp-1Ch] BYREF
  USHORT v47[2]; // [rsp+28h] [rbp-18h] BYREF
  unsigned __int16 v48; // [rsp+2Ch] [rbp-14h]
  int v49; // [rsp+30h] [rbp-10h]
  USHORT usAugend[2]; // [rsp+34h] [rbp-Ch]
  int v51; // [rsp+38h] [rbp-8h]
  int v52; // [rsp+3Ch] [rbp-4h]

  v5 = 0;
  v7 = 0;
  pusResult[0] = 0;
  v8 = a2;
  v51 = 0;
  LOWORD(v9) = 0;
  *(_DWORD *)usAugend = 0;
  v47[0] = 0;
  v45[0] = 0;
  v10 = 0;
  if ( a2 < 4u || !a1 || *(_BYTE *)a1 != 1 )
    return 3221225485LL;
  v11 = *(_WORD *)(a1 + 2);
  v48 = v11;
  v12 = 0;
  v13 = 0;
  v49 = 0;
  v14 = 0;
  while ( 2 )
  {
    v52 = v14;
    if ( (unsigned __int16)v14 >= 2u )
    {
      *a5 = v7;
      return (unsigned int)v5;
    }
    v15 = (unsigned __int16 *)(a1 + 4);
    for ( i = v5; i < v11; ++i )
    {
      if ( v12 )
      {
        v17 = (_OWORD *)(*(_QWORD *)(v12 + 8) + 32LL * i);
        *v17 = 0;
        v17[1] = 0;
      }
      v18 = v8;
      if ( a1 + v8 - (unsigned __int64)v15 < 2 )
        return 3221225485LL;
      v19 = *v15;
      if ( v8 < (unsigned __int64)(v19 + 2) )
        return 3221225485LL;
      if ( (_WORD)v19 )
      {
        v20 = (const void *)(v19 + a1);
        if ( v19 + a1 )
          v21 = wcsnlen((const wchar_t *)(v19 + a1), ((unsigned __int64)v8 - v19) >> 1);
        else
          v21 = v5;
        if ( UIntPtrToUShort(2 * v21 + 2, pusResult) < 0 )
          return 3221225621LL;
        if ( v12 )
        {
          v22 = 32LL * i;
          *(_QWORD *)(v22 + *(_QWORD *)(v12 + 8)) = v12 + (unsigned __int16)v10;
          memcpy_0(*(void **)(v22 + *(_QWORD *)(v12 + 8)), v20, pusResult[0]);
        }
        if ( UShortAdd(v10, pusResult[0], v45) < 0 )
          return 3221225621LL;
        v10 = v45[0];
        v13 = v49;
        LOWORD(v9) = usAugend[0];
        v8 = a2;
      }
      v23 = v15 + 1;
      if ( a1 + v18 - (unsigned __int64)v23 < 4 )
        return 3221225485LL;
      v24 = *v23;
      v25 = (unsigned __int16 *)(v23 + 1);
      if ( v12 )
        *(_DWORD *)(32LL * i + *(_QWORD *)(v12 + 8) + 8) = v24;
      if ( v24 )
      {
        v26 = v24 - 1;
        if ( v26 )
        {
          v27 = v26 - 1;
          if ( v27 )
          {
            v28 = v27 - 1;
            if ( v28 )
            {
              if ( v28 != 1 )
                return 3221225701LL;
              if ( a1 + v18 - (unsigned __int64)v25 < 2 )
                return 3221225485LL;
              v29 = *v25++;
              if ( v12 )
                *(_WORD *)(32LL * i + *(_QWORD *)(v12 + 8) + 16) = v29;
              if ( a1 + v18 - (unsigned __int64)v25 < 2 )
                return 3221225485LL;
              v30 = *v25;
              if ( v8 < (unsigned __int16)v30 )
                return 3221225485LL;
              if ( (_WORD)v30 )
              {
                if ( v12 )
                {
                  v31 = 32LL * i;
                  *(_QWORD *)(v31 + *(_QWORD *)(v12 + 8) + 24) = v12 + (unsigned __int16)v9;
                  memcpy_0(*(void **)(v31 + *(_QWORD *)(v12 + 8) + 24), (const void *)(a1 + v30), v29);
                }
                if ( UShortAdd(usAugend[0], v29, v47) < 0 )
                  return 3221225621LL;
                *(_DWORD *)usAugend = v47[0];
              }
              goto LABEL_60;
            }
            if ( a1 + v18 - (unsigned __int64)v25 < 2 )
              return 3221225485LL;
            v32 = *v25++;
            if ( v12 )
              *(_WORD *)(32LL * i + *(_QWORD *)(v12 + 8) + 16) = v32;
            if ( a1 + v18 - (unsigned __int64)v25 < 2 )
              return 3221225485LL;
            v33 = *v25;
            if ( v8 < (unsigned __int16)v33 )
              return 3221225485LL;
            if ( (_WORD)v33 )
            {
              if ( v12 )
              {
                v34 = 32LL * i;
                *(_QWORD *)(v34 + *(_QWORD *)(v12 + 8) + 24) = v12 + (unsigned __int16)v10;
                memcpy_0(*(void **)(v34 + *(_QWORD *)(v12 + 8) + 24), (const void *)(a1 + v33), 2 * v32);
              }
              v35 = 2 * v32;
              goto LABEL_58;
            }
          }
          else
          {
            if ( a1 + v18 - (unsigned __int64)v25 < 2 )
              return 3221225485LL;
            v36 = *v25;
            if ( v18 < v36 + 2 )
              return 3221225485LL;
            if ( (_WORD)v36 )
            {
              v37 = (const void *)(v36 + a1);
              if ( v36 + a1 )
                v38 = wcsnlen((const wchar_t *)(v36 + a1), ((unsigned __int64)v8 - v36) >> 1);
              else
                v38 = v5;
              if ( UIntPtrToUShort(2 * v38 + 2, pusResult) < 0 )
                return 3221225621LL;
              if ( v12 )
              {
                v39 = 32LL * i;
                *(_QWORD *)(v39 + *(_QWORD *)(v12 + 8) + 16) = v12 + (unsigned __int16)v10;
                memcpy_0(*(void **)(v39 + *(_QWORD *)(v12 + 8) + 16), v37, pusResult[0]);
              }
              v35 = pusResult[0];
LABEL_58:
              if ( UShortAdd(v10, v35, v45) < 0 )
                return 3221225621LL;
              v10 = v45[0];
            }
          }
LABEL_60:
          v13 = v49;
          v15 = v25 + 1;
          goto LABEL_67;
        }
        if ( a1 + v18 - (unsigned __int64)v25 < 8 )
          return 3221225485LL;
        v40 = *(_QWORD *)v25;
        v15 = v25 + 4;
        if ( v12 )
          *(_QWORD *)(32LL * i + *(_QWORD *)(v12 + 8) + 16) = v40;
      }
      else
      {
        if ( a1 + v18 - (unsigned __int64)v25 < 4 )
          return 3221225485LL;
        v41 = *(_DWORD *)v25;
        v15 = v25 + 2;
        if ( v12 )
          *(_DWORD *)(32LL * i + *(_QWORD *)(v12 + 8) + 16) = v41;
      }
LABEL_67:
      LOWORD(v9) = usAugend[0];
      LOWORD(v13) = v13 + 32;
      v8 = a2;
      v11 = v48;
      v49 = v13;
    }
    if ( v12 )
    {
      v7 = v51;
LABEL_78:
      HIWORD(v14) = HIWORD(v52);
      LOWORD(v14) = v52 + 1;
      continue;
    }
    break;
  }
  v45[0] = 16;
  if ( UShortAdd(0x10u, v13, v45) < 0 || UShortAdd(v45[0], v10, v45) < 0 || UShortAdd(v45[0], v42, v45) < 0 )
    return 3221225621LL;
  v7 = v45[0];
  v51 = v45[0];
  if ( a4 && a3 >= v45[0] )
  {
    *(_QWORD *)(a4 + 8) = 0;
    v12 = a4;
    *(_WORD *)a4 = 0;
    if ( v11 )
    {
      *(_WORD *)a4 = v11;
      *(_QWORD *)(a4 + 8) = a4 + 16;
    }
    v8 = a2;
    v9 = v43 + v10;
    LOWORD(v9) = v43 + v10 + 16;
    v5 = 0;
    v45[0] = v43 + 16;
    v10 = (unsigned __int16)(v43 + 16);
    *(_DWORD *)usAugend = v9;
    v47[0] = v9;
    v13 = 0;
    v49 = 0;
    goto LABEL_78;
  }
  *a5 = v45[0];
  return 3221225507LL;
}

```

## disassembly

```asm
0x18000b1f8  mov     rax, rsp
0x18000b1fb  mov     [rax+8], rbx
0x18000b1ff  mov     [rax+20h], r9
0x18000b203  mov     [rax+18h], r8w
0x18000b208  mov     [rax+10h], dx
0x18000b20c  push    rbp
0x18000b20d  push    rsi
0x18000b20e  push    rdi
0x18000b20f  push    r12
0x18000b211  push    r13
0x18000b213  push    r14
0x18000b215  push    r15
0x18000b217  mov     rbp, rsp
0x18000b21a  sub     rsp, 40h
0x18000b21e  xor     r9d, r9d
0x18000b221  mov     r15, rcx
0x18000b224  mov     ecx, r9d
0x18000b227  mov     [rbp+pusResult], r9w
0x18000b22c  movzx   r8d, dx
0x18000b230  mov     [rbp+var_8], ecx
0x18000b233  mov     r11d, r9d
0x18000b236  mov     dword ptr [rbp+usAugend], r9d
0x18000b23a  lea     eax, [r9+4]
0x18000b23e  mov     [rbp+var_18], r9w
0x18000b243  mov     [rbp+var_20], r9w
0x18000b248  mov     r12d, r9d
0x18000b24b  cmp     dx, ax
0x18000b24e  jb      loc_18000B769
0x18000b254  test    r15, r15
0x18000b257  jz      loc_18000B769
0x18000b25d  cmp     byte ptr [r15], 1
0x18000b261  jnz     loc_18000B769
0x18000b267  movzx   esi, word ptr [r15+2]
0x18000b26c  lea     edx, [rax-2]
0x18000b26f  mov     [rbp+var_14], si
0x18000b273  mov     r14d, r9d
0x18000b276  mov     r10d, r9d
0x18000b279  mov     [rbp+var_10], r9d
0x18000b27d  mov     ebx, r9d
0x18000b280  mov     [rbp+var_4], ebx
0x18000b283  cmp     bx, dx
0x18000b286  jnb     loc_18000B75D
0x18000b28c  lea     rdi, [r15+4]
0x18000b290  mov     r13d, r9d
0x18000b293  cmp     r13w, si
0x18000b297  jnb     loc_18000B676
0x18000b29d  test    r14, r14
0x18000b2a0  jz      short loc_18000B2B8
0x18000b2a2  xorps   xmm0, xmm0
0x18000b2a5  movzx   eax, r13w
0x18000b2a9  shl     rax, 5
0x18000b2ad  add     rax, [r14+8]
0x18000b2b1  movups  xmmword ptr [rax], xmm0
0x18000b2b4  movups  xmmword ptr [rax+10h], xmm0
0x18000b2b8  movzx   esi, r8w
0x18000b2bc  mov     eax, esi
0x18000b2be  sub     rax, rdi
0x18000b2c1  add     rax, r15
0x18000b2c4  cmp     rax, rdx
0x18000b2c7  jb      loc_18000B769
0x18000b2cd  movzx   ecx, word ptr [rdi]
0x18000b2d0  lea     rax, [rcx+2]
0x18000b2d4  cmp     rsi, rax
0x18000b2d7  jb      loc_18000B769
0x18000b2dd  test    cx, cx
0x18000b2e0  jz      loc_18000B381
0x18000b2e6  lea     rbx, [rcx+r15]
0x18000b2ea  test    rbx, rbx
0x18000b2ed  jnz     short loc_18000B2F4
0x18000b2ef  mov     rax, r9
0x18000b2f2  jmp     short loc_18000B309
0x18000b2f4  mov     rdx, rsi
0x18000b2f7  sub     rdx, rcx
0x18000b2fa  mov     rcx, rbx; Source
0x18000b2fd  shr     rdx, 1; MaxCount
0x18000b300  call    cs:__imp_wcsnlen
0x18000b306  xor     r9d, r9d
0x18000b309  lea     rcx, ds:2[rax*2]; uOperand
0x18000b311  lea     rdx, [rbp+pusResult]; pusResult
0x18000b315  call    UIntPtrToUShort
0x18000b31a  test    eax, eax
0x18000b31c  js      loc_18000B741
0x18000b322  test    r14, r14
0x18000b325  jz      short loc_18000B356
0x18000b327  mov     rax, [r14+8]
0x18000b32b  mov     rdx, rbx; Src
0x18000b32e  movzx   r9d, r13w
0x18000b332  shl     r9, 5
0x18000b336  movzx   r8d, r12w
0x18000b33a  add     r8, r14
0x18000b33d  mov     [r9+rax], r8
0x18000b341  mov     rcx, [r14+8]
0x18000b345  movzx   r8d, [rbp+pusResult]; Size
0x18000b34a  mov     rcx, [r9+rcx]; void *
0x18000b34e  call    memcpy_0
0x18000b353  xor     r9d, r9d
0x18000b356  movzx   edx, [rbp+pusResult]; usAddend
0x18000b35a  lea     r8, [rbp+var_20]; pusResult
0x18000b35e  movzx   ecx, r12w; usAugend
0x18000b362  call    UShortAdd
0x18000b367  test    eax, eax
0x18000b369  js      loc_18000B741
0x18000b36f  movzx   r12d, [rbp+var_20]
0x18000b374  mov     r10d, [rbp+var_10]
0x18000b378  mov     r11d, dword ptr [rbp+usAugend]
0x18000b37c  movzx   r8d, [rbp+arg_8]
0x18000b381  add     rdi, 2
0x18000b385  mov     rax, rsi
0x18000b388  sub     rax, rdi
0x18000b38b  add     rax, r15
0x18000b38e  cmp     rax, 4
0x18000b392  jb      loc_18000B769
0x18000b398  mov     eax, [rdi]
0x18000b39a  add     rdi, 4
0x18000b39e  test    r14, r14
0x18000b3a1  jz      short loc_18000B3B3
0x18000b3a3  mov     rcx, [r14+8]
0x18000b3a7  movzx   edx, r13w
0x18000b3ab  shl     rdx, 5
0x18000b3af  mov     [rdx+rcx+8], eax
0x18000b3b3  test    eax, eax
0x18000b3b5  jz      loc_18000B627
0x18000b3bb  sub     eax, 1
0x18000b3be  jz      loc_18000B5F8
0x18000b3c4  sub     eax, 1
0x18000b3c7  jz      loc_18000B529
0x18000b3cd  sub     eax, 1
0x18000b3d0  jz      loc_18000B491
0x18000b3d6  cmp     eax, 1
0x18000b3d9  jnz     loc_18000B748
0x18000b3df  mov     rax, rsi
0x18000b3e2  mov     edx, 2
0x18000b3e7  sub     rax, rdi
0x18000b3ea  add     rax, r15
0x18000b3ed  cmp     rax, rdx
0x18000b3f0  jb      loc_18000B769
0x18000b3f6  movzx   ebx, word ptr [rdi]
0x18000b3f9  add     rdi, rdx
0x18000b3fc  test    r14, r14
0x18000b3ff  jz      short loc_18000B412
0x18000b401  mov     rax, [r14+8]
0x18000b405  movzx   ecx, r13w
0x18000b409  shl     rcx, 5
0x18000b40d  mov     [rcx+rax+10h], bx
0x18000b412  sub     rsi, rdi
0x18000b415  add     rsi, r15
0x18000b418  cmp     rsi, rdx
0x18000b41b  jb      loc_18000B769
0x18000b421  movzx   r10d, word ptr [rdi]
0x18000b425  cmp     r8w, r10w
0x18000b429  jb      loc_18000B769
0x18000b42f  test    r10w, r10w
0x18000b433  jz      loc_18000B5EF
0x18000b439  test    r14, r14
0x18000b43c  jz      short loc_18000B46E
0x18000b43e  mov     rax, [r14+8]
0x18000b442  mov     r8, rbx; Size
0x18000b445  movzx   edx, r11w
0x18000b449  add     rdx, r14
0x18000b44c  movzx   r9d, r13w
0x18000b450  shl     r9, 5
0x18000b454  mov     [r9+rax+18h], rdx
0x18000b459  lea     rdx, [r15+r10]; Src
0x18000b45d  mov     rcx, [r14+8]
0x18000b461  mov     rcx, [r9+rcx+18h]; void *
0x18000b466  call    memcpy_0
0x18000b46b  xor     r9d, r9d
0x18000b46e  mov     ecx, dword ptr [rbp+usAugend]; usAugend
0x18000b471  lea     r8, [rbp+var_18]; pusResult
0x18000b475  movzx   edx, bx; usAddend
0x18000b478  call    UShortAdd
0x18000b47d  test    eax, eax
0x18000b47f  js      loc_18000B741
0x18000b485  movzx   ecx, [rbp+var_18]
0x18000b489  mov     dword ptr [rbp+usAugend], ecx
0x18000b48c  jmp     loc_18000B5EA
0x18000b491  mov     rax, rsi
0x18000b494  mov     edx, 2
0x18000b499  sub     rax, rdi
0x18000b49c  add     rax, r15
0x18000b49f  cmp     rax, rdx
0x18000b4a2  jb      loc_18000B769
0x18000b4a8  movzx   ebx, word ptr [rdi]
0x18000b4ab  add     rdi, rdx
0x18000b4ae  test    r14, r14
0x18000b4b1  jz      short loc_18000B4C4
0x18000b4b3  mov     rax, [r14+8]
0x18000b4b7  movzx   ecx, r13w
0x18000b4bb  shl     rcx, 5
0x18000b4bf  mov     [rcx+rax+10h], bx
0x18000b4c4  sub     rsi, rdi
0x18000b4c7  add     rsi, r15
0x18000b4ca  cmp     rsi, rdx
0x18000b4cd  jb      loc_18000B769
0x18000b4d3  movzx   ecx, word ptr [rdi]
0x18000b4d6  cmp     r8w, cx
0x18000b4da  jb      loc_18000B769
0x18000b4e0  test    cx, cx
0x18000b4e3  jz      loc_18000B5EF
0x18000b4e9  test    r14, r14
0x18000b4ec  jz      short loc_18000B521
0x18000b4ee  mov     rax, [r14+8]
0x18000b4f2  mov     r8, rbx
0x18000b4f5  movzx   r9d, r13w
0x18000b4f9  add     r8, r8; Size
0x18000b4fc  shl     r9, 5
0x18000b500  movzx   edx, r12w
0x18000b504  add     rdx, r14
0x18000b507  mov     [r9+rax+18h], rdx
0x18000b50c  lea     rdx, [r15+rcx]; Src
0x18000b510  mov     rcx, [r14+8]
0x18000b514  mov     rcx, [r9+rcx+18h]; void *
0x18000b519  call    memcpy_0
0x18000b51e  xor     r9d, r9d
0x18000b521  lea     edx, [rbx+rbx]
0x18000b524  jmp     loc_18000B5D0
0x18000b529  mov     rax, rsi
0x18000b52c  mov     edx, 2
0x18000b531  sub     rax, rdi
0x18000b534  add     rax, r15
0x18000b537  cmp     rax, rdx
0x18000b53a  jb      loc_18000B769
0x18000b540  movzx   ecx, word ptr [rdi]
0x18000b543  lea     rax, [rcx+2]
0x18000b547  cmp     rsi, rax
0x18000b54a  jb      loc_18000B769
0x18000b550  test    cx, cx
0x18000b553  jz      loc_18000B5EF
0x18000b559  lea     rbx, [rcx+r15]
0x18000b55d  test    rbx, rbx
0x18000b560  jnz     short loc_18000B567
0x18000b562  mov     rax, r9
0x18000b565  jmp     short loc_18000B57D
0x18000b567  movzx   edx, r8w
0x18000b56b  sub     rdx, rcx
0x18000b56e  mov     rcx, rbx; Source
0x18000b571  shr     rdx, 1; MaxCount
0x18000b574  call    cs:__imp_wcsnlen
0x18000b57a  xor     r9d, r9d
0x18000b57d  lea     rcx, ds:2[rax*2]; uOperand
0x18000b585  lea     rdx, [rbp+pusResult]; pusResult
0x18000b589  call    UIntPtrToUShort
0x18000b58e  test    eax, eax
0x18000b590  js      loc_18000B741
0x18000b596  test    r14, r14
0x18000b599  jz      short loc_18000B5CC
0x18000b59b  mov     rax, [r14+8]
0x18000b59f  mov     rdx, rbx; Src
0x18000b5a2  movzx   r9d, r13w
0x18000b5a6  shl     r9, 5
0x18000b5aa  movzx   r8d, r12w
0x18000b5ae  add     r8, r14
0x18000b5b1  mov     [r9+rax+10h], r8
0x18000b5b6  mov     rcx, [r14+8]
0x18000b5ba  movzx   r8d, [rbp+pusResult]; Size
0x18000b5bf  mov     rcx, [r9+rcx+10h]; void *
0x18000b5c4  call    memcpy_0
0x18000b5c9  xor     r9d, r9d
0x18000b5cc  movzx   edx, [rbp+pusResult]; usAddend
0x18000b5d0  lea     r8, [rbp+var_20]; pusResult
0x18000b5d4  movzx   ecx, r12w; usAugend
0x18000b5d8  call    UShortAdd
0x18000b5dd  test    eax, eax
0x18000b5df  js      loc_18000B741
0x18000b5e5  movzx   r12d, [rbp+var_20]
0x18000b5ea  mov     edx, 2
0x18000b5ef  mov     r10d, [rbp+var_10]
0x18000b5f3  add     rdi, rdx
0x18000b5f6  jmp     short loc_18000B657
0x18000b5f8  sub     rsi, rdi
0x18000b5fb  add     rsi, r15
0x18000b5fe  cmp     rsi, 8
0x18000b602  jb      loc_18000B769
0x18000b608  mov     rax, [rdi]
0x18000b60b  add     rdi, 8
0x18000b60f  test    r14, r14
0x18000b612  jz      short loc_18000B652
0x18000b614  mov     rcx, [r14+8]
0x18000b618  movzx   edx, r13w
0x18000b61c  shl     rdx, 5
0x18000b620  mov     [rdx+rcx+10h], rax
0x18000b625  jmp     short loc_18000B652
0x18000b627  sub     rsi, rdi
0x18000b62a  add     rsi, r15
0x18000b62d  cmp     rsi, 4
0x18000b631  jb      loc_18000B769
0x18000b637  mov     eax, [rdi]
0x18000b639  add     rdi, 4
0x18000b63d  test    r14, r14
0x18000b640  jz      short loc_18000B652
0x18000b642  mov     rcx, [r14+8]
0x18000b646  movzx   edx, r13w
0x18000b64a  shl     rdx, 5
0x18000b64e  mov     [rdx+rcx+10h], eax
0x18000b652  mov     edx, 2
0x18000b657  mov     r11d, dword ptr [rbp+usAugend]
0x18000b65b  add     r10w, 20h ; ' '
0x18000b660  movzx   r8d, [rbp+arg_8]
0x18000b665  inc     r13w
0x18000b669  movzx   esi, [rbp+var_14]
  ... truncated ...
```
