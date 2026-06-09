# ElViewLog

- ea: `0x18001e370`
- end: `0x18001e508`
- name: `ElViewLog`
- size: `408`
- prototype: `__int64 __fastcall(LPCWSTR lpFile)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18001d508`

## callees

- `0x18000f380`
- `0x18001e370`
- `0x18001e944`
- `0x18004d0d2`
- `0x18004d110`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e4de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e4de`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18001e4ac`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18001e4ac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e4cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e4d6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e4cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e4d6`
- `USER32!WaitForInputIdle` at `0x18001e4c0`
- `USER32!WaitForInputIdle` at `0x18001e4c0`
- `SHELL32!FindExecutableW` at `0x18001e3c7`
- `SHELL32!FindExecutableW` at `0x18001e3c7`

## pseudocode

```c
__int64 __fastcall ElViewLog(LPCWSTR lpFile)
{
  HINSTANCE ExecutableW; // rax
  HRESULT v3; // eax
  unsigned int v4; // ebx
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+50h] [rbp-B0h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Result[264]; // [rsp+E0h] [rbp-20h] BYREF
  wchar_t pszDest[576]; // [rsp+2F0h] [rbp+1F0h] BYREF

  *(&StartupInfo.cb + 1) = 0;
  memset_0(&StartupInfo, 0, 0x64u);
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  ExecutableW = FindExecutableW(lpFile, 0, Result);
  if ( ExecutableW != (HINSTANCE)31 )
  {
    if ( (unsigned __int64)ExecutableW <= 0x20 )
      return GetLastError();
    goto LABEL_5;
  }
  v3 = StringCchCopyExW(Result, 0x104u, L"hh.exe ", 0, 0, 0x100u);
  if ( v3 >= 0 )
  {
LABEL_5:
    v3 = StringCchPrintfExW(pszDest, 0x23Bu, 0, 0, 0x100u, L"\"%s\" \"%s\"", Result, lpFile);
    if ( v3 < 0 )
      return (unsigned __int16)v3;
    memset_0(&StartupInfo.cb + 1, 0, 0x64u);
    StartupInfo.cb = 104;
    if ( CreateProcessW(0, pszDest, 0, 0, 1, 0, 0, 0, &StartupInfo, &ProcessInformation) )
    {
      v4 = 0;
      WaitForInputIdle(ProcessInformation.hProcess, 0xFFFFFFFF);
      CloseHandle(ProcessInformation.hThread);
      CloseHandle(ProcessInformation.hProcess);
      return v4;
    }
    return GetLastError();
  }
  return (unsigned __int16)v3;
}

