# RWWaitForSingleObjectWithoutTimeout

- ea: `0x18014a5f4`
- end: `0x18014a6d0`
- name: `RWWaitForSingleObjectWithoutTimeout`
- size: `220`
- prototype: `unsigned int __fastcall(void *handle, CRWLock *pLock)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002dc8c`
- `0x18002deac`

## callees

- `0x18008db2c`
- `0x18014a5f4`
- `0x18014d5b0`

## import_xrefs

- `ntdll!DbgPrint` at `0x18014a646`
- `ntdll!DbgPrint` at `0x18014a646`
- `ntdll!RtlDllShutdownInProgress` at `0x18014a64c`
- `ntdll!RtlDllShutdownInProgress` at `0x18014a6b5`
- `ntdll!RtlDllShutdownInProgress` at `0x18014a64c`
- `ntdll!RtlDllShutdownInProgress` at `0x18014a6b5`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18014a656`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18014a6bf`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18014a656`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18014a6bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014a67f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014a67f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18014a62d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18014a62d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18014a625`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18014a625`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18014a60c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18014a60c`

## string_xrefs

- `0x18014a63c`: `%#x:%#x> Timed out trying to acquire reader-writer lock %p, WriterID = %#x. If non-zero, switch to the WriterID thread and examine why it is blocked.\n`
- `0x18014a6a4`: `onecore\com\combase\rwlock\rwlock.cxx`

## pseudocode

```c
__int64 __fastcall RWWaitForSingleObjectWithoutTimeout(void *handle, CRWLock *pLock)
{
  DWORD v4; // eax
  unsigned int v5; // ebx
  volatile unsigned int dwWriterID; // ebx
  DWORD CurrentThreadId; // edi
  DWORD CurrentProcessId; // eax
  DWORD LastError; // eax

  while ( 1 )
  {
    v4 = WaitForSingleObjectEx(handle, 0xFFFFFFFF, 0);
    v5 = v4;
    if ( v4 != 192 )
      break;
LABEL_4:
    if ( !RtlDllShutdownInProgress() )
      IsDebuggerPresent();
  }
  if ( v4 == 258 )
  {
    dwWriterID = pLock->_dwWriterID;
    CurrentThreadId = GetCurrentThreadId();
    CurrentProcessId = GetCurrentProcessId();
    DbgPrint(
      "%#x:%#x> Timed out trying to acquire reader-writer lock %p, WriterID = %#x. If non-zero, switch to the WriterID th"
      "read and examine why it is blocked.\n",
      CurrentProcessId,
      CurrentThreadId,
      pLock,
      dwWriterID);
    goto LABEL_4;
  }
  if ( v4 )
  {
    if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
    {
      LastError = GetLastError();
      ComTraceMessageT<unsigned long,unsigned long>(
        "onecore\\com\\combase\\rwlock\\rwlock.cxx",
        "RWWaitForSingleObjectWithoutTimeout",
        382,
        ERRORS,
        L"%d %d",
        v5,
        LastError);
    }
    if ( !RtlDllShutdownInProgress() )
      IsDebuggerPresent();
  }
  return v5;
}

```

## disassembly

```asm
0x18014a5f4  push    rbx
0x18014a5f6  push    rbp
0x18014a5f7  push    rsi
0x18014a5f8  push    rdi
0x18014a5f9  sub     rsp, 48h
0x18014a5fd  mov     rbp, pLock
0x18014a600  mov     rsi, handle
0x18014a603  xor     r8d, r8d; bAlertable
0x18014a606  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18014a609  mov     handle, rsi; hHandle
0x18014a60c  call    cs:__imp_WaitForSingleObjectEx
0x18014a612  mov     ebx, eax
0x18014a614  cmp     eax, 0C0h
0x18014a619  jz      short loc_18014A64C
0x18014a61b  cmp     eax, 102h
0x18014a620  jnz     short loc_18014A65E
0x18014a622  mov     ebx, [rbp+0Ch]
0x18014a625  call    cs:__imp_GetCurrentThreadId
0x18014a62b  mov     edi, eax
0x18014a62d  call    cs:__imp_GetCurrentProcessId
0x18014a633  mov     r9, rbp
0x18014a636  mov     dword ptr [rsp+68h+format], ebx
0x18014a63a  mov     edx, eax
0x18014a63c  lea     handle, aXXTimedOutTryi; "%#x:%#x> Timed out trying to acquire re"...
0x18014a643  mov     r8d, edi
0x18014a646  call    cs:__imp_DbgPrint
0x18014a64c  call    cs:__imp_RtlDllShutdownInProgress
0x18014a652  test    al, al
0x18014a654  jnz     short loc_18014A603
0x18014a656  call    cs:__imp_IsDebuggerPresent
0x18014a65c  jmp     short loc_18014A603
0x18014a65e  test    ebx, ebx
0x18014a660  jz      short loc_18014A6C5
0x18014a662  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x18014a668  test    eax, eax
0x18014a66a  jnz     short loc_18014A67F
0x18014a66c  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x18014a672  jz      short loc_18014A6B5
0x18014a674  xor     ecx, ecx; level
0x18014a676  call    IsWppLevelEnabled
0x18014a67b  test    al, al
0x18014a67d  jz      short loc_18014A6B5
0x18014a67f  call    cs:__imp_GetLastError
0x18014a685  mov     [rsp+68h+var_38], eax; <args_1>
0x18014a689  xor     r9d, r9d; level
0x18014a68c  mov     [rsp+68h+var_40], ebx; <args_0>
0x18014a690  lea     pLock, aRwwaitforsingl; "RWWaitForSingleObjectWithoutTimeout"
0x18014a697  lea     rax, aDD; "%d %d"
0x18014a69e  mov     r8d, 17Eh; line
0x18014a6a4  lea     handle, aOnecoreComComb_13; "onecore\\com\\combase\\rwlock\\rwlock.c"...
0x18014a6ab  mov     [rsp+68h+format], rax; format
0x18014a6b0  call    ??$ComTraceMessageT@KK@@YAXPEBD0HW4TraceLevel@@PEBGKK@Z; ComTraceMessageT<ulong,ulong>(char const *,char const *,int,TraceLevel,ushort const *,ulong,ulong)
0x18014a6b5  call    cs:__imp_RtlDllShutdownInProgress
0x18014a6bb  test    al, al
0x18014a6bd  jnz     short loc_18014A6C5
0x18014a6bf  call    cs:__imp_IsDebuggerPresent
0x18014a6c5  mov     eax, ebx
0x18014a6c7  add     rsp, 48h
0x18014a6cb  pop     rdi
0x18014a6cc  pop     rsi
0x18014a6cd  pop     rbp
0x18014a6ce  pop     rbx
0x18014a6cf  retn
```
