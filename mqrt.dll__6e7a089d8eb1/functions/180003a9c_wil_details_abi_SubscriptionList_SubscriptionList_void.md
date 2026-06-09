# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x180003a9c`
- end: `0x180003acc`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `48`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180003938`
- `0x180003968`

## callees

- `0x180003a9c`
- `0x1800044ac`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180003abf`
- `KERNEL32!DeleteCriticalSection` at `0x180003abf`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details_abi::SubscriptionList::~SubscriptionList(LPCRITICAL_SECTION lpCriticalSection, void *a2)
{
  wil::details *LockSemaphore; // rcx

  LockSemaphore = (wil::details *)lpCriticalSection[1].LockSemaphore;
  lpCriticalSection[1].LockSemaphore = 0;
  if ( LockSemaphore )
    wil::details::FreeProcessHeap(LockSemaphore, a2);
  DeleteCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x180003a9c  push    rbx
0x180003a9e  sub     rsp, 20h
0x180003aa2  mov     rbx, rcx
0x180003aa5  mov     rcx, [rcx+40h]; this
0x180003aa9  mov     qword ptr [rbx+40h], 0
0x180003ab1  test    rcx, rcx
0x180003ab4  jz      short loc_180003ABC
0x180003ab6  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180003abb  nop
0x180003abc  mov     rcx, rbx; lpCriticalSection
0x180003abf  call    cs:__imp_DeleteCriticalSection
0x180003ac5  nop
0x180003ac6  add     rsp, 20h
0x180003aca  pop     rbx
0x180003acb  retn
```
