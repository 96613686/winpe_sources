# DtcExceptionFilter(_EXCEPTION_POINTERS *,int)

- ea: `0x18000db58`
- end: `0x18000dc83`
- name: `?DtcExceptionFilter@@YAKPEAU_EXCEPTION_POINTERS@@H@Z`
- size: `299`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180006210`

## callees

- `0x18000db58`
- `0x18000dd90`
- `0x18000debc`
- `0x18000df74`
- `0x180012830`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000dbb9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000dbb9`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000dc50`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000dc50`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000dc66`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000dc66`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x18000dbc8`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x18000dbc8`
- `ADVAPI32!DeregisterEventSource` at `0x18000dc74`
- `ADVAPI32!DeregisterEventSource` at `0x18000dc74`
- `ADVAPI32!ReportEventW` at `0x18000dc45`
- `ADVAPI32!ReportEventW` at `0x18000dc45`
- `ADVAPI32!RegisterEventSourceW` at `0x18000dc07`
- `ADVAPI32!RegisterEventSourceW` at `0x18000dc07`

## string_xrefs

- `0x18000dbd3`: `The process '%s' hit an exception in a MSDTC related component.\nThe following exception (0x%08x) was generated at 0x%016p, Pid:%d.\nThe process is being terminated.\nAdditional information useful in a debugger:\nYou can do '.exr 0x%p' to display the exception record.\nYou can do '.cxr 0x%p' to display the context at the time of the exception.\n\n`

## pseudocode

```c
__int64 __fastcall DtcExceptionFilter(struct _EXCEPTION_POINTERS *a1)
{
  PEXCEPTION_RECORD ExceptionRecord; // r15
  PCONTEXT ContextRecord; // rbx
  DWORD CurrentProcessId; // eax
  PVOID ExceptionAddress; // rsi
  DWORD v7; // edi
  DWORD ExceptionCode; // ebp
  LPWSTR CommandLineW; // rax
  HANDLE v10; // rbx
  unsigned int v11; // edx
  DWORD lpUserSid; // [rsp+20h] [rbp-688h]
  DWORD dwDataSize; // [rsp+30h] [rbp-678h]
  LPCWSTR Strings; // [rsp+50h] [rbp-658h] BYREF
  WCHAR OutputString[768]; // [rsp+60h] [rbp-648h] BYREF

  ExceptionRecord = a1->ExceptionRecord;
  Strings = OutputString;
  if ( ExceptionRecord->ExceptionCode != -2147483645 )
  {
    ContextRecord = a1->ContextRecord;
    CurrentProcessId = GetCurrentProcessId();
    ExceptionAddress = ExceptionRecord->ExceptionAddress;
    v7 = CurrentProcessId;
    ExceptionCode = ExceptionRecord->ExceptionCode;
    CommandLineW = GetCommandLineW();
    dwDataSize = v7;
    lpUserSid = ExceptionCode;
    StringCbPrintfW(
      OutputString,
      0x600u,
      L"The process '%s' hit an exception in a MSDTC related component.\n"
       "The following exception (0x%08x) was generated at 0x%016p, Pid:%d.\n"
       "The process is being terminated.\n"
       "Additional information useful in a debugger:\n"
       "You can do '.exr 0x%p' to display the exception record.\n"
       "You can do '.cxr 0x%p' to display the context at the time of the exception.\n"
       "\n",
      CommandLineW,
      lpUserSid,
      ExceptionAddress,
      dwDataSize,
      ExceptionRecord,
      ContextRecord);
    v10 = RegisterEventSourceW(0, L"MSDTC");
    if ( v10 )
      ReportEventW(v10, 1u, 1u, 0xC0001103, 0, 1u, 0, &Strings, 0);
    OutputDebugStringW(OutputString);
    if ( GetLocalDTCProfileInt("DtcDebugBreak", v11) )
      DebugBreak();
    if ( v10 )
      DeregisterEventSource(v10);
    DtcRaiseExceptionForWatsonCrashAnalysis(a1);
    JUMPOUT(0x18000DC82LL);
  }
  return 0;
}

```

## disassembly

