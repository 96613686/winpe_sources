# HnsClientApi::LoadHnsApiLib(void)

- ea: `0x180082f4c`
- end: `0x1800830ff`
- name: `?LoadHnsApiLib@HnsClientApi@@AEAAXXZ`
- size: `435`
- prototype: `void __fastcall(HnsClientApi *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180082e30`

## callees

- `0x180015608`
- `0x180020d20`
- `0x18007eeec`
- `0x180082824`
- `0x180082f4c`
- `0x180083108`
- `0x1800baf04`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180082f68`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180082f8a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180082f68`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180082f8a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180082fd3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180083001`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008302f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008305d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008308a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800830b8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180082fd3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180083001`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008302f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008305d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008308a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800830b8`

## string_xrefs

- `0x180082f83`: `computenetwork.dll`
- `0x180082f61`: `XboxNetApiSvcExtHost.dll`
- `0x180083025`: `HcnCloseGuestNetworkService`
- `0x180083080`: `HcnRegisterGuestNetworkServiceCallback`
- `0x180082ff7`: `HcnOpenGuestNetworkService`
- `0x180082fc9`: `HcnEnumerateGuestNetworkServices`
- `0x1800830ae`: `HcnUnregisterGuestNetworkServiceCallback`
- `0x180082fb7`: `onecore\net\netprofiles\service\src\kryptonhostmanager\libs\hnsclient\hnsclientapi.cpp`
- `0x180082fe7`: `onecore\net\netprofiles\service\src\kryptonhostmanager\libs\hnsclient\hnsclientapi.cpp`
- `0x180083015`: `onecore\net\netprofiles\service\src\kryptonhostmanager\libs\hnsclient\hnsclientapi.cpp`
- `0x180083043`: `onecore\net\netprofiles\service\src\kryptonhostmanager\libs\hnsclient\hnsclientapi.cpp`
- `0x180083071`: `onecore\net\netprofiles\service\src\kryptonhostmanager\libs\hnsclient\hnsclientapi.cpp`
- `0x18008309e`: `onecore\net\netprofiles\service\src\kryptonhostmanager\libs\hnsclient\hnsclientapi.cpp`
- `0x1800830cc`: `onecore\net\netprofiles\service\src\kryptonhostmanager\libs\hnsclient\hnsclientapi.cpp`
- `0x180083053`: `HcnQueryGuestNetworkServiceProperties`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall HnsClientApi::LoadHnsApiLib(HnsClientApi *this)
{
  HMODULE Library; // rbx
  HMODULE v3; // rax
  FARPROC ProcAddress; // rax
  const char *v5; // r9
  FARPROC v6; // rax
  const char *v7; // r9
  FARPROC v8; // rax
  const char *v9; // r9
  FARPROC v10; // rax
  const char *v11; // r9
  FARPROC v12; // rax
  const char *v13; // r9
  FARPROC v14; // rax
  const char *v15; // r9
  int v16[6]; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  Library = LoadLibraryExW(L"XboxNetApiSvcExtHost.dll", 0, 0x800u);
  *(_QWORD *)v16 = Library;
  if ( !Library )
  {
    v3 = LoadLibraryExW(L"computenetwork.dll", 0, 0x800u);
    wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(
      v16,
      v3);
    Library = *(HMODULE *)v16;
  }
  if ( !Library )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x21,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\kryptonhostmanager\\libs\\hnsclient\\hnsclientapi.cpp",
      (const char *)0x8007007ELL,
      v16[0]);
  ProcAddress = GetProcAddress(Library, "HcnEnumerateGuestNetworkServices");
  *((_QWORD *)this + 1) = ProcAddress;
  if ( !ProcAddress )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x25,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\kryptonhostmanager\\libs\\hnsclient\\hnsclientapi.cpp",
      v5);
  v6 = GetProcAddress(Library, "HcnOpenGuestNetworkService");
  *((_QWORD *)this + 2) = v6;
  if ( !v6 )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x29,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\kryptonhostmanager\\libs\\hnsclient\\hnsclientapi.cpp",
      v7);
  v8 = GetProcAddress(Library, "HcnCloseGuestNetworkService");
  *((_QWORD *)this + 3) = v8;
  if ( !v8 )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x2D,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\kryptonhostmanager\\libs\\hnsclient\\hnsclientapi.cpp",
      v9);
  v10 = GetProcAddress(Library, "HcnQueryGuestNetworkServiceProperties");
  *((_QWORD *)this + 4) = v10;
  if ( !v10 )
    wil::details::in1diag3::_Log_GetLastError(
      retaddr,
      (void *)0x32,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\kryptonhostmanager\\libs\\hnsclient\\hnsclientapi.cpp",
      v11);
  v12 = GetProcAddress(Library, "HcnRegisterGuestNetworkServiceCallback");
  *((_QWORD *)this + 5) = v12;
  if ( !v12 )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x36,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\kryptonhostmanager\\libs\\hnsclient\\hnsclientapi.cpp",
      v13);
  v14 = GetProcAddress(Library, "HcnUnregisterGuestNetworkServiceCallback");
  *((_QWORD *)this + 6) = v14;
  if ( !v14 )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x3A,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\kryptonhostmanager\\libs\\hnsclient\\hnsclientapi.cpp",
      v15);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>::operator=(
    this,
    v16);
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(v16);
}

```

## disassembly

