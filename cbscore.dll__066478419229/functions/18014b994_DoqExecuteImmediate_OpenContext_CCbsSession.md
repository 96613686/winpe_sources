# DoqExecuteImmediate::OpenContext(CCbsSession *)

- ea: `0x18014b994`
- end: `0x18014bb1c`
- name: `?OpenContext@DoqExecuteImmediate@@AEAAJPEAVCCbsSession@@@Z`
- size: `392`
- prototype: `int(DoqExecuteImmediate *__hidden this, struct CCbsSession *)`
- caller_count: `3`
- callee_count: `10`
- tags: `reparse_path, registry_config, loader_planting, service_task, installer_update`

## callers

- `0x1800cf6f8`
- `0x18014aaac`
- `0x18014b730`

## callees

- `0x180028e24`
- `0x180098538`
- `0x180099548`
- `0x18009cf78`
- `0x1800ad504`
- `0x1800eb920`
- `0x18012b630`
- `0x180145828`
- `0x180145fd0`
- `0x18014b994`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18014ba4f`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18014ba4f`
- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryW` at `0x18014b9de`
- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryW` at `0x18014ba0b`
- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryW` at `0x18014b9de`
- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryW` at `0x18014ba0b`

## string_xrefs

- `0x18014ba04`: `advapi32.dll`
- `0x18014baa2`: `Failed opening driver update context`
- `0x18014b9fb`: `Loaded api-ms-win-service-private-l1-1-2.dll to get I_ScReparseServiceDatabase`
- `0x18014b9d7`: `api-ms-win-service-private-l1-1-2.dll`
- `0x18014ba70`: `Function I_ScReparseServiceDatabase NOT found`
- `0x18014ba64`: `Function I_ScReparseServiceDatabase found`
- `0x18014ba48`: `I_ScReparseServiceDatabase`
- `0x18014ba28`: `Loaded advapi32.dll to get I_ScReparseServiceDatabase`

## pseudocode

```c
__int64 __fastcall DoqExecuteImmediate::OpenContext(DoqExecuteImmediate *this, struct CCbsSession *a2)
{
  HMODULE *v4; // rbx
  HMODULE LibraryW; // rax
  const char *v6; // rdx
  HMODULE v7; // rax
  FARPROC ProcAddress; // rax
  const char *v9; // rdx
  int v10; // eax
  unsigned int v11; // ebx
  int v12; // edx
  int v14; // [rsp+20h] [rbp-38h]
  int v15[2]; // [rsp+30h] [rbp-28h] BYREF
  int v16; // [rsp+38h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  DoqExecuteImmediate::Close(this);
  if ( (unsigned int)CCbsSession::IsOffline(a2) )
    goto LABEL_13;
  v4 = (HMODULE *)((char *)this + 8);
  if ( !*((_QWORD *)this + 1) )
  {
    LibraryW = LoadLibraryW(L"api-ms-win-service-private-l1-1-2.dll");
    wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(
      (char *)this + 8,
      LibraryW);
    if ( *v4 )
    {
      v6 = "Loaded api-ms-win-service-private-l1-1-2.dll to get I_ScReparseServiceDatabase";
LABEL_7:
      LogAdapter::TraceAtLevel<>(1, v6);
      goto LABEL_8;
    }
    v7 = LoadLibraryW(L"advapi32.dll");
    wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(
      (char *)this + 8,
      v7);
    if ( *v4 )
    {
      v6 = "Loaded advapi32.dll to get I_ScReparseServiceDatabase";
      goto LABEL_7;
    }
  }
LABEL_8:
  if ( *v4 && !*((_QWORD *)this + 2) )
  {
    ProcAddress = GetProcAddress(*v4, "I_ScReparseServiceDatabase");
    *((_QWORD *)this + 2) = ProcAddress;
    v9 = "Function I_ScReparseServiceDatabase found";
    if ( !ProcAddress )
      v9 = "Function I_ScReparseServiceDatabase NOT found";
    LogAdapter::TraceAtLevel<>(1, v9);
  }
LABEL_13:
  v10 = DirectDriverOpenContext(a2, this);
  v11 = v10;
  if ( v10 >= 0 )
    return 0;
  v16 = v10;
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed opening driver update context");
    *(_QWORD *)v15 = &v16;
    LOBYTE(v12) = 1;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (_DWORD)LogAdapter::g_Logger,
      v12,
      3,
      (unsigned int)": {}",
      (__int64)v15);
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x5A2,
    (unsigned int)"onecore\\base\\cbs\\core\\driveroperationqueue.cpp",
    (const char *)v11,
    v14);
  return v11;
}

```

## disassembly

