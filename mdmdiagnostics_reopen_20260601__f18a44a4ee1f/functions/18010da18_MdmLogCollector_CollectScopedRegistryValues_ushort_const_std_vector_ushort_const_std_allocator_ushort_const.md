# MdmLogCollector::CollectScopedRegistryValues(ushort const *,std::vector<ushort const *,std::allocator<ushort const *>> &)

- ea: `0x18010da18`
- end: `0x18010e478`
- name: `?CollectScopedRegistryValues@MdmLogCollector@@AEAAJPEBGAEAV?$vector@PEBGV?$allocator@PEBG@std@@@std@@@Z`
- size: `2656`
- prototype: ``
- caller_count: `2`
- callee_count: `27`
- tags: `registry_config, loader_planting`

## callers

- `0x18010a6dc`
- `0x18010c7b0`

## callees

- `0x180019080`
- `0x180019594`
- `0x18001a054`
- `0x1800e4508`
- `0x1800e68b0`
- `0x1800e69f4`
- `0x1800e7de8`
- `0x1800e8a44`
- `0x1800ed46c`
- `0x1800efd9c`
- `0x1800f1140`
- `0x1800f4b2c`
- `0x1800f99d4`
- `0x1800fa7d4`
- `0x180105294`
- `0x180105e98`
- `0x180105f10`
- `0x180105f3c`
- `0x180106b3c`
- `0x180106dc8`
- `0x180107e90`
- `0x1801081c4`
- `0x180109140`
- `0x1801093e8`
- `0x18010da18`
- `0x18011273c`
- `0x18011291c`

## import_xrefs

- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@H@Z` at `0x18010ddd9`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@H@Z` at `0x18010ddd9`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x18010dd92`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x18010dd92`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x18010ddc4`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x18010ddc4`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x18010de83`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x18010de83`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18010dced`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18010dced`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18010db72`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18010db72`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18010dc73`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18010dc73`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18010da92`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18010da92`

## string_xrefs

