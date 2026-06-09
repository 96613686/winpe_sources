# CiFreeValidationContext

- ea: `0x18009df48`
- end: `0x18009df7d`
- name: `CiFreeValidationContext`
- size: `53`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `9`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1800644b0`
- `0x1800751e4`
- `0x18008d750`
- `0x18009ddb8`
- `0x18009e8d4`
- `0x18009e9b0`
- `0x18009f338`
- `0x18009fff8`
- `0x1800e5fd0`

## callees

- `0x18002c1b0`

## import_xrefs

- `ntoskrnl!ExFreeToPagedLookasideList` at `0x18009df6a`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x18009df6a`

## pseudocode

```c
void __fastcall CiFreeValidationContext(void (***Entry)(void))
{
  (*Entry[380])();
  ExFreeToPagedLookasideList(&g_CiValidationLookasideList, Entry);
}

```

## disassembly

```asm
0x18009df48  push    rbx
0x18009df4a  sub     rsp, 20h
0x18009df4e  mov     rax, [rcx+0BE0h]
0x18009df55  mov     rbx, rcx
0x18009df58  mov     rax, [rax]
0x18009df5b  call    _guard_dispatch_icall
0x18009df60  mov     rdx, rbx; Entry
0x18009df63  lea     rcx, g_CiValidationLookasideList; Lookaside
0x18009df6a  call    cs:__imp_ExFreeToPagedLookasideList
0x18009df71  nop     dword ptr [rax+rax+00h]
0x18009df76  add     rsp, 20h
0x18009df7a  pop     rbx
0x18009df7b  retn
```
