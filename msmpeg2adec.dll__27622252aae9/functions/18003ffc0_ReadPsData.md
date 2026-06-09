# ReadPsData

- ea: `0x18003ffc0`
- end: `0x180040533`
- name: `ReadPsData`
- size: `1395`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18003ab30`

## callees

- `0x1800363f0`
- `0x18003ffc0`

## pseudocode

```c
__int64 __fastcall ReadPsData(_DWORD *a1, int *a2, int a3)
{
  int v6; // r15d
  bool v7; // zf
  unsigned int v8; // eax
  unsigned int v9; // eax
  unsigned int v10; // eax
  int v11; // ecx
  int v12; // edi
  unsigned int v13; // eax
  __int64 v14; // rax
  int j; // r13d
  int v16; // eax
  int v17; // r12d
  __int64 *v18; // rsi
  int k; // ebp
  int v20; // edi
  __int64 v21; // rax
  __int64 v22; // rax
  int v23; // r12d
  __int64 *v24; // rsi
  int v25; // r13d
  int m; // ebp
  int v27; // edi
  __int64 v28; // rax
  __int64 v29; // rax
  unsigned int v30; // ecx
  int v31; // edi
  int v32; // esi
  int v34; // ecx
  int i; // esi
  unsigned int v36; // edi

  if ( !a1 )
    return 0;
  if ( a2 )
    v6 = *a2 + 8 * (a2[2] - a2[4]);
  else
    v6 = 0;
  if ( !*a2 )
    FillBitCache(a2, 1u);
  if ( (((unsigned int)a2[1] >> --*a2) & 1) != 0 )
  {
    if ( !*a2 )
      FillBitCache(a2, 1u);
    v7 = (((unsigned int)a2[1] >> --*a2) & 1) == 0;
    a1[6] = ((unsigned int)a2[1] >> *a2) & 1;
    if ( !v7 )
    {
      if ( (unsigned int)*a2 < 3 )
        FillBitCache(a2, 3u);
      *a2 -= 3;
      v8 = ((unsigned int)a2[1] >> *a2) & 7;
      a1[486] = v8;
      if ( v8 <= 2 )
      {
        a1[9] = 0;
      }
      else
      {
        a1[9] = 1;
        a1[486] = v8 - 3;
      }
    }
    if ( !*a2 )
      FillBitCache(a2, 1u);
    v7 = (((unsigned int)a2[1] >> --*a2) & 1) == 0;
    a1[7] = ((unsigned int)a2[1] >> *a2) & 1;
    if ( !v7 )
    {
      if ( (unsigned int)*a2 < 3 )
        FillBitCache(a2, 3u);
      *a2 -= 3;
      v9 = ((unsigned int)a2[1] >> *a2) & 7;
      a1[487] = v9;
      if ( v9 > 2 )
        a1[487] = v9 - 3;
    }
    if ( !*a2 )
      FillBitCache(a2, 1u);
    a1[8] = ((unsigned int)a2[1] >> --*a2) & 1;
  }
  if ( !*a2 )
    FillBitCache(a2, 1u);
  v7 = (((unsigned int)a2[1] >> --*a2) & 1) == 0;
  a1[488] = ((unsigned int)a2[1] >> *a2) & 1;
  v10 = *a2;
  if ( v7 )
  {
    if ( v10 < 2 )
      FillBitCache(a2, 2u);
    *a2 -= 2;
    v11 = dword_1800959E0[((unsigned __int64)(unsigned int)a2[1] >> *(_BYTE *)a2) & 3];
    a1[489] = v11;
  }
  else
  {
    if ( v10 < 2 )
      FillBitCache(a2, 2u);
    *a2 -= 2;
    v12 = 1;
    v11 = (((unsigned int)a2[1] >> *a2) & 3) + 1;
    v13 = (((unsigned int)a2[1] >> *a2) & 3) + 2;
    a1[489] = v11;
    if ( v13 > 1 )
    {
      do
      {
        if ( (unsigned int)*a2 < 5 )
          FillBitCache(a2, 5u);
        *a2 -= 5;
        v14 = v12++;
        a1[v14 + 490] = (((unsigned int)a2[1] >> *a2) & 0x1F) + 1;
        v11 = a1[489];
      }
      while ( v12 < v11 + 1 );
    }
  }
  if ( (int)a1[486] > 2 || (int)a1[487] > 2 )
  {
    v34 = v6 + 8 * (a2[4] - a2[2]) - *a2;
    a1[5] = 0;
    if ( v34 <= a3 )
    {
      for ( i = a3 - v34; i; i -= v36 )
      {
        v36 = i;
        if ( i > 8 )
          v36 = 8;
        if ( *a2 < v36 )
          FillBitCache(a2, v36);
        *a2 -= v36;
      }
      return (unsigned int)(v6 + 8 * (a2[4] - a2[2]) - *a2);
    }
    return 0;
  }
  if ( a1[6] )
  {
    for ( j = 0; j < v11; v11 = a1[489] )
    {
      if ( !*a2 )
        FillBitCache(a2, 1u);
      --*a2;
      v16 = a1[9];
      v17 = ((unsigned int)a2[1] >> *a2) & 1;
      if ( v17 )
      {
        v18 = aBookPsIidFineTimeDecode;
        if ( !v16 )
          v18 = aBookPsIidTimeDecode;
      }
      else
      {
        v18 = aBookPsIidFineFreqDecode;
        if ( !v16 )
          v18 = aBookPsIidFreqDecode;
      }
      for ( k = 0; k < dword_1800959F0[a1[486]]; a1[v21] = v20 + 64 )
      {
        LOBYTE(v20) = 0;
        do
        {
          if ( !*a2 )
            FillBitCache(a2, 1u);
          --*a2;
          v20 = *((char *)v18 + 2 * (unsigned __int8)v20 + (((unsigned __int64)(unsigned int)a2[1] >> *(_BYTE *)a2) & 1));
        }
        while ( (v20 & 0x80u) == 0 );
        v21 = 34LL * j + 78 + k++;
      }
      if ( a2[11] )
        return 0;
      v22 = j++;
      a1[v22 + 496] = v17;
    }
  }
  if ( a1[7] )
  {
    v23 = 0;
    if ( v11 > 0 )
    {
      do
      {
        if ( !*a2 )
          FillBitCache(a2, 1u);
        --*a2;
        v24 = aBookPsIccFreqDecode;
        v25 = ((unsigned int)a2[1] >> *a2) & 1;
        if ( v25 )
          v24 = aBookPsIccTimeDecode;
        for ( m = 0; m < dword_1800959F0[a1[487]]; a1[v28] = v27 + 64 )
        {
          LOBYTE(v27) = 0;
          do
          {
            if ( !*a2 )
              FillBitCache(a2, 1u);
            --*a2;
            v27 = *((char *)v24
                  + 2 * (unsigned __int8)v27
                  + (((unsigned __int64)(unsigned int)a2[1] >> *(_BYTE *)a2) & 1));
          }
          while ( (v27 & 0x80u) == 0 );
          v28 = 34LL * v23 + 282 + m++;
        }
        if ( a2[11] )
          return 0;
        v29 = v23++;
        a1[v29 + 501] = v25;
      }
      while ( v23 < a1[489] );
    }
  }
  if ( a1[8] )
  {
    if ( (unsigned int)*a2 < 4 )
      FillBitCache(a2, 4u);
    *a2 -= 4;
    v30 = *a2;
    v31 = ((unsigned int)a2[1] >> *a2) & 0xF;
    if ( v31 == 15 )
    {
      if ( v30 < 8 )
        FillBitCache(a2, 8u);
      v30 = *a2 - 8;
      v31 = (unsigned __int8)((unsigned int)a2[1] >> (*(_BYTE *)a2 - 8)) + 15;
      *a2 = v30;
    }
    if ( v31 )
    {
      v32 = 0;
      do
      {
        if ( v30 < 8 )
          FillBitCache(a2, 8u);
        *a2 -= 8;
        ++v32;
        v30 = *a2;
      }
      while ( v32 < v31 );
    }
  }
  a1[5] = 1;
  return (unsigned int)(v6 + 8 * (a2[4] - a2[2]) - *a2);
}

