# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x180017aec`
- end: `0x180017b1b`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `47`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800179e8`
- `0x180017a18`

## callees

- `0x180009d9c`
- `0x180017aec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180017b14`

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
0x180017aec  push    rbx
0x180017aee  sub     rsp, 20h
0x180017af2  mov     rbx, rcx
0x180017af5  mov     rcx, [rcx+40h]; this
0x180017af9  mov     qword ptr [rbx+40h], 0
0x180017b01  test    rcx, rcx
0x180017b04  jz      short loc_180017B0C
0x180017b06  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180017b0b  nop
0x180017b0c  mov     rcx, rbx
0x180017b0f  add     rsp, 20h
0x180017b13  pop     rbx
0x180017b14  jmp     cs:__imp_DeleteCriticalSection
```
