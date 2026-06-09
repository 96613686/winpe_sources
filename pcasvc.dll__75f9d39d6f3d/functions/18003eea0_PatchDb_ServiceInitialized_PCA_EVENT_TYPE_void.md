# PatchDb_ServiceInitialized(_PCA_EVENT_TYPE,void *)

- ea: `0x18003eea0`
- end: `0x18003ef74`
- name: `?PatchDb_ServiceInitialized@@YAKW4_PCA_EVENT_TYPE@@PEAX@Z`
- size: `212`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, installer_update`

## callees

- `0x180012920`
- `0x18003eea0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003eeb4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003eeb4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003eec4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ef14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003eec4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ef14`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18003ef09`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18003ef09`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18003ef61`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18003ef61`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003ef41`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003ef41`

## string_xrefs

- `0x18003eeca`: `Failed to create wait event [%d]`
- `0x18003ef1a`: `Failed to create the worker thread [%d]`
- `0x18003eed7`: `PatchDb_ServiceInitialized`
- `0x18003ef27`: `PatchDb_ServiceInitialized`

## pseudocode

```c
__int64 PatchDb_ServiceInitialized()
{
  DWORD LastError; // ebx
  HANDLE EventW; // rdi
  HANDLE Thread; // rax

  LastError = 0;
  EventW = CreateEventW(0, 0, 0, 0);
  if ( EventW )
  {
    Thread = CreateThread(0, 0, PatchDb_WorkerThread, 0, 4u, 0);
    if ( Thread )
    {
      g_PatchDbState |= 1u;
      g_PatchDbWaitEvent = EventW;
      g_PatchDbWorkerThread = Thread;
      ResumeThread(Thread);
    }
    else
    {
      LastError = GetLastError();
      AslLogCallPrintf(
        1,
        (unsigned int)"PatchDb_ServiceInitialized",
        173,
        (unsigned int)"Failed to create the worker thread [%d]");
      CloseHandle(EventW);
    }
  }
  else
  {
    LastError = GetLastError();
    AslLogCallPrintf(
      1,
      (unsigned int)"PatchDb_ServiceInitialized",
      160,
      (unsigned int)"Failed to create wait event [%d]");
  }
  return LastError;
}

```

## disassembly

```asm
0x18003eea0  mov     [rsp+arg_0], rbx
0x18003eea5  push    rdi
0x18003eea6  sub     rsp, 30h
0x18003eeaa  xor     r9d, r9d; lpName
0x18003eead  xor     r8d, r8d; bInitialState
0x18003eeb0  xor     edx, edx; bManualReset
0x18003eeb2  xor     ecx, ecx; lpEventAttributes
0x18003eeb4  call    cs:__imp_CreateEventW
0x18003eeba  xor     ebx, ebx
0x18003eebc  mov     rdi, rax
0x18003eebf  test    rax, rax
0x18003eec2  jnz     short loc_18003EEEE
0x18003eec4  call    cs:__imp_GetLastError
0x18003eeca  lea     r9, aFailedToCreate_43; "Failed to create wait event [%d]"
0x18003eed1  mov     r8d, 0A0h
0x18003eed7  lea     rdx, aPatchdbService; "PatchDb_ServiceInitialized"
0x18003eede  mov     [rsp+38h+dwCreationFlags], eax
0x18003eee2  lea     ecx, [rdi+1]
0x18003eee5  mov     ebx, eax
0x18003eee7  call    AslLogCallPrintf
0x18003eeec  jmp     short loc_18003EF67
0x18003eeee  mov     [rsp+38h+lpThreadId], rbx; lpThreadId
0x18003eef3  lea     r8, ?PatchDb_WorkerThread@@YAKPEAX@Z; lpStartAddress
0x18003eefa  xor     r9d, r9d; lpParameter
0x18003eefd  mov     [rsp+38h+dwCreationFlags], 4; dwCreationFlags
0x18003ef05  xor     edx, edx; dwStackSize
0x18003ef07  xor     ecx, ecx; lpThreadAttributes
0x18003ef09  call    cs:__imp_CreateThread
0x18003ef0f  test    rax, rax
0x18003ef12  jnz     short loc_18003EF49
0x18003ef14  call    cs:__imp_GetLastError
0x18003ef1a  lea     r9, aFailedToCreate_99; "Failed to create the worker thread [%d]"
0x18003ef21  mov     r8d, 0ADh
0x18003ef27  lea     rdx, aPatchdbService; "PatchDb_ServiceInitialized"
0x18003ef2e  mov     [rsp+38h+dwCreationFlags], eax
0x18003ef32  mov     ecx, 1
0x18003ef37  mov     ebx, eax
0x18003ef39  call    AslLogCallPrintf
0x18003ef3e  mov     rcx, rdi; hObject
0x18003ef41  call    cs:__imp_CloseHandle
0x18003ef47  jmp     short loc_18003EF67
0x18003ef49  or      cs:?g_PatchDbState@@3KA, 1; ulong g_PatchDbState
0x18003ef50  mov     rcx, rax; hThread
0x18003ef53  mov     cs:?g_PatchDbWaitEvent@@3PEAXEA, rdi; void * g_PatchDbWaitEvent
0x18003ef5a  mov     cs:?g_PatchDbWorkerThread@@3PEAXEA, rax; void * g_PatchDbWorkerThread
0x18003ef61  call    cs:__imp_ResumeThread
0x18003ef67  mov     eax, ebx
0x18003ef69  mov     rbx, [rsp+38h+arg_0]
0x18003ef6e  add     rsp, 30h
0x18003ef72  pop     rdi
0x18003ef73  retn
```
