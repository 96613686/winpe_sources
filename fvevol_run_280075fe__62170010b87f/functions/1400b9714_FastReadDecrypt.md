# FastReadDecrypt

- ea: `0x1400b9714`
- end: `0x1400b98f9`
- name: `FastReadDecrypt`
- size: `485`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x1400b9cc0`

## callees

- `0x140009f00`
- `0x1400294e4`
- `0x14002c140`
- `0x14009d600`
- `0x1400b9714`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutex` at `0x1400b97b1`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400b97b1`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400b9807`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400b9807`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400b9883`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400b9883`
- `ntoskrnl!MmUnmapLockedPages` at `0x1400b9841`
- `ntoskrnl!MmUnmapLockedPages` at `0x1400b9841`
- `ntoskrnl!MmMapLockedPagesWithReservedMapping` at `0x1400b97d2`
- `ntoskrnl!MmMapLockedPagesWithReservedMapping` at `0x1400b97d2`
- `ntoskrnl!MmUnmapReservedMapping` at `0x1400b97f8`
- `ntoskrnl!MmUnmapReservedMapping` at `0x1400b97f8`
- `ntoskrnl!MmMapMdl` at `0x1400b9797`
- `ntoskrnl!MmMapMdl` at `0x1400b9797`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400b975d`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400b975d`
- `ntoskrnl!KeBugCheckEx` at `0x1400b98ad`
- `ntoskrnl!KeBugCheckEx` at `0x1400b98ad`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b98c2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b98c2`

## pseudocode

```c
__int64 __fastcall FastReadDecrypt(__int64 a1, __int64 a2, __int64 a3)
{
  struct _MDL *v3; // r15
  __int64 v5; // rdi
  __int64 v7; // rcx
  PVOID v8; // rsi
  PVOID v9; // rax
  int v10; // r15d
  __int64 v11; // rcx
  char v12; // al
  __int64 v13; // rcx
  int v14; // ebx

  v3 = *(struct _MDL **)(a3 + 56);
  v5 = *(_QWORD *)(a1 + 64);
  v7 = *(_QWORD *)(a2 + 8);
  if ( v3 )
  {
    if ( (*(_BYTE *)(v7 + 10) & 5) != 0 )
      v8 = *(PVOID *)(v7 + 24);
    else
      v8 = MmMapLockedPagesSpecifyCache((PMDL)v7, 0, MmCached, 0, 0, 0x40000010u);
  }
  else
  {
    v8 = 0;
    v3 = *(struct _MDL **)(a2 + 8);
  }
  FvePerfTraceDevPtr(v5, FVE_PERF_READ_SUBREQUEST_STOP, a2);
  if ( (int)MmMapMdl(v3, 4, FastReadMapped, a2) < 0 )
  {
    ExAcquireFastMutex((PFAST_MUTEX)(v5 + 2120));
    v9 = MmMapLockedPagesWithReservedMapping(*(PVOID *)(v5 + 2104), 0x72455646u, v3, MmCached);
    FastReadMapped(a2, v9);
    MmUnmapReservedMapping(*(PVOID *)(v5 + 2104), 0x72455646u, v3);
    ExReleaseFastMutex((PFAST_MUTEX)(v5 + 2120));
  }
  FvePerfTraceDevPtr(v5, &FVE_PERF_READ_REQUEST_STOP, a2);
  v10 = *(_DWORD *)(a3 + 40);
  if ( *(_QWORD *)(a3 + 56) )
  {
    v11 = *(_QWORD *)(a2 + 8);
    if ( (*(_BYTE *)(v11 + 10) & 0x20) != 0 )
      MmUnmapLockedPages(*(PVOID *)(v11 + 24), *(PMDL *)(a2 + 8));
    *(_QWORD *)(a2 + 8) = *(_QWORD *)(a3 + 56);
  }
  if ( v8 )
  {
    v12 = *(_BYTE *)(a3 + 44);
    if ( v12 == 1 )
    {
      v13 = *(_QWORD *)(v5 + 2024);
      if ( v13 )
        PplFreeToLookasideListProcessor(v13, v8, *(unsigned int *)(a3 + 48));
      else
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v5 + 2016), v8);
    }
    else
    {
      if ( v12 != 2 )
        KeBugCheckEx(0x120u, 0xCu, 0, 0, 0);
      ExFreePoolWithTag(v8, 0x70455646u);
    }
  }
  v14 = *(_DWORD *)(v5 + 840);
  FvepInformRundownFinishedWithDisk(v5, a2, v10);
  return v14 != 0 ? 0xC0000016 : 0;
}

```

