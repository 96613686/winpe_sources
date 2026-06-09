# Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::GatherSpecificSubKeys(std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>,HKEY__ *)

- ea: `0x180124928`
- end: `0x180124cc3`
- name: `?GatherSpecificSubKeys@XMLDiagnosticReportGenerator@MDMDiagnostics@MDM@Windows@Microsoft@@AEAAJV?$shared_ptr@VDiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@@std@@PEAUHKEY__@@@Z`
- size: `923`
- prototype: `__int64 __fastcall(Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator *this)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180124088`

## callees

- `0x180019000`
- `0x180019508`
- `0x18001981c`
- `0x180019f88`
- `0x180019fc4`
- `0x1800e691c`
- `0x1800e7124`
- `0x1800e7c08`
- `0x1800e82e4`
- `0x1800ece5c`
- `0x1800ed6e4`
- `0x1800ee898`
- `0x18012347c`
- `0x180124928`
- `0x1801256fc`
- `0x1801258f8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x180124a04`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x180124a04`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1801249e5`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1801249e5`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180124b84`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180124b84`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180124b19`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180124b19`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180124ae9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180124ae9`

## string_xrefs

- `0x1801249ad`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\registrytoxml\xmldiagnosticreportgenerator.cpp`
- `0x180124bf5`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\registrytoxml\xmldiagnosticreportgenerator.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::GatherSpecificSubKeys(
        Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator *this,
        const unsigned __int16 **a2,
        HKEY a3)
{
  const unsigned __int16 *v6; // rsi
  signed int v7; // edi
  __int64 v8; // rdx
  std::_Ref_count_base *v9; // rcx
  wchar_t *v11; // r14
  __int64 v12; // rsi
  unsigned __int64 v13; // rcx
  unsigned __int64 v14; // rax
  void *v15; // rax
  std::_Ref_count_base *v16; // rcx
  rsize_t v17; // rdx
  errno_t v18; // eax
  LSTATUS v19; // eax
  bool v20; // zf
  DWORD i; // r14d
  LSTATUS v22; // eax
  bool v23; // zf
  __int64 v24; // rdx
  std::_Ref_count_base *v25; // rcx
  int phkResult; // [rsp+20h] [rbp-E0h]
  int phkResulta; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  void *Block; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cchName; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t *Context; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v32[16]; // [rsp+68h] [rbp-98h] BYREF
  const unsigned __int16 **v33; // [rsp+78h] [rbp-88h]
  void **p_Block; // [rsp+80h] [rbp-80h]
  char v35; // [rsp+88h] [rbp-78h]
  wchar_t Str[264]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR Name; // [rsp+2A0h] [rbp+1A0h] BYREF
  _BYTE v38[526]; // [rsp+2A2h] [rbp+1A2h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4F8h] [rbp+3F8h]

  v33 = a2;
  Context = 0;
  hKey = 0;
  v6 = *a2;
  memset_0(Str, 0, 0x208u);
  v7 = StringCchCopyW(Str, 0x103u, v6);
  if ( v7 < 0 )
  {
    v8 = 296;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\registrytoxml\\xmldiagnosticreportgenerator.cpp",
      (const char *)(unsigned int)v7,
      phkResult);
LABEL_4:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    v9 = (std::_Ref_count_base *)a2[1];
    if ( v9 )
      std::_Ref_count_base::_Decref(v9);
    return (unsigned int)v7;
  }
  if ( wcsstr(Str, L"\\*") )
  {
    v11 = wcstok_s(Str, L"*", &Context);
    Block = 0;
    p_Block = &Block;
    v35 = 1;
    v12 = -1;
    v13 = -1;
    do
      ++v13;
    while ( v11[v13] );
    v14 = 2 * v13;
    if ( !is_mul_ok(v13, 2u) )
      v14 = -1;
    v15 = operator new[](v14, (const struct std::nothrow_t *)std::nothrow);
    Block = v15;
    if ( !v15 )
    {
      operator delete(0);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      v16 = (std::_Ref_count_base *)a2[1];
      if ( v16 )
        std::_Ref_count_base::_Decref(v16);
      return 2147942414LL;
    }
    v17 = -1;
    do
      ++v17;
    while ( v11[v17] );
    v18 = o_wmemcpy_s_0((wchar_t *)v15, v17, v11, v17 - 1);
    v7 = v18;
    if ( v18 )
    {
      if ( v18 > 0 )
        v7 = (unsigned __int16)v18 | 0x80070000;
LABEL_21:
      operator delete(Block);
      goto LABEL_4;
    }
    do
      ++v12;
    while ( v11[v12] );
    *((_WORD *)Block + v12 - 1) = 0;
    if ( hKey )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&cchName);
      RegCloseKey(hKey);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&cchName);
    }
    hKey = 0;
    v19 = RegOpenKeyExW(a3, (LPCWSTR)Block, 0, 0x20019u, &hKey);
    v20 = v19 == 0;
    if ( v19 > 0 )
      v20 = 0;
    if ( v20 )
    {
      memset_0(v38, 0, 0x206u);
      for ( i = 0; ; ++i )
      {
        cchName = 260;
        Name = 0;
        v22 = RegEnumKeyExW(hKey, i, &Name, &cchName, 0, 0, 0, 0);
        v23 = v22 == 0;
        if ( v22 > 0 )
          v23 = 0;
        if ( !v23 )
          goto LABEL_38;
        v7 = Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::WriteStartElement(this, *a2 + 520);
        if ( v7 < 0 )
          break;
        std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>(
          v32,
          a2);
        Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::CrawlTree(this);
        v7 = Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::WriteEndElement(this);
        if ( v7 < 0 )
        {
          v24 = 364;
LABEL_37:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v24,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\registrytoxml\\xmldiagnosticreportgenerator.cpp",
            (const char *)(unsigned int)v7,
            phkResulta);
          goto LABEL_21;
        }
      }
      v24 = 362;
      goto LABEL_37;
    }
LABEL_38:
    operator delete(Block);
  }
  else if ( v6 )
  {
    v7 = Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::WriteStartElement(this, *a2 + 520);
    if ( v7 < 0 )
    {
      v8 = 378;
      goto LABEL_3;
    }
    std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>(
      v32,
      a2);
    Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::CrawlTree(this);
    v7 = Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::WriteEndElement(this);
    if ( v7 < 0 )
    {
      v8 = 380;
      goto LABEL_3;
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  v25 = (std::_Ref_count_base *)a2[1];
  if ( v25 )
    std::_Ref_count_base::_Decref(v25);
  return 0;
}

```

