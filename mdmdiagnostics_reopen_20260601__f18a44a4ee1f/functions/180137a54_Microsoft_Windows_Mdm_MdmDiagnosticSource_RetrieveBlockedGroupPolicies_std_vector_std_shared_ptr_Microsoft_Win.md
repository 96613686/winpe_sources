# Microsoft::Windows::Mdm::MdmDiagnosticSource::RetrieveBlockedGroupPolicies(std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>,std::allocator<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>> &)

- ea: `0x180137a54`
- end: `0x180137e9a`
- name: `?RetrieveBlockedGroupPolicies@MdmDiagnosticSource@Mdm@Windows@Microsoft@@YAJAEAV?$vector@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@2@@std@@@Z`
- size: `1094`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18012c258`

## callees

- `0x180019080`
- `0x1800e4408`
- `0x1800e688c`
- `0x1800e7de8`
- `0x1800ed46c`
- `0x1800ef8c4`
- `0x1800efd9c`
- `0x180105294`
- `0x180105480`
- `0x180136228`
- `0x1801373d8`
- `0x180137a54`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x180137a8a`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180137a8a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180137ac3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180137b74`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180137be9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180137c6b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180137ac3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180137b74`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180137be9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180137c6b`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall Microsoft::Windows::Mdm::MdmDiagnosticSource::RetrieveBlockedGroupPolicies(__int64 a1)
{
  __int64 v1; // r14
  char IsStateSeparationEnabled; // al
  const WCHAR *v3; // rdx
  unsigned int v4; // eax
  unsigned int v5; // ebx
  int SubKeyNames; // eax
  __int64 v7; // rdi
  __int64 v8; // r13
  const WCHAR *v9; // rax
  unsigned int v10; // eax
  int v11; // eax
  __int64 v12; // rsi
  __int64 v13; // r12
  const WCHAR *v14; // rax
  unsigned int v15; // eax
  int v16; // eax
  __int64 v17; // rbx
  __int64 v18; // r15
  const WCHAR *v19; // rax
  unsigned int v20; // eax
  int BlockedGroupPolicyData; // eax
  unsigned int v22; // r14d
  int v23; // eax
  unsigned int phkResult; // [rsp+20h] [rbp-99h]
  unsigned int phkResulta; // [rsp+20h] [rbp-99h]
  unsigned int phkResultb; // [rsp+20h] [rbp-99h]
  unsigned int phkResultc; // [rsp+20h] [rbp-99h]
  int phkResultd; // [rsp+20h] [rbp-99h]
  int phkResulte; // [rsp+20h] [rbp-99h]
  HKEY v31; // [rsp+30h] [rbp-89h] BYREF
  HKEY v32; // [rsp+38h] [rbp-81h] BYREF
  HKEY v33; // [rsp+40h] [rbp-79h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-71h] BYREF
  _QWORD v35[3]; // [rsp+50h] [rbp-69h] BYREF
  _QWORD v36[3]; // [rsp+68h] [rbp-51h] BYREF
  __int64 v37; // [rsp+80h] [rbp-39h] BYREF
  __int64 v38; // [rsp+88h] [rbp-31h]
  __int64 v39; // [rsp+98h] [rbp-21h]
  _BYTE v40[32]; // [rsp+A0h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v1 = a1;
  v39 = a1;
  hKey = 0;
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled();
  v3 = L"OSData\\SOFTWARE\\Microsoft\\MdmWins";
  if ( !IsStateSeparationEnabled )
    v3 = L"SOFTWARE\\Microsoft\\MdmWins";
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v3, 0, 0x20019u, &hKey);
  if ( v4 )
  {
    v5 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x28C,
           (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\policies.cpp",
           (const char *)v4,
           phkResult);
  }
  else
  {
    std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>(v35);
    SubKeyNames = anonymous_namespace_::GetSubKeyNames(&hKey, 0, v35);
    v5 = SubKeyNames;
    if ( SubKeyNames >= 0 )
    {
      v7 = v35[0];
      v8 = v35[1];
LABEL_9:
      if ( v7 == v8 )
      {
        std::vector<std::wstring>::_Tidy(v35);
        v5 = 0;
        goto LABEL_37;
      }
      v31 = 0;
      v9 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v7);
      v10 = RegOpenKeyExW(hKey, v9, 0, 0x20019u, &v31);
      if ( v10 )
      {
        v5 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x297,
               (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\policies.cpp",
               (const char *)v10,
               phkResulta);
      }
      else
      {
        std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>(v36);
        v11 = anonymous_namespace_::GetSubKeyNames(&v31, 0, v36);
        v5 = v11;
        if ( v11 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x29A,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\policies.cpp",
            (const char *)(unsigned int)v11,
            phkResulta);
        }
        else
        {
          v12 = v36[0];
          v13 = v36[1];
          while ( 1 )
          {
            if ( v12 == v13 )
            {
              std::vector<std::wstring>::_Tidy(v36);
              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v31);
              v7 += 32;
              goto LABEL_9;
            }
            v32 = 0;
            v14 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v12);
            v15 = RegOpenKeyExW(v31, v14, 0, 0x20019u, &v32);
            if ( v15 )
              break;
            std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>(&v37);
            v16 = anonymous_namespace_::GetSubKeyNames(&v32, 0, &v37);
            v5 = v16;
            if ( v16 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x2A4,
                (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\policies.cpp",
                (const char *)(unsigned int)v16,
                phkResultb);
              goto LABEL_29;
            }
            v17 = v37;
            v18 = v38;
            if ( (v38 - v37) >> 5 )
            {
              while ( v17 != v18 )
              {
                v33 = 0;
                v19 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v17);
                v20 = RegOpenKeyExW(v32, v19, 0, 0x20019u, &v33);
                if ( v20 )
                {
                  v5 = wil::details::in1diag3::Return_Win32(
                         retaddr,
                         (void *)0x2AD,
                         (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\policies.cpp",
                         (const char *)v20,
                         phkResultc);
                  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v33);
                  goto LABEL_29;
                }
                BlockedGroupPolicyData = anonymous_namespace_::GetBlockedGroupPolicyData(
                                           (unsigned int)&v33,
                                           v7,
                                           v12,
                                           v17,
                                           v1);
                v22 = BlockedGroupPolicyData;
                if ( BlockedGroupPolicyData < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x2AF,
                    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\policies.cpp",
                    (const char *)(unsigned int)BlockedGroupPolicyData,
                    phkResultd);
                  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v33);
                  std::vector<std::wstring>::_Tidy(&v37);
                  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v32);
                  std::vector<std::wstring>::_Tidy(v36);
                  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v31);
                  std::vector<std::wstring>::_Tidy(v35);
                  v5 = v22;
                  goto LABEL_37;
                }
                wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v33);
                v17 += 32;
                v1 = v39;
              }
            }
            else
            {
              std::wstring::wstring(v40);
              v23 = anonymous_namespace_::GetBlockedGroupPolicyData((unsigned int)&v32, v7, v12, (unsigned int)v40, v1);
              v5 = v23;
              if ( v23 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x2B5,
                  (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\policies.cpp",
                  (const char *)(unsigned int)v23,
                  phkResulte);
                std::wstring::_Tidy_deallocate(v40);
LABEL_29:
                std::vector<std::wstring>::_Tidy(&v37);
                goto LABEL_31;
              }
              std::wstring::_Tidy_deallocate(v40);
            }
            std::vector<std::wstring>::_Tidy(&v37);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v32);
            v12 += 32;
          }
          v5 = wil::details::in1diag3::Return_Win32(
                 retaddr,
                 (void *)0x2A1,
                 (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\policies.cpp",
                 (const char *)v15,
                 phkResultb);
LABEL_31:
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v32);
        }
        std::vector<std::wstring>::_Tidy(v36);
      }
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v31);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x290,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\policies.cpp",
        (const char *)(unsigned int)SubKeyNames,
        phkResult);
    }
    std::vector<std::wstring>::_Tidy(v35);
  }
LABEL_37:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return v5;
}

```

