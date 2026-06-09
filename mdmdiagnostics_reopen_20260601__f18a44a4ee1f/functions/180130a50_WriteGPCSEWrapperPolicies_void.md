# WriteGPCSEWrapperPolicies(void)

- ea: `0x180130a50`
- end: `0x180131163`
- name: `?WriteGPCSEWrapperPolicies@@YAJXZ`
- size: `1811`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180128138`

## callees

- `0x180019080`
- `0x18001a054`
- `0x1800a9fc0`
- `0x1800e4408`
- `0x1800e68b0`
- `0x1800e734c`
- `0x1800e7de8`
- `0x1800e8508`
- `0x1800ed46c`
- `0x1800efd9c`
- `0x180105480`
- `0x180106b6c`
- `0x180106ee0`
- `0x18012269c`
- `0x18012845c`
- `0x1801284b0`
- `0x180129498`
- `0x180129aac`
- `0x180129ee0`
- `0x180130a50`
- `0x1801330e0`
- `0x180134e3c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180130c00`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180130f01`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180130c00`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180130f01`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180130b9c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180130c64`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180130ea4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180130f63`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180130b9c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180130c64`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180130ea4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180130f63`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180130c2d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180130e68`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180130f2d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180130c2d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180130e68`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180130f2d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180130caf`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180130fae`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180130caf`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180130fae`

## string_xrefs

