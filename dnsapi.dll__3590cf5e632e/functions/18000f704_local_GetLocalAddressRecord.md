# local_GetLocalAddressRecord

- ea: `0x18000f704`
- end: `0x18000ffc0`
- name: `local_GetLocalAddressRecord`
- size: `2236`
- prototype: ``
- caller_count: `2`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x18002d30c`
- `0x18006fc70`

## callees

- `0x180005870`
- `0x18000598c`
- `0x18000d6d4`
- `0x18000f704`
- `0x1800112d0`
- `0x180027744`
- `0x18002b050`
- `0x18002f52c`
- `0x180035d40`
- `0x18005dee4`
- `0x18006649c`
- `0x18008b5f0`
- `0x18008bf98`
- `0x1800dbadc`
- `0x1800dbfe0`
- `0x1800ddfa8`
- `0x1800de650`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000f96f`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000f96f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000f852`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000f8ba`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000f90d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000f9fb`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000f852`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000f8ba`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000f90d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000f9fb`

## pseudocode

```c
__int64 __fastcall local_GetLocalAddressRecord(__int64 a1, unsigned __int16 a2, __int64 a3, __int64 a4, int a5)
{
  int v5; // esi
  __int64 v7; // r14
  __int64 v9; // rax
  const WCHAR *v10; // rbx
  int v11; // r12d
  int v12; // ecx
  void *v13; // r15
  __int64 v14; // rdi
  __int64 cchCount2; // r9
  __int64 v16; // r9
  __int64 v17; // r9
  wchar_t *v18; // rax
  const WCHAR *v19; // r15
  const WCHAR *v20; // rdx
  const WCHAR *v21; // rcx
  __int64 v22; // r9
  int v24; // ecx
  __int64 LocalAddrArray; // rax
  void *v26; // rdi
  __int64 v27; // rdi
  __int64 v28; // rdx
  __int64 v29; // rdx
  __int64 v30; // rdx
  __int64 v31; // rdi
  int v32; // r14d
  unsigned int i; // esi
  __int64 v34; // rdi
  __int64 v35; // rax
  void *v36; // rdi
  __int64 v37; // rdi
  __int64 ForwardRecord; // rax
  int lpString2; // [rsp+20h] [rbp-A1h]
  __int64 v41; // [rsp+38h] [rbp-89h]
  int v42; // [rsp+40h] [rbp-81h]
  __int64 AdapterByName; // [rsp+48h] [rbp-79h]
  WCHAR *v45; // [rsp+58h] [rbp-69h]
  __int128 v46; // [rsp+60h] [rbp-61h] BYREF
  __int128 v47; // [rsp+70h] [rbp-51h]
  int v48; // [rsp+80h] [rbp-41h]
  _BYTE v49[64]; // [rsp+90h] [rbp-31h] BYREF

  v5 = a2;
  v7 = a1;
  AdapterByName = a4;
  memset_0(v49, 0, sizeof(v49));
  v9 = *(_QWORD *)(v7 + 1024);
  v10 = *(const WCHAR **)(v7 + 240);
  v47 = 0;
  v41 = v9;
  v46 = 0;
  if ( SBYTE3(xmmword_1801119E0) < 0 )
  {
    WPP_SF_Sd(1055, 19, (unsigned int)WPP_f4ef6d0c0ed83ebd4dc80ffe2f825eb2_Traceguids, (_DWORD)v10, v5);
    v9 = v41;
  }
  v11 = 3;
  *(_DWORD *)(v7 + 524) = 0;
  *(_QWORD *)(v7 + 1016) = 0;
  if ( a5 )
    v11 = a5;
  if ( (_WORD)v5 == 1 )
  {
    v42 = 2;
  }
  else if ( (_WORD)v5 == 28 )
  {
    v42 = 23;
  }
  else
  {
    if ( v5 != 34 )
      return 9003;
    v42 = 22;
  }
  if ( a3 )
  {
    if ( !a4 )
    {
      AdapterByName = NetInfo_GetAdapterByName(v9, a3);
      if ( !AdapterByName )
        return 9003;
    }
  }
  v12 = *(_DWORD *)(v7 + 264);
  v13 = (void *)(v7 + 2768);
  v14 = -1;
  v45 = (WCHAR *)(v7 + 2768);
  *(_QWORD *)&v46 = 0;
  *((_QWORD *)&v46 + 1) = &v46;
  if ( v12 < 0 )
  {
    if ( !v10 )
      return 9003;
    goto LABEL_27;
  }
  if ( !v10 || !*v10 )
  {
    if ( SBYTE1(xmmword_1801119E0) < 0 )
      WPP_SF_(1039, 20, WPP_f4ef6d0c0ed83ebd4dc80ffe2f825eb2_Traceguids);
    goto LABEL_67;
  }
  if ( v10 == L"..localmachine" )
    goto LABEL_64;
  cchCount2 = -1;
  do
    ++cchCount2;
  while ( v10[cchCount2] );
  if ( (_DWORD)cchCount2 == 14 )
  {
LABEL_15:
    if ( CompareStringW(0x7Fu, 1u, v10, cchCount2, L"..localmachine", cchCount2) != 2 )
      goto LABEL_16;
LABEL_64:
    if ( SBYTE1(xmmword_1801119E0) < 0 )
      WPP_SF_(1039, 21, WPP_f4ef6d0c0ed83ebd4dc80ffe2f825eb2_Traceguids);
    v11 |= 4u;
    goto LABEL_67;
  }
  if ( (_DWORD)cchCount2 == 15 && v10[14] == 46 )
  {
    LODWORD(cchCount2) = 14;
    goto LABEL_15;
  }
LABEL_16:
  if ( (v11 & 2) == 0 )
    return 9003;
  if ( v10 == L"loopback" )
    goto LABEL_135;
  v16 = -1;
  do
    ++v16;
  while ( v10[v16] );
  if ( (_DWORD)v16 == 8 )
  {
LABEL_21:
    if ( CompareStringW(0x7Fu, 1u, v10, v16, L"loopback", v16) == 2 )
      goto LABEL_135;
    goto LABEL_22;
  }
  if ( (_DWORD)v16 == 9 && v10[8] == 46 )
  {
    LODWORD(v16) = 8;
    goto LABEL_21;
  }
LABEL_22:
  if ( v10 == L"localhost" )
    goto LABEL_135;
  v17 = -1;
  do
    ++v17;
  while ( v10[v17] );
  if ( (_DWORD)v17 == 9 )
    goto LABEL_26;
  if ( (_DWORD)v17 == 10 && v10[9] == 46 )
  {
    LODWORD(v17) = 9;
LABEL_26:
    if ( CompareStringW(0x7Fu, 1u, v10, v17, L"localhost", v17) != 2 )
      goto LABEL_27;
LABEL_135:
    *(_QWORD *)&v47 = 0;
    DWORD2(v47) = 0;
    goto LABEL_129;
  }
LABEL_27:
  if ( !*(_QWORD *)(v41 + 24) )
  {
    if ( (SBYTE1(xmmword_1801119E0) & 0x80u) == 0 )
      return 9003;
    v29 = 22;
LABEL_119:
    WPP_SF_(1039, v29, WPP_f4ef6d0c0ed83ebd4dc80ffe2f825eb2_Traceguids);
    return 9003;
  }
  v48 = 512;
  if ( !(unsigned int)Dns_StringCopy((void *)(v7 + 2768), 1, 1) )
  {
    if ( (SBYTE3(xmmword_1801119E0) & 0x80u) == 0 )
      return 9003;
    v28 = 23;
    goto LABEL_95;
  }
  v18 = wcschr((const wchar_t *)(v7 + 2768), 0x2Eu);
  if ( v18 && (v19 = v18 + 1, v18[1]) )
  {
    v20 = (const WCHAR *)(v7 + 2768);
    if ( (unsigned __int64)v19 > v7 + 2768 )
    {
      *v18 = 0;
      goto LABEL_33;
    }
  }
  else
  {
    v20 = (const WCHAR *)(v7 + 2768);
  }
  v19 = 0;
LABEL_33:
  v21 = *(const WCHAR **)(v41 + 24);
  if ( v20 != v21 )
  {
    if ( !v20 || !v21 )
      goto LABEL_41;
    v22 = -1;
    do
      ++v22;
    while ( v20[v22] );
    do
      ++v14;
    while ( v21[v14] );
    if ( (_DWORD)v14 != (_DWORD)v22 )
    {
      if ( (_DWORD)v14 == (_DWORD)v22 + 1 )
      {
        if ( v21[(int)v22] != 46 )
          goto LABEL_41;
      }
      else
      {
        if ( (_DWORD)v14 + 1 != (_DWORD)v22 || v20[(int)v14] != 46 )
          goto LABEL_41;
        LODWORD(v22) = v14;
      }
    }
    if ( CompareStringW(0x7Fu, 1u, v20, v22, v21, v22) != 2 )
    {
LABEL_41:
      if ( (SBYTE3(xmmword_1801119E0) & 0x80u) == 0 )
        return 9003;
      v28 = 24;
LABEL_95:
      WPP_SF_S(1055, v28, WPP_f4ef6d0c0ed83ebd4dc80ffe2f825eb2_Traceguids, v10);
      return 9003;
    }
  }
  if ( !v19 )
  {
    if ( (SBYTE1(xmmword_1801119E0) & 0x80u) == 0 )
    {
LABEL_80:
      v13 = (void *)(v7 + 2768);
LABEL_67:
      if ( *(_QWORD *)(v41 + 24) )
      {
        if ( !Dns_NameAppend_W(v13) )
          return 9003;
        v10 = (const WCHAR *)v13;
      }
      else
      {
        v10 = L"localhost";
      }
      v24 = v11 | 4;
      if ( (*(_DWORD *)(v7 + 264) & 0x10000000) == 0 )
        v24 = v11;
      LOBYTE(v11) = v24;
      LocalAddrArray = NetInfo_CreateLocalAddrArray(v41, 0, AdapterByName, v42, v24);
      v26 = (void *)LocalAddrArray;
      if ( !LocalAddrArray )
        return 9501;
      localip_BuildRRListFromArray(&v46, v10, (unsigned __int16)v5, LocalAddrArray);
      DnsApiFree(v26);
      v27 = v46;
      if ( (_QWORD)v46 )
      {
        if ( SBYTE1(xmmword_1801119E0) < 0 )
          WPP_SF_q(1039, 30, WPP_f4ef6d0c0ed83ebd4dc80ffe2f825eb2_Traceguids, v46);
        *(_QWORD *)(v7 + 1016) = v27;
        return 0;
      }
      goto LABEL_125;
    }
    v30 = 25;
LABEL_97:
    WPP_SF_(1039, v30, WPP_f4ef6d0c0ed83ebd4dc80ffe2f825eb2_Traceguids);
    goto LABEL_80;
  }
  v31 = v41;
  if ( (unsigned int)Dns_NameCompare_W(v19, *(PCNZWCH *)(v41 + 16)) )
  {
    if ( (SBYTE1(xmmword_1801119E0) & 0x80u) == 0 )
      goto LABEL_80;
    v30 = 26;
    goto LABEL_97;
  }
  v32 = 0;
  v10 = 0;
  for ( i = 0; i < *(_DWORD *)(v31 + 68); ++i )
  {
    v34 = 160LL * i + v31 + 104;
    if ( (!AdapterByName || AdapterByName == v34)
      && ((*(_BYTE *)(v34 + 68) & 2) != 0 || (a5 & 0x20) != 0)
      && *(_QWORD *)(v34 + 32)
      && (unsigned int)Dns_NameCompare_W(v19, *(PCNZWCH *)(v34 + 8)) )
    {
      if ( !v32 )
      {
        if ( SBYTE1(xmmword_1801119E0) < 0 )
          WPP_SF_S(1039, 27, WPP_f4ef6d0c0ed83ebd4dc80ffe2f825eb2_Traceguids, *(_QWORD *)(v34 + 8));
        v10 = v45;
        if ( !Dns_NameAppend_W(v45) )
          return 9003;
        v32 = 1;
      }
      v35 = NetInfo_CreateLocalAddrArray(v41, 0, v34, v42, v11);
      v36 = (void *)v35;
      if ( v35 )
      {
        localip_BuildRRListFromArray(&v46, v10, a2, v35);
        DnsApiFree(v36);
      }
    }
    v31 = v41;
  }
  if ( !v32 )
  {
    if ( (SBYTE1(xmmword_1801119E0) & 0x80u) == 0 )
      return 9003;
    v29 = 28;
    goto LABEL_119;
  }
  v37 = v46;
  if ( (_QWORD)v46 )
  {
    if ( SBYTE1(xmmword_1801119E0) < 0 )
      WPP_SF_q(1039, 29, WPP_f4ef6d0c0ed83ebd4dc80ffe2f825eb2_Traceguids, v46);
    *(_QWORD *)(a1 + 1016) = v37;
    return 0;
  }
  LOWORD(v5) = a2;
  v7 = a1;
LABEL_125:
  if ( (v11 & 2) == 0 )
    return 9501;
  if ( SBYTE3(xmmword_1801119E0) < 0 )
    WPP_SF_(1055, 31, WPP_f4ef6d0c0ed83ebd4dc80ffe2f825eb2_Traceguids);
  *(_QWORD *)&v47 = 0;
  *(_DWORD *)(v7 + 524) = 1;
  DWORD2(v47) = 0;
LABEL_129:
  HIDWORD(v47) = 0x1000000;
  if ( (*(_BYTE *)(v41 + 56) & 0x10) == 0 && (_WORD)v5 == 1 || (*(_DWORD *)(v41 + 56) & 0x100) == 0 && (_WORD)v5 == 28 )
    return 9501;
  if ( (_WORD)v5 == 1 )
    DnsAddr_BuildFromIp4(v49);
  else
    DnsAddr_BuildFromIp6(v49);
  ForwardRecord = Dns_CreateForwardRecord(
                    (_DWORD)v10,
                    (unsigned __int16)v5,
                    (unsigned int)v49,
                    dword_1801117BC,
                    lpString2,
                    1);
  *(_QWORD *)(v7 + 1016) = ForwardRecord;
  return ForwardRecord == 0 ? 0xE : 0;
}

```

