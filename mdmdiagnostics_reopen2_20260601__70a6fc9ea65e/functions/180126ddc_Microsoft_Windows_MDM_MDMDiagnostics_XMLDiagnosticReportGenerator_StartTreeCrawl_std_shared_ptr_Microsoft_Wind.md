# Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::StartTreeCrawl(std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>)

- ea: `0x180126ddc`
- end: `0x180127086`
- name: `?StartTreeCrawl@XMLDiagnosticReportGenerator@MDMDiagnostics@MDM@Windows@Microsoft@@AEAAJV?$shared_ptr@VDiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@@std@@@Z`
- size: `682`
- prototype: `__int64 __fastcall(Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator *this)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180126680`

## callees

- `0x180019080`
- `0x18001a054`
- `0x1800e6b14`
- `0x1800e734c`
- `0x1800e7de8`
- `0x1800e8508`
- `0x1800ed46c`
- `0x1800edd28`
- `0x1800eef28`
- `0x180105744`
- `0x18012680c`
- `0x180126b3c`
- `0x180126ddc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180126ea5`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180126f46`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180126f69`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180126ea5`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180126f46`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180126f69`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180126ed4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180126ed4`
- `DMCmnUtils!OmaDmRegistryRetrieveCurrentUsersHKCU` at `0x180126efd`
- `DMCmnUtils!OmaDmRegistryRetrieveCurrentUsersHKCU` at `0x180126efd`

## string_xrefs

- `0x180126f1e`: `Impersonation Failure`
- `0x180126e59`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\registrytoxml\xmldiagnosticreportgenerator.cpp`
- `0x180126fbf`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\registrytoxml\xmldiagnosticreportgenerator.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::StartTreeCrawl(
        Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator *this,
        __int64 a2)
{
  int v4; // eax
  unsigned int v5; // edi
  std::_Ref_count_base *v6; // rcx
  int v8; // eax
  __int64 v9; // rcx
  int CurrentKeyData; // eax
  unsigned int v11; // esi
  __int64 v12; // rdx
  std::_Ref_count_base *v13; // rcx
  int ChildKeyData; // eax
  std::_Ref_count_base *v15; // rcx
  HKEY hKey; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v17; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE v18[16]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v19; // [rsp+40h] [rbp-C0h]
  wchar_t Str[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  v19 = a2;
  v17 = 0;
  hKey = 0;
  memset_0(Str, 0, 0x208u);
  v4 = StringCchCopyW(Str, 0x103u, *(const unsigned __int16 **)a2);
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x47,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\registrytoxml\\xmldiagnosticreportgenerator.cpp",
      (const char *)(unsigned int)v4,
      (int)hKey);
LABEL_3:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v17);
    v6 = *(std::_Ref_count_base **)(a2 + 8);
    if ( v6 )
      std::_Ref_count_base::_Decref(v6);
    return v5;
  }
  if ( wcsstr(Str, L"HKCU") )
  {
    hKey = 0;
    v8 = OmaDmRegistryRetrieveCurrentUsersHKCU(0x20019u, &hKey);
    if ( v8 < 0 && (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 8) != 0 )
      McTemplateU0zd_EventWriteTransfer(
        v9,
        EnterpriseDiagnosticsMdmDiagnosticsGetDiagnosticsDataFailure,
        L"Impersonation Failure",
        (unsigned int)v8);
  }
  else
  {
    wcsstr(Str, L"HKUS");
  }
  if ( wcsstr(Str, L"\\*") )
  {
    std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>(
      v18,
      a2);
    ChildKeyData = Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::GetChildKeyData(this);
    v11 = ChildKeyData;
    if ( ChildKeyData < 0 )
    {
      v5 = -2147024894;
      if ( ChildKeyData == -2147024894 )
        goto LABEL_3;
      v12 = 100;
LABEL_15:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v12,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\registrytoxml\\xmldiagnosticreportgenerator.cpp",
        (const char *)v11,
        (int)hKey);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v17);
      v13 = *(std::_Ref_count_base **)(a2 + 8);
      if ( v13 )
        std::_Ref_count_base::_Decref(v13);
      return v11;
    }
  }
  else
  {
    std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>(
      v18,
      a2);
    CurrentKeyData = Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::GetCurrentKeyData(this);
    v11 = CurrentKeyData;
    if ( CurrentKeyData < 0 )
    {
      v5 = -2147024894;
      if ( CurrentKeyData == -2147024894 )
        goto LABEL_3;
      v12 = 96;
      goto LABEL_15;
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v17);
  v15 = *(std::_Ref_count_base **)(a2 + 8);
  if ( v15 )
    std::_Ref_count_base::_Decref(v15);
  return 0;
}

```

