# WaitingLockedQueue<IUnknown>::~WaitingLockedQueue<IUnknown>(void)

- ea: `0x14002abf4`
- end: `0x14002ac3d`
- name: `??1?$WaitingLockedQueue@UIUnknown@@@@QEAA@XZ`
- size: `73`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14002b5c8`
- `0x14002b600`
- `0x14005ffca`

## callees

- `0x1400071e8`
- `0x14001c32c`
- `0x14002abf4`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x14002ac2a`
- `KERNEL32!DeleteCriticalSection` at `0x14002ac2a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall WaitingLockedQueue<IUnknown>::~WaitingLockedQueue<IUnknown>(LPCRITICAL_SECTION lpCriticalSection)
{
  NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Reset(&lpCriticalSection[2].SpinCount);
  NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Reset(&lpCriticalSection[2].LockSemaphore);
  NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Reset(&lpCriticalSection[2].OwningThread);
  std::deque<PrnExcept::TRefSmartPtr<IShutdownComponent>>::~deque<PrnExcept::TRefSmartPtr<IShutdownComponent>>(&lpCriticalSection[1].OwningThread);
  if ( lpCriticalSection[1].LockCount >= 0 )
  {
    DeleteCriticalSection(lpCriticalSection);
    lpCriticalSection[1].LockCount = -2147467259;
  }
}

```

## disassembly

```asm
0x14002abf4  push    rbx
0x14002abf6  sub     rsp, 20h
0x14002abfa  mov     rbx, rcx
0x14002abfd  add     rcx, 70h ; 'p'
0x14002ac01  call    ?Reset@?$TGenericSP@PEAXVTAutoHandleNT@NCoreLibrary@@PEAX$0?0PEBQEAX@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Reset(void)
0x14002ac06  lea     rcx, [rbx+68h]
0x14002ac0a  call    ?Reset@?$TGenericSP@PEAXVTAutoHandleNT@NCoreLibrary@@PEAX$0?0PEBQEAX@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Reset(void)
0x14002ac0f  lea     rcx, [rbx+60h]
0x14002ac13  call    ?Reset@?$TGenericSP@PEAXVTAutoHandleNT@NCoreLibrary@@PEAX$0?0PEBQEAX@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Reset(void)
0x14002ac18  lea     rcx, [rbx+38h]
0x14002ac1c  call    ??1?$deque@V?$TRefSmartPtr@UIShutdownComponent@@@PrnExcept@@V?$allocator@V?$TRefSmartPtr@UIShutdownComponent@@@PrnExcept@@@std@@@std@@QEAA@XZ; std::deque<PrnExcept::TRefSmartPtr<IShutdownComponent>>::~deque<PrnExcept::TRefSmartPtr<IShutdownComponent>>(void)
0x14002ac21  cmp     dword ptr [rbx+30h], 0
0x14002ac25  jl      short loc_14002AC37
0x14002ac27  mov     rcx, rbx; lpCriticalSection
0x14002ac2a  call    cs:__imp_DeleteCriticalSection
0x14002ac30  mov     dword ptr [rbx+30h], 80004005h
0x14002ac37  add     rsp, 20h
0x14002ac3b  pop     rbx
0x14002ac3c  retn
```
