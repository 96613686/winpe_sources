# RtlpStackDbSegmentFindOrCreate

- ea: `0x1800fd154`
- end: `0x1800fd72f`
- name: `RtlpStackDbSegmentFindOrCreate`
- size: `1499`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18015aa9c`

## callees

- `0x180017e90`
- `0x1800183a0`
- `0x180053150`
- `0x180053dd0`
- `0x1800fd154`
- `0x18011bdc4`
- `0x18015ab8c`
- `0x180163a80`
- `0x18016f020`

## pseudocode

```c
__int64 __fastcall RtlpStackDbSegmentFindOrCreate(__int64 a1, unsigned int *a2)
{
  unsigned __int8 *v3; // r8
  __int64 v5; // r9
  __int64 v6; // rdi
  __int64 v7; // r9
  __int64 v8; // r9
  __int64 v9; // rdx
  __int64 v10; // r14
  __int64 v11; // rbx
  __int64 v12; // r15
  int v13; // r8d
  __int64 v14; // rdi
  __int64 v15; // rdx
  __int64 v16; // rax
  _QWORD *v17; // r15
  unsigned int v18; // ebx
  __int64 v19; // r14
  __int64 v20; // rdx
  __int64 v21; // r13
  int v22; // eax
  __int64 v23; // rbx
  __int64 v24; // rcx
  __int64 v25; // rdx
  __int64 v27; // rcx
  __int64 v28; // rax
  __int64 v29; // r9
  __int64 v30; // r9
  __int64 v31; // r9
  __int64 v32; // r9
  __int64 v33; // rbp
  void (__fastcall *v34)(__int64, __int64, char *, __int64); // r13
  char *v35; // r8
  char v36; // cl
  unsigned __int64 v37; // rcx
  __int64 v38; // rdi
  __int64 v39; // r9
  __int64 v40; // r14
  _QWORD *v41; // r10
  __int64 v42; // rcx
  __int64 v43; // rdx
  __int64 v44; // [rsp+60h] [rbp+8h]
  __int64 v45; // [rsp+60h] [rbp+8h]
  __int64 v46; // [rsp+60h] [rbp+8h]

  v3 = (unsigned __int8 *)*((_QWORD *)a2 + 1);
  v5 = 8LL * *a2;
  v6 = 314159;
  if ( (unsigned __int64)v5 >= 8 )
  {
    do
    {
      v5 -= 8;
      v27 = v3[6] + 37 * (v3[5] + 37 * (v3[4] + 37 * (v3[3] + 37 * (v3[2] + 37 * (v3[1] + 37 * (*v3 + 37 * v6))))));
      v28 = v3[7];
      v3 += 8;
      v6 = v28 + 37 * v27;
    }
    while ( v5 >= 8 );
  }
  v7 = v5 - 1;
  if ( v7 )
  {
    v8 = v7 - 1;
    if ( v8 )
    {
      v29 = v8 - 1;
      if ( v29 )
      {
        v30 = v29 - 1;
        if ( v30 )
        {
          v31 = v30 - 1;
          if ( v31 )
          {
            v32 = v31 - 1;
            if ( v32 )
            {
              if ( v32 != 1 )
                goto LABEL_6;
              v6 = *v3++ + 37 * v6;
            }
            v6 = *v3++ + 37 * v6;
          }
          v6 = *v3++ + 37 * v6;
        }
        v6 = *v3++ + 37 * v6;
      }
      v6 = *v3++ + 37 * v6;
    }
    v6 = *v3++ + 37 * v6;
  }
  v6 = *v3 + 37 * v6;
LABEL_6:
  RtlAcquireSRWLockShared(a1 + 40);
  v10 = -1LL << (*(_BYTE *)(a1 + 4) & 0x1F);
  v11 = 0;
  v12 = v6 & v10;
LABEL_7:
  if ( v11 )
    goto LABEL_10;
  v13 = *(_DWORD *)(a1 + 4) >> 5;
  if ( v13 )
  {
    v9 = (v13 - 1)
       & (HIBYTE(v12)
        + 37
        * (BYTE6(v12)
         + 37
         * (BYTE5(v12)
          + 37
          * (BYTE4(v12)
           + 37
           * (BYTE3(v12) + 37 * (BYTE2(v12) + 37 * (BYTE1(v12) + 37 * ((unsigned int)(unsigned __int8)v12 + 11623883))))))));
    v11 = *(_QWORD *)(a1 + 8) + 8 * v9;
LABEL_10:
    while ( 1 )
    {
      v11 = *(_QWORD *)v11;
      if ( (v11 & 1) != 0 )
        break;
      if ( v12 == (v10 & *(_QWORD *)(v11 + 8)) )
      {
        if ( !v11 )
          break;
        if ( (unsigned int)RtlpStackDbSegmentComparitor(v11, a2) )
        {
          v14 = v11 & -(__int64)((unsigned int)RtlpStackDbRefCountIncrement(v11 + 16, v9) != 0);
          RtlReleaseSRWLockShared(a1 + 40, v15);
          return v14;
        }
        goto LABEL_7;
      }
    }
  }
  RtlReleaseSRWLockShared(a1 + 40, v9);
  v16 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(a1 + 48))(8 * *a2 + 24, *(_QWORD *)(a1 + 64));
  v17 = (_QWORD *)v16;
  if ( !v16 )
    return 0;
  *(_OWORD *)v16 = 0;
  *(_QWORD *)(v16 + 16) = 0;
  *(_QWORD *)(v16 + 16) &= 0xFF00000000000001uLL;
  *(_QWORD *)(v16 + 16) |= 1uLL;
  *(_BYTE *)(v16 + 23) = *(_BYTE *)a2;
  *(_QWORD *)(v16 + 8) = v6;
  memmove((void *)(v16 + 24), *((const void **)a2 + 1), 8LL * *a2);
  RtlAcquireSRWLockExclusive(a1 + 40);
  v18 = *(_DWORD *)(a1 + 4);
  v19 = 0;
  v20 = -1LL << (*(_BYTE *)(a1 + 4) & 0x1F);
  v44 = v20;
  v21 = v6 & v20;
