# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x18000ade4`
- end: `0x18000ae12`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ad24`
- `0x1800123c8`

## callees

- `0x18000ade4`
- `0x180012f6c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000ae0b`

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
0x18000ade4  push    rbx
0x18000ade6  sub     rsp, 20h
0x18000adea  mov     rbx, rcx
0x18000aded  mov     rcx, [rcx+40h]; this
0x18000adf1  mov     qword ptr [rbx+40h], 0
0x18000adf9  test    rcx, rcx
0x18000adfc  jz      short loc_18000AE03
0x18000adfe  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18000ae03  mov     rcx, rbx
0x18000ae06  add     rsp, 20h
0x18000ae0a  pop     rbx
0x18000ae0b  jmp     cs:__imp_DeleteCriticalSection
```
