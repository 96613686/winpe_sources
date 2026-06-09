# CscPathPrefixCleanup

- ea: `0x140053300`
- end: `0x14005332f`
- name: `CscPathPrefixCleanup`
- size: `47`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation`

## callers

- `0x140090740`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x140053309`
- `ntoskrnl!ExDeleteResourceLite` at `0x140053309`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14005331c`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14005331c`

## pseudocode

```c
void __fastcall CscPathPrefixCleanup(__int64 a1)
{
  ExDeleteResourceLite((PERESOURCE)a1);
  ExDeletePagedLookasideList((PPAGED_LOOKASIDE_LIST)(a1 + 192));
}

```

## disassembly

```asm
0x140053300  push    rbx
0x140053302  sub     rsp, 20h
0x140053306  mov     rbx, rcx
0x140053309  call    cs:__imp_ExDeleteResourceLite
0x140053310  nop     dword ptr [rax+rax+00h]
0x140053315  lea     rcx, [rbx+0C0h]; Lookaside
0x14005331c  call    cs:__imp_ExDeletePagedLookasideList
0x140053323  nop     dword ptr [rax+rax+00h]
0x140053328  add     rsp, 20h
0x14005332c  pop     rbx
0x14005332d  retn
```