## disassembly

```asm
0x180137a54  push    rbp
0x180137a56  push    rbx
0x180137a57  push    rsi
0x180137a58  push    rdi
0x180137a59  push    r12
0x180137a5b  push    r13
0x180137a5d  push    r14
0x180137a5f  push    r15
0x180137a61  lea     rbp, [rsp-1Fh]
0x180137a66  sub     rsp, 0D8h
0x180137a6d  mov     rax, cs:__security_cookie
0x180137a74  xor     rax, rsp
0x180137a77  mov     [rbp+57h+var_50], rax
0x180137a7b  mov     r14, rcx
0x180137a7e  mov     [rbp+57h+var_78], rcx
0x180137a82  mov     [rbp+57h+hKey], 0
0x180137a8a  call    cs:__imp_RtlIsStateSeparationEnabled
0x180137a91  nop     dword ptr [rax+rax+00h]
0x180137a96  lea     rcx, aSoftwareMicros_8; "SOFTWARE\\Microsoft\\MdmWins"
0x180137a9d  lea     rdx, aOsdataSoftware_5; "OSData\\SOFTWARE\\Microsoft\\MdmWins"
0x180137aa4  test    al, al
0x180137aa6  cmovz   rdx, rcx; lpSubKey
0x180137aaa  lea     rax, [rbp+57h+hKey]
0x180137aae  mov     qword ptr [rsp+110h+phkResult], rax; int
0x180137ab3  mov     r9d, 20019h; samDesired
0x180137ab9  xor     r8d, r8d; ulOptions
0x180137abc  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180137ac3  call    cs:__imp_RegOpenKeyExW
0x180137aca  nop     dword ptr [rax+rax+00h]
0x180137acf  test    eax, eax
0x180137ad1  jz      short loc_180137AF2
0x180137ad3  mov     rcx, [rbp+5Fh]; this
0x180137ad7  mov     r9d, eax; char *
0x180137ada  lea     r8, aOnecoreuapAdmi_32; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180137ae1  mov     edx, 28Ch; void *
0x180137ae6  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180137aeb  mov     ebx, eax
0x180137aed  jmp     loc_180137E6E
0x180137af2  lea     rcx, [rbp+57h+var_C0]
0x180137af6  call    ??0?$vector@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>(void)
0x180137afb  nop
0x180137afc  lea     r8, [rbp+57h+var_C0]
0x180137b00  xor     edx, edx
0x180137b02  lea     rcx, [rbp+57h+hKey]
0x180137b06  call    _anonymous_namespace___GetSubKeyNames
0x180137b0b  mov     ebx, eax
0x180137b0d  test    eax, eax
0x180137b0f  jns     short loc_180137B38
0x180137b11  mov     rcx, [rbp+5Fh]; this
0x180137b15  mov     r9d, eax; char *
0x180137b18  lea     r8, aOnecoreuapAdmi_32; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180137b1f  mov     edx, 290h; void *
0x180137b24  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180137b29  nop
0x180137b2a  lea     rcx, [rbp+57h+var_C0]
0x180137b2e  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180137b33  jmp     loc_180137E6E
0x180137b38  mov     rdi, [rbp+57h+var_C0]
0x180137b3c  mov     r13, [rbp+57h+var_B8]
0x180137b40  cmp     rdi, r13
0x180137b43  jz      loc_180137E63
0x180137b49  mov     [rsp+110h+var_E0], 0
0x180137b52  mov     rcx, rdi
0x180137b55  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180137b5a  lea     rcx, [rsp+110h+var_E0]
0x180137b5f  mov     qword ptr [rsp+110h+phkResult], rcx; unsigned int
0x180137b64  mov     r9d, 20019h; samDesired
0x180137b6a  xor     r8d, r8d; ulOptions
0x180137b6d  mov     rdx, rax; lpSubKey
0x180137b70  mov     rcx, [rbp+57h+hKey]; hKey
0x180137b74  call    cs:__imp_RegOpenKeyExW
0x180137b7b  nop     dword ptr [rax+rax+00h]
0x180137b80  test    eax, eax
0x180137b82  jnz     loc_180137E3A
0x180137b88  lea     rcx, [rbp+57h+var_A8]
0x180137b8c  call    ??0?$vector@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>(void)
0x180137b91  nop
0x180137b92  lea     r8, [rbp+57h+var_A8]
0x180137b96  xor     edx, edx
0x180137b98  lea     rcx, [rsp+110h+var_E0]
0x180137b9d  call    _anonymous_namespace___GetSubKeyNames
0x180137ba2  mov     ebx, eax
0x180137ba4  test    eax, eax
0x180137ba6  js      loc_180137E16
0x180137bac  mov     rsi, [rbp+57h+var_A8]
0x180137bb0  mov     r12, [rbp+57h+var_A0]
0x180137bb4  cmp     rsi, r12
0x180137bb7  jz      loc_180137D08
0x180137bbd  mov     [rsp+110h+var_D8], 0
0x180137bc6  mov     rcx, rsi
0x180137bc9  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180137bce  lea     rcx, [rsp+110h+var_D8]
0x180137bd3  mov     qword ptr [rsp+110h+phkResult], rcx; unsigned int
0x180137bd8  mov     r9d, 20019h; samDesired
0x180137bde  xor     r8d, r8d; ulOptions
0x180137be1  mov     rdx, rax; lpSubKey
0x180137be4  mov     rcx, [rsp+110h+var_E0]; hKey
0x180137be9  call    cs:__imp_RegOpenKeyExW
0x180137bf0  nop     dword ptr [rax+rax+00h]
0x180137bf5  test    eax, eax
0x180137bf7  jnz     loc_180137DF0
0x180137bfd  lea     rcx, [rbp+57h+var_90]
0x180137c01  call    ??0?$vector@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>(void)
0x180137c06  nop
0x180137c07  lea     r8, [rbp+57h+var_90]
0x180137c0b  xor     edx, edx
0x180137c0d  lea     rcx, [rsp+110h+var_D8]
0x180137c12  call    _anonymous_namespace___GetSubKeyNames
0x180137c17  mov     ebx, eax
0x180137c19  test    eax, eax
0x180137c1b  js      loc_180137DCC
0x180137c21  mov     rbx, [rbp+57h+var_90]
0x180137c25  mov     r15, [rbp+57h+var_88]
0x180137c29  mov     rax, r15
0x180137c2c  sub     rax, rbx
0x180137c2f  sar     rax, 5
0x180137c33  test    rax, rax
0x180137c36  jz      short loc_180137CB4
0x180137c38  cmp     rbx, r15
0x180137c3b  jz      loc_180137CEB
0x180137c41  mov     [rbp+57h+var_D0], 0
0x180137c49  mov     rcx, rbx
0x180137c4c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180137c51  lea     rcx, [rbp+57h+var_D0]
0x180137c55  mov     qword ptr [rsp+110h+phkResult], rcx; unsigned int
0x180137c5a  mov     r9d, 20019h; samDesired
0x180137c60  xor     r8d, r8d; ulOptions
0x180137c63  mov     rdx, rax; lpSubKey
0x180137c66  mov     rcx, [rsp+110h+var_D8]; hKey
0x180137c6b  call    cs:__imp_RegOpenKeyExW
0x180137c72  nop     dword ptr [rax+rax+00h]
0x180137c77  test    eax, eax
0x180137c79  jnz     loc_180137D83
0x180137c7f  mov     qword ptr [rsp+110h+phkResult], r14; int
0x180137c84  mov     r9, rbx
0x180137c87  mov     r8, rsi
0x180137c8a  mov     rdx, rdi
0x180137c8d  lea     rcx, [rbp+57h+var_D0]
0x180137c91  call    _anonymous_namespace___GetBlockedGroupPolicyData
0x180137c96  mov     r14d, eax
0x180137c99  test    eax, eax
0x180137c9b  js      loc_180137D25
0x180137ca1  lea     rcx, [rbp+57h+var_D0]
0x180137ca5  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180137caa  add     rbx, 20h ; ' '
0x180137cae  mov     r14, [rbp+57h+var_78]
0x180137cb2  jmp     short loc_180137C38
0x180137cb4  lea     rcx, [rbp+57h+var_70]
0x180137cb8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180137cbd  nop
0x180137cbe  mov     qword ptr [rsp+110h+phkResult], r14; int
0x180137cc3  lea     r9, [rbp+57h+var_70]
0x180137cc7  mov     r8, rsi
0x180137cca  mov     rdx, rdi
0x180137ccd  lea     rcx, [rsp+110h+var_D8]
0x180137cd2  call    _anonymous_namespace___GetBlockedGroupPolicyData
0x180137cd7  mov     ebx, eax
0x180137cd9  test    eax, eax
0x180137cdb  js      loc_180137DA8
0x180137ce1  lea     rcx, [rbp+57h+var_70]
0x180137ce5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180137cea  nop
0x180137ceb  lea     rcx, [rbp+57h+var_90]
0x180137cef  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180137cf4  nop
0x180137cf5  lea     rcx, [rsp+110h+var_D8]
0x180137cfa  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180137cff  add     rsi, 20h ; ' '
0x180137d03  jmp     loc_180137BB4
0x180137d08  lea     rcx, [rbp+57h+var_A8]
0x180137d0c  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180137d11  nop
0x180137d12  lea     rcx, [rsp+110h+var_E0]
0x180137d17  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180137d1c  add     rdi, 20h ; ' '
0x180137d20  jmp     loc_180137B40
0x180137d25  mov     rcx, [rbp+5Fh]; this
0x180137d29  mov     r9d, r14d; char *
0x180137d2c  lea     r8, aOnecoreuapAdmi_32; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180137d33  mov     edx, 2AFh; void *
0x180137d38  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180137d3d  nop
0x180137d3e  lea     rcx, [rbp+57h+var_D0]
0x180137d42  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180137d47  nop
0x180137d48  lea     rcx, [rbp+57h+var_90]
0x180137d4c  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180137d51  nop
0x180137d52  lea     rcx, [rsp+110h+var_D8]
0x180137d57  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180137d5c  nop
0x180137d5d  lea     rcx, [rbp+57h+var_A8]
0x180137d61  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180137d66  nop
0x180137d67  lea     rcx, [rsp+110h+var_E0]
0x180137d6c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180137d71  nop
0x180137d72  lea     rcx, [rbp+57h+var_C0]
0x180137d76  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180137d7b  mov     ebx, r14d
0x180137d7e  jmp     loc_180137E6E
0x180137d83  mov     rcx, [rbp+5Fh]; this
0x180137d87  mov     r9d, eax; char *
0x180137d8a  lea     r8, aOnecoreuapAdmi_32; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180137d91  mov     edx, 2ADh; void *
0x180137d96  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180137d9b  mov     ebx, eax
0x180137d9d  lea     rcx, [rbp+57h+var_D0]
0x180137da1  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180137da6  jmp     short loc_180137DE5
0x180137da8  mov     rcx, [rbp+5Fh]; this
0x180137dac  mov     r9d, eax; char *
0x180137daf  lea     r8, aOnecoreuapAdmi_32; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180137db6  mov     edx, 2B5h; void *
0x180137dbb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180137dc0  nop
0x180137dc1  lea     rcx, [rbp+57h+var_70]
0x180137dc5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180137dca  jmp     short loc_180137DE5
0x180137dcc  mov     rcx, [rbp+5Fh]; this
0x180137dd0  mov     r9d, eax; char *
0x180137dd3  lea     r8, aOnecoreuapAdmi_32; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180137dda  mov     edx, 2A4h; void *
0x180137ddf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180137de4  nop
0x180137de5  lea     rcx, [rbp+57h+var_90]
0x180137de9  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180137dee  jmp     short loc_180137E0A
0x180137df0  mov     rcx, [rbp+5Fh]; this
0x180137df4  mov     r9d, eax; char *
0x180137df7  lea     r8, aOnecoreuapAdmi_32; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180137dfe  mov     edx, 2A1h; void *
0x180137e03  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180137e08  mov     ebx, eax
0x180137e0a  lea     rcx, [rsp+110h+var_D8]
0x180137e0f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180137e14  jmp     short loc_180137E2F
0x180137e16  mov     rcx, [rbp+5Fh]; this
0x180137e1a  mov     r9d, eax; char *
0x180137e1d  lea     r8, aOnecoreuapAdmi_32; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180137e24  mov     edx, 29Ah; void *
0x180137e29  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180137e2e  nop
0x180137e2f  lea     rcx, [rbp+57h+var_A8]
0x180137e33  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180137e38  jmp     short loc_180137E54
0x180137e3a  mov     rcx, [rbp+5Fh]; this
0x180137e3e  mov     r9d, eax; char *
0x180137e41  lea     r8, aOnecoreuapAdmi_32; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180137e48  mov     edx, 297h; void *
0x180137e4d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180137e52  mov     ebx, eax
0x180137e54  lea     rcx, [rsp+110h+var_E0]
0x180137e59  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180137e5e  jmp     loc_180137B2A
0x180137e63  lea     rcx, [rbp+57h+var_C0]
0x180137e67  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180137e6c  xor     ebx, ebx
0x180137e6e  lea     rcx, [rbp+57h+hKey]
0x180137e72  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180137e77  mov     eax, ebx
0x180137e79  mov     rcx, [rbp+57h+var_50]
0x180137e7d  xor     rcx, rsp; StackCookie
0x180137e80  call    __security_check_cookie
0x180137e85  add     rsp, 0D8h
0x180137e8c  pop     r15
0x180137e8e  pop     r14
0x180137e90  pop     r13
0x180137e92  pop     r12
0x180137e94  pop     rdi
0x180137e95  pop     rsi
0x180137e96  pop     rbx
0x180137e97  pop     rbp
0x180137e98  retn
```
