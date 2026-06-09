# WriteGPCSEWrapperPolicies(void)

- ea: `0x18012ece8`
- end: `0x18012f3b8`
- name: `?WriteGPCSEWrapperPolicies@@YAJXZ`
- size: `1744`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1801266fc`

## callees

- `0x180019000`
- `0x180019fc4`
- `0x1800a9e20`
- `0x1800e4348`
- `0x1800e66dc`
- `0x1800e7124`
- `0x1800e7c08`
- `0x1800e82e4`
- `0x1800ece5c`
- `0x1800ef5d8`
- `0x180104270`
- `0x1801058cc`
- `0x180105c40`
- `0x180120ce0`
- `0x180126a14`
- `0x180126a64`
- `0x1801279ac`
- `0x180127fa8`
- `0x1801283b0`
- `0x18012ece8`
- `0x1801312d0`
- `0x180132f88`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18012ee92`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18012f16f`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18012ee92`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18012f16f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18012ee34`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18012eeea`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18012f118`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18012f1c5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18012ee34`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18012eeea`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18012f118`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18012f1c5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18012eeb9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18012f0e2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18012f195`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18012eeb9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18012f0e2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18012f195`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18012ef2f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18012f20a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18012ef2f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18012f20a`

## string_xrefs

- `0x18012edc9`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012f051`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012f094`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012f320`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012f350`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 WriteGPCSEWrapperPolicies(void)
{
  __int64 v0; // rbx
  __int64 v1; // rax
  signed int v2; // ebx
  LSTATUS ValueW; // ebx
  DWORD v4; // esi
  HKEY v5; // rbx
  LSTATUS v6; // eax
  bool v7; // sf
  int v8; // eax
  signed int v9; // edi
  HKEY *v10; // rcx
  HKEY *p_hkey; // rcx
  HKEY v12; // rbx
  LSTATUS v13; // ebx
  DWORD v14; // esi
  HKEY v15; // rbx
  LSTATUS v16; // eax
  bool v17; // sf
  int v18; // eax
  int phkResult; // [rsp+20h] [rbp-E0h]
  int phkResulta; // [rsp+20h] [rbp-E0h]
  int phkResultb; // [rsp+20h] [rbp-E0h]
  int phkResultc; // [rsp+20h] [rbp-E0h]
  int phkResultd; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  HKEY v26; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cchName; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hkey; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v29[8]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v30; // [rsp+68h] [rbp-98h]
  __int64 v31; // [rsp+70h] [rbp-90h]
  DWORD pcbData; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v33[8]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v34[8]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v35; // [rsp+90h] [rbp-70h]
  __int64 v36; // [rsp+98h] [rbp-68h]
  _BYTE v37[40]; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD v38[10]; // [rsp+D0h] [rbp-30h] BYREF
  _DWORD v39[3]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v40[4]; // [rsp+12Ch] [rbp+2Ch] BYREF
  _QWORD v41[3]; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v42[8]; // [rsp+148h] [rbp+48h] BYREF
  WCHAR Name; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v44[526]; // [rsp+152h] [rbp+52h] BYREF
  _WORD pvData[2048]; // [rsp+360h] [rbp+260h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+13A8h] [rbp+12A8h]

  v41[0] = L"Target";
  v41[1] = L"Policy ID";
  v41[2] = L"XML";
  v39[0] = 30;
  v39[1] = 15;
  v39[2] = 55;
  Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::TableWithColumnHeaders(
    (Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders *)v38,
    L"GPCSEWrapper Policies",
    L"Policies Table");
  v0 = std::vector<int>::vector<int>(v29, v39, v40);
  v1 = std::vector<std::wstring>::vector<std::wstring>(v34, v41, v42);
  v2 = Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::WriteSectionHeaderForTable(
         v38,
         L"GP CSEs that are wrapped by MDM",
         v1,
         v0);
  std::vector<std::wstring>::_Tidy(v34);
  std::vector<enum TpmCapabilityPT>::_Tidy(v29);
  if ( v2 >= 0 )
  {
    pvData[0] = 0;
    pcbData = 2048;
    cchName = 261;
    Name = 0;
    memset_0(v44, 0, 0x208u);
    hKey = 0;
    ValueW = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\GPCSEWrapper", 0, 0x20019u, &hKey);
    if ( ValueW != 2 )
    {
      v4 = 0;
      while ( !ValueW )
      {
        hkey = 0;
        std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>(v29);
        cchName = 261;
        ValueW = RegEnumKeyExW(hKey, v4, &Name, &cchName, 0, 0, 0, 0);
        if ( !ValueW )
        {
          v5 = hkey;
          if ( hkey )
          {
            wil::last_error_context::last_error_context((wil::last_error_context *)&v26);
            RegCloseKey(v5);
            wil::last_error_context::~last_error_context((wil::last_error_context *)&v26);
          }
          hkey = 0;
          v6 = RegOpenKeyExW(hKey, &Name, 0, 0x20019u, &hkey);
          v2 = v6;
          if ( v6 > 0 )
            v2 = (unsigned __int16)v6 | 0x80070000;
          if ( v2 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x982,
              (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
              (const char *)(unsigned int)v2,
              phkResulta);
            std::vector<std::wstring>::_Tidy(v29);
            p_hkey = &hkey;
LABEL_29:
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(p_hkey);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
            goto LABEL_58;
          }
          ValueW = RegGetValueW(hkey, 0, L"XML", 2u, 0, pvData, &pcbData);
          v7 = ValueW < 0;
          if ( ValueW > 0 )
            v7 = 1;
          if ( !v7 )
          {
            std::vector<std::wstring>::clear(v29);
            std::wstring::wstring(v34, L"Device");
            if ( v30 == v31 )
              std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(v29, v30, v34);
            else
              std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(v29, v34);
            std::wstring::_Tidy_deallocate(v34);
            std::wstring::wstring(v34, &Name);
            if ( v30 == v31 )
              std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(v29, v30, v34);
            else
              std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(v29, v34);
            std::wstring::_Tidy_deallocate(v34);
            std::wstring::wstring(v34, pvData);
            if ( v30 == v31 )
              std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(v29, v30, v34);
            else
              std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(v29, v34);
            std::wstring::_Tidy_deallocate(v34);
            v8 = Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::AddTableRow(v38, v29);
            v9 = v8;
            if ( v8 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x98A,
                (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
                (const char *)(unsigned int)v8,
                phkResultb);
              std::vector<std::wstring>::_Tidy(v29);
              v10 = &hkey;
LABEL_27:
              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v10);
              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
              v2 = v9;
              goto LABEL_58;
            }
          }
        }
        std::vector<std::wstring>::_Tidy(v29);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
        ++v4;
      }
      v12 = hKey;
      if ( hKey )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v26);
        RegCloseKey(v12);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&v26);
      }
      hKey = 0;
      v13 = RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\GPCSEWrapper", 0, 0x20019u, &hKey);
      if ( v13 != 2 )
      {
        v14 = 0;
        while ( !v13 )
        {
          v26 = 0;
          std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>(v34);
          cchName = 261;
          v13 = RegEnumKeyExW(hKey, v14, &Name, &cchName, 0, 0, 0, 0);
          if ( !v13 )
          {
            v15 = v26;
            if ( v26 )
            {
              wil::last_error_context::last_error_context((wil::last_error_context *)v33);
              RegCloseKey(v15);
              wil::last_error_context::~last_error_context((wil::last_error_context *)v33);
            }
            v26 = 0;
            v16 = RegOpenKeyExW(hKey, &Name, 0, 0x20019u, &v26);
            v2 = v16;
            if ( v16 > 0 )
              v2 = (unsigned __int16)v16 | 0x80070000;
            if ( v2 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x99F,
                (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
                (const char *)(unsigned int)v2,
                phkResultc);
              std::vector<std::wstring>::_Tidy(v34);
              p_hkey = &v26;
              goto LABEL_29;
            }
            v13 = RegGetValueW(v26, 0, L"XML", 2u, 0, pvData, &pcbData);
            v17 = v13 < 0;
            if ( v13 > 0 )
              v17 = 1;
            if ( !v17 )
            {
              std::vector<std::wstring>::clear(v34);
              std::wstring::wstring(v37, L"User");
              if ( v35 == v36 )
                std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(v34, v35, v37);
              else
                std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(v34, v37);
              std::wstring::_Tidy_deallocate(v37);
              std::wstring::wstring(v37, &Name);
              if ( v35 == v36 )
                std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(v34, v35, v37);
              else
                std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(v34, v37);
              std::wstring::_Tidy_deallocate(v37);
              std::wstring::wstring(v37, pvData);
              if ( v35 == v36 )
                std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(v34, v35, v37);
              else
                std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(v34, v37);
              std::wstring::_Tidy_deallocate(v37);
              v18 = Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::AddTableRow(v38, v34);
              v9 = v18;
              if ( v18 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x9A7,
                  (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
                  (const char *)(unsigned int)v18,
                  phkResultd);
                std::vector<std::wstring>::_Tidy(v34);
                v10 = &v26;
                goto LABEL_27;
              }
            }
          }
          std::vector<std::wstring>::_Tidy(v34);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v26);
          ++v14;
        }
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    v2 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x968,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
      (const char *)(unsigned int)v2,
      phkResult);
  }
LABEL_58:
  v38[0] = &Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::`vftable';
  Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable((Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable *)v38);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18012ece8  push    rbp
