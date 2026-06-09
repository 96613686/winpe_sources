# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x18000c4d8`
- end: `0x18000c7b2`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `730`
- prototype: `__int64 __fastcall(__int64, volatile signed __int32 *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000b9e4`

## callees

- `0x18000c4d8`

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
0x18000c4d8  push    rbx
0x18000c4da  push    rbp
0x18000c4db  push    rsi
0x18000c4dc  push    rdi
0x18000c4dd  xor     eax, eax
0x18000c4df  xorps   xmm0, xmm0
0x18000c4e2  mov     r11d, r8d
0x18000c4e5  mov     rsi, rdx
0x18000c4e8  mov     r10, rcx
0x18000c4eb  mov     r9d, r8d
0x18000c4ee  movups  xmmword ptr [rcx], xmm0
0x18000c4f1  mov     [rcx+10h], rax
0x18000c4f5  test    r8d, r8d
0x18000c4f8  jz      loc_18000C6DC
0x18000c4fe  sub     r9d, 1
0x18000c502  jz      loc_18000C623
0x18000c508  sub     r9d, 1
0x18000c50c  jz      loc_18000C5AA
0x18000c512  sub     r9d, 1
0x18000c516  jz      loc_18000C5AA
0x18000c51c  sub     r9d, 1
0x18000c520  jz      loc_18000C6DC
0x18000c526  sub     r9d, 1
0x18000c52a  jz      loc_18000C623
0x18000c530  sub     r9d, 1
0x18000c534  jz      short loc_18000C5AA
0x18000c536  cmp     r9d, 1
0x18000c53a  jz      short loc_18000C5AA
0x18000c53c  add     r8d, 0FFFFFEC0h
0x18000c543  lea     ebx, [rax+1]
0x18000c546  cmp     r8d, 40h ; '@'
0x18000c54a  jge     short loc_18000C595
0x18000c54c  mov     eax, [rdx+4]
0x18000c54f  lea     ecx, [rbx+0Fh]
0x18000c552  mov     r9d, r8d
0x18000c555  shl     r9d, 5
0x18000c559  test    cl, al
0x18000c55b  jz      short loc_18000C56E
0x18000c55d  mov     edx, eax
0x18000c55f  shr     edx, 5
0x18000c562  and     edx, 3Fh
0x18000c565  cmp     edx, r8d
0x18000c568  jnz     short loc_18000C56E
0x18000c56a  mov     edx, ebx
0x18000c56c  jmp     short loc_18000C570
0x18000c56e  xor     edx, edx
0x18000c570  mov     [r10+10h], edx
0x18000c574  mov     edx, r9d
0x18000c577  xor     edx, eax
0x18000c579  and     edx, 7E0h
0x18000c57f  xor     edx, eax
0x18000c581  or      edx, ecx
0x18000c583  lock cmpxchg [rsi+4], edx
0x18000c588  jnz     short loc_18000C559
0x18000c58a  cmp     dword ptr [r10+10h], 0
0x18000c58f  jnz     loc_18000C7AA
0x18000c595  mov     [r10+8], r11d
0x18000c599  mov     [r10+4], ebx
0x18000c59d  mov     dword ptr [r10+0Ch], 0
0x18000c5a5  jmp     loc_18000C7AA
0x18000c5aa  xor     ecx, ecx
0x18000c5ac  sub     r11d, 2
0x18000c5b0  jz      short loc_18000C5D8
0x18000c5b2  sub     r11d, 1
0x18000c5b6  jz      short loc_18000C5D1
0x18000c5b8  sub     r11d, 3
0x18000c5bc  jz      short loc_18000C5CA
0x18000c5be  cmp     r11d, 1
0x18000c5c2  jnz     short loc_18000C5DD
0x18000c5c4  lea     ecx, [r11+0Fh]
0x18000c5c8  jmp     short loc_18000C5DD
0x18000c5ca  mov     ecx, 4
0x18000c5cf  jmp     short loc_18000C5DD
0x18000c5d1  mov     ecx, 8
0x18000c5d6  jmp     short loc_18000C5DD
0x18000c5d8  mov     ecx, 2
0x18000c5dd  mov     edx, [rdx]
0x18000c5df  mov     ebx, 1
0x18000c5e4  xor     eax, eax
0x18000c5e6  mov     r8d, ecx
0x18000c5e9  or      r8d, edx
0x18000c5ec  cmp     r8d, edx
0x18000c5ef  mov     r9d, r8d
0x18000c5f2  setz    al
0x18000c5f5  or      r9d, ebx
0x18000c5f8  cmp     r8d, edx
0x18000c5fb  mov     [r10+10h], eax
0x18000c5ff  mov     eax, edx
0x18000c601  cmovz   r9d, r8d
0x18000c605  lock cmpxchg [rsi], r9d
0x18000c60a  jz      short loc_18000C610
0x18000c60c  mov     edx, eax
0x18000c60e  jmp     short loc_18000C5E4
0x18000c610  test    bl, r9b
0x18000c613  jz      short loc_18000C619
0x18000c615  test    bl, dl
0x18000c617  jz      short loc_18000C61B
0x18000c619  xor     ebx, ebx
0x18000c61b  mov     [r10], ebx
0x18000c61e  jmp     loc_18000C7AA
0x18000c623  mov     ecx, [rdx]
0x18000c625  xor     r9d, r9d
0x18000c628  cmp     r11d, 5
0x18000c62c  mov     ebx, 1
0x18000c631  setz    r9b
0x18000c635  mov     eax, ecx
0x18000c637  mov     dword ptr [r10+4], 0
0x18000c63f  or      eax, ebx
0x18000c641  mov     edx, eax
0x18000c643  shr     edx, 16h
0x18000c646  and     edx, ebx
0x18000c648  cmp     edx, r9d
0x18000c64b  jz      short loc_18000C68D
0x18000c64d  mov     r8d, eax
0x18000c650  shr     r8d, 0Fh
0x18000c654  and     r8d, 7Fh
0x18000c658  jbe     short loc_18000C672
0x18000c65a  cmp     r11d, ebx
0x18000c65d  mov     [r10+4], r8d
0x18000c661  mov     edx, 5
0x18000c666  cmovnz  edx, ebx
0x18000c669  and     eax, 0FFC07FFFh
0x18000c66e  mov     [r10+8], edx
0x18000c672  xor     r8d, r8d
0x18000c675  mov     edx, 400000h
0x18000c67a  cmp     r11d, 5
0x18000c67e  cmovz   r8d, edx
0x18000c682  mov     edx, eax
0x18000c684  btr     edx, 16h
0x18000c688  mov     eax, r8d
0x18000c68b  or      eax, edx
0x18000c68d  mov     edx, eax
0x18000c68f  shr     edx, 0Fh
0x18000c692  and     edx, 7Fh
0x18000c695  lea     r8d, [rdx+1]
0x18000c699  cmp     r8d, 7Fh
0x18000c69d  ja      short loc_18000C6A4
0x18000c69f  cmp     r8d, edx
0x18000c6a2  jnb     short loc_18000C6AF
0x18000c6a4  mov     r8d, ebx
0x18000c6a7  mov     [r10+8], r11d
0x18000c6ab  mov     [r10+4], edx
0x18000c6af  shl     r8d, 0Fh
0x18000c6b3  xor     r8d, eax
0x18000c6b6  and     r8d, 3F8000h
0x18000c6bd  xor     r8d, eax
0x18000c6c0  mov     eax, ecx
0x18000c6c2  lock cmpxchg [rsi], r8d
0x18000c6c7  jz      short loc_18000C6D0
0x18000c6c9  mov     ecx, eax
0x18000c6cb  jmp     loc_18000C635
0x18000c6d0  not     ecx
0x18000c6d2  and     ecx, ebx
0x18000c6d4  mov     [r10], ecx
0x18000c6d7  jmp     loc_18000C7A2
0x18000c6dc  mov     edx, [rdx]
0x18000c6de  xor     ebp, ebp
0x18000c6e0  lea     ecx, [rbp+4]
0x18000c6e3  cmp     r11d, ecx
0x18000c6e6  lea     ebx, [rcx-3]
0x18000c6e9  setz    bpl
0x18000c6ed  mov     eax, edx
0x18000c6ef  mov     dword ptr [r10+4], 0
0x18000c6f7  or      eax, ebx
0x18000c6f9  mov     r8d, eax
0x18000c6fc  shr     r8d, 0Eh
0x18000c700  and     r8d, ebx
0x18000c703  cmp     r8d, ebp
0x18000c706  jz      short loc_18000C74F
0x18000c708  mov     edi, eax
0x18000c70a  shr     edi, 5
0x18000c70d  and     edi, 1FFh
0x18000c713  jbe     short loc_18000C731
0x18000c715  mov     r8d, r11d
0x18000c718  mov     [r10+4], edi
0x18000c71c  neg     r8d
0x18000c71f  sbb     r9d, r9d
0x18000c722  not     r9d
0x18000c725  and     r9d, ecx
0x18000c728  mov     [r10+8], r9d
0x18000c72c  and     eax, 0FFFFC01Fh
0x18000c731  xor     r9d, r9d
0x18000c734  mov     r8d, 4000h
0x18000c73a  cmp     r11d, ecx
0x18000c73d  cmovz   r9d, r8d
0x18000c741  mov     r8d, eax
0x18000c744  btr     r8d, 0Eh
0x18000c749  mov     eax, r9d
0x18000c74c  or      eax, r8d
0x18000c74f  mov     r8d, eax
0x18000c752  shr     r8d, 5
0x18000c756  and     r8d, 1FFh
0x18000c75d  lea     r9d, [r8+1]
0x18000c761  cmp     r9d, 1FFh
0x18000c768  ja      short loc_18000C76F
0x18000c76a  cmp     r9d, r8d
0x18000c76d  jnb     short loc_18000C77A
0x18000c76f  mov     r9d, ebx
0x18000c772  mov     [r10+8], r11d
0x18000c776  mov     [r10+4], r8d
0x18000c77a  shl     r9d, 5
0x18000c77e  xor     r9d, eax
0x18000c781  and     r9d, 3FE0h
0x18000c788  xor     r9d, eax
0x18000c78b  mov     eax, edx
0x18000c78d  lock cmpxchg [rsi], r9d
0x18000c792  jz      short loc_18000C79B
0x18000c794  mov     edx, eax
0x18000c796  jmp     loc_18000C6ED
0x18000c79b  not     edx
0x18000c79d  and     edx, ebx
0x18000c79f  mov     [r10], edx
0x18000c7a2  mov     dword ptr [r10+10h], 0
0x18000c7aa  mov     rax, r10
0x18000c7ad  pop     rdi
0x18000c7ae  pop     rsi
0x18000c7af  pop     rbp
0x18000c7b0  pop     rbx
0x18000c7b1  retn
```
