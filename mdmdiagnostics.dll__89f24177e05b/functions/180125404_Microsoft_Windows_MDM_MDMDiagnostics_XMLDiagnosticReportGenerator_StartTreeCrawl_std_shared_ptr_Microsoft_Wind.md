# Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::StartTreeCrawl(std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>)

- ea: `0x180125404`
- end: `0x18012568f`
- name: `?StartTreeCrawl@XMLDiagnosticReportGenerator@MDMDiagnostics@MDM@Windows@Microsoft@@AEAAJV?$shared_ptr@VDiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@@std@@@Z`
- size: `651`
- prototype: `__int64 __fastcall(Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator *this)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180124cd0`

## callees

- `0x180019000`
- `0x180019fc4`
- `0x1800e691c`
- `0x1800e7124`
- `0x1800e7c08`
- `0x1800e82e4`
- `0x1800ece5c`
- `0x1800ed6e4`
- `0x1800ee898`
- `0x18010450c`
- `0x180124e58`
- `0x180125170`
- `0x180125404`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1801254cd`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18012555c`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180125579`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1801254cd`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18012555c`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180125579`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801254f6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801254f6`
- `DMCmnUtils!OmaDmRegistryRetrieveCurrentUsersHKCU` at `0x180125519`
- `DMCmnUtils!OmaDmRegistryRetrieveCurrentUsersHKCU` at `0x180125519`

## string_xrefs

- `0x180125534`: `Impersonation Failure`
- `0x180125481`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\registrytoxml\xmldiagnosticreportgenerator.cpp`
- `0x1801255c9`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\registrytoxml\xmldiagnosticreportgenerator.cpp`

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
  char v8; // r14
  __int64 v9; // rdi
  int v10; // eax
  __int64 v11; // rcx
  int CurrentKeyData; // eax
  unsigned int v13; // esi
  __int64 v14; // rdx
  std::_Ref_count_base *v15; // rcx
  __int64 v16; // rax
  int ChildKeyData; // eax
  std::_Ref_count_base *v18; // rcx
  HKEY hKey; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v20; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE v21[16]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v22; // [rsp+40h] [rbp-C0h]
  wchar_t Str[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  v22 = a2;
  v20 = 0;
  hKey = 0;
  memset_0(Str, 0, 0x208u);
  v4 = StringCchCopyW(Str, 0x103u, *(const unsigned __int16 **)a2);
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x48,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\registrytoxml\\xmldiagnosticreportgenerator.cpp",
      (const char *)(unsigned int)v4,
      (int)hKey);
LABEL_3:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v20);
    v6 = *(std::_Ref_count_base **)(a2 + 8);
    if ( v6 )
      std::_Ref_count_base::_Decref(v6);
    return v5;
  }
  v8 = 0;
  if ( wcsstr(Str, L"HKCU") )
  {
    v9 = -2147483647;
    hKey = 0;
    v10 = OmaDmRegistryRetrieveCurrentUsersHKCU(0x20019u, &hKey);
    if ( v10 < 0 )
    {
      if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 8) != 0 )
        McTemplateU0zd_EventWriteTransfer(
          v11,
          EnterpriseDiagnosticsMdmDiagnosticsGetDiagnosticsDataFailure,
          L"Impersonation Failure",
          (unsigned int)v10);
    }
    else
    {
      v8 = 1;
    }
  }
  else
  {
    v9 = -2147483646;
    if ( wcsstr(Str, L"HKUS") )
      v9 = -2147483645;
  }
  if ( wcsstr(Str, L"\\*") )
  {
    if ( v8 )
      v9 = (__int64)hKey;
    v16 = std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>(
            v21,
            a2);
    ChildKeyData = Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::GetChildKeyData(
                     this,
                     v16,
                     (HKEY)v9,
                     Str);
    v13 = ChildKeyData;
    if ( ChildKeyData < 0 )
    {
      v5 = -2147024894;
      if ( ChildKeyData == -2147024894 )
        goto LABEL_3;
      v14 = 101;
LABEL_17:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v14,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\registrytoxml\\xmldiagnosticreportgenerator.cpp",
        (const char *)v13,
        (int)hKey);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v20);
      v15 = *(std::_Ref_count_base **)(a2 + 8);
      if ( v15 )
        std::_Ref_count_base::_Decref(v15);
      return v13;
    }
  }
  else
  {
    std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>(
      v21,
      a2);
    CurrentKeyData = Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::GetCurrentKeyData(this);
    v13 = CurrentKeyData;
    if ( CurrentKeyData < 0 )
    {
      v5 = -2147024894;
      if ( CurrentKeyData == -2147024894 )
        goto LABEL_3;
      v14 = 97;
      goto LABEL_17;
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v20);
  v18 = *(std::_Ref_count_base **)(a2 + 8);
  if ( v18 )
    std::_Ref_count_base::_Decref(v18);
  return 0;
}

```

