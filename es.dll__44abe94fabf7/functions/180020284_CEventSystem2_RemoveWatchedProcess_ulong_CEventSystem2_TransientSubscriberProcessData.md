# CEventSystem2::RemoveWatchedProcess(ulong,CEventSystem2::TransientSubscriberProcessData *)

- ea: `0x180020284`
- end: `0x1800202f4`
- name: `?RemoveWatchedProcess@CEventSystem2@@AEAAXKPEAUTransientSubscriberProcessData@1@@Z`
- size: `112`
- prototype: `void(CEventSystem2 *__hidden this, unsigned int, struct CEventSystem2::TransientSubscriberProcessData *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001fffc`

## callees

- `0x180010410`
- `0x1800202fc`
- `0x180020350`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800202a1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800202a1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800202d3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800202d3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800202b0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800202b0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800202bf`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800202bf`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800202c9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800202c9`

## pseudocode

```c
void __fastcall CEventSystem2::RemoveWatchedProcess(
        struct _RTL_CRITICAL_SECTION *this,
        __int64 a2,
        struct CEventSystem2::TransientSubscriberProcessData *a3)
{
  CMap<unsigned long,unsigned long,CEventSystem2::TransientSubscriberProcessData *,CEventSystem2::TransientSubscriberProcessData *>::RemoveKey(&this[2]);
  LeaveCriticalSection(this + 3);
  SetThreadpoolWait(*((PTP_WAIT *)a3 + 2), 0, 0);
  WaitForThreadpoolWaitCallbacks(*((PTP_WAIT *)a3 + 2), 1);
  CloseThreadpoolWait(*((PTP_WAIT *)a3 + 2));
  CloseHandle(*((HANDLE *)a3 + 1));
  CEventSystem2::TransientSubscriberProcessData::`scalar deleting destructor'(a3);
  CSemExclusiveES::Lock((CSemExclusiveES *)&this[3]);
}

```

## disassembly

```asm
0x180020284  mov     [rsp+arg_0], rbx
0x180020289  push    rdi
0x18002028a  sub     rsp, 20h
0x18002028e  mov     rbx, rcx
0x180020291  mov     rdi, r8
0x180020294  add     rcx, 50h ; 'P'
0x180020298  call    ?RemoveKey@?$CMap@KKPEAUTransientSubscriberProcessData@CEventSystem2@@PEAU12@@@QEAAHK@Z; CMap<ulong,ulong,CEventSystem2::TransientSubscriberProcessData *,CEventSystem2::TransientSubscriberProcessData *>::RemoveKey(ulong)
0x18002029d  lea     rcx, [rbx+78h]; lpCriticalSection
0x1800202a1  call    cs:__imp_LeaveCriticalSection
0x1800202a7  mov     rcx, [rdi+10h]; pwa
0x1800202ab  xor     r8d, r8d; pftTimeout
0x1800202ae  xor     edx, edx; h
0x1800202b0  call    cs:__imp_SetThreadpoolWait
0x1800202b6  mov     rcx, [rdi+10h]; pwa
0x1800202ba  mov     edx, 1; fCancelPendingCallbacks
0x1800202bf  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x1800202c5  mov     rcx, [rdi+10h]; pwa
0x1800202c9  call    cs:__imp_CloseThreadpoolWait
0x1800202cf  mov     rcx, [rdi+8]; hObject
0x1800202d3  call    cs:__imp_CloseHandle
0x1800202d9  mov     rcx, rdi; this
0x1800202dc  call    ??_GTransientSubscriberProcessData@CEventSystem2@@QEAAPEAXI@Z; CEventSystem2::TransientSubscriberProcessData::`scalar deleting destructor'(uint)
0x1800202e1  lea     rcx, [rbx+78h]; this
0x1800202e5  mov     rbx, [rsp+28h+arg_0]
0x1800202ea  add     rsp, 20h
0x1800202ee  pop     rdi
0x1800202ef  jmp     ?Lock@CSemExclusiveES@@QEAAXXZ; CSemExclusiveES::Lock(void)
```
