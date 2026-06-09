# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x180016244`
- end: `0x18001651e`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `730`
- prototype: `__int64 __fastcall(__int64, volatile signed __int32 *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180015ab8`

## callees

- `0x180016244`

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
0x180016244  push    rbx
0x180016246  push    rbp
0x180016247  push    rsi
0x180016248  push    rdi
0x180016249  xor     eax, eax
0x18001624b  xorps   xmm0, xmm0
0x18001624e  mov     r11d, r8d
0x180016251  mov     rsi, rdx
0x180016254  mov     r10, rcx
0x180016257  mov     r9d, r8d
0x18001625a  movups  xmmword ptr [rcx], xmm0
0x18001625d  mov     [rcx+10h], rax
0x180016261  test    r8d, r8d
0x180016264  jz      loc_180016448
0x18001626a  sub     r9d, 1
0x18001626e  jz      loc_18001638F
0x180016274  sub     r9d, 1
0x180016278  jz      loc_180016316
0x18001627e  sub     r9d, 1
0x180016282  jz      loc_180016316
0x180016288  sub     r9d, 1
0x18001628c  jz      loc_180016448
0x180016292  sub     r9d, 1
0x180016296  jz      loc_18001638F
0x18001629c  sub     r9d, 1
0x1800162a0  jz      short loc_180016316
0x1800162a2  cmp     r9d, 1
0x1800162a6  jz      short loc_180016316
0x1800162a8  add     r8d, 0FFFFFEC0h
0x1800162af  lea     ebx, [rax+1]
0x1800162b2  cmp     r8d, 40h ; '@'
0x1800162b6  jge     short loc_180016301
0x1800162b8  mov     eax, [rdx+4]
0x1800162bb  lea     ecx, [rbx+0Fh]
0x1800162be  mov     r9d, r8d
0x1800162c1  shl     r9d, 5
0x1800162c5  test    cl, al
0x1800162c7  jz      short loc_1800162DA
0x1800162c9  mov     edx, eax
0x1800162cb  shr     edx, 5
0x1800162ce  and     edx, 3Fh
0x1800162d1  cmp     edx, r8d
0x1800162d4  jnz     short loc_1800162DA
0x1800162d6  mov     edx, ebx
0x1800162d8  jmp     short loc_1800162DC
0x1800162da  xor     edx, edx
0x1800162dc  mov     [r10+10h], edx
0x1800162e0  mov     edx, r9d
0x1800162e3  xor     edx, eax
0x1800162e5  and     edx, 7E0h
0x1800162eb  xor     edx, eax
0x1800162ed  or      edx, ecx
0x1800162ef  lock cmpxchg [rsi+4], edx
0x1800162f4  jnz     short loc_1800162C5
0x1800162f6  cmp     dword ptr [r10+10h], 0
0x1800162fb  jnz     loc_180016516
0x180016301  mov     [r10+8], r11d
0x180016305  mov     [r10+4], ebx
0x180016309  mov     dword ptr [r10+0Ch], 0
0x180016311  jmp     loc_180016516
0x180016316  xor     ecx, ecx
0x180016318  sub     r11d, 2
0x18001631c  jz      short loc_180016344
0x18001631e  sub     r11d, 1
0x180016322  jz      short loc_18001633D
0x180016324  sub     r11d, 3
0x180016328  jz      short loc_180016336
0x18001632a  cmp     r11d, 1
0x18001632e  jnz     short loc_180016349
0x180016330  lea     ecx, [r11+0Fh]
0x180016334  jmp     short loc_180016349
0x180016336  mov     ecx, 4
0x18001633b  jmp     short loc_180016349
0x18001633d  mov     ecx, 8
0x180016342  jmp     short loc_180016349
0x180016344  mov     ecx, 2
0x180016349  mov     edx, [rdx]
0x18001634b  mov     ebx, 1
0x180016350  xor     eax, eax
0x180016352  mov     r8d, ecx
0x180016355  or      r8d, edx
0x180016358  cmp     r8d, edx
0x18001635b  mov     r9d, r8d
0x18001635e  setz    al
0x180016361  or      r9d, ebx
0x180016364  cmp     r8d, edx
0x180016367  mov     [r10+10h], eax
0x18001636b  mov     eax, edx
0x18001636d  cmovz   r9d, r8d
0x180016371  lock cmpxchg [rsi], r9d
0x180016376  jz      short loc_18001637C
0x180016378  mov     edx, eax
0x18001637a  jmp     short loc_180016350
0x18001637c  test    bl, r9b
0x18001637f  jz      short loc_180016385
0x180016381  test    bl, dl
0x180016383  jz      short loc_180016387
0x180016385  xor     ebx, ebx
0x180016387  mov     [r10], ebx
0x18001638a  jmp     loc_180016516
0x18001638f  mov     ecx, [rdx]
0x180016391  xor     r9d, r9d
0x180016394  cmp     r11d, 5
0x180016398  mov     ebx, 1
0x18001639d  setz    r9b
0x1800163a1  mov     eax, ecx
0x1800163a3  mov     dword ptr [r10+4], 0
0x1800163ab  or      eax, ebx
0x1800163ad  mov     edx, eax
0x1800163af  shr     edx, 16h
0x1800163b2  and     edx, ebx
0x1800163b4  cmp     edx, r9d
0x1800163b7  jz      short loc_1800163F9
0x1800163b9  mov     r8d, eax
0x1800163bc  shr     r8d, 0Fh
0x1800163c0  and     r8d, 7Fh
0x1800163c4  jbe     short loc_1800163DE
0x1800163c6  cmp     r11d, ebx
0x1800163c9  mov     [r10+4], r8d
0x1800163cd  mov     edx, 5
0x1800163d2  cmovnz  edx, ebx
0x1800163d5  and     eax, 0FFC07FFFh
0x1800163da  mov     [r10+8], edx
0x1800163de  xor     r8d, r8d
0x1800163e1  mov     edx, 400000h
0x1800163e6  cmp     r11d, 5
0x1800163ea  cmovz   r8d, edx
0x1800163ee  mov     edx, eax
0x1800163f0  btr     edx, 16h
0x1800163f4  mov     eax, r8d
0x1800163f7  or      eax, edx
0x1800163f9  mov     edx, eax
0x1800163fb  shr     edx, 0Fh
0x1800163fe  and     edx, 7Fh
0x180016401  lea     r8d, [rdx+1]
0x180016405  cmp     r8d, 7Fh
0x180016409  ja      short loc_180016410
0x18001640b  cmp     r8d, edx
0x18001640e  jnb     short loc_18001641B
0x180016410  mov     r8d, ebx
0x180016413  mov     [r10+8], r11d
0x180016417  mov     [r10+4], edx
0x18001641b  shl     r8d, 0Fh
0x18001641f  xor     r8d, eax
0x180016422  and     r8d, 3F8000h
0x180016429  xor     r8d, eax
0x18001642c  mov     eax, ecx
0x18001642e  lock cmpxchg [rsi], r8d
0x180016433  jz      short loc_18001643C
0x180016435  mov     ecx, eax
0x180016437  jmp     loc_1800163A1
0x18001643c  not     ecx
0x18001643e  and     ecx, ebx
0x180016440  mov     [r10], ecx
0x180016443  jmp     loc_18001650E
0x180016448  mov     edx, [rdx]
0x18001644a  xor     ebp, ebp
0x18001644c  lea     ecx, [rbp+4]
0x18001644f  cmp     r11d, ecx
0x180016452  lea     ebx, [rcx-3]
0x180016455  setz    bpl
0x180016459  mov     eax, edx
0x18001645b  mov     dword ptr [r10+4], 0
0x180016463  or      eax, ebx
0x180016465  mov     r8d, eax
0x180016468  shr     r8d, 0Eh
0x18001646c  and     r8d, ebx
0x18001646f  cmp     r8d, ebp
0x180016472  jz      short loc_1800164BB
0x180016474  mov     edi, eax
0x180016476  shr     edi, 5
0x180016479  and     edi, 1FFh
0x18001647f  jbe     short loc_18001649D
0x180016481  mov     r8d, r11d
0x180016484  mov     [r10+4], edi
0x180016488  neg     r8d
0x18001648b  sbb     r9d, r9d
0x18001648e  not     r9d
0x180016491  and     r9d, ecx
0x180016494  mov     [r10+8], r9d
0x180016498  and     eax, 0FFFFC01Fh
0x18001649d  xor     r9d, r9d
0x1800164a0  mov     r8d, 4000h
0x1800164a6  cmp     r11d, ecx
0x1800164a9  cmovz   r9d, r8d
0x1800164ad  mov     r8d, eax
0x1800164b0  btr     r8d, 0Eh
0x1800164b5  mov     eax, r9d
0x1800164b8  or      eax, r8d
0x1800164bb  mov     r8d, eax
0x1800164be  shr     r8d, 5
0x1800164c2  and     r8d, 1FFh
0x1800164c9  lea     r9d, [r8+1]
0x1800164cd  cmp     r9d, 1FFh
0x1800164d4  ja      short loc_1800164DB
0x1800164d6  cmp     r9d, r8d
0x1800164d9  jnb     short loc_1800164E6
0x1800164db  mov     r9d, ebx
0x1800164de  mov     [r10+8], r11d
0x1800164e2  mov     [r10+4], r8d
0x1800164e6  shl     r9d, 5
0x1800164ea  xor     r9d, eax
0x1800164ed  and     r9d, 3FE0h
0x1800164f4  xor     r9d, eax
0x1800164f7  mov     eax, edx
0x1800164f9  lock cmpxchg [rsi], r9d
0x1800164fe  jz      short loc_180016507
0x180016500  mov     edx, eax
0x180016502  jmp     loc_180016459
0x180016507  not     edx
0x180016509  and     edx, ebx
0x18001650b  mov     [r10], edx
0x18001650e  mov     dword ptr [r10+10h], 0
0x180016516  mov     rax, r10
0x180016519  pop     rdi
0x18001651a  pop     rsi
0x18001651b  pop     rbp
0x18001651c  pop     rbx
0x18001651d  retn
```
