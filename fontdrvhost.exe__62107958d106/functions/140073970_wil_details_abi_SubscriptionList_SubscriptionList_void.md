# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x140073970`
- end: `0x14007399e`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140066da8`
- `0x140077ddc`

## callees

- `0x140073970`
- `0x14007887c`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x140073997`

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
0x140073970  push    rbx
0x140073972  sub     rsp, 20h
0x140073976  mov     rbx, rcx
0x140073979  mov     rcx, [rcx+40h]; this
0x14007397d  mov     qword ptr [rbx+40h], 0
0x140073985  test    rcx, rcx
0x140073988  jz      short loc_14007398F
0x14007398a  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x14007398f  mov     rcx, rbx
0x140073992  add     rsp, 20h
0x140073996  pop     rbx
0x140073997  jmp     cs:__imp_DeleteCriticalSection
```
