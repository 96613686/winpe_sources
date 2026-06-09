# MountMgrUnload

- ea: `0x14000d7a0`
- end: `0x14000d997`
- name: `MountMgrUnload`
- size: `503`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `reparse_path, loader_planting`

## callees

- `0x14000a510`
- `0x14000c7d8`
- `0x14000c954`
- `0x14000d7a0`
- `0x1400100a4`
- `0x140018cd0`

## import_xrefs

- `ntoskrnl!IoUnregisterPlugPlayNotification` at `0x14000d88c`
- `ntoskrnl!IoUnregisterPlugPlayNotification` at `0x14000d88c`
- `ntoskrnl!IoDeleteDevice` at `0x14000d975`
- `ntoskrnl!IoDeleteDevice` at `0x14000d975`
- `ntoskrnl!KeReleaseMutex` at `0x14000d944`
- `ntoskrnl!KeReleaseMutex` at `0x14000d944`
- `ntoskrnl!KeReleaseSemaphore` at `0x14000d853`
- `ntoskrnl!KeReleaseSemaphore` at `0x14000d853`
- `ntoskrnl!EtwUnregister` at `0x14000d7bd`
- `ntoskrnl!EtwUnregister` at `0x14000d7bd`
- `ntoskrnl!IoUnregisterShutdownNotification` at `0x14000d7d7`
- `ntoskrnl!IoUnregisterShutdownNotification` at `0x14000d7d7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d7fc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d7fc`
- `ntoskrnl!KeInitializeEvent` at `0x14000d828`
- `ntoskrnl!KeInitializeEvent` at `0x14000d828`
- `ntoskrnl!PsFreeSiloContextSlot` at `0x14000d956`
- `ntoskrnl!PsFreeSiloContextSlot` at `0x14000d956`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000d873`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000d8ac`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000d873`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000d8ac`

## pseudocode

```c
__int64 MountMgrUnload()
{
  char *DeviceExtension; // rbx
  void *v1; // rcx
  struct _KMUTANT *v2; // rsi
  _QWORD **v3; // rdi
  _QWORD *v4; // rcx
  _QWORD *v5; // rax
  _QWORD **v6; // rdi
  _QWORD *v7; // rcx
  _QWORD *v8; // rax
  _QWORD **v9; // rbx
  _QWORD *v10; // rcx
  _QWORD *v11; // rax

  if ( gEtwProvRegHandle )
  {
    EtwUnregister(gEtwProvRegHandle);
    gEtwProvRegHandle = 0;
  }
  IoUnregisterShutdownNotification(gDeviceObject);
  DeviceExtension = (char *)gDeviceObject->DeviceExtension;
  v1 = (void *)*((_QWORD *)DeviceExtension + 34);
  if ( v1 )
  {
    ExFreePoolWithTag(v1, 0);
    *((_QWORD *)DeviceExtension + 34) = 0;
  }
  _InterlockedExchange(&gUnloading, 1);
  KeInitializeEvent(&gUnloadEvent, NotificationEvent, 0);
  if ( _InterlockedIncrement((volatile signed __int32 *)DeviceExtension + 62) <= 0 )
  {
    _InterlockedDecrement((volatile signed __int32 *)DeviceExtension + 62);
  }
  else
  {
    KeReleaseSemaphore((PRKSEMAPHORE)(DeviceExtension + 216), 0, 1, 0);
    KeWaitForSingleObject(&gUnloadEvent, Executive, 0, 0, 0);
  }
  IoUnregisterPlugPlayNotification(*((PVOID *)DeviceExtension + 6));
  v2 = (struct _KMUTANT *)(DeviceExtension + 56);
  KeWaitForSingleObject(DeviceExtension + 56, Executive, 0, 0, 0);
  v3 = (_QWORD **)(DeviceExtension + 32);
  while ( 1 )
  {
    v4 = *v3;
    if ( *v3 == v3 )
      break;
    if ( (_QWORD **)v4[1] != v3 || (v5 = (_QWORD *)*v4, *(_QWORD **)(*v4 + 8LL) != v4) )
LABEL_23:
      __fastfail(3u);
    *v3 = v5;
    v5[1] = v3;
    MountMgrFreeDeadDeviceInfo(v4);
  }
  v6 = (_QWORD **)(DeviceExtension + 16);
  while ( 1 )
  {
    v7 = *v6;
    if ( *v6 == v6 )
      break;
    if ( (_QWORD **)v7[1] != v6 )
      goto LABEL_23;
    v8 = (_QWORD *)*v7;
    if ( *(_QWORD **)(*v7 + 8LL) != v7 )
      goto LABEL_23;
    *v6 = v8;
    v8[1] = v6;
    MountMgrFreeMountedDeviceInfo(v7);
  }
  v9 = (_QWORD **)(DeviceExtension + 176);
  while ( 1 )
  {
    v10 = *v9;
    if ( *v9 == v9 )
      break;
    if ( (_QWORD **)v10[1] != v9 )
      goto LABEL_23;
    v11 = (_QWORD *)*v10;
    if ( *(_QWORD **)(*v10 + 8LL) != v10 )
      goto LABEL_23;
    *v9 = v11;
    v11[1] = v9;
    MountMgrFreeSavedLink(v10);
  }
  KeReleaseMutex(v2, 0);
  PsFreeSiloContextSlot((unsigned int)gSiloSlot);
  GlobalDeleteSymbolicLink((__int64)asc_140007068);
  IoDeleteDevice(gDeviceObject);
  return WppCleanupKm();
}

```

