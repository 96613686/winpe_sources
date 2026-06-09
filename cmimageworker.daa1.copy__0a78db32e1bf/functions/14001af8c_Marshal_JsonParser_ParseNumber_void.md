# Marshal::JsonParser::ParseNumber(void)

- ea: `0x14001af8c`
- end: `0x14001b37d`
- name: `?ParseNumber@JsonParser@Marshal@@QEAA?AUNumber@12@XZ`
- size: `1009`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14001e274`

## callees

- `0x140002d4e`
- `0x140014138`
- `0x14001af8c`
- `0x14002e8d8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstod` at `0x14001b23f`
- `api-ms-win-crt-private-l1-1-0!_o_wcstod` at `0x14001b23f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14001b216`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14001b216`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x14001b274`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x14001b274`
- `msvcp_win!?_Xinvalid_argument@std@@YAXPEBD@Z` at `0x14001b25c`
- `msvcp_win!?_Xinvalid_argument@std@@YAXPEBD@Z` at `0x14001b25c`

## pseudocode

```c
__int64 __fastcall Marshal::JsonParser::ParseNumber(_QWORD *a1, __int64 a2)
{
  __int64 v2; // r12
  unsigned __int64 v4; // r10
  unsigned __int64 v5; // r8
  __int64 v6; // rdx
  int v7; // ecx
  char v8; // si
  __int64 v9; // rdi
  __int64 v10; // r9
  char v11; // bl
  unsigned __int64 v12; // r11
  __int64 v13; // rdx
  __int64 v14; // rdi
  int v15; // eax
  unsigned int v16; // ecx
  void **v17; // rsi
  unsigned __int64 v18; // rax
  const void *v19; // r9
  unsigned __int64 v20; // rdx
  char *v21; // r12
  __int64 v22; // rbx
  _DWORD *v23; // rax
  _DWORD *v24; // rbx
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // r9
  unsigned __int64 v28; // r8
  unsigned __int64 v29; // rax
  unsigned __int64 v30; // rdx
  bool v31; // cf
  int v33; // [rsp+20h] [rbp-48h] BYREF
  int v34; // [rsp+24h] [rbp-44h] BYREF
  int v35; // [rsp+28h] [rbp-40h] BYREF
  int v36; // [rsp+2Ch] [rbp-3Ch] BYREF
  int pExceptionObject; // [rsp+30h] [rbp-38h] BYREF
  __int64 v38; // [rsp+70h] [rbp+8h] BYREF
  __int64 v39; // [rsp+78h] [rbp+10h]

  v39 = a2;
  v2 = a2;
  v4 = a1[1];
  v5 = a1[2];
  v6 = 2 * v5;
  v38 = 2 * v5;
  if ( v5 >= v4 )
  {
    v7 = -1;
    v38 = 2 * v5;
    goto LABEL_8;
  }
  v7 = *(unsigned __int16 *)(*a1 + 2 * v5);
  if ( v7 != 45 )
  {
LABEL_8:
    v8 = 0;
    v10 = 1;
    v9 = 1;
    goto LABEL_9;
  }
  v8 = 1;
  if ( v5 + 1 >= v4 )
    v7 = -1;
  else
    v7 = *(unsigned __int16 *)(*a1 + v6 + 2);
  v9 = 2;
  v10 = 2;
LABEL_9:
  v11 = 0;
  if ( v7 == 48 )
  {
    v12 = 0;
    if ( v5 + v9 >= v4 )
      LODWORD(v13) = -1;
    else
      LODWORD(v13) = *(unsigned __int16 *)(*a1 + 2 * (v5 + v9));
  }
  else
  {
    if ( (unsigned int)(v7 - 49) > 8 )
    {
      pExceptionObject = 14;
      throw (Marshal::JsonParser::ParseException *)&pExceptionObject;
    }
    v9 = v10;
    v12 = v7 - 48;
    if ( v5 + v10 >= v4 )
      goto LABEL_46;
    v13 = *(unsigned __int16 *)(*a1 + 2 * (v5 + v10));
    if ( (unsigned int)v13 >= 0x30 )
    {
      while ( (unsigned int)v13 <= 0x39 )
      {
        if ( v12 > 0x1999999999999999LL || v12 == 0x1999999999999999LL && (unsigned int)(v13 - 48) > 5 )
          v11 = 1;
        v12 = v13 + 2 * (v12 + 4 * (v12 - 6));
        ++v9;
        if ( v5 + v9 >= v4 )
          goto LABEL_45;
        v13 = *(unsigned __int16 *)(*a1 + 2 * (v5 + v9));
        if ( (unsigned int)v13 < 0x30 )
          break;
      }
    }
  }
  if ( (_DWORD)v13 == 46 )
  {
    v14 = v9 + 1;
    if ( v14 + v5 >= v4 || (unsigned int)*(unsigned __int16 *)(*a1 + 2 * (v14 + v5)) - 48 > 9 )
    {
      v33 = 14;
      throw (Marshal::JsonParser::ParseException *)&v33;
    }
    v11 = 1;
    v9 = v14 + 1;
    if ( v5 + v9 >= v4 )
      goto LABEL_45;
    LODWORD(v13) = *(unsigned __int16 *)(*a1 + 2 * (v5 + v9));
    if ( (unsigned int)v13 >= 0x30 )
    {
      while ( (unsigned int)v13 <= 0x39 )
      {
        ++v9;
        if ( v5 + v9 >= v4 )
          goto LABEL_45;
        LODWORD(v13) = *(unsigned __int16 *)(*a1 + 2 * (v5 + v9));
        if ( (unsigned int)v13 < 0x30 )
          goto LABEL_33;
      }
    }
  }
  if ( (_DWORD)v13 == 101 )
    goto LABEL_34;
LABEL_33:
  if ( (_DWORD)v13 == 69 )
  {
LABEL_34:
    if ( ++v9 + v5 >= v4 )
      goto LABEL_85;
    v15 = *(unsigned __int16 *)(*a1 + 2 * (v9 + v5));
    if ( v15 == 43 || v15 == 45 )
    {
      if ( ++v9 + v5 >= v4 )
        v15 = -1;
      else
        v15 = *(unsigned __int16 *)(*a1 + 2 * (v9 + v5));
    }
    if ( (unsigned int)(v15 - 48) > 9 )
    {
LABEL_85:
      v34 = 14;
      throw (Marshal::JsonParser::ParseException *)&v34;
    }
    v11 = 1;
    do
    {
      ++v9;
      if ( v5 + v9 >= v4 )
        break;
      v16 = *(unsigned __int16 *)(*a1 + 2 * (v5 + v9));
      if ( v16 < 0x30 )
        break;
    }
    while ( v16 <= 0x39 );
  }
LABEL_45:
  v6 = v38;
LABEL_46:
  if ( v8 && v12 > 0x8000000000000000uLL )
    v11 = 1;
  *(_OWORD *)v2 = 0;
  if ( v11 )
  {
    v17 = (void **)(a1 + 8);
    v18 = v5 + v9;
    if ( v4 < v5 + v9 )
      v18 = v4;
    v19 = (const void *)(*a1 + v6);
    v20 = (__int64)(2 * v18 - v6) >> 1;
    if ( v20 > a1[11] )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(a1 + 8);
    }
    else
    {
      v21 = (char *)(a1 + 8);
      if ( a1[11] > 7u )
        v21 = (char *)*v17;
      a1[10] = v20;
      v22 = 2 * v20;
      memmove_0(v21, v19, 2 * v20);
      *(_WORD *)&v21[v22] = 0;
      v2 = v39;
    }
    *(_DWORD *)(v2 + 8) = 2;
    v23 = (_DWORD *)_o__errno();
    v24 = v23;
    if ( a1[11] > 7u )
      v17 = (void **)*v17;
    v38 = 0;
    *v23 = 0;
    _o_wcstod(v17, &v38);
    try
    {
      v25 = v38;
      if ( v17 == (void **)v38 )
        std::_Xinvalid_argument("invalid stod argument");
      if ( *v24 == 34 )
        std::_Xout_of_range("stod argument out of range");
      v26 = (v25 - (__int64)v17) >> 1;
      *(_QWORD *)v2 = 0;
    }
    catch ( std::exception )
    {
      v36 = 14;
      throw (Marshal::JsonParser::ParseException *)&v36;
    }
    if ( v26 != a1[10] )
    {
      v35 = 14;
      throw (Marshal::JsonParser::ParseException *)&v35;
    }
  }
  else
  {
    if ( v8 )
    {
      *(_DWORD *)(v2 + 8) = 1;
      v12 = -(__int64)v12;
    }
    *(_QWORD *)v2 = v12;
  }
  v27 = a1[2];
  v28 = a1[1];
  v29 = v28;
  if ( v28 >= v27 + v9 )
    v29 = v27 + v9;
  a1[3] = v29;
  while ( 1 )
  {
    v30 = v27 + v9;
    v31 = v28 < v27 + v9;
    if ( v28 <= v27 + v9 )
      break;
    if ( *(_WORD *)(*a1 + 2 * v30) != 9
      && *(_WORD *)(*a1 + 2 * v30) != 10
      && *(_WORD *)(*a1 + 2 * v30) != 13
      && *(_WORD *)(*a1 + 2 * v30) != 32 )
    {
      v31 = v28 < v30;
      break;
    }
    ++v9;
  }
  if ( v31 )
    v30 = v28;
  a1[2] = v30;
  return v2;
}

```

