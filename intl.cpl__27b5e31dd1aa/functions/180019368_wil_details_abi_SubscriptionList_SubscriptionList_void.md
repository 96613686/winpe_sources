# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x180019368`
- end: `0x180019396`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18001926c`
- `0x18001929c`

## callees

- `0x1800049cc`
- `0x180019368`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001938f`

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
0x180019368  push    rbx
0x18001936a  sub     rsp, 20h
0x18001936e  mov     rbx, rcx
0x180019371  mov     rcx, [rcx+40h]; this
0x180019375  mov     qword ptr [rbx+40h], 0
0x18001937d  test    rcx, rcx
0x180019380  jz      short loc_180019387
0x180019382  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180019387  mov     rcx, rbx
0x18001938a  add     rsp, 20h
0x18001938e  pop     rbx
0x18001938f  jmp     cs:__imp_DeleteCriticalSection
```
