# Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::GetChildKeyData(std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>,HKEY__ *,ushort *)

- ea: `0x180124e58`
- end: `0x180125168`
- name: `?GetChildKeyData@XMLDiagnosticReportGenerator@MDMDiagnostics@MDM@Windows@Microsoft@@AEAAJV?$shared_ptr@VDiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@@std@@PEAUHKEY__@@PEAG@Z`
- size: `784`
- prototype: `__int64 __fastcall(Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator *this, __int64, HKEY, wchar_t *)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180125404`

## callees

- `0x180019000`
- `0x180019508`
- `0x18001981c`
- `0x180019fc4`
- `0x1800e691c`
- `0x1800e7124`
- `0x1800e7c08`
- `0x1800e82e4`
- `0x1800ece5c`
- `0x1800ed690`
- `0x1800ee898`
- `0x18012347c`
- `0x180124e58`
- `0x180125698`
- `0x1801256fc`
- `0x1801258f8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x180124ec8`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x180124ec8`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18012509e`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18012509e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180124fff`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180124fff`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180124fcb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180124fcb`

## string_xrefs

- `0x180124ef3`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\registrytoxml\xmldiagnosticreportgenerator.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::GetChildKeyData(
        Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator *this,
        __int64 a2,
        HKEY a3,
        wchar_t *a4)
{
  const unsigned __int16 *v7; // rsi
  unsigned __int64 v8; // rdx
  signed int v9; // ebx
  __int64 v10; // rdx
  std::_Ref_count_base *v11; // rcx
  unsigned __int64 v13; // rbx
  unsigned __int64 v14; // rax
  void *v15; // rax
  std::_Ref_count_base *v16; // rcx
  LSTATUS v17; // eax
  std::_Ref_count_base *v18; // rcx
  DWORD i; // esi
  LSTATUS v20; // eax
  bool v21; // zf
  std::_Ref_count_base *v22; // rcx
  int phkResult; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  void *Block; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int64 v26; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cchName; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t *Context[3]; // [rsp+60h] [rbp-A0h] BYREF
  char v29; // [rsp+78h] [rbp-88h]
  _BYTE v30[16]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR Name; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v32[526]; // [rsp+92h] [rbp-6Eh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2E8h] [rbp+1E8h]

  Context[1] = (wchar_t *)a2;
  hKey = 0;
  Context[0] = 0;
  Block = 0;
  Context[2] = (wchar_t *)&Block;
  v29 = 1;
  v7 = wcstok_s(a4, L"*", Context) + 5;
  v26 = 0;
  v9 = StringCchLengthW(v7, v8, &v26);
  if ( v9 < 0 )
  {
    v10 = 168;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\registrytoxml\\xmldiagnosticreportgenerator.cpp",
      (const char *)(unsigned int)v9,
      phkResult);
    operator delete(Block);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    v11 = *(std::_Ref_count_base **)(a2 + 8);
    if ( v11 )
      std::_Ref_count_base::_Decref(v11);
    return (unsigned int)v9;
  }
  v13 = v26;
  v14 = 2 * v26;
  if ( !is_mul_ok(v26, 2u) )
    v14 = -1;
  v15 = operator new[](v14, (const struct std::nothrow_t *)std::nothrow);
  Block = v15;
  if ( v15 )
  {
    v9 = StringCchCopyNW((unsigned __int16 *)v15, v13, v7, v13 - 1);
    if ( v9 < 0 )
    {
      v10 = 180;
      goto LABEL_3;
    }
    hKey = 0;
    v17 = RegOpenKeyExW(a3, (LPCWSTR)Block, 0, 0x20019u, &hKey);
    v9 = v17;
    if ( v17 > 0 )
      v9 = (unsigned __int16)v17 | 0x80070000;
    if ( v9 >= 0 )
    {
      memset_0(v32, 0, 0x206u);
      for ( i = 0; ; ++i )
      {
        cchName = 260;
        Name = 0;
        v20 = RegEnumKeyExW(hKey, i, &Name, &cchName, 0, 0, 0, 0);
        v21 = v20 == 0;
        if ( v20 > 0 )
          v21 = 0;
        if ( !v21 )
          break;
        v9 = Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::WriteStartElement(
               this,
               (const unsigned __int16 *)(*(_QWORD *)a2 + 1040LL));
        if ( v9 < 0 )
        {
          v10 = 214;
          goto LABEL_3;
        }
        std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>(
          v30,
          a2);
        v9 = Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::CrawlTree(this);
        if ( v9 < 0 )
        {
          v10 = 215;
          goto LABEL_3;
        }
        v9 = Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::WriteEndElement(this);
        if ( v9 < 0 )
        {
          v10 = 216;
          goto LABEL_3;
        }
      }
      operator delete(Block);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      v22 = *(std::_Ref_count_base **)(a2 + 8);
      if ( v22 )
        std::_Ref_count_base::_Decref(v22);
      return 0;
    }
    else
    {
      if ( v9 != -2147024894 )
      {
        v10 = 187;
        goto LABEL_3;
      }
      operator delete(Block);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      v18 = *(std::_Ref_count_base **)(a2 + 8);
      if ( v18 )
        std::_Ref_count_base::_Decref(v18);
      return 2147942402LL;
    }
  }
  else
  {
    operator delete(0);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    v16 = *(std::_Ref_count_base **)(a2 + 8);
    if ( v16 )
      std::_Ref_count_base::_Decref(v16);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180124e58  push    rbp
0x180124e5a  push    rbx
0x180124e5b  push    rsi
0x180124e5c  push    rdi
0x180124e5d  push    r14
0x180124e5f  push    r15
0x180124e61  lea     rbp, [rsp-1B8h]
0x180124e69  sub     rsp, 2B8h
0x180124e70  mov     rax, cs:__security_cookie
0x180124e77  xor     rax, rsp
0x180124e7a  mov     [rbp+1E0h+var_40], rax
0x180124e81  mov     r15, r8
0x180124e84  mov     rdi, rdx
0x180124e87  mov     r14, rcx
0x180124e8a  mov     [rsp+2E0h+var_278], rdx
0x180124e8f  mov     [rsp+2E0h+hKey], 0
0x180124e98  mov     [rsp+2E0h+Context], 0
0x180124ea1  mov     [rsp+2E0h+Block], 0
0x180124eaa  lea     rax, [rsp+2E0h+Block]
0x180124eaf  mov     [rsp+2E0h+var_270], rax
0x180124eb4  mov     [rsp+2E0h+var_268], 1
0x180124eb9  lea     r8, [rsp+2E0h+Context]; Context
0x180124ebe  lea     rdx, Delimiter; "*"
0x180124ec5  mov     rcx, r9; String
0x180124ec8  call    cs:__imp_wcstok_s
0x180124ece  lea     rsi, [rax+0Ah]
0x180124ed2  mov     [rsp+2E0h+var_290], 0
0x180124edb  lea     r8, [rsp+2E0h+var_290]; unsigned __int64 *
0x180124ee0  mov     rcx, rsi; unsigned __int16 *
0x180124ee3  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180124ee8  mov     ebx, eax
0x180124eea  test    eax, eax
0x180124eec  jns     short loc_180124F35
0x180124eee  mov     edx, 0A8h; void *
0x180124ef3  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180124efa  mov     r9d, ebx; char *
0x180124efd  mov     rcx, [rbp+1E8h]; this
0x180124f04  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180124f09  nop
0x180124f0a  mov     rcx, [rsp+2E0h+Block]; Block
0x180124f0f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180124f14  nop
0x180124f15  lea     rcx, [rsp+2E0h+hKey]
0x180124f1a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180124f1f  nop
0x180124f20  mov     rcx, [rdi+8]; this
0x180124f24  test    rcx, rcx
0x180124f27  jz      short loc_180124F2E
0x180124f29  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180124f2e  mov     eax, ebx
0x180124f30  jmp     loc_180125149
0x180124f35  mov     eax, 2
0x180124f3a  mov     rbx, [rsp+2E0h+var_290]
0x180124f3f  mul     rbx
0x180124f42  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180124f49  cmovb   rax, rcx
0x180124f4d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180124f54  mov     rcx, rax; unsigned __int64
0x180124f57  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180124f5c  mov     [rsp+2E0h+Block], rax
0x180124f61  test    rax, rax
0x180124f64  jnz     short loc_180124F92
0x180124f66  mov     rcx, rax; Block
0x180124f69  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180124f6e  nop
0x180124f6f  lea     rcx, [rsp+2E0h+hKey]
0x180124f74  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180124f79  nop
0x180124f7a  mov     rcx, [rdi+8]; this
0x180124f7e  test    rcx, rcx
0x180124f81  jz      short loc_180124F88
0x180124f83  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180124f88  mov     eax, 8007000Eh
0x180124f8d  jmp     loc_180125149
0x180124f92  lea     r9, [rbx-1]; unsigned __int64
0x180124f96  mov     r8, rsi; unsigned __int16 *
0x180124f99  mov     rdx, rbx; unsigned __int64
0x180124f9c  mov     rcx, rax; unsigned __int16 *
0x180124f9f  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180124fa4  mov     ebx, eax
0x180124fa6  test    eax, eax
0x180124fa8  jns     short loc_180124FB4
0x180124faa  mov     edx, 0B4h
0x180124faf  jmp     loc_180124EF3
0x180124fb4  mov     rbx, [rsp+2E0h+hKey]
0x180124fb9  test    rbx, rbx
0x180124fbc  jz      short loc_180124FDB
0x180124fbe  lea     rcx, [rsp+2E0h+var_290]; this
0x180124fc3  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180124fc8  mov     rcx, rbx; hKey
0x180124fcb  call    cs:__imp_RegCloseKey
0x180124fd1  lea     rcx, [rsp+2E0h+var_290]; this
0x180124fd6  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180124fdb  mov     [rsp+2E0h+hKey], 0
0x180124fe4  lea     rax, [rsp+2E0h+hKey]
0x180124fe9  mov     [rsp+2E0h+phkResult], rax; phkResult
0x180124fee  mov     r9d, 20019h; samDesired
0x180124ff4  xor     r8d, r8d; ulOptions
0x180124ff7  mov     rdx, [rsp+2E0h+Block]; lpSubKey
0x180124ffc  mov     rcx, r15; hKey
0x180124fff  call    cs:__imp_RegOpenKeyExW
0x180125005  mov     ebx, eax
0x180125007  mov     r15d, 80070000h
0x18012500d  test    eax, eax
0x18012500f  jle     short loc_180125017
0x180125011  movzx   ebx, ax
0x180125014  or      ebx, r15d
0x180125017  test    ebx, ebx
0x180125019  jns     short loc_180125059
0x18012501b  mov     esi, 80070002h
0x180125020  cmp     ebx, esi
0x180125022  jnz     short loc_18012504F
0x180125024  mov     rcx, [rsp+2E0h+Block]; Block
0x180125029  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18012502e  nop
0x18012502f  lea     rcx, [rsp+2E0h+hKey]
0x180125034  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180125039  nop
0x18012503a  mov     rcx, [rdi+8]; this
0x18012503e  test    rcx, rcx
0x180125041  jz      short loc_180125048
0x180125043  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180125048  mov     eax, esi
0x18012504a  jmp     loc_180125149
0x18012504f  mov     edx, 0BBh
0x180125054  jmp     loc_180124EF3
0x180125059  xor     edx, edx; Val
0x18012505b  mov     r8d, 206h; Size
0x180125061  lea     rcx, [rbp+1E0h+var_24E]; void *
0x180125065  call    memset_0
0x18012506a  xor     esi, esi
0x18012506c  mov     [rsp+2E0h+cchName], 104h
0x180125074  xor     eax, eax
0x180125076  mov     [rbp+1E0h+Name], ax
0x18012507a  mov     [rsp+2E0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x18012507f  mov     [rsp+2E0h+lpcchClass], rax; lpcchClass
0x180125084  mov     [rsp+2E0h+lpClass], rax; lpClass
0x180125089  mov     [rsp+2E0h+phkResult], rax; lpReserved
0x18012508e  lea     r9, [rsp+2E0h+cchName]; lpcchName
0x180125093  lea     r8, [rbp+1E0h+Name]; lpName
0x180125097  mov     edx, esi; dwIndex
0x180125099  mov     rcx, [rsp+2E0h+hKey]; hKey
0x18012509e  call    cs:__imp_RegEnumKeyExW
0x1801250a4  test    eax, eax
0x1801250a6  jle     short loc_1801250B0
0x1801250a8  movzx   eax, ax
0x1801250ab  or      eax, r15d
0x1801250ae  test    eax, eax
0x1801250b0  jnz     short loc_180125123
0x1801250b2  mov     rdx, [rdi]
0x1801250b5  add     rdx, 410h; unsigned __int16 *
0x1801250bc  mov     rcx, r14; this
0x1801250bf  call    ?WriteStartElement@XMLDiagnosticReportGenerator@MDMDiagnostics@MDM@Windows@Microsoft@@AEAAJPEBG@Z; Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::WriteStartElement(ushort const *)
0x1801250c4  mov     ebx, eax
0x1801250c6  test    eax, eax
0x1801250c8  js      short loc_180125119
0x1801250ca  mov     r8, [rsp+2E0h+hKey]
0x1801250cf  mov     rdx, rdi
0x1801250d2  lea     rcx, [rbp+1E0h+var_260]
0x1801250d6  call    ??0?$shared_ptr@VDiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>(std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey> const &)
0x1801250db  lea     r9, [rbp+1E0h+Name]
0x1801250df  mov     rdx, rax
0x1801250e2  mov     rcx, r14; this
0x1801250e5  call    ?CrawlTree@XMLDiagnosticReportGenerator@MDMDiagnostics@MDM@Windows@Microsoft@@AEAAJV?$shared_ptr@VDiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@@std@@PEAUHKEY__@@PEAG@Z; Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::CrawlTree(std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>,HKEY__ *,ushort *)
0x1801250ea  mov     ebx, eax
0x1801250ec  test    eax, eax
0x1801250ee  js      short loc_18012510F
0x1801250f0  mov     rcx, r14; this
0x1801250f3  call    ?WriteEndElement@XMLDiagnosticReportGenerator@MDMDiagnostics@MDM@Windows@Microsoft@@AEAAJXZ; Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::WriteEndElement(void)
0x1801250f8  mov     ebx, eax
0x1801250fa  test    eax, eax
0x1801250fc  js      short loc_180125105
0x1801250fe  inc     esi
0x180125100  jmp     loc_18012506C
0x180125105  mov     edx, 0D8h
0x18012510a  jmp     loc_180124EF3
0x18012510f  mov     edx, 0D7h
0x180125114  jmp     loc_180124EF3
0x180125119  mov     edx, 0D6h
0x18012511e  jmp     loc_180124EF3
0x180125123  mov     rcx, [rsp+2E0h+Block]; Block
0x180125128  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18012512d  nop
0x18012512e  lea     rcx, [rsp+2E0h+hKey]
0x180125133  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180125138  nop
0x180125139  mov     rcx, [rdi+8]; this
0x18012513d  test    rcx, rcx
0x180125140  jz      short loc_180125147
0x180125142  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180125147  xor     eax, eax
0x180125149  mov     rcx, [rbp+1E0h+var_40]
0x180125150  xor     rcx, rsp; StackCookie
0x180125153  call    __security_check_cookie
0x180125158  add     rsp, 2B8h
0x18012515f  pop     r15
0x180125161  pop     r14
0x180125163  pop     rdi
0x180125164  pop     rsi
0x180125165  pop     rbx
0x180125166  pop     rbp
0x180125167  retn
```
