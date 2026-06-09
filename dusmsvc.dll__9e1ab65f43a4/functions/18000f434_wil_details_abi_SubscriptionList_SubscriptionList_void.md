# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x18000f434`
- end: `0x18000f462`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000f338`
- `0x18000f368`

## callees

- `0x18000af40`
- `0x18000f434`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000f45b`

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
0x18000f434  push    rbx
0x18000f436  sub     rsp, 20h
0x18000f43a  mov     rbx, rcx
0x18000f43d  mov     rcx, [rcx+40h]; this
0x18000f441  mov     qword ptr [rbx+40h], 0
0x18000f449  test    rcx, rcx
0x18000f44c  jz      short loc_18000F453
0x18000f44e  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18000f453  mov     rcx, rbx
0x18000f456  add     rsp, 20h
0x18000f45a  pop     rbx
0x18000f45b  jmp     cs:__imp_DeleteCriticalSection
```
