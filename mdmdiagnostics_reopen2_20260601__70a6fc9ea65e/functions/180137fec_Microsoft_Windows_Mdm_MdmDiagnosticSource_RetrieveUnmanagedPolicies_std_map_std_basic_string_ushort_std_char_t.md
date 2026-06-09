# Microsoft::Windows::Mdm::MdmDiagnosticSource::RetrieveUnmanagedPolicies(std::map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>,std::allocator<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>,std::allocator<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>>>>>> &)

- ea: `0x180137fec`
- end: `0x1801384c0`
- name: `?RetrieveUnmanagedPolicies@MdmDiagnosticSource@Mdm@Windows@Microsoft@@YAJAEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@2@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@2@@2@@std@@@2@@std@@@Z`
- size: `1236`
- prototype: ``
- caller_count: `1`
- callee_count: `29`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1801337bc`

## callees

- `0x180019080`
- `0x1800190a4`
- `0x1800e4408`
- `0x1800e5744`
- `0x1800e688c`
- `0x1800e6b14`
- `0x1800e7de8`
- `0x1800ed46c`
- `0x1800eef28`
- `0x1800ef8c4`
- `0x1800efd9c`
- `0x1800faa0c`
- `0x180105294`
- `0x180105480`
- `0x180109344`
- `0x180113174`
- `0x1801131f8`
- `0x1801165f0`
- `0x180127344`
- `0x180135004`
- `0x180135178`
- `0x1801354dc`
- `0x180135660`
- `0x18013576c`
- `0x180136d14`
- `0x1801373d8`
- `0x180137588`
- `0x180137fec`
- `0x1801385c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180138042`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180138108`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180138042`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180138108`
- `policymanager!EnterprisePolicyManagerStore_IsAreaPolicySLAPIAllowed` at `0x180138215`
- `policymanager!EnterprisePolicyManagerStore_IsAreaPolicySLAPIAllowed` at `0x180138215`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall Microsoft::Windows::Mdm::MdmDiagnosticSource::RetrieveUnmanagedPolicies(_QWORD *a1)
{
  int v2; // esi
  unsigned int v3; // eax
  unsigned int v4; // ebx
  int SubKeyNames; // eax
  __int64 v6; // r14
  __int64 v7; // rax
  const WCHAR *v8; // rax
  unsigned int v9; // eax
  int v10; // eax
  __int64 v11; // r15
  __int64 v12; // r13
  unsigned int DefaultPolicyValue; // eax
  _DWORD *v14; // rbx
  Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy *v15; // rdi
  __int64 v16; // rbx
  __int64 v17; // rax
  unsigned __int64 UniquePolicyId; // rbx
  struct Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals *v19; // rax
  char *v20; // rbx
  _QWORD *v21; // rax
  char v22; // bl
  __int64 v23; // rbx
  __int64 v24; // rcx
  __int64 v25; // rax
  __int64 v26; // rcx
  __int64 v27; // r9
  __int64 *v28; // rcx
  unsigned int phkResult; // [rsp+20h] [rbp-E0h]
  unsigned int phkResulta; // [rsp+20h] [rbp-E0h]
  int v32; // [rsp+30h] [rbp-D0h] BYREF
  HKEY v33; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v35; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v36; // [rsp+50h] [rbp-B0h]
  __int64 v37; // [rsp+58h] [rbp-A8h]
  _DWORD *v38; // [rsp+60h] [rbp-A0h] BYREF
  std::_Ref_count_base *v39; // [rsp+68h] [rbp-98h]
  unsigned __int64 v40; // [rsp+70h] [rbp-90h] BYREF
  __int64 v41; // [rsp+78h] [rbp-88h] BYREF
  __int64 v42; // [rsp+80h] [rbp-80h]
  _QWORD v43[3]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v44; // [rsp+A8h] [rbp-58h]
  std::_Ref_count_base *v45[2]; // [rsp+B0h] [rbp-50h] BYREF
  _DWORD *v46; // [rsp+C0h] [rbp-40h]
  _BYTE v47[8]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v48[16]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v49; // [rsp+E0h] [rbp-20h]
  _BYTE v50[16]; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE v51[16]; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE v52[16]; // [rsp+108h] [rbp+8h] BYREF
  _BYTE v53[32]; // [rsp+118h] [rbp+18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]

  v2 = 0;
  v32 = 0;
  hKey = 0;
  v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\PolicyManager\\default", 0, 0x20019u, &hKey);
  if ( v3 )
  {
    v4 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x252,
           (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\policies.cpp",
           (const char *)v3,
           phkResult);
  }
  else
  {
    std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>(&v41);
    SubKeyNames = anonymous_namespace_::GetSubKeyNames(&hKey, 0, &v41);
    v4 = SubKeyNames;
    if ( SubKeyNames >= 0 )
    {
      v6 = v41;
      v7 = v42;
      v44 = v42;
LABEL_7:
      if ( v6 == v7 )
      {
        std::vector<std::wstring>::_Tidy(&v41);
        v4 = 0;
        goto LABEL_47;
      }
      v33 = 0;
      v8 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v6);
      v9 = RegOpenKeyExW(hKey, v8, 0, 0x20019u, &v33);
      if ( v9 )
      {
        v4 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x25B,
               (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\policies.cpp",
               (const char *)v9,
               phkResulta);
      }
      else
      {
        std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>(v43);
        v10 = anonymous_namespace_::GetSubKeyNames(&v33, 0, v43);
        v4 = v10;
        if ( v10 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x25F,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\policies.cpp",
            (const char *)(unsigned int)v10,
            phkResulta);
        }
        else
        {
          v11 = v43[0];
          v12 = v43[1];
          while ( 1 )
          {
            if ( v11 == v12 )
            {
              std::vector<std::wstring>::_Tidy(v43);
              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v33);
              v6 += 32;
              v7 = v44;
              goto LABEL_7;
            }
            std::wstring::wstring(v53);
            DefaultPolicyValue = anonymous_namespace_::GetDefaultPolicyValue(v6, v11, v53);
            v4 = DefaultPolicyValue;
            if ( ((DefaultPolicyValue + 0x80000000) & 0x80000000) == 0 && DefaultPolicyValue != -2147024894 )
              break;
            v14 = operator new(0xD0u);
            v46 = v14;
            *(_OWORD *)v14 = 0;
            v14[2] = 1;
            v14[3] = 1;
            *(_QWORD *)v14 = &std::_Ref_count_obj2<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>::`vftable';
            v15 = (Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy *)(v14 + 4);
            std::_Construct_in_place<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy,std::wstring &,std::wstring &,unsigned short const (&)[1]>(
              v14 + 4,
              v6,
              v11,
              &Name);
            v2 |= 2u;
            v38 = v14 + 4;
            v39 = (std::_Ref_count_base *)v14;
            std::wstring::operator=(v14 + 36, v53);
            v32 = 0;
            v16 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v11);
            v17 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v6);
            phkResulta = 0;
            EnterprisePolicyManagerStore_IsAreaPolicySLAPIAllowed(0, v17, v16, &v32);
            UniquePolicyId = Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy::GetUniquePolicyId(v15, 0);
            if ( !v32 )
              goto LABEL_20;
            v19 = Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance();
            v40 = UniquePolicyId;
            v20 = (char *)v19 + 64;
            if ( *(_QWORD *)std::_Tree<std::_Tmap_traits<unsigned __int64,std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>>>,0>>::find(
                              (char *)v19 + 64,
                              v47,
                              &v40) == *((_QWORD *)v19 + 8) )
            {
              *(_OWORD *)v45 = 0;
            }
            else
            {
              v21 = (_QWORD *)std::map<unsigned __int64,std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>>::_Try_emplace<unsigned __int64 const &,>(
                                v20,
                                v50,
                                &v40);
              std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>(
                v45,
                *v21 + 40LL);
            }
            v2 |= 5u;
            if ( v45[0] )
LABEL_20:
              v22 = 0;
            else
              v22 = 1;
            if ( (v2 & 1) != 0 )
            {
              v2 &= ~1u;
              if ( v45[1] )
                std::_Ref_count_base::_Decref(v45[1]);
            }
            if ( v22 )
            {
              std::_Tree<std::_Tmap_traits<std::wstring,std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>>>>,0>>::_Find_lower_bound<std::wstring>(
                a1,
                v48,
                v6);
              v23 = v49;
              if ( !(unsigned __int8)std::_Tree<std::_Tmap_traits<std::wstring,std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>>>>,0>>::_Lower_bound_duplicate<std::wstring>(
                                       v24,
                                       v49,
                                       v6)
                || v23 == *a1 )
              {
                std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>(&v35);
                if ( v36 == v37 )
                {
                  std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>>::_Emplace_reallocate<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy> const &>(
                    &v35,
                    v36,
                    &v38);
                }
                else
                {
                  std::_Construct_in_place<std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>,std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey> const &>(
                    v36,
                    &v38);
                  v36 += 16;
                }
                v28 = (__int64 *)(*(_QWORD *)std::map<std::wstring,std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>>>::_Try_emplace<std::wstring const &,>(
                                               a1,
                                               v52,
                                               v6)
                                + 64LL);
                if ( v28 != &v35 )
                  std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>>::_Assign_counted_range<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy> *>(
                    v28,
                    v35,
                    (v36 - v35) >> 4);
                if ( v35 )
                {
                  std::_Destroy_range<std::allocator<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>>>(
                    v35,
                    v36);
                  std::_Deallocate<16>(v35, (v37 - v35) & 0xFFFFFFFFFFFFFFF0uLL);
                }
              }
              else
              {
                v25 = std::map<std::wstring,std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>>>::_Try_emplace<std::wstring const &,>(
                        a1,
                        v51,
                        v6);
                v26 = *(_QWORD *)(*(_QWORD *)v25 + 72LL);
                if ( v26 == *(_QWORD *)(*(_QWORD *)v25 + 80LL) )
                {
                  std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>>::_Emplace_reallocate<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy> const &>(
                    *(_QWORD *)v25 + 64LL,
                    *(_QWORD *)(*(_QWORD *)v25 + 72LL),
                    &v38);
                }
                else
                {
                  std::_Construct_in_place<std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>,std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey> const &>(
                    v26,
                    &v38);
                  *(_QWORD *)(v27 + 72) += 16LL;
                }
              }
            }
            if ( v39 )
              std::_Ref_count_base::_Decref(v39);
            std::wstring::_Tidy_deallocate(v53);
            v11 += 32;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x267,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\policies.cpp",
            (const char *)DefaultPolicyValue,
            phkResulta);
          std::wstring::_Tidy_deallocate(v53);
        }
        std::vector<std::wstring>::_Tidy(v43);
      }
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v33);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x256,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\policies.cpp",
        (const char *)(unsigned int)SubKeyNames,
        phkResult);
    }
    std::vector<std::wstring>::_Tidy(&v41);
  }
LABEL_47:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return v4;
}

```

## disassembly

```asm
0x180137fec  push    rbp
0x180137fee  push    rbx
0x180137fef  push    rsi
0x180137ff0  push    rdi
0x180137ff1  push    r12
0x180137ff3  push    r13
0x180137ff5  push    r14
0x180137ff7  push    r15
0x180137ff9  lea     rbp, [rsp-48h]
0x180137ffe  sub     rsp, 148h
0x180138005  mov     rax, cs:__security_cookie
0x18013800c  xor     rax, rsp
0x18013800f  mov     [rbp+80h+var_48], rax
0x180138013  mov     r12, rcx
0x180138016  xor     esi, esi
0x180138018  mov     [rsp+180h+var_150], esi
0x18013801c  mov     [rsp+180h+hKey], rsi
0x180138021  lea     rax, [rsp+180h+hKey]
0x180138026  mov     qword ptr [rsp+180h+phkResult], rax; int
0x18013802b  mov     r9d, 20019h; samDesired
0x180138031  xor     r8d, r8d; ulOptions
0x180138034  lea     rdx, aSoftwareMicros_5; "SOFTWARE\\Microsoft\\PolicyManager\\def"...
0x18013803b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180138042  call    cs:__imp_RegOpenKeyExW
0x180138049  nop     dword ptr [rax+rax+00h]
0x18013804e  test    eax, eax
0x180138050  jz      short loc_180138074
0x180138052  mov     rcx, [rbp+88h]; this
0x180138059  mov     r9d, eax; char *
0x18013805c  lea     r8, aOnecoreuapAdmi_32; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180138063  mov     edx, 252h; void *
0x180138068  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18013806d  mov     ebx, eax
0x18013806f  jmp     loc_180138493
0x180138074  lea     rcx, [rsp+180h+var_108]
0x180138079  call    ??0?$vector@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>(void)
0x18013807e  nop
0x18013807f  lea     r8, [rsp+180h+var_108]
0x180138084  xor     edx, edx
0x180138086  lea     rcx, [rsp+180h+hKey]
0x18013808b  call    _anonymous_namespace___GetSubKeyNames
0x180138090  mov     ebx, eax
0x180138092  test    eax, eax
0x180138094  jns     short loc_1801380C1
0x180138096  mov     rcx, [rbp+88h]; this
0x18013809d  mov     r9d, eax; char *
0x1801380a0  lea     r8, aOnecoreuapAdmi_32; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1801380a7  mov     edx, 256h; void *
0x1801380ac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801380b1  nop
0x1801380b2  lea     rcx, [rsp+180h+var_108]
0x1801380b7  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1801380bc  jmp     loc_180138493
0x1801380c1  mov     r14, [rsp+180h+var_108]
0x1801380c6  mov     rax, [rbp+80h+var_100]
0x1801380ca  mov     [rbp+80h+var_D8], rax
0x1801380ce  mov     edi, 80000000h
0x1801380d3  cmp     r14, rax
0x1801380d6  jz      loc_180138487
0x1801380dc  mov     [rsp+180h+var_148], 0
0x1801380e5  mov     rcx, r14
0x1801380e8  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1801380ed  lea     rcx, [rsp+180h+var_148]
0x1801380f2  mov     qword ptr [rsp+180h+phkResult], rcx; unsigned int
0x1801380f7  mov     r9d, 20019h; samDesired
0x1801380fd  xor     r8d, r8d; ulOptions
0x180138100  mov     rdx, rax; lpSubKey
0x180138103  mov     rcx, [rsp+180h+hKey]; hKey
0x180138108  call    cs:__imp_RegOpenKeyExW
0x18013810f  nop     dword ptr [rax+rax+00h]
0x180138114  test    eax, eax
0x180138116  jnz     loc_18013845B
0x18013811c  lea     rcx, [rbp+80h+var_F0]
0x180138120  call    ??0?$vector@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>(void)
0x180138125  nop
0x180138126  lea     r8, [rbp+80h+var_F0]
0x18013812a  xor     edx, edx
0x18013812c  lea     rcx, [rsp+180h+var_148]
0x180138131  call    _anonymous_namespace___GetSubKeyNames
0x180138136  mov     ebx, eax
0x180138138  test    eax, eax
0x18013813a  js      loc_180138434
0x180138140  mov     r15, [rbp+80h+var_F0]
0x180138144  mov     r13, [rbp+80h+var_E8]
0x180138148  cmp     r15, r13
0x18013814b  jz      loc_1801383EC
0x180138151  lea     rcx, [rbp+80h+var_68]
0x180138155  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18013815a  nop
0x18013815b  lea     r8, [rbp+80h+var_68]
0x18013815f  mov     rdx, r15
0x180138162  mov     rcx, r14
0x180138165  call    _anonymous_namespace___GetDefaultPolicyValue
0x18013816a  mov     ebx, eax
0x18013816c  lea     ecx, [rax+rdi]
0x18013816f  test    edi, ecx
0x180138171  jnz     short loc_18013817E
0x180138173  cmp     eax, 80070002h
0x180138178  jnz     loc_18013840D
0x18013817e  mov     ecx, 0D0h; Size
0x180138183  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180138188  mov     rbx, rax
0x18013818b  mov     [rbp+80h+var_C0], rax
0x18013818f  xorps   xmm0, xmm0
0x180138192  movups  xmmword ptr [rax], xmm0
0x180138195  mov     dword ptr [rax+8], 1
0x18013819c  mov     dword ptr [rax+0Ch], 1
0x1801381a3  lea     rax, ??_7?$_Ref_count_obj2@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@6B@; const std::_Ref_count_obj2<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>::`vftable'
0x1801381aa  mov     [rbx], rax
0x1801381ad  lea     rdi, [rbx+10h]
0x1801381b1  lea     r9, Name
0x1801381b8  mov     r8, r15
0x1801381bb  mov     rdx, r14
0x1801381be  mov     rcx, rdi
0x1801381c1  call    ??$_Construct_in_place@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV67@AEAY00$$CBG@std@@YAXAEAVPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@1AEAY00$$CBG@Z; std::_Construct_in_place<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy,std::wstring &,std::wstring &,ushort const (&)[1]>(Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy &,std::wstring &,std::wstring &,ushort const (&)[1])
0x1801381c6  nop
0x1801381c7  or      esi, 2
0x1801381ca  mov     [rsp+180h+var_120], rdi
0x1801381cf  mov     [rsp+180h+var_118], rbx
0x1801381d4  lea     rcx, [rdi+80h]
0x1801381db  lea     rdx, [rbp+80h+var_68]
0x1801381df  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1801381e4  mov     [rsp+180h+var_150], 0
0x1801381ec  mov     rcx, r15
0x1801381ef  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1801381f4  mov     rbx, rax
0x1801381f7  mov     rcx, r14
0x1801381fa  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1801381ff  mov     qword ptr [rsp+180h+phkResult], 0
0x180138208  lea     r9, [rsp+180h+var_150]
0x18013820d  mov     r8, rbx
0x180138210  mov     rdx, rax
0x180138213  xor     ecx, ecx
0x180138215  call    cs:__imp_?EnterprisePolicyManagerStore_IsAreaPolicySLAPIAllowed@@YAJW4EnrollmentEnrollType@@PEBG1PEAHPEAPEAE@Z; EnterprisePolicyManagerStore_IsAreaPolicySLAPIAllowed(EnrollmentEnrollType,ushort const *,ushort const *,int *,uchar * *)
0x18013821c  nop     dword ptr [rax+rax+00h]
0x180138221  xor     edx, edx; bool
0x180138223  mov     rcx, rdi; this
0x180138226  call    ?GetUniquePolicyId@Policy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAA_K_N@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy::GetUniquePolicyId(bool)
0x18013822b  mov     rbx, rax
0x18013822e  cmp     [rsp+180h+var_150], 0
0x180138233  jz      short loc_180138299
0x180138235  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x18013823a  mov     [rsp+180h+var_110], rbx
0x18013823f  lea     rbx, [rax+40h]
0x180138243  lea     r8, [rsp+180h+var_110]
0x180138248  lea     rdx, [rbp+80h+var_B8]
0x18013824c  mov     rcx, rbx
0x18013824f  call    ?find@?$_Tree@V?$_Tmap_traits@_KV?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@std@@@std@@@std@@@2@AEB_K@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>>>,0>>::find(unsigned __int64 const &)
0x180138254  mov     rcx, [rbx]
0x180138257  cmp     [rax], rcx
0x18013825a  jnz     short loc_180138266
0x18013825c  xorps   xmm0, xmm0
0x18013825f  movdqu  xmmword ptr [rbp+80h+var_D0], xmm0
0x180138264  jmp     short loc_180138287
0x180138266  lea     r8, [rsp+180h+var_110]
0x18013826b  lea     rdx, [rbp+80h+var_98]
0x18013826f  mov     rcx, rbx
0x180138272  call    ??$_Try_emplace@AEB_K$$V@?$map@_KV?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CB_KV?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@std@@PEAX@std@@_N@1@AEB_K@Z; std::map<unsigned __int64,std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>>::_Try_emplace<unsigned __int64 const &,>(unsigned __int64 const &)
0x180138277  mov     rdx, [rax]
0x18013827a  add     rdx, 28h ; '('
0x18013827e  lea     rcx, [rbp+80h+var_D0]
0x180138282  call    ??0?$shared_ptr@VDiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>(std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey> const &)
0x180138287  mov     eax, 5
0x18013828c  or      esi, eax
0x18013828e  cmp     [rbp+80h+var_D0], 0
0x180138293  jnz     short loc_180138299
0x180138295  mov     bl, 1
0x180138297  jmp     short loc_18013829B
0x180138299  xor     bl, bl
0x18013829b  test    sil, 1
0x18013829f  jz      short loc_1801382B2
0x1801382a1  and     esi, 0FFFFFFFEh
0x1801382a4  mov     rcx, [rbp+80h+var_D0+8]; this
0x1801382a8  test    rcx, rcx
0x1801382ab  jz      short loc_1801382B2
0x1801382ad  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801382b2  test    bl, bl
0x1801382b4  jz      loc_1801383C5
0x1801382ba  mov     r8, r14
0x1801382bd  lea     rdx, [rbp+80h+var_B0]
0x1801382c1  mov     rcx, r12
0x1801382c4  call    ??$_Find_lower_bound@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@2@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@2@@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@2@@2@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>>>>,0>>::_Find_lower_bound<std::wstring>(std::wstring const &)
0x1801382c9  mov     r8, r14
0x1801382cc  mov     rbx, [rbp+80h+var_A0]
0x1801382d0  mov     rdx, rbx
0x1801382d3  call    ??$_Lower_bound_duplicate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@2@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@2@@2@@std@@@2@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@2@@2@@std@@PEAX@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>>>>,0>>::_Lower_bound_duplicate<std::wstring>(std::_Tree_node<std::pair<std::wstring const,std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>>>,void *> * const,std::wstring const &)
0x1801382d8  test    al, al
0x1801382da  jz      short loc_180138328
0x1801382dc  cmp     rbx, [r12]
0x1801382e0  jz      short loc_180138328
0x1801382e2  mov     r8, r14
0x1801382e5  lea     rdx, [rbp+80h+var_88]
0x1801382e9  mov     rcx, r12
0x1801382ec  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@2@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@2@@2@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@2@@2@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>>>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x1801382f1  mov     r9, [rax]
0x1801382f4  mov     rcx, [r9+48h]
0x1801382f8  cmp     rcx, [r9+50h]
0x1801382fc  jz      short loc_180138312
0x1801382fe  lea     rdx, [rsp+180h+var_120]
0x180138303  call    ??$_Construct_in_place@V?$shared_ptr@VDiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@@std@@AEBV12@@std@@YAXAEAV?$shared_ptr@VDiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@@0@AEBV10@@Z; std::_Construct_in_place<std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>,std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey> const &>(std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey> &,std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey> const &)
0x180138308  add     qword ptr [r9+48h], 10h
0x18013830d  jmp     loc_1801383C5
0x180138312  lea     r8, [rsp+180h+var_120]
0x180138317  mov     rdx, rcx
0x18013831a  lea     rcx, [r9+40h]
0x18013831e  call    ??$_Emplace_reallocate@AEBV?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@?$vector@V?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@1@QEAV21@AEBV21@@Z; std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>>::_Emplace_reallocate<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy> const &>(std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy> * const,std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy> const &)
0x180138323  jmp     loc_1801383C5
0x180138328  lea     rcx, [rsp+180h+var_138]
0x18013832d  call    ??0?$vector@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>(void)
0x180138332  nop
0x180138333  mov     rcx, [rsp+180h+var_130]
0x180138338  cmp     rcx, [rsp+180h+var_128]
0x18013833d  jz      short loc_180138351
0x18013833f  lea     rdx, [rsp+180h+var_120]
0x180138344  call    ??$_Construct_in_place@V?$shared_ptr@VDiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@@std@@AEBV12@@std@@YAXAEAV?$shared_ptr@VDiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@@0@AEBV10@@Z; std::_Construct_in_place<std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>,std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey> const &>(std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey> &,std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey> const &)
0x180138349  add     [rsp+180h+var_130], 10h
0x18013834f  jmp     short loc_180138363
0x180138351  lea     r8, [rsp+180h+var_120]
0x180138356  mov     rdx, rcx
0x180138359  lea     rcx, [rsp+180h+var_138]
0x18013835e  call    ??$_Emplace_reallocate@AEBV?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@?$vector@V?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@1@QEAV21@AEBV21@@Z; std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>>::_Emplace_reallocate<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy> const &>(std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy> * const,std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy> const &)
0x180138363  mov     r8, r14
0x180138366  lea     rdx, [rbp+80h+var_78]
0x18013836a  mov     rcx, r12
0x18013836d  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@2@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@2@@2@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@2@@2@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>>>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x180138372  mov     rcx, [rax]
0x180138375  add     rcx, 40h ; '@'
0x180138379  lea     rax, [rsp+180h+var_138]
0x18013837e  cmp     rcx, rax
0x180138381  jz      short loc_18013839A
0x180138383  mov     r8, [rsp+180h+var_130]
0x180138388  mov     rdx, [rsp+180h+var_138]
0x18013838d  sub     r8, rdx
0x180138390  sar     r8, 4
0x180138394  call    ??$_Assign_counted_range@PEAV?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@?$vector@V?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@2@@std@@AEAAXPEAV?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@1@_K@Z; std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>>::_Assign_counted_range<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy> *>(std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy> *,unsigned __int64)
0x180138399  nop
0x18013839a  mov     rcx, [rsp+180h+var_138]
0x18013839f  test    rcx, rcx
0x1801383a2  jz      short loc_1801383C5
0x1801383a4  mov     rdx, [rsp+180h+var_130]
0x1801383a9  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>>>(std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy> *,std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy> * const,std::allocator<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>> &)
0x1801383ae  mov     rcx, [rsp+180h+var_138]
0x1801383b3  mov     rdx, [rsp+180h+var_128]
0x1801383b8  sub     rdx, rcx
0x1801383bb  and     rdx, 0FFFFFFFFFFFFFFF0h
0x1801383bf  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1801383c4  nop
0x1801383c5  mov     rcx, [rsp+180h+var_118]; this
0x1801383ca  test    rcx, rcx
0x1801383cd  jz      short loc_1801383D5
0x1801383cf  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801383d4  nop
0x1801383d5  lea     rcx, [rbp+80h+var_68]
0x1801383d9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801383de  add     r15, 20h ; ' '
0x1801383e2  mov     edi, 80000000h
0x1801383e7  jmp     loc_180138148
0x1801383ec  lea     rcx, [rbp+80h+var_F0]
0x1801383f0  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1801383f5  nop
0x1801383f6  lea     rcx, [rsp+180h+var_148]
0x1801383fb  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180138400  add     r14, 20h ; ' '
0x180138404  mov     rax, [rbp+80h+var_D8]
0x180138408  jmp     loc_1801380D3
0x18013840d  mov     rcx, [rbp+88h]; this
0x180138414  mov     r9d, eax; char *
0x180138417  lea     r8, aOnecoreuapAdmi_32; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18013841e  mov     edx, 267h; void *
0x180138423  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180138428  nop
0x180138429  lea     rcx, [rbp+80h+var_68]
0x18013842d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180138432  jmp     short loc_180138450
0x180138434  mov     rcx, [rbp+88h]; this
0x18013843b  mov     r9d, eax; char *
0x18013843e  lea     r8, aOnecoreuapAdmi_32; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180138445  mov     edx, 25Fh; void *
0x18013844a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013844f  nop
0x180138450  lea     rcx, [rbp+80h+var_F0]
0x180138454  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180138459  jmp     short loc_180138478
0x18013845b  mov     rcx, [rbp+88h]; this
0x180138462  mov     r9d, eax; char *
0x180138465  lea     r8, aOnecoreuapAdmi_32; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18013846c  mov     edx, 25Bh; void *
0x180138471  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180138476  mov     ebx, eax
0x180138478  lea     rcx, [rsp+180h+var_148]
0x18013847d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180138482  jmp     loc_1801380B2
0x180138487  lea     rcx, [rsp+180h+var_108]
0x18013848c  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180138491  xor     ebx, ebx
0x180138493  lea     rcx, [rsp+180h+hKey]
0x180138498  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18013849d  mov     eax, ebx
0x18013849f  mov     rcx, [rbp+80h+var_48]
0x1801384a3  xor     rcx, rsp; StackCookie
  ... truncated ...
```
