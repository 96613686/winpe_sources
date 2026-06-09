# MdmLogCollector::CollectScopedRegistryValues(ushort const *,std::vector<ushort const *,std::allocator<ushort const *>> &)

- ea: `0x18010c55c`
- end: `0x18010cf92`
- name: `?CollectScopedRegistryValues@MdmLogCollector@@AEAAJPEBGAEAV?$vector@PEBGV?$allocator@PEBG@std@@@std@@@Z`
- size: `2614`
- prototype: ``
- caller_count: `2`
- callee_count: `27`
- tags: `registry_config, loader_planting`

## callers

- `0x180109340`
- `0x18010b364`

## callees

- `0x180019000`
- `0x180019514`
- `0x180019fc4`
- `0x1800e4444`
- `0x1800e66dc`
- `0x1800e680c`
- `0x1800e7c08`
- `0x1800e87e8`
- `0x1800ece5c`
- `0x1800ef5d8`
- `0x1800f08d0`
- `0x1800f3f8c`
- `0x1800f89d8`
- `0x1800f97d0`
- `0x180104108`
- `0x180104bdc`
- `0x180104c54`
- `0x180104c80`
- `0x18010589c`
- `0x180105b28`
- `0x180106bc4`
- `0x180106ef0`
- `0x180107e60`
- `0x1801080f8`
- `0x18010c55c`
- `0x18011129c`
- `0x180111474`

## import_xrefs

- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@H@Z` at `0x18010c8f8`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@H@Z` at `0x18010c8f8`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x18010c8bd`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x18010c8bd`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x18010c8e9`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x18010c8e9`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x18010c9a5`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x18010c9a5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18010c81e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18010c81e`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18010c6ad`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18010c6ad`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18010c7aa`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18010c7aa`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18010c5d3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18010c5d3`

## string_xrefs

- `0x18010c611`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010c6c2`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010c7ca`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010c9ba`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=19 #try_helpers=1
__int64 __fastcall MdmLogCollector::CollectScopedRegistryValues(__int64 a1, const WCHAR *a2, _QWORD *a3)
{
  _QWORD *v3; // rsi
  DWORD v4; // r14d
  int v5; // r12d
  _QWORD *v6; // r15
  __int64 v7; // r13
  LSTATUS v8; // eax
  unsigned int v9; // ebx
  unsigned int v11; // eax
  unsigned int v12; // ebx
  unsigned int *v13; // rdi
  __int64 v14; // r9
  unsigned int v15; // eax
  unsigned int v16; // ebx
  _QWORD *v17; // rbx
  _QWORD *i; // rsi
  __int64 v19; // rax
  __int64 v20; // rax
  DWORD m; // ebx
  __int64 v22; // rax
  unsigned int v23; // eax
  unsigned int v24; // ebx
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rax
  _BYTE *v28; // rcx
  DWORD v29; // r14d
  _WORD *v30; // rbx
  __int64 v31; // rsi
  __int64 v32; // rax
  __int64 v33; // rax
  __int64 v34; // rax
  __int64 v35; // rax
  __int64 v36; // rax
  __int64 v37; // rax
  __int64 v38; // rax
  __int16 *j; // rbx
  __int64 k; // r8
  __int64 v41; // rsi
  __int64 v42; // r14
  __int64 v43; // rax
  __int64 v44; // rbx
  __int64 v45; // rax
  __int64 v46; // rax
  __int64 v47; // rax
  __int64 v48; // rdx
  __int64 v49; // rcx
  int phkResult; // [rsp+20h] [rbp-308h]
  unsigned int phkResulta; // [rsp+20h] [rbp-308h]
  unsigned int phkResultb; // [rsp+20h] [rbp-308h]
  char v53[4]; // [rsp+60h] [rbp-2C8h] BYREF
  DWORD cbData; // [rsp+64h] [rbp-2C4h] BYREF
  DWORD cbMaxValueNameLen; // [rsp+68h] [rbp-2C0h] BYREF
  DWORD cchValueName; // [rsp+6Ch] [rbp-2BCh] BYREF
  HKEY hKey; // [rsp+70h] [rbp-2B8h] BYREF
  DWORD cbMaxValueLen; // [rsp+78h] [rbp-2B0h] BYREF
  DWORD Type; // [rsp+7Ch] [rbp-2ACh] BYREF
  LPWSTR lpValueName; // [rsp+80h] [rbp-2A8h] BYREF
  DWORD cValues; // [rsp+88h] [rbp-2A0h] BYREF
  DWORD v62; // [rsp+8Ch] [rbp-29Ch]
  DWORD cbMaxSubKeyLen; // [rsp+90h] [rbp-298h] BYREF
  DWORD cSubKeys; // [rsp+94h] [rbp-294h] BYREF
  unsigned int *v65; // [rsp+98h] [rbp-290h] BYREF
  _QWORD *v66; // [rsp+A0h] [rbp-288h]
  __int16 v67; // [rsp+B0h] [rbp-278h] BYREF
  int v68; // [rsp+B2h] [rbp-276h]
  __int16 v69; // [rsp+B6h] [rbp-272h]
  const wchar_t *v70; // [rsp+B8h] [rbp-270h]
  __int16 v71; // [rsp+C0h] [rbp-268h]
  int v72; // [rsp+C2h] [rbp-266h]
  __int16 v73; // [rsp+C6h] [rbp-262h]
  const wchar_t *v74; // [rsp+C8h] [rbp-260h]
  __int16 v75; // [rsp+D0h] [rbp-258h]
  int v76; // [rsp+D2h] [rbp-256h]
  __int16 v77; // [rsp+D6h] [rbp-252h]
  const wchar_t *v78; // [rsp+D8h] [rbp-250h]
  __int16 v79; // [rsp+E0h] [rbp-248h]
  int v80; // [rsp+E2h] [rbp-246h]
  __int16 v81; // [rsp+E6h] [rbp-242h]
  const wchar_t *v82; // [rsp+E8h] [rbp-240h]
  __int64 v83; // [rsp+F0h] [rbp-238h] BYREF
  _BYTE v84[16]; // [rsp+100h] [rbp-228h] BYREF
  char v85[8]; // [rsp+110h] [rbp-218h] BYREF
  _BYTE v86[232]; // [rsp+118h] [rbp-210h] BYREF
  __int128 Src; // [rsp+200h] [rbp-128h] BYREF
  __int64 v88; // [rsp+210h] [rbp-118h]
  __int64 v89; // [rsp+218h] [rbp-110h]
  _BYTE v90[32]; // [rsp+220h] [rbp-108h] BYREF
  __int128 v91; // [rsp+240h] [rbp-E8h] BYREF
  __int64 v92; // [rsp+250h] [rbp-D8h]
  __int64 v93; // [rsp+258h] [rbp-D0h]
  _BYTE v94[32]; // [rsp+260h] [rbp-C8h] BYREF
  _BYTE v95[32]; // [rsp+280h] [rbp-A8h] BYREF
  _BYTE v96[32]; // [rsp+2A0h] [rbp-88h] BYREF
  __int16 v97; // [rsp+2C0h] [rbp-68h] BYREF
  __int128 v98; // [rsp+2C2h] [rbp-66h]
  _BYTE v99[22]; // [rsp+2D2h] [rbp-56h] BYREF
  _BYTE v100[6]; // [rsp+2EAh] [rbp-3Eh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+328h] [rbp+0h]

  v3 = a3;
  v66 = a3;
  v4 = 0;
  v5 = 0;
  cchValueName = 0;
  v6 = (_QWORD *)(a1 + 128);
  v7 = *(_QWORD *)(a1 + 136);
  v83 = *(_QWORD *)(a1 + 128);
  hKey = 0;
  v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 0x20019u, &hKey);
  v9 = v8;
  if ( v8 > 0 )
    v9 = (unsigned __int16)v8 | 0x80070000;
  if ( (v9 & 0x80000000) == 0 )
  {
    cSubKeys = 0;
    cbMaxSubKeyLen = 0;
    cValues = 0;
    cbMaxValueNameLen = 0;
    cbMaxValueLen = 0;
    v11 = RegQueryInfoKeyW(
            hKey,
            0,
            0,
            0,
            &cSubKeys,
            &cbMaxSubKeyLen,
            0,
            &cValues,
            &cbMaxValueNameLen,
            &cbMaxValueLen,
            0,
            0);
    if ( v11 )
    {
      v12 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x617,
              (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
              (const char *)v11,
              phkResulta);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      return v12;
    }
    lpValueName = (LPWSTR)operator new[](saturated_mul(++cbMaxValueNameLen, 2u));
    v13 = (unsigned int *)operator new[](cbMaxValueLen);
    v65 = v13;
    while ( 1 )
    {
      v62 = v4;
      if ( v4 >= cValues
        || (cchValueName = cbMaxValueNameLen,
            memset_0(lpValueName, 0, 2LL * cbMaxValueNameLen),
            cbData = cbMaxValueLen,
            memset_0(v13, 0, cbMaxValueLen),
            Type = 0,
            v15 = RegEnumValueW(hKey, v4, lpValueName, &cchValueName, 0, &Type, (LPBYTE)v13, &cbData),
            v15 == 259) )
      {
        v49 = *v6 + 32LL * (int)((v7 - v83) >> 5);
        LOBYTE(v14) = v53[0];
        std::_Sort_unchecked_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short_______lambda_bae75b49ee98f1ce6856e77292e28388___(
          v49,
          v6[1],
          (v6[1] - v49) >> 5,
          v14);
        std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v65);
        std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&lpValueName);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        return 0;
      }
      if ( v15 )
      {
        v16 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x630,
                (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
                (const char *)v15,
                phkResultb);
        std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v65);
        std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&lpValueName);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        return v16;
      }
      v17 = (_QWORD *)v3[1];
      for ( i = (_QWORD *)*v3; i != v17 && (unsigned int)_o__wcsicmp(*i, lpValueName); ++i )
        ;
      if ( i != (_QWORD *)v66[1] )
        break;
