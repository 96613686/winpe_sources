# FastWriteEncrypt

- ea: `0x1400b9a20`
- end: `0x1400b9bcc`
- name: `FastWriteEncrypt`
- size: `428`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1400b9cc0`
- `0x1400e49ec`

## callees

- `0x14002c140`
- `0x14009da70`
- `0x1400b9900`
- `0x1400b9a20`
- `0x1400d5fc0`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x1400b9bb2`
- `ntoskrnl!IofCallDriver` at `0x1400b9bb2`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400b9a7e`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400b9a7e`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400b9ad6`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400b9ad6`
- `ntoskrnl!IofCompleteRequest` at `0x1400b9b69`
- `ntoskrnl!IofCompleteRequest` at `0x1400b9b69`
- `ntoskrnl!MmMapLockedPagesWithReservedMapping` at `0x1400b9aa0`
- `ntoskrnl!MmMapLockedPagesWithReservedMapping` at `0x1400b9aa0`
- `ntoskrnl!MmUnmapReservedMapping` at `0x1400b9ac7`
- `ntoskrnl!MmUnmapReservedMapping` at `0x1400b9ac7`
- `ntoskrnl!MmMapMdl` at `0x1400b9a62`
- `ntoskrnl!MmMapMdl` at `0x1400b9a62`

## pseudocode

```c
void __fastcall FastWriteEncrypt(__int64 a1, IRP *a2, __int64 a3)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r15
  int v7; // ebp
  PVOID v8; // rax
  struct _IO_STACK_LOCATION *v9; // rax
  struct _IO_STACK_LOCATION *v10; // rax
  __int64 LockArray_high; // rcx

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  FvePerfTraceDevPtrPtr(a1, FVE_PERF_WRITE_SUBREQUEST_INIT, a2, a2);
  v7 = MmMapMdl(a2->MdlAddress, 4, FastWriteMapped, a2);
  if ( v7 < 0 )
  {
    ExAcquireFastMutex((PFAST_MUTEX)(a1 + 2120));
    v8 = MmMapLockedPagesWithReservedMapping(*(PVOID *)(a1 + 2104), 0x72455646u, a2->MdlAddress, MmCached);
    FastWriteMapped((__int64)a2, v8);
    MmUnmapReservedMapping(*(PVOID *)(a1 + 2104), 0x72455646u, a2->MdlAddress);
    ExReleaseFastMutex((PFAST_MUTEX)(a1 + 2120));
  }
  a2->MdlAddress = (PMDL)(a3 + 64);
  v9 = a2->Tail.Overlay.CurrentStackLocation;
  *(_OWORD *)&v9[-1].MajorFunction = *(_OWORD *)&v9->MajorFunction;
  *(_OWORD *)&v9[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v9->Parameters.NotifyDirectoryEx.CompletionFilter;
  *(_OWORD *)(&v9[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v9->Parameters.SetQuota + 6);
  v9[-1].FileObject = v9->FileObject;
  v9[-1].Control = 0;
  v10 = a2->Tail.Overlay.CurrentStackLocation;
  v10[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)FastWriteCompletionRoutine;
  v10[-1].Context = (PVOID)a3;
  v10[-1].Control = -32;
  FvePerfTraceDevPtr(a1, FVE_PERF_WRITE_SUBREQUEST_START, a2);
  if ( v7 >= 0 )
  {
    if ( *(_DWORD *)(a1 + 2328) == 1 )
    {
      _InterlockedIncrement64((volatile signed __int64 *)(*(_QWORD *)(a1 + 2336) + 56LL));
    }
    else
    {
      LockArray_high = HIDWORD(KeGetPcr()[1].LockArray);
      ++*(_QWORD *)(296 * LockArray_high + *(_QWORD *)(a1 + 2336) + 56);
    }
    IofCallDriver(*(PDEVICE_OBJECT *)(a1 + 112), a2);
  }
  else
  {
    a2->IoStatus.Status = v7;
    a2->IoStatus.Information = 0;
    if ( (int)FastWriteCompletionRoutine(CurrentStackLocation->DeviceObject, a2, a3) >= 0 )
      IofCompleteRequest(a2, 0);
  }
}

```

## disassembly

