# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x140002324`
- end: `0x1400025f7`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `723`
- prototype: `__int64 __fastcall(__int64, volatile signed __int32 *, int, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000272c`

## callees

- `0x140002324`

## pseudocode

```c
__int64 __fastcall wil_details_FeatureReporting_RecordUsageInCache(
        __int64 a1,
        volatile signed __int32 *a2,
        int a3,
        int a4)
{
  int v7; // r8d
  unsigned __int32 v8; // eax
  BOOL v9; // edx
  unsigned __int32 v10; // ett
  int v11; // ecx
  signed __int32 v12; // edx
  int v13; // ebx
  signed __int32 v14; // r9d
  signed __int32 v15; // eax
  signed __int32 v16; // ecx
  BOOL v17; // r9d
  unsigned int v18; // eax
  int v19; // edx
  int v20; // r8d
  unsigned int v21; // edx
  unsigned int v22; // r8d
  signed __int32 v23; // eax
  signed __int32 v24; // edx
  BOOL v25; // ebp
  unsigned int v26; // eax
  int v27; // r9d
  unsigned int v28; // r8d
  unsigned int v29; // r9d
  signed __int32 v30; // eax

  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  switch ( a3 )
  {
    case 0:
      goto LABEL_49;
    case 1:
      goto LABEL_34;
    case 2:
    case 3:
      goto LABEL_17;
    case 4:
LABEL_49:
      v24 = *a2;
      v25 = a3 == 4;
      while ( 1 )
      {
        *(_DWORD *)(a1 + 4) = 0;
        v26 = v24 | 1;
        if ( (((v24 | 1u) >> 14) & 1) != v25 )
        {
          if ( ((v26 >> 5) & 0x1FF) != 0 )
          {
            *(_DWORD *)(a1 + 4) = (v26 >> 5) & 0x1FF;
            *(_DWORD *)(a1 + 8) = a3 == 0 ? 4 : 0;
            v26 = v24 & 0xFFFFC01E | 1;
          }
          v27 = 0;
          if ( a3 == 4 )
            v27 = 0x4000;
          v26 = v26 & 0xFFFFBFFF | v27;
        }
        v28 = (v26 >> 5) & 0x1FF;
        v29 = v28 + 1;
        if ( v28 + 1 > 0x1FF || v29 < v28 )
        {
          LOWORD(v29) = 1;
          *(_DWORD *)(a1 + 8) = a3;
          *(_DWORD *)(a1 + 4) = v28;
        }
        v30 = _InterlockedCompareExchange(
                a2,
                v26 ^ ((unsigned __int16)v26 ^ (unsigned __int16)(32 * v29)) & 0x3FE0,
                v24);
        if ( v24 == v30 )
          break;
        v24 = v30;
      }
      *(_DWORD *)a1 = (v24 & 1) == 0;
      goto LABEL_62;
    case 5:
LABEL_34:
      v16 = *a2;
      v17 = a3 == 5;
      while ( 1 )
      {
        *(_DWORD *)(a1 + 4) = 0;
        v18 = v16 | 1;
        if ( (((v16 | 1u) >> 22) & 1) != v17 )
        {
          if ( ((v18 >> 15) & 0x7F) != 0 )
          {
            *(_DWORD *)(a1 + 4) = (v18 >> 15) & 0x7F;
            v19 = 5;
            if ( a3 != 1 )
              v19 = 1;
            v18 = v16 & 0xFFC07FFE | 1;
            *(_DWORD *)(a1 + 8) = v19;
          }
          v20 = 0;
          if ( a3 == 5 )
            v20 = 0x400000;
          v18 = v18 & 0xFFBFFFFF | v20;
        }
        v21 = (v18 >> 15) & 0x7F;
        v22 = v21 + 1;
        if ( v21 + 1 > 0x7F || v22 < v21 )
        {
          v22 = 1;
          *(_DWORD *)(a1 + 8) = a3;
          *(_DWORD *)(a1 + 4) = v21;
        }
        v23 = _InterlockedCompareExchange(a2, v18 ^ (v18 ^ (v22 << 15)) & 0x3F8000, v16);
        if ( v16 == v23 )
          break;
        v16 = v23;
      }
      *(_DWORD *)a1 = (v16 & 1) == 0;
LABEL_62:
      *(_DWORD *)(a1 + 16) = 0;
      return a1;
  }
  if ( (unsigned int)(a3 - 6) >= 2 )
  {
    v7 = a3 - 320;
    if ( v7 >= 64 )
      goto LABEL_16;
    v8 = *((_DWORD *)a2 + 1);
    do
    {
      v9 = (v8 & 0x10) != 0 && ((v8 >> 5) & 0x3F) == v7;
      *(_DWORD *)(a1 + 16) = v9;
      v10 = v8;
      v8 = _InterlockedCompareExchange(
             a2 + 1,
             v8 ^ ((unsigned __int16)v8 ^ (unsigned __int16)(32 * v7)) & 0x7E0 | 0x10,
             v8);
    }
    while ( v10 != v8 );
    if ( !*(_DWORD *)(a1 + 16) )
    {
LABEL_16:
      *(_DWORD *)(a1 + 8) = a3;
      *(_DWORD *)(a1 + 4) = 1;
      *(_DWORD *)(a1 + 12) = a4;
    }
    return a1;
  }
LABEL_17:
  v11 = 0;
  switch ( a3 )
  {
    case 2:
      v11 = 2;
      break;
    case 3:
      v11 = 8;
      break;
    case 6:
      v11 = 4;
      break;
    case 7:
      v11 = 16;
      break;
  }
  v12 = *a2;
  v13 = 1;
  while ( 1 )
  {
    v14 = v12 | v11 | 1;
    *(_DWORD *)(a1 + 16) = (v12 | v11) == v12;
    if ( (v12 | v11) == v12 )
      v14 = v12 | v11;
    v15 = _InterlockedCompareExchange(a2, v14, v12);
    if ( v12 == v15 )
      break;
    v12 = v15;
  }
  if ( (v14 & 1) == 0 || (v12 & 1) != 0 )
    v13 = 0;
  *(_DWORD *)a1 = v13;
  return a1;
}

```

