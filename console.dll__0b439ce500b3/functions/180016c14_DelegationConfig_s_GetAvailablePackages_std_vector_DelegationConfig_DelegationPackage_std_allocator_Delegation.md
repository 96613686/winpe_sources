# DelegationConfig::s_GetAvailablePackages(std::vector<DelegationConfig::DelegationPackage,std::allocator<DelegationConfig::DelegationPackage>> &,DelegationConfig::DelegationPackage &)

- ea: `0x180016c14`
- end: `0x180017362`
- name: `?s_GetAvailablePackages@DelegationConfig@@SAJAEAV?$vector@UDelegationPackage@DelegationConfig@@V?$allocator@UDelegationPackage@DelegationConfig@@@std@@@std@@AEAUDelegationPackage@1@@Z`
- size: `1870`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000752c`

## callees

- `0x1800015b0`
- `0x1800058a4`
- `0x180008714`
- `0x180008c34`
- `0x180008c74`
- `0x180008cc0`
- `0x18000db24`
- `0x18000eb2c`
- `0x18000eb3c`
- `0x180014a84`
- `0x180014c20`
- `0x180014fec`
- `0x180015010`
- `0x180015028`
- `0x18001507c`
- `0x180015310`
- `0x1800153d0`
- `0x180015880`
- `0x180016c14`
- `0x180017368`
- `0x180018d00`

## import_xrefs

- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180017240`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180017240`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800170bf`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001720e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001732c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800170bf`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001720e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001732c`

## string_xrefs

