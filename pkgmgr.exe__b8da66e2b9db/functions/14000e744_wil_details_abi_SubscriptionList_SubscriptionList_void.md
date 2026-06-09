# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x14000e744`
- end: `0x14000e772`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14000e670`
- `0x14000e6a0`

## callees

- `0x14000438c`
- `0x14000e744`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000e76b`

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
0x14000e744  push    rbx
0x14000e746  sub     rsp, 20h
0x14000e74a  mov     rbx, rcx
0x14000e74d  mov     rcx, [rcx+40h]; this
0x14000e751  mov     qword ptr [rbx+40h], 0
0x14000e759  test    rcx, rcx
0x14000e75c  jz      short loc_14000E763
0x14000e75e  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x14000e763  mov     rcx, rbx
0x14000e766  add     rsp, 20h
0x14000e76a  pop     rbx
0x14000e76b  jmp     cs:__imp_DeleteCriticalSection
```
