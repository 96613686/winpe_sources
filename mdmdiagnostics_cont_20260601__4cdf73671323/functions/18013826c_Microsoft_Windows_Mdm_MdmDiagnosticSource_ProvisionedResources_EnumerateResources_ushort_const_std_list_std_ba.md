# Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::EnumerateResources(ushort const *,std::list<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &,std::list<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &)

- ea: `0x18013826c`
- end: `0x180138506`
- name: `?EnumerateResources@ProvisionedResources@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAJPEBGAEAV?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@1@Z`
- size: `666`
- prototype: ``
- caller_count: `4`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18012afd8`
- `0x18012fa78`
- `0x180132118`
- `0x1801326ec`

## callees

- `0x180019000`
- `0x1800e66dc`
- `0x1800e7124`
- `0x1800e7c08`
- `0x1800e82e4`
- `0x1800ece5c`
- `0x1800ee878`
- `0x1800ef188`
- `0x1800ef5d8`
- `0x1800f8a0c`
- `0x1800f8aa0`
- `0x1800f9558`
- `0x1800f9a0c`
- `0x18010440c`
- `0x180128e28`
- `0x180137cd0`
- `0x18013826c`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x1801382f4`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1801382f4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18013836d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18013836d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180138331`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180138331`
- `DMCmnUtils!DmGetActiveUserSid` at `0x180138409`
- `DMCmnUtils!DmGetActiveUserSid` at `0x180138409`

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
0x18013826c  push    rbp
0x18013826e  push    rbx
0x18013826f  push    rsi
0x180138270  push    rdi
0x180138271  push    r14
0x180138273  lea     rbp, [rsp-37h]
0x180138278  sub     rsp, 0E0h
0x18013827f  mov     rax, cs:__security_cookie
0x180138286  xor     rax, rsp
0x180138289  mov     [rbp+57h+var_28], rax
0x18013828d  mov     r14, r9
0x180138290  mov     rsi, r8
0x180138293  mov     rdi, rdx
0x180138296  xorps   xmm1, xmm1
0x180138299  movdqu  [rbp+57h+var_C0], xmm1
0x18013829e  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x1801382a3  lea     rdx, [rbp+57h+var_C0]
0x1801382a7  mov     rcx, rax
0x1801382aa  call    ?GetEnrollmentId@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAJAEAV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::GetEnrollmentId(wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>> &)
0x1801382af  mov     ebx, eax
0x1801382b1  test    eax, eax
0x1801382b3  jns     short loc_1801382D2
0x1801382b5  mov     rcx, [rbp+5Fh]; this
0x1801382b9  mov     r9d, eax; char *
0x1801382bc  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1801382c3  mov     edx, 37h ; '7'; void *
0x1801382c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801382cd  jmp     loc_1801384E1
0x1801382d2  mov     [rbp+57h+hKey], 0
0x1801382da  mov     rax, qword ptr [rbp+57h+var_C0]
0x1801382de  test    rax, rax
0x1801382e1  jz      short loc_1801382E8
0x1801382e3  mov     rdx, [rax]
0x1801382e6  jmp     short loc_1801382EA
0x1801382e8  xor     edx, edx
0x1801382ea  lea     rcx, [rbp+57h+var_88]
0x1801382ee  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1801382f3  nop
0x1801382f4  call    cs:__imp_RtlIsStateSeparationEnabled
0x1801382fa  lea     rcx, aSoftwareMicros_12; "SOFTWARE\\Microsoft\\EnterpriseResource"...
0x180138301  lea     rdx, aOsdataSoftware_0; "OSData\\SOFTWARE\\Microsoft\\Enterprise"...
0x180138308  test    al, al
0x18013830a  cmovz   rdx, rcx
0x18013830e  lea     r8, [rbp+57h+var_88]
0x180138312  lea     rcx, [rbp+57h+var_A8]
0x180138316  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBGAEBV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring const &)
0x18013831b  nop
0x18013831c  mov     rbx, [rbp+57h+hKey]
0x180138320  test    rbx, rbx
0x180138323  jz      short loc_180138340
0x180138325  lea     rcx, [rbp+57h+var_B0]; this
0x180138329  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18013832e  mov     rcx, rbx; hKey
0x180138331  call    cs:__imp_RegCloseKey
0x180138337  lea     rcx, [rbp+57h+var_B0]; this
0x18013833b  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180138340  mov     [rbp+57h+hKey], 0
0x180138348  lea     rcx, [rbp+57h+var_A8]
0x18013834c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180138351  mov     rdx, rax; lpSubKey
0x180138354  lea     rax, [rbp+57h+hKey]
0x180138358  mov     qword ptr [rsp+100h+phkResult], rax; int
0x18013835d  mov     r9d, 20019h; samDesired
0x180138363  xor     r8d, r8d; ulOptions
0x180138366  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18013836d  call    cs:__imp_RegOpenKeyExW
0x180138373  mov     ebx, eax
0x180138375  cmp     eax, 2
0x180138378  jz      loc_1801384C2
0x18013837e  test    eax, eax
0x180138380  jle     short loc_18013838B
0x180138382  movzx   ebx, ax
0x180138385  or      ebx, 80070000h
0x18013838b  test    ebx, ebx
0x18013838d  jns     short loc_1801383CA
0x18013838f  mov     r9d, ebx; char *
0x180138392  mov     edx, 3Fh ; '?'; void *
0x180138397  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18013839e  mov     rcx, [rbp+5Fh]; this
0x1801383a2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801383a7  nop
0x1801383a8  lea     rcx, [rbp+57h+var_A8]
0x1801383ac  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801383b1  nop
0x1801383b2  lea     rcx, [rbp+57h+var_88]
0x1801383b6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801383bb  nop
0x1801383bc  lea     rcx, [rbp+57h+hKey]
0x1801383c0  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801383c5  jmp     loc_1801384E1
0x1801383ca  mov     qword ptr [rsp+100h+phkResult], rsi; int
0x1801383cf  mov     r9, rdi
0x1801383d2  lea     r8, aDeviceDefault; "device\\default"
0x1801383d9  lea     rdx, [rbp+57h+hKey]
0x1801383dd  call    ?Enumerate@ProvisionedResources@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEBG1AEAV?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::Enumerate(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,ushort const *,ushort const *,std::list<std::wstring> &)
0x1801383e2  mov     ebx, eax
0x1801383e4  test    eax, eax
0x1801383e6  jns     short loc_1801383F2
0x1801383e8  mov     r9d, eax
0x1801383eb  mov     edx, 42h ; 'B'
0x1801383f0  jmp     short loc_180138397
0x1801383f2  mov     [rbp+57h+var_C8], 0
0x1801383fa  xor     edx, edx
0x1801383fc  lea     rcx, [rbp+57h+var_C8]
0x180138400  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180138405  lea     rcx, [rbp+57h+var_C8]
0x180138409  call    cs:__imp_?DmGetActiveUserSid@@YAJPEAPEAG@Z; DmGetActiveUserSid(ushort * *)
0x18013840f  mov     ebx, eax
0x180138411  test    eax, eax
0x180138413  jns     short loc_18013843C
0x180138415  mov     rcx, [rbp+5Fh]; this
0x180138419  mov     r9d, eax; char *
0x18013841c  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180138423  mov     edx, 46h ; 'F'; void *
0x180138428  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013842d  nop
0x18013842e  lea     rcx, [rbp+57h+var_C8]
0x180138432  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180138437  jmp     loc_1801383A8
0x18013843c  mov     rdx, [rbp+57h+var_C8]
0x180138440  lea     rcx, [rbp+57h+var_68]
0x180138444  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180138449  nop
0x18013844a  lea     r8, aDefault; "\\default"
0x180138451  lea     rdx, [rbp+57h+var_68]
0x180138455  lea     rcx, [rbp+57h+var_48]
0x180138459  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x18013845e  nop
0x18013845f  mov     rcx, rax
0x180138462  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180138467  mov     qword ptr [rsp+100h+phkResult], r14; int
0x18013846c  mov     r9, rdi
0x18013846f  mov     r8, rax
0x180138472  lea     rdx, [rbp+57h+hKey]
0x180138476  call    ?Enumerate@ProvisionedResources@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEBG1AEAV?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::Enumerate(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,ushort const *,ushort const *,std::list<std::wstring> &)
0x18013847b  mov     ebx, eax
0x18013847d  lea     rcx, [rbp+57h+var_48]
0x180138481  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180138486  test    ebx, ebx
0x180138488  jns     short loc_1801384AE
0x18013848a  mov     rcx, [rbp+5Fh]; this
0x18013848e  mov     r9d, ebx; char *
0x180138491  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180138498  mov     edx, 48h ; 'H'; void *
0x18013849d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801384a2  nop
0x1801384a3  lea     rcx, [rbp+57h+var_68]
0x1801384a7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801384ac  jmp     short loc_18013842E
0x1801384ae  lea     rcx, [rbp+57h+var_68]
0x1801384b2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801384b7  nop
0x1801384b8  lea     rcx, [rbp+57h+var_C8]
0x1801384bc  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1801384c1  nop
0x1801384c2  lea     rcx, [rbp+57h+var_A8]
0x1801384c6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801384cb  nop
0x1801384cc  lea     rcx, [rbp+57h+var_88]
0x1801384d0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801384d5  nop
0x1801384d6  lea     rcx, [rbp+57h+hKey]
0x1801384da  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801384df  xor     ebx, ebx
0x1801384e1  lea     rcx, [rbp+57h+var_C0]
0x1801384e5  call    ??1?$shared_ptr@VRedirectedPolicies@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@QEAA@XZ; std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(void)
0x1801384ea  mov     eax, ebx
0x1801384ec  mov     rcx, [rbp+57h+var_28]
0x1801384f0  xor     rcx, rsp; StackCookie
0x1801384f3  call    __security_check_cookie
0x1801384f8  add     rsp, 0E0h
0x1801384ff  pop     r14
0x180138501  pop     rdi
0x180138502  pop     rsi
0x180138503  pop     rbx
0x180138504  pop     rbp
0x180138505  retn
```
