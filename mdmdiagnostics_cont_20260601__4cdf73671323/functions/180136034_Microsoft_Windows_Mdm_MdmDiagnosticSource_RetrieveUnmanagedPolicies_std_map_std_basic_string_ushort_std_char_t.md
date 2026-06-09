# Microsoft::Windows::Mdm::MdmDiagnosticSource::RetrieveUnmanagedPolicies(std::map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>,std::allocator<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>,std::allocator<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>>>>>> &)

- ea: `0x180136034`
- end: `0x1801364f5`
- name: `?RetrieveUnmanagedPolicies@MdmDiagnosticSource@Mdm@Windows@Microsoft@@YAJAEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@2@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@2@@2@@std@@@2@@std@@@Z`
- size: `1217`
- prototype: ``
- caller_count: `1`
- callee_count: `29`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18013197c`

## callees

- `0x180019000`
- `0x180019024`
- `0x1800e4348`
- `0x1800e5594`
- `0x1800e66b8`
- `0x1800e691c`
- `0x1800e7c08`
- `0x1800ece5c`
- `0x1800ee898`
- `0x1800ef188`
- `0x1800ef5d8`
- `0x1800f9a0c`
- `0x180104108`
- `0x180104270`
- `0x180108060`
- `0x180111c80`
- `0x180111d04`
- `0x180115004`
- `0x18012594c`
- `0x180133134`
- `0x1801332a8`
- `0x18013360c`
- `0x18013378c`
- `0x1801338a0`
- `0x180134dd0`
- `0x180135484`
- `0x18013561c`
- `0x180136034`
- `0x1801365f0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18013608a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18013614a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18013608a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18013614a`
- `policymanager!EnterprisePolicyManagerStore_IsAreaPolicySLAPIAllowed` at `0x180136251`
- `policymanager!EnterprisePolicyManagerStore_IsAreaPolicySLAPIAllowed` at `0x180136251`

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
0x180136034  push    rbp
0x180136036  push    rbx
0x180136037  push    rsi
0x180136038  push    rdi
0x180136039  push    r12
0x18013603b  push    r13
0x18013603d  push    r14
0x18013603f  push    r15
0x180136041  lea     rbp, [rsp-48h]
0x180136046  sub     rsp, 148h
0x18013604d  mov     rax, cs:__security_cookie
0x180136054  xor     rax, rsp
0x180136057  mov     [rbp+80h+var_48], rax
0x18013605b  mov     r12, rcx
0x18013605e  xor     esi, esi
0x180136060  mov     [rsp+180h+var_150], esi
0x180136064  mov     [rsp+180h+hKey], rsi
0x180136069  lea     rax, [rsp+180h+hKey]
0x18013606e  mov     qword ptr [rsp+180h+phkResult], rax; int
0x180136073  mov     r9d, 20019h; samDesired
0x180136079  xor     r8d, r8d; ulOptions
0x18013607c  lea     rdx, aSoftwareMicros_5; "SOFTWARE\\Microsoft\\PolicyManager\\def"...
0x180136083  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18013608a  call    cs:__imp_RegOpenKeyExW
0x180136090  test    eax, eax
0x180136092  jz      short loc_1801360B6
0x180136094  mov     rcx, [rbp+88h]; this
0x18013609b  mov     r9d, eax; char *
0x18013609e  lea     r8, aOnecoreuapAdmi_32; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1801360a5  mov     edx, 252h; void *
0x1801360aa  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1801360af  mov     ebx, eax
0x1801360b1  jmp     loc_1801364C9
0x1801360b6  lea     rcx, [rsp+180h+var_108]
0x1801360bb  call    ??0?$vector@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>(void)
0x1801360c0  nop
0x1801360c1  lea     r8, [rsp+180h+var_108]
0x1801360c6  xor     edx, edx
0x1801360c8  lea     rcx, [rsp+180h+hKey]
0x1801360cd  call    _anonymous_namespace___GetSubKeyNames
0x1801360d2  mov     ebx, eax
0x1801360d4  test    eax, eax
0x1801360d6  jns     short loc_180136103
0x1801360d8  mov     rcx, [rbp+88h]; this
0x1801360df  mov     r9d, eax; char *
0x1801360e2  lea     r8, aOnecoreuapAdmi_32; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1801360e9  mov     edx, 256h; void *
0x1801360ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801360f3  nop
0x1801360f4  lea     rcx, [rsp+180h+var_108]
0x1801360f9  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1801360fe  jmp     loc_1801364C9
0x180136103  mov     r14, [rsp+180h+var_108]
0x180136108  mov     rax, [rbp+80h+var_100]
0x18013610c  mov     [rbp+80h+var_D8], rax
0x180136110  mov     edi, 80000000h
0x180136115  cmp     r14, rax
0x180136118  jz      loc_1801364BD
0x18013611e  mov     [rsp+180h+var_148], 0
0x180136127  mov     rcx, r14
0x18013612a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18013612f  lea     rcx, [rsp+180h+var_148]
0x180136134  mov     qword ptr [rsp+180h+phkResult], rcx; unsigned int
0x180136139  mov     r9d, 20019h; samDesired
0x18013613f  xor     r8d, r8d; ulOptions
0x180136142  mov     rdx, rax; lpSubKey
0x180136145  mov     rcx, [rsp+180h+hKey]; hKey
0x18013614a  call    cs:__imp_RegOpenKeyExW
0x180136150  test    eax, eax
0x180136152  jnz     loc_180136491
0x180136158  lea     rcx, [rbp+80h+var_F0]
0x18013615c  call    ??0?$vector@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>(void)
0x180136161  nop
0x180136162  lea     r8, [rbp+80h+var_F0]
0x180136166  xor     edx, edx
0x180136168  lea     rcx, [rsp+180h+var_148]
0x18013616d  call    _anonymous_namespace___GetSubKeyNames
0x180136172  mov     ebx, eax
0x180136174  test    eax, eax
0x180136176  js      loc_18013646A
0x18013617c  mov     r15, [rbp+80h+var_F0]
0x180136180  mov     r13, [rbp+80h+var_E8]
0x180136184  cmp     r15, r13
0x180136187  jz      loc_180136422
0x18013618d  lea     rcx, [rbp+80h+var_68]
0x180136191  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180136196  nop
0x180136197  lea     r8, [rbp+80h+var_68]
0x18013619b  mov     rdx, r15
0x18013619e  mov     rcx, r14
0x1801361a1  call    _anonymous_namespace___GetDefaultPolicyValue
0x1801361a6  mov     ebx, eax
0x1801361a8  lea     ecx, [rax+rdi]
0x1801361ab  test    edi, ecx
0x1801361ad  jnz     short loc_1801361BA
0x1801361af  cmp     eax, 80070002h
0x1801361b4  jnz     loc_180136443
0x1801361ba  mov     ecx, 0D0h; Size
0x1801361bf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1801361c4  mov     rbx, rax
0x1801361c7  mov     [rbp+80h+var_C0], rax
0x1801361cb  xorps   xmm0, xmm0
0x1801361ce  movups  xmmword ptr [rax], xmm0
0x1801361d1  mov     dword ptr [rax+8], 1
0x1801361d8  mov     dword ptr [rax+0Ch], 1
0x1801361df  lea     rax, ??_7?$_Ref_count_obj2@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@6B@; const std::_Ref_count_obj2<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>::`vftable'
0x1801361e6  mov     [rbx], rax
0x1801361e9  lea     rdi, [rbx+10h]
0x1801361ed  lea     r9, Name
0x1801361f4  mov     r8, r15
0x1801361f7  mov     rdx, r14
0x1801361fa  mov     rcx, rdi
0x1801361fd  call    ??$_Construct_in_place@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV67@AEAY00$$CBG@std@@YAXAEAVPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@1AEAY00$$CBG@Z; std::_Construct_in_place<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy,std::wstring &,std::wstring &,ushort const (&)[1]>(Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy &,std::wstring &,std::wstring &,ushort const (&)[1])
0x180136202  nop
0x180136203  or      esi, 2
0x180136206  mov     [rsp+180h+var_120], rdi
0x18013620b  mov     [rsp+180h+var_118], rbx
0x180136210  lea     rcx, [rdi+80h]
0x180136217  lea     rdx, [rbp+80h+var_68]
0x18013621b  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180136220  mov     [rsp+180h+var_150], 0
0x180136228  mov     rcx, r15
0x18013622b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180136230  mov     rbx, rax
0x180136233  mov     rcx, r14
0x180136236  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18013623b  mov     qword ptr [rsp+180h+phkResult], 0
0x180136244  lea     r9, [rsp+180h+var_150]
0x180136249  mov     r8, rbx
0x18013624c  mov     rdx, rax
0x18013624f  xor     ecx, ecx
0x180136251  call    cs:__imp_?EnterprisePolicyManagerStore_IsAreaPolicySLAPIAllowed@@YAJW4EnrollmentEnrollType@@PEBG1PEAHPEAPEAE@Z; EnterprisePolicyManagerStore_IsAreaPolicySLAPIAllowed(EnrollmentEnrollType,ushort const *,ushort const *,int *,uchar * *)
0x180136257  xor     edx, edx; bool
0x180136259  mov     rcx, rdi; this
0x18013625c  call    ?GetUniquePolicyId@Policy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAA_K_N@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy::GetUniquePolicyId(bool)
0x180136261  mov     rbx, rax
0x180136264  cmp     [rsp+180h+var_150], 0
0x180136269  jz      short loc_1801362CF
0x18013626b  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x180136270  mov     [rsp+180h+var_110], rbx
0x180136275  lea     rbx, [rax+40h]
0x180136279  lea     r8, [rsp+180h+var_110]
0x18013627e  lea     rdx, [rbp+80h+var_B8]
0x180136282  mov     rcx, rbx
0x180136285  call    ?find@?$_Tree@V?$_Tmap_traits@_KV?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@std@@@std@@@std@@@2@AEB_K@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>>>,0>>::find(unsigned __int64 const &)
0x18013628a  mov     rcx, [rbx]
0x18013628d  cmp     [rax], rcx
0x180136290  jnz     short loc_18013629C
0x180136292  xorps   xmm0, xmm0
0x180136295  movdqu  xmmword ptr [rbp+80h+var_D0], xmm0
0x18013629a  jmp     short loc_1801362BD
0x18013629c  lea     r8, [rsp+180h+var_110]
0x1801362a1  lea     rdx, [rbp+80h+var_98]
0x1801362a5  mov     rcx, rbx
0x1801362a8  call    ??$_Try_emplace@AEB_K$$V@?$map@_KV?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CB_KV?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@std@@PEAX@std@@_N@1@AEB_K@Z; std::map<unsigned __int64,std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>>::_Try_emplace<unsigned __int64 const &,>(unsigned __int64 const &)
0x1801362ad  mov     rdx, [rax]
0x1801362b0  add     rdx, 28h ; '('
0x1801362b4  lea     rcx, [rbp+80h+var_D0]
0x1801362b8  call    ??0?$shared_ptr@VDiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>(std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey> const &)
0x1801362bd  mov     eax, 5
0x1801362c2  or      esi, eax
0x1801362c4  cmp     [rbp+80h+var_D0], 0
0x1801362c9  jnz     short loc_1801362CF
0x1801362cb  mov     bl, 1
0x1801362cd  jmp     short loc_1801362D1
0x1801362cf  xor     bl, bl
0x1801362d1  test    sil, 1
0x1801362d5  jz      short loc_1801362E8
0x1801362d7  and     esi, 0FFFFFFFEh
0x1801362da  mov     rcx, [rbp+80h+var_D0+8]; this
0x1801362de  test    rcx, rcx
0x1801362e1  jz      short loc_1801362E8
0x1801362e3  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801362e8  test    bl, bl
0x1801362ea  jz      loc_1801363FB
0x1801362f0  mov     r8, r14
0x1801362f3  lea     rdx, [rbp+80h+var_B0]
0x1801362f7  mov     rcx, r12
0x1801362fa  call    ??$_Find_lower_bound@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@2@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@2@@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@2@@2@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>>>>,0>>::_Find_lower_bound<std::wstring>(std::wstring const &)
0x1801362ff  mov     r8, r14
0x180136302  mov     rbx, [rbp+80h+var_A0]
0x180136306  mov     rdx, rbx
0x180136309  call    ??$_Lower_bound_duplicate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@2@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@2@@2@@std@@@2@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@2@@2@@std@@PEAX@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>>>>,0>>::_Lower_bound_duplicate<std::wstring>(std::_Tree_node<std::pair<std::wstring const,std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>>>,void *> * const,std::wstring const &)
0x18013630e  test    al, al
0x180136310  jz      short loc_18013635E
0x180136312  cmp     rbx, [r12]
0x180136316  jz      short loc_18013635E
0x180136318  mov     r8, r14
0x18013631b  lea     rdx, [rbp+80h+var_88]
0x18013631f  mov     rcx, r12
0x180136322  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@2@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@2@@2@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@2@@2@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>>>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x180136327  mov     r9, [rax]
0x18013632a  mov     rcx, [r9+48h]
0x18013632e  cmp     rcx, [r9+50h]
0x180136332  jz      short loc_180136348
0x180136334  lea     rdx, [rsp+180h+var_120]
0x180136339  call    ??$_Construct_in_place@V?$shared_ptr@VDiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@@std@@AEBV12@@std@@YAXAEAV?$shared_ptr@VDiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@@0@AEBV10@@Z; std::_Construct_in_place<std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>,std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey> const &>(std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey> &,std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey> const &)
0x18013633e  add     qword ptr [r9+48h], 10h
0x180136343  jmp     loc_1801363FB
0x180136348  lea     r8, [rsp+180h+var_120]
0x18013634d  mov     rdx, rcx
0x180136350  lea     rcx, [r9+40h]
0x180136354  call    ??$_Emplace_reallocate@AEBV?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@?$vector@V?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@1@QEAV21@AEBV21@@Z; std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>>::_Emplace_reallocate<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy> const &>(std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy> * const,std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy> const &)
0x180136359  jmp     loc_1801363FB
0x18013635e  lea     rcx, [rsp+180h+var_138]
0x180136363  call    ??0?$vector@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>(void)
0x180136368  nop
0x180136369  mov     rcx, [rsp+180h+var_130]
0x18013636e  cmp     rcx, [rsp+180h+var_128]
0x180136373  jz      short loc_180136387
0x180136375  lea     rdx, [rsp+180h+var_120]
0x18013637a  call    ??$_Construct_in_place@V?$shared_ptr@VDiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@@std@@AEBV12@@std@@YAXAEAV?$shared_ptr@VDiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@@0@AEBV10@@Z; std::_Construct_in_place<std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>,std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey> const &>(std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey> &,std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey> const &)
0x18013637f  add     [rsp+180h+var_130], 10h
0x180136385  jmp     short loc_180136399
0x180136387  lea     r8, [rsp+180h+var_120]
0x18013638c  mov     rdx, rcx
0x18013638f  lea     rcx, [rsp+180h+var_138]
0x180136394  call    ??$_Emplace_reallocate@AEBV?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@?$vector@V?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@1@QEAV21@AEBV21@@Z; std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>>::_Emplace_reallocate<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy> const &>(std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy> * const,std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy> const &)
0x180136399  mov     r8, r14
0x18013639c  lea     rdx, [rbp+80h+var_78]
0x1801363a0  mov     rcx, r12
0x1801363a3  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@2@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@2@@2@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@2@@2@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>>>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x1801363a8  mov     rcx, [rax]
0x1801363ab  add     rcx, 40h ; '@'
0x1801363af  lea     rax, [rsp+180h+var_138]
0x1801363b4  cmp     rcx, rax
0x1801363b7  jz      short loc_1801363D0
0x1801363b9  mov     r8, [rsp+180h+var_130]
0x1801363be  mov     rdx, [rsp+180h+var_138]
0x1801363c3  sub     r8, rdx
0x1801363c6  sar     r8, 4
0x1801363ca  call    ??$_Assign_counted_range@PEAV?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@?$vector@V?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@2@@std@@AEAAXPEAV?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@1@_K@Z; std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>>::_Assign_counted_range<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy> *>(std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy> *,unsigned __int64)
0x1801363cf  nop
0x1801363d0  mov     rcx, [rsp+180h+var_138]
0x1801363d5  test    rcx, rcx
0x1801363d8  jz      short loc_1801363FB
0x1801363da  mov     rdx, [rsp+180h+var_130]
0x1801363df  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>>>(std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy> *,std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy> * const,std::allocator<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>> &)
0x1801363e4  mov     rcx, [rsp+180h+var_138]
0x1801363e9  mov     rdx, [rsp+180h+var_128]
0x1801363ee  sub     rdx, rcx
0x1801363f1  and     rdx, 0FFFFFFFFFFFFFFF0h
0x1801363f5  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1801363fa  nop
0x1801363fb  mov     rcx, [rsp+180h+var_118]; this
0x180136400  test    rcx, rcx
0x180136403  jz      short loc_18013640B
0x180136405  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18013640a  nop
0x18013640b  lea     rcx, [rbp+80h+var_68]
0x18013640f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180136414  add     r15, 20h ; ' '
0x180136418  mov     edi, 80000000h
0x18013641d  jmp     loc_180136184
0x180136422  lea     rcx, [rbp+80h+var_F0]
0x180136426  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18013642b  nop
0x18013642c  lea     rcx, [rsp+180h+var_148]
0x180136431  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180136436  add     r14, 20h ; ' '
0x18013643a  mov     rax, [rbp+80h+var_D8]
0x18013643e  jmp     loc_180136115
0x180136443  mov     rcx, [rbp+88h]; this
0x18013644a  mov     r9d, eax; char *
0x18013644d  lea     r8, aOnecoreuapAdmi_32; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180136454  mov     edx, 267h; void *
0x180136459  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013645e  nop
0x18013645f  lea     rcx, [rbp+80h+var_68]
0x180136463  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180136468  jmp     short loc_180136486
0x18013646a  mov     rcx, [rbp+88h]; this
0x180136471  mov     r9d, eax; char *
0x180136474  lea     r8, aOnecoreuapAdmi_32; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18013647b  mov     edx, 25Fh; void *
0x180136480  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180136485  nop
0x180136486  lea     rcx, [rbp+80h+var_F0]
0x18013648a  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18013648f  jmp     short loc_1801364AE
0x180136491  mov     rcx, [rbp+88h]; this
0x180136498  mov     r9d, eax; char *
0x18013649b  lea     r8, aOnecoreuapAdmi_32; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1801364a2  mov     edx, 25Bh; void *
0x1801364a7  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1801364ac  mov     ebx, eax
0x1801364ae  lea     rcx, [rsp+180h+var_148]
0x1801364b3  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801364b8  jmp     loc_1801360F4
0x1801364bd  lea     rcx, [rsp+180h+var_108]
0x1801364c2  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1801364c7  xor     ebx, ebx
0x1801364c9  lea     rcx, [rsp+180h+hKey]
0x1801364ce  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801364d3  mov     eax, ebx
0x1801364d5  mov     rcx, [rbp+80h+var_48]
0x1801364d9  xor     rcx, rsp; StackCookie
0x1801364dc  call    __security_check_cookie
0x1801364e1  add     rsp, 148h
0x1801364e8  pop     r15
  ... truncated ...
```
