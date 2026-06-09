# FIPostFSControlCallback

- ea: `0x140001480`
- end: `0x140001565`
- name: `FIPostFSControlCallback`
- size: `229`
- prototype: `FLT_POSTOP_CALLBACK_STATUS __stdcall(PFLT_CALLBACK_DATA Data, PCFLT_RELATED_OBJECTS FltObjects, PVOID CompletionContext, FLT_POST_OPERATION_FLAGS Flags)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140001480`
- `0x140001570`
- `0x140001644`
- `0x140001790`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x1400014ad`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400014d5`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400014ad`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400014d5`
- `FLTMGR!FltDoCompletionProcessingWhenSafe` at `0x140001542`
- `FLTMGR!FltDoCompletionProcessingWhenSafe` at `0x140001542`

## pseudocode

```c
__int64 __fastcall FIPostFSControlCallback(
        PFLT_CALLBACK_DATA Data,
        PCFLT_RELATED_OBJECTS FltObjects,
        PVOID CompletionContext,
        FLT_POST_OPERATION_FLAGS Flags)
{
  PFLT_IO_PARAMETER_BLOCK Iopb; // rax
  DWORD LowPart; // edi
  enum _FLT_POSTOP_CALLBACK_STATUS RetPostOperationStatus; // [rsp+50h] [rbp+8h] BYREF

  Iopb = Data->Iopb;
  RetPostOperationStatus = FLT_POSTOP_FINISHED_PROCESSING;
  LowPart = Iopb->Parameters.Read.ByteOffset.LowPart;
  if ( KeGetCurrentIrql() > 1u )
  {
    FltDoCompletionProcessingWhenSafe(
      Data,
      FltObjects,
      CompletionContext,
      Flags,
      FIPostFSControlCallback,
      &RetPostOperationStatus);
    CompletionContext = 0;
  }
  else if ( *(_QWORD *)(qword_140009A00 + 24) )
  {
    FIETWLogOperationEnd(Data);
  }
  if ( KeGetCurrentIrql() <= 1u )
  {
    if ( ((LowPart - 589848) & 0xFFFFFFF7) == 0 )
      _InterlockedDecrement(&dword_1400099F8);
    if ( ((unsigned __int8)CompletionContext & 7) != 0 )
      FIPfFileFSOpPostCallbackCleanup(CompletionContext);
    if ( LowPart == 589940 )
      FIPostMoveFile(Data);
  }
  return (unsigned int)RetPostOperationStatus;
}

```

## disassembly

```asm
0x140001480  mov     [rsp+arg_8], rbx
0x140001485  mov     [rsp+arg_10], rbp
0x14000148a  push    rsi
0x14000148b  push    rdi
0x14000148c  push    r14
0x14000148e  sub     rsp, 30h
0x140001492  mov     rax, [rcx+10h]
0x140001496  mov     ebp, r9d
0x140001499  mov     [rsp+48h+arg_0], 0
0x1400014a1  mov     rsi, r8
0x1400014a4  mov     r14, rdx
0x1400014a7  mov     rbx, rcx
0x1400014aa  mov     edi, [rax+28h]
0x1400014ad  call    cs:__imp_KeGetCurrentIrql
0x1400014b4  nop     dword ptr [rax+rax+00h]
0x1400014b9  cmp     al, 1
0x1400014bb  ja      short loc_140001520
0x1400014bd  mov     rax, cs:qword_140009A00
0x1400014c4  mov     rcx, [rax+18h]
0x1400014c8  test    rcx, rcx
0x1400014cb  jz      short loc_1400014D5
0x1400014cd  mov     rcx, rbx
0x1400014d0  call    FIETWLogOperationEnd
0x1400014d5  call    cs:__imp_KeGetCurrentIrql
0x1400014dc  nop     dword ptr [rax+rax+00h]
0x1400014e1  cmp     al, 1
0x1400014e3  ja      short loc_140001508
0x1400014e5  lea     eax, [rdi-90018h]
0x1400014eb  test    eax, 0FFFFFFF7h
0x1400014f0  jz      short loc_14000155C
0x1400014f2  test    sil, 7
0x1400014f6  jnz     short loc_140001552
0x1400014f8  cmp     edi, 90074h
0x1400014fe  jnz     short loc_140001508
0x140001500  mov     rcx, rbx
0x140001503  call    FIPostMoveFile
0x140001508  mov     eax, [rsp+48h+arg_0]
0x14000150c  mov     rbx, [rsp+48h+arg_8]
0x140001511  mov     rbp, [rsp+48h+arg_10]
0x140001516  add     rsp, 30h
0x14000151a  pop     r14
0x14000151c  pop     rdi
0x14000151d  pop     rsi
0x14000151e  retn
0x140001520  lea     rax, [rsp+48h+arg_0]
0x140001525  mov     r9d, ebp; Flags
0x140001528  mov     [rsp+48h+RetPostOperationStatus], rax; RetPostOperationStatus
0x14000152d  mov     r8, rsi; CompletionContext
0x140001530  lea     rax, FIPostFSControlCallback
0x140001537  mov     rdx, r14; FltObjects
0x14000153a  mov     rcx, rbx; Data
0x14000153d  mov     [rsp+48h+SafePostCallback], rax; SafePostCallback
0x140001542  call    cs:__imp_FltDoCompletionProcessingWhenSafe
0x140001549  nop     dword ptr [rax+rax+00h]
0x14000154e  xor     esi, esi
0x140001550  jmp     short loc_1400014D5
0x140001552  mov     rcx, rsi
0x140001555  call    FIPfFileFSOpPostCallbackCleanup
0x14000155a  jmp     short loc_1400014F8
0x14000155c  lock dec cs:dword_1400099F8
0x140001563  jmp     short loc_1400014F2
```
