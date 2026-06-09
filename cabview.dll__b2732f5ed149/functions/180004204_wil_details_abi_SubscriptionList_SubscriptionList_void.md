# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x180004204`
- end: `0x180004232`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180004108`
- `0x180004138`

## callees

- `0x180004204`
- `0x180005abc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000422b`

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
0x180004204  push    rbx
0x180004206  sub     rsp, 20h
0x18000420a  mov     rbx, rcx
0x18000420d  mov     rcx, [rcx+40h]; this
0x180004211  mov     qword ptr [rbx+40h], 0
0x180004219  test    rcx, rcx
0x18000421c  jz      short loc_180004223
0x18000421e  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180004223  mov     rcx, rbx
0x180004226  add     rsp, 20h
0x18000422a  pop     rbx
0x18000422b  jmp     cs:__imp_DeleteCriticalSection
```
