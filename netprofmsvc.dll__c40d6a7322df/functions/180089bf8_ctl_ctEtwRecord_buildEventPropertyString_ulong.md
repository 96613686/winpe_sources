# ctl::ctEtwRecord::buildEventPropertyString(ulong)

- ea: `0x180089bf8`
- end: `0x18008a45b`
- name: `?buildEventPropertyString@ctEtwRecord@ctl@@AEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@Z`
- size: `2147`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800f15fc`

## callees

- `0x18000e190`
- `0x18001e920`
- `0x18001f600`
- `0x18002aae0`
- `0x18002b050`
- `0x18002b250`
- `0x1800801ac`
- `0x1800802d4`
- `0x180089bf8`
- `0x18008a4d8`
- `0x18008e780`
- `0x1800910d8`
- `0x18009ba90`
- `0x18009f5e8`
- `0x1800a88a0`
- `0x1800a959c`
- `0x1800a9738`
- `0x1800a9744`
- `0x1800a97b0`
- `0x1800a98c0`
- `0x1800a9924`
- `0x1800e885c`
- `0x1800eaa0c`
- `0x1800f16d0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__i64tow_s` at `0x180089f0e`
- `api-ms-win-crt-private-l1-1-0!_o__i64tow_s` at `0x180089f0e`
- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x180089d1c`
- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x180089fde`
- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x18008a14f`
- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x18008a250`
- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x180089d1c`
- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x180089fde`
- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x18008a14f`
- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x18008a250`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x180089ede`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x18008a1f0`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x180089ede`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x18008a1f0`
- `ntdll!RtlIpv4AddressToStringW` at `0x180089f4c`
- `ntdll!RtlIpv4AddressToStringW` at `0x180089f4c`
- `ntdll!RtlIpv6AddressToStringW` at `0x18008a0df`
- `ntdll!RtlIpv6AddressToStringW` at `0x18008a0df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a2ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a2ca`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180089dce`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180089e1e`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180089dce`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180089e1e`
- `RPCRT4!RpcStringFreeW` at `0x18008a0b3`
- `RPCRT4!RpcStringFreeW` at `0x18008a0b3`
- `RPCRT4!UuidToStringW` at `0x18008a093`
- `RPCRT4!UuidToStringW` at `0x18008a093`
- `WS2_32!WSAAddressToStringW` at `0x18008a118`
- `WS2_32!WSAAddressToStringW` at `0x18008a118`
- `WS2_32!__imp_ntohs` at `0x180089fb1`
- `WS2_32!__imp_ntohs` at `0x180089fb1`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18008a2bc`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18008a34b`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18008a2bc`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18008a34b`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall ctl::ctEtwRecord::buildEventPropertyString(ctl::ctEtwRecord *a1, __int64 a2, unsigned int a3)
{
  __int64 v3; // rsi
  __int64 v6; // r9
  unsigned __int64 v7; // r14
  __int64 v8; // rcx
  __int64 v9; // r8
  unsigned __int16 *v10; // rdi
  unsigned int v11; // edx
  unsigned int v12; // edx
  unsigned int v13; // edx
  unsigned int v14; // edx
  __int64 v15; // rcx
  WCHAR *v16; // rdx
  unsigned __int16 *v17; // r8
  unsigned __int64 v18; // rax
  const CHAR *v19; // r8
  int v20; // eax
  int cchWideChar; // edi
  const CHAR *v22; // r8
  unsigned __int16 *v23; // r8
  unsigned __int64 v24; // rcx
  unsigned int v25; // edx
  unsigned int v26; // edx
  unsigned int v27; // edx
  unsigned int v28; // edx
  RPC_WSTR v29; // rcx
  int v30; // edx
  double v31; // xmm3_8
  unsigned int v32; // edx
  unsigned int v33; // edx
  __int64 v34; // rdx
  int v35; // edx
  unsigned int v36; // r15d
  unsigned int v37; // edx
  __int64 v38; // rdx
  int v39; // edx
  unsigned int v40; // r15d
  void *v41; // rax
  void *v42; // rax
  LPWSTR v43; // rsi
  DWORD cchName; // [rsp+70h] [rbp-90h] BYREF
  RPC_WSTR StringUuid; // [rsp+78h] [rbp-88h] BYREF
  DWORD cchReferencedDomainName; // [rsp+80h] [rbp-80h] BYREF
  WCHAR Name[2]; // [rsp+84h] [rbp-7Ch] BYREF
  LPWSTR ReferencedDomainName[2]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v50; // [rsp+98h] [rbp-68h]
  LPCCH lpMultiByteStr[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v52; // [rsp+B0h] [rbp-50h]
  unsigned __int64 v53; // [rsp+B8h] [rbp-48h]
  WCHAR S[104]; // [rsp+C0h] [rbp-40h] BYREF

  v3 = a3;
  cchName = 0;
  if ( !ctl::ctEtwRecord::queryTopLevelPropertyCount(a1, &cchName) || (unsigned int)v3 >= cchName )
  {
    std::runtime_error::runtime_error(
      (std::runtime_error *)ReferencedDomainName,
      "ctEtwRecord - ETW Property value requested is out of range");
    throw (std::runtime_error *)ReferencedDomainName;
  }
  _mm_lfence();
  memset_0(S, 0, 0xC8u);
  std::wstring::wstring(a2);
  v6 = *((_QWORD *)a1 + 20);
  v7 = *(unsigned int *)(v6 + 24 * v3 + 16);
  if ( !(_DWORD)v7 )
    return a2;
  v8 = *((_QWORD *)a1 + 17);
  v9 = *(unsigned __int16 *)(v8 + 24 * v3 + 122);
  v10 = *(unsigned __int16 **)(v6 + 24 * v3);
  v11 = *(unsigned __int16 *)(v8 + 24 * v3 + 120);
  if ( v11 > 0xB )
  {
    if ( v11 > 0x11 )
    {
      v37 = v11 - 18;
      if ( !v37 )
      {
        if ( (_DWORD)v7 == 16 )
        {
          snwprintf_s(S, 0x64u, 0x63u, L"%d/%d/%d - %d:%d:%d::%d", *v10, v10[1], v10[3], v10[4], v10[5], v10[6], v10[7]);
          goto LABEL_126;
        }
        return a2;
      }
      v38 = v37 - 1;
      if ( !(_DWORD)v38 )
      {
        std::wstring::operator=(a2, v38, v9);
        v40 = 0;
        do
        {
          _o__itow_s((unsigned int)*((char *)v10 + v40), S, 100, 16);
          std::wstring::append(a2, S);
          ++v40;
        }
        while ( v40 < (unsigned int)v7 );
        std::wstring::push_back(a2, 93);
        *(_OWORD *)lpMultiByteStr = 0;
        *(_OWORD *)ReferencedDomainName = 0;
        cchName = 0;
        cchReferencedDomainName = 0;
        LODWORD(StringUuid) = 0;
        if ( !LookupAccountSidW(0, v10, Name, &cchName, Name, &cchReferencedDomainName, (PSID_NAME_USE)&StringUuid)
          && GetLastError() == 122 )
        {
          v41 = operator new[](saturated_mul(cchName, 2u));
          std::shared_ptr<wchar_t [0]>::reset<wchar_t,0>(lpMultiByteStr, v41);
          v42 = operator new[](saturated_mul(cchReferencedDomainName, 2u));
          std::shared_ptr<wchar_t [0]>::reset<wchar_t,0>(ReferencedDomainName, v42);
          v43 = ReferencedDomainName[0];
          if ( LookupAccountSidW(
                 0,
                 v10,
                 (LPWSTR)lpMultiByteStr[0],
                 &cchName,
                 ReferencedDomainName[0],
                 &cchReferencedDomainName,
                 (PSID_NAME_USE)&StringUuid) )
          {
            std::wstring::append(a2, L"  ");
            std::wstring::append(a2, v43);
            std::wstring::append(a2, L"\\");
            std::wstring::append(a2, lpMultiByteStr[0]);
          }
        }
        if ( ReferencedDomainName[1] )
          std::_Ref_count_base::_Decref((std::_Ref_count_base *)ReferencedDomainName[1]);
        if ( lpMultiByteStr[1] )
          std::_Ref_count_base::_Decref((std::_Ref_count_base *)lpMultiByteStr[1]);
        return a2;
      }
      v39 = v38 - 1;
      if ( !v39 )
      {
        if ( (_DWORD)v7 == 4 )
        {
          v15 = *v10;
          goto LABEL_17;
        }
        return a2;
      }
      if ( v39 != 1 || (_DWORD)v7 != 8 )
        return a2;
    }
    else
    {
      if ( v11 == 17 )
      {
        if ( (_DWORD)v7 != 8 )
          return a2;
        StringUuid = *(RPC_WSTR *)v10;
        v29 = StringUuid;
        goto LABEL_109;
      }
      v32 = v11 - 12;
      if ( !v32 )
      {
        v31 = *(double *)v10;
        goto LABEL_73;
      }
      v33 = v32 - 1;
      if ( !v33 )
      {
        if ( *(_DWORD *)v10 )
          goto LABEL_21;
        goto LABEL_99;
      }
      v34 = v33 - 1;
      if ( !(_DWORD)v34 )
      {
        if ( !(_WORD)v9 || (_WORD)v9 == 15 )
        {
          std::wstring::operator=(a2, v34, v9);
          v36 = 0;
          do
          {
            _o__itow_s(*((unsigned __int8 *)v10 + v36), S, 100, 16);
            std::wstring::append(a2, S);
            ++v36;
          }
          while ( v36 < (unsigned int)v7 );
          std::wstring::push_back(a2, 93);
          return a2;
        }
        if ( (_WORD)v9 != 24 )
        {
          if ( (_WORD)v9 == 25 )
          {
            LODWORD(StringUuid) = 100;
            if ( !WSAAddressToStringW((LPSOCKADDR)v10, v7, 0, S, (LPDWORD)&StringUuid) )
              goto LABEL_126;
          }
          return a2;
        }
        RtlIpv6AddressToStringW((const struct in6_addr *)v10, S);
LABEL_111:
        std::wstring::append(a2, S);
        return a2;
      }
      v35 = v34 - 1;
      if ( !v35 )
      {
        if ( (_DWORD)v7 == 16 )
        {
          StringUuid = 0;
          if ( !UuidToStringW((const UUID *)v10, &StringUuid) )
          {
            std::wstring::assign(a2, StringUuid);
            RpcStringFreeW(&StringUuid);
          }
        }
        return a2;
      }
      if ( v35 != 1 )
        return a2;
      if ( (_DWORD)v7 == 4 )
      {
        v15 = *(unsigned int *)v10;
        goto LABEL_71;
      }
      if ( (_DWORD)v7 != 8 )
      {
        wprintf(L"TDH_INTYPE_POINTER was called with a %d -size value\n", (unsigned int)v7, v9);
        return a2;
      }
    }
    v29 = *(RPC_WSTR *)v10;
LABEL_109:
    _o__ui64tow_s(v29, S, 100);
    goto LABEL_110;
  }
  if ( v11 == 11 )
  {
    v31 = *(float *)v10;
LABEL_73:
    swprintf_s(S, 0x64u, L"%f", v31);
    goto LABEL_111;
  }
  if ( v11 > 5 )
  {
    v25 = v11 - 6;
    if ( !v25 )
    {
      if ( (_WORD)v9 )
      {
        v15 = *v10;
        if ( (_WORD)v9 != 6 )
        {
          if ( (_WORD)v9 == 22 )
          {
            v15 = ntohs(v15);
            goto LABEL_17;
          }
          if ( (_WORD)v9 != 17 )
            return a2;
          goto LABEL_71;
        }
      }
      else
      {
        LOWORD(v15) = *v10;
      }
      v15 = (unsigned __int16)v15;
      goto LABEL_17;
    }
    v26 = v25 - 1;
    if ( !v26 )
    {
      v15 = *(unsigned int *)v10;
      goto LABEL_17;
    }
    v27 = v26 - 1;
    if ( v27 )
    {
      v28 = v27 - 1;
      if ( !v28 )
      {
        _o__i64tow_s(*(_QWORD *)v10, S, 100);
        goto LABEL_126;
      }
      if ( v28 != 1 )
        return a2;
      v29 = *(RPC_WSTR *)v10;
      if ( !(_WORD)v9 || (_WORD)v9 == 10 )
      {
        _o__ui64tow_s(v29, S, 100);
        goto LABEL_126;
      }
      if ( (_WORD)v9 != 19 )
        return a2;
      goto LABEL_109;
    }
    v15 = *(unsigned int *)v10;
    if ( !(_WORD)v9 )
      goto LABEL_17;
    if ( (unsigned int)v9 <= 0x1B )
    {
      v30 = 137364736;
      if ( _bittest(&v30, v9) )
        goto LABEL_17;
    }
    if ( (_WORD)v9 == 23 )
    {
      RtlIpv4AddressToStringW(*(const struct in_addr **)(v6 + 24 * v3), S);
      goto LABEL_111;
    }
    if ( (_WORD)v9 != 18 && (unsigned __int16)(v9 - 29) > 3u )
    {
      ctl::ctAlwaysFatalCondition(
        (ctl *)L"Unknown TDH_OUTTYPE [%u] for the TDH_INTYPE_UINT32 value [%u]",
        (const wchar_t *)(unsigned int)v9,
        (unsigned int)v15);
      return a2;
    }
LABEL_71:
    _o__itow_s(v15, S, 100, 16);
LABEL_110:
    std::wstring::assign(a2, L"0x");
    goto LABEL_111;
  }
  if ( v11 == 5 )
  {
    v15 = (unsigned int)(__int16)*v10;
    goto LABEL_17;
  }
  if ( !*(_WORD *)(v8 + 24 * v3 + 120) )
  {
    v16 = L"null";
    goto LABEL_127;
  }
  v12 = v11 - 1;
  if ( !v12 )
  {
    v23 = &v10[v7 >> 1];
    if ( v10 < v23 )
    {
      do
      {
        v24 = (unsigned __int64)(v23 - 1);
        if ( *(v23 - 1) )
          break;
        --v23;
      }
      while ( (unsigned __int64)v10 < v24 );
    }
    std::wstring::_Assign<wchar_t>(a2, *(_QWORD *)(v6 + 24 * v3), v23 - v10);
    return a2;
  }
  v13 = v12 - 1;
  if ( !v13 )
  {
    v17 = (unsigned __int16 *)((char *)v10 + v7);
    if ( v10 < (unsigned __int16 *)((char *)v10 + v7) )
    {
      do
      {
        v18 = (unsigned __int64)v17 - 1;
        if ( *((_BYTE *)v17 - 1) )
          break;
        v17 = (unsigned __int16 *)((char *)v17 - 1);
      }
      while ( (unsigned __int64)v10 < v18 );
    }
    *(_OWORD *)lpMultiByteStr = 0;
    v52 = 0;
    v53 = 0;
    if ( v10 == v17 )
      std::string::_Construct_empty(lpMultiByteStr);
    else
      std::string::_Construct<1,char const *>(lpMultiByteStr, v10, (char *)v17 - (char *)v10);
    v19 = (const CHAR *)lpMultiByteStr;
    if ( v53 > 0xF )
      v19 = lpMultiByteStr[0];
    v20 = MultiByteToWideChar(0, 0, v19, -1, 0, 0);
    cchWideChar = v20;
    if ( v20 )
    {
      Name[0] = 0;
      *(_OWORD *)ReferencedDomainName = 0;
      v50 = 0;
      std::vector<wchar_t>::_Construct_n<wchar_t const &>(ReferencedDomainName, v20, Name);
      v22 = (const CHAR *)lpMultiByteStr;
      if ( v53 > 0xF )
        v22 = lpMultiByteStr[0];
      if ( MultiByteToWideChar(0, 0, v22, -1, ReferencedDomainName[0], cchWideChar) )
        std::wstring::assign(a2, ReferencedDomainName[0]);
      std::vector<unsigned short>::_Tidy(ReferencedDomainName);
    }
    std::string::~string(lpMultiByteStr);
    return a2;
  }
  v14 = v13 - 1;
  if ( !v14 )
  {
    v15 = (unsigned int)*(char *)v10;
    goto LABEL_17;
  }
  if ( v14 == 1 )
  {
    if ( !(_WORD)v9 )
    {
      LOBYTE(v15) = *(_BYTE *)v10;
LABEL_16:
      v15 = (unsigned __int8)v15;
LABEL_17:
      _o__itow_s(v15, S, 100, 10);
LABEL_126:
      v16 = S;
      goto LABEL_127;
    }
    v15 = *(unsigned __int8 *)v10;
    if ( (_WORD)v9 == 4 )
      goto LABEL_16;
    if ( (_WORD)v9 != 16 )
    {
      if ( (_WORD)v9 == 13 )
      {
        if ( (_BYTE)v15 )
        {
LABEL_21:
          v16 = L"true";
LABEL_127:
          std::wstring::assign(a2, v16);
          return a2;
        }
LABEL_99:
        v16 = L"false";
        goto LABEL_127;
      }
      return a2;
    }
    goto LABEL_71;
  }
  return a2;
}

```