- `0x180016e4c`: `onecore\windows\core\console\open\src\propslib\delegationconfig.cpp`
- `0x180016e88`: `onecore\windows\core\console\open\src\propslib\delegationconfig.cpp`
- `0x180016ffc`: `onecore\windows\core\console\open\src\propslib\delegationconfig.cpp`
- `0x180016e31`: `com.microsoft.windows.console.host`
- `0x180016e6d`: `com.microsoft.windows.terminal.host`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 DelegationConfig::s_GetAvailablePackages()
{
  __int64 v0; // rdx
  __int64 v1; // rdx
  int v2; // eax
  int v3; // eax
  _QWORD *i; // rbx
  _QWORD *v5; // r12
  _QWORD *j; // rdi
  _QWORD *v7; // r14
  __int64 v8; // rax
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rdx
  char v12; // cl
  __int64 DelegationPair; // rax
  _OWORD *v15; // rbx
  __int64 v16; // rdi
  char v17; // al
  __int64 v18; // rdx
  char v19; // al
  int v20; // [rsp+20h] [rbp-188h] BYREF
  __int128 v21; // [rsp+28h] [rbp-180h] BYREF
  __int64 v22; // [rsp+38h] [rbp-170h]
  __int128 v23; // [rsp+40h] [rbp-168h] BYREF
  __int64 v24; // [rsp+50h] [rbp-158h]
  _OWORD Buf2[2]; // [rsp+60h] [rbp-148h] BYREF
  int v26; // [rsp+80h] [rbp-128h]
  _BYTE v27[40]; // [rsp+88h] [rbp-120h] BYREF
  _BYTE v28[36]; // [rsp+B0h] [rbp-F8h] BYREF
  int v29; // [rsp+D4h] [rbp-D4h]
  _BYTE v30[32]; // [rsp+D8h] [rbp-D0h] BYREF
  _BYTE v31[32]; // [rsp+F8h] [rbp-B0h] BYREF
  _BYTE v32[32]; // [rsp+118h] [rbp-90h] BYREF
  _BYTE v33[32]; // [rsp+138h] [rbp-70h] BYREF
  __int64 v34; // [rsp+158h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+0h]

  wil::CoInitializeEx(&v20);
  if ( g_availablePackages != (_QWORD)xmmword_180023990 )
  {
    std::_Destroy_range<std::allocator<DelegationConfig::DelegationPackage>>();
    *(_QWORD *)&xmmword_180023990 = g_availablePackages;
  }
  *(_OWORD *)v28 = DelegationConfig::DefaultDelegationPair;
  memset(&v28[16], 0, 20);
  v29 = 0;
  std::wstring::wstring(v30);
  std::wstring::wstring(v31);
  std::wstring::wstring(v32);
  std::wstring::wstring(v33);
  v34 = 0;
  v0 = xmmword_180023990;
  if ( (_QWORD)xmmword_180023990 == *((_QWORD *)&xmmword_180023990 + 1) )
  {
    std::vector<DelegationConfig::DelegationPackage>::_Emplace_reallocate<DelegationConfig::DelegationPackage>(
      0,
      xmmword_180023990,
      v28);
  }
  else
  {
    *(_OWORD *)xmmword_180023990 = *(_OWORD *)v28;
    *(_OWORD *)(v0 + 16) = *(_OWORD *)&v28[16];
    *(_DWORD *)(v0 + 32) = *(_DWORD *)&v28[32];
    DelegationConfig::PackageInfo::PackageInfo(v0 + 40, v30);
    *(_QWORD *)&xmmword_180023990 = xmmword_180023990 + 176;
  }
  DelegationConfig::PackageInfo::~PackageInfo((DelegationConfig::PackageInfo *)v30);
  *(_OWORD *)v28 = DelegationConfig::ConhostDelegationPair;
  *(_OWORD *)&v28[16] = xmmword_18001D480;
  *(_DWORD *)&v28[32] = 2107404511;
  v29 = 0;
  std::wstring::wstring(v30);
  std::wstring::wstring(v31);
  std::wstring::wstring(v32);
  std::wstring::wstring(v33);
  v34 = 0;
  v1 = xmmword_180023990;
  if ( (_QWORD)xmmword_180023990 == *((_QWORD *)&xmmword_180023990 + 1) )
  {
    std::vector<DelegationConfig::DelegationPackage>::_Emplace_reallocate<DelegationConfig::DelegationPackage>(
      0,
      xmmword_180023990,
      v28);
  }
  else
  {
    *(_OWORD *)xmmword_180023990 = *(_OWORD *)v28;
    *(_OWORD *)(v1 + 16) = *(_OWORD *)&v28[16];
    *(_DWORD *)(v1 + 32) = *(_DWORD *)&v28[32];
    DelegationConfig::PackageInfo::PackageInfo(v1 + 40, v30);
    *(_QWORD *)&xmmword_180023990 = xmmword_180023990 + 176;
  }
  DelegationConfig::PackageInfo::~PackageInfo((DelegationConfig::PackageInfo *)v30);
  std::vector<DelegationConfig::DelegationBase>::vector<DelegationConfig::DelegationBase>(&v23);
  v2 = lookupCatalog(L"com.microsoft.windows.console.host", (__int64)&v23);
  if ( v2 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xAB,
      (unsigned int)"onecore\\windows\\core\\console\\open\\src\\propslib\\delegationconfig.cpp",
      (const char *)(unsigned int)v2,
      v20);
  std::vector<DelegationConfig::DelegationBase>::vector<DelegationConfig::DelegationBase>(&v21);
  v3 = lookupCatalog(L"com.microsoft.windows.terminal.host", (__int64)&v21);
  if ( v3 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xAE,
      (unsigned int)"onecore\\windows\\core\\console\\open\\src\\propslib\\delegationconfig.cpp",
      (const char *)(unsigned int)v3,
      v20);
  v5 = (_QWORD *)*((_QWORD *)&v21 + 1);
  for ( i = (_QWORD *)v21; i != v5; i += 19 )
  {
    v7 = (_QWORD *)*((_QWORD *)&v23 + 1);
    for ( j = (_QWORD *)v23; j != v7; j += 19 )
    {
      if ( DelegationConfig::PackageInfo::IsFromSamePackage(
             (DelegationConfig::PackageInfo *)(i + 2),
             (const struct DelegationConfig::PackageInfo *)(j + 2)) )
      {
        memset(&v28[4], 0, 32);
        DelegationConfig::PackageInfo::PackageInfo((DelegationConfig::PackageInfo *)v30);
        v8 = j[1];
        v9 = i[1];
        *(_DWORD *)v28 = 3;
        *(_QWORD *)&v28[4] = *j;
        *(_QWORD *)&v28[12] = v8;
        *(_QWORD *)&v28[20] = *i;
        *(_QWORD *)&v28[28] = v9;
        DelegationConfig::PackageInfo::operator=(v30, i + 2);
        v11 = xmmword_180023990;
        if ( (_QWORD)xmmword_180023990 == *((_QWORD *)&xmmword_180023990 + 1) )
        {
          std::vector<DelegationConfig::DelegationPackage>::_Emplace_reallocate<DelegationConfig::DelegationPackage>(
            v10,
            xmmword_180023990,
            v28);
        }
        else
        {
          *(_DWORD *)xmmword_180023990 = *(_DWORD *)v28;
          *(_OWORD *)(v11 + 4) = *(_OWORD *)&v28[4];
          *(_OWORD *)(v11 + 20) = *(_OWORD *)&v28[20];
          DelegationConfig::PackageInfo::PackageInfo(v11 + 40, v30);
          *(_QWORD *)&xmmword_180023990 = xmmword_180023990 + 176;
        }
        DelegationConfig::PackageInfo::~PackageInfo((DelegationConfig::PackageInfo *)v30);
        break;
      }
    }
  }
  if ( g_availablePackages == (_QWORD)xmmword_180023990 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC3,
      (unsigned int)"onecore\\windows\\core\\console\\open\\src\\propslib\\delegationconfig.cpp",
      (const char *)0x80004005LL,
      v20);
    if ( (_QWORD)v21 )
    {
      std::_Destroy_range<std::allocator<DelegationConfig::DelegationBase>>(v21, *((_QWORD *)&v21 + 1));
      std::_Deallocate<16>(v21, 8 * ((v22 - (__int64)v21) >> 3));
      v21 = 0;
      v22 = 0;
    }
    if ( (_QWORD)v23 )
    {
      std::_Destroy_range<std::allocator<DelegationConfig::DelegationBase>>(v23, *((_QWORD *)&v23 + 1));
      std::_Deallocate<16>(v23, 8 * ((v24 - (__int64)v23) >> 3));
      v23 = 0;
      v24 = 0;
    }
    v12 = v20;
    LOBYTE(v20) = 0;
    if ( v12 )
      CoUninitialize();
    return 2147500037LL;
  }
  else
  {
    DelegationPair = DelegationConfig::s_GetDelegationPair(v27);
    Buf2[0] = *(_OWORD *)DelegationPair;
    Buf2[1] = *(_OWORD *)(DelegationPair + 16);
    v26 = *(_DWORD *)(DelegationPair + 32);
    v15 = (_OWORD *)std::vector<DelegationConfig::DelegationPackage>::_Unchecked_begin();
    v16 = std::vector<DelegationConfig::DelegationPackage>::_Unchecked_end();
    while ( v15 != (_OWORD *)v16 )
    {
      if ( !memcmp_0(v15, Buf2, 0x24u) )
      {
        g_selectedPackage = *v15;
        xmmword_180023290 = v15[1];
        dword_1800232A0 = *((_DWORD *)v15 + 8);
        DelegationConfig::PackageInfo::operator=(qword_1800232A8, (char *)v15 + 40);
        if ( (_QWORD)v21 )
        {
          std::_Destroy_range<std::allocator<DelegationConfig::DelegationBase>>(v21, *((_QWORD *)&v21 + 1));
          std::_Deallocate<16>(v21, 8 * ((v22 - (__int64)v21) >> 3));
          v21 = 0;
          v22 = 0;
        }
        if ( (_QWORD)v23 )
        {
          std::_Destroy_range<std::allocator<DelegationConfig::DelegationBase>>(v23, *((_QWORD *)&v23 + 1));
          std::_Deallocate<16>(v23, 8 * ((v24 - (__int64)v23) >> 3));
          v23 = 0;
          v24 = 0;
        }
        v17 = v20;
        LOBYTE(v20) = 0;
        if ( v17 )
          CoUninitialize();
        return 0;
      }
      v15 += 11;
    }
    v18 = g_availablePackages;
    if ( (_QWORD)xmmword_180023990 == g_availablePackages )
      std::_Xout_of_range("invalid vector subscript");
    g_selectedPackage = *(_OWORD *)v18;
    xmmword_180023290 = *(_OWORD *)(v18 + 16);
    dword_1800232A0 = *(_DWORD *)(v18 + 32);
    DelegationConfig::PackageInfo::operator=(qword_1800232A8, v18 + 40);
    if ( (_QWORD)v21 )
    {
      std::_Destroy_range<std::allocator<DelegationConfig::DelegationBase>>(v21, *((_QWORD *)&v21 + 1));
      std::_Deallocate<16>(v21, 8 * ((v22 - (__int64)v21) >> 3));
      v21 = 0;
      v22 = 0;
    }
    if ( (_QWORD)v23 )
    {
      std::_Destroy_range<std::allocator<DelegationConfig::DelegationBase>>(v23, *((_QWORD *)&v23 + 1));
      std::_Deallocate<16>(v23, 8 * ((v24 - (__int64)v23) >> 3));
      v23 = 0;
      v24 = 0;
    }
    v19 = v20;
    LOBYTE(v20) = 0;
    if ( v19 )
      CoUninitialize();
    return 0;
  }
}