## disassembly

```asm
0x180126ddc  mov     [rsp-8+arg_10], rbx
0x180126de1  push    rbp
0x180126de2  push    rsi
0x180126de3  push    rdi
0x180126de4  push    r14
0x180126de6  push    r15
0x180126de8  lea     rbp, [rsp-170h]
0x180126df0  sub     rsp, 270h
0x180126df7  mov     rax, cs:__security_cookie
0x180126dfe  xor     rax, rsp
0x180126e01  mov     [rbp+190h+var_30], rax
0x180126e08  mov     rbx, rdx
0x180126e0b  mov     r15, rcx
0x180126e0e  mov     [rsp+290h+var_250], rdx
0x180126e13  mov     [rsp+290h+var_268], 0
0x180126e1c  mov     [rsp+290h+hKey], 0; int
0x180126e25  xor     edx, edx; Val
0x180126e27  mov     r8d, 208h; Size
0x180126e2d  lea     rcx, [rsp+290h+Str]; void *
0x180126e32  call    memset_0
0x180126e37  mov     r8, [rbx]; unsigned __int16 *
0x180126e3a  mov     edx, 103h; unsigned __int64
0x180126e3f  lea     rcx, [rsp+290h+Str]; unsigned __int16 *
0x180126e44  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180126e49  mov     edi, eax
0x180126e4b  test    eax, eax
0x180126e4d  jns     short loc_180126E96
0x180126e4f  mov     rcx, [rbp+198h]; this
0x180126e56  mov     r9d, eax; char *
0x180126e59  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180126e60  mov     edx, 47h ; 'G'; void *
0x180126e65  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180126e6a  nop
0x180126e6b  lea     rcx, [rsp+290h+hKey]
0x180126e70  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180126e75  nop
0x180126e76  lea     rcx, [rsp+290h+var_268]
0x180126e7b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180126e80  nop
0x180126e81  mov     rcx, [rbx+8]; this
0x180126e85  test    rcx, rcx
0x180126e88  jz      short loc_180126E8F
0x180126e8a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180126e8f  mov     eax, edi
0x180126e91  jmp     loc_18012705F
0x180126e96  xor     r14b, r14b
0x180126e99  lea     rdx, aHkcu; "HKCU"
0x180126ea0  lea     rcx, [rsp+290h+Str]; Str
0x180126ea5  call    cs:__imp_wcsstr
0x180126eac  nop     dword ptr [rax+rax+00h]
0x180126eb1  test    rax, rax
0x180126eb4  jz      short loc_180126F33
0x180126eb6  mov     rdi, 0FFFFFFFF80000001h
0x180126ebd  mov     rsi, [rsp+290h+hKey]
0x180126ec2  test    rsi, rsi
0x180126ec5  jz      short loc_180126EEA
0x180126ec7  lea     rcx, [rsp+290h+var_260]; this
0x180126ecc  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180126ed1  mov     rcx, rsi; hKey
0x180126ed4  call    cs:__imp_RegCloseKey
0x180126edb  nop     dword ptr [rax+rax+00h]
0x180126ee0  lea     rcx, [rsp+290h+var_260]; this
0x180126ee5  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180126eea  mov     [rsp+290h+hKey], 0
0x180126ef3  lea     rdx, [rsp+290h+hKey]
0x180126ef8  mov     ecx, 20019h
0x180126efd  call    cs:__imp_?OmaDmRegistryRetrieveCurrentUsersHKCU@@YAJKPEAPEAUHKEY__@@@Z; OmaDmRegistryRetrieveCurrentUsersHKCU(ulong,HKEY__ * *)
0x180126f04  nop     dword ptr [rax+rax+00h]
0x180126f09  test    eax, eax
0x180126f0b  js      short loc_180126F12
0x180126f0d  mov     r14b, 1
0x180126f10  jmp     short loc_180126F5D
0x180126f12  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 8
0x180126f19  jz      short loc_180126F5D
0x180126f1b  mov     r9d, eax
0x180126f1e  lea     r8, aImpersonationF; "Impersonation Failure"
0x180126f25  lea     rdx, EnterpriseDiagnosticsMdmDiagnosticsGetDiagnosticsDataFailure
0x180126f2c  call    McTemplateU0zd_EventWriteTransfer
0x180126f31  jmp     short loc_180126F5D
0x180126f33  mov     rdi, 0FFFFFFFF80000002h
0x180126f3a  lea     rdx, aHkus; "HKUS"
0x180126f41  lea     rcx, [rsp+290h+Str]; Str
0x180126f46  call    cs:__imp_wcsstr
0x180126f4d  nop     dword ptr [rax+rax+00h]
0x180126f52  lea     rcx, [rdi+1]
0x180126f56  test    rax, rax
0x180126f59  cmovnz  rdi, rcx
0x180126f5d  lea     rdx, asc_1801D5540; "\\*"
0x180126f64  lea     rcx, [rsp+290h+Str]; Str
0x180126f69  call    cs:__imp_wcsstr
0x180126f70  nop     dword ptr [rax+rax+00h]
0x180126f75  mov     rdx, rbx
0x180126f78  lea     rcx, [rsp+290h+var_260]
0x180126f7d  test    rax, rax
0x180126f80  jnz     short loc_180126FFE
0x180126f82  test    r14b, r14b
0x180126f85  cmovnz  rdi, [rsp+290h+hKey]
0x180126f8b  call    ??0?$shared_ptr@VDiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>(std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey> const &)
0x180126f90  lea     r9, [rsp+290h+Str]
0x180126f95  mov     r8, rdi
0x180126f98  mov     rdx, rax
0x180126f9b  mov     rcx, r15; this
0x180126f9e  call    ?GetCurrentKeyData@XMLDiagnosticReportGenerator@MDMDiagnostics@MDM@Windows@Microsoft@@AEAAJV?$shared_ptr@VDiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@@std@@PEAUHKEY__@@PEAG@Z; Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::GetCurrentKeyData(std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>,HKEY__ *,ushort *)
0x180126fa3  mov     esi, eax
0x180126fa5  test    eax, eax
0x180126fa7  jns     loc_180127039
0x180126fad  mov     edi, 80070002h
0x180126fb2  cmp     eax, edi
0x180126fb4  jz      loc_180126E6B
0x180126fba  mov     edx, 60h ; '`'; void *
0x180126fbf  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180126fc6  mov     r9d, esi; char *
0x180126fc9  mov     rcx, [rbp+198h]; this
0x180126fd0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180126fd5  nop
0x180126fd6  lea     rcx, [rsp+290h+hKey]
0x180126fdb  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180126fe0  nop
0x180126fe1  lea     rcx, [rsp+290h+var_268]
0x180126fe6  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180126feb  nop
0x180126fec  mov     rcx, [rbx+8]; this
0x180126ff0  test    rcx, rcx
0x180126ff3  jz      short loc_180126FFA
0x180126ff5  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180126ffa  mov     eax, esi
0x180126ffc  jmp     short loc_18012705F
0x180126ffe  test    r14b, r14b
0x180127001  cmovnz  rdi, [rsp+290h+hKey]
0x180127007  call    ??0?$shared_ptr@VDiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>(std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey> const &)
0x18012700c  lea     r9, [rsp+290h+Str]
0x180127011  mov     r8, rdi
0x180127014  mov     rdx, rax
0x180127017  mov     rcx, r15; this
0x18012701a  call    ?GetChildKeyData@XMLDiagnosticReportGenerator@MDMDiagnostics@MDM@Windows@Microsoft@@AEAAJV?$shared_ptr@VDiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@@std@@PEAUHKEY__@@PEAG@Z; Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::GetChildKeyData(std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>,HKEY__ *,ushort *)
0x18012701f  mov     esi, eax
0x180127021  test    eax, eax
0x180127023  jns     short loc_180127039
0x180127025  mov     edi, 80070002h
0x18012702a  cmp     eax, edi
0x18012702c  jz      loc_180126E6B
0x180127032  mov     edx, 64h ; 'd'
0x180127037  jmp     short loc_180126FBF
0x180127039  lea     rcx, [rsp+290h+hKey]
0x18012703e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180127043  nop
0x180127044  lea     rcx, [rsp+290h+var_268]
0x180127049  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18012704e  nop
0x18012704f  mov     rcx, [rbx+8]; this
0x180127053  test    rcx, rcx
0x180127056  jz      short loc_18012705D
0x180127058  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18012705d  xor     eax, eax
0x18012705f  mov     rcx, [rbp+190h+var_30]
0x180127066  xor     rcx, rsp; StackCookie
0x180127069  call    __security_check_cookie
0x18012706e  mov     rbx, [rsp+290h+arg_10]
0x180127076  add     rsp, 270h
0x18012707d  pop     r15
0x18012707f  pop     r14
0x180127081  pop     rdi
0x180127082  pop     rsi
0x180127083  pop     rbp
0x180127084  retn
```
