# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x1800036cc`
- end: `0x1800036fa`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180003570`
- `0x1800035a0`

## callees

- `0x1800036cc`
- `0x18000411c`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800036f3`

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
0x1800036cc  push    rbx
0x1800036ce  sub     rsp, 20h
0x1800036d2  mov     rbx, rcx
0x1800036d5  mov     rcx, [rcx+40h]; this
0x1800036d9  mov     qword ptr [rbx+40h], 0
0x1800036e1  test    rcx, rcx
0x1800036e4  jz      short loc_1800036EB
0x1800036e6  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x1800036eb  mov     rcx, rbx
0x1800036ee  add     rsp, 20h
0x1800036f2  pop     rbx
0x1800036f3  jmp     cs:__imp_DeleteCriticalSection
```
