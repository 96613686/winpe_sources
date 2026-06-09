# FveFilterRundownRead

- ea: `0x140027fb0`
- end: `0x1400281d2`
- name: `FveFilterRundownRead`
- size: `546`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140027fb0`
- `0x1400281d8`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140028039`
- `ntoskrnl!IofCompleteRequest` at `0x1400281bc`
- `ntoskrnl!IofCompleteRequest` at `0x140028039`
- `ntoskrnl!IofCompleteRequest` at `0x1400281bc`
- `ntoskrnl!IoQueueWorkItem` at `0x1400280bc`
- `ntoskrnl!IoQueueWorkItem` at `0x1400280bc`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400280d0`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400280d0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140028069`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140028069`

## pseudocode

```c
__int64 __fastcall FveFilterRundownRead(__int64 a1, IRP *a2, __int64 a3, __int64 a4)
{
  _QWORD *v4; // r8
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r9
  UCHAR MajorFunction; // cl
  __int64 v9; // rsi
  char *Context; // rdi
  unsigned int v11; // edi
  KIRQL v12; // al
  struct _LIST_ENTRY *v13; // r8
  struct _LIST_ENTRY *v14; // rcx
  KIRQL v15; // r14
  struct _LIST_ENTRY *Flink; // rdx
  __int64 (__fastcall *CompletionRoutine)(); // rax
  _QWORD *v18; // r8
  unsigned int v19; // r11d
  __int64 v20; // rbp
  __int64 v21; // rax

  v4 = *(_QWORD **)(a1 + 64);
  if ( !*v4 )
  {
    CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
    MajorFunction = CurrentStackLocation->MajorFunction;
    if ( (unsigned __int8)(CurrentStackLocation->MajorFunction - 3) > 1u )
    {
LABEL_8:
      v11 = -1073741823;
      a2->IoStatus.Information = 0;
      a2->IoStatus.Status = -1073741823;
      IofCompleteRequest(a2, 0);
      return v11;
    }
    v9 = v4[3];
    if ( (__int64 (__fastcall *)())CurrentStackLocation->CompletionRoutine == FveTestRwCompletion )
    {
      Context = (char *)CurrentStackLocation->Context;
    }
    else
    {
      if ( MajorFunction == 3 )
      {
        if ( (_UNKNOWN *)CurrentStackLocation->CompletionRoutine != &ReadCompletionRoutine )
          goto LABEL_8;
      }
      else
      {
        if ( MajorFunction != 4 )
          goto LABEL_8;
        if ( (_UNKNOWN *)CurrentStackLocation->CompletionRoutine != &WriteCompletionRoutine )
        {
          CompletionRoutine = (__int64 (__fastcall *)())CurrentStackLocation->CompletionRoutine;
          if ( CompletionRoutine != FveInlineWriteCompletionRoutineRdpLevel1
            && (char *)CompletionRoutine != (char *)FveInlineWriteCompletionRoutineRdpLevel2 )
          {
            goto LABEL_8;
          }
          v18 = *(_QWORD **)(v9 + 16);
          Context = 0;
          if ( v18 == (_QWORD *)(v9 + 16) )
            goto LABEL_8;
          while ( !Context )
          {
            v19 = *(_DWORD *)(v9 + 296);
            if ( v19 )
            {
              v20 = 0;
              do
              {
                if ( Context )
                  break;
                v21 = v18[4];
                if ( *(IRP **)(*(_QWORD *)(v21 + 8 * v20) + 24LL) == a2 )
                  Context = *(char **)(v21 + 8 * v20);
                v20 = (unsigned int)(v20 + 1);
              }
              while ( (unsigned int)v20 < v19 );
            }
            v18 = (_QWORD *)*v18;
            if ( v18 == (_QWORD *)(v9 + 16) )
              goto LABEL_7;
          }
          goto LABEL_10;
        }
      }
      Context = *(char **)(*((_QWORD *)CurrentStackLocation->Context + 2) + 192LL);
    }
LABEL_7:
    if ( !Context )
      goto LABEL_8;
LABEL_10:
    CurrentStackLocation->Control |= 1u;
    v12 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)Context + 14);
    v13 = (struct _LIST_ENTRY *)*((_QWORD *)Context + 13);
    v14 = (struct _LIST_ENTRY *)(Context + 96);
    v15 = v12;
    if ( (char *)v13->Flink != Context + 96 )
      __fastfail(3u);
    Flink = v14->Flink;
    a2->Tail.Overlay.ListEntry.Flink = v14;
    a2->Tail.Overlay.ListEntry.Blink = v13;
    v13->Flink = &a2->Tail.Overlay.ListEntry;
    *((_QWORD *)Context + 13) = &a2->Tail.Overlay.ListEntry;
    if ( Flink == v14 )
      IoQueueWorkItem(*((PIO_WORKITEM *)Context + 9), FveTestRwStorageWorker, *(WORK_QUEUE_TYPE *)(v9 + 344), Context);
    KeReleaseSpinLock((PKSPIN_LOCK)Context + 14, v15);
    return 259;
  }
  if ( *(_QWORD *)(v4[1] + 8LL) != a1 )
    return FveFilterRundownReadWrite(a1, a2, 0, a4);
  a2->IoStatus.Information = 0;
  a2->IoStatus.Status = -1073741808;
  IofCompleteRequest(a2, 0);
  return 3221225488LL;
}

