# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x180007ebc`
- end: `0x180007eea`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180007d58`
- `0x180007d88`

## callees

- `0x180007ebc`
- `0x18000897c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007ee3`

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
0x180007ebc  push    rbx
0x180007ebe  sub     rsp, 20h
0x180007ec2  mov     rbx, rcx
0x180007ec5  mov     rcx, [rcx+40h]; this
0x180007ec9  mov     qword ptr [rbx+40h], 0
0x180007ed1  test    rcx, rcx
0x180007ed4  jz      short loc_180007EDB
0x180007ed6  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180007edb  mov     rcx, rbx
0x180007ede  add     rsp, 20h
0x180007ee2  pop     rbx
0x180007ee3  jmp     cs:__imp_DeleteCriticalSection
```