LABEL_17:
  if ( v19 )
    goto LABEL_20;
  if ( v18 >> 5 )
  {
    v19 = *(_QWORD *)(a1 + 8)
        + 8LL
        * (((v18 >> 5) - 1)
         & (HIBYTE(v21)
          + 37
          * (BYTE6(v21)
           + 37
           * (BYTE5(v21)
            + 37
            * (BYTE4(v21)
             + 37 * (BYTE3(v21) + 37 * (BYTE2(v21) + 37 * (BYTE1(v21) + 37 * ((unsigned __int8)v21 + 11623883)))))))));
    v20 = v44;
LABEL_20:
    while ( 1 )
    {
      v19 = *(_QWORD *)v19;
      if ( (v19 & 1) != 0 )
        break;
      if ( v21 == (v20 & *(_QWORD *)(v19 + 8)) )
      {
        if ( !v19 )
          break;
        v22 = RtlpStackDbSegmentComparitor(v19, a2);
        v20 = v44;
        if ( v22 )
        {
          v14 = v19 & -(__int64)((unsigned int)RtlpStackDbRefCountIncrement(v19 + 16, v44) != 0);
          goto LABEL_27;
        }
        goto LABEL_17;
      }
    }
  }
  v23 = 2 * (v18 >> 5);
  if ( *(_DWORD *)a1 < (unsigned int)v23 )
    goto LABEL_26;
  v33 = *(_QWORD *)(a1 + 64);
  v34 = *(void (__fastcall **)(__int64, __int64, char *, __int64))(a1 + 56);
  if ( (unsigned int)v23 < 4 )
    v23 = 4;
  v35 = (char *)(*(__int64 (__fastcall **)(__int64, _QWORD))(a1 + 48))(8LL * (unsigned int)v23, *(_QWORD *)(a1 + 64));
  if ( v35 )
  {
    if ( (((_DWORD)v23 - 1) & (unsigned int)v23) != 0 )
    {
      v36 = -1;
      do
      {
        ++v36;
        LODWORD(v23) = (unsigned int)v23 >> 1;
      }
      while ( (_DWORD)v23 );
      v23 = (unsigned int)(1 << v36);
    }
    if ( (unsigned int)v23 > 0x4000000 )
      v23 = 0x4000000;
    v37 = (unsigned int)v23;
    if ( v35 > &v35[8 * v23] )
      v37 = 0;
    if ( v37 )
      memset64(v35, a1 | 1, v37);
    v38 = 0;
    v39 = -1LL << (*(_BYTE *)(a1 + 4) & 0x1F);
    if ( (*(_DWORD *)(a1 + 4) & 0xFFFFFFE0) != 0 )
    {
      do
      {
        v40 = *(_QWORD *)(a1 + 8);
        while ( 1 )
        {
          v41 = *(_QWORD **)(v40 + 8 * v38);
          if ( ((unsigned __int8)v41 & 1) != 0 )
            break;
          *(_QWORD *)(v40 + 8 * v38) = *v41;
          v46 = v39 & v41[1];
          v43 = ((_DWORD)v23 - 1)
              & (HIBYTE(v46)
               + 37
               * (BYTE6(v46)
                + 37
                * (BYTE5(v46)
                 + 37
                 * (BYTE4(v46)
                  + 37
                  * (BYTE3(v46)
                   + 37 * (BYTE2(v46) + 37 * (BYTE1(v46) + 37 * ((unsigned int)(unsigned __int8)v46 + 11623883))))))));
          *v41 = *(_QWORD *)&v35[8 * v43];
          *(_QWORD *)&v35[8 * v43] = v41;
        }
        v38 = (unsigned int)(v38 + 1);
      }
      while ( (unsigned int)v38 < *(_DWORD *)(a1 + 4) >> 5 );
    }
    v42 = *(_QWORD *)(a1 + 8);
    *(_QWORD *)(a1 + 8) = v35;
    *(_DWORD *)(a1 + 4) = *(_DWORD *)(a1 + 4) & 0x1F | (32 * v23);
    if ( v42 )
      v34(v42, v33, v35, v39);
    goto LABEL_26;
  }
  if ( *(_DWORD *)(a1 + 4) >= 0x20u )
  {
LABEL_26:
    v45 = v17[1] & (-1LL << (*(_DWORD *)(a1 + 4) & 0x1F));
    v24 = *(_QWORD *)(a1 + 8);
    v25 = ((*(_DWORD *)(a1 + 4) >> 5) - 1)
        & (HIBYTE(v45)
         + 37
         * (BYTE6(v45)
          + 37
          * (BYTE5(v45)
           + 37
           * (BYTE4(v45)
            + 37
            * (BYTE3(v45) + 37 * (BYTE2(v45) + 37 * (BYTE1(v45) + 37 * ((unsigned int)(unsigned __int8)v45 + 11623883))))))));
    v14 = (__int64)v17;
    *v17 = *(_QWORD *)(v24 + 8 * v25);
    *(_QWORD *)(v24 + 8 * v25) = v17;
    ++*(_DWORD *)a1;
    v17 = 0;
    goto LABEL_27;
  }
  v14 = 0;
