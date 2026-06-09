# RtlpStackDbSegmentFindOrCreate

- ea: `0x1800fd774`
- end: `0x1800fdd4f`
- name: `RtlpStackDbSegmentFindOrCreate`
- size: `1499`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18015b42c`

## callees

- `0x180017e90`
- `0x1800183a0`
- `0x18006fb30`
- `0x1800707b0`
- `0x1800fd774`
- `0x18011c8b4`
- `0x18015b51c`
- `0x180164280`
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
0x1800fd774  mov     [rsp+arg_10], rbx
0x1800fd779  push    rbp
0x1800fd77a  push    rsi
0x1800fd77b  push    rdi
0x1800fd77c  push    r12
0x1800fd77e  push    r13
0x1800fd780  push    r14
0x1800fd782  push    r15
0x1800fd784  sub     rsp, 20h
0x1800fd788  mov     r9d, [rdx]
0x1800fd78b  mov     rbp, rdx
0x1800fd78e  mov     r8, [rdx+8]
0x1800fd792  mov     rsi, rcx
0x1800fd795  shl     r9, 3
0x1800fd799  mov     edi, 4CB2Fh
0x1800fd79e  cmp     r9, 8
0x1800fd7a2  jnb     loc_1800FDAE5
0x1800fd7a8  sub     r9, 1
0x1800fd7ac  jz      short loc_1800FD7C6
0x1800fd7ae  sub     r9, 1
0x1800fd7b2  jnz     loc_1800FDB58
0x1800fd7b8  movzx   eax, byte ptr [r8]
0x1800fd7bc  imul    rdi, 25h ; '%'
0x1800fd7c0  add     rdi, rax
0x1800fd7c3  inc     r8
0x1800fd7c6  movzx   eax, byte ptr [r8]
0x1800fd7ca  imul    rdi, 25h ; '%'
0x1800fd7ce  add     rdi, rax
0x1800fd7d1  lea     r12, [rsi+28h]
0x1800fd7d5  mov     rcx, r12
0x1800fd7d8  call    RtlAcquireSRWLockShared
0x1800fd7dd  mov     ecx, [rsi+4]
0x1800fd7e0  or      r13, 0FFFFFFFFFFFFFFFFh
0x1800fd7e4  and     ecx, 1Fh
0x1800fd7e7  mov     r14, r13
0x1800fd7ea  shl     r14, cl
0x1800fd7ed  xor     ebx, ebx
0x1800fd7ef  mov     r15, r14
0x1800fd7f2  and     r15, rdi
0x1800fd7f5  test    rbx, rbx
0x1800fd7f8  jnz     short loc_1800FD873
0x1800fd7fa  mov     r8d, [rsi+4]
0x1800fd7fe  shr     r8d, 5
0x1800fd802  test    r8d, r8d
0x1800fd805  jz      loc_1800FD8BD
0x1800fd80b  lea     r9, [rsp+58h+arg_0]
0x1800fd810  mov     [rsp+58h+arg_0], r15
0x1800fd815  movzx   eax, byte ptr [r9]
0x1800fd819  add     eax, 0B15DCBh
0x1800fd81e  imul    ecx, eax, 25h ; '%'
0x1800fd821  movzx   eax, byte ptr [r9+1]
0x1800fd826  add     ecx, eax
0x1800fd828  movzx   eax, byte ptr [r9+2]
0x1800fd82d  imul    edx, ecx, 25h ; '%'
0x1800fd830  add     edx, eax
0x1800fd832  movzx   eax, byte ptr [r9+3]
0x1800fd837  imul    ecx, edx, 25h ; '%'
0x1800fd83a  add     ecx, eax
0x1800fd83c  movzx   eax, byte ptr [r9+4]
0x1800fd841  imul    edx, ecx, 25h ; '%'
0x1800fd844  add     edx, eax
0x1800fd846  movzx   eax, byte ptr [r9+5]
0x1800fd84b  imul    ecx, edx, 25h ; '%'
0x1800fd84e  add     ecx, eax
0x1800fd850  movzx   eax, byte ptr [r9+6]
0x1800fd855  imul    edx, ecx, 25h ; '%'
0x1800fd858  lea     ecx, [r8-1]
0x1800fd85c  add     edx, eax
0x1800fd85e  movzx   eax, byte ptr [r9+7]
0x1800fd863  imul    edx, 25h ; '%'
0x1800fd866  add     edx, eax
0x1800fd868  mov     rax, [rsi+8]
0x1800fd86c  and     rdx, rcx
0x1800fd86f  lea     rbx, [rax+rdx*8]
0x1800fd873  mov     rbx, [rbx]
0x1800fd876  test    bl, 1
0x1800fd879  jnz     short loc_1800FD8BD
0x1800fd87b  mov     rax, [rbx+8]
0x1800fd87f  and     rax, r14
0x1800fd882  cmp     r15, rax
0x1800fd885  jnz     short loc_1800FD873
0x1800fd887  test    rbx, rbx
0x1800fd88a  jz      short loc_1800FD8BD
0x1800fd88c  mov     rdx, rbp
0x1800fd88f  mov     rcx, rbx
0x1800fd892  call    RtlpStackDbSegmentComparitor
0x1800fd897  test    eax, eax
0x1800fd899  jz      loc_1800FD7F5
0x1800fd89f  lea     rcx, [rbx+10h]
0x1800fd8a3  call    RtlpStackDbRefCountIncrement
0x1800fd8a8  neg     eax
0x1800fd8aa  mov     rcx, r12
0x1800fd8ad  sbb     rdi, rdi
0x1800fd8b0  and     rdi, rbx
0x1800fd8b3  call    RtlReleaseSRWLockShared
0x1800fd8b8  jmp     loc_1800FDACC
0x1800fd8bd  mov     rcx, r12
0x1800fd8c0  call    RtlReleaseSRWLockShared
0x1800fd8c5  mov     eax, [rbp+0]
0x1800fd8c8  mov     rdx, [rsi+40h]
0x1800fd8cc  lea     ecx, ds:18h[rax*8]
0x1800fd8d3  mov     rax, [rsi+30h]
0x1800fd8d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fd8dc  mov     r15, rax
0x1800fd8df  test    rax, rax
0x1800fd8e2  jz      loc_1800FDD3D
0x1800fd8e8  xor     eax, eax
0x1800fd8ea  lea     rcx, [r15+18h]; void *
0x1800fd8ee  xorps   xmm0, xmm0
0x1800fd8f1  movups  xmmword ptr [r15], xmm0
0x1800fd8f5  mov     [r15+10h], rax
0x1800fd8f9  mov     rax, 0FF00000000000001h
0x1800fd903  and     [r15+10h], rax
0x1800fd907  or      qword ptr [r15+10h], 1
0x1800fd90c  mov     al, [rbp+0]
0x1800fd90f  mov     [r15+17h], al
0x1800fd913  mov     [r15+8], rdi
0x1800fd917  mov     r8d, [rbp+0]
0x1800fd91b  mov     rdx, [rbp+8]; Src
0x1800fd91f  shl     r8, 3; Size
0x1800fd923  call    memmove
0x1800fd928  mov     rcx, r12
0x1800fd92b  call    RtlAcquireSRWLockExclusive
0x1800fd930  mov     ebx, [rsi+4]
0x1800fd933  mov     rdx, r13
0x1800fd936  mov     ecx, ebx
0x1800fd938  xor     r14d, r14d
0x1800fd93b  and     ecx, 1Fh
0x1800fd93e  shl     rdx, cl
0x1800fd941  mov     r13, rdx
0x1800fd944  mov     [rsp+58h+arg_0], rdx
0x1800fd949  and     r13, rdi
0x1800fd94c  test    r14, r14
0x1800fd94f  jnz     short loc_1800FD9CA
0x1800fd951  mov     edi, ebx
0x1800fd953  shr     edi, 5
0x1800fd956  test    edi, edi
0x1800fd958  jz      loc_1800FDA12
0x1800fd95e  lea     r8, [rsp+58h+arg_8]
0x1800fd963  mov     [rsp+58h+arg_8], r13
0x1800fd968  movzx   eax, byte ptr [r8]
0x1800fd96c  add     eax, 0B15DCBh
0x1800fd971  imul    ecx, eax, 25h ; '%'
0x1800fd974  movzx   eax, byte ptr [r8+1]
0x1800fd979  add     ecx, eax
0x1800fd97b  movzx   eax, byte ptr [r8+2]
0x1800fd980  imul    edx, ecx, 25h ; '%'
0x1800fd983  add     edx, eax
0x1800fd985  movzx   eax, byte ptr [r8+3]
0x1800fd98a  imul    ecx, edx, 25h ; '%'
0x1800fd98d  add     ecx, eax
0x1800fd98f  movzx   eax, byte ptr [r8+4]
0x1800fd994  imul    edx, ecx, 25h ; '%'
0x1800fd997  add     edx, eax
0x1800fd999  movzx   eax, byte ptr [r8+5]
0x1800fd99e  imul    ecx, edx, 25h ; '%'
0x1800fd9a1  add     ecx, eax
0x1800fd9a3  movzx   eax, byte ptr [r8+6]
0x1800fd9a8  imul    edx, ecx, 25h ; '%'
0x1800fd9ab  lea     ecx, [rdi-1]
0x1800fd9ae  add     edx, eax
0x1800fd9b0  movzx   eax, byte ptr [r8+7]
0x1800fd9b5  imul    edx, 25h ; '%'
0x1800fd9b8  add     edx, eax
0x1800fd9ba  mov     rax, [rsi+8]
0x1800fd9be  and     rdx, rcx
0x1800fd9c1  lea     r14, [rax+rdx*8]
0x1800fd9c5  mov     rdx, [rsp+58h+arg_0]
0x1800fd9ca  mov     r14, [r14]
0x1800fd9cd  test    r14b, 1
0x1800fd9d1  jnz     short loc_1800FDA12
0x1800fd9d3  mov     rax, [r14+8]
0x1800fd9d7  and     rax, rdx
0x1800fd9da  cmp     r13, rax
0x1800fd9dd  jnz     short loc_1800FD9CA
0x1800fd9df  test    r14, r14
0x1800fd9e2  jz      short loc_1800FDA12
0x1800fd9e4  mov     rdx, rbp
0x1800fd9e7  mov     rcx, r14
0x1800fd9ea  call    RtlpStackDbSegmentComparitor
0x1800fd9ef  mov     rdx, [rsp+58h+arg_0]
0x1800fd9f4  test    eax, eax
0x1800fd9f6  jz      loc_1800FD94C
0x1800fd9fc  lea     rcx, [r14+10h]
0x1800fda00  call    RtlpStackDbRefCountIncrement
0x1800fda05  neg     eax
0x1800fda07  sbb     rdi, rdi
0x1800fda0a  and     rdi, r14
0x1800fda0d  jmp     loc_1800FDAAF
0x1800fda12  shr     ebx, 5
0x1800fda15  add     ebx, ebx
0x1800fda17  cmp     [rsi], ebx
0x1800fda19  jnb     loc_1800FDBC5
0x1800fda1f  mov     edi, [rsi+4]
0x1800fda22  lea     r8, [rsp+58h+arg_0]
0x1800fda27  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800fda2b  mov     ecx, edi
0x1800fda2d  and     ecx, 1Fh
0x1800fda30  shr     edi, 5
0x1800fda33  shl     rax, cl
0x1800fda36  and     rax, [r15+8]
0x1800fda3a  mov     [rsp+58h+arg_0], rax
0x1800fda3f  movzx   eax, byte ptr [r8]
0x1800fda43  add     eax, 0B15DCBh
0x1800fda48  imul    ecx, eax, 25h ; '%'
0x1800fda4b  movzx   eax, byte ptr [r8+1]
0x1800fda50  add     ecx, eax
0x1800fda52  movzx   eax, byte ptr [r8+2]
0x1800fda57  imul    edx, ecx, 25h ; '%'
0x1800fda5a  add     edx, eax
0x1800fda5c  movzx   eax, byte ptr [r8+3]
0x1800fda61  imul    ecx, edx, 25h ; '%'
0x1800fda64  add     ecx, eax
0x1800fda66  movzx   eax, byte ptr [r8+4]
0x1800fda6b  imul    edx, ecx, 25h ; '%'
0x1800fda6e  add     edx, eax
0x1800fda70  movzx   eax, byte ptr [r8+5]
0x1800fda75  imul    ecx, edx, 25h ; '%'
0x1800fda78  add     ecx, eax
0x1800fda7a  movzx   eax, byte ptr [r8+6]
0x1800fda7f  imul    edx, ecx, 25h ; '%'
0x1800fda82  mov     rcx, [rsi+8]
0x1800fda86  add     edx, eax
0x1800fda88  movzx   eax, byte ptr [r8+7]
0x1800fda8d  imul    edx, 25h ; '%'
0x1800fda90  add     edx, eax
0x1800fda92  lea     eax, [rdi-1]
0x1800fda95  and     rdx, rax
0x1800fda98  mov     rdi, r15
0x1800fda9b  mov     rax, [rcx+rdx*8]
0x1800fda9f  mov     [r15], rax
0x1800fdaa2  mov     [rcx+rdx*8], r15
0x1800fdaa6  mov     eax, [rsi]
0x1800fdaa8  inc     eax
0x1800fdaaa  mov     [rsi], eax
0x1800fdaac  xor     r15d, r15d
0x1800fdaaf  mov     rcx, r12
0x1800fdab2  call    RtlReleaseSRWLockExclusive
0x1800fdab7  test    r15, r15
0x1800fdaba  jz      short loc_1800FDACC
0x1800fdabc  mov     rdx, [rsi+40h]
0x1800fdac0  mov     rcx, r15
0x1800fdac3  mov     rax, [rsi+38h]
0x1800fdac7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fdacc  mov     rbx, [rsp+58h+arg_10]
0x1800fdad1  mov     rax, rdi
0x1800fdad4  add     rsp, 20h
0x1800fdad8  pop     r15
0x1800fdada  pop     r14
0x1800fdadc  pop     r13
0x1800fdade  pop     r12
0x1800fdae0  pop     rdi
0x1800fdae1  pop     rsi
0x1800fdae2  pop     rbp
0x1800fdae3  retn
0x1800fdae5  movzx   eax, byte ptr [r8]
0x1800fdae9  sub     r9, 8
0x1800fdaed  imul    rcx, rdi, 25h ; '%'
0x1800fdaf1  add     rcx, rax
0x1800fdaf4  movzx   eax, byte ptr [r8+1]
0x1800fdaf9  imul    rdx, rcx, 25h ; '%'
0x1800fdafd  add     rdx, rax
0x1800fdb00  movzx   eax, byte ptr [r8+2]
0x1800fdb05  imul    rcx, rdx, 25h ; '%'
0x1800fdb09  add     rcx, rax
0x1800fdb0c  movzx   eax, byte ptr [r8+3]
0x1800fdb11  imul    rdx, rcx, 25h ; '%'
0x1800fdb15  add     rdx, rax
0x1800fdb18  movzx   eax, byte ptr [r8+4]
0x1800fdb1d  imul    rcx, rdx, 25h ; '%'
0x1800fdb21  add     rcx, rax
0x1800fdb24  movzx   eax, byte ptr [r8+5]
0x1800fdb29  imul    rdx, rcx, 25h ; '%'
0x1800fdb2d  add     rdx, rax
0x1800fdb30  movzx   eax, byte ptr [r8+6]
0x1800fdb35  imul    rcx, rdx, 25h ; '%'
0x1800fdb39  add     rcx, rax
0x1800fdb3c  movzx   eax, byte ptr [r8+7]
0x1800fdb41  imul    rdi, rcx, 25h ; '%'
0x1800fdb45  add     r8, 8
0x1800fdb49  add     rdi, rax
0x1800fdb4c  cmp     r9, 8
0x1800fdb50  jl      loc_1800FD7A8
0x1800fdb56  jmp     short loc_1800FDAE5
0x1800fdb58  sub     r9, 1
0x1800fdb5c  jz      short loc_1800FDBB2
0x1800fdb5e  sub     r9, 1
0x1800fdb62  jz      short loc_1800FDBA4
0x1800fdb64  sub     r9, 1
0x1800fdb68  jz      short loc_1800FDB96
0x1800fdb6a  sub     r9, 1
0x1800fdb6e  jz      short loc_1800FDB88
0x1800fdb70  cmp     r9, 1
0x1800fdb74  jnz     loc_1800FD7D1
0x1800fdb7a  movzx   eax, byte ptr [r8]
0x1800fdb7e  imul    rdi, 25h ; '%'
0x1800fdb82  add     rdi, rax
0x1800fdb85  inc     r8
0x1800fdb88  movzx   eax, byte ptr [r8]
0x1800fdb8c  imul    rdi, 25h ; '%'
  ... truncated ...
```
