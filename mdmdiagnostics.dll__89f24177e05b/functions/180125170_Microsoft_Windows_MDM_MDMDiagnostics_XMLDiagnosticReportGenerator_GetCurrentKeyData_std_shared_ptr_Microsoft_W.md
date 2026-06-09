# Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::GetCurrentKeyData(std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>,HKEY__ *,ushort *)

- ea: `0x180125170`
- end: `0x1801253fd`
- name: `?GetCurrentKeyData@XMLDiagnosticReportGenerator@MDMDiagnostics@MDM@Windows@Microsoft@@AEAAJV?$shared_ptr@VDiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@@std@@PEAUHKEY__@@PEAG@Z`
- size: `653`
- prototype: `__int64 __fastcall(Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator *this)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180125404`

## callees

- `0x180019508`
- `0x18001981c`
- `0x1800e691c`
- `0x1800e7124`
- `0x1800e7c08`
- `0x1800e82e4`
- `0x1800ece5c`
- `0x1800ed6e4`
- `0x1800ee898`
- `0x180124088`
- `0x180124208`
- `0x180125170`
- `0x180125698`
- `0x1801256fc`
- `0x1801258f8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801252e0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801252e0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801252b0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801252b0`

## string_xrefs

- `0x1801251c6`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\registrytoxml\xmldiagnosticreportgenerator.cpp`
- `0x180125279`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\registrytoxml\xmldiagnosticreportgenerator.cpp`

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
      (void *)0x73,
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
    v16 = 129;
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
      v16 = 141;
      goto LABEL_14;
    }
    std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>(
      v23,
      a2);
    v9 = Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::GatherRegistryValues(this);
    if ( v9 < 0 )
    {
      v16 = 142;
      goto LABEL_14;
    }
    std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>(
      v23,
      a2);
    v9 = Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::GatherRegistryKeys(this);
    if ( v9 < 0 )
    {
      v16 = 143;
      goto LABEL_14;
    }
    v9 = Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::WriteEndElement(this);
    if ( v9 < 0 )
    {
      v16 = 144;
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
      v16 = 136;
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
0x180125170  mov     [rsp-28h+arg_0], rbx
0x180125175  mov     [rsp-28h+arg_8], rdx
0x18012517a  push    rbp
0x18012517b  push    rsi
0x18012517c  push    rdi
0x18012517d  push    r14
0x18012517f  push    r15
0x180125181  mov     rbp, rsp
0x180125184  sub     rsp, 60h
0x180125188  mov     r15, r8
0x18012518b  mov     rbx, rdx
0x18012518e  mov     rsi, rcx
0x180125191  mov     [rbp+Block], 0
0x180125199  mov     [rbp+hKey], 0
0x1801251a1  lea     r14, [r9+0Ah]
0x1801251a5  mov     [rbp+var_28], 0
0x1801251ad  lea     r8, [rbp+var_28]; unsigned __int64 *
0x1801251b1  mov     rcx, r14; unsigned __int16 *
0x1801251b4  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1801251b9  mov     edi, eax
0x1801251bb  test    eax, eax
0x1801251bd  jns     short loc_1801251F7
0x1801251bf  mov     rcx, [rbp+28h]; this
0x1801251c3  mov     r9d, eax; char *
0x1801251c6  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1801251cd  mov     edx, 73h ; 's'; void *
0x1801251d2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801251d7  nop
0x1801251d8  lea     rcx, [rbp+hKey]
0x1801251dc  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801251e1  nop
0x1801251e2  mov     rcx, [rbx+8]; this
0x1801251e6  test    rcx, rcx
0x1801251e9  jz      short loc_1801251F0
0x1801251eb  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801251f0  mov     eax, edi
0x1801251f2  jmp     loc_1801253E9
0x1801251f7  mov     rdi, [rbp+var_28]
0x1801251fb  inc     rdi
0x1801251fe  mov     eax, 2
0x180125203  mul     rdi
0x180125206  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18012520d  cmovb   rax, rcx
0x180125211  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180125218  mov     rcx, rax; unsigned __int64
0x18012521b  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180125220  mov     [rbp+Block], rax
0x180125224  lea     rcx, [rbp+Block]
0x180125228  mov     [rbp+var_18], rcx
0x18012522c  mov     [rbp+var_10], 1
0x180125230  test    rax, rax
0x180125233  jnz     short loc_180125260
0x180125235  mov     rcx, rax; Block
0x180125238  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18012523d  nop
0x18012523e  lea     rcx, [rbp+hKey]
0x180125242  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180125247  nop
0x180125248  mov     rcx, [rbx+8]; this
0x18012524c  test    rcx, rcx
0x18012524f  jz      short loc_180125256
0x180125251  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180125256  mov     eax, 8007000Eh
0x18012525b  jmp     loc_1801253E9
0x180125260  mov     r8, r14; unsigned __int16 *
0x180125263  mov     rdx, rdi; unsigned __int64
0x180125266  mov     rcx, rax; unsigned __int16 *
0x180125269  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18012526e  mov     edi, eax
0x180125270  test    eax, eax
0x180125272  jns     short loc_18012529B
0x180125274  mov     edx, 81h; void *
0x180125279  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180125280  mov     r9d, edi; char *
0x180125283  mov     rcx, [rbp+28h]; this
0x180125287  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012528c  nop
0x18012528d  mov     rcx, [rbp+Block]; Block
0x180125291  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180125296  jmp     loc_1801251D8
0x18012529b  mov     rdi, [rbp+hKey]
0x18012529f  test    rdi, rdi
0x1801252a2  jz      short loc_1801252BF
0x1801252a4  lea     rcx, [rbp+var_28]; this
0x1801252a8  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1801252ad  mov     rcx, rdi; hKey
0x1801252b0  call    cs:__imp_RegCloseKey
0x1801252b6  lea     rcx, [rbp+var_28]; this
0x1801252ba  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1801252bf  mov     [rbp+hKey], 0
0x1801252c7  lea     rax, [rbp+hKey]
0x1801252cb  mov     qword ptr [rsp+60h+phkResult], rax; phkResult
0x1801252d0  mov     r9d, 20019h; samDesired
0x1801252d6  xor     r8d, r8d; ulOptions
0x1801252d9  mov     rdx, [rbp+Block]; lpSubKey
0x1801252dd  mov     rcx, r15; hKey
0x1801252e0  call    cs:__imp_RegOpenKeyExW
0x1801252e6  mov     edi, eax
0x1801252e8  test    eax, eax
0x1801252ea  jle     short loc_1801252F5
0x1801252ec  movzx   edi, ax
0x1801252ef  or      edi, 80070000h
0x1801252f5  test    edi, edi
0x1801252f7  jns     short loc_180125335
0x1801252f9  mov     esi, 80070002h
0x1801252fe  cmp     edi, esi
0x180125300  jnz     short loc_18012532B
0x180125302  mov     rcx, [rbp+Block]; Block
0x180125306  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18012530b  nop
0x18012530c  lea     rcx, [rbp+hKey]
0x180125310  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180125315  nop
0x180125316  mov     rcx, [rbx+8]; this
0x18012531a  test    rcx, rcx
0x18012531d  jz      short loc_180125324
0x18012531f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180125324  mov     eax, esi
0x180125326  jmp     loc_1801253E9
0x18012532b  mov     edx, 88h
0x180125330  jmp     loc_180125279
0x180125335  mov     rdx, [rbx]
0x180125338  add     rdx, 410h; unsigned __int16 *
0x18012533f  mov     rcx, rsi; this
0x180125342  call    ?WriteStartElement@XMLDiagnosticReportGenerator@MDMDiagnostics@MDM@Windows@Microsoft@@AEAAJPEBG@Z; Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::WriteStartElement(ushort const *)
0x180125347  mov     edi, eax
0x180125349  test    eax, eax
0x18012534b  jns     short loc_180125357
0x18012534d  mov     edx, 8Dh
0x180125352  jmp     loc_180125279
0x180125357  mov     r8, [rbp+hKey]
0x18012535b  mov     rdx, rbx
0x18012535e  lea     rcx, [rbp+var_28]
0x180125362  call    ??0?$shared_ptr@VDiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>(std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey> const &)
0x180125367  mov     rdx, rax
0x18012536a  mov     rcx, rsi; this
0x18012536d  call    ?GatherRegistryValues@XMLDiagnosticReportGenerator@MDMDiagnostics@MDM@Windows@Microsoft@@AEAAJV?$shared_ptr@VDiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@@std@@PEAUHKEY__@@@Z; Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::GatherRegistryValues(std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>,HKEY__ *)
0x180125372  mov     edi, eax
0x180125374  test    eax, eax
0x180125376  jns     short loc_180125382
0x180125378  mov     edx, 8Eh
0x18012537d  jmp     loc_180125279
0x180125382  mov     r8, [rbp+hKey]
0x180125386  mov     rdx, rbx
0x180125389  lea     rcx, [rbp+var_28]
0x18012538d  call    ??0?$shared_ptr@VDiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>(std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey> const &)
0x180125392  mov     rdx, rax
0x180125395  mov     rcx, rsi; this
0x180125398  call    ?GatherRegistryKeys@XMLDiagnosticReportGenerator@MDMDiagnostics@MDM@Windows@Microsoft@@AEAAJV?$shared_ptr@VDiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@@std@@PEAUHKEY__@@@Z; Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::GatherRegistryKeys(std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>,HKEY__ *)
0x18012539d  mov     edi, eax
0x18012539f  test    eax, eax
0x1801253a1  jns     short loc_1801253AD
0x1801253a3  mov     edx, 8Fh
0x1801253a8  jmp     loc_180125279
0x1801253ad  mov     rcx, rsi; this
0x1801253b0  call    ?WriteEndElement@XMLDiagnosticReportGenerator@MDMDiagnostics@MDM@Windows@Microsoft@@AEAAJXZ; Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::WriteEndElement(void)
0x1801253b5  mov     edi, eax
0x1801253b7  test    eax, eax
0x1801253b9  jns     short loc_1801253C5
0x1801253bb  mov     edx, 90h
0x1801253c0  jmp     loc_180125279
0x1801253c5  mov     rcx, [rbp+Block]; Block
0x1801253c9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1801253ce  nop
0x1801253cf  lea     rcx, [rbp+hKey]
0x1801253d3  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801253d8  nop
0x1801253d9  mov     rcx, [rbx+8]; this
0x1801253dd  test    rcx, rcx
0x1801253e0  jz      short loc_1801253E7
0x1801253e2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801253e7  xor     eax, eax
0x1801253e9  mov     rbx, [rsp+60h+arg_0]
0x1801253f1  add     rsp, 60h
0x1801253f5  pop     r15
0x1801253f7  pop     r14
0x1801253f9  pop     rdi
0x1801253fa  pop     rsi
0x1801253fb  pop     rbp
0x1801253fc  retn
```
