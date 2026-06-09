# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x180007c5c`
- end: `0x180007c88`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `44`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x180007a20`
- `0x180007a54`
- `0x180024095`
- `0x1800240c4`
- `0x180024534`
- `0x18002458f`
- `0x1800245be`
- `0x180024922`

## callees

- `0x180007d94`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007c7b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007c7b`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall wil::details_abi::SubscriptionList::~SubscriptionList(LPCRITICAL_SECTION lpCriticalSection)
{
  wil::details_abi::heap_buffer::~heap_buffer((wil::details_abi::heap_buffer *)&lpCriticalSection[1]);
  DeleteCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x180007c5c  mov     [rsp+arg_0], rcx
0x180007c61  push    rbx
0x180007c62  sub     rsp, 20h
0x180007c66  mov     rbx, rcx
0x180007c69  add     rcx, 28h ; '('; this
0x180007c6d  mov     [rsp+28h+arg_8], rcx
0x180007c72  call    ??1heap_buffer@details_abi@wil@@QEAA@XZ; wil::details_abi::heap_buffer::~heap_buffer(void)
0x180007c77  nop
0x180007c78  mov     rcx, rbx; lpCriticalSection
0x180007c7b  call    cs:__imp_DeleteCriticalSection
0x180007c81  nop
0x180007c82  add     rsp, 20h
0x180007c86  pop     rbx
0x180007c87  retn
```
