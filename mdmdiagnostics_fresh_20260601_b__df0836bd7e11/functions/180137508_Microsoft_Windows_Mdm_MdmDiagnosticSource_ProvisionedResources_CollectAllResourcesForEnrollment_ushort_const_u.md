# Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::CollectAllResourcesForEnrollment(ushort const *,ulong,std::list<Microsoft::Windows::Mdm::MdmDiagnosticSource::ResourceRecord,std::allocator<Microsoft::Windows::Mdm::MdmDiagnosticSource::ResourceRecord>> &)

- ea: `0x180137508`
- end: `0x18013783a`
- name: `?CollectAllResourcesForEnrollment@ProvisionedResources@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJPEBGKAEAV?$list@VResourceRecord@MdmDiagnosticSource@Mdm@Windows@Microsoft@@V?$allocator@VResourceRecord@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@std@@@Z`
- size: `818`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180138070`

## callees

- `0x180019000`
- `0x1800e5594`
- `0x1800e66dc`
- `0x1800e7124`
- `0x1800e7c08`
- `0x1800e82e4`
- `0x1800ece5c`
- `0x1800ef188`
- `0x1800ef5d8`
- `0x1800ef900`
- `0x180104108`
- `0x1801271ec`
- `0x180127908`
- `0x1801371c0`
- `0x1801371f0`
- `0x180137508`
- `0x180137cd0`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x18013754b`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18013754b`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1801376b6`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1801376b6`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18013771b`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18013771b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801375cd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801375cd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180137592`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180137592`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::CollectAllResourcesForEnrollment(
        __int64 a1,
        __int64 a2,
        int a3,
        int a4)
{
  char IsStateSeparationEnabled; // al
  const wchar_t *v7; // rdx
  const WCHAR *v8; // rax
  LSTATUS v9; // eax
  unsigned int v10; // ebx
  unsigned int v12; // eax
  __int64 v13; // rdx
  DWORD i; // esi
  const WCHAR *v15; // rax
  __int64 v16; // rcx
  int v17; // eax
  _QWORD *v18; // rdi
  _QWORD *j; // rbx
  __int64 v20; // rcx
  __int64 v21; // rcx
  int phkResult; // [rsp+20h] [rbp-E0h]
  unsigned int phkResulta; // [rsp+20h] [rbp-E0h]
  int phkResultb; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cSubKeys; // [rsp+68h] [rbp-98h] BYREF
  int v27; // [rsp+70h] [rbp-90h] BYREF
  DWORD cchName[2]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v29; // [rsp+80h] [rbp-80h] BYREF
  int v30[2]; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v31[2]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v32[32]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v33[32]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR Name[264]; // [rsp+F0h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+338h] [rbp+238h]

  v31[0] = a2;
  v27 = a3;
  hKey = 0;
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled();
  v7 = L"OSData\\SOFTWARE\\Microsoft\\EnterpriseResourceManager\\Tracked\\";
  if ( !IsStateSeparationEnabled )
    v7 = L"SOFTWARE\\Microsoft\\EnterpriseResourceManager\\Tracked\\";
  std::wstring::wstring(v33, v7);
  std::wstring::append(v33, a2);
  hKey = 0;
  v8 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v33);
  v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v8, 0, 0x20019u, &hKey);
  v10 = v9;
  if ( v9 )
  {
    if ( v9 != 2 )
    {
      if ( v9 > 0 )
        v10 = (unsigned __int16)v9 | 0x80070000;
      if ( (v10 & 0x80000000) != 0 )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x193,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\erm.cpp",
          (const char *)v10,
          phkResult);
      goto LABEL_11;
    }
    *(_QWORD *)cchName = 0;
    v29 = 0;
    std::list<Microsoft::Windows::Mdm::MdmDiagnosticSource::ResourceRecord>::emplace_back<unsigned long &,unsigned short const * &,std::nullptr_t,std::nullptr_t>(
      a4,
      (unsigned int)&v27,
      (unsigned int)v31,
      (unsigned int)&v29,
      (__int64)cchName);
