# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x18000d29c`
- end: `0x18000d2ca`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000d194`
- `0x1800121e0`

## callees

- `0x18000d29c`
- `0x180012bfc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d2c3`

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
0x18000d29c  push    rbx
0x18000d29e  sub     rsp, 20h
0x18000d2a2  mov     rbx, rcx
0x18000d2a5  mov     rcx, [rcx+40h]; this
0x18000d2a9  mov     qword ptr [rbx+40h], 0
0x18000d2b1  test    rcx, rcx
0x18000d2b4  jz      short loc_18000D2BB
0x18000d2b6  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18000d2bb  mov     rcx, rbx
0x18000d2be  add     rsp, 20h
0x18000d2c2  pop     rbx
0x18000d2c3  jmp     cs:__imp_DeleteCriticalSection
```
