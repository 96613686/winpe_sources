# TRC_TraceBufferW

- ea: `0x140107aa8`
- end: `0x140107be7`
- name: `TRC_TraceBufferW`
- size: `319`
- prototype: `__int64 __fastcall(int, int, int, int, int, int, STRSAFE_LPCWSTR pszFormat, char)`
- caller_count: `4`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x140096010`
- `0x140096224`
- `0x1400963a0`
- `0x1400965c4`

## callees

- `0x140008a78`
- `0x140008b7c`
- `0x140107aa8`
- `0x140111220`

## import_xrefs

- `KERNEL32!GetSystemTime` at `0x140107b0d`
- `KERNEL32!GetSystemTime` at `0x140107b0d`
- `KERNEL32!DebugBreak` at `0x140107af8`
- `KERNEL32!DebugBreak` at `0x140107af8`
- `KERNEL32!GetCurrentProcessId` at `0x140107b58`
- `KERNEL32!GetCurrentProcessId` at `0x140107b58`
- `KERNEL32!OutputDebugStringW` at `0x140107bbe`
- `KERNEL32!OutputDebugStringW` at `0x140107bbe`
- `KERNEL32!GetCurrentThreadId` at `0x140107b50`
- `KERNEL32!GetCurrentThreadId` at `0x140107b50`

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
0x140107aa8  push    rbp
0x140107aaa  push    rbx
0x140107aab  push    rsi
0x140107aac  push    rdi
0x140107aad  push    r12
0x140107aaf  push    r13
0x140107ab1  push    r14
0x140107ab3  push    r15
0x140107ab5  lea     rbp, [rsp-2C8h]
0x140107abd  sub     rsp, 3C8h
0x140107ac4  mov     rax, cs:__security_cookie
0x140107acb  xor     rax, rsp
0x140107ace  mov     [rbp+300h+var_50], rax
0x140107ad5  mov     [rbp+300h+var_370], r9
0x140107ad9  xorps   xmm0, xmm0
0x140107adc  mov     [rbp+300h+var_380], r8d
0x140107ae0  lea     rbx, [rbp+300h+arg_38]
0x140107ae7  mov     [rbp+300h+var_378], 0
0x140107aef  movups  xmmword ptr [rbp+300h+SystemTime.wYear], xmm0
0x140107af3  cmp     ecx, 4
0x140107af6  jnz     short loc_140107B00
0x140107af8  call    cs:__imp_DebugBreak
0x140107afe  jmp     short loc_140107B09
0x140107b00  cmp     ecx, 3
0x140107b03  jnz     loc_140107BC4
0x140107b09  lea     rcx, [rbp+300h+SystemTime]; lpSystemTime
0x140107b0d  call    cs:__imp_GetSystemTime
0x140107b13  mov     r9, [rbp+300h+pszFormat]; pszFormat
0x140107b1a  lea     rcx, [rbp+300h+pszDest]; pszDest
0x140107b1e  mov     edx, 80h; cchDest
0x140107b23  mov     [rsp+400h+argList], rbx; argList
0x140107b28  call    StringVPrintfWorkerW
0x140107b2d  movzx   eax, [rbp+300h+SystemTime.wYear]
0x140107b31  movzx   edi, [rbp+300h+SystemTime.wMilliseconds]
0x140107b35  movzx   esi, [rbp+300h+SystemTime.wSecond]
0x140107b39  movzx   r14d, [rbp+300h+SystemTime.wMinute]
0x140107b3e  movzx   r15d, [rbp+300h+SystemTime.wHour]
0x140107b43  movzx   r12d, [rbp+300h+SystemTime.wDay]
0x140107b48  movzx   r13d, [rbp+300h+SystemTime.wMonth]
0x140107b4d  mov     dword ptr [rbp+300h+var_378], eax
0x140107b50  call    cs:__imp_GetCurrentThreadId
0x140107b56  mov     ebx, eax
0x140107b58  call    cs:__imp_GetCurrentProcessId
0x140107b5e  mov     r9d, dword ptr [rbp+300h+var_378]
0x140107b62  lea     rcx, [rbp+300h+pszDest]
0x140107b66  mov     [rsp+400h+var_390], rcx
0x140107b6b  lea     r8, a04d02d02d02d02; "%04d-%02d-%02d %02d:%02d:%02d.%03d PID:"...
0x140107b72  mov     rcx, [rbp+300h+var_370]
0x140107b76  mov     edx, 0FFh; unsigned __int64
0x140107b7b  mov     [rsp+400h+var_398], rcx
0x140107b80  mov     ecx, [rbp+300h+var_380]
0x140107b83  mov     [rsp+400h+var_3A0], ecx
0x140107b87  lea     rcx, [rbp+300h+OutputString]; unsigned __int16 *
0x140107b8e  mov     [rsp+400h+var_3A8], ebx
0x140107b92  mov     [rsp+400h+var_3B0], eax
0x140107b96  mov     [rsp+400h+var_3B8], edi
0x140107b9a  mov     [rsp+400h+var_3C0], esi
0x140107b9e  mov     [rsp+400h+var_3C8], r14d
0x140107ba3  mov     [rsp+400h+var_3D0], r15d
0x140107ba8  mov     [rsp+400h+var_3D8], r12d
0x140107bad  mov     dword ptr [rsp+400h+argList], r13d
0x140107bb2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140107bb7  lea     rcx, [rbp+300h+OutputString]; lpOutputString
0x140107bbe  call    cs:__imp_OutputDebugStringW
0x140107bc4  mov     rcx, [rbp+300h+var_50]
0x140107bcb  xor     rcx, rsp; StackCookie
0x140107bce  call    __security_check_cookie
0x140107bd3  add     rsp, 3C8h
0x140107bda  pop     r15
0x140107bdc  pop     r14
0x140107bde  pop     r13
0x140107be0  pop     r12
0x140107be2  pop     rdi
0x140107be3  pop     rsi
0x140107be4  pop     rbx
0x140107be5  pop     rbp
0x140107be6  retn
```
