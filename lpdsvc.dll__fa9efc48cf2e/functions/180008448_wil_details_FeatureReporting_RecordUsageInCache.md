# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x180008448`
- end: `0x18000871a`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `722`
- prototype: `__int64 __fastcall(__int64, volatile signed __int32 *, int, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000883c`

## callees

- `0x180008448`

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
0x180008448  push    rbx
0x18000844a  push    rbp
0x18000844b  push    rsi
0x18000844c  push    rdi
0x18000844d  xor     eax, eax
0x18000844f  xorps   xmm0, xmm0
0x180008452  mov     r10, rcx
0x180008455  mov     edi, r9d
0x180008458  mov     r11d, r8d
0x18000845b  mov     rsi, rdx
0x18000845e  movups  xmmword ptr [rcx], xmm0
0x180008461  mov     [rcx+10h], rax
0x180008465  mov     ecx, r8d
0x180008468  test    r8d, r8d
0x18000846b  jz      loc_180008644
0x180008471  sub     ecx, 1
0x180008474  jz      loc_18000858B
0x18000847a  sub     ecx, 1
0x18000847d  jz      loc_180008512
0x180008483  sub     ecx, 1
0x180008486  jz      loc_180008512
0x18000848c  sub     ecx, 1
0x18000848f  jz      loc_180008644
0x180008495  sub     ecx, 1
0x180008498  jz      loc_18000858B
0x18000849e  sub     ecx, 1
0x1800084a1  jz      short loc_180008512
0x1800084a3  cmp     ecx, 1
0x1800084a6  jz      short loc_180008512
0x1800084a8  add     r8d, 0FFFFFEC0h
0x1800084af  lea     ebx, [rax+1]
0x1800084b2  cmp     r8d, 40h ; '@'
0x1800084b6  jge     short loc_180008501
0x1800084b8  mov     eax, [rdx+4]
0x1800084bb  lea     ecx, [rbx+0Fh]
0x1800084be  mov     r9d, r8d
0x1800084c1  shl     r9d, 5
0x1800084c5  test    cl, al
0x1800084c7  jz      short loc_1800084DA
0x1800084c9  mov     edx, eax
0x1800084cb  shr     edx, 5
0x1800084ce  and     edx, 3Fh
0x1800084d1  cmp     edx, r8d
0x1800084d4  jnz     short loc_1800084DA
0x1800084d6  mov     edx, ebx
0x1800084d8  jmp     short loc_1800084DC
0x1800084da  xor     edx, edx
0x1800084dc  mov     [r10+10h], edx
0x1800084e0  mov     edx, r9d
0x1800084e3  xor     edx, eax
0x1800084e5  and     edx, 7E0h
0x1800084eb  xor     edx, eax
0x1800084ed  or      edx, ecx
0x1800084ef  lock cmpxchg [rsi+4], edx
0x1800084f4  jnz     short loc_1800084C5
0x1800084f6  cmp     dword ptr [r10+10h], 0
0x1800084fb  jnz     loc_180008712
0x180008501  mov     [r10+8], r11d
0x180008505  mov     [r10+4], ebx
0x180008509  mov     [r10+0Ch], edi
0x18000850d  jmp     loc_180008712
0x180008512  xor     ecx, ecx
0x180008514  sub     r11d, 2
0x180008518  jz      short loc_180008540
0x18000851a  sub     r11d, 1
0x18000851e  jz      short loc_180008539
0x180008520  sub     r11d, 3
0x180008524  jz      short loc_180008532
0x180008526  cmp     r11d, 1
0x18000852a  jnz     short loc_180008545
0x18000852c  lea     ecx, [r11+0Fh]
0x180008530  jmp     short loc_180008545
0x180008532  mov     ecx, 4
0x180008537  jmp     short loc_180008545
0x180008539  mov     ecx, 8
0x18000853e  jmp     short loc_180008545
0x180008540  mov     ecx, 2
0x180008545  mov     edx, [rdx]
0x180008547  mov     ebx, 1
0x18000854c  xor     eax, eax
0x18000854e  mov     r8d, ecx
0x180008551  or      r8d, edx
0x180008554  cmp     r8d, edx
0x180008557  mov     r9d, r8d
0x18000855a  setz    al
0x18000855d  or      r9d, ebx
0x180008560  cmp     r8d, edx
0x180008563  mov     [r10+10h], eax
0x180008567  mov     eax, edx
0x180008569  cmovz   r9d, r8d
0x18000856d  lock cmpxchg [rsi], r9d
0x180008572  jz      short loc_180008578
0x180008574  mov     edx, eax
0x180008576  jmp     short loc_18000854C
0x180008578  test    bl, r9b
0x18000857b  jz      short loc_180008581
0x18000857d  test    bl, dl
0x18000857f  jz      short loc_180008583
0x180008581  xor     ebx, ebx
0x180008583  mov     [r10], ebx
0x180008586  jmp     loc_180008712
0x18000858b  mov     ecx, [rdx]
0x18000858d  xor     r9d, r9d
0x180008590  cmp     r11d, 5
0x180008594  mov     ebx, 1
0x180008599  setz    r9b
0x18000859d  mov     eax, ecx
0x18000859f  mov     dword ptr [r10+4], 0
0x1800085a7  or      eax, ebx
0x1800085a9  mov     edx, eax
0x1800085ab  shr     edx, 16h
0x1800085ae  and     edx, ebx
0x1800085b0  cmp     edx, r9d
0x1800085b3  jz      short loc_1800085F5
0x1800085b5  mov     r8d, eax
0x1800085b8  shr     r8d, 0Fh
0x1800085bc  and     r8d, 7Fh
0x1800085c0  jbe     short loc_1800085DA
0x1800085c2  cmp     r11d, ebx
0x1800085c5  mov     [r10+4], r8d
0x1800085c9  mov     edx, 5
0x1800085ce  cmovnz  edx, ebx
0x1800085d1  and     eax, 0FFC07FFFh
0x1800085d6  mov     [r10+8], edx
0x1800085da  xor     r8d, r8d
0x1800085dd  mov     edx, 400000h
0x1800085e2  cmp     r11d, 5
0x1800085e6  cmovz   r8d, edx
0x1800085ea  mov     edx, eax
0x1800085ec  btr     edx, 16h
0x1800085f0  mov     eax, r8d
0x1800085f3  or      eax, edx
0x1800085f5  mov     edx, eax
0x1800085f7  shr     edx, 0Fh
0x1800085fa  and     edx, 7Fh
0x1800085fd  lea     r8d, [rdx+1]
0x180008601  cmp     r8d, 7Fh
0x180008605  ja      short loc_18000860C
0x180008607  cmp     r8d, edx
0x18000860a  jnb     short loc_180008617
0x18000860c  mov     r8d, ebx
0x18000860f  mov     [r10+8], r11d
0x180008613  mov     [r10+4], edx
0x180008617  shl     r8d, 0Fh
0x18000861b  xor     r8d, eax
0x18000861e  and     r8d, 3F8000h
0x180008625  xor     r8d, eax
0x180008628  mov     eax, ecx
0x18000862a  lock cmpxchg [rsi], r8d
0x18000862f  jz      short loc_180008638
0x180008631  mov     ecx, eax
0x180008633  jmp     loc_18000859D
0x180008638  not     ecx
0x18000863a  and     ecx, ebx
0x18000863c  mov     [r10], ecx
0x18000863f  jmp     loc_18000870A
0x180008644  mov     edx, [rdx]
0x180008646  xor     ebp, ebp
0x180008648  lea     ecx, [rbp+4]
0x18000864b  cmp     r11d, ecx
0x18000864e  lea     ebx, [rcx-3]
0x180008651  setz    bpl
0x180008655  mov     eax, edx
0x180008657  mov     dword ptr [r10+4], 0
0x18000865f  or      eax, ebx
0x180008661  mov     r8d, eax
0x180008664  shr     r8d, 0Eh
0x180008668  and     r8d, ebx
0x18000866b  cmp     r8d, ebp
0x18000866e  jz      short loc_1800086B7
0x180008670  mov     edi, eax
0x180008672  shr     edi, 5
0x180008675  and     edi, 1FFh
0x18000867b  jbe     short loc_180008699
0x18000867d  mov     r8d, r11d
0x180008680  mov     [r10+4], edi
0x180008684  neg     r8d
0x180008687  sbb     r9d, r9d
0x18000868a  not     r9d
0x18000868d  and     r9d, ecx
0x180008690  mov     [r10+8], r9d
0x180008694  and     eax, 0FFFFC01Fh
0x180008699  xor     r9d, r9d
0x18000869c  mov     r8d, 4000h
0x1800086a2  cmp     r11d, ecx
0x1800086a5  cmovz   r9d, r8d
0x1800086a9  mov     r8d, eax
0x1800086ac  btr     r8d, 0Eh
0x1800086b1  mov     eax, r9d
0x1800086b4  or      eax, r8d
0x1800086b7  mov     r8d, eax
0x1800086ba  shr     r8d, 5
0x1800086be  and     r8d, 1FFh
0x1800086c5  lea     r9d, [r8+1]
0x1800086c9  cmp     r9d, 1FFh
0x1800086d0  ja      short loc_1800086D7
0x1800086d2  cmp     r9d, r8d
0x1800086d5  jnb     short loc_1800086E2
0x1800086d7  mov     r9d, ebx
0x1800086da  mov     [r10+8], r11d
0x1800086de  mov     [r10+4], r8d
0x1800086e2  shl     r9d, 5
0x1800086e6  xor     r9d, eax
0x1800086e9  and     r9d, 3FE0h
0x1800086f0  xor     r9d, eax
0x1800086f3  mov     eax, edx
0x1800086f5  lock cmpxchg [rsi], r9d
0x1800086fa  jz      short loc_180008703
0x1800086fc  mov     edx, eax
0x1800086fe  jmp     loc_180008655
0x180008703  not     edx
0x180008705  and     edx, ebx
0x180008707  mov     [r10], edx
0x18000870a  mov     dword ptr [r10+10h], 0
0x180008712  mov     rax, r10
0x180008715  pop     rdi
0x180008716  pop     rsi
0x180008717  pop     rbp
0x180008718  pop     rbx
0x180008719  retn
```
