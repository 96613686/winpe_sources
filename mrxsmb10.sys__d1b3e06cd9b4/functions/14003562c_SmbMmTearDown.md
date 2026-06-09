# SmbMmTearDown

- ea: `0x14003562c`
- end: `0x1400356b5`
- name: `SmbMmTearDown`
- size: `137`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `authz_impersonation`

## callers

- `0x140031b98`
- `0x140032a30`

## import_xrefs

- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140035657`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14003566a`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14003567d`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140035690`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400356a3`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140035657`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14003566a`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14003567d`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140035690`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400356a3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140035639`
- `ntoskrnl!ExFreePoolWithTag` at `0x140035639`

## pseudocode

```c
void SmbMmTearDown()
{
  ExFreePoolWithTag(SmbMmRequestZoneSegmentPtr, 0);
  SmbMmRequestZoneSegmentPtr = 0;
  ExDeleteNPagedLookasideList(&SmbMmExchangesLookasideList);
  ExDeleteNPagedLookasideList(&Lookaside);
  ExDeleteNPagedLookasideList(&stru_14001F900);
  ExDeleteNPagedLookasideList(&stru_14001FA00);
  ExDeleteNPagedLookasideList(&stru_14001FA80);
}

```

## disassembly

```asm
0x14003562c  sub     rsp, 28h
0x140035630  mov     rcx, cs:SmbMmRequestZoneSegmentPtr; P
0x140035637  xor     edx, edx; Tag
0x140035639  call    cs:__imp_ExFreePoolWithTag
0x140035640  nop     dword ptr [rax+rax+00h]
0x140035645  lea     rcx, SmbMmExchangesLookasideList; Lookaside
0x14003564c  mov     cs:SmbMmRequestZoneSegmentPtr, 0
0x140035657  call    cs:__imp_ExDeleteNPagedLookasideList
0x14003565e  nop     dword ptr [rax+rax+00h]
0x140035663  lea     rcx, Lookaside; Lookaside
0x14003566a  call    cs:__imp_ExDeleteNPagedLookasideList
0x140035671  nop     dword ptr [rax+rax+00h]
0x140035676  lea     rcx, stru_14001F900; Lookaside
0x14003567d  call    cs:__imp_ExDeleteNPagedLookasideList
0x140035684  nop     dword ptr [rax+rax+00h]
0x140035689  lea     rcx, stru_14001FA00; Lookaside
0x140035690  call    cs:__imp_ExDeleteNPagedLookasideList
0x140035697  nop     dword ptr [rax+rax+00h]
0x14003569c  lea     rcx, stru_14001FA80; Lookaside
0x1400356a3  call    cs:__imp_ExDeleteNPagedLookasideList
0x1400356aa  nop     dword ptr [rax+rax+00h]
0x1400356af  add     rsp, 28h
0x1400356b3  retn
```
