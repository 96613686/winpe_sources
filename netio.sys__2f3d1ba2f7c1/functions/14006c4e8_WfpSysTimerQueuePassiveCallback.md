# WfpSysTimerQueuePassiveCallback

- ea: `0x14006c4e8`
- end: `0x14006c5e9`
- name: `WfpSysTimerQueuePassiveCallback`
- size: `257`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x14006c170`

## callees

- `0x140009520`
- `0x140009e00`
- `0x140039de0`
- `0x14006c4e8`

## import_xrefs

- `ntoskrnl!IoQueueWorkItem` at `0x14006c57b`
- `ntoskrnl!IoQueueWorkItem` at `0x14006c57b`
- `ntoskrnl!IoAllocateWorkItem` at `0x14006c535`
- `ntoskrnl!IoAllocateWorkItem` at `0x14006c535`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14006c5bc`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14006c5bc`

## pseudocode

```c
__int64 __fastcall WfpSysTimerQueuePassiveCallback(__int64 a1)
{
  __int64 v1; // rsi
  PIO_WORKITEM *v2; // rbx
  __int64 v4; // rdi
  PIO_WORKITEM WorkItem; // rax
  __int64 v6; // r8
  const char *v7; // rdx
  PVOID Context; // [rsp+50h] [rbp+8h] BYREF

  v1 = *(_QWORD *)(a1 + 160);
  v2 = 0;
  Context = 0;
  if ( *(_DWORD *)(v1 + 192) >= 0xAu || !*(_QWORD *)(v1 + 208) )
  {
    v6 = 3221225473LL;
    v7 = "WfpSysTimerQueuePassiveCallback";
LABEL_9:
    v4 = WfpReportSysErrorAsNtStatus(a1, v7, v6, 1);
    if ( !v4 )
      return v4;
    goto LABEL_10;
  }
  v4 = WfpAllocFromNPagedLookasideList((struct _NPAGED_LOOKASIDE_LIST *)(v1 + 64), &Context);
  if ( !v4 )
  {
    WorkItem = IoAllocateWorkItem(*(PDEVICE_OBJECT *)(v1 + 208));
    v2 = (PIO_WORKITEM *)Context;
    *(_QWORD *)Context = WorkItem;
    if ( WorkItem )
    {
      v2[1] = (PIO_WORKITEM)a1;
      _InterlockedIncrement((volatile signed __int32 *)(v1 + 192));
      IoQueueWorkItem(*v2, WfpSysTimerPassiveCallback, DelayedWorkQueue, v2);
      return v4;
    }
    v6 = 3221225495LL;
    v7 = "IoAllocateWorkItem";
    goto LABEL_9;
  }
  v2 = (PIO_WORKITEM *)Context;
LABEL_10:
  if ( !v2 || (ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v1 + 64), v2), v4) )
    WfpReportError(v4, "WfpSysTimerQueuePassiveCallback");
  return v4;
}

```

## disassembly

```asm
0x14006c4e8  push    rbx
0x14006c4ea  push    rbp
0x14006c4eb  push    rsi
0x14006c4ec  push    rdi
0x14006c4ed  sub     rsp, 28h
0x14006c4f1  mov     rsi, [rcx+0A0h]
0x14006c4f8  xor     ebx, ebx
0x14006c4fa  mov     rbp, rcx
0x14006c4fd  mov     [rsp+48h+Context], rbx
0x14006c502  cmp     dword ptr [rsi+0C0h], 0Ah
0x14006c509  jnb     loc_14006C590
0x14006c50f  cmp     [rsi+0D0h], rbx
0x14006c516  jz      short loc_14006C590
0x14006c518  lea     rdx, [rsp+48h+Context]
0x14006c51d  lea     rcx, [rsi+40h]
0x14006c521  call    WfpAllocFromNPagedLookasideList
0x14006c526  mov     rdi, rax
0x14006c529  test    rax, rax
0x14006c52c  jnz     short loc_14006C589
0x14006c52e  mov     rcx, [rsi+0D0h]; DeviceObject
0x14006c535  call    cs:__imp_IoAllocateWorkItem
0x14006c53c  nop     dword ptr [rax+rax+00h]
0x14006c541  mov     rbx, [rsp+48h+Context]
0x14006c546  mov     [rbx], rax
0x14006c549  test    rax, rax
0x14006c54c  jnz     short loc_14006C55D
0x14006c54e  mov     r8d, 0C0000017h
0x14006c554  lea     rdx, aIoallocatework; "IoAllocateWorkItem"
0x14006c55b  jmp     short loc_14006C59D
0x14006c55d  mov     [rbx+8], rbp
0x14006c561  lock inc dword ptr [rsi+0C0h]
0x14006c568  mov     rcx, [rbx]; IoWorkItem
0x14006c56b  lea     rdx, WfpSysTimerPassiveCallback; WorkerRoutine
0x14006c572  mov     r9, rbx; Context
0x14006c575  mov     r8d, 1; QueueType
0x14006c57b  call    cs:__imp_IoQueueWorkItem
0x14006c582  nop     dword ptr [rax+rax+00h]
0x14006c587  jmp     short loc_14006C5DC
0x14006c589  mov     rbx, [rsp+48h+Context]
0x14006c58e  jmp     short loc_14006C5B0
0x14006c590  mov     r8d, 0C0000001h
0x14006c596  lea     rdx, aWfpsystimerque; "WfpSysTimerQueuePassiveCallback"
0x14006c59d  mov     r9d, 1
0x14006c5a3  call    WfpReportSysErrorAsNtStatus
0x14006c5a8  mov     rdi, rax
0x14006c5ab  test    rax, rax
0x14006c5ae  jz      short loc_14006C5DC
0x14006c5b0  test    rbx, rbx
0x14006c5b3  jz      short loc_14006C5CD
0x14006c5b5  mov     rdx, rbx; Entry
0x14006c5b8  lea     rcx, [rsi+40h]; Lookaside
0x14006c5bc  call    cs:__imp_ExFreeToNPagedLookasideList
0x14006c5c3  nop     dword ptr [rax+rax+00h]
0x14006c5c8  test    rdi, rdi
0x14006c5cb  jz      short loc_14006C5DC
0x14006c5cd  lea     rdx, aWfpsystimerque; "WfpSysTimerQueuePassiveCallback"
0x14006c5d4  mov     rcx, rdi
0x14006c5d7  call    WfpReportError
0x14006c5dc  mov     rax, rdi
0x14006c5df  add     rsp, 28h
0x14006c5e3  pop     rdi
0x14006c5e4  pop     rsi
0x14006c5e5  pop     rbp
0x14006c5e6  pop     rbx
0x14006c5e7  retn
```
