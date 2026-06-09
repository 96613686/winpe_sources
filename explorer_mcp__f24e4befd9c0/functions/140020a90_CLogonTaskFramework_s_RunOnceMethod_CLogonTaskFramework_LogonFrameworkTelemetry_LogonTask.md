# CLogonTaskFramework::s_RunOnceMethod(CLogonTaskFramework *,LogonFrameworkTelemetry::LogonTask *)

- ea: `0x140020a90`
- end: `0x140020cd4`
- name: `?s_RunOnceMethod@CLogonTaskFramework@@CAJPEAV1@PEAVLogonTask@LogonFrameworkTelemetry@@@Z`
- size: `580`
- prototype: `__int64 __fastcall(struct CLogonTaskFramework *, struct LogonFrameworkTelemetry::LogonTask *)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x14001b2c8`
- `0x14001c330`
- `0x140020a90`
- `0x140020cdc`
- `0x140021780`
- `0x140021aac`
- `0x140087808`
- `0x14010cdbc`
- `0x14010e160`
- `0x14010ed90`
- `0x1401285c8`
- `0x14013af98`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x140020bb6`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x140020bb6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140020c98`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140020ca9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140020c98`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140020ca9`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x140020c6a`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x140020c6a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathQuoteSpacesW` at `0x140020b32`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathQuoteSpacesW` at `0x140020b32`
- `SHELL32!__imp_IsUserAnAdmin` at `0x140020af3`
- `SHELL32!__imp_IsUserAnAdmin` at `0x140020af3`

## string_xrefs

- `0x140020aff`: `shell\lib\logontasks\logontasks.cpp`

## pseudocode

```c
__int64 __fastcall CLogonTaskFramework::s_RunOnceMethod(
        struct CLogonTaskFramework *a1,
        struct LogonFrameworkTelemetry::LogonTask *a2)
{
  unsigned int Error; // ebx
  int PathInSystemDirectory; // eax
  __int64 v5; // rdx
  unsigned int v6; // eax
  HRESULT v7; // eax
  unsigned int bInheritHandles; // [rsp+20h] [rbp-E0h]
  int bInheritHandlesa; // [rsp+20h] [rbp-E0h]
  int bInheritHandlesb; // [rsp+20h] [rbp-E0h]
  int bInheritHandlesc; // [rsp+20h] [rbp-E0h]
  DWORD dwindex; // [rsp+50h] [rbp-B0h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+58h] [rbp-A8h] BYREF
  HANDLE pHandles; // [rsp+70h] [rbp-90h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+80h] [rbp-80h] BYREF
  WCHAR sz[264]; // [rsp+F0h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+338h] [rbp+238h]

  Error = 0;
  if ( !(unsigned int)ShouldProcessHKLMRunOnce(a1, a2) || (unsigned int)HasRunStuffBeenDone() )
    return Error;
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  if ( !IsUserAnAdmin() )
  {
    v6 = AicProcessRunOnce(&ProcessInformation);
    if ( !v6 )
      goto LABEL_15;
    wil::details::in1diag3::_Log_Win32(
      retaddr,
      (void *)0x86B,
      (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
      (const char *)v6,
      bInheritHandles);
    Error = ResultFromKnownLastError();
    goto LABEL_13;
  }
  PathInSystemDirectory = GetPathInSystemDirectory(L"runonce.exe", sz);
  if ( PathInSystemDirectory < 0 )
  {
    Error = -2147467259;
    v5 = 2135;
LABEL_8:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
      (const char *)(unsigned int)PathInSystemDirectory,
      bInheritHandles);
    goto LABEL_14;
  }
  PathQuoteSpacesW(sz);
  PathInSystemDirectory = StringCchCatW(sz, 0x104u, L" /Explorer");
  Error = PathInSystemDirectory;
  if ( PathInSystemDirectory < 0 )
  {
    v5 = 2139;
    goto LABEL_8;
  }
  if ( !CreateProcessW(0, sz, 0, 0, 0, 0x80u, 0, 0, &StartupInfo, &ProcessInformation) )
  {
    Error = ResultFromKnownLastError();
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)0x862,
      (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
      (const char *)Error,
      bInheritHandlesb);
LABEL_13:
    if ( (Error & 0x80000000) != 0 )
    {
LABEL_14:
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x875,
        (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
        (const char *)Error,
        bInheritHandlesa);
      if ( (Error & 0x80000000) != 0 )
        return Error;
    }
  }
