# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x18000cf80`
- end: `0x18000cfae`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000cec0`
- `0x180012084`

## callees

- `0x18000cf80`
- `0x18001294c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000cfa7`

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
0x18000cf80  push    rbx
0x18000cf82  sub     rsp, 20h
0x18000cf86  mov     rbx, rcx
0x18000cf89  mov     rcx, [rcx+40h]; this
0x18000cf8d  mov     qword ptr [rbx+40h], 0
0x18000cf95  test    rcx, rcx
0x18000cf98  jz      short loc_18000CF9F
0x18000cf9a  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18000cf9f  mov     rcx, rbx
0x18000cfa2  add     rsp, 20h
0x18000cfa6  pop     rbx
0x18000cfa7  jmp     cs:__imp_DeleteCriticalSection
```
