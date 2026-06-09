# IgdResolver::SsdpApi::SsdpApi(void)

- ea: `0x1800807e0`
- end: `0x180080a44`
- name: `??0SsdpApi@IgdResolver@@QEAA@XZ`
- size: `612`
- prototype: `__int64 __fastcall(IgdResolver::SsdpApi *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x1800803c8`

## callees

- `0x18007eeec`
- `0x1800807e0`
- `0x180082824`
- `0x1800baf04`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008086d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800808a1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800808d3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180080905`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180080937`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180080969`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008099b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800809cd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008086d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800808a1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800808d3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180080905`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180080937`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180080969`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008099b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800809cd`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180080831`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180080831`

## string_xrefs

- `0x180080851`: `onecore\net\netprofiles\service\src\igd\lib\igdresolver.cpp`
- `0x180080885`: `onecore\net\netprofiles\service\src\igd\lib\igdresolver.cpp`
- `0x1800808b7`: `onecore\net\netprofiles\service\src\igd\lib\igdresolver.cpp`
- `0x1800808e9`: `onecore\net\netprofiles\service\src\igd\lib\igdresolver.cpp`
- `0x18008091b`: `onecore\net\netprofiles\service\src\igd\lib\igdresolver.cpp`
- `0x18008094d`: `onecore\net\netprofiles\service\src\igd\lib\igdresolver.cpp`
- `0x18008097f`: `onecore\net\netprofiles\service\src\igd\lib\igdresolver.cpp`
- `0x1800809b1`: `onecore\net\netprofiles\service\src\igd\lib\igdresolver.cpp`
- `0x1800809e0`: `onecore\net\netprofiles\service\src\igd\lib\igdresolver.cpp`
- `0x1800808fb`: `FindServicesClose`
- `0x1800808c9`: `FindServices`
- `0x18008092d`: `GetFirstService`
- `0x18008082a`: `ssdpapi.dll`
- `0x18008095f`: `GetNextService`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
IgdResolver::SsdpApi *__fastcall IgdResolver::SsdpApi::SsdpApi(IgdResolver::SsdpApi *this)
{
  HMODULE LibraryW; // rbx
  const char *v3; // r9
  const char *v4; // r9
  const char *v5; // r9
  FARPROC v6; // r13
  const char *v7; // r9
  FARPROC v8; // r12
  const char *v9; // r9
  FARPROC v10; // r15
  const char *v11; // r9
  FARPROC v12; // r14
  FARPROC v13; // rbp
  const char *v14; // r9
  FARPROC v15; // rsi
  const char *v16; // r9
  FARPROC v17; // rax
  const char *v18; // r9
  HMODULE v20; // [rsp+20h] [rbp-68h] BYREF
  FARPROC ProcAddress; // [rsp+28h] [rbp-60h]
  IgdResolver::SsdpApi *v22; // [rsp+30h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v22 = this;
  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_BYTE *)this + 72) = 0;
  *((_QWORD *)this + 10) = -1;
  LibraryW = LoadLibraryW(L"ssdpapi.dll");
  v20 = LibraryW;
  if ( !LibraryW )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0xD7,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\igd\\lib\\igdresolver.cpp",
      v3);
  ProcAddress = GetProcAddress(LibraryW, "SsdpStartup");
  if ( !ProcAddress )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0xDA,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\igd\\lib\\igdresolver.cpp",
      v4);
  v6 = GetProcAddress(LibraryW, "SsdpCleanup");
  if ( !v6 )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0xDD,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\igd\\lib\\igdresolver.cpp",
      v5);
  v8 = GetProcAddress(LibraryW, "FindServices");
  if ( !v8 )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0xE1,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\igd\\lib\\igdresolver.cpp",
      v7);
  v10 = GetProcAddress(LibraryW, "FindServicesClose");
  if ( !v10 )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0xE4,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\igd\\lib\\igdresolver.cpp",
      v9);
  v12 = GetProcAddress(LibraryW, "GetFirstService");
  if ( !v12 )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0xE8,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\igd\\lib\\igdresolver.cpp",
      v11);
  v13 = GetProcAddress(LibraryW, "GetNextService");
  if ( !v13 )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0xEC,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\igd\\lib\\igdresolver.cpp",
      v14);
  v15 = GetProcAddress(LibraryW, "RegisterNotification");
  if ( !v15 )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0xF1,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\igd\\lib\\igdresolver.cpp",
      v16);
  v17 = GetProcAddress(LibraryW, "DeregisterNotification");
  if ( !v17 )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0xF5,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\igd\\lib\\igdresolver.cpp",
      v18);
  *((_QWORD *)this + 1) = ProcAddress;
  *((_QWORD *)this + 2) = v6;
  *((_QWORD *)this + 3) = v8;
  *((_QWORD *)this + 4) = v10;
  *((_QWORD *)this + 5) = v12;
  *((_QWORD *)this + 6) = v13;
  *((_QWORD *)this + 7) = v15;
  *((_QWORD *)this + 8) = v17;
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>::operator=(
    this,
    &v20);
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v20);
  return this;
}

```

