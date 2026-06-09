# Microsoft::HostGuardian::Client::HgServicePlugin::HgServicePlugin(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x180013d28`
- end: `0x180013fd6`
- name: `??0HgServicePlugin@Client@HostGuardian@Microsoft@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `686`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000ba8c`

## callees

- `0x180001770`
- `0x1800021f0`
- `0x180003d0c`
- `0x180003e30`
- `0x180004274`
- `0x1800077f8`
- `0x180007878`
- `0x1800081e0`
- `0x1800087a4`
- `0x18000977c`
- `0x18000a7bc`
- `0x18000a84c`
- `0x18000e0b0`
- `0x180013d28`
- `0x18001486c`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180013eb5`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180013eb5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013ed1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013ef3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013ed1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013ef3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013ebd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013ebd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013dfb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013eaa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013dfb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013eaa`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180013de9`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180013de9`

## string_xrefs

- `0x180013e5b`: `hgsclientplugin.dll`
- `0x180013e2b`: `Plugin was not found.  Using the default.`
- `0x180013f31`: `servercommon\base\securehostingservice\common\service\lib\hgserviceplugin.cpp`
- `0x180013f78`: `servercommon\base\securehostingservice\common\service\lib\hgserviceplugin.cpp`
- `0x180013fb2`: `servercommon\base\securehostingservice\common\service\lib\hgserviceplugin.cpp`
- `0x180013fc4`: `servercommon\base\securehostingservice\common\service\lib\hgserviceplugin.cpp`
- `0x180013ec7`: `InitializeAttestationPlugin`
- `0x180013ee8`: `UninitializeAttestationPlugin`
- `0x180013f22`: `Plugin initialization failed.`

## pseudocode