```

## disassembly

```asm
0x18001e370  mov     [rsp-8+arg_8], rbx
0x18001e375  push    rbp
0x18001e376  lea     rbp, [rsp-680h]
0x18001e37e  sub     rsp, 780h
0x18001e385  mov     rax, cs:__security_cookie
0x18001e38c  xor     rax, rsp
0x18001e38f  mov     [rbp+680h+var_10], rax
0x18001e396  xor     eax, eax
0x18001e398  mov     rbx, rcx
0x18001e39b  xor     edx, edx; Val
0x18001e39d  mov     dword ptr [rsp+780h+StartupInfo+4], eax
0x18001e3a1  lea     rcx, [rsp+780h+StartupInfo]; void *
0x18001e3a6  lea     r8d, [rax+64h]; Size
0x18001e3aa  call    memset_0
0x18001e3af  xorps   xmm0, xmm0
0x18001e3b2  lea     r8, [rbp+680h+Result]; lpResult
0x18001e3b6  xor     eax, eax
0x18001e3b8  xor     edx, edx; lpDirectory
0x18001e3ba  mov     rcx, rbx; lpFile
0x18001e3bd  mov     qword ptr [rsp+780h+ProcessInformation.dwProcessId], rax
0x18001e3c2  movups  xmmword ptr [rsp+780h+ProcessInformation.hProcess], xmm0
0x18001e3c7  call    cs:__imp_FindExecutableW
0x18001e3cd  cmp     rax, 1Fh
0x18001e3d1  jnz     short loc_18001E408
0x18001e3d3  mov     [rsp+780h+dwFlags], 100h; dwFlags
0x18001e3db  lea     r8, aHhExe; "hh.exe "
0x18001e3e2  xor     r9d, r9d; ppszDestEnd
0x18001e3e5  mov     [rsp+780h+pcchRemaining], 0; pcchRemaining
0x18001e3ee  mov     edx, 104h; cchDest
0x18001e3f3  lea     rcx, [rbp+680h+Result]; pszDest
0x18001e3f7  call    StringCchCopyExW
0x18001e3fc  test    eax, eax
0x18001e3fe  jns     short loc_18001E412
0x18001e400  movzx   ebx, ax
0x18001e403  jmp     loc_18001E4E6
0x18001e408  cmp     rax, 20h ; ' '
0x18001e40c  jbe     loc_18001E4DE
0x18001e412  mov     [rsp+780h+lpCurrentDirectory], rbx
0x18001e417  lea     rax, [rbp+680h+Result]
0x18001e41b  mov     [rsp+780h+lpEnvironment], rax
0x18001e420  lea     rcx, [rbp+680h+pszDest]; pszDest
0x18001e427  lea     rax, aSS_3; "\"%s\" \"%s\""
0x18001e42e  xor     r9d, r9d; pcchRemaining
0x18001e431  mov     qword ptr [rsp+780h+dwFlags], rax; pszFormat
0x18001e436  xor     r8d, r8d; ppszDestEnd
0x18001e439  mov     edx, 23Bh; cchDest
0x18001e43e  mov     dword ptr [rsp+780h+pcchRemaining], 100h; dwFlags
0x18001e446  call    StringCchPrintfExW
0x18001e44b  test    eax, eax
0x18001e44d  js      short loc_18001E400
0x18001e44f  xor     edx, edx; Val
0x18001e451  lea     rcx, [rsp+780h+StartupInfo+4]; void *
0x18001e456  lea     r8d, [rdx+64h]; Size
0x18001e45a  call    memset_0
0x18001e45f  lea     rax, [rsp+780h+ProcessInformation]
0x18001e464  mov     [rsp+780h+StartupInfo.cb], 68h ; 'h'
0x18001e46c  mov     [rsp+780h+lpProcessInformation], rax; lpProcessInformation
0x18001e471  lea     rdx, [rbp+680h+pszDest]; lpCommandLine
0x18001e478  lea     rax, [rsp+780h+StartupInfo]
0x18001e47d  xor     r9d, r9d; lpThreadAttributes
0x18001e480  mov     [rsp+780h+lpStartupInfo], rax; lpStartupInfo
0x18001e485  xor     r8d, r8d; lpProcessAttributes
0x18001e488  mov     [rsp+780h+lpCurrentDirectory], 0; lpCurrentDirectory
0x18001e491  xor     ecx, ecx; lpApplicationName
0x18001e493  mov     [rsp+780h+lpEnvironment], 0; lpEnvironment
0x18001e49c  mov     [rsp+780h+dwFlags], 0; dwCreationFlags
0x18001e4a4  mov     dword ptr [rsp+780h+pcchRemaining], 1; bInheritHandles
0x18001e4ac  call    cs:__imp_CreateProcessW
0x18001e4b2  test    eax, eax
0x18001e4b4  jz      short loc_18001E4DE
0x18001e4b6  mov     rcx, [rsp+780h+ProcessInformation.hProcess]; hProcess
0x18001e4bb  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001e4be  xor     ebx, ebx
0x18001e4c0  call    cs:__imp_WaitForInputIdle
0x18001e4c6  mov     rcx, [rsp+780h+ProcessInformation.hThread]; hObject
0x18001e4cb  call    cs:__imp_CloseHandle
0x18001e4d1  mov     rcx, [rsp+780h+ProcessInformation.hProcess]; hObject
0x18001e4d6  call    cs:__imp_CloseHandle
0x18001e4dc  jmp     short loc_18001E4E6
0x18001e4de  call    cs:__imp_GetLastError
0x18001e4e4  mov     ebx, eax
0x18001e4e6  mov     eax, ebx
0x18001e4e8  mov     rcx, [rbp+680h+var_10]
0x18001e4ef  xor     rcx, rsp; StackCookie
0x18001e4f2  call    __security_check_cookie
0x18001e4f7  mov     rbx, [rsp+780h+arg_8]
0x18001e4ff  add     rsp, 780h
0x18001e506  pop     rbp
0x18001e507  retn
```
