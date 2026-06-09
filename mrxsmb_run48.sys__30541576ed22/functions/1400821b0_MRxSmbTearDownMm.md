# MRxSmbTearDownMm

- ea: `0x1400821b0`
- end: `0x140082256`
- name: `MRxSmbTearDownMm`
- size: `166`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140080ce4`

## callees

- `0x14003b87c`
- `0x1400821b0`

## import_xrefs

- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400821c9`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400821c9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140082210`
- `ntoskrnl!ExFreePoolWithTag` at `0x140082238`
- `ntoskrnl!ExFreePoolWithTag` at `0x140082210`
- `ntoskrnl!ExFreePoolWithTag` at `0x140082238`

## pseudocode

```c
void MRxSmbTearDownMm()
{
  __int64 i; // rbx

  for ( i = 0; i != 5; ++i )
    ExDeleteNPagedLookasideList(&SmbBufferLookasideList + i);
  if ( SmbMmExchangeLookasideList )
  {
    PplDestroyLookasideList((char *)SmbMmExchangeLookasideList, 0x6D536358u);
    SmbMmExchangeLookasideList = 0;
  }
  if ( GlobalTrashBuffer )
  {
    ExFreePoolWithTag(GlobalTrashBuffer, 0x6D536254u);
    GlobalTrashBuffer = 0;
  }
  if ( GlobalPaddingBuffer )
  {
    ExFreePoolWithTag(GlobalPaddingBuffer, 0x6D536150u);
    GlobalPaddingBuffer = 0;
  }
}

```

## disassembly

```asm
0x1400821b0  push    rbx
0x1400821b2  sub     rsp, 20h
0x1400821b6  xor     ebx, ebx
0x1400821b8  lea     rax, SmbBufferLookasideList
0x1400821bf  mov     rcx, rbx
0x1400821c2  shl     rcx, 7
0x1400821c6  add     rcx, rax; Lookaside
0x1400821c9  call    cs:__imp_ExDeleteNPagedLookasideList
0x1400821d0  nop     dword ptr [rax+rax+00h]
0x1400821d5  inc     rbx
0x1400821d8  cmp     rbx, 5
0x1400821dc  jnz     short loc_1400821B8
0x1400821de  mov     rcx, cs:SmbMmExchangeLookasideList; P
0x1400821e5  test    rcx, rcx
0x1400821e8  jz      short loc_1400821FF
0x1400821ea  mov     edx, 6D536358h; Tag
0x1400821ef  call    PplDestroyLookasideList
0x1400821f4  mov     cs:SmbMmExchangeLookasideList, 0
0x1400821ff  mov     rcx, cs:GlobalTrashBuffer; P
0x140082206  test    rcx, rcx
0x140082209  jz      short loc_140082227
0x14008220b  mov     edx, 6D536254h; Tag
0x140082210  call    cs:__imp_ExFreePoolWithTag
0x140082217  nop     dword ptr [rax+rax+00h]
0x14008221c  mov     cs:GlobalTrashBuffer, 0
0x140082227  mov     rcx, cs:GlobalPaddingBuffer; P
0x14008222e  test    rcx, rcx
0x140082231  jz      short loc_14008224F
0x140082233  mov     edx, 6D536150h; Tag
0x140082238  call    cs:__imp_ExFreePoolWithTag
0x14008223f  nop     dword ptr [rax+rax+00h]
0x140082244  mov     cs:GlobalPaddingBuffer, 0
0x14008224f  add     rsp, 20h
0x140082253  pop     rbx
0x140082254  retn
```
