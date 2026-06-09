# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x14000443c`
- end: `0x14000446a`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140003f50`
- `0x140007768`

## callees

- `0x14000443c`
- `0x14000886c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140004463`

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
0x14000443c  push    rbx
0x14000443e  sub     rsp, 20h
0x140004442  mov     rbx, rcx
0x140004445  mov     rcx, [rcx+40h]; this
0x140004449  mov     qword ptr [rbx+40h], 0
0x140004451  test    rcx, rcx
0x140004454  jz      short loc_14000445B
0x140004456  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x14000445b  mov     rcx, rbx
0x14000445e  add     rsp, 20h
0x140004462  pop     rbx
0x140004463  jmp     cs:__imp_DeleteCriticalSection
```
