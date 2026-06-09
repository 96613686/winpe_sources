# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x180004b50`
- end: `0x180004b7e`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180004a54`
- `0x180004a84`

## callees

- `0x180004b50`
- `0x18000563c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004b77`

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
0x180004b50  push    rbx
0x180004b52  sub     rsp, 20h
0x180004b56  mov     rbx, rcx
0x180004b59  mov     rcx, [rcx+40h]; this
0x180004b5d  mov     qword ptr [rbx+40h], 0
0x180004b65  test    rcx, rcx
0x180004b68  jz      short loc_180004B6F
0x180004b6a  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180004b6f  mov     rcx, rbx
0x180004b72  add     rsp, 20h
0x180004b76  pop     rbx
0x180004b77  jmp     cs:__imp_DeleteCriticalSection
```
