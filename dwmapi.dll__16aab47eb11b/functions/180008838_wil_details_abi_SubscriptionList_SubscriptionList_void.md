# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x180008838`
- end: `0x180008866`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180008730`
- `0x18000e65c`

## callees

- `0x180008838`
- `0x18000ee4c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000885f`

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
0x180008838  push    rbx
0x18000883a  sub     rsp, 20h
0x18000883e  mov     rbx, rcx
0x180008841  mov     rcx, [rcx+40h]; this
0x180008845  mov     qword ptr [rbx+40h], 0
0x18000884d  test    rcx, rcx
0x180008850  jz      short loc_180008857
0x180008852  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180008857  mov     rcx, rbx
0x18000885a  add     rsp, 20h
0x18000885e  pop     rbx
0x18000885f  jmp     cs:__imp_DeleteCriticalSection
```
