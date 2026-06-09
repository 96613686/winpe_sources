# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x1800061bc`
- end: `0x1800061ea`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180006098`
- `0x1800060c8`

## callees

- `0x1800061bc`
- `0x18000745c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800061e3`

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
0x1800061bc  push    rbx
0x1800061be  sub     rsp, 20h
0x1800061c2  mov     rbx, rcx
0x1800061c5  mov     rcx, [rcx+40h]; this
0x1800061c9  mov     qword ptr [rbx+40h], 0
0x1800061d1  test    rcx, rcx
0x1800061d4  jz      short loc_1800061DB
0x1800061d6  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x1800061db  mov     rcx, rbx
0x1800061de  add     rsp, 20h
0x1800061e2  pop     rbx
0x1800061e3  jmp     cs:__imp_DeleteCriticalSection
```
