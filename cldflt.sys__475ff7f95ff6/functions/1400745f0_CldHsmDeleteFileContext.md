# CldHsmDeleteFileContext

- ea: `0x1400745f0`
- end: `0x140074632`
- name: `CldHsmDeleteFileContext`
- size: `66`
- prototype: `void __fastcall(_QWORD *Entry)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, authz_impersonation`

## callees

- `0x1400745f0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140074624`
- `ntoskrnl!ExFreePoolWithTag` at `0x140074624`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14007460c`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14007460c`

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
0x1400745f0  push    rbx
0x1400745f2  sub     rsp, 20h
0x1400745f6  mov     rbx, rcx
0x1400745f9  mov     rcx, [rcx+38h]; P
0x1400745fd  test    rcx, rcx
0x140074600  jnz     short loc_14007461F
0x140074602  mov     rdx, rbx; Entry
0x140074605  lea     rcx, stru_140028A80; Lookaside
0x14007460c  call    cs:__imp_ExFreeToPagedLookasideList
0x140074613  nop     dword ptr [rax+rax+00h]
0x140074618  add     rsp, 20h
0x14007461c  pop     rbx
0x14007461d  retn
0x14007461f  mov     edx, 53536C43h; Tag
0x140074624  call    cs:__imp_ExFreePoolWithTag
0x14007462b  nop     dword ptr [rax+rax+00h]
0x140074630  jmp     short loc_140074602
```
