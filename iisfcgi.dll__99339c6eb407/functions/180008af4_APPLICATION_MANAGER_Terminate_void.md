# APPLICATION_MANAGER::Terminate(void)

- ea: `0x180008af4`
- end: `0x180008be0`
- name: `?Terminate@APPLICATION_MANAGER@@SAJXZ`
- size: `236`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000b180`

## callees

- `0x1800023c0`
- `0x180008af4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180008b72`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180008b72`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008b23`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008b7f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008b98`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008b23`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008b7f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008b98`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x180008b53`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x180008b53`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180008bc5`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180008bc5`

## pseudocode

```c
__int64 APPLICATION_MANAGER::Terminate(void)
{
  HANDLE v0; // rcx

  if ( APPLICATION_MANAGER::sm_fTransportInitialized )
    TRANSPORT::StaticTerminate();
  APPLICATION_MANAGER::sm_fTransportInitialized = 0;
  if ( APPLICATION_MANAGER::sm_fApplicationInitialized && APPLICATION::sm_hJobObject )
  {
    CloseHandle(APPLICATION::sm_hJobObject);
    APPLICATION::sm_hJobObject = 0;
  }
  APPLICATION_MANAGER::sm_fApplicationInitialized = 0;
  if ( APPLICATION_MANAGER::sm_fFileListenerInitialized )
  {
    v0 = FILE_LISTENER::sm_hCompletionPort;
    if ( FILE_LISTENER::sm_hCompletionPort )
    {
      PostQueuedCompletionStatus(FILE_LISTENER::sm_hCompletionPort, 0, 0xFFFFFFFFFFFFFFFFuLL, 0);
      v0 = FILE_LISTENER::sm_hCompletionPort;
    }
    if ( FILE_LISTENER::sm_hListenerThread )
    {
      WaitForSingleObject(FILE_LISTENER::sm_hListenerThread, 0xFFFFFFFF);
      CloseHandle(FILE_LISTENER::sm_hListenerThread);
      v0 = FILE_LISTENER::sm_hCompletionPort;
      FILE_LISTENER::sm_hListenerThread = 0;
    }
    if ( v0 )
    {
      CloseHandle(v0);
      FILE_LISTENER::sm_hCompletionPort = 0;
    }
  }
  APPLICATION_MANAGER::sm_fFileListenerInitialized = 0;
  if ( APPLICATION_MANAGER::sm_fSystemUsageTimerInitialized && APPLICATION_MANAGER::sm_hSystemUsageTimer )
  {
    DeleteTimerQueueTimer(0, APPLICATION_MANAGER::sm_hSystemUsageTimer, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
    APPLICATION_MANAGER::sm_hSystemUsageTimer = 0;
  }
  APPLICATION_MANAGER::sm_fSystemUsageTimerInitialized = 0;
  return 0;
}

```

## disassembly

