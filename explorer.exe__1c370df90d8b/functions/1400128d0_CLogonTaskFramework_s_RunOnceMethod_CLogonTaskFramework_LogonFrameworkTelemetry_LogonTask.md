# CLogonTaskFramework::s_RunOnceMethod(CLogonTaskFramework *,LogonFrameworkTelemetry::LogonTask *)

- ea: `0x1400128d0`
- end: `0x140012aeb`
- name: `?s_RunOnceMethod@CLogonTaskFramework@@CAJPEAV1@PEAVLogonTask@LogonFrameworkTelemetry@@@Z`
- size: `539`
- prototype: `__int64 __fastcall(struct CLogonTaskFramework *, struct LogonFrameworkTelemetry::LogonTask *)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x140012074`
- `0x140012138`
- `0x1400128d0`
- `0x140012af4`
- `0x140016b10`
- `0x14001eba8`
- `0x140081704`
- `0x140102d58`
- `0x1401040e0`
- `0x140104ce0`
- `0x14011d330`
- `0x14012f27c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1400129ea`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1400129ea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140012abc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140012ac7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140012abc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140012ac7`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x140012a94`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x140012a94`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathQuoteSpacesW` at `0x14001296c`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathQuoteSpacesW` at `0x14001296c`
- `SHELL32!__imp_IsUserAnAdmin` at `0x140012933`
- `SHELL32!__imp_IsUserAnAdmin` at `0x140012933`

## string_xrefs

- `0x140012939`: `shell\lib\logontasks\logontasks.cpp`

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
      (void *)0x867,
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
    v5 = 2131;
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
    v5 = 2135;
    goto LABEL_8;
  }
  if ( !CreateProcessW(0, sz, 0, 0, 0, 0x80u, 0, 0, &StartupInfo, &ProcessInformation) )
  {
    Error = ResultFromKnownLastError();
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)0x85E,
      (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
      (const char *)Error,
      bInheritHandlesb);
LABEL_13:
    if ( (Error & 0x80000000) != 0 )
    {
LABEL_14:
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x871,
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
        (void *)0x87A,
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
0x1400128d0  push    rbp
0x1400128d2  push    rbx
0x1400128d3  push    rdi
0x1400128d4  push    r14
0x1400128d6  lea     rbp, [rsp-218h]
0x1400128de  sub     rsp, 318h
0x1400128e5  mov     rax, cs:__security_cookie
0x1400128ec  xor     rax, rsp
0x1400128ef  mov     [rbp+230h+var_30], rax
0x1400128f6  mov     rdi, rcx
0x1400128f9  xor     ebx, ebx
0x1400128fb  call    ShouldProcessHKLMRunOnce
0x140012900  test    eax, eax
0x140012902  jz      loc_140012ACD
0x140012908  call    HasRunStuffBeenDone
0x14001290d  test    eax, eax
0x14001290f  jnz     loc_140012ACD
0x140012915  xor     edx, edx; Val
0x140012917  lea     r8d, [rbx+68h]; Size
0x14001291b  lea     rcx, [rbp+230h+StartupInfo]; void *
0x14001291f  call    memset_0
0x140012924  xorps   xmm0, xmm0
0x140012927  xor     eax, eax
0x140012929  movups  xmmword ptr [rsp+330h+ProcessInformation.hProcess], xmm0
0x14001292e  mov     qword ptr [rsp+330h+ProcessInformation.dwProcessId], rax
0x140012933  call    cs:__imp_IsUserAnAdmin
0x140012939  lea     r14, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x140012940  test    eax, eax
0x140012942  jz      loc_140012A14
0x140012948  lea     rdx, [rbp+230h+sz]; pszPath
0x14001294c  lea     rcx, aRunonceExe; "runonce.exe"
0x140012953  call    GetPathInSystemDirectory
0x140012958  test    eax, eax
0x14001295a  jns     short loc_140012968
0x14001295c  mov     ebx, 80004005h
0x140012961  mov     edx, 853h
0x140012966  jmp     short loc_140012992
0x140012968  lea     rcx, [rbp+230h+sz]; lpsz
0x14001296c  call    cs:__imp_PathQuoteSpacesW
0x140012972  lea     r8, aExplorer_3; " /Explorer"
0x140012979  mov     edx, 104h; unsigned __int64
0x14001297e  lea     rcx, [rbp+230h+sz]; unsigned __int16 *
0x140012982  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140012987  mov     ebx, eax
0x140012989  test    eax, eax
0x14001298b  jns     short loc_1400129A9
0x14001298d  mov     edx, 857h; void *
0x140012992  mov     rcx, [rbp+238h]; this
0x140012999  mov     r8, r14; unsigned int
0x14001299c  mov     r9d, eax; char *
0x14001299f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1400129a4  jmp     loc_140012A44
0x1400129a9  lea     rax, [rsp+330h+ProcessInformation]
0x1400129ae  xor     r9d, r9d; lpThreadAttributes
0x1400129b1  mov     [rsp+330h+lpProcessInformation], rax; lpProcessInformation
0x1400129b6  lea     rdx, [rbp+230h+sz]; lpCommandLine
0x1400129ba  lea     rax, [rbp+230h+StartupInfo]
0x1400129be  xor     r8d, r8d; lpProcessAttributes
0x1400129c1  mov     [rsp+330h+lpStartupInfo], rax; lpStartupInfo
0x1400129c6  xor     ecx, ecx; lpApplicationName
0x1400129c8  mov     [rsp+330h+lpCurrentDirectory], 0; lpCurrentDirectory
0x1400129d1  mov     [rsp+330h+lpEnvironment], 0; lpEnvironment
0x1400129da  mov     [rsp+330h+dwCreationFlags], 80h; dwCreationFlags
0x1400129e2  mov     [rsp+330h+bInheritHandles], 0; int
0x1400129ea  call    cs:__imp_CreateProcessW
0x1400129f0  test    eax, eax
0x1400129f2  jnz     short loc_140012A5F
0x1400129f4  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1400129f9  mov     rcx, [rbp+238h]; this
0x140012a00  mov     r9d, eax; char *
0x140012a03  mov     r8, r14; unsigned int
0x140012a06  mov     edx, 85Eh; void *
0x140012a0b  mov     ebx, eax
0x140012a0d  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x140012a12  jmp     short loc_140012A40
0x140012a14  lea     rcx, [rsp+330h+ProcessInformation]; struct _PROCESS_INFORMATION *
0x140012a19  call    ?AicProcessRunOnce@@YAKPEAU_PROCESS_INFORMATION@@@Z; AicProcessRunOnce(_PROCESS_INFORMATION *)
0x140012a1e  test    eax, eax
0x140012a20  jz      short loc_140012A5F
0x140012a22  mov     rcx, [rbp+238h]; this
0x140012a29  mov     r9d, eax; char *
0x140012a2c  mov     r8, r14; unsigned int
0x140012a2f  mov     edx, 867h; void *
0x140012a34  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x140012a39  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x140012a3e  mov     ebx, eax
0x140012a40  test    ebx, ebx
0x140012a42  jns     short loc_140012A5F
0x140012a44  mov     rcx, [rbp+238h]; this
0x140012a4b  mov     r9d, ebx; char *
0x140012a4e  mov     r8, r14; unsigned int
0x140012a51  mov     edx, 871h; void *
0x140012a56  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140012a5b  test    ebx, ebx
0x140012a5d  js      short loc_140012ACD
0x140012a5f  test    byte ptr [rdi+0DCh], 40h
0x140012a66  jnz     short loc_140012AB7
0x140012a68  mov     rax, [rsp+330h+ProcessInformation.hProcess]
0x140012a6d  lea     r9, [rsp+330h+pHandles]; pHandles
0x140012a72  mov     [rsp+330h+pHandles], rax
0x140012a77  mov     r8d, 1; cHandles
0x140012a7d  lea     rax, [rsp+330h+dwindex]
0x140012a82  mov     [rsp+330h+dwindex], 0
0x140012a8a  or      edx, 0FFFFFFFFh; dwTimeout
0x140012a8d  mov     qword ptr [rsp+330h+bInheritHandles], rax; int
0x140012a92  xor     ecx, ecx; dwFlags
0x140012a94  call    cs:__imp_CoWaitForMultipleHandles
0x140012a9a  mov     ebx, eax
0x140012a9c  test    eax, eax
0x140012a9e  jns     short loc_140012AB7
0x140012aa0  mov     rcx, [rbp+238h]; this
0x140012aa7  mov     r9d, eax; char *
0x140012aaa  mov     r8, r14; unsigned int
0x140012aad  mov     edx, 87Ah; void *
0x140012ab2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140012ab7  mov     rcx, [rsp+330h+ProcessInformation.hThread]; hObject
0x140012abc  call    cs:__imp_CloseHandle
0x140012ac2  mov     rcx, [rsp+330h+ProcessInformation.hProcess]; hObject
0x140012ac7  call    cs:__imp_CloseHandle
0x140012acd  mov     eax, ebx
0x140012acf  mov     rcx, [rbp+230h+var_30]
0x140012ad6  xor     rcx, rsp; StackCookie
0x140012ad9  call    __security_check_cookie
0x140012ade  add     rsp, 318h
0x140012ae5  pop     r14
0x140012ae7  pop     rdi
0x140012ae8  pop     rbx
0x140012ae9  pop     rbp
0x140012aea  retn
```
