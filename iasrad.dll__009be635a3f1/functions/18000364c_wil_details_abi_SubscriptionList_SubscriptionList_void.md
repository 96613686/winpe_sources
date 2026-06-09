# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x18000364c`
- end: `0x18000367a`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800034f0`
- `0x180003520`

## callees

- `0x18000364c`
- `0x1800041bc`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180003673`

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
0x18000364c  push    rbx
0x18000364e  sub     rsp, 20h
0x180003652  mov     rbx, rcx
0x180003655  mov     rcx, [rcx+40h]; this
0x180003659  mov     qword ptr [rbx+40h], 0
0x180003661  test    rcx, rcx
0x180003664  jz      short loc_18000366B
0x180003666  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18000366b  mov     rcx, rbx
0x18000366e  add     rsp, 20h
0x180003672  pop     rbx
0x180003673  jmp     cs:__imp_DeleteCriticalSection
```