## disassembly

```asm
0x14001af8c  mov     [rsp+arg_10], rbx
0x14001af91  mov     [rsp+arg_18], rsi
0x14001af96  mov     [rsp+arg_8], rdx
0x14001af9b  push    rdi
0x14001af9c  push    r12
0x14001af9e  push    r13
0x14001afa0  push    r14
0x14001afa2  push    r15
0x14001afa4  sub     rsp, 40h
0x14001afa8  mov     r12, rdx
0x14001afab  mov     r14, rcx
0x14001afae  mov     r10, [rcx+8]
0x14001afb2  mov     r8, [rcx+10h]
0x14001afb6  lea     rdx, [r8+r8]
0x14001afba  mov     [rsp+68h+arg_0], rdx
0x14001afbf  cmp     r8, r10
0x14001afc2  jnb     short loc_14001AFFA
0x14001afc4  mov     rax, [rcx]
0x14001afc7  movzx   ecx, word ptr [rax+rdx]
0x14001afcb  cmp     ecx, 2Dh ; '-'
0x14001afce  jnz     short loc_14001B002
0x14001afd0  lea     r15d, [rcx-2Ch]
0x14001afd4  mov     sil, r15b
0x14001afd7  lea     rax, [r8+1]
0x14001afdb  cmp     rax, r10
0x14001afde  jnb     short loc_14001AFEA
0x14001afe0  mov     rax, [r14]
0x14001afe3  movzx   ecx, word ptr [rax+rdx+2]
0x14001afe8  jmp     short loc_14001AFED
0x14001afea  or      ecx, 0FFFFFFFFh
0x14001afed  mov     edi, 2
0x14001aff2  mov     r9d, edi
0x14001aff5  xor     r13d, r13d
0x14001aff8  jmp     short loc_14001B012
0x14001affa  or      ecx, 0FFFFFFFFh
0x14001affd  mov     [rsp+68h+arg_0], rdx
0x14001b002  xor     r13d, r13d
0x14001b005  mov     sil, r13b
0x14001b008  lea     r15d, [r13+1]
0x14001b00c  mov     r9d, r15d
0x14001b00f  mov     edi, r15d
0x14001b012  mov     bl, r13b
0x14001b015  cmp     ecx, 30h ; '0'
0x14001b018  jnz     short loc_14001B034
0x14001b01a  mov     r11, r13
0x14001b01d  lea     rcx, [r8+rdi]
0x14001b021  cmp     rcx, r10
0x14001b024  jnb     short loc_14001B02F
0x14001b026  mov     rax, [r14]
0x14001b029  movzx   edx, word ptr [rax+rcx*2]
0x14001b02d  jmp     short loc_14001B0AB
0x14001b02f  or      edx, 0FFFFFFFFh
0x14001b032  jmp     short loc_14001B0AB
0x14001b034  lea     eax, [rcx-31h]
0x14001b037  cmp     eax, 8
0x14001b03a  ja      loc_14001B315
0x14001b040  mov     rdi, r9
0x14001b043  lea     eax, [rcx-30h]
0x14001b046  movsxd  r11, eax
0x14001b049  lea     rcx, [r8+r9]
0x14001b04d  cmp     rcx, r10
0x14001b050  jnb     loc_14001B184
0x14001b056  mov     rax, [r14]
0x14001b059  movzx   edx, word ptr [rax+rcx*2]
0x14001b05d  cmp     edx, 30h ; '0'
0x14001b060  jb      short loc_14001B0AB
0x14001b062  mov     r9, 1999999999999999h
0x14001b06c  cmp     edx, 39h ; '9'
0x14001b06f  ja      short loc_14001B0AB
0x14001b071  cmp     r11, r9
0x14001b074  ja      short loc_14001B080
0x14001b076  jnz     short loc_14001B083
0x14001b078  lea     eax, [rdx-30h]
0x14001b07b  cmp     eax, 5
0x14001b07e  jbe     short loc_14001B083
0x14001b080  mov     bl, r15b
0x14001b083  lea     rcx, [r11-6]
0x14001b087  lea     rcx, [r11+rcx*4]
0x14001b08b  lea     r11, [rdx+rcx*2]
0x14001b08f  add     rdi, r15
0x14001b092  lea     rcx, [r8+rdi]
0x14001b096  cmp     rcx, r10
0x14001b099  jnb     loc_14001B17F
0x14001b09f  mov     rax, [r14]
0x14001b0a2  movzx   edx, word ptr [rax+rcx*2]
0x14001b0a6  cmp     edx, 30h ; '0'
0x14001b0a9  jnb     short loc_14001B06C
0x14001b0ab  cmp     edx, 2Eh ; '.'
0x14001b0ae  jnz     short loc_14001B10E
0x14001b0b0  inc     rdi
0x14001b0b3  lea     rcx, [rdi+r8]
0x14001b0b7  cmp     rcx, r10
0x14001b0ba  jnb     loc_14001B32F
0x14001b0c0  mov     rax, [r14]
0x14001b0c3  movzx   ecx, word ptr [rax+rcx*2]
0x14001b0c7  sub     ecx, 30h ; '0'
0x14001b0ca  cmp     ecx, 9
0x14001b0cd  ja      loc_14001B32F
0x14001b0d3  mov     bl, r15b
0x14001b0d6  add     rdi, r15
0x14001b0d9  lea     rcx, [r8+rdi]
0x14001b0dd  cmp     rcx, r10
0x14001b0e0  jnb     loc_14001B17F
0x14001b0e6  movzx   edx, word ptr [rax+rcx*2]
0x14001b0ea  cmp     edx, 30h ; '0'
0x14001b0ed  jb      short loc_14001B10E
0x14001b0ef  cmp     edx, 39h ; '9'
0x14001b0f2  ja      short loc_14001B10E
0x14001b0f4  add     rdi, r15
0x14001b0f7  lea     rcx, [r8+rdi]
0x14001b0fb  cmp     rcx, r10
0x14001b0fe  jnb     short loc_14001B17F
0x14001b100  mov     rax, [r14]
0x14001b103  movzx   edx, word ptr [rax+rcx*2]
0x14001b107  cmp     edx, 30h ; '0'
0x14001b10a  jnb     short loc_14001B0EF
0x14001b10c  jmp     short loc_14001B113
0x14001b10e  cmp     edx, 65h ; 'e'
0x14001b111  jz      short loc_14001B118
0x14001b113  cmp     edx, 45h ; 'E'
0x14001b116  jnz     short loc_14001B17F
0x14001b118  inc     rdi
0x14001b11b  lea     rcx, [rdi+r8]
0x14001b11f  cmp     rcx, r10
0x14001b122  jnb     loc_14001B349
0x14001b128  mov     rax, [r14]
0x14001b12b  movzx   eax, word ptr [rax+rcx*2]
0x14001b12f  cmp     eax, 2Bh ; '+'
0x14001b132  jz      short loc_14001B139
0x14001b134  cmp     eax, 2Dh ; '-'
0x14001b137  jnz     short loc_14001B151
0x14001b139  add     rdi, r15
0x14001b13c  lea     rcx, [rdi+r8]
0x14001b140  cmp     rcx, r10
0x14001b143  jnb     short loc_14001B14E
0x14001b145  mov     rax, [r14]
0x14001b148  movzx   eax, word ptr [rax+rcx*2]
0x14001b14c  jmp     short loc_14001B151
0x14001b14e  or      eax, 0FFFFFFFFh
0x14001b151  add     eax, 0FFFFFFD0h
0x14001b154  cmp     eax, 9
0x14001b157  ja      loc_14001B349
0x14001b15d  mov     bl, r15b
0x14001b160  jmp     short loc_14001B167
0x14001b162  cmp     ecx, 39h ; '9'
0x14001b165  ja      short loc_14001B17F
0x14001b167  add     rdi, r15
0x14001b16a  lea     rcx, [r8+rdi]
0x14001b16e  cmp     rcx, r10
0x14001b171  jnb     short loc_14001B17F
0x14001b173  mov     rax, [r14]
0x14001b176  movzx   ecx, word ptr [rax+rcx*2]
0x14001b17a  cmp     ecx, 30h ; '0'
0x14001b17d  jnb     short loc_14001B162
0x14001b17f  mov     rdx, [rsp+68h+arg_0]
0x14001b184  test    sil, sil
0x14001b187  jz      short loc_14001B19D
0x14001b189  movzx   ebx, bl
0x14001b18c  mov     rax, 8000000000000000h
0x14001b196  cmp     r11, rax
0x14001b199  cmova   ebx, r15d
0x14001b19d  xorps   xmm0, xmm0
0x14001b1a0  movups  xmmword ptr [r12], xmm0
0x14001b1a5  test    bl, bl
0x14001b1a7  jz      loc_14001B298
0x14001b1ad  lea     rsi, [r14+40h]
0x14001b1b1  mov     rcx, [r14]
0x14001b1b4  lea     rax, [r8+rdi]
0x14001b1b8  cmp     r10, rax
0x14001b1bb  cmovb   rax, r10
0x14001b1bf  lea     r9, [rcx+rdx]
0x14001b1c3  lea     rdx, [rax+rax]
0x14001b1c7  sub     rdx, r9
0x14001b1ca  add     rdx, rcx
0x14001b1cd  sar     rdx, 1
0x14001b1d0  cmp     rdx, [rsi+18h]
0x14001b1d4  ja      short loc_14001B205
0x14001b1d6  mov     r12, rsi
0x14001b1d9  cmp     qword ptr [rsi+18h], 7
0x14001b1de  jbe     short loc_14001B1E3
0x14001b1e0  mov     r12, [rsi]
0x14001b1e3  mov     [rsi+10h], rdx
0x14001b1e7  lea     rbx, [rdx+rdx]
0x14001b1eb  mov     r8, rbx; Size
0x14001b1ee  mov     rdx, r9; Src
0x14001b1f1  mov     rcx, r12; void *
0x14001b1f4  call    memmove_0
0x14001b1f9  mov     [rbx+r12], r13w
0x14001b1fe  mov     r12, [rsp+68h+arg_8]
0x14001b203  jmp     short loc_14001B20D
0x14001b205  mov     rcx, rsi
0x14001b208  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x14001b20d  mov     dword ptr [r12+8], 2
0x14001b216  call    cs:__imp__o__errno
0x14001b21d  nop     dword ptr [rax+rax+00h]
0x14001b222  mov     rbx, rax
0x14001b225  cmp     qword ptr [rsi+18h], 7
0x14001b22a  jbe     short loc_14001B22F
0x14001b22c  mov     rsi, [rsi]
0x14001b22f  mov     [rsp+68h+arg_0], r13
0x14001b234  mov     [rax], r13d
0x14001b237  lea     rdx, [rsp+68h+arg_0]
0x14001b23c  mov     rcx, rsi
0x14001b23f  call    cs:__imp__o_wcstod
0x14001b246  nop     dword ptr [rax+rax+00h]
0x14001b24b  mov     rax, [rsp+68h+arg_0]
0x14001b250  cmp     rsi, rax
0x14001b253  jnz     short loc_14001B268
0x14001b255  lea     rcx, aInvalidStodArg; "invalid stod argument"
0x14001b25c  call    cs:__imp_?_Xinvalid_argument@std@@YAXPEBD@Z; std::_Xinvalid_argument(char const *)
0x14001b263  nop     dword ptr [rax+rax+00h]
0x14001b268  cmp     dword ptr [rbx], 22h ; '"'
0x14001b26b  jnz     short loc_14001B280
0x14001b26d  lea     rcx, aStodArgumentOu; "stod argument out of range"
0x14001b274  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x14001b27b  nop     dword ptr [rax+rax+00h]
0x14001b280  sub     rax, rsi
0x14001b283  sar     rax, 1
0x14001b286  movsd   qword ptr [r12], xmm0
0x14001b28c  cmp     rax, [r14+50h]
0x14001b290  jnz     loc_14001B363
0x14001b296  jmp     short loc_14001B2A9
0x14001b298  test    sil, sil
0x14001b29b  jz      short loc_14001B2A5
0x14001b29d  mov     [r12+8], r15d
0x14001b2a2  neg     r11
0x14001b2a5  mov     [r12], r11
0x14001b2a9  mov     r9, [r14+10h]
0x14001b2ad  lea     rcx, [r9+rdi]
0x14001b2b1  mov     r8, [r14+8]
0x14001b2b5  mov     rax, r8
0x14001b2b8  cmp     r8, rcx
0x14001b2bb  cmovnb  rax, rcx
0x14001b2bf  mov     [r14+18h], rax
0x14001b2c3  lea     rdx, [r9+rdi]
0x14001b2c7  cmp     r8, rdx
0x14001b2ca  jbe     short loc_14001B2EF
0x14001b2cc  mov     rax, [r14]
0x14001b2cf  movzx   ecx, word ptr [rax+rdx*2]
0x14001b2d3  sub     ecx, 9
0x14001b2d6  jz      short loc_14001B2E7
0x14001b2d8  sub     ecx, 1
0x14001b2db  jz      short loc_14001B2E7
0x14001b2dd  sub     ecx, 3
0x14001b2e0  jz      short loc_14001B2E7
0x14001b2e2  cmp     ecx, 13h
0x14001b2e5  jnz     short loc_14001B2EC
0x14001b2e7  add     rdi, r15
0x14001b2ea  jmp     short loc_14001B2C3
0x14001b2ec  cmp     r8, rdx
0x14001b2ef  cmovb   rdx, r8
0x14001b2f3  mov     [r14+10h], rdx
0x14001b2f7  mov     rax, r12
0x14001b2fa  lea     r11, [rsp+68h+var_28]
0x14001b2ff  mov     rbx, [r11+40h]
0x14001b303  mov     rsi, [r11+48h]
0x14001b307  mov     rsp, r11
0x14001b30a  pop     r15
0x14001b30c  pop     r14
0x14001b30e  pop     r13
0x14001b310  pop     r12
0x14001b312  pop     rdi
0x14001b313  retn
0x14001b315  mov     [rsp+68h+pExceptionObject], 0Eh
0x14001b31d  lea     rdx, _TI1?AUParseException@JsonParser@Marshal@@; pThrowInfo
0x14001b324  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x14001b329  call    _CxxThrowException_0
0x14001b32f  mov     [rsp+68h+var_48], 0Eh
0x14001b337  lea     rdx, _TI1?AUParseException@JsonParser@Marshal@@; pThrowInfo
0x14001b33e  lea     rcx, [rsp+68h+var_48]; pExceptionObject
0x14001b343  call    _CxxThrowException_0
0x14001b349  mov     [rsp+68h+var_44], 0Eh
0x14001b351  lea     rdx, _TI1?AUParseException@JsonParser@Marshal@@; pThrowInfo
0x14001b358  lea     rcx, [rsp+68h+var_44]; pExceptionObject
0x14001b35d  call    _CxxThrowException_0
0x14001b363  mov     [rsp+68h+var_40], 0Eh
0x14001b36b  lea     rdx, _TI1?AUParseException@JsonParser@Marshal@@; pThrowInfo
0x14001b372  lea     rcx, [rsp+68h+var_40]; pExceptionObject
0x14001b377  call    _CxxThrowException_0
```
