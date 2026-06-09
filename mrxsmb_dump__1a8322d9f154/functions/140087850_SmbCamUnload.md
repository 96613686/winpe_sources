# SmbCamUnload

- ea: `0x140087850`
- end: `0x1400878d5`
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
- `0x140087850`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14008787d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400878ad`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008787d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400878ad`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14008786c`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14008786c`
- `ntoskrnl!ExDeleteFastResource` at `0x140087890`
- `ntoskrnl!ExDeleteFastResource` at `0x140087890`

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
0x140087850  push    rbx
0x140087852  sub     rsp, 20h
0x140087856  call    ?Unload@?$ClusterTicketManager@VImpKernelMode@@@@SAXXZ; ClusterTicketManager<ImpKernelMode>::Unload(void)
0x14008785b  xor     ebx, ebx
0x14008785d  xchg    rbx, cs:?S_lookaside@?$ImpKernelModeWithLookasideAlloc@$0CI@@@0REAU_PAGED_LOOKASIDE_LIST@@EA; _PAGED_LOOKASIDE_LIST * ImpKernelModeWithLookasideAlloc<40>::S_lookaside
0x140087864  test    rbx, rbx
0x140087867  jz      short loc_140087889
0x140087869  mov     rcx, rbx; Lookaside
0x14008786c  call    cs:__imp_ExDeletePagedLookasideList
0x140087873  nop     dword ptr [rax+rax+00h]
0x140087878  xor     edx, edx; Tag
0x14008787a  mov     rcx, rbx; P
0x14008787d  call    cs:__imp_ExFreePoolWithTag
0x140087884  nop     dword ptr [rax+rax+00h]
0x140087889  lea     rcx, ?GlobalResource@@3U_FAST_ERESOURCE@@A; _FAST_ERESOURCE GlobalResource
0x140087890  call    cs:__imp_ExDeleteFastResource
0x140087897  nop     dword ptr [rax+rax+00h]
0x14008789c  mov     rcx, qword ptr cs:?ComputerSidAndAttributes@@3U_SID_AND_ATTRIBUTES@@A.Revision; P
0x1400878a3  test    rcx, rcx
0x1400878a6  jz      short loc_1400878CE
0x1400878a8  mov     edx, 41434D53h; Tag
0x1400878ad  call    cs:__imp_ExFreePoolWithTag
0x1400878b4  nop     dword ptr [rax+rax+00h]
0x1400878b9  mov     qword ptr cs:?ComputerSidAndAttributes@@3U_SID_AND_ATTRIBUTES@@A.Revision, 0; _SID_AND_ATTRIBUTES ComputerSidAndAttributes ...
0x1400878c4  mov     cs:?ComputerSidAndAttributes@@3U_SID_AND_ATTRIBUTES@@A.SubAuthority, 0; _SID_AND_ATTRIBUTES ComputerSidAndAttributes ...
0x1400878ce  add     rsp, 20h
0x1400878d2  pop     rbx
0x1400878d3  retn
```
