# FatFreeResource

- ea: `0x14000656c`
- end: `0x14000659e`
- name: `FatFreeResource`
- size: `50`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `4`
- callee_count: `0`
- tags: `authz_impersonation`

## callers

- `0x14004763c`
- `0x140047960`
- `0x140047e34`
- `0x140048184`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x140006575`
- `ntoskrnl!ExDeleteResourceLite` at `0x140006575`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000658b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000658b`

## pseudocode

```c
void __fastcall FatFreeResource(struct _ERESOURCE *Entry)
{
  ExDeleteResourceLite(Entry);
  ExFreeToNPagedLookasideList(&FatEResourceLookasideList, Entry);
}

```

## disassembly

```asm
0x14000656c  push    rbx
0x14000656e  sub     rsp, 20h
0x140006572  mov     rbx, rcx
0x140006575  call    cs:__imp_ExDeleteResourceLite
0x14000657c  nop     dword ptr [rax+rax+00h]
0x140006581  mov     rdx, rbx; Entry
0x140006584  lea     rcx, FatEResourceLookasideList; Lookaside
0x14000658b  call    cs:__imp_ExFreeToNPagedLookasideList
0x140006592  nop     dword ptr [rax+rax+00h]
0x140006597  add     rsp, 20h
0x14000659b  pop     rbx
0x14000659c  retn
```
