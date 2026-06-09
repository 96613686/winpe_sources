# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x18000ae38`
- end: `0x18000ae6b`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `51`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ad38`
- `0x18000ad68`

## callees

- `0x1800075a8`
- `0x18000ae38`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000ae5f`

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
0x18000ae38  push    rbx
0x18000ae3a  sub     rsp, 20h
0x18000ae3e  mov     rbx, rcx
0x18000ae41  mov     rcx, [rcx+40h]; this
0x18000ae45  mov     qword ptr [rbx+40h], 0
0x18000ae4d  test    rcx, rcx
0x18000ae50  jz      short loc_18000AE57
0x18000ae52  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18000ae57  mov     rcx, rbx
0x18000ae5a  add     rsp, 20h
0x18000ae5e  pop     rbx
0x18000ae5f  jmp     cs:__imp_DeleteCriticalSection
```
