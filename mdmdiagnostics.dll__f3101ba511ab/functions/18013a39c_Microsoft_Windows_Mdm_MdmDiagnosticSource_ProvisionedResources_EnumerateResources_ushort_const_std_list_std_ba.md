# Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::EnumerateResources(ushort const *,std::list<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &,std::list<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &)

- ea: `0x18013a39c`
- end: `0x18013a64f`
- name: `?EnumerateResources@ProvisionedResources@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAJPEBGAEAV?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@1@Z`
- size: `691`
- prototype: ``
- caller_count: `4`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18012cbf8`
- `0x18013184c`
- `0x180133f7c`
- `0x180134578`

## callees

- `0x180019080`
- `0x1800e68b0`
- `0x1800e734c`
- `0x1800e7de8`
- `0x1800e8508`
- `0x1800ed46c`
- `0x1800eef08`
- `0x1800ef8c4`
- `0x1800efd9c`
- `0x1800f9a08`
- `0x1800f9a94`
- `0x1800fa538`
- `0x1800faa0c`
- `0x18010562c`
- `0x18012a958`
- `0x180139dd0`
- `0x18013a39c`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x18013a424`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18013a424`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18013a4a9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18013a4a9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18013a467`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18013a467`
- `DMCmnUtils!DmGetActiveUserSid` at `0x18013a54b`
- `DMCmnUtils!DmGetActiveUserSid` at `0x18013a54b`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::EnumerateResources(
        __int64 a1,
        __int64 a2,
        int a3,
        int a4)
{
  struct Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals *v7; // rax
  int EnrollmentId; // eax
  signed int v9; // ebx
  __int64 v10; // rdx
  char IsStateSeparationEnabled; // al
  const wchar_t *v12; // rdx
  const WCHAR *v13; // rax
  LSTATUS v14; // eax
  __int64 v15; // rcx
  unsigned __int64 v16; // r9
  __int64 v17; // rdx
  int v18; // eax
  int ActiveUserSid; // eax
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rcx
  int phkResult; // [rsp+20h] [rbp-89h]
  int phkResulta; // [rsp+20h] [rbp-89h]
  HKEY hKey; // [rsp+30h] [rbp-79h] BYREF
  unsigned __int16 *v27; // [rsp+38h] [rbp-71h] BYREF
  __int128 v28; // [rsp+40h] [rbp-69h] BYREF
  _BYTE v29[32]; // [rsp+58h] [rbp-51h] BYREF
  _BYTE v30[32]; // [rsp+78h] [rbp-31h] BYREF
  _BYTE v31[32]; // [rsp+98h] [rbp-11h] BYREF
  _BYTE v32[32]; // [rsp+B8h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  v28 = 0;
  v7 = Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance();
  EnrollmentId = Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::GetEnrollmentId(v7, &v28);
  v9 = EnrollmentId;
  if ( EnrollmentId >= 0 )
  {
    hKey = 0;
    if ( (_QWORD)v28 )
      v10 = *(_QWORD *)v28;
    else
      v10 = 0;
    std::wstring::wstring(v30, v10);
    IsStateSeparationEnabled = RtlIsStateSeparationEnabled();
    v12 = L"OSData\\SOFTWARE\\Microsoft\\EnterpriseResourceManager\\Tracked\\";
    if ( !IsStateSeparationEnabled )
      v12 = L"SOFTWARE\\Microsoft\\EnterpriseResourceManager\\Tracked\\";
    std::operator+<unsigned short>(v29, v12, v30);
    hKey = 0;
    v13 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v29);
    v14 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v13, 0, 0x20019u, &hKey);
    v9 = v14;
    if ( v14 != 2 )
    {
      if ( v14 > 0 )
        v9 = (unsigned __int16)v14 | 0x80070000;
      if ( v9 < 0 )
      {
        v16 = (unsigned int)v9;
        v17 = 63;
LABEL_13:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v17,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\erm.cpp",
          (const char *)v16,
          phkResulta);
LABEL_14:
        std::wstring::_Tidy_deallocate(v29);
        std::wstring::_Tidy_deallocate(v30);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        goto LABEL_24;
      }
      phkResulta = a3;
      v18 = Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::Enumerate(
              v15,
              &hKey,
              L"device\\default",
              a2);
      v9 = v18;
      if ( v18 < 0 )
      {
        v16 = (unsigned int)v18;
        v17 = 66;
        goto LABEL_13;
      }
      v27 = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v27,
        0);
      ActiveUserSid = DmGetActiveUserSid(&v27);
      v9 = ActiveUserSid;
      if ( ActiveUserSid < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x46,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\erm.cpp",
          (const char *)(unsigned int)ActiveUserSid,
          a3);
LABEL_19:
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v27);
        goto LABEL_14;
      }
      std::wstring::wstring(v31, v27);
      v20 = std::operator+<unsigned short>(v32, v31, L"\\default");
      v21 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v20);
      v9 = Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::Enumerate(v22, &hKey, v21, a2);
      std::wstring::_Tidy_deallocate(v32);
      if ( v9 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x48,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\erm.cpp",
          (const char *)(unsigned int)v9,
          a4);
        std::wstring::_Tidy_deallocate(v31);
        goto LABEL_19;
      }
      std::wstring::_Tidy_deallocate(v31);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v27);
    }
    std::wstring::_Tidy_deallocate(v29);
    std::wstring::_Tidy_deallocate(v30);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    v9 = 0;
    goto LABEL_24;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x37,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\erm.cpp",
    (const char *)(unsigned int)EnrollmentId,
    phkResult);
LABEL_24:
  std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(&v28);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18013a39c  push    rbp
0x18013a39e  push    rbx
0x18013a39f  push    rsi
0x18013a3a0  push    rdi
0x18013a3a1  push    r14
0x18013a3a3  lea     rbp, [rsp-37h]
0x18013a3a8  sub     rsp, 0E0h
0x18013a3af  mov     rax, cs:__security_cookie
0x18013a3b6  xor     rax, rsp
0x18013a3b9  mov     [rbp+57h+var_28], rax
0x18013a3bd  mov     r14, r9
0x18013a3c0  mov     rsi, r8
0x18013a3c3  mov     rdi, rdx
0x18013a3c6  xorps   xmm1, xmm1
0x18013a3c9  movdqu  [rbp+57h+var_C0], xmm1
0x18013a3ce  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x18013a3d3  lea     rdx, [rbp+57h+var_C0]
0x18013a3d7  mov     rcx, rax
0x18013a3da  call    ?GetEnrollmentId@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAJAEAV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::GetEnrollmentId(wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>> &)
0x18013a3df  mov     ebx, eax
0x18013a3e1  test    eax, eax
0x18013a3e3  jns     short loc_18013A402
0x18013a3e5  mov     rcx, [rbp+5Fh]; this
0x18013a3e9  mov     r9d, eax; char *
0x18013a3ec  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18013a3f3  mov     edx, 37h ; '7'; void *
0x18013a3f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013a3fd  jmp     loc_18013A629
0x18013a402  mov     [rbp+57h+hKey], 0
0x18013a40a  mov     rax, qword ptr [rbp+57h+var_C0]
0x18013a40e  test    rax, rax
0x18013a411  jz      short loc_18013A418
0x18013a413  mov     rdx, [rax]
0x18013a416  jmp     short loc_18013A41A
0x18013a418  xor     edx, edx
0x18013a41a  lea     rcx, [rbp+57h+var_88]
0x18013a41e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18013a423  nop
0x18013a424  call    cs:__imp_RtlIsStateSeparationEnabled
0x18013a42b  nop     dword ptr [rax+rax+00h]
0x18013a430  lea     rcx, aSoftwareMicros_12; "SOFTWARE\\Microsoft\\EnterpriseResource"...
0x18013a437  lea     rdx, aOsdataSoftware_0; "OSData\\SOFTWARE\\Microsoft\\Enterprise"...
0x18013a43e  test    al, al
0x18013a440  cmovz   rdx, rcx
0x18013a444  lea     r8, [rbp+57h+var_88]
0x18013a448  lea     rcx, [rbp+57h+var_A8]
0x18013a44c  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBGAEBV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring const &)
0x18013a451  nop
0x18013a452  mov     rbx, [rbp+57h+hKey]
0x18013a456  test    rbx, rbx
0x18013a459  jz      short loc_18013A47C
0x18013a45b  lea     rcx, [rbp+57h+var_B0]; this
0x18013a45f  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18013a464  mov     rcx, rbx; hKey
0x18013a467  call    cs:__imp_RegCloseKey
0x18013a46e  nop     dword ptr [rax+rax+00h]
0x18013a473  lea     rcx, [rbp+57h+var_B0]; this
0x18013a477  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18013a47c  mov     [rbp+57h+hKey], 0
0x18013a484  lea     rcx, [rbp+57h+var_A8]
0x18013a488  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18013a48d  mov     rdx, rax; lpSubKey
0x18013a490  lea     rax, [rbp+57h+hKey]
0x18013a494  mov     qword ptr [rsp+100h+phkResult], rax; int
0x18013a499  mov     r9d, 20019h; samDesired
0x18013a49f  xor     r8d, r8d; ulOptions
0x18013a4a2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18013a4a9  call    cs:__imp_RegOpenKeyExW
0x18013a4b0  nop     dword ptr [rax+rax+00h]
0x18013a4b5  mov     ebx, eax
0x18013a4b7  cmp     eax, 2
0x18013a4ba  jz      loc_18013A60A
0x18013a4c0  test    eax, eax
0x18013a4c2  jle     short loc_18013A4CD
0x18013a4c4  movzx   ebx, ax
0x18013a4c7  or      ebx, 80070000h
0x18013a4cd  test    ebx, ebx
0x18013a4cf  jns     short loc_18013A50C
0x18013a4d1  mov     r9d, ebx; char *
0x18013a4d4  mov     edx, 3Fh ; '?'; void *
0x18013a4d9  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18013a4e0  mov     rcx, [rbp+5Fh]; this
0x18013a4e4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013a4e9  nop
0x18013a4ea  lea     rcx, [rbp+57h+var_A8]
0x18013a4ee  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013a4f3  nop
0x18013a4f4  lea     rcx, [rbp+57h+var_88]
0x18013a4f8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013a4fd  nop
0x18013a4fe  lea     rcx, [rbp+57h+hKey]
0x18013a502  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18013a507  jmp     loc_18013A629
0x18013a50c  mov     qword ptr [rsp+100h+phkResult], rsi; int
0x18013a511  mov     r9, rdi
0x18013a514  lea     r8, aDeviceDefault; "device\\default"
0x18013a51b  lea     rdx, [rbp+57h+hKey]
0x18013a51f  call    ?Enumerate@ProvisionedResources@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEBG1AEAV?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::Enumerate(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,ushort const *,ushort const *,std::list<std::wstring> &)
0x18013a524  mov     ebx, eax
0x18013a526  test    eax, eax
0x18013a528  jns     short loc_18013A534
0x18013a52a  mov     r9d, eax
0x18013a52d  mov     edx, 42h ; 'B'
0x18013a532  jmp     short loc_18013A4D9
0x18013a534  mov     [rbp+57h+var_C8], 0
0x18013a53c  xor     edx, edx
0x18013a53e  lea     rcx, [rbp+57h+var_C8]
0x18013a542  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18013a547  lea     rcx, [rbp+57h+var_C8]
0x18013a54b  call    cs:__imp_?DmGetActiveUserSid@@YAJPEAPEAG@Z; DmGetActiveUserSid(ushort * *)
0x18013a552  nop     dword ptr [rax+rax+00h]
0x18013a557  mov     ebx, eax
0x18013a559  test    eax, eax
0x18013a55b  jns     short loc_18013A584
0x18013a55d  mov     rcx, [rbp+5Fh]; this
0x18013a561  mov     r9d, eax; char *
0x18013a564  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18013a56b  mov     edx, 46h ; 'F'; void *
0x18013a570  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013a575  nop
0x18013a576  lea     rcx, [rbp+57h+var_C8]
0x18013a57a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18013a57f  jmp     loc_18013A4EA
0x18013a584  mov     rdx, [rbp+57h+var_C8]
0x18013a588  lea     rcx, [rbp+57h+var_68]
0x18013a58c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18013a591  nop
0x18013a592  lea     r8, aDefault; "\\default"
0x18013a599  lea     rdx, [rbp+57h+var_68]
0x18013a59d  lea     rcx, [rbp+57h+var_48]
0x18013a5a1  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x18013a5a6  nop
0x18013a5a7  mov     rcx, rax
0x18013a5aa  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18013a5af  mov     qword ptr [rsp+100h+phkResult], r14; int
0x18013a5b4  mov     r9, rdi
0x18013a5b7  mov     r8, rax
0x18013a5ba  lea     rdx, [rbp+57h+hKey]
0x18013a5be  call    ?Enumerate@ProvisionedResources@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEBG1AEAV?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::Enumerate(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,ushort const *,ushort const *,std::list<std::wstring> &)
0x18013a5c3  mov     ebx, eax
0x18013a5c5  lea     rcx, [rbp+57h+var_48]
0x18013a5c9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013a5ce  test    ebx, ebx
0x18013a5d0  jns     short loc_18013A5F6
0x18013a5d2  mov     rcx, [rbp+5Fh]; this
0x18013a5d6  mov     r9d, ebx; char *
0x18013a5d9  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18013a5e0  mov     edx, 48h ; 'H'; void *
0x18013a5e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013a5ea  nop
0x18013a5eb  lea     rcx, [rbp+57h+var_68]
0x18013a5ef  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013a5f4  jmp     short loc_18013A576
0x18013a5f6  lea     rcx, [rbp+57h+var_68]
0x18013a5fa  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013a5ff  nop
0x18013a600  lea     rcx, [rbp+57h+var_C8]
0x18013a604  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18013a609  nop
0x18013a60a  lea     rcx, [rbp+57h+var_A8]
0x18013a60e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013a613  nop
0x18013a614  lea     rcx, [rbp+57h+var_88]
0x18013a618  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013a61d  nop
0x18013a61e  lea     rcx, [rbp+57h+hKey]
0x18013a622  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18013a627  xor     ebx, ebx
0x18013a629  lea     rcx, [rbp+57h+var_C0]
0x18013a62d  call    ??1?$shared_ptr@VRedirectedPolicies@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@QEAA@XZ; std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(void)
0x18013a632  mov     eax, ebx
0x18013a634  mov     rcx, [rbp+57h+var_28]
0x18013a638  xor     rcx, rsp; StackCookie
0x18013a63b  call    __security_check_cookie
0x18013a640  add     rsp, 0E0h
0x18013a647  pop     r14
0x18013a649  pop     rdi
0x18013a64a  pop     rsi
0x18013a64b  pop     rbx
0x18013a64c  pop     rbp
0x18013a64d  retn
```