## disassembly

```asm
0x1400b9714  push    rbx
0x1400b9716  push    rbp
0x1400b9717  push    rsi
0x1400b9718  push    rdi
0x1400b9719  push    r14
0x1400b971b  push    r15
0x1400b971d  sub     rsp, 38h
0x1400b9721  mov     r15, [r8+38h]
0x1400b9725  mov     r14, r8
0x1400b9728  mov     rdi, [rcx+40h]
0x1400b972c  mov     rbp, rdx
0x1400b972f  mov     rcx, [rdx+8]; MemoryDescriptorList
0x1400b9733  test    r15, r15
0x1400b9736  jz      short loc_1400B976E
0x1400b9738  test    byte ptr [rcx+0Ah], 5
0x1400b973c  jz      short loc_1400B9744
0x1400b973e  mov     rsi, [rcx+18h]
0x1400b9742  jmp     short loc_1400B9773
0x1400b9744  xor     r9d, r9d; RequestedAddress
0x1400b9747  mov     [rsp+68h+Priority], 40000010h; Priority
0x1400b974f  xor     edx, edx; AccessMode
0x1400b9751  mov     [rsp+68h+BugCheckOnFailure], 0; BugCheckOnFailure
0x1400b9759  lea     r8d, [r9+1]; CacheType
0x1400b975d  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400b9764  nop     dword ptr [rax+rax+00h]
0x1400b9769  mov     rsi, rax
0x1400b976c  jmp     short loc_1400B9773
0x1400b976e  xor     esi, esi
0x1400b9770  mov     r15, rcx
0x1400b9773  mov     r8, rbp
0x1400b9776  lea     rdx, FVE_PERF_READ_SUBREQUEST_STOP
0x1400b977d  mov     rcx, rdi
0x1400b9780  call    FvePerfTraceDevPtr
0x1400b9785  mov     r9, rbp
0x1400b9788  lea     r8, FastReadMapped
0x1400b978f  mov     edx, 4
0x1400b9794  mov     rcx, r15
0x1400b9797  call    cs:__imp_MmMapMdl
0x1400b979e  nop     dword ptr [rax+rax+00h]
0x1400b97a3  test    eax, eax
0x1400b97a5  jns     short loc_1400B9813
0x1400b97a7  lea     rbx, [rdi+848h]
0x1400b97ae  mov     rcx, rbx; FastMutex
0x1400b97b1  call    cs:__imp_ExAcquireFastMutex
0x1400b97b8  nop     dword ptr [rax+rax+00h]
0x1400b97bd  mov     rcx, [rdi+838h]; MappingAddress
0x1400b97c4  mov     r9d, 1; CacheType
0x1400b97ca  mov     r8, r15; MemoryDescriptorList
0x1400b97cd  mov     edx, 72455646h; PoolTag
0x1400b97d2  call    cs:__imp_MmMapLockedPagesWithReservedMapping
0x1400b97d9  nop     dword ptr [rax+rax+00h]
0x1400b97de  mov     rdx, rax
0x1400b97e1  mov     rcx, rbp
0x1400b97e4  call    FastReadMapped
0x1400b97e9  mov     rcx, [rdi+838h]; BaseAddress
0x1400b97f0  mov     r8, r15; MemoryDescriptorList
0x1400b97f3  mov     edx, 72455646h; PoolTag
0x1400b97f8  call    cs:__imp_MmUnmapReservedMapping
0x1400b97ff  nop     dword ptr [rax+rax+00h]
0x1400b9804  mov     rcx, rbx; FastMutex
0x1400b9807  call    cs:__imp_ExReleaseFastMutex
0x1400b980e  nop     dword ptr [rax+rax+00h]
0x1400b9813  mov     r8, rbp
0x1400b9816  lea     rdx, FVE_PERF_READ_REQUEST_STOP
0x1400b981d  mov     rcx, rdi
0x1400b9820  call    FvePerfTraceDevPtr
0x1400b9825  cmp     qword ptr [r14+38h], 0
0x1400b982a  mov     r15d, [r14+28h]
0x1400b982e  jz      short loc_1400B9855
0x1400b9830  mov     rcx, [rbp+8]
0x1400b9834  test    byte ptr [rcx+0Ah], 20h
0x1400b9838  jz      short loc_1400B984D
0x1400b983a  mov     rdx, rcx; MemoryDescriptorList
0x1400b983d  mov     rcx, [rcx+18h]; BaseAddress
0x1400b9841  call    cs:__imp_MmUnmapLockedPages
0x1400b9848  nop     dword ptr [rax+rax+00h]
0x1400b984d  mov     rax, [r14+38h]
0x1400b9851  mov     [rbp+8], rax
0x1400b9855  test    rsi, rsi
0x1400b9858  jz      short loc_1400B98CE
0x1400b985a  mov     al, [r14+2Ch]
0x1400b985e  cmp     al, 1
0x1400b9860  jnz     short loc_1400B9891
0x1400b9862  mov     rcx, [rdi+7E8h]
0x1400b9869  mov     rdx, rsi; Entry
0x1400b986c  test    rcx, rcx
0x1400b986f  jz      short loc_1400B987C
0x1400b9871  mov     r8d, [r14+30h]
0x1400b9875  call    PplFreeToLookasideListProcessor
0x1400b987a  jmp     short loc_1400B98CE
0x1400b987c  mov     rcx, [rdi+7E0h]; Lookaside
0x1400b9883  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400b988a  nop     dword ptr [rax+rax+00h]
0x1400b988f  jmp     short loc_1400B98CE
0x1400b9891  cmp     al, 2
0x1400b9893  jz      short loc_1400B98BA
0x1400b9895  xor     r9d, r9d; BugCheckParameter3
0x1400b9898  mov     qword ptr [rsp+68h+BugCheckOnFailure], 0; BugCheckParameter4
0x1400b98a1  xor     r8d, r8d; BugCheckParameter2
0x1400b98a4  mov     ecx, 120h; BugCheckCode
0x1400b98a9  lea     edx, [r9+0Ch]; BugCheckParameter1
0x1400b98ad  call    cs:__imp_KeBugCheckEx
0x1400b98ba  mov     edx, 70455646h; Tag
0x1400b98bf  mov     rcx, rsi; P
0x1400b98c2  call    cs:__imp_ExFreePoolWithTag
0x1400b98c9  nop     dword ptr [rax+rax+00h]
0x1400b98ce  mov     ebx, [rdi+348h]
0x1400b98d4  mov     r8b, r15b
0x1400b98d7  mov     rdx, rbp
0x1400b98da  mov     rcx, rdi
0x1400b98dd  call    FvepInformRundownFinishedWithDisk
0x1400b98e2  neg     ebx
0x1400b98e4  sbb     eax, eax
0x1400b98e6  and     eax, 0C0000016h
0x1400b98eb  add     rsp, 38h
0x1400b98ef  pop     r15
0x1400b98f1  pop     r14
0x1400b98f3  pop     rdi
0x1400b98f4  pop     rsi
0x1400b98f5  pop     rbp
0x1400b98f6  pop     rbx
0x1400b98f7  retn
```
