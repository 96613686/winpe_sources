# Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::CollectAllResourcesForEnrollment(ushort const *,ulong,std::list<Microsoft::Windows::Mdm::MdmDiagnosticSource::ResourceRecord,std::allocator<Microsoft::Windows::Mdm::MdmDiagnosticSource::ResourceRecord>> &)

- ea: `0x18013959c`
- end: `0x1801398ed`
- name: `?CollectAllResourcesForEnrollment@ProvisionedResources@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJPEBGKAEAV?$list@VResourceRecord@MdmDiagnosticSource@Mdm@Windows@Microsoft@@V?$allocator@VResourceRecord@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@std@@@Z`
- size: `849`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18013a188`

## callees

- `0x180019080`
- `0x1800e5744`
- `0x1800e68b0`
- `0x1800e734c`
- `0x1800e7de8`
- `0x1800e8508`
- `0x1800ed46c`
- `0x1800ef8c4`
- `0x1800efd9c`
- `0x1800f00e4`
- `0x180105294`
- `0x180128c50`
- `0x1801293ec`
- `0x18013923c`
- `0x180139270`
- `0x18013959c`
- `0x180139dd0`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x1801395df`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1801395df`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18013975d`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18013975d`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1801397c8`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1801397c8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18013966d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18013966d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18013962c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18013962c`

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
0x18013959c  mov     [rsp-8+arg_0], rbx
0x1801395a1  push    rbp
0x1801395a2  push    rsi
0x1801395a3  push    rdi
0x1801395a4  push    r14
0x1801395a6  push    r15
0x1801395a8  lea     rbp, [rsp-210h]
0x1801395b0  sub     rsp, 310h
0x1801395b7  mov     rax, cs:__security_cookie
0x1801395be  xor     rax, rsp
0x1801395c1  mov     [rbp+230h+var_30], rax
0x1801395c8  mov     r14, r9
0x1801395cb  mov     rbx, rdx
0x1801395ce  mov     [rbp+230h+var_290], rdx
0x1801395d2  mov     [rsp+330h+var_2C0], r8d
0x1801395d7  xor     r15d, r15d
0x1801395da  mov     [rsp+330h+hKey], r15
0x1801395df  call    cs:__imp_RtlIsStateSeparationEnabled
0x1801395e6  nop     dword ptr [rax+rax+00h]
0x1801395eb  lea     rcx, aSoftwareMicros_12; "SOFTWARE\\Microsoft\\EnterpriseResource"...
0x1801395f2  lea     rdx, aOsdataSoftware_0; "OSData\\SOFTWARE\\Microsoft\\Enterprise"...
0x1801395f9  test    al, al
0x1801395fb  cmovz   rdx, rcx
0x1801395ff  lea     rcx, [rbp+230h+var_260]
0x180139603  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180139608  nop
0x180139609  mov     rdx, rbx
0x18013960c  lea     rcx, [rbp+230h+var_260]
0x180139610  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180139615  mov     rbx, [rsp+330h+hKey]
0x18013961a  test    rbx, rbx
0x18013961d  jz      short loc_180139642
0x18013961f  lea     rcx, [rsp+330h+cchName]; this
0x180139624  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180139629  mov     rcx, rbx; hKey
0x18013962c  call    cs:__imp_RegCloseKey
0x180139633  nop     dword ptr [rax+rax+00h]
0x180139638  lea     rcx, [rsp+330h+cchName]; this
0x18013963d  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180139642  mov     [rsp+330h+hKey], r15
0x180139647  lea     rcx, [rbp+230h+var_260]
0x18013964b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180139650  mov     rdx, rax; lpSubKey
0x180139653  lea     rax, [rsp+330h+hKey]
0x180139658  mov     [rsp+330h+phkResult], rax; int
0x18013965d  mov     r9d, 20019h; samDesired
0x180139663  xor     r8d, r8d; ulOptions
0x180139666  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18013966d  call    cs:__imp_RegOpenKeyExW
0x180139674  nop     dword ptr [rax+rax+00h]
0x180139679  mov     ebx, eax
0x18013967b  test    eax, eax
0x18013967d  jz      loc_18013971E
0x180139683  cmp     eax, 2
0x180139686  jz      short loc_1801396B6
0x180139688  test    eax, eax
0x18013968a  jle     short loc_180139695
0x18013968c  movzx   ebx, ax
0x18013968f  or      ebx, 80070000h
0x180139695  test    ebx, ebx
0x180139697  jns     short loc_1801396E1
0x180139699  mov     rcx, [rbp+238h]; this
0x1801396a0  mov     r9d, ebx; char *
0x1801396a3  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1801396aa  mov     edx, 193h; void *
0x1801396af  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801396b4  jmp     short loc_1801396E1
0x1801396b6  mov     qword ptr [rsp+330h+cchName], r15
0x1801396bb  mov     [rbp+230h+var_2B0], r15
0x1801396bf  lea     rax, [rsp+330h+cchName]
0x1801396c4  mov     [rsp+330h+phkResult], rax
0x1801396c9  lea     r9, [rbp+230h+var_2B0]
0x1801396cd  lea     r8, [rbp+230h+var_290]
0x1801396d1  lea     rdx, [rsp+330h+var_2C0]
0x1801396d6  mov     rcx, r14
0x1801396d9  call    ??$emplace_back@AEAKAEAPEBG$$T$$T@?$list@VResourceRecord@MdmDiagnosticSource@Mdm@Windows@Microsoft@@V?$allocator@VResourceRecord@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@std@@QEAAAEAVResourceRecord@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAKAEAPEBG$$QEA$$T2@Z
0x1801396de  mov     ebx, r15d
0x1801396e1  lea     rcx, [rbp+230h+var_260]
0x1801396e5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801396ea  nop
0x1801396eb  lea     rcx, [rsp+330h+hKey]
0x1801396f0  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801396f5  mov     eax, ebx
0x1801396f7  mov     rcx, [rbp+230h+var_30]
0x1801396fe  xor     rcx, rsp; StackCookie
0x180139701  call    __security_check_cookie
0x180139706  mov     rbx, [rsp+330h+arg_0]
0x18013970e  add     rsp, 310h
0x180139715  pop     r15
0x180139717  pop     r14
0x180139719  pop     rdi
0x18013971a  pop     rsi
0x18013971b  pop     rbp
0x18013971c  retn
0x18013971e  mov     [rsp+330h+cSubKeys], r15d
0x180139723  mov     [rsp+330h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180139728  mov     [rsp+330h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18013972d  mov     [rsp+330h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180139732  mov     [rsp+330h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180139737  mov     [rsp+330h+lpcValues], r15; lpcValues
0x18013973c  mov     [rsp+330h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180139741  mov     [rsp+330h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x180139746  lea     rax, [rsp+330h+cSubKeys]
0x18013974b  mov     [rsp+330h+phkResult], rax; unsigned int
0x180139750  xor     r9d, r9d; lpReserved
0x180139753  xor     r8d, r8d; lpcchClass
0x180139756  xor     edx, edx; lpClass
0x180139758  mov     rcx, [rsp+330h+hKey]; hKey
0x18013975d  call    cs:__imp_RegQueryInfoKeyW
0x180139764  nop     dword ptr [rax+rax+00h]
0x180139769  test    eax, eax
0x18013976b  jz      short loc_18013978F
0x18013976d  mov     edx, 1ABh; void *
0x180139772  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180139779  mov     r9d, eax; char *
0x18013977c  mov     rcx, [rbp+238h]; this
0x180139783  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180139788  mov     ebx, eax
0x18013978a  jmp     loc_1801396E1
0x18013978f  mov     esi, r15d
0x180139792  cmp     esi, [rsp+330h+cSubKeys]
0x180139796  jnb     loc_1801396DE
0x18013979c  mov     [rsp+330h+cchName], 104h
0x1801397a4  mov     [rsp+330h+lpcValues], r15; lpftLastWriteTime
0x1801397a9  mov     [rsp+330h+lpcbMaxClassLen], r15; lpcchClass
0x1801397ae  mov     [rsp+330h+lpcbMaxSubKeyLen], r15; lpClass
0x1801397b3  mov     [rsp+330h+phkResult], r15; lpReserved
0x1801397b8  lea     r9, [rsp+330h+cchName]; lpcchName
0x1801397bd  lea     r8, [rbp+230h+Name]; lpName
0x1801397c1  mov     edx, esi; dwIndex
0x1801397c3  mov     rcx, [rsp+330h+hKey]; hKey
0x1801397c8  call    cs:__imp_RegEnumKeyExW
0x1801397cf  nop     dword ptr [rax+rax+00h]
0x1801397d4  test    eax, eax
0x1801397d6  jnz     loc_1801398E2
0x1801397dc  lea     rcx, [rbp+230h+var_2A8]
0x1801397e0  call    ??0?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::list<std::wstring>::list<std::wstring>(void)
0x1801397e5  nop
0x1801397e6  lea     rdx, [rbp+230h+Name]
0x1801397ea  lea     rcx, [rbp+230h+var_280]
0x1801397ee  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1801397f3  nop
0x1801397f4  lea     rdx, psz; "\\"
0x1801397fb  lea     rcx, [rbp+230h+var_280]
0x1801397ff  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180139804  lea     rdx, aDefault_0; "default"
0x18013980b  lea     rcx, [rbp+230h+var_280]
0x18013980f  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180139814  lea     rcx, [rbp+230h+var_280]
0x180139818  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18013981d  mov     r8, rax
0x180139820  lea     rax, [rbp+230h+var_2A8]
0x180139824  mov     [rsp+330h+phkResult], rax; int
0x180139829  xor     r9d, r9d
0x18013982c  lea     rdx, [rsp+330h+hKey]
0x180139831  call    ?Enumerate@ProvisionedResources@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEBG1AEAV?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::Enumerate(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,ushort const *,ushort const *,std::list<std::wstring> &)
0x180139836  mov     ebx, eax
0x180139838  test    eax, eax
0x18013983a  js      short loc_1801398A0
0x18013983c  mov     rdi, qword ptr [rbp+230h+var_2A8]
0x180139840  mov     rbx, [rdi]
0x180139843  cmp     rbx, rdi
0x180139846  jz      short loc_180139878
0x180139848  lea     rcx, [rbx+10h]
0x18013984c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180139851  mov     [rbp+230h+var_2B0], rax
0x180139855  lea     rax, [rbp+230h+var_2B0]
0x180139859  mov     [rsp+330h+phkResult], rax
0x18013985e  lea     r9, [rbp+230h+Name]
0x180139862  lea     r8, [rbp+230h+var_290]
0x180139866  lea     rdx, [rsp+330h+var_2C0]
0x18013986b  mov     rcx, r14
0x18013986e  call    ??$emplace_back@AEAKAEAPEBGAEAY0BAE@GPEBG@?$list@VResourceRecord@MdmDiagnosticSource@Mdm@Windows@Microsoft@@V?$allocator@VResourceRecord@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@std@@QEAAAEAVResourceRecord@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAKAEAPEBGAEAY0BAE@G$$QEAPEBG@Z; std::list<Microsoft::Windows::Mdm::MdmDiagnosticSource::ResourceRecord>::emplace_back<ulong &,ushort const * &,ushort (&)[260],ushort const *>(ulong &,ushort const * &,ushort (&)[260],ushort const * &&)
0x180139873  mov     rbx, [rbx]
0x180139876  jmp     short loc_180139843
0x180139878  lea     rcx, [rbp+230h+var_280]
0x18013987c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180139881  nop
0x180139882  mov     rdx, qword ptr [rbp+230h+var_2A8]
0x180139886  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x18013988b  mov     edx, 30h ; '0'
0x180139890  mov     rcx, qword ptr [rbp+230h+var_2A8]
0x180139894  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180139899  inc     esi
0x18013989b  jmp     loc_180139792
0x1801398a0  mov     rcx, [rbp+238h]; this
0x1801398a7  mov     r9d, eax; char *
0x1801398aa  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1801398b1  mov     edx, 1B7h; void *
0x1801398b6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801398bb  nop
0x1801398bc  lea     rcx, [rbp+230h+var_280]
0x1801398c0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801398c5  nop
0x1801398c6  mov     rdx, qword ptr [rbp+230h+var_2A8]
0x1801398ca  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x1801398cf  mov     edx, 30h ; '0'
0x1801398d4  mov     rcx, qword ptr [rbp+230h+var_2A8]
0x1801398d8  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1801398dd  jmp     loc_1801396E1
0x1801398e2  mov     edx, 1B0h
0x1801398e7  jmp     loc_180139772
```
