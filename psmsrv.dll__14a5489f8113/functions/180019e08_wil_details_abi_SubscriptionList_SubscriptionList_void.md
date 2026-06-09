# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x180019e08`
- end: `0x180019e36`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180017bac`
- `0x180026588`

## callees

- `0x180019e08`
- `0x180026fbc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180019e2f`

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
0x180019e08  push    rbx
0x180019e0a  sub     rsp, 20h
0x180019e0e  mov     rbx, rcx
0x180019e11  mov     rcx, [rcx+40h]; this
0x180019e15  mov     qword ptr [rbx+40h], 0
0x180019e1d  test    rcx, rcx
0x180019e20  jz      short loc_180019E27
0x180019e22  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180019e27  mov     rcx, rbx
0x180019e2a  add     rsp, 20h
0x180019e2e  pop     rbx
0x180019e2f  jmp     cs:__imp_DeleteCriticalSection
```