```

## disassembly

```asm
0x140027fb0  push    rbx
0x140027fb2  sub     rsp, 20h
0x140027fb6  mov     r8, [rcx+40h]
0x140027fba  mov     rbx, rdx
0x140027fbd  cmp     qword ptr [r8], 0
0x140027fc1  jz      short loc_140027FE0
0x140027fc3  mov     rax, [r8+8]
0x140027fc7  cmp     [rax+8], rcx
0x140027fcb  jz      loc_1400281A8
0x140027fd1  xor     r8d, r8d
0x140027fd4  call    FveFilterRundownReadWrite
0x140027fd9  add     rsp, 20h
0x140027fdd  pop     rbx
0x140027fde  retn
0x140027fe0  mov     r9, [rdx+0B8h]
0x140027fe7  mov     [rsp+28h+arg_0], rbp
0x140027fec  mov     [rsp+28h+arg_8], rsi
0x140027ff1  mov     [rsp+28h+arg_10], rdi
0x140027ff6  movzx   ecx, byte ptr [r9]
0x140027ffa  mov     [rsp+28h+arg_18], r14
0x140027fff  lea     eax, [rcx-3]
0x140028002  cmp     al, 1
0x140028004  ja      short loc_140028024
0x140028006  mov     rsi, [r8+18h]
0x14002800a  lea     rax, FveTestRwCompletion
0x140028011  cmp     [r9+38h], rax
0x140028015  jnz     loc_1400280E6
0x14002801b  mov     rdi, [r9+40h]
0x14002801f  test    rdi, rdi
0x140028022  jnz     short loc_140028060
0x140028024  mov     edi, 0C0000001h
0x140028029  mov     qword ptr [rbx+38h], 0
0x140028031  xor     edx, edx; PriorityBoost
0x140028033  mov     [rbx+30h], edi
0x140028036  mov     rcx, rbx; Irp
0x140028039  call    cs:__imp_IofCompleteRequest
0x140028040  nop     dword ptr [rax+rax+00h]
0x140028045  mov     rsi, [rsp+28h+arg_8]
0x14002804a  mov     eax, edi
0x14002804c  mov     rdi, [rsp+28h+arg_10]
0x140028051  mov     rbp, [rsp+28h+arg_0]
0x140028056  mov     r14, [rsp+28h+arg_18]
0x14002805b  jmp     loc_140027FD9
0x140028060  or      byte ptr [r9+3], 1
0x140028065  lea     rcx, [rdi+70h]; SpinLock
0x140028069  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140028070  nop     dword ptr [rax+rax+00h]
0x140028075  mov     r8, [rdi+68h]
0x140028079  lea     rcx, [rdi+60h]
0x14002807d  movzx   r14d, al
0x140028081  cmp     [r8], rcx
0x140028084  jnz     loc_1400281A1
0x14002808a  mov     rdx, [rcx]
0x14002808d  lea     rax, [rbx+0A8h]
0x140028094  mov     [rax], rcx
0x140028097  mov     [rax+8], r8
0x14002809b  mov     [r8], rax
0x14002809e  mov     [rcx+8], rax
0x1400280a2  cmp     rdx, rcx
0x1400280a5  jnz     short loc_1400280C8
0x1400280a7  mov     r8d, [rsi+158h]; QueueType
0x1400280ae  lea     rdx, FveTestRwStorageWorker; WorkerRoutine
0x1400280b5  mov     rcx, [rdi+48h]; IoWorkItem
0x1400280b9  mov     r9, rdi; Context
0x1400280bc  call    cs:__imp_IoQueueWorkItem
0x1400280c3  nop     dword ptr [rax+rax+00h]
0x1400280c8  movzx   edx, r14b; NewIrql
0x1400280cc  lea     rcx, [rdi+70h]; SpinLock
0x1400280d0  call    cs:__imp_KeReleaseSpinLock
0x1400280d7  nop     dword ptr [rax+rax+00h]
0x1400280dc  mov     edi, 103h
0x1400280e1  jmp     loc_140028045
0x1400280e6  cmp     cl, 3
0x1400280e9  jnz     short loc_140028110
0x1400280eb  lea     rax, ReadCompletionRoutine
0x1400280f2  cmp     [r9+38h], rax
0x1400280f6  jnz     loc_140028024
0x1400280fc  mov     rax, [r9+40h]
0x140028100  mov     rcx, [rax+10h]
0x140028104  mov     rdi, [rcx+0C0h]
0x14002810b  jmp     loc_14002801F
0x140028110  cmp     cl, 4
0x140028113  jnz     loc_140028024
0x140028119  lea     rax, WriteCompletionRoutine
0x140028120  cmp     [r9+38h], rax
0x140028124  jz      short loc_1400280FC
0x140028126  cmp     cl, cl
0x140028128  jnz     loc_140028024
0x14002812e  mov     rax, [r9+38h]
0x140028132  lea     rcx, FveInlineWriteCompletionRoutineRdpLevel1
0x140028139  cmp     rax, rcx
0x14002813c  jz      short loc_14002814E
0x14002813e  lea     rcx, FveInlineWriteCompletionRoutineRdpLevel2
0x140028145  cmp     rax, rcx
0x140028148  jnz     loc_140028024
0x14002814e  mov     r8, [rsi+10h]
0x140028152  lea     r10, [rsi+10h]
0x140028156  xor     edi, edi
0x140028158  cmp     r8, r10
0x14002815b  jz      loc_140028024
0x140028161  test    rdi, rdi
0x140028164  jnz     loc_140028060
0x14002816a  mov     r11d, [rsi+128h]
0x140028171  test    r11d, r11d
0x140028174  jz      short loc_140028194
0x140028176  xor     ebp, ebp
0x140028178  test    rdi, rdi
0x14002817b  jnz     short loc_140028194
0x14002817d  mov     rax, [r8+20h]
0x140028181  mov     rdx, [rax+rbp*8]
0x140028185  cmp     [rdx+18h], rbx
0x140028189  cmovz   rdi, rdx
0x14002818d  inc     ebp
0x14002818f  cmp     ebp, r11d
0x140028192  jb      short loc_140028178
0x140028194  mov     r8, [r8]
0x140028197  cmp     r8, r10
0x14002819a  jnz     short loc_140028161
0x14002819c  jmp     loc_14002801F
0x1400281a1  mov     ecx, 3
0x1400281a6  int     29h; Win8: RtlFailFast(ecx)
0x1400281a8  mov     qword ptr [rdx+38h], 0
0x1400281b0  mov     rcx, rbx; Irp
0x1400281b3  mov     dword ptr [rdx+30h], 0C0000010h
0x1400281ba  xor     edx, edx; PriorityBoost
0x1400281bc  call    cs:__imp_IofCompleteRequest
0x1400281c3  nop     dword ptr [rax+rax+00h]
0x1400281c8  mov     eax, 0C0000010h
0x1400281cd  jmp     loc_140027FD9
```