LABEL_67:
      ++v4;
      v3 = v66;
    }
    Src = 0;
    v88 = 0;
    v89 = 7;
    LOWORD(Src) = 0;
    switch ( Type )
    {
      case 1u:
        v36 = std::wstring::wstring(v90, L"\"");
        v37 = std::operator+<unsigned short>(v94, v36, v13);
        v38 = std::operator+<unsigned short>(v95, v37, L"\"");
        std::wstring::operator=(&Src, v38);
        std::wstring::_Tidy_deallocate(v95);
        std::wstring::_Tidy_deallocate(v94);
        break;
      case 4u:
        v35 = std::_UIntegral_to_buff<unsigned short,unsigned int>(v100, *v13);
        std::wstring::wstring(v90, v35, v100, v53);
        v5 |= 3u;
        std::wstring::operator=(&Src, v90);
        break;
      case 7u:
        std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(v84);
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v85, L"[");
        v29 = 0;
        v30 = v13;
        while ( v29 < cbData )
        {
          if ( !*v30 )
            break;
          v31 = -1;
          do
            ++v31;
          while ( v30[v31] );
          if ( (_DWORD)v31 )
          {
            v32 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v85, L"\"");
            v33 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v32, v30);
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(v33, L"\"");
          }
          else
          {
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(v85, L"null");
          }
          v29 += v31 + 1;
          if ( v29 >= cbData )
            break;
          v34 = -1;
          do
            ++v34;
          while ( v30[v34] );
          v30 += v34 + 1;
          if ( *v30 )
            std::basic_ostream<unsigned short>::operator<<(v85, 44);
        }
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v85, L"]");
        std::basic_stringbuf<unsigned short>::str(v86, v90);
        v5 |= 4u;
        std::wstring::operator=(&Src, v90);
        std::wstring::_Tidy_deallocate(v90);
        goto LABEL_46;
      case 0xBu:
        v97 = 48;
        v98 = 0;
        memset(v99, 0, sizeof(v99));
        v23 = _o__ui64tow_s(*(_QWORD *)v13, &v97, 20, 16);
        if ( v23 )
        {
          v24 = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0x64B,
                  (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
                  (const char *)v23,
                  phkResultb);
          std::wstring::_Tidy_deallocate(&Src);
          std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v65);
          std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&lpValueName);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
          return v24;
        }
        v25 = std::wstring::wstring(v95, L"\"REG_QWORD: 0x");
        v26 = std::operator+<unsigned short>(v94, v25, &v97);
        v27 = std::operator+<unsigned short>(v90, v26, L"\"");
        std::wstring::operator=(&Src, v27);
        std::wstring::_Tidy_deallocate(v90);
        std::wstring::_Tidy_deallocate(v94);
        v28 = v95;
