# RxDispatchToWorkerThread

- ea: `0x140001fe0`
- end: `0x14000203f`
- name: `RxDispatchToWorkerThread`
- size: `95`
- prototype: `NTSTATUS __stdcall(PRDBSS_DEVICE_OBJECT pMRxDeviceObject, WORK_QUEUE_TYPE WorkQueueType, PRX_WORKERTHREAD_ROUTINE Routine, PVOID pContext)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1400013b0`

## callees

- `0x140001fe0`
- `0x140002580`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140001ffb`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140001ffb`

## pseudocode

```c
NTSTATUS __stdcall RxDispatchToWorkerThread(
        PRDBSS_DEVICE_OBJECT pMRxDeviceObject,
        WORK_QUEUE_TYPE WorkQueueType,
        PRX_WORKERTHREAD_ROUTINE Routine,
        PVOID pContext)
{
  if ( ExAllocateFromNPagedLookasideList(&RxWorkItemLookasideList) )
    return RxpPostToWorkerThread(pMRxDeviceObject, (__int64)pContext, 1);
  else
    return -1073741670;
}

```

## disassembly

```asm
0x140001fe0  push    rbx
0x140001fe2  push    rbp
0x140001fe3  push    rsi
0x140001fe4  push    rdi
0x140001fe5  sub     rsp, 38h
0x140001fe9  mov     rbp, rcx
0x140001fec  mov     rbx, r9
0x140001fef  lea     rcx, RxWorkItemLookasideList; Lookaside
0x140001ff6  mov     rdi, r8
0x140001ff9  mov     esi, edx
0x140001ffb  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140002002  nop     dword ptr [rax+rax+00h]
0x140002007  test    rax, rax
0x14000200a  jz      short loc_140002030
0x14000200c  mov     [rsp+58h+var_30], 1; char
0x140002011  mov     r9, rdi
0x140002014  mov     r8, rax
0x140002017  mov     [rsp+58h+var_38], rbx; __int64
0x14000201c  mov     edx, esi
0x14000201e  mov     rcx, rbp; Object
0x140002021  call    RxpPostToWorkerThread
0x140002026  add     rsp, 38h
0x14000202a  pop     rdi
0x14000202b  pop     rsi
0x14000202c  pop     rbp
0x14000202d  pop     rbx
0x14000202e  retn
0x140002030  mov     eax, 0C000009Ah
0x140002035  add     rsp, 38h
0x140002039  pop     rdi
0x14000203a  pop     rsi
0x14000203b  pop     rbp
0x14000203c  pop     rbx
0x14000203d  retn
```
