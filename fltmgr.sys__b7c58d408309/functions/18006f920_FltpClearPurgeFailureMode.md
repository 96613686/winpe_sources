# FltpClearPurgeFailureMode

- ea: `0x18006f920`
- end: `0x18006fa54`
- name: `FltpClearPurgeFailureMode`
- size: `308`
- prototype: `__int64 __fastcall(_QWORD *Context, char)`
- caller_count: `3`
- callee_count: `7`
- tags: ``

## callers

- `0x180054680`
- `0x18006c670`
- `0x18006f880`

## callees

- `0x180008080`
- `0x180008a70`
- `0x180009f20`
- `0x18000c700`
- `0x1800183b0`
- `0x180019520`
- `0x18006f920`

## import_xrefs

- `ntoskrnl!ExQueueWorkItem` at `0x18007ac0d`
- `ntoskrnl!ExQueueWorkItem` at `0x18007ac0d`
- `ntoskrnl!KeDelayExecutionThread` at `0x18007abd6`
- `ntoskrnl!KeDelayExecutionThread` at `0x18007abd6`

## pseudocode

```c
__int64 __fastcall FltpClearPurgeFailureMode(_QWORD *Context, char a2)
{
  __int64 v2; // rbx
  __int64 v5; // r8
  PFLT_CALLBACK_DATA v7; // rbp
  _DWORD *v8; // r15
  unsigned int Status; // r14d
  PFLT_CALLBACK_DATA CallbackData; // [rsp+60h] [rbp+8h] BYREF
  LARGE_INTEGER Interval; // [rsp+70h] [rbp+18h] BYREF

  v2 = *(Context - 12);
  Interval.QuadPart = 0;
  CallbackData = 0;
  v5 = *(_QWORD *)(*(_QWORD *)v2 + 64LL);
  if ( (*(_DWORD *)(v5 + 56) & 0x200) != 0 )
    return 0;
  FltpAllocateCallbackDataMustSucceed(*(_QWORD *)v2, *(_QWORD *)(v2 + 8), v5, &CallbackData);
  v7 = CallbackData;
  v8 = (_DWORD *)(v2 + 48);
  while ( 1 )
  {
    *v8 |= 2u;
    FltReuseCallbackData(v7);
    v7->Iopb->MajorFunction = 13;
    v7->Iopb->MinorFunction = 0;
    v7->Iopb->Parameters.Read.ByteOffset.LowPart = 590448;
    v7->Iopb->Parameters.Create.Options = 4;
    v7->Iopb->Parameters.Read.Length = 0;
    v7->Iopb->Parameters.CreatePipe.Parameters = v8;
    v7->Iopb->IrpFlags = 20;
    FltPerformSynchronousIo(v7);
    Status = v7->IoStatus.Status;
    if ( (int)FltpDbgStatus(Status) >= 0 )
      break;
    if ( Status == -1073741536 )
    {
      if ( !a2 )
      {
        FltReferenceContext(Context);
        *(_QWORD *)(v2 + 80) = Context;
        *(_QWORD *)(v2 + 72) = FltpClearPurgeFailureModeWorker;
        *(_QWORD *)(v2 + 56) = 0;
        ExQueueWorkItem((PWORK_QUEUE_ITEM)(v2 + 56), CriticalWorkQueue);
        break;
      }
LABEL_12:
      Status = 0;
      break;
    }
    if ( Status != -1073741670 && Status != -1073741801 )
      goto LABEL_12;
    Interval.QuadPart = -100000;
    KeDelayExecutionThread(0, 0, &Interval);
  }
  FltFreeCallbackData(v7);
  return Status;
}

```

## disassembly

