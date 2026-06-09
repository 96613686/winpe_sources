# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x180024f50`
- end: `0x180025222`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `722`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001de4c`

## callees

- `0x180024f50`

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
0x180024f50  push    rbx
0x180024f52  push    rbp
0x180024f53  push    rsi
0x180024f54  push    rdi
0x180024f55  xor     eax, eax
0x180024f57  xorps   xmm0, xmm0
0x180024f5a  mov     r10, rcx
0x180024f5d  mov     edi, r9d
0x180024f60  mov     r11d, r8d
0x180024f63  mov     rsi, rdx
0x180024f66  movups  xmmword ptr [rcx], xmm0
0x180024f69  mov     [rcx+10h], rax
0x180024f6d  mov     ecx, r8d
0x180024f70  test    r8d, r8d
0x180024f73  jz      loc_18002514C
0x180024f79  sub     ecx, 1
0x180024f7c  jz      loc_180025093
0x180024f82  sub     ecx, 1
0x180024f85  jz      loc_18002501A
0x180024f8b  sub     ecx, 1
0x180024f8e  jz      loc_18002501A
0x180024f94  sub     ecx, 1
0x180024f97  jz      loc_18002514C
0x180024f9d  sub     ecx, 1
0x180024fa0  jz      loc_180025093
0x180024fa6  sub     ecx, 1
0x180024fa9  jz      short loc_18002501A
0x180024fab  cmp     ecx, 1
0x180024fae  jz      short loc_18002501A
0x180024fb0  add     r8d, 0FFFFFEC0h
0x180024fb7  lea     ebx, [rax+1]
0x180024fba  cmp     r8d, 40h ; '@'
0x180024fbe  jge     short loc_180025009
0x180024fc0  mov     eax, [rdx+4]
0x180024fc3  lea     ecx, [rbx+0Fh]
0x180024fc6  mov     r9d, r8d
0x180024fc9  shl     r9d, 5
0x180024fcd  test    cl, al
0x180024fcf  jz      short loc_180024FE2
0x180024fd1  mov     edx, eax
0x180024fd3  shr     edx, 5
0x180024fd6  and     edx, 3Fh
0x180024fd9  cmp     edx, r8d
0x180024fdc  jnz     short loc_180024FE2
0x180024fde  mov     edx, ebx
0x180024fe0  jmp     short loc_180024FE4
0x180024fe2  xor     edx, edx
0x180024fe4  mov     [r10+10h], edx
0x180024fe8  mov     edx, r9d
0x180024feb  xor     edx, eax
0x180024fed  and     edx, 7E0h
0x180024ff3  xor     edx, eax
0x180024ff5  or      edx, ecx
0x180024ff7  lock cmpxchg [rsi+4], edx
0x180024ffc  jnz     short loc_180024FCD
0x180024ffe  cmp     dword ptr [r10+10h], 0
0x180025003  jnz     loc_18002521A
0x180025009  mov     [r10+8], r11d
0x18002500d  mov     [r10+4], ebx
0x180025011  mov     [r10+0Ch], edi
0x180025015  jmp     loc_18002521A
0x18002501a  xor     ecx, ecx
0x18002501c  sub     r11d, 2
0x180025020  jz      short loc_180025048
0x180025022  sub     r11d, 1
0x180025026  jz      short loc_180025041
0x180025028  sub     r11d, 3
0x18002502c  jz      short loc_18002503A
0x18002502e  cmp     r11d, 1
0x180025032  jnz     short loc_18002504D
0x180025034  lea     ecx, [r11+0Fh]
0x180025038  jmp     short loc_18002504D
0x18002503a  mov     ecx, 4
0x18002503f  jmp     short loc_18002504D
0x180025041  mov     ecx, 8
0x180025046  jmp     short loc_18002504D
0x180025048  mov     ecx, 2
0x18002504d  mov     edx, [rdx]
0x18002504f  mov     ebx, 1
0x180025054  xor     eax, eax
0x180025056  mov     r8d, ecx
0x180025059  or      r8d, edx
0x18002505c  cmp     r8d, edx
0x18002505f  mov     r9d, r8d
0x180025062  setz    al
0x180025065  or      r9d, ebx
0x180025068  cmp     r8d, edx
0x18002506b  mov     [r10+10h], eax
0x18002506f  mov     eax, edx
0x180025071  cmovz   r9d, r8d
0x180025075  lock cmpxchg [rsi], r9d
0x18002507a  jz      short loc_180025080
0x18002507c  mov     edx, eax
0x18002507e  jmp     short loc_180025054
0x180025080  test    bl, r9b
0x180025083  jz      short loc_180025089
0x180025085  test    bl, dl
0x180025087  jz      short loc_18002508B
0x180025089  xor     ebx, ebx
0x18002508b  mov     [r10], ebx
0x18002508e  jmp     loc_18002521A
0x180025093  mov     ecx, [rdx]
0x180025095  xor     r9d, r9d
0x180025098  cmp     r11d, 5
0x18002509c  mov     ebx, 1
0x1800250a1  setz    r9b
0x1800250a5  mov     eax, ecx
0x1800250a7  mov     dword ptr [r10+4], 0
0x1800250af  or      eax, ebx
0x1800250b1  mov     edx, eax
0x1800250b3  shr     edx, 16h
0x1800250b6  and     edx, ebx
0x1800250b8  cmp     edx, r9d
0x1800250bb  jz      short loc_1800250FD
0x1800250bd  mov     r8d, eax
0x1800250c0  shr     r8d, 0Fh
0x1800250c4  and     r8d, 7Fh
0x1800250c8  jbe     short loc_1800250E2
0x1800250ca  cmp     r11d, ebx
0x1800250cd  mov     [r10+4], r8d
0x1800250d1  mov     edx, 5
0x1800250d6  cmovnz  edx, ebx
0x1800250d9  and     eax, 0FFC07FFFh
0x1800250de  mov     [r10+8], edx
0x1800250e2  xor     r8d, r8d
0x1800250e5  mov     edx, 400000h
0x1800250ea  cmp     r11d, 5
0x1800250ee  cmovz   r8d, edx
0x1800250f2  mov     edx, eax
0x1800250f4  btr     edx, 16h
0x1800250f8  mov     eax, r8d
0x1800250fb  or      eax, edx
0x1800250fd  mov     edx, eax
0x1800250ff  shr     edx, 0Fh
0x180025102  and     edx, 7Fh
0x180025105  lea     r8d, [rdx+1]
0x180025109  cmp     r8d, 7Fh
0x18002510d  ja      short loc_180025114
0x18002510f  cmp     r8d, edx
0x180025112  jnb     short loc_18002511F
0x180025114  mov     r8d, ebx
0x180025117  mov     [r10+8], r11d
0x18002511b  mov     [r10+4], edx
0x18002511f  shl     r8d, 0Fh
0x180025123  xor     r8d, eax
0x180025126  and     r8d, 3F8000h
0x18002512d  xor     r8d, eax
0x180025130  mov     eax, ecx
0x180025132  lock cmpxchg [rsi], r8d
0x180025137  jz      short loc_180025140
0x180025139  mov     ecx, eax
0x18002513b  jmp     loc_1800250A5
0x180025140  not     ecx
0x180025142  and     ecx, ebx
0x180025144  mov     [r10], ecx
0x180025147  jmp     loc_180025212
0x18002514c  mov     edx, [rdx]
0x18002514e  xor     ebp, ebp
0x180025150  lea     ecx, [rbp+4]
0x180025153  cmp     r11d, ecx
0x180025156  lea     ebx, [rcx-3]
0x180025159  setz    bpl
0x18002515d  mov     eax, edx
0x18002515f  mov     dword ptr [r10+4], 0
0x180025167  or      eax, ebx
0x180025169  mov     r8d, eax
0x18002516c  shr     r8d, 0Eh
0x180025170  and     r8d, ebx
0x180025173  cmp     r8d, ebp
0x180025176  jz      short loc_1800251BF
0x180025178  mov     edi, eax
0x18002517a  shr     edi, 5
0x18002517d  and     edi, 1FFh
0x180025183  jbe     short loc_1800251A1
0x180025185  mov     r8d, r11d
0x180025188  mov     [r10+4], edi
0x18002518c  neg     r8d
0x18002518f  sbb     r9d, r9d
0x180025192  not     r9d
0x180025195  and     r9d, ecx
0x180025198  mov     [r10+8], r9d
0x18002519c  and     eax, 0FFFFC01Fh
0x1800251a1  xor     r9d, r9d
0x1800251a4  mov     r8d, 4000h
0x1800251aa  cmp     r11d, ecx
0x1800251ad  cmovz   r9d, r8d
0x1800251b1  mov     r8d, eax
0x1800251b4  btr     r8d, 0Eh
0x1800251b9  mov     eax, r9d
0x1800251bc  or      eax, r8d
0x1800251bf  mov     r8d, eax
0x1800251c2  shr     r8d, 5
0x1800251c6  and     r8d, 1FFh
0x1800251cd  lea     r9d, [r8+1]
0x1800251d1  cmp     r9d, 1FFh
0x1800251d8  ja      short loc_1800251DF
0x1800251da  cmp     r9d, r8d
0x1800251dd  jnb     short loc_1800251EA
0x1800251df  mov     r9d, ebx
0x1800251e2  mov     [r10+8], r11d
0x1800251e6  mov     [r10+4], r8d
0x1800251ea  shl     r9d, 5
0x1800251ee  xor     r9d, eax
0x1800251f1  and     r9d, 3FE0h
0x1800251f8  xor     r9d, eax
0x1800251fb  mov     eax, edx
0x1800251fd  lock cmpxchg [rsi], r9d
0x180025202  jz      short loc_18002520B
0x180025204  mov     edx, eax
0x180025206  jmp     loc_18002515D
0x18002520b  not     edx
0x18002520d  and     edx, ebx
0x18002520f  mov     [r10], edx
0x180025212  mov     dword ptr [r10+10h], 0
0x18002521a  mov     rax, r10
0x18002521d  pop     rdi
0x18002521e  pop     rsi
0x18002521f  pop     rbp
0x180025220  pop     rbx
0x180025221  retn
```