LABEL_10:
    v10 = 0;
    goto LABEL_11;
  }
  cSubKeys = 0;
  v12 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
  if ( !v12 )
  {
    for ( i = 0; i < cSubKeys; ++i )
    {
      cchName[0] = 260;
      v12 = RegEnumKeyExW(hKey, i, Name, cchName, 0, 0, 0, 0);
      if ( v12 )
      {
        v13 = 432;
        goto LABEL_14;
      }
      std::list<std::wstring>::list<std::wstring>(v30);
      std::wstring::wstring(v32, Name);
      std::wstring::append(v32, L"\\");
      std::wstring::append(v32, L"default");
      v15 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v32);
      v17 = Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::Enumerate(v16, &hKey, v15, 0, v30);
      v10 = v17;
      if ( v17 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1B7,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\erm.cpp",
          (const char *)(unsigned int)v17,
          phkResultb);
        std::wstring::_Tidy_deallocate(v32);
        std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(
          v21,
          *(_QWORD *)v30);
        std::_Deallocate<16>(*(_QWORD *)v30, 48);
        goto LABEL_11;
      }
      v18 = *(_QWORD **)v30;
      for ( j = **(_QWORD ***)v30; j != v18; j = (_QWORD *)*j )
      {
        v29 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(j + 2);
        std::list<Microsoft::Windows::Mdm::MdmDiagnosticSource::ResourceRecord>::emplace_back<unsigned long &,unsigned short const * &,unsigned short (&)[260],unsigned short const *>(
          a4,
          (unsigned int)&v27,
          (unsigned int)v31,
          (unsigned int)Name,
          (__int64)&v29);
      }
      std::wstring::_Tidy_deallocate(v32);
      std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(
        v20,
        *(_QWORD *)v30);
      std::_Deallocate<16>(*(_QWORD *)v30, 48);
    }
    goto LABEL_10;
  }
  v13 = 427;
LABEL_14:
  v10 = wil::details::in1diag3::Return_Win32(
          retaddr,
          (void *)v13,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\erm.cpp",
          (const char *)v12,
          phkResulta);
LABEL_11:
  std::wstring::_Tidy_deallocate(v33);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return v10;
}

