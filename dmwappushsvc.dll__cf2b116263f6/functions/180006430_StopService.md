# StopService

- ea: `0x180006430`
- end: `0x180006505`
- name: `StopService`
- size: `213`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1800012a8`
- `0x1800049c0`
- `0x180004bec`
- `0x180006430`
- `0x18000650c`
- `0x180006770`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800064ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800064ad`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x1800064d7`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x1800064d7`
- `dmpushroutercore!UnregisterRPCInterface` at `0x180006436`
- `dmpushroutercore!UnregisterRPCInterface` at `0x180006436`

## pseudocode

```c
__int64 StopService()
{
  int v0; // eax
  __int64 v1; // rcx
  DWORD v2; // ebx
  __int64 *v3; // rdx

  v0 = UnregisterRPCInterface();
  v2 = v0;
  if ( v0 >= 0 )
  {
    if ( (Microsoft_Windows_DeviceManagement_PushrouterEnableBits & 2) != 0 )
      McTemplateU0d_EventWriteTransfer(
        v1,
        (const EVENT_DESCRIPTOR *)PushRouterSvcEngUnregisterRPCInterfaceSucceeded,
        (unsigned int)v0);
    v0 = SvcEngUninitialize(v1);
    v2 = v0;
    if ( v0 >= 0 )
    {
      if ( (Microsoft_Windows_DeviceManagement_PushrouterEnableBits & 2) == 0 )
        goto LABEL_12;
      v3 = PushRouterSvcEngUninitializeSucceeded;
    }
    else
    {
      if ( (Microsoft_Windows_DeviceManagement_PushrouterEnableBits & 1) == 0 )
        goto LABEL_12;
      v3 = PushRouterSvcEngUninitializeFailed;
    }
  }
  else
  {
    if ( (Microsoft_Windows_DeviceManagement_PushrouterEnableBits & 1) == 0 )
      goto LABEL_12;
    v3 = PushRouterSvcEngUnregisterRPCInterfaceFailed;
  }
  McTemplateU0d_EventWriteTransfer(v1, (const EVENT_DESCRIPTOR *)v3, (unsigned int)v0);
LABEL_12:
  if ( hEvent )
  {
    CloseHandle(hEvent);
    hEvent = 0;
  }
  qword_18001C8A0 = 0;
  if ( WaitHandle )
  {
    UnregisterWaitEx(WaitHandle, 0);
    WaitHandle = 0;
  }
  SvcEngUpdateServiceStatus(1, v2, 0);
  McGenEventUnregister_EventUnregister();
  return TraceLoggingUnregister_EventUnregister();
}

```

## disassembly

```asm
0x180006430  push    rbx
0x180006432  sub     rsp, 20h
0x180006436  call    cs:__imp_UnregisterRPCInterface
0x18000643c  mov     ebx, eax
0x18000643e  test    eax, eax
0x180006440  jns     short loc_180006454
0x180006442  test    cs:Microsoft_Windows_DeviceManagement_PushrouterEnableBits, 1
0x180006449  jz      short loc_1800064A1
0x18000644b  lea     rdx, PushRouterSvcEngUnregisterRPCInterfaceFailed
0x180006452  jmp     short loc_180006499
0x180006454  test    cs:Microsoft_Windows_DeviceManagement_PushrouterEnableBits, 2
0x18000645b  jz      short loc_18000646C
0x18000645d  mov     r8d, eax
0x180006460  lea     rdx, PushRouterSvcEngUnregisterRPCInterfaceSucceeded
0x180006467  call    McTemplateU0d_EventWriteTransfer
0x18000646c  call    ?SvcEngUninitialize@@YAJJ@Z; SvcEngUninitialize(long)
0x180006471  mov     ebx, eax
0x180006473  test    eax, eax
0x180006475  jns     short loc_180006489
0x180006477  test    cs:Microsoft_Windows_DeviceManagement_PushrouterEnableBits, 1
0x18000647e  jz      short loc_1800064A1
0x180006480  lea     rdx, PushRouterSvcEngUninitializeFailed
0x180006487  jmp     short loc_180006499
0x180006489  test    cs:Microsoft_Windows_DeviceManagement_PushrouterEnableBits, 2
0x180006490  jz      short loc_1800064A1
0x180006492  lea     rdx, PushRouterSvcEngUninitializeSucceeded
0x180006499  mov     r8d, eax
0x18000649c  call    McTemplateU0d_EventWriteTransfer
0x1800064a1  mov     rcx, cs:hEvent; hObject
0x1800064a8  test    rcx, rcx
0x1800064ab  jz      short loc_1800064BE
0x1800064ad  call    cs:__imp_CloseHandle
0x1800064b3  mov     cs:hEvent, 0
0x1800064be  mov     rcx, cs:WaitHandle; WaitHandle
0x1800064c5  mov     cs:qword_18001C8A0, 0
0x1800064d0  test    rcx, rcx
0x1800064d3  jz      short loc_1800064E8
0x1800064d5  xor     edx, edx; CompletionEvent
0x1800064d7  call    cs:__imp_UnregisterWaitEx
0x1800064dd  mov     cs:WaitHandle, 0
0x1800064e8  xor     r8d, r8d; unsigned int
0x1800064eb  mov     edx, ebx; unsigned int
0x1800064ed  lea     ecx, [r8+1]; unsigned int
0x1800064f1  call    ?SvcEngUpdateServiceStatus@@YAJKKK@Z; SvcEngUpdateServiceStatus(ulong,ulong,ulong)
0x1800064f6  call    McGenEventUnregister_EventUnregister
0x1800064fb  add     rsp, 20h
0x1800064ff  pop     rbx
0x180006500  jmp     TraceLoggingUnregister_EventUnregister
```
