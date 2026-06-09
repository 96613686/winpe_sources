# RasSignalMonitorThreadExit

- ea: `0x180022890`
- end: `0x1800228e5`
- name: `RasSignalMonitorThreadExit`
- size: `85`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180022890`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800228b8`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800228b8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800228c5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800228c5`

## pseudocode

```c
BOOL RasSignalMonitorThreadExit()
{
  HANDLE v0; // rcx
  BOOL result; // eax

  v0 = g_hRasmanServiceMonitorThread;
  if ( g_hRasmanServiceMonitorThread && g_fRasmanMonitorThread )
  {
    if ( g_hEventServiceMonitorTerminate )
    {
      SetEvent(g_hEventServiceMonitorTerminate);
      v0 = g_hRasmanServiceMonitorThread;
    }
    result = CloseHandle(v0);
  }
  g_fRasmanMonitorThread = 0;
  g_hRasmanServiceMonitorThread = 0;
  return result;
}

```

## disassembly

```asm
0x180022890  sub     rsp, 28h
0x180022894  mov     rcx, cs:g_hRasmanServiceMonitorThread
0x18002289b  test    rcx, rcx
0x18002289e  jz      short loc_1800228CB
0x1800228a0  cmp     cs:g_fRasmanMonitorThread, 0
0x1800228a7  jz      short loc_1800228CB
0x1800228a9  mov     rax, cs:g_hEventServiceMonitorTerminate
0x1800228b0  test    rax, rax
0x1800228b3  jz      short loc_1800228C5
0x1800228b5  mov     rcx, rax; hEvent
0x1800228b8  call    cs:__imp_SetEvent
0x1800228be  mov     rcx, cs:g_hRasmanServiceMonitorThread; hObject
0x1800228c5  call    cs:__imp_CloseHandle
0x1800228cb  mov     cs:g_fRasmanMonitorThread, 0
0x1800228d5  mov     cs:g_hRasmanServiceMonitorThread, 0
0x1800228e0  add     rsp, 28h
0x1800228e4  retn
```
