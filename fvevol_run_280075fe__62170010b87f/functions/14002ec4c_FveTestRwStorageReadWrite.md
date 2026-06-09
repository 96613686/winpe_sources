# FveTestRwStorageReadWrite

- ea: `0x14002ec4c`
- end: `0x14002eddd`
- name: `FveTestRwStorageReadWrite`
- size: `401`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400304c0`

## callees

- `0x14002ec4c`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14002ecb0`
- `ntoskrnl!IofCompleteRequest` at `0x14002ecb0`
- `ntoskrnl!IoQueueWorkItem` at `0x14002edb4`
- `ntoskrnl!IoQueueWorkItem` at `0x14002edb4`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002edc7`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002edc7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002ed5f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002ed5f`

## pseudocode

```c
__int64 __fastcall FveTestRwStorageReadWrite(__int64 a1, IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r8
  __int64 v4; // r14
  UCHAR MajorFunction; // al
  char *Context; // rbx
  __int64 (__fastcall *CompletionRoutine)(); // rax
  _QWORD *v9; // r9
  unsigned int v10; // r11d
  __int64 v11; // rsi
  __int64 v12; // rax
  KIRQL v13; // al
  struct _LIST_ENTRY *v14; // r8
  KIRQL v15; // bp
  struct _LIST_ENTRY *v16; // r9
  struct _LIST_ENTRY *Flink; // rdx

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v4 = *(_QWORD *)(*(_QWORD *)(a1 + 64) + 24LL);
  MajorFunction = CurrentStackLocation->MajorFunction;
  if ( CurrentStackLocation->MajorFunction != 3 && MajorFunction != 4 )
    goto LABEL_7;
  if ( (__int64 (__fastcall *)())CurrentStackLocation->CompletionRoutine == FveTestRwCompletion )
  {
    Context = (char *)CurrentStackLocation->Context;
    goto LABEL_22;
  }
  if ( MajorFunction == 3 )
  {
    if ( (_UNKNOWN *)CurrentStackLocation->CompletionRoutine != &ReadCompletionRoutine )
      goto LABEL_7;
  }
  else
  {
    if ( MajorFunction != 4 )
      goto LABEL_7;
    if ( (_UNKNOWN *)CurrentStackLocation->CompletionRoutine != &WriteCompletionRoutine )
    {
      CompletionRoutine = (__int64 (__fastcall *)())CurrentStackLocation->CompletionRoutine;
      if ( CompletionRoutine == FveInlineWriteCompletionRoutineRdpLevel1
        || (char *)CompletionRoutine == (char *)FveInlineWriteCompletionRoutineRdpLevel2 )
      {
        Context = 0;
        v9 = *(_QWORD **)(v4 + 16);
        if ( v9 != (_QWORD *)(v4 + 16) )
        {
          while ( !Context )
          {
            v10 = *(_DWORD *)(v4 + 296);
            if ( v10 )
            {
              v11 = 0;
              do
              {
                if ( Context )
                  break;
                v12 = v9[4];
                if ( *(IRP **)(*(_QWORD *)(v12 + 8 * v11) + 24LL) == a2 )
                  Context = *(char **)(v12 + 8 * v11);
                v11 = (unsigned int)(v11 + 1);
              }
              while ( (unsigned int)v11 < v10 );
            }
            v9 = (_QWORD *)*v9;
            if ( v9 == (_QWORD *)(v4 + 16) )
              goto LABEL_22;
          }
          goto LABEL_23;
        }
      }
LABEL_7:
      a2->IoStatus.Information = 0;
      a2->IoStatus.Status = -1073741823;
      IofCompleteRequest(a2, 0);
      return 3221225473LL;
    }
  }
  Context = *(char **)(*((_QWORD *)CurrentStackLocation->Context + 2) + 192LL);
LABEL_22:
  if ( !Context )
    goto LABEL_7;
LABEL_23:
  CurrentStackLocation->Control |= 1u;
  v13 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)Context + 14);
  v14 = (struct _LIST_ENTRY *)(Context + 96);
  v15 = v13;
  v16 = (struct _LIST_ENTRY *)*((_QWORD *)Context + 13);
  if ( (char *)v16->Flink != Context + 96 )
    __fastfail(3u);
  Flink = v14->Flink;
  a2->Tail.Overlay.ListEntry.Flink = v14;
  a2->Tail.Overlay.ListEntry.Blink = v16;
  v16->Flink = &a2->Tail.Overlay.ListEntry;
  *((_QWORD *)Context + 13) = &a2->Tail.Overlay.ListEntry;
  if ( Flink == v14 )
    IoQueueWorkItem(
      *((PIO_WORKITEM *)Context + 9),
      (PIO_WORKITEM_ROUTINE)FveTestRwStorageWorker,
      *(WORK_QUEUE_TYPE *)(v4 + 344),
      Context);
  KeReleaseSpinLock((PKSPIN_LOCK)Context + 14, v15);
  return 259;
}

```

## disassembly

