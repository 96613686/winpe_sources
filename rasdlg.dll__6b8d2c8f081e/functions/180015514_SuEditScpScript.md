# SuEditScpScript

- ea: `0x180015514`
- end: `0x18001569a`
- name: `SuEditScpScript`
- size: `390`
- prototype: `__int64 __fastcall(HWND hWnd)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180015498`

## callees

- `0x18000f380`
- `0x180015514`
- `0x18003b40c`
- `0x180048b6c`
- `0x18004d0d2`
- `0x18004d110`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001564d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001564d`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18001562b`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18001562b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001563a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015645`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001563a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015645`
- `rtutils!TracePrintfExA` at `0x1800155b9`
- `rtutils!TracePrintfExA` at `0x1800155b9`

## string_xrefs

- `0x1800155af`: `WriteShortcutFile: StringCchPrintfEx failed. hr = 0x%x`

## pseudocode

```c
HRESULT __fastcall SuEditScpScript(HWND hWnd, __int64 a2)
{
  HRESULT result; // eax
  DWORD LastError; // eax
  DWORD dwFlags; // [rsp+20h] [rbp-E0h]
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+50h] [rbp-B0h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+70h] [rbp-90h] BYREF
  wchar_t pszDest[576]; // [rsp+E0h] [rbp-20h] BYREF

  *(&StartupInfo.cb + 1) = 0;
  memset_0(&StartupInfo, 0, 0x64u);
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  result = StringCchPrintfExW(pszDest, 0x23Bu, 0, 0, 0x100u, L"notepad.exe %s", a2);
  if ( result >= 0 )
  {
    memset_0(&StartupInfo.cb + 1, 0, 0x64u);
    StartupInfo.cb = 104;
    if ( g_dwTraceId != -1 )
      TracePrintfW1("SuEditScp-cmd=%s", pszDest);
    if ( CreateProcessW(0, pszDest, 0, 0, 1, 0, 0, 0, &StartupInfo, &ProcessInformation) )
    {
      CloseHandle(ProcessInformation.hThread);
      return CloseHandle(ProcessInformation.hProcess);
    }
    else
    {
      LastError = GetLastError();
      return ErrorDlgUtil(hWnd, 0x146u, LastError, 0, dwFlags, 0x169u, 0xFAu);
    }
  }
  else if ( g_dwTraceId != -1 )
  {
    return TracePrintfExA(g_dwTraceId, 0xCu, "WriteShortcutFile: StringCchPrintfEx failed. hr = 0x%x", result);
  }
  return result;
}

```

## disassembly