```asm
0x18014b994  mov     [rsp+arg_10], rbx
0x18014b999  mov     [rsp+arg_18], rsi
0x18014b99e  push    rdi
0x18014b99f  sub     rsp, 50h
0x18014b9a3  mov     rax, cs:__security_cookie
0x18014b9aa  xor     rax, rsp
0x18014b9ad  mov     [rsp+58h+var_18], rax
0x18014b9b2  mov     rsi, rdx
0x18014b9b5  mov     rdi, rcx
0x18014b9b8  call    ?Close@DoqExecuteImmediate@@QEAAJXZ; DoqExecuteImmediate::Close(void)
0x18014b9bd  mov     rcx, rsi; this
0x18014b9c0  call    ?IsOffline@CCbsSession@@QEBAHXZ; CCbsSession::IsOffline(void)
0x18014b9c5  test    eax, eax
0x18014b9c7  jnz     loc_18014BA7C
0x18014b9cd  lea     rbx, [rdi+8]
0x18014b9d1  cmp     qword ptr [rbx], 0
0x18014b9d5  jnz     short loc_18014BA39
0x18014b9d7  lea     rcx, aApiMsWinServic; "api-ms-win-service-private-l1-1-2.dll"
0x18014b9de  call    cs:__imp_LoadLibraryW
0x18014b9e5  nop     dword ptr [rax+rax+00h]
0x18014b9ea  mov     rdx, rax
0x18014b9ed  mov     rcx, rbx
0x18014b9f0  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHINSTANCE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(HINSTANCE__ *)
0x18014b9f5  cmp     qword ptr [rbx], 0
0x18014b9f9  jz      short loc_18014BA04
0x18014b9fb  lea     rdx, aLoadedApiMsWin; "Loaded api-ms-win-service-private-l1-1-"...
0x18014ba02  jmp     short loc_18014BA2F
0x18014ba04  lea     rcx, aAdvapi32Dll; "advapi32.dll"
0x18014ba0b  call    cs:__imp_LoadLibraryW
0x18014ba12  nop     dword ptr [rax+rax+00h]
0x18014ba17  mov     rdx, rax
0x18014ba1a  mov     rcx, rbx
0x18014ba1d  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHINSTANCE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(HINSTANCE__ *)
0x18014ba22  cmp     qword ptr [rbx], 0
0x18014ba26  jz      short loc_18014BA39
0x18014ba28  lea     rdx, aLoadedAdvapi32; "Loaded advapi32.dll to get I_ScReparseS"...
0x18014ba2f  mov     ecx, 1
0x18014ba34  call    ??$TraceAtLevel@$$V@LogAdapter@@YAXW4LogLevel@0@QEBD@Z; LogAdapter::TraceAtLevel<>(LogAdapter::LogLevel,char const * const)
0x18014ba39  mov     rcx, [rbx]; hModule
0x18014ba3c  test    rcx, rcx
0x18014ba3f  jz      short loc_18014BA7C
0x18014ba41  cmp     qword ptr [rdi+10h], 0
0x18014ba46  jnz     short loc_18014BA7C
0x18014ba48  lea     rdx, aIScreparseserv; "I_ScReparseServiceDatabase"
0x18014ba4f  call    cs:__imp_GetProcAddress
0x18014ba56  nop     dword ptr [rax+rax+00h]
0x18014ba5b  mov     [rdi+10h], rax
0x18014ba5f  mov     ecx, 1
0x18014ba64  lea     rdx, aFunctionIScrep; "Function I_ScReparseServiceDatabase fou"...
0x18014ba6b  test    rax, rax
0x18014ba6e  jnz     short loc_18014BA77
0x18014ba70  lea     rdx, aFunctionIScrep_0; "Function I_ScReparseServiceDatabase NOT"...
0x18014ba77  call    ??$TraceAtLevel@$$V@LogAdapter@@YAXW4LogLevel@0@QEBD@Z; LogAdapter::TraceAtLevel<>(LogAdapter::LogLevel,char const * const)
0x18014ba7c  mov     rdx, rdi
0x18014ba7f  mov     rcx, rsi
0x18014ba82  call    DirectDriverOpenContext
0x18014ba87  mov     ebx, eax
0x18014ba89  test    eax, eax
0x18014ba8b  jns     short loc_18014BAFC
0x18014ba8d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18014ba94  mov     [rsp+58h+var_20], eax
0x18014ba98  test    rcx, rcx
0x18014ba9b  jz      short loc_18014BADF
0x18014ba9d  mov     edi, 3
0x18014baa2  lea     r9, aFailedOpeningD_1; "Failed opening driver update context"
0x18014baa9  mov     r8d, edi
0x18014baac  xor     edx, edx
0x18014baae  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18014bab3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18014baba  lea     rax, [rsp+58h+var_20]
0x18014babf  mov     qword ptr [rsp+58h+var_28], rax
0x18014bac4  lea     r9, asc_1802EE7AC; ": {}"
0x18014bacb  lea     rax, [rsp+58h+var_28]
0x18014bad0  mov     r8d, edi
0x18014bad3  mov     dl, 1
0x18014bad5  mov     qword ptr [rsp+58h+var_38], rax; int
0x18014bada  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18014badf  mov     rcx, [rsp+58h]; this
0x18014bae4  lea     r8, aOnecoreBaseCbs_33; "onecore\\base\\cbs\\core\\driveroperati"...
0x18014baeb  mov     r9d, ebx; char *
0x18014baee  mov     edx, 5A2h; void *
0x18014baf3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18014baf8  mov     eax, ebx
0x18014bafa  jmp     short loc_18014BAFE
0x18014bafc  xor     eax, eax
0x18014bafe  mov     rcx, [rsp+58h+var_18]
0x18014bb03  xor     rcx, rsp; StackCookie
0x18014bb06  call    __security_check_cookie
0x18014bb0b  mov     rbx, [rsp+58h+arg_10]
0x18014bb10  mov     rsi, [rsp+58h+arg_18]
0x18014bb15  add     rsp, 50h
0x18014bb19  pop     rdi
0x18014bb1a  retn
```
