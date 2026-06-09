# Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticDataInputParser::ParseElement(ulong *)

- ea: `0x1801248b4`
- end: `0x180124c07`
- name: `?ParseElement@XMLDiagnosticDataInputParser@MDMDiagnostics@MDM@Windows@Microsoft@@AEAAJPEAK@Z`
- size: `851`
- prototype: `__int64 __fastcall(Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticDataInputParser *__hidden this, unsigned int *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180124ce0`

## callees

- `0x1800e6b14`
- `0x1800ed46c`
- `0x1800eef28`
- `0x1800fa810`
- `0x1801242b8`
- `0x18012430c`
- `0x1801245a4`
- `0x180124790`
- `0x1801248b4`
- `0x180127350`
- `0x1801273c0`
- `0x180127430`
- `0x180193010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18012491a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180124a40`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180124a70`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180124a95`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180124aba`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180124b7f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180124ba8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180124bd7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18012491a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180124a40`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180124a70`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180124a95`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180124aba`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180124b7f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180124ba8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180124bd7`

## string_xrefs

- `0x1801248f3`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\registrytoxml\xmldiagnosticdatainputparser.cpp`
- `0x18012498f`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\registrytoxml\xmldiagnosticdatainputparser.cpp`
- `0x180124b2a`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\registrytoxml\xmldiagnosticdatainputparser.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticDataInputParser::ParseElement(
        Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticDataInputParser *this,
        unsigned int *a2)
{
  int Attributes; // ebx
  __int64 v5; // rdx
  __int64 v7; // rax
  char *v8; // r14
  const char *v9; // r9
  int v10; // eax
  __int64 v11; // rbx
  std::_Ref_count_base *v12; // rcx
  __int64 v13; // rax
  __int64 v14; // r8
  __int64 v15; // rax
  const char *v16; // r9
  int v17; // eax
  std::_Ref_count_base *v18[2]; // [rsp+20h] [rbp-38h] BYREF
  _BYTE v19[8]; // [rsp+30h] [rbp-28h] BYREF
  std::_Ref_count_base *v20; // [rsp+38h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  unsigned int v22; // [rsp+60h] [rbp+8h]
  __int64 v23; // [rsp+70h] [rbp+18h] BYREF

  v23 = 0;
  Attributes = (*(__int64 (__fastcall **)(_QWORD, __int64 *, _QWORD))(**((_QWORD **)this + 3) + 112LL))(
                 *((_QWORD *)this + 3),
                 &v23,
                 0);
  if ( Attributes < 0 )
  {
    v5 = 81;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\registrytoxml\\xmldiagnosticdatainputparser.cpp",
      (const char *)(unsigned int)Attributes,
      (int)v18[0]);
    return (unsigned int)Attributes;
  }
  if ( !(unsigned int)_o__wcsicmp(v23, L"Key") )
  {
    ++*a2;
    *(_OWORD *)v18 = 0;
    try
    {
      v7 = std::make_shared<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey,>();
      std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::operator=(
        v18,
        v7);
      if ( v20 )
        std::_Ref_count_base::_Decref(v20);
      v8 = (char *)this + 32;
      std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>(
        v19,
        v18);
    }
    catch ( ... )
    {
      v22 = wil::details::in1diag3::Return_CaughtException(
              retaddr,
              (void *)0x5E,
              (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\registrytoxml\\xmldiagnosticdatainputparser.cpp",
              v9);
      goto LABEL_19;
    }
    v10 = Microsoft::Windows::MDM::MDMDiagnostics::DiagKey::AddChildKey();
    Attributes = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x61,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\registrytoxml\\xmldiagnosticdatainputparser.cpp",
        (const char *)(unsigned int)v10,
        (int)v18[0]);
      goto LABEL_12;
    }
    v11 = std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>(
            v19,
            v8);
    std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>::operator=((char *)v18[0] + 1608, v11);
    v12 = *(std::_Ref_count_base **)(v11 + 8);
    if ( v12 )
      std::_Ref_count_base::_Decref(v12);
    std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>::operator=(v8, v18);
    if ( *a2 == 1 )
    {
      v13 = std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>(
              v19,
              v8);
      Microsoft::Windows::MDM::MDMDiagnostics::DiagData::AddKey(v14, v13);
    }
