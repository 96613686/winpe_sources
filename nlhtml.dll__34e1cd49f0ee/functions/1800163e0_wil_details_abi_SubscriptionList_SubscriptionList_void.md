# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x1800163e0`
- end: `0x18001640e`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18001627c`
- `0x1800162ac`

## callees

- `0x1800163e0`
- `0x180016f7c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180016407`

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
0x1800163e0  push    rbx
0x1800163e2  sub     rsp, 20h
0x1800163e6  mov     rbx, rcx
0x1800163e9  mov     rcx, [rcx+40h]; this
0x1800163ed  mov     qword ptr [rbx+40h], 0
0x1800163f5  test    rcx, rcx
0x1800163f8  jz      short loc_1800163FF
0x1800163fa  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x1800163ff  mov     rcx, rbx
0x180016402  add     rsp, 20h
0x180016406  pop     rbx
0x180016407  jmp     cs:__imp_DeleteCriticalSection
```