## disassembly

```asm
0x18000f704  mov     [rsp-8+arg_8], rbx
0x18000f709  push    rbp
0x18000f70a  push    rsi
0x18000f70b  push    rdi
0x18000f70c  push    r12
0x18000f70e  push    r13
0x18000f710  push    r14
0x18000f712  push    r15
0x18000f714  lea     rbp, [rsp-1Fh]
0x18000f719  sub     rsp, 0E0h
0x18000f720  mov     rax, cs:__security_cookie
0x18000f727  xor     rax, rsp
0x18000f72a  mov     [rbp+4Fh+var_40], rax
0x18000f72e  movzx   esi, dx
0x18000f731  mov     rdi, r8
0x18000f734  xor     edx, edx; Val
0x18000f736  mov     [rbp+4Fh+var_C0], rcx
0x18000f73a  mov     r14, rcx
0x18000f73d  mov     [rbp+4Fh+var_C8], r9
0x18000f741  lea     rcx, [rbp+4Fh+var_80]; void *
0x18000f745  mov     [rsp+110h+var_E0], si
0x18000f74a  mov     r15, r9
0x18000f74d  lea     r8d, [rdx+40h]; Size
0x18000f751  call    memset_0
0x18000f756  mov     rax, [r14+400h]
0x18000f75d  xorps   xmm0, xmm0
0x18000f760  mov     rbx, [r14+0F0h]
0x18000f767  xorps   xmm1, xmm1
0x18000f76a  movups  [rbp+4Fh+var_A0], xmm0
0x18000f76e  mov     [rsp+110h+var_D8], rax
0x18000f773  movups  [rbp+4Fh+var_B0], xmm1
0x18000f777  xor     edx, edx
0x18000f779  cmp     byte ptr cs:xmmword_1801119E0+3, dl
0x18000f77f  jl      loc_18000FC77
0x18000f785  mov     ecx, [rbp+4Fh+arg_20]
0x18000f788  mov     r12d, 3
0x18000f78e  test    ecx, ecx
0x18000f790  mov     [r14+20Ch], edx
0x18000f797  mov     [r14+3F8h], rdx
0x18000f79e  cmovnz  r12d, ecx
0x18000f7a2  mov     ecx, 1Ch
0x18000f7a7  lea     r10d, [rcx-1Bh]
0x18000f7ab  cmp     si, r10w
0x18000f7af  jnz     loc_18000FA4D
0x18000f7b5  mov     [rsp+110h+var_D0], 2
0x18000f7bd  test    rdi, rdi
0x18000f7c0  jnz     loc_18000FCB6
0x18000f7c6  mov     ecx, [r14+108h]
0x18000f7cd  lea     r15, [r14+0AD0h]
0x18000f7d4  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000f7d8  mov     [rbp+4Fh+var_B8], r15
0x18000f7dc  bt      rcx, 1Fh
0x18000f7e1  mov     qword ptr [rbp+4Fh+var_B0], rdx
0x18000f7e5  lea     rax, [rbp+4Fh+var_B0]
0x18000f7e9  mov     r13d, 40Fh
0x18000f7ef  mov     qword ptr [rbp+4Fh+var_B0+8], rax
0x18000f7f3  lea     r11, aLocalhost; "localhost"
0x18000f7fa  lea     r8d, [rdi+2Fh]
0x18000f7fe  jb      loc_18000FA63
0x18000f804  test    rbx, rbx
0x18000f807  jz      loc_18000FB0F
0x18000f80d  cmp     [rbx], dx
0x18000f810  jz      loc_18000FB0F
0x18000f816  lea     rax, aLocalmachine; "..localmachine"
0x18000f81d  cmp     rbx, rax
0x18000f820  jz      loc_18000FB2D
0x18000f826  mov     r9, rdi
0x18000f829  inc     r9; cchCount1
0x18000f82c  cmp     [rbx+r9*2], dx
0x18000f831  jnz     short loc_18000F829
0x18000f833  cmp     r9d, 0Eh
0x18000f837  jnz     loc_18000FAAD
0x18000f83d  mov     [rsp+110h+cchCount2], r9d; cchCount2
0x18000f842  mov     r8, rbx; lpString1
0x18000f845  mov     edx, r10d; dwCmpFlags
0x18000f848  mov     [rsp+110h+lpString2], rax; lpString2
0x18000f84d  mov     ecx, 7Fh; Locale
0x18000f852  call    cs:__imp_CompareStringW
0x18000f859  nop     dword ptr [rax+rax+00h]
0x18000f85e  xor     edx, edx
0x18000f860  cmp     eax, 2
0x18000f863  jz      loc_18000FB2D
0x18000f869  lea     r8d, [rdx+2Eh]
0x18000f86d  lea     r11, aLocalhost; "localhost"
0x18000f874  test    r12b, 2
0x18000f878  jz      loc_18000FA20
0x18000f87e  lea     rax, aLoopback; "loopback"
0x18000f885  cmp     rbx, rax
0x18000f888  jz      loc_18000FF3E
0x18000f88e  mov     r9, rdi
0x18000f891  inc     r9; cchCount1
0x18000f894  cmp     [rbx+r9*2], dx
0x18000f899  jnz     short loc_18000F891
0x18000f89b  cmp     r9d, 8
0x18000f89f  jnz     loc_18000FACD
0x18000f8a5  mov     edx, 1; dwCmpFlags
0x18000f8aa  mov     [rsp+110h+cchCount2], r9d; cchCount2
0x18000f8af  mov     r8, rbx; lpString1
0x18000f8b2  mov     [rsp+110h+lpString2], rax; lpString2
0x18000f8b7  lea     ecx, [rdx+7Eh]; Locale
0x18000f8ba  call    cs:__imp_CompareStringW
0x18000f8c1  nop     dword ptr [rax+rax+00h]
0x18000f8c6  cmp     eax, 2
0x18000f8c9  jz      loc_18000FF3E
0x18000f8cf  xor     edx, edx
0x18000f8d1  lea     r11, aLocalhost; "localhost"
0x18000f8d8  cmp     rbx, r11
0x18000f8db  jz      loc_18000FF3E
0x18000f8e1  mov     r9, rdi
0x18000f8e4  inc     r9; cchCount1
0x18000f8e7  cmp     [rbx+r9*2], dx
0x18000f8ec  jnz     short loc_18000F8E4
0x18000f8ee  cmp     r9d, 9
0x18000f8f2  jnz     loc_18000FAED
0x18000f8f8  mov     edx, 1; dwCmpFlags
0x18000f8fd  mov     [rsp+110h+cchCount2], r9d; cchCount2
0x18000f902  mov     r8, rbx; lpString1
0x18000f905  mov     [rsp+110h+lpString2], r11; lpString2
0x18000f90a  lea     ecx, [rdx+7Eh]; Locale
0x18000f90d  call    cs:__imp_CompareStringW
0x18000f914  nop     dword ptr [rax+rax+00h]
0x18000f919  cmp     eax, 2
0x18000f91c  jz      loc_18000FF3E
0x18000f922  xor     edx, edx
0x18000f924  mov     rax, [rsp+110h+var_D8]
0x18000f929  cmp     [rax+18h], rdx
0x18000f92d  jz      loc_18000FC36
0x18000f933  mov     r8, [r14+0F0h]
0x18000f93a  lea     rdx, [rbp+4Fh+var_90]
0x18000f93e  mov     eax, 1
0x18000f943  mov     [rbp+4Fh+var_90], 200h
0x18000f94a  mov     [rsp+110h+cchCount2], eax; int
0x18000f94e  xor     r9d, r9d
0x18000f951  mov     rcx, r15; void *
0x18000f954  mov     dword ptr [rsp+110h+lpString2], eax; int
0x18000f958  call    Dns_StringCopy
0x18000f95d  xor     r8d, r8d
0x18000f960  test    eax, eax
0x18000f962  jz      loc_18000FC1F
0x18000f968  lea     edx, [r8+2Eh]; Ch
0x18000f96c  mov     rcx, r15; Str
0x18000f96f  call    cs:__imp_wcschr
0x18000f976  nop     dword ptr [rax+rax+00h]
0x18000f97b  xor     r8d, r8d
0x18000f97e  test    rax, rax
0x18000f981  jz      loc_18000FA6E
0x18000f987  lea     r15, [rax+2]
0x18000f98b  cmp     [r15], r8w
0x18000f98f  jz      loc_18000FA6E
0x18000f995  lea     rdx, [r14+0AD0h]
0x18000f99c  cmp     r15, rdx
0x18000f99f  jbe     loc_18000FA75
0x18000f9a5  mov     [r15-2], r8w
0x18000f9aa  mov     rax, [rsp+110h+var_D8]
0x18000f9af  mov     rcx, [rax+18h]
0x18000f9b3  cmp     rdx, rcx
0x18000f9b6  jz      loc_18000FBFD
0x18000f9bc  test    rdx, rdx
0x18000f9bf  jz      short loc_18000FA13
0x18000f9c1  test    rcx, rcx
0x18000f9c4  jz      short loc_18000FA13
0x18000f9c6  mov     r9, rdi
0x18000f9c9  inc     r9; cchCount1
0x18000f9cc  cmp     [rdx+r9*2], r8w
0x18000f9d1  jnz     short loc_18000F9C9
0x18000f9d3  inc     rdi
0x18000f9d6  cmp     [rcx+rdi*2], r8w
0x18000f9db  jnz     short loc_18000F9D3
0x18000f9dd  cmp     edi, r9d
0x18000f9e0  jnz     loc_18000FA7D
0x18000f9e6  mov     r8, rdx; lpString1
0x18000f9e9  mov     [rsp+110h+cchCount2], r9d; cchCount2
0x18000f9ee  mov     edx, 1; dwCmpFlags
0x18000f9f3  mov     [rsp+110h+lpString2], rcx; lpString2
0x18000f9f8  lea     ecx, [rdx+7Eh]; Locale
0x18000f9fb  call    cs:__imp_CompareStringW
0x18000fa02  nop     dword ptr [rax+rax+00h]
0x18000fa07  xor     r8d, r8d
0x18000fa0a  cmp     eax, 2
0x18000fa0d  jz      loc_18000FBFD
0x18000fa13  cmp     byte ptr cs:xmmword_1801119E0+3, r8b
0x18000fa1a  jl      loc_18000FCE2
0x18000fa20  mov     eax, 232Bh
0x18000fa25  mov     rcx, [rbp+4Fh+var_40]
0x18000fa29  xor     rcx, rsp; StackCookie
0x18000fa2c  call    __security_check_cookie
0x18000fa31  mov     rbx, [rsp+110h+arg_8]
0x18000fa39  add     rsp, 0E0h
0x18000fa40  pop     r15
0x18000fa42  pop     r14
0x18000fa44  pop     r13
0x18000fa46  pop     r12
0x18000fa48  pop     rdi
0x18000fa49  pop     rsi
0x18000fa4a  pop     rbp
0x18000fa4b  retn
0x18000fa4d  cmp     si, cx
0x18000fa50  jnz     loc_18000FCA0
0x18000fa56  mov     [rsp+110h+var_D0], 17h
0x18000fa5e  jmp     loc_18000F7BD
0x18000fa63  test    rbx, rbx
0x18000fa66  jnz     loc_18000F924
0x18000fa6c  jmp     short loc_18000FA20
0x18000fa6e  lea     rdx, [r14+0AD0h]
0x18000fa75  mov     r15, r8
0x18000fa78  jmp     loc_18000F9AA
0x18000fa7d  lea     eax, [r9+1]
0x18000fa81  cmp     edi, eax
0x18000fa83  jz      loc_18000FC4C
0x18000fa89  lea     eax, [rdi+1]
0x18000fa8c  cmp     eax, r9d
0x18000fa8f  jnz     short loc_18000FA13
0x18000fa91  movsxd  rax, edi
0x18000fa94  mov     r10d, 2Eh ; '.'
0x18000fa9a  cmp     [rdx+rax*2], r10w
0x18000fa9f  jnz     loc_18000FA13
0x18000faa5  mov     r9d, edi
0x18000faa8  jmp     loc_18000F9E6
0x18000faad  cmp     r9d, 0Fh
0x18000fab1  jnz     loc_18000F874
0x18000fab7  cmp     [rbx+1Ch], r8w
0x18000fabc  jnz     loc_18000F874
0x18000fac2  mov     r9d, 0Eh
0x18000fac8  jmp     loc_18000F83D
0x18000facd  cmp     r9d, 9
0x18000fad1  jnz     loc_18000F8D8
0x18000fad7  cmp     [rbx+10h], r8w
0x18000fadc  jnz     loc_18000F8D8
0x18000fae2  mov     r9d, 8
0x18000fae8  jmp     loc_18000F8A5
0x18000faed  cmp     r9d, 0Ah
0x18000faf1  jnz     loc_18000F924
0x18000faf7  lea     r10d, [r9+24h]
0x18000fafb  cmp     [rbx+12h], r10w
0x18000fb00  jnz     loc_18000F924
0x18000fb06  lea     r9d, [r10-25h]
0x18000fb0a  jmp     loc_18000F8F8
0x18000fb0f  cmp     byte ptr cs:xmmword_1801119E0+1, dl
0x18000fb15  jge     short loc_18000FB44
0x18000fb17  mov     edx, 14h
0x18000fb1c  lea     r8, WPP_f4ef6d0c0ed83ebd4dc80ffe2f825eb2_Traceguids
0x18000fb23  mov     ecx, r13d
0x18000fb26  call    WPP_SF_
0x18000fb2b  jmp     short loc_18000FB3D
0x18000fb2d  cmp     byte ptr cs:xmmword_1801119E0+1, dl
0x18000fb33  jl      loc_18000FF4F
0x18000fb39  or      r12d, 4
0x18000fb3d  lea     r11, aLocalhost; "localhost"
0x18000fb44  mov     rax, [rsp+110h+var_D8]
0x18000fb49  xor     edi, edi
0x18000fb4b  mov     r8, [rax+18h]
0x18000fb4f  test    r8, r8
0x18000fb52  jz      loc_18000FC65
0x18000fb58  test    byte ptr [rbp+4Fh+arg_20], 40h
0x18000fb5c  mov     r9d, edi
0x18000fb5f  mov     rcx, r15; void *
0x18000fb62  cmovz   r9, [rax+10h]
0x18000fb67  call    Dns_NameAppend_W
0x18000fb6c  test    rax, rax
0x18000fb6f  jz      loc_18000FA20
0x18000fb75  mov     rbx, r15
0x18000fb78  mov     eax, [r14+108h]
0x18000fb7f  mov     ecx, r12d
0x18000fb82  mov     r9d, [rsp+110h+var_D0]
0x18000fb87  or      ecx, 4
0x18000fb8a  mov     r8, [rbp+4Fh+var_C8]
0x18000fb8e  and     eax, 10000000h
0x18000fb93  test    rax, rax
0x18000fb96  cmovz   ecx, r12d
0x18000fb9a  xor     edx, edx
0x18000fb9c  mov     r12d, ecx
0x18000fb9f  mov     dword ptr [rsp+110h+lpString2], ecx
0x18000fba3  mov     rcx, [rsp+110h+var_D8]
0x18000fba8  call    NetInfo_CreateLocalAddrArray
0x18000fbad  mov     rdi, rax
0x18000fbb0  test    rax, rax
0x18000fbb3  jz      loc_18000FC6D
0x18000fbb9  mov     r9, rax
0x18000fbbc  lea     rcx, [rbp+4Fh+var_B0]
0x18000fbc0  movzx   r8d, si
0x18000fbc4  mov     rdx, rbx
0x18000fbc7  call    localip_BuildRRListFromArray
0x18000fbcc  mov     rcx, rdi; lpMem
0x18000fbcf  call    DnsApiFree
0x18000fbd4  mov     rdi, qword ptr [rbp+4Fh+var_B0]
0x18000fbd8  xor     edx, edx
0x18000fbda  test    rdi, rdi
0x18000fbdd  jz      loc_18000FEB3
0x18000fbe3  cmp     byte ptr cs:xmmword_1801119E0+1, dl
0x18000fbe9  jl      loc_18000FF68
0x18000fbef  mov     [r14+3F8h], rdi
0x18000fbf6  xor     eax, eax
0x18000fbf8  jmp     loc_18000FA25
0x18000fbfd  test    r15, r15
0x18000fc00  jnz     loc_18000FD20
0x18000fc06  cmp     byte ptr cs:xmmword_1801119E0+1, r8b
0x18000fc0d  jl      loc_18000FD00
0x18000fc13  lea     r15, [r14+0AD0h]
0x18000fc1a  jmp     loc_18000FB3D
0x18000fc1f  cmp     byte ptr cs:xmmword_1801119E0+3, r8b
  ... truncated ...
```