```asm
0x1400b9a20  push    rbx
0x1400b9a22  push    rbp
0x1400b9a23  push    rsi
0x1400b9a24  push    rdi
0x1400b9a25  push    r14
0x1400b9a27  push    r15
0x1400b9a29  sub     rsp, 28h
0x1400b9a2d  mov     r15, [rdx+0B8h]
0x1400b9a34  mov     r14, r8
0x1400b9a37  mov     r8, rdx
0x1400b9a3a  mov     rdi, rdx
0x1400b9a3d  mov     r9, rdx
0x1400b9a40  mov     rsi, rcx
0x1400b9a43  lea     rdx, FVE_PERF_WRITE_SUBREQUEST_INIT
0x1400b9a4a  call    FvePerfTraceDevPtrPtr
0x1400b9a4f  mov     rcx, [rdi+8]
0x1400b9a53  lea     r8, FastWriteMapped
0x1400b9a5a  mov     r9, rdi
0x1400b9a5d  mov     edx, 4
0x1400b9a62  call    cs:__imp_MmMapMdl
0x1400b9a69  nop     dword ptr [rax+rax+00h]
0x1400b9a6e  mov     ebp, eax
0x1400b9a70  test    eax, eax
0x1400b9a72  jns     short loc_1400B9AE2
0x1400b9a74  lea     rbx, [rsi+848h]
0x1400b9a7b  mov     rcx, rbx; FastMutex
0x1400b9a7e  call    cs:__imp_ExAcquireFastMutex
0x1400b9a85  nop     dword ptr [rax+rax+00h]
0x1400b9a8a  mov     r8, [rdi+8]; MemoryDescriptorList
0x1400b9a8e  mov     r9d, 1; CacheType
0x1400b9a94  mov     rcx, [rsi+838h]; MappingAddress
0x1400b9a9b  mov     edx, 72455646h; PoolTag
0x1400b9aa0  call    cs:__imp_MmMapLockedPagesWithReservedMapping
0x1400b9aa7  nop     dword ptr [rax+rax+00h]
0x1400b9aac  mov     rdx, rax
0x1400b9aaf  mov     rcx, rdi
0x1400b9ab2  call    FastWriteMapped
0x1400b9ab7  mov     r8, [rdi+8]; MemoryDescriptorList
0x1400b9abb  mov     edx, 72455646h; PoolTag
0x1400b9ac0  mov     rcx, [rsi+838h]; BaseAddress
0x1400b9ac7  call    cs:__imp_MmUnmapReservedMapping
0x1400b9ace  nop     dword ptr [rax+rax+00h]
0x1400b9ad3  mov     rcx, rbx; FastMutex
0x1400b9ad6  call    cs:__imp_ExReleaseFastMutex
0x1400b9add  nop     dword ptr [rax+rax+00h]
0x1400b9ae2  lea     rax, [r14+40h]
0x1400b9ae6  mov     r8, rdi
0x1400b9ae9  mov     [rdi+8], rax
0x1400b9aed  lea     rcx, FastWriteCompletionRoutine
0x1400b9af4  mov     rax, [rdi+0B8h]
0x1400b9afb  lea     rdx, FVE_PERF_WRITE_SUBREQUEST_START
0x1400b9b02  movups  xmm0, xmmword ptr [rax]
0x1400b9b05  movups  xmmword ptr [rax-48h], xmm0
0x1400b9b09  movups  xmm1, xmmword ptr [rax+10h]
0x1400b9b0d  movups  xmmword ptr [rax-38h], xmm1
0x1400b9b11  movups  xmm0, xmmword ptr [rax+20h]
0x1400b9b15  movups  xmmword ptr [rax-28h], xmm0
0x1400b9b19  movsd   xmm1, qword ptr [rax+30h]
0x1400b9b1e  movsd   qword ptr [rax-18h], xmm1
0x1400b9b23  mov     byte ptr [rax-45h], 0
0x1400b9b27  mov     rax, [rdi+0B8h]
0x1400b9b2e  mov     [rax-10h], rcx
0x1400b9b32  mov     rcx, rsi
0x1400b9b35  mov     [rax-8], r14
0x1400b9b39  mov     byte ptr [rax-45h], 0E0h
0x1400b9b3d  call    FvePerfTraceDevPtr
0x1400b9b42  test    ebp, ebp
0x1400b9b44  jns     short loc_1400B9B77
0x1400b9b46  mov     [rdi+30h], ebp
0x1400b9b49  mov     r8, r14
0x1400b9b4c  mov     qword ptr [rdi+38h], 0
0x1400b9b54  mov     rdx, rdi
0x1400b9b57  mov     rcx, [r15+28h]
0x1400b9b5b  call    FastWriteCompletionRoutine
0x1400b9b60  test    eax, eax
0x1400b9b62  js      short loc_1400B9BBE
0x1400b9b64  xor     edx, edx; PriorityBoost
0x1400b9b66  mov     rcx, rdi; Irp
0x1400b9b69  call    cs:__imp_IofCompleteRequest
0x1400b9b70  nop     dword ptr [rax+rax+00h]
0x1400b9b75  jmp     short loc_1400B9BBE
0x1400b9b77  cmp     dword ptr [rsi+918h], 1
0x1400b9b7e  jnz     short loc_1400B9B8E
0x1400b9b80  mov     rax, [rsi+920h]
0x1400b9b87  lock inc qword ptr [rax+38h]
0x1400b9b8c  jmp     short loc_1400B9BAB
0x1400b9b8e  mov     eax, gs:1A4h
0x1400b9b96  mov     ecx, eax
0x1400b9b98  mov     rax, [rsi+920h]
0x1400b9b9f  imul    rdx, rcx, 128h
0x1400b9ba6  inc     qword ptr [rdx+rax+38h]
0x1400b9bab  mov     rcx, [rsi+70h]; DeviceObject
0x1400b9baf  mov     rdx, rdi; Irp
0x1400b9bb2  call    cs:__imp_IofCallDriver
0x1400b9bb9  nop     dword ptr [rax+rax+00h]
0x1400b9bbe  add     rsp, 28h
0x1400b9bc2  pop     r15
0x1400b9bc4  pop     r14
0x1400b9bc6  pop     rdi
0x1400b9bc7  pop     rsi
0x1400b9bc8  pop     rbp
0x1400b9bc9  pop     rbx
0x1400b9bca  retn
```
