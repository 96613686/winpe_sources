# DriverUnload

- ea: `0x140008250`
- end: `0x140008327`
- name: `DriverUnload`
- size: `215`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task, installer_update`

## callees

- `0x1400018f0`
- `0x140008250`
- `0x1400085ac`
- `0x1400088cc`
- `0x140008920`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140008297`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400082f7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008297`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400082f7`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140008270`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140008270`
- `FLTMGR!FltDeletePushLock` at `0x1400082cc`
- `FLTMGR!FltDeletePushLock` at `0x1400082df`
- `FLTMGR!FltDeletePushLock` at `0x1400082cc`
- `FLTMGR!FltDeletePushLock` at `0x1400082df`
- `FLTMGR!FltReleasePushLockEx` at `0x1400082b5`
- `FLTMGR!FltReleasePushLockEx` at `0x1400082b5`

## pseudocode

```c
__int64 DriverUnload()
{
  PVOID DeviceExtension; // rcx
  char *v1; // rax
  _QWORD *v2; // rbx
  void *v3; // rcx

  RtdsUnregisterUpdateCallback(&NAMED_PIPE_EVENT_GUID);
  RtdsReaderShutdown();
  FltAcquirePushLockExclusiveEx(WPP_MAIN_CB.DeviceExtension, 0);
  DeviceExtension = WPP_MAIN_CB.DeviceExtension;
  v1 = (char *)WPP_MAIN_CB.DeviceExtension + 8;
  v2 = (_QWORD *)*((_QWORD *)WPP_MAIN_CB.DeviceExtension + 1);
  while ( v2 != (_QWORD *)v1 )
  {
    v3 = v2;
    v2 = (_QWORD *)*v2;
    ExFreePoolWithTag(v3, 0x6774704Eu);
    DeviceExtension = WPP_MAIN_CB.DeviceExtension;
    v1 = (char *)WPP_MAIN_CB.DeviceExtension + 8;
  }
  FltReleasePushLockEx(DeviceExtension, 0);
  FltDeletePushLock((PULONG_PTR)WPP_MAIN_CB.DeviceExtension + 3);
  FltDeletePushLock((PULONG_PTR)WPP_MAIN_CB.DeviceExtension);
  ExFreePoolWithTag(WPP_MAIN_CB.DeviceExtension, 0x6774704Eu);
  McGenEventUnregister_EtwUnregister(&NPTRIG_ETW_PROVIDER_GUID_Context);
  McGenEventUnregister_EtwUnregister(&SERVICE_TRIGGER_PERF_EVENT_GUID_Context);
  return WppCleanupKm();
}

```

## disassembly

```asm
0x140008250  push    rbx
0x140008252  sub     rsp, 20h
0x140008256  lea     rcx, NAMED_PIPE_EVENT_GUID
0x14000825d  call    RtdsUnregisterUpdateCallback
0x140008262  call    RtdsReaderShutdown
0x140008267  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x14000826e  xor     edx, edx
0x140008270  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x140008277  nop     dword ptr [rax+rax+00h]
0x14000827c  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x140008283  lea     rax, [rcx+8]
0x140008287  mov     rbx, [rax]
0x14000828a  jmp     short loc_1400082AE
0x14000828c  mov     rcx, rbx; P
0x14000828f  mov     edx, 6774704Eh; Tag
0x140008294  mov     rbx, [rbx]
0x140008297  call    cs:__imp_ExFreePoolWithTag
0x14000829e  nop     dword ptr [rax+rax+00h]
0x1400082a3  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x1400082aa  lea     rax, [rcx+8]
0x1400082ae  cmp     rbx, rax
0x1400082b1  jnz     short loc_14000828C
0x1400082b3  xor     edx, edx
0x1400082b5  call    cs:__imp_FltReleasePushLockEx
0x1400082bc  nop     dword ptr [rax+rax+00h]
0x1400082c1  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x1400082c8  add     rcx, 18h; PushLock
0x1400082cc  call    cs:__imp_FltDeletePushLock
0x1400082d3  nop     dword ptr [rax+rax+00h]
0x1400082d8  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension; PushLock
0x1400082df  call    cs:__imp_FltDeletePushLock
0x1400082e6  nop     dword ptr [rax+rax+00h]
0x1400082eb  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension; P
0x1400082f2  mov     edx, 6774704Eh; Tag
0x1400082f7  call    cs:__imp_ExFreePoolWithTag
0x1400082fe  nop     dword ptr [rax+rax+00h]
0x140008303  lea     rcx, NPTRIG_ETW_PROVIDER_GUID_Context
0x14000830a  call    McGenEventUnregister_EtwUnregister
0x14000830f  lea     rcx, SERVICE_TRIGGER_PERF_EVENT_GUID_Context
0x140008316  call    McGenEventUnregister_EtwUnregister
0x14000831b  call    WppCleanupKm
0x140008320  add     rsp, 20h
0x140008324  pop     rbx
0x140008325  retn
```
