# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x180004a58`
- end: `0x180004a86`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800048a8`
- `0x1800048d8`

## callees

- `0x180004a58`
- `0x1800089f0`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180004a7f`

## pseudocode

```c
void __fastcall wil::details_abi::SubscriptionList::~SubscriptionList(struct _RTL_CRITICAL_SECTION *this)
{
  HANDLE LockSemaphore; // rcx

  LockSemaphore = this[1].LockSemaphore;
  this[1].LockSemaphore = 0;
  if ( LockSemaphore )
    MemoryFree(LockSemaphore);
  DeleteCriticalSection(this);
}

```

## disassembly

```asm
0x180004a58  push    rbx
0x180004a5a  sub     rsp, 20h
0x180004a5e  mov     rbx, rcx
0x180004a61  mov     rcx, [rcx+40h]; void *
0x180004a65  mov     qword ptr [rbx+40h], 0
0x180004a6d  test    rcx, rcx
0x180004a70  jz      short loc_180004A77
0x180004a72  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x180004a77  mov     rcx, rbx
0x180004a7a  add     rsp, 20h
0x180004a7e  pop     rbx
0x180004a7f  jmp     cs:__imp_DeleteCriticalSection
```
