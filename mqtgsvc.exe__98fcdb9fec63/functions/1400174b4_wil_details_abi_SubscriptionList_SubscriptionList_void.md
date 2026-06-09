# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x1400174b4`
- end: `0x1400174e4`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `48`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140017350`
- `0x140017380`

## callees

- `0x1400174b4`
- `0x14001801c`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1400174d7`
- `KERNEL32!DeleteCriticalSection` at `0x1400174d7`

## pseudocode

```c
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
0x1400174b4  push    rbx
0x1400174b6  sub     rsp, 20h
0x1400174ba  mov     rbx, rcx
0x1400174bd  mov     rcx, [rcx+40h]; this
0x1400174c1  mov     qword ptr [rbx+40h], 0
0x1400174c9  test    rcx, rcx
0x1400174cc  jz      short loc_1400174D4
0x1400174ce  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x1400174d3  nop
0x1400174d4  mov     rcx, rbx; lpCriticalSection
0x1400174d7  call    cs:__imp_DeleteCriticalSection
0x1400174dd  nop
0x1400174de  add     rsp, 20h
0x1400174e2  pop     rbx
0x1400174e3  retn
```
