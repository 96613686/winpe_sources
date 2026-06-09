# CPolicyMonitor::~CPolicyMonitor(void)

- ea: `0x180053198`
- end: `0x1800532c9`
- name: `??1CPolicyMonitor@@UEAA@XZ`
- size: `305`
- prototype: `void __fastcall(CPolicyMonitor *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800535a0`

## callees

- `0x180014a80`
- `0x180053198`

## import_xrefs

- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800531d3`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800531d3`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800531bb`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800531bb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18005321b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18005321b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180053208`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180053208`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180053291`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180053291`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180053233`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005324b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180053263`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005327b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180053233`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005324b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180053263`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005327b`
- `api-ms-win-oobe-notification-l1-1-0!UnregisterWaitUntilOOBECompleted` at `0x1800531eb`
- `api-ms-win-oobe-notification-l1-1-0!UnregisterWaitUntilOOBECompleted` at `0x1800531eb`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180053198  mov     [rsp+arg_0], rbx
0x18005319d  push    rdi
0x18005319e  sub     rsp, 20h
0x1800531a2  mov     rbx, rcx
0x1800531a5  lea     rax, ??_7CPolicyMonitor@@6B@; const CPolicyMonitor::`vftable'
0x1800531ac  mov     [rcx], rax
0x1800531af  mov     rcx, [rcx+698h]; hEvent
0x1800531b6  test    rcx, rcx
0x1800531b9  jz      short loc_1800531C7
0x1800531bb  call    cs:__imp_SetEvent
0x1800531c2  nop     dword ptr [rax+rax+00h]
0x1800531c7  mov     rcx, [rbx+6B0h]
0x1800531ce  test    rcx, rcx
0x1800531d1  jz      short loc_1800531DF
0x1800531d3  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x1800531da  nop     dword ptr [rax+rax+00h]
0x1800531df  mov     rcx, [rbx+6B8h]
0x1800531e6  test    rcx, rcx
0x1800531e9  jz      short loc_1800531F7
0x1800531eb  call    cs:__imp_UnregisterWaitUntilOOBECompleted
0x1800531f2  nop     dword ptr [rax+rax+00h]
0x1800531f7  mov     rcx, [rbx+6A8h]; pwk
0x1800531fe  test    rcx, rcx
0x180053201  jz      short loc_180053227
0x180053203  mov     edx, 1; fCancelPendingCallbacks
0x180053208  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18005320f  nop     dword ptr [rax+rax+00h]
0x180053214  mov     rcx, [rbx+6A8h]; pwk
0x18005321b  call    cs:__imp_CloseThreadpoolWork
0x180053222  nop     dword ptr [rax+rax+00h]
0x180053227  mov     rcx, [rbx+638h]; hKey
0x18005322e  test    rcx, rcx
0x180053231  jz      short loc_18005323F
0x180053233  call    cs:__imp_RegCloseKey
0x18005323a  nop     dword ptr [rax+rax+00h]
0x18005323f  mov     rcx, [rbx+640h]; hKey
0x180053246  test    rcx, rcx
0x180053249  jz      short loc_180053257
0x18005324b  call    cs:__imp_RegCloseKey
0x180053252  nop     dword ptr [rax+rax+00h]
0x180053257  mov     rcx, [rbx+648h]; hKey
0x18005325e  test    rcx, rcx
0x180053261  jz      short loc_18005326F
0x180053263  call    cs:__imp_RegCloseKey
0x18005326a  nop     dword ptr [rax+rax+00h]
0x18005326f  mov     rcx, [rbx+650h]; hKey
0x180053276  test    rcx, rcx
0x180053279  jz      short loc_180053287
0x18005327b  call    cs:__imp_RegCloseKey
0x180053282  nop     dword ptr [rax+rax+00h]
0x180053287  xor     edi, edi
0x180053289  mov     rcx, [rbx+rdi*8+660h]; hObject
0x180053291  call    cs:__imp_CloseHandle
0x180053298  nop     dword ptr [rax+rax+00h]
0x18005329d  inc     rdi
0x1800532a0  cmp     rdi, 8
0x1800532a4  jnz     short loc_180053289
0x1800532a6  lea     rax, ??_7?$CTSPrivateObject@UIUnknown@@@@6B@; const CTSPrivateObject<IUnknown>::`vftable'
0x1800532ad  mov     [rbx], rax
0x1800532b0  lea     rcx, [rbx+628h]; struct _LIST_ENTRY *
0x1800532b7  call    ?RemoveTrackingObject@@YAXPEAU_LIST_ENTRY@@@Z; RemoveTrackingObject(_LIST_ENTRY *)
0x1800532bc  nop
0x1800532bd  mov     rbx, [rsp+28h+arg_0]
0x1800532c2  add     rsp, 20h
0x1800532c6  pop     rdi
0x1800532c7  retn
```
