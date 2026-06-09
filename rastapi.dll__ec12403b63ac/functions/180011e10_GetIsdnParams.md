# GetIsdnParams

- ea: `0x180011e10`
- end: `0x180012338`
- name: `GetIsdnParams`
- size: `1320`
- prototype: `__int64 __fastcall(_BYTE *, __int64, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180011d5c`

## callees

- `0x180011e10`

## string_xrefs

- `0x180012113`: `EnableCompression`

## pseudocode

```c
__int64 __fastcall GetIsdnParams(_BYTE *a1, __int64 a2, unsigned int *a3)
{
  unsigned int v3; // esi
  _BYTE *v4; // r11
  __int64 v5; // rdi
  __int64 v7; // r9
  __int64 v9; // rdx
  _BYTE *v10; // r15
  __int64 v11; // r8
  _BYTE *v12; // rbp
  __int64 v13; // r10
  _BYTE *v14; // r12
  __int64 v15; // rax
  _BYTE *v16; // r13
  __int64 v17; // rcx
  unsigned int v18; // eax
  __int64 v20; // rbx
  __int64 v21; // rsi
  _BYTE *v22; // rcx
  __int64 v23; // rax
  const char *v24; // r9
  __int64 v25; // r8
  _BYTE *v26; // rdx
  _BYTE *v27; // rax
  __int64 v28; // rax
  __int64 v29; // rdx
  unsigned __int64 v30; // rdx
  __int64 v31; // rax
  _BYTE *v32; // r8
  _BYTE *v33; // rax
  const char *v34; // r10
  _BYTE *v35; // rcx
  __int64 v36; // r9
  __int64 v37; // r8
  _BYTE *v38; // rdx
  _BYTE *v39; // rax
  __int64 v40; // rax
  __int64 v41; // rdx
  unsigned __int64 v42; // rdx
  __int64 v43; // rax
  _BYTE *v44; // r8
  _BYTE *v45; // rax
  const char *v46; // r9
  _BYTE *v47; // rdx
  __int64 v48; // r8
  _BYTE *v49; // rcx
  __int64 v50; // rax
  _BYTE *v51; // rax
  __int64 v52; // rax
  __int64 v53; // rdx
  unsigned __int64 v54; // rdx
  __int64 v55; // rax
  _BYTE *v56; // r8
  _BYTE *v57; // rax
  const char *v58; // r10
  _BYTE *v59; // rcx
  __int64 v60; // r8
  __int64 v61; // rax
  _BYTE *v62; // rdx
  _BYTE *v63; // rax
  __int64 v64; // rax
  __int64 v65; // rdx
  unsigned __int64 v66; // rdx
  __int64 v67; // rax
  _BYTE *v68; // r8
  _BYTE *v69; // rax
  const char *v70; // r10
  _BYTE *v71; // rdx
  _BYTE *v72; // rcx
  __int64 v73; // r8
  __int64 v74; // rax
  _BYTE *v75; // rax
  __int64 v76; // rax
  __int64 v77; // rdx
  unsigned __int64 v78; // rdx
  __int64 v79; // rax
  _BYTE *v80; // r8
  _BYTE *v81; // rax
  const char *v82; // r8
  _BYTE *v83; // rdx
  _BYTE *v84; // rcx
  __int64 v85; // rax
  _BYTE *v86; // r8
  _BYTE *v87; // rax
  __int64 v88; // rax
  unsigned __int64 v89; // rdx
  _BYTE *v90; // rax
  _BYTE *v91; // [rsp+48h] [rbp+8h]

  v3 = *a3;
  v4 = a1 + 260;
  v5 = -1;
  v7 = -1;
  do
    ++v7;
  while ( v4[v7] );
  v9 = -1;
  v91 = a1 + 360;
  do
    ++v9;
  while ( a1[v9 + 360] );
  v10 = a1 + 460;
  v11 = -1;
  do
    ++v11;
  while ( v10[v11] );
  v12 = a1 + 560;
  v13 = -1;
  do
    ++v13;
  while ( v12[v13] );
  v14 = a1 + 660;
  v15 = -1;
  do
    ++v15;
  while ( v14[v15] );
  v16 = a1 + 760;
  v17 = -1;
  do
    ++v17;
  while ( v16[v17] );
  v18 = v17 + v7 + v9 + v11 + v13 + v15 + 351;
  *a3 = v18;
  if ( v18 > v3 )
    return 603;
  v20 = 2147483646;
  *(_DWORD *)a2 = 6;
  v21 = 32;
  v22 = (_BYTE *)(a2 + 344);
  v23 = 2147483646;
  v24 = "PhoneNumber";
  v25 = 32;
  v26 = (_BYTE *)(a2 + 8);
  do
  {
    if ( !v23 )
      break;
    if ( !*v24 )
      break;
    *v26++ = *v24++;
    --v23;
    --v25;
  }
  while ( v25 );
  v27 = v26 - 1;
  if ( v25 )
    v27 = v26;
  *v27 = 0;
  v28 = -1;
  *(_DWORD *)(a2 + 40) = 1;
  *(_BYTE *)(a2 + 44) = 0;
  do
    ++v28;
  while ( v4[v28] );
  *(_DWORD *)(a2 + 48) = v28;
  v29 = -1;
  *(_QWORD *)(a2 + 56) = v22;
  do
    ++v29;
  while ( v4[v29] );
  v30 = v29 + 1;
  if ( v30 )
  {
    if ( v30 <= 0x7FFFFFFF )
    {
      v31 = 2147483646;
      v32 = (_BYTE *)(a2 + 344);
      do
      {
        if ( !v31 )
          break;
        if ( !*v4 )
          break;
        *v32++ = *v4++;
        --v31;
        --v30;
      }
      while ( v30 );
      v33 = v32 - 1;
      if ( v30 )
        v33 = v32;
      *v33 = 0;
    }
    else
    {
      *v22 = 0;
    }
  }
  v34 = "LineType";
  v35 = &v22[*(_DWORD *)(a2 + 48) + 1];
  v36 = 2147483646;
  v37 = 32;
  v38 = (_BYTE *)(a2 + 64);
  do
  {
    if ( !v36 )
      break;
    if ( !*v34 )
      break;
    *v38++ = *v34++;
    --v36;
    --v37;
  }
  while ( v37 );
  v39 = v38 - 1;
  if ( v37 )
    v39 = v38;
  *v39 = 0;
  v40 = -1;
  *(_DWORD *)(a2 + 96) = 1;
  *(_BYTE *)(a2 + 100) = 0;
  do
    ++v40;
  while ( v10[v40] );
  *(_DWORD *)(a2 + 104) = v40;
  v41 = -1;
  *(_QWORD *)(a2 + 112) = v35;
  do
    ++v41;
  while ( v10[v41] );
  v42 = v41 + 1;
  if ( v42 )
  {
    if ( v42 <= 0x7FFFFFFF )
    {
      v43 = 2147483646;
      v44 = v35;
      do
      {
        if ( !v43 )
          break;
        if ( !*v10 )
          break;
        *v44++ = *v10++;
        --v43;
        --v42;
      }
      while ( v42 );
      v45 = v44 - 1;
      if ( v42 )
        v45 = v44;
      *v45 = 0;
    }
    else
    {
      *v35 = 0;
    }
  }
  v46 = "Fallback";
  v47 = (_BYTE *)(a2 + 120);
  v48 = 32;
  v49 = &v35[*(_DWORD *)(a2 + 104) + 1];
  v50 = 2147483646;
  do
  {
    if ( !v50 )
      break;
    if ( !*v46 )
      break;
    *v47++ = *v46++;
    --v50;
    --v48;
  }
  while ( v48 );
  v51 = v47 - 1;
  if ( v48 )
    v51 = v47;
  *v51 = 0;
  v52 = -1;
  *(_DWORD *)(a2 + 152) = 1;
  *(_BYTE *)(a2 + 156) = 0;
  do
    ++v52;
  while ( v12[v52] );
  *(_DWORD *)(a2 + 160) = v52;
  v53 = -1;
  *(_QWORD *)(a2 + 168) = v49;
  do
    ++v53;
  while ( v12[v53] );
  v54 = v53 + 1;
  if ( v54 )
  {
    if ( v54 <= 0x7FFFFFFF )
    {
      v55 = 2147483646;
      v56 = v49;
      do
      {
        if ( !v55 )
          break;
        if ( !*v12 )
          break;
        *v56++ = *v12++;
        --v55;
        --v54;
      }
      while ( v54 );
      v57 = v56 - 1;
      if ( v54 )
        v57 = v56;
      *v57 = 0;
    }
    else
    {
      *v49 = 0;
    }
  }
  v58 = "EnableCompression";
  v59 = &v49[*(_DWORD *)(a2 + 160) + 1];
  v60 = 32;
  v61 = 2147483646;
  v62 = (_BYTE *)(a2 + 176);
  do
  {
    if ( !v61 )
      break;
    if ( !*v58 )
      break;
    *v62++ = *v58++;
    --v61;
    --v60;
  }
  while ( v60 );
  v63 = v62 - 1;
  if ( v60 )
    v63 = v62;
  *v63 = 0;
  v64 = -1;
  *(_DWORD *)(a2 + 208) = 1;
  *(_BYTE *)(a2 + 212) = 0;
  do
    ++v64;
  while ( v14[v64] );
  *(_DWORD *)(a2 + 216) = v64;
  v65 = -1;
  *(_QWORD *)(a2 + 224) = v59;
  do
    ++v65;
  while ( v14[v65] );
  v66 = v65 + 1;
  if ( v66 )
  {
    if ( v66 <= 0x7FFFFFFF )
    {
      v67 = 2147483646;
      v68 = v59;
      do
      {
        if ( !v67 )
          break;
        if ( !*v14 )
          break;
        *v68++ = *v14++;
        --v67;
        --v66;
      }
      while ( v66 );
      v69 = v68 - 1;
      if ( v66 )
        v69 = v68;
      *v69 = 0;
    }
    else
    {
      *v59 = 0;
    }
  }
  v70 = "ChannelAggregation";
  v71 = (_BYTE *)(a2 + 232);
  v72 = &v59[*(_DWORD *)(a2 + 216) + 1];
  v73 = 32;
  v74 = 2147483646;
  do
  {
    if ( !v74 )
      break;
    if ( !*v70 )
      break;
    *v71++ = *v70++;
    --v74;
    --v73;
  }
  while ( v73 );
  v75 = v71 - 1;
  if ( v73 )
    v75 = v71;
  *v75 = 0;
  v76 = -1;
  *(_DWORD *)(a2 + 264) = 1;
  *(_BYTE *)(a2 + 268) = 0;
  do
    ++v76;
  while ( v16[v76] );
  *(_DWORD *)(a2 + 272) = v76;
  v77 = -1;
  *(_QWORD *)(a2 + 280) = v72;
  do
    ++v77;
  while ( v16[v77] );
  v78 = v77 + 1;
  if ( v78 )
  {
    if ( v78 <= 0x7FFFFFFF )
    {
      v79 = 2147483646;
      v80 = v72;
      do
      {
        if ( !v79 )
          break;
        if ( !*v16 )
          break;
        *v80++ = *v16++;
        --v79;
        --v78;
      }
      while ( v78 );
      v81 = v80 - 1;
      if ( v78 )
        v81 = v80;
      *v81 = 0;
    }
    else
    {
      *v72 = 0;
    }
  }
  v82 = "ConnectBps";
  v83 = (_BYTE *)(a2 + 288);
  v84 = &v72[*(_DWORD *)(a2 + 272) + 1];
  v85 = 2147483646;
  do
  {
    if ( !v85 )
      break;
    if ( !*v82 )
      break;
    *v83++ = *v82++;
    --v85;
    --v21;
  }
  while ( v21 );
  v86 = v91;
  v87 = v83 - 1;
  if ( v21 )
    v87 = v83;
  *v87 = 0;
  v88 = -1;
  *(_DWORD *)(a2 + 320) = 1;
  *(_BYTE *)(a2 + 324) = 0;
  do
    ++v88;
  while ( v91[v88] );
  *(_DWORD *)(a2 + 328) = v88;
  *(_QWORD *)(a2 + 336) = v84;
  do
    ++v5;
  while ( v91[v5] );
  v89 = v5 + 1;
  if ( v5 != -1 )
  {
    if ( v89 <= 0x7FFFFFFF )
    {
      do
      {
        if ( !v20 )
          break;
        if ( !*v86 )
          break;
        *v84++ = *v86++;
        --v20;
        --v89;
      }
      while ( v89 );
      v90 = v84 - 1;
      if ( v89 )
        v90 = v84;
      *v90 = 0;
    }
    else
    {
      *v84 = 0;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180011e10  push    rbx
0x180011e12  push    rbp
0x180011e13  push    rsi
0x180011e14  push    rdi
0x180011e15  push    r12
0x180011e17  push    r13
0x180011e19  push    r14
0x180011e1b  push    r15
0x180011e1d  mov     esi, [r8]
0x180011e20  lea     r11, [rcx+104h]
0x180011e27  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180011e2b  mov     rbx, r8
0x180011e2e  mov     r9, rdi
0x180011e31  xor     r13d, r13d
0x180011e34  mov     r14, rdx
0x180011e37  inc     r9
0x180011e3a  cmp     [r11+r9], r13b
0x180011e3e  jnz     short loc_180011E37
0x180011e40  lea     rax, [r11+64h]
0x180011e44  mov     rdx, rdi
0x180011e47  mov     [rsp+40h+arg_0], rax
0x180011e4c  inc     rdx
0x180011e4f  cmp     [rax+rdx], r13b
0x180011e53  jnz     short loc_180011E4C
0x180011e55  lea     r15, [rcx+1CCh]
0x180011e5c  mov     r8, rdi
0x180011e5f  inc     r8
0x180011e62  cmp     [r15+r8], r13b
0x180011e66  jnz     short loc_180011E5F
0x180011e68  lea     rbp, [rcx+230h]
0x180011e6f  mov     r10, rdi
0x180011e72  inc     r10
0x180011e75  cmp     [r10+rbp], r13b
0x180011e79  jnz     short loc_180011E72
0x180011e7b  lea     r12, [rcx+294h]
0x180011e82  mov     rax, rdi
0x180011e85  inc     rax
0x180011e88  cmp     [r12+rax], r13b
0x180011e8c  jnz     short loc_180011E85
0x180011e8e  lea     r13, [rcx+2F8h]
0x180011e95  mov     rcx, rdi
0x180011e98  inc     rcx
0x180011e9b  cmp     byte ptr [rcx+r13], 0
0x180011ea0  jnz     short loc_180011E98
0x180011ea2  add     eax, 15Fh
0x180011ea7  add     eax, r10d
0x180011eaa  add     eax, r8d
0x180011ead  add     eax, edx
0x180011eaf  add     eax, r9d
0x180011eb2  add     eax, ecx
0x180011eb4  mov     [rbx], eax
0x180011eb6  cmp     eax, esi
0x180011eb8  jbe     short loc_180011EC4
0x180011eba  mov     eax, 25Bh
0x180011ebf  jmp     loc_18001232B
0x180011ec4  mov     ebx, 7FFFFFFEh
0x180011ec9  mov     dword ptr [r14], 6
0x180011ed0  mov     esi, 20h ; ' '
0x180011ed5  lea     rcx, [r14+158h]
0x180011edc  mov     eax, ebx
0x180011ede  lea     r9, aPhonenumber; "PhoneNumber"
0x180011ee5  mov     r8d, esi
0x180011ee8  lea     rdx, [r14+8]
0x180011eec  test    rax, rax
0x180011eef  jz      short loc_180011F0B
0x180011ef1  mov     r10b, [r9]
0x180011ef4  test    r10b, r10b
0x180011ef7  jz      short loc_180011F0B
0x180011ef9  mov     [rdx], r10b
0x180011efc  inc     r9
0x180011eff  inc     rdx
0x180011f02  dec     rax
0x180011f05  sub     r8, 1
0x180011f09  jnz     short loc_180011EEC
0x180011f0b  test    r8, r8
0x180011f0e  lea     rax, [rdx-1]
0x180011f12  cmovnz  rax, rdx
0x180011f16  mov     byte ptr [rax], 0
0x180011f19  mov     rax, rdi
0x180011f1c  mov     dword ptr [r14+28h], 1
0x180011f24  mov     byte ptr [r14+2Ch], 0
0x180011f29  inc     rax
0x180011f2c  cmp     byte ptr [r11+rax], 0
0x180011f31  jnz     short loc_180011F29
0x180011f33  mov     [r14+30h], eax
0x180011f37  mov     rdx, rdi
0x180011f3a  mov     [r14+38h], rcx
0x180011f3e  inc     rdx
0x180011f41  cmp     byte ptr [r11+rdx], 0
0x180011f46  jnz     short loc_180011F3E
0x180011f48  add     rdx, 1
0x180011f4c  jz      short loc_180011F8F
0x180011f4e  cmp     rdx, 7FFFFFFFh
0x180011f55  jbe     short loc_180011F5C
0x180011f57  mov     byte ptr [rcx], 0
0x180011f5a  jmp     short loc_180011F8F
0x180011f5c  mov     rax, rbx
0x180011f5f  mov     r8, rcx
0x180011f62  test    rax, rax
0x180011f65  jz      short loc_180011F81
0x180011f67  mov     r9b, [r11]
0x180011f6a  test    r9b, r9b
0x180011f6d  jz      short loc_180011F81
0x180011f6f  mov     [r8], r9b
0x180011f72  inc     r11
0x180011f75  inc     r8
0x180011f78  dec     rax
0x180011f7b  sub     rdx, 1
0x180011f7f  jnz     short loc_180011F62
0x180011f81  test    rdx, rdx
0x180011f84  lea     rax, [r8-1]
0x180011f88  cmovnz  rax, r8
0x180011f8c  mov     byte ptr [rax], 0
0x180011f8f  mov     eax, [r14+30h]
0x180011f93  lea     r11, [r14+40h]
0x180011f97  inc     eax
0x180011f99  lea     r10, aLinetype; "LineType"
0x180011fa0  add     rcx, rax
0x180011fa3  mov     r9, rbx
0x180011fa6  xor     r14d, r14d
0x180011fa9  mov     r8, rsi
0x180011fac  mov     rdx, r11
0x180011faf  test    r9, r9
0x180011fb2  jz      short loc_180011FCC
0x180011fb4  mov     al, [r10]
0x180011fb7  test    al, al
0x180011fb9  jz      short loc_180011FCC
0x180011fbb  mov     [rdx], al
0x180011fbd  inc     r10
0x180011fc0  inc     rdx
0x180011fc3  dec     r9
0x180011fc6  sub     r8, 1
0x180011fca  jnz     short loc_180011FAF
0x180011fcc  test    r8, r8
0x180011fcf  lea     rax, [rdx-1]
0x180011fd3  cmovnz  rax, rdx
0x180011fd7  mov     [rax], r14b
0x180011fda  mov     rax, rdi
0x180011fdd  mov     dword ptr [r11+20h], 1
0x180011fe5  mov     [r11+24h], r14b
0x180011fe9  inc     rax
0x180011fec  cmp     [r15+rax], r14b
0x180011ff0  jnz     short loc_180011FE9
0x180011ff2  mov     [r11+28h], eax
0x180011ff6  mov     rdx, rdi
0x180011ff9  mov     [r11+30h], rcx
0x180011ffd  inc     rdx
0x180012000  cmp     [r15+rdx], r14b
0x180012004  jnz     short loc_180011FFD
0x180012006  add     rdx, 1
0x18001200a  jz      short loc_18001204D
0x18001200c  cmp     rdx, 7FFFFFFFh
0x180012013  jbe     short loc_18001201A
0x180012015  mov     [rcx], r14b
0x180012018  jmp     short loc_18001204D
0x18001201a  mov     rax, rbx
0x18001201d  mov     r8, rcx
0x180012020  test    rax, rax
0x180012023  jz      short loc_18001203F
0x180012025  mov     r9b, [r15]
0x180012028  test    r9b, r9b
0x18001202b  jz      short loc_18001203F
0x18001202d  mov     [r8], r9b
0x180012030  inc     r15
0x180012033  inc     r8
0x180012036  dec     rax
0x180012039  sub     rdx, 1
0x18001203d  jnz     short loc_180012020
0x18001203f  test    rdx, rdx
0x180012042  lea     rax, [r8-1]
0x180012046  cmovnz  rax, r8
0x18001204a  mov     [rax], r14b
0x18001204d  mov     eax, [r11+28h]
0x180012051  lea     r9, aFallback; "Fallback"
0x180012058  mov     r15d, 1
0x18001205e  lea     rdx, [r11+38h]
0x180012062  add     eax, r15d
0x180012065  mov     r8, rsi
0x180012068  add     rcx, rax
0x18001206b  mov     rax, rbx
0x18001206e  test    rax, rax
0x180012071  jz      short loc_18001208C
0x180012073  mov     r10b, [r9]
0x180012076  test    r10b, r10b
0x180012079  jz      short loc_18001208C
0x18001207b  mov     [rdx], r10b
0x18001207e  add     r9, r15
0x180012081  add     rdx, r15
0x180012084  sub     rax, r15
0x180012087  sub     r8, r15
0x18001208a  jnz     short loc_18001206E
0x18001208c  test    r8, r8
0x18001208f  lea     rax, [rdx-1]
0x180012093  cmovnz  rax, rdx
0x180012097  mov     [rax], r14b
0x18001209a  mov     rax, rdi
0x18001209d  mov     [r11+58h], r15d
0x1800120a1  mov     [r11+5Ch], r14b
0x1800120a5  inc     rax
0x1800120a8  cmp     [rax+rbp], r14b
0x1800120ac  jnz     short loc_1800120A5
0x1800120ae  mov     [r11+60h], eax
0x1800120b2  mov     rdx, rdi
0x1800120b5  mov     [r11+68h], rcx
0x1800120b9  inc     rdx
0x1800120bc  cmp     [rdx+rbp], r14b
0x1800120c0  jnz     short loc_1800120B9
0x1800120c2  add     rdx, r15
0x1800120c5  jz      short loc_180012108
0x1800120c7  cmp     rdx, 7FFFFFFFh
0x1800120ce  jbe     short loc_1800120D5
0x1800120d0  mov     [rcx], r14b
0x1800120d3  jmp     short loc_180012108
0x1800120d5  mov     rax, rbx
0x1800120d8  mov     r8, rcx
0x1800120db  test    rax, rax
0x1800120de  jz      short loc_1800120FA
0x1800120e0  mov     r9b, [rbp+0]
0x1800120e4  test    r9b, r9b
0x1800120e7  jz      short loc_1800120FA
0x1800120e9  mov     [r8], r9b
0x1800120ec  add     rbp, r15
0x1800120ef  add     r8, r15
0x1800120f2  sub     rax, r15
0x1800120f5  sub     rdx, r15
0x1800120f8  jnz     short loc_1800120DB
0x1800120fa  test    rdx, rdx
0x1800120fd  lea     rax, [r8-1]
0x180012101  cmovnz  rax, r8
0x180012105  mov     [rax], r14b
0x180012108  mov     eax, [r11+60h]
0x18001210c  lea     r9, [r11+70h]
0x180012110  add     eax, r15d
0x180012113  lea     r10, aEnablecompress; "EnableCompression"
0x18001211a  add     rcx, rax
0x18001211d  mov     r8, rsi
0x180012120  mov     rax, rbx
0x180012123  mov     rdx, r9
0x180012126  test    rax, rax
0x180012129  jz      short loc_180012144
0x18001212b  mov     r11b, [r10]
0x18001212e  test    r11b, r11b
0x180012131  jz      short loc_180012144
0x180012133  mov     [rdx], r11b
0x180012136  add     r10, r15
0x180012139  add     rdx, r15
0x18001213c  sub     rax, r15
0x18001213f  sub     r8, r15
0x180012142  jnz     short loc_180012126
0x180012144  test    r8, r8
0x180012147  lea     rax, [rdx-1]
0x18001214b  cmovnz  rax, rdx
0x18001214f  mov     [rax], r14b
0x180012152  mov     rax, rdi
0x180012155  mov     [r9+20h], r15d
0x180012159  mov     [r9+24h], r14b
0x18001215d  inc     rax
0x180012160  cmp     [r12+rax], r14b
0x180012164  jnz     short loc_18001215D
0x180012166  mov     [r9+28h], eax
0x18001216a  mov     rdx, rdi
0x18001216d  mov     [r9+30h], rcx
0x180012171  inc     rdx
0x180012174  cmp     [r12+rdx], r14b
0x180012178  jnz     short loc_180012171
0x18001217a  mov     ebp, 7FFFFFFFh
0x18001217f  add     rdx, r15
0x180012182  jz      short loc_1800121C1
0x180012184  cmp     rdx, rbp
0x180012187  jbe     short loc_18001218E
0x180012189  mov     [rcx], r14b
0x18001218c  jmp     short loc_1800121C1
0x18001218e  mov     rax, rbx
0x180012191  mov     r8, rcx
0x180012194  test    rax, rax
0x180012197  jz      short loc_1800121B3
0x180012199  mov     r10b, [r12]
0x18001219d  test    r10b, r10b
0x1800121a0  jz      short loc_1800121B3
0x1800121a2  mov     [r8], r10b
0x1800121a5  add     r12, r15
0x1800121a8  add     r8, r15
0x1800121ab  sub     rax, r15
0x1800121ae  sub     rdx, r15
0x1800121b1  jnz     short loc_180012194
0x1800121b3  test    rdx, rdx
0x1800121b6  lea     rax, [r8-1]
0x1800121ba  cmovnz  rax, r8
0x1800121be  mov     [rax], r14b
0x1800121c1  mov     eax, [r9+28h]
0x1800121c5  lea     r10, aChannelaggrega; "ChannelAggregation"
0x1800121cc  add     eax, r15d
0x1800121cf  lea     rdx, [r9+38h]
0x1800121d3  add     rcx, rax
0x1800121d6  mov     r8, rsi
0x1800121d9  mov     rax, rbx
0x1800121dc  test    rax, rax
0x1800121df  jz      short loc_1800121FA
0x1800121e1  mov     r11b, [r10]
0x1800121e4  test    r11b, r11b
  ... truncated ...
```