```

## disassembly

```asm
0x180137508  mov     [rsp-8+arg_0], rbx
0x18013750d  push    rbp
0x18013750e  push    rsi
0x18013750f  push    rdi
0x180137510  push    r14
0x180137512  push    r15
0x180137514  lea     rbp, [rsp-210h]
0x18013751c  sub     rsp, 310h
0x180137523  mov     rax, cs:__security_cookie
0x18013752a  xor     rax, rsp
0x18013752d  mov     [rbp+230h+var_30], rax
0x180137534  mov     r14, r9
0x180137537  mov     rbx, rdx
0x18013753a  mov     [rbp+230h+var_290], rdx
0x18013753e  mov     [rsp+330h+var_2C0], r8d
0x180137543  xor     r15d, r15d
0x180137546  mov     [rsp+330h+hKey], r15
0x18013754b  call    cs:__imp_RtlIsStateSeparationEnabled
0x180137551  lea     rcx, aSoftwareMicros_12; "SOFTWARE\\Microsoft\\EnterpriseResource"...
0x180137558  lea     rdx, aOsdataSoftware_0; "OSData\\SOFTWARE\\Microsoft\\Enterprise"...
0x18013755f  test    al, al
0x180137561  cmovz   rdx, rcx
0x180137565  lea     rcx, [rbp+230h+var_260]
0x180137569  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18013756e  nop
0x18013756f  mov     rdx, rbx
0x180137572  lea     rcx, [rbp+230h+var_260]
0x180137576  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18013757b  mov     rbx, [rsp+330h+hKey]
0x180137580  test    rbx, rbx
0x180137583  jz      short loc_1801375A2
0x180137585  lea     rcx, [rsp+330h+cchName]; this
0x18013758a  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18013758f  mov     rcx, rbx; hKey
0x180137592  call    cs:__imp_RegCloseKey
0x180137598  lea     rcx, [rsp+330h+cchName]; this
0x18013759d  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1801375a2  mov     [rsp+330h+hKey], r15
0x1801375a7  lea     rcx, [rbp+230h+var_260]
0x1801375ab  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1801375b0  mov     rdx, rax; lpSubKey
0x1801375b3  lea     rax, [rsp+330h+hKey]
0x1801375b8  mov     [rsp+330h+phkResult], rax; int
0x1801375bd  mov     r9d, 20019h; samDesired
0x1801375c3  xor     r8d, r8d; ulOptions
0x1801375c6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1801375cd  call    cs:__imp_RegOpenKeyExW
0x1801375d3  mov     ebx, eax
0x1801375d5  test    eax, eax
0x1801375d7  jz      loc_180137677
0x1801375dd  cmp     eax, 2
0x1801375e0  jz      short loc_180137610
0x1801375e2  test    eax, eax
0x1801375e4  jle     short loc_1801375EF
0x1801375e6  movzx   ebx, ax
0x1801375e9  or      ebx, 80070000h
0x1801375ef  test    ebx, ebx
0x1801375f1  jns     short loc_18013763B
0x1801375f3  mov     rcx, [rbp+238h]; this
0x1801375fa  mov     r9d, ebx; char *
0x1801375fd  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180137604  mov     edx, 193h; void *
0x180137609  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013760e  jmp     short loc_18013763B
0x180137610  mov     qword ptr [rsp+330h+cchName], r15
0x180137615  mov     [rbp+230h+var_2B0], r15
0x180137619  lea     rax, [rsp+330h+cchName]
0x18013761e  mov     [rsp+330h+phkResult], rax
0x180137623  lea     r9, [rbp+230h+var_2B0]
0x180137627  lea     r8, [rbp+230h+var_290]
0x18013762b  lea     rdx, [rsp+330h+var_2C0]
0x180137630  mov     rcx, r14
0x180137633  call    ??$emplace_back@AEAKAEAPEBG$$T$$T@?$list@VResourceRecord@MdmDiagnosticSource@Mdm@Windows@Microsoft@@V?$allocator@VResourceRecord@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@std@@QEAAAEAVResourceRecord@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAKAEAPEBG$$QEA$$T2@Z
0x180137638  mov     ebx, r15d
0x18013763b  lea     rcx, [rbp+230h+var_260]
0x18013763f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180137644  nop
0x180137645  lea     rcx, [rsp+330h+hKey]
0x18013764a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18013764f  mov     eax, ebx
0x180137651  mov     rcx, [rbp+230h+var_30]
0x180137658  xor     rcx, rsp; StackCookie
0x18013765b  call    __security_check_cookie
0x180137660  mov     rbx, [rsp+330h+arg_0]
0x180137668  add     rsp, 310h
0x18013766f  pop     r15
0x180137671  pop     r14
0x180137673  pop     rdi
0x180137674  pop     rsi
0x180137675  pop     rbp
0x180137676  retn
0x180137677  mov     [rsp+330h+cSubKeys], r15d
0x18013767c  mov     [rsp+330h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180137681  mov     [rsp+330h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180137686  mov     [rsp+330h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x18013768b  mov     [rsp+330h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180137690  mov     [rsp+330h+lpcValues], r15; lpcValues
0x180137695  mov     [rsp+330h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18013769a  mov     [rsp+330h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x18013769f  lea     rax, [rsp+330h+cSubKeys]
0x1801376a4  mov     [rsp+330h+phkResult], rax; unsigned int
0x1801376a9  xor     r9d, r9d; lpReserved
0x1801376ac  xor     r8d, r8d; lpcchClass
0x1801376af  xor     edx, edx; lpClass
0x1801376b1  mov     rcx, [rsp+330h+hKey]; hKey
0x1801376b6  call    cs:__imp_RegQueryInfoKeyW
0x1801376bc  test    eax, eax
0x1801376be  jz      short loc_1801376E2
0x1801376c0  mov     edx, 1ABh; void *
0x1801376c5  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1801376cc  mov     r9d, eax; char *
0x1801376cf  mov     rcx, [rbp+238h]; this
0x1801376d6  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1801376db  mov     ebx, eax
0x1801376dd  jmp     loc_18013763B
0x1801376e2  mov     esi, r15d
0x1801376e5  cmp     esi, [rsp+330h+cSubKeys]
0x1801376e9  jnb     loc_180137638
0x1801376ef  mov     [rsp+330h+cchName], 104h
0x1801376f7  mov     [rsp+330h+lpcValues], r15; lpftLastWriteTime
0x1801376fc  mov     [rsp+330h+lpcbMaxClassLen], r15; lpcchClass
0x180137701  mov     [rsp+330h+lpcbMaxSubKeyLen], r15; lpClass
0x180137706  mov     [rsp+330h+phkResult], r15; lpReserved
0x18013770b  lea     r9, [rsp+330h+cchName]; lpcchName
0x180137710  lea     r8, [rbp+230h+Name]; lpName
0x180137714  mov     edx, esi; dwIndex
0x180137716  mov     rcx, [rsp+330h+hKey]; hKey
0x18013771b  call    cs:__imp_RegEnumKeyExW
0x180137721  test    eax, eax
0x180137723  jnz     loc_18013782F
0x180137729  lea     rcx, [rbp+230h+var_2A8]
0x18013772d  call    ??0?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::list<std::wstring>::list<std::wstring>(void)
0x180137732  nop
0x180137733  lea     rdx, [rbp+230h+Name]
0x180137737  lea     rcx, [rbp+230h+var_280]
0x18013773b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180137740  nop
0x180137741  lea     rdx, psz; "\\"
0x180137748  lea     rcx, [rbp+230h+var_280]
0x18013774c  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180137751  lea     rdx, aDefault_0; "default"
0x180137758  lea     rcx, [rbp+230h+var_280]
0x18013775c  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180137761  lea     rcx, [rbp+230h+var_280]
0x180137765  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18013776a  mov     r8, rax
0x18013776d  lea     rax, [rbp+230h+var_2A8]
0x180137771  mov     [rsp+330h+phkResult], rax; int
0x180137776  xor     r9d, r9d
0x180137779  lea     rdx, [rsp+330h+hKey]
0x18013777e  call    ?Enumerate@ProvisionedResources@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEBG1AEAV?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::Enumerate(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,ushort const *,ushort const *,std::list<std::wstring> &)
0x180137783  mov     ebx, eax
0x180137785  test    eax, eax
0x180137787  js      short loc_1801377ED
0x180137789  mov     rdi, qword ptr [rbp+230h+var_2A8]
0x18013778d  mov     rbx, [rdi]
0x180137790  cmp     rbx, rdi
0x180137793  jz      short loc_1801377C5
0x180137795  lea     rcx, [rbx+10h]
0x180137799  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18013779e  mov     [rbp+230h+var_2B0], rax
0x1801377a2  lea     rax, [rbp+230h+var_2B0]
0x1801377a6  mov     [rsp+330h+phkResult], rax
0x1801377ab  lea     r9, [rbp+230h+Name]
0x1801377af  lea     r8, [rbp+230h+var_290]
0x1801377b3  lea     rdx, [rsp+330h+var_2C0]
0x1801377b8  mov     rcx, r14
0x1801377bb  call    ??$emplace_back@AEAKAEAPEBGAEAY0BAE@GPEBG@?$list@VResourceRecord@MdmDiagnosticSource@Mdm@Windows@Microsoft@@V?$allocator@VResourceRecord@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@std@@QEAAAEAVResourceRecord@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAKAEAPEBGAEAY0BAE@G$$QEAPEBG@Z; std::list<Microsoft::Windows::Mdm::MdmDiagnosticSource::ResourceRecord>::emplace_back<ulong &,ushort const * &,ushort (&)[260],ushort const *>(ulong &,ushort const * &,ushort (&)[260],ushort const * &&)
0x1801377c0  mov     rbx, [rbx]
0x1801377c3  jmp     short loc_180137790
0x1801377c5  lea     rcx, [rbp+230h+var_280]
0x1801377c9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801377ce  nop
0x1801377cf  mov     rdx, qword ptr [rbp+230h+var_2A8]
0x1801377d3  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x1801377d8  mov     edx, 30h ; '0'
0x1801377dd  mov     rcx, qword ptr [rbp+230h+var_2A8]
0x1801377e1  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1801377e6  inc     esi
0x1801377e8  jmp     loc_1801376E5
0x1801377ed  mov     rcx, [rbp+238h]; this
0x1801377f4  mov     r9d, eax; char *
0x1801377f7  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1801377fe  mov     edx, 1B7h; void *
0x180137803  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180137808  nop
0x180137809  lea     rcx, [rbp+230h+var_280]
0x18013780d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180137812  nop
0x180137813  mov     rdx, qword ptr [rbp+230h+var_2A8]
0x180137817  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x18013781c  mov     edx, 30h ; '0'
0x180137821  mov     rcx, qword ptr [rbp+230h+var_2A8]
0x180137825  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18013782a  jmp     loc_18013763B
0x18013782f  mov     edx, 1B0h
0x180137834  jmp     loc_1801376C5
```
