# Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::GetChildKeyData(std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>,HKEY__ *,ushort *)

- ea: `0x18012680c`
- end: `0x180126b35`
- name: `?GetChildKeyData@XMLDiagnosticReportGenerator@MDMDiagnostics@MDM@Windows@Microsoft@@AEAAJV?$shared_ptr@VDiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@@std@@PEAUHKEY__@@PEAG@Z`
- size: `809`
- prototype: `__int64 __fastcall(Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator *this)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180126ddc`

## callees

- `0x180019080`
- `0x180019588`
- `0x18001989c`
- `0x18001a054`
- `0x1800e6b14`
- `0x1800e734c`
- `0x1800e7de8`
- `0x1800e8508`
- `0x1800ed46c`
- `0x1800edcd4`
- `0x1800eef28`
- `0x180124f84`
- `0x18012680c`
- `0x18012708c`
- `0x1801270f0`
- `0x1801272f0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18012687c`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18012687c`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180126a64`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180126a64`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801269bf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801269bf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180126985`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180126985`

## string_xrefs

- `0x1801268ad`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\registrytoxml\xmldiagnosticreportgenerator.cpp`

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
    v10 = 167;
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
      v10 = 179;
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
          v10 = 213;
          goto LABEL_3;
        }
        std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>(
          v30,
          a2);
        v9 = Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::CrawlTree(this);
        if ( v9 < 0 )
        {
          v10 = 214;
          goto LABEL_3;
        }
        v9 = Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::WriteEndElement(this);
        if ( v9 < 0 )
        {
          v10 = 215;
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
        v10 = 186;
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
0x18012680c  push    rbp
0x18012680e  push    rbx
0x18012680f  push    rsi
0x180126810  push    rdi
0x180126811  push    r14
0x180126813  push    r15
0x180126815  lea     rbp, [rsp-1B8h]
0x18012681d  sub     rsp, 2B8h
0x180126824  mov     rax, cs:__security_cookie
0x18012682b  xor     rax, rsp
0x18012682e  mov     [rbp+1E0h+var_40], rax
0x180126835  mov     r15, r8
0x180126838  mov     rdi, rdx
0x18012683b  mov     r14, rcx
0x18012683e  mov     [rsp+2E0h+var_278], rdx
0x180126843  mov     [rsp+2E0h+hKey], 0
0x18012684c  mov     [rsp+2E0h+Context], 0
0x180126855  mov     [rsp+2E0h+Block], 0
0x18012685e  lea     rax, [rsp+2E0h+Block]
0x180126863  mov     [rsp+2E0h+var_270], rax
0x180126868  mov     [rsp+2E0h+var_268], 1
0x18012686d  lea     r8, [rsp+2E0h+Context]; Context
0x180126872  lea     rdx, Delimiter; "*"
0x180126879  mov     rcx, r9; String
0x18012687c  call    cs:__imp_wcstok_s
0x180126883  nop     dword ptr [rax+rax+00h]
0x180126888  lea     rsi, [rax+0Ah]
0x18012688c  mov     [rsp+2E0h+var_290], 0
0x180126895  lea     r8, [rsp+2E0h+var_290]; unsigned __int64 *
0x18012689a  mov     rcx, rsi; unsigned __int16 *
0x18012689d  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1801268a2  mov     ebx, eax
0x1801268a4  test    eax, eax
0x1801268a6  jns     short loc_1801268EF
0x1801268a8  mov     edx, 0A7h; void *
0x1801268ad  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1801268b4  mov     r9d, ebx; char *
0x1801268b7  mov     rcx, [rbp+1E8h]; this
0x1801268be  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801268c3  nop
0x1801268c4  mov     rcx, [rsp+2E0h+Block]; Block
0x1801268c9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1801268ce  nop
0x1801268cf  lea     rcx, [rsp+2E0h+hKey]
0x1801268d4  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801268d9  nop
0x1801268da  mov     rcx, [rdi+8]; this
0x1801268de  test    rcx, rcx
0x1801268e1  jz      short loc_1801268E8
0x1801268e3  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801268e8  mov     eax, ebx
0x1801268ea  jmp     loc_180126B15
0x1801268ef  mov     eax, 2
0x1801268f4  mov     rbx, [rsp+2E0h+var_290]
0x1801268f9  mul     rbx
0x1801268fc  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180126903  cmovb   rax, rcx
0x180126907  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18012690e  mov     rcx, rax; unsigned __int64
0x180126911  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180126916  mov     [rsp+2E0h+Block], rax
0x18012691b  test    rax, rax
0x18012691e  jnz     short loc_18012694C
0x180126920  mov     rcx, rax; Block
0x180126923  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180126928  nop
0x180126929  lea     rcx, [rsp+2E0h+hKey]
0x18012692e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180126933  nop
0x180126934  mov     rcx, [rdi+8]; this
0x180126938  test    rcx, rcx
0x18012693b  jz      short loc_180126942
0x18012693d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180126942  mov     eax, 8007000Eh
0x180126947  jmp     loc_180126B15
0x18012694c  lea     r9, [rbx-1]; unsigned __int64
0x180126950  mov     r8, rsi; unsigned __int16 *
0x180126953  mov     rdx, rbx; unsigned __int64
0x180126956  mov     rcx, rax; unsigned __int16 *
0x180126959  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18012695e  mov     ebx, eax
0x180126960  test    eax, eax
0x180126962  jns     short loc_18012696E
0x180126964  mov     edx, 0B3h
0x180126969  jmp     loc_1801268AD
0x18012696e  mov     rbx, [rsp+2E0h+hKey]
0x180126973  test    rbx, rbx
0x180126976  jz      short loc_18012699B
0x180126978  lea     rcx, [rsp+2E0h+var_290]; this
0x18012697d  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180126982  mov     rcx, rbx; hKey
0x180126985  call    cs:__imp_RegCloseKey
0x18012698c  nop     dword ptr [rax+rax+00h]
0x180126991  lea     rcx, [rsp+2E0h+var_290]; this
0x180126996  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18012699b  mov     [rsp+2E0h+hKey], 0
0x1801269a4  lea     rax, [rsp+2E0h+hKey]
0x1801269a9  mov     [rsp+2E0h+phkResult], rax; phkResult
0x1801269ae  mov     r9d, 20019h; samDesired
0x1801269b4  xor     r8d, r8d; ulOptions
0x1801269b7  mov     rdx, [rsp+2E0h+Block]; lpSubKey
0x1801269bc  mov     rcx, r15; hKey
0x1801269bf  call    cs:__imp_RegOpenKeyExW
0x1801269c6  nop     dword ptr [rax+rax+00h]
0x1801269cb  mov     ebx, eax
0x1801269cd  mov     r15d, 80070000h
0x1801269d3  test    eax, eax
0x1801269d5  jle     short loc_1801269DD
0x1801269d7  movzx   ebx, ax
0x1801269da  or      ebx, r15d
0x1801269dd  test    ebx, ebx
0x1801269df  jns     short loc_180126A1F
0x1801269e1  mov     esi, 80070002h
0x1801269e6  cmp     ebx, esi
0x1801269e8  jnz     short loc_180126A15
0x1801269ea  mov     rcx, [rsp+2E0h+Block]; Block
0x1801269ef  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1801269f4  nop
0x1801269f5  lea     rcx, [rsp+2E0h+hKey]
0x1801269fa  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801269ff  nop
0x180126a00  mov     rcx, [rdi+8]; this
0x180126a04  test    rcx, rcx
0x180126a07  jz      short loc_180126A0E
0x180126a09  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180126a0e  mov     eax, esi
0x180126a10  jmp     loc_180126B15
0x180126a15  mov     edx, 0BAh
0x180126a1a  jmp     loc_1801268AD
0x180126a1f  xor     edx, edx; Val
0x180126a21  mov     r8d, 206h; Size
0x180126a27  lea     rcx, [rbp+1E0h+var_24E]; void *
0x180126a2b  call    memset_0
0x180126a30  xor     esi, esi
0x180126a32  mov     [rsp+2E0h+cchName], 104h
0x180126a3a  xor     eax, eax
0x180126a3c  mov     [rbp+1E0h+Name], ax
0x180126a40  mov     [rsp+2E0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180126a45  mov     [rsp+2E0h+lpcchClass], rax; lpcchClass
0x180126a4a  mov     [rsp+2E0h+lpClass], rax; lpClass
0x180126a4f  mov     [rsp+2E0h+phkResult], rax; lpReserved
0x180126a54  lea     r9, [rsp+2E0h+cchName]; lpcchName
0x180126a59  lea     r8, [rbp+1E0h+Name]; lpName
0x180126a5d  mov     edx, esi; dwIndex
0x180126a5f  mov     rcx, [rsp+2E0h+hKey]; hKey
0x180126a64  call    cs:__imp_RegEnumKeyExW
0x180126a6b  nop     dword ptr [rax+rax+00h]
0x180126a70  test    eax, eax
0x180126a72  jle     short loc_180126A7C
0x180126a74  movzx   eax, ax
0x180126a77  or      eax, r15d
0x180126a7a  test    eax, eax
0x180126a7c  jnz     short loc_180126AEF
0x180126a7e  mov     rdx, [rdi]
0x180126a81  add     rdx, 410h; unsigned __int16 *
0x180126a88  mov     rcx, r14; this
0x180126a8b  call    ?WriteStartElement@XMLDiagnosticReportGenerator@MDMDiagnostics@MDM@Windows@Microsoft@@AEAAJPEBG@Z; Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::WriteStartElement(ushort const *)
0x180126a90  mov     ebx, eax
0x180126a92  test    eax, eax
0x180126a94  js      short loc_180126AE5
0x180126a96  mov     r8, [rsp+2E0h+hKey]
0x180126a9b  mov     rdx, rdi
0x180126a9e  lea     rcx, [rbp+1E0h+var_260]
0x180126aa2  call    ??0?$shared_ptr@VDiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>(std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey> const &)
0x180126aa7  lea     r9, [rbp+1E0h+Name]
0x180126aab  mov     rdx, rax
0x180126aae  mov     rcx, r14; this
0x180126ab1  call    ?CrawlTree@XMLDiagnosticReportGenerator@MDMDiagnostics@MDM@Windows@Microsoft@@AEAAJV?$shared_ptr@VDiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@@std@@PEAUHKEY__@@PEAG@Z; Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::CrawlTree(std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>,HKEY__ *,ushort *)
0x180126ab6  mov     ebx, eax
0x180126ab8  test    eax, eax
0x180126aba  js      short loc_180126ADB
0x180126abc  mov     rcx, r14; this
0x180126abf  call    ?WriteEndElement@XMLDiagnosticReportGenerator@MDMDiagnostics@MDM@Windows@Microsoft@@AEAAJXZ; Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::WriteEndElement(void)
0x180126ac4  mov     ebx, eax
0x180126ac6  test    eax, eax
0x180126ac8  js      short loc_180126AD1
0x180126aca  inc     esi
0x180126acc  jmp     loc_180126A32
0x180126ad1  mov     edx, 0D7h
0x180126ad6  jmp     loc_1801268AD
0x180126adb  mov     edx, 0D6h
0x180126ae0  jmp     loc_1801268AD
0x180126ae5  mov     edx, 0D5h
0x180126aea  jmp     loc_1801268AD
0x180126aef  mov     rcx, [rsp+2E0h+Block]; Block
0x180126af4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180126af9  nop
0x180126afa  lea     rcx, [rsp+2E0h+hKey]
0x180126aff  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180126b04  nop
0x180126b05  mov     rcx, [rdi+8]; this
0x180126b09  test    rcx, rcx
0x180126b0c  jz      short loc_180126B13
0x180126b0e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180126b13  xor     eax, eax
0x180126b15  mov     rcx, [rbp+1E0h+var_40]
0x180126b1c  xor     rcx, rsp; StackCookie
0x180126b1f  call    __security_check_cookie
0x180126b24  add     rsp, 2B8h
0x180126b2b  pop     r15
0x180126b2d  pop     r14
0x180126b2f  pop     rdi
0x180126b30  pop     rsi
0x180126b31  pop     rbx
0x180126b32  pop     rbp
0x180126b33  retn
```
