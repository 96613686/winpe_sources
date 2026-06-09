# TerminateSiloNotification(_EJOB *)

- ea: `0x140020bf0`
- end: `0x140020c65`
- name: `?TerminateSiloNotification@@YAXPEAU_EJOB@@@Z`
- size: `117`
- prototype: `void __fastcall(struct _EJOB *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14000d3dc`
- `0x140020bf0`

## import_xrefs

- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x140020c36`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x140020c36`
- `ntoskrnl!PsGetSiloMonitorContextSlot` at `0x140020c09`
- `ntoskrnl!PsGetSiloMonitorContextSlot` at `0x140020c09`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x140020c52`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x140020c52`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x140020c1f`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x140020c1f`

## pseudocode

```c
void __fastcall TerminateSiloNotification(struct _EJOB *a1)
{
  unsigned int SiloMonitorContextSlot; // eax
  __int64 v3; // rbx
  PDEVICE_OBJECT DeviceObject; // [rsp+38h] [rbp+10h] BYREF

  DeviceObject = 0;
  SiloMonitorContextSlot = PsGetSiloMonitorContextSlot(g_pSiloMonitor);
  PsGetPermanentSiloContext(a1, SiloMonitorContextSlot, &DeviceObject);
  if ( DeviceObject )
  {
    v3 = PsAttachSiloToCurrentThread(a1);
    ACDeleteDeviceObject(DeviceObject);
    PsDetachSiloFromCurrentThread(v3);
  }
}

```

## disassembly

```asm
0x140020bf0  push    rbx
0x140020bf2  sub     rsp, 20h
0x140020bf6  mov     rbx, rcx
0x140020bf9  mov     [rsp+28h+DeviceObject], 0
0x140020c02  mov     rcx, cs:?g_pSiloMonitor@@3PEAU_SILO_MONITOR@@EA; _SILO_MONITOR * g_pSiloMonitor
0x140020c09  call    cs:__imp_PsGetSiloMonitorContextSlot
0x140020c10  nop     dword ptr [rax+rax+00h]
0x140020c15  lea     r8, [rsp+28h+DeviceObject]
0x140020c1a  mov     rcx, rbx
0x140020c1d  mov     edx, eax
0x140020c1f  call    cs:__imp_PsGetPermanentSiloContext
0x140020c26  nop     dword ptr [rax+rax+00h]
0x140020c2b  cmp     [rsp+28h+DeviceObject], 0
0x140020c31  jz      short loc_140020C5E
0x140020c33  mov     rcx, rbx
0x140020c36  call    cs:__imp_PsAttachSiloToCurrentThread
0x140020c3d  nop     dword ptr [rax+rax+00h]
0x140020c42  mov     rcx, [rsp+28h+DeviceObject]; DeviceObject
0x140020c47  mov     rbx, rax
0x140020c4a  call    ?ACDeleteDeviceObject@@YAXPEAU_DEVICE_OBJECT@@@Z; ACDeleteDeviceObject(_DEVICE_OBJECT *)
0x140020c4f  mov     rcx, rbx
0x140020c52  call    cs:__imp_PsDetachSiloFromCurrentThread
0x140020c59  nop     dword ptr [rax+rax+00h]
0x140020c5e  add     rsp, 20h
0x140020c62  pop     rbx
0x140020c63  retn
```
