# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x1400053b0`
- end: `0x1400053de`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140005254`
- `0x140005284`

## callees

- `0x1400053b0`
- `0x1400063dc`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1400053d7`

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
0x1400053b0  push    rbx
0x1400053b2  sub     rsp, 20h
0x1400053b6  mov     rbx, rcx
0x1400053b9  mov     rcx, [rcx+40h]; this
0x1400053bd  mov     qword ptr [rbx+40h], 0
0x1400053c5  test    rcx, rcx
0x1400053c8  jz      short loc_1400053CF
0x1400053ca  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x1400053cf  mov     rcx, rbx
0x1400053d2  add     rsp, 20h
0x1400053d6  pop     rbx
0x1400053d7  jmp     cs:__imp_DeleteCriticalSection
```
