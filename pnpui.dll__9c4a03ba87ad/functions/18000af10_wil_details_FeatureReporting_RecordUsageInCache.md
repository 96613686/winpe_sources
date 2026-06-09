# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x18000af10`
- end: `0x18000b1e2`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `722`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000c754`

## callees

- `0x18000af10`

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
0x18000af10  push    rbx
0x18000af12  push    rbp
0x18000af13  push    rsi
0x18000af14  push    rdi
0x18000af15  xor     eax, eax
0x18000af17  xorps   xmm0, xmm0
0x18000af1a  mov     r10, rcx
0x18000af1d  mov     edi, r9d
0x18000af20  mov     r11d, r8d
0x18000af23  mov     rsi, rdx
0x18000af26  movups  xmmword ptr [rcx], xmm0
0x18000af29  mov     [rcx+10h], rax
0x18000af2d  mov     ecx, r8d
0x18000af30  test    r8d, r8d
0x18000af33  jz      loc_18000B10C
0x18000af39  sub     ecx, 1
0x18000af3c  jz      loc_18000B053
0x18000af42  sub     ecx, 1
0x18000af45  jz      loc_18000AFDA
0x18000af4b  sub     ecx, 1
0x18000af4e  jz      loc_18000AFDA
0x18000af54  sub     ecx, 1
0x18000af57  jz      loc_18000B10C
0x18000af5d  sub     ecx, 1
0x18000af60  jz      loc_18000B053
0x18000af66  sub     ecx, 1
0x18000af69  jz      short loc_18000AFDA
0x18000af6b  cmp     ecx, 1
0x18000af6e  jz      short loc_18000AFDA
0x18000af70  add     r8d, 0FFFFFEC0h
0x18000af77  lea     ebx, [rax+1]
0x18000af7a  cmp     r8d, 40h ; '@'
0x18000af7e  jge     short loc_18000AFC9
0x18000af80  mov     eax, [rdx+4]
0x18000af83  lea     ecx, [rbx+0Fh]
0x18000af86  mov     r9d, r8d
0x18000af89  shl     r9d, 5
0x18000af8d  test    cl, al
0x18000af8f  jz      short loc_18000AFA2
0x18000af91  mov     edx, eax
0x18000af93  shr     edx, 5
0x18000af96  and     edx, 3Fh
0x18000af99  cmp     edx, r8d
0x18000af9c  jnz     short loc_18000AFA2
0x18000af9e  mov     edx, ebx
0x18000afa0  jmp     short loc_18000AFA4
0x18000afa2  xor     edx, edx
0x18000afa4  mov     [r10+10h], edx
0x18000afa8  mov     edx, r9d
0x18000afab  xor     edx, eax
0x18000afad  and     edx, 7E0h
0x18000afb3  xor     edx, eax
0x18000afb5  or      edx, ecx
0x18000afb7  lock cmpxchg [rsi+4], edx
0x18000afbc  jnz     short loc_18000AF8D
0x18000afbe  cmp     dword ptr [r10+10h], 0
0x18000afc3  jnz     loc_18000B1DA
0x18000afc9  mov     [r10+8], r11d
0x18000afcd  mov     [r10+4], ebx
0x18000afd1  mov     [r10+0Ch], edi
0x18000afd5  jmp     loc_18000B1DA
0x18000afda  xor     ecx, ecx
0x18000afdc  sub     r11d, 2
0x18000afe0  jz      short loc_18000B008
0x18000afe2  sub     r11d, 1
0x18000afe6  jz      short loc_18000B001
0x18000afe8  sub     r11d, 3
0x18000afec  jz      short loc_18000AFFA
0x18000afee  cmp     r11d, 1
0x18000aff2  jnz     short loc_18000B00D
0x18000aff4  lea     ecx, [r11+0Fh]
0x18000aff8  jmp     short loc_18000B00D
0x18000affa  mov     ecx, 4
0x18000afff  jmp     short loc_18000B00D
0x18000b001  mov     ecx, 8
0x18000b006  jmp     short loc_18000B00D
0x18000b008  mov     ecx, 2
0x18000b00d  mov     edx, [rdx]
0x18000b00f  mov     ebx, 1
0x18000b014  xor     eax, eax
0x18000b016  mov     r8d, ecx
0x18000b019  or      r8d, edx
0x18000b01c  cmp     r8d, edx
0x18000b01f  mov     r9d, r8d
0x18000b022  setz    al
0x18000b025  or      r9d, ebx
0x18000b028  cmp     r8d, edx
0x18000b02b  mov     [r10+10h], eax
0x18000b02f  mov     eax, edx
0x18000b031  cmovz   r9d, r8d
0x18000b035  lock cmpxchg [rsi], r9d
0x18000b03a  jz      short loc_18000B040
0x18000b03c  mov     edx, eax
0x18000b03e  jmp     short loc_18000B014
0x18000b040  test    bl, r9b
0x18000b043  jz      short loc_18000B049
0x18000b045  test    bl, dl
0x18000b047  jz      short loc_18000B04B
0x18000b049  xor     ebx, ebx
0x18000b04b  mov     [r10], ebx
0x18000b04e  jmp     loc_18000B1DA
0x18000b053  mov     ecx, [rdx]
0x18000b055  xor     r9d, r9d
0x18000b058  cmp     r11d, 5
0x18000b05c  mov     ebx, 1
0x18000b061  setz    r9b
0x18000b065  mov     eax, ecx
0x18000b067  mov     dword ptr [r10+4], 0
0x18000b06f  or      eax, ebx
0x18000b071  mov     edx, eax
0x18000b073  shr     edx, 16h
0x18000b076  and     edx, ebx
0x18000b078  cmp     edx, r9d
0x18000b07b  jz      short loc_18000B0BD
0x18000b07d  mov     r8d, eax
0x18000b080  shr     r8d, 0Fh
0x18000b084  and     r8d, 7Fh
0x18000b088  jbe     short loc_18000B0A2
0x18000b08a  cmp     r11d, ebx
0x18000b08d  mov     [r10+4], r8d
0x18000b091  mov     edx, 5
0x18000b096  cmovnz  edx, ebx
0x18000b099  and     eax, 0FFC07FFFh
0x18000b09e  mov     [r10+8], edx
0x18000b0a2  xor     r8d, r8d
0x18000b0a5  mov     edx, 400000h
0x18000b0aa  cmp     r11d, 5
0x18000b0ae  cmovz   r8d, edx
0x18000b0b2  mov     edx, eax
0x18000b0b4  btr     edx, 16h
0x18000b0b8  mov     eax, r8d
0x18000b0bb  or      eax, edx
0x18000b0bd  mov     edx, eax
0x18000b0bf  shr     edx, 0Fh
0x18000b0c2  and     edx, 7Fh
0x18000b0c5  lea     r8d, [rdx+1]
0x18000b0c9  cmp     r8d, 7Fh
0x18000b0cd  ja      short loc_18000B0D4
0x18000b0cf  cmp     r8d, edx
0x18000b0d2  jnb     short loc_18000B0DF
0x18000b0d4  mov     r8d, ebx
0x18000b0d7  mov     [r10+8], r11d
0x18000b0db  mov     [r10+4], edx
0x18000b0df  shl     r8d, 0Fh
0x18000b0e3  xor     r8d, eax
0x18000b0e6  and     r8d, 3F8000h
0x18000b0ed  xor     r8d, eax
0x18000b0f0  mov     eax, ecx
0x18000b0f2  lock cmpxchg [rsi], r8d
0x18000b0f7  jz      short loc_18000B100
0x18000b0f9  mov     ecx, eax
0x18000b0fb  jmp     loc_18000B065
0x18000b100  not     ecx
0x18000b102  and     ecx, ebx
0x18000b104  mov     [r10], ecx
0x18000b107  jmp     loc_18000B1D2
0x18000b10c  mov     edx, [rdx]
0x18000b10e  xor     ebp, ebp
0x18000b110  lea     ecx, [rbp+4]
0x18000b113  cmp     r11d, ecx
0x18000b116  lea     ebx, [rcx-3]
0x18000b119  setz    bpl
0x18000b11d  mov     eax, edx
0x18000b11f  mov     dword ptr [r10+4], 0
0x18000b127  or      eax, ebx
0x18000b129  mov     r8d, eax
0x18000b12c  shr     r8d, 0Eh
0x18000b130  and     r8d, ebx
0x18000b133  cmp     r8d, ebp
0x18000b136  jz      short loc_18000B17F
0x18000b138  mov     edi, eax
0x18000b13a  shr     edi, 5
0x18000b13d  and     edi, 1FFh
0x18000b143  jbe     short loc_18000B161
0x18000b145  mov     r8d, r11d
0x18000b148  mov     [r10+4], edi
0x18000b14c  neg     r8d
0x18000b14f  sbb     r9d, r9d
0x18000b152  not     r9d
0x18000b155  and     r9d, ecx
0x18000b158  mov     [r10+8], r9d
0x18000b15c  and     eax, 0FFFFC01Fh
0x18000b161  xor     r9d, r9d
0x18000b164  mov     r8d, 4000h
0x18000b16a  cmp     r11d, ecx
0x18000b16d  cmovz   r9d, r8d
0x18000b171  mov     r8d, eax
0x18000b174  btr     r8d, 0Eh
0x18000b179  mov     eax, r9d
0x18000b17c  or      eax, r8d
0x18000b17f  mov     r8d, eax
0x18000b182  shr     r8d, 5
0x18000b186  and     r8d, 1FFh
0x18000b18d  lea     r9d, [r8+1]
0x18000b191  cmp     r9d, 1FFh
0x18000b198  ja      short loc_18000B19F
0x18000b19a  cmp     r9d, r8d
0x18000b19d  jnb     short loc_18000B1AA
0x18000b19f  mov     r9d, ebx
0x18000b1a2  mov     [r10+8], r11d
0x18000b1a6  mov     [r10+4], r8d
0x18000b1aa  shl     r9d, 5
0x18000b1ae  xor     r9d, eax
0x18000b1b1  and     r9d, 3FE0h
0x18000b1b8  xor     r9d, eax
0x18000b1bb  mov     eax, edx
0x18000b1bd  lock cmpxchg [rsi], r9d
0x18000b1c2  jz      short loc_18000B1CB
0x18000b1c4  mov     edx, eax
0x18000b1c6  jmp     loc_18000B11D
0x18000b1cb  not     edx
0x18000b1cd  and     edx, ebx
0x18000b1cf  mov     [r10], edx
0x18000b1d2  mov     dword ptr [r10+10h], 0
0x18000b1da  mov     rax, r10
0x18000b1dd  pop     rdi
0x18000b1de  pop     rsi
0x18000b1df  pop     rbp
0x18000b1e0  pop     rbx
0x18000b1e1  retn
```
