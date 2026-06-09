# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x140007028`
- end: `0x140007056`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140006f2c`
- `0x140006f5c`

## callees

- `0x1400045bc`
- `0x140007028`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000704f`

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
0x140007028  push    rbx
0x14000702a  sub     rsp, 20h
0x14000702e  mov     rbx, rcx
0x140007031  mov     rcx, [rcx+40h]; this
0x140007035  mov     qword ptr [rbx+40h], 0
0x14000703d  test    rcx, rcx
0x140007040  jz      short loc_140007047
0x140007042  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x140007047  mov     rcx, rbx
0x14000704a  add     rsp, 20h
0x14000704e  pop     rbx
0x14000704f  jmp     cs:__imp_DeleteCriticalSection
```
