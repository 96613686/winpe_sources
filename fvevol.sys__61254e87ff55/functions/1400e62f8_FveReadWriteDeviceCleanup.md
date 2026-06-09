# FveReadWriteDeviceCleanup

- ea: `0x1400e62f8`
- end: `0x1400e64ac`
- name: `FveReadWriteDeviceCleanup`
- size: `436`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140024a64`
- `0x140030430`
- `0x1400e7934`

## callees

- `0x1400dbdd0`
- `0x1400e62f8`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x1400e6341`
- `ntoskrnl!KeReleaseMutex` at `0x1400e6341`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400e646d`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400e646d`
- `ntoskrnl!MmFreeMappingAddress` at `0x1400e641e`
- `ntoskrnl!MmFreeMappingAddress` at `0x1400e641e`
- `ntoskrnl!IoFreeMdl` at `0x1400e6441`
- `ntoskrnl!IoFreeMdl` at `0x1400e6441`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400e6326`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400e6326`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e6387`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e63ce`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e63f6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e6485`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e6387`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e63ce`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e63f6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e6485`

## pseudocode

```c
LONG __fastcall FveReadWriteDeviceCleanup(__int64 a1, char a2)
{
  struct _KMUTANT *v2; // rbp
  int v5; // eax
  void *v7; // rcx
  __int64 v8; // rdx
  void *v9; // rcx
  void *v10; // rcx
  void *v11; // rcx
  struct _MDL *v12; // rcx
  struct _NPAGED_LOOKASIDE_LIST *v13; // rcx

  v2 = *(struct _KMUTANT **)(a1 + 8);
  KeWaitForSingleObject(&v2[176], Executive, 0, 0, 0);
  v5 = *(_DWORD *)(a1 + 4728);
  if ( v5 && (a2 || v5 != 1) )
  {
    _InterlockedDecrement((volatile signed __int32 *)(a1 + 4728));
    if ( a2 || *(int *)(a1 + 4728) <= 0 )
    {
      v7 = *(void **)(a1 + 2040);
      if ( v7 )
      {
        ExFreePoolWithTag(v7, 0x78455646u);
        *(_QWORD *)(a1 + 2040) = 0;
      }
      v8 = *(_QWORD *)(a1 + 2056);
      if ( v8 )
      {
        *(_QWORD *)(a1 + 2056) = 0;
        ReleaseSubIrp(a1, v8);
      }
      v9 = *(void **)(a1 + 2072);
      if ( v9 )
      {
        ExFreePoolWithTag(v9, 0x77455646u);
        *(_QWORD *)(a1 + 2072) = 0;
      }
      v10 = *(void **)(a1 + 2088);
      if ( v10 )
      {
        ExFreePoolWithTag(v10, 0x70455646u);
        *(_QWORD *)(a1 + 2088) = 0;
      }
      v11 = *(void **)(a1 + 2104);
      if ( v11 )
      {
        MmFreeMappingAddress(v11, 0x72455646u);
        *(_QWORD *)(a1 + 2104) = 0;
      }
      v12 = *(struct _MDL **)(a1 + 2112);
      if ( v12 )
      {
        IoFreeMdl(v12);
        *(_QWORD *)(a1 + 2112) = 0;
      }
      v13 = *(struct _NPAGED_LOOKASIDE_LIST **)(a1 + 2016);
      if ( v13 )
      {
        if ( v13 != (struct _NPAGED_LOOKASIDE_LIST *)v2[165].Header.WaitListHead.Blink )
        {
          ExDeleteNPagedLookasideList(v13);
          ExFreePoolWithTag(*(PVOID *)(a1 + 2016), 0x30455646u);
        }
        *(_QWORD *)(a1 + 2016) = 0;
      }
      *(_QWORD *)(a1 + 2024) = 0;
    }
  }
  return KeReleaseMutex(v2 + 176, 0);
}

```

## disassembly