```asm
0x180082f4c  mov     [rsp+arg_8], rbx
0x180082f51  push    rdi
0x180082f52  sub     rsp, 30h
0x180082f56  mov     rdi, rcx
0x180082f59  xor     edx, edx; hFile
0x180082f5b  mov     r8d, 800h; dwFlags
0x180082f61  lea     rcx, aXboxnetapisvce; "XboxNetApiSvcExtHost.dll"
0x180082f68  call    cs:__imp_LoadLibraryExW
0x180082f6e  mov     rbx, rax
0x180082f71  mov     qword ptr [rsp+38h+var_18], rax; int
0x180082f76  test    rax, rax
0x180082f79  jnz     short loc_180082FA2
0x180082f7b  xor     edx, edx; hFile
0x180082f7d  mov     r8d, 800h; dwFlags
0x180082f83  lea     rcx, aComputenetwork; "computenetwork.dll"
0x180082f8a  call    cs:__imp_LoadLibraryExW
0x180082f90  mov     rdx, rax
0x180082f93  lea     rcx, [rsp+38h+var_18]
0x180082f98  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHINSTANCE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(HINSTANCE__ *)
0x180082f9d  mov     rbx, qword ptr [rsp+38h+var_18]
0x180082fa2  test    rbx, rbx
0x180082fa5  setz    al
0x180082fa8  mov     rcx, [rsp+38h]; this
0x180082fad  test    al, al
0x180082faf  jz      short loc_180082FC9
0x180082fb1  mov     r9d, 8007007Eh; char *
0x180082fb7  lea     r8, aOnecoreNetNetp_31; "onecore\\net\\netprofiles\\service\\src"...
0x180082fbe  mov     edx, 21h ; '!'; void *
0x180082fc3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180082fc9  lea     rdx, aHcnenumerategu; "HcnEnumerateGuestNetworkServices"
0x180082fd0  mov     rcx, rbx; hModule
0x180082fd3  call    cs:__imp_GetProcAddress
0x180082fd9  mov     [rdi+8], rax
0x180082fdd  mov     rcx, [rsp+38h]; this
0x180082fe2  test    rax, rax
0x180082fe5  jnz     short loc_180082FF7
0x180082fe7  lea     r8, aOnecoreNetNetp_31; "onecore\\net\\netprofiles\\service\\src"...
0x180082fee  lea     edx, [rax+25h]; void *
0x180082ff1  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180082ff7  lea     rdx, aHcnopenguestne; "HcnOpenGuestNetworkService"
0x180082ffe  mov     rcx, rbx; hModule
0x180083001  call    cs:__imp_GetProcAddress
0x180083007  mov     [rdi+10h], rax
0x18008300b  mov     rcx, [rsp+38h]; this
0x180083010  test    rax, rax
0x180083013  jnz     short loc_180083025
0x180083015  lea     r8, aOnecoreNetNetp_31; "onecore\\net\\netprofiles\\service\\src"...
0x18008301c  lea     edx, [rax+29h]; void *
0x18008301f  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180083025  lea     rdx, aHcncloseguestn; "HcnCloseGuestNetworkService"
0x18008302c  mov     rcx, rbx; hModule
0x18008302f  call    cs:__imp_GetProcAddress
0x180083035  mov     [rdi+18h], rax
0x180083039  mov     rcx, [rsp+38h]; this
0x18008303e  test    rax, rax
0x180083041  jnz     short loc_180083053
0x180083043  lea     r8, aOnecoreNetNetp_31; "onecore\\net\\netprofiles\\service\\src"...
0x18008304a  lea     edx, [rax+2Dh]; void *
0x18008304d  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180083053  lea     rdx, aHcnqueryguestn; "HcnQueryGuestNetworkServiceProperties"
0x18008305a  mov     rcx, rbx; hModule
0x18008305d  call    cs:__imp_GetProcAddress
0x180083063  mov     [rdi+20h], rax
0x180083067  mov     rcx, [rsp+38h]; this
0x18008306c  test    rax, rax
0x18008306f  jnz     short loc_180083080
0x180083071  lea     r8, aOnecoreNetNetp_31; "onecore\\net\\netprofiles\\service\\src"...
0x180083078  lea     edx, [rax+32h]; void *
0x18008307b  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x180083080  lea     rdx, aHcnregistergue; "HcnRegisterGuestNetworkServiceCallback"
0x180083087  mov     rcx, rbx; hModule
0x18008308a  call    cs:__imp_GetProcAddress
0x180083090  mov     [rdi+28h], rax
0x180083094  mov     rcx, [rsp+38h]; this
0x180083099  test    rax, rax
0x18008309c  jnz     short loc_1800830AE
0x18008309e  lea     r8, aOnecoreNetNetp_31; "onecore\\net\\netprofiles\\service\\src"...
0x1800830a5  lea     edx, [rax+36h]; void *
0x1800830a8  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1800830ae  lea     rdx, aHcnunregisterg; "HcnUnregisterGuestNetworkServiceCallbac"...
0x1800830b5  mov     rcx, rbx; hModule
0x1800830b8  call    cs:__imp_GetProcAddress
0x1800830be  mov     [rdi+30h], rax
0x1800830c2  mov     rcx, [rsp+38h]; this
0x1800830c7  test    rax, rax
0x1800830ca  jnz     short loc_1800830DC
0x1800830cc  lea     r8, aOnecoreNetNetp_31; "onecore\\net\\netprofiles\\service\\src"...
0x1800830d3  lea     edx, [rax+3Ah]; void *
0x1800830d6  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1800830dc  lea     rdx, [rsp+38h+var_18]
0x1800830e1  mov     rcx, rdi
0x1800830e4  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>> &&)
0x1800830e9  nop
0x1800830ea  lea     rcx, [rsp+38h+var_18]
0x1800830ef  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x1800830f4  mov     rbx, [rsp+38h+arg_8]
0x1800830f9  add     rsp, 30h
0x1800830fd  pop     rdi
0x1800830fe  retn
```
