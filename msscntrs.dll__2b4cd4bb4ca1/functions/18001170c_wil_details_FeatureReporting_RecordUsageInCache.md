# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x18001170c`
- end: `0x1800119e6`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `730`
- prototype: `__int64 __fastcall(__int64, volatile signed __int32 *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000fb64`

## callees

- `0x18001170c`

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
0x18001170c  push    rbx
0x18001170e  push    rbp
0x18001170f  push    rsi
0x180011710  push    rdi
0x180011711  xor     eax, eax
0x180011713  xorps   xmm0, xmm0
0x180011716  mov     r11d, r8d
0x180011719  mov     rsi, rdx
0x18001171c  mov     r10, rcx
0x18001171f  mov     r9d, r8d
0x180011722  movups  xmmword ptr [rcx], xmm0
0x180011725  mov     [rcx+10h], rax
0x180011729  test    r8d, r8d
0x18001172c  jz      loc_180011910
0x180011732  sub     r9d, 1
0x180011736  jz      loc_180011857
0x18001173c  sub     r9d, 1
0x180011740  jz      loc_1800117DE
0x180011746  sub     r9d, 1
0x18001174a  jz      loc_1800117DE
0x180011750  sub     r9d, 1
0x180011754  jz      loc_180011910
0x18001175a  sub     r9d, 1
0x18001175e  jz      loc_180011857
0x180011764  sub     r9d, 1
0x180011768  jz      short loc_1800117DE
0x18001176a  cmp     r9d, 1
0x18001176e  jz      short loc_1800117DE
0x180011770  add     r8d, 0FFFFFEC0h
0x180011777  lea     ebx, [rax+1]
0x18001177a  cmp     r8d, 40h ; '@'
0x18001177e  jge     short loc_1800117C9
0x180011780  mov     eax, [rdx+4]
0x180011783  lea     ecx, [rbx+0Fh]
0x180011786  mov     r9d, r8d
0x180011789  shl     r9d, 5
0x18001178d  test    cl, al
0x18001178f  jz      short loc_1800117A2
0x180011791  mov     edx, eax
0x180011793  shr     edx, 5
0x180011796  and     edx, 3Fh
0x180011799  cmp     edx, r8d
0x18001179c  jnz     short loc_1800117A2
0x18001179e  mov     edx, ebx
0x1800117a0  jmp     short loc_1800117A4
0x1800117a2  xor     edx, edx
0x1800117a4  mov     [r10+10h], edx
0x1800117a8  mov     edx, r9d
0x1800117ab  xor     edx, eax
0x1800117ad  and     edx, 7E0h
0x1800117b3  xor     edx, eax
0x1800117b5  or      edx, ecx
0x1800117b7  lock cmpxchg [rsi+4], edx
0x1800117bc  jnz     short loc_18001178D
0x1800117be  cmp     dword ptr [r10+10h], 0
0x1800117c3  jnz     loc_1800119DE
0x1800117c9  mov     [r10+8], r11d
0x1800117cd  mov     [r10+4], ebx
0x1800117d1  mov     dword ptr [r10+0Ch], 0
0x1800117d9  jmp     loc_1800119DE
0x1800117de  xor     ecx, ecx
0x1800117e0  sub     r11d, 2
0x1800117e4  jz      short loc_18001180C
0x1800117e6  sub     r11d, 1
0x1800117ea  jz      short loc_180011805
0x1800117ec  sub     r11d, 3
0x1800117f0  jz      short loc_1800117FE
0x1800117f2  cmp     r11d, 1
0x1800117f6  jnz     short loc_180011811
0x1800117f8  lea     ecx, [r11+0Fh]
0x1800117fc  jmp     short loc_180011811
0x1800117fe  mov     ecx, 4
0x180011803  jmp     short loc_180011811
0x180011805  mov     ecx, 8
0x18001180a  jmp     short loc_180011811
0x18001180c  mov     ecx, 2
0x180011811  mov     edx, [rdx]
0x180011813  mov     ebx, 1
0x180011818  xor     eax, eax
0x18001181a  mov     r8d, ecx
0x18001181d  or      r8d, edx
0x180011820  cmp     r8d, edx
0x180011823  mov     r9d, r8d
0x180011826  setz    al
0x180011829  or      r9d, ebx
0x18001182c  cmp     r8d, edx
0x18001182f  mov     [r10+10h], eax
0x180011833  mov     eax, edx
0x180011835  cmovz   r9d, r8d
0x180011839  lock cmpxchg [rsi], r9d
0x18001183e  jz      short loc_180011844
0x180011840  mov     edx, eax
0x180011842  jmp     short loc_180011818
0x180011844  test    bl, r9b
0x180011847  jz      short loc_18001184D
0x180011849  test    bl, dl
0x18001184b  jz      short loc_18001184F
0x18001184d  xor     ebx, ebx
0x18001184f  mov     [r10], ebx
0x180011852  jmp     loc_1800119DE
0x180011857  mov     ecx, [rdx]
0x180011859  xor     r9d, r9d
0x18001185c  cmp     r11d, 5
0x180011860  mov     ebx, 1
0x180011865  setz    r9b
0x180011869  mov     eax, ecx
0x18001186b  mov     dword ptr [r10+4], 0
0x180011873  or      eax, ebx
0x180011875  mov     edx, eax
0x180011877  shr     edx, 16h
0x18001187a  and     edx, ebx
0x18001187c  cmp     edx, r9d
0x18001187f  jz      short loc_1800118C1
0x180011881  mov     r8d, eax
0x180011884  shr     r8d, 0Fh
0x180011888  and     r8d, 7Fh
0x18001188c  jbe     short loc_1800118A6
0x18001188e  cmp     r11d, ebx
0x180011891  mov     [r10+4], r8d
0x180011895  mov     edx, 5
0x18001189a  cmovnz  edx, ebx
0x18001189d  and     eax, 0FFC07FFFh
0x1800118a2  mov     [r10+8], edx
0x1800118a6  xor     r8d, r8d
0x1800118a9  mov     edx, 400000h
0x1800118ae  cmp     r11d, 5
0x1800118b2  cmovz   r8d, edx
0x1800118b6  mov     edx, eax
0x1800118b8  btr     edx, 16h
0x1800118bc  mov     eax, r8d
0x1800118bf  or      eax, edx
0x1800118c1  mov     edx, eax
0x1800118c3  shr     edx, 0Fh
0x1800118c6  and     edx, 7Fh
0x1800118c9  lea     r8d, [rdx+1]
0x1800118cd  cmp     r8d, 7Fh
0x1800118d1  ja      short loc_1800118D8
0x1800118d3  cmp     r8d, edx
0x1800118d6  jnb     short loc_1800118E3
0x1800118d8  mov     r8d, ebx
0x1800118db  mov     [r10+8], r11d
0x1800118df  mov     [r10+4], edx
0x1800118e3  shl     r8d, 0Fh
0x1800118e7  xor     r8d, eax
0x1800118ea  and     r8d, 3F8000h
0x1800118f1  xor     r8d, eax
0x1800118f4  mov     eax, ecx
0x1800118f6  lock cmpxchg [rsi], r8d
0x1800118fb  jz      short loc_180011904
0x1800118fd  mov     ecx, eax
0x1800118ff  jmp     loc_180011869
0x180011904  not     ecx
0x180011906  and     ecx, ebx
0x180011908  mov     [r10], ecx
0x18001190b  jmp     loc_1800119D6
0x180011910  mov     edx, [rdx]
0x180011912  xor     ebp, ebp
0x180011914  lea     ecx, [rbp+4]
0x180011917  cmp     r11d, ecx
0x18001191a  lea     ebx, [rcx-3]
0x18001191d  setz    bpl
0x180011921  mov     eax, edx
0x180011923  mov     dword ptr [r10+4], 0
0x18001192b  or      eax, ebx
0x18001192d  mov     r8d, eax
0x180011930  shr     r8d, 0Eh
0x180011934  and     r8d, ebx
0x180011937  cmp     r8d, ebp
0x18001193a  jz      short loc_180011983
0x18001193c  mov     edi, eax
0x18001193e  shr     edi, 5
0x180011941  and     edi, 1FFh
0x180011947  jbe     short loc_180011965
0x180011949  mov     r8d, r11d
0x18001194c  mov     [r10+4], edi
0x180011950  neg     r8d
0x180011953  sbb     r9d, r9d
0x180011956  not     r9d
0x180011959  and     r9d, ecx
0x18001195c  mov     [r10+8], r9d
0x180011960  and     eax, 0FFFFC01Fh
0x180011965  xor     r9d, r9d
0x180011968  mov     r8d, 4000h
0x18001196e  cmp     r11d, ecx
0x180011971  cmovz   r9d, r8d
0x180011975  mov     r8d, eax
0x180011978  btr     r8d, 0Eh
0x18001197d  mov     eax, r9d
0x180011980  or      eax, r8d
0x180011983  mov     r8d, eax
0x180011986  shr     r8d, 5
0x18001198a  and     r8d, 1FFh
0x180011991  lea     r9d, [r8+1]
0x180011995  cmp     r9d, 1FFh
0x18001199c  ja      short loc_1800119A3
0x18001199e  cmp     r9d, r8d
0x1800119a1  jnb     short loc_1800119AE
0x1800119a3  mov     r9d, ebx
0x1800119a6  mov     [r10+8], r11d
0x1800119aa  mov     [r10+4], r8d
0x1800119ae  shl     r9d, 5
0x1800119b2  xor     r9d, eax
0x1800119b5  and     r9d, 3FE0h
0x1800119bc  xor     r9d, eax
0x1800119bf  mov     eax, edx
0x1800119c1  lock cmpxchg [rsi], r9d
0x1800119c6  jz      short loc_1800119CF
0x1800119c8  mov     edx, eax
0x1800119ca  jmp     loc_180011921
0x1800119cf  not     edx
0x1800119d1  and     edx, ebx
0x1800119d3  mov     [r10], edx
0x1800119d6  mov     dword ptr [r10+10h], 0
0x1800119de  mov     rax, r10
0x1800119e1  pop     rdi
0x1800119e2  pop     rsi
0x1800119e3  pop     rbp
0x1800119e4  pop     rbx
0x1800119e5  retn
```
