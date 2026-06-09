# Dot11FreeScanOidRequest

- ea: `0x140055844`
- end: `0x1400558be`
- name: `Dot11FreeScanOidRequest`
- size: `122`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140016310`
- `0x1400558f0`
- `0x140056434`

## callees

- `0x140055844`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14005586b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14005589a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14005586b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14005589a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005587c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400558ab`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005587c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400558ab`

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
0x140055844  push    rbx
0x140055846  sub     rsp, 20h
0x14005584a  mov     rbx, rcx
0x14005584d  mov     rcx, [rcx+110h]
0x140055854  test    rcx, rcx
0x140055857  jz      short loc_140055888
0x140055859  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x14005585d  mov     rax, [rcx]
0x140055860  test    rax, rax
0x140055863  jz      short loc_140055879
0x140055865  mov     rdx, rcx; Entry
0x140055868  mov     rcx, rax; Lookaside
0x14005586b  call    cs:__imp_ExFreeToNPagedLookasideList
0x140055872  nop     dword ptr [rax+rax+00h]
0x140055877  jmp     short loc_140055888
0x140055879  mov     edx, [rcx+8]; Tag
0x14005587c  call    cs:__imp_ExFreePoolWithTag
0x140055883  nop     dword ptr [rax+rax+00h]
0x140055888  lea     rcx, [rbx-10h]; P
0x14005588c  mov     rax, [rcx]
0x14005588f  test    rax, rax
0x140055892  jz      short loc_1400558A8
0x140055894  mov     rdx, rcx; Entry
0x140055897  mov     rcx, rax; Lookaside
0x14005589a  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400558a1  nop     dword ptr [rax+rax+00h]
0x1400558a6  jmp     short loc_1400558B7
0x1400558a8  mov     edx, [rcx+8]; Tag
0x1400558ab  call    cs:__imp_ExFreePoolWithTag
0x1400558b2  nop     dword ptr [rax+rax+00h]
0x1400558b7  add     rsp, 20h
0x1400558bb  pop     rbx
0x1400558bc  retn
```
