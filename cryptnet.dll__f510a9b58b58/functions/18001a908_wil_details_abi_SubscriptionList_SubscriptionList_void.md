# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x18001a908`
- end: `0x18001a936`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18001a840`
- `0x180020ef4`

## callees

- `0x18001a908`
- `0x18002181c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001a92f`

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
0x18001a908  push    rbx
0x18001a90a  sub     rsp, 20h
0x18001a90e  mov     rbx, rcx
0x18001a911  mov     rcx, [rcx+40h]; this
0x18001a915  mov     qword ptr [rbx+40h], 0
0x18001a91d  test    rcx, rcx
0x18001a920  jz      short loc_18001A927
0x18001a922  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18001a927  mov     rcx, rbx
0x18001a92a  add     rsp, 20h
0x18001a92e  pop     rbx
0x18001a92f  jmp     cs:__imp_DeleteCriticalSection
```
