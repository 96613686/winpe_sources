# Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticDataInputParser::ParseElement(ulong *)

- ea: `0x180122dec`
- end: `0x18012310e`
- name: `?ParseElement@XMLDiagnosticDataInputParser@MDMDiagnostics@MDM@Windows@Microsoft@@AEAAJPEAK@Z`
- size: `802`
- prototype: `__int64 __fastcall(Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticDataInputParser *__hidden this, unsigned int *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1801231e0`

## callees

- `0x1800e691c`
- `0x1800ece5c`
- `0x1800ee898`
- `0x1800f980c`
- `0x180122808`
- `0x18012285c`
- `0x180122ae8`
- `0x180122cd0`
- `0x180122dec`
- `0x180125958`
- `0x1801259c8`
- `0x180125a38`
- `0x180191010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180122e52`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180122f72`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180122f9b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180122fba`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180122fd9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180123098`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801230bb`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801230e4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180122e52`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180122f72`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180122f9b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180122fba`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180122fd9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180123098`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801230bb`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801230e4`

## string_xrefs

- `0x180122e2b`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\registrytoxml\xmldiagnosticdatainputparser.cpp`
- `0x180122ec1`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\registrytoxml\xmldiagnosticdatainputparser.cpp`
- `0x180123043`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\registrytoxml\xmldiagnosticdatainputparser.cpp`

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
0x180122dec  mov     [rsp+arg_8], rbx
0x180122df1  push    rsi
0x180122df2  push    rdi
0x180122df3  push    r14
0x180122df5  sub     rsp, 40h
0x180122df9  mov     rsi, rdx
0x180122dfc  mov     rdi, rcx
0x180122dff  mov     [rsp+58h+arg_10], 0
0x180122e08  mov     rcx, [rcx+18h]
0x180122e0c  mov     rax, [rcx]
0x180122e0f  xor     r8d, r8d
0x180122e12  lea     rdx, [rsp+58h+arg_10]
0x180122e17  mov     rax, [rax+70h]
0x180122e1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180122e20  mov     ebx, eax
0x180122e22  test    eax, eax
0x180122e24  jns     short loc_180122E46
0x180122e26  mov     edx, 51h ; 'Q'; void *
0x180122e2b  lea     r8, aOnecoreuapAdmi_27; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180122e32  mov     r9d, ebx; char *
0x180122e35  mov     rcx, [rsp+58h]; this
0x180122e3a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180122e3f  mov     eax, ebx
0x180122e41  jmp     loc_180122F81
0x180122e46  lea     rdx, aKey; "Key"
0x180122e4d  mov     rcx, [rsp+58h+arg_10]
0x180122e52  call    cs:__imp__o__wcsicmp
0x180122e58  test    eax, eax
0x180122e5a  jnz     loc_180122F66
0x180122e60  inc     dword ptr [rsi]
0x180122e62  xorps   xmm0, xmm0
0x180122e65  movdqu  xmmword ptr [rsp+58h+var_38], xmm0; int
0x180122e6b  lea     rcx, [rsp+58h+var_28]
0x180122e70  call    ??$make_shared@VDiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@$$V@std@@YA?AV?$shared_ptr@VDiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@@0@XZ; std::make_shared<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey,>(void)
0x180122e75  mov     rdx, rax
0x180122e78  lea     rcx, [rsp+58h+var_38]
0x180122e7d  call    ??4?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::operator=(std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>> &&)
0x180122e82  mov     rcx, [rsp+58h+var_20]; this
0x180122e87  test    rcx, rcx
0x180122e8a  jz      short loc_180122E92
0x180122e8c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180122e91  nop
0x180122e92  lea     r14, [rdi+20h]
0x180122e96  mov     r8, [r14]
0x180122e99  lea     rdx, [rsp+58h+var_38]
0x180122e9e  lea     rcx, [rsp+58h+var_28]
0x180122ea3  call    ??0?$shared_ptr@VDiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>(std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey> const &)
0x180122ea8  mov     rdx, rax
0x180122eab  mov     rcx, r8
0x180122eae  call    ?AddChildKey@DiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@QEAAJV?$shared_ptr@VDiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@@std@@@Z; Microsoft::Windows::MDM::MDMDiagnostics::DiagKey::AddChildKey(std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>)
0x180122eb3  mov     ebx, eax
0x180122eb5  test    eax, eax
0x180122eb7  jns     short loc_180122EEB
0x180122eb9  mov     rcx, [rsp+58h]; this
0x180122ebe  mov     r9d, eax; char *
0x180122ec1  lea     r8, aOnecoreuapAdmi_27; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180122ec8  mov     edx, 61h ; 'a'; void *
0x180122ecd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180122ed2  nop
0x180122ed3  mov     rcx, [rsp+58h+var_38+8]; this
0x180122ed8  test    rcx, rcx
0x180122edb  jz      loc_180122E3F
0x180122ee1  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180122ee6  jmp     loc_180122E3F
0x180122eeb  mov     rdx, r14
0x180122eee  lea     rcx, [rsp+58h+var_28]
0x180122ef3  call    ??0?$shared_ptr@VDiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>(std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey> const &)
0x180122ef8  mov     rbx, rax
0x180122efb  mov     rcx, [rsp+58h+var_38]
0x180122f00  add     rcx, 648h
0x180122f07  mov     rdx, rax
0x180122f0a  call    ??4?$shared_ptr@VDiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>::operator=(std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey> const &)
0x180122f0f  mov     rcx, [rbx+8]; this
0x180122f13  test    rcx, rcx
0x180122f16  jz      short loc_180122F1D
0x180122f18  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180122f1d  lea     rdx, [rsp+58h+var_38]
0x180122f22  mov     rcx, r14
0x180122f25  call    ??4?$shared_ptr@VDiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>::operator=(std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey> const &)
0x180122f2a  cmp     dword ptr [rsi], 1
0x180122f2d  jnz     short loc_180122F4C
0x180122f2f  mov     r8, [rdi+8]
0x180122f33  mov     rdx, r14
0x180122f36  lea     rcx, [rsp+58h+var_28]
0x180122f3b  call    ??0?$shared_ptr@VDiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>(std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey> const &)
0x180122f40  mov     rdx, rax
0x180122f43  mov     rcx, r8
0x180122f46  call    ?AddKey@DiagData@MDMDiagnostics@MDM@Windows@Microsoft@@QEAAJV?$shared_ptr@VDiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@@std@@@Z; Microsoft::Windows::MDM::MDMDiagnostics::DiagData::AddKey(std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>)
0x180122f4b  nop
0x180122f4c  jmp     loc_18012306F
0x180122f51  mov     rcx, [rsp+58h+var_38+8]; this
0x180122f56  test    rcx, rcx
0x180122f59  jz      short loc_180122F60
0x180122f5b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180122f60  mov     eax, [rsp+58h+arg_0]
0x180122f64  jmp     short loc_180122F81
0x180122f66  lea     rdx, aPath; "Path"
0x180122f6d  mov     rcx, [rsp+58h+arg_10]
0x180122f72  call    cs:__imp__o__wcsicmp
0x180122f78  test    eax, eax
0x180122f7a  jnz     short loc_180122F8F
0x180122f7c  mov     [rdi+40h], eax
0x180122f7f  xor     eax, eax
0x180122f81  mov     rbx, [rsp+58h+arg_8]
0x180122f86  add     rsp, 40h
0x180122f8a  pop     r14
0x180122f8c  pop     rdi
0x180122f8d  pop     rsi
0x180122f8e  retn
0x180122f8f  lea     rdx, aRepresentation; "Representation"
0x180122f96  mov     rcx, [rsp+58h+arg_10]
0x180122f9b  call    cs:__imp__o__wcsicmp
0x180122fa1  test    eax, eax
0x180122fa3  jnz     short loc_180122FAE
0x180122fa5  mov     dword ptr [rdi+40h], 2
0x180122fac  jmp     short loc_180122F7F
0x180122fae  lea     rdx, aCategory; "Category"
0x180122fb5  mov     rcx, [rsp+58h+arg_10]
0x180122fba  call    cs:__imp__o__wcsicmp
0x180122fc0  test    eax, eax
0x180122fc2  jnz     short loc_180122FCD
0x180122fc4  mov     dword ptr [rdi+40h], 1
0x180122fcb  jmp     short loc_180122F7F
0x180122fcd  lea     rdx, aValue_0; "Value"
0x180122fd4  mov     rcx, [rsp+58h+arg_10]
0x180122fd9  call    cs:__imp__o__wcsicmp
0x180122fdf  test    eax, eax
0x180122fe1  jnz     loc_18012308C
0x180122fe7  xorps   xmm0, xmm0
0x180122fea  movdqu  xmmword ptr [rsp+58h+var_38], xmm0; int
0x180122ff0  lea     rcx, [rsp+58h+var_28]
0x180122ff5  call    ??$make_shared@VDiagValue@MDMDiagnostics@MDM@Windows@Microsoft@@$$V@std@@YA?AV?$shared_ptr@VDiagValue@MDMDiagnostics@MDM@Windows@Microsoft@@@0@XZ; std::make_shared<Microsoft::Windows::MDM::MDMDiagnostics::DiagValue,>(void)
0x180122ffa  mov     rdx, rax
0x180122ffd  lea     rcx, [rsp+58h+var_38]
0x180123002  call    ??4?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::operator=(std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>> &&)
0x180123007  mov     rcx, [rsp+58h+var_20]; this
0x18012300c  test    rcx, rcx
0x18012300f  jz      short loc_180123017
0x180123011  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180123016  nop
0x180123017  mov     r8, [rdi+20h]
0x18012301b  lea     rdx, [rsp+58h+var_38]
0x180123020  lea     rcx, [rsp+58h+var_28]
0x180123025  call    ??0?$shared_ptr@VDiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>(std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey> const &)
0x18012302a  mov     rdx, rax
0x18012302d  mov     rcx, r8
0x180123030  call    ?AddValue@DiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@QEAAJV?$shared_ptr@VDiagValue@MDMDiagnostics@MDM@Windows@Microsoft@@@std@@@Z; Microsoft::Windows::MDM::MDMDiagnostics::DiagKey::AddValue(std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagValue>)
0x180123035  mov     ebx, eax
0x180123037  test    eax, eax
0x180123039  jns     short loc_18012305A
0x18012303b  mov     rcx, [rsp+58h]; this
0x180123040  mov     r9d, eax; char *
0x180123043  lea     r8, aOnecoreuapAdmi_27; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18012304a  mov     edx, 8Ah; void *
0x18012304f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180123054  nop
0x180123055  jmp     loc_180122ED3
0x18012305a  lea     rcx, [rdi+30h]
0x18012305e  lea     rdx, [rsp+58h+var_38]
0x180123063  call    ??4?$shared_ptr@VDiagKey@MDMDiagnostics@MDM@Windows@Microsoft@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey>::operator=(std::shared_ptr<Microsoft::Windows::MDM::MDMDiagnostics::DiagKey> const &)
0x180123068  mov     dword ptr [rdi+40h], 4
0x18012306f  mov     rcx, [rsp+58h+var_38+8]; this
0x180123074  test    rcx, rcx
0x180123077  jz      loc_180122F7F
0x18012307d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180123082  jmp     loc_180122F7F
0x180123087  jmp     loc_180122F51
0x18012308c  lea     rdx, aName; "Name"
0x180123093  mov     rcx, [rsp+58h+arg_10]
0x180123098  call    cs:__imp__o__wcsicmp
0x18012309e  test    eax, eax
0x1801230a0  jnz     short loc_1801230AF
0x1801230a2  mov     qword ptr [rdi+40h], 4
0x1801230aa  jmp     loc_180122F7F
0x1801230af  lea     rdx, aValuerepresent; "ValueRepresentation"
0x1801230b6  mov     rcx, [rsp+58h+arg_10]
0x1801230bb  call    cs:__imp__o__wcsicmp
0x1801230c1  test    eax, eax
0x1801230c3  jnz     short loc_1801230D8
0x1801230c5  mov     dword ptr [rdi+40h], 4
0x1801230cc  mov     dword ptr [rdi+44h], 1
0x1801230d3  jmp     loc_180122F7F
0x1801230d8  lea     rdx, aDatasource; "DataSource"
0x1801230df  mov     rcx, [rsp+58h+arg_10]
0x1801230e4  call    cs:__imp__o__wcsicmp
0x1801230ea  test    eax, eax
0x1801230ec  jnz     loc_180122F7F
0x1801230f2  mov     rcx, rdi; this
0x1801230f5  call    ?ExtractAttributes@XMLDiagnosticDataInputParser@MDMDiagnostics@MDM@Windows@Microsoft@@AEAAJXZ; Microsoft::Windows::MDM::MDMDiagnostics::XMLDiagnosticDataInputParser::ExtractAttributes(void)
0x1801230fa  mov     ebx, eax
0x1801230fc  test    eax, eax
0x1801230fe  jns     loc_180122F7F
0x180123104  mov     edx, 9Fh
0x180123109  jmp     loc_180122E2B
```
