# CloudExperienceHostAPI::OobeDisplayLanguageManagerCore::get_ShouldSkip(uchar *)

- ea: `0x180038a00`
- end: `0x180038b85`
- name: `?get_ShouldSkip@OobeDisplayLanguageManagerCore@CloudExperienceHostAPI@@UEAAJPEAE@Z`
- size: `389`
- prototype: `__int64 __fastcall(CloudExperienceHostAPI::OobeDisplayLanguageManagerCore *__hidden this, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800076b4`
- `0x1800076d4`
- `0x180009814`
- `0x18000a788`
- `0x18000b200`
- `0x1800117bc`
- `0x180032054`
- `0x180035080`
- `0x1800365f0`
- `0x180038a00`
- `0x18006e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180038a91`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180038a91`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180038a5c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180038a5c`

## string_xrefs

- `0x180038a6f`: `shellcommon\shell\oobe\core\components\winrt\oobedisplaylanguagecore.cpp`
- `0x180038aa9`: `shellcommon\shell\oobe\core\components\winrt\oobedisplaylanguagecore.cpp`
- `0x180038afb`: `shellcommon\shell\oobe\core\components\winrt\oobedisplaylanguagecore.cpp`
- `0x180038b27`: `shellcommon\shell\oobe\core\components\winrt\oobedisplaylanguagecore.cpp`
- `0x180038a55`: `coreglobconfig.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CloudExperienceHostAPI::OobeDisplayLanguageManagerCore::get_ShouldSkip(
        CloudExperienceHostAPI::OobeDisplayLanguageManagerCore *this,
        unsigned __int8 *a2)
{
  __int64 v4; // rcx
  HMODULE Library; // rax
  const char *v7; // r9
  unsigned int LastError; // ebx
  FARPROC ProcAddress; // rbx
  int v10; // eax
  __int64 v11; // rbx
  int v12; // [rsp+20h] [rbp-20h]
  HMODULE v13[2]; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  __int64 v15; // [rsp+60h] [rbp+20h] BYREF
  unsigned __int64 v16; // [rsp+68h] [rbp+28h] BYREF
  const wchar_t *v17; // [rsp+70h] [rbp+30h] BYREF
  char v18; // [rsp+78h] [rbp+38h] BYREF

  CloudExperienceHostCoreTelemetry::GlobalizationState<char const (&)[71]>("CloudExperienceHostAPI::OobeDisplayLanguageMa"
                                                                           "nagerCore::get_ShouldSkip");
  *a2 = 0;
  v4 = *((_QWORD *)this + 7);
  if ( v4 )
    return (*(__int64 (__fastcall **)(__int64, unsigned __int8 *))(*(_QWORD *)v4 + 48LL))(v4, a2);
  v15 = 0;
  v16 = 0;
  Library = LoadLibraryExW(L"coreglobconfig.dll", 0, 0x800u);
  v13[0] = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "GetSupportedDisplayLanguages");
    if ( !ProcAddress )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE3,
        (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobedisplaylanguagecore.cpp",
        (const char *)0x8000FFFFLL,
        v12);
      LastError = -2147418113;
      goto LABEL_15;
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v15,
      0);
    v10 = ((__int64 (__fastcall *)(__int64, _QWORD, _QWORD, __int64 *))ProcAddress)(59, 0, 0, &v15);
    LastError = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xEA,
        (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobedisplaylanguagecore.cpp",
        (const char *)(unsigned int)v10,
        (int)&v16);
      goto LABEL_15;
    }
    if ( v16 >= 2 )
    {
      v17 = L"CloudAssignedLanguage";
      v11 = *(_QWORD *)AutoPilotUtils::AutoPilotTryGetStringPolicy(&v18, &v17);
      Windows::Internal::String::~String((Windows::Internal::String *)&v18);
      if ( !v11 )
      {
LABEL_14:
        LastError = 0;
        goto LABEL_15;
      }
    }
    else if ( !v16 )
    {
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0xF2,
        (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobedisplaylanguagecore.cpp",
        (const char *)0x8000FFFFLL,
        (int)&v16);
    }
    *a2 = 1;
    goto LABEL_14;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0xDC,
                (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobedisplaylanguagecore.cpp",
                v7);
LABEL_15:
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(v13);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v15);
  return LastError;
}

```

## disassembly

