# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x180027d28`
- end: `0x180027d57`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `47`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180027bc8`
- `0x180027bf8`

## callees

- `0x180027d28`
- `0x180028f2c`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180027d50`

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
0x180027d28  push    rbx
0x180027d2a  sub     rsp, 20h
0x180027d2e  mov     rbx, rcx
0x180027d31  mov     rcx, [rcx+40h]; this
0x180027d35  mov     qword ptr [rbx+40h], 0
0x180027d3d  test    rcx, rcx
0x180027d40  jz      short loc_180027D48
0x180027d42  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180027d47  nop
0x180027d48  mov     rcx, rbx
0x180027d4b  add     rsp, 20h
0x180027d4f  pop     rbx
0x180027d50  jmp     cs:__imp_DeleteCriticalSection
```