LABEL_37:
    if ( v18[1] )
      std::_Ref_count_base::_Decref(v18[1]);
    return 0;
  }
  if ( !(unsigned int)_o__wcsicmp(v23, L"Path") )
  {
    *((_DWORD *)this + 16) = 0;
    return 0;
  }
  if ( !(unsigned int)_o__wcsicmp(v23, L"Representation") )
  {
    *((_DWORD *)this + 16) = 2;
    return 0;
  }
  if ( !(unsigned int)_o__wcsicmp(v23, L"Category") )
  {
    *((_DWORD *)this + 16) = 1;
    return 0;
  }
  if ( (unsigned int)_o__wcsicmp(v23, L"Value") )
  {
    if ( (unsigned int)_o__wcsicmp(v23, L"Name") )
    {
      if ( (unsigned int)_o__wcsicmp(v23, L"ValueRepresentation") )
      {
        if ( !(unsigned int)_o__wcsicmp(v23, L"DataSource") )
        {
          Attributes = Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticDataInputParser::ExtractAttributes(this);
          if ( Attributes < 0 )
          {
            v5 = 159;
            goto LABEL_3;
          }
        }
      }
      else
      {
        *((_DWORD *)this + 16) = 4;
        *((_DWORD *)this + 17) = 1;
      }
    }
    else
    {
      *((_QWORD *)this + 8) = 4;
    }
    return 0;
  }
  *(_OWORD *)v18 = 0;
  try
  {
    v15 = std::make_shared<Microsoft::Windows::MDM::MDMDiagnostics::DiagValue,>(v19);
    std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::operator=(
      v18,
      v15);
    if ( v20 )
      std::_Ref_count_base::_Decref(v20);
    std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>(
      v19,
      v18);
  }
  catch ( ... )
  {
    v22 = wil::details::in1diag3::Return_CaughtException(
            retaddr,
            (void *)0x87,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\registrytoxml\\xmldiagnosticdatainputparser.cpp",
            v16);
LABEL_19:
    if ( v18[1] )
      std::_Ref_count_base::_Decref(v18[1]);
    return v22;
  }
  v17 = Microsoft::Windows::MDM::MDMDiagnostics::DiagKey::AddValue();
  Attributes = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8A,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\registrytoxml\\xmldiagnosticdatainputparser.cpp",
      (const char *)(unsigned int)v17,
      (int)v18[0]);
LABEL_12:
    if ( v18[1] )
      std::_Ref_count_base::_Decref(v18[1]);
    return (unsigned int)Attributes;
  }
  std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>::operator=((char *)this + 48, v18);
  *((_DWORD *)this + 16) = 4;
  goto LABEL_37;
}

