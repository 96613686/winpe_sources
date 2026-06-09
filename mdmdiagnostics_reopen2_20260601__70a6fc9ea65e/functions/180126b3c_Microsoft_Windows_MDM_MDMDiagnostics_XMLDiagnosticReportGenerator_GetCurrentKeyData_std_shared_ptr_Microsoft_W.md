# Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::GetCurrentKeyData(std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>,HKEY__ *,ushort *)

- ea: `0x180126b3c`
- end: `0x180126dd6`
- name: `?GetCurrentKeyData@XMLDiagnosticReportGenerator@MDMDiagnostics@MDM@Windows@Microsoft@@AEAAJV?$shared_ptr@VDiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@@std@@PEAUHKEY__@@PEAG@Z`
- size: `666`
- prototype: `__int64 __fastcall(Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator *this)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180126ddc`

## callees

- `0x180019588`
- `0x18001989c`
- `0x1800e6b14`
- `0x1800e734c`
- `0x1800e7de8`
- `0x1800e8508`
- `0x1800ed46c`
- `0x1800edd28`
- `0x1800eef28`
- `0x180125a74`
- `0x180125bf8`
- `0x180126b3c`
- `0x18012708c`
- `0x1801270f0`
- `0x1801272f0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180126cb2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180126cb2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180126c7c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180126c7c`

## string_xrefs

- `0x180126b92`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\registrytoxml\xmldiagnosticreportgenerator.cpp`
- `0x180126c45`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\registrytoxml\xmldiagnosticreportgenerator.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::GetCurrentKeyData(
        Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator *this,
        _QWORD *a2,
        HKEY a3,
        __int64 a4)
{
  const unsigned __int16 *v7; // r14
  int v8; // eax
  signed int v9; // edi
  std::_Ref_count_base *v10; // rcx
  unsigned __int64 v12; // rdi
  unsigned __int64 v13; // rax
  void *v14; // rax
  std::_Ref_count_base *v15; // rcx
  __int64 v16; // rdx
  HKEY v17; // rdi
  LSTATUS v18; // eax
  std::_Ref_count_base *v19; // rcx
  std::_Ref_count_base *v20; // rcx
  int phkResult; // [rsp+20h] [rbp-40h]
  void *Block; // [rsp+30h] [rbp-30h] BYREF
  unsigned __int64 v23[3]; // [rsp+38h] [rbp-28h] BYREF
  char v24; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]
  HKEY hKey; // [rsp+A8h] [rbp+48h] BYREF

  Block = 0;
  hKey = 0;
  v7 = (const unsigned __int16 *)(a4 + 10);
  v23[0] = 0;
  v8 = StringCchLengthW((const unsigned __int16 *)(a4 + 10), (unsigned __int64)a2, v23);
  v9 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x72,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\registrytoxml\\xmldiagnosticreportgenerator.cpp",
      (const char *)(unsigned int)v8,
      phkResult);
LABEL_3:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    v10 = (std::_Ref_count_base *)a2[1];
    if ( v10 )
      std::_Ref_count_base::_Decref(v10);
    return (unsigned int)v9;
  }
  v12 = v23[0] + 1;
  v13 = 2 * (v23[0] + 1);
  if ( !is_mul_ok(v23[0] + 1, 2u) )
    v13 = -1;
  v14 = operator new[](v13, (const struct std::nothrow_t *)std::nothrow);
  Block = v14;
  v23[2] = (unsigned __int64)&Block;
  v24 = 1;
  if ( !v14 )
  {
    operator delete(0);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    v15 = (std::_Ref_count_base *)a2[1];
    if ( v15 )
      std::_Ref_count_base::_Decref(v15);
    return 2147942414LL;
  }
  v9 = StringCchCopyW((unsigned __int16 *)v14, v12, v7);
  if ( v9 < 0 )
  {
    v16 = 128;
LABEL_14:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\registrytoxml\\xmldiagnosticreportgenerator.cpp",
      (const char *)(unsigned int)v9,
      phkResult);
    operator delete(Block);
    goto LABEL_3;
  }
  v17 = hKey;
  if ( hKey )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)v23);
    RegCloseKey(v17);
    wil::last_error_context::~last_error_context((wil::last_error_context *)v23);
  }
  hKey = 0;
  v18 = RegOpenKeyExW(a3, (LPCWSTR)Block, 0, 0x20019u, &hKey);
  v9 = v18;
  if ( v18 > 0 )
    v9 = (unsigned __int16)v18 | 0x80070000;
  if ( v9 >= 0 )
  {
    v9 = Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::WriteStartElement(
           this,
           (const unsigned __int16 *)(*a2 + 1040LL));
    if ( v9 < 0 )
    {
      v16 = 140;
      goto LABEL_14;
    }
    std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>(
      v23,
      a2);
    v9 = Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::GatherRegistryValues(this);
    if ( v9 < 0 )
    {
      v16 = 141;
      goto LABEL_14;
    }
    std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>(
      v23,
      a2);
    v9 = Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::GatherRegistryKeys(this);
    if ( v9 < 0 )
    {
      v16 = 142;
      goto LABEL_14;
    }
    v9 = Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::WriteEndElement(this);
    if ( v9 < 0 )
    {
      v16 = 143;
      goto LABEL_14;
    }
    operator delete(Block);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    v20 = (std::_Ref_count_base *)a2[1];
    if ( v20 )
      std::_Ref_count_base::_Decref(v20);
    return 0;
  }
  else
  {
    if ( v9 != -2147024894 )
    {
      v16 = 135;
      goto LABEL_14;
    }
    operator delete(Block);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    v19 = (std::_Ref_count_base *)a2[1];
    if ( v19 )
      std::_Ref_count_base::_Decref(v19);
    return 2147942402LL;
  }
}

```

