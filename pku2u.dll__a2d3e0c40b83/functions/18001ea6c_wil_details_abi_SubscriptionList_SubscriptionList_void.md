# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x18001ea6c`
- end: `0x18001ea9a`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18001e974`
- `0x180027594`

## callees

- `0x18001ea6c`
- `0x18002584c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001ea93`

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
0x18001ea6c  push    rbx
0x18001ea6e  sub     rsp, 20h
0x18001ea72  mov     rbx, rcx
0x18001ea75  mov     rcx, [rcx+40h]; this
0x18001ea79  mov     qword ptr [rbx+40h], 0
0x18001ea81  test    rcx, rcx
0x18001ea84  jz      short loc_18001EA8B
0x18001ea86  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18001ea8b  mov     rcx, rbx
0x18001ea8e  add     rsp, 20h
0x18001ea92  pop     rbx
0x18001ea93  jmp     cs:__imp_DeleteCriticalSection
```
