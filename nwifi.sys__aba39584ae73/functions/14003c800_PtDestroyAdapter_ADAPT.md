# PtDestroyAdapter(_ADAPT *)

- ea: `0x14003c800`
- end: `0x14003c8d0`
- name: `?PtDestroyAdapter@@YAXPEAU_ADAPT@@@Z`
- size: `208`
- prototype: `void __fastcall(struct _ADAPT *)`
- caller_count: `8`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1400160d0`
- `0x140018590`
- `0x140030bec`
- `0x140030e68`
- `0x140035ae0`
- `0x14003c18c`
- `0x14003d934`
- `0x140056e70`

## callees

- `0x14003c800`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14003c827`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14003c875`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14003c8ac`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14003c827`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14003c875`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14003c8ac`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003c838`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003c886`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003c8bd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003c838`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003c886`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003c8bd`

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
0x14003c800  push    rbx
0x14003c802  sub     rsp, 20h
0x14003c806  mov     rbx, rcx
0x14003c809  mov     rcx, [rcx+3D0h]
0x14003c810  test    rcx, rcx
0x14003c813  jz      short loc_14003C85A
0x14003c815  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x14003c819  mov     rax, [rcx]
0x14003c81c  test    rax, rax
0x14003c81f  jz      short loc_14003C835
0x14003c821  mov     rdx, rcx; Entry
0x14003c824  mov     rcx, rax; Lookaside
0x14003c827  call    cs:__imp_ExFreeToNPagedLookasideList
0x14003c82e  nop     dword ptr [rax+rax+00h]
0x14003c833  jmp     short loc_14003C844
0x14003c835  mov     edx, [rcx+8]; Tag
0x14003c838  call    cs:__imp_ExFreePoolWithTag
0x14003c83f  nop     dword ptr [rax+rax+00h]
0x14003c844  mov     qword ptr [rbx+3D0h], 0
0x14003c84f  mov     qword ptr [rbx+3C4h], 0
0x14003c85a  mov     rcx, [rbx+18h]
0x14003c85e  test    rcx, rcx
0x14003c861  jz      short loc_14003C89A
0x14003c863  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x14003c867  mov     rax, [rcx]
0x14003c86a  test    rax, rax
0x14003c86d  jz      short loc_14003C883
0x14003c86f  mov     rdx, rcx; Entry
0x14003c872  mov     rcx, rax; Lookaside
0x14003c875  call    cs:__imp_ExFreeToNPagedLookasideList
0x14003c87c  nop     dword ptr [rax+rax+00h]
0x14003c881  jmp     short loc_14003C892
0x14003c883  mov     edx, [rcx+8]; Tag
0x14003c886  call    cs:__imp_ExFreePoolWithTag
0x14003c88d  nop     dword ptr [rax+rax+00h]
0x14003c892  mov     qword ptr [rbx+18h], 0
0x14003c89a  lea     rcx, [rbx-10h]; P
0x14003c89e  mov     rax, [rcx]
0x14003c8a1  test    rax, rax
0x14003c8a4  jz      short loc_14003C8BA
0x14003c8a6  mov     rdx, rcx; Entry
0x14003c8a9  mov     rcx, rax; Lookaside
0x14003c8ac  call    cs:__imp_ExFreeToNPagedLookasideList
0x14003c8b3  nop     dword ptr [rax+rax+00h]
0x14003c8b8  jmp     short loc_14003C8C9
0x14003c8ba  mov     edx, [rcx+8]; Tag
0x14003c8bd  call    cs:__imp_ExFreePoolWithTag
0x14003c8c4  nop     dword ptr [rax+rax+00h]
0x14003c8c9  add     rsp, 20h
0x14003c8cd  pop     rbx
0x14003c8ce  retn
```
