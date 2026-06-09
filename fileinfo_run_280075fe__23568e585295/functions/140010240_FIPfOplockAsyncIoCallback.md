# FIPfOplockAsyncIoCallback

- ea: `0x140010240`
- end: `0x140010348`
- name: `FIPfOplockAsyncIoCallback`
- size: `264`
- prototype: `void __stdcall(PFLT_CALLBACK_DATA CallbackData, PFLT_CONTEXT Context)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1400101c8`
- `0x140010240`

## import_xrefs

- `ntoskrnl!KeQueryPriorityThread` at `0x1400102c9`
- `ntoskrnl!KeQueryPriorityThread` at `0x1400102c9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001031c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001031c`
- `FLTMGR!FltFreeCallbackData` at `0x14001032b`
- `FLTMGR!FltFreeCallbackData` at `0x14001032b`
- `FLTMGR!FltQueueGenericWorkItem` at `0x1400102f0`
- `FLTMGR!FltQueueGenericWorkItem` at `0x1400102f0`

## pseudocode

```c
void __fastcall FIPfOplockAsyncIoCallback(PFLT_CALLBACK_DATA CallbackData, PFLT_CONTEXT Context)
{
  _DWORD *Parameters; // rsi
  KPRIORITY PriorityThread; // eax

  Parameters = CallbackData->Iopb->Parameters.CreatePipe.Parameters;
  if ( (Parameters[3] & 1) != 0 )
  {
    _InterlockedIncrement(&dword_1400097DC);
    *((_QWORD *)Context + 11) = ((MEMORY[0xFFFFF78000000004] * HIDWORD(MEMORY[0xFFFFF78000000320])) << 8)
                              + ((MEMORY[0xFFFFF78000000004] * (unsigned __int64)MEMORY[0xFFFFF78000000320]) >> 24);
    if ( _InterlockedIncrement64((volatile signed __int64 *)Context + 12) <= 1 )
      __fastfail(0xEu);
    PriorityThread = KeQueryPriorityThread(KeGetCurrentThread());
    if ( FltQueueGenericWorkItem(
           *((PFLT_GENERIC_WORKITEM *)Context + 6),
           FIGlobals,
           FIPfOplockBreakNotifyWorker,
           (WORK_QUEUE_TYPE)(PriorityThread + 32),
           Context) < 0 )
    {
      _InterlockedIncrement(&dword_1400099B4);
      FIPfOpenContextDereference(Context);
    }
  }
  FIPfOpenContextDereference(Context);
  ExFreePoolWithTag(Parameters, 0);
  FltFreeCallbackData(CallbackData);
}

```

## disassembly

```asm
0x140010240  mov     [rsp+arg_0], rbx
0x140010245  mov     [rsp+arg_8], rsi
0x14001024a  push    rdi
0x14001024b  sub     rsp, 30h
0x14001024f  mov     rax, [rcx+10h]
0x140010253  mov     rbx, rdx
0x140010256  mov     rdi, rcx
0x140010259  mov     rsi, [rax+30h]
0x14001025d  mov     eax, [rsi+0Ch]
0x140010260  test    al, 1
0x140010262  jz      loc_14001030F
0x140010268  lock inc cs:dword_1400097DC
0x14001026f  mov     rcx, 0FFFFF78000000004h
0x140010279  mov     rax, 0FFFFF78000000320h
0x140010283  mov     rax, [rax]
0x140010286  mov     edx, [rcx]
0x140010288  mov     ecx, eax
0x14001028a  shr     rax, 20h
0x14001028e  imul    rax, rdx
0x140010292  imul    rcx, rdx
0x140010296  shl     rax, 8
0x14001029a  shr     rcx, 18h
0x14001029e  add     rcx, rax
0x1400102a1  mov     eax, 1
0x1400102a6  mov     [rbx+58h], rcx
0x1400102aa  lock xadd [rbx+60h], rax
0x1400102b0  inc     rax
0x1400102b3  cmp     rax, 1
0x1400102b7  jg      short loc_1400102C0
0x1400102b9  mov     ecx, 0Eh
0x1400102be  int     29h; Win8: RtlFailFast(ecx)
0x1400102c0  mov     rcx, gs:188h; Thread
0x1400102c9  call    cs:__imp_KeQueryPriorityThread
0x1400102d0  nop     dword ptr [rax+rax+00h]
0x1400102d5  mov     rdx, cs:FIGlobals; FltObject
0x1400102dc  lea     r8, FIPfOplockBreakNotifyWorker; WorkerRoutine
0x1400102e3  mov     rcx, [rbx+30h]; FltWorkItem
0x1400102e7  mov     [rsp+38h+Context], rbx; Context
0x1400102ec  lea     r9d, [rax+20h]; QueueType
0x1400102f0  call    cs:__imp_FltQueueGenericWorkItem
0x1400102f7  nop     dword ptr [rax+rax+00h]
0x1400102fc  test    eax, eax
0x1400102fe  jns     short loc_14001030F
0x140010300  lock inc cs:dword_1400099B4
0x140010307  mov     rcx, rbx; P
0x14001030a  call    FIPfOpenContextDereference
0x14001030f  mov     rcx, rbx; P
0x140010312  call    FIPfOpenContextDereference
0x140010317  xor     edx, edx; Tag
0x140010319  mov     rcx, rsi; P
0x14001031c  call    cs:__imp_ExFreePoolWithTag
0x140010323  nop     dword ptr [rax+rax+00h]
0x140010328  mov     rcx, rdi; CallbackData
0x14001032b  call    cs:__imp_FltFreeCallbackData
0x140010332  nop     dword ptr [rax+rax+00h]
0x140010337  mov     rbx, [rsp+38h+arg_0]
0x14001033c  mov     rsi, [rsp+38h+arg_8]
0x140010341  add     rsp, 30h
0x140010345  pop     rdi
0x140010346  retn
```
