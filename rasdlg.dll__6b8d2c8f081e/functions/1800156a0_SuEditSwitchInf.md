# SuEditSwitchInf

- ea: `0x1800156a0`
- end: `0x18001584f`
- name: `SuEditSwitchInf`
- size: `431`
- prototype: `__int64 __fastcall(HWND hWnd)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180015498`

## callees

- `0x18000f380`
- `0x1800156a0`
- `0x18003b40c`
- `0x180048b6c`
- `0x18004d0d2`
- `0x18004d110`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015806`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015806`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1800157e4`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1800157e4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800157f3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800157fe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800157f3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800157fe`
- `rtutils!TracePrintfExA` at `0x180015760`
- `rtutils!TracePrintfExA` at `0x180015760`

## pseudocode

```c
HRESULT __fastcall SuEditSwitchInf(HWND hWnd)
{
  HRESULT result; // eax
  DWORD LastError; // eax
  DWORD dwFlags; // [rsp+20h] [rbp-E0h]
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+50h] [rbp-B0h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+70h] [rbp-90h] BYREF
  _WORD v7[264]; // [rsp+E0h] [rbp-20h] BYREF
  wchar_t pszDest[576]; // [rsp+2F0h] [rbp+1F0h] BYREF

  *(&StartupInfo.cb + 1) = 0;
  memset_0(&StartupInfo, 0, 0x64u);
  v7[0] = 0;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  ((void (__fastcall *)(_QWORD, _WORD *, __int64))g_pGetSystemDirectory)(0, v7, 260);
  result = StringCchPrintfExW(pszDest, 0x23Bu, 0, 0, 0x100u, L"notepad.exe %s\\ras\\switch.inf", v7);
  if ( result >= 0 )
  {
    memset_0(&StartupInfo.cb + 1, 0, 0x64u);
    StartupInfo.cb = 104;
    if ( g_dwTraceId != -1 )
      TracePrintfW1("SuEditInf-cmd=%s", pszDest);
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
    return TracePrintfExA(g_dwTraceId, 0xCu, "SuEditSwitchInf: StringCchPrintfEx failed. hr = 0x%x", result);
  }
  return result;
}

```

## disassembly

