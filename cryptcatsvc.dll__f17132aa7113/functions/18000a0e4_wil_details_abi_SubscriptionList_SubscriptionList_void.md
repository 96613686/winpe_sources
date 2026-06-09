# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x18000a0e4`
- end: `0x18000a112`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a024`
- `0x18000de58`

## callees

- `0x18000a0e4`
- `0x18000e9fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a10b`

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
0x18000a0e4  push    rbx
0x18000a0e6  sub     rsp, 20h
0x18000a0ea  mov     rbx, rcx
0x18000a0ed  mov     rcx, [rcx+40h]; this
0x18000a0f1  mov     qword ptr [rbx+40h], 0
0x18000a0f9  test    rcx, rcx
0x18000a0fc  jz      short loc_18000A103
0x18000a0fe  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18000a103  mov     rcx, rbx
0x18000a106  add     rsp, 20h
0x18000a10a  pop     rbx
0x18000a10b  jmp     cs:__imp_DeleteCriticalSection
```
