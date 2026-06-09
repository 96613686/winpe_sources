# ItViewScriptLog

- ea: `0x18002a44c`
- end: `0x18002a5e2`
- name: `ItViewScriptLog`
- size: `406`
- prototype: `int __fastcall(HWND hWnd)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180029ab0`
- `0x180029dc8`

## callees

- `0x18000f380`
- `0x18002a44c`
- `0x180048b6c`
- `0x18004d0d2`
- `0x18004d110`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18002a4f6`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18002a4f6`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18002a57c`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18002a57c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a59e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a59e`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18002a571`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18002a571`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a58b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a596`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a58b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a596`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002a4e3`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002a512`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002a4e3`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002a512`

## string_xrefs

- `0x18002a498`: `%windir%\system32\ras\script.log`

## pseudocode

```c
int __fastcall ItViewScriptLog(HWND hWnd)
{
  HRESULT v2; // eax
  DWORD LastError; // r8d
  DWORD v4; // ebx
  WCHAR *v5; // rax
  WCHAR *v6; // rsi
  BOOL v7; // ebx
  DWORD dwFlags; // [rsp+20h] [rbp-E0h]
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+50h] [rbp-B0h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+70h] [rbp-90h] BYREF
  wchar_t pszDest[576]; // [rsp+E0h] [rbp-20h] BYREF

  *(&StartupInfo.cb + 1) = 0;
  memset_0(&StartupInfo, 0, 0x64u);
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  v2 = StringCchPrintfExW(pszDest, 0x23Bu, 0, 0, 0x100u, L"notepad.exe \"%s\"");
  if ( v2 >= 0 )
  {
    v4 = ExpandEnvironmentStringsW(pszDest, 0, 0);
    v5 = (WCHAR *)GlobalAlloc(0x40u, 2LL * (v4 + 1));
    v6 = v5;
    if ( v5 )
    {
      ExpandEnvironmentStringsW(pszDest, v5, v4);
      memset_0(&StartupInfo.cb + 1, 0, 0x64u);
      StartupInfo.cb = 104;
      v7 = CreateProcessW(0, v6, 0, 0, 1, 0, 0, 0, &StartupInfo, &ProcessInformation);
      GlobalFree(v6);
      if ( v7 )
      {
        CloseHandle(ProcessInformation.hThread);
        return CloseHandle(ProcessInformation.hProcess);
      }
    }
    LastError = GetLastError();
  }
  else
  {
    LastError = (unsigned __int16)v2;
  }
  return ErrorDlgUtil(hWnd, 0x145u, LastError, 0, dwFlags, 0x169u, 0xFAu);
}

```

## disassembly

