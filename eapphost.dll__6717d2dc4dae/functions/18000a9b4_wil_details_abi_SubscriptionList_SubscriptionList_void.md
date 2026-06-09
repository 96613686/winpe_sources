# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x18000a9b4`
- end: `0x18000a9e2`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a8b8`
- `0x18000a8e8`

## callees

- `0x18000730c`
- `0x18000a9b4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a9db`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
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
0x18000a9b4  push    rbx
0x18000a9b6  sub     rsp, 20h
0x18000a9ba  mov     rbx, rcx
0x18000a9bd  mov     rcx, [rcx+40h]; this
0x18000a9c1  mov     qword ptr [rbx+40h], 0
0x18000a9c9  test    rcx, rcx
0x18000a9cc  jz      short loc_18000A9D3
0x18000a9ce  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18000a9d3  mov     rcx, rbx
0x18000a9d6  add     rsp, 20h
0x18000a9da  pop     rbx
0x18000a9db  jmp     cs:__imp_DeleteCriticalSection
```
