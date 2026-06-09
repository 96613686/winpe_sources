# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x180002d78`
- end: `0x180002da6`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180002c7c`
- `0x180005ff8`

## callees

- `0x180002d78`
- `0x180006b7c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002d9f`

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
0x180002d78  push    rbx
0x180002d7a  sub     rsp, 20h
0x180002d7e  mov     rbx, rcx
0x180002d81  mov     rcx, [rcx+40h]; this
0x180002d85  mov     qword ptr [rbx+40h], 0
0x180002d8d  test    rcx, rcx
0x180002d90  jz      short loc_180002D97
0x180002d92  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180002d97  mov     rcx, rbx
0x180002d9a  add     rsp, 20h
0x180002d9e  pop     rbx
0x180002d9f  jmp     cs:__imp_DeleteCriticalSection
```
