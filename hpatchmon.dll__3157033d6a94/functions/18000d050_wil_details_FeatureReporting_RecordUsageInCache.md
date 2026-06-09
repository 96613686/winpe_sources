# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x18000d050`
- end: `0x18000d32a`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `730`
- prototype: `__int64 __fastcall(__int64, volatile signed __int32 *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800097a8`

## callees

- `0x18000d050`

## pseudocode

```c
__int64 __fastcall wil_details_FeatureReporting_RecordUsageInCache(__int64 a1, volatile signed __int32 *a2, int a3)
{
  int v6; // r8d
  unsigned __int32 v7; // eax
  BOOL v8; // edx
  unsigned __int32 v9; // ett
  int v10; // ecx
  signed __int32 v11; // edx
  int v12; // ebx
  signed __int32 v13; // r9d
  signed __int32 v14; // eax
  signed __int32 v15; // ecx
  BOOL v16; // r9d
  unsigned int v17; // eax
  int v18; // edx
  int v19; // r8d
  unsigned int v20; // edx
  unsigned int v21; // r8d
  signed __int32 v22; // eax
  signed __int32 v23; // edx
  BOOL v24; // ebp
  unsigned int v25; // eax
  int v26; // r9d
  unsigned int v27; // r8d
  unsigned int v28; // r9d
  signed __int32 v29; // eax

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
      v23 = *a2;
      v24 = a3 == 4;
      while ( 1 )
      {
        *(_DWORD *)(a1 + 4) = 0;
        v25 = v23 | 1;
        if ( (((v23 | 1u) >> 14) & 1) != v24 )
        {
          if ( ((v25 >> 5) & 0x1FF) != 0 )
          {
            *(_DWORD *)(a1 + 4) = (v25 >> 5) & 0x1FF;
            *(_DWORD *)(a1 + 8) = a3 == 0 ? 4 : 0;
            v25 = v23 & 0xFFFFC01E | 1;
          }
          v26 = 0;
          if ( a3 == 4 )
            v26 = 0x4000;
          v25 = v25 & 0xFFFFBFFF | v26;
        }
        v27 = (v25 >> 5) & 0x1FF;
        v28 = v27 + 1;
        if ( v27 + 1 > 0x1FF || v28 < v27 )
        {
          LOWORD(v28) = 1;
          *(_DWORD *)(a1 + 8) = a3;
          *(_DWORD *)(a1 + 4) = v27;
        }
        v29 = _InterlockedCompareExchange(
                a2,
                v25 ^ ((unsigned __int16)v25 ^ (unsigned __int16)(32 * v28)) & 0x3FE0,
                v23);
        if ( v23 == v29 )
          break;
        v23 = v29;
      }
      *(_DWORD *)a1 = (v23 & 1) == 0;
      goto LABEL_62;
    case 5:
LABEL_34:
      v15 = *a2;
      v16 = a3 == 5;
      while ( 1 )
      {
        *(_DWORD *)(a1 + 4) = 0;
        v17 = v15 | 1;
        if ( (((v15 | 1u) >> 22) & 1) != v16 )
        {
          if ( ((v17 >> 15) & 0x7F) != 0 )
          {
            *(_DWORD *)(a1 + 4) = (v17 >> 15) & 0x7F;
            v18 = 5;
            if ( a3 != 1 )
              v18 = 1;
            v17 = v15 & 0xFFC07FFE | 1;
            *(_DWORD *)(a1 + 8) = v18;
          }
          v19 = 0;
          if ( a3 == 5 )
            v19 = 0x400000;
          v17 = v17 & 0xFFBFFFFF | v19;
        }
        v20 = (v17 >> 15) & 0x7F;
        v21 = v20 + 1;
        if ( v20 + 1 > 0x7F || v21 < v20 )
        {
          v21 = 1;
          *(_DWORD *)(a1 + 8) = a3;
          *(_DWORD *)(a1 + 4) = v20;
        }
        v22 = _InterlockedCompareExchange(a2, v17 ^ (v17 ^ (v21 << 15)) & 0x3F8000, v15);
        if ( v15 == v22 )
          break;
        v15 = v22;
      }
      *(_DWORD *)a1 = (v15 & 1) == 0;
LABEL_62:
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
      *(_DWORD *)(a1 + 8) = a3;
      *(_DWORD *)(a1 + 4) = 1;
      *(_DWORD *)(a1 + 12) = 0;
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
  while ( 1 )
  {
    v13 = v11 | v10 | 1;
    *(_DWORD *)(a1 + 16) = (v11 | v10) == v11;
    if ( (v11 | v10) == v11 )
      v13 = v11 | v10;
    v14 = _InterlockedCompareExchange(a2, v13, v11);
    if ( v11 == v14 )
      break;
    v11 = v14;
  }
  if ( (v13 & 1) == 0 || (v11 & 1) != 0 )
    v12 = 0;
  *(_DWORD *)a1 = v12;
  return a1;
}

```

