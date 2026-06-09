# MRxSmbTearDownMm

- ea: `0x140082160`
- end: `0x140082206`
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
- `0x140082160`

## import_xrefs

- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140082179`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140082179`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400821c0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400821e8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400821c0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400821e8`

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
0x140082160  push    rbx
0x140082162  sub     rsp, 20h
0x140082166  xor     ebx, ebx
0x140082168  lea     rax, SmbBufferLookasideList
0x14008216f  mov     rcx, rbx
0x140082172  shl     rcx, 7
0x140082176  add     rcx, rax; Lookaside
0x140082179  call    cs:__imp_ExDeleteNPagedLookasideList
0x140082180  nop     dword ptr [rax+rax+00h]
0x140082185  inc     rbx
0x140082188  cmp     rbx, 5
0x14008218c  jnz     short loc_140082168
0x14008218e  mov     rcx, cs:SmbMmExchangeLookasideList; P
0x140082195  test    rcx, rcx
0x140082198  jz      short loc_1400821AF
0x14008219a  mov     edx, 6D536358h; Tag
0x14008219f  call    PplDestroyLookasideList
0x1400821a4  mov     cs:SmbMmExchangeLookasideList, 0
0x1400821af  mov     rcx, cs:GlobalTrashBuffer; P
0x1400821b6  test    rcx, rcx
0x1400821b9  jz      short loc_1400821D7
0x1400821bb  mov     edx, 6D536254h; Tag
0x1400821c0  call    cs:__imp_ExFreePoolWithTag
0x1400821c7  nop     dword ptr [rax+rax+00h]
0x1400821cc  mov     cs:GlobalTrashBuffer, 0
0x1400821d7  mov     rcx, cs:GlobalPaddingBuffer; P
0x1400821de  test    rcx, rcx
0x1400821e1  jz      short loc_1400821FF
0x1400821e3  mov     edx, 6D536150h; Tag
0x1400821e8  call    cs:__imp_ExFreePoolWithTag
0x1400821ef  nop     dword ptr [rax+rax+00h]
0x1400821f4  mov     cs:GlobalPaddingBuffer, 0
0x1400821ff  add     rsp, 20h
0x140082203  pop     rbx
0x140082204  retn
```