LABEL_50:
        std::wstring::_Tidy_deallocate(v28);
LABEL_51:
        v91 = 0;
        v92 = 0;
        v93 = 7;
        LOWORD(v91) = 0;
        if ( lpValueName && *lpValueName )
          std::wstring::assign(&v91, lpValueName);
        else
          std::wstring::assign(&v91, L"@");
        v67 = 92;
        v68 = 0;
        v69 = 0;
        v70 = L"\\\\";
        v71 = 13;
        v72 = 0;
        v73 = 0;
        v74 = L"\\r";
        v75 = 10;
        v76 = 0;
        v77 = 0;
        v78 = L"\\n";
        v79 = 9;
        v80 = 0;
        v81 = 0;
        v82 = L"\\t";
        for ( j = &v67; j != (__int16 *)&v83; j += 8 )
        {
          for ( k = 0; ; k = v43 + v41 )
          {
            v41 = std::wstring::find(&Src, (unsigned __int16)*j, k);
            if ( v41 == -1 )
              break;
            v42 = *((_QWORD *)j + 1);
            std::wstring::replace(&Src);
            v43 = -1;
            do
              ++v43;
            while ( *(_WORD *)(v42 + 2 * v43) );
          }
        }
        v44 = std::wstring::wstring(&v97, L"\":");
        v45 = std::wstring::wstring(v90, L"\"");
        v46 = std::operator+<unsigned short>(v94, v45, &v91);
        v47 = std::operator+<unsigned short>(v95, v46, v44);
        std::operator+<unsigned short>(v96, v47, &Src);
        std::wstring::_Tidy_deallocate(v95);
        std::wstring::_Tidy_deallocate(v94);
        std::wstring::_Tidy_deallocate(v90);
        std::wstring::_Tidy_deallocate(&v97);
        v48 = v6[1];
        if ( v48 == v6[2] )
          std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(v6, v48, v96);
        else
          std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring const &>(v6, v96);
        std::wstring::_Tidy_deallocate(v96);
        std::wstring::_Tidy_deallocate(&v91);
        std::wstring::_Tidy_deallocate(&Src);
        v4 = v62;
        goto LABEL_67;
      default:
        std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(v84);
        v19 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v85, L"\"Hex: (reg type ");
        v20 = std::basic_ostream<unsigned short>::operator<<(v19, Type);
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v20, L" ): ");
        for ( m = 0; m < cbData; ++m )
        {
          v22 = std::basic_ostream<unsigned short>::operator<<(v85, std::hex);
          std::basic_ostream<unsigned short>::operator<<(v22, *((unsigned __int8 *)v13 + m));
          if ( m != cbData - 1 )
            std::basic_ostream<unsigned short>::operator<<(v85, 44);
        }
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v85, L"\"");
        std::basic_stringbuf<unsigned short>::str(v86, v90);
        v5 |= 8u;
        std::wstring::operator=(&Src, v90);
        std::wstring::_Tidy_deallocate(v90);
LABEL_46:
        std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vbase destructor'(v84);
        goto LABEL_51;
    }
    v28 = v90;
    goto LABEL_50;
  }
  if ( v9 == -2147024894 )
  {
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return 2147942402LL;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x60D,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
      (const char *)v9,
      phkResult);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return v9;
  }
}

