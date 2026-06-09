# NTQueueToWorkerThread

- ea: `0x14000da94`
- end: `0x14000dc32`
- name: `NTQueueToWorkerThread`
- size: `414`
- prototype: ``
- caller_count: `24`
- callee_count: `3`
- tags: ``

## callers

- `0x1400031bc`
- `0x140004038`
- `0x140006900`
- `0x140007354`
- `0x14000b540`
- `0x14000d9a0`
- `0x14000e408`
- `0x14000efd4`
- `0x140011640`
- `0x140011998`
- `0x140014220`
- `0x140014a40`
- `0x14001e8f4`
- `0x14001f600`
- `0x140020810`
- `0x140020900`
- `0x140021280`
- `0x1400232bc`
- `0x140023e40`
- `0x140024504`
- `0x140024c40`
- `0x140027200`
- `0x1400281b0`
- `0x140029d28`

## callees

- `0x140006900`
- `0x14000da94`
- `0x14000dc40`

## import_xrefs

- `ntoskrnl!ExQueueWorkItem` at `0x14000db8e`
- `ntoskrnl!ExQueueWorkItem` at `0x14000db8e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000db14`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000db14`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000dba4`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000dba4`
- `ntoskrnl!ExAllocatePool2` at `0x14000dbce`
- `ntoskrnl!ExAllocatePool2` at `0x14000dbce`

## pseudocode

```c
__int64 __fastcall NTQueueToWorkerThread(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        char a7,
        char a8)
{
  __int64 v9; // r14
  KIRQL v12; // al
  __int64 *v13; // rcx
  KIRQL v14; // si
  __int64 Pool2; // rax

  v9 = a3;
  if ( a6 )
  {
    LOBYTE(a3) = a7;
    if ( !(unsigned __int8)NBT_REFERENCE_DEVICE(a6, 1, a3) )
      return 3221225488LL;
  }
  if ( a1 && !*(_DWORD *)(a1 + 64) )
  {
    *(_DWORD *)(a1 + 60) = 0;
LABEL_5:
    *(_QWORD *)(a1 + 32) = a5;
    *(_BYTE *)(a1 + 68) = a8;
    *(_DWORD *)(a1 + 64) = 1;
    *(_QWORD *)(a1 + 16) = v9;
    *(_QWORD *)(a1 + 24) = a4;
    *(_QWORD *)(a1 + 40) = a6;
    *(_QWORD *)(a1 + 48) = a2;
    *(_QWORD *)(a1 + 8) = a1;
    *(_QWORD *)a1 = a1;
    v12 = KeAcquireSpinLockRaiseToDpc(&qword_1400396D8);
    v13 = (__int64 *)qword_1400396E8;
    v14 = v12;
    if ( *(PVOID **)qword_1400396E8 != &P )
      __fastfail(3u);
    *(_QWORD *)a1 = &P;
    *(_QWORD *)(a1 + 8) = v13;
    *v13 = a1;
    qword_1400396E8 = a1;
    _InterlockedAdd(&dword_1400396F0, 1u);
    if ( !byte_140039752 && !_InterlockedExchange(&dword_1400396F4, 1) )
    {
      WorkItem.List.Flink = 0;
      WorkItem.WorkerRoutine = (PWORKER_THREAD_ROUTINE)NTExecuteWorker;
      WorkItem.Parameter = &WorkItem;
      ExQueueWorkItem(&WorkItem, CriticalWorkQueue);
    }
    KeReleaseSpinLock(&qword_1400396D8, v14);
    return 0;
  }
  Pool2 = ExAllocatePool2(64, 72, 842162766);
  a1 = Pool2;
  if ( Pool2 )
  {
    *(_DWORD *)(Pool2 + 60) = 1;
    goto LABEL_5;
  }
  if ( a6 )
    NBT_DEREFERENCE_DEVICE(a6, 1);
  return 3221225626LL;
}

