# Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController::~BthLEPrepairingController(void)

- ea: `0x18002b240`
- end: `0x18002b307`
- name: `??1BthLEPrepairingController@BthLEPrepairing@Bluetooth@Internal@Windows@@UEAA@XZ`
- size: `199`
- prototype: `void __fastcall(Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, installer_update`

## callers

- `0x18002b870`

## callees

- `0x180001b94`
- `0x18002b240`
- `0x18002b310`
- `0x18002c4b4`
- `0x18002c984`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002b265`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002b265`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18002b2e0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18002b2e0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18002b2ef`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18002b2ef`

## pseudocode

```c
void __fastcall Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController::~BthLEPrepairingController(
        Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController *this)
{
  void *v2; // rbx
  volatile signed __int32 *v3; // rbx
  struct _TP_WORK *v4; // rbx

  *(_QWORD *)this = &Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController::`vftable';
  Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController::Stop(this);
  McGenEventUnregister_EventUnregister();
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  v2 = (void *)*((_QWORD *)this + 5);
  if ( v2 )
  {
    Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDeviceMonitor::~BthLEPrepairingDeviceMonitor(*((Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDeviceMonitor **)this + 5));
    operator delete(v2, (const struct std::nothrow_t *)0x48);
  }
  v3 = (volatile signed __int32 *)*((_QWORD *)this + 4);
  if ( v3 )
  {
    if ( _InterlockedExchangeAdd(v3 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v3)(v3);
      if ( _InterlockedExchangeAdd(v3 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v3 + 8LL))(v3);
    }
  }
  v4 = (struct _TP_WORK *)*((_QWORD *)this + 2);
  if ( v4 )
  {
    WaitForThreadpoolWorkCallbacks(*((PTP_WORK *)this + 2), 1);
    CloseThreadpoolWork(v4);
  }
}

```

## disassembly

```asm
0x18002b240  mov     [rsp+arg_0], rbx
0x18002b245  push    rdi
0x18002b246  sub     rsp, 20h
0x18002b24a  lea     rax, ??_7BthLEPrepairingController@BthLEPrepairing@Bluetooth@Internal@Windows@@6B@; const Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController::`vftable'
0x18002b251  mov     rdi, rcx
0x18002b254  mov     [rcx], rax
0x18002b257  call    ?Stop@BthLEPrepairingController@BthLEPrepairing@Bluetooth@Internal@Windows@@QEAAJXZ; Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController::Stop(void)
0x18002b25c  call    McGenEventUnregister_EventUnregister
0x18002b261  lea     rcx, [rdi+30h]; lpCriticalSection
0x18002b265  call    cs:__imp_DeleteCriticalSection
0x18002b26c  nop     dword ptr [rax+rax+00h]
0x18002b271  mov     rbx, [rdi+28h]
0x18002b275  test    rbx, rbx
0x18002b278  jz      short loc_18002B28F
0x18002b27a  mov     rcx, rbx; this
0x18002b27d  call    ??1BthLEPrepairingDeviceMonitor@BthLEPrepairing@Bluetooth@Internal@Windows@@QEAA@XZ; Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDeviceMonitor::~BthLEPrepairingDeviceMonitor(void)
0x18002b282  mov     edx, 48h ; 'H'; struct std::nothrow_t *
0x18002b287  mov     rcx, rbx; void *
0x18002b28a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002b28f  mov     rbx, [rdi+20h]
0x18002b293  test    rbx, rbx
0x18002b296  jz      short loc_18002B2CF
0x18002b298  or      eax, 0FFFFFFFFh
0x18002b29b  lock xadd [rbx+8], eax
0x18002b2a0  cmp     eax, 1
0x18002b2a3  jnz     short loc_18002B2CF
0x18002b2a5  mov     rax, [rbx]
0x18002b2a8  mov     rcx, rbx
0x18002b2ab  mov     rax, [rax]
0x18002b2ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b2b3  or      eax, 0FFFFFFFFh
0x18002b2b6  lock xadd [rbx+0Ch], eax
0x18002b2bb  cmp     eax, 1
0x18002b2be  jnz     short loc_18002B2CF
0x18002b2c0  mov     rax, [rbx]
0x18002b2c3  mov     rcx, rbx
0x18002b2c6  mov     rax, [rax+8]
0x18002b2ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b2cf  mov     rbx, [rdi+10h]
0x18002b2d3  test    rbx, rbx
0x18002b2d6  jz      short loc_18002B2FB
0x18002b2d8  mov     edx, 1; fCancelPendingCallbacks
0x18002b2dd  mov     rcx, rbx; pwk
0x18002b2e0  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18002b2e7  nop     dword ptr [rax+rax+00h]
0x18002b2ec  mov     rcx, rbx; pwk
0x18002b2ef  call    cs:__imp_CloseThreadpoolWork
0x18002b2f6  nop     dword ptr [rax+rax+00h]
0x18002b2fb  mov     rbx, [rsp+28h+arg_0]
0x18002b300  add     rsp, 20h
0x18002b304  pop     rdi
0x18002b305  retn
```
