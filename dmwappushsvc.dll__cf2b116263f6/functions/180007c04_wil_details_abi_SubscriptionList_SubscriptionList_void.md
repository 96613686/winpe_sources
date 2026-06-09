# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x180007c04`
- end: `0x180007c32`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180007ae0`
- `0x180007b10`

## callees

- `0x180007c04`
- `0x180008794`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007c2b`

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
0x180007c04  push    rbx
0x180007c06  sub     rsp, 20h
0x180007c0a  mov     rbx, rcx
0x180007c0d  mov     rcx, [rcx+40h]; this
0x180007c11  mov     qword ptr [rbx+40h], 0
0x180007c19  test    rcx, rcx
0x180007c1c  jz      short loc_180007C23
0x180007c1e  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180007c23  mov     rcx, rbx
0x180007c26  add     rsp, 20h
0x180007c2a  pop     rbx
0x180007c2b  jmp     cs:__imp_DeleteCriticalSection
```
