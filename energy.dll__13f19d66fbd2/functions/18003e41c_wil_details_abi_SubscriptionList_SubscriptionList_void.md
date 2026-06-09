# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x18003e41c`
- end: `0x18003e44a`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18003e35c`
- `0x1800510d0`

## callees

- `0x18003e41c`
- `0x180051e0c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003e443`

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
0x18003e41c  push    rbx
0x18003e41e  sub     rsp, 20h
0x18003e422  mov     rbx, rcx
0x18003e425  mov     rcx, [rcx+40h]; this
0x18003e429  mov     qword ptr [rbx+40h], 0
0x18003e431  test    rcx, rcx
0x18003e434  jz      short loc_18003E43B
0x18003e436  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18003e43b  mov     rcx, rbx
0x18003e43e  add     rsp, 20h
0x18003e442  pop     rbx
0x18003e443  jmp     cs:__imp_DeleteCriticalSection
```
