# CreateSiloNotification(_EJOB *)

- ea: `0x140020b40`
- end: `0x140020be1`
- name: `?CreateSiloNotification@@YAJPEAU_EJOB@@@Z`
- size: `161`
- prototype: `__int64 __fastcall(struct _EJOB *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x14000cef8`
- `0x14000d3dc`
- `0x140020b40`

## import_xrefs

- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x140020b55`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x140020b55`
- `ntoskrnl!PsIsHostSilo` at `0x140020b77`
- `ntoskrnl!PsIsHostSilo` at `0x140020b77`
- `ntoskrnl!PsInsertPermanentSiloContext` at `0x140020bac`
- `ntoskrnl!PsInsertPermanentSiloContext` at `0x140020bac`
- `ntoskrnl!PsGetSiloMonitorContextSlot` at `0x140020b98`
- `ntoskrnl!PsGetSiloMonitorContextSlot` at `0x140020b98`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x140020bc9`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x140020bc9`

## pseudocode

```c
__int64 __fastcall CreateSiloNotification(struct _EJOB *a1)
{
  __int64 v2; // rbp
  const struct _UNICODE_STRING *v3; // rdx
  struct _DRIVER_OBJECT *v4; // rcx
  int inserted; // edi
  char IsHostSilo; // al
  struct _DEVICE_OBJECT *v7; // rbx
  unsigned int SiloMonitorContextSlot; // eax
  PDEVICE_OBJECT DeviceObject; // [rsp+58h] [rbp+10h] BYREF

  DeviceObject = 0;
  v2 = PsAttachSiloToCurrentThread();
  inserted = ACCreateDeviceObject(v4, v3, &DeviceObject);
  if ( inserted >= 0 )
  {
    IsHostSilo = PsIsHostSilo(a1);
    v7 = DeviceObject;
    if ( !IsHostSilo )
      DeviceObject->Flags &= ~0x80u;
    SiloMonitorContextSlot = PsGetSiloMonitorContextSlot(g_pSiloMonitor);
    inserted = PsInsertPermanentSiloContext(a1, SiloMonitorContextSlot, v7);
    if ( inserted < 0 )
      ACDeleteDeviceObject(v7);
  }
  PsDetachSiloFromCurrentThread(v2);
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x140020b40  push    rbx
0x140020b42  push    rbp
0x140020b43  push    rsi
0x140020b44  push    rdi
0x140020b45  sub     rsp, 28h
0x140020b49  mov     rsi, rcx
0x140020b4c  mov     [rsp+48h+DeviceObject], 0
0x140020b55  call    cs:__imp_PsAttachSiloToCurrentThread
0x140020b5c  nop     dword ptr [rax+rax+00h]
0x140020b61  lea     r8, [rsp+48h+DeviceObject]; struct _DEVICE_OBJECT **
0x140020b66  mov     rbp, rax
0x140020b69  call    ?ACCreateDeviceObject@@YAJPEAU_DRIVER_OBJECT@@PEBU_UNICODE_STRING@@PEAPEAU_DEVICE_OBJECT@@@Z; ACCreateDeviceObject(_DRIVER_OBJECT *,_UNICODE_STRING const *,_DEVICE_OBJECT * *)
0x140020b6e  mov     edi, eax
0x140020b70  test    eax, eax
0x140020b72  js      short loc_140020BC6
0x140020b74  mov     rcx, rsi
0x140020b77  call    cs:__imp_PsIsHostSilo
0x140020b7e  nop     dword ptr [rax+rax+00h]
0x140020b83  mov     rbx, [rsp+48h+DeviceObject]
0x140020b88  test    al, al
0x140020b8a  jnz     short loc_140020B91
0x140020b8c  btr     dword ptr [rbx+30h], 7
0x140020b91  mov     rcx, cs:?g_pSiloMonitor@@3PEAU_SILO_MONITOR@@EA; _SILO_MONITOR * g_pSiloMonitor
0x140020b98  call    cs:__imp_PsGetSiloMonitorContextSlot
0x140020b9f  nop     dword ptr [rax+rax+00h]
0x140020ba4  mov     r8, rbx
0x140020ba7  mov     rcx, rsi
0x140020baa  mov     edx, eax
0x140020bac  call    cs:__imp_PsInsertPermanentSiloContext
0x140020bb3  nop     dword ptr [rax+rax+00h]
0x140020bb8  mov     edi, eax
0x140020bba  test    eax, eax
0x140020bbc  jns     short loc_140020BC6
0x140020bbe  mov     rcx, rbx; DeviceObject
0x140020bc1  call    ?ACDeleteDeviceObject@@YAXPEAU_DEVICE_OBJECT@@@Z; ACDeleteDeviceObject(_DEVICE_OBJECT *)
0x140020bc6  mov     rcx, rbp
0x140020bc9  call    cs:__imp_PsDetachSiloFromCurrentThread
0x140020bd0  nop     dword ptr [rax+rax+00h]
0x140020bd5  mov     eax, edi
0x140020bd7  add     rsp, 28h
0x140020bdb  pop     rdi
0x140020bdc  pop     rsi
0x140020bdd  pop     rbp
0x140020bde  pop     rbx
0x140020bdf  retn
```
