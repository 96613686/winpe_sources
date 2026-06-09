# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x18007824c`
- end: `0x18007827f`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `51`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180078150`
- `0x180078180`

## callees

- `0x18007824c`
- `0x180079004`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180078273`

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
0x18007824c  push    rbx
0x18007824e  sub     rsp, 20h
0x180078252  mov     rbx, rcx
0x180078255  mov     rcx, [rcx+40h]; this
0x180078259  mov     qword ptr [rbx+40h], 0
0x180078261  test    rcx, rcx
0x180078264  jz      short loc_18007826B
0x180078266  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18007826b  mov     rcx, rbx
0x18007826e  add     rsp, 20h
0x180078272  pop     rbx
0x180078273  jmp     cs:__imp_DeleteCriticalSection
```
