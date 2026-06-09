# Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::GatherSpecificSubKeys(std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>,HKEY__ *)

- ea: `0x1801262b8`
- end: `0x180126672`
- name: `?GatherSpecificSubKeys@XMLDiagnosticReportGenerator@MDMDiagnostics@MDM@Windows@Microsoft@@AEAAJV?$shared_ptr@VDiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@@std@@PEAUHKEY__@@@Z`
- size: `954`
- prototype: `__int64 __fastcall(Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator *this)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180125a74`

## callees

- `0x180019080`
- `0x180019588`
- `0x18001989c`
- `0x18001a018`
- `0x18001a054`
- `0x1800e6b14`
- `0x1800e734c`
- `0x1800e7de8`
- `0x1800e8508`
- `0x1800ed46c`
- `0x1800edd28`
- `0x1800eef28`
- `0x180124f84`
- `0x1801262b8`
- `0x1801270f0`
- `0x1801272f0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18012639a`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18012639a`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180126375`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180126375`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18012652c`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18012652c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801264bb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801264bb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180126485`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180126485`

## string_xrefs

- `0x18012633d`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\registrytoxml\xmldiagnosticreportgenerator.cpp`
- `0x1801265a3`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\registrytoxml\xmldiagnosticreportgenerator.cpp`

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
    v8 = 295;
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
          v24 = 363;
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
      v24 = 361;
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
      v8 = 377;
      goto LABEL_3;
    }
    std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>(
      v32,
      a2);
    Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::CrawlTree(this);
    v7 = Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::WriteEndElement(this);
    if ( v7 < 0 )
    {
      v8 = 379;
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
0x1801262b8  mov     [rsp-8+arg_18], rbx
0x1801262bd  push    rbp
0x1801262be  push    rsi
0x1801262bf  push    rdi
0x1801262c0  push    r12
0x1801262c2  push    r13
0x1801262c4  push    r14
0x1801262c6  push    r15
0x1801262c8  lea     rbp, [rsp-3C0h]
0x1801262d0  sub     rsp, 4C0h
0x1801262d7  mov     rax, cs:__security_cookie
0x1801262de  xor     rax, rsp
0x1801262e1  mov     [rbp+3F0h+var_40], rax
0x1801262e8  mov     r12, r8
0x1801262eb  mov     rbx, rdx
0x1801262ee  mov     r15, rcx
0x1801262f1  mov     [rsp+4F0h+var_478], rdx
0x1801262f6  xor     r13d, r13d
0x1801262f9  mov     [rsp+4F0h+Context], r13
0x1801262fe  mov     [rsp+4F0h+hKey], r13
0x180126303  mov     rsi, [rdx]
0x180126306  xor     edx, edx; Val
0x180126308  mov     r8d, 208h; Size
0x18012630e  lea     rcx, [rbp+3F0h+Str]; void *
0x180126312  call    memset_0
0x180126317  mov     r8, rsi; unsigned __int16 *
0x18012631a  mov     edx, 103h; unsigned __int64
0x18012631f  lea     rcx, [rbp+3F0h+Str]; unsigned __int16 *
0x180126323  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180126328  mov     edi, eax
0x18012632a  test    eax, eax
0x18012632c  jns     short loc_18012636A
0x18012632e  mov     edx, 127h; void *
0x180126333  mov     rcx, [rbp+3F8h]; this
0x18012633a  mov     r9d, edi; char *
0x18012633d  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180126344  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180126349  nop
0x18012634a  lea     rcx, [rsp+4F0h+hKey]
0x18012634f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180126354  nop
0x180126355  mov     rcx, [rbx+8]; this
0x180126359  test    rcx, rcx
0x18012635c  jz      short loc_180126363
0x18012635e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180126363  mov     eax, edi
0x180126365  jmp     loc_1801265E4
0x18012636a  lea     rdx, asc_1801D5540; "\\*"
0x180126371  lea     rcx, [rbp+3F0h+Str]; Str
0x180126375  call    cs:__imp_wcsstr
0x18012637c  nop     dword ptr [rax+rax+00h]
0x180126381  test    rax, rax
0x180126384  jz      loc_18012660F
0x18012638a  lea     r8, [rsp+4F0h+Context]; Context
0x18012638f  lea     rdx, Delimiter; "*"
0x180126396  lea     rcx, [rbp+3F0h+Str]; String
0x18012639a  call    cs:__imp_wcstok_s
0x1801263a1  nop     dword ptr [rax+rax+00h]
0x1801263a6  mov     r14, rax
0x1801263a9  mov     [rsp+4F0h+Block], r13
0x1801263ae  lea     rax, [rsp+4F0h+Block]
0x1801263b3  mov     [rbp+3F0h+var_470], rax
0x1801263b7  mov     [rbp+3F0h+var_468], 1
0x1801263bb  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1801263bf  mov     rcx, rsi
0x1801263c2  inc     rcx
0x1801263c5  cmp     [r14+rcx*2], r13w
0x1801263ca  jnz     short loc_1801263C2
0x1801263cc  mov     eax, 2
0x1801263d1  mul     rcx
0x1801263d4  cmovb   rax, rsi
0x1801263d8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1801263df  mov     rcx, rax; unsigned __int64
0x1801263e2  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1801263e7  mov     [rsp+4F0h+Block], rax
0x1801263ec  test    rax, rax
0x1801263ef  jnz     short loc_18012641D
0x1801263f1  mov     rcx, rax; Block
0x1801263f4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1801263f9  nop
0x1801263fa  lea     rcx, [rsp+4F0h+hKey]
0x1801263ff  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180126404  nop
0x180126405  mov     rcx, [rbx+8]; this
0x180126409  test    rcx, rcx
0x18012640c  jz      short loc_180126413
0x18012640e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180126413  mov     eax, 8007000Eh
0x180126418  jmp     loc_1801265E4
0x18012641d  mov     rdx, rsi
0x180126420  inc     rdx; N1
0x180126423  cmp     [r14+rdx*2], r13w
0x180126428  jnz     short loc_180126420
0x18012642a  lea     r9, [rdx-1]; N
0x18012642e  mov     r8, r14; S2
0x180126431  mov     rcx, rax; S1
0x180126434  call    _o_wmemcpy_s_0
0x180126439  mov     edi, eax
0x18012643b  test    eax, eax
0x18012643d  jz      short loc_180126459
0x18012643f  jle     short loc_18012644A
0x180126441  movzx   edi, ax
0x180126444  or      edi, 80070000h
0x18012644a  mov     rcx, [rsp+4F0h+Block]; Block
0x18012644f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180126454  jmp     loc_18012634A
0x180126459  inc     rsi
0x18012645c  cmp     [r14+rsi*2], r13w
0x180126461  jnz     short loc_180126459
0x180126463  mov     rax, [rsp+4F0h+Block]
0x180126468  mov     [rax+rsi*2-2], r13w
0x18012646e  mov     rdi, [rsp+4F0h+hKey]
0x180126473  test    rdi, rdi
0x180126476  jz      short loc_18012649B
0x180126478  lea     rcx, [rsp+4F0h+cchName]; this
0x18012647d  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180126482  mov     rcx, rdi; hKey
0x180126485  call    cs:__imp_RegCloseKey
0x18012648c  nop     dword ptr [rax+rax+00h]
0x180126491  lea     rcx, [rsp+4F0h+cchName]; this
0x180126496  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18012649b  mov     [rsp+4F0h+hKey], r13
0x1801264a0  lea     rax, [rsp+4F0h+hKey]
0x1801264a5  mov     [rsp+4F0h+phkResult], rax; phkResult
0x1801264aa  mov     r9d, 20019h; samDesired
0x1801264b0  xor     r8d, r8d; ulOptions
0x1801264b3  mov     rdx, [rsp+4F0h+Block]; lpSubKey
0x1801264b8  mov     rcx, r12; hKey
0x1801264bb  call    cs:__imp_RegOpenKeyExW
0x1801264c2  nop     dword ptr [rax+rax+00h]
0x1801264c7  mov     esi, 80070000h
0x1801264cc  test    eax, eax
0x1801264ce  jle     short loc_1801264D7
0x1801264d0  movzx   eax, ax
0x1801264d3  or      eax, esi
0x1801264d5  test    eax, eax
0x1801264d7  jnz     loc_1801265BE
0x1801264dd  xor     edx, edx; Val
0x1801264df  mov     r8d, 206h; Size
0x1801264e5  lea     rcx, [rbp+3F0h+var_24E]; void *
0x1801264ec  call    memset_0
0x1801264f1  mov     r14d, r13d
0x1801264f4  mov     [rsp+4F0h+cchName], 104h
0x1801264fc  mov     [rbp+3F0h+Name], r13w
0x180126504  mov     [rsp+4F0h+lpftLastWriteTime], r13; lpftLastWriteTime
0x180126509  mov     [rsp+4F0h+lpcchClass], r13; lpcchClass
0x18012650e  mov     [rsp+4F0h+lpClass], r13; lpClass
0x180126513  mov     [rsp+4F0h+phkResult], r13; int
0x180126518  lea     r9, [rsp+4F0h+cchName]; lpcchName
0x18012651d  lea     r8, [rbp+3F0h+Name]; lpName
0x180126524  mov     edx, r14d; dwIndex
0x180126527  mov     rcx, [rsp+4F0h+hKey]; hKey
0x18012652c  call    cs:__imp_RegEnumKeyExW
0x180126533  nop     dword ptr [rax+rax+00h]
0x180126538  test    eax, eax
0x18012653a  jle     short loc_180126543
0x18012653c  movzx   eax, ax
0x18012653f  or      eax, esi
0x180126541  test    eax, eax
0x180126543  jnz     short loc_1801265BE
0x180126545  mov     rdx, [rbx]
0x180126548  add     rdx, 410h; unsigned __int16 *
0x18012654f  mov     rcx, r15; this
0x180126552  call    ?WriteStartElement@XMLDiagnosticReportGenerator@MDMDiagnostics@MDM@Windows@Microsoft@@AEAAJPEBG@Z; Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::WriteStartElement(ushort const *)
0x180126557  mov     edi, eax
0x180126559  test    eax, eax
0x18012655b  js      short loc_18012659E
0x18012655d  mov     r8, [rsp+4F0h+hKey]
0x180126562  mov     rdx, rbx
0x180126565  lea     rcx, [rsp+4F0h+var_488]
0x18012656a  call    ??0?$shared_ptr@VDiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>(std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey> const &)
0x18012656f  lea     r9, [rbp+3F0h+Name]
0x180126576  mov     rdx, rax
0x180126579  mov     rcx, r15; this
0x18012657c  call    ?CrawlTree@XMLDiagnosticReportGenerator@MDMDiagnostics@MDM@Windows@Microsoft@@AEAAJV?$shared_ptr@VDiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@@std@@PEAUHKEY__@@PEAG@Z; Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::CrawlTree(std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>,HKEY__ *,ushort *)
0x180126581  mov     rcx, r15; this
0x180126584  call    ?WriteEndElement@XMLDiagnosticReportGenerator@MDMDiagnostics@MDM@Windows@Microsoft@@AEAAJXZ; Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::WriteEndElement(void)
0x180126589  mov     edi, eax
0x18012658b  test    eax, eax
0x18012658d  js      short loc_180126597
0x18012658f  inc     r14d
0x180126592  jmp     loc_1801264F4
0x180126597  mov     edx, 16Bh
0x18012659c  jmp     short loc_1801265A3
0x18012659e  mov     edx, 169h; void *
0x1801265a3  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1801265aa  mov     r9d, edi; char *
0x1801265ad  mov     rcx, [rbp+3F8h]; this
0x1801265b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801265b9  jmp     loc_18012644A
0x1801265be  mov     rcx, [rsp+4F0h+Block]; Block
0x1801265c3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1801265c8  nop
0x1801265c9  lea     rcx, [rsp+4F0h+hKey]
0x1801265ce  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801265d3  nop
0x1801265d4  mov     rcx, [rbx+8]; this
0x1801265d8  test    rcx, rcx
0x1801265db  jz      short loc_1801265E2
0x1801265dd  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801265e2  xor     eax, eax
0x1801265e4  mov     rcx, [rbp+3F0h+var_40]
0x1801265eb  xor     rcx, rsp; StackCookie
0x1801265ee  call    __security_check_cookie
0x1801265f3  mov     rbx, [rsp+4F0h+arg_18]
0x1801265fb  add     rsp, 4C0h
0x180126602  pop     r15
0x180126604  pop     r14
0x180126606  pop     r13
0x180126608  pop     r12
0x18012660a  pop     rdi
0x18012660b  pop     rsi
0x18012660c  pop     rbp
0x18012660d  retn
0x18012660f  test    rsi, rsi
0x180126612  jz      short loc_1801265C9
0x180126614  mov     rdx, [rbx]
0x180126617  add     rdx, 410h; unsigned __int16 *
0x18012661e  mov     rcx, r15; this
0x180126621  call    ?WriteStartElement@XMLDiagnosticReportGenerator@MDMDiagnostics@MDM@Windows@Microsoft@@AEAAJPEBG@Z; Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::WriteStartElement(ushort const *)
0x180126626  mov     edi, eax
0x180126628  test    eax, eax
0x18012662a  jns     short loc_180126636
0x18012662c  mov     edx, 179h
0x180126631  jmp     loc_180126333
0x180126636  mov     rdx, rbx
0x180126639  lea     rcx, [rsp+4F0h+var_488]
0x18012663e  call    ??0?$shared_ptr@VDiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>(std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey> const &)
0x180126643  lea     r9, [rbp+3F0h+Str]
0x180126647  mov     r8, r12
0x18012664a  mov     rdx, rax
0x18012664d  mov     rcx, r15; this
0x180126650  call    ?CrawlTree@XMLDiagnosticReportGenerator@MDMDiagnostics@MDM@Windows@Microsoft@@AEAAJV?$shared_ptr@VDiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@@std@@PEAUHKEY__@@PEAG@Z; Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::CrawlTree(std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>,HKEY__ *,ushort *)
0x180126655  mov     rcx, r15; this
0x180126658  call    ?WriteEndElement@XMLDiagnosticReportGenerator@MDMDiagnostics@MDM@Windows@Microsoft@@AEAAJXZ; Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticReportGenerator::WriteEndElement(void)
0x18012665d  mov     edi, eax
0x18012665f  test    eax, eax
0x180126661  jns     loc_1801265C9
0x180126667  mov     edx, 17Bh
0x18012666c  jmp     loc_180126333
```