## disassembly

```asm
0x180089bf8  push    rbp
0x180089bfa  push    rbx
0x180089bfb  push    rsi
0x180089bfc  push    rdi
0x180089bfd  push    r12
0x180089bff  push    r14
0x180089c01  push    r15
0x180089c03  lea     rbp, [rsp-0A0h]
0x180089c0b  sub     rsp, 1A0h
0x180089c12  mov     rax, cs:__security_cookie
0x180089c19  xor     rax, rsp
0x180089c1c  mov     [rbp+0D0h+var_40], rax
0x180089c23  mov     esi, r8d
0x180089c26  mov     rbx, rdx
0x180089c29  mov     rdi, rcx
0x180089c2c  mov     [rsp+1D0h+var_168], rdx
0x180089c31  xor     r12d, r12d
0x180089c34  mov     [rsp+1D0h+var_170], r12d
0x180089c39  mov     [rsp+1D0h+cchName], r12d
0x180089c3e  lea     rdx, [rsp+1D0h+cchName]; unsigned int *
0x180089c43  call    ?queryTopLevelPropertyCount@ctEtwRecord@ctl@@QEBA_NPEAK@Z; ctl::ctEtwRecord::queryTopLevelPropertyCount(ulong *)
0x180089c48  test    al, al
0x180089c4a  jz      loc_18008A43A
0x180089c50  cmp     esi, [rsp+1D0h+cchName]
0x180089c54  jnb     loc_18008A43A
0x180089c5a  lfence
0x180089c5d  xor     edx, edx; Val
0x180089c5f  mov     r8d, 0C8h; Size
0x180089c65  lea     rcx, [rbp+0D0h+S]; void *
0x180089c69  call    memset_0
0x180089c6e  mov     rcx, rbx
0x180089c71  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180089c76  mov     [rsp+1D0h+var_170], 1
0x180089c7e  lea     rdx, [rsi+rsi*2]
0x180089c82  mov     r9, [rdi+0A0h]
0x180089c89  mov     r14d, [r9+rdx*8+10h]
0x180089c8e  test    r14d, r14d
0x180089c91  jz      loc_18008A416
0x180089c97  mov     rcx, [rdi+88h]
0x180089c9e  movzx   r8d, word ptr [rcx+rdx*8+7Ah]
0x180089ca4  mov     rdi, [r9+rdx*8]
0x180089ca8  lea     rax, [rsi+rsi*2]
0x180089cac  movzx   edx, word ptr [rcx+rax*8+78h]
0x180089cb1  cmp     edx, 0Bh
0x180089cb4  ja      loc_18008A00F
0x180089cba  jz      loc_180089FE9
0x180089cc0  cmp     edx, 5
0x180089cc3  ja      loc_180089E98
0x180089cc9  jz      loc_180089E90
0x180089ccf  test    edx, edx
0x180089cd1  jz      loc_180089E84
0x180089cd7  sub     edx, 1
0x180089cda  jz      loc_180089E4D
0x180089ce0  sub     edx, 1
0x180089ce3  jz      short loc_180089D62
0x180089ce5  sub     edx, 1
0x180089ce8  jz      short loc_180089D5D
0x180089cea  cmp     edx, 1
0x180089ced  jnz     loc_18008A416
0x180089cf3  test    r8w, r8w
0x180089cf7  jnz     short loc_180089CFD
0x180089cf9  mov     cl, [rdi]
0x180089cfb  jmp     short loc_180089D0B
0x180089cfd  movzx   ecx, byte ptr [rdi]
0x180089d00  mov     eax, 4
0x180089d05  cmp     ax, r8w
0x180089d09  jnz     short loc_180089D27
0x180089d0b  movzx   ecx, cl
0x180089d0e  lea     rdx, [rbp+0D0h+S]
0x180089d12  mov     r8d, 64h ; 'd'
0x180089d18  lea     r9d, [r8-5Ah]
0x180089d1c  call    cs:__imp__o__itow_s
0x180089d22  jmp     loc_18008A40A
0x180089d27  mov     esi, 10h
0x180089d2c  cmp     si, r8w
0x180089d30  jnz     short loc_180089D3A
0x180089d32  mov     r9d, esi
0x180089d35  jmp     loc_180089FD4
0x180089d3a  mov     eax, 0Dh
0x180089d3f  cmp     ax, r8w
0x180089d43  jnz     loc_18008A416
0x180089d49  test    cl, cl
0x180089d4b  jz      loc_18008A184
0x180089d51  lea     rdx, aTrue; "true"
0x180089d58  jmp     loc_18008A40E
0x180089d5d  movsx   ecx, byte ptr [rdi]
0x180089d60  jmp     short loc_180089D0E
0x180089d62  lea     r8, [rdi+r14]
0x180089d66  cmp     rdi, r8
0x180089d69  jnb     short loc_180089D7C
0x180089d6b  lea     rax, [r8-1]
0x180089d6f  cmp     [rax], r12b
0x180089d72  jnz     short loc_180089D7C
0x180089d74  mov     r8, rax
0x180089d77  cmp     rdi, rax
0x180089d7a  jb      short loc_180089D6B
0x180089d7c  xorps   xmm0, xmm0
0x180089d7f  movups  xmmword ptr [rbp+0D0h+lpMultiByteStr], xmm0
0x180089d83  mov     [rbp+0D0h+var_120], r12
0x180089d87  mov     [rbp+0D0h+var_118], r12
0x180089d8b  lea     rcx, [rbp+0D0h+lpMultiByteStr]
0x180089d8f  cmp     rdi, r8
0x180089d92  jnz     short loc_180089D9B
0x180089d94  call    ?_Construct_empty@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Construct_empty(void)
0x180089d99  jmp     short loc_180089DA7
0x180089d9b  sub     r8, rdi
0x180089d9e  mov     rdx, rdi
0x180089da1  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180089da6  nop
0x180089da7  lea     r8, [rbp+0D0h+lpMultiByteStr]
0x180089dab  mov     esi, 0Fh
0x180089db0  cmp     [rbp+0D0h+var_118], rsi
0x180089db4  cmova   r8, [rbp+0D0h+lpMultiByteStr]; lpMultiByteStr
0x180089db9  mov     [rsp+1D0h+cchWideChar], r12d; cchWideChar
0x180089dbe  mov     [rsp+1D0h+lpWideCharStr], r12; lpWideCharStr
0x180089dc3  or      r14, 0FFFFFFFFFFFFFFFFh
0x180089dc7  mov     r9d, r14d; cbMultiByte
0x180089dca  xor     edx, edx; dwFlags
0x180089dcc  xor     ecx, ecx; CodePage
0x180089dce  call    cs:__imp_MultiByteToWideChar
0x180089dd4  movsxd  rdi, eax
0x180089dd7  test    eax, eax
0x180089dd9  jz      short loc_180089E3F
0x180089ddb  xorps   xmm0, xmm0
0x180089dde  mov     [rbp+0D0h+Name], r12w
0x180089de3  movdqu  xmmword ptr [rbp+0D0h+ReferencedDomainName], xmm0
0x180089de8  mov     [rbp+0D0h+var_138], r12
0x180089dec  mov     rdx, rdi
0x180089def  lea     r8, [rbp+0D0h+Name]
0x180089df3  lea     rcx, [rbp+0D0h+ReferencedDomainName]
0x180089df7  call    ??$_Construct_n@AEB_W@?$vector@_WV?$allocator@_W@std@@@std@@AEAAX_KAEB_W@Z; std::vector<wchar_t>::_Construct_n<wchar_t const &>(unsigned __int64,wchar_t const &)
0x180089dfc  nop
0x180089dfd  mov     rax, [rbp+0D0h+ReferencedDomainName]
0x180089e01  lea     r8, [rbp+0D0h+lpMultiByteStr]
0x180089e05  cmp     [rbp+0D0h+var_118], rsi
0x180089e09  cmova   r8, [rbp+0D0h+lpMultiByteStr]; lpMultiByteStr
0x180089e0e  mov     [rsp+1D0h+cchWideChar], edi; cchWideChar
0x180089e12  mov     [rsp+1D0h+lpWideCharStr], rax; lpWideCharStr
0x180089e17  mov     r9d, r14d; cbMultiByte
0x180089e1a  xor     edx, edx; dwFlags
0x180089e1c  xor     ecx, ecx; CodePage
0x180089e1e  call    cs:__imp_MultiByteToWideChar
0x180089e24  test    eax, eax
0x180089e26  jz      short loc_180089E35
0x180089e28  mov     rdx, [rbp+0D0h+ReferencedDomainName]
0x180089e2c  mov     rcx, rbx
0x180089e2f  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x180089e34  nop
0x180089e35  lea     rcx, [rbp+0D0h+ReferencedDomainName]
0x180089e39  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x180089e3e  nop
0x180089e3f  lea     rcx, [rbp+0D0h+lpMultiByteStr]
0x180089e43  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180089e48  jmp     loc_18008A416
0x180089e4d  mov     rax, r14
0x180089e50  shr     rax, 1
0x180089e53  lea     r8, [rdi+rax*2]
0x180089e57  cmp     rdi, r8
0x180089e5a  jnb     short loc_180089E6E
0x180089e5c  lea     rcx, [r8-2]
0x180089e60  cmp     r12w, [rcx]
0x180089e64  jnz     short loc_180089E6E
0x180089e66  mov     r8, rcx
0x180089e69  cmp     rdi, rcx
0x180089e6c  jb      short loc_180089E5C
0x180089e6e  sub     r8, rdi
0x180089e71  sar     r8, 1
0x180089e74  mov     rdx, rdi
0x180089e77  mov     rcx, rbx
0x180089e7a  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x180089e7f  jmp     loc_18008A416
0x180089e84  lea     rdx, aNull; "null"
0x180089e8b  jmp     loc_18008A40E
0x180089e90  movsx   ecx, word ptr [rdi]
0x180089e93  jmp     loc_180089D0E
0x180089e98  mov     eax, 6
0x180089e9d  sub     edx, eax
0x180089e9f  jz      loc_180089F8A
0x180089ea5  sub     edx, 1
0x180089ea8  jz      loc_180089F83
0x180089eae  sub     edx, 1
0x180089eb1  jz      short loc_180089F19
0x180089eb3  sub     edx, 1
0x180089eb6  jz      short loc_180089EFD
0x180089eb8  cmp     edx, 1
0x180089ebb  jnz     loc_18008A416
0x180089ec1  lea     r9d, [rax+4]
0x180089ec5  mov     rcx, [rdi]
0x180089ec8  test    r8w, r8w
0x180089ecc  jz      short loc_180089ED4
0x180089ece  cmp     r9w, r8w
0x180089ed2  jnz     short loc_180089EE9
0x180089ed4  mov     r8d, 64h ; 'd'
0x180089eda  lea     rdx, [rbp+0D0h+S]
0x180089ede  call    cs:__imp__o__ui64tow_s
0x180089ee4  jmp     loc_18008A40A
0x180089ee9  mov     eax, 13h
0x180089eee  cmp     ax, r8w
0x180089ef2  jnz     loc_18008A416
0x180089ef8  jmp     loc_18008A1E2
0x180089efd  mov     r9d, 0Ah
0x180089f03  lea     r8d, [r9+5Ah]
0x180089f07  lea     rdx, [rbp+0D0h+S]
0x180089f0b  mov     rcx, [rdi]
0x180089f0e  call    cs:__imp__o__i64tow_s
0x180089f14  jmp     loc_18008A40A
0x180089f19  mov     ecx, [rdi]
0x180089f1b  test    r8w, r8w
0x180089f1f  jz      loc_180089D0E
0x180089f25  cmp     r8d, 1Bh
0x180089f29  ja      short loc_180089F3A
0x180089f2b  mov     edx, 8300500h
0x180089f30  bt      edx, r8d
0x180089f34  jb      loc_180089D0E
0x180089f3a  mov     eax, 17h
0x180089f3f  cmp     ax, r8w
0x180089f43  jnz     short loc_180089F57
0x180089f45  lea     rdx, [rbp+0D0h+S]; S
0x180089f49  mov     rcx, rdi; Addr
0x180089f4c  call    cs:__imp_RtlIpv4AddressToStringW
0x180089f52  jmp     loc_18008A205
0x180089f57  mov     eax, 12h
0x180089f5c  cmp     r8w, ax
0x180089f60  jz      short loc_180089FCE
0x180089f62  lea     eax, [r8-1Dh]
0x180089f66  cmp     ax, 3
0x180089f6a  jbe     short loc_180089FCE
0x180089f6c  mov     edx, r8d; wchar_t *
0x180089f6f  mov     r8d, ecx
0x180089f72  lea     rcx, aUnknownTdhOutt; "Unknown TDH_OUTTYPE [%u] for the TDH_IN"...
0x180089f79  call    ?ctAlwaysFatalCondition@ctl@@YAXPEB_WZZ; ctl::ctAlwaysFatalCondition(wchar_t const *,...)
0x180089f7e  jmp     loc_18008A416
0x180089f83  mov     ecx, [rdi]
0x180089f85  jmp     loc_180089D0E
0x180089f8a  test    r8w, r8w
0x180089f8e  jnz     short loc_180089F95
0x180089f90  movzx   ecx, word ptr [rdi]
0x180089f93  jmp     short loc_180089F9E
0x180089f95  movzx   ecx, word ptr [rdi]; netshort
0x180089f98  cmp     ax, r8w
0x180089f9c  jnz     short loc_180089FA6
0x180089f9e  movzx   ecx, cx
0x180089fa1  jmp     loc_180089D0E
0x180089fa6  mov     eax, 16h
0x180089fab  cmp     ax, r8w
0x180089faf  jnz     short loc_180089FBF
0x180089fb1  call    cs:__imp_ntohs
0x180089fb7  movzx   ecx, ax
0x180089fba  jmp     loc_180089D0E
0x180089fbf  mov     eax, 11h
0x180089fc4  cmp     ax, r8w
0x180089fc8  jnz     loc_18008A416
0x180089fce  mov     r9d, 10h
0x180089fd4  lea     rdx, [rbp+0D0h+S]
0x180089fd8  mov     r8d, 64h ; 'd'
0x180089fde  call    cs:__imp__o__itow_s
0x180089fe4  jmp     loc_18008A1F6
0x180089fe9  movss   xmm3, dword ptr [rdi]
0x180089fed  cvtps2pd xmm3, xmm3
0x180089ff0  movq    r9, xmm3
0x180089ff5  lea     r8, Format; "%f"
0x180089ffc  mov     edx, 64h ; 'd'; BufferCount
0x18008a001  lea     rcx, [rbp+0D0h+S]; Buffer
0x18008a005  call    swprintf_s
0x18008a00a  jmp     loc_18008A205
0x18008a00f  mov     eax, 11h
0x18008a014  cmp     edx, eax
0x18008a016  ja      loc_18008A1B9
0x18008a01c  jz      loc_18008A199
0x18008a022  sub     edx, 0Ch
0x18008a025  jz      loc_18008A190
0x18008a02b  sub     edx, 1
0x18008a02e  jz      loc_18008A17B
0x18008a034  sub     edx, 1
0x18008a037  jz      loc_18008A0BE
0x18008a03d  sub     edx, 1
0x18008a040  jz      short loc_18008A078
0x18008a042  cmp     edx, 1
0x18008a045  jnz     loc_18008A416
0x18008a04b  lea     eax, [rdx+3]
0x18008a04e  cmp     r14d, eax
0x18008a051  jnz     short loc_18008A05A
0x18008a053  mov     ecx, [rdi]
0x18008a055  jmp     loc_180089FCE
0x18008a05a  cmp     r14d, 8
0x18008a05e  jz      loc_18008A1DF
0x18008a064  mov     edx, r14d
0x18008a067  lea     rcx, aTdhIntypePoint; "TDH_INTYPE_POINTER was called with a %d"...
0x18008a06e  call    wprintf
0x18008a073  jmp     loc_18008A416
0x18008a078  mov     esi, 10h
0x18008a07d  cmp     r14d, esi
0x18008a080  jnz     loc_18008A416
0x18008a086  mov     [rsp+1D0h+StringUuid], r12
0x18008a08b  lea     rdx, [rsp+1D0h+StringUuid]; StringUuid
0x18008a090  mov     rcx, rdi; Uuid
0x18008a093  call    cs:__imp_UuidToStringW
0x18008a099  test    eax, eax
0x18008a09b  jnz     loc_18008A416
0x18008a0a1  mov     rdx, [rsp+1D0h+StringUuid]
  ... truncated ...
```
