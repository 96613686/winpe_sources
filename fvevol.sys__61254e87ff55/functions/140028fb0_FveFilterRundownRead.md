# FveFilterRundownRead

- ea: `0x140028fb0`
- end: `0x1400291d2`
- name: `FveFilterRundownRead`
- size: `546`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140028fb0`
- `0x1400291d8`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140029039`
- `ntoskrnl!IofCompleteRequest` at `0x1400291bc`
- `ntoskrnl!IofCompleteRequest` at `0x140029039`
- `ntoskrnl!IofCompleteRequest` at `0x1400291bc`
- `ntoskrnl!IoQueueWorkItem` at `0x1400290bc`
- `ntoskrnl!IoQueueWorkItem` at `0x1400290bc`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400290d0`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400290d0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140029069`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140029069`

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
0x140028fb0  push    rbx
0x140028fb2  sub     rsp, 20h
0x140028fb6  mov     r8, [rcx+40h]
0x140028fba  mov     rbx, rdx
0x140028fbd  cmp     qword ptr [r8], 0
0x140028fc1  jz      short loc_140028FE0
0x140028fc3  mov     rax, [r8+8]
0x140028fc7  cmp     [rax+8], rcx
0x140028fcb  jz      loc_1400291A8
0x140028fd1  xor     r8d, r8d
0x140028fd4  call    FveFilterRundownReadWrite
0x140028fd9  add     rsp, 20h
0x140028fdd  pop     rbx
0x140028fde  retn
0x140028fe0  mov     r9, [rdx+0B8h]
0x140028fe7  mov     [rsp+28h+arg_0], rbp
0x140028fec  mov     [rsp+28h+arg_8], rsi
0x140028ff1  mov     [rsp+28h+arg_10], rdi
0x140028ff6  movzx   ecx, byte ptr [r9]
0x140028ffa  mov     [rsp+28h+arg_18], r14
0x140028fff  lea     eax, [rcx-3]
0x140029002  cmp     al, 1
0x140029004  ja      short loc_140029024
0x140029006  mov     rsi, [r8+18h]
0x14002900a  lea     rax, FveTestRwCompletion
0x140029011  cmp     [r9+38h], rax
0x140029015  jnz     loc_1400290E6
0x14002901b  mov     rdi, [r9+40h]
0x14002901f  test    rdi, rdi
0x140029022  jnz     short loc_140029060
0x140029024  mov     edi, 0C0000001h
0x140029029  mov     qword ptr [rbx+38h], 0
0x140029031  xor     edx, edx; PriorityBoost
0x140029033  mov     [rbx+30h], edi
0x140029036  mov     rcx, rbx; Irp
0x140029039  call    cs:__imp_IofCompleteRequest
0x140029040  nop     dword ptr [rax+rax+00h]
0x140029045  mov     rsi, [rsp+28h+arg_8]
0x14002904a  mov     eax, edi
0x14002904c  mov     rdi, [rsp+28h+arg_10]
0x140029051  mov     rbp, [rsp+28h+arg_0]
0x140029056  mov     r14, [rsp+28h+arg_18]
0x14002905b  jmp     loc_140028FD9
0x140029060  or      byte ptr [r9+3], 1
0x140029065  lea     rcx, [rdi+70h]; SpinLock
0x140029069  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140029070  nop     dword ptr [rax+rax+00h]
0x140029075  mov     r8, [rdi+68h]
0x140029079  lea     rcx, [rdi+60h]
0x14002907d  movzx   r14d, al
0x140029081  cmp     [r8], rcx
0x140029084  jnz     loc_1400291A1
0x14002908a  mov     rdx, [rcx]
0x14002908d  lea     rax, [rbx+0A8h]
0x140029094  mov     [rax], rcx
0x140029097  mov     [rax+8], r8
0x14002909b  mov     [r8], rax
0x14002909e  mov     [rcx+8], rax
0x1400290a2  cmp     rdx, rcx
0x1400290a5  jnz     short loc_1400290C8
0x1400290a7  mov     r8d, [rsi+158h]; QueueType
0x1400290ae  lea     rdx, FveTestRwStorageWorker; WorkerRoutine
0x1400290b5  mov     rcx, [rdi+48h]; IoWorkItem
0x1400290b9  mov     r9, rdi; Context
0x1400290bc  call    cs:__imp_IoQueueWorkItem
0x1400290c3  nop     dword ptr [rax+rax+00h]
0x1400290c8  movzx   edx, r14b; NewIrql
0x1400290cc  lea     rcx, [rdi+70h]; SpinLock
0x1400290d0  call    cs:__imp_KeReleaseSpinLock
0x1400290d7  nop     dword ptr [rax+rax+00h]
0x1400290dc  mov     edi, 103h
0x1400290e1  jmp     loc_140029045
0x1400290e6  cmp     cl, 3
0x1400290e9  jnz     short loc_140029110
0x1400290eb  lea     rax, ReadCompletionRoutine
0x1400290f2  cmp     [r9+38h], rax
0x1400290f6  jnz     loc_140029024
0x1400290fc  mov     rax, [r9+40h]
0x140029100  mov     rcx, [rax+10h]
0x140029104  mov     rdi, [rcx+0C0h]
0x14002910b  jmp     loc_14002901F
0x140029110  cmp     cl, 4
0x140029113  jnz     loc_140029024
0x140029119  lea     rax, WriteCompletionRoutine
0x140029120  cmp     [r9+38h], rax
0x140029124  jz      short loc_1400290FC
0x140029126  cmp     cl, cl
0x140029128  jnz     loc_140029024
0x14002912e  mov     rax, [r9+38h]
0x140029132  lea     rcx, FveInlineWriteCompletionRoutineRdpLevel1
0x140029139  cmp     rax, rcx
0x14002913c  jz      short loc_14002914E
0x14002913e  lea     rcx, FveInlineWriteCompletionRoutineRdpLevel2
0x140029145  cmp     rax, rcx
0x140029148  jnz     loc_140029024
0x14002914e  mov     r8, [rsi+10h]
0x140029152  lea     r10, [rsi+10h]
0x140029156  xor     edi, edi
0x140029158  cmp     r8, r10
0x14002915b  jz      loc_140029024
0x140029161  test    rdi, rdi
0x140029164  jnz     loc_140029060
0x14002916a  mov     r11d, [rsi+128h]
0x140029171  test    r11d, r11d
0x140029174  jz      short loc_140029194
0x140029176  xor     ebp, ebp
0x140029178  test    rdi, rdi
0x14002917b  jnz     short loc_140029194
0x14002917d  mov     rax, [r8+20h]
0x140029181  mov     rdx, [rax+rbp*8]
0x140029185  cmp     [rdx+18h], rbx
0x140029189  cmovz   rdi, rdx
0x14002918d  inc     ebp
0x14002918f  cmp     ebp, r11d
0x140029192  jb      short loc_140029178
0x140029194  mov     r8, [r8]
0x140029197  cmp     r8, r10
0x14002919a  jnz     short loc_140029161
0x14002919c  jmp     loc_14002901F
0x1400291a1  mov     ecx, 3
0x1400291a6  int     29h; Win8: RtlFailFast(ecx)
0x1400291a8  mov     qword ptr [rdx+38h], 0
0x1400291b0  mov     rcx, rbx; Irp
0x1400291b3  mov     dword ptr [rdx+30h], 0C0000010h
0x1400291ba  xor     edx, edx; PriorityBoost
0x1400291bc  call    cs:__imp_IofCompleteRequest
0x1400291c3  nop     dword ptr [rax+rax+00h]
0x1400291c8  mov     eax, 0C0000010h
0x1400291cd  jmp     loc_140028FD9
```