## disassembly

```asm
0x18000d050  push    rbx
0x18000d052  push    rbp
0x18000d053  push    rsi
0x18000d054  push    rdi
0x18000d055  xor     eax, eax
0x18000d057  xorps   xmm0, xmm0
0x18000d05a  mov     r11d, r8d
0x18000d05d  mov     rsi, rdx
0x18000d060  mov     r10, rcx
0x18000d063  mov     r9d, r8d
0x18000d066  movups  xmmword ptr [rcx], xmm0
0x18000d069  mov     [rcx+10h], rax
0x18000d06d  test    r8d, r8d
0x18000d070  jz      loc_18000D254
0x18000d076  sub     r9d, 1
0x18000d07a  jz      loc_18000D19B
0x18000d080  sub     r9d, 1
0x18000d084  jz      loc_18000D122
0x18000d08a  sub     r9d, 1
0x18000d08e  jz      loc_18000D122
0x18000d094  sub     r9d, 1
0x18000d098  jz      loc_18000D254
0x18000d09e  sub     r9d, 1
0x18000d0a2  jz      loc_18000D19B
0x18000d0a8  sub     r9d, 1
0x18000d0ac  jz      short loc_18000D122
0x18000d0ae  cmp     r9d, 1
0x18000d0b2  jz      short loc_18000D122
0x18000d0b4  add     r8d, 0FFFFFEC0h
0x18000d0bb  lea     ebx, [rax+1]
0x18000d0be  cmp     r8d, 40h ; '@'
0x18000d0c2  jge     short loc_18000D10D
0x18000d0c4  mov     eax, [rdx+4]
0x18000d0c7  lea     ecx, [rbx+0Fh]
0x18000d0ca  mov     r9d, r8d
0x18000d0cd  shl     r9d, 5
0x18000d0d1  test    cl, al
0x18000d0d3  jz      short loc_18000D0E6
0x18000d0d5  mov     edx, eax
0x18000d0d7  shr     edx, 5
0x18000d0da  and     edx, 3Fh
0x18000d0dd  cmp     edx, r8d
0x18000d0e0  jnz     short loc_18000D0E6
0x18000d0e2  mov     edx, ebx
0x18000d0e4  jmp     short loc_18000D0E8
0x18000d0e6  xor     edx, edx
0x18000d0e8  mov     [r10+10h], edx
0x18000d0ec  mov     edx, r9d
0x18000d0ef  xor     edx, eax
0x18000d0f1  and     edx, 7E0h
0x18000d0f7  xor     edx, eax
0x18000d0f9  or      edx, ecx
0x18000d0fb  lock cmpxchg [rsi+4], edx
0x18000d100  jnz     short loc_18000D0D1
0x18000d102  cmp     dword ptr [r10+10h], 0
0x18000d107  jnz     loc_18000D322
0x18000d10d  mov     [r10+8], r11d
0x18000d111  mov     [r10+4], ebx
0x18000d115  mov     dword ptr [r10+0Ch], 0
0x18000d11d  jmp     loc_18000D322
0x18000d122  xor     ecx, ecx
0x18000d124  sub     r11d, 2
0x18000d128  jz      short loc_18000D150
0x18000d12a  sub     r11d, 1
0x18000d12e  jz      short loc_18000D149
0x18000d130  sub     r11d, 3
0x18000d134  jz      short loc_18000D142
0x18000d136  cmp     r11d, 1
0x18000d13a  jnz     short loc_18000D155
0x18000d13c  lea     ecx, [r11+0Fh]
0x18000d140  jmp     short loc_18000D155
0x18000d142  mov     ecx, 4
0x18000d147  jmp     short loc_18000D155
0x18000d149  mov     ecx, 8
0x18000d14e  jmp     short loc_18000D155
0x18000d150  mov     ecx, 2
0x18000d155  mov     edx, [rdx]
0x18000d157  mov     ebx, 1
0x18000d15c  xor     eax, eax
0x18000d15e  mov     r8d, ecx
0x18000d161  or      r8d, edx
0x18000d164  cmp     r8d, edx
0x18000d167  mov     r9d, r8d
0x18000d16a  setz    al
0x18000d16d  or      r9d, ebx
0x18000d170  cmp     r8d, edx
0x18000d173  mov     [r10+10h], eax
0x18000d177  mov     eax, edx
0x18000d179  cmovz   r9d, r8d
0x18000d17d  lock cmpxchg [rsi], r9d
0x18000d182  jz      short loc_18000D188
0x18000d184  mov     edx, eax
0x18000d186  jmp     short loc_18000D15C
0x18000d188  test    bl, r9b
0x18000d18b  jz      short loc_18000D191
0x18000d18d  test    bl, dl
0x18000d18f  jz      short loc_18000D193
0x18000d191  xor     ebx, ebx
0x18000d193  mov     [r10], ebx
0x18000d196  jmp     loc_18000D322
0x18000d19b  mov     ecx, [rdx]
0x18000d19d  xor     r9d, r9d
0x18000d1a0  cmp     r11d, 5
0x18000d1a4  mov     ebx, 1
0x18000d1a9  setz    r9b
0x18000d1ad  mov     eax, ecx
0x18000d1af  mov     dword ptr [r10+4], 0
0x18000d1b7  or      eax, ebx
0x18000d1b9  mov     edx, eax
0x18000d1bb  shr     edx, 16h
0x18000d1be  and     edx, ebx
0x18000d1c0  cmp     edx, r9d
0x18000d1c3  jz      short loc_18000D205
0x18000d1c5  mov     r8d, eax
0x18000d1c8  shr     r8d, 0Fh
0x18000d1cc  and     r8d, 7Fh
0x18000d1d0  jbe     short loc_18000D1EA
0x18000d1d2  cmp     r11d, ebx
0x18000d1d5  mov     [r10+4], r8d
0x18000d1d9  mov     edx, 5
0x18000d1de  cmovnz  edx, ebx
0x18000d1e1  and     eax, 0FFC07FFFh
0x18000d1e6  mov     [r10+8], edx
0x18000d1ea  xor     r8d, r8d
0x18000d1ed  mov     edx, 400000h
0x18000d1f2  cmp     r11d, 5
0x18000d1f6  cmovz   r8d, edx
0x18000d1fa  mov     edx, eax
0x18000d1fc  btr     edx, 16h
0x18000d200  mov     eax, r8d
0x18000d203  or      eax, edx
0x18000d205  mov     edx, eax
0x18000d207  shr     edx, 0Fh
0x18000d20a  and     edx, 7Fh
0x18000d20d  lea     r8d, [rdx+1]
0x18000d211  cmp     r8d, 7Fh
0x18000d215  ja      short loc_18000D21C
0x18000d217  cmp     r8d, edx
0x18000d21a  jnb     short loc_18000D227
0x18000d21c  mov     r8d, ebx
0x18000d21f  mov     [r10+8], r11d
0x18000d223  mov     [r10+4], edx
0x18000d227  shl     r8d, 0Fh
0x18000d22b  xor     r8d, eax
0x18000d22e  and     r8d, 3F8000h
0x18000d235  xor     r8d, eax
0x18000d238  mov     eax, ecx
0x18000d23a  lock cmpxchg [rsi], r8d
0x18000d23f  jz      short loc_18000D248
0x18000d241  mov     ecx, eax
0x18000d243  jmp     loc_18000D1AD
0x18000d248  not     ecx
0x18000d24a  and     ecx, ebx
0x18000d24c  mov     [r10], ecx
0x18000d24f  jmp     loc_18000D31A
0x18000d254  mov     edx, [rdx]
0x18000d256  xor     ebp, ebp
0x18000d258  lea     ecx, [rbp+4]
0x18000d25b  cmp     r11d, ecx
0x18000d25e  lea     ebx, [rcx-3]
0x18000d261  setz    bpl
0x18000d265  mov     eax, edx
0x18000d267  mov     dword ptr [r10+4], 0
0x18000d26f  or      eax, ebx
0x18000d271  mov     r8d, eax
0x18000d274  shr     r8d, 0Eh
0x18000d278  and     r8d, ebx
0x18000d27b  cmp     r8d, ebp
0x18000d27e  jz      short loc_18000D2C7
0x18000d280  mov     edi, eax
0x18000d282  shr     edi, 5
0x18000d285  and     edi, 1FFh
0x18000d28b  jbe     short loc_18000D2A9
0x18000d28d  mov     r8d, r11d
0x18000d290  mov     [r10+4], edi
0x18000d294  neg     r8d
0x18000d297  sbb     r9d, r9d
0x18000d29a  not     r9d
0x18000d29d  and     r9d, ecx
0x18000d2a0  mov     [r10+8], r9d
0x18000d2a4  and     eax, 0FFFFC01Fh
0x18000d2a9  xor     r9d, r9d
0x18000d2ac  mov     r8d, 4000h
0x18000d2b2  cmp     r11d, ecx
0x18000d2b5  cmovz   r9d, r8d
0x18000d2b9  mov     r8d, eax
0x18000d2bc  btr     r8d, 0Eh
0x18000d2c1  mov     eax, r9d
0x18000d2c4  or      eax, r8d
0x18000d2c7  mov     r8d, eax
0x18000d2ca  shr     r8d, 5
0x18000d2ce  and     r8d, 1FFh
0x18000d2d5  lea     r9d, [r8+1]
0x18000d2d9  cmp     r9d, 1FFh
0x18000d2e0  ja      short loc_18000D2E7
0x18000d2e2  cmp     r9d, r8d
0x18000d2e5  jnb     short loc_18000D2F2
0x18000d2e7  mov     r9d, ebx
0x18000d2ea  mov     [r10+8], r11d
0x18000d2ee  mov     [r10+4], r8d
0x18000d2f2  shl     r9d, 5
0x18000d2f6  xor     r9d, eax
0x18000d2f9  and     r9d, 3FE0h
0x18000d300  xor     r9d, eax
0x18000d303  mov     eax, edx
0x18000d305  lock cmpxchg [rsi], r9d
0x18000d30a  jz      short loc_18000D313
0x18000d30c  mov     edx, eax
0x18000d30e  jmp     loc_18000D265
0x18000d313  not     edx
0x18000d315  and     edx, ebx
0x18000d317  mov     [r10], edx
0x18000d31a  mov     dword ptr [r10+10h], 0
0x18000d322  mov     rax, r10
0x18000d325  pop     rdi
0x18000d326  pop     rsi
0x18000d327  pop     rbp
0x18000d328  pop     rbx
0x18000d329  retn
```
