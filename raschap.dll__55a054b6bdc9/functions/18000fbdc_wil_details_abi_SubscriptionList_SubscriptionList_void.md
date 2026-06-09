# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x18000fbdc`
- end: `0x18000fc0b`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `47`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000fae4`
- `0x18001f138`

## callees

- `0x18000fbdc`
- `0x18001fe7c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000fc04`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x18000fbdc  push    rbx
0x18000fbde  sub     rsp, 20h
0x18000fbe2  mov     rbx, rcx
0x18000fbe5  mov     rcx, [rcx+40h]; this
0x18000fbe9  mov     qword ptr [rbx+40h], 0
0x18000fbf1  test    rcx, rcx
0x18000fbf4  jz      short loc_18000FBFC
0x18000fbf6  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18000fbfb  nop
0x18000fbfc  mov     rcx, rbx
0x18000fbff  add     rsp, 20h
0x18000fc03  pop     rbx
0x18000fc04  jmp     cs:__imp_DeleteCriticalSection
```