```

## disassembly

```asm
0x18010c55c  mov     [rsp+arg_10], rbx
0x18010c561  mov     [rsp+arg_18], rsi
0x18010c566  push    rdi
0x18010c567  push    r12
0x18010c569  push    r13
0x18010c56b  push    r14
0x18010c56d  push    r15
0x18010c56f  sub     rsp, 300h
0x18010c576  mov     rax, cs:__security_cookie
0x18010c57d  xor     rax, rsp
0x18010c580  mov     [rsp+328h+var_38], rax
0x18010c588  mov     rsi, r8
0x18010c58b  mov     [rsp+328h+var_288], r8
0x18010c593  xor     r14d, r14d
0x18010c596  mov     r12d, r14d
0x18010c599  mov     [rsp+328h+cchValueName], r14d
0x18010c59e  lea     r15, [rcx+80h]
0x18010c5a5  mov     r13, [r15+8]
0x18010c5a9  mov     rax, [r15]
0x18010c5ac  mov     [rsp+328h+var_238], rax
0x18010c5b4  mov     [rsp+328h+hKey], r14
0x18010c5b9  lea     rax, [rsp+328h+hKey]
0x18010c5be  mov     [rsp+328h+phkResult], rax; int
0x18010c5c3  mov     r9d, 20019h; samDesired
0x18010c5c9  xor     r8d, r8d; ulOptions
0x18010c5cc  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18010c5d3  call    cs:__imp_RegOpenKeyExW
0x18010c5d9  mov     ebx, eax
0x18010c5db  test    eax, eax
0x18010c5dd  jle     short loc_18010C5E8
0x18010c5df  movzx   ebx, ax
0x18010c5e2  or      ebx, 80070000h
0x18010c5e8  test    ebx, ebx
0x18010c5ea  jns     short loc_18010C634
0x18010c5ec  mov     edi, 80070002h
0x18010c5f1  cmp     ebx, edi
0x18010c5f3  jnz     short loc_18010C606
0x18010c5f5  lea     rcx, [rsp+328h+hKey]
0x18010c5fa  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18010c5ff  mov     eax, edi
0x18010c601  jmp     loc_18010CF64
0x18010c606  mov     rcx, [rsp+328h]; this
0x18010c60e  mov     r9d, ebx; char *
0x18010c611  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010c618  mov     edx, 60Dh; void *
0x18010c61d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010c622  nop
0x18010c623  lea     rcx, [rsp+328h+hKey]
0x18010c628  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18010c62d  mov     eax, ebx
0x18010c62f  jmp     loc_18010CF64
0x18010c634  mov     [rsp+328h+cSubKeys], r14d
0x18010c63c  mov     [rsp+328h+cbMaxSubKeyLen], r14d
0x18010c644  mov     [rsp+328h+cValues], r14d
0x18010c64c  mov     [rsp+328h+cbMaxValueNameLen], r14d
0x18010c651  mov     [rsp+328h+cbMaxValueLen], r14d
0x18010c656  mov     [rsp+328h+lpftLastWriteTime], r14; lpftLastWriteTime
0x18010c65b  mov     [rsp+328h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x18010c660  lea     rax, [rsp+328h+cbMaxValueLen]
0x18010c665  mov     [rsp+328h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x18010c66a  lea     rax, [rsp+328h+cbMaxValueNameLen]
0x18010c66f  mov     [rsp+328h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x18010c674  lea     rax, [rsp+328h+cValues]
0x18010c67c  mov     [rsp+328h+lpcValues], rax; lpcValues
0x18010c681  mov     [rsp+328h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x18010c686  lea     rax, [rsp+328h+cbMaxSubKeyLen]
0x18010c68e  mov     [rsp+328h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x18010c693  lea     rax, [rsp+328h+cSubKeys]
0x18010c69b  mov     [rsp+328h+phkResult], rax; unsigned int
0x18010c6a0  xor     r9d, r9d; lpReserved
0x18010c6a3  xor     r8d, r8d; lpcchClass
0x18010c6a6  xor     edx, edx; lpClass
0x18010c6a8  mov     rcx, [rsp+328h+hKey]; hKey
0x18010c6ad  call    cs:__imp_RegQueryInfoKeyW
0x18010c6b3  test    eax, eax
0x18010c6b5  jz      short loc_18010C6E6
0x18010c6b7  mov     rcx, [rsp+328h]; this
0x18010c6bf  mov     r9d, eax; char *
0x18010c6c2  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010c6c9  mov     edx, 617h; void *
0x18010c6ce  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18010c6d3  mov     ebx, eax
0x18010c6d5  lea     rcx, [rsp+328h+hKey]
0x18010c6da  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18010c6df  mov     eax, ebx
0x18010c6e1  jmp     loc_18010CF64
0x18010c6e6  mov     eax, [rsp+328h+cbMaxValueNameLen]
0x18010c6ea  inc     eax
0x18010c6ec  mov     [rsp+328h+cbMaxValueNameLen], eax
0x18010c6f0  mov     ecx, eax
0x18010c6f2  mov     eax, 2
0x18010c6f7  mul     rcx
0x18010c6fa  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18010c701  cmovb   rax, rcx
0x18010c705  mov     rcx, rax; unsigned __int64
0x18010c708  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18010c70d  mov     [rsp+328h+lpValueName], rax
0x18010c715  mov     ecx, [rsp+328h+cbMaxValueLen]; unsigned __int64
0x18010c719  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18010c71e  mov     rdi, rax
0x18010c721  mov     [rsp+328h+var_290], rax
0x18010c729  mov     [rsp+328h+var_29C], r14d
0x18010c731  cmp     r14d, [rsp+328h+cValues]
0x18010c739  jnb     loc_18010CF07
0x18010c73f  mov     eax, [rsp+328h+cbMaxValueNameLen]
0x18010c743  mov     [rsp+328h+cchValueName], eax
0x18010c747  mov     r8d, eax
0x18010c74a  add     r8, r8; Size
0x18010c74d  xor     edx, edx; Val
0x18010c74f  mov     rcx, [rsp+328h+lpValueName]; void *
0x18010c757  call    memset_0
0x18010c75c  mov     eax, [rsp+328h+cbMaxValueLen]
0x18010c760  mov     [rsp+328h+cbData], eax
0x18010c764  mov     r8d, eax; Size
0x18010c767  xor     edx, edx; Val
0x18010c769  mov     rcx, rdi; void *
0x18010c76c  call    memset_0
0x18010c771  xor     ebx, ebx
0x18010c773  mov     [rsp+328h+Type], ebx
0x18010c777  lea     rax, [rsp+328h+cbData]
0x18010c77c  mov     [rsp+328h+lpcValues], rax; lpcbData
0x18010c781  mov     [rsp+328h+lpcbMaxClassLen], rdi; lpData
0x18010c786  lea     rax, [rsp+328h+Type]
0x18010c78b  mov     [rsp+328h+lpcbMaxSubKeyLen], rax; lpType
0x18010c790  mov     [rsp+328h+phkResult], rbx; unsigned int
0x18010c795  lea     r9, [rsp+328h+cchValueName]; lpcchValueName
0x18010c79a  mov     r8, [rsp+328h+lpValueName]; lpValueName
0x18010c7a2  mov     edx, r14d; dwIndex
0x18010c7a5  mov     rcx, [rsp+328h+hKey]; hKey
0x18010c7aa  call    cs:__imp_RegEnumValueW
0x18010c7b0  cmp     eax, 103h
0x18010c7b5  jz      loc_18010CF07
0x18010c7bb  test    eax, eax
0x18010c7bd  jz      short loc_18010C80A
0x18010c7bf  mov     rcx, [rsp+328h]; this
0x18010c7c7  mov     r9d, eax; char *
0x18010c7ca  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010c7d1  mov     edx, 630h; void *
0x18010c7d6  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18010c7db  mov     ebx, eax
0x18010c7dd  lea     rcx, [rsp+328h+var_290]
0x18010c7e5  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x18010c7ea  nop
0x18010c7eb  lea     rcx, [rsp+328h+lpValueName]
0x18010c7f3  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x18010c7f8  nop
0x18010c7f9  lea     rcx, [rsp+328h+hKey]
0x18010c7fe  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18010c803  mov     eax, ebx
0x18010c805  jmp     loc_18010CF64
0x18010c80a  mov     rbx, [rsi+8]
0x18010c80e  mov     rsi, [rsi]
0x18010c811  jmp     short loc_18010C82C
0x18010c813  mov     rdx, [rsp+328h+lpValueName]
0x18010c81b  mov     rcx, [rsi]
0x18010c81e  call    cs:__imp__o__wcsicmp
0x18010c824  test    eax, eax
0x18010c826  jz      short loc_18010C831
0x18010c828  add     rsi, 8
0x18010c82c  cmp     rsi, rbx
0x18010c82f  jnz     short loc_18010C813
0x18010c831  mov     rax, [rsp+328h+var_288]
0x18010c839  cmp     rsi, [rax+8]
0x18010c83d  jz      loc_18010CEF7
0x18010c843  xorps   xmm0, xmm0
0x18010c846  movups  [rsp+328h+Src], xmm0
0x18010c84e  xor     esi, esi
0x18010c850  mov     [rsp+328h+var_118], rsi
0x18010c858  mov     [rsp+328h+var_110], 7
0x18010c864  mov     word ptr [rsp+328h+Src], si
0x18010c86c  mov     eax, [rsp+328h+Type]
0x18010c870  sub     eax, 1
0x18010c873  jz      loc_18010CC00
0x18010c879  sub     eax, 3
0x18010c87c  jz      loc_18010CBB9
0x18010c882  sub     eax, 3
0x18010c885  jz      loc_18010CA86
0x18010c88b  cmp     eax, 4
0x18010c88e  jz      loc_18010C96B
0x18010c894  lea     rcx, [rsp+328h+var_228]
0x18010c89c  call    ??0?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)
0x18010c8a1  nop
0x18010c8a2  lea     rdx, aHexRegType; "\"Hex: (reg type "
0x18010c8a9  lea     rcx, [rsp+328h+var_218]
0x18010c8b1  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18010c8b6  mov     edx, [rsp+328h+Type]
0x18010c8ba  mov     rcx, rax
0x18010c8bd  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z; std::basic_ostream<ushort>::operator<<(ulong)
0x18010c8c3  lea     rdx, asc_1801D28E8; " ): "
0x18010c8ca  mov     rcx, rax
0x18010c8cd  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18010c8d2  mov     ebx, esi
0x18010c8d4  lea     rcx, [rsp+328h+var_218]
0x18010c8dc  cmp     ebx, [rsp+328h+cbData]
0x18010c8e0  jnb     short loc_18010C91E
0x18010c8e2  lea     rdx, ?hex@std@@YAAEAVios_base@1@AEAV21@@Z; std::hex(std::ios_base &)
0x18010c8e9  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z; std::basic_ostream<ushort>::operator<<(std::ios_base & (*)(std::ios_base &))
0x18010c8ef  mov     ecx, ebx
0x18010c8f1  movzx   edx, byte ptr [rcx+rdi]
0x18010c8f5  mov     rcx, rax
0x18010c8f8  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@H@Z; std::basic_ostream<ushort>::operator<<(int)
0x18010c8fe  mov     eax, [rsp+328h+cbData]
0x18010c902  dec     eax
0x18010c904  cmp     ebx, eax
0x18010c906  jz      short loc_18010C91A
0x18010c908  mov     edx, 2Ch ; ','
0x18010c90d  lea     rcx, [rsp+328h+var_218]
0x18010c915  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@G@Z; std::basic_ostream<ushort>::operator<<(ushort)
0x18010c91a  inc     ebx
0x18010c91c  jmp     short loc_18010C8D4
0x18010c91e  lea     rdx, asc_1801D12D4; "\""
0x18010c925  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18010c92a  lea     rdx, [rsp+328h+var_108]
0x18010c932  lea     rcx, [rsp+328h+var_210]
0x18010c93a  call    ?str@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_stringbuf<ushort>::str(void)
0x18010c93f  or      r12d, 8
0x18010c943  lea     rdx, [rsp+328h+var_108]
0x18010c94b  lea     rcx, [rsp+328h+Src]
0x18010c953  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18010c958  lea     rcx, [rsp+328h+var_108]
0x18010c960  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010c965  nop
0x18010c966  jmp     loc_18010CBA7
0x18010c96b  mov     eax, 30h ; '0'
0x18010c970  mov     [rsp+328h+var_68], ax
0x18010c978  xor     eax, eax
0x18010c97a  movups  [rsp+328h+var_66], xmm0
0x18010c982  movups  xmmword ptr [rsp+328h+var_56], xmm0
0x18010c98a  mov     qword ptr [rsp+328h+var_56+0Eh], rax
0x18010c992  lea     r9d, [rax+10h]
0x18010c996  lea     r8d, [rax+14h]
0x18010c99a  lea     rdx, [rsp+328h+var_68]
0x18010c9a2  mov     rcx, [rdi]
0x18010c9a5  call    cs:__imp__o__ui64tow_s
0x18010c9ab  test    eax, eax
0x18010c9ad  jz      short loc_18010CA08
0x18010c9af  mov     rcx, [rsp+328h]; this
0x18010c9b7  mov     r9d, eax; char *
0x18010c9ba  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010c9c1  mov     edx, 64Bh; void *
0x18010c9c6  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18010c9cb  mov     ebx, eax
0x18010c9cd  lea     rcx, [rsp+328h+Src]
0x18010c9d5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010c9da  nop
0x18010c9db  lea     rcx, [rsp+328h+var_290]
0x18010c9e3  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x18010c9e8  nop
0x18010c9e9  lea     rcx, [rsp+328h+lpValueName]
0x18010c9f1  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x18010c9f6  nop
0x18010c9f7  lea     rcx, [rsp+328h+hKey]
0x18010c9fc  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18010ca01  mov     eax, ebx
0x18010ca03  jmp     loc_18010CF64
0x18010ca08  lea     rdx, aRegQword0x; "\"REG_QWORD: 0x"
0x18010ca0f  lea     rcx, [rsp+328h+var_A8]
0x18010ca17  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18010ca1c  nop
0x18010ca1d  lea     r8, [rsp+328h+var_68]
0x18010ca25  mov     rdx, rax
0x18010ca28  lea     rcx, [rsp+328h+var_C8]
0x18010ca30  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18010ca35  nop
0x18010ca36  lea     r8, asc_1801D12D4; "\""
0x18010ca3d  mov     rdx, rax
0x18010ca40  lea     rcx, [rsp+328h+var_108]
0x18010ca48  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18010ca4d  mov     rdx, rax
0x18010ca50  lea     rcx, [rsp+328h+Src]
0x18010ca58  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18010ca5d  lea     rcx, [rsp+328h+var_108]
0x18010ca65  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010ca6a  nop
0x18010ca6b  lea     rcx, [rsp+328h+var_C8]
0x18010ca73  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010ca78  nop
0x18010ca79  lea     rcx, [rsp+328h+var_A8]
0x18010ca81  jmp     loc_18010CC74
0x18010ca86  lea     rcx, [rsp+328h+var_228]
0x18010ca8e  call    ??0?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)
0x18010ca93  nop
0x18010ca94  lea     rdx, asc_1801D2880; "["
0x18010ca9b  lea     rcx, [rsp+328h+var_218]
0x18010caa3  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18010caa8  mov     r14d, esi
0x18010caab  mov     rbx, rdi
0x18010caae  cmp     r14d, [rsp+328h+cbData]
0x18010cab3  jnb     loc_18010CB57
0x18010cab9  cmp     si, [rbx]
0x18010cabc  jz      loc_18010CB57
0x18010cac2  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18010cac6  xor     eax, eax
0x18010cac8  inc     rsi
0x18010cacb  cmp     [rbx+rsi*2], ax
0x18010cacf  jnz     short loc_18010CAC8
0x18010cad1  lea     rcx, [rsp+328h+var_218]
0x18010cad9  test    esi, esi
0x18010cadb  jnz     short loc_18010CAEB
0x18010cadd  lea     rdx, aNull; "null"
  ... truncated ...
```
