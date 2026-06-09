# CiFreeValidationContext

- ea: `0x180097ae8`
- end: `0x180097b1d`
- name: `CiFreeValidationContext`
- size: `53`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `9`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180063a10`
- `0x180073c54`
- `0x180095950`
- `0x180097958`
- `0x180098474`
- `0x180098818`
- `0x1800989d8`
- `0x180099688`
- `0x1800e55e0`

## callees

- `0x18002bfd0`

## import_xrefs

- `ntoskrnl!ExFreeToPagedLookasideList` at `0x180097b0a`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x180097b0a`

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
0x180097ae8  push    rbx
0x180097aea  sub     rsp, 20h
0x180097aee  mov     rax, [rcx+0BD8h]
0x180097af5  mov     rbx, rcx
0x180097af8  mov     rax, [rax]
0x180097afb  call    _guard_dispatch_icall
0x180097b00  mov     rdx, rbx; Entry
0x180097b03  lea     rcx, g_CiValidationLookasideList; Lookaside
0x180097b0a  call    cs:__imp_ExFreeToPagedLookasideList
0x180097b11  nop     dword ptr [rax+rax+00h]
0x180097b16  add     rsp, 20h
0x180097b1a  pop     rbx
0x180097b1b  retn
```
