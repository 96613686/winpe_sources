# FILE_LISTENER::StaticInitialize(void)

- ea: `0x180004700`
- end: `0x1800047e3`
- name: `?StaticInitialize@FILE_LISTENER@@SAJXZ`
- size: `227`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180007e1c`

## callees

- `0x180004700`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000476f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000476f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004794`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800047b1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004794`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800047b1`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x18000472c`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x18000472c`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000475d`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000475d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180004706`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180004706`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x180004716`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x180004716`

## pseudocode

```c
__int64 FILE_LISTENER::StaticInitialize(void)
{
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  signed int v2; // ebx

  CurrentProcess = GetCurrentProcess();
  if ( IsWow64Process(CurrentProcess, &FILE_LISTENER::sm_fIsWow64)
    && (FILE_LISTENER::sm_hCompletionPort = CreateIoCompletionPort((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 0, 0)) != 0
    && (FILE_LISTENER::sm_hListenerThread = CreateThread(
                                              0,
                                              0,
                                              (LPTHREAD_START_ROUTINE)FILE_LISTENER::ChangeNotificationThread,
                                              0,
                                              0,
                                              0)) != 0 )
  {
    v2 = 0;
    qword_180017F80 = (__int64)&FILE_LISTENER::sm_UncListenersList;
    FILE_LISTENER::sm_UncListenersList.Flink = &FILE_LISTENER::sm_UncListenersList;
  }
  else
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      v2 = (unsigned __int16)LastError | 0x80070000;
    if ( v2 < 0 )
    {
      if ( FILE_LISTENER::sm_hCompletionPort )
      {
        CloseHandle(FILE_LISTENER::sm_hCompletionPort);
        FILE_LISTENER::sm_hCompletionPort = 0;
      }
      if ( FILE_LISTENER::sm_hListenerThread )
      {
        CloseHandle(FILE_LISTENER::sm_hListenerThread);
        FILE_LISTENER::sm_hListenerThread = 0;
      }
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180004700  push    rbx
0x180004702  sub     rsp, 30h
0x180004706  call    cs:__imp_GetCurrentProcess
0x18000470c  mov     rcx, rax; hProcess
0x18000470f  lea     rdx, ?sm_fIsWow64@FILE_LISTENER@@0HA; Wow64Process
0x180004716  call    cs:__imp_IsWow64Process
0x18000471c  test    eax, eax
0x18000471e  jz      short loc_18000476F
0x180004720  xor     r9d, r9d; NumberOfConcurrentThreads
0x180004723  xor     r8d, r8d; CompletionKey
0x180004726  xor     edx, edx; ExistingCompletionPort
0x180004728  or      rcx, 0FFFFFFFFFFFFFFFFh; FileHandle
0x18000472c  call    cs:__imp_CreateIoCompletionPort
0x180004732  mov     cs:?sm_hCompletionPort@FILE_LISTENER@@0PEAXEA, rax; void * FILE_LISTENER::sm_hCompletionPort
0x180004739  test    rax, rax
0x18000473c  jz      short loc_18000476F
0x18000473e  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x180004747  lea     r8, ?ChangeNotificationThread@FILE_LISTENER@@CAKPEAX@Z; lpStartAddress
0x18000474e  xor     r9d, r9d; lpParameter
0x180004751  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x180004759  xor     edx, edx; dwStackSize
0x18000475b  xor     ecx, ecx; lpThreadAttributes
0x18000475d  call    cs:__imp_CreateThread
0x180004763  mov     cs:?sm_hListenerThread@FILE_LISTENER@@0PEAXEA, rax; void * FILE_LISTENER::sm_hListenerThread
0x18000476a  test    rax, rax
0x18000476d  jnz     short loc_1800047C4
0x18000476f  call    cs:__imp_GetLastError
0x180004775  mov     ebx, eax
0x180004777  test    eax, eax
0x180004779  jle     short loc_180004784
0x18000477b  movzx   ebx, ax
0x18000477e  or      ebx, 80070000h
0x180004784  test    ebx, ebx
0x180004786  jns     short loc_1800047DB
0x180004788  mov     rcx, cs:?sm_hCompletionPort@FILE_LISTENER@@0PEAXEA; hObject
0x18000478f  test    rcx, rcx
0x180004792  jz      short loc_1800047A5
0x180004794  call    cs:__imp_CloseHandle
0x18000479a  mov     cs:?sm_hCompletionPort@FILE_LISTENER@@0PEAXEA, 0; void * FILE_LISTENER::sm_hCompletionPort
0x1800047a5  mov     rcx, cs:?sm_hListenerThread@FILE_LISTENER@@0PEAXEA; hObject
0x1800047ac  test    rcx, rcx
0x1800047af  jz      short loc_1800047DB
0x1800047b1  call    cs:__imp_CloseHandle
0x1800047b7  mov     cs:?sm_hListenerThread@FILE_LISTENER@@0PEAXEA, 0; void * FILE_LISTENER::sm_hListenerThread
0x1800047c2  jmp     short loc_1800047DB
0x1800047c4  lea     rax, ?sm_UncListenersList@FILE_LISTENER@@0U_LIST_ENTRY@@A; _LIST_ENTRY FILE_LISTENER::sm_UncListenersList
0x1800047cb  xor     ebx, ebx
0x1800047cd  mov     cs:qword_180017F80, rax
0x1800047d4  mov     cs:?sm_UncListenersList@FILE_LISTENER@@0U_LIST_ENTRY@@A, rax; _LIST_ENTRY FILE_LISTENER::sm_UncListenersList
0x1800047db  mov     eax, ebx
0x1800047dd  add     rsp, 30h
0x1800047e1  pop     rbx
0x1800047e2  retn
```