```asm
0x1400e62f8  push    rbx
0x1400e62fa  push    rbp
0x1400e62fb  push    rsi
0x1400e62fc  push    rdi
0x1400e62fd  sub     rsp, 38h
0x1400e6301  mov     rbp, [rcx+8]
0x1400e6305  mov     dil, dl
0x1400e6308  mov     rbx, rcx
0x1400e630b  mov     [rsp+58h+Timeout], 0; Timeout
0x1400e6314  xor     r9d, r9d; Alertable
0x1400e6317  xor     r8d, r8d; WaitMode
0x1400e631a  xor     edx, edx; WaitReason
0x1400e631c  lea     rsi, [rbp+2680h]
0x1400e6323  mov     rcx, rsi; Object
0x1400e6326  call    cs:__imp_KeWaitForSingleObject
0x1400e632d  nop     dword ptr [rax+rax+00h]
0x1400e6332  mov     eax, [rbx+1278h]
0x1400e6338  test    eax, eax
0x1400e633a  jnz     short loc_1400E6357
0x1400e633c  xor     edx, edx; Wait
0x1400e633e  mov     rcx, rsi; Mutex
0x1400e6341  call    cs:__imp_KeReleaseMutex
0x1400e6348  nop     dword ptr [rax+rax+00h]
0x1400e634d  add     rsp, 38h
0x1400e6351  pop     rdi
0x1400e6352  pop     rsi
0x1400e6353  pop     rbp
0x1400e6354  pop     rbx
0x1400e6355  retn
0x1400e6357  test    dil, dil
0x1400e635a  jnz     short loc_1400E6361
0x1400e635c  cmp     eax, 1
0x1400e635f  jz      short loc_1400E633C
0x1400e6361  lock dec dword ptr [rbx+1278h]
0x1400e6368  test    dil, dil
0x1400e636b  jnz     short loc_1400E6376
0x1400e636d  cmp     dword ptr [rbx+1278h], 0
0x1400e6374  jg      short loc_1400E633C
0x1400e6376  mov     rcx, [rbx+7F8h]; P
0x1400e637d  test    rcx, rcx
0x1400e6380  jz      short loc_1400E639E
0x1400e6382  mov     edx, 78455646h; Tag
0x1400e6387  call    cs:__imp_ExFreePoolWithTag
0x1400e638e  nop     dword ptr [rax+rax+00h]
0x1400e6393  mov     qword ptr [rbx+7F8h], 0
0x1400e639e  mov     rdx, [rbx+808h]
0x1400e63a5  test    rdx, rdx
0x1400e63a8  jz      short loc_1400E63BD
0x1400e63aa  mov     rcx, rbx
0x1400e63ad  mov     qword ptr [rbx+808h], 0
0x1400e63b8  call    ReleaseSubIrp
0x1400e63bd  mov     rcx, [rbx+818h]; P
0x1400e63c4  test    rcx, rcx
0x1400e63c7  jz      short loc_1400E63E5
0x1400e63c9  mov     edx, 77455646h; Tag
0x1400e63ce  call    cs:__imp_ExFreePoolWithTag
0x1400e63d5  nop     dword ptr [rax+rax+00h]
0x1400e63da  mov     qword ptr [rbx+818h], 0
0x1400e63e5  mov     rcx, [rbx+828h]; P
0x1400e63ec  test    rcx, rcx
0x1400e63ef  jz      short loc_1400E640D
0x1400e63f1  mov     edx, 70455646h; Tag
0x1400e63f6  call    cs:__imp_ExFreePoolWithTag
0x1400e63fd  nop     dword ptr [rax+rax+00h]
0x1400e6402  mov     qword ptr [rbx+828h], 0
0x1400e640d  mov     rcx, [rbx+838h]; BaseAddress
0x1400e6414  test    rcx, rcx
0x1400e6417  jz      short loc_1400E6435
0x1400e6419  mov     edx, 72455646h; PoolTag
0x1400e641e  call    cs:__imp_MmFreeMappingAddress
0x1400e6425  nop     dword ptr [rax+rax+00h]
0x1400e642a  mov     qword ptr [rbx+838h], 0
0x1400e6435  mov     rcx, [rbx+840h]; Mdl
0x1400e643c  test    rcx, rcx
0x1400e643f  jz      short loc_1400E6458
0x1400e6441  call    cs:__imp_IoFreeMdl
0x1400e6448  nop     dword ptr [rax+rax+00h]
0x1400e644d  mov     qword ptr [rbx+840h], 0
0x1400e6458  mov     rcx, [rbx+7E0h]; Lookaside
0x1400e645f  test    rcx, rcx
0x1400e6462  jz      short loc_1400E649C
0x1400e6464  cmp     rcx, [rbp+2428h]
0x1400e646b  jz      short loc_1400E6491
0x1400e646d  call    cs:__imp_ExDeleteNPagedLookasideList
0x1400e6474  nop     dword ptr [rax+rax+00h]
0x1400e6479  mov     rcx, [rbx+7E0h]; P
0x1400e6480  mov     edx, 30455646h; Tag
0x1400e6485  call    cs:__imp_ExFreePoolWithTag
0x1400e648c  nop     dword ptr [rax+rax+00h]
0x1400e6491  mov     qword ptr [rbx+7E0h], 0
0x1400e649c  mov     qword ptr [rbx+7E8h], 0
0x1400e64a7  jmp     loc_1400E633C
```
