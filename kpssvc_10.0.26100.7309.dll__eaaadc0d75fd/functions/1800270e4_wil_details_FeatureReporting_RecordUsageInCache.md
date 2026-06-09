# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x1800270e4`
- end: `0x1800273c4`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `736`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180024d74`

## callees

- `0x1800270e4`

## pseudocode

```c
__int64 __fastcall wil_details_FeatureReporting_RecordUsageInCache(__int64 a1, volatile signed __int32 *a2, int a3)
{
  int v6; // r8d
  unsigned __int32 v7; // eax
  BOOL v8; // ecx
  unsigned __int32 v9; // ett
  int v10; // edx
  signed __int32 v11; // eax
  int v12; // ebx
  char v13; // r9
  signed __int32 v14; // r8d
  signed __int32 v15; // ett
  signed __int32 v16; // eax
  BOOL v17; // edi
  unsigned int v18; // ecx
  char v19; // r9
  int v20; // edx
  int v21; // r8d
  unsigned int v22; // r8d
  unsigned int v23; // edx
  signed __int32 v24; // ett
  signed __int32 v25; // eax
  BOOL v26; // r14d
  unsigned int v27; // ecx
  char v28; // di
  int v29; // r9d
  unsigned int v30; // r9d
  unsigned int v31; // r8d
  signed __int32 v32; // ett

  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  switch ( a3 )
  {
    case 0:
      goto LABEL_47;
    case 1:
      goto LABEL_33;
    case 2:
    case 3:
      goto LABEL_17;
    case 4:
LABEL_47:
      v25 = *a2;
      v26 = a3 == 4;
      do
      {
        *(_DWORD *)(a1 + 4) = 0;
        v27 = v25 | 1;
        v28 = v25;
        if ( (((v25 | 1u) >> 14) & 1) != v26 )
        {
          if ( ((v27 >> 5) & 0x1FF) != 0 )
          {
            *(_DWORD *)(a1 + 4) = (v27 >> 5) & 0x1FF;
            *(_DWORD *)(a1 + 8) = a3 == 0 ? 4 : 0;
            v27 = v25 & 0xFFFFC01E | 1;
          }
          v29 = 0;
          if ( a3 == 4 )
            v29 = 0x4000;
          v27 = v27 & 0xFFFFBFFF | v29;
        }
        v30 = (v27 >> 5) & 0x1FF;
        v31 = v30 + 1;
        if ( v30 + 1 > 0x1FF || v31 < v30 )
        {
          LOWORD(v31) = 1;
          *(_DWORD *)(a1 + 8) = a3;
          *(_DWORD *)(a1 + 4) = v30;
        }
        v32 = v25;
        v25 = _InterlockedCompareExchange(
                a2,
                ((unsigned __int16)v27 ^ (unsigned __int16)(32 * v31)) & 0x3FE0 ^ v27,
                v25);
      }
      while ( v32 != v25 );
      *(_DWORD *)a1 = (v28 & 1) == 0;
      goto LABEL_59;
    case 5:
LABEL_33:
      v16 = *a2;
      v17 = a3 == 5;
      do
      {
        *(_DWORD *)(a1 + 4) = 0;
        v18 = v16 | 1;
        v19 = v16;
        if ( (((v16 | 1u) >> 22) & 1) != v17 )
        {
          if ( ((v18 >> 15) & 0x7F) != 0 )
          {
            *(_DWORD *)(a1 + 4) = (v18 >> 15) & 0x7F;
            v20 = 5;
            if ( a3 != 1 )
              v20 = 1;
            v18 = v16 & 0xFFC07FFE | 1;
            *(_DWORD *)(a1 + 8) = v20;
          }
          v21 = 0;
          if ( a3 == 5 )
            v21 = 0x400000;
          v18 = v18 & 0xFFBFFFFF | v21;
        }
        v22 = (v18 >> 15) & 0x7F;
        v23 = v22 + 1;
        if ( v22 + 1 > 0x7F || v23 < v22 )
        {
          v23 = 1;
          *(_DWORD *)(a1 + 8) = a3;
          *(_DWORD *)(a1 + 4) = v22;
        }
        v24 = v16;
        v16 = _InterlockedCompareExchange(a2, (v18 ^ (v23 << 15)) & 0x3F8000 ^ v18, v16);
      }
      while ( v24 != v16 );
      *(_DWORD *)a1 = (v19 & 1) == 0;
LABEL_59:
      *(_DWORD *)(a1 + 16) = 0;
      return a1;
  }
  if ( (unsigned int)(a3 - 6) >= 2 )
  {
    v6 = a3 - 320;
    if ( v6 >= 64 )
      goto LABEL_16;
    v7 = *((_DWORD *)a2 + 1);
    do
    {
      v8 = (v7 & 0x10) != 0 && ((v7 >> 5) & 0x3F) == v6;
      *(_DWORD *)(a1 + 16) = v8;
      v9 = v7;
      v7 = _InterlockedCompareExchange(
             a2 + 1,
             v7 ^ ((unsigned __int16)v7 ^ (unsigned __int16)(32 * v6)) & 0x7E0 | 0x10,
             v7);
    }
    while ( v9 != v7 );
    if ( !*(_DWORD *)(a1 + 16) )
    {
LABEL_16:
      *(_DWORD *)(a1 + 12) = 0;
      *(_DWORD *)(a1 + 8) = a3;
      *(_DWORD *)(a1 + 4) = 1;
    }
    return a1;
  }
LABEL_17:
  v10 = 0;
  switch ( a3 )
  {
    case 2:
      v10 = 2;
      break;
    case 3:
      v10 = 8;
      break;
    case 6:
      v10 = 4;
      break;
    case 7:
      v10 = 16;
      break;
  }
  v11 = *a2;
  v12 = 1;
  do
  {
    v13 = v11;
    *(_DWORD *)(a1 + 16) = (v11 | v10) == v11;
    v14 = v11 | v10 | 1;
    if ( (v11 | v10) == v11 )
      v14 = v11 | v10;
    v15 = v11;
    v11 = _InterlockedCompareExchange(a2, v14, v11);
  }
  while ( v15 != v11 );
  if ( (v14 & 1) == 0 || (v13 & 1) != 0 )
    v12 = 0;
  *(_DWORD *)a1 = v12;
  return a1;
}

