# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x18000324c`
- end: `0x18000327a`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180003160`
- `0x18000c820`

## callees

- `0x18000324c`
- `0x1800041b8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003273`

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
0x18000324c  push    rbx
0x18000324e  sub     rsp, 20h
0x180003252  mov     rbx, rcx
0x180003255  mov     rcx, [rcx+40h]; this
0x180003259  mov     qword ptr [rbx+40h], 0
0x180003261  test    rcx, rcx
0x180003264  jz      short loc_18000326B
0x180003266  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18000326b  mov     rcx, rbx
0x18000326e  add     rsp, 20h
0x180003272  pop     rbx
0x180003273  jmp     cs:__imp_DeleteCriticalSection
```
