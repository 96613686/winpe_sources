# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x180023628`
- end: `0x180023654`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `44`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, void *)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x180023450`
- `0x180023484`
- `0x180039357`
- `0x1800393b2`
- `0x1800393e1`
- `0x1800396d5`
- `0x180039730`
- `0x18003975f`

## callees

- `0x18002373c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180023647`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180023647`

## pseudocode

```c
void __fastcall wil::details_abi::SubscriptionList::~SubscriptionList(LPCRITICAL_SECTION lpCriticalSection, void *a2)
{
  wil::details_abi::heap_buffer::~heap_buffer((wil::details_abi::heap_buffer *)&lpCriticalSection[1], a2);
  DeleteCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x180023628  mov     [rsp+arg_0], rcx
0x18002362d  push    rbx
0x18002362e  sub     rsp, 20h
0x180023632  mov     rbx, rcx
0x180023635  add     rcx, 28h ; '('; this
0x180023639  mov     [rsp+28h+arg_8], rcx
0x18002363e  call    ??1heap_buffer@details_abi@wil@@QEAA@XZ; wil::details_abi::heap_buffer::~heap_buffer(void)
0x180023643  nop
0x180023644  mov     rcx, rbx; lpCriticalSection
0x180023647  call    cs:__imp_DeleteCriticalSection
0x18002364d  nop
0x18002364e  add     rsp, 20h
0x180023652  pop     rbx
0x180023653  retn
```
