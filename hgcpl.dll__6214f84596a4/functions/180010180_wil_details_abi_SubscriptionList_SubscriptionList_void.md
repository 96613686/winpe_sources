# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x180010180`
- end: `0x1800101ae`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800100ac`
- `0x1800100dc`

## callees

- `0x180004d4c`
- `0x180010180`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800101a7`

## pseudocode

```c
void __fastcall wil::details_abi::SubscriptionList::~SubscriptionList(struct _RTL_CRITICAL_SECTION *this, void *a2)
{
  DirectUI *LockSemaphore; // rcx

  LockSemaphore = (DirectUI *)this[1].LockSemaphore;
  this[1].LockSemaphore = 0;
  if ( LockSemaphore )
    DirectUI::HFree(LockSemaphore, a2);
  DeleteCriticalSection(this);
}

```

## disassembly

```asm
0x180010180  push    rbx
0x180010182  sub     rsp, 20h
0x180010186  mov     rbx, rcx
0x180010189  mov     rcx, [rcx+40h]; this
0x18001018d  mov     qword ptr [rbx+40h], 0
0x180010195  test    rcx, rcx
0x180010198  jz      short loc_18001019F
0x18001019a  call    ?HFree@DirectUI@@YAXPEAX@Z; DirectUI::HFree(void *)
0x18001019f  mov     rcx, rbx
0x1800101a2  add     rsp, 20h
0x1800101a6  pop     rbx
0x1800101a7  jmp     cs:__imp_DeleteCriticalSection
```
