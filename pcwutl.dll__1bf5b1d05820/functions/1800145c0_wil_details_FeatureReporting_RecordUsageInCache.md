# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x1800145c0`
- end: `0x180014892`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `722`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800149c4`

## callees

- `0x1800145c0`

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
0x1800145c0  push    rbx
0x1800145c2  push    rbp
0x1800145c3  push    rsi
0x1800145c4  push    rdi
0x1800145c5  xor     eax, eax
0x1800145c7  xorps   xmm0, xmm0
0x1800145ca  mov     r10, rcx
0x1800145cd  mov     edi, r9d
0x1800145d0  mov     r11d, r8d
0x1800145d3  mov     rsi, rdx
0x1800145d6  movups  xmmword ptr [rcx], xmm0
0x1800145d9  mov     [rcx+10h], rax
0x1800145dd  mov     ecx, r8d
0x1800145e0  test    r8d, r8d
0x1800145e3  jz      loc_1800147BC
0x1800145e9  sub     ecx, 1
0x1800145ec  jz      loc_180014703
0x1800145f2  sub     ecx, 1
0x1800145f5  jz      loc_18001468A
0x1800145fb  sub     ecx, 1
0x1800145fe  jz      loc_18001468A
0x180014604  sub     ecx, 1
0x180014607  jz      loc_1800147BC
0x18001460d  sub     ecx, 1
0x180014610  jz      loc_180014703
0x180014616  sub     ecx, 1
0x180014619  jz      short loc_18001468A
0x18001461b  cmp     ecx, 1
0x18001461e  jz      short loc_18001468A
0x180014620  add     r8d, 0FFFFFEC0h
0x180014627  lea     ebx, [rax+1]
0x18001462a  cmp     r8d, 40h ; '@'
0x18001462e  jge     short loc_180014679
0x180014630  mov     eax, [rdx+4]
0x180014633  lea     ecx, [rbx+0Fh]
0x180014636  mov     r9d, r8d
0x180014639  shl     r9d, 5
0x18001463d  test    cl, al
0x18001463f  jz      short loc_180014652
0x180014641  mov     edx, eax
0x180014643  shr     edx, 5
0x180014646  and     edx, 3Fh
0x180014649  cmp     edx, r8d
0x18001464c  jnz     short loc_180014652
0x18001464e  mov     edx, ebx
0x180014650  jmp     short loc_180014654
0x180014652  xor     edx, edx
0x180014654  mov     [r10+10h], edx
0x180014658  mov     edx, r9d
0x18001465b  xor     edx, eax
0x18001465d  and     edx, 7E0h
0x180014663  xor     edx, eax
0x180014665  or      edx, ecx
0x180014667  lock cmpxchg [rsi+4], edx
0x18001466c  jnz     short loc_18001463D
0x18001466e  cmp     dword ptr [r10+10h], 0
0x180014673  jnz     loc_18001488A
0x180014679  mov     [r10+8], r11d
0x18001467d  mov     [r10+4], ebx
0x180014681  mov     [r10+0Ch], edi
0x180014685  jmp     loc_18001488A
0x18001468a  xor     ecx, ecx
0x18001468c  sub     r11d, 2
0x180014690  jz      short loc_1800146B8
0x180014692  sub     r11d, 1
0x180014696  jz      short loc_1800146B1
0x180014698  sub     r11d, 3
0x18001469c  jz      short loc_1800146AA
0x18001469e  cmp     r11d, 1
0x1800146a2  jnz     short loc_1800146BD
0x1800146a4  lea     ecx, [r11+0Fh]
0x1800146a8  jmp     short loc_1800146BD
0x1800146aa  mov     ecx, 4
0x1800146af  jmp     short loc_1800146BD
0x1800146b1  mov     ecx, 8
0x1800146b6  jmp     short loc_1800146BD
0x1800146b8  mov     ecx, 2
0x1800146bd  mov     edx, [rdx]
0x1800146bf  mov     ebx, 1
0x1800146c4  xor     eax, eax
0x1800146c6  mov     r8d, ecx
0x1800146c9  or      r8d, edx
0x1800146cc  cmp     r8d, edx
0x1800146cf  mov     r9d, r8d
0x1800146d2  setz    al
0x1800146d5  or      r9d, ebx
0x1800146d8  cmp     r8d, edx
0x1800146db  mov     [r10+10h], eax
0x1800146df  mov     eax, edx
0x1800146e1  cmovz   r9d, r8d
0x1800146e5  lock cmpxchg [rsi], r9d
0x1800146ea  jz      short loc_1800146F0
0x1800146ec  mov     edx, eax
0x1800146ee  jmp     short loc_1800146C4
0x1800146f0  test    bl, r9b
0x1800146f3  jz      short loc_1800146F9
0x1800146f5  test    bl, dl
0x1800146f7  jz      short loc_1800146FB
0x1800146f9  xor     ebx, ebx
0x1800146fb  mov     [r10], ebx
0x1800146fe  jmp     loc_18001488A
0x180014703  mov     ecx, [rdx]
0x180014705  xor     r9d, r9d
0x180014708  cmp     r11d, 5
0x18001470c  mov     ebx, 1
0x180014711  setz    r9b
0x180014715  mov     eax, ecx
0x180014717  mov     dword ptr [r10+4], 0
0x18001471f  or      eax, ebx
0x180014721  mov     edx, eax
0x180014723  shr     edx, 16h
0x180014726  and     edx, ebx
0x180014728  cmp     edx, r9d
0x18001472b  jz      short loc_18001476D
0x18001472d  mov     r8d, eax
0x180014730  shr     r8d, 0Fh
0x180014734  and     r8d, 7Fh
0x180014738  jbe     short loc_180014752
0x18001473a  cmp     r11d, ebx
0x18001473d  mov     [r10+4], r8d
0x180014741  mov     edx, 5
0x180014746  cmovnz  edx, ebx
0x180014749  and     eax, 0FFC07FFFh
0x18001474e  mov     [r10+8], edx
0x180014752  xor     r8d, r8d
0x180014755  mov     edx, 400000h
0x18001475a  cmp     r11d, 5
0x18001475e  cmovz   r8d, edx
0x180014762  mov     edx, eax
0x180014764  btr     edx, 16h
0x180014768  mov     eax, r8d
0x18001476b  or      eax, edx
0x18001476d  mov     edx, eax
0x18001476f  shr     edx, 0Fh
0x180014772  and     edx, 7Fh
0x180014775  lea     r8d, [rdx+1]
0x180014779  cmp     r8d, 7Fh
0x18001477d  ja      short loc_180014784
0x18001477f  cmp     r8d, edx
0x180014782  jnb     short loc_18001478F
0x180014784  mov     r8d, ebx
0x180014787  mov     [r10+8], r11d
0x18001478b  mov     [r10+4], edx
0x18001478f  shl     r8d, 0Fh
0x180014793  xor     r8d, eax
0x180014796  and     r8d, 3F8000h
0x18001479d  xor     r8d, eax
0x1800147a0  mov     eax, ecx
0x1800147a2  lock cmpxchg [rsi], r8d
0x1800147a7  jz      short loc_1800147B0
0x1800147a9  mov     ecx, eax
0x1800147ab  jmp     loc_180014715
0x1800147b0  not     ecx
0x1800147b2  and     ecx, ebx
0x1800147b4  mov     [r10], ecx
0x1800147b7  jmp     loc_180014882
0x1800147bc  mov     edx, [rdx]
0x1800147be  xor     ebp, ebp
0x1800147c0  lea     ecx, [rbp+4]
0x1800147c3  cmp     r11d, ecx
0x1800147c6  lea     ebx, [rcx-3]
0x1800147c9  setz    bpl
0x1800147cd  mov     eax, edx
0x1800147cf  mov     dword ptr [r10+4], 0
0x1800147d7  or      eax, ebx
0x1800147d9  mov     r8d, eax
0x1800147dc  shr     r8d, 0Eh
0x1800147e0  and     r8d, ebx
0x1800147e3  cmp     r8d, ebp
0x1800147e6  jz      short loc_18001482F
0x1800147e8  mov     edi, eax
0x1800147ea  shr     edi, 5
0x1800147ed  and     edi, 1FFh
0x1800147f3  jbe     short loc_180014811
0x1800147f5  mov     r8d, r11d
0x1800147f8  mov     [r10+4], edi
0x1800147fc  neg     r8d
0x1800147ff  sbb     r9d, r9d
0x180014802  not     r9d
0x180014805  and     r9d, ecx
0x180014808  mov     [r10+8], r9d
0x18001480c  and     eax, 0FFFFC01Fh
0x180014811  xor     r9d, r9d
0x180014814  mov     r8d, 4000h
0x18001481a  cmp     r11d, ecx
0x18001481d  cmovz   r9d, r8d
0x180014821  mov     r8d, eax
0x180014824  btr     r8d, 0Eh
0x180014829  mov     eax, r9d
0x18001482c  or      eax, r8d
0x18001482f  mov     r8d, eax
0x180014832  shr     r8d, 5
0x180014836  and     r8d, 1FFh
0x18001483d  lea     r9d, [r8+1]
0x180014841  cmp     r9d, 1FFh
0x180014848  ja      short loc_18001484F
0x18001484a  cmp     r9d, r8d
0x18001484d  jnb     short loc_18001485A
0x18001484f  mov     r9d, ebx
0x180014852  mov     [r10+8], r11d
0x180014856  mov     [r10+4], r8d
0x18001485a  shl     r9d, 5
0x18001485e  xor     r9d, eax
0x180014861  and     r9d, 3FE0h
0x180014868  xor     r9d, eax
0x18001486b  mov     eax, edx
0x18001486d  lock cmpxchg [rsi], r9d
0x180014872  jz      short loc_18001487B
0x180014874  mov     edx, eax
0x180014876  jmp     loc_1800147CD
0x18001487b  not     edx
0x18001487d  and     edx, ebx
0x18001487f  mov     [r10], edx
0x180014882  mov     dword ptr [r10+10h], 0
0x18001488a  mov     rax, r10
0x18001488d  pop     rdi
0x18001488e  pop     rsi
0x18001488f  pop     rbp
0x180014890  pop     rbx
0x180014891  retn
```
