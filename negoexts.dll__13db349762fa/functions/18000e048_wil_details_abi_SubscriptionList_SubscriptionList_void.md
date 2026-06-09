# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x18000e048`
- end: `0x18000e076`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000df88`
- `0x180010a14`

## callees

- `0x18000e048`
- `0x18001145c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e06f`

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
0x18000e048  push    rbx
0x18000e04a  sub     rsp, 20h
0x18000e04e  mov     rbx, rcx
0x18000e051  mov     rcx, [rcx+40h]; this
0x18000e055  mov     qword ptr [rbx+40h], 0
0x18000e05d  test    rcx, rcx
0x18000e060  jz      short loc_18000E067
0x18000e062  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18000e067  mov     rcx, rbx
0x18000e06a  add     rsp, 20h
0x18000e06e  pop     rbx
0x18000e06f  jmp     cs:__imp_DeleteCriticalSection
```