```

## disassembly

```asm
0x1800270e4  mov     rax, rsp
0x1800270e7  mov     [rax+8], rbx
0x1800270eb  mov     [rax+10h], rbp
0x1800270ef  mov     [rax+18h], rsi
0x1800270f3  mov     [rax+20h], rdi
0x1800270f7  push    r14
0x1800270f9  xor     eax, eax
0x1800270fb  xorps   xmm0, xmm0
0x1800270fe  mov     r10, rcx
0x180027101  mov     r11d, r8d
0x180027104  mov     rsi, rdx
0x180027107  movups  xmmword ptr [rcx], xmm0
0x18002710a  mov     [rcx+10h], rax
0x18002710e  mov     ecx, r8d
0x180027111  test    r8d, r8d
0x180027114  jz      loc_1800272E2
0x18002711a  sub     ecx, 1
0x18002711d  jz      loc_180027231
0x180027123  sub     ecx, 1
0x180027126  jz      loc_1800271BC
0x18002712c  sub     ecx, 1
0x18002712f  jz      loc_1800271BC
0x180027135  sub     ecx, 1
0x180027138  jz      loc_1800272E2
0x18002713e  sub     ecx, 1
0x180027141  jz      loc_180027231
0x180027147  sub     ecx, 1
0x18002714a  jz      short loc_1800271BC
0x18002714c  cmp     ecx, 1
0x18002714f  jz      short loc_1800271BC
0x180027151  add     r8d, 0FFFFFEC0h
0x180027158  lea     ebx, [rax+1]
0x18002715b  cmp     r8d, 40h ; '@'
0x18002715f  jge     short loc_1800271AA
0x180027161  mov     eax, [rdx+4]
0x180027164  mov     r9d, r8d
0x180027167  shl     r9d, 5
0x18002716b  lea     edx, [rbx+0Fh]
0x18002716e  test    dl, al
0x180027170  jz      short loc_180027183
0x180027172  mov     ecx, eax
0x180027174  shr     ecx, 5
0x180027177  and     ecx, 3Fh
0x18002717a  cmp     ecx, r8d
0x18002717d  jnz     short loc_180027183
0x18002717f  mov     ecx, ebx
0x180027181  jmp     short loc_180027185
0x180027183  xor     ecx, ecx
0x180027185  mov     [r10+10h], ecx
0x180027189  mov     ecx, r9d
0x18002718c  xor     ecx, eax
0x18002718e  and     ecx, 7E0h
0x180027194  xor     ecx, eax
0x180027196  or      ecx, edx
0x180027198  lock cmpxchg [rsi+4], ecx
0x18002719d  jnz     short loc_18002716E
0x18002719f  cmp     dword ptr [r10+10h], 0
0x1800271a4  jnz     loc_1800273A9
0x1800271aa  and     dword ptr [r10+0Ch], 0
0x1800271af  mov     [r10+8], r11d
0x1800271b3  mov     [r10+4], ebx
0x1800271b7  jmp     loc_1800273A9
0x1800271bc  xor     edx, edx
0x1800271be  sub     r11d, 2
0x1800271c2  jz      short loc_1800271EA
0x1800271c4  sub     r11d, 1
0x1800271c8  jz      short loc_1800271E3
0x1800271ca  sub     r11d, 3
0x1800271ce  jz      short loc_1800271DC
0x1800271d0  cmp     r11d, 1
0x1800271d4  jnz     short loc_1800271EF
0x1800271d6  lea     edx, [r11+0Fh]
0x1800271da  jmp     short loc_1800271EF
0x1800271dc  mov     edx, 4
0x1800271e1  jmp     short loc_1800271EF
0x1800271e3  mov     edx, 8
0x1800271e8  jmp     short loc_1800271EF
0x1800271ea  mov     edx, 2
0x1800271ef  mov     eax, [rsi]
0x1800271f1  mov     ebx, 1
0x1800271f6  xor     r8d, r8d
0x1800271f9  mov     ecx, edx
0x1800271fb  or      ecx, eax
0x1800271fd  mov     r9d, eax
0x180027200  cmp     ecx, eax
0x180027202  setz    r8b
0x180027206  mov     [r10+10h], r8d
0x18002720a  mov     r8d, ecx
0x18002720d  or      r8d, ebx
0x180027210  cmp     ecx, eax
0x180027212  cmovz   r8d, ecx
0x180027216  lock cmpxchg [rsi], r8d
0x18002721b  jnz     short loc_1800271F6
0x18002721d  test    bl, r8b
0x180027220  jz      short loc_180027227
0x180027222  test    bl, r9b
0x180027225  jz      short loc_180027229
0x180027227  xor     ebx, ebx
0x180027229  mov     [r10], ebx
0x18002722c  jmp     loc_1800273A9
0x180027231  mov     eax, [rdx]
0x180027233  xor     edi, edi
0x180027235  cmp     r11d, 5
0x180027239  mov     ebx, 1
0x18002723e  setz    dil
0x180027242  and     dword ptr [r10+4], 0
0x180027247  mov     ecx, eax
0x180027249  or      ecx, ebx
0x18002724b  mov     r9d, eax
0x18002724e  mov     edx, ecx
0x180027250  shr     edx, 16h
0x180027253  and     edx, ebx
0x180027255  cmp     edx, edi
0x180027257  jz      short loc_18002729A
0x180027259  mov     r8d, ecx
0x18002725c  shr     r8d, 0Fh
0x180027260  and     r8d, 7Fh
0x180027264  jbe     short loc_18002727F
0x180027266  cmp     r11d, ebx
0x180027269  mov     [r10+4], r8d
0x18002726d  mov     edx, 5
0x180027272  cmovnz  edx, ebx
0x180027275  and     ecx, 0FFC07FFFh
0x18002727b  mov     [r10+8], edx
0x18002727f  xor     r8d, r8d
0x180027282  mov     edx, 400000h
0x180027287  cmp     r11d, 5
0x18002728b  cmovz   r8d, edx
0x18002728f  mov     edx, ecx
0x180027291  btr     edx, 16h
0x180027295  mov     ecx, r8d
0x180027298  or      ecx, edx
0x18002729a  mov     r8d, ecx
0x18002729d  shr     r8d, 0Fh
0x1800272a1  and     r8d, 7Fh
0x1800272a5  lea     edx, [r8+1]
0x1800272a9  cmp     edx, 7Fh
0x1800272ac  ja      short loc_1800272B3
0x1800272ae  cmp     edx, r8d
0x1800272b1  jnb     short loc_1800272BD
0x1800272b3  mov     edx, ebx
0x1800272b5  mov     [r10+8], r11d
0x1800272b9  mov     [r10+4], r8d
0x1800272bd  shl     edx, 0Fh
0x1800272c0  xor     edx, ecx
0x1800272c2  and     edx, 3F8000h
0x1800272c8  xor     ecx, edx
0x1800272ca  lock cmpxchg [rsi], ecx
0x1800272ce  jnz     loc_180027242
0x1800272d4  not     r9d
0x1800272d7  and     r9d, ebx
0x1800272da  mov     [r10], r9d
0x1800272dd  jmp     loc_1800273A4
0x1800272e2  mov     eax, [rdx]
0x1800272e4  xor     r14d, r14d
0x1800272e7  lea     edx, [r14+4]
0x1800272eb  cmp     r11d, edx
0x1800272ee  lea     ebx, [rdx-3]
0x1800272f1  setz    r14b
0x1800272f5  and     dword ptr [r10+4], 0
0x1800272fa  mov     ecx, eax
0x1800272fc  or      ecx, ebx
0x1800272fe  mov     edi, eax
0x180027300  mov     r8d, ecx
0x180027303  shr     r8d, 0Eh
0x180027307  and     r8d, ebx
0x18002730a  cmp     r8d, r14d
0x18002730d  jz      short loc_180027357
0x18002730f  mov     ebp, ecx
0x180027311  shr     ebp, 5
0x180027314  and     ebp, 1FFh
0x18002731a  jbe     short loc_180027339
0x18002731c  mov     r8d, r11d
0x18002731f  mov     [r10+4], ebp
0x180027323  neg     r8d
0x180027326  sbb     r9d, r9d
0x180027329  not     r9d
0x18002732c  and     r9d, edx
0x18002732f  mov     [r10+8], r9d
0x180027333  and     ecx, 0FFFFC01Fh
0x180027339  xor     r9d, r9d
0x18002733c  mov     r8d, 4000h
0x180027342  cmp     r11d, edx
0x180027345  cmovz   r9d, r8d
0x180027349  mov     r8d, ecx
0x18002734c  btr     r8d, 0Eh
0x180027351  mov     ecx, r9d
0x180027354  or      ecx, r8d
0x180027357  mov     r9d, ecx
0x18002735a  shr     r9d, 5
0x18002735e  and     r9d, 1FFh
0x180027365  lea     r8d, [r9+1]
0x180027369  cmp     r8d, 1FFh
0x180027370  ja      short loc_180027377
0x180027372  cmp     r8d, r9d
0x180027375  jnb     short loc_180027382
0x180027377  mov     r8d, ebx
0x18002737a  mov     [r10+8], r11d
0x18002737e  mov     [r10+4], r9d
0x180027382  shl     r8d, 5
0x180027386  xor     r8d, ecx
0x180027389  and     r8d, 3FE0h
0x180027390  xor     ecx, r8d
0x180027393  lock cmpxchg [rsi], ecx
0x180027397  jnz     loc_1800272F5
0x18002739d  not     edi
0x18002739f  and     edi, ebx
0x1800273a1  mov     [r10], edi
0x1800273a4  and     dword ptr [r10+10h], 0
0x1800273a9  mov     rbx, [rsp+8+arg_0]
0x1800273ae  mov     rax, r10
0x1800273b1  mov     rbp, [rsp+8+arg_8]
0x1800273b6  mov     rsi, [rsp+8+arg_10]
0x1800273bb  mov     rdi, [rsp+8+arg_18]
0x1800273c0  pop     r14
0x1800273c2  retn
```
