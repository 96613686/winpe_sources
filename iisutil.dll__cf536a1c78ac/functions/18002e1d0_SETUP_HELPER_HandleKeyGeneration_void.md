# SETUP_HELPER::HandleKeyGeneration(void)

- ea: `0x18002e1d0`
- end: `0x18002e334`
- name: `?HandleKeyGeneration@SETUP_HELPER@@SAKXZ`
- size: `356`
- prototype: `__int64(void)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callees

- `0x18002e138`
- `0x18002e1d0`
- `0x18002e368`
- `0x18002e52e`

## import_xrefs

- `msvcrt!_wcsdup` at `0x18002e213`
- `msvcrt!_wcsdup` at `0x18002e213`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e29c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e2d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e29c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e2d9`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18002e28c`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18002e28c`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x18002e2c9`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x18002e2c9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002e2b5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002e2b5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e2eb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e2fb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e2eb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e2fb`

## pseudocode

```c
__int64 SETUP_HELPER::HandleKeyGeneration(void)
{
  wchar_t *v0; // rax
  WCHAR *v1; // rbx
  const unsigned __int16 *v2; // rcx
  unsigned int v3; // eax
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
  v3 = SETUP_HELPER::ReadBreadcrumb(v2, &v8);
  if ( v3 )
  {
    LastError = 0;
    if ( v3 != 2 )
      return v3;
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
0x18002e1d0  mov     [rsp-8+arg_10], rbx
0x18002e1d5  push    rbp
0x18002e1d6  lea     rbp, [rsp-57h]
0x18002e1db  sub     rsp, 0E0h
0x18002e1e2  xor     eax, eax
0x18002e1e4  mov     [rbp+57h+ExitCode], 0
0x18002e1eb  xorps   xmm0, xmm0
0x18002e1ee  mov     [rbp+57h+arg_0], 0
0x18002e1f5  xor     edx, edx; Val
0x18002e1f7  mov     qword ptr [rbp+57h+ProcessInformation.dwProcessId], rax
0x18002e1fb  lea     rcx, [rbp+57h+StartupInfo]; void *
0x18002e1ff  lea     r8d, [rax+68h]; Size
0x18002e203  movups  xmmword ptr [rbp+57h+ProcessInformation.hProcess], xmm0
0x18002e207  call    memset_0
0x18002e20c  lea     rcx, aCmdCInetsrvIis; "cmd /C \".\\inetsrv\\iissetup.exe /keyg"...
0x18002e213  call    cs:__imp__wcsdup
0x18002e21a  nop     dword ptr [rax+rax+00h]
0x18002e21f  lea     rdx, [rbp+57h+arg_0]; unsigned int *
0x18002e223  mov     [rbp+57h+StartupInfo.cb], 68h ; 'h'
0x18002e22a  mov     rbx, rax
0x18002e22d  call    ?ReadBreadcrumb@SETUP_HELPER@@CAKPEBGPEAK@Z; SETUP_HELPER::ReadBreadcrumb(ushort const *,ulong *)
0x18002e232  test    eax, eax
0x18002e234  jz      short loc_18002E243
0x18002e236  xor     ebx, ebx
0x18002e238  cmp     eax, 2
0x18002e23b  cmovnz  ebx, eax
0x18002e23e  jmp     loc_18002E320
0x18002e243  cmp     [rbp+57h+arg_0], 1
0x18002e247  jnz     loc_18002E31E
0x18002e24d  lea     rax, [rbp+57h+ProcessInformation]
0x18002e251  xor     r9d, r9d; lpThreadAttributes
0x18002e254  mov     [rsp+0E0h+lpProcessInformation], rax; lpProcessInformation
0x18002e259  xor     r8d, r8d; lpProcessAttributes
0x18002e25c  lea     rax, [rbp+57h+StartupInfo]
0x18002e260  mov     rdx, rbx; lpCommandLine
0x18002e263  mov     [rsp+0E0h+lpStartupInfo], rax; lpStartupInfo
0x18002e268  xor     ecx, ecx; lpApplicationName
0x18002e26a  mov     [rsp+0E0h+lpCurrentDirectory], 0; lpCurrentDirectory
0x18002e273  mov     [rsp+0E0h+lpEnvironment], 0; lpEnvironment
0x18002e27c  mov     [rsp+0E0h+dwCreationFlags], 8; dwCreationFlags
0x18002e284  mov     [rsp+0E0h+bInheritHandles], 0; bInheritHandles
0x18002e28c  call    cs:__imp_CreateProcessW
0x18002e293  nop     dword ptr [rax+rax+00h]
0x18002e298  test    eax, eax
0x18002e29a  jnz     short loc_18002E2AC
0x18002e29c  call    cs:__imp_GetLastError
0x18002e2a3  nop     dword ptr [rax+rax+00h]
0x18002e2a8  mov     ebx, eax
0x18002e2aa  jmp     short loc_18002E320
0x18002e2ac  mov     rcx, [rbp+57h+ProcessInformation.hProcess]; hHandle
0x18002e2b0  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18002e2b3  xor     ebx, ebx
0x18002e2b5  call    cs:__imp_WaitForSingleObject
0x18002e2bc  nop     dword ptr [rax+rax+00h]
0x18002e2c1  mov     rcx, [rbp+57h+ProcessInformation.hProcess]; hProcess
0x18002e2c5  lea     rdx, [rbp+57h+ExitCode]; lpExitCode
0x18002e2c9  call    cs:__imp_GetExitCodeProcess
0x18002e2d0  nop     dword ptr [rax+rax+00h]
0x18002e2d5  test    eax, eax
0x18002e2d7  jnz     short loc_18002E2E7
0x18002e2d9  call    cs:__imp_GetLastError
0x18002e2e0  nop     dword ptr [rax+rax+00h]
0x18002e2e5  mov     ebx, eax
0x18002e2e7  mov     rcx, [rbp+57h+ProcessInformation.hProcess]; hObject
0x18002e2eb  call    cs:__imp_CloseHandle
0x18002e2f2  nop     dword ptr [rax+rax+00h]
0x18002e2f7  mov     rcx, [rbp+57h+ProcessInformation.hThread]; hObject
0x18002e2fb  call    cs:__imp_CloseHandle
0x18002e302  nop     dword ptr [rax+rax+00h]
0x18002e307  test    ebx, ebx
0x18002e309  jnz     short loc_18002E320
0x18002e30b  mov     ebx, [rbp+57h+ExitCode]
0x18002e30e  test    ebx, ebx
0x18002e310  jnz     short loc_18002E320
0x18002e312  lea     rcx, aGeneratekeys; "GenerateKeys"
0x18002e319  call    ?DeleteBreadcrumb@SETUP_HELPER@@CAKPEBG@Z; SETUP_HELPER::DeleteBreadcrumb(ushort const *)
0x18002e31e  xor     ebx, ebx
0x18002e320  mov     eax, ebx
0x18002e322  mov     rbx, [rsp+0E0h+arg_10]
0x18002e32a  add     rsp, 0E0h
0x18002e331  pop     rbp
0x18002e332  retn
```