LABEL_15:
  if ( (*((_BYTE *)a1 + 220) & 0x40) == 0 )
  {
    pHandles = ProcessInformation.hProcess;
    dwindex = 0;
    v7 = CoWaitForMultipleHandles(0, 0xFFFFFFFF, 1u, &pHandles, &dwindex);
    Error = v7;
    if ( v7 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x87E,
        (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
        (const char *)(unsigned int)v7,
        bInheritHandlesc);
  }
  CloseHandle(ProcessInformation.hThread);
  CloseHandle(ProcessInformation.hProcess);
  return Error;
}

```

## disassembly

```asm
0x140020a90  push    rbp
0x140020a92  push    rbx
0x140020a93  push    rdi
0x140020a94  push    r14
0x140020a96  lea     rbp, [rsp-218h]
0x140020a9e  sub     rsp, 318h
0x140020aa5  mov     rax, cs:__security_cookie
0x140020aac  xor     rax, rsp
0x140020aaf  mov     [rbp+230h+var_30], rax
0x140020ab6  mov     rdi, rcx
0x140020ab9  xor     ebx, ebx
0x140020abb  call    ShouldProcessHKLMRunOnce
0x140020ac0  test    eax, eax
0x140020ac2  jz      loc_140020CB5
0x140020ac8  call    HasRunStuffBeenDone
0x140020acd  test    eax, eax
0x140020acf  jnz     loc_140020CB5
0x140020ad5  xor     edx, edx; Val
0x140020ad7  lea     r8d, [rbx+68h]; Size
0x140020adb  lea     rcx, [rbp+230h+StartupInfo]; void *
0x140020adf  call    memset_0
0x140020ae4  xorps   xmm0, xmm0
0x140020ae7  xor     eax, eax
0x140020ae9  movups  xmmword ptr [rsp+330h+ProcessInformation.hProcess], xmm0
0x140020aee  mov     qword ptr [rsp+330h+ProcessInformation.dwProcessId], rax
0x140020af3  call    cs:__imp_IsUserAnAdmin
0x140020afa  nop     dword ptr [rax+rax+00h]
0x140020aff  lea     r14, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x140020b06  test    eax, eax
0x140020b08  jz      loc_140020BE6
0x140020b0e  lea     rdx, [rbp+230h+sz]; pszPath
0x140020b12  lea     rcx, aRunonceExe; "runonce.exe"
0x140020b19  call    GetPathInSystemDirectory
0x140020b1e  test    eax, eax
0x140020b20  jns     short loc_140020B2E
0x140020b22  mov     ebx, 80004005h
0x140020b27  mov     edx, 857h
0x140020b2c  jmp     short loc_140020B5E
0x140020b2e  lea     rcx, [rbp+230h+sz]; lpsz
0x140020b32  call    cs:__imp_PathQuoteSpacesW
0x140020b39  nop     dword ptr [rax+rax+00h]
0x140020b3e  lea     r8, aExplorer_3; " /Explorer"
0x140020b45  mov     edx, 104h; unsigned __int64
0x140020b4a  lea     rcx, [rbp+230h+sz]; unsigned __int16 *
0x140020b4e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140020b53  mov     ebx, eax
0x140020b55  test    eax, eax
0x140020b57  jns     short loc_140020B75
0x140020b59  mov     edx, 85Bh; void *
0x140020b5e  mov     rcx, [rbp+238h]; this
0x140020b65  mov     r8, r14; unsigned int
0x140020b68  mov     r9d, eax; char *
0x140020b6b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140020b70  jmp     loc_140020C16
0x140020b75  lea     rax, [rsp+330h+ProcessInformation]
0x140020b7a  xor     r9d, r9d; lpThreadAttributes
0x140020b7d  mov     [rsp+330h+lpProcessInformation], rax; lpProcessInformation
0x140020b82  lea     rdx, [rbp+230h+sz]; lpCommandLine
0x140020b86  lea     rax, [rbp+230h+StartupInfo]
0x140020b8a  xor     r8d, r8d; lpProcessAttributes
0x140020b8d  mov     [rsp+330h+lpStartupInfo], rax; lpStartupInfo
0x140020b92  xor     ecx, ecx; lpApplicationName
0x140020b94  mov     [rsp+330h+lpCurrentDirectory], 0; lpCurrentDirectory
0x140020b9d  mov     [rsp+330h+lpEnvironment], 0; lpEnvironment
0x140020ba6  mov     [rsp+330h+dwCreationFlags], 80h; dwCreationFlags
0x140020bae  mov     [rsp+330h+bInheritHandles], 0; int
0x140020bb6  call    cs:__imp_CreateProcessW
0x140020bbd  nop     dword ptr [rax+rax+00h]
0x140020bc2  test    eax, eax
0x140020bc4  jnz     short loc_140020C35
0x140020bc6  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x140020bcb  mov     rcx, [rbp+238h]; this
0x140020bd2  mov     r9d, eax; char *
0x140020bd5  mov     r8, r14; unsigned int
0x140020bd8  mov     edx, 862h; void *
0x140020bdd  mov     ebx, eax
0x140020bdf  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x140020be4  jmp     short loc_140020C12
0x140020be6  lea     rcx, [rsp+330h+ProcessInformation]; struct _PROCESS_INFORMATION *
0x140020beb  call    ?AicProcessRunOnce@@YAKPEAU_PROCESS_INFORMATION@@@Z; AicProcessRunOnce(_PROCESS_INFORMATION *)
0x140020bf0  test    eax, eax
0x140020bf2  jz      short loc_140020C35
0x140020bf4  mov     rcx, [rbp+238h]; this
0x140020bfb  mov     r9d, eax; char *
0x140020bfe  mov     r8, r14; unsigned int
0x140020c01  mov     edx, 86Bh; void *
0x140020c06  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x140020c0b  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x140020c10  mov     ebx, eax
0x140020c12  test    ebx, ebx
0x140020c14  jns     short loc_140020C35
0x140020c16  mov     rcx, [rbp+238h]; this
0x140020c1d  mov     r9d, ebx; char *
0x140020c20  mov     r8, r14; unsigned int
0x140020c23  mov     edx, 875h; void *
0x140020c28  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140020c2d  test    ebx, ebx
0x140020c2f  js      loc_140020CB5
0x140020c35  test    byte ptr [rdi+0DCh], 40h
0x140020c3c  jnz     short loc_140020C93
0x140020c3e  mov     rax, [rsp+330h+ProcessInformation.hProcess]
0x140020c43  lea     r9, [rsp+330h+pHandles]; pHandles
0x140020c48  mov     [rsp+330h+pHandles], rax
0x140020c4d  mov     r8d, 1; cHandles
0x140020c53  lea     rax, [rsp+330h+dwindex]
0x140020c58  mov     [rsp+330h+dwindex], 0
0x140020c60  or      edx, 0FFFFFFFFh; dwTimeout
0x140020c63  mov     qword ptr [rsp+330h+bInheritHandles], rax; int
0x140020c68  xor     ecx, ecx; dwFlags
0x140020c6a  call    cs:__imp_CoWaitForMultipleHandles
0x140020c71  nop     dword ptr [rax+rax+00h]
0x140020c76  mov     ebx, eax
0x140020c78  test    eax, eax
0x140020c7a  jns     short loc_140020C93
0x140020c7c  mov     rcx, [rbp+238h]; this
0x140020c83  mov     r9d, eax; char *
0x140020c86  mov     r8, r14; unsigned int
0x140020c89  mov     edx, 87Eh; void *
0x140020c8e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140020c93  mov     rcx, [rsp+330h+ProcessInformation.hThread]; hObject
0x140020c98  call    cs:__imp_CloseHandle
0x140020c9f  nop     dword ptr [rax+rax+00h]
0x140020ca4  mov     rcx, [rsp+330h+ProcessInformation.hProcess]; hObject
0x140020ca9  call    cs:__imp_CloseHandle
0x140020cb0  nop     dword ptr [rax+rax+00h]
0x140020cb5  mov     eax, ebx
0x140020cb7  mov     rcx, [rbp+230h+var_30]
0x140020cbe  xor     rcx, rsp; StackCookie
0x140020cc1  call    __security_check_cookie
0x140020cc6  add     rsp, 318h
0x140020ccd  pop     r14
0x140020ccf  pop     rdi
0x140020cd0  pop     rbx
0x140020cd1  pop     rbp
0x140020cd2  retn
```