```c
__int64 __fastcall Microsoft::HostGuardian::Client::HgServicePlugin::HgServicePlugin(__int64 a1, __int64 a2)
{
  char i; // r14
  const WCHAR *v5; // rcx
  HMODULE LibraryW; // rsi
  DWORD LastError; // eax
  __int64 v8; // rcx
  DWORD v9; // ebx
  __int64 appended; // rax
  HMODULE v11; // r14
  DWORD v12; // ebx
  FARPROC ProcAddress; // rax
  const char *v14; // r9
  FARPROC v15; // rax
  const char *v16; // r9
  unsigned int v17; // eax
  __int64 v19; // rax
  __int64 v20; // rcx
  unsigned int v21; // [rsp+20h] [rbp-79h]
  const char *v22; // [rsp+28h] [rbp-71h]
  __int128 v23; // [rsp+30h] [rbp-69h] BYREF
  __int64 v24; // [rsp+40h] [rbp-59h]
  __int64 v25; // [rsp+48h] [rbp-51h]
  __int64 v26; // [rsp+50h] [rbp-49h]
  LPCWSTR lpLibFileName[4]; // [rsp+60h] [rbp-39h] BYREF
  _OWORD Src[4]; // [rsp+80h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v26 = a1;
  *(_QWORD *)a1 = &Microsoft::HostGuardian::Client::HgServicePlugin::`vftable';
  *(_QWORD *)(a1 + 8) = 0;
  memset_0(Src, 0, sizeof(Src));
  *(_OWORD *)(a1 + 40) = Src[0];
  *(_OWORD *)(a1 + 56) = Src[1];
  *(_OWORD *)(a1 + 72) = Src[2];
  *(_OWORD *)(a1 + 88) = Src[3];
  *(_OWORD *)(a1 + 104) = 0;
  *(_QWORD *)(a1 + 120) = 0;
  *(_QWORD *)(a1 + 128) = 7;
  *(_WORD *)(a1 + 104) = 0;
  std::wstring::wstring(lpLibFileName, a2);
  for ( i = 0; ; i = 1 )
  {
    v5 = (const WCHAR *)lpLibFileName;
    if ( lpLibFileName[3] > (LPCWSTR)7 )
      v5 = lpLibFileName[0];
    LibraryW = LoadLibraryW(v5);
    if ( LibraryW )
      break;
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError != 2 && LastError != 126 && LastError != 87 || i )
    {
      if ( (Microsoft_Windows_HostGuardianClient_ServiceEnableBits & 0x20) != 0 )
      {
        v19 = std::wstring::c_str(lpLibFileName);
        McTemplateU0z_EventWriteTransfer(v20, PluginLoadFailed, v19);
      }
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x25,
        (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgserviceplugin.cpp",
        (const char *)v9,
        v21);
    }
    if ( (Microsoft_Windows_HostGuardianClient_ServiceEnableBits & 4) != 0 )
      McTemplateU0zq_EventWriteTransfer(
        v8,
        ServiceDebugWarning,
        L"Plugin was not found.  Using the default.",
        LastError);
    v23 = 0;
    v24 = 0;
    v25 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v23, L"hgsclientplugin.dll", 19);
    appended = Microsoft::HostGuardian::Client::Utilities::AppendBinaryToSystemPath(Src);
    std::wstring::operator=(lpLibFileName, appended);
    std::wstring::~wstring(Src);
  }
  std::wstring::operator=(a1 + 104, lpLibFileName);
  v11 = *(HMODULE *)(a1 + 8);
  if ( v11 )
  {
    v12 = GetLastError();
    FreeLibrary(v11);
    SetLastError(v12);
  }
  *(_QWORD *)(a1 + 8) = LibraryW;
  ProcAddress = GetProcAddress(LibraryW, "InitializeAttestationPlugin");
  *(_QWORD *)(a1 + 24) = ProcAddress;
  if ( !ProcAddress )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x2F,
      (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgserviceplugin.cpp",
      v14);
  v15 = GetProcAddress(*(HMODULE *)(a1 + 8), "UninitializeAttestationPlugin");
  *(_QWORD *)(a1 + 32) = v15;
  if ( !v15 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x31,
      (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgserviceplugin.cpp",
      v16);
  *(_DWORD *)(a1 + 40) = 64;
  v17 = (*(__int64 (__fastcall **)(__int64, __int64))(a1 + 24))(a1 + 40, a1 + 16);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x35,
    (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgserviceplugin.cpp",
    (const char *)v17,
    (int)"Plugin initialization failed.",
    v22);
  std::wstring::~wstring(lpLibFileName);
  return a1;
}