- `0x18010dad6`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010db8d`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010dc99`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010de9e`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=19 #try_helpers=1
__int64 __fastcall MdmLogCollector::CollectScopedRegistryValues(__int64 a1, const WCHAR *a2, _QWORD *a3)
{
  _QWORD *v3; // rsi
  DWORD v4; // r13d
  int v5; // r14d
  _QWORD *v6; // r15
  __int64 v7; // r12
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
  __int64 v23; // rax
  unsigned int v24; // eax
  unsigned int v25; // ebx
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rax
  _BYTE *v29; // rcx
  DWORD v30; // r14d
  _WORD *v31; // rbx
  __int64 v32; // rsi
  __int64 v33; // rax
  __int64 v34; // rax
  __int64 v35; // rax
  __int64 v36; // rax
  __int64 v37; // rax
  __int64 v38; // rax
  __int64 v39; // rax
  __int64 v40; // rax
  __int16 *j; // rbx
  __int64 k; // r8
  __int64 v43; // rax
  __int64 v44; // rsi
  __int64 v45; // r14
  __int64 v46; // rax
  __int64 v47; // rbx
  __int64 v48; // rax
  __int64 v49; // rax
  __int64 v50; // rax
  __int64 v51; // rdx
  __int64 v52; // rcx
  int phkResult; // [rsp+20h] [rbp-308h]
  unsigned int phkResulta; // [rsp+20h] [rbp-308h]
  unsigned int phkResultb; // [rsp+20h] [rbp-308h]
  char v56[4]; // [rsp+60h] [rbp-2C8h] BYREF
  DWORD cbData; // [rsp+64h] [rbp-2C4h] BYREF
  DWORD cbMaxValueNameLen; // [rsp+68h] [rbp-2C0h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-2B8h] BYREF
  DWORD cbMaxValueLen; // [rsp+78h] [rbp-2B0h] BYREF
  DWORD Type; // [rsp+7Ch] [rbp-2ACh] BYREF
  DWORD cchValueName; // [rsp+80h] [rbp-2A8h] BYREF
  LPWSTR lpValueName; // [rsp+88h] [rbp-2A0h] BYREF
  DWORD cValues; // [rsp+90h] [rbp-298h] BYREF
  int v65; // [rsp+94h] [rbp-294h]
  DWORD cbMaxSubKeyLen; // [rsp+98h] [rbp-290h] BYREF
  DWORD cSubKeys; // [rsp+9Ch] [rbp-28Ch] BYREF
  unsigned int *v68; // [rsp+A0h] [rbp-288h] BYREF
  _QWORD *v69; // [rsp+A8h] [rbp-280h]
  __int16 v70; // [rsp+B0h] [rbp-278h] BYREF
  int v71; // [rsp+B2h] [rbp-276h]
  __int16 v72; // [rsp+B6h] [rbp-272h]
  const wchar_t *v73; // [rsp+B8h] [rbp-270h]
  __int16 v74; // [rsp+C0h] [rbp-268h]
  int v75; // [rsp+C2h] [rbp-266h]
  __int16 v76; // [rsp+C6h] [rbp-262h]
  const wchar_t *v77; // [rsp+C8h] [rbp-260h]
  __int16 v78; // [rsp+D0h] [rbp-258h]
  int v79; // [rsp+D2h] [rbp-256h]
  __int16 v80; // [rsp+D6h] [rbp-252h]
  const wchar_t *v81; // [rsp+D8h] [rbp-250h]
  __int16 v82; // [rsp+E0h] [rbp-248h]
  int v83; // [rsp+E2h] [rbp-246h]
  __int16 v84; // [rsp+E6h] [rbp-242h]
  const wchar_t *v85; // [rsp+E8h] [rbp-240h]
  __int64 v86; // [rsp+F0h] [rbp-238h] BYREF
  _BYTE v87[16]; // [rsp+100h] [rbp-228h] BYREF
  _BYTE v88[240]; // [rsp+110h] [rbp-218h] BYREF
  __int128 v89; // [rsp+200h] [rbp-128h] BYREF
  __int64 v90; // [rsp+210h] [rbp-118h]
  __int64 v91; // [rsp+218h] [rbp-110h]
  _BYTE v92[32]; // [rsp+220h] [rbp-108h] BYREF
  __int128 v93; // [rsp+240h] [rbp-E8h] BYREF
  __int64 v94; // [rsp+250h] [rbp-D8h]
  __int64 v95; // [rsp+258h] [rbp-D0h]
  _BYTE v96[32]; // [rsp+260h] [rbp-C8h] BYREF
  _BYTE v97[32]; // [rsp+280h] [rbp-A8h] BYREF
  _BYTE v98[32]; // [rsp+2A0h] [rbp-88h] BYREF
  __int16 v99; // [rsp+2C0h] [rbp-68h] BYREF
  __int128 v100; // [rsp+2C2h] [rbp-66h]
  _BYTE v101[22]; // [rsp+2D2h] [rbp-56h] BYREF
  _BYTE v102[6]; // [rsp+2EAh] [rbp-3Eh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+328h] [rbp+0h]

  v3 = a3;
  v69 = a3;
  v4 = 0;
  v5 = 0;
  v65 = 0;
  v6 = (_QWORD *)(a1 + 128);
  v7 = *(_QWORD *)(a1 + 136);
  v86 = *(_QWORD *)(a1 + 128);
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
              (void *)0x5EE,
              (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
              (const char *)v11,
              phkResulta);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      return v12;
    }
    lpValueName = (LPWSTR)operator new[](saturated_mul(++cbMaxValueNameLen, 2u));
    v13 = (unsigned int *)operator new[](cbMaxValueLen);
    v68 = v13;
    while ( 1 )
    {
      if ( v4 >= cValues
        || (cchValueName = cbMaxValueNameLen,
            memset_0(lpValueName, 0, 2LL * cbMaxValueNameLen),
            cbData = cbMaxValueLen,
            memset_0(v13, 0, cbMaxValueLen),
            Type = 0,
            v15 = RegEnumValueW(hKey, v4, lpValueName, &cchValueName, 0, &Type, (LPBYTE)v13, &cbData),
            v15 == 259) )
      {
        v52 = *v6 + 32LL * (int)((v7 - v86) >> 5);
        LOBYTE(v14) = v56[0];
        std::_Sort_unchecked_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short_______lambda_bae75b49ee98f1ce6856e77292e28388___(
          v52,
          v6[1],
          (v6[1] - v52) >> 5,
          v14);
        std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v68);
        std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&lpValueName);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        return 0;
      }
      if ( v15 )
      {
        v16 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x607,
                (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
                (const char *)v15,
                phkResultb);
        std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v68);
        std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&lpValueName);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        return v16;
      }
      v17 = (_QWORD *)v3[1];
      for ( i = (_QWORD *)*v3; i != v17 && (unsigned int)_o__wcsicmp(*i, lpValueName); ++i )
        ;
      if ( i != (_QWORD *)v69[1] )
        break;
LABEL_67:
      ++v4;
      v3 = v69;
    }
    v89 = 0;
    v90 = 0;
    v91 = 7;
    LOWORD(v89) = 0;
    switch ( Type )
    {
      case 1u:
        v38 = std::wstring::wstring(v92, L"\"");
        v39 = std::operator+<unsigned short>(v97, v38, v13);
        v40 = std::operator+<unsigned short>(v96, v39, L"\"");
        std::wstring::operator=(&v89, v40);
        std::wstring::_Tidy_deallocate(v96);
        std::wstring::_Tidy_deallocate(v97);
        break;
      case 4u:
        v37 = std::_UIntegral_to_buff<unsigned short,unsigned int>(v102, *v13);
        std::wstring::wstring(v92, v37, v102, v56);
        v65 = v5 | 3;
        std::wstring::operator=(&v89, v92);
        break;
      case 7u:
        std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(v87);
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v88, L"[");
        v30 = 0;
        v31 = v13;
        while ( v30 < cbData )
        {
          if ( !*v31 )
            break;
          v32 = -1;
          do
            ++v32;
          while ( v31[v32] );
          if ( (_DWORD)v32 )
          {
            v33 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v88, L"\"");
            v34 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v33, v31);
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(v34, L"\"");
          }
          else
          {
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(v88, L"null");
          }
          v30 += v32 + 1;
          if ( v30 >= cbData )
            break;
          v35 = -1;
          do
            ++v35;
          while ( v31[v35] );
          v31 += v35 + 1;
          if ( *v31 )
            std::basic_ostream<unsigned short>::operator<<(v88, 44);
        }
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v88, L"]");
        v36 = std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::str(
                v87,
                v96);
        std::wstring::operator=(&v89, v36);
        std::wstring::_Tidy_deallocate(v96);
        goto LABEL_46;
      case 0xBu:
        v99 = 48;
        v100 = 0;
        memset(v101, 0, sizeof(v101));
        v24 = _o__ui64tow_s(*(_QWORD *)v13, &v99, 20, 16);
        if ( v24 )
        {
          v25 = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0x622,
                  (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
                  (const char *)v24,
                  phkResultb);
          std::wstring::_Tidy_deallocate(&v89);
          std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v68);
          std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&lpValueName);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
          return v25;
        }
        v26 = std::wstring::wstring(v96, L"\"REG_QWORD: 0x");
        v27 = std::operator+<unsigned short>(v97, v26, &v99);
        v28 = std::operator+<unsigned short>(v92, v27, L"\"");
        std::wstring::operator=(&v89, v28);
        std::wstring::_Tidy_deallocate(v92);
        std::wstring::_Tidy_deallocate(v97);
        v29 = v96;
LABEL_50:
        std::wstring::_Tidy_deallocate(v29);
LABEL_51:
        v93 = 0;
        v94 = 0;
        v95 = 7;
        LOWORD(v93) = 0;
        if ( lpValueName && *lpValueName )
          std::wstring::assign(&v93, lpValueName);
        else
          std::wstring::assign(&v93, L"@");
        v70 = 92;
        v71 = 0;
        v72 = 0;
        v73 = L"\\\\";
        v74 = 13;
        v75 = 0;
        v76 = 0;
        v77 = L"\\r";
        v78 = 10;
        v79 = 0;
        v80 = 0;
        v81 = L"\\n";
        v82 = 9;
        v83 = 0;
        v84 = 0;
        v85 = L"\\t";
        for ( j = &v70; j != (__int16 *)&v86; j += 8 )
        {
          for ( k = 0; ; k = v46 + v44 )
          {
            v43 = std::wstring::find(&v89, (unsigned __int16)*j, k);
            v44 = v43;
            if ( v43 == -1 )
              break;
            v45 = *((_QWORD *)j + 1);
            std::wstring::replace(&v89, v43, 1, v45);
            v46 = -1;
            do
              ++v46;
            while ( *(_WORD *)(v45 + 2 * v46) );
          }
        }
        v47 = std::wstring::wstring(&v99, L"\":");
        v48 = std::wstring::wstring(v92, L"\"");
        v49 = std::operator+<unsigned short>(v97, v48, &v93);
        v50 = std::operator+<unsigned short>(v96, v49, v47);
        std::operator+<unsigned short>(v98, v50, &v89);
        std::wstring::_Tidy_deallocate(v96);
        std::wstring::_Tidy_deallocate(v97);
        std::wstring::_Tidy_deallocate(v92);
        std::wstring::_Tidy_deallocate(&v99);
        v51 = v6[1];
        if ( v51 == v6[2] )
          std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(v6, v51, v98);
        else
          std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring const &>(v6, v98);
        std::wstring::_Tidy_deallocate(v98);
        std::wstring::_Tidy_deallocate(&v93);
        std::wstring::_Tidy_deallocate(&v89);
        v5 = v65;
        goto LABEL_67;
      default:
        std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(v87);
        v19 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v88, L"\"Hex: (reg type ");
        v20 = std::basic_ostream<unsigned short>::operator<<(v19, Type);
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v20, L" ): ");
        for ( m = 0; m < cbData; ++m )
        {
          v22 = std::basic_ostream<unsigned short>::operator<<(v88, std::hex);
          std::basic_ostream<unsigned short>::operator<<(v22, *((unsigned __int8 *)v13 + m));
          if ( m != cbData - 1 )
            std::basic_ostream<unsigned short>::operator<<(v88, 44);
        }
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v88, L"\"");
        v23 = std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::str(
                v87,
                v92);
        std::wstring::operator=(&v89, v23);
        std::wstring::_Tidy_deallocate(v92);
LABEL_46:
        std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vbase destructor'(v87);
        goto LABEL_51;
    }
    v29 = v92;
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
      (void *)0x5E4,
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
0x18010da18  mov     [rsp+arg_10], rbx
0x18010da1d  mov     [rsp+arg_18], rsi
0x18010da22  push    rdi
0x18010da23  push    r12
0x18010da25  push    r13
0x18010da27  push    r14
0x18010da29  push    r15
0x18010da2b  sub     rsp, 300h
0x18010da32  mov     rax, cs:__security_cookie
0x18010da39  xor     rax, rsp
0x18010da3c  mov     [rsp+328h+var_38], rax
0x18010da44  mov     rsi, r8
0x18010da47  mov     [rsp+328h+var_280], r8
0x18010da4f  xor     r13d, r13d
0x18010da52  mov     r14d, r13d
0x18010da55  mov     [rsp+328h+var_294], r13d
0x18010da5d  lea     r15, [rcx+80h]
0x18010da64  mov     r12, [r15+8]
0x18010da68  mov     rax, [r15]
0x18010da6b  mov     [rsp+328h+var_238], rax
0x18010da73  mov     [rsp+328h+hKey], r13
0x18010da78  lea     rax, [rsp+328h+hKey]
0x18010da7d  mov     [rsp+328h+phkResult], rax; int
0x18010da82  mov     r9d, 20019h; samDesired
0x18010da88  xor     r8d, r8d; ulOptions
0x18010da8b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18010da92  call    cs:__imp_RegOpenKeyExW
0x18010da99  nop     dword ptr [rax+rax+00h]
0x18010da9e  mov     ebx, eax
0x18010daa0  test    eax, eax
0x18010daa2  jle     short loc_18010DAAD
0x18010daa4  movzx   ebx, ax
0x18010daa7  or      ebx, 80070000h
0x18010daad  test    ebx, ebx
0x18010daaf  jns     short loc_18010DAF9
0x18010dab1  mov     edi, 80070002h
0x18010dab6  cmp     ebx, edi
0x18010dab8  jnz     short loc_18010DACB
0x18010daba  lea     rcx, [rsp+328h+hKey]
0x18010dabf  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18010dac4  mov     eax, edi
0x18010dac6  jmp     loc_18010E44A
0x18010dacb  mov     rcx, [rsp+328h]; this
0x18010dad3  mov     r9d, ebx; char *
0x18010dad6  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010dadd  mov     edx, 5E4h; void *
0x18010dae2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010dae7  nop
0x18010dae8  lea     rcx, [rsp+328h+hKey]
0x18010daed  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18010daf2  mov     eax, ebx
0x18010daf4  jmp     loc_18010E44A
0x18010daf9  mov     [rsp+328h+cSubKeys], r13d
0x18010db01  mov     [rsp+328h+cbMaxSubKeyLen], r13d
0x18010db09  mov     [rsp+328h+cValues], r13d
0x18010db11  mov     [rsp+328h+cbMaxValueNameLen], r13d
0x18010db16  mov     [rsp+328h+cbMaxValueLen], r13d
0x18010db1b  mov     [rsp+328h+lpftLastWriteTime], r13; lpftLastWriteTime
0x18010db20  mov     [rsp+328h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x18010db25  lea     rax, [rsp+328h+cbMaxValueLen]
0x18010db2a  mov     [rsp+328h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x18010db2f  lea     rax, [rsp+328h+cbMaxValueNameLen]
0x18010db34  mov     [rsp+328h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x18010db39  lea     rax, [rsp+328h+cValues]
0x18010db41  mov     [rsp+328h+lpcValues], rax; lpcValues
0x18010db46  mov     [rsp+328h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x18010db4b  lea     rax, [rsp+328h+cbMaxSubKeyLen]
0x18010db53  mov     [rsp+328h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x18010db58  lea     rax, [rsp+328h+cSubKeys]
0x18010db60  mov     [rsp+328h+phkResult], rax; unsigned int
0x18010db65  xor     r9d, r9d; lpReserved
0x18010db68  xor     r8d, r8d; lpcchClass
0x18010db6b  xor     edx, edx; lpClass
0x18010db6d  mov     rcx, [rsp+328h+hKey]; hKey
0x18010db72  call    cs:__imp_RegQueryInfoKeyW
0x18010db79  nop     dword ptr [rax+rax+00h]
0x18010db7e  test    eax, eax
0x18010db80  jz      short loc_18010DBB1
0x18010db82  mov     rcx, [rsp+328h]; this
0x18010db8a  mov     r9d, eax; char *
0x18010db8d  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010db94  mov     edx, 5EEh; void *
0x18010db99  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18010db9e  mov     ebx, eax
0x18010dba0  lea     rcx, [rsp+328h+hKey]
0x18010dba5  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18010dbaa  mov     eax, ebx
0x18010dbac  jmp     loc_18010E44A
0x18010dbb1  mov     eax, [rsp+328h+cbMaxValueNameLen]
0x18010dbb5  inc     eax
0x18010dbb7  mov     [rsp+328h+cbMaxValueNameLen], eax
0x18010dbbb  mov     ecx, eax
0x18010dbbd  mov     eax, 2
0x18010dbc2  mul     rcx
0x18010dbc5  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18010dbcc  cmovb   rax, rcx
0x18010dbd0  mov     rcx, rax; unsigned __int64
0x18010dbd3  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18010dbd8  mov     [rsp+328h+lpValueName], rax
0x18010dbe0  mov     ecx, [rsp+328h+cbMaxValueLen]; unsigned __int64
0x18010dbe4  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18010dbe9  mov     rdi, rax
0x18010dbec  mov     [rsp+328h+var_288], rax
0x18010dbf4  cmp     r13d, [rsp+328h+cValues]
0x18010dbfc  jnb     loc_18010E3EA
0x18010dc02  mov     eax, [rsp+328h+cbMaxValueNameLen]
0x18010dc06  mov     [rsp+328h+cchValueName], eax
0x18010dc0d  mov     r8d, eax
0x18010dc10  add     r8, r8; Size
0x18010dc13  xor     edx, edx; Val
0x18010dc15  mov     rcx, [rsp+328h+lpValueName]; void *
0x18010dc1d  call    memset_0
0x18010dc22  mov     eax, [rsp+328h+cbMaxValueLen]
0x18010dc26  mov     [rsp+328h+cbData], eax
0x18010dc2a  mov     r8d, eax; Size
0x18010dc2d  xor     edx, edx; Val
0x18010dc2f  mov     rcx, rdi; void *
0x18010dc32  call    memset_0
0x18010dc37  xor     ebx, ebx
0x18010dc39  mov     [rsp+328h+Type], ebx
0x18010dc3d  lea     rax, [rsp+328h+cbData]
0x18010dc42  mov     [rsp+328h+lpcValues], rax; lpcbData
0x18010dc47  mov     [rsp+328h+lpcbMaxClassLen], rdi; lpData
0x18010dc4c  lea     rax, [rsp+328h+Type]
0x18010dc51  mov     [rsp+328h+lpcbMaxSubKeyLen], rax; lpType
0x18010dc56  mov     [rsp+328h+phkResult], rbx; unsigned int
0x18010dc5b  lea     r9, [rsp+328h+cchValueName]; lpcchValueName
0x18010dc63  mov     r8, [rsp+328h+lpValueName]; lpValueName
0x18010dc6b  mov     edx, r13d; dwIndex
0x18010dc6e  mov     rcx, [rsp+328h+hKey]; hKey
0x18010dc73  call    cs:__imp_RegEnumValueW
0x18010dc7a  nop     dword ptr [rax+rax+00h]
0x18010dc7f  cmp     eax, 103h
0x18010dc84  jz      loc_18010E3EA
0x18010dc8a  test    eax, eax
0x18010dc8c  jz      short loc_18010DCD9
0x18010dc8e  mov     rcx, [rsp+328h]; this
0x18010dc96  mov     r9d, eax; char *
0x18010dc99  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010dca0  mov     edx, 607h; void *
0x18010dca5  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18010dcaa  mov     ebx, eax
0x18010dcac  lea     rcx, [rsp+328h+var_288]
0x18010dcb4  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x18010dcb9  nop
0x18010dcba  lea     rcx, [rsp+328h+lpValueName]
0x18010dcc2  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x18010dcc7  nop
0x18010dcc8  lea     rcx, [rsp+328h+hKey]
0x18010dccd  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18010dcd2  mov     eax, ebx
0x18010dcd4  jmp     loc_18010E44A
0x18010dcd9  mov     rbx, [rsi+8]
0x18010dcdd  mov     rsi, [rsi]
0x18010dce0  jmp     short loc_18010DD01
0x18010dce2  mov     rdx, [rsp+328h+lpValueName]
0x18010dcea  mov     rcx, [rsi]
0x18010dced  call    cs:__imp__o__wcsicmp
0x18010dcf4  nop     dword ptr [rax+rax+00h]
0x18010dcf9  test    eax, eax
0x18010dcfb  jz      short loc_18010DD06
0x18010dcfd  add     rsi, 8
0x18010dd01  cmp     rsi, rbx
0x18010dd04  jnz     short loc_18010DCE2
0x18010dd06  mov     rax, [rsp+328h+var_280]
0x18010dd0e  cmp     rsi, [rax+8]
0x18010dd12  jz      loc_18010E3DA
0x18010dd18  xorps   xmm0, xmm0
0x18010dd1b  movups  [rsp+328h+var_128], xmm0
0x18010dd23  xor     esi, esi
0x18010dd25  mov     [rsp+328h+var_118], rsi
0x18010dd2d  mov     [rsp+328h+var_110], 7
0x18010dd39  mov     word ptr [rsp+328h+var_128], si
0x18010dd41  mov     eax, [rsp+328h+Type]
0x18010dd45  sub     eax, 1
0x18010dd48  jz      loc_18010E0E3
0x18010dd4e  sub     eax, 3
0x18010dd51  jz      loc_18010E094
0x18010dd57  sub     eax, 3
0x18010dd5a  jz      loc_18010DF6A
0x18010dd60  cmp     eax, 4
0x18010dd63  jz      loc_18010DE49
0x18010dd69  lea     rcx, [rsp+328h+var_228]
0x18010dd71  call    ??0?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)
0x18010dd76  nop
0x18010dd77  lea     rdx, aHexRegType; "\"Hex: (reg type "
0x18010dd7e  lea     rcx, [rsp+328h+var_218]
0x18010dd86  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18010dd8b  mov     edx, [rsp+328h+Type]
0x18010dd8f  mov     rcx, rax
0x18010dd92  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z; std::basic_ostream<ushort>::operator<<(ulong)
0x18010dd99  nop     dword ptr [rax+rax+00h]
0x18010dd9e  lea     rdx, asc_1801D48D8; " ): "
0x18010dda5  mov     rcx, rax
0x18010dda8  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18010ddad  mov     ebx, esi
0x18010ddaf  lea     rcx, [rsp+328h+var_218]
0x18010ddb7  cmp     ebx, [rsp+328h+cbData]
0x18010ddbb  jnb     short loc_18010DE05
0x18010ddbd  lea     rdx, ?hex@std@@YAAEAVios_base@1@AEAV21@@Z; std::hex(std::ios_base &)
0x18010ddc4  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z; std::basic_ostream<ushort>::operator<<(std::ios_base & (*)(std::ios_base &))
0x18010ddcb  nop     dword ptr [rax+rax+00h]
0x18010ddd0  mov     ecx, ebx
0x18010ddd2  movzx   edx, byte ptr [rcx+rdi]
0x18010ddd6  mov     rcx, rax
0x18010ddd9  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@H@Z; std::basic_ostream<ushort>::operator<<(int)
0x18010dde0  nop     dword ptr [rax+rax+00h]
0x18010dde5  mov     eax, [rsp+328h+cbData]
0x18010dde9  dec     eax
0x18010ddeb  cmp     ebx, eax
0x18010dded  jz      short loc_18010DE01
0x18010ddef  mov     edx, 2Ch ; ','
0x18010ddf4  lea     rcx, [rsp+328h+var_218]
0x18010ddfc  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@G@Z; std::basic_ostream<ushort>::operator<<(ushort)
0x18010de01  inc     ebx
0x18010de03  jmp     short loc_18010DDAF
0x18010de05  lea     rdx, asc_1801D32C4; "\""
0x18010de0c  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18010de11  lea     rdx, [rsp+328h+var_108]
0x18010de19  lea     rcx, [rsp+328h+var_228]
0x18010de21  call    ?str@?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::str(void)
0x18010de26  mov     rdx, rax
0x18010de29  lea     rcx, [rsp+328h+var_128]
0x18010de31  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18010de36  lea     rcx, [rsp+328h+var_108]
0x18010de3e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010de43  nop
0x18010de44  jmp     loc_18010E082
0x18010de49  mov     eax, 30h ; '0'
0x18010de4e  mov     [rsp+328h+var_68], ax
0x18010de56  xor     eax, eax
0x18010de58  movups  [rsp+328h+var_66], xmm0
0x18010de60  movups  xmmword ptr [rsp+328h+var_56], xmm0
0x18010de68  mov     qword ptr [rsp+328h+var_56+0Eh], rax
0x18010de70  lea     r9d, [rax+10h]
0x18010de74  lea     r8d, [rax+14h]
0x18010de78  lea     rdx, [rsp+328h+var_68]
0x18010de80  mov     rcx, [rdi]
0x18010de83  call    cs:__imp__o__ui64tow_s
0x18010de8a  nop     dword ptr [rax+rax+00h]
0x18010de8f  test    eax, eax
0x18010de91  jz      short loc_18010DEEC
0x18010de93  mov     rcx, [rsp+328h]; this
0x18010de9b  mov     r9d, eax; char *
0x18010de9e  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010dea5  mov     edx, 622h; void *
0x18010deaa  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18010deaf  mov     ebx, eax
0x18010deb1  lea     rcx, [rsp+328h+var_128]
0x18010deb9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010debe  nop
0x18010debf  lea     rcx, [rsp+328h+var_288]
0x18010dec7  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x18010decc  nop
0x18010decd  lea     rcx, [rsp+328h+lpValueName]
0x18010ded5  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x18010deda  nop
0x18010dedb  lea     rcx, [rsp+328h+hKey]
0x18010dee0  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18010dee5  mov     eax, ebx
0x18010dee7  jmp     loc_18010E44A
0x18010deec  lea     rdx, aRegQword0x; "\"REG_QWORD: 0x"
0x18010def3  lea     rcx, [rsp+328h+var_C8]
0x18010defb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18010df00  nop
0x18010df01  lea     r8, [rsp+328h+var_68]
0x18010df09  mov     rdx, rax
0x18010df0c  lea     rcx, [rsp+328h+var_A8]
0x18010df14  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18010df19  nop
0x18010df1a  lea     r8, asc_1801D32C4; "\""
0x18010df21  mov     rdx, rax
0x18010df24  lea     rcx, [rsp+328h+var_108]
0x18010df2c  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18010df31  mov     rdx, rax
0x18010df34  lea     rcx, [rsp+328h+var_128]
0x18010df3c  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18010df41  lea     rcx, [rsp+328h+var_108]
0x18010df49  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010df4e  nop
0x18010df4f  lea     rcx, [rsp+328h+var_A8]
0x18010df57  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010df5c  nop
0x18010df5d  lea     rcx, [rsp+328h+var_C8]
0x18010df65  jmp     loc_18010E157
0x18010df6a  lea     rcx, [rsp+328h+var_228]
0x18010df72  call    ??0?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)
0x18010df77  nop
0x18010df78  lea     rdx, asc_1801D4870; "["
0x18010df7f  lea     rcx, [rsp+328h+var_218]
0x18010df87  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18010df8c  mov     r14d, esi
0x18010df8f  mov     rbx, rdi
0x18010df92  cmp     r14d, [rsp+328h+cbData]
0x18010df97  jnb     loc_18010E03B
0x18010df9d  cmp     si, [rbx]
0x18010dfa0  jz      loc_18010E03B
0x18010dfa6  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18010dfaa  xor     eax, eax
0x18010dfac  inc     rsi
  ... truncated ...
```
