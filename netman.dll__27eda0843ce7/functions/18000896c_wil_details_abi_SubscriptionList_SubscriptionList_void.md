# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x18000896c`
- end: `0x18000899a`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800087f4`
- `0x180008824`

## callees

- `0x18000896c`
- `0x1800101d4`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180008993`

## pseudocode

```c
void __fastcall wil::details_abi::SubscriptionList::~SubscriptionList(struct _RTL_CRITICAL_SECTION *this, void *a2)
{
  wil::details *LockSemaphore; // rcx

  LockSemaphore = (wil::details *)this[1].LockSemaphore;
  this[1].LockSemaphore = 0;
  if ( LockSemaphore )
    wil::details::FreeProcessHeap(LockSemaphore, a2);
  DeleteCriticalSection(this);
}

```

## disassembly

```asm
0x18000896c  push    rbx
0x18000896e  sub     rsp, 20h
0x180008972  mov     rbx, rcx
0x180008975  mov     rcx, [rcx+40h]; this
0x180008979  mov     qword ptr [rbx+40h], 0
0x180008981  test    rcx, rcx
0x180008984  jz      short loc_18000898B
0x180008986  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18000898b  mov     rcx, rbx
0x18000898e  add     rsp, 20h
0x180008992  pop     rbx
0x180008993  jmp     cs:__imp_DeleteCriticalSection
```
