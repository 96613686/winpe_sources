# Rdp::Stack::Shim::CAdapterShim::LoadAvenc(void)

- ea: `0x1800193e4`
- end: `0x1800196b2`
- name: `?LoadAvenc@CAdapterShim@Shim@Stack@Rdp@@AEAAXXZ`
- size: `718`
- prototype: `void __fastcall(Rdp::Stack::Shim::CAdapterShim *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting`

## callers

- `0x180019f08`

## callees

- `0x18000141c`
- `0x180002508`
- `0x1800036f0`
- `0x18000cea4`
- `0x18000cf28`
- `0x18000d98c`
- `0x18000ed34`
- `0x180013e3c`
- `0x180018050`
- `0x180018850`
- `0x1800193e4`
- `0x18001b34c`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800194eb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800194eb`
- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryW` at `0x180019492`
- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryW` at `0x180019492`

## string_xrefs

- `0x18001941a`: `Video encoder dll has already been loaded`
- `0x180019469`: `Failed to retrieve PKEY_EncodingDllName property`
- `0x1800194c5`: `Failed to load video encoder dll`
- `0x180019648`: `AdapterShimAvencVersion: Iface: %#x.%#x, Dll: %#x.%#x, Build: %#x`

## pseudocode

```c
void __fastcall Rdp::Stack::Shim::CAdapterShim::LoadAvenc(Rdp::Stack::Shim::CAdapterShim *this)
{
  HMODULE *v1; // rsi
  const WCHAR *v3; // rbx
  unsigned int WString; // eax
  HMODULE LibraryW; // rax
  FARPROC ProcAddress; // rbx
  unsigned int v7; // eax
  int v8; // r8d
  int v9; // r9d
  char *v10; // [rsp+28h] [rbp-41h]
  char *v11; // [rsp+28h] [rbp-41h]
  char *v12; // [rsp+28h] [rbp-41h]
  const char *v13; // [rsp+30h] [rbp-39h]
  __int64 v14; // [rsp+30h] [rbp-39h]
  __int64 v15; // [rsp+38h] [rbp-31h]
  __int64 v16; // [rsp+40h] [rbp-29h]
  __int64 v17; // [rsp+48h] [rbp-21h]
  int v18; // [rsp+60h] [rbp-9h] BYREF
  int v19; // [rsp+64h] [rbp-5h] BYREF
  int v20; // [rsp+68h] [rbp-1h] BYREF
  int v21; // [rsp+6Ch] [rbp+3h] BYREF
  int v22; // [rsp+70h] [rbp+7h] BYREF
  HMODULE v23; // [rsp+78h] [rbp+Fh] BYREF
  const char *v24; // [rsp+80h] [rbp+17h] BYREF
  __int64 v25; // [rsp+88h] [rbp+1Fh] BYREF
  __int128 *v26; // [rsp+90h] [rbp+27h] BYREF
  int v27; // [rsp+98h] [rbp+2Fh] BYREF
  __int64 v28; // [rsp+9Ch] [rbp+33h]
  int v29; // [rsp+A4h] [rbp+3Bh]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v1 = (HMODULE *)((char *)this + 136);
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0xDE,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\adaptershim.cpp",
    (const char *)0x80070057LL,
    *((_QWORD *)this + 17) != 0,
    (bool)"Video encoder dll has already been loaded",
    v13);
  v3 = (const WCHAR *)((char *)this + 104);
  WString = Rdp::Utils::Props::IPropertyStore_GetWString(
              *((_QWORD *)this + 18),
              PKEY_EncodingDllName,
              (char *)this + 104);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0xE8,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\adaptershim.cpp",
    (const char *)WString,
    (int)"Failed to retrieve PKEY_EncodingDllName property",
    v10);
  if ( *((_QWORD *)this + 16) > 7u )
    v3 = *(const WCHAR **)v3;
  LibraryW = LoadLibraryW(v3);
  v23 = LibraryW;
  if ( v1 != &v23 )
  {
    wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(
      v1,
      LibraryW);
    v23 = 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v23);
  wil::details::in1diag3::Throw_GetLastErrorIfNullMsg<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>,0>(
    retaddr,
    238,
    "onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\adaptershim.cpp",
    v1,
    "Failed to load video encoder dll");
  ProcAddress = GetProcAddress(*v1, "NegotiateVersions");
  wil::details::in1diag3::Throw_GetLastErrorIfNullMsg<long (*)(Rdp::Avenc::AVENC_VERSION_INFO const *,Rdp::Avenc::AVENC_VERSION_INFO *,Rdp::Avenc::AVENC_VERSION_INFO *),0>(
    retaddr,
    243,
    "onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\adaptershim.cpp",
    ProcAddress,
    "Failed to load address of NegotiateVersions");
  v27 = 16;
  v28 = 1;
  v29 = 0;
  v7 = ((__int64 (__fastcall *)(int *, char *, char *))ProcAddress)(&v27, (char *)this + 184, (char *)this + 200);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x103,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\adaptershim.cpp",
    (const char *)v7,
    (int)"Failed to negotiate versions with Avenc",
    v11);
  if ( (unsigned int)dword_18003C058 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18003C058, 0x400000000000LL) )
  {
    v18 = *((_DWORD *)this + 53);
    v19 = *((_DWORD *)this + 52);
    v20 = *((_DWORD *)this + 51);
    v21 = *((_DWORD *)this + 48);
    v22 = *((_DWORD *)this + 47);
    v24 = "Avenc versions";
    v26 = &xmmword_18003CA50;
    v25 = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (unsigned int)&dword_18003C058,
      (unsigned int)&dword_180035884,
      v8,
      v9,
      (__int64)&v26,
      (__int64)&v25,
      (__int64)&v24,
      (__int64)&v22,
      (__int64)&v21,
      (__int64)&v20,
      (__int64)&v19,
      (__int64)&v18);
  }
  LODWORD(v17) = *((_DWORD *)this + 53);
  LODWORD(v16) = *((_DWORD *)this + 52);
  LODWORD(v15) = *((_DWORD *)this + 51);
  LODWORD(v14) = *((_DWORD *)this + 48);
  LODWORD(v12) = *((_DWORD *)this + 47);
  Rdp::Modern::Utils::CInflightRecorder::pushN(
    (Rdp::Modern::Utils::CInflightRecorder *)&Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
    (wchar_t *)L"AdapterShimAvencVersion: Iface: %#x.%#x, Dll: %#x.%#x, Build: %#x",
    "Rdp::Stack::Shim::CAdapterShim::LoadAvenc",
    "onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\adaptershim.cpp",
    0x114u,
    v12,
    v14,
    v15,
    v16,
    v17);
}

```

