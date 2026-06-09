# SmbCeDiscardExchange

- ea: `0x140052944`
- end: `0x140052995`
- name: `SmbCeDiscardExchange`
- size: `81`
- prototype: `__int64 __fastcall(PVOID pContext)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x14000f1d0`
- `0x14000f310`
- `0x14000f48c`
- `0x140029b20`
- `0x14004f060`

## callees

- `0x140009340`
- `0x140052944`

## import_xrefs

- `rdbss!RxPostToWorkerThread` at `0x140052982`
- `rdbss!RxPostToWorkerThread` at `0x140052982`
- `mrxsmb!MRxSmbDeviceObject` at `0x140052960`

## pseudocode

```c
NTSTATUS __fastcall SmbCeDiscardExchange(char *pContext)
{
  if ( (*((_DWORD *)pContext + 18) & 1) != 0 )
    SmbCeDissociateMidFromExchange(*((_QWORD *)pContext + 10), pContext);
  return RxPostToWorkerThread(
           MRxSmbDeviceObject,
           NormalWorkQueue,
           (PRX_WORK_QUEUE_ITEM)(pContext + 176),
           (PRX_WORKERTHREAD_ROUTINE)SmbCeDiscardExchangeWorkerThreadRoutine,
           pContext);
}

```

## disassembly

```asm
0x140052944  push    rbx
0x140052946  sub     rsp, 30h
0x14005294a  mov     eax, [rcx+48h]
0x14005294d  mov     rbx, rcx
0x140052950  test    al, 1
0x140052952  jz      short loc_140052960
0x140052954  mov     rdx, rcx
0x140052957  mov     rcx, [rcx+50h]
0x14005295b  call    SmbCeDissociateMidFromExchange
0x140052960  mov     rcx, cs:__imp_MRxSmbDeviceObject
0x140052967  lea     r8, [rbx+0B0h]; pWorkQueueItem
0x14005296e  lea     r9, SmbCeDiscardExchangeWorkerThreadRoutine; Routine
0x140052975  mov     [rsp+38h+pContext], rbx; pContext
0x14005297a  mov     edx, 3; WorkQueueType
0x14005297f  mov     rcx, [rcx]; pMRxDeviceObject
0x140052982  call    cs:__imp_RxPostToWorkerThread
0x140052989  nop     dword ptr [rax+rax+00h]
0x14005298e  add     rsp, 30h
0x140052992  pop     rbx
0x140052993  retn
```