- `0x180130b31`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x180130dd7`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x180130e1a`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x1801310ca`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x1801310fa`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`

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
0x180130a50  push    rbp
0x180130a52  push    rbx
0x180130a53  push    rsi
0x180130a54  push    rdi
0x180130a55  push    r14
0x180130a57  push    r15
0x180130a59  lea     rbp, [rsp-1278h]
0x180130a61  mov     eax, 1378h
0x180130a66  call    _alloca_probe
0x180130a6b  sub     rsp, rax
0x180130a6e  mov     rax, cs:__security_cookie
0x180130a75  xor     rax, rsp
0x180130a78  mov     [rbp+12A0h+var_40], rax
0x180130a7f  lea     rax, aTarget; "Target"
0x180130a86  mov     [rbp+12A0h+var_1270], rax
0x180130a8a  lea     rax, aPolicyId; "Policy ID"
0x180130a91  mov     [rbp+12A0h+var_1268], rax
0x180130a95  lea     rdi, aXml; "XML"
0x180130a9c  mov     [rbp+12A0h+var_1260], rdi
0x180130aa0  mov     [rbp+12A0h+var_1280], 1Eh
0x180130aa7  mov     [rbp+12A0h+var_127C], 0Fh
0x180130aae  mov     [rbp+12A0h+var_1278], 37h ; '7'
0x180130ab5  lea     r8, aPoliciesTable; "Policies Table"
0x180130abc  lea     rdx, aGpcsewrapperPo; "GPCSEWrapper Policies"
0x180130ac3  lea     rcx, [rbp+12A0h+var_12D0]; this
0x180130ac7  call    ??0TableWithColumnHeaders@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAA@PEBG0@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::TableWithColumnHeaders(ushort const *,ushort const *)
0x180130acc  nop
0x180130acd  lea     r8, [rbp+12A0h+var_1274]
0x180130ad1  lea     rdx, [rbp+12A0h+var_1280]
0x180130ad5  lea     rcx, [rsp+13A0h+var_1340]
0x180130ada  call    ??$?0PEBH$0A@@?$vector@HV?$allocator@H@std@@@std@@QEAA@PEBH0AEBV?$allocator@H@1@@Z; std::vector<int>::vector<int>(int const *,int const *,std::allocator<int> const &)
0x180130adf  mov     rbx, rax
0x180130ae2  lea     r8, [rbp+12A0h+var_1258]
0x180130ae6  lea     rdx, [rbp+12A0h+var_1270]
0x180130aea  lea     rcx, [rbp+12A0h+var_1318]
0x180130aee  call    ??$?0PEBQEBG$0A@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@PEBQEBG0AEBV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@@Z; std::vector<std::wstring>::vector<std::wstring>(ushort const * const *,ushort const * const *,std::allocator<std::wstring> const &)
0x180130af3  nop
0x180130af4  mov     r9, rbx
0x180130af7  mov     r8, rax
0x180130afa  lea     rdx, aGpCsesThatAreW; "GP CSEs that are wrapped by MDM"
0x180130b01  lea     rcx, [rbp+12A0h+var_12D0]
0x180130b05  call    ?WriteSectionHeaderForTable@TableWithColumnHeaders@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAAJPEBGAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAV?$vector@HV?$allocator@H@std@@@7@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::WriteSectionHeaderForTable(ushort const *,std::vector<std::wstring> &,std::vector<int> &)
0x180130b0a  mov     ebx, eax
0x180130b0c  lea     rcx, [rbp+12A0h+var_1318]
0x180130b10  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180130b15  nop
0x180130b16  lea     rcx, [rsp+13A0h+var_1340]
0x180130b1b  call    ?_Tidy@?$vector@W4TpmCapabilityPT@@V?$allocator@W4TpmCapabilityPT@@@std@@@std@@AEAAXXZ; std::vector<TpmCapabilityPT>::_Tidy(void)
0x180130b20  xor     r14d, r14d
0x180130b23  test    ebx, ebx
0x180130b25  jns     short loc_180130B47
0x180130b27  mov     rcx, [rbp+12A8h]; this
0x180130b2e  mov     r9d, ebx; char *
0x180130b31  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180130b38  mov     edx, 968h; void *
0x180130b3d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180130b42  jmp     loc_18013112D
0x180130b47  mov     [rbp+12A0h+pvData], r14w
0x180130b4f  mov     [rsp+13A0h+pcbData], 800h
0x180130b57  mov     [rsp+13A0h+cchName], 105h
0x180130b5f  mov     [rbp+12A0h+Name], r14w
0x180130b64  xor     edx, edx; Val
0x180130b66  mov     r8d, 208h; Size
0x180130b6c  lea     rcx, [rbp+12A0h+var_124E]; void *
0x180130b70  call    memset_0
0x180130b75  nop
0x180130b76  mov     [rsp+13A0h+hKey], r14
0x180130b7b  lea     rax, [rsp+13A0h+hKey]
0x180130b80  mov     [rsp+13A0h+phkResult], rax; phkResult
0x180130b85  mov     r9d, 20019h; samDesired
0x180130b8b  xor     r8d, r8d; ulOptions
0x180130b8e  lea     rdx, aSoftwareMicros_13; "Software\\Microsoft\\GPCSEWrapper"
0x180130b95  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180130b9c  call    cs:__imp_RegOpenKeyExW
0x180130ba3  nop     dword ptr [rax+rax+00h]
0x180130ba8  mov     ebx, eax
0x180130baa  cmp     eax, 2
0x180130bad  jz      loc_180131120
0x180130bb3  mov     esi, r14d
0x180130bb6  mov     r15d, 80070000h
0x180130bbc  test    ebx, ebx
0x180130bbe  jnz     loc_180130E51
0x180130bc4  mov     [rsp+13A0h+hkey], r14
0x180130bc9  lea     rcx, [rsp+13A0h+var_1340]
0x180130bce  call    ??0?$vector@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>(void)
0x180130bd3  nop
0x180130bd4  mov     [rsp+13A0h+cchName], 105h
0x180130bdc  mov     [rsp+13A0h+lpftLastWriteTime], r14; lpftLastWriteTime
0x180130be1  mov     [rsp+13A0h+lpcchClass], r14; lpcchClass
0x180130be6  mov     [rsp+13A0h+lpClass], r14; lpClass
0x180130beb  mov     [rsp+13A0h+phkResult], r14; lpReserved
0x180130bf0  lea     r9, [rsp+13A0h+cchName]; lpcchName
0x180130bf5  lea     r8, [rbp+12A0h+Name]; lpName
0x180130bf9  mov     edx, esi; dwIndex
0x180130bfb  mov     rcx, [rsp+13A0h+hKey]; hKey
0x180130c00  call    cs:__imp_RegEnumKeyExW
0x180130c07  nop     dword ptr [rax+rax+00h]
0x180130c0c  mov     ebx, eax
0x180130c0e  test    eax, eax
0x180130c10  jnz     loc_180130DB1
0x180130c16  mov     rbx, [rsp+13A0h+hkey]
0x180130c1b  test    rbx, rbx
0x180130c1e  jz      short loc_180130C43
0x180130c20  lea     rcx, [rsp+13A0h+var_1358]; this
0x180130c25  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180130c2a  mov     rcx, rbx; hKey
0x180130c2d  call    cs:__imp_RegCloseKey
0x180130c34  nop     dword ptr [rax+rax+00h]
0x180130c39  lea     rcx, [rsp+13A0h+var_1358]; this
0x180130c3e  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180130c43  mov     [rsp+13A0h+hkey], r14
0x180130c48  lea     rax, [rsp+13A0h+hkey]
0x180130c4d  mov     [rsp+13A0h+phkResult], rax; int
0x180130c52  mov     r9d, 20019h; samDesired
0x180130c58  xor     r8d, r8d; ulOptions
0x180130c5b  lea     rdx, [rbp+12A0h+Name]; lpSubKey
0x180130c5f  mov     rcx, [rsp+13A0h+hKey]; hKey
0x180130c64  call    cs:__imp_RegOpenKeyExW
0x180130c6b  nop     dword ptr [rax+rax+00h]
0x180130c70  mov     ebx, eax
0x180130c72  test    eax, eax
0x180130c74  jle     short loc_180130C7C
0x180130c76  movzx   ebx, ax
0x180130c79  or      ebx, r15d
0x180130c7c  test    ebx, ebx
0x180130c7e  js      loc_180130E10
0x180130c84  lea     rax, [rsp+13A0h+pcbData]
0x180130c89  mov     [rsp+13A0h+lpcchClass], rax; pcbData
0x180130c8e  lea     rax, [rbp+12A0h+pvData]
0x180130c95  mov     [rsp+13A0h+lpClass], rax; pvData
0x180130c9a  mov     [rsp+13A0h+phkResult], r14; int
0x180130c9f  mov     r9d, 2; dwFlags
0x180130ca5  mov     r8, rdi; lpValue
0x180130ca8  xor     edx, edx; lpSubKey
0x180130caa  mov     rcx, [rsp+13A0h+hkey]; hkey
0x180130caf  call    cs:__imp_RegGetValueW
0x180130cb6  nop     dword ptr [rax+rax+00h]
0x180130cbb  mov     ebx, eax
0x180130cbd  test    eax, eax
0x180130cbf  jle     short loc_180130CC9
0x180130cc1  movzx   eax, ax
0x180130cc4  or      eax, r15d
0x180130cc7  test    eax, eax
0x180130cc9  js      loc_180130DB1
0x180130ccf  lea     rcx, [rsp+13A0h+var_1340]
0x180130cd4  call    ?clear@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAXXZ; std::vector<std::wstring>::clear(void)
0x180130cd9  lea     rdx, aDevice; "Device"
0x180130ce0  lea     rcx, [rbp+12A0h+var_1318]
0x180130ce4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180130ce9  nop
0x180130cea  mov     rdx, [rsp+13A0h+var_1338]
0x180130cef  lea     rcx, [rsp+13A0h+var_1340]
0x180130cf4  cmp     rdx, [rsp+13A0h+var_1330]
0x180130cf9  jz      short loc_180130D06
0x180130cfb  lea     rdx, [rbp+12A0h+var_1318]
0x180130cff  call    ??$_Emplace_back_with_unused_capacity@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(std::wstring &&)
0x180130d04  jmp     short loc_180130D10
0x180130d06  lea     r8, [rbp+12A0h+var_1318]
0x180130d0a  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x180130d0f  nop
0x180130d10  lea     rcx, [rbp+12A0h+var_1318]
0x180130d14  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180130d19  lea     rdx, [rbp+12A0h+Name]
0x180130d1d  lea     rcx, [rbp+12A0h+var_1318]
0x180130d21  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180130d26  nop
0x180130d27  mov     rdx, [rsp+13A0h+var_1338]
0x180130d2c  lea     rcx, [rsp+13A0h+var_1340]
0x180130d31  cmp     rdx, [rsp+13A0h+var_1330]
0x180130d36  jz      short loc_180130D43
0x180130d38  lea     rdx, [rbp+12A0h+var_1318]
0x180130d3c  call    ??$_Emplace_back_with_unused_capacity@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(std::wstring &&)
0x180130d41  jmp     short loc_180130D4D
0x180130d43  lea     r8, [rbp+12A0h+var_1318]
0x180130d47  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x180130d4c  nop
0x180130d4d  lea     rcx, [rbp+12A0h+var_1318]
0x180130d51  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180130d56  lea     rdx, [rbp+12A0h+pvData]
0x180130d5d  lea     rcx, [rbp+12A0h+var_1318]
0x180130d61  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180130d66  nop
0x180130d67  mov     rdx, [rsp+13A0h+var_1338]
0x180130d6c  lea     rcx, [rsp+13A0h+var_1340]
0x180130d71  cmp     rdx, [rsp+13A0h+var_1330]
0x180130d76  jz      short loc_180130D83
0x180130d78  lea     rdx, [rbp+12A0h+var_1318]
0x180130d7c  call    ??$_Emplace_back_with_unused_capacity@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(std::wstring &&)
0x180130d81  jmp     short loc_180130D8D
0x180130d83  lea     r8, [rbp+12A0h+var_1318]
0x180130d87  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x180130d8c  nop
0x180130d8d  lea     rcx, [rbp+12A0h+var_1318]
0x180130d91  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180130d96  lea     rdx, [rsp+13A0h+var_1340]
0x180130d9b  lea     rcx, [rbp+12A0h+var_12D0]
0x180130d9f  call    ?AddTableRow@TableWithColumnHeaders@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAAJAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::AddTableRow(std::vector<std::wstring> &)
0x180130da4  mov     edi, eax
0x180130da6  test    eax, eax
0x180130da8  js      short loc_180130DCD
0x180130daa  lea     rdi, aXml; "XML"
0x180130db1  lea     rcx, [rsp+13A0h+var_1340]
0x180130db6  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180130dbb  nop
0x180130dbc  lea     rcx, [rsp+13A0h+hkey]
0x180130dc1  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180130dc6  inc     esi
0x180130dc8  jmp     loc_180130BBC
0x180130dcd  mov     rcx, [rbp+12A8h]; this
0x180130dd4  mov     r9d, edi; char *
0x180130dd7  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180130dde  mov     edx, 98Ah; void *
0x180130de3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180130de8  nop
0x180130de9  lea     rcx, [rsp+13A0h+var_1340]
0x180130dee  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180130df3  nop
0x180130df4  lea     rcx, [rsp+13A0h+hkey]
0x180130df9  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180130dfe  nop
0x180130dff  lea     rcx, [rsp+13A0h+hKey]
0x180130e04  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180130e09  mov     ebx, edi
0x180130e0b  jmp     loc_18013112D
0x180130e10  mov     rcx, [rbp+12A8h]; this
0x180130e17  mov     r9d, ebx; char *
0x180130e1a  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180130e21  mov     edx, 982h; void *
0x180130e26  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180130e2b  nop
0x180130e2c  lea     rcx, [rsp+13A0h+var_1340]
0x180130e31  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180130e36  nop
0x180130e37  lea     rcx, [rsp+13A0h+hkey]
0x180130e3c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180130e41  nop
0x180130e42  lea     rcx, [rsp+13A0h+hKey]
0x180130e47  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180130e4c  jmp     loc_18013112D
0x180130e51  mov     rbx, [rsp+13A0h+hKey]
0x180130e56  test    rbx, rbx
0x180130e59  jz      short loc_180130E7E
0x180130e5b  lea     rcx, [rsp+13A0h+var_1358]; this
0x180130e60  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180130e65  mov     rcx, rbx; hKey
0x180130e68  call    cs:__imp_RegCloseKey
0x180130e6f  nop     dword ptr [rax+rax+00h]
0x180130e74  lea     rcx, [rsp+13A0h+var_1358]; this
0x180130e79  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180130e7e  mov     [rsp+13A0h+hKey], r14
0x180130e83  lea     rax, [rsp+13A0h+hKey]
0x180130e88  mov     [rsp+13A0h+phkResult], rax; phkResult
0x180130e8d  mov     r9d, 20019h; samDesired
0x180130e93  xor     r8d, r8d; ulOptions
0x180130e96  lea     rdx, aSoftwareMicros_13; "Software\\Microsoft\\GPCSEWrapper"
0x180130e9d  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180130ea4  call    cs:__imp_RegOpenKeyExW
0x180130eab  nop     dword ptr [rax+rax+00h]
0x180130eb0  mov     ebx, eax
0x180130eb2  cmp     eax, 2
0x180130eb5  jz      loc_180131120
0x180130ebb  mov     esi, r14d
0x180130ebe  test    ebx, ebx
0x180130ec0  jnz     loc_180131120
0x180130ec6  mov     [rsp+13A0h+var_1358], r14
0x180130ecb  lea     rcx, [rbp+12A0h+var_1318]
0x180130ecf  call    ??0?$vector@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>(void)
0x180130ed4  nop
0x180130ed5  mov     [rsp+13A0h+cchName], 105h
0x180130edd  mov     [rsp+13A0h+lpftLastWriteTime], r14; lpftLastWriteTime
0x180130ee2  mov     [rsp+13A0h+lpcchClass], r14; lpcchClass
0x180130ee7  mov     [rsp+13A0h+lpClass], r14; lpClass
0x180130eec  mov     [rsp+13A0h+phkResult], r14; lpReserved
0x180130ef1  lea     r9, [rsp+13A0h+cchName]; lpcchName
0x180130ef6  lea     r8, [rbp+12A0h+Name]; lpName
0x180130efa  mov     edx, esi; dwIndex
0x180130efc  mov     rcx, [rsp+13A0h+hKey]; hKey
0x180130f01  call    cs:__imp_RegEnumKeyExW
0x180130f08  nop     dword ptr [rax+rax+00h]
0x180130f0d  mov     ebx, eax
0x180130f0f  test    eax, eax
0x180130f11  jnz     loc_1801310A5
0x180130f17  mov     rbx, [rsp+13A0h+var_1358]
0x180130f1c  test    rbx, rbx
0x180130f1f  jz      short loc_180130F42
0x180130f21  lea     rcx, [rbp+12A0h+var_1320]; this
0x180130f25  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180130f2a  mov     rcx, rbx; hKey
0x180130f2d  call    cs:__imp_RegCloseKey
0x180130f34  nop     dword ptr [rax+rax+00h]
0x180130f39  lea     rcx, [rbp+12A0h+var_1320]; this
0x180130f3d  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180130f42  mov     [rsp+13A0h+var_1358], r14
0x180130f47  lea     rax, [rsp+13A0h+var_1358]
0x180130f4c  mov     [rsp+13A0h+phkResult], rax; int
0x180130f51  mov     r9d, 20019h; samDesired
0x180130f57  xor     r8d, r8d; ulOptions
0x180130f5a  lea     rdx, [rbp+12A0h+Name]; lpSubKey
0x180130f5e  mov     rcx, [rsp+13A0h+hKey]; hKey
0x180130f63  call    cs:__imp_RegOpenKeyExW
  ... truncated ...
```
