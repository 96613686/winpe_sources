# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x18000ca24`
- end: `0x18000ca52`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000c964`
- `0x180012814`

## callees

- `0x180002a8c`
- `0x18000ca24`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000ca4b`

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
0x18000ca24  push    rbx
0x18000ca26  sub     rsp, 20h
0x18000ca2a  mov     rbx, rcx
0x18000ca2d  mov     rcx, [rcx+40h]; this
0x18000ca31  mov     qword ptr [rbx+40h], 0
0x18000ca39  test    rcx, rcx
0x18000ca3c  jz      short loc_18000CA43
0x18000ca3e  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18000ca43  mov     rcx, rbx
0x18000ca46  add     rsp, 20h
0x18000ca4a  pop     rbx
0x18000ca4b  jmp     cs:__imp_DeleteCriticalSection
```
