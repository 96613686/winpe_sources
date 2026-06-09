# StopService

- ea: `0x180008a60`
- end: `0x180008ad6`
- name: `StopService`
- size: `118`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update`

## callees

- `0x180008600`
- `0x180008a60`
- `0x180008af0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008aa9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008aa9`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180008a8c`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180008a8c`

## pseudocode

```c
__int64 StopService()
{
  UpdateServiceStatus(3, 1066, 3000);
  ShutdownWinreg();
  if ( g_hRegisteredWait )
  {
    UnregisterWaitEx(g_hRegisteredWait, 0);
    g_hRegisteredWait = 0;
  }
  if ( g_hEventTerminated )
  {
    CloseHandle(g_hEventTerminated);
    g_hEventTerminated = 0;
  }
  g_svcsGlobalData = 0;
  return UpdateServiceStatus(1, 0, 0);
}

```

## disassembly

```asm
0x180008a60  sub     rsp, 28h
0x180008a64  mov     edx, 42Ah
0x180008a69  mov     r8d, 0BB8h
0x180008a6f  mov     ecx, 3
0x180008a74  call    UpdateServiceStatus
0x180008a79  call    ShutdownWinreg
0x180008a7e  mov     rcx, cs:g_hRegisteredWait; WaitHandle
0x180008a85  test    rcx, rcx
0x180008a88  jz      short loc_180008A9D
0x180008a8a  xor     edx, edx; CompletionEvent
0x180008a8c  call    cs:__imp_UnregisterWaitEx
0x180008a92  mov     cs:g_hRegisteredWait, 0
0x180008a9d  mov     rcx, cs:g_hEventTerminated; hObject
0x180008aa4  test    rcx, rcx
0x180008aa7  jz      short loc_180008ABA
0x180008aa9  call    cs:__imp_CloseHandle
0x180008aaf  mov     cs:g_hEventTerminated, 0
0x180008aba  xor     edx, edx
0x180008abc  mov     cs:g_svcsGlobalData, 0
0x180008ac7  xor     r8d, r8d
0x180008aca  lea     ecx, [rdx+1]
0x180008acd  add     rsp, 28h
0x180008ad1  jmp     UpdateServiceStatus
```