```

## disassembly

```asm
0x180013d28  mov     [rsp-8+arg_10], rbx
0x180013d2d  mov     [rsp-8+arg_18], rsi
0x180013d32  push    rbp
0x180013d33  push    rdi
0x180013d34  push    r12
0x180013d36  push    r14
0x180013d38  push    r15
0x180013d3a  lea     rbp, [rsp-37h]
0x180013d3f  sub     rsp, 0D0h
0x180013d46  mov     rax, cs:__security_cookie
0x180013d4d  xor     rax, rsp
0x180013d50  mov     [rbp+57h+var_30], rax
0x180013d54  mov     rbx, rdx
0x180013d57  mov     rdi, rcx
0x180013d5a  mov     [rbp+57h+var_A0], rcx
0x180013d5e  lea     rax, ??_7HgServicePlugin@Client@HostGuardian@Microsoft@@6B@; const Microsoft::HostGuardian::Client::HgServicePlugin::`vftable'
0x180013d65  mov     [rcx], rax
0x180013d68  mov     qword ptr [rcx+8], 0
0x180013d70  xor     edx, edx; Val
0x180013d72  lea     r8d, [rdx+40h]; Size
0x180013d76  lea     rcx, [rbp+57h+Src]; void *
0x180013d7a  call    memset_0
0x180013d7f  lea     r12, [rdi+28h]
0x180013d83  movups  xmm0, [rbp+57h+Src]
0x180013d87  movups  xmmword ptr [r12], xmm0
0x180013d8c  movups  xmm1, [rbp+57h+var_60]
0x180013d90  movups  xmmword ptr [r12+10h], xmm1
0x180013d96  movups  xmm0, [rbp+57h+var_50]
0x180013d9a  movups  xmmword ptr [r12+20h], xmm0
0x180013da0  movups  xmm1, [rbp+57h+var_40]
0x180013da4  movups  xmmword ptr [r12+30h], xmm1
0x180013daa  lea     r15, [rdi+68h]
0x180013dae  xorps   xmm0, xmm0
0x180013db1  movups  xmmword ptr [r15], xmm0
0x180013db5  mov     qword ptr [r15+10h], 0
0x180013dbd  mov     qword ptr [r15+18h], 7
0x180013dc5  xor     eax, eax
0x180013dc7  mov     [r15], ax
0x180013dcb  mov     rdx, rbx
0x180013dce  lea     rcx, [rbp+57h+lpLibFileName]
0x180013dd2  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180013dd7  nop
0x180013dd8  xor     r14b, r14b
0x180013ddb  lea     rcx, [rbp+57h+lpLibFileName]
0x180013ddf  cmp     [rbp+57h+var_78], 7
0x180013de4  cmova   rcx, [rbp+57h+lpLibFileName]; lpLibFileName
0x180013de9  call    cs:__imp_LoadLibraryW
0x180013def  mov     rsi, rax
0x180013df2  test    rax, rax
0x180013df5  jnz     loc_180013E95
0x180013dfb  call    cs:__imp_GetLastError
0x180013e01  mov     ebx, eax
0x180013e03  cmp     eax, 2
0x180013e06  jz      short loc_180013E16
0x180013e08  cmp     eax, 7Eh ; '~'
0x180013e0b  jz      short loc_180013E16
0x180013e0d  cmp     eax, 57h ; 'W'
0x180013e10  jnz     loc_180013F8A
0x180013e16  test    r14b, r14b
0x180013e19  jnz     loc_180013F8A
0x180013e1f  test    byte ptr cs:Microsoft_Windows_HostGuardianClient_ServiceEnableBits, 4
0x180013e26  jz      short loc_180013E3E
0x180013e28  mov     r9d, ebx
0x180013e2b  lea     r8, aPluginWasNotFo; "Plugin was not found.  Using the defaul"...
0x180013e32  lea     rdx, ServiceDebugWarning
0x180013e39  call    McTemplateU0zq_EventWriteTransfer
0x180013e3e  xorps   xmm0, xmm0
0x180013e41  movups  [rbp+57h+var_C0], xmm0
0x180013e45  mov     [rbp+57h+var_B0], 0
0x180013e4d  mov     [rbp+57h+var_A8], 0
0x180013e55  mov     r8d, 13h
0x180013e5b  lea     rdx, aHgsclientplugi; "hgsclientplugin.dll"
0x180013e62  lea     rcx, [rbp+57h+var_C0]
0x180013e66  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180013e6b  lea     rdx, [rbp+57h+var_C0]
0x180013e6f  lea     rcx, [rbp+57h+Src]; Src
0x180013e73  call    ?AppendBinaryToSystemPath@Utilities@Client@HostGuardian@Microsoft@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V56@@Z; Microsoft::HostGuardian::Client::Utilities::AppendBinaryToSystemPath(std::wstring)
0x180013e78  mov     rdx, rax
0x180013e7b  lea     rcx, [rbp+57h+lpLibFileName]
0x180013e7f  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180013e84  lea     rcx, [rbp+57h+Src]
0x180013e88  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180013e8d  mov     r14b, 1
0x180013e90  jmp     loc_180013DDB
0x180013e95  lea     rdx, [rbp+57h+lpLibFileName]
0x180013e99  mov     rcx, r15
0x180013e9c  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180013ea1  mov     r14, [rdi+8]
0x180013ea5  test    r14, r14
0x180013ea8  jz      short loc_180013EC3
0x180013eaa  call    cs:__imp_GetLastError
0x180013eb0  mov     ebx, eax
0x180013eb2  mov     rcx, r14; hLibModule
0x180013eb5  call    cs:__imp_FreeLibrary
0x180013ebb  mov     ecx, ebx; dwErrCode
0x180013ebd  call    cs:__imp_SetLastError
0x180013ec3  mov     [rdi+8], rsi
0x180013ec7  lea     rdx, aInitializeatte; "InitializeAttestationPlugin"
0x180013ece  mov     rcx, rsi; hModule
0x180013ed1  call    cs:__imp_GetProcAddress
0x180013ed7  mov     [rdi+18h], rax
0x180013edb  mov     rcx, [rbp+5Fh]; this
0x180013edf  test    rax, rax
0x180013ee2  jz      loc_180013FC4
0x180013ee8  lea     rdx, aUninitializeat; "UninitializeAttestationPlugin"
0x180013eef  mov     rcx, [rdi+8]; hModule
0x180013ef3  call    cs:__imp_GetProcAddress
0x180013ef9  mov     [rdi+20h], rax
0x180013efd  mov     rcx, [rbp+5Fh]; this
0x180013f01  test    rax, rax
0x180013f04  jz      short loc_180013F78
0x180013f06  mov     dword ptr [r12], 40h ; '@'
0x180013f0e  lea     rdx, [rdi+10h]
0x180013f12  mov     rcx, r12
0x180013f15  mov     rax, [rdi+18h]
0x180013f19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f1e  mov     rcx, [rbp+5Fh]; this
0x180013f22  lea     rdx, aPluginInitiali; "Plugin initialization failed."
0x180013f29  mov     qword ptr [rsp+0F0h+var_D0], rdx; int
0x180013f2e  mov     r9d, eax; char *
0x180013f31  lea     r8, aServercommonBa_4; "servercommon\\base\\securehostingservic"...
0x180013f38  mov     edx, 35h ; '5'; void *
0x180013f3d  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180013f42  nop
0x180013f43  lea     rcx, [rbp+57h+lpLibFileName]
0x180013f47  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180013f4c  nop
0x180013f4d  mov     rax, rdi
0x180013f50  mov     rcx, [rbp+57h+var_30]
0x180013f54  xor     rcx, rsp; StackCookie
0x180013f57  call    __security_check_cookie
0x180013f5c  lea     r11, [rsp+0F0h+var_20]
0x180013f64  mov     rbx, [r11+40h]
0x180013f68  mov     rsi, [r11+48h]
0x180013f6c  mov     rsp, r11
0x180013f6f  pop     r15
0x180013f71  pop     r14
0x180013f73  pop     r12
0x180013f75  pop     rdi
0x180013f76  pop     rbp
0x180013f77  retn
0x180013f78  lea     r8, aServercommonBa_4; "servercommon\\base\\securehostingservic"...
0x180013f7f  mov     edx, 31h ; '1'; void *
0x180013f84  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180013f8a  test    byte ptr cs:Microsoft_Windows_HostGuardianClient_ServiceEnableBits, 20h
0x180013f91  jz      short loc_180013FAB
0x180013f93  lea     rcx, [rbp+57h+lpLibFileName]
0x180013f97  call    ?c_str@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBAPEB_WXZ; std::wstring::c_str(void)
0x180013f9c  mov     r8, rax
0x180013f9f  lea     rdx, PluginLoadFailed
0x180013fa6  call    McTemplateU0z_EventWriteTransfer
0x180013fab  mov     rcx, [rbp+5Fh]; this
0x180013faf  mov     r9d, ebx; char *
0x180013fb2  lea     r8, aServercommonBa_4; "servercommon\\base\\securehostingservic"...
0x180013fb9  mov     edx, 25h ; '%'; void *
0x180013fbe  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180013fc4  lea     r8, aServercommonBa_4; "servercommon\\base\\securehostingservic"...
0x180013fcb  mov     edx, 2Fh ; '/'; void *
0x180013fd0  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