## disassembly

```asm
0x1800807e0  push    rbx
0x1800807e2  push    rbp
0x1800807e3  push    rsi
0x1800807e4  push    rdi
0x1800807e5  push    r12
0x1800807e7  push    r13
0x1800807e9  push    r14
0x1800807eb  push    r15
0x1800807ed  sub     rsp, 48h
0x1800807f1  mov     rdi, rcx
0x1800807f4  mov     [rsp+88h+var_58], rcx
0x1800807f9  xor     esi, esi
0x1800807fb  mov     [rcx], rsi
0x1800807fe  mov     [rcx+8], rsi
0x180080802  mov     [rcx+10h], rsi
0x180080806  mov     [rcx+18h], rsi
0x18008080a  mov     [rcx+20h], rsi
0x18008080e  mov     [rcx+28h], rsi
0x180080812  mov     [rcx+30h], rsi
0x180080816  mov     [rcx+38h], rsi
0x18008081a  mov     [rcx+40h], rsi
0x18008081e  mov     [rcx+48h], sil
0x180080822  mov     qword ptr [rcx+50h], 0FFFFFFFFFFFFFFFFh
0x18008082a  lea     rcx, aSsdpapiDll; "ssdpapi.dll"
0x180080831  call    cs:__imp_LoadLibraryW
0x180080837  mov     rbx, rax
0x18008083a  mov     [rsp+88h+var_68], rax
0x18008083f  test    rax, rax
0x180080842  setz    al
0x180080845  mov     rcx, [rsp+88h]; this
0x18008084d  test    al, al
0x18008084f  jz      short loc_180080863
0x180080851  lea     r8, aOnecoreNetNetp_54; "onecore\\net\\netprofiles\\service\\src"...
0x180080858  mov     edx, 0D7h; void *
0x18008085d  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180080863  lea     rdx, aSsdpstartup; "SsdpStartup"
0x18008086a  mov     rcx, rbx; hModule
0x18008086d  call    cs:__imp_GetProcAddress
0x180080873  mov     [rsp+88h+var_60], rax
0x180080878  mov     rcx, [rsp+88h]; this
0x180080880  test    rax, rax
0x180080883  jnz     short loc_180080897
0x180080885  lea     r8, aOnecoreNetNetp_54; "onecore\\net\\netprofiles\\service\\src"...
0x18008088c  mov     edx, 0DAh; void *
0x180080891  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180080897  lea     rdx, aSsdpcleanup; "SsdpCleanup"
0x18008089e  mov     rcx, rbx; hModule
0x1800808a1  call    cs:__imp_GetProcAddress
0x1800808a7  mov     r13, rax
0x1800808aa  mov     rcx, [rsp+88h]; this
0x1800808b2  test    rax, rax
0x1800808b5  jnz     short loc_1800808C9
0x1800808b7  lea     r8, aOnecoreNetNetp_54; "onecore\\net\\netprofiles\\service\\src"...
0x1800808be  mov     edx, 0DDh; void *
0x1800808c3  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1800808c9  lea     rdx, aFindservices; "FindServices"
0x1800808d0  mov     rcx, rbx; hModule
0x1800808d3  call    cs:__imp_GetProcAddress
0x1800808d9  mov     r12, rax
0x1800808dc  mov     rcx, [rsp+88h]; this
0x1800808e4  test    rax, rax
0x1800808e7  jnz     short loc_1800808FB
0x1800808e9  lea     r8, aOnecoreNetNetp_54; "onecore\\net\\netprofiles\\service\\src"...
0x1800808f0  mov     edx, 0E1h; void *
0x1800808f5  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1800808fb  lea     rdx, aFindservicescl; "FindServicesClose"
0x180080902  mov     rcx, rbx; hModule
0x180080905  call    cs:__imp_GetProcAddress
0x18008090b  mov     r15, rax
0x18008090e  mov     rcx, [rsp+88h]; this
0x180080916  test    rax, rax
0x180080919  jnz     short loc_18008092D
0x18008091b  lea     r8, aOnecoreNetNetp_54; "onecore\\net\\netprofiles\\service\\src"...
0x180080922  mov     edx, 0E4h; void *
0x180080927  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18008092d  lea     rdx, aGetfirstservic; "GetFirstService"
0x180080934  mov     rcx, rbx; hModule
0x180080937  call    cs:__imp_GetProcAddress
0x18008093d  mov     r14, rax
0x180080940  mov     rcx, [rsp+88h]; this
0x180080948  test    rax, rax
0x18008094b  jnz     short loc_18008095F
0x18008094d  lea     r8, aOnecoreNetNetp_54; "onecore\\net\\netprofiles\\service\\src"...
0x180080954  mov     edx, 0E8h; void *
0x180080959  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18008095f  lea     rdx, aGetnextservice; "GetNextService"
0x180080966  mov     rcx, rbx; hModule
0x180080969  call    cs:__imp_GetProcAddress
0x18008096f  mov     rbp, rax
0x180080972  mov     rcx, [rsp+88h]; this
0x18008097a  test    rax, rax
0x18008097d  jnz     short loc_180080991
0x18008097f  lea     r8, aOnecoreNetNetp_54; "onecore\\net\\netprofiles\\service\\src"...
0x180080986  mov     edx, 0ECh; void *
0x18008098b  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180080991  lea     rdx, aRegisternotifi; "RegisterNotification"
0x180080998  mov     rcx, rbx; hModule
0x18008099b  call    cs:__imp_GetProcAddress
0x1800809a1  mov     rsi, rax
0x1800809a4  mov     rcx, [rsp+88h]; this
0x1800809ac  test    rax, rax
0x1800809af  jnz     short loc_1800809C3
0x1800809b1  lea     r8, aOnecoreNetNetp_54; "onecore\\net\\netprofiles\\service\\src"...
0x1800809b8  mov     edx, 0F1h; void *
0x1800809bd  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1800809c3  lea     rdx, aDeregisternoti; "DeregisterNotification"
0x1800809ca  mov     rcx, rbx; hModule
0x1800809cd  call    cs:__imp_GetProcAddress
0x1800809d3  mov     rcx, [rsp+88h]; this
0x1800809db  test    rax, rax
0x1800809de  jnz     short loc_1800809F2
0x1800809e0  lea     r8, aOnecoreNetNetp_54; "onecore\\net\\netprofiles\\service\\src"...
0x1800809e7  mov     edx, 0F5h; void *
0x1800809ec  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1800809f2  mov     rcx, [rsp+88h+var_60]
0x1800809f7  mov     [rdi+8], rcx
0x1800809fb  mov     [rdi+10h], r13
0x1800809ff  mov     [rdi+18h], r12
0x180080a03  mov     [rdi+20h], r15
0x180080a07  mov     [rdi+28h], r14
0x180080a0b  mov     [rdi+30h], rbp
0x180080a0f  mov     [rdi+38h], rsi
0x180080a13  mov     [rdi+40h], rax
0x180080a17  lea     rdx, [rsp+88h+var_68]
0x180080a1c  mov     rcx, rdi
0x180080a1f  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>> &&)
0x180080a24  nop
0x180080a25  lea     rcx, [rsp+88h+var_68]
0x180080a2a  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x180080a2f  nop
0x180080a30  mov     rax, rdi
0x180080a33  add     rsp, 48h
0x180080a37  pop     r15
0x180080a39  pop     r14
0x180080a3b  pop     r13
0x180080a3d  pop     r12
0x180080a3f  pop     rdi
0x180080a40  pop     rsi
0x180080a41  pop     rbp
0x180080a42  pop     rbx
0x180080a43  retn
```