```asm
0x180008af4  push    rbx
0x180008af6  sub     rsp, 20h
0x180008afa  xor     ebx, ebx
0x180008afc  cmp     cs:?sm_fTransportInitialized@APPLICATION_MANAGER@@0HA, ebx; int APPLICATION_MANAGER::sm_fTransportInitialized
0x180008b02  jz      short loc_180008B09
0x180008b04  call    ?StaticTerminate@TRANSPORT@@SAJXZ; TRANSPORT::StaticTerminate(void)
0x180008b09  cmp     cs:?sm_fApplicationInitialized@APPLICATION_MANAGER@@0HA, ebx; int APPLICATION_MANAGER::sm_fApplicationInitialized
0x180008b0f  mov     cs:?sm_fTransportInitialized@APPLICATION_MANAGER@@0HA, ebx; int APPLICATION_MANAGER::sm_fTransportInitialized
0x180008b15  jz      short loc_180008B30
0x180008b17  mov     rcx, cs:?sm_hJobObject@APPLICATION@@0PEAXEA; hObject
0x180008b1e  test    rcx, rcx
0x180008b21  jz      short loc_180008B30
0x180008b23  call    cs:__imp_CloseHandle
0x180008b29  mov     cs:?sm_hJobObject@APPLICATION@@0PEAXEA, rbx; void * APPLICATION::sm_hJobObject
0x180008b30  cmp     cs:?sm_fFileListenerInitialized@APPLICATION_MANAGER@@0HA, ebx; int APPLICATION_MANAGER::sm_fFileListenerInitialized
0x180008b36  mov     cs:?sm_fApplicationInitialized@APPLICATION_MANAGER@@0HA, ebx; int APPLICATION_MANAGER::sm_fApplicationInitialized
0x180008b3c  jz      short loc_180008BA5
0x180008b3e  mov     rcx, cs:?sm_hCompletionPort@FILE_LISTENER@@0PEAXEA; CompletionPort
0x180008b45  test    rcx, rcx
0x180008b48  jz      short loc_180008B60
0x180008b4a  xor     r9d, r9d; lpOverlapped
0x180008b4d  or      r8, 0FFFFFFFFFFFFFFFFh; dwCompletionKey
0x180008b51  xor     edx, edx; dwNumberOfBytesTransferred
0x180008b53  call    cs:__imp_PostQueuedCompletionStatus
0x180008b59  mov     rcx, cs:?sm_hCompletionPort@FILE_LISTENER@@0PEAXEA; void * FILE_LISTENER::sm_hCompletionPort
0x180008b60  mov     rax, cs:?sm_hListenerThread@FILE_LISTENER@@0PEAXEA; void * FILE_LISTENER::sm_hListenerThread
0x180008b67  test    rax, rax
0x180008b6a  jz      short loc_180008B93
0x180008b6c  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180008b6f  mov     rcx, rax; hHandle
0x180008b72  call    cs:__imp_WaitForSingleObject
0x180008b78  mov     rcx, cs:?sm_hListenerThread@FILE_LISTENER@@0PEAXEA; hObject
0x180008b7f  call    cs:__imp_CloseHandle
0x180008b85  mov     rcx, cs:?sm_hCompletionPort@FILE_LISTENER@@0PEAXEA; hObject
0x180008b8c  mov     cs:?sm_hListenerThread@FILE_LISTENER@@0PEAXEA, rbx; void * FILE_LISTENER::sm_hListenerThread
0x180008b93  test    rcx, rcx
0x180008b96  jz      short loc_180008BA5
0x180008b98  call    cs:__imp_CloseHandle
0x180008b9e  mov     cs:?sm_hCompletionPort@FILE_LISTENER@@0PEAXEA, rbx; void * FILE_LISTENER::sm_hCompletionPort
0x180008ba5  cmp     cs:?sm_fSystemUsageTimerInitialized@APPLICATION_MANAGER@@0HA, ebx; int APPLICATION_MANAGER::sm_fSystemUsageTimerInitialized
0x180008bab  mov     cs:?sm_fFileListenerInitialized@APPLICATION_MANAGER@@0HA, ebx; int APPLICATION_MANAGER::sm_fFileListenerInitialized
0x180008bb1  jz      short loc_180008BD2
0x180008bb3  mov     rdx, cs:?sm_hSystemUsageTimer@APPLICATION_MANAGER@@0PEAXEA; Timer
0x180008bba  test    rdx, rdx
0x180008bbd  jz      short loc_180008BD2
0x180008bbf  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180008bc3  xor     ecx, ecx; TimerQueue
0x180008bc5  call    cs:__imp_DeleteTimerQueueTimer
0x180008bcb  mov     cs:?sm_hSystemUsageTimer@APPLICATION_MANAGER@@0PEAXEA, rbx; void * APPLICATION_MANAGER::sm_hSystemUsageTimer
0x180008bd2  mov     cs:?sm_fSystemUsageTimerInitialized@APPLICATION_MANAGER@@0HA, ebx; int APPLICATION_MANAGER::sm_fSystemUsageTimerInitialized
0x180008bd8  xor     eax, eax
0x180008bda  add     rsp, 20h
0x180008bde  pop     rbx
0x180008bdf  retn
```