```asm
0x180015514  mov     [rsp-8+arg_10], rbx
0x180015519  mov     [rsp-8+arg_18], rdi
0x18001551e  push    rbp
0x18001551f  lea     rbp, [rsp-470h]
0x180015527  sub     rsp, 570h
0x18001552e  mov     rax, cs:__security_cookie
0x180015535  xor     rax, rsp
0x180015538  mov     [rbp+470h+var_10], rax
0x18001553f  xor     eax, eax
0x180015541  mov     rbx, rdx
0x180015544  mov     rdi, rcx
0x180015547  mov     dword ptr [rsp+570h+StartupInfo+4], eax
0x18001554b  xor     edx, edx; Val
0x18001554d  lea     rcx, [rsp+570h+StartupInfo]; void *
0x180015552  lea     r8d, [rax+64h]; Size
0x180015556  call    memset_0
0x18001555b  xor     eax, eax
0x18001555d  mov     [rsp+570h+lpEnvironment], rbx
0x180015562  mov     qword ptr [rsp+570h+ProcessInformation.dwProcessId], rax
0x180015567  lea     rcx, [rbp+470h+pszDest]; pszDest
0x18001556b  lea     rax, aNotepadExeS; "notepad.exe %s"
0x180015572  xorps   xmm0, xmm0
0x180015575  mov     [rsp+570h+pszFormat], rax; pszFormat
0x18001557a  xor     r9d, r9d; pcchRemaining
0x18001557d  xor     r8d, r8d; ppszDestEnd
0x180015580  mov     [rsp+570h+dwFlags], 100h; dwFlags
0x180015588  mov     edx, 23Bh; cchDest
0x18001558d  movups  xmmword ptr [rsp+570h+ProcessInformation.hProcess], xmm0
0x180015592  call    StringCchPrintfExW
0x180015597  xor     ebx, ebx
0x180015599  test    eax, eax
0x18001559b  jns     short loc_1800155C4
0x18001559d  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800155a3  cmp     ecx, 0FFFFFFFFh
0x1800155a6  jz      loc_180015676
0x1800155ac  mov     r9d, eax
0x1800155af  lea     r8, aWriteshortcutf; "WriteShortcutFile: StringCchPrintfEx fa"...
0x1800155b6  lea     edx, [rbx+0Ch]; dwFlags
0x1800155b9  call    cs:__imp_TracePrintfExA
0x1800155bf  jmp     loc_180015676
0x1800155c4  xor     edx, edx; Val
0x1800155c6  lea     rcx, [rsp+570h+StartupInfo+4]; void *
0x1800155cb  lea     r8d, [rdx+64h]; Size
0x1800155cf  call    memset_0
0x1800155d4  cmp     cs:g_dwTraceId, 0FFFFFFFFh
0x1800155db  mov     [rsp+570h+StartupInfo.cb], 68h ; 'h'
0x1800155e3  jz      short loc_1800155F5
0x1800155e5  lea     rdx, [rbp+470h+pszDest]; lpWideCharStr
0x1800155e9  lea     rcx, aSueditscpCmdS; "SuEditScp-cmd=%s"
0x1800155f0  call    TracePrintfW1
0x1800155f5  lea     rax, [rsp+570h+ProcessInformation]
0x1800155fa  xor     r9d, r9d; lpThreadAttributes
0x1800155fd  mov     [rsp+570h+lpProcessInformation], rax; lpProcessInformation
0x180015602  lea     rdx, [rbp+470h+pszDest]; lpCommandLine
0x180015606  lea     rax, [rsp+570h+StartupInfo]
0x18001560b  xor     r8d, r8d; lpProcessAttributes
0x18001560e  mov     [rsp+570h+lpStartupInfo], rax; lpStartupInfo
0x180015613  xor     ecx, ecx; lpApplicationName
0x180015615  mov     [rsp+570h+lpCurrentDirectory], rbx; lpCurrentDirectory
0x18001561a  mov     [rsp+570h+lpEnvironment], rbx; lpEnvironment
0x18001561f  mov     dword ptr [rsp+570h+pszFormat], ebx; dwCreationFlags
0x180015623  mov     [rsp+570h+dwFlags], 1; int
0x18001562b  call    cs:__imp_CreateProcessW
0x180015631  test    eax, eax
0x180015633  jz      short loc_18001564D
0x180015635  mov     rcx, [rsp+570h+ProcessInformation.hThread]; hObject
0x18001563a  call    cs:__imp_CloseHandle
0x180015640  mov     rcx, [rsp+570h+ProcessInformation.hProcess]; hObject
0x180015645  call    cs:__imp_CloseHandle
0x18001564b  jmp     short loc_180015676
0x18001564d  call    cs:__imp_GetLastError
0x180015653  mov     dword ptr [rsp+570h+lpEnvironment], 0FAh; UINT
0x18001565b  xor     r9d, r9d
0x18001565e  mov     r8d, eax; dwMessageId
0x180015661  mov     dword ptr [rsp+570h+pszFormat], 169h; UINT
0x180015669  mov     edx, 146h; uID
0x18001566e  mov     rcx, rdi; hWnd
0x180015671  call    ErrorDlgUtil
0x180015676  mov     rcx, [rbp+470h+var_10]
0x18001567d  xor     rcx, rsp; StackCookie
0x180015680  call    __security_check_cookie
0x180015685  lea     r11, [rsp+570h+var_s0]
0x18001568d  mov     rbx, [r11+20h]
0x180015691  mov     rdi, [r11+28h]
0x180015695  mov     rsp, r11
0x180015698  pop     rbp
0x180015699  retn
```
