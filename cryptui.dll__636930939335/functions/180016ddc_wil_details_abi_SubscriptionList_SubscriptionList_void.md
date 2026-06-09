# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x180016ddc`
- end: `0x180016e08`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `44`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x180016ba8`
- `0x180016bdc`
- `0x18003f27b`
- `0x18003f2aa`
- `0x18003f654`
- `0x18003f6af`
- `0x18003f6de`
- `0x18003fb80`

## callees

- `0x180016f1c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180016dfb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180016dfb`

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
0x180016ddc  mov     [rsp+arg_0], rcx
0x180016de1  push    rbx
0x180016de2  sub     rsp, 20h
0x180016de6  mov     rbx, rcx
0x180016de9  add     rcx, 28h ; '('; this
0x180016ded  mov     [rsp+28h+arg_8], rcx
0x180016df2  call    ??1heap_buffer@details_abi@wil@@QEAA@XZ; wil::details_abi::heap_buffer::~heap_buffer(void)
0x180016df7  nop
0x180016df8  mov     rcx, rbx; lpCriticalSection
0x180016dfb  call    cs:__imp_DeleteCriticalSection
0x180016e01  nop
0x180016e02  add     rsp, 20h
0x180016e06  pop     rbx
0x180016e07  retn
```
