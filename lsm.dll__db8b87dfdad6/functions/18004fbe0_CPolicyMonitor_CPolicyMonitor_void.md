# CPolicyMonitor::~CPolicyMonitor(void)

- ea: `0x18004fbe0`
- end: `0x18004fcd4`
- name: `??1CPolicyMonitor@@UEAA@XZ`
- size: `244`
- prototype: `void __fastcall(CPolicyMonitor *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004ff80`

## callees

- `0x180010f20`
- `0x18004fbe0`

## import_xrefs

- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18004fc15`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18004fc15`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004fc03`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004fc03`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18004fc4b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18004fc4b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18004fc3e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18004fc3e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004fca3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004fca3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004fc5d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004fc6f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004fc81`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004fc93`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004fc5d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004fc6f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004fc81`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004fc93`
- `api-ms-win-oobe-notification-l1-1-0!UnregisterWaitUntilOOBECompleted` at `0x18004fc27`
- `api-ms-win-oobe-notification-l1-1-0!UnregisterWaitUntilOOBECompleted` at `0x18004fc27`

## pseudocode

```c
void __fastcall CPolicyMonitor::~CPolicyMonitor(CPolicyMonitor *this)
{
  void *v2; // rcx
  struct _TP_WORK *v3; // rcx
  HKEY v4; // rcx
  HKEY v5; // rcx
  HKEY v6; // rcx
  HKEY v7; // rcx
  __int64 i; // rdi

  *(_QWORD *)this = &CPolicyMonitor::`vftable';
  v2 = (void *)*((_QWORD *)this + 211);
  if ( v2 )
    SetEvent(v2);
  if ( *((_QWORD *)this + 214) )
    RtlUnsubscribeWnfNotificationWaitForCompletion();
  if ( *((_QWORD *)this + 215) )
    UnregisterWaitUntilOOBECompleted();
  v3 = (struct _TP_WORK *)*((_QWORD *)this + 213);
  if ( v3 )
  {
    WaitForThreadpoolWorkCallbacks(v3, 1);
    CloseThreadpoolWork(*((PTP_WORK *)this + 213));
  }
  v4 = (HKEY)*((_QWORD *)this + 199);
  if ( v4 )
    RegCloseKey(v4);
  v5 = (HKEY)*((_QWORD *)this + 200);
  if ( v5 )
    RegCloseKey(v5);
  v6 = (HKEY)*((_QWORD *)this + 201);
  if ( v6 )
    RegCloseKey(v6);
  v7 = (HKEY)*((_QWORD *)this + 202);
  if ( v7 )
    RegCloseKey(v7);
  for ( i = 0; i != 8; ++i )
    CloseHandle(*((HANDLE *)this + i + 204));
  *(_QWORD *)this = &CTSPrivateObject<IUnknown>::`vftable';
  RemoveTrackingObject((struct _LIST_ENTRY *)((char *)this + 1576));
}

```

## disassembly

```asm
0x18004fbe0  mov     [rsp+arg_0], rbx
0x18004fbe5  push    rdi
0x18004fbe6  sub     rsp, 20h
0x18004fbea  mov     rbx, rcx
0x18004fbed  lea     rax, ??_7CPolicyMonitor@@6B@; const CPolicyMonitor::`vftable'
0x18004fbf4  mov     [rcx], rax
0x18004fbf7  mov     rcx, [rcx+698h]; hEvent
0x18004fbfe  test    rcx, rcx
0x18004fc01  jz      short loc_18004FC09
0x18004fc03  call    cs:__imp_SetEvent
0x18004fc09  mov     rcx, [rbx+6B0h]
0x18004fc10  test    rcx, rcx
0x18004fc13  jz      short loc_18004FC1B
0x18004fc15  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x18004fc1b  mov     rcx, [rbx+6B8h]
0x18004fc22  test    rcx, rcx
0x18004fc25  jz      short loc_18004FC2D
0x18004fc27  call    cs:__imp_UnregisterWaitUntilOOBECompleted
0x18004fc2d  mov     rcx, [rbx+6A8h]; pwk
0x18004fc34  test    rcx, rcx
0x18004fc37  jz      short loc_18004FC51
0x18004fc39  mov     edx, 1; fCancelPendingCallbacks
0x18004fc3e  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18004fc44  mov     rcx, [rbx+6A8h]; pwk
0x18004fc4b  call    cs:__imp_CloseThreadpoolWork
0x18004fc51  mov     rcx, [rbx+638h]; hKey
0x18004fc58  test    rcx, rcx
0x18004fc5b  jz      short loc_18004FC63
0x18004fc5d  call    cs:__imp_RegCloseKey
0x18004fc63  mov     rcx, [rbx+640h]; hKey
0x18004fc6a  test    rcx, rcx
0x18004fc6d  jz      short loc_18004FC75
0x18004fc6f  call    cs:__imp_RegCloseKey
0x18004fc75  mov     rcx, [rbx+648h]; hKey
0x18004fc7c  test    rcx, rcx
0x18004fc7f  jz      short loc_18004FC87
0x18004fc81  call    cs:__imp_RegCloseKey
0x18004fc87  mov     rcx, [rbx+650h]; hKey
0x18004fc8e  test    rcx, rcx
0x18004fc91  jz      short loc_18004FC99
0x18004fc93  call    cs:__imp_RegCloseKey
0x18004fc99  xor     edi, edi
0x18004fc9b  mov     rcx, [rbx+rdi*8+660h]; hObject
0x18004fca3  call    cs:__imp_CloseHandle
0x18004fca9  inc     rdi
0x18004fcac  cmp     rdi, 8
0x18004fcb0  jnz     short loc_18004FC9B
0x18004fcb2  lea     rax, ??_7?$CTSPrivateObject@UIUnknown@@@@6B@; const CTSPrivateObject<IUnknown>::`vftable'
0x18004fcb9  mov     [rbx], rax
0x18004fcbc  lea     rcx, [rbx+628h]; struct _LIST_ENTRY *
0x18004fcc3  call    ?RemoveTrackingObject@@YAXPEAU_LIST_ENTRY@@@Z; RemoveTrackingObject(_LIST_ENTRY *)
0x18004fcc8  nop
0x18004fcc9  mov     rbx, [rsp+28h+arg_0]
0x18004fcce  add     rsp, 20h
0x18004fcd2  pop     rdi
0x18004fcd3  retn
```
