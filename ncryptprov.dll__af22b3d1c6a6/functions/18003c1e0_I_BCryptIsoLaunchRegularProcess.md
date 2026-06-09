# I_BCryptIsoLaunchRegularProcess

- ea: `0x18003c1e0`
- end: `0x18003c2fd`
- name: `I_BCryptIsoLaunchRegularProcess`
- size: `285`
- prototype: `__int64 __fastcall(LPCWSTR lpApplicationName, LPWSTR lpCommandLine, HANDLE *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002831c`

## callees

- `0x18000af80`
- `0x180038970`
- `0x18003c1e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c273`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c2be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c273`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c2be`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18003c263`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18003c263`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003c2ae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003c2ae`

## string_xrefs

- `0x18003c2d7`: `onecore\ds\security\cryptoapi\ncrypt\ium\lib\bcryptisotrustlet.cpp`

## pseudocode

```c
__int64 __fastcall I_BCryptIsoLaunchRegularProcess(LPCWSTR lpApplicationName, LPWSTR lpCommandLine, HANDLE *a3)
{
  signed int LastError; // eax
  unsigned int v7; // ebx
  __int64 v8; // r9
  const char *v9; // rdx
  HANDLE hThread; // rcx
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+50h] [rbp-98h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+70h] [rbp-78h] BYREF

  *a3 = 0;
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  if ( !CreateProcessW(lpApplicationName, lpCommandLine, 0, 0, 0, 0, 0, 0, &StartupInfo, &ProcessInformation) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0xC0070000;
    else
      v7 = LastError;
    v8 = 294;
    v9 = "error";
    goto LABEL_8;
  }
  v7 = 0;
  hThread = ProcessInformation.hThread;
  *a3 = ProcessInformation.hProcess;
  if ( !CloseHandle(hThread) )
  {
    LastError = GetLastError();
    v8 = 306;
    v9 = "GetLastError()";
LABEL_8:
    DebugTraceError(
      (unsigned int)LastError,
      v9,
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\ium\\lib\\bcryptisotrustlet.cpp",
      v8);
  }
  return v7;
}

```

## disassembly

```asm
0x18003c1e0  mov     [rsp+arg_0], rbx
0x18003c1e5  mov     [rsp+arg_8], rsi
0x18003c1ea  push    rdi
0x18003c1eb  sub     rsp, 0E0h
0x18003c1f2  mov     rbx, rdx
0x18003c1f5  mov     qword ptr [r8], 0
0x18003c1fc  xor     edx, edx; Val
0x18003c1fe  mov     rsi, r8
0x18003c201  mov     rdi, rcx
0x18003c204  lea     rcx, [rsp+0E8h+StartupInfo]; void *
0x18003c209  lea     r8d, [rdx+68h]; Size
0x18003c20d  call    memset_0
0x18003c212  xor     eax, eax
0x18003c214  xorps   xmm0, xmm0
0x18003c217  mov     qword ptr [rsp+0E8h+ProcessInformation.dwProcessId], rax
0x18003c21c  xor     r9d, r9d; lpThreadAttributes
0x18003c21f  lea     rax, [rsp+0E8h+ProcessInformation]
0x18003c224  xor     r8d, r8d; lpProcessAttributes
0x18003c227  mov     [rsp+0E8h+lpProcessInformation], rax; lpProcessInformation
0x18003c22c  mov     rdx, rbx; lpCommandLine
0x18003c22f  lea     rax, [rsp+0E8h+StartupInfo]
0x18003c234  mov     rcx, rdi; lpApplicationName
0x18003c237  mov     [rsp+0E8h+lpStartupInfo], rax; lpStartupInfo
0x18003c23c  mov     [rsp+0E8h+lpCurrentDirectory], 0; lpCurrentDirectory
0x18003c245  mov     [rsp+0E8h+lpEnvironment], 0; lpEnvironment
0x18003c24e  mov     [rsp+0E8h+dwCreationFlags], 0; dwCreationFlags
0x18003c256  mov     [rsp+0E8h+bInheritHandles], 0; bInheritHandles
0x18003c25e  movups  xmmword ptr [rsp+0E8h+ProcessInformation.hProcess], xmm0
0x18003c263  call    cs:__imp_CreateProcessW
0x18003c26a  nop     dword ptr [rax+rax+00h]
0x18003c26f  test    eax, eax
0x18003c271  jnz     short loc_18003C29F
0x18003c273  call    cs:__imp_GetLastError
0x18003c27a  nop     dword ptr [rax+rax+00h]
0x18003c27f  test    eax, eax
0x18003c281  jg      short loc_18003C287
0x18003c283  mov     ebx, eax
0x18003c285  jmp     short loc_18003C290
0x18003c287  movzx   ebx, ax
0x18003c28a  or      ebx, 0C0070000h
0x18003c290  mov     r9d, 126h
0x18003c296  lea     rdx, aError; "error"
0x18003c29d  jmp     short loc_18003C2D7
0x18003c29f  mov     rax, [rsp+0E8h+ProcessInformation.hProcess]
0x18003c2a4  xor     ebx, ebx
0x18003c2a6  mov     rcx, [rsp+0E8h+ProcessInformation.hThread]; hObject
0x18003c2ab  mov     [rsi], rax
0x18003c2ae  call    cs:__imp_CloseHandle
0x18003c2b5  nop     dword ptr [rax+rax+00h]
0x18003c2ba  test    eax, eax
0x18003c2bc  jnz     short loc_18003C2E5
0x18003c2be  call    cs:__imp_GetLastError
0x18003c2c5  nop     dword ptr [rax+rax+00h]
0x18003c2ca  mov     r9d, 132h
0x18003c2d0  lea     rdx, aGetlasterror; "GetLastError()"
0x18003c2d7  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003c2de  mov     ecx, eax
0x18003c2e0  call    DebugTraceError
0x18003c2e5  lea     r11, [rsp+0E8h+var_8]
0x18003c2ed  mov     eax, ebx
0x18003c2ef  mov     rbx, [r11+10h]
0x18003c2f3  mov     rsi, [r11+18h]
0x18003c2f7  mov     rsp, r11
0x18003c2fa  pop     rdi
0x18003c2fb  retn
```
