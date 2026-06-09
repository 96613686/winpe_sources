# CldHsmDeleteFileContext

- ea: `0x1400744d0`
- end: `0x140074512`
- name: `CldHsmDeleteFileContext`
- size: `66`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, authz_impersonation`

## callees

- `0x1400744d0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140074504`
- `ntoskrnl!ExFreePoolWithTag` at `0x140074504`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400744ec`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400744ec`

## pseudocode

```c
void __fastcall CldHsmDeleteFileContext(_QWORD *Entry)
{
  void *v2; // rcx

  v2 = (void *)Entry[7];
  if ( v2 )
    ExFreePoolWithTag(v2, 0x53536C43u);
  ExFreeToPagedLookasideList(&stru_140028A80, Entry);
}

```

## disassembly

```asm
0x1400744d0  push    rbx
0x1400744d2  sub     rsp, 20h
0x1400744d6  mov     rbx, rcx
0x1400744d9  mov     rcx, [rcx+38h]; P
0x1400744dd  test    rcx, rcx
0x1400744e0  jnz     short loc_1400744FF
0x1400744e2  mov     rdx, rbx; Entry
0x1400744e5  lea     rcx, stru_140028A80; Lookaside
0x1400744ec  call    cs:__imp_ExFreeToPagedLookasideList
0x1400744f3  nop     dword ptr [rax+rax+00h]
0x1400744f8  add     rsp, 20h
0x1400744fc  pop     rbx
0x1400744fd  retn
0x1400744ff  mov     edx, 53536C43h; Tag
0x140074504  call    cs:__imp_ExFreePoolWithTag
0x14007450b  nop     dword ptr [rax+rax+00h]
0x140074510  jmp     short loc_1400744E2
```
