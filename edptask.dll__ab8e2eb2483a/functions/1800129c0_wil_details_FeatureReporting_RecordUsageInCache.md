# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x1800129c0`
- end: `0x180012c9a`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `730`
- prototype: `__int64 __fastcall(__int64, volatile signed __int32 *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180010468`

## callees

- `0x1800129c0`

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
0x1800129c0  push    rbx
0x1800129c2  push    rbp
0x1800129c3  push    rsi
0x1800129c4  push    rdi
0x1800129c5  xor     eax, eax
0x1800129c7  xorps   xmm0, xmm0
0x1800129ca  mov     r11d, r8d
0x1800129cd  mov     rsi, rdx
0x1800129d0  mov     r10, rcx
0x1800129d3  mov     r9d, r8d
0x1800129d6  movups  xmmword ptr [rcx], xmm0
0x1800129d9  mov     [rcx+10h], rax
0x1800129dd  test    r8d, r8d
0x1800129e0  jz      loc_180012BC4
0x1800129e6  sub     r9d, 1
0x1800129ea  jz      loc_180012B0B
0x1800129f0  sub     r9d, 1
0x1800129f4  jz      loc_180012A92
0x1800129fa  sub     r9d, 1
0x1800129fe  jz      loc_180012A92
0x180012a04  sub     r9d, 1
0x180012a08  jz      loc_180012BC4
0x180012a0e  sub     r9d, 1
0x180012a12  jz      loc_180012B0B
0x180012a18  sub     r9d, 1
0x180012a1c  jz      short loc_180012A92
0x180012a1e  cmp     r9d, 1
0x180012a22  jz      short loc_180012A92
0x180012a24  add     r8d, 0FFFFFEC0h
0x180012a2b  lea     ebx, [rax+1]
0x180012a2e  cmp     r8d, 40h ; '@'
0x180012a32  jge     short loc_180012A7D
0x180012a34  mov     eax, [rdx+4]
0x180012a37  lea     ecx, [rbx+0Fh]
0x180012a3a  mov     r9d, r8d
0x180012a3d  shl     r9d, 5
0x180012a41  test    cl, al
0x180012a43  jz      short loc_180012A56
0x180012a45  mov     edx, eax
0x180012a47  shr     edx, 5
0x180012a4a  and     edx, 3Fh
0x180012a4d  cmp     edx, r8d
0x180012a50  jnz     short loc_180012A56
0x180012a52  mov     edx, ebx
0x180012a54  jmp     short loc_180012A58
0x180012a56  xor     edx, edx
0x180012a58  mov     [r10+10h], edx
0x180012a5c  mov     edx, r9d
0x180012a5f  xor     edx, eax
0x180012a61  and     edx, 7E0h
0x180012a67  xor     edx, eax
0x180012a69  or      edx, ecx
0x180012a6b  lock cmpxchg [rsi+4], edx
0x180012a70  jnz     short loc_180012A41
0x180012a72  cmp     dword ptr [r10+10h], 0
0x180012a77  jnz     loc_180012C92
0x180012a7d  mov     [r10+8], r11d
0x180012a81  mov     [r10+4], ebx
0x180012a85  mov     dword ptr [r10+0Ch], 0
0x180012a8d  jmp     loc_180012C92
0x180012a92  xor     ecx, ecx
0x180012a94  sub     r11d, 2
0x180012a98  jz      short loc_180012AC0
0x180012a9a  sub     r11d, 1
0x180012a9e  jz      short loc_180012AB9
0x180012aa0  sub     r11d, 3
0x180012aa4  jz      short loc_180012AB2
0x180012aa6  cmp     r11d, 1
0x180012aaa  jnz     short loc_180012AC5
0x180012aac  lea     ecx, [r11+0Fh]
0x180012ab0  jmp     short loc_180012AC5
0x180012ab2  mov     ecx, 4
0x180012ab7  jmp     short loc_180012AC5
0x180012ab9  mov     ecx, 8
0x180012abe  jmp     short loc_180012AC5
0x180012ac0  mov     ecx, 2
0x180012ac5  mov     edx, [rdx]
0x180012ac7  mov     ebx, 1
0x180012acc  xor     eax, eax
0x180012ace  mov     r8d, ecx
0x180012ad1  or      r8d, edx
0x180012ad4  cmp     r8d, edx
0x180012ad7  mov     r9d, r8d
0x180012ada  setz    al
0x180012add  or      r9d, ebx
0x180012ae0  cmp     r8d, edx
0x180012ae3  mov     [r10+10h], eax
0x180012ae7  mov     eax, edx
0x180012ae9  cmovz   r9d, r8d
0x180012aed  lock cmpxchg [rsi], r9d
0x180012af2  jz      short loc_180012AF8
0x180012af4  mov     edx, eax
0x180012af6  jmp     short loc_180012ACC
0x180012af8  test    bl, r9b
0x180012afb  jz      short loc_180012B01
0x180012afd  test    bl, dl
0x180012aff  jz      short loc_180012B03
0x180012b01  xor     ebx, ebx
0x180012b03  mov     [r10], ebx
0x180012b06  jmp     loc_180012C92
0x180012b0b  mov     ecx, [rdx]
0x180012b0d  xor     r9d, r9d
0x180012b10  cmp     r11d, 5
0x180012b14  mov     ebx, 1
0x180012b19  setz    r9b
0x180012b1d  mov     eax, ecx
0x180012b1f  mov     dword ptr [r10+4], 0
0x180012b27  or      eax, ebx
0x180012b29  mov     edx, eax
0x180012b2b  shr     edx, 16h
0x180012b2e  and     edx, ebx
0x180012b30  cmp     edx, r9d
0x180012b33  jz      short loc_180012B75
0x180012b35  mov     r8d, eax
0x180012b38  shr     r8d, 0Fh
0x180012b3c  and     r8d, 7Fh
0x180012b40  jbe     short loc_180012B5A
0x180012b42  cmp     r11d, ebx
0x180012b45  mov     [r10+4], r8d
0x180012b49  mov     edx, 5
0x180012b4e  cmovnz  edx, ebx
0x180012b51  and     eax, 0FFC07FFFh
0x180012b56  mov     [r10+8], edx
0x180012b5a  xor     r8d, r8d
0x180012b5d  mov     edx, 400000h
0x180012b62  cmp     r11d, 5
0x180012b66  cmovz   r8d, edx
0x180012b6a  mov     edx, eax
0x180012b6c  btr     edx, 16h
0x180012b70  mov     eax, r8d
0x180012b73  or      eax, edx
0x180012b75  mov     edx, eax
0x180012b77  shr     edx, 0Fh
0x180012b7a  and     edx, 7Fh
0x180012b7d  lea     r8d, [rdx+1]
0x180012b81  cmp     r8d, 7Fh
0x180012b85  ja      short loc_180012B8C
0x180012b87  cmp     r8d, edx
0x180012b8a  jnb     short loc_180012B97
0x180012b8c  mov     r8d, ebx
0x180012b8f  mov     [r10+8], r11d
0x180012b93  mov     [r10+4], edx
0x180012b97  shl     r8d, 0Fh
0x180012b9b  xor     r8d, eax
0x180012b9e  and     r8d, 3F8000h
0x180012ba5  xor     r8d, eax
0x180012ba8  mov     eax, ecx
0x180012baa  lock cmpxchg [rsi], r8d
0x180012baf  jz      short loc_180012BB8
0x180012bb1  mov     ecx, eax
0x180012bb3  jmp     loc_180012B1D
0x180012bb8  not     ecx
0x180012bba  and     ecx, ebx
0x180012bbc  mov     [r10], ecx
0x180012bbf  jmp     loc_180012C8A
0x180012bc4  mov     edx, [rdx]
0x180012bc6  xor     ebp, ebp
0x180012bc8  lea     ecx, [rbp+4]
0x180012bcb  cmp     r11d, ecx
0x180012bce  lea     ebx, [rcx-3]
0x180012bd1  setz    bpl
0x180012bd5  mov     eax, edx
0x180012bd7  mov     dword ptr [r10+4], 0
0x180012bdf  or      eax, ebx
0x180012be1  mov     r8d, eax
0x180012be4  shr     r8d, 0Eh
0x180012be8  and     r8d, ebx
0x180012beb  cmp     r8d, ebp
0x180012bee  jz      short loc_180012C37
0x180012bf0  mov     edi, eax
0x180012bf2  shr     edi, 5
0x180012bf5  and     edi, 1FFh
0x180012bfb  jbe     short loc_180012C19
0x180012bfd  mov     r8d, r11d
0x180012c00  mov     [r10+4], edi
0x180012c04  neg     r8d
0x180012c07  sbb     r9d, r9d
0x180012c0a  not     r9d
0x180012c0d  and     r9d, ecx
0x180012c10  mov     [r10+8], r9d
0x180012c14  and     eax, 0FFFFC01Fh
0x180012c19  xor     r9d, r9d
0x180012c1c  mov     r8d, 4000h
0x180012c22  cmp     r11d, ecx
0x180012c25  cmovz   r9d, r8d
0x180012c29  mov     r8d, eax
0x180012c2c  btr     r8d, 0Eh
0x180012c31  mov     eax, r9d
0x180012c34  or      eax, r8d
0x180012c37  mov     r8d, eax
0x180012c3a  shr     r8d, 5
0x180012c3e  and     r8d, 1FFh
0x180012c45  lea     r9d, [r8+1]
0x180012c49  cmp     r9d, 1FFh
0x180012c50  ja      short loc_180012C57
0x180012c52  cmp     r9d, r8d
0x180012c55  jnb     short loc_180012C62
0x180012c57  mov     r9d, ebx
0x180012c5a  mov     [r10+8], r11d
0x180012c5e  mov     [r10+4], r8d
0x180012c62  shl     r9d, 5
0x180012c66  xor     r9d, eax
0x180012c69  and     r9d, 3FE0h
0x180012c70  xor     r9d, eax
0x180012c73  mov     eax, edx
0x180012c75  lock cmpxchg [rsi], r9d
0x180012c7a  jz      short loc_180012C83
0x180012c7c  mov     edx, eax
0x180012c7e  jmp     loc_180012BD5
0x180012c83  not     edx
0x180012c85  and     edx, ebx
0x180012c87  mov     [r10], edx
0x180012c8a  mov     dword ptr [r10+10h], 0
0x180012c92  mov     rax, r10
0x180012c95  pop     rdi
0x180012c96  pop     rsi
0x180012c97  pop     rbp
0x180012c98  pop     rbx
0x180012c99  retn
```