## disassembly

```asm
0x14000d7a0  mov     [rsp+arg_0], rbx
0x14000d7a5  mov     [rsp+arg_8], rsi
0x14000d7aa  push    rdi
0x14000d7ab  sub     rsp, 30h
0x14000d7af  mov     rcx, cs:gEtwProvRegHandle; RegHandle
0x14000d7b6  xor     edi, edi
0x14000d7b8  test    rcx, rcx
0x14000d7bb  jz      short loc_14000D7D0
0x14000d7bd  call    cs:__imp_EtwUnregister
0x14000d7c4  nop     dword ptr [rax+rax+00h]
0x14000d7c9  mov     cs:gEtwProvRegHandle, rdi
0x14000d7d0  mov     rcx, cs:gDeviceObject; DeviceObject
0x14000d7d7  call    cs:__imp_IoUnregisterShutdownNotification
0x14000d7de  nop     dword ptr [rax+rax+00h]
0x14000d7e3  mov     rax, cs:gDeviceObject
0x14000d7ea  mov     rbx, [rax+40h]
0x14000d7ee  mov     rcx, [rbx+110h]; P
0x14000d7f5  test    rcx, rcx
0x14000d7f8  jz      short loc_14000D80F
0x14000d7fa  xor     edx, edx; Tag
0x14000d7fc  call    cs:__imp_ExFreePoolWithTag
0x14000d803  nop     dword ptr [rax+rax+00h]
0x14000d808  mov     [rbx+110h], rdi
0x14000d80f  mov     esi, 1
0x14000d814  lea     rcx, gUnloadEvent; Event
0x14000d81b  mov     eax, esi
0x14000d81d  xor     r8d, r8d; State
0x14000d820  xchg    eax, cs:gUnloading
0x14000d826  xor     edx, edx; Type
0x14000d828  call    cs:__imp_KeInitializeEvent
0x14000d82f  nop     dword ptr [rax+rax+00h]
0x14000d834  mov     eax, esi
0x14000d836  lock xadd [rbx+0F8h], eax
0x14000d83e  add     eax, esi
0x14000d840  test    eax, eax
0x14000d842  jle     short loc_14000D881
0x14000d844  lea     rcx, [rbx+0D8h]; Semaphore
0x14000d84b  xor     r9d, r9d; Wait
0x14000d84e  mov     r8d, esi; Adjustment
0x14000d851  xor     edx, edx; Increment
0x14000d853  call    cs:__imp_KeReleaseSemaphore
0x14000d85a  nop     dword ptr [rax+rax+00h]
0x14000d85f  xor     r9d, r9d; Alertable
0x14000d862  mov     [rsp+38h+Timeout], rdi; Timeout
0x14000d867  xor     r8d, r8d; WaitMode
0x14000d86a  lea     rcx, gUnloadEvent; Object
0x14000d871  xor     edx, edx; WaitReason
0x14000d873  call    cs:__imp_KeWaitForSingleObject
0x14000d87a  nop     dword ptr [rax+rax+00h]
0x14000d87f  jmp     short loc_14000D888
0x14000d881  lock dec dword ptr [rbx+0F8h]
0x14000d888  mov     rcx, [rbx+30h]; NotificationEntry
0x14000d88c  call    cs:__imp_IoUnregisterPlugPlayNotification
0x14000d893  nop     dword ptr [rax+rax+00h]
0x14000d898  lea     rsi, [rbx+38h]
0x14000d89c  mov     [rsp+38h+Timeout], rdi; Timeout
0x14000d8a1  mov     rcx, rsi; Object
0x14000d8a4  xor     r9d, r9d; Alertable
0x14000d8a7  xor     r8d, r8d; WaitMode
0x14000d8aa  xor     edx, edx; WaitReason
0x14000d8ac  call    cs:__imp_KeWaitForSingleObject
0x14000d8b3  nop     dword ptr [rax+rax+00h]
0x14000d8b8  lea     rdi, [rbx+20h]
0x14000d8bc  mov     rcx, [rdi]; P
0x14000d8bf  cmp     rcx, rdi
0x14000d8c2  jz      short loc_14000D8E1
0x14000d8c4  cmp     [rcx+8], rdi
0x14000d8c8  jnz     short loc_14000D938
0x14000d8ca  mov     rax, [rcx]
0x14000d8cd  cmp     [rax+8], rcx
0x14000d8d1  jnz     short loc_14000D938
0x14000d8d3  mov     [rdi], rax
0x14000d8d6  mov     [rax+8], rdi
0x14000d8da  call    MountMgrFreeDeadDeviceInfo
0x14000d8df  jmp     short loc_14000D8BC
0x14000d8e1  lea     rdi, [rbx+10h]
0x14000d8e5  mov     rcx, [rdi]; P
0x14000d8e8  cmp     rcx, rdi
0x14000d8eb  jz      short loc_14000D90C
0x14000d8ed  cmp     [rcx+8], rdi
0x14000d8f1  jnz     short loc_14000D938
0x14000d8f3  mov     rax, [rcx]
0x14000d8f6  cmp     [rax+8], rcx
0x14000d8fa  jnz     short loc_14000D938
0x14000d8fc  mov     [rdi], rax
0x14000d8ff  xor     edx, edx
0x14000d901  mov     [rax+8], rdi
0x14000d905  call    MountMgrFreeMountedDeviceInfo
0x14000d90a  jmp     short loc_14000D8E5
0x14000d90c  add     rbx, 0B0h
0x14000d913  mov     rcx, [rbx]; P
0x14000d916  cmp     rcx, rbx
0x14000d919  jz      short loc_14000D93F
0x14000d91b  cmp     [rcx+8], rbx
0x14000d91f  jnz     short loc_14000D938
0x14000d921  mov     rax, [rcx]
0x14000d924  cmp     [rax+8], rcx
0x14000d928  jnz     short loc_14000D938
0x14000d92a  mov     [rbx], rax
0x14000d92d  mov     [rax+8], rbx
0x14000d931  call    MountMgrFreeSavedLink
0x14000d936  jmp     short loc_14000D913
0x14000d938  mov     ecx, 3
0x14000d93d  int     29h; Win8: RtlFailFast(ecx)
0x14000d93f  xor     edx, edx; Wait
0x14000d941  mov     rcx, rsi; Mutex
0x14000d944  call    cs:__imp_KeReleaseMutex
0x14000d94b  nop     dword ptr [rax+rax+00h]
0x14000d950  mov     ecx, cs:gSiloSlot
0x14000d956  call    cs:__imp_PsFreeSiloContextSlot
0x14000d95d  nop     dword ptr [rax+rax+00h]
0x14000d962  lea     rcx, asc_140007068; ":<"
0x14000d969  call    GlobalDeleteSymbolicLink
0x14000d96e  mov     rcx, cs:gDeviceObject; DeviceObject
0x14000d975  call    cs:__imp_IoDeleteDevice
0x14000d97c  nop     dword ptr [rax+rax+00h]
0x14000d981  call    WppCleanupKm
0x14000d986  mov     rbx, [rsp+38h+arg_0]
0x14000d98b  mov     rsi, [rsp+38h+arg_8]
0x14000d990  add     rsp, 30h
0x14000d994  pop     rdi
0x14000d995  retn
```
