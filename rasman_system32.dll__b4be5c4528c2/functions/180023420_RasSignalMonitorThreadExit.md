# RasSignalMonitorThreadExit

- ea: `0x180023420`
- end: `0x180023482`
- name: `RasSignalMonitorThreadExit`
- size: `98`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180023420`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180023448`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180023448`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002345b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002345b`

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
0x180023420  sub     rsp, 28h
0x180023424  mov     rcx, cs:g_hRasmanServiceMonitorThread
0x18002342b  test    rcx, rcx
0x18002342e  jz      short loc_180023467
0x180023430  cmp     cs:g_fRasmanMonitorThread, 0
0x180023437  jz      short loc_180023467
0x180023439  mov     rax, cs:g_hEventServiceMonitorTerminate
0x180023440  test    rax, rax
0x180023443  jz      short loc_18002345B
0x180023445  mov     rcx, rax; hEvent
0x180023448  call    cs:__imp_SetEvent
0x18002344f  nop     dword ptr [rax+rax+00h]
0x180023454  mov     rcx, cs:g_hRasmanServiceMonitorThread; hObject
0x18002345b  call    cs:__imp_CloseHandle
0x180023462  nop     dword ptr [rax+rax+00h]
0x180023467  mov     cs:g_fRasmanMonitorThread, 0
0x180023471  mov     cs:g_hRasmanServiceMonitorThread, 0
0x18002347c  add     rsp, 28h
0x180023480  retn
```