## disassembly

```asm
0x140002324  push    rbx
0x140002326  push    rbp
0x140002327  push    rsi
0x140002328  push    rdi
0x140002329  xor     eax, eax
0x14000232b  xorps   xmm0, xmm0
0x14000232e  mov     r10, rcx
0x140002331  mov     edi, r9d
0x140002334  mov     r11d, r8d
0x140002337  mov     rsi, rdx
0x14000233a  movups  xmmword ptr [rcx], xmm0
0x14000233d  mov     [rcx+10h], rax
0x140002341  mov     ecx, r8d
0x140002344  test    r8d, r8d
0x140002347  jz      loc_140002520
0x14000234d  sub     ecx, 1
0x140002350  jz      loc_140002467
0x140002356  sub     ecx, 1
0x140002359  jz      loc_1400023EE
0x14000235f  sub     ecx, 1
0x140002362  jz      loc_1400023EE
0x140002368  sub     ecx, 1
0x14000236b  jz      loc_140002520
0x140002371  sub     ecx, 1
0x140002374  jz      loc_140002467
0x14000237a  sub     ecx, 1
0x14000237d  jz      short loc_1400023EE
0x14000237f  cmp     ecx, 1
0x140002382  jz      short loc_1400023EE
0x140002384  add     r8d, 0FFFFFEC0h
0x14000238b  lea     ebx, [rax+1]
0x14000238e  cmp     r8d, 40h ; '@'
0x140002392  jge     short loc_1400023DD
0x140002394  mov     eax, [rdx+4]
0x140002397  lea     ecx, [rbx+0Fh]
0x14000239a  mov     r9d, r8d
0x14000239d  shl     r9d, 5
0x1400023a1  test    cl, al
0x1400023a3  jz      short loc_1400023B6
0x1400023a5  mov     edx, eax
0x1400023a7  shr     edx, 5
0x1400023aa  and     edx, 3Fh
0x1400023ad  cmp     edx, r8d
0x1400023b0  jnz     short loc_1400023B6
0x1400023b2  mov     edx, ebx
0x1400023b4  jmp     short loc_1400023B8
0x1400023b6  xor     edx, edx
0x1400023b8  mov     [r10+10h], edx
0x1400023bc  mov     edx, r9d
0x1400023bf  xor     edx, eax
0x1400023c1  and     edx, 7E0h
0x1400023c7  xor     edx, eax
0x1400023c9  or      edx, ecx
0x1400023cb  lock cmpxchg [rsi+4], edx
0x1400023d0  jnz     short loc_1400023A1
0x1400023d2  cmp     dword ptr [r10+10h], 0
0x1400023d7  jnz     loc_1400025EE
0x1400023dd  mov     [r10+8], r11d
0x1400023e1  mov     [r10+4], ebx
0x1400023e5  mov     [r10+0Ch], edi
0x1400023e9  jmp     loc_1400025EE
0x1400023ee  xor     ecx, ecx
0x1400023f0  sub     r11d, 2
0x1400023f4  jz      short loc_14000241C
0x1400023f6  sub     r11d, 1
0x1400023fa  jz      short loc_140002415
0x1400023fc  sub     r11d, 3
0x140002400  jz      short loc_14000240E
0x140002402  cmp     r11d, 1
0x140002406  jnz     short loc_140002421
0x140002408  lea     ecx, [r11+0Fh]
0x14000240c  jmp     short loc_140002421
0x14000240e  mov     ecx, 4
0x140002413  jmp     short loc_140002421
0x140002415  mov     ecx, 8
0x14000241a  jmp     short loc_140002421
0x14000241c  mov     ecx, 2
0x140002421  mov     edx, [rdx]
0x140002423  mov     ebx, 1
0x140002428  xor     eax, eax
0x14000242a  mov     r8d, ecx
0x14000242d  or      r8d, edx
0x140002430  cmp     r8d, edx
0x140002433  mov     r9d, r8d
0x140002436  setz    al
0x140002439  or      r9d, ebx
0x14000243c  cmp     r8d, edx
0x14000243f  mov     [r10+10h], eax
0x140002443  mov     eax, edx
0x140002445  cmovz   r9d, r8d
0x140002449  lock cmpxchg [rsi], r9d
0x14000244e  jz      short loc_140002454
0x140002450  mov     edx, eax
0x140002452  jmp     short loc_140002428
0x140002454  test    bl, r9b
0x140002457  jz      short loc_14000245D
0x140002459  test    bl, dl
0x14000245b  jz      short loc_14000245F
0x14000245d  xor     ebx, ebx
0x14000245f  mov     [r10], ebx
0x140002462  jmp     loc_1400025EE
0x140002467  mov     ecx, [rdx]
0x140002469  xor     r9d, r9d
0x14000246c  cmp     r11d, 5
0x140002470  mov     ebx, 1
0x140002475  setz    r9b
0x140002479  mov     eax, ecx
0x14000247b  mov     dword ptr [r10+4], 0
0x140002483  or      eax, ebx
0x140002485  mov     edx, eax
0x140002487  shr     edx, 16h
0x14000248a  and     edx, ebx
0x14000248c  cmp     edx, r9d
0x14000248f  jz      short loc_1400024D1
0x140002491  mov     r8d, eax
0x140002494  shr     r8d, 0Fh
0x140002498  and     r8d, 7Fh
0x14000249c  jbe     short loc_1400024B6
0x14000249e  cmp     r11d, ebx
0x1400024a1  mov     [r10+4], r8d
0x1400024a5  mov     edx, 5
0x1400024aa  cmovnz  edx, ebx
0x1400024ad  and     eax, 0FFC07FFFh
0x1400024b2  mov     [r10+8], edx
0x1400024b6  xor     r8d, r8d
0x1400024b9  mov     edx, 400000h
0x1400024be  cmp     r11d, 5
0x1400024c2  cmovz   r8d, edx
0x1400024c6  mov     edx, eax
0x1400024c8  btr     edx, 16h
0x1400024cc  mov     eax, r8d
0x1400024cf  or      eax, edx
0x1400024d1  mov     edx, eax
0x1400024d3  shr     edx, 0Fh
0x1400024d6  and     edx, 7Fh
0x1400024d9  lea     r8d, [rdx+1]
0x1400024dd  cmp     r8d, 7Fh
0x1400024e1  ja      short loc_1400024E8
0x1400024e3  cmp     r8d, edx
0x1400024e6  jnb     short loc_1400024F3
0x1400024e8  mov     r8d, ebx
0x1400024eb  mov     [r10+8], r11d
0x1400024ef  mov     [r10+4], edx
0x1400024f3  shl     r8d, 0Fh
0x1400024f7  xor     r8d, eax
0x1400024fa  and     r8d, 3F8000h
0x140002501  xor     r8d, eax
0x140002504  mov     eax, ecx
0x140002506  lock cmpxchg [rsi], r8d
0x14000250b  jz      short loc_140002514
0x14000250d  mov     ecx, eax
0x14000250f  jmp     loc_140002479
0x140002514  not     ecx
0x140002516  and     ecx, ebx
0x140002518  mov     [r10], ecx
0x14000251b  jmp     loc_1400025E6
0x140002520  mov     edx, [rdx]
0x140002522  xor     ebp, ebp
0x140002524  lea     ecx, [rbp+4]
0x140002527  cmp     r11d, ecx
0x14000252a  lea     ebx, [rcx-3]
0x14000252d  setz    bpl
0x140002531  mov     eax, edx
0x140002533  mov     dword ptr [r10+4], 0
0x14000253b  or      eax, ebx
0x14000253d  mov     r8d, eax
0x140002540  shr     r8d, 0Eh
0x140002544  and     r8d, ebx
0x140002547  cmp     r8d, ebp
0x14000254a  jz      short loc_140002593
0x14000254c  mov     edi, eax
0x14000254e  shr     edi, 5
0x140002551  and     edi, 1FFh
0x140002557  jbe     short loc_140002575
0x140002559  mov     r8d, r11d
0x14000255c  mov     [r10+4], edi
0x140002560  neg     r8d
0x140002563  sbb     r9d, r9d
0x140002566  not     r9d
0x140002569  and     r9d, ecx
0x14000256c  mov     [r10+8], r9d
0x140002570  and     eax, 0FFFFC01Fh
0x140002575  xor     r9d, r9d
0x140002578  mov     r8d, 4000h
0x14000257e  cmp     r11d, ecx
0x140002581  cmovz   r9d, r8d
0x140002585  mov     r8d, eax
0x140002588  btr     r8d, 0Eh
0x14000258d  mov     eax, r9d
0x140002590  or      eax, r8d
0x140002593  mov     r8d, eax
0x140002596  shr     r8d, 5
0x14000259a  and     r8d, 1FFh
0x1400025a1  lea     r9d, [r8+1]
0x1400025a5  cmp     r9d, 1FFh
0x1400025ac  ja      short loc_1400025B3
0x1400025ae  cmp     r9d, r8d
0x1400025b1  jnb     short loc_1400025BE
0x1400025b3  mov     r9d, ebx
0x1400025b6  mov     [r10+8], r11d
0x1400025ba  mov     [r10+4], r8d
0x1400025be  shl     r9d, 5
0x1400025c2  xor     r9d, eax
0x1400025c5  and     r9d, 3FE0h
0x1400025cc  xor     r9d, eax
0x1400025cf  mov     eax, edx
0x1400025d1  lock cmpxchg [rsi], r9d
0x1400025d6  jz      short loc_1400025DF
0x1400025d8  mov     edx, eax
0x1400025da  jmp     loc_140002531
0x1400025df  not     edx
0x1400025e1  and     edx, ebx
0x1400025e3  mov     [r10], edx
0x1400025e6  mov     dword ptr [r10+10h], 0
0x1400025ee  mov     rax, r10
0x1400025f1  pop     rdi
0x1400025f2  pop     rsi
0x1400025f3  pop     rbp
0x1400025f4  pop     rbx
0x1400025f5  retn
```
