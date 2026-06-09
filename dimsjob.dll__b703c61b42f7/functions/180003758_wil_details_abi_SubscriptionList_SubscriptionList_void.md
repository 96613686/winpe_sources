# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x180003758`
- end: `0x180003786`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180003698`
- `0x180005ab4`

## callees

- `0x180003758`
- `0x1800064e4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000377f`

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
0x180003758  push    rbx
0x18000375a  sub     rsp, 20h
0x18000375e  mov     rbx, rcx
0x180003761  mov     rcx, [rcx+40h]; this
0x180003765  mov     qword ptr [rbx+40h], 0
0x18000376d  test    rcx, rcx
0x180003770  jz      short loc_180003777
0x180003772  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180003777  mov     rcx, rbx
0x18000377a  add     rsp, 20h
0x18000377e  pop     rbx
0x18000377f  jmp     cs:__imp_DeleteCriticalSection
```
