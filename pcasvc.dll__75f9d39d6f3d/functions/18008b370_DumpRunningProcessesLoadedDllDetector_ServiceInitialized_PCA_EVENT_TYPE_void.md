# DumpRunningProcessesLoadedDllDetector_ServiceInitialized(_PCA_EVENT_TYPE,void *)

- ea: `0x18008b370`
- end: `0x18008b444`
- name: `?DumpRunningProcessesLoadedDllDetector_ServiceInitialized@@YAKW4_PCA_EVENT_TYPE@@PEAX@Z`
- size: `212`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180012920`
- `0x18008b370`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18008b384`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18008b384`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b394`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b3e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b394`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b3e4`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18008b3d9`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18008b3d9`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18008b431`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18008b431`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008b411`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008b411`

## string_xrefs

- `0x18008b39a`: `Failed to create wait event [%d]`
- `0x18008b3ea`: `Failed to create the worker thread [%d]`
- `0x18008b3a7`: `DumpRunningProcessesLoadedDllDetector_ServiceInitialized`
- `0x18008b3f7`: `DumpRunningProcessesLoadedDllDetector_ServiceInitialized`

## pseudocode

```c
__int64 DumpRunningProcessesLoadedDllDetector_ServiceInitialized()
{
  DWORD LastError; // ebx
  HANDLE EventW; // rdi
  HANDLE Thread; // rax

  LastError = 0;
  EventW = CreateEventW(0, 0, 0, 0);
  if ( EventW )
  {
    Thread = CreateThread(0, 0, DumpRunningProcessesLoadedDllDetector_WorkerThread, 0, 4u, 0);
    if ( Thread )
    {
      g_DllDetectorState |= 1u;
      g_DllDetectorWaitEvent = EventW;
      g_DllDetectorWorkerThread = Thread;
      ResumeThread(Thread);
    }
    else
    {
      LastError = GetLastError();
      AslLogCallPrintf(
        1,
        (unsigned int)"DumpRunningProcessesLoadedDllDetector_ServiceInitialized",
        2338,
        (unsigned int)"Failed to create the worker thread [%d]");
      CloseHandle(EventW);
    }
  }
  else
  {
    LastError = GetLastError();
    AslLogCallPrintf(
      1,
      (unsigned int)"DumpRunningProcessesLoadedDllDetector_ServiceInitialized",
      2325,
      (unsigned int)"Failed to create wait event [%d]");
  }
  return LastError;
}

```

## disassembly

```asm
0x18008b370  mov     [rsp+arg_0], rbx
0x18008b375  push    rdi
0x18008b376  sub     rsp, 30h
0x18008b37a  xor     r9d, r9d; lpName
0x18008b37d  xor     r8d, r8d; bInitialState
0x18008b380  xor     edx, edx; bManualReset
0x18008b382  xor     ecx, ecx; lpEventAttributes
0x18008b384  call    cs:__imp_CreateEventW
0x18008b38a  xor     ebx, ebx
0x18008b38c  mov     rdi, rax
0x18008b38f  test    rax, rax
0x18008b392  jnz     short loc_18008B3BE
0x18008b394  call    cs:__imp_GetLastError
0x18008b39a  lea     r9, aFailedToCreate_43; "Failed to create wait event [%d]"
0x18008b3a1  mov     r8d, 915h
0x18008b3a7  lea     rdx, aDumprunningpro_5; "DumpRunningProcessesLoadedDllDetector_S"...
0x18008b3ae  mov     [rsp+38h+dwCreationFlags], eax
0x18008b3b2  lea     ecx, [rdi+1]
0x18008b3b5  mov     ebx, eax
0x18008b3b7  call    AslLogCallPrintf
0x18008b3bc  jmp     short loc_18008B437
0x18008b3be  mov     [rsp+38h+lpThreadId], rbx; lpThreadId
0x18008b3c3  lea     r8, ?DumpRunningProcessesLoadedDllDetector_WorkerThread@@YAKPEAX@Z; lpStartAddress
0x18008b3ca  xor     r9d, r9d; lpParameter
0x18008b3cd  mov     [rsp+38h+dwCreationFlags], 4; dwCreationFlags
0x18008b3d5  xor     edx, edx; dwStackSize
0x18008b3d7  xor     ecx, ecx; lpThreadAttributes
0x18008b3d9  call    cs:__imp_CreateThread
0x18008b3df  test    rax, rax
0x18008b3e2  jnz     short loc_18008B419
0x18008b3e4  call    cs:__imp_GetLastError
0x18008b3ea  lea     r9, aFailedToCreate_99; "Failed to create the worker thread [%d]"
0x18008b3f1  mov     r8d, 922h
0x18008b3f7  lea     rdx, aDumprunningpro_5; "DumpRunningProcessesLoadedDllDetector_S"...
0x18008b3fe  mov     [rsp+38h+dwCreationFlags], eax
0x18008b402  mov     ecx, 1
0x18008b407  mov     ebx, eax
0x18008b409  call    AslLogCallPrintf
0x18008b40e  mov     rcx, rdi; hObject
0x18008b411  call    cs:__imp_CloseHandle
0x18008b417  jmp     short loc_18008B437
0x18008b419  or      cs:?g_DllDetectorState@@3KA, 1; ulong g_DllDetectorState
0x18008b420  mov     rcx, rax; hThread
0x18008b423  mov     cs:?g_DllDetectorWaitEvent@@3PEAXEA, rdi; void * g_DllDetectorWaitEvent
0x18008b42a  mov     cs:?g_DllDetectorWorkerThread@@3PEAXEA, rax; void * g_DllDetectorWorkerThread
0x18008b431  call    cs:__imp_ResumeThread
0x18008b437  mov     eax, ebx
0x18008b439  mov     rbx, [rsp+38h+arg_0]
0x18008b43e  add     rsp, 30h
0x18008b442  pop     rdi
0x18008b443  retn
```
