# SmbCamUnload

- ea: `0x1400878a0`
- end: `0x140087925`
- name: `SmbCamUnload`
- size: `133`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140080ce4`

## callees

- `0x14004f4ac`
- `0x1400878a0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400878cd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400878fd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400878cd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400878fd`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x1400878bc`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x1400878bc`
- `ntoskrnl!ExDeleteFastResource` at `0x1400878e0`
- `ntoskrnl!ExDeleteFastResource` at `0x1400878e0`

## pseudocode

```c
void SmbCamUnload()
{
  struct _PAGED_LOOKASIDE_LIST *v0; // rbx

  ClusterTicketManager<ImpKernelMode>::Unload();
  v0 = (struct _PAGED_LOOKASIDE_LIST *)_InterlockedExchange64(&ImpKernelModeWithLookasideAlloc<40>::S_lookaside, 0);
  if ( v0 )
  {
    ExDeletePagedLookasideList(v0);
    ExFreePoolWithTag(v0, 0);
  }
  ExDeleteFastResource(&GlobalResource);
  if ( *(_QWORD *)&ComputerSidAndAttributes.Revision )
  {
    ExFreePoolWithTag(*(PVOID *)&ComputerSidAndAttributes.Revision, 0x41434D53u);
    *(_QWORD *)&ComputerSidAndAttributes.Revision = 0;
    ComputerSidAndAttributes.SubAuthority[0] = 0;
  }
}

```

## disassembly

```asm
0x1400878a0  push    rbx
0x1400878a2  sub     rsp, 20h
0x1400878a6  call    ?Unload@?$ClusterTicketManager@VImpKernelMode@@@@SAXXZ; ClusterTicketManager<ImpKernelMode>::Unload(void)
0x1400878ab  xor     ebx, ebx
0x1400878ad  xchg    rbx, cs:?S_lookaside@?$ImpKernelModeWithLookasideAlloc@$0CI@@@0REAU_PAGED_LOOKASIDE_LIST@@EA; _PAGED_LOOKASIDE_LIST * ImpKernelModeWithLookasideAlloc<40>::S_lookaside
0x1400878b4  test    rbx, rbx
0x1400878b7  jz      short loc_1400878D9
0x1400878b9  mov     rcx, rbx; Lookaside
0x1400878bc  call    cs:__imp_ExDeletePagedLookasideList
0x1400878c3  nop     dword ptr [rax+rax+00h]
0x1400878c8  xor     edx, edx; Tag
0x1400878ca  mov     rcx, rbx; P
0x1400878cd  call    cs:__imp_ExFreePoolWithTag
0x1400878d4  nop     dword ptr [rax+rax+00h]
0x1400878d9  lea     rcx, ?GlobalResource@@3U_FAST_ERESOURCE@@A; _FAST_ERESOURCE GlobalResource
0x1400878e0  call    cs:__imp_ExDeleteFastResource
0x1400878e7  nop     dword ptr [rax+rax+00h]
0x1400878ec  mov     rcx, qword ptr cs:?ComputerSidAndAttributes@@3U_SID_AND_ATTRIBUTES@@A.Revision; P
0x1400878f3  test    rcx, rcx
0x1400878f6  jz      short loc_14008791E
0x1400878f8  mov     edx, 41434D53h; Tag
0x1400878fd  call    cs:__imp_ExFreePoolWithTag
0x140087904  nop     dword ptr [rax+rax+00h]
0x140087909  mov     qword ptr cs:?ComputerSidAndAttributes@@3U_SID_AND_ATTRIBUTES@@A.Revision, 0; _SID_AND_ATTRIBUTES ComputerSidAndAttributes ...
0x140087914  mov     cs:?ComputerSidAndAttributes@@3U_SID_AND_ATTRIBUTES@@A.SubAuthority, 0; _SID_AND_ATTRIBUTES ComputerSidAndAttributes ...
0x14008791e  add     rsp, 20h
0x140087922  pop     rbx
0x140087923  retn
```