```asm
0x1800156a0  mov     [rsp-8+arg_8], rbx
0x1800156a5  push    rbp
0x1800156a6  lea     rbp, [rsp-680h]
0x1800156ae  sub     rsp, 780h
0x1800156b5  mov     rax, cs:__security_cookie
0x1800156bc  xor     rax, rsp
0x1800156bf  mov     [rbp+680h+var_10], rax
0x1800156c6  xor     eax, eax
0x1800156c8  mov     rbx, rcx
0x1800156cb  xor     edx, edx; Val
0x1800156cd  mov     dword ptr [rsp+780h+StartupInfo+4], eax
0x1800156d1  lea     rcx, [rsp+780h+StartupInfo]; void *
0x1800156d6  lea     r8d, [rax+64h]; Size
0x1800156da  call    memset_0
0x1800156df  xor     eax, eax
0x1800156e1  lea     rdx, [rbp+680h+var_6A0]
0x1800156e5  mov     qword ptr [rsp+780h+ProcessInformation.dwProcessId], rax
0x1800156ea  xorps   xmm0, xmm0
0x1800156ed  mov     [rbp+680h+var_6A0], ax
0x1800156f1  mov     r8d, 104h
0x1800156f7  mov     rax, cs:g_pGetSystemDirectory
0x1800156fe  xor     ecx, ecx
0x180015700  movups  xmmword ptr [rsp+780h+ProcessInformation.hProcess], xmm0
0x180015705  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001570a  lea     rax, [rbp+680h+var_6A0]
0x18001570e  xor     r9d, r9d; pcchRemaining
0x180015711  mov     [rsp+780h+lpEnvironment], rax
0x180015716  lea     rcx, [rbp+680h+pszDest]; pszDest
0x18001571d  lea     rax, aNotepadExeSRas; "notepad.exe %s\\ras\\switch.inf"
0x180015724  xor     r8d, r8d; ppszDestEnd
0x180015727  mov     [rsp+780h+pszFormat], rax; pszFormat
0x18001572c  mov     edx, 23Bh; cchDest
0x180015731  mov     [rsp+780h+dwFlags], 100h; dwFlags
0x180015739  call    StringCchPrintfExW
0x18001573e  test    eax, eax
0x180015740  jns     short loc_18001576B
0x180015742  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180015748  cmp     ecx, 0FFFFFFFFh
0x18001574b  jz      loc_18001582F
0x180015751  mov     r9d, eax
0x180015754  lea     r8, aSueditswitchin; "SuEditSwitchInf: StringCchPrintfEx fail"...
0x18001575b  mov     edx, 0Ch; dwFlags
0x180015760  call    cs:__imp_TracePrintfExA
0x180015766  jmp     loc_18001582F
0x18001576b  xor     edx, edx; Val
0x18001576d  lea     rcx, [rsp+780h+StartupInfo+4]; void *
0x180015772  lea     r8d, [rdx+64h]; Size
0x180015776  call    memset_0
0x18001577b  cmp     cs:g_dwTraceId, 0FFFFFFFFh
0x180015782  mov     [rsp+780h+StartupInfo.cb], 68h ; 'h'
0x18001578a  jz      short loc_18001579F
0x18001578c  lea     rdx, [rbp+680h+pszDest]; lpWideCharStr
0x180015793  lea     rcx, aSueditinfCmdS; "SuEditInf-cmd=%s"
0x18001579a  call    TracePrintfW1
0x18001579f  lea     rax, [rsp+780h+ProcessInformation]
0x1800157a4  xor     r9d, r9d; lpThreadAttributes
0x1800157a7  mov     [rsp+780h+lpProcessInformation], rax; lpProcessInformation
0x1800157ac  lea     rdx, [rbp+680h+pszDest]; lpCommandLine
0x1800157b3  lea     rax, [rsp+780h+StartupInfo]
0x1800157b8  xor     r8d, r8d; lpProcessAttributes
0x1800157bb  mov     [rsp+780h+lpStartupInfo], rax; lpStartupInfo
0x1800157c0  xor     ecx, ecx; lpApplicationName
0x1800157c2  mov     [rsp+780h+lpCurrentDirectory], 0; lpCurrentDirectory
0x1800157cb  mov     [rsp+780h+lpEnvironment], 0; lpEnvironment
0x1800157d4  mov     dword ptr [rsp+780h+pszFormat], 0; dwCreationFlags
0x1800157dc  mov     [rsp+780h+dwFlags], 1; int
0x1800157e4  call    cs:__imp_CreateProcessW
0x1800157ea  test    eax, eax
0x1800157ec  jz      short loc_180015806
0x1800157ee  mov     rcx, [rsp+780h+ProcessInformation.hThread]; hObject
0x1800157f3  call    cs:__imp_CloseHandle
0x1800157f9  mov     rcx, [rsp+780h+ProcessInformation.hProcess]; hObject
0x1800157fe  call    cs:__imp_CloseHandle
0x180015804  jmp     short loc_18001582F
0x180015806  call    cs:__imp_GetLastError
0x18001580c  mov     dword ptr [rsp+780h+lpEnvironment], 0FAh; UINT
0x180015814  xor     r9d, r9d
0x180015817  mov     r8d, eax; dwMessageId
0x18001581a  mov     dword ptr [rsp+780h+pszFormat], 169h; UINT
0x180015822  mov     edx, 146h; uID
0x180015827  mov     rcx, rbx; hWnd
0x18001582a  call    ErrorDlgUtil
0x18001582f  mov     rcx, [rbp+680h+var_10]
0x180015836  xor     rcx, rsp; StackCookie
0x180015839  call    __security_check_cookie
0x18001583e  mov     rbx, [rsp+780h+arg_8]
0x180015846  add     rsp, 780h
0x18001584d  pop     rbp
0x18001584e  retn
```