```asm
0x180038a00  push    rbp
0x180038a02  push    rbx
0x180038a03  push    rdi
0x180038a04  mov     rbp, rsp
0x180038a07  sub     rsp, 40h
0x180038a0b  mov     rdi, rdx
0x180038a0e  mov     rbx, rcx
0x180038a11  lea     rcx, aCloudexperienc_5; "CloudExperienceHostAPI::OobeDisplayLang"...
0x180038a18  call    ??$GlobalizationState@AEAY0EH@$$CBD@CloudExperienceHostCoreTelemetry@@SAXAEAY0EH@$$CBD@Z; CloudExperienceHostCoreTelemetry::GlobalizationState<char const (&)[71]>(char const (&)[71])
0x180038a1d  mov     byte ptr [rdi], 0
0x180038a20  mov     rcx, [rbx+38h]
0x180038a24  test    rcx, rcx
0x180038a27  jz      short loc_180038A3D
0x180038a29  mov     rax, [rcx]
0x180038a2c  mov     rdx, rdi
0x180038a2f  mov     rax, [rax+30h]
0x180038a33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038a38  jmp     loc_180038B7D
0x180038a3d  mov     [rbp+arg_0], 0
0x180038a45  mov     [rbp+arg_8], 0
0x180038a4d  xor     edx, edx; hFile
0x180038a4f  mov     r8d, 800h; dwFlags
0x180038a55  lea     rcx, aCoreglobconfig; "coreglobconfig.dll"
0x180038a5c  call    cs:__imp_LoadLibraryExW
0x180038a62  mov     [rbp+var_10], rax
0x180038a66  test    rax, rax
0x180038a69  jnz     short loc_180038A87
0x180038a6b  mov     rcx, [rbp+18h]; this
0x180038a6f  lea     r8, aShellcommonShe_18; "shellcommon\\shell\\oobe\\core\\compone"...
0x180038a76  mov     edx, 0DCh; void *
0x180038a7b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180038a80  mov     ebx, eax
0x180038a82  jmp     loc_180038B68
0x180038a87  lea     rdx, aGetsupporteddi; "GetSupportedDisplayLanguages"
0x180038a8e  mov     rcx, rax; hModule
0x180038a91  call    cs:__imp_GetProcAddress
0x180038a97  mov     rbx, rax
0x180038a9a  test    rax, rax
0x180038a9d  jnz     short loc_180038AC4
0x180038a9f  mov     rcx, [rbp+18h]; this
0x180038aa3  mov     r9d, 8000FFFFh; char *
0x180038aa9  lea     r8, aShellcommonShe_18; "shellcommon\\shell\\oobe\\core\\compone"...
0x180038ab0  mov     edx, 0E3h; void *
0x180038ab5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038aba  mov     ebx, 8000FFFFh
0x180038abf  jmp     loc_180038B68
0x180038ac4  xor     edx, edx
0x180038ac6  lea     rcx, [rbp+arg_0]
0x180038aca  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180038acf  mov     ecx, 3Bh ; ';'
0x180038ad4  lea     rax, [rbp+arg_8]
0x180038ad8  mov     qword ptr [rsp+40h+var_20], rax; int
0x180038add  lea     r9, [rbp+arg_0]
0x180038ae1  xor     r8d, r8d
0x180038ae4  xor     edx, edx
0x180038ae6  mov     rax, rbx
0x180038ae9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038aee  mov     ebx, eax
0x180038af0  test    eax, eax
0x180038af2  jns     short loc_180038B0E
0x180038af4  mov     rcx, [rbp+18h]; this
0x180038af8  mov     r9d, eax; char *
0x180038afb  lea     r8, aShellcommonShe_18; "shellcommon\\shell\\oobe\\core\\compone"...
0x180038b02  mov     edx, 0EAh; void *
0x180038b07  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038b0c  jmp     short loc_180038B68
0x180038b0e  mov     rax, [rbp+arg_8]
0x180038b12  cmp     rax, 2
0x180038b16  jnb     short loc_180038B3A
0x180038b18  test    rax, rax
0x180038b1b  jnz     short loc_180038B63
0x180038b1d  mov     rcx, [rbp+18h]; this
0x180038b21  mov     r9d, 8000FFFFh; char *
0x180038b27  lea     r8, aShellcommonShe_18; "shellcommon\\shell\\oobe\\core\\compone"...
0x180038b2e  mov     edx, 0F2h; void *
0x180038b33  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180038b38  jmp     short loc_180038B63
0x180038b3a  lea     rax, aCloudassignedl; "CloudAssignedLanguage"
0x180038b41  mov     [rbp+arg_10], rax
0x180038b45  lea     rdx, [rbp+arg_10]
0x180038b49  lea     rcx, [rbp+arg_18]
0x180038b4d  call    ?AutoPilotTryGetStringPolicy@AutoPilotUtils@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBQEBG@Z; AutoPilotUtils::AutoPilotTryGetStringPolicy(ushort const * const &)
0x180038b52  mov     rbx, [rax]
0x180038b55  lea     rcx, [rbp+arg_18]; this
0x180038b59  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180038b5e  test    rbx, rbx
0x180038b61  jz      short loc_180038B66
0x180038b63  mov     byte ptr [rdi], 1
0x180038b66  xor     ebx, ebx
0x180038b68  lea     rcx, [rbp+var_10]
0x180038b6c  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x180038b71  nop
0x180038b72  lea     rcx, [rbp+arg_0]
0x180038b76  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180038b7b  mov     eax, ebx
0x180038b7d  add     rsp, 40h
0x180038b81  pop     rdi
0x180038b82  pop     rbx
0x180038b83  pop     rbp
0x180038b84  retn
```
