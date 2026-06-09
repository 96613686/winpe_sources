# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x1800105b0`
- end: `0x1800105e3`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `51`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800104b8`
- `0x180018908`

## callees

- `0x1800105b0`
- `0x180019834`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800105d7`

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
0x1800105b0  push    rbx
0x1800105b2  sub     rsp, 20h
0x1800105b6  mov     rbx, rcx
0x1800105b9  mov     rcx, [rcx+40h]; this
0x1800105bd  mov     qword ptr [rbx+40h], 0
0x1800105c5  test    rcx, rcx
0x1800105c8  jz      short loc_1800105CF
0x1800105ca  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x1800105cf  mov     rcx, rbx
0x1800105d2  add     rsp, 20h
0x1800105d6  pop     rbx
0x1800105d7  jmp     cs:__imp_DeleteCriticalSection
```