```

## disassembly

```asm
0x14000da94  push    rbx
0x14000da96  push    rbp
0x14000da97  push    rsi
0x14000da98  push    rdi
0x14000da99  push    r14
0x14000da9b  push    r15
0x14000da9d  sub     rsp, 28h
0x14000daa1  mov     rsi, [rsp+58h+arg_28]
0x14000daa9  mov     rbp, r9
0x14000daac  mov     r14, r8
0x14000daaf  mov     r15, rdx
0x14000dab2  mov     rbx, rcx
0x14000dab5  mov     edi, 1
0x14000daba  test    rsi, rsi
0x14000dabd  jnz     loc_14000DBF6
0x14000dac3  test    rbx, rbx
0x14000dac6  jz      loc_14000DBC0
0x14000dacc  cmp     dword ptr [rbx+40h], 0
0x14000dad0  jnz     loc_14000DBC0
0x14000dad6  mov     dword ptr [rbx+3Ch], 0
0x14000dadd  mov     rax, [rsp+58h+arg_20]
0x14000dae5  lea     rcx, qword_1400396D8; SpinLock
0x14000daec  mov     [rbx+20h], rax
0x14000daf0  mov     al, [rsp+58h+arg_38]
0x14000daf7  mov     [rbx+44h], al
0x14000dafa  mov     [rbx+40h], edi
0x14000dafd  mov     [rbx+10h], r14
0x14000db01  mov     [rbx+18h], rbp
0x14000db05  mov     [rbx+28h], rsi
0x14000db09  mov     [rbx+30h], r15
0x14000db0d  mov     [rbx+8], rbx
0x14000db11  mov     [rbx], rbx
0x14000db14  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000db1b  nop     dword ptr [rax+rax+00h]
0x14000db20  mov     rcx, cs:qword_1400396E8
0x14000db27  mov     sil, al
0x14000db2a  lea     rax, P
0x14000db31  cmp     [rcx], rax
0x14000db34  jnz     loc_14000DC17
0x14000db3a  mov     [rbx], rax
0x14000db3d  mov     [rbx+8], rcx
0x14000db41  mov     [rcx], rbx
0x14000db44  mov     cs:qword_1400396E8, rbx
0x14000db4b  lock add cs:dword_1400396F0, edi
0x14000db52  cmp     cs:byte_140039752, 0
0x14000db59  jnz     short loc_14000DB9A
0x14000db5b  xchg    edi, cs:dword_1400396F4
0x14000db61  test    edi, edi
0x14000db63  jnz     short loc_14000DB9A
0x14000db65  lea     rax, NTExecuteWorker
0x14000db6c  mov     cs:WorkItem.List.Flink, 0
0x14000db77  lea     rcx, WorkItem; WorkItem
0x14000db7e  mov     cs:WorkItem.WorkerRoutine, rax
0x14000db85  xor     edx, edx; QueueType
0x14000db87  mov     cs:WorkItem.Parameter, rcx
0x14000db8e  call    cs:__imp_ExQueueWorkItem
0x14000db95  nop     dword ptr [rax+rax+00h]
0x14000db9a  mov     dl, sil; NewIrql
0x14000db9d  lea     rcx, qword_1400396D8; SpinLock
0x14000dba4  call    cs:__imp_KeReleaseSpinLock
0x14000dbab  nop     dword ptr [rax+rax+00h]
0x14000dbb0  xor     eax, eax
0x14000dbb2  add     rsp, 28h
0x14000dbb6  pop     r15
0x14000dbb8  pop     r14
0x14000dbba  pop     rdi
0x14000dbbb  pop     rsi
0x14000dbbc  pop     rbp
0x14000dbbd  pop     rbx
0x14000dbbe  retn
0x14000dbc0  mov     edx, 48h ; 'H'
0x14000dbc5  mov     r8d, 3232624Eh
0x14000dbcb  lea     ecx, [rdx-8]
0x14000dbce  call    cs:__imp_ExAllocatePool2
0x14000dbd5  nop     dword ptr [rax+rax+00h]
0x14000dbda  mov     rbx, rax
0x14000dbdd  test    rax, rax
0x14000dbe0  jnz     short loc_14000DBEE
0x14000dbe2  test    rsi, rsi
0x14000dbe5  jnz     short loc_14000DC1E
0x14000dbe7  mov     eax, 0C000009Ah
0x14000dbec  jmp     short loc_14000DBB2
0x14000dbee  mov     [rax+3Ch], edi
0x14000dbf1  jmp     loc_14000DADD
0x14000dbf6  mov     r8b, [rsp+58h+arg_30]
0x14000dbfe  mov     edx, edi
0x14000dc00  mov     rcx, rsi
0x14000dc03  call    NBT_REFERENCE_DEVICE
0x14000dc08  test    al, al
0x14000dc0a  jnz     loc_14000DAC3
0x14000dc10  mov     eax, 0C0000010h
0x14000dc15  jmp     short loc_14000DBB2
0x14000dc17  mov     ecx, 3
0x14000dc1c  int     29h; Win8: RtlFailFast(ecx)
0x14000dc1e  mov     r8b, [rsp+58h+arg_30]
0x14000dc26  mov     edx, edi
0x14000dc28  mov     rcx, rsi
0x14000dc2b  call    NBT_DEREFERENCE_DEVICE
0x14000dc30  jmp     short loc_14000DBE7
```
