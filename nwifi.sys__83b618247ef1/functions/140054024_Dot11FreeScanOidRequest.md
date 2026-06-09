# Dot11FreeScanOidRequest

- ea: `0x140054024`
- end: `0x14005409e`
- name: `Dot11FreeScanOidRequest`
- size: `122`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140016320`
- `0x1400540d0`
- `0x140054c14`

## callees

- `0x140054024`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14005404b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14005407a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14005404b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14005407a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005405c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005408b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005405c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005408b`

## pseudocode

```c
void __fastcall Dot11FreeScanOidRequest(__int64 a1)
{
  __int64 v2; // rcx
  __int64 v3; // rcx

  v2 = *(_QWORD *)(a1 + 272);
  if ( v2 )
  {
    v3 = v2 - 16;
    if ( *(_QWORD *)v3 )
      ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v3, (PVOID)v3);
    else
      ExFreePoolWithTag((PVOID)v3, *(_DWORD *)(v3 + 8));
  }
  if ( *(_QWORD *)(a1 - 16) )
    ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(a1 - 16), (PVOID)(a1 - 16));
  else
    ExFreePoolWithTag((PVOID)(a1 - 16), *(_DWORD *)(a1 - 16 + 8));
}

```

## disassembly

```asm
0x140054024  push    rbx
0x140054026  sub     rsp, 20h
0x14005402a  mov     rbx, rcx
0x14005402d  mov     rcx, [rcx+110h]
0x140054034  test    rcx, rcx
0x140054037  jz      short loc_140054068
0x140054039  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x14005403d  mov     rax, [rcx]
0x140054040  test    rax, rax
0x140054043  jz      short loc_140054059
0x140054045  mov     rdx, rcx; Entry
0x140054048  mov     rcx, rax; Lookaside
0x14005404b  call    cs:__imp_ExFreeToNPagedLookasideList
0x140054052  nop     dword ptr [rax+rax+00h]
0x140054057  jmp     short loc_140054068
0x140054059  mov     edx, [rcx+8]; Tag
0x14005405c  call    cs:__imp_ExFreePoolWithTag
0x140054063  nop     dword ptr [rax+rax+00h]
0x140054068  lea     rcx, [rbx-10h]; P
0x14005406c  mov     rax, [rcx]
0x14005406f  test    rax, rax
0x140054072  jz      short loc_140054088
0x140054074  mov     rdx, rcx; Entry
0x140054077  mov     rcx, rax; Lookaside
0x14005407a  call    cs:__imp_ExFreeToNPagedLookasideList
0x140054081  nop     dword ptr [rax+rax+00h]
0x140054086  jmp     short loc_140054097
0x140054088  mov     edx, [rcx+8]; Tag
0x14005408b  call    cs:__imp_ExFreePoolWithTag
0x140054092  nop     dword ptr [rax+rax+00h]
0x140054097  add     rsp, 20h
0x14005409b  pop     rbx
0x14005409c  retn
```