```asm
0x18000db58  push    rbx
0x18000db5a  push    rbp
0x18000db5b  push    rsi
0x18000db5c  push    rdi
0x18000db5d  push    r14
0x18000db5f  push    r15
0x18000db61  sub     rsp, 678h
0x18000db68  mov     rax, cs:__security_cookie
0x18000db6f  xor     rax, rsp
0x18000db72  mov     [rsp+6A8h+var_48], rax
0x18000db7a  mov     r15, [rcx]
0x18000db7d  lea     rax, [rsp+6A8h+OutputString]
0x18000db82  mov     [rsp+6A8h+Strings], rax
0x18000db87  mov     r14, rcx
0x18000db8a  cmp     dword ptr [r15], 80000003h
0x18000db91  jnz     short loc_18000DBB5
0x18000db93  xor     eax, eax
0x18000db95  mov     rcx, [rsp+6A8h+var_48]
0x18000db9d  xor     rcx, rsp; StackCookie
0x18000dba0  call    __security_check_cookie
0x18000dba5  add     rsp, 678h
0x18000dbac  pop     r15
0x18000dbae  pop     r14
0x18000dbb0  pop     rdi
0x18000dbb1  pop     rsi
0x18000dbb2  pop     rbp
0x18000dbb3  pop     rbx
0x18000dbb4  retn
0x18000dbb5  mov     rbx, [rcx+8]
0x18000dbb9  call    cs:__imp_GetCurrentProcessId
0x18000dbbf  mov     rsi, [r15+10h]
0x18000dbc3  mov     edi, eax
0x18000dbc5  mov     ebp, [r15]
0x18000dbc8  call    cs:__imp_GetCommandLineW
0x18000dbce  mov     [rsp+6A8h+lpRawData], rbx
0x18000dbd3  lea     r8, aTheProcessSHit; "The process '%s' hit an exception in a "...
0x18000dbda  mov     [rsp+6A8h+lpStrings], r15
0x18000dbdf  lea     rcx, [rsp+6A8h+OutputString]; unsigned __int16 *
0x18000dbe4  mov     [rsp+6A8h+dwDataSize], edi
0x18000dbe8  mov     r9, rax
0x18000dbeb  mov     qword ptr [rsp+6A8h+wNumStrings], rsi
0x18000dbf0  mov     edx, 600h; unsigned __int64
0x18000dbf5  mov     dword ptr [rsp+6A8h+lpUserSid], ebp
0x18000dbf9  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000dbfe  lea     rdx, SourceName; "MSDTC"
0x18000dc05  xor     ecx, ecx; lpUNCServerName
0x18000dc07  call    cs:__imp_RegisterEventSourceW
0x18000dc0d  xor     edi, edi
0x18000dc0f  mov     rbx, rax
0x18000dc12  test    rax, rax
0x18000dc15  jz      short loc_18000DC4B
0x18000dc17  mov     [rsp+6A8h+lpRawData], rdi; lpRawData
0x18000dc1c  lea     ecx, [rdi+1]
0x18000dc1f  lea     rax, [rsp+6A8h+Strings]
0x18000dc24  mov     r8d, ecx; wCategory
0x18000dc27  mov     [rsp+6A8h+lpStrings], rax; lpStrings
0x18000dc2c  mov     edx, ecx; wType
0x18000dc2e  mov     [rsp+6A8h+dwDataSize], edi; dwDataSize
0x18000dc32  mov     r9d, 0C0001103h; dwEventID
0x18000dc38  mov     [rsp+6A8h+wNumStrings], cx; wNumStrings
0x18000dc3d  mov     rcx, rbx; hEventLog
0x18000dc40  mov     [rsp+6A8h+lpUserSid], rdi; lpUserSid
0x18000dc45  call    cs:__imp_ReportEventW
0x18000dc4b  lea     rcx, [rsp+6A8h+OutputString]; lpOutputString
0x18000dc50  call    cs:__imp_OutputDebugStringW
0x18000dc56  lea     rcx, aDtcdebugbreak; "DtcDebugBreak"
0x18000dc5d  call    ?GetLocalDTCProfileInt@@YAKPEBDK@Z; GetLocalDTCProfileInt(char const *,ulong)
0x18000dc62  test    eax, eax
0x18000dc64  jz      short loc_18000DC6C
0x18000dc66  call    cs:__imp_DebugBreak
0x18000dc6c  test    rbx, rbx
0x18000dc6f  jz      short loc_18000DC7A
0x18000dc71  mov     rcx, rbx; hEventLog
0x18000dc74  call    cs:__imp_DeregisterEventSource
0x18000dc7a  mov     rcx, r14; struct _EXCEPTION_POINTERS *
0x18000dc7d  call    ?DtcRaiseExceptionForWatsonCrashAnalysis@@YAXPEAU_EXCEPTION_POINTERS@@@Z; DtcRaiseExceptionForWatsonCrashAnalysis(_EXCEPTION_POINTERS *)
```