```

## disassembly

```asm
0x1801248b4  mov     [rsp+arg_8], rbx
0x1801248b9  push    rsi
0x1801248ba  push    rdi
0x1801248bb  push    r14
0x1801248bd  sub     rsp, 40h
0x1801248c1  mov     rsi, rdx
0x1801248c4  mov     rdi, rcx
0x1801248c7  mov     [rsp+58h+arg_10], 0
0x1801248d0  mov     rcx, [rcx+18h]
0x1801248d4  mov     rax, [rcx]
0x1801248d7  xor     r8d, r8d
0x1801248da  lea     rdx, [rsp+58h+arg_10]
0x1801248df  mov     rax, [rax+70h]
0x1801248e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801248e8  mov     ebx, eax
0x1801248ea  test    eax, eax
0x1801248ec  jns     short loc_18012490E
0x1801248ee  mov     edx, 51h ; 'Q'; void *
0x1801248f3  lea     r8, aOnecoreuapAdmi_27; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1801248fa  mov     r9d, ebx; char *
0x1801248fd  mov     rcx, [rsp+58h]; this
0x180124902  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180124907  mov     eax, ebx
0x180124909  jmp     loc_180124A55
0x18012490e  lea     rdx, aKey; "Key"
0x180124915  mov     rcx, [rsp+58h+arg_10]
0x18012491a  call    cs:__imp__o__wcsicmp
0x180124921  nop     dword ptr [rax+rax+00h]
0x180124926  test    eax, eax
0x180124928  jnz     loc_180124A34
0x18012492e  inc     dword ptr [rsi]
0x180124930  xorps   xmm0, xmm0
0x180124933  movdqu  xmmword ptr [rsp+58h+var_38], xmm0; int
0x180124939  lea     rcx, [rsp+58h+var_28]
0x18012493e  call    ??$make_shared@VDiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@$$V@std@@YA?AV?$shared_ptr@VDiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@@0@XZ; std::make_shared<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey,>(void)
0x180124943  mov     rdx, rax
0x180124946  lea     rcx, [rsp+58h+var_38]
0x18012494b  call    ??4?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::operator=(std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>> &&)
0x180124950  mov     rcx, [rsp+58h+var_20]; this
0x180124955  test    rcx, rcx
0x180124958  jz      short loc_180124960
0x18012495a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18012495f  nop
0x180124960  lea     r14, [rdi+20h]
0x180124964  mov     r8, [r14]
0x180124967  lea     rdx, [rsp+58h+var_38]
0x18012496c  lea     rcx, [rsp+58h+var_28]
0x180124971  call    ??0?$shared_ptr@VDiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>(std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey> const &)
0x180124976  mov     rdx, rax
0x180124979  mov     rcx, r8
0x18012497c  call    ?AddChildKey@DiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@QEAAJV?$shared_ptr@VDiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@@std@@@Z; Microsoft::Windows::MDM::MDMDiagnostics::DiagKey::AddChildKey(std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>)
0x180124981  mov     ebx, eax
0x180124983  test    eax, eax
0x180124985  jns     short loc_1801249B9
0x180124987  mov     rcx, [rsp+58h]; this
0x18012498c  mov     r9d, eax; char *
0x18012498f  lea     r8, aOnecoreuapAdmi_27; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180124996  mov     edx, 61h ; 'a'; void *
0x18012499b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801249a0  nop
0x1801249a1  mov     rcx, [rsp+58h+var_38+8]; this
0x1801249a6  test    rcx, rcx
0x1801249a9  jz      loc_180124907
0x1801249af  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801249b4  jmp     loc_180124907
0x1801249b9  mov     rdx, r14
0x1801249bc  lea     rcx, [rsp+58h+var_28]
0x1801249c1  call    ??0?$shared_ptr@VDiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>(std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey> const &)
0x1801249c6  mov     rbx, rax
0x1801249c9  mov     rcx, [rsp+58h+var_38]
0x1801249ce  add     rcx, 648h
0x1801249d5  mov     rdx, rax
0x1801249d8  call    ??4?$shared_ptr@VDiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>::operator=(std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey> const &)
0x1801249dd  mov     rcx, [rbx+8]; this
0x1801249e1  test    rcx, rcx
0x1801249e4  jz      short loc_1801249EB
0x1801249e6  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801249eb  lea     rdx, [rsp+58h+var_38]
0x1801249f0  mov     rcx, r14
0x1801249f3  call    ??4?$shared_ptr@VDiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>::operator=(std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey> const &)
0x1801249f8  cmp     dword ptr [rsi], 1
0x1801249fb  jnz     short loc_180124A1A
0x1801249fd  mov     r8, [rdi+8]
0x180124a01  mov     rdx, r14
0x180124a04  lea     rcx, [rsp+58h+var_28]
0x180124a09  call    ??0?$shared_ptr@VDiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>(std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey> const &)
0x180124a0e  mov     rdx, rax
0x180124a11  mov     rcx, r8
0x180124a14  call    ?AddKey@DiagData@MDMDiagnostics@MDM@Windows@Microsoft@@QEAAJV?$shared_ptr@VDiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@@std@@@Z; Microsoft::Windows::MDM::MDMDiagnostics::DiagData::AddKey(std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>)
0x180124a19  nop
0x180124a1a  jmp     loc_180124B56
0x180124a1f  mov     rcx, [rsp+58h+var_38+8]; this
0x180124a24  test    rcx, rcx
0x180124a27  jz      short loc_180124A2E
0x180124a29  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180124a2e  mov     eax, [rsp+58h+arg_0]
0x180124a32  jmp     short loc_180124A55
0x180124a34  lea     rdx, aPath; "Path"
0x180124a3b  mov     rcx, [rsp+58h+arg_10]
0x180124a40  call    cs:__imp__o__wcsicmp
0x180124a47  nop     dword ptr [rax+rax+00h]
0x180124a4c  test    eax, eax
0x180124a4e  jnz     short loc_180124A64
0x180124a50  mov     [rdi+40h], eax
0x180124a53  xor     eax, eax
0x180124a55  mov     rbx, [rsp+58h+arg_8]
0x180124a5a  add     rsp, 40h
0x180124a5e  pop     r14
0x180124a60  pop     rdi
0x180124a61  pop     rsi
0x180124a62  retn
0x180124a64  lea     rdx, aRepresentation; "Representation"
0x180124a6b  mov     rcx, [rsp+58h+arg_10]
0x180124a70  call    cs:__imp__o__wcsicmp
0x180124a77  nop     dword ptr [rax+rax+00h]
0x180124a7c  test    eax, eax
0x180124a7e  jnz     short loc_180124A89
0x180124a80  mov     dword ptr [rdi+40h], 2
0x180124a87  jmp     short loc_180124A53
0x180124a89  lea     rdx, aCategory; "Category"
0x180124a90  mov     rcx, [rsp+58h+arg_10]
0x180124a95  call    cs:__imp__o__wcsicmp
0x180124a9c  nop     dword ptr [rax+rax+00h]
0x180124aa1  test    eax, eax
0x180124aa3  jnz     short loc_180124AAE
0x180124aa5  mov     dword ptr [rdi+40h], 1
0x180124aac  jmp     short loc_180124A53
0x180124aae  lea     rdx, aValue_0; "Value"
0x180124ab5  mov     rcx, [rsp+58h+arg_10]
0x180124aba  call    cs:__imp__o__wcsicmp
0x180124ac1  nop     dword ptr [rax+rax+00h]
0x180124ac6  test    eax, eax
0x180124ac8  jnz     loc_180124B73
0x180124ace  xorps   xmm0, xmm0
0x180124ad1  movdqu  xmmword ptr [rsp+58h+var_38], xmm0; int
0x180124ad7  lea     rcx, [rsp+58h+var_28]
0x180124adc  call    ??$make_shared@VDiagValue@MDMDiagnostics@MDM@Windows@Microsoft@@$$V@std@@YA?AV?$shared_ptr@VDiagValue@MDMDiagnostics@MDM@Windows@Microsoft@@@0@XZ; std::make_shared<Microsoft::Windows::MDM::MDMDiagnostics::DiagValue,>(void)
0x180124ae1  mov     rdx, rax
0x180124ae4  lea     rcx, [rsp+58h+var_38]
0x180124ae9  call    ??4?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::operator=(std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>> &&)
0x180124aee  mov     rcx, [rsp+58h+var_20]; this
0x180124af3  test    rcx, rcx
0x180124af6  jz      short loc_180124AFE
0x180124af8  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180124afd  nop
0x180124afe  mov     r8, [rdi+20h]
0x180124b02  lea     rdx, [rsp+58h+var_38]
0x180124b07  lea     rcx, [rsp+58h+var_28]
0x180124b0c  call    ??0?$shared_ptr@VDiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>(std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey> const &)
0x180124b11  mov     rdx, rax
0x180124b14  mov     rcx, r8
0x180124b17  call    ?AddValue@DiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@QEAAJV?$shared_ptr@VDiagValue@MDMDiagnostics@MDM@Windows@Microsoft@@@std@@@Z; Microsoft::Windows::MDM::MDMDiagnostics::DiagKey::AddValue(std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagValue>)
0x180124b1c  mov     ebx, eax
0x180124b1e  test    eax, eax
0x180124b20  jns     short loc_180124B41
0x180124b22  mov     rcx, [rsp+58h]; this
0x180124b27  mov     r9d, eax; char *
0x180124b2a  lea     r8, aOnecoreuapAdmi_27; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180124b31  mov     edx, 8Ah; void *
0x180124b36  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180124b3b  nop
0x180124b3c  jmp     loc_1801249A1
0x180124b41  lea     rcx, [rdi+30h]
0x180124b45  lea     rdx, [rsp+58h+var_38]
0x180124b4a  call    ??4?$shared_ptr@VDiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>::operator=(std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey> const &)
0x180124b4f  mov     dword ptr [rdi+40h], 4
0x180124b56  mov     rcx, [rsp+58h+var_38+8]; this
0x180124b5b  test    rcx, rcx
0x180124b5e  jz      loc_180124A53
0x180124b64  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180124b69  jmp     loc_180124A53
0x180124b6e  jmp     loc_180124A1F
0x180124b73  lea     rdx, aName; "Name"
0x180124b7a  mov     rcx, [rsp+58h+arg_10]
0x180124b7f  call    cs:__imp__o__wcsicmp
0x180124b86  nop     dword ptr [rax+rax+00h]
0x180124b8b  test    eax, eax
0x180124b8d  jnz     short loc_180124B9C
0x180124b8f  mov     qword ptr [rdi+40h], 4
0x180124b97  jmp     loc_180124A53
0x180124b9c  lea     rdx, aValuerepresent; "ValueRepresentation"
0x180124ba3  mov     rcx, [rsp+58h+arg_10]
0x180124ba8  call    cs:__imp__o__wcsicmp
0x180124baf  nop     dword ptr [rax+rax+00h]
0x180124bb4  test    eax, eax
0x180124bb6  jnz     short loc_180124BCB
0x180124bb8  mov     dword ptr [rdi+40h], 4
0x180124bbf  mov     dword ptr [rdi+44h], 1
0x180124bc6  jmp     loc_180124A53
0x180124bcb  lea     rdx, aDatasource; "DataSource"
0x180124bd2  mov     rcx, [rsp+58h+arg_10]
0x180124bd7  call    cs:__imp__o__wcsicmp
0x180124bde  nop     dword ptr [rax+rax+00h]
0x180124be3  test    eax, eax
0x180124be5  jnz     loc_180124A53
0x180124beb  mov     rcx, rdi; this
0x180124bee  call    ?ExtractAttributes@XMLDiagnosticDataInputParser@MDMDiagnostics@MDM@Windows@Microsoft@@AEAAJXZ; Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticDataInputParser::ExtractAttributes(void)
0x180124bf3  mov     ebx, eax
0x180124bf5  test    eax, eax
0x180124bf7  jns     loc_180124A53
0x180124bfd  mov     edx, 9Fh
0x180124c02  jmp     loc_1801248F3
```