## disassembly

```asm
0x180125404  mov     [rsp-8+arg_10], rbx
0x180125409  push    rbp
0x18012540a  push    rsi
0x18012540b  push    rdi
0x18012540c  push    r14
0x18012540e  push    r15
0x180125410  lea     rbp, [rsp-170h]
0x180125418  sub     rsp, 270h
0x18012541f  mov     rax, cs:__security_cookie
0x180125426  xor     rax, rsp
0x180125429  mov     [rbp+190h+var_30], rax
0x180125430  mov     rbx, rdx
0x180125433  mov     r15, rcx
0x180125436  mov     [rsp+290h+var_250], rdx
0x18012543b  mov     [rsp+290h+var_268], 0
0x180125444  mov     [rsp+290h+hKey], 0; int
0x18012544d  xor     edx, edx; Val
0x18012544f  mov     r8d, 208h; Size
0x180125455  lea     rcx, [rsp+290h+Str]; void *
0x18012545a  call    memset_0
0x18012545f  mov     r8, [rbx]; unsigned __int16 *
0x180125462  mov     edx, 103h; unsigned __int64
0x180125467  lea     rcx, [rsp+290h+Str]; unsigned __int16 *
0x18012546c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180125471  mov     edi, eax
0x180125473  test    eax, eax
0x180125475  jns     short loc_1801254BE
0x180125477  mov     rcx, [rbp+198h]; this
0x18012547e  mov     r9d, eax; char *
0x180125481  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180125488  mov     edx, 48h ; 'H'; void *
0x18012548d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180125492  nop
0x180125493  lea     rcx, [rsp+290h+hKey]
0x180125498  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18012549d  nop
0x18012549e  lea     rcx, [rsp+290h+var_268]
0x1801254a3  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801254a8  nop
0x1801254a9  mov     rcx, [rbx+8]; this
0x1801254ad  test    rcx, rcx
0x1801254b0  jz      short loc_1801254B7
0x1801254b2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801254b7  mov     eax, edi
0x1801254b9  jmp     loc_180125669
0x1801254be  xor     r14b, r14b
0x1801254c1  lea     rdx, aHkcu; "HKCU"
0x1801254c8  lea     rcx, [rsp+290h+Str]; Str
0x1801254cd  call    cs:__imp_wcsstr
0x1801254d3  test    rax, rax
0x1801254d6  jz      short loc_180125549
0x1801254d8  mov     rdi, 0FFFFFFFF80000001h
0x1801254df  mov     rsi, [rsp+290h+hKey]
0x1801254e4  test    rsi, rsi
0x1801254e7  jz      short loc_180125506
0x1801254e9  lea     rcx, [rsp+290h+var_260]; this
0x1801254ee  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1801254f3  mov     rcx, rsi; hKey
0x1801254f6  call    cs:__imp_RegCloseKey
0x1801254fc  lea     rcx, [rsp+290h+var_260]; this
0x180125501  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180125506  mov     [rsp+290h+hKey], 0
0x18012550f  lea     rdx, [rsp+290h+hKey]
0x180125514  mov     ecx, 20019h
0x180125519  call    cs:__imp_?OmaDmRegistryRetrieveCurrentUsersHKCU@@YAJKPEAPEAUHKEY__@@@Z; OmaDmRegistryRetrieveCurrentUsersHKCU(ulong,HKEY__ * *)
0x18012551f  test    eax, eax
0x180125521  js      short loc_180125528
0x180125523  mov     r14b, 1
0x180125526  jmp     short loc_18012556D
0x180125528  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 8
0x18012552f  jz      short loc_18012556D
0x180125531  mov     r9d, eax
0x180125534  lea     r8, aImpersonationF; "Impersonation Failure"
0x18012553b  lea     rdx, EnterpriseDiagnosticsMdmDiagnosticsGetDiagnosticsDataFailure
0x180125542  call    McTemplateU0zd_EventWriteTransfer
0x180125547  jmp     short loc_18012556D
0x180125549  mov     rdi, 0FFFFFFFF80000002h
0x180125550  lea     rdx, aHkus; "HKUS"
0x180125557  lea     rcx, [rsp+290h+Str]; Str
0x18012555c  call    cs:__imp_wcsstr
0x180125562  lea     rcx, [rdi+1]
0x180125566  test    rax, rax
0x180125569  cmovnz  rdi, rcx
0x18012556d  lea     rdx, asc_1801D3550; "\\*"
0x180125574  lea     rcx, [rsp+290h+Str]; Str
0x180125579  call    cs:__imp_wcsstr
0x18012557f  mov     rdx, rbx
0x180125582  lea     rcx, [rsp+290h+var_260]
0x180125587  test    rax, rax
0x18012558a  jnz     short loc_180125608
0x18012558c  test    r14b, r14b
0x18012558f  cmovnz  rdi, [rsp+290h+hKey]
0x180125595  call    ??0?$shared_ptr@VDiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>(std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey> const &)
0x18012559a  lea     r9, [rsp+290h+Str]
0x18012559f  mov     r8, rdi
0x1801255a2  mov     rdx, rax
0x1801255a5  mov     rcx, r15; this
0x1801255a8  call    ?GetCurrentKeyData@XMLDiagnosticReportGenerator@MDMDiagnostics@MDM@Windows@Microsoft@@AEAAJV?$shared_ptr@VDiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@@std@@PEAUHKEY__@@PEAG@Z; Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::GetCurrentKeyData(std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>,HKEY__ *,ushort *)
0x1801255ad  mov     esi, eax
0x1801255af  test    eax, eax
0x1801255b1  jns     loc_180125643
0x1801255b7  mov     edi, 80070002h
0x1801255bc  cmp     eax, edi
0x1801255be  jz      loc_180125493
0x1801255c4  mov     edx, 61h ; 'a'; void *
0x1801255c9  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1801255d0  mov     r9d, esi; char *
0x1801255d3  mov     rcx, [rbp+198h]; this
0x1801255da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801255df  nop
0x1801255e0  lea     rcx, [rsp+290h+hKey]
0x1801255e5  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801255ea  nop
0x1801255eb  lea     rcx, [rsp+290h+var_268]
0x1801255f0  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801255f5  nop
0x1801255f6  mov     rcx, [rbx+8]; this
0x1801255fa  test    rcx, rcx
0x1801255fd  jz      short loc_180125604
0x1801255ff  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180125604  mov     eax, esi
0x180125606  jmp     short loc_180125669
0x180125608  test    r14b, r14b
0x18012560b  cmovnz  rdi, [rsp+290h+hKey]
0x180125611  call    ??0?$shared_ptr@VDiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>(std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey> const &)
0x180125616  lea     r9, [rsp+290h+Str]
0x18012561b  mov     r8, rdi
0x18012561e  mov     rdx, rax
0x180125621  mov     rcx, r15; this
0x180125624  call    ?GetChildKeyData@XMLDiagnosticReportGenerator@MDMDiagnostics@MDM@Windows@Microsoft@@AEAAJV?$shared_ptr@VDiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@@std@@PEAUHKEY__@@PEAG@Z; Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::GetChildKeyData(std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>,HKEY__ *,ushort *)
0x180125629  mov     esi, eax
0x18012562b  test    eax, eax
0x18012562d  jns     short loc_180125643
0x18012562f  mov     edi, 80070002h
0x180125634  cmp     eax, edi
0x180125636  jz      loc_180125493
0x18012563c  mov     edx, 65h ; 'e'
0x180125641  jmp     short loc_1801255C9
0x180125643  lea     rcx, [rsp+290h+hKey]
0x180125648  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18012564d  nop
0x18012564e  lea     rcx, [rsp+290h+var_268]
0x180125653  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180125658  nop
0x180125659  mov     rcx, [rbx+8]; this
0x18012565d  test    rcx, rcx
0x180125660  jz      short loc_180125667
0x180125662  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180125667  xor     eax, eax
0x180125669  mov     rcx, [rbp+190h+var_30]
0x180125670  xor     rcx, rsp; StackCookie
0x180125673  call    __security_check_cookie
0x180125678  mov     rbx, [rsp+290h+arg_10]
0x180125680  add     rsp, 270h
0x180125687  pop     r15
0x180125689  pop     r14
0x18012568b  pop     rdi
0x18012568c  pop     rsi
0x18012568d  pop     rbp
0x18012568e  retn
```