```asm
0x18006f920  push    rbx
0x18006f922  push    rsi
0x18006f923  push    rdi
0x18006f924  push    r12
0x18006f926  sub     rsp, 38h
0x18006f92a  mov     rbx, [rcx-60h]
0x18006f92e  xor     r12d, r12d
0x18006f931  mov     qword ptr [rsp+58h+Interval], r12
0x18006f936  movzx   esi, dl
0x18006f939  mov     rdi, rcx
0x18006f93c  mov     [rsp+58h+CallbackData], r12
0x18006f941  mov     rax, [rbx]
0x18006f944  mov     r8, [rax+40h]
0x18006f948  mov     eax, [r8+38h]
0x18006f94c  bt      eax, 9
0x18006f950  jnb     short loc_18006F95F
0x18006f952  xor     eax, eax
0x18006f954  add     rsp, 38h
0x18006f958  pop     r12
0x18006f95a  pop     rdi
0x18006f95b  pop     rsi
0x18006f95c  pop     rbx
0x18006f95d  retn
0x18006f95f  mov     rdx, [rbx+8]
0x18006f963  lea     r9, [rsp+58h+CallbackData]
0x18006f968  mov     rcx, [rbx]
0x18006f96b  mov     [rsp+58h+arg_8], rbp
0x18006f970  mov     [rsp+58h+var_28], r13
0x18006f975  mov     [rsp+58h+var_30], r14
0x18006f97a  mov     [rsp+58h+var_38], r15
0x18006f97f  call    FltpAllocateCallbackDataMustSucceed
0x18006f984  mov     rbp, [rsp+58h+CallbackData]
0x18006f989  lea     r15, [rbx+30h]
0x18006f98d  mov     r13d, 33Dh
0x18006f993  or      dword ptr [r15], 2
0x18006f997  mov     rcx, rbp; CallbackData
0x18006f99a  call    FltReuseCallbackData
0x18006f99f  mov     rax, [rbp+10h]
0x18006f9a3  mov     rcx, rbp; CallbackData
0x18006f9a6  mov     byte ptr [rax+4], 0Dh
0x18006f9aa  mov     rax, [rbp+10h]
0x18006f9ae  mov     [rax+5], r12b
0x18006f9b2  mov     rax, [rbp+10h]
0x18006f9b6  mov     dword ptr [rax+28h], 90270h
0x18006f9bd  mov     rax, [rbp+10h]
0x18006f9c1  mov     dword ptr [rax+20h], 4
0x18006f9c8  mov     rax, [rbp+10h]
0x18006f9cc  mov     [rax+18h], r12d
0x18006f9d0  mov     rax, [rbp+10h]
0x18006f9d4  mov     [rax+30h], r15
0x18006f9d8  mov     rax, [rbp+10h]
0x18006f9dc  mov     dword ptr [rax], 14h
0x18006f9e2  call    FltPerformSynchronousIo
0x18006f9e7  mov     r14d, [rbp+18h]
0x18006f9eb  lea     rdx, aMinkernelFsFil_11; "minkernel\\fs\\filtermgr\\filter\\secti"...
0x18006f9f2  xor     r9d, r9d
0x18006f9f5  mov     r8d, r13d
0x18006f9f8  mov     ecx, r14d
0x18006f9fb  call    FltpDbgStatus
0x18006fa00  test    eax, eax
0x18006fa02  js      short loc_18006FA28
0x18006fa04  mov     rcx, rbp; CallbackData
0x18006fa07  call    FltFreeCallbackData
0x18006fa0c  mov     r15, [rsp+58h+var_38]
0x18006fa11  mov     eax, r14d
0x18006fa14  mov     r14, [rsp+58h+var_30]
0x18006fa19  mov     r13, [rsp+58h+var_28]
0x18006fa1e  mov     rbp, [rsp+58h+arg_8]
0x18006fa23  jmp     loc_18006F954
0x18006fa28  cmp     r14d, 0C0000120h
0x18006fa2f  jz      loc_18007ABE8
0x18006fa35  cmp     r14d, 0C000009Ah
0x18006fa3c  jz      loc_18007ABC4
0x18006fa42  cmp     r14d, 0C0000017h
0x18006fa49  jz      loc_18007ABC4
0x18006fa4f  jmp     loc_18007AC1F
0x18007abc4  lea     r8, [rsp+58h+Interval]; Interval
0x18007abc9  mov     qword ptr [rsp+58h+Interval], 0FFFFFFFFFFFE7960h
0x18007abd2  xor     edx, edx; Alertable
0x18007abd4  xor     ecx, ecx; WaitMode
0x18007abd6  call    cs:__imp_KeDelayExecutionThread
0x18007abdd  nop     dword ptr [rax+rax+00h]
0x18007abe2  nop
0x18007abe3  jmp     loc_18006F993
0x18007abe8  test    sil, sil
0x18007abeb  jnz     short loc_18007AC1F
0x18007abed  mov     rcx, rdi; Context
0x18007abf0  call    FltReferenceContext
0x18007abf5  lea     rcx, [rbx+38h]; WorkItem
0x18007abf9  xor     edx, edx; QueueType
0x18007abfb  lea     rax, FltpClearPurgeFailureModeWorker
0x18007ac02  mov     [rcx+18h], rdi
0x18007ac06  mov     [rcx+10h], rax
0x18007ac0a  mov     [rcx], r12
0x18007ac0d  call    cs:__imp_ExQueueWorkItem
0x18007ac14  nop     dword ptr [rax+rax+00h]
0x18007ac19  nop
0x18007ac1a  jmp     loc_18006FA04
0x18007ac1f  mov     r14d, r12d
0x18007ac22  jmp     loc_18006FA04
```
