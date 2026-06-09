# FastWriteEncrypt

- ea: `0x1400bbaf0`
- end: `0x1400bbc9c`
- name: `FastWriteEncrypt`
- size: `428`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1400bbd90`
- `0x1400ec57c`

## callees

- `0x14002d140`
- `0x14009e9b0`
- `0x1400bb9d0`
- `0x1400bbaf0`
- `0x1400dba60`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x1400bbc82`
- `ntoskrnl!IofCallDriver` at `0x1400bbc82`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400bbb4e`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400bbb4e`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400bbba6`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400bbba6`
- `ntoskrnl!IofCompleteRequest` at `0x1400bbc39`
- `ntoskrnl!IofCompleteRequest` at `0x1400bbc39`
- `ntoskrnl!MmMapLockedPagesWithReservedMapping` at `0x1400bbb70`
- `ntoskrnl!MmMapLockedPagesWithReservedMapping` at `0x1400bbb70`
- `ntoskrnl!MmUnmapReservedMapping` at `0x1400bbb97`
- `ntoskrnl!MmUnmapReservedMapping` at `0x1400bbb97`
- `ntoskrnl!MmMapMdl` at `0x1400bbb32`
- `ntoskrnl!MmMapMdl` at `0x1400bbb32`

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
    if ( *(_DWORD *)(a1 + 2344) == 1 )
    {
      _InterlockedIncrement64((volatile signed __int64 *)(*(_QWORD *)(a1 + 2352) + 56LL));
    }
    else
    {
      LockArray_high = HIDWORD(KeGetPcr()[1].LockArray);
      ++*(_QWORD *)(296 * LockArray_high + *(_QWORD *)(a1 + 2352) + 56);
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
0x1400bbaf0  push    rbx
0x1400bbaf2  push    rbp
0x1400bbaf3  push    rsi
0x1400bbaf4  push    rdi
0x1400bbaf5  push    r14
0x1400bbaf7  push    r15
0x1400bbaf9  sub     rsp, 28h
0x1400bbafd  mov     r15, [rdx+0B8h]
0x1400bbb04  mov     r14, r8
0x1400bbb07  mov     r8, rdx
0x1400bbb0a  mov     rdi, rdx
0x1400bbb0d  mov     r9, rdx
0x1400bbb10  mov     rsi, rcx
0x1400bbb13  lea     rdx, FVE_PERF_WRITE_SUBREQUEST_INIT
0x1400bbb1a  call    FvePerfTraceDevPtrPtr
0x1400bbb1f  mov     rcx, [rdi+8]
0x1400bbb23  lea     r8, FastWriteMapped
0x1400bbb2a  mov     r9, rdi
0x1400bbb2d  mov     edx, 4
0x1400bbb32  call    cs:__imp_MmMapMdl
0x1400bbb39  nop     dword ptr [rax+rax+00h]
0x1400bbb3e  mov     ebp, eax
0x1400bbb40  test    eax, eax
0x1400bbb42  jns     short loc_1400BBBB2
0x1400bbb44  lea     rbx, [rsi+848h]
0x1400bbb4b  mov     rcx, rbx; FastMutex
0x1400bbb4e  call    cs:__imp_ExAcquireFastMutex
0x1400bbb55  nop     dword ptr [rax+rax+00h]
0x1400bbb5a  mov     r8, [rdi+8]; MemoryDescriptorList
0x1400bbb5e  mov     r9d, 1; CacheType
0x1400bbb64  mov     rcx, [rsi+838h]; MappingAddress
0x1400bbb6b  mov     edx, 72455646h; PoolTag
0x1400bbb70  call    cs:__imp_MmMapLockedPagesWithReservedMapping
0x1400bbb77  nop     dword ptr [rax+rax+00h]
0x1400bbb7c  mov     rdx, rax
0x1400bbb7f  mov     rcx, rdi
0x1400bbb82  call    FastWriteMapped
0x1400bbb87  mov     r8, [rdi+8]; MemoryDescriptorList
0x1400bbb8b  mov     edx, 72455646h; PoolTag
0x1400bbb90  mov     rcx, [rsi+838h]; BaseAddress
0x1400bbb97  call    cs:__imp_MmUnmapReservedMapping
0x1400bbb9e  nop     dword ptr [rax+rax+00h]
0x1400bbba3  mov     rcx, rbx; FastMutex
0x1400bbba6  call    cs:__imp_ExReleaseFastMutex
0x1400bbbad  nop     dword ptr [rax+rax+00h]
0x1400bbbb2  lea     rax, [r14+40h]
0x1400bbbb6  mov     r8, rdi
0x1400bbbb9  mov     [rdi+8], rax
0x1400bbbbd  lea     rcx, FastWriteCompletionRoutine
0x1400bbbc4  mov     rax, [rdi+0B8h]
0x1400bbbcb  lea     rdx, FVE_PERF_WRITE_SUBREQUEST_START
0x1400bbbd2  movups  xmm0, xmmword ptr [rax]
0x1400bbbd5  movups  xmmword ptr [rax-48h], xmm0
0x1400bbbd9  movups  xmm1, xmmword ptr [rax+10h]
0x1400bbbdd  movups  xmmword ptr [rax-38h], xmm1
0x1400bbbe1  movups  xmm0, xmmword ptr [rax+20h]
0x1400bbbe5  movups  xmmword ptr [rax-28h], xmm0
0x1400bbbe9  movsd   xmm1, qword ptr [rax+30h]
0x1400bbbee  movsd   qword ptr [rax-18h], xmm1
0x1400bbbf3  mov     byte ptr [rax-45h], 0
0x1400bbbf7  mov     rax, [rdi+0B8h]
0x1400bbbfe  mov     [rax-10h], rcx
0x1400bbc02  mov     rcx, rsi
0x1400bbc05  mov     [rax-8], r14
0x1400bbc09  mov     byte ptr [rax-45h], 0E0h
0x1400bbc0d  call    FvePerfTraceDevPtr
0x1400bbc12  test    ebp, ebp
0x1400bbc14  jns     short loc_1400BBC47
0x1400bbc16  mov     [rdi+30h], ebp
0x1400bbc19  mov     r8, r14
0x1400bbc1c  mov     qword ptr [rdi+38h], 0
0x1400bbc24  mov     rdx, rdi
0x1400bbc27  mov     rcx, [r15+28h]
0x1400bbc2b  call    FastWriteCompletionRoutine
0x1400bbc30  test    eax, eax
0x1400bbc32  js      short loc_1400BBC8E
0x1400bbc34  xor     edx, edx; PriorityBoost
0x1400bbc36  mov     rcx, rdi; Irp
0x1400bbc39  call    cs:__imp_IofCompleteRequest
0x1400bbc40  nop     dword ptr [rax+rax+00h]
0x1400bbc45  jmp     short loc_1400BBC8E
0x1400bbc47  cmp     dword ptr [rsi+928h], 1
0x1400bbc4e  jnz     short loc_1400BBC5E
0x1400bbc50  mov     rax, [rsi+930h]
0x1400bbc57  lock inc qword ptr [rax+38h]
0x1400bbc5c  jmp     short loc_1400BBC7B
0x1400bbc5e  mov     eax, gs:1A4h
0x1400bbc66  mov     ecx, eax
0x1400bbc68  mov     rax, [rsi+930h]
0x1400bbc6f  imul    rdx, rcx, 128h
0x1400bbc76  inc     qword ptr [rdx+rax+38h]
0x1400bbc7b  mov     rcx, [rsi+70h]; DeviceObject
0x1400bbc7f  mov     rdx, rdi; Irp
0x1400bbc82  call    cs:__imp_IofCallDriver
0x1400bbc89  nop     dword ptr [rax+rax+00h]
0x1400bbc8e  add     rsp, 28h
0x1400bbc92  pop     r15
0x1400bbc94  pop     r14
0x1400bbc96  pop     rdi
0x1400bbc97  pop     rsi
0x1400bbc98  pop     rbp
0x1400bbc99  pop     rbx
0x1400bbc9a  retn
```
