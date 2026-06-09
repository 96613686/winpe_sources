# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x180005f10`
- end: `0x180005f40`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `48`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180005dac`
- `0x180005ddc`

## callees

- `0x180005f10`
- `0x18000695c`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180005f33`
- `KERNEL32!DeleteCriticalSection` at `0x180005f33`

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
0x180005f10  push    rbx
0x180005f12  sub     rsp, 20h
0x180005f16  mov     rbx, rcx
0x180005f19  mov     rcx, [rcx+40h]; this
0x180005f1d  mov     qword ptr [rbx+40h], 0
0x180005f25  test    rcx, rcx
0x180005f28  jz      short loc_180005F30
0x180005f2a  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180005f2f  nop
0x180005f30  mov     rcx, rbx; lpCriticalSection
0x180005f33  call    cs:__imp_DeleteCriticalSection
0x180005f39  nop
0x180005f3a  add     rsp, 20h
0x180005f3e  pop     rbx
0x180005f3f  retn
```