```

## disassembly

```asm
0x18003ffc0  mov     [rsp+arg_8], rbx
0x18003ffc5  push    rbp
0x18003ffc6  push    rsi
0x18003ffc7  push    rdi
0x18003ffc8  push    r12
0x18003ffca  push    r13
0x18003ffcc  push    r14
0x18003ffce  push    r15
0x18003ffd0  sub     rsp, 20h
0x18003ffd4  mov     esi, r8d
0x18003ffd7  mov     rbx, rdx
0x18003ffda  mov     r14, rcx
0x18003ffdd  test    rcx, rcx
0x18003ffe0  jz      loc_18004051B
0x18003ffe6  test    rdx, rdx
0x18003ffe9  jnz     short loc_18003FFF0
0x18003ffeb  xor     r15d, r15d
0x18003ffee  jmp     short loc_18003FFFC
0x18003fff0  mov     ecx, [rdx+8]
0x18003fff3  sub     ecx, [rdx+10h]
0x18003fff6  mov     eax, [rdx]
0x18003fff8  lea     r15d, [rax+rcx*8]
0x18003fffc  cmp     dword ptr [rdx], 1
0x18003ffff  mov     [rsp+58h+arg_0], r15d
0x180040004  jnb     short loc_180040013
0x180040006  mov     edx, 1
0x18004000b  mov     rcx, rbx
0x18004000e  call    FillBitCache
0x180040013  dec     dword ptr [rbx]
0x180040015  mov     edx, [rbx]
0x180040017  mov     ecx, edx
0x180040019  mov     eax, [rbx+4]
0x18004001c  shr     eax, cl
0x18004001e  test    al, 1
0x180040020  jz      loc_18004010C
0x180040026  cmp     edx, 1
0x180040029  jnb     short loc_180040038
0x18004002b  mov     edx, 1
0x180040030  mov     rcx, rbx
0x180040033  call    FillBitCache
0x180040038  dec     dword ptr [rbx]
0x18004003a  mov     eax, [rbx+4]
0x18004003d  mov     ecx, [rbx]
0x18004003f  shr     eax, cl
0x180040041  and     eax, 1
0x180040044  mov     [r14+18h], eax
0x180040048  jz      short loc_180040091
0x18004004a  cmp     dword ptr [rbx], 3
0x18004004d  jnb     short loc_18004005C
0x18004004f  mov     edx, 3
0x180040054  mov     rcx, rbx
0x180040057  call    FillBitCache
0x18004005c  add     dword ptr [rbx], 0FFFFFFFDh
0x18004005f  mov     eax, [rbx+4]
0x180040062  mov     ecx, [rbx]
0x180040064  shr     eax, cl
0x180040066  and     eax, 7
0x180040069  mov     [r14+798h], eax
0x180040070  cmp     eax, 2
0x180040073  jbe     short loc_180040089
0x180040075  add     eax, 0FFFFFFFDh
0x180040078  mov     dword ptr [r14+24h], 1
0x180040080  mov     [r14+798h], eax
0x180040087  jmp     short loc_180040091
0x180040089  mov     dword ptr [r14+24h], 0
0x180040091  cmp     dword ptr [rbx], 1
0x180040094  jnb     short loc_1800400A3
0x180040096  mov     edx, 1
0x18004009b  mov     rcx, rbx
0x18004009e  call    FillBitCache
0x1800400a3  dec     dword ptr [rbx]
0x1800400a5  mov     eax, [rbx+4]
0x1800400a8  mov     ecx, [rbx]
0x1800400aa  shr     eax, cl
0x1800400ac  and     eax, 1
0x1800400af  mov     [r14+1Ch], eax
0x1800400b3  jz      short loc_1800400EA
0x1800400b5  cmp     dword ptr [rbx], 3
0x1800400b8  jnb     short loc_1800400C7
0x1800400ba  mov     edx, 3
0x1800400bf  mov     rcx, rbx
0x1800400c2  call    FillBitCache
0x1800400c7  add     dword ptr [rbx], 0FFFFFFFDh
0x1800400ca  mov     eax, [rbx+4]
0x1800400cd  mov     ecx, [rbx]
0x1800400cf  shr     eax, cl
0x1800400d1  and     eax, 7
0x1800400d4  mov     [r14+79Ch], eax
0x1800400db  cmp     eax, 2
0x1800400de  jbe     short loc_1800400EA
0x1800400e0  add     eax, 0FFFFFFFDh
0x1800400e3  mov     [r14+79Ch], eax
0x1800400ea  cmp     dword ptr [rbx], 1
0x1800400ed  jnb     short loc_1800400FC
0x1800400ef  mov     edx, 1
0x1800400f4  mov     rcx, rbx
0x1800400f7  call    FillBitCache
0x1800400fc  dec     dword ptr [rbx]
0x1800400fe  mov     eax, [rbx+4]
0x180040101  mov     ecx, [rbx]
0x180040103  shr     eax, cl
0x180040105  and     eax, 1
0x180040108  mov     [r14+20h], eax
0x18004010c  cmp     dword ptr [rbx], 1
0x18004010f  jnb     short loc_18004011E
0x180040111  mov     edx, 1
0x180040116  mov     rcx, rbx
0x180040119  call    FillBitCache
0x18004011e  dec     dword ptr [rbx]
0x180040120  lea     rdi, __ImageBase
0x180040127  mov     eax, [rbx+4]
0x18004012a  mov     ecx, [rbx]
0x18004012c  shr     eax, cl
0x18004012e  and     eax, 1
0x180040131  mov     [r14+7A0h], eax
0x180040138  mov     eax, [rbx]
0x18004013a  jnz     short loc_18004016D
0x18004013c  cmp     eax, 2
0x18004013f  jnb     short loc_18004014E
0x180040141  mov     edx, 2
0x180040146  mov     rcx, rbx
0x180040149  call    FillBitCache
0x18004014e  add     dword ptr [rbx], 0FFFFFFFEh
0x180040151  movzx   ecx, byte ptr [rbx]
0x180040154  mov     eax, [rbx+4]
0x180040157  shr     rax, cl
0x18004015a  and     eax, 3
0x18004015d  mov     ecx, ds:rva dword_1800959E0[rdi+rax*4]
0x180040164  mov     [r14+7A4h], ecx
0x18004016b  jmp     short loc_1800401E5
0x18004016d  cmp     eax, 2
0x180040170  jnb     short loc_18004017F
0x180040172  mov     edx, 2
0x180040177  mov     rcx, rbx
0x18004017a  call    FillBitCache
0x18004017f  add     dword ptr [rbx], 0FFFFFFFEh
0x180040182  mov     edi, 1
0x180040187  mov     ecx, [rbx]
0x180040189  mov     eax, [rbx+4]
0x18004018c  shr     eax, cl
0x18004018e  and     eax, 3
0x180040191  lea     ecx, [rax+1]
0x180040194  lea     eax, [rcx+1]
0x180040197  mov     [r14+7A4h], ecx
0x18004019e  cmp     eax, edi
0x1800401a0  jbe     short loc_1800401DE
0x1800401a2  cmp     dword ptr [rbx], 5
0x1800401a5  jnb     short loc_1800401B4
0x1800401a7  mov     edx, 5
0x1800401ac  mov     rcx, rbx
0x1800401af  call    FillBitCache
0x1800401b4  add     dword ptr [rbx], 0FFFFFFFBh
0x1800401b7  mov     ecx, [rbx]
0x1800401b9  mov     edx, [rbx+4]
0x1800401bc  shr     edx, cl
0x1800401be  movsxd  rax, edi
0x1800401c1  and     edx, 1Fh
0x1800401c4  inc     edx
0x1800401c6  inc     edi
0x1800401c8  mov     [r14+rax*4+7A8h], edx
0x1800401d0  mov     ecx, [r14+7A4h]
0x1800401d7  lea     eax, [rcx+1]
0x1800401da  cmp     edi, eax
0x1800401dc  jl      short loc_1800401A2
0x1800401de  lea     rdi, __ImageBase
0x1800401e5  cmp     dword ptr [r14+798h], 2
0x1800401ed  jg      loc_1800404C4
0x1800401f3  cmp     dword ptr [r14+79Ch], 2
0x1800401fb  jg      loc_1800404C4
0x180040201  cmp     dword ptr [r14+18h], 0
0x180040206  jz      loc_180040335
0x18004020c  xor     r13d, r13d
0x18004020f  test    ecx, ecx
0x180040211  jle     loc_180040335
0x180040217  lea     r8, aBookPsIidFreqDecode
0x18004021e  lea     rdx, aBookPsIidTimeDecode
0x180040225  cmp     dword ptr [rbx], 1
0x180040228  jnb     short loc_180040245
0x18004022a  mov     edx, 1
0x18004022f  mov     rcx, rbx
0x180040232  call    FillBitCache
0x180040237  lea     rdx, aBookPsIidTimeDecode
0x18004023e  lea     r8, aBookPsIidFreqDecode
0x180040245  dec     dword ptr [rbx]
0x180040247  mov     r12d, [rbx+4]
0x18004024b  mov     ecx, [rbx]
0x18004024d  mov     eax, [r14+24h]
0x180040251  shr     r12d, cl
0x180040254  and     r12d, 1
0x180040258  mov     [rsp+58h+arg_18], r12d
0x18004025d  jnz     short loc_18004026E
0x18004025f  test    eax, eax
0x180040261  lea     rsi, aBookPsIidFineFreqDecode
0x180040268  cmovz   rsi, r8
0x18004026c  jmp     short loc_18004027B
0x18004026e  test    eax, eax
0x180040270  lea     rsi, aBookPsIidFineTimeDecode
0x180040277  cmovz   rsi, rdx
0x18004027b  movsxd  rax, dword ptr [r14+798h]
0x180040282  xor     ebp, ebp
0x180040284  cmp     ds:rva dword_1800959F0[rdi+rax*4], ebp
0x18004028b  jle     short loc_1800402FF
0x18004028d  movsxd  rax, r13d
0x180040290  lea     r12, __ImageBase
0x180040297  imul    r15, rax, 22h ; '"'
0x18004029b  add     r15, 4Eh ; 'N'
0x18004029f  nop
0x1800402a0  xor     dil, dil
0x1800402a3  cmp     dword ptr [rbx], 1
0x1800402a6  jnb     short loc_1800402B5
0x1800402a8  mov     edx, 1
0x1800402ad  mov     rcx, rbx
0x1800402b0  call    FillBitCache
0x1800402b5  dec     dword ptr [rbx]
0x1800402b7  movzx   ecx, byte ptr [rbx]
0x1800402ba  mov     eax, [rbx+4]
0x1800402bd  shr     rax, cl
0x1800402c0  and     eax, 1
0x1800402c3  movzx   ecx, dil
0x1800402c7  add     rax, rsi
0x1800402ca  movsx   edi, byte ptr [rax+rcx*2]
0x1800402ce  test    dil, dil
0x1800402d1  jns     short loc_1800402A3
0x1800402d3  movsxd  rax, ebp
0x1800402d6  lea     ecx, [rdi+40h]
0x1800402d9  add     rax, r15
0x1800402dc  inc     ebp
0x1800402de  mov     [r14+rax*4], ecx
0x1800402e2  movsxd  rax, dword ptr [r14+798h]
0x1800402e9  cmp     ebp, ds:rva dword_1800959F0[r12+rax*4]
0x1800402f1  jl      short loc_1800402A0
0x1800402f3  mov     r12d, [rsp+58h+arg_18]
0x1800402f8  lea     rdi, __ImageBase
0x1800402ff  cmp     dword ptr [rbx+2Ch], 0
0x180040303  jnz     loc_18004051B
0x180040309  movsxd  rax, r13d
0x18004030c  lea     rdx, aBookPsIidTimeDecode
0x180040313  inc     r13d
0x180040316  lea     r8, aBookPsIidFreqDecode
0x18004031d  mov     [r14+rax*4+7C0h], r12d
0x180040325  mov     ecx, [r14+7A4h]
0x18004032c  cmp     r13d, ecx
0x18004032f  jl      loc_180040225
0x180040335  cmp     dword ptr [r14+1Ch], 0
0x18004033a  jz      loc_18004043C
0x180040340  xor     r12d, r12d
0x180040343  test    ecx, ecx
0x180040345  jle     loc_18004043C
0x18004034b  lea     rdi, aBookPsIccTimeDecode
0x180040352  lea     r15, __ImageBase
0x180040359  nop     dword ptr [rax+00000000h]
0x180040360  cmp     dword ptr [rbx], 1
0x180040363  jnb     short loc_180040372
0x180040365  mov     edx, 1
0x18004036a  mov     rcx, rbx
0x18004036d  call    FillBitCache
0x180040372  dec     dword ptr [rbx]
0x180040374  lea     rsi, aBookPsIccFreqDecode
0x18004037b  mov     r13d, [rbx+4]
0x18004037f  mov     ecx, [rbx]
0x180040381  movsxd  rax, dword ptr [r14+79Ch]
0x180040388  shr     r13d, cl
0x18004038b  and     r13d, 1
0x18004038f  cmovnz  rsi, rdi
0x180040393  xor     ebp, ebp
0x180040395  cmp     ds:rva dword_1800959F0[r15+rax*4], ebp
0x18004039d  jle     short loc_180040417
0x18004039f  movsxd  rax, r12d
0x1800403a2  imul    r15, rax, 22h ; '"'
0x1800403a6  add     r15, 11Ah
0x1800403ad  nop     dword ptr [rax]
0x1800403b0  xor     dil, dil
0x1800403b3  cmp     dword ptr [rbx], 1
0x1800403b6  jnb     short loc_1800403C5
0x1800403b8  mov     edx, 1
0x1800403bd  mov     rcx, rbx
0x1800403c0  call    FillBitCache
0x1800403c5  dec     dword ptr [rbx]
0x1800403c7  movzx   ecx, byte ptr [rbx]
0x1800403ca  mov     eax, [rbx+4]
0x1800403cd  shr     rax, cl
0x1800403d0  and     eax, 1
0x1800403d3  movzx   ecx, dil
0x1800403d7  add     rax, rsi
0x1800403da  movsx   edi, byte ptr [rax+rcx*2]
0x1800403de  test    dil, dil
0x1800403e1  jns     short loc_1800403B3
0x1800403e3  movsxd  rax, ebp
0x1800403e6  lea     ecx, [rdi+40h]
0x1800403e9  add     rax, r15
0x1800403ec  inc     ebp
0x1800403ee  mov     [r14+rax*4], ecx
0x1800403f2  lea     rcx, __ImageBase
0x1800403f9  movsxd  rax, dword ptr [r14+79Ch]
0x180040400  cmp     ebp, ds:rva dword_1800959F0[rcx+rax*4]
0x180040407  jl      short loc_1800403B0
0x180040409  lea     rdi, aBookPsIccTimeDecode
0x180040410  lea     r15, __ImageBase
0x180040417  cmp     dword ptr [rbx+2Ch], 0
0x18004041b  jnz     loc_18004051B
  ... truncated ...
```