## disassembly

```asm
0x180126b3c  mov     [rsp-28h+arg_0], rbx
0x180126b41  mov     [rsp-28h+arg_8], rdx
0x180126b46  push    rbp
0x180126b47  push    rsi
0x180126b48  push    rdi
0x180126b49  push    r14
0x180126b4b  push    r15
0x180126b4d  mov     rbp, rsp
0x180126b50  sub     rsp, 60h
0x180126b54  mov     r15, r8
0x180126b57  mov     rbx, rdx
0x180126b5a  mov     rsi, rcx
0x180126b5d  mov     [rbp+Block], 0
0x180126b65  mov     [rbp+hKey], 0
0x180126b6d  lea     r14, [r9+0Ah]
0x180126b71  mov     [rbp+var_28], 0
0x180126b79  lea     r8, [rbp+var_28]; unsigned __int64 *
0x180126b7d  mov     rcx, r14; unsigned __int16 *
0x180126b80  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180126b85  mov     edi, eax
0x180126b87  test    eax, eax
0x180126b89  jns     short loc_180126BC3
0x180126b8b  mov     rcx, [rbp+28h]; this
0x180126b8f  mov     r9d, eax; char *
0x180126b92  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180126b99  mov     edx, 72h ; 'r'; void *
0x180126b9e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180126ba3  nop
0x180126ba4  lea     rcx, [rbp+hKey]
0x180126ba8  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180126bad  nop
0x180126bae  mov     rcx, [rbx+8]; this
0x180126bb2  test    rcx, rcx
0x180126bb5  jz      short loc_180126BBC
0x180126bb7  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180126bbc  mov     eax, edi
0x180126bbe  jmp     loc_180126DC1
0x180126bc3  mov     rdi, [rbp+var_28]
0x180126bc7  inc     rdi
0x180126bca  mov     eax, 2
0x180126bcf  mul     rdi
0x180126bd2  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180126bd9  cmovb   rax, rcx
0x180126bdd  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180126be4  mov     rcx, rax; unsigned __int64
0x180126be7  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180126bec  mov     [rbp+Block], rax
0x180126bf0  lea     rcx, [rbp+Block]
0x180126bf4  mov     [rbp+var_18], rcx
0x180126bf8  mov     [rbp+var_10], 1
0x180126bfc  test    rax, rax
0x180126bff  jnz     short loc_180126C2C
0x180126c01  mov     rcx, rax; Block
0x180126c04  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180126c09  nop
0x180126c0a  lea     rcx, [rbp+hKey]
0x180126c0e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180126c13  nop
0x180126c14  mov     rcx, [rbx+8]; this
0x180126c18  test    rcx, rcx
0x180126c1b  jz      short loc_180126C22
0x180126c1d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180126c22  mov     eax, 8007000Eh
0x180126c27  jmp     loc_180126DC1
0x180126c2c  mov     r8, r14; unsigned __int16 *
0x180126c2f  mov     rdx, rdi; unsigned __int64
0x180126c32  mov     rcx, rax; unsigned __int16 *
0x180126c35  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180126c3a  mov     edi, eax
0x180126c3c  test    eax, eax
0x180126c3e  jns     short loc_180126C67
0x180126c40  mov     edx, 80h; void *
0x180126c45  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180126c4c  mov     r9d, edi; char *
0x180126c4f  mov     rcx, [rbp+28h]; this
0x180126c53  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180126c58  nop
0x180126c59  mov     rcx, [rbp+Block]; Block
0x180126c5d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180126c62  jmp     loc_180126BA4
0x180126c67  mov     rdi, [rbp+hKey]
0x180126c6b  test    rdi, rdi
0x180126c6e  jz      short loc_180126C91
0x180126c70  lea     rcx, [rbp+var_28]; this
0x180126c74  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180126c79  mov     rcx, rdi; hKey
0x180126c7c  call    cs:__imp_RegCloseKey
0x180126c83  nop     dword ptr [rax+rax+00h]
0x180126c88  lea     rcx, [rbp+var_28]; this
0x180126c8c  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180126c91  mov     [rbp+hKey], 0
0x180126c99  lea     rax, [rbp+hKey]
0x180126c9d  mov     qword ptr [rsp+60h+phkResult], rax; phkResult
0x180126ca2  mov     r9d, 20019h; samDesired
0x180126ca8  xor     r8d, r8d; ulOptions
0x180126cab  mov     rdx, [rbp+Block]; lpSubKey
0x180126caf  mov     rcx, r15; hKey
0x180126cb2  call    cs:__imp_RegOpenKeyExW
0x180126cb9  nop     dword ptr [rax+rax+00h]
0x180126cbe  mov     edi, eax
0x180126cc0  test    eax, eax
0x180126cc2  jle     short loc_180126CCD
0x180126cc4  movzx   edi, ax
0x180126cc7  or      edi, 80070000h
0x180126ccd  test    edi, edi
0x180126ccf  jns     short loc_180126D0D
0x180126cd1  mov     esi, 80070002h
0x180126cd6  cmp     edi, esi
0x180126cd8  jnz     short loc_180126D03
0x180126cda  mov     rcx, [rbp+Block]; Block
0x180126cde  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180126ce3  nop
0x180126ce4  lea     rcx, [rbp+hKey]
0x180126ce8  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180126ced  nop
0x180126cee  mov     rcx, [rbx+8]; this
0x180126cf2  test    rcx, rcx
0x180126cf5  jz      short loc_180126CFC
0x180126cf7  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180126cfc  mov     eax, esi
0x180126cfe  jmp     loc_180126DC1
0x180126d03  mov     edx, 87h
0x180126d08  jmp     loc_180126C45
0x180126d0d  mov     rdx, [rbx]
0x180126d10  add     rdx, 410h; unsigned __int16 *
0x180126d17  mov     rcx, rsi; this
0x180126d1a  call    ?WriteStartElement@XMLDiagnosticReportGenerator@MDMDiagnostics@MDM@Windows@Microsoft@@AEAAJPEBG@Z; Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::WriteStartElement(ushort const *)
0x180126d1f  mov     edi, eax
0x180126d21  test    eax, eax
0x180126d23  jns     short loc_180126D2F
0x180126d25  mov     edx, 8Ch
0x180126d2a  jmp     loc_180126C45
0x180126d2f  mov     r8, [rbp+hKey]
0x180126d33  mov     rdx, rbx
0x180126d36  lea     rcx, [rbp+var_28]
0x180126d3a  call    ??0?$shared_ptr@VDiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>(std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey> const &)
0x180126d3f  mov     rdx, rax
0x180126d42  mov     rcx, rsi; this
0x180126d45  call    ?GatherRegistryValues@XMLDiagnosticReportGenerator@MDMDiagnostics@MDM@Windows@Microsoft@@AEAAJV?$shared_ptr@VDiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@@std@@PEAUHKEY__@@@Z; Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::GatherRegistryValues(std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>,HKEY__ *)
0x180126d4a  mov     edi, eax
0x180126d4c  test    eax, eax
0x180126d4e  jns     short loc_180126D5A
0x180126d50  mov     edx, 8Dh
0x180126d55  jmp     loc_180126C45
0x180126d5a  mov     r8, [rbp+hKey]
0x180126d5e  mov     rdx, rbx
0x180126d61  lea     rcx, [rbp+var_28]
0x180126d65  call    ??0?$shared_ptr@VDiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>(std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey> const &)
0x180126d6a  mov     rdx, rax
0x180126d6d  mov     rcx, rsi; this
0x180126d70  call    ?GatherRegistryKeys@XMLDiagnosticReportGenerator@MDMDiagnostics@MDM@Windows@Microsoft@@AEAAJV?$shared_ptr@VDiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@@std@@PEAUHKEY__@@@Z; Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::GatherRegistryKeys(std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>,HKEY__ *)
0x180126d75  mov     edi, eax
0x180126d77  test    eax, eax
0x180126d79  jns     short loc_180126D85
0x180126d7b  mov     edx, 8Eh
0x180126d80  jmp     loc_180126C45
0x180126d85  mov     rcx, rsi; this
0x180126d88  call    ?WriteEndElement@XMLDiagnosticReportGenerator@MDMDiagnostics@MDM@Windows@Microsoft@@AEAAJXZ; Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::WriteEndElement(void)
0x180126d8d  mov     edi, eax
0x180126d8f  test    eax, eax
0x180126d91  jns     short loc_180126D9D
0x180126d93  mov     edx, 8Fh
0x180126d98  jmp     loc_180126C45
0x180126d9d  mov     rcx, [rbp+Block]; Block
0x180126da1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180126da6  nop
0x180126da7  lea     rcx, [rbp+hKey]
0x180126dab  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180126db0  nop
0x180126db1  mov     rcx, [rbx+8]; this
0x180126db5  test    rcx, rcx
0x180126db8  jz      short loc_180126DBF
0x180126dba  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180126dbf  xor     eax, eax
0x180126dc1  mov     rbx, [rsp+60h+arg_0]
0x180126dc9  add     rsp, 60h
0x180126dcd  pop     r15
0x180126dcf  pop     r14
0x180126dd1  pop     rdi
0x180126dd2  pop     rsi
0x180126dd3  pop     rbp
0x180126dd4  retn
```
