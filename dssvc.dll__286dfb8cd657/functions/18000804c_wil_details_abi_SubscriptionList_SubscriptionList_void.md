# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x18000804c`
- end: `0x18000807a`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180007f78`
- `0x180007fa8`

## callees

- `0x18000494c`
- `0x18000804c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008073`

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
0x18000804c  push    rbx
0x18000804e  sub     rsp, 20h
0x180008052  mov     rbx, rcx
0x180008055  mov     rcx, [rcx+40h]; this
0x180008059  mov     qword ptr [rbx+40h], 0
0x180008061  test    rcx, rcx
0x180008064  jz      short loc_18000806B
0x180008066  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18000806b  mov     rcx, rbx
0x18000806e  add     rsp, 20h
0x180008072  pop     rbx
0x180008073  jmp     cs:__imp_DeleteCriticalSection
```
