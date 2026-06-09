# StopService

- ea: `0x180008f30`
- end: `0x180008fe1`
- name: `StopService`
- size: `177`
- prototype: `ULONG()`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, installer_update`

## callees

- `0x180008f30`
- `0x18000947c`
- `0x18000993c`
- `0x18000a820`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008f49`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008f49`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180008fb3`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180008fb3`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180008fda`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180008f73`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180008f73`

## pseudocode

```c
ULONG StopService()
{
  DWORD v0; // ebx
  REGHANDLE v1; // rcx
  REGHANDLE v2; // rcx

  v0 = UninitializeService();
  if ( hEvent )
  {
    CloseHandle(hEvent);
    hEvent = 0;
  }
  qword_18001B6F0 = 0;
  if ( WaitHandle )
  {
    UnregisterWaitEx(WaitHandle, 0);
    WaitHandle = 0;
  }
  SvcEngUpdateServiceStatus(1, v0, 0);
  McGenEventUnregister_EventUnregister();
  v1 = RegHandle;
  dword_18001B028 = 0;
  RegHandle = 0;
  EventUnregister(v1);
  v2 = qword_18001B080;
  dword_18001B060 = 0;
  qword_18001B080 = 0;
  return EventUnregister(v2);
}

```

## disassembly

```asm
0x180008f30  push    rbx
0x180008f32  sub     rsp, 20h
0x180008f36  call    ?UninitializeService@@YAJJ@Z; UninitializeService(long)
0x180008f3b  mov     rcx, cs:hEvent; hObject
0x180008f42  mov     ebx, eax
0x180008f44  test    rcx, rcx
0x180008f47  jz      short loc_180008F5A
0x180008f49  call    cs:__imp_CloseHandle
0x180008f4f  mov     cs:hEvent, 0
0x180008f5a  mov     rcx, cs:WaitHandle; WaitHandle
0x180008f61  mov     cs:qword_18001B6F0, 0
0x180008f6c  test    rcx, rcx
0x180008f6f  jz      short loc_180008F84
0x180008f71  xor     edx, edx; CompletionEvent
0x180008f73  call    cs:__imp_UnregisterWaitEx
0x180008f79  mov     cs:WaitHandle, 0
0x180008f84  xor     r8d, r8d; unsigned int
0x180008f87  mov     edx, ebx; unsigned int
0x180008f89  lea     ecx, [r8+1]; unsigned int
0x180008f8d  call    ?SvcEngUpdateServiceStatus@@YAJKKK@Z; SvcEngUpdateServiceStatus(ulong,ulong,ulong)
0x180008f92  call    McGenEventUnregister_EventUnregister
0x180008f97  mov     rcx, cs:RegHandle; RegHandle
0x180008f9e  mov     cs:dword_18001B028, 0
0x180008fa8  mov     cs:RegHandle, 0
0x180008fb3  call    cs:__imp_EventUnregister
0x180008fb9  mov     rcx, cs:qword_18001B080
0x180008fc0  mov     cs:dword_18001B060, 0
0x180008fca  mov     cs:qword_18001B080, 0
0x180008fd5  add     rsp, 20h
0x180008fd9  pop     rbx
0x180008fda  jmp     cs:__imp_EventUnregister
```