## disassembly

```asm
0x1800193e4  mov     [rsp-8+arg_8], rbx
0x1800193e9  mov     [rsp-8+arg_10], rsi
0x1800193ee  push    rbp
0x1800193ef  push    rdi
0x1800193f0  push    r15
0x1800193f2  lea     rbp, [rsp-47h]
0x1800193f7  sub     rsp, 0B0h
0x1800193fe  mov     rax, cs:__security_cookie
0x180019405  xor     rax, rsp
0x180019408  mov     [rbp+57h+var_18], rax
0x18001940c  lea     rsi, [rcx+88h]
0x180019413  mov     rdi, rcx
0x180019416  cmp     qword ptr [rsi], 0
0x18001941a  lea     rdx, aVideoEncoderDl; "Video encoder dll has already been load"...
0x180019421  mov     rcx, [rbp+5Fh]; this
0x180019425  lea     r15, aOnecoreuapTerm_25; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x18001942c  mov     [rsp+0C0h+var_98], rdx; char *
0x180019431  setnz   al
0x180019434  mov     r9d, 80070057h; char *
0x18001943a  mov     [rsp+0C0h+var_A0], al; char
0x18001943e  mov     r8, r15; unsigned int
0x180019441  mov     edx, 0DEh; void *
0x180019446  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18001944b  mov     rcx, [rdi+90h]
0x180019452  lea     rbx, [rdi+68h]
0x180019456  mov     r8, rbx
0x180019459  lea     rdx, PKEY_EncodingDllName
0x180019460  call    ?IPropertyStore_GetWString@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Rdp::Utils::Props::IPropertyStore_GetWString(IPropertyStore *,_tagpropertykey const &,std::wstring &)
0x180019465  mov     rcx, [rbp+5Fh]; this
0x180019469  lea     rdx, aFailedToRetrie_17; "Failed to retrieve PKEY_EncodingDllName"...
0x180019470  mov     qword ptr [rsp+0C0h+var_A0], rdx; int
0x180019475  mov     r9d, eax; char *
0x180019478  mov     edx, 0E8h; void *
0x18001947d  mov     r8, r15; unsigned int
0x180019480  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180019485  cmp     qword ptr [rbx+18h], 7
0x18001948a  jbe     short loc_18001948F
0x18001948c  mov     rbx, [rbx]
0x18001948f  mov     rcx, rbx; lpLibFileName
0x180019492  call    cs:__imp_LoadLibraryW
0x180019498  lea     rcx, [rbp+57h+var_48]
0x18001949c  mov     [rbp+57h+var_48], rax
0x1800194a0  cmp     rsi, rcx
0x1800194a3  jz      short loc_1800194B8
0x1800194a5  mov     rdx, rax
0x1800194a8  mov     rcx, rsi
0x1800194ab  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHINSTANCE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(HINSTANCE__ *)
0x1800194b0  mov     [rbp+57h+var_48], 0
0x1800194b8  lea     rcx, [rbp+57h+var_48]
0x1800194bc  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x1800194c1  mov     rcx, [rbp+5Fh]
0x1800194c5  lea     rax, aFailedToLoadVi; "Failed to load video encoder dll"
0x1800194cc  mov     r9, rsi
0x1800194cf  mov     qword ptr [rsp+0C0h+var_A0], rax
0x1800194d4  mov     r8, r15
0x1800194d7  mov     edx, 0EEh
0x1800194dc  call    ??$Throw_GetLastErrorIfNullMsg@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@$0A@@in1diag3@details@wil@@YAXPEAXIPEBDAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfNullMsg<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>,0>(void *,uint,char const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>> const &,char const *,...)
0x1800194e1  mov     rcx, [rsi]; hModule
0x1800194e4  lea     rdx, aNegotiateversi; "NegotiateVersions"
0x1800194eb  call    cs:__imp_GetProcAddress
0x1800194f1  mov     rcx, [rbp+5Fh]
0x1800194f5  mov     r8, r15
0x1800194f8  mov     rbx, rax
0x1800194fb  mov     edx, 0F3h
0x180019500  lea     rax, aFailedToLoadAd; "Failed to load address of NegotiateVers"...
0x180019507  mov     r9, rbx
0x18001950a  mov     qword ptr [rsp+0C0h+var_A0], rax
0x18001950f  call    ??$Throw_GetLastErrorIfNullMsg@P6AJPEBUAVENC_VERSION_INFO@Avenc@Rdp@@PEAU123@1@Z$0A@@in1diag3@details@wil@@YAP6AJPEBUAVENC_VERSION_INFO@Avenc@Rdp@@PEAU345@1@ZPEAXIPEBDP6AJ011@Z3ZZ; wil::details::in1diag3::Throw_GetLastErrorIfNullMsg<long (*)(Rdp::Avenc::AVENC_VERSION_INFO const *,Rdp::Avenc::AVENC_VERSION_INFO *,Rdp::Avenc::AVENC_VERSION_INFO *),0>(void *,uint,char const *,long (*)(Rdp::Avenc::AVENC_VERSION_INFO const *,Rdp::Avenc::AVENC_VERSION_INFO *,Rdp::Avenc::AVENC_VERSION_INFO *),char const *,...)
0x180019514  lea     r8, [rdi+0C8h]
0x18001951b  mov     [rbp+57h+var_28], 10h
0x180019522  lea     rdx, [rdi+0B8h]
0x180019529  mov     [rbp+57h+var_24], 1
0x180019531  lea     rcx, [rbp+57h+var_28]
0x180019535  mov     [rbp+57h+var_1C], 0
0x18001953c  mov     rax, rbx
0x18001953f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019544  mov     rcx, [rbp+5Fh]; this
0x180019548  lea     rdx, aFailedToNegoti; "Failed to negotiate versions with Avenc"
0x18001954f  mov     qword ptr [rsp+0C0h+var_A0], rdx; int
0x180019554  mov     r9d, eax; char *
0x180019557  mov     edx, 103h; void *
0x18001955c  mov     r8, r15; unsigned int
0x18001955f  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180019564  mov     eax, cs:dword_18003C058
0x18001956a  cmp     eax, 4
0x18001956d  jbe     loc_180019637
0x180019573  mov     rdx, 400000000000h
0x18001957d  lea     rcx, dword_18003C058
0x180019584  call    _tlgKeywordOn
0x180019589  test    al, al
0x18001958b  jz      loc_180019637
0x180019591  mov     eax, [rdi+0D4h]
0x180019597  lea     rdx, dword_180035884
0x18001959e  mov     [rbp+57h+var_60], eax
0x1800195a1  lea     rcx, dword_18003C058
0x1800195a8  mov     eax, [rdi+0D0h]
0x1800195ae  mov     [rbp+57h+var_5C], eax
0x1800195b1  mov     eax, [rdi+0CCh]
0x1800195b7  mov     [rbp+57h+var_58], eax
0x1800195ba  mov     eax, [rdi+0C0h]
0x1800195c0  mov     [rbp+57h+var_54], eax
0x1800195c3  mov     eax, [rdi+0BCh]
0x1800195c9  mov     [rbp+57h+var_50], eax
0x1800195cc  lea     rax, aAvencVersions; "Avenc versions"
0x1800195d3  mov     [rbp+57h+var_40], rax
0x1800195d7  lea     rax, xmmword_18003CA50
0x1800195de  mov     [rbp+57h+var_30], rax
0x1800195e2  lea     rax, [rbp+57h+var_60]
0x1800195e6  mov     [rsp+0C0h+var_68], rax
0x1800195eb  lea     rax, [rbp+57h+var_5C]
0x1800195ef  mov     [rsp+0C0h+var_70], rax
0x1800195f4  lea     rax, [rbp+57h+var_58]
0x1800195f8  mov     [rsp+0C0h+var_78], rax
0x1800195fd  lea     rax, [rbp+57h+var_54]
0x180019601  mov     [rsp+0C0h+var_80], rax
0x180019606  lea     rax, [rbp+57h+var_50]
0x18001960a  mov     [rsp+0C0h+var_88], rax
0x18001960f  lea     rax, [rbp+57h+var_40]
0x180019613  mov     [rsp+0C0h+var_90], rax
0x180019618  lea     rax, [rbp+57h+var_38]
0x18001961c  mov     [rsp+0C0h+var_98], rax
0x180019621  lea     rax, [rbp+57h+var_30]
0x180019625  mov     qword ptr [rsp+0C0h+var_A0], rax
0x18001962a  mov     [rbp+57h+var_38], 1000000h
0x180019632  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U4@U4@U4@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@6666@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180019637  mov     eax, [rdi+0D4h]
0x18001963d  lea     r8, aRdpStackShimCa_4; "Rdp::Stack::Shim::CAdapterShim::LoadAve"...
0x180019644  mov     dword ptr [rsp+0C0h+var_78], eax
0x180019648  lea     rdx, aAdaptershimave; "AdapterShimAvencVersion: Iface: %#x.%#x"...
0x18001964f  mov     eax, [rdi+0D0h]
0x180019655  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x18001965c  mov     dword ptr [rsp+0C0h+var_80], eax
0x180019660  mov     r9, r15; char *
0x180019663  mov     eax, [rdi+0CCh]
0x180019669  mov     dword ptr [rsp+0C0h+var_88], eax
0x18001966d  mov     eax, [rdi+0C0h]
0x180019673  mov     dword ptr [rsp+0C0h+var_90], eax
0x180019677  mov     eax, [rdi+0BCh]
0x18001967d  mov     dword ptr [rsp+0C0h+var_98], eax
0x180019681  mov     dword ptr [rsp+0C0h+var_A0], 114h; unsigned int
0x180019689  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x18001968e  mov     rcx, [rbp+57h+var_18]
0x180019692  xor     rcx, rsp; StackCookie
0x180019695  call    __security_check_cookie
0x18001969a  lea     r11, [rsp+0C0h+var_10]
0x1800196a2  mov     rbx, [r11+28h]
0x1800196a6  mov     rsi, [r11+30h]
0x1800196aa  mov     rsp, r11
0x1800196ad  pop     r15
0x1800196af  pop     rdi
0x1800196b0  pop     rbp
0x1800196b1  retn
```
