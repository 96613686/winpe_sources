# PtDestroyAdapter(_ADAPT *)

- ea: `0x14003c5e0`
- end: `0x14003c6b0`
- name: `?PtDestroyAdapter@@YAXPEAU_ADAPT@@@Z`
- size: `208`
- prototype: `void __fastcall(struct _ADAPT *)`
- caller_count: `8`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1400160e0`
- `0x140018590`
- `0x14003095c`
- `0x140030bd8`
- `0x1400358c0`
- `0x14003bf6c`
- `0x14003d714`
- `0x140055650`

## callees

- `0x14003c5e0`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14003c607`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14003c655`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14003c68c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14003c607`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14003c655`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14003c68c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003c618`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003c666`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003c69d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003c618`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003c666`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003c69d`

## pseudocode

```c
void __fastcall PtDestroyAdapter(struct _ADAPT *a1)
{
  _NDIS_GUID *pSupportedGUIDs; // rcx
  ULONG *v3; // rcx
  _NDIS_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES *pNwfAttrs; // rcx
  ULONG *p_ExtAPAttributes; // rcx

  pSupportedGUIDs = a1->pSupportedGUIDs;
  if ( pSupportedGUIDs )
  {
    v3 = (ULONG *)&pSupportedGUIDs[-1].Guid.Data4[4];
    if ( *(_QWORD *)v3 )
      ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v3, v3);
    else
      ExFreePoolWithTag(v3, v3[2]);
    a1->pSupportedGUIDs = 0;
    *(_QWORD *)&a1->uBufSizeOfSupportedGUIDs = 0;
  }
  pNwfAttrs = a1->pNwfAttrs;
  if ( pNwfAttrs )
  {
    p_ExtAPAttributes = (ULONG *)&pNwfAttrs[-1].ExtAPAttributes;
    if ( *(_QWORD *)p_ExtAPAttributes )
      ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)p_ExtAPAttributes, p_ExtAPAttributes);
    else
      ExFreePoolWithTag(p_ExtAPAttributes, p_ExtAPAttributes[2]);
    a1->pNwfAttrs = 0;
  }
  if ( a1[-1].BaseMiniportNetLuid.Value )
    ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)a1[-1].BaseMiniportNetLuid.Value, &a1[-1].BaseMiniportNetLuid);
  else
    ExFreePoolWithTag(&a1[-1].BaseMiniportNetLuid, a1[-1].PhyStateChangesSuppressed);
}

```

## disassembly

```asm
0x14003c5e0  push    rbx
0x14003c5e2  sub     rsp, 20h
0x14003c5e6  mov     rbx, rcx
0x14003c5e9  mov     rcx, [rcx+3D0h]
0x14003c5f0  test    rcx, rcx
0x14003c5f3  jz      short loc_14003C63A
0x14003c5f5  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x14003c5f9  mov     rax, [rcx]
0x14003c5fc  test    rax, rax
0x14003c5ff  jz      short loc_14003C615
0x14003c601  mov     rdx, rcx; Entry
0x14003c604  mov     rcx, rax; Lookaside
0x14003c607  call    cs:__imp_ExFreeToNPagedLookasideList
0x14003c60e  nop     dword ptr [rax+rax+00h]
0x14003c613  jmp     short loc_14003C624
0x14003c615  mov     edx, [rcx+8]; Tag
0x14003c618  call    cs:__imp_ExFreePoolWithTag
0x14003c61f  nop     dword ptr [rax+rax+00h]
0x14003c624  mov     qword ptr [rbx+3D0h], 0
0x14003c62f  mov     qword ptr [rbx+3C4h], 0
0x14003c63a  mov     rcx, [rbx+18h]
0x14003c63e  test    rcx, rcx
0x14003c641  jz      short loc_14003C67A
0x14003c643  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x14003c647  mov     rax, [rcx]
0x14003c64a  test    rax, rax
0x14003c64d  jz      short loc_14003C663
0x14003c64f  mov     rdx, rcx; Entry
0x14003c652  mov     rcx, rax; Lookaside
0x14003c655  call    cs:__imp_ExFreeToNPagedLookasideList
0x14003c65c  nop     dword ptr [rax+rax+00h]
0x14003c661  jmp     short loc_14003C672
0x14003c663  mov     edx, [rcx+8]; Tag
0x14003c666  call    cs:__imp_ExFreePoolWithTag
0x14003c66d  nop     dword ptr [rax+rax+00h]
0x14003c672  mov     qword ptr [rbx+18h], 0
0x14003c67a  lea     rcx, [rbx-10h]; P
0x14003c67e  mov     rax, [rcx]
0x14003c681  test    rax, rax
0x14003c684  jz      short loc_14003C69A
0x14003c686  mov     rdx, rcx; Entry
0x14003c689  mov     rcx, rax; Lookaside
0x14003c68c  call    cs:__imp_ExFreeToNPagedLookasideList
0x14003c693  nop     dword ptr [rax+rax+00h]
0x14003c698  jmp     short loc_14003C6A9
0x14003c69a  mov     edx, [rcx+8]; Tag
0x14003c69d  call    cs:__imp_ExFreePoolWithTag
0x14003c6a4  nop     dword ptr [rax+rax+00h]
0x14003c6a9  add     rsp, 20h
0x14003c6ad  pop     rbx
0x14003c6ae  retn
```