## disassembly

```asm
0x180124928  mov     [rsp-8+arg_18], rbx
0x18012492d  push    rbp
0x18012492e  push    rsi
0x18012492f  push    rdi
0x180124930  push    r12
0x180124932  push    r13
0x180124934  push    r14
0x180124936  push    r15
0x180124938  lea     rbp, [rsp-3C0h]
0x180124940  sub     rsp, 4C0h
0x180124947  mov     rax, cs:__security_cookie
0x18012494e  xor     rax, rsp
0x180124951  mov     [rbp+3F0h+var_40], rax
0x180124958  mov     r12, r8
0x18012495b  mov     rbx, rdx
0x18012495e  mov     r15, rcx
0x180124961  mov     [rsp+4F0h+var_478], rdx
0x180124966  xor     r13d, r13d
0x180124969  mov     [rsp+4F0h+Context], r13
0x18012496e  mov     [rsp+4F0h+hKey], r13
0x180124973  mov     rsi, [rdx]
0x180124976  xor     edx, edx; Val
0x180124978  mov     r8d, 208h; Size
0x18012497e  lea     rcx, [rbp+3F0h+Str]; void *
0x180124982  call    memset_0
0x180124987  mov     r8, rsi; unsigned __int16 *
0x18012498a  mov     edx, 103h; unsigned __int64
0x18012498f  lea     rcx, [rbp+3F0h+Str]; unsigned __int16 *
0x180124993  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180124998  mov     edi, eax
0x18012499a  test    eax, eax
0x18012499c  jns     short loc_1801249DA
0x18012499e  mov     edx, 128h; void *
0x1801249a3  mov     rcx, [rbp+3F8h]; this
0x1801249aa  mov     r9d, edi; char *
0x1801249ad  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1801249b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801249b9  nop
0x1801249ba  lea     rcx, [rsp+4F0h+hKey]
0x1801249bf  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801249c4  nop
0x1801249c5  mov     rcx, [rbx+8]; this
0x1801249c9  test    rcx, rcx
0x1801249cc  jz      short loc_1801249D3
0x1801249ce  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801249d3  mov     eax, edi
0x1801249d5  jmp     loc_180124C36
0x1801249da  lea     rdx, asc_1801D3550; "\\*"
0x1801249e1  lea     rcx, [rbp+3F0h+Str]; Str
0x1801249e5  call    cs:__imp_wcsstr
0x1801249eb  test    rax, rax
0x1801249ee  jz      loc_180124C60
0x1801249f4  lea     r8, [rsp+4F0h+Context]; Context
0x1801249f9  lea     rdx, Delimiter; "*"
0x180124a00  lea     rcx, [rbp+3F0h+Str]; String
0x180124a04  call    cs:__imp_wcstok_s
0x180124a0a  mov     r14, rax
0x180124a0d  mov     [rsp+4F0h+Block], r13
0x180124a12  lea     rax, [rsp+4F0h+Block]
0x180124a17  mov     [rbp+3F0h+var_470], rax
0x180124a1b  mov     [rbp+3F0h+var_468], 1
0x180124a1f  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180124a23  mov     rcx, rsi
0x180124a26  inc     rcx
0x180124a29  cmp     [r14+rcx*2], r13w
0x180124a2e  jnz     short loc_180124A26
0x180124a30  mov     eax, 2
0x180124a35  mul     rcx
0x180124a38  cmovb   rax, rsi
0x180124a3c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180124a43  mov     rcx, rax; unsigned __int64
0x180124a46  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180124a4b  mov     [rsp+4F0h+Block], rax
0x180124a50  test    rax, rax
0x180124a53  jnz     short loc_180124A81
0x180124a55  mov     rcx, rax; Block
0x180124a58  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180124a5d  nop
0x180124a5e  lea     rcx, [rsp+4F0h+hKey]
0x180124a63  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180124a68  nop
0x180124a69  mov     rcx, [rbx+8]; this
0x180124a6d  test    rcx, rcx
0x180124a70  jz      short loc_180124A77
0x180124a72  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180124a77  mov     eax, 8007000Eh
0x180124a7c  jmp     loc_180124C36
0x180124a81  mov     rdx, rsi
0x180124a84  inc     rdx; N1
0x180124a87  cmp     [r14+rdx*2], r13w
0x180124a8c  jnz     short loc_180124A84
0x180124a8e  lea     r9, [rdx-1]; N
0x180124a92  mov     r8, r14; S2
0x180124a95  mov     rcx, rax; S1
0x180124a98  call    _o_wmemcpy_s_0
0x180124a9d  mov     edi, eax
0x180124a9f  test    eax, eax
0x180124aa1  jz      short loc_180124ABD
0x180124aa3  jle     short loc_180124AAE
0x180124aa5  movzx   edi, ax
0x180124aa8  or      edi, 80070000h
0x180124aae  mov     rcx, [rsp+4F0h+Block]; Block
0x180124ab3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180124ab8  jmp     loc_1801249BA
0x180124abd  inc     rsi
0x180124ac0  cmp     [r14+rsi*2], r13w
0x180124ac5  jnz     short loc_180124ABD
0x180124ac7  mov     rax, [rsp+4F0h+Block]
0x180124acc  mov     [rax+rsi*2-2], r13w
0x180124ad2  mov     rdi, [rsp+4F0h+hKey]
0x180124ad7  test    rdi, rdi
0x180124ada  jz      short loc_180124AF9
0x180124adc  lea     rcx, [rsp+4F0h+cchName]; this
0x180124ae1  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180124ae6  mov     rcx, rdi; hKey
0x180124ae9  call    cs:__imp_RegCloseKey
0x180124aef  lea     rcx, [rsp+4F0h+cchName]; this
0x180124af4  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180124af9  mov     [rsp+4F0h+hKey], r13
0x180124afe  lea     rax, [rsp+4F0h+hKey]
0x180124b03  mov     [rsp+4F0h+phkResult], rax; phkResult
0x180124b08  mov     r9d, 20019h; samDesired
0x180124b0e  xor     r8d, r8d; ulOptions
0x180124b11  mov     rdx, [rsp+4F0h+Block]; lpSubKey
0x180124b16  mov     rcx, r12; hKey
0x180124b19  call    cs:__imp_RegOpenKeyExW
0x180124b1f  mov     esi, 80070000h
0x180124b24  test    eax, eax
0x180124b26  jle     short loc_180124B2F
0x180124b28  movzx   eax, ax
0x180124b2b  or      eax, esi
0x180124b2d  test    eax, eax
0x180124b2f  jnz     loc_180124C10
0x180124b35  xor     edx, edx; Val
0x180124b37  mov     r8d, 206h; Size
0x180124b3d  lea     rcx, [rbp+3F0h+var_24E]; void *
0x180124b44  call    memset_0
0x180124b49  mov     r14d, r13d
0x180124b4c  mov     [rsp+4F0h+cchName], 104h
0x180124b54  mov     [rbp+3F0h+Name], r13w
0x180124b5c  mov     [rsp+4F0h+lpftLastWriteTime], r13; lpftLastWriteTime
0x180124b61  mov     [rsp+4F0h+lpcchClass], r13; lpcchClass
0x180124b66  mov     [rsp+4F0h+lpClass], r13; lpClass
0x180124b6b  mov     [rsp+4F0h+phkResult], r13; int
0x180124b70  lea     r9, [rsp+4F0h+cchName]; lpcchName
0x180124b75  lea     r8, [rbp+3F0h+Name]; lpName
0x180124b7c  mov     edx, r14d; dwIndex
0x180124b7f  mov     rcx, [rsp+4F0h+hKey]; hKey
0x180124b84  call    cs:__imp_RegEnumKeyExW
0x180124b8a  test    eax, eax
0x180124b8c  jle     short loc_180124B95
0x180124b8e  movzx   eax, ax
0x180124b91  or      eax, esi
0x180124b93  test    eax, eax
0x180124b95  jnz     short loc_180124C10
0x180124b97  mov     rdx, [rbx]
0x180124b9a  add     rdx, 410h; unsigned __int16 *
0x180124ba1  mov     rcx, r15; this
0x180124ba4  call    ?WriteStartElement@XMLDiagnosticReportGenerator@MDMDiagnostics@MDM@Windows@Microsoft@@AEAAJPEBG@Z; Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::WriteStartElement(ushort const *)
0x180124ba9  mov     edi, eax
0x180124bab  test    eax, eax
0x180124bad  js      short loc_180124BF0
0x180124baf  mov     r8, [rsp+4F0h+hKey]
0x180124bb4  mov     rdx, rbx
0x180124bb7  lea     rcx, [rsp+4F0h+var_488]
0x180124bbc  call    ??0?$shared_ptr@VDiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>(std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey> const &)
0x180124bc1  lea     r9, [rbp+3F0h+Name]
0x180124bc8  mov     rdx, rax
0x180124bcb  mov     rcx, r15; this
0x180124bce  call    ?CrawlTree@XMLDiagnosticReportGenerator@MDMDiagnostics@MDM@Windows@Microsoft@@AEAAJV?$shared_ptr@VDiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@@std@@PEAUHKEY__@@PEAG@Z; Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::CrawlTree(std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>,HKEY__ *,ushort *)
0x180124bd3  mov     rcx, r15; this
0x180124bd6  call    ?WriteEndElement@XMLDiagnosticReportGenerator@MDMDiagnostics@MDM@Windows@Microsoft@@AEAAJXZ; Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::WriteEndElement(void)
0x180124bdb  mov     edi, eax
0x180124bdd  test    eax, eax
0x180124bdf  js      short loc_180124BE9
0x180124be1  inc     r14d
0x180124be4  jmp     loc_180124B4C
0x180124be9  mov     edx, 16Ch
0x180124bee  jmp     short loc_180124BF5
0x180124bf0  mov     edx, 16Ah; void *
0x180124bf5  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180124bfc  mov     r9d, edi; char *
0x180124bff  mov     rcx, [rbp+3F8h]; this
0x180124c06  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180124c0b  jmp     loc_180124AAE
0x180124c10  mov     rcx, [rsp+4F0h+Block]; Block
0x180124c15  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180124c1a  nop
0x180124c1b  lea     rcx, [rsp+4F0h+hKey]
0x180124c20  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180124c25  nop
0x180124c26  mov     rcx, [rbx+8]; this
0x180124c2a  test    rcx, rcx
0x180124c2d  jz      short loc_180124C34
0x180124c2f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180124c34  xor     eax, eax
0x180124c36  mov     rcx, [rbp+3F0h+var_40]
0x180124c3d  xor     rcx, rsp; StackCookie
0x180124c40  call    __security_check_cookie
0x180124c45  mov     rbx, [rsp+4F0h+arg_18]
0x180124c4d  add     rsp, 4C0h
0x180124c54  pop     r15
0x180124c56  pop     r14
0x180124c58  pop     r13
0x180124c5a  pop     r12
0x180124c5c  pop     rdi
0x180124c5d  pop     rsi
0x180124c5e  pop     rbp
0x180124c5f  retn
0x180124c60  test    rsi, rsi
0x180124c63  jz      short loc_180124C1B
0x180124c65  mov     rdx, [rbx]
0x180124c68  add     rdx, 410h; unsigned __int16 *
0x180124c6f  mov     rcx, r15; this
0x180124c72  call    ?WriteStartElement@XMLDiagnosticReportGenerator@MDMDiagnostics@MDM@Windows@Microsoft@@AEAAJPEBG@Z; Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::WriteStartElement(ushort const *)
0x180124c77  mov     edi, eax
0x180124c79  test    eax, eax
0x180124c7b  jns     short loc_180124C87
0x180124c7d  mov     edx, 17Ah
0x180124c82  jmp     loc_1801249A3
0x180124c87  mov     rdx, rbx
0x180124c8a  lea     rcx, [rsp+4F0h+var_488]
0x180124c8f  call    ??0?$shared_ptr@VDiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>(std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey> const &)
0x180124c94  lea     r9, [rbp+3F0h+Str]
0x180124c98  mov     r8, r12
0x180124c9b  mov     rdx, rax
0x180124c9e  mov     rcx, r15; this
0x180124ca1  call    ?CrawlTree@XMLDiagnosticReportGenerator@MDMDiagnostics@MDM@Windows@Microsoft@@AEAAJV?$shared_ptr@VDiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@@std@@PEAUHKEY__@@PEAG@Z; Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::CrawlTree(std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>,HKEY__ *,ushort *)
0x180124ca6  mov     rcx, r15; this
0x180124ca9  call    ?WriteEndElement@XMLDiagnosticReportGenerator@MDMDiagnostics@MDM@Windows@Microsoft@@AEAAJXZ; Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::WriteEndElement(void)
0x180124cae  mov     edi, eax
0x180124cb0  test    eax, eax
0x180124cb2  jns     loc_180124C1B
0x180124cb8  mov     edx, 17Ch
0x180124cbd  jmp     loc_1801249A3
```
