# CiFreeValidationContext

- ea: `0x180099118`
- end: `0x18009914d`
- name: `CiFreeValidationContext`
- size: `53`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `9`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180064340`
- `0x180074f04`
- `0x180096f80`
- `0x180098f88`
- `0x180099aa4`
- `0x180099e48`
- `0x18009a008`
- `0x18009acb8`
- `0x1800e5a50`

## callees

- `0x18002c000`

## import_xrefs

- `ntoskrnl!ExFreeToPagedLookasideList` at `0x18009913a`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x18009913a`

## pseudocode

```c
void __fastcall CiFreeValidationContext(void (***Entry)(void))
{
  (*Entry[379])();
  ExFreeToPagedLookasideList(&g_CiValidationLookasideList, Entry);
}

```

## disassembly

```asm
0x180099118  push    rbx
0x18009911a  sub     rsp, 20h
0x18009911e  mov     rax, [rcx+0BD8h]
0x180099125  mov     rbx, rcx
0x180099128  mov     rax, [rax]
0x18009912b  call    _guard_dispatch_icall
0x180099130  mov     rdx, rbx; Entry
0x180099133  lea     rcx, g_CiValidationLookasideList; Lookaside
0x18009913a  call    cs:__imp_ExFreeToPagedLookasideList
0x180099141  nop     dword ptr [rax+rax+00h]
0x180099146  add     rsp, 20h
0x18009914a  pop     rbx
0x18009914b  retn
```
