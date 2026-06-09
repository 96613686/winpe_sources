# Rdp::Avenc::Hevc::CMFApi::Init(void)

- ea: `0x1800273e8`
- end: `0x1800275f6`
- name: `?Init@CMFApi@Hevc@Avenc@Rdp@@QEAAXXZ`
- size: `526`
- prototype: `void __fastcall(Rdp::Avenc::Hevc::CMFApi *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180025e10`

## callees

- `0x18001733c`
- `0x1800273e8`
- `0x1800275fc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180027427`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180027442`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180027427`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180027442`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002747a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180027496`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800274b3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800274d0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800274ed`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002750a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180027527`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180027544`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002747a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180027496`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800274b3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800274d0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800274ed`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002750a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180027527`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180027544`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002742f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002742f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002741c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002741c`
- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryW` at `0x1800273fd`
- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryW` at `0x1800273fd`

## string_xrefs

- `0x1800273f6`: `mfplat.dll`
- `0x18002744d`: `Failed to load mfplat dll`
- `0x1800274ac`: `MFCreateSample`
- `0x1800274c9`: `MFCreateMemoryBuffer`
- `0x1800274e6`: `MFCreateMediaType`
- `0x180027503`: `MFCreateDXGISurfaceBuffer`
- `0x18002753d`: `MFCreateAttributes`

## pseudocode

```c
void __fastcall Rdp::Avenc::Hevc::CMFApi::Init(Rdp::Avenc::Hevc::CMFApi *this)
{
  HMODULE LibraryW; // rbp
  HMODULE *v3; // rdi
  HMODULE v4; // r14
  DWORD LastError; // ebx
  FARPROC ProcAddress; // rax
  const char *v7; // r9
  FARPROC v8; // rax
  const char *v9; // r9
  FARPROC v10; // rax
  const char *v11; // r9
  FARPROC v12; // rax
  const char *v13; // r9
  FARPROC v14; // rax
  const char *v15; // r9
  FARPROC v16; // rax
  const char *v17; // r9
  FARPROC v18; // rax
  const char *v19; // r9
  FARPROC v20; // rax
  const char *v21; // r9
  char v22; // [rsp+30h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  LibraryW = LoadLibraryW(L"mfplat.dll");
  v3 = (HMODULE *)((char *)this + 64);
  if ( (char *)this + 64 == &v22 )
  {
    if ( LibraryW )
      FreeLibrary(LibraryW);
  }
  else
  {
    v4 = *v3;
    if ( *v3 )
    {
      LastError = GetLastError();
      FreeLibrary(v4);
      SetLastError(LastError);
    }
    *v3 = LibraryW;
  }
  wil::details::in1diag3::Throw_GetLastErrorIfNullMsg<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>,0>(
    (_DWORD)retaddr,
    51,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\hevcprocessor\\cmfapi.cpp",
    (_DWORD)this + 64,
    "Failed to load mfplat dll");
  ProcAddress = GetProcAddress(*v3, "MFStartup");
  *(_QWORD *)this = ProcAddress;
  if ( !ProcAddress )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x36,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\hevcprocessor\\cmfapi.cpp",
      v7);
  v8 = GetProcAddress(*v3, "MFShutdown");
  *((_QWORD *)this + 1) = v8;
  if ( !v8 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x39,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\hevcprocessor\\cmfapi.cpp",
      v9);
  v10 = GetProcAddress(*v3, "MFCreateSample");
  *((_QWORD *)this + 2) = v10;
  if ( !v10 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x3C,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\hevcprocessor\\cmfapi.cpp",
      v11);
  v12 = GetProcAddress(*v3, "MFCreateMemoryBuffer");
  *((_QWORD *)this + 3) = v12;
  if ( !v12 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x3F,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\hevcprocessor\\cmfapi.cpp",
      v13);
  v14 = GetProcAddress(*v3, "MFCreateMediaType");
  *((_QWORD *)this + 4) = v14;
  if ( !v14 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x42,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\hevcprocessor\\cmfapi.cpp",
      v15);
  v16 = GetProcAddress(*v3, "MFCreateDXGISurfaceBuffer");
  *((_QWORD *)this + 5) = v16;
  if ( !v16 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x45,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\hevcprocessor\\cmfapi.cpp",
      v17);
  v18 = GetProcAddress(*v3, "MFTEnum2");
  *((_QWORD *)this + 6) = v18;
  if ( !v18 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x48,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\hevcprocessor\\cmfapi.cpp",
      v19);
  v20 = GetProcAddress(*v3, "MFCreateAttributes");
  *((_QWORD *)this + 7) = v20;
  if ( !v20 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x4B,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\hevcprocessor\\cmfapi.cpp",
      v21);
}

```

## disassembly