0x18012ecea  push    rbx
0x18012eceb  push    rsi
0x18012ecec  push    rdi
0x18012eced  push    r14
0x18012ecef  push    r15
0x18012ecf1  lea     rbp, [rsp-1278h]
0x18012ecf9  mov     eax, 1378h
0x18012ecfe  call    _alloca_probe
0x18012ed03  sub     rsp, rax
0x18012ed06  mov     rax, cs:__security_cookie
0x18012ed0d  xor     rax, rsp
0x18012ed10  mov     [rbp+12A0h+var_40], rax
0x18012ed17  lea     rax, aTarget; "Target"
0x18012ed1e  mov     [rbp+12A0h+var_1270], rax
0x18012ed22  lea     rax, aPolicyId; "Policy ID"
0x18012ed29  mov     [rbp+12A0h+var_1268], rax
0x18012ed2d  lea     rdi, aXml; "XML"
0x18012ed34  mov     [rbp+12A0h+var_1260], rdi
0x18012ed38  mov     [rbp+12A0h+var_1280], 1Eh
0x18012ed3f  mov     [rbp+12A0h+var_127C], 0Fh
0x18012ed46  mov     [rbp+12A0h+var_1278], 37h ; '7'
0x18012ed4d  lea     r8, aPoliciesTable; "Policies Table"
0x18012ed54  lea     rdx, aGpcsewrapperPo; "GPCSEWrapper Policies"
0x18012ed5b  lea     rcx, [rbp+12A0h+var_12D0]; this
0x18012ed5f  call    ??0TableWithColumnHeaders@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAA@PEBG0@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::TableWithColumnHeaders(ushort const *,ushort const *)
0x18012ed64  nop
0x18012ed65  lea     r8, [rbp+12A0h+var_1274]
0x18012ed69  lea     rdx, [rbp+12A0h+var_1280]
0x18012ed6d  lea     rcx, [rsp+13A0h+var_1340]
0x18012ed72  call    ??$?0PEBH$0A@@?$vector@HV?$allocator@H@std@@@std@@QEAA@PEBH0AEBV?$allocator@H@1@@Z; std::vector<int>::vector<int>(int const *,int const *,std::allocator<int> const &)
0x18012ed77  mov     rbx, rax
0x18012ed7a  lea     r8, [rbp+12A0h+var_1258]
0x18012ed7e  lea     rdx, [rbp+12A0h+var_1270]
0x18012ed82  lea     rcx, [rbp+12A0h+var_1318]
0x18012ed86  call    ??$?0PEBQEBG$0A@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@PEBQEBG0AEBV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@@Z; std::vector<std::wstring>::vector<std::wstring>(ushort const * const *,ushort const * const *,std::allocator<std::wstring> const &)
0x18012ed8b  nop
0x18012ed8c  mov     r9, rbx
0x18012ed8f  mov     r8, rax
0x18012ed92  lea     rdx, aGpCsesThatAreW; "GP CSEs that are wrapped by MDM"
0x18012ed99  lea     rcx, [rbp+12A0h+var_12D0]
0x18012ed9d  call    ?WriteSectionHeaderForTable@TableWithColumnHeaders@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAAJPEBGAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAV?$vector@HV?$allocator@H@std@@@7@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::WriteSectionHeaderForTable(ushort const *,std::vector<std::wstring> &,std::vector<int> &)
0x18012eda2  mov     ebx, eax
0x18012eda4  lea     rcx, [rbp+12A0h+var_1318]
0x18012eda8  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18012edad  nop
0x18012edae  lea     rcx, [rsp+13A0h+var_1340]
0x18012edb3  call    ?_Tidy@?$vector@W4TpmCapabilityPT@@V?$allocator@W4TpmCapabilityPT@@@std@@@std@@AEAAXXZ; std::vector<TpmCapabilityPT>::_Tidy(void)
0x18012edb8  xor     r14d, r14d
0x18012edbb  test    ebx, ebx
0x18012edbd  jns     short loc_18012EDDF
0x18012edbf  mov     rcx, [rbp+12A8h]; this
0x18012edc6  mov     r9d, ebx; char *
0x18012edc9  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18012edd0  mov     edx, 968h; void *
0x18012edd5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012edda  jmp     loc_18012F383
0x18012eddf  mov     [rbp+12A0h+pvData], r14w
0x18012ede7  mov     [rsp+13A0h+pcbData], 800h
0x18012edef  mov     [rsp+13A0h+cchName], 105h
0x18012edf7  mov     [rbp+12A0h+Name], r14w
0x18012edfc  xor     edx, edx; Val
0x18012edfe  mov     r8d, 208h; Size
0x18012ee04  lea     rcx, [rbp+12A0h+var_124E]; void *
0x18012ee08  call    memset_0
0x18012ee0d  nop
0x18012ee0e  mov     [rsp+13A0h+hKey], r14
0x18012ee13  lea     rax, [rsp+13A0h+hKey]
0x18012ee18  mov     [rsp+13A0h+phkResult], rax; phkResult
0x18012ee1d  mov     r9d, 20019h; samDesired
0x18012ee23  xor     r8d, r8d; ulOptions
0x18012ee26  lea     rdx, aSoftwareMicros_13; "Software\\Microsoft\\GPCSEWrapper"
0x18012ee2d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18012ee34  call    cs:__imp_RegOpenKeyExW
0x18012ee3a  mov     ebx, eax
0x18012ee3c  cmp     eax, 2
0x18012ee3f  jz      loc_18012F376
0x18012ee45  mov     esi, r14d
0x18012ee48  mov     r15d, 80070000h
0x18012ee4e  test    ebx, ebx
0x18012ee50  jnz     loc_18012F0CB
0x18012ee56  mov     [rsp+13A0h+hkey], r14
0x18012ee5b  lea     rcx, [rsp+13A0h+var_1340]
0x18012ee60  call    ??0?$vector@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>(void)
0x18012ee65  nop
0x18012ee66  mov     [rsp+13A0h+cchName], 105h
0x18012ee6e  mov     [rsp+13A0h+lpftLastWriteTime], r14; lpftLastWriteTime
0x18012ee73  mov     [rsp+13A0h+lpcchClass], r14; lpcchClass
0x18012ee78  mov     [rsp+13A0h+lpClass], r14; lpClass
0x18012ee7d  mov     [rsp+13A0h+phkResult], r14; lpReserved
0x18012ee82  lea     r9, [rsp+13A0h+cchName]; lpcchName
0x18012ee87  lea     r8, [rbp+12A0h+Name]; lpName
0x18012ee8b  mov     edx, esi; dwIndex
0x18012ee8d  mov     rcx, [rsp+13A0h+hKey]; hKey
0x18012ee92  call    cs:__imp_RegEnumKeyExW
0x18012ee98  mov     ebx, eax
0x18012ee9a  test    eax, eax
0x18012ee9c  jnz     loc_18012F02B
0x18012eea2  mov     rbx, [rsp+13A0h+hkey]
0x18012eea7  test    rbx, rbx
0x18012eeaa  jz      short loc_18012EEC9
0x18012eeac  lea     rcx, [rsp+13A0h+var_1358]; this
0x18012eeb1  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18012eeb6  mov     rcx, rbx; hKey
0x18012eeb9  call    cs:__imp_RegCloseKey
0x18012eebf  lea     rcx, [rsp+13A0h+var_1358]; this
0x18012eec4  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18012eec9  mov     [rsp+13A0h+hkey], r14
0x18012eece  lea     rax, [rsp+13A0h+hkey]
0x18012eed3  mov     [rsp+13A0h+phkResult], rax; int
0x18012eed8  mov     r9d, 20019h; samDesired
0x18012eede  xor     r8d, r8d; ulOptions
0x18012eee1  lea     rdx, [rbp+12A0h+Name]; lpSubKey
0x18012eee5  mov     rcx, [rsp+13A0h+hKey]; hKey
0x18012eeea  call    cs:__imp_RegOpenKeyExW
0x18012eef0  mov     ebx, eax
0x18012eef2  test    eax, eax
0x18012eef4  jle     short loc_18012EEFC
0x18012eef6  movzx   ebx, ax
0x18012eef9  or      ebx, r15d
0x18012eefc  test    ebx, ebx
0x18012eefe  js      loc_18012F08A
0x18012ef04  lea     rax, [rsp+13A0h+pcbData]
0x18012ef09  mov     [rsp+13A0h+lpcchClass], rax; pcbData
0x18012ef0e  lea     rax, [rbp+12A0h+pvData]
0x18012ef15  mov     [rsp+13A0h+lpClass], rax; pvData
0x18012ef1a  mov     [rsp+13A0h+phkResult], r14; int
0x18012ef1f  mov     r9d, 2; dwFlags
0x18012ef25  mov     r8, rdi; lpValue
0x18012ef28  xor     edx, edx; lpSubKey
0x18012ef2a  mov     rcx, [rsp+13A0h+hkey]; hkey
0x18012ef2f  call    cs:__imp_RegGetValueW
0x18012ef35  mov     ebx, eax
0x18012ef37  test    eax, eax
0x18012ef39  jle     short loc_18012EF43
0x18012ef3b  movzx   eax, ax
0x18012ef3e  or      eax, r15d
0x18012ef41  test    eax, eax
0x18012ef43  js      loc_18012F02B
0x18012ef49  lea     rcx, [rsp+13A0h+var_1340]
0x18012ef4e  call    ?clear@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAXXZ; std::vector<std::wstring>::clear(void)
0x18012ef53  lea     rdx, aDevice; "Device"
0x18012ef5a  lea     rcx, [rbp+12A0h+var_1318]
0x18012ef5e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18012ef63  nop
0x18012ef64  mov     rdx, [rsp+13A0h+var_1338]
0x18012ef69  lea     rcx, [rsp+13A0h+var_1340]
0x18012ef6e  cmp     rdx, [rsp+13A0h+var_1330]
0x18012ef73  jz      short loc_18012EF80
0x18012ef75  lea     rdx, [rbp+12A0h+var_1318]
0x18012ef79  call    ??$_Emplace_back_with_unused_capacity@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(std::wstring &&)
0x18012ef7e  jmp     short loc_18012EF8A
0x18012ef80  lea     r8, [rbp+12A0h+var_1318]
0x18012ef84  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x18012ef89  nop
0x18012ef8a  lea     rcx, [rbp+12A0h+var_1318]
0x18012ef8e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012ef93  lea     rdx, [rbp+12A0h+Name]
0x18012ef97  lea     rcx, [rbp+12A0h+var_1318]
0x18012ef9b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18012efa0  nop
0x18012efa1  mov     rdx, [rsp+13A0h+var_1338]
0x18012efa6  lea     rcx, [rsp+13A0h+var_1340]
0x18012efab  cmp     rdx, [rsp+13A0h+var_1330]
0x18012efb0  jz      short loc_18012EFBD
0x18012efb2  lea     rdx, [rbp+12A0h+var_1318]
0x18012efb6  call    ??$_Emplace_back_with_unused_capacity@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(std::wstring &&)
0x18012efbb  jmp     short loc_18012EFC7
0x18012efbd  lea     r8, [rbp+12A0h+var_1318]
0x18012efc1  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x18012efc6  nop
0x18012efc7  lea     rcx, [rbp+12A0h+var_1318]
0x18012efcb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012efd0  lea     rdx, [rbp+12A0h+pvData]
0x18012efd7  lea     rcx, [rbp+12A0h+var_1318]
0x18012efdb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18012efe0  nop
0x18012efe1  mov     rdx, [rsp+13A0h+var_1338]
0x18012efe6  lea     rcx, [rsp+13A0h+var_1340]
0x18012efeb  cmp     rdx, [rsp+13A0h+var_1330]
0x18012eff0  jz      short loc_18012EFFD
0x18012eff2  lea     rdx, [rbp+12A0h+var_1318]
0x18012eff6  call    ??$_Emplace_back_with_unused_capacity@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(std::wstring &&)
0x18012effb  jmp     short loc_18012F007
0x18012effd  lea     r8, [rbp+12A0h+var_1318]
0x18012f001  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x18012f006  nop
0x18012f007  lea     rcx, [rbp+12A0h+var_1318]
0x18012f00b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012f010  lea     rdx, [rsp+13A0h+var_1340]
0x18012f015  lea     rcx, [rbp+12A0h+var_12D0]
0x18012f019  call    ?AddTableRow@TableWithColumnHeaders@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAAJAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::AddTableRow(std::vector<std::wstring> &)
0x18012f01e  mov     edi, eax
0x18012f020  test    eax, eax
0x18012f022  js      short loc_18012F047
0x18012f024  lea     rdi, aXml; "XML"
0x18012f02b  lea     rcx, [rsp+13A0h+var_1340]
0x18012f030  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18012f035  nop
0x18012f036  lea     rcx, [rsp+13A0h+hkey]
0x18012f03b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18012f040  inc     esi
0x18012f042  jmp     loc_18012EE4E
0x18012f047  mov     rcx, [rbp+12A8h]; this
0x18012f04e  mov     r9d, edi; char *
0x18012f051  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18012f058  mov     edx, 98Ah; void *
0x18012f05d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012f062  nop
0x18012f063  lea     rcx, [rsp+13A0h+var_1340]
0x18012f068  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18012f06d  nop
0x18012f06e  lea     rcx, [rsp+13A0h+hkey]
0x18012f073  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18012f078  nop
0x18012f079  lea     rcx, [rsp+13A0h+hKey]
0x18012f07e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18012f083  mov     ebx, edi
0x18012f085  jmp     loc_18012F383
0x18012f08a  mov     rcx, [rbp+12A8h]; this
0x18012f091  mov     r9d, ebx; char *
0x18012f094  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18012f09b  mov     edx, 982h; void *
0x18012f0a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012f0a5  nop
0x18012f0a6  lea     rcx, [rsp+13A0h+var_1340]
0x18012f0ab  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18012f0b0  nop
0x18012f0b1  lea     rcx, [rsp+13A0h+hkey]
0x18012f0b6  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18012f0bb  nop
0x18012f0bc  lea     rcx, [rsp+13A0h+hKey]
0x18012f0c1  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18012f0c6  jmp     loc_18012F383
0x18012f0cb  mov     rbx, [rsp+13A0h+hKey]
0x18012f0d0  test    rbx, rbx
0x18012f0d3  jz      short loc_18012F0F2
0x18012f0d5  lea     rcx, [rsp+13A0h+var_1358]; this
0x18012f0da  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18012f0df  mov     rcx, rbx; hKey
0x18012f0e2  call    cs:__imp_RegCloseKey
0x18012f0e8  lea     rcx, [rsp+13A0h+var_1358]; this
0x18012f0ed  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18012f0f2  mov     [rsp+13A0h+hKey], r14
0x18012f0f7  lea     rax, [rsp+13A0h+hKey]
0x18012f0fc  mov     [rsp+13A0h+phkResult], rax; phkResult
0x18012f101  mov     r9d, 20019h; samDesired
0x18012f107  xor     r8d, r8d; ulOptions
0x18012f10a  lea     rdx, aSoftwareMicros_13; "Software\\Microsoft\\GPCSEWrapper"
0x18012f111  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18012f118  call    cs:__imp_RegOpenKeyExW
0x18012f11e  mov     ebx, eax
0x18012f120  cmp     eax, 2
0x18012f123  jz      loc_18012F376
0x18012f129  mov     esi, r14d
0x18012f12c  test    ebx, ebx
0x18012f12e  jnz     loc_18012F376
0x18012f134  mov     [rsp+13A0h+var_1358], r14
0x18012f139  lea     rcx, [rbp+12A0h+var_1318]
0x18012f13d  call    ??0?$vector@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>(void)
0x18012f142  nop
0x18012f143  mov     [rsp+13A0h+cchName], 105h
0x18012f14b  mov     [rsp+13A0h+lpftLastWriteTime], r14; lpftLastWriteTime
0x18012f150  mov     [rsp+13A0h+lpcchClass], r14; lpcchClass
0x18012f155  mov     [rsp+13A0h+lpClass], r14; lpClass
0x18012f15a  mov     [rsp+13A0h+phkResult], r14; lpReserved
0x18012f15f  lea     r9, [rsp+13A0h+cchName]; lpcchName
0x18012f164  lea     r8, [rbp+12A0h+Name]; lpName
0x18012f168  mov     edx, esi; dwIndex
0x18012f16a  mov     rcx, [rsp+13A0h+hKey]; hKey
0x18012f16f  call    cs:__imp_RegEnumKeyExW
0x18012f175  mov     ebx, eax
0x18012f177  test    eax, eax
0x18012f179  jnz     loc_18012F2FB
0x18012f17f  mov     rbx, [rsp+13A0h+var_1358]
0x18012f184  test    rbx, rbx
0x18012f187  jz      short loc_18012F1A4
0x18012f189  lea     rcx, [rbp+12A0h+var_1320]; this
0x18012f18d  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18012f192  mov     rcx, rbx; hKey
0x18012f195  call    cs:__imp_RegCloseKey
0x18012f19b  lea     rcx, [rbp+12A0h+var_1320]; this
0x18012f19f  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18012f1a4  mov     [rsp+13A0h+var_1358], r14
0x18012f1a9  lea     rax, [rsp+13A0h+var_1358]
0x18012f1ae  mov     [rsp+13A0h+phkResult], rax; int
0x18012f1b3  mov     r9d, 20019h; samDesired
0x18012f1b9  xor     r8d, r8d; ulOptions
0x18012f1bc  lea     rdx, [rbp+12A0h+Name]; lpSubKey
0x18012f1c0  mov     rcx, [rsp+13A0h+hKey]; hKey
0x18012f1c5  call    cs:__imp_RegOpenKeyExW
0x18012f1cb  mov     ebx, eax
0x18012f1cd  test    eax, eax
0x18012f1cf  jle     short loc_18012F1D7
0x18012f1d1  movzx   ebx, ax
0x18012f1d4  or      ebx, r15d
0x18012f1d7  test    ebx, ebx
0x18012f1d9  js      loc_18012F346
0x18012f1df  lea     rax, [rsp+13A0h+pcbData]
0x18012f1e4  mov     [rsp+13A0h+lpcchClass], rax; pcbData
  ... truncated ...
```