```asm
0x14002ec4c  push    rbx
0x14002ec4e  push    rbp
0x14002ec4f  push    rsi
0x14002ec50  push    rdi
0x14002ec51  push    r14
0x14002ec53  sub     rsp, 20h
0x14002ec57  mov     rax, [rcx+40h]
0x14002ec5b  mov     rdi, rdx
0x14002ec5e  mov     r8, [rdx+0B8h]
0x14002ec65  mov     r14, [rax+18h]
0x14002ec69  mov     al, [r8]
0x14002ec6c  cmp     al, 3
0x14002ec6e  jz      short loc_14002EC74
0x14002ec70  cmp     al, 4
0x14002ec72  jnz     short loc_14002EC9B
0x14002ec74  lea     rcx, FveTestRwCompletion
0x14002ec7b  cmp     [r8+38h], rcx
0x14002ec7f  jnz     short loc_14002EC8A
0x14002ec81  mov     rbx, [r8+40h]
0x14002ec85  jmp     loc_14002ED4D
0x14002ec8a  cmp     al, 3
0x14002ec8c  jnz     short loc_14002ECCA
0x14002ec8e  lea     rax, ReadCompletionRoutine
0x14002ec95  cmp     [r8+38h], rax
0x14002ec99  jz      short loc_14002ECDB
0x14002ec9b  mov     ebx, 0C0000001h
0x14002eca0  mov     qword ptr [rdi+38h], 0
0x14002eca8  xor     edx, edx; PriorityBoost
0x14002ecaa  mov     [rdi+30h], ebx
0x14002ecad  mov     rcx, rdi; Irp
0x14002ecb0  call    cs:__imp_IofCompleteRequest
0x14002ecb7  nop     dword ptr [rax+rax+00h]
0x14002ecbc  mov     eax, ebx
0x14002ecbe  add     rsp, 20h
0x14002ecc2  pop     r14
0x14002ecc4  pop     rdi
0x14002ecc5  pop     rsi
0x14002ecc6  pop     rbp
0x14002ecc7  pop     rbx
0x14002ecc8  retn
0x14002ecca  cmp     al, 4
0x14002eccc  jnz     short loc_14002EC9B
0x14002ecce  lea     rax, WriteCompletionRoutine
0x14002ecd5  cmp     [r8+38h], rax
0x14002ecd9  jnz     short loc_14002ECEC
0x14002ecdb  mov     rax, [r8+40h]
0x14002ecdf  mov     rcx, [rax+10h]
0x14002ece3  mov     rbx, [rcx+0C0h]
0x14002ecea  jmp     short loc_14002ED4D
0x14002ecec  mov     rax, [r8+38h]
0x14002ecf0  lea     rcx, FveInlineWriteCompletionRoutineRdpLevel1
0x14002ecf7  cmp     rax, rcx
0x14002ecfa  jz      short loc_14002ED08
0x14002ecfc  lea     rcx, FveInlineWriteCompletionRoutineRdpLevel2
0x14002ed03  cmp     rax, rcx
0x14002ed06  jnz     short loc_14002EC9B
0x14002ed08  lea     r10, [r14+10h]
0x14002ed0c  xor     ebx, ebx
0x14002ed0e  mov     r9, [r10]
0x14002ed11  cmp     r9, r10
0x14002ed14  jz      short loc_14002EC9B
0x14002ed16  test    rbx, rbx
0x14002ed19  jnz     short loc_14002ED56
0x14002ed1b  mov     r11d, [r14+128h]
0x14002ed22  test    r11d, r11d
0x14002ed25  jz      short loc_14002ED45
0x14002ed27  xor     esi, esi
0x14002ed29  test    rbx, rbx
0x14002ed2c  jnz     short loc_14002ED45
0x14002ed2e  mov     rax, [r9+20h]
0x14002ed32  mov     rdx, [rax+rsi*8]
0x14002ed36  cmp     [rdx+18h], rdi
0x14002ed3a  cmovz   rbx, rdx
0x14002ed3e  inc     esi
0x14002ed40  cmp     esi, r11d
0x14002ed43  jb      short loc_14002ED29
0x14002ed45  mov     r9, [r9]
0x14002ed48  cmp     r9, r10
0x14002ed4b  jnz     short loc_14002ED16
0x14002ed4d  test    rbx, rbx
0x14002ed50  jz      loc_14002EC9B
0x14002ed56  or      byte ptr [r8+3], 1
0x14002ed5b  lea     rcx, [rbx+70h]; SpinLock
0x14002ed5f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002ed66  nop     dword ptr [rax+rax+00h]
0x14002ed6b  lea     r8, [rbx+60h]
0x14002ed6f  mov     bpl, al
0x14002ed72  mov     r9, [r8+8]
0x14002ed76  cmp     [r9], r8
0x14002ed79  jz      short loc_14002ED82
0x14002ed7b  mov     ecx, 3
0x14002ed80  int     29h; Win8: RtlFailFast(ecx)
0x14002ed82  mov     rdx, [r8]
0x14002ed85  lea     rax, [rdi+0A8h]
0x14002ed8c  mov     [rax], r8
0x14002ed8f  mov     [rax+8], r9
0x14002ed93  mov     [r9], rax
0x14002ed96  mov     [r8+8], rax
0x14002ed9a  cmp     rdx, r8
0x14002ed9d  jnz     short loc_14002EDC0
0x14002ed9f  mov     r8d, [r14+158h]; QueueType
0x14002eda6  lea     rdx, FveTestRwStorageWorker; WorkerRoutine
0x14002edad  mov     rcx, [rbx+48h]; IoWorkItem
0x14002edb1  mov     r9, rbx; Context
0x14002edb4  call    cs:__imp_IoQueueWorkItem
0x14002edbb  nop     dword ptr [rax+rax+00h]
0x14002edc0  mov     dl, bpl; NewIrql
0x14002edc3  lea     rcx, [rbx+70h]; SpinLock
0x14002edc7  call    cs:__imp_KeReleaseSpinLock
0x14002edce  nop     dword ptr [rax+rax+00h]
0x14002edd3  mov     eax, 103h
0x14002edd8  jmp     loc_14002ECBE
```
