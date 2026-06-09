# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x18000d7a4`
- end: `0x18000d7d2`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000d6e4`
- `0x180011250`

## callees

- `0x18000d7a4`
- `0x18000f344`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000d7cb`

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
0x18000d7a4  push    rbx
0x18000d7a6  sub     rsp, 20h
0x18000d7aa  mov     rbx, rcx
0x18000d7ad  mov     rcx, [rcx+40h]; this
0x18000d7b1  mov     qword ptr [rbx+40h], 0
0x18000d7b9  test    rcx, rcx
0x18000d7bc  jz      short loc_18000D7C3
0x18000d7be  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18000d7c3  mov     rcx, rbx
0x18000d7c6  add     rsp, 20h
0x18000d7ca  pop     rbx
0x18000d7cb  jmp     cs:__imp_DeleteCriticalSection
```
