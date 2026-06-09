# SETUP_HELPER::HandleKeyGeneration(void)

- ea: `0x18002c180`
- end: `0x18002c2b3`
- name: `?HandleKeyGeneration@SETUP_HELPER@@SAKXZ`
- size: `307`
- prototype: `unsigned int(void)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callees

- `0x18002c104`
- `0x18002c180`
- `0x18002c2e8`
- `0x18002c48e`

## import_xrefs

- `msvcrt!_wcsdup` at `0x18002c1c3`
- `msvcrt!_wcsdup` at `0x18002c1c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c240`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c26b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c240`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c26b`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18002c236`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18002c236`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x18002c261`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x18002c261`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002c253`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002c253`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c277`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c281`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c277`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c281`

## pseudocode

```c
__int64 SETUP_HELPER::HandleKeyGeneration(void)
{
  wchar_t *v0; // rax
  WCHAR *v1; // rbx
  const unsigned __int16 *v2; // rcx
  DWORD Breadcrumb; // eax
  DWORD LastError; // ebx
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+50h] [rbp-39h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+70h] [rbp-19h] BYREF
  unsigned int v8; // [rsp+F0h] [rbp+67h] BYREF
  DWORD ExitCode; // [rsp+F8h] [rbp+6Fh] BYREF

  ExitCode = 0;
  v8 = 0;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  v0 = _wcsdup(L"cmd /C \".\\inetsrv\\iissetup.exe /keygen \"");
  StartupInfo.cb = 104;
  v1 = v0;
  Breadcrumb = SETUP_HELPER::ReadBreadcrumb(v2, (BYTE *)&v8);
  if ( Breadcrumb )
  {
    LastError = 0;
    if ( Breadcrumb != 2 )
      return Breadcrumb;
    return LastError;
  }
  if ( v8 != 1 )
    return 0;
  if ( !CreateProcessW(0, v1, 0, 0, 0, 8u, 0, 0, &StartupInfo, &ProcessInformation) )
    return GetLastError();
  LastError = 0;
  WaitForSingleObject(ProcessInformation.hProcess, 0xFFFFFFFF);
  if ( !GetExitCodeProcess(ProcessInformation.hProcess, &ExitCode) )
    LastError = GetLastError();
  CloseHandle(ProcessInformation.hProcess);
  CloseHandle(ProcessInformation.hThread);
  if ( !LastError )
  {
    LastError = ExitCode;
    if ( !ExitCode )
    {
      SETUP_HELPER::DeleteBreadcrumb(L"GenerateKeys");
      return 0;
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x18002c180  mov     [rsp-8+arg_10], rbx
0x18002c185  push    rbp
0x18002c186  lea     rbp, [rsp-57h]
0x18002c18b  sub     rsp, 0E0h
0x18002c192  xor     eax, eax
0x18002c194  mov     [rbp+57h+ExitCode], 0
0x18002c19b  xorps   xmm0, xmm0
0x18002c19e  mov     [rbp+57h+arg_0], 0
0x18002c1a5  xor     edx, edx; Val
0x18002c1a7  mov     qword ptr [rbp+57h+ProcessInformation.dwProcessId], rax
0x18002c1ab  lea     rcx, [rbp+57h+StartupInfo]; void *
0x18002c1af  lea     r8d, [rax+68h]; Size
0x18002c1b3  movups  xmmword ptr [rbp+57h+ProcessInformation.hProcess], xmm0
0x18002c1b7  call    memset_0
0x18002c1bc  lea     rcx, aCmdCInetsrvIis; "cmd /C \".\\inetsrv\\iissetup.exe /keyg"...
0x18002c1c3  call    cs:__imp__wcsdup
0x18002c1c9  lea     rdx, [rbp+57h+arg_0]; unsigned int *
0x18002c1cd  mov     [rbp+57h+StartupInfo.cb], 68h ; 'h'
0x18002c1d4  mov     rbx, rax
0x18002c1d7  call    ?ReadBreadcrumb@SETUP_HELPER@@CAKPEBGPEAK@Z; SETUP_HELPER::ReadBreadcrumb(ushort const *,ulong *)
0x18002c1dc  test    eax, eax
0x18002c1de  jz      short loc_18002C1ED
0x18002c1e0  xor     ebx, ebx
0x18002c1e2  cmp     eax, 2
0x18002c1e5  cmovnz  ebx, eax
0x18002c1e8  jmp     loc_18002C2A0
0x18002c1ed  cmp     [rbp+57h+arg_0], 1
0x18002c1f1  jnz     loc_18002C29E
0x18002c1f7  lea     rax, [rbp+57h+ProcessInformation]
0x18002c1fb  xor     r9d, r9d; lpThreadAttributes
0x18002c1fe  mov     [rsp+0E0h+lpProcessInformation], rax; lpProcessInformation
0x18002c203  xor     r8d, r8d; lpProcessAttributes
0x18002c206  lea     rax, [rbp+57h+StartupInfo]
0x18002c20a  mov     rdx, rbx; lpCommandLine
0x18002c20d  mov     [rsp+0E0h+lpStartupInfo], rax; lpStartupInfo
0x18002c212  xor     ecx, ecx; lpApplicationName
0x18002c214  mov     [rsp+0E0h+lpCurrentDirectory], 0; lpCurrentDirectory
0x18002c21d  mov     [rsp+0E0h+lpEnvironment], 0; lpEnvironment
0x18002c226  mov     [rsp+0E0h+dwCreationFlags], 8; dwCreationFlags
0x18002c22e  mov     [rsp+0E0h+bInheritHandles], 0; bInheritHandles
0x18002c236  call    cs:__imp_CreateProcessW
0x18002c23c  test    eax, eax
0x18002c23e  jnz     short loc_18002C24A
0x18002c240  call    cs:__imp_GetLastError
0x18002c246  mov     ebx, eax
0x18002c248  jmp     short loc_18002C2A0
0x18002c24a  mov     rcx, [rbp+57h+ProcessInformation.hProcess]; hHandle
0x18002c24e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18002c251  xor     ebx, ebx
0x18002c253  call    cs:__imp_WaitForSingleObject
0x18002c259  mov     rcx, [rbp+57h+ProcessInformation.hProcess]; hProcess
0x18002c25d  lea     rdx, [rbp+57h+ExitCode]; lpExitCode
0x18002c261  call    cs:__imp_GetExitCodeProcess
0x18002c267  test    eax, eax
0x18002c269  jnz     short loc_18002C273
0x18002c26b  call    cs:__imp_GetLastError
0x18002c271  mov     ebx, eax
0x18002c273  mov     rcx, [rbp+57h+ProcessInformation.hProcess]; hObject
0x18002c277  call    cs:__imp_CloseHandle
0x18002c27d  mov     rcx, [rbp+57h+ProcessInformation.hThread]; hObject
0x18002c281  call    cs:__imp_CloseHandle
0x18002c287  test    ebx, ebx
0x18002c289  jnz     short loc_18002C2A0
0x18002c28b  mov     ebx, [rbp+57h+ExitCode]
0x18002c28e  test    ebx, ebx
0x18002c290  jnz     short loc_18002C2A0
0x18002c292  lea     rcx, aGeneratekeys; "GenerateKeys"
0x18002c299  call    ?DeleteBreadcrumb@SETUP_HELPER@@CAKPEBG@Z; SETUP_HELPER::DeleteBreadcrumb(ushort const *)
0x18002c29e  xor     ebx, ebx
0x18002c2a0  mov     eax, ebx
0x18002c2a2  mov     rbx, [rsp+0E0h+arg_10]
0x18002c2aa  add     rsp, 0E0h
0x18002c2b1  pop     rbp
0x18002c2b2  retn
```
