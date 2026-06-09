# FastReadDecrypt

- ea: `0x1400bb7e4`
- end: `0x1400bb9c9`
- name: `FastReadDecrypt`
- size: `485`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x1400bbd90`

## callees

- `0x140009fc0`
- `0x14002a4e4`
- `0x14002d140`
- `0x14009e540`
- `0x1400bb7e4`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutex` at `0x1400bb881`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400bb881`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400bb8d7`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400bb8d7`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400bb953`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400bb953`
- `ntoskrnl!MmUnmapLockedPages` at `0x1400bb911`
- `ntoskrnl!MmUnmapLockedPages` at `0x1400bb911`
- `ntoskrnl!MmMapLockedPagesWithReservedMapping` at `0x1400bb8a2`
- `ntoskrnl!MmMapLockedPagesWithReservedMapping` at `0x1400bb8a2`
- `ntoskrnl!MmUnmapReservedMapping` at `0x1400bb8c8`
- `ntoskrnl!MmUnmapReservedMapping` at `0x1400bb8c8`
- `ntoskrnl!MmMapMdl` at `0x1400bb867`
- `ntoskrnl!MmMapMdl` at `0x1400bb867`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400bb82d`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400bb82d`
- `ntoskrnl!KeBugCheckEx` at `0x1400bb97d`
- `ntoskrnl!KeBugCheckEx` at `0x1400bb97d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bb992`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bb992`

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
0x1400bb7e4  push    rbx
0x1400bb7e6  push    rbp
0x1400bb7e7  push    rsi
0x1400bb7e8  push    rdi
0x1400bb7e9  push    r14
0x1400bb7eb  push    r15
0x1400bb7ed  sub     rsp, 38h
0x1400bb7f1  mov     r15, [r8+38h]
0x1400bb7f5  mov     r14, r8
0x1400bb7f8  mov     rdi, [rcx+40h]
0x1400bb7fc  mov     rbp, rdx
0x1400bb7ff  mov     rcx, [rdx+8]; MemoryDescriptorList
0x1400bb803  test    r15, r15
0x1400bb806  jz      short loc_1400BB83E
0x1400bb808  test    byte ptr [rcx+0Ah], 5
0x1400bb80c  jz      short loc_1400BB814
0x1400bb80e  mov     rsi, [rcx+18h]
0x1400bb812  jmp     short loc_1400BB843
0x1400bb814  xor     r9d, r9d; RequestedAddress
0x1400bb817  mov     [rsp+68h+Priority], 40000010h; Priority
0x1400bb81f  xor     edx, edx; AccessMode
0x1400bb821  mov     [rsp+68h+BugCheckOnFailure], 0; BugCheckOnFailure
0x1400bb829  lea     r8d, [r9+1]; CacheType
0x1400bb82d  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400bb834  nop     dword ptr [rax+rax+00h]
0x1400bb839  mov     rsi, rax
0x1400bb83c  jmp     short loc_1400BB843
0x1400bb83e  xor     esi, esi
0x1400bb840  mov     r15, rcx
0x1400bb843  mov     r8, rbp
0x1400bb846  lea     rdx, FVE_PERF_READ_SUBREQUEST_STOP
0x1400bb84d  mov     rcx, rdi
0x1400bb850  call    FvePerfTraceDevPtr
0x1400bb855  mov     r9, rbp
0x1400bb858  lea     r8, FastReadMapped
0x1400bb85f  mov     edx, 4
0x1400bb864  mov     rcx, r15
0x1400bb867  call    cs:__imp_MmMapMdl
0x1400bb86e  nop     dword ptr [rax+rax+00h]
0x1400bb873  test    eax, eax
0x1400bb875  jns     short loc_1400BB8E3
0x1400bb877  lea     rbx, [rdi+848h]
0x1400bb87e  mov     rcx, rbx; FastMutex
0x1400bb881  call    cs:__imp_ExAcquireFastMutex
0x1400bb888  nop     dword ptr [rax+rax+00h]
0x1400bb88d  mov     rcx, [rdi+838h]; MappingAddress
0x1400bb894  mov     r9d, 1; CacheType
0x1400bb89a  mov     r8, r15; MemoryDescriptorList
0x1400bb89d  mov     edx, 72455646h; PoolTag
0x1400bb8a2  call    cs:__imp_MmMapLockedPagesWithReservedMapping
0x1400bb8a9  nop     dword ptr [rax+rax+00h]
0x1400bb8ae  mov     rdx, rax
0x1400bb8b1  mov     rcx, rbp
0x1400bb8b4  call    FastReadMapped
0x1400bb8b9  mov     rcx, [rdi+838h]; BaseAddress
0x1400bb8c0  mov     r8, r15; MemoryDescriptorList
0x1400bb8c3  mov     edx, 72455646h; PoolTag
0x1400bb8c8  call    cs:__imp_MmUnmapReservedMapping
0x1400bb8cf  nop     dword ptr [rax+rax+00h]
0x1400bb8d4  mov     rcx, rbx; FastMutex
0x1400bb8d7  call    cs:__imp_ExReleaseFastMutex
0x1400bb8de  nop     dword ptr [rax+rax+00h]
0x1400bb8e3  mov     r8, rbp
0x1400bb8e6  lea     rdx, FVE_PERF_READ_REQUEST_STOP
0x1400bb8ed  mov     rcx, rdi
0x1400bb8f0  call    FvePerfTraceDevPtr
0x1400bb8f5  cmp     qword ptr [r14+38h], 0
0x1400bb8fa  mov     r15d, [r14+28h]
0x1400bb8fe  jz      short loc_1400BB925
0x1400bb900  mov     rcx, [rbp+8]
0x1400bb904  test    byte ptr [rcx+0Ah], 20h
0x1400bb908  jz      short loc_1400BB91D
0x1400bb90a  mov     rdx, rcx; MemoryDescriptorList
0x1400bb90d  mov     rcx, [rcx+18h]; BaseAddress
0x1400bb911  call    cs:__imp_MmUnmapLockedPages
0x1400bb918  nop     dword ptr [rax+rax+00h]
0x1400bb91d  mov     rax, [r14+38h]
0x1400bb921  mov     [rbp+8], rax
0x1400bb925  test    rsi, rsi
0x1400bb928  jz      short loc_1400BB99E
0x1400bb92a  mov     al, [r14+2Ch]
0x1400bb92e  cmp     al, 1
0x1400bb930  jnz     short loc_1400BB961
0x1400bb932  mov     rcx, [rdi+7E8h]
0x1400bb939  mov     rdx, rsi; Entry
0x1400bb93c  test    rcx, rcx
0x1400bb93f  jz      short loc_1400BB94C
0x1400bb941  mov     r8d, [r14+30h]
0x1400bb945  call    PplFreeToLookasideListProcessor
0x1400bb94a  jmp     short loc_1400BB99E
0x1400bb94c  mov     rcx, [rdi+7E0h]; Lookaside
0x1400bb953  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400bb95a  nop     dword ptr [rax+rax+00h]
0x1400bb95f  jmp     short loc_1400BB99E
0x1400bb961  cmp     al, 2
0x1400bb963  jz      short loc_1400BB98A
0x1400bb965  xor     r9d, r9d; BugCheckParameter3
0x1400bb968  mov     qword ptr [rsp+68h+BugCheckOnFailure], 0; BugCheckParameter4
0x1400bb971  xor     r8d, r8d; BugCheckParameter2
0x1400bb974  mov     ecx, 120h; BugCheckCode
0x1400bb979  lea     edx, [r9+0Ch]; BugCheckParameter1
0x1400bb97d  call    cs:__imp_KeBugCheckEx
0x1400bb98a  mov     edx, 70455646h; Tag
0x1400bb98f  mov     rcx, rsi; P
0x1400bb992  call    cs:__imp_ExFreePoolWithTag
0x1400bb999  nop     dword ptr [rax+rax+00h]
0x1400bb99e  mov     ebx, [rdi+348h]
0x1400bb9a4  mov     r8b, r15b
0x1400bb9a7  mov     rdx, rbp
0x1400bb9aa  mov     rcx, rdi
0x1400bb9ad  call    FvepInformRundownFinishedWithDisk
0x1400bb9b2  neg     ebx
0x1400bb9b4  sbb     eax, eax
0x1400bb9b6  and     eax, 0C0000016h
0x1400bb9bb  add     rsp, 38h
0x1400bb9bf  pop     r15
0x1400bb9c1  pop     r14
0x1400bb9c3  pop     rdi
0x1400bb9c4  pop     rsi
0x1400bb9c5  pop     rbp
0x1400bb9c6  pop     rbx
0x1400bb9c7  retn
```
