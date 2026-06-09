# TRC_TraceBufferW

- ea: `0x140060ae0`
- end: `0x140060c1f`
- name: `TRC_TraceBufferW`
- size: `319`
- prototype: `__int64 __fastcall(int, int, int, int, int, int, STRSAFE_LPCWSTR pszFormat, char)`
- caller_count: `4`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x1400600a8`
- `0x14006032c`
- `0x140060438`
- `0x14006059c`

## callees

- `0x140008ce0`
- `0x140008de4`
- `0x140060ae0`
- `0x14006a120`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x140060b30`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x140060b30`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140060bf6`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140060bf6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140060b88`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140060b88`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140060b90`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140060b90`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x140060b45`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x140060b45`

## pseudocode

```c
void TRC_TraceBufferW(int a1, int a2, int a3, __int64 a4, int a5, int a6, STRSAFE_LPCWSTR pszFormat, ...)
{
  size_t *v7; // r8
  int wMilliseconds; // edi
  int wSecond; // esi
  int wMinute; // r14d
  int wHour; // r15d
  int wDay; // r12d
  int wMonth; // r13d
  va_list argList; // [rsp+20h] [rbp-E0h]
  DWORD CurrentProcessId; // [rsp+50h] [rbp-B0h]
  DWORD CurrentThreadId; // [rsp+58h] [rbp-A8h]
  unsigned int wYear; // [rsp+88h] [rbp-78h]
  _SYSTEMTIME SystemTime; // [rsp+98h] [rbp-68h] BYREF
  wchar_t pszDest[128]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR OutputString[256]; // [rsp+1B0h] [rbp+B0h] BYREF
  va_list va; // [rsp+448h] [rbp+348h] BYREF

  va_start(va, pszFormat);
  SystemTime = 0;
  if ( a1 == 4 )
  {
    DebugBreak();
  }
  else if ( a1 != 3 )
  {
    return;
  }
  GetSystemTime(&SystemTime);
  StringVPrintfWorkerW(pszDest, 0x80u, v7, pszFormat, va);
  wMilliseconds = SystemTime.wMilliseconds;
  wSecond = SystemTime.wSecond;
  wMinute = SystemTime.wMinute;
  wHour = SystemTime.wHour;
  wDay = SystemTime.wDay;
  wMonth = SystemTime.wMonth;
  wYear = SystemTime.wYear;
  CurrentThreadId = GetCurrentThreadId();
  CurrentProcessId = GetCurrentProcessId();
  LODWORD(argList) = wMonth;
  StringCchPrintfW(
    OutputString,
    0xFFu,
    L"%04d-%02d-%02d %02d:%02d:%02d.%03d PID:0x%x TID:0x%x L:%04d:%s - %s\r\n",
    wYear,
    argList,
    wDay,
    wHour,
    wMinute,
    wSecond,
    wMilliseconds,
    CurrentProcessId,
    CurrentThreadId,
    a3,
    a4,
    pszDest);
  OutputDebugStringW(OutputString);
}

```

## disassembly