```asm
0x1800273e8  push    rbx
0x1800273ea  push    rbp
0x1800273eb  push    rsi
0x1800273ec  push    rdi
0x1800273ed  push    r14
0x1800273ef  sub     rsp, 40h
0x1800273f3  mov     rsi, rcx
0x1800273f6  lea     rcx, LibFileName; "mfplat.dll"
0x1800273fd  call    cs:__imp_LoadLibraryW
0x180027403  mov     rbp, rax
0x180027406  lea     rdi, [rsi+40h]
0x18002740a  lea     rax, [rsp+68h+var_38]
0x18002740f  cmp     rdi, rax
0x180027412  jz      short loc_18002743A
0x180027414  mov     r14, [rdi]
0x180027417  test    r14, r14
0x18002741a  jz      short loc_180027435
0x18002741c  call    cs:__imp_GetLastError
0x180027422  mov     rcx, r14; hLibModule
0x180027425  mov     ebx, eax
0x180027427  call    cs:__imp_FreeLibrary
0x18002742d  mov     ecx, ebx; dwErrCode
0x18002742f  call    cs:__imp_SetLastError
0x180027435  mov     [rdi], rbp
0x180027438  jmp     short loc_180027448
0x18002743a  test    rbp, rbp
0x18002743d  jz      short loc_180027448
0x18002743f  mov     rcx, rbp; hLibModule
0x180027442  call    cs:__imp_FreeLibrary
0x180027448  mov     rcx, [rsp+68h]
0x18002744d  lea     rax, aFailedToLoadMf; "Failed to load mfplat dll"
0x180027454  lea     rbx, aOnecoreuapTerm_17; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18002745b  mov     [rsp+68h+var_48], rax
0x180027460  mov     r8, rbx
0x180027463  mov     r9, rdi
0x180027466  mov     edx, 33h ; '3'
0x18002746b  call    ??$Throw_GetLastErrorIfNullMsg@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@$0A@@in1diag3@details@wil@@YAXPEAXIPEBDAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfNullMsg<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>,0>(void *,uint,char const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>> const &,char const *,...)
0x180027470  mov     rcx, [rdi]; hModule
0x180027473  lea     rdx, aMfstartup_0; "MFStartup"
0x18002747a  call    cs:__imp_GetProcAddress
0x180027480  mov     [rsi], rax
0x180027483  test    rax, rax
0x180027486  jz      loc_180027571
0x18002748c  mov     rcx, [rdi]; hModule
0x18002748f  lea     rdx, aMfshutdown_0; "MFShutdown"
0x180027496  call    cs:__imp_GetProcAddress
0x18002749c  mov     [rsi+8], rax
0x1800274a0  test    rax, rax
0x1800274a3  jz      loc_180027584
0x1800274a9  mov     rcx, [rdi]; hModule
0x1800274ac  lea     rdx, aMfcreatesample_2; "MFCreateSample"
0x1800274b3  call    cs:__imp_GetProcAddress
0x1800274b9  mov     [rsi+10h], rax
0x1800274bd  test    rax, rax
0x1800274c0  jz      loc_180027597
0x1800274c6  mov     rcx, [rdi]; hModule
0x1800274c9  lea     rdx, aMfcreatememory; "MFCreateMemoryBuffer"
0x1800274d0  call    cs:__imp_GetProcAddress
0x1800274d6  mov     [rsi+18h], rax
0x1800274da  test    rax, rax
0x1800274dd  jz      loc_1800275AA
0x1800274e3  mov     rcx, [rdi]; hModule
0x1800274e6  lea     rdx, aMfcreatemediat_0; "MFCreateMediaType"
0x1800274ed  call    cs:__imp_GetProcAddress
0x1800274f3  mov     [rsi+20h], rax
0x1800274f7  test    rax, rax
0x1800274fa  jz      loc_1800275BD
0x180027500  mov     rcx, [rdi]; hModule
0x180027503  lea     rdx, aMfcreatedxgisu_0; "MFCreateDXGISurfaceBuffer"
0x18002750a  call    cs:__imp_GetProcAddress
0x180027510  mov     [rsi+28h], rax
0x180027514  test    rax, rax
0x180027517  jz      loc_1800275D0
0x18002751d  mov     rcx, [rdi]; hModule
0x180027520  lea     rdx, aMftenum2; "MFTEnum2"
0x180027527  call    cs:__imp_GetProcAddress
0x18002752d  mov     [rsi+30h], rax
0x180027531  test    rax, rax
0x180027534  jz      loc_1800275E3
0x18002753a  mov     rcx, [rdi]; hModule
0x18002753d  lea     rdx, aMfcreateattrib_0; "MFCreateAttributes"
0x180027544  call    cs:__imp_GetProcAddress
0x18002754a  mov     [rsi+38h], rax
0x18002754e  test    rax, rax
0x180027551  jz      short loc_18002755E
0x180027553  add     rsp, 40h
0x180027557  pop     r14
0x180027559  pop     rdi
0x18002755a  pop     rsi
0x18002755b  pop     rbp
0x18002755c  pop     rbx
0x18002755d  retn
0x18002755e  mov     rcx, [rsp+68h]; this
0x180027563  mov     r8, rbx; unsigned int
0x180027566  mov     edx, 4Bh ; 'K'; void *
0x18002756b  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180027571  mov     rcx, [rsp+68h]; this
0x180027576  mov     r8, rbx; unsigned int
0x180027579  mov     edx, 36h ; '6'; void *
0x18002757e  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180027584  mov     rcx, [rsp+68h]; this
0x180027589  mov     r8, rbx; unsigned int
0x18002758c  mov     edx, 39h ; '9'; void *
0x180027591  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180027597  mov     rcx, [rsp+68h]; this
0x18002759c  mov     r8, rbx; unsigned int
0x18002759f  mov     edx, 3Ch ; '<'; void *
0x1800275a4  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x1800275aa  mov     rcx, [rsp+68h]; this
0x1800275af  mov     r8, rbx; unsigned int
0x1800275b2  mov     edx, 3Fh ; '?'; void *
0x1800275b7  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x1800275bd  mov     rcx, [rsp+68h]; this
0x1800275c2  mov     r8, rbx; unsigned int
0x1800275c5  mov     edx, 42h ; 'B'; void *
0x1800275ca  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x1800275d0  mov     rcx, [rsp+68h]; this
0x1800275d5  mov     r8, rbx; unsigned int
0x1800275d8  mov     edx, 45h ; 'E'; void *
0x1800275dd  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x1800275e3  mov     rcx, [rsp+68h]; this
0x1800275e8  mov     r8, rbx; unsigned int
0x1800275eb  mov     edx, 48h ; 'H'; void *
0x1800275f0  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
```
