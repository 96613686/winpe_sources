# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x18001c5ac`
- end: `0x18001c887`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `731`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800119b0`

## callees

- `0x18001c5ac`

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
0x18001c5ac  push    rbx
0x18001c5ae  push    rbp
0x18001c5af  push    rsi
0x18001c5b0  push    rdi
0x18001c5b1  xor     eax, eax
0x18001c5b3  xorps   xmm0, xmm0
0x18001c5b6  mov     r11d, r8d
0x18001c5b9  mov     rsi, rdx
0x18001c5bc  mov     r10, rcx
0x18001c5bf  mov     r9d, r8d
0x18001c5c2  movups  xmmword ptr [rcx], xmm0
0x18001c5c5  mov     [rcx+10h], rax
0x18001c5c9  test    r8d, r8d
0x18001c5cc  jz      loc_18001C7B0
0x18001c5d2  sub     r9d, 1
0x18001c5d6  jz      loc_18001C6F7
0x18001c5dc  sub     r9d, 1
0x18001c5e0  jz      loc_18001C67E
0x18001c5e6  sub     r9d, 1
0x18001c5ea  jz      loc_18001C67E
0x18001c5f0  sub     r9d, 1
0x18001c5f4  jz      loc_18001C7B0
0x18001c5fa  sub     r9d, 1
0x18001c5fe  jz      loc_18001C6F7
0x18001c604  sub     r9d, 1
0x18001c608  jz      short loc_18001C67E
0x18001c60a  cmp     r9d, 1
0x18001c60e  jz      short loc_18001C67E
0x18001c610  add     r8d, 0FFFFFEC0h
0x18001c617  lea     ebx, [rax+1]
0x18001c61a  cmp     r8d, 40h ; '@'
0x18001c61e  jge     short loc_18001C669
0x18001c620  mov     eax, [rdx+4]
0x18001c623  lea     ecx, [rbx+0Fh]
0x18001c626  mov     r9d, r8d
0x18001c629  shl     r9d, 5
0x18001c62d  test    cl, al
0x18001c62f  jz      short loc_18001C642
0x18001c631  mov     edx, eax
0x18001c633  shr     edx, 5
0x18001c636  and     edx, 3Fh
0x18001c639  cmp     edx, r8d
0x18001c63c  jnz     short loc_18001C642
0x18001c63e  mov     edx, ebx
0x18001c640  jmp     short loc_18001C644
0x18001c642  xor     edx, edx
0x18001c644  mov     [r10+10h], edx
0x18001c648  mov     edx, r9d
0x18001c64b  xor     edx, eax
0x18001c64d  and     edx, 7E0h
0x18001c653  xor     edx, eax
0x18001c655  or      edx, ecx
0x18001c657  lock cmpxchg [rsi+4], edx
0x18001c65c  jnz     short loc_18001C62D
0x18001c65e  cmp     dword ptr [r10+10h], 0
0x18001c663  jnz     loc_18001C87E
0x18001c669  mov     [r10+8], r11d
0x18001c66d  mov     [r10+4], ebx
0x18001c671  mov     dword ptr [r10+0Ch], 0
0x18001c679  jmp     loc_18001C87E
0x18001c67e  xor     ecx, ecx
0x18001c680  sub     r11d, 2
0x18001c684  jz      short loc_18001C6AC
0x18001c686  sub     r11d, 1
0x18001c68a  jz      short loc_18001C6A5
0x18001c68c  sub     r11d, 3
0x18001c690  jz      short loc_18001C69E
0x18001c692  cmp     r11d, 1
0x18001c696  jnz     short loc_18001C6B1
0x18001c698  lea     ecx, [r11+0Fh]
0x18001c69c  jmp     short loc_18001C6B1
0x18001c69e  mov     ecx, 4
0x18001c6a3  jmp     short loc_18001C6B1
0x18001c6a5  mov     ecx, 8
0x18001c6aa  jmp     short loc_18001C6B1
0x18001c6ac  mov     ecx, 2
0x18001c6b1  mov     edx, [rdx]
0x18001c6b3  mov     ebx, 1
0x18001c6b8  xor     eax, eax
0x18001c6ba  mov     r8d, ecx
0x18001c6bd  or      r8d, edx
0x18001c6c0  cmp     r8d, edx
0x18001c6c3  mov     r9d, r8d
0x18001c6c6  setz    al
0x18001c6c9  or      r9d, ebx
0x18001c6cc  cmp     r8d, edx
0x18001c6cf  mov     [r10+10h], eax
0x18001c6d3  mov     eax, edx
0x18001c6d5  cmovz   r9d, r8d
0x18001c6d9  lock cmpxchg [rsi], r9d
0x18001c6de  jz      short loc_18001C6E4
0x18001c6e0  mov     edx, eax
0x18001c6e2  jmp     short loc_18001C6B8
0x18001c6e4  test    bl, r9b
0x18001c6e7  jz      short loc_18001C6ED
0x18001c6e9  test    bl, dl
0x18001c6eb  jz      short loc_18001C6EF
0x18001c6ed  xor     ebx, ebx
0x18001c6ef  mov     [r10], ebx
0x18001c6f2  jmp     loc_18001C87E
0x18001c6f7  mov     ecx, [rdx]
0x18001c6f9  xor     r9d, r9d
0x18001c6fc  cmp     r11d, 5
0x18001c700  mov     ebx, 1
0x18001c705  setz    r9b
0x18001c709  mov     eax, ecx
0x18001c70b  mov     dword ptr [r10+4], 0
0x18001c713  or      eax, ebx
0x18001c715  mov     edx, eax
0x18001c717  shr     edx, 16h
0x18001c71a  and     edx, ebx
0x18001c71c  cmp     edx, r9d
0x18001c71f  jz      short loc_18001C761
0x18001c721  mov     r8d, eax
0x18001c724  shr     r8d, 0Fh
0x18001c728  and     r8d, 7Fh
0x18001c72c  jbe     short loc_18001C746
0x18001c72e  cmp     r11d, ebx
0x18001c731  mov     [r10+4], r8d
0x18001c735  mov     edx, 5
0x18001c73a  cmovnz  edx, ebx
0x18001c73d  and     eax, 0FFC07FFFh
0x18001c742  mov     [r10+8], edx
0x18001c746  xor     r8d, r8d
0x18001c749  mov     edx, 400000h
0x18001c74e  cmp     r11d, 5
0x18001c752  cmovz   r8d, edx
0x18001c756  mov     edx, eax
0x18001c758  btr     edx, 16h
0x18001c75c  mov     eax, r8d
0x18001c75f  or      eax, edx
0x18001c761  mov     edx, eax
0x18001c763  shr     edx, 0Fh
0x18001c766  and     edx, 7Fh
0x18001c769  lea     r8d, [rdx+1]
0x18001c76d  cmp     r8d, 7Fh
0x18001c771  ja      short loc_18001C778
0x18001c773  cmp     r8d, edx
0x18001c776  jnb     short loc_18001C783
0x18001c778  mov     r8d, ebx
0x18001c77b  mov     [r10+8], r11d
0x18001c77f  mov     [r10+4], edx
0x18001c783  shl     r8d, 0Fh
0x18001c787  xor     r8d, eax
0x18001c78a  and     r8d, 3F8000h
0x18001c791  xor     r8d, eax
0x18001c794  mov     eax, ecx
0x18001c796  lock cmpxchg [rsi], r8d
0x18001c79b  jz      short loc_18001C7A4
0x18001c79d  mov     ecx, eax
0x18001c79f  jmp     loc_18001C709
0x18001c7a4  not     ecx
0x18001c7a6  and     ecx, ebx
0x18001c7a8  mov     [r10], ecx
0x18001c7ab  jmp     loc_18001C876
0x18001c7b0  mov     edx, [rdx]
0x18001c7b2  xor     ebp, ebp
0x18001c7b4  lea     ecx, [rbp+4]
0x18001c7b7  cmp     r11d, ecx
0x18001c7ba  lea     ebx, [rcx-3]
0x18001c7bd  setz    bpl
0x18001c7c1  mov     eax, edx
0x18001c7c3  mov     dword ptr [r10+4], 0
0x18001c7cb  or      eax, ebx
0x18001c7cd  mov     r8d, eax
0x18001c7d0  shr     r8d, 0Eh
0x18001c7d4  and     r8d, ebx
0x18001c7d7  cmp     r8d, ebp
0x18001c7da  jz      short loc_18001C823
0x18001c7dc  mov     edi, eax
0x18001c7de  shr     edi, 5
0x18001c7e1  and     edi, 1FFh
0x18001c7e7  jbe     short loc_18001C805
0x18001c7e9  mov     r8d, r11d
0x18001c7ec  mov     [r10+4], edi
0x18001c7f0  neg     r8d
0x18001c7f3  sbb     r9d, r9d
0x18001c7f6  not     r9d
0x18001c7f9  and     r9d, ecx
0x18001c7fc  mov     [r10+8], r9d
0x18001c800  and     eax, 0FFFFC01Fh
0x18001c805  xor     r9d, r9d
0x18001c808  mov     r8d, 4000h
0x18001c80e  cmp     r11d, ecx
0x18001c811  cmovz   r9d, r8d
0x18001c815  mov     r8d, eax
0x18001c818  btr     r8d, 0Eh
0x18001c81d  mov     eax, r9d
0x18001c820  or      eax, r8d
0x18001c823  mov     r8d, eax
0x18001c826  shr     r8d, 5
0x18001c82a  and     r8d, 1FFh
0x18001c831  lea     r9d, [r8+1]
0x18001c835  cmp     r9d, 1FFh
0x18001c83c  ja      short loc_18001C843
0x18001c83e  cmp     r9d, r8d
0x18001c841  jnb     short loc_18001C84E
0x18001c843  mov     r9d, ebx
0x18001c846  mov     [r10+8], r11d
0x18001c84a  mov     [r10+4], r8d
0x18001c84e  shl     r9d, 5
0x18001c852  xor     r9d, eax
0x18001c855  and     r9d, 3FE0h
0x18001c85c  xor     r9d, eax
0x18001c85f  mov     eax, edx
0x18001c861  lock cmpxchg [rsi], r9d
0x18001c866  jz      short loc_18001C86F
0x18001c868  mov     edx, eax
0x18001c86a  jmp     loc_18001C7C1
0x18001c86f  not     edx
0x18001c871  and     edx, ebx
0x18001c873  mov     [r10], edx
0x18001c876  mov     dword ptr [r10+10h], 0
0x18001c87e  mov     rax, r10
0x18001c881  pop     rdi
0x18001c882  pop     rsi
0x18001c883  pop     rbp
0x18001c884  pop     rbx
0x18001c885  retn
```