```asm
0x140060ae0  push    rbp
0x140060ae2  push    rbx
0x140060ae3  push    rsi
0x140060ae4  push    rdi
0x140060ae5  push    r12
0x140060ae7  push    r13
0x140060ae9  push    r14
0x140060aeb  push    r15
0x140060aed  lea     rbp, [rsp-2C8h]
0x140060af5  sub     rsp, 3C8h
0x140060afc  mov     rax, cs:__security_cookie
0x140060b03  xor     rax, rsp
0x140060b06  mov     [rbp+300h+var_50], rax
0x140060b0d  mov     [rbp+300h+var_370], r9
0x140060b11  xorps   xmm0, xmm0
0x140060b14  mov     [rbp+300h+var_380], r8d
0x140060b18  lea     rbx, [rbp+300h+arg_38]
0x140060b1f  mov     [rbp+300h+var_378], 0
0x140060b27  movups  xmmword ptr [rbp+300h+SystemTime.wYear], xmm0
0x140060b2b  cmp     ecx, 4
0x140060b2e  jnz     short loc_140060B38
0x140060b30  call    cs:__imp_DebugBreak
0x140060b36  jmp     short loc_140060B41
0x140060b38  cmp     ecx, 3
0x140060b3b  jnz     loc_140060BFC
0x140060b41  lea     rcx, [rbp+300h+SystemTime]; lpSystemTime
0x140060b45  call    cs:__imp_GetSystemTime
0x140060b4b  mov     r9, [rbp+300h+pszFormat]; pszFormat
0x140060b52  lea     rcx, [rbp+300h+pszDest]; pszDest
0x140060b56  mov     edx, 80h; cchDest
0x140060b5b  mov     [rsp+400h+argList], rbx; argList
0x140060b60  call    StringVPrintfWorkerW
0x140060b65  movzx   eax, [rbp+300h+SystemTime.wYear]
0x140060b69  movzx   edi, [rbp+300h+SystemTime.wMilliseconds]
0x140060b6d  movzx   esi, [rbp+300h+SystemTime.wSecond]
0x140060b71  movzx   r14d, [rbp+300h+SystemTime.wMinute]
0x140060b76  movzx   r15d, [rbp+300h+SystemTime.wHour]
0x140060b7b  movzx   r12d, [rbp+300h+SystemTime.wDay]
0x140060b80  movzx   r13d, [rbp+300h+SystemTime.wMonth]
0x140060b85  mov     dword ptr [rbp+300h+var_378], eax
0x140060b88  call    cs:__imp_GetCurrentThreadId
0x140060b8e  mov     ebx, eax
0x140060b90  call    cs:__imp_GetCurrentProcessId
0x140060b96  mov     r9d, dword ptr [rbp+300h+var_378]
0x140060b9a  lea     rcx, [rbp+300h+pszDest]
0x140060b9e  mov     [rsp+400h+var_390], rcx
0x140060ba3  lea     r8, a04d02d02d02d02; "%04d-%02d-%02d %02d:%02d:%02d.%03d PID:"...
0x140060baa  mov     rcx, [rbp+300h+var_370]
0x140060bae  mov     edx, 0FFh; unsigned __int64
0x140060bb3  mov     [rsp+400h+var_398], rcx
0x140060bb8  mov     ecx, [rbp+300h+var_380]
0x140060bbb  mov     [rsp+400h+var_3A0], ecx
0x140060bbf  lea     rcx, [rbp+300h+OutputString]; unsigned __int16 *
0x140060bc6  mov     [rsp+400h+var_3A8], ebx
0x140060bca  mov     [rsp+400h+var_3B0], eax
0x140060bce  mov     [rsp+400h+var_3B8], edi
0x140060bd2  mov     [rsp+400h+var_3C0], esi
0x140060bd6  mov     [rsp+400h+var_3C8], r14d
0x140060bdb  mov     [rsp+400h+var_3D0], r15d
0x140060be0  mov     [rsp+400h+var_3D8], r12d
0x140060be5  mov     dword ptr [rsp+400h+argList], r13d
0x140060bea  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140060bef  lea     rcx, [rbp+300h+OutputString]; lpOutputString
0x140060bf6  call    cs:__imp_OutputDebugStringW
0x140060bfc  mov     rcx, [rbp+300h+var_50]
0x140060c03  xor     rcx, rsp; StackCookie
0x140060c06  call    __security_check_cookie
0x140060c0b  add     rsp, 3C8h
0x140060c12  pop     r15
0x140060c14  pop     r14
0x140060c16  pop     r13
0x140060c18  pop     r12
0x140060c1a  pop     rdi
0x140060c1b  pop     rsi
0x140060c1c  pop     rbx
0x140060c1d  pop     rbp
0x140060c1e  retn
```
