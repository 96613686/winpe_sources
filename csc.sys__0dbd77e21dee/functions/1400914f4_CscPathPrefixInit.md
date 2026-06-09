# CscPathPrefixInit

- ea: `0x1400914f4`
- end: `0x140091564`
- name: `CscPathPrefixInit`
- size: `112`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation`

## callers

- `0x140090740`

## import_xrefs

- `ntoskrnl!ExInitializePagedLookasideList` at `0x14009154f`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14009154f`
- `ntoskrnl!ExFreePool` at `0x140091509`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140091514`
- `ntoskrnl!ExInitializeResourceLite` at `0x1400914fd`
- `ntoskrnl!ExInitializeResourceLite` at `0x1400914fd`

## pseudocode

```c
__int64 __fastcall CscPathPrefixInit(__int64 a1)
{
  ExInitializeResourceLite((PERESOURCE)a1);
  *(_QWORD *)(a1 + 112) = a1 + 104;
  *(_QWORD *)(a1 + 104) = a1 + 104;
  *(_QWORD *)(a1 + 128) = a1 + 120;
  *(_QWORD *)(a1 + 120) = a1 + 120;
  ExInitializePagedLookasideList(
    (PPAGED_LOOKASIDE_LIST)(a1 + 192),
    ExAllocatePoolWithTag,
    ExFreePool,
    0,
    0x68u,
    0x43534350u,
    0);
  return 0;
}

```

## disassembly

```asm
0x1400914f4  push    rbx
0x1400914f6  sub     rsp, 40h
0x1400914fa  mov     rbx, rcx
0x1400914fd  call    cs:__imp_ExInitializeResourceLite
0x140091504  nop     dword ptr [rax+rax+00h]
0x140091509  mov     r8, cs:__imp_ExFreePool; Free
0x140091510  lea     rax, [rbx+68h]
0x140091514  mov     rdx, cs:__imp_ExAllocatePoolWithTag; Allocate
0x14009151b  lea     rcx, [rbx+0C0h]; Lookaside
0x140091522  mov     [rax+8], rax
0x140091526  xor     r9d, r9d; Flags
0x140091529  mov     [rax], rax
0x14009152c  lea     rax, [rbx+78h]
0x140091530  mov     [rax+8], rax
0x140091534  mov     [rax], rax
0x140091537  xor     eax, eax
0x140091539  mov     [rsp+48h+Depth], ax; Depth
0x14009153e  mov     [rsp+48h+Tag], 43534350h; Tag
0x140091546  mov     [rsp+48h+Size], 68h ; 'h'; Size
0x14009154f  call    cs:__imp_ExInitializePagedLookasideList
0x140091556  nop     dword ptr [rax+rax+00h]
0x14009155b  xor     eax, eax
0x14009155d  add     rsp, 40h
0x140091561  pop     rbx
0x140091562  retn
```