```asm
0x18002a44c  push    rbp
0x18002a44e  push    rbx
0x18002a44f  push    rsi
0x18002a450  push    rdi
0x18002a451  lea     rbp, [rsp-478h]
0x18002a459  sub     rsp, 578h
0x18002a460  mov     rax, cs:__security_cookie
0x18002a467  xor     rax, rsp
0x18002a46a  mov     [rbp+490h+var_30], rax
0x18002a471  xor     eax, eax
0x18002a473  mov     rdi, rcx
0x18002a476  xor     edx, edx; Val
0x18002a478  mov     dword ptr [rsp+590h+StartupInfo+4], eax
0x18002a47c  lea     rcx, [rsp+590h+StartupInfo]; void *
0x18002a481  lea     r8d, [rax+64h]; Size
0x18002a485  call    memset_0
0x18002a48a  xor     eax, eax
0x18002a48c  lea     rcx, [rbp+490h+pszDest]; pszDest
0x18002a490  mov     qword ptr [rsp+590h+ProcessInformation.dwProcessId], rax
0x18002a495  xorps   xmm0, xmm0
0x18002a498  lea     rax, aWindirSystem32; "%windir%\\system32\\ras\\script.log"
0x18002a49f  xor     r9d, r9d; pcchRemaining
0x18002a4a2  mov     [rsp+590h+lpEnvironment], rax
0x18002a4a7  xor     r8d, r8d; ppszDestEnd
0x18002a4aa  lea     rax, aNotepadExeS_0; "notepad.exe \"%s\""
0x18002a4b1  mov     edx, 23Bh; cchDest
0x18002a4b6  mov     [rsp+590h+pszFormat], rax; pszFormat
0x18002a4bb  mov     [rsp+590h+dwFlags], 100h; int
0x18002a4c3  movups  xmmword ptr [rsp+590h+ProcessInformation.hProcess], xmm0
0x18002a4c8  call    StringCchPrintfExW
0x18002a4cd  test    eax, eax
0x18002a4cf  jns     short loc_18002A4DA
0x18002a4d1  movzx   r8d, ax
0x18002a4d5  jmp     loc_18002A5A7
0x18002a4da  xor     r8d, r8d; nSize
0x18002a4dd  lea     rcx, [rbp+490h+pszDest]; lpSrc
0x18002a4e1  xor     edx, edx; lpDst
0x18002a4e3  call    cs:__imp_ExpandEnvironmentStringsW
0x18002a4e9  mov     ecx, 40h ; '@'; uFlags
0x18002a4ee  mov     ebx, eax
0x18002a4f0  lea     edx, [rax+1]
0x18002a4f3  add     rdx, rdx; dwBytes
0x18002a4f6  call    cs:__imp_GlobalAlloc
0x18002a4fc  mov     rsi, rax
0x18002a4ff  test    rax, rax
0x18002a502  jz      loc_18002A59E
0x18002a508  mov     r8d, ebx; nSize
0x18002a50b  lea     rcx, [rbp+490h+pszDest]; lpSrc
0x18002a50f  mov     rdx, rax; lpDst
0x18002a512  call    cs:__imp_ExpandEnvironmentStringsW
0x18002a518  xor     edx, edx; Val
0x18002a51a  lea     rcx, [rsp+590h+StartupInfo+4]; void *
0x18002a51f  lea     r8d, [rdx+64h]; Size
0x18002a523  call    memset_0
0x18002a528  lea     rax, [rsp+590h+ProcessInformation]
0x18002a52d  mov     [rsp+590h+StartupInfo.cb], 68h ; 'h'
0x18002a535  mov     [rsp+590h+lpProcessInformation], rax; lpProcessInformation
0x18002a53a  xor     r9d, r9d; lpThreadAttributes
0x18002a53d  lea     rax, [rsp+590h+StartupInfo]
0x18002a542  xor     r8d, r8d; lpProcessAttributes
0x18002a545  mov     [rsp+590h+lpStartupInfo], rax; lpStartupInfo
0x18002a54a  mov     rdx, rsi; lpCommandLine
0x18002a54d  mov     [rsp+590h+lpCurrentDirectory], 0; lpCurrentDirectory
0x18002a556  xor     ecx, ecx; lpApplicationName
0x18002a558  mov     [rsp+590h+lpEnvironment], 0; lpEnvironment
0x18002a561  mov     dword ptr [rsp+590h+pszFormat], 0; dwCreationFlags
0x18002a569  mov     [rsp+590h+dwFlags], 1; bInheritHandles
0x18002a571  call    cs:__imp_CreateProcessW
0x18002a577  mov     rcx, rsi; hMem
0x18002a57a  mov     ebx, eax
0x18002a57c  call    cs:__imp_GlobalFree
0x18002a582  test    ebx, ebx
0x18002a584  jz      short loc_18002A59E
0x18002a586  mov     rcx, [rsp+590h+ProcessInformation.hThread]; hObject
0x18002a58b  call    cs:__imp_CloseHandle
0x18002a591  mov     rcx, [rsp+590h+ProcessInformation.hProcess]; hObject
0x18002a596  call    cs:__imp_CloseHandle
0x18002a59c  jmp     short loc_18002A5C7
0x18002a59e  call    cs:__imp_GetLastError
0x18002a5a4  mov     r8d, eax; dwMessageId
0x18002a5a7  mov     dword ptr [rsp+590h+lpEnvironment], 0FAh; UINT
0x18002a5af  xor     r9d, r9d
0x18002a5b2  mov     edx, 145h; uID
0x18002a5b7  mov     dword ptr [rsp+590h+pszFormat], 169h; UINT
0x18002a5bf  mov     rcx, rdi; hWnd
0x18002a5c2  call    ErrorDlgUtil
0x18002a5c7  mov     rcx, [rbp+490h+var_30]
0x18002a5ce  xor     rcx, rsp; StackCookie
0x18002a5d1  call    __security_check_cookie
0x18002a5d6  add     rsp, 578h
0x18002a5dd  pop     rdi
0x18002a5de  pop     rsi
0x18002a5df  pop     rbx
0x18002a5e0  pop     rbp
0x18002a5e1  retn
```
