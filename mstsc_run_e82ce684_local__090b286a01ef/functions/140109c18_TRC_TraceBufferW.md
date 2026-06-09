# TRC_TraceBufferW

- ea: `0x140109c18`
- end: `0x140109d57`
- name: `TRC_TraceBufferW`
- size: `319`
- prototype: `__int64 __fastcall(int, int, int, int, int, int, STRSAFE_LPCWSTR pszFormat, char)`
- caller_count: `4`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x140098180`
- `0x140098394`
- `0x140098510`
- `0x140098734`

## callees

- `0x140008a78`
- `0x140008b7c`
- `0x140109c18`
- `0x140113390`

## import_xrefs

- `KERNEL32!GetSystemTime` at `0x140109c7d`
- `KERNEL32!GetSystemTime` at `0x140109c7d`
- `KERNEL32!DebugBreak` at `0x140109c68`
- `KERNEL32!DebugBreak` at `0x140109c68`
- `KERNEL32!GetCurrentProcessId` at `0x140109cc8`
- `KERNEL32!GetCurrentProcessId` at `0x140109cc8`
- `KERNEL32!OutputDebugStringW` at `0x140109d2e`
- `KERNEL32!OutputDebugStringW` at `0x140109d2e`
- `KERNEL32!GetCurrentThreadId` at `0x140109cc0`
- `KERNEL32!GetCurrentThreadId` at `0x140109cc0`

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
  struct _SYSTEMTIME SystemTime; // [rsp+98h] [rbp-68h] BYREF
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
0x140109c18  push    rbp
0x140109c1a  push    rbx
0x140109c1b  push    rsi
0x140109c1c  push    rdi
0x140109c1d  push    r12
0x140109c1f  push    r13
0x140109c21  push    r14
0x140109c23  push    r15
0x140109c25  lea     rbp, [rsp-2C8h]
0x140109c2d  sub     rsp, 3C8h
0x140109c34  mov     rax, cs:__security_cookie
0x140109c3b  xor     rax, rsp
0x140109c3e  mov     [rbp+300h+var_50], rax
0x140109c45  mov     [rbp+300h+var_370], r9
0x140109c49  xorps   xmm0, xmm0
0x140109c4c  mov     [rbp+300h+var_380], r8d
0x140109c50  lea     rbx, [rbp+300h+arg_38]
0x140109c57  mov     [rbp+300h+var_378], 0
0x140109c5f  movups  xmmword ptr [rbp+300h+SystemTime.wYear], xmm0
0x140109c63  cmp     ecx, 4
0x140109c66  jnz     short loc_140109C70
0x140109c68  call    cs:__imp_DebugBreak
0x140109c6e  jmp     short loc_140109C79
0x140109c70  cmp     ecx, 3
0x140109c73  jnz     loc_140109D34
0x140109c79  lea     rcx, [rbp+300h+SystemTime]; lpSystemTime
0x140109c7d  call    cs:__imp_GetSystemTime
0x140109c83  mov     r9, [rbp+300h+pszFormat]; pszFormat
0x140109c8a  lea     rcx, [rbp+300h+pszDest]; pszDest
0x140109c8e  mov     edx, 80h; cchDest
0x140109c93  mov     [rsp+400h+argList], rbx; argList
0x140109c98  call    StringVPrintfWorkerW
0x140109c9d  movzx   eax, [rbp+300h+SystemTime.wYear]
0x140109ca1  movzx   edi, [rbp+300h+SystemTime.wMilliseconds]
0x140109ca5  movzx   esi, [rbp+300h+SystemTime.wSecond]
0x140109ca9  movzx   r14d, [rbp+300h+SystemTime.wMinute]
0x140109cae  movzx   r15d, [rbp+300h+SystemTime.wHour]
0x140109cb3  movzx   r12d, [rbp+300h+SystemTime.wDay]
0x140109cb8  movzx   r13d, [rbp+300h+SystemTime.wMonth]
0x140109cbd  mov     dword ptr [rbp+300h+var_378], eax
0x140109cc0  call    cs:__imp_GetCurrentThreadId
0x140109cc6  mov     ebx, eax
0x140109cc8  call    cs:__imp_GetCurrentProcessId
0x140109cce  mov     r9d, dword ptr [rbp+300h+var_378]
0x140109cd2  lea     rcx, [rbp+300h+pszDest]
0x140109cd6  mov     [rsp+400h+var_390], rcx
0x140109cdb  lea     r8, a04d02d02d02d02; "%04d-%02d-%02d %02d:%02d:%02d.%03d PID:"...
0x140109ce2  mov     rcx, [rbp+300h+var_370]
0x140109ce6  mov     edx, 0FFh; unsigned __int64
0x140109ceb  mov     [rsp+400h+var_398], rcx
0x140109cf0  mov     ecx, [rbp+300h+var_380]
0x140109cf3  mov     [rsp+400h+var_3A0], ecx
0x140109cf7  lea     rcx, [rbp+300h+OutputString]; unsigned __int16 *
0x140109cfe  mov     [rsp+400h+var_3A8], ebx
0x140109d02  mov     [rsp+400h+var_3B0], eax
0x140109d06  mov     [rsp+400h+var_3B8], edi
0x140109d0a  mov     [rsp+400h+var_3C0], esi
0x140109d0e  mov     [rsp+400h+var_3C8], r14d
0x140109d13  mov     [rsp+400h+var_3D0], r15d
0x140109d18  mov     [rsp+400h+var_3D8], r12d
0x140109d1d  mov     dword ptr [rsp+400h+argList], r13d
0x140109d22  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140109d27  lea     rcx, [rbp+300h+OutputString]; lpOutputString
0x140109d2e  call    cs:__imp_OutputDebugStringW
0x140109d34  mov     rcx, [rbp+300h+var_50]
0x140109d3b  xor     rcx, rsp; StackCookie
0x140109d3e  call    __security_check_cookie
0x140109d43  add     rsp, 3C8h
0x140109d4a  pop     r15
0x140109d4c  pop     r14
0x140109d4e  pop     r13
0x140109d50  pop     r12
0x140109d52  pop     rdi
0x140109d53  pop     rsi
0x140109d54  pop     rbx
0x140109d55  pop     rbp
0x140109d56  retn
```
