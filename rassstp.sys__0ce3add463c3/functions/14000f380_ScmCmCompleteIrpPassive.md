# ScmCmCompleteIrpPassive

- ea: `0x14000f380`
- end: `0x14000f3e6`
- name: `ScmCmCompleteIrpPassive`
- size: `102`
- prototype: `NDIS_IO_WORKITEM_FUNCTION`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14000f380`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14000f3d3`
- `ntoskrnl!IofCompleteRequest` at `0x14000f3d3`
- `ntoskrnl!MmLockPagableDataSection` at `0x14000f3af`
- `ntoskrnl!MmLockPagableDataSection` at `0x14000f3af`
- `NDIS!NdisFreeIoWorkItem` at `0x14000f38c`
- `NDIS!NdisFreeIoWorkItem` at `0x14000f38c`

## pseudocode

```c
void __fastcall ScmCmCompleteIrpPassive(IRP *WorkItemContext, NDIS_HANDLE NdisIoWorkItemHandle)
{
  NdisFreeIoWorkItem(NdisIoWorkItemHandle);
  if ( !*((_BYTE *)SstpGlobals + 569) )
  {
    MmLockPagableDataSection(&SmpReturnNetBufferListChain);
    *((_BYTE *)SstpGlobals + 569) = 1;
  }
  if ( WorkItemContext )
    IofCompleteRequest(WorkItemContext, 0);
}

```

## disassembly

```asm
0x14000f380  push    rbx
0x14000f382  sub     rsp, 20h
0x14000f386  mov     rbx, rcx
0x14000f389  mov     rcx, rdx; NdisIoWorkItemHandle
0x14000f38c  call    cs:__imp_NdisFreeIoWorkItem
0x14000f393  nop     dword ptr [rax+rax+00h]
0x14000f398  mov     rax, cs:SstpGlobals
0x14000f39f  cmp     byte ptr [rax+239h], 0
0x14000f3a6  jnz     short loc_14000F3C9
0x14000f3a8  lea     rcx, SmpReturnNetBufferListChain; AddressWithinSection
0x14000f3af  call    cs:__imp_MmLockPagableDataSection
0x14000f3b6  nop     dword ptr [rax+rax+00h]
0x14000f3bb  mov     rax, cs:SstpGlobals
0x14000f3c2  mov     byte ptr [rax+239h], 1
0x14000f3c9  test    rbx, rbx
0x14000f3cc  jz      short loc_14000F3DF
0x14000f3ce  xor     edx, edx; PriorityBoost
0x14000f3d0  mov     rcx, rbx; Irp
0x14000f3d3  call    cs:__imp_IofCompleteRequest
0x14000f3da  nop     dword ptr [rax+rax+00h]
0x14000f3df  add     rsp, 20h
0x14000f3e3  pop     rbx
0x14000f3e4  retn
```