LABEL_27:
  RtlReleaseSRWLockExclusive(a1 + 40);
  if ( v17 )
    (*(void (__fastcall **)(_QWORD *, _QWORD))(a1 + 56))(v17, *(_QWORD *)(a1 + 64));
  return v14;
}

```

## disassembly

```asm
0x1800fd154  mov     [rsp+arg_10], rbx
0x1800fd159  push    rbp
0x1800fd15a  push    rsi
0x1800fd15b  push    rdi
0x1800fd15c  push    r12
0x1800fd15e  push    r13
0x1800fd160  push    r14
0x1800fd162  push    r15
0x1800fd164  sub     rsp, 20h
0x1800fd168  mov     r9d, [rdx]
0x1800fd16b  mov     rbp, rdx
0x1800fd16e  mov     r8, [rdx+8]
0x1800fd172  mov     rsi, rcx
0x1800fd175  shl     r9, 3
0x1800fd179  mov     edi, 4CB2Fh
0x1800fd17e  cmp     r9, 8
0x1800fd182  jnb     loc_1800FD4C5
0x1800fd188  sub     r9, 1
0x1800fd18c  jz      short loc_1800FD1A6
0x1800fd18e  sub     r9, 1
0x1800fd192  jnz     loc_1800FD538
0x1800fd198  movzx   eax, byte ptr [r8]
0x1800fd19c  imul    rdi, 25h ; '%'
0x1800fd1a0  add     rdi, rax
0x1800fd1a3  inc     r8
0x1800fd1a6  movzx   eax, byte ptr [r8]
0x1800fd1aa  imul    rdi, 25h ; '%'
0x1800fd1ae  add     rdi, rax
0x1800fd1b1  lea     r12, [rsi+28h]
0x1800fd1b5  mov     rcx, r12
0x1800fd1b8  call    RtlAcquireSRWLockShared
0x1800fd1bd  mov     ecx, [rsi+4]
0x1800fd1c0  or      r13, 0FFFFFFFFFFFFFFFFh
0x1800fd1c4  and     ecx, 1Fh
0x1800fd1c7  mov     r14, r13
0x1800fd1ca  shl     r14, cl
0x1800fd1cd  xor     ebx, ebx
0x1800fd1cf  mov     r15, r14
0x1800fd1d2  and     r15, rdi
0x1800fd1d5  test    rbx, rbx
0x1800fd1d8  jnz     short loc_1800FD253
0x1800fd1da  mov     r8d, [rsi+4]
0x1800fd1de  shr     r8d, 5
0x1800fd1e2  test    r8d, r8d
0x1800fd1e5  jz      loc_1800FD29D
0x1800fd1eb  lea     r9, [rsp+58h+arg_0]
0x1800fd1f0  mov     [rsp+58h+arg_0], r15
0x1800fd1f5  movzx   eax, byte ptr [r9]
0x1800fd1f9  add     eax, 0B15DCBh
0x1800fd1fe  imul    ecx, eax, 25h ; '%'
0x1800fd201  movzx   eax, byte ptr [r9+1]
0x1800fd206  add     ecx, eax
0x1800fd208  movzx   eax, byte ptr [r9+2]
0x1800fd20d  imul    edx, ecx, 25h ; '%'
0x1800fd210  add     edx, eax
0x1800fd212  movzx   eax, byte ptr [r9+3]
0x1800fd217  imul    ecx, edx, 25h ; '%'
0x1800fd21a  add     ecx, eax
0x1800fd21c  movzx   eax, byte ptr [r9+4]
0x1800fd221  imul    edx, ecx, 25h ; '%'
0x1800fd224  add     edx, eax
0x1800fd226  movzx   eax, byte ptr [r9+5]
0x1800fd22b  imul    ecx, edx, 25h ; '%'
0x1800fd22e  add     ecx, eax
0x1800fd230  movzx   eax, byte ptr [r9+6]
0x1800fd235  imul    edx, ecx, 25h ; '%'
0x1800fd238  lea     ecx, [r8-1]
0x1800fd23c  add     edx, eax
0x1800fd23e  movzx   eax, byte ptr [r9+7]
0x1800fd243  imul    edx, 25h ; '%'
0x1800fd246  add     edx, eax
0x1800fd248  mov     rax, [rsi+8]
0x1800fd24c  and     rdx, rcx
0x1800fd24f  lea     rbx, [rax+rdx*8]
0x1800fd253  mov     rbx, [rbx]
0x1800fd256  test    bl, 1
0x1800fd259  jnz     short loc_1800FD29D
0x1800fd25b  mov     rax, [rbx+8]
0x1800fd25f  and     rax, r14
0x1800fd262  cmp     r15, rax
0x1800fd265  jnz     short loc_1800FD253
0x1800fd267  test    rbx, rbx
0x1800fd26a  jz      short loc_1800FD29D
0x1800fd26c  mov     rdx, rbp
0x1800fd26f  mov     rcx, rbx
0x1800fd272  call    RtlpStackDbSegmentComparitor
0x1800fd277  test    eax, eax
0x1800fd279  jz      loc_1800FD1D5
0x1800fd27f  lea     rcx, [rbx+10h]
0x1800fd283  call    RtlpStackDbRefCountIncrement
0x1800fd288  neg     eax
0x1800fd28a  mov     rcx, r12
0x1800fd28d  sbb     rdi, rdi
0x1800fd290  and     rdi, rbx
0x1800fd293  call    RtlReleaseSRWLockShared
0x1800fd298  jmp     loc_1800FD4AC
0x1800fd29d  mov     rcx, r12
0x1800fd2a0  call    RtlReleaseSRWLockShared
0x1800fd2a5  mov     eax, [rbp+0]
0x1800fd2a8  mov     rdx, [rsi+40h]
0x1800fd2ac  lea     ecx, ds:18h[rax*8]
0x1800fd2b3  mov     rax, [rsi+30h]
0x1800fd2b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fd2bc  mov     r15, rax
0x1800fd2bf  test    rax, rax
0x1800fd2c2  jz      loc_1800FD71D
0x1800fd2c8  xor     eax, eax
0x1800fd2ca  lea     rcx, [r15+18h]; void *
0x1800fd2ce  xorps   xmm0, xmm0
0x1800fd2d1  movups  xmmword ptr [r15], xmm0
0x1800fd2d5  mov     [r15+10h], rax
0x1800fd2d9  mov     rax, 0FF00000000000001h
0x1800fd2e3  and     [r15+10h], rax
0x1800fd2e7  or      qword ptr [r15+10h], 1
0x1800fd2ec  mov     al, [rbp+0]
0x1800fd2ef  mov     [r15+17h], al
0x1800fd2f3  mov     [r15+8], rdi
0x1800fd2f7  mov     r8d, [rbp+0]
0x1800fd2fb  mov     rdx, [rbp+8]; Src
0x1800fd2ff  shl     r8, 3; Size
0x1800fd303  call    memmove
0x1800fd308  mov     rcx, r12
0x1800fd30b  call    RtlAcquireSRWLockExclusive
0x1800fd310  mov     ebx, [rsi+4]
0x1800fd313  mov     rdx, r13
0x1800fd316  mov     ecx, ebx
0x1800fd318  xor     r14d, r14d
0x1800fd31b  and     ecx, 1Fh
0x1800fd31e  shl     rdx, cl
0x1800fd321  mov     r13, rdx
0x1800fd324  mov     [rsp+58h+arg_0], rdx
0x1800fd329  and     r13, rdi
0x1800fd32c  test    r14, r14
0x1800fd32f  jnz     short loc_1800FD3AA
0x1800fd331  mov     edi, ebx
0x1800fd333  shr     edi, 5
0x1800fd336  test    edi, edi
0x1800fd338  jz      loc_1800FD3F2
0x1800fd33e  lea     r8, [rsp+58h+arg_8]
0x1800fd343  mov     [rsp+58h+arg_8], r13
0x1800fd348  movzx   eax, byte ptr [r8]
0x1800fd34c  add     eax, 0B15DCBh
0x1800fd351  imul    ecx, eax, 25h ; '%'
0x1800fd354  movzx   eax, byte ptr [r8+1]
0x1800fd359  add     ecx, eax
0x1800fd35b  movzx   eax, byte ptr [r8+2]
0x1800fd360  imul    edx, ecx, 25h ; '%'
0x1800fd363  add     edx, eax
0x1800fd365  movzx   eax, byte ptr [r8+3]
0x1800fd36a  imul    ecx, edx, 25h ; '%'
0x1800fd36d  add     ecx, eax
0x1800fd36f  movzx   eax, byte ptr [r8+4]
0x1800fd374  imul    edx, ecx, 25h ; '%'
0x1800fd377  add     edx, eax
0x1800fd379  movzx   eax, byte ptr [r8+5]
0x1800fd37e  imul    ecx, edx, 25h ; '%'
0x1800fd381  add     ecx, eax
0x1800fd383  movzx   eax, byte ptr [r8+6]
0x1800fd388  imul    edx, ecx, 25h ; '%'
0x1800fd38b  lea     ecx, [rdi-1]
0x1800fd38e  add     edx, eax
0x1800fd390  movzx   eax, byte ptr [r8+7]
0x1800fd395  imul    edx, 25h ; '%'
0x1800fd398  add     edx, eax
0x1800fd39a  mov     rax, [rsi+8]
0x1800fd39e  and     rdx, rcx
0x1800fd3a1  lea     r14, [rax+rdx*8]
0x1800fd3a5  mov     rdx, [rsp+58h+arg_0]
0x1800fd3aa  mov     r14, [r14]
0x1800fd3ad  test    r14b, 1
0x1800fd3b1  jnz     short loc_1800FD3F2
0x1800fd3b3  mov     rax, [r14+8]
0x1800fd3b7  and     rax, rdx
0x1800fd3ba  cmp     r13, rax
0x1800fd3bd  jnz     short loc_1800FD3AA
0x1800fd3bf  test    r14, r14
0x1800fd3c2  jz      short loc_1800FD3F2
0x1800fd3c4  mov     rdx, rbp
0x1800fd3c7  mov     rcx, r14
0x1800fd3ca  call    RtlpStackDbSegmentComparitor
0x1800fd3cf  mov     rdx, [rsp+58h+arg_0]
0x1800fd3d4  test    eax, eax
0x1800fd3d6  jz      loc_1800FD32C
0x1800fd3dc  lea     rcx, [r14+10h]
0x1800fd3e0  call    RtlpStackDbRefCountIncrement
0x1800fd3e5  neg     eax
0x1800fd3e7  sbb     rdi, rdi
0x1800fd3ea  and     rdi, r14
0x1800fd3ed  jmp     loc_1800FD48F
0x1800fd3f2  shr     ebx, 5
0x1800fd3f5  add     ebx, ebx
0x1800fd3f7  cmp     [rsi], ebx
0x1800fd3f9  jnb     loc_1800FD5A5
0x1800fd3ff  mov     edi, [rsi+4]
0x1800fd402  lea     r8, [rsp+58h+arg_0]
0x1800fd407  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800fd40b  mov     ecx, edi
0x1800fd40d  and     ecx, 1Fh
0x1800fd410  shr     edi, 5
0x1800fd413  shl     rax, cl
0x1800fd416  and     rax, [r15+8]
0x1800fd41a  mov     [rsp+58h+arg_0], rax
0x1800fd41f  movzx   eax, byte ptr [r8]
0x1800fd423  add     eax, 0B15DCBh
0x1800fd428  imul    ecx, eax, 25h ; '%'
0x1800fd42b  movzx   eax, byte ptr [r8+1]
0x1800fd430  add     ecx, eax
0x1800fd432  movzx   eax, byte ptr [r8+2]
0x1800fd437  imul    edx, ecx, 25h ; '%'
0x1800fd43a  add     edx, eax
0x1800fd43c  movzx   eax, byte ptr [r8+3]
0x1800fd441  imul    ecx, edx, 25h ; '%'
0x1800fd444  add     ecx, eax
0x1800fd446  movzx   eax, byte ptr [r8+4]
0x1800fd44b  imul    edx, ecx, 25h ; '%'
0x1800fd44e  add     edx, eax
0x1800fd450  movzx   eax, byte ptr [r8+5]
0x1800fd455  imul    ecx, edx, 25h ; '%'
0x1800fd458  add     ecx, eax
0x1800fd45a  movzx   eax, byte ptr [r8+6]
0x1800fd45f  imul    edx, ecx, 25h ; '%'
0x1800fd462  mov     rcx, [rsi+8]
0x1800fd466  add     edx, eax
0x1800fd468  movzx   eax, byte ptr [r8+7]
0x1800fd46d  imul    edx, 25h ; '%'
0x1800fd470  add     edx, eax
0x1800fd472  lea     eax, [rdi-1]
0x1800fd475  and     rdx, rax
0x1800fd478  mov     rdi, r15
0x1800fd47b  mov     rax, [rcx+rdx*8]
0x1800fd47f  mov     [r15], rax
0x1800fd482  mov     [rcx+rdx*8], r15
0x1800fd486  mov     eax, [rsi]
0x1800fd488  inc     eax
0x1800fd48a  mov     [rsi], eax
0x1800fd48c  xor     r15d, r15d
0x1800fd48f  mov     rcx, r12
0x1800fd492  call    RtlReleaseSRWLockExclusive
0x1800fd497  test    r15, r15
0x1800fd49a  jz      short loc_1800FD4AC
0x1800fd49c  mov     rdx, [rsi+40h]
0x1800fd4a0  mov     rcx, r15
0x1800fd4a3  mov     rax, [rsi+38h]
0x1800fd4a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fd4ac  mov     rbx, [rsp+58h+arg_10]
0x1800fd4b1  mov     rax, rdi
0x1800fd4b4  add     rsp, 20h
0x1800fd4b8  pop     r15
0x1800fd4ba  pop     r14
0x1800fd4bc  pop     r13
0x1800fd4be  pop     r12
0x1800fd4c0  pop     rdi
0x1800fd4c1  pop     rsi
0x1800fd4c2  pop     rbp
0x1800fd4c3  retn
0x1800fd4c5  movzx   eax, byte ptr [r8]
0x1800fd4c9  sub     r9, 8
0x1800fd4cd  imul    rcx, rdi, 25h ; '%'
0x1800fd4d1  add     rcx, rax
0x1800fd4d4  movzx   eax, byte ptr [r8+1]
0x1800fd4d9  imul    rdx, rcx, 25h ; '%'
0x1800fd4dd  add     rdx, rax
0x1800fd4e0  movzx   eax, byte ptr [r8+2]
0x1800fd4e5  imul    rcx, rdx, 25h ; '%'
0x1800fd4e9  add     rcx, rax
0x1800fd4ec  movzx   eax, byte ptr [r8+3]
0x1800fd4f1  imul    rdx, rcx, 25h ; '%'
0x1800fd4f5  add     rdx, rax
0x1800fd4f8  movzx   eax, byte ptr [r8+4]
0x1800fd4fd  imul    rcx, rdx, 25h ; '%'
0x1800fd501  add     rcx, rax
0x1800fd504  movzx   eax, byte ptr [r8+5]
0x1800fd509  imul    rdx, rcx, 25h ; '%'
0x1800fd50d  add     rdx, rax
0x1800fd510  movzx   eax, byte ptr [r8+6]
0x1800fd515  imul    rcx, rdx, 25h ; '%'
0x1800fd519  add     rcx, rax
0x1800fd51c  movzx   eax, byte ptr [r8+7]
0x1800fd521  imul    rdi, rcx, 25h ; '%'
0x1800fd525  add     r8, 8
0x1800fd529  add     rdi, rax
0x1800fd52c  cmp     r9, 8
0x1800fd530  jl      loc_1800FD188
0x1800fd536  jmp     short loc_1800FD4C5
0x1800fd538  sub     r9, 1
0x1800fd53c  jz      short loc_1800FD592
0x1800fd53e  sub     r9, 1
0x1800fd542  jz      short loc_1800FD584
0x1800fd544  sub     r9, 1
0x1800fd548  jz      short loc_1800FD576
0x1800fd54a  sub     r9, 1
0x1800fd54e  jz      short loc_1800FD568
0x1800fd550  cmp     r9, 1
0x1800fd554  jnz     loc_1800FD1B1
0x1800fd55a  movzx   eax, byte ptr [r8]
0x1800fd55e  imul    rdi, 25h ; '%'
0x1800fd562  add     rdi, rax
0x1800fd565  inc     r8
0x1800fd568  movzx   eax, byte ptr [r8]
0x1800fd56c  imul    rdi, 25h ; '%'
  ... truncated ...
```
