# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x180003a40`
- end: `0x180003a70`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `48`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800038dc`
- `0x18000390c`

## callees

- `0x180003a40`
- `0x18000459c`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180003a63`
- `KERNEL32!DeleteCriticalSection` at `0x180003a63`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details_abi::SubscriptionList::~SubscriptionList(LPCRITICAL_SECTION lpCriticalSection, void *a2)
{
  wil::details *LockSemaphore; // rcx

  LockSemaphore = (wil::details *)lpCriticalSection[1].LockSemaphore;
  lpCriticalSection[1].LockSemaphore = 0;
  if ( LockSemaphore )
    wil::details::FreeProcessHeap(LockSemaphore, a2);
  DeleteCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x180003a40  push    rbx
0x180003a42  sub     rsp, 20h
0x180003a46  mov     rbx, rcx
0x180003a49  mov     rcx, [rcx+40h]; this
0x180003a4d  mov     qword ptr [rbx+40h], 0
0x180003a55  test    rcx, rcx
0x180003a58  jz      short loc_180003A60
0x180003a5a  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180003a5f  nop
0x180003a60  mov     rcx, rbx; lpCriticalSection
0x180003a63  call    cs:__imp_DeleteCriticalSection
0x180003a69  nop
0x180003a6a  add     rsp, 20h
0x180003a6e  pop     rbx
0x180003a6f  retn
```
