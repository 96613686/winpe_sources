# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x18000e55c`
- end: `0x18000e836`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `730`
- prototype: `__int64 __fastcall(__int64, volatile signed __int32 *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000bf84`

## callees

- `0x18000e55c`

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
0x18000e55c  push    rbx
0x18000e55e  push    rbp
0x18000e55f  push    rsi
0x18000e560  push    rdi
0x18000e561  xor     eax, eax
0x18000e563  xorps   xmm0, xmm0
0x18000e566  mov     r11d, r8d
0x18000e569  mov     rsi, rdx
0x18000e56c  mov     r10, rcx
0x18000e56f  mov     r9d, r8d
0x18000e572  movups  xmmword ptr [rcx], xmm0
0x18000e575  mov     [rcx+10h], rax
0x18000e579  test    r8d, r8d
0x18000e57c  jz      loc_18000E760
0x18000e582  sub     r9d, 1
0x18000e586  jz      loc_18000E6A7
0x18000e58c  sub     r9d, 1
0x18000e590  jz      loc_18000E62E
0x18000e596  sub     r9d, 1
0x18000e59a  jz      loc_18000E62E
0x18000e5a0  sub     r9d, 1
0x18000e5a4  jz      loc_18000E760
0x18000e5aa  sub     r9d, 1
0x18000e5ae  jz      loc_18000E6A7
0x18000e5b4  sub     r9d, 1
0x18000e5b8  jz      short loc_18000E62E
0x18000e5ba  cmp     r9d, 1
0x18000e5be  jz      short loc_18000E62E
0x18000e5c0  add     r8d, 0FFFFFEC0h
0x18000e5c7  lea     ebx, [rax+1]
0x18000e5ca  cmp     r8d, 40h ; '@'
0x18000e5ce  jge     short loc_18000E619
0x18000e5d0  mov     eax, [rdx+4]
0x18000e5d3  lea     ecx, [rbx+0Fh]
0x18000e5d6  mov     r9d, r8d
0x18000e5d9  shl     r9d, 5
0x18000e5dd  test    cl, al
0x18000e5df  jz      short loc_18000E5F2
0x18000e5e1  mov     edx, eax
0x18000e5e3  shr     edx, 5
0x18000e5e6  and     edx, 3Fh
0x18000e5e9  cmp     edx, r8d
0x18000e5ec  jnz     short loc_18000E5F2
0x18000e5ee  mov     edx, ebx
0x18000e5f0  jmp     short loc_18000E5F4
0x18000e5f2  xor     edx, edx
0x18000e5f4  mov     [r10+10h], edx
0x18000e5f8  mov     edx, r9d
0x18000e5fb  xor     edx, eax
0x18000e5fd  and     edx, 7E0h
0x18000e603  xor     edx, eax
0x18000e605  or      edx, ecx
0x18000e607  lock cmpxchg [rsi+4], edx
0x18000e60c  jnz     short loc_18000E5DD
0x18000e60e  cmp     dword ptr [r10+10h], 0
0x18000e613  jnz     loc_18000E82E
0x18000e619  mov     [r10+8], r11d
0x18000e61d  mov     [r10+4], ebx
0x18000e621  mov     dword ptr [r10+0Ch], 0
0x18000e629  jmp     loc_18000E82E
0x18000e62e  xor     ecx, ecx
0x18000e630  sub     r11d, 2
0x18000e634  jz      short loc_18000E65C
0x18000e636  sub     r11d, 1
0x18000e63a  jz      short loc_18000E655
0x18000e63c  sub     r11d, 3
0x18000e640  jz      short loc_18000E64E
0x18000e642  cmp     r11d, 1
0x18000e646  jnz     short loc_18000E661
0x18000e648  lea     ecx, [r11+0Fh]
0x18000e64c  jmp     short loc_18000E661
0x18000e64e  mov     ecx, 4
0x18000e653  jmp     short loc_18000E661
0x18000e655  mov     ecx, 8
0x18000e65a  jmp     short loc_18000E661
0x18000e65c  mov     ecx, 2
0x18000e661  mov     edx, [rdx]
0x18000e663  mov     ebx, 1
0x18000e668  xor     eax, eax
0x18000e66a  mov     r8d, ecx
0x18000e66d  or      r8d, edx
0x18000e670  cmp     r8d, edx
0x18000e673  mov     r9d, r8d
0x18000e676  setz    al
0x18000e679  or      r9d, ebx
0x18000e67c  cmp     r8d, edx
0x18000e67f  mov     [r10+10h], eax
0x18000e683  mov     eax, edx
0x18000e685  cmovz   r9d, r8d
0x18000e689  lock cmpxchg [rsi], r9d
0x18000e68e  jz      short loc_18000E694
0x18000e690  mov     edx, eax
0x18000e692  jmp     short loc_18000E668
0x18000e694  test    bl, r9b
0x18000e697  jz      short loc_18000E69D
0x18000e699  test    bl, dl
0x18000e69b  jz      short loc_18000E69F
0x18000e69d  xor     ebx, ebx
0x18000e69f  mov     [r10], ebx
0x18000e6a2  jmp     loc_18000E82E
0x18000e6a7  mov     ecx, [rdx]
0x18000e6a9  xor     r9d, r9d
0x18000e6ac  cmp     r11d, 5
0x18000e6b0  mov     ebx, 1
0x18000e6b5  setz    r9b
0x18000e6b9  mov     eax, ecx
0x18000e6bb  mov     dword ptr [r10+4], 0
0x18000e6c3  or      eax, ebx
0x18000e6c5  mov     edx, eax
0x18000e6c7  shr     edx, 16h
0x18000e6ca  and     edx, ebx
0x18000e6cc  cmp     edx, r9d
0x18000e6cf  jz      short loc_18000E711
0x18000e6d1  mov     r8d, eax
0x18000e6d4  shr     r8d, 0Fh
0x18000e6d8  and     r8d, 7Fh
0x18000e6dc  jbe     short loc_18000E6F6
0x18000e6de  cmp     r11d, ebx
0x18000e6e1  mov     [r10+4], r8d
0x18000e6e5  mov     edx, 5
0x18000e6ea  cmovnz  edx, ebx
0x18000e6ed  and     eax, 0FFC07FFFh
0x18000e6f2  mov     [r10+8], edx
0x18000e6f6  xor     r8d, r8d
0x18000e6f9  mov     edx, 400000h
0x18000e6fe  cmp     r11d, 5
0x18000e702  cmovz   r8d, edx
0x18000e706  mov     edx, eax
0x18000e708  btr     edx, 16h
0x18000e70c  mov     eax, r8d
0x18000e70f  or      eax, edx
0x18000e711  mov     edx, eax
0x18000e713  shr     edx, 0Fh
0x18000e716  and     edx, 7Fh
0x18000e719  lea     r8d, [rdx+1]
0x18000e71d  cmp     r8d, 7Fh
0x18000e721  ja      short loc_18000E728
0x18000e723  cmp     r8d, edx
0x18000e726  jnb     short loc_18000E733
0x18000e728  mov     r8d, ebx
0x18000e72b  mov     [r10+8], r11d
0x18000e72f  mov     [r10+4], edx
0x18000e733  shl     r8d, 0Fh
0x18000e737  xor     r8d, eax
0x18000e73a  and     r8d, 3F8000h
0x18000e741  xor     r8d, eax
0x18000e744  mov     eax, ecx
0x18000e746  lock cmpxchg [rsi], r8d
0x18000e74b  jz      short loc_18000E754
0x18000e74d  mov     ecx, eax
0x18000e74f  jmp     loc_18000E6B9
0x18000e754  not     ecx
0x18000e756  and     ecx, ebx
0x18000e758  mov     [r10], ecx
0x18000e75b  jmp     loc_18000E826
0x18000e760  mov     edx, [rdx]
0x18000e762  xor     ebp, ebp
0x18000e764  lea     ecx, [rbp+4]
0x18000e767  cmp     r11d, ecx
0x18000e76a  lea     ebx, [rcx-3]
0x18000e76d  setz    bpl
0x18000e771  mov     eax, edx
0x18000e773  mov     dword ptr [r10+4], 0
0x18000e77b  or      eax, ebx
0x18000e77d  mov     r8d, eax
0x18000e780  shr     r8d, 0Eh
0x18000e784  and     r8d, ebx
0x18000e787  cmp     r8d, ebp
0x18000e78a  jz      short loc_18000E7D3
0x18000e78c  mov     edi, eax
0x18000e78e  shr     edi, 5
0x18000e791  and     edi, 1FFh
0x18000e797  jbe     short loc_18000E7B5
0x18000e799  mov     r8d, r11d
0x18000e79c  mov     [r10+4], edi
0x18000e7a0  neg     r8d
0x18000e7a3  sbb     r9d, r9d
0x18000e7a6  not     r9d
0x18000e7a9  and     r9d, ecx
0x18000e7ac  mov     [r10+8], r9d
0x18000e7b0  and     eax, 0FFFFC01Fh
0x18000e7b5  xor     r9d, r9d
0x18000e7b8  mov     r8d, 4000h
0x18000e7be  cmp     r11d, ecx
0x18000e7c1  cmovz   r9d, r8d
0x18000e7c5  mov     r8d, eax
0x18000e7c8  btr     r8d, 0Eh
0x18000e7cd  mov     eax, r9d
0x18000e7d0  or      eax, r8d
0x18000e7d3  mov     r8d, eax
0x18000e7d6  shr     r8d, 5
0x18000e7da  and     r8d, 1FFh
0x18000e7e1  lea     r9d, [r8+1]
0x18000e7e5  cmp     r9d, 1FFh
0x18000e7ec  ja      short loc_18000E7F3
0x18000e7ee  cmp     r9d, r8d
0x18000e7f1  jnb     short loc_18000E7FE
0x18000e7f3  mov     r9d, ebx
0x18000e7f6  mov     [r10+8], r11d
0x18000e7fa  mov     [r10+4], r8d
0x18000e7fe  shl     r9d, 5
0x18000e802  xor     r9d, eax
0x18000e805  and     r9d, 3FE0h
0x18000e80c  xor     r9d, eax
0x18000e80f  mov     eax, edx
0x18000e811  lock cmpxchg [rsi], r9d
0x18000e816  jz      short loc_18000E81F
0x18000e818  mov     edx, eax
0x18000e81a  jmp     loc_18000E771
0x18000e81f  not     edx
0x18000e821  and     edx, ebx
0x18000e823  mov     [r10], edx
0x18000e826  mov     dword ptr [r10+10h], 0
0x18000e82e  mov     rax, r10
0x18000e831  pop     rdi
0x18000e832  pop     rsi
0x18000e833  pop     rbp
0x18000e834  pop     rbx
0x18000e835  retn
```
