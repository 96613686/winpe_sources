# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x180032470`
- end: `0x18003249e`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180032374`
- `0x1800323a4`

## callees

- `0x180032470`
- `0x180032dcc`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180032497`

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
0x180032470  push    rbx
0x180032472  sub     rsp, 20h
0x180032476  mov     rbx, rcx
0x180032479  mov     rcx, [rcx+40h]; this
0x18003247d  mov     qword ptr [rbx+40h], 0
0x180032485  test    rcx, rcx
0x180032488  jz      short loc_18003248F
0x18003248a  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18003248f  mov     rcx, rbx
0x180032492  add     rsp, 20h
0x180032496  pop     rbx
0x180032497  jmp     cs:__imp_DeleteCriticalSection
```
