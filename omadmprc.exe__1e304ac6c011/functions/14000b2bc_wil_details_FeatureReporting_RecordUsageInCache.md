# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x14000b2bc`
- end: `0x14000b597`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `731`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400081cc`

## callees

- `0x14000b2bc`

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
0x14000b2bc  push    rbx
0x14000b2be  push    rbp
0x14000b2bf  push    rsi
0x14000b2c0  push    rdi
0x14000b2c1  xor     eax, eax
0x14000b2c3  xorps   xmm0, xmm0
0x14000b2c6  mov     r11d, r8d
0x14000b2c9  mov     rsi, rdx
0x14000b2cc  mov     r10, rcx
0x14000b2cf  mov     r9d, r8d
0x14000b2d2  movups  xmmword ptr [rcx], xmm0
0x14000b2d5  mov     [rcx+10h], rax
0x14000b2d9  test    r8d, r8d
0x14000b2dc  jz      loc_14000B4C0
0x14000b2e2  sub     r9d, 1
0x14000b2e6  jz      loc_14000B407
0x14000b2ec  sub     r9d, 1
0x14000b2f0  jz      loc_14000B38E
0x14000b2f6  sub     r9d, 1
0x14000b2fa  jz      loc_14000B38E
0x14000b300  sub     r9d, 1
0x14000b304  jz      loc_14000B4C0
0x14000b30a  sub     r9d, 1
0x14000b30e  jz      loc_14000B407
0x14000b314  sub     r9d, 1
0x14000b318  jz      short loc_14000B38E
0x14000b31a  cmp     r9d, 1
0x14000b31e  jz      short loc_14000B38E
0x14000b320  add     r8d, 0FFFFFEC0h
0x14000b327  lea     ebx, [rax+1]
0x14000b32a  cmp     r8d, 40h ; '@'
0x14000b32e  jge     short loc_14000B379
0x14000b330  mov     eax, [rdx+4]
0x14000b333  lea     ecx, [rbx+0Fh]
0x14000b336  mov     r9d, r8d
0x14000b339  shl     r9d, 5
0x14000b33d  test    cl, al
0x14000b33f  jz      short loc_14000B352
0x14000b341  mov     edx, eax
0x14000b343  shr     edx, 5
0x14000b346  and     edx, 3Fh
0x14000b349  cmp     edx, r8d
0x14000b34c  jnz     short loc_14000B352
0x14000b34e  mov     edx, ebx
0x14000b350  jmp     short loc_14000B354
0x14000b352  xor     edx, edx
0x14000b354  mov     [r10+10h], edx
0x14000b358  mov     edx, r9d
0x14000b35b  xor     edx, eax
0x14000b35d  and     edx, 7E0h
0x14000b363  xor     edx, eax
0x14000b365  or      edx, ecx
0x14000b367  lock cmpxchg [rsi+4], edx
0x14000b36c  jnz     short loc_14000B33D
0x14000b36e  cmp     dword ptr [r10+10h], 0
0x14000b373  jnz     loc_14000B58E
0x14000b379  mov     [r10+8], r11d
0x14000b37d  mov     [r10+4], ebx
0x14000b381  mov     dword ptr [r10+0Ch], 0
0x14000b389  jmp     loc_14000B58E
0x14000b38e  xor     ecx, ecx
0x14000b390  sub     r11d, 2
0x14000b394  jz      short loc_14000B3BC
0x14000b396  sub     r11d, 1
0x14000b39a  jz      short loc_14000B3B5
0x14000b39c  sub     r11d, 3
0x14000b3a0  jz      short loc_14000B3AE
0x14000b3a2  cmp     r11d, 1
0x14000b3a6  jnz     short loc_14000B3C1
0x14000b3a8  lea     ecx, [r11+0Fh]
0x14000b3ac  jmp     short loc_14000B3C1
0x14000b3ae  mov     ecx, 4
0x14000b3b3  jmp     short loc_14000B3C1
0x14000b3b5  mov     ecx, 8
0x14000b3ba  jmp     short loc_14000B3C1
0x14000b3bc  mov     ecx, 2
0x14000b3c1  mov     edx, [rdx]
0x14000b3c3  mov     ebx, 1
0x14000b3c8  xor     eax, eax
0x14000b3ca  mov     r8d, ecx
0x14000b3cd  or      r8d, edx
0x14000b3d0  cmp     r8d, edx
0x14000b3d3  mov     r9d, r8d
0x14000b3d6  setz    al
0x14000b3d9  or      r9d, ebx
0x14000b3dc  cmp     r8d, edx
0x14000b3df  mov     [r10+10h], eax
0x14000b3e3  mov     eax, edx
0x14000b3e5  cmovz   r9d, r8d
0x14000b3e9  lock cmpxchg [rsi], r9d
0x14000b3ee  jz      short loc_14000B3F4
0x14000b3f0  mov     edx, eax
0x14000b3f2  jmp     short loc_14000B3C8
0x14000b3f4  test    bl, r9b
0x14000b3f7  jz      short loc_14000B3FD
0x14000b3f9  test    bl, dl
0x14000b3fb  jz      short loc_14000B3FF
0x14000b3fd  xor     ebx, ebx
0x14000b3ff  mov     [r10], ebx
0x14000b402  jmp     loc_14000B58E
0x14000b407  mov     ecx, [rdx]
0x14000b409  xor     r9d, r9d
0x14000b40c  cmp     r11d, 5
0x14000b410  mov     ebx, 1
0x14000b415  setz    r9b
0x14000b419  mov     eax, ecx
0x14000b41b  mov     dword ptr [r10+4], 0
0x14000b423  or      eax, ebx
0x14000b425  mov     edx, eax
0x14000b427  shr     edx, 16h
0x14000b42a  and     edx, ebx
0x14000b42c  cmp     edx, r9d
0x14000b42f  jz      short loc_14000B471
0x14000b431  mov     r8d, eax
0x14000b434  shr     r8d, 0Fh
0x14000b438  and     r8d, 7Fh
0x14000b43c  jbe     short loc_14000B456
0x14000b43e  cmp     r11d, ebx
0x14000b441  mov     [r10+4], r8d
0x14000b445  mov     edx, 5
0x14000b44a  cmovnz  edx, ebx
0x14000b44d  and     eax, 0FFC07FFFh
0x14000b452  mov     [r10+8], edx
0x14000b456  xor     r8d, r8d
0x14000b459  mov     edx, 400000h
0x14000b45e  cmp     r11d, 5
0x14000b462  cmovz   r8d, edx
0x14000b466  mov     edx, eax
0x14000b468  btr     edx, 16h
0x14000b46c  mov     eax, r8d
0x14000b46f  or      eax, edx
0x14000b471  mov     edx, eax
0x14000b473  shr     edx, 0Fh
0x14000b476  and     edx, 7Fh
0x14000b479  lea     r8d, [rdx+1]
0x14000b47d  cmp     r8d, 7Fh
0x14000b481  ja      short loc_14000B488
0x14000b483  cmp     r8d, edx
0x14000b486  jnb     short loc_14000B493
0x14000b488  mov     r8d, ebx
0x14000b48b  mov     [r10+8], r11d
0x14000b48f  mov     [r10+4], edx
0x14000b493  shl     r8d, 0Fh
0x14000b497  xor     r8d, eax
0x14000b49a  and     r8d, 3F8000h
0x14000b4a1  xor     r8d, eax
0x14000b4a4  mov     eax, ecx
0x14000b4a6  lock cmpxchg [rsi], r8d
0x14000b4ab  jz      short loc_14000B4B4
0x14000b4ad  mov     ecx, eax
0x14000b4af  jmp     loc_14000B419
0x14000b4b4  not     ecx
0x14000b4b6  and     ecx, ebx
0x14000b4b8  mov     [r10], ecx
0x14000b4bb  jmp     loc_14000B586
0x14000b4c0  mov     edx, [rdx]
0x14000b4c2  xor     ebp, ebp
0x14000b4c4  lea     ecx, [rbp+4]
0x14000b4c7  cmp     r11d, ecx
0x14000b4ca  lea     ebx, [rcx-3]
0x14000b4cd  setz    bpl
0x14000b4d1  mov     eax, edx
0x14000b4d3  mov     dword ptr [r10+4], 0
0x14000b4db  or      eax, ebx
0x14000b4dd  mov     r8d, eax
0x14000b4e0  shr     r8d, 0Eh
0x14000b4e4  and     r8d, ebx
0x14000b4e7  cmp     r8d, ebp
0x14000b4ea  jz      short loc_14000B533
0x14000b4ec  mov     edi, eax
0x14000b4ee  shr     edi, 5
0x14000b4f1  and     edi, 1FFh
0x14000b4f7  jbe     short loc_14000B515
0x14000b4f9  mov     r8d, r11d
0x14000b4fc  mov     [r10+4], edi
0x14000b500  neg     r8d
0x14000b503  sbb     r9d, r9d
0x14000b506  not     r9d
0x14000b509  and     r9d, ecx
0x14000b50c  mov     [r10+8], r9d
0x14000b510  and     eax, 0FFFFC01Fh
0x14000b515  xor     r9d, r9d
0x14000b518  mov     r8d, 4000h
0x14000b51e  cmp     r11d, ecx
0x14000b521  cmovz   r9d, r8d
0x14000b525  mov     r8d, eax
0x14000b528  btr     r8d, 0Eh
0x14000b52d  mov     eax, r9d
0x14000b530  or      eax, r8d
0x14000b533  mov     r8d, eax
0x14000b536  shr     r8d, 5
0x14000b53a  and     r8d, 1FFh
0x14000b541  lea     r9d, [r8+1]
0x14000b545  cmp     r9d, 1FFh
0x14000b54c  ja      short loc_14000B553
0x14000b54e  cmp     r9d, r8d
0x14000b551  jnb     short loc_14000B55E
0x14000b553  mov     r9d, ebx
0x14000b556  mov     [r10+8], r11d
0x14000b55a  mov     [r10+4], r8d
0x14000b55e  shl     r9d, 5
0x14000b562  xor     r9d, eax
0x14000b565  and     r9d, 3FE0h
0x14000b56c  xor     r9d, eax
0x14000b56f  mov     eax, edx
0x14000b571  lock cmpxchg [rsi], r9d
0x14000b576  jz      short loc_14000B57F
0x14000b578  mov     edx, eax
0x14000b57a  jmp     loc_14000B4D1
0x14000b57f  not     edx
0x14000b581  and     edx, ebx
0x14000b583  mov     [r10], edx
0x14000b586  mov     dword ptr [r10+10h], 0
0x14000b58e  mov     rax, r10
0x14000b591  pop     rdi
0x14000b592  pop     rsi
0x14000b593  pop     rbp
0x14000b594  pop     rbx
0x14000b595  retn
```