```

## disassembly

```asm
0x180016c14  push    rbx
0x180016c16  push    rsi
0x180016c17  push    rdi
0x180016c18  push    r12
0x180016c1a  push    r14
0x180016c1c  push    r15
0x180016c1e  sub     rsp, 178h
0x180016c25  mov     rax, cs:__security_cookie
0x180016c2c  xor     rax, rsp
0x180016c2f  mov     [rsp+1A8h+var_48], rax
0x180016c37  lea     rcx, [rsp+1A8h+var_188]
0x180016c3c  call    ?CoInitializeEx@wil@@YA?AV?$unique_call@P6AXXZ$1?CoUninitialize@@YAXXZ$00@1@K@Z; wil::CoInitializeEx(ulong)
0x180016c41  nop
0x180016c42  mov     rdx, qword ptr cs:xmmword_180023990
0x180016c49  mov     rcx, cs:?g_availablePackages@@3V?$vector@UDelegationPackage@DelegationConfig@@V?$allocator@UDelegationPackage@DelegationConfig@@@std@@@std@@A; std::vector<DelegationConfig::DelegationPackage> g_availablePackages
0x180016c50  cmp     rcx, rdx
0x180016c53  jz      short loc_180016C68
0x180016c55  call    ??$_Destroy_range@V?$allocator@UDelegationPackage@DelegationConfig@@@std@@@std@@YAXPEAUDelegationPackage@DelegationConfig@@QEAU12@AEAV?$allocator@UDelegationPackage@DelegationConfig@@@0@@Z; std::_Destroy_range<std::allocator<DelegationConfig::DelegationPackage>>(DelegationConfig::DelegationPackage *,DelegationConfig::DelegationPackage * const,std::allocator<DelegationConfig::DelegationPackage> &)
0x180016c5a  mov     rax, cs:?g_availablePackages@@3V?$vector@UDelegationPackage@DelegationConfig@@V?$allocator@UDelegationPackage@DelegationConfig@@@std@@@std@@A; std::vector<DelegationConfig::DelegationPackage> g_availablePackages
0x180016c61  mov     qword ptr cs:xmmword_180023990, rax
0x180016c68  movups  xmm0, cs:?DefaultDelegationPair@DelegationConfig@@2UDelegationPair@1@B; DelegationConfig::DelegationPair const DelegationConfig::DefaultDelegationPair
0x180016c6f  movaps  [rsp+1A8h+var_F8], xmm0
0x180016c77  movups  xmm1, cs:xmmword_18001D4A8
0x180016c7e  movaps  xmmword ptr [rsp+1A8h+var_E8], xmm1
0x180016c86  mov     eax, cs:dword_18001D4B8
0x180016c8c  mov     dword ptr [rsp+1A8h+var_E8+10h], eax
0x180016c93  xor     eax, eax
0x180016c95  mov     [rsp+1A8h+var_D4], eax
0x180016c9c  lea     rcx, [rsp+1A8h+var_D0]
0x180016ca4  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180016ca9  lea     rcx, [rsp+1A8h+var_B0]
0x180016cb1  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180016cb6  lea     rcx, [rsp+1A8h+var_90]
0x180016cbe  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180016cc3  lea     rcx, [rsp+1A8h+var_70]
0x180016ccb  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180016cd0  xor     ecx, ecx
0x180016cd2  mov     [rsp+1A8h+var_50], rcx
0x180016cda  mov     rdx, qword ptr cs:xmmword_180023990
0x180016ce1  cmp     rdx, qword ptr cs:xmmword_180023990+8
0x180016ce8  jz      short loc_180016D2A
0x180016cea  movaps  xmm0, [rsp+1A8h+var_F8]
0x180016cf2  movups  xmmword ptr [rdx], xmm0
0x180016cf5  movaps  xmm1, xmmword ptr [rsp+1A8h+var_E8]
0x180016cfd  movups  xmmword ptr [rdx+10h], xmm1
0x180016d01  mov     eax, dword ptr [rsp+1A8h+var_E8+10h]
0x180016d08  mov     [rdx+20h], eax
0x180016d0b  lea     rcx, [rdx+28h]
0x180016d0f  lea     rdx, [rsp+1A8h+var_D0]
0x180016d17  call    ??0PackageInfo@DelegationConfig@@QEAA@$$QEAU01@@Z; DelegationConfig::PackageInfo::PackageInfo(DelegationConfig::PackageInfo &&)
0x180016d1c  mov     esi, 0B0h
0x180016d21  add     qword ptr cs:xmmword_180023990, rsi
0x180016d28  jmp     short loc_180016D3C
0x180016d2a  lea     r8, [rsp+1A8h+var_F8]
0x180016d32  call    ??$_Emplace_reallocate@UDelegationPackage@DelegationConfig@@@?$vector@UDelegationPackage@DelegationConfig@@V?$allocator@UDelegationPackage@DelegationConfig@@@std@@@std@@AEAAPEAUDelegationPackage@DelegationConfig@@QEAU23@$$QEAU23@@Z; std::vector<DelegationConfig::DelegationPackage>::_Emplace_reallocate<DelegationConfig::DelegationPackage>(DelegationConfig::DelegationPackage * const,DelegationConfig::DelegationPackage &&)
0x180016d37  mov     esi, 0B0h
0x180016d3c  lea     rcx, [rsp+1A8h+var_D0]; this
0x180016d44  call    ??1PackageInfo@DelegationConfig@@QEAA@XZ; DelegationConfig::PackageInfo::~PackageInfo(void)
0x180016d49  movups  xmm0, cs:?ConhostDelegationPair@DelegationConfig@@2UDelegationPair@1@B; DelegationConfig::DelegationPair const DelegationConfig::ConhostDelegationPair
0x180016d50  movaps  [rsp+1A8h+var_F8], xmm0
0x180016d58  movups  xmm1, cs:xmmword_18001D480
0x180016d5f  movaps  xmmword ptr [rsp+1A8h+var_E8], xmm1
0x180016d67  mov     eax, cs:dword_18001D490
0x180016d6d  mov     dword ptr [rsp+1A8h+var_E8+10h], eax
0x180016d74  xor     eax, eax
0x180016d76  mov     [rsp+1A8h+var_D4], eax
0x180016d7d  lea     rcx, [rsp+1A8h+var_D0]
0x180016d85  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180016d8a  lea     rcx, [rsp+1A8h+var_B0]
0x180016d92  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180016d97  lea     rcx, [rsp+1A8h+var_90]
0x180016d9f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180016da4  lea     rcx, [rsp+1A8h+var_70]
0x180016dac  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180016db1  xor     ecx, ecx
0x180016db3  mov     [rsp+1A8h+var_50], rcx
0x180016dbb  mov     rdx, qword ptr cs:xmmword_180023990
0x180016dc2  cmp     rdx, qword ptr cs:xmmword_180023990+8
0x180016dc9  jz      short loc_180016E06
0x180016dcb  movaps  xmm0, [rsp+1A8h+var_F8]
0x180016dd3  movups  xmmword ptr [rdx], xmm0
0x180016dd6  movaps  xmm1, xmmword ptr [rsp+1A8h+var_E8]
0x180016dde  movups  xmmword ptr [rdx+10h], xmm1
0x180016de2  mov     eax, dword ptr [rsp+1A8h+var_E8+10h]
0x180016de9  mov     [rdx+20h], eax
0x180016dec  lea     rcx, [rdx+28h]
0x180016df0  lea     rdx, [rsp+1A8h+var_D0]
0x180016df8  call    ??0PackageInfo@DelegationConfig@@QEAA@$$QEAU01@@Z; DelegationConfig::PackageInfo::PackageInfo(DelegationConfig::PackageInfo &&)
0x180016dfd  add     qword ptr cs:xmmword_180023990, rsi
0x180016e04  jmp     short loc_180016E14
0x180016e06  lea     r8, [rsp+1A8h+var_F8]
0x180016e0e  call    ??$_Emplace_reallocate@UDelegationPackage@DelegationConfig@@@?$vector@UDelegationPackage@DelegationConfig@@V?$allocator@UDelegationPackage@DelegationConfig@@@std@@@std@@AEAAPEAUDelegationPackage@DelegationConfig@@QEAU23@$$QEAU23@@Z; std::vector<DelegationConfig::DelegationPackage>::_Emplace_reallocate<DelegationConfig::DelegationPackage>(DelegationConfig::DelegationPackage * const,DelegationConfig::DelegationPackage &&)
0x180016e13  nop
0x180016e14  lea     rcx, [rsp+1A8h+var_D0]; this
0x180016e1c  call    ??1PackageInfo@DelegationConfig@@QEAA@XZ; DelegationConfig::PackageInfo::~PackageInfo(void)
0x180016e21  lea     rcx, [rsp+1A8h+var_168]
0x180016e26  call    ??0?$vector@UDelegationBase@DelegationConfig@@V?$allocator@UDelegationBase@DelegationConfig@@@std@@@std@@QEAA@XZ; std::vector<DelegationConfig::DelegationBase>::vector<DelegationConfig::DelegationBase>(void)
0x180016e2b  nop
0x180016e2c  lea     rdx, [rsp+1A8h+var_168]
0x180016e31  lea     rcx, aComMicrosoftWi; "com.microsoft.windows.console.host"
0x180016e38  call    _lookupCatalog
0x180016e3d  mov     rcx, [rsp+1A8h]; this
0x180016e45  test    eax, eax
0x180016e47  jns     short loc_180016E5D
0x180016e49  mov     r9d, eax; char *
0x180016e4c  lea     r8, aOnecoreWindows; "onecore\\windows\\core\\console\\open\\"...
0x180016e53  mov     edx, 0ABh; void *
0x180016e58  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180016e5d  lea     rcx, [rsp+1A8h+var_180]
0x180016e62  call    ??0?$vector@UDelegationBase@DelegationConfig@@V?$allocator@UDelegationBase@DelegationConfig@@@std@@@std@@QEAA@XZ; std::vector<DelegationConfig::DelegationBase>::vector<DelegationConfig::DelegationBase>(void)
0x180016e67  nop
0x180016e68  lea     rdx, [rsp+1A8h+var_180]
0x180016e6d  lea     rcx, aComMicrosoftWi_0; "com.microsoft.windows.terminal.host"
0x180016e74  call    _lookupCatalog
0x180016e79  mov     rcx, [rsp+1A8h]; this
0x180016e81  test    eax, eax
0x180016e83  jns     short loc_180016E99
0x180016e85  mov     r9d, eax; char *
0x180016e88  lea     r8, aOnecoreWindows; "onecore\\windows\\core\\console\\open\\"...
0x180016e8f  mov     edx, 0AEh; void *
0x180016e94  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180016e99  mov     rbx, qword ptr [rsp+1A8h+var_180]
0x180016e9e  mov     r12, qword ptr [rsp+1A8h+var_180+8]
0x180016ea3  cmp     rbx, r12
0x180016ea6  jz      loc_180016FD8
0x180016eac  mov     rdi, qword ptr [rsp+1A8h+var_168]
0x180016eb1  mov     r14, qword ptr [rsp+1A8h+var_168+8]
0x180016eb6  cmp     rdi, r14
0x180016eb9  jz      loc_180016FC0
0x180016ebf  lea     rdx, [rdi+10h]; struct DelegationConfig::PackageInfo *
0x180016ec3  lea     rcx, [rbx+10h]; this
0x180016ec7  call    ?IsFromSamePackage@PackageInfo@DelegationConfig@@QEBA_NAEBU12@@Z; DelegationConfig::PackageInfo::IsFromSamePackage(DelegationConfig::PackageInfo const &)
0x180016ecc  test    al, al
0x180016ece  jz      loc_180016FCC
0x180016ed4  xorps   xmm0, xmm0
0x180016ed7  movups  [rsp+1A8h+var_F8+4], xmm0
0x180016edf  xorps   xmm1, xmm1
0x180016ee2  movups  xmmword ptr [rsp+1A8h+var_E8+4], xmm1
0x180016eea  lea     rcx, [rsp+1A8h+var_D0]; this
0x180016ef2  call    ??0PackageInfo@DelegationConfig@@QEAA@XZ; DelegationConfig::PackageInfo::PackageInfo(void)
0x180016ef7  nop
0x180016ef8  mov     rax, [rdi+8]
0x180016efc  mov     rcx, [rbx+8]
0x180016f00  mov     dword ptr [rsp+1A8h+var_F8], 3
0x180016f0b  mov     r8, [rdi]
0x180016f0e  mov     qword ptr [rsp+1A8h+var_F8+4], r8
0x180016f16  mov     qword ptr [rsp+1A8h+var_F8+0Ch], rax
0x180016f1e  mov     rax, [rbx]
0x180016f21  mov     qword ptr [rsp+1A8h+var_E8+4], rax
0x180016f29  mov     qword ptr [rsp+1A8h+var_E8+0Ch], rcx
0x180016f31  lea     rdx, [rbx+10h]
0x180016f35  lea     rcx, [rsp+1A8h+var_D0]
0x180016f3d  call    ??4PackageInfo@DelegationConfig@@QEAAAEAU01@AEBU01@@Z; DelegationConfig::PackageInfo::operator=(DelegationConfig::PackageInfo const &)
0x180016f42  mov     rdx, qword ptr cs:xmmword_180023990
0x180016f49  cmp     rdx, qword ptr cs:xmmword_180023990+8
0x180016f50  jz      short loc_180016FA5
0x180016f52  mov     eax, dword ptr [rsp+1A8h+var_F8]
0x180016f59  mov     [rdx], eax
0x180016f5b  mov     rax, qword ptr [rsp+1A8h+var_F8+4]
0x180016f63  mov     [rdx+4], rax
0x180016f67  mov     rax, qword ptr [rsp+1A8h+var_F8+0Ch]
0x180016f6f  mov     [rdx+0Ch], rax
0x180016f73  mov     rax, qword ptr [rsp+1A8h+var_E8+4]
0x180016f7b  mov     [rdx+14h], rax
0x180016f7f  mov     rax, qword ptr [rsp+1A8h+var_E8+0Ch]
0x180016f87  mov     [rdx+1Ch], rax
0x180016f8b  lea     rcx, [rdx+28h]
0x180016f8f  lea     rdx, [rsp+1A8h+var_D0]
0x180016f97  call    ??0PackageInfo@DelegationConfig@@QEAA@$$QEAU01@@Z; DelegationConfig::PackageInfo::PackageInfo(DelegationConfig::PackageInfo &&)
0x180016f9c  add     qword ptr cs:xmmword_180023990, rsi
0x180016fa3  jmp     short loc_180016FB3
0x180016fa5  lea     r8, [rsp+1A8h+var_F8]
0x180016fad  call    ??$_Emplace_reallocate@UDelegationPackage@DelegationConfig@@@?$vector@UDelegationPackage@DelegationConfig@@V?$allocator@UDelegationPackage@DelegationConfig@@@std@@@std@@AEAAPEAUDelegationPackage@DelegationConfig@@QEAU23@$$QEAU23@@Z; std::vector<DelegationConfig::DelegationPackage>::_Emplace_reallocate<DelegationConfig::DelegationPackage>(DelegationConfig::DelegationPackage * const,DelegationConfig::DelegationPackage &&)
0x180016fb2  nop
0x180016fb3  lea     rcx, [rsp+1A8h+var_D0]; this
0x180016fbb  call    ??1PackageInfo@DelegationConfig@@QEAA@XZ; DelegationConfig::PackageInfo::~PackageInfo(void)
0x180016fc0  add     rbx, 98h
0x180016fc7  jmp     loc_180016EA3
0x180016fcc  add     rdi, 98h
0x180016fd3  jmp     loc_180016EB6
0x180016fd8  mov     rax, qword ptr cs:xmmword_180023990
0x180016fdf  cmp     cs:?g_availablePackages@@3V?$vector@UDelegationPackage@DelegationConfig@@V?$allocator@UDelegationPackage@DelegationConfig@@@std@@@std@@A, rax; std::vector<DelegationConfig::DelegationPackage> g_availablePackages
0x180016fe6  jnz     loc_1800170D2
0x180016fec  mov     rcx, [rsp+1A8h]; this
0x180016ff4  mov     edi, 80004005h
0x180016ff9  mov     r9d, edi; char *
0x180016ffc  lea     r8, aOnecoreWindows; "onecore\\windows\\core\\console\\open\\"...
0x180017003  mov     edx, 0C3h; void *
0x180017008  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001700d  nop
0x18001700e  mov     rcx, qword ptr [rsp+1A8h+var_180]
0x180017013  test    rcx, rcx
0x180017016  jz      short loc_180017061
0x180017018  mov     rdx, qword ptr [rsp+1A8h+var_180+8]
0x18001701d  call    ??$_Destroy_range@V?$allocator@UDelegationBase@DelegationConfig@@@std@@@std@@YAXPEAUDelegationBase@DelegationConfig@@QEAU12@AEAV?$allocator@UDelegationBase@DelegationConfig@@@0@@Z; std::_Destroy_range<std::allocator<DelegationConfig::DelegationBase>>(DelegationConfig::DelegationBase *,DelegationConfig::DelegationBase * const,std::allocator<DelegationConfig::DelegationBase> &)
0x180017022  mov     rcx, qword ptr [rsp+1A8h+var_180]
0x180017027  mov     rax, [rsp+1A8h+var_170]
0x18001702c  sub     rax, rcx
0x18001702f  sar     rax, 3
0x180017033  mov     rbx, 86BCA1AF286BCA1Bh
0x18001703d  imul    rax, rbx
0x180017041  imul    rdx, rax, 98h
0x180017048  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001704d  xorps   xmm0, xmm0
0x180017050  movdqu  [rsp+1A8h+var_180], xmm0
0x180017056  mov     [rsp+1A8h+var_170], 0
0x18001705f  jmp     short loc_18001706B
0x180017061  mov     rbx, 86BCA1AF286BCA1Bh
0x18001706b  mov     rcx, qword ptr [rsp+1A8h+var_168]
0x180017070  test    rcx, rcx
0x180017073  jz      short loc_1800170B2
0x180017075  mov     rdx, qword ptr [rsp+1A8h+var_168+8]
0x18001707a  call    ??$_Destroy_range@V?$allocator@UDelegationBase@DelegationConfig@@@std@@@std@@YAXPEAUDelegationBase@DelegationConfig@@QEAU12@AEAV?$allocator@UDelegationBase@DelegationConfig@@@0@@Z; std::_Destroy_range<std::allocator<DelegationConfig::DelegationBase>>(DelegationConfig::DelegationBase *,DelegationConfig::DelegationBase * const,std::allocator<DelegationConfig::DelegationBase> &)
0x18001707f  mov     rcx, qword ptr [rsp+1A8h+var_168]
0x180017084  mov     rax, [rsp+1A8h+var_158]
0x180017089  sub     rax, rcx
0x18001708c  sar     rax, 3
0x180017090  imul    rax, rbx
0x180017094  imul    rdx, rax, 98h
0x18001709b  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800170a0  xorps   xmm0, xmm0
0x1800170a3  movdqu  [rsp+1A8h+var_168], xmm0
0x1800170a9  mov     [rsp+1A8h+var_158], 0
0x1800170b2  mov     cl, byte ptr [rsp+1A8h+var_188]
0x1800170b6  mov     byte ptr [rsp+1A8h+var_188], 0
0x1800170bb  test    cl, cl
0x1800170bd  jz      short loc_1800170CB
0x1800170bf  call    cs:__imp_CoUninitialize
0x1800170c6  nop     dword ptr [rax+rax+00h]
0x1800170cb  mov     eax, edi
0x1800170cd  jmp     loc_180017340
0x1800170d2  lea     rcx, [rsp+1A8h+var_120]
0x1800170da  call    ?s_GetDelegationPair@DelegationConfig@@SA?AUDelegationPair@1@XZ; DelegationConfig::s_GetDelegationPair(void)
0x1800170df  movups  xmm0, xmmword ptr [rax]
0x1800170e2  movups  [rsp+1A8h+Buf2], xmm0
0x1800170e7  movups  xmm1, xmmword ptr [rax+10h]
0x1800170eb  movups  [rsp+1A8h+var_138], xmm1
0x1800170f0  mov     eax, [rax+20h]
0x1800170f3  mov     [rsp+1A8h+var_128], eax
0x1800170fa  call    ?_Unchecked_begin@?$vector@UDelegationPackage@DelegationConfig@@V?$allocator@UDelegationPackage@DelegationConfig@@@std@@@std@@QEBAPEBUDelegationPackage@DelegationConfig@@XZ; std::vector<DelegationConfig::DelegationPackage>::_Unchecked_begin(void)
0x1800170ff  mov     rbx, rax
0x180017102  call    ?_Unchecked_end@?$vector@UDelegationPackage@DelegationConfig@@V?$allocator@UDelegationPackage@DelegationConfig@@@std@@@std@@QEBAPEBUDelegationPackage@DelegationConfig@@XZ; std::vector<DelegationConfig::DelegationPackage>::_Unchecked_end(void)
0x180017107  mov     rdi, rax
0x18001710a  cmp     rbx, rdi
0x18001710d  jz      loc_180017229
0x180017113  mov     r8d, 24h ; '$'; Size
0x180017119  lea     rdx, [rsp+1A8h+Buf2]; Buf2
0x18001711e  mov     rcx, rbx; Buf1
0x180017121  call    memcmp_0
0x180017126  test    eax, eax
0x180017128  jnz     loc_180017221
0x18001712e  movups  xmm0, xmmword ptr [rbx]
0x180017131  movaps  cs:?g_selectedPackage@@3UDelegationPackage@DelegationConfig@@A, xmm0; DelegationConfig::DelegationPackage g_selectedPackage
0x180017138  movups  xmm1, xmmword ptr [rbx+10h]
0x18001713c  movaps  cs:xmmword_180023290, xmm1
0x180017143  mov     eax, [rbx+20h]
0x180017146  mov     cs:dword_1800232A0, eax
0x18001714c  lea     rdx, [rbx+28h]
0x180017150  lea     rcx, qword_1800232A8
0x180017157  call    ??4PackageInfo@DelegationConfig@@QEAAAEAU01@AEBU01@@Z; DelegationConfig::PackageInfo::operator=(DelegationConfig::PackageInfo const &)
0x18001715c  nop
0x18001715d  mov     rcx, qword ptr [rsp+1A8h+var_180]
0x180017162  test    rcx, rcx
0x180017165  jz      short loc_1800171B0
0x180017167  mov     rdx, qword ptr [rsp+1A8h+var_180+8]
0x18001716c  call    ??$_Destroy_range@V?$allocator@UDelegationBase@DelegationConfig@@@std@@@std@@YAXPEAUDelegationBase@DelegationConfig@@QEAU12@AEAV?$allocator@UDelegationBase@DelegationConfig@@@0@@Z; std::_Destroy_range<std::allocator<DelegationConfig::DelegationBase>>(DelegationConfig::DelegationBase *,DelegationConfig::DelegationBase * const,std::allocator<DelegationConfig::DelegationBase> &)
0x180017171  mov     rcx, qword ptr [rsp+1A8h+var_180]
0x180017176  mov     rax, [rsp+1A8h+var_170]
0x18001717b  sub     rax, rcx
0x18001717e  sar     rax, 3
0x180017182  mov     rbx, 86BCA1AF286BCA1Bh
0x18001718c  imul    rax, rbx
0x180017190  imul    rdx, rax, 98h
0x180017197  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001719c  xorps   xmm0, xmm0
0x18001719f  movdqu  [rsp+1A8h+var_180], xmm0
0x1800171a5  mov     [rsp+1A8h+var_170], 0
0x1800171ae  jmp     short loc_1800171BA
0x1800171b0  mov     rbx, 86BCA1AF286BCA1Bh
0x1800171ba  mov     rcx, qword ptr [rsp+1A8h+var_168]
0x1800171bf  test    rcx, rcx
0x1800171c2  jz      short loc_180017201
0x1800171c4  mov     rdx, qword ptr [rsp+1A8h+var_168+8]
0x1800171c9  call    ??$_Destroy_range@V?$allocator@UDelegationBase@DelegationConfig@@@std@@@std@@YAXPEAUDelegationBase@DelegationConfig@@QEAU12@AEAV?$allocator@UDelegationBase@DelegationConfig@@@0@@Z; std::_Destroy_range<std::allocator<DelegationConfig::DelegationBase>>(DelegationConfig::DelegationBase *,DelegationConfig::DelegationBase * const,std::allocator<DelegationConfig::DelegationBase> &)
0x1800171ce  mov     rcx, qword ptr [rsp+1A8h+var_168]
0x1800171d3  mov     rax, [rsp+1A8h+var_158]
0x1800171d8  sub     rax, rcx
0x1800171db  sar     rax, 3
0x1800171df  imul    rax, rbx
0x1800171e3  imul    rdx, rax, 98h
0x1800171ea  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800171ef  xorps   xmm0, xmm0
0x1800171f2  movdqu  [rsp+1A8h+var_168], xmm0
0x1800171f8  mov     [rsp+1A8h+var_158], 0
0x180017201  mov     al, byte ptr [rsp+1A8h+var_188]
0x180017205  mov     byte ptr [rsp+1A8h+var_188], 0
0x18001720a  test    al, al
0x18001720c  jz      short loc_18001721A
0x18001720e  call    cs:__imp_CoUninitialize
0x180017215  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
