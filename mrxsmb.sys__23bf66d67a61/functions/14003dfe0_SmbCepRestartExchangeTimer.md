# SmbCepRestartExchangeTimer

- ea: `0x14003dfe0`
- end: `0x14003e146`
- name: `SmbCepRestartExchangeTimer`
- size: `358`
- prototype: `__int64 __fastcall(PRDBSS_DEVICE_OBJECT pMRxDeviceObject)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x14003dfe0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14003e019`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14003e019`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14003e097`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14003e097`
- `rdbss!RxPostToWorkerThread` at `0x14003e0ea`
- `rdbss!RxPostToWorkerThread` at `0x14003e0ea`
- `rdbss!RxPostPreAllocatedOneShotTimerRequest` at `0x14003e12d`
- `rdbss!RxPostPreAllocatedOneShotTimerRequest` at `0x14003e12d`

## pseudocode

```c
PRX_WORK_QUEUE_ITEM *__fastcall SmbCepRestartExchangeTimer(PRDBSS_DEVICE_OBJECT pMRxDeviceObject)
{
  KSPIN_LOCK *p_Reserved; // r15
  __int64 v3; // r14
  PRX_WORK_QUEUE_ITEM **v4; // rsi
  PRX_WORK_QUEUE_ITEM **v5; // rdx
  PRX_WORK_QUEUE_ITEM **v6; // rcx
  PRX_WORK_QUEUE_ITEM ***v7; // rax
  PRX_WORK_QUEUE_ITEM *v8; // r8
  PRX_WORK_QUEUE_ITEM **v9; // rax
  PRX_WORK_QUEUE_ITEM **v10; // r14
  struct _RX_WORK_QUEUE_ITEM_ *v11; // r8
  PRX_WORK_QUEUE_ITEM *result; // rax
  struct _LIST_ENTRY *Flink; // rax
  char v14; // [rsp+30h] [rbp-20h]
  PRX_WORK_QUEUE_ITEM pWorkQueueItem; // [rsp+40h] [rbp-10h] BYREF
  PRX_WORK_QUEUE_ITEM *p_pWorkQueueItem; // [rsp+48h] [rbp-8h]

  p_Reserved = (KSPIN_LOCK *)&pMRxDeviceObject[1].DeviceObject.Reserved;
  v3 = MEMORY[0xFFFFF78000000008];
  p_pWorkQueueItem = &pWorkQueueItem;
  pWorkQueueItem = (PRX_WORK_QUEUE_ITEM)&pWorkQueueItem;
  KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)&pMRxDeviceObject[1].DeviceObject.Reserved);
  v4 = (PRX_WORK_QUEUE_ITEM **)(&pMRxDeviceObject[1].Reserved + 1);
  v5 = (PRX_WORK_QUEUE_ITEM **)*((_QWORD *)&pMRxDeviceObject[1].Reserved + 1);
  while ( v5 != v4 && (unsigned __int64)(v3 - (_QWORD)v5[8]) >= 0x2FAF080 )
  {
    v6 = (PRX_WORK_QUEUE_ITEM **)*v5;
    if ( (*v5)[1] != (PRX_WORK_QUEUE_ITEM)v5
      || (v7 = (PRX_WORK_QUEUE_ITEM ***)v5[1], *v7 != v5)
      || (*v7 = v6,
          v6[1] = (PRX_WORK_QUEUE_ITEM *)v7,
          v8 = p_pWorkQueueItem,
          *p_pWorkQueueItem != (PRX_WORK_QUEUE_ITEM)&pWorkQueueItem) )
    {
LABEL_13:
      __fastfail(3u);
    }
    v9 = v5;
    v5[1] = p_pWorkQueueItem;
    v5 = v6;
    *v9 = &pWorkQueueItem;
    *v8 = (PRX_WORK_QUEUE_ITEM)v9;
    p_pWorkQueueItem = (PRX_WORK_QUEUE_ITEM *)v9;
  }
  v10 = (PRX_WORK_QUEUE_ITEM **)*v4;
  KeReleaseSpinLockFromDpcLevel(p_Reserved);
  while ( 1 )
  {
    v11 = pWorkQueueItem;
    result = &pWorkQueueItem;
    if ( pWorkQueueItem == (PRX_WORK_QUEUE_ITEM)&pWorkQueueItem )
      break;
    if ( (PRX_WORK_QUEUE_ITEM *)pWorkQueueItem->List.Blink != &pWorkQueueItem )
      goto LABEL_13;
    Flink = pWorkQueueItem->List.Flink;
    if ( (PRX_WORK_QUEUE_ITEM)pWorkQueueItem->List.Flink->Blink != pWorkQueueItem )
      goto LABEL_13;
    pWorkQueueItem = (PRX_WORK_QUEUE_ITEM)pWorkQueueItem->List.Flink;
    Flink->Blink = (struct _LIST_ENTRY *)&pWorkQueueItem;
    RxPostToWorkerThread(pMRxDeviceObject, NormalWorkQueue, v11, SmbCepRestartExchangeWorker, &v11[-6]);
  }
  if ( v10 != v4 )
  {
    v14 = 1;
    return (PRX_WORK_QUEUE_ITEM *)RxPostPreAllocatedOneShotTimerRequest(
                                    pMRxDeviceObject,
                                    3,
                                    &pMRxDeviceObject[1].RdbssExports,
                                    SmbCepRestartExchangeTimer,
                                    pMRxDeviceObject,
                                    50000000,
                                    v14);
  }
  return result;
}

```

## disassembly

```asm
0x14003dfe0  push    rbp
0x14003dfe2  push    rsi
0x14003dfe3  push    rdi
0x14003dfe4  push    r14
0x14003dfe6  push    r15
0x14003dfe8  mov     rbp, rsp
0x14003dfeb  sub     rsp, 50h
0x14003dfef  lea     rax, [rbp+pWorkQueueItem]
0x14003dff3  mov     rdi, rcx
0x14003dff6  lea     r15, [rcx+7B0h]
0x14003dffd  mov     r14, 0FFFFF78000000008h
0x14003e007  mov     rcx, r15; SpinLock
0x14003e00a  mov     r14, [r14]
0x14003e00d  mov     [rbp+var_8], rax
0x14003e011  lea     rax, [rbp+pWorkQueueItem]
0x14003e015  mov     [rbp+pWorkQueueItem], rax
0x14003e019  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14003e020  nop     dword ptr [rax+rax+00h]
0x14003e025  lea     rsi, [rdi+7B8h]
0x14003e02c  mov     rdx, [rsi]
0x14003e02f  cmp     rdx, rsi
0x14003e032  jz      short loc_14003E091
0x14003e034  mov     rax, r14
0x14003e037  sub     rax, [rdx+40h]
0x14003e03b  cmp     rax, 2FAF080h
0x14003e041  jb      short loc_14003E091
0x14003e043  mov     rcx, [rdx]
0x14003e046  cmp     [rcx+8], rdx
0x14003e04a  jnz     loc_14003E0F8
0x14003e050  lea     r9, [rdx+8]
0x14003e054  mov     rax, [r9]
0x14003e057  cmp     [rax], rdx
0x14003e05a  jnz     loc_14003E0F8
0x14003e060  mov     [rax], rcx
0x14003e063  mov     [rcx+8], rax
0x14003e067  lea     rax, [rbp+pWorkQueueItem]
0x14003e06b  mov     r8, [rbp+var_8]
0x14003e06f  cmp     [r8], rax
0x14003e072  jnz     loc_14003E0F8
0x14003e078  mov     rax, rdx
0x14003e07b  mov     [r9], r8
0x14003e07e  mov     rdx, rcx
0x14003e081  lea     rcx, [rbp+pWorkQueueItem]
0x14003e085  mov     [rax], rcx
0x14003e088  mov     [r8], rax
0x14003e08b  mov     [rbp+var_8], rax
0x14003e08f  jmp     short loc_14003E02F
0x14003e091  mov     r14, [rsi]
0x14003e094  mov     rcx, r15; SpinLock
0x14003e097  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14003e09e  nop     dword ptr [rax+rax+00h]
0x14003e0a3  mov     r8, [rbp+pWorkQueueItem]; pWorkQueueItem
0x14003e0a7  lea     rax, [rbp+pWorkQueueItem]
0x14003e0ab  cmp     r8, rax
0x14003e0ae  jz      short loc_14003E0FF
0x14003e0b0  lea     rax, [rbp+pWorkQueueItem]
0x14003e0b4  cmp     [r8+8], rax
0x14003e0b8  jnz     short loc_14003E0F8
0x14003e0ba  mov     rax, [r8]
0x14003e0bd  cmp     [rax+8], r8
0x14003e0c1  jnz     short loc_14003E0F8
0x14003e0c3  mov     [rbp+pWorkQueueItem], rax
0x14003e0c7  lea     rcx, [rbp+pWorkQueueItem]
0x14003e0cb  mov     [rax+8], rcx
0x14003e0cf  lea     r9, SmbCepRestartExchangeWorker; Routine
0x14003e0d6  lea     rax, [r8-0F0h]
0x14003e0dd  mov     edx, 3; WorkQueueType
0x14003e0e2  mov     rcx, rdi; pMRxDeviceObject
0x14003e0e5  mov     [rsp+50h+pContext], rax; pContext
0x14003e0ea  call    cs:__imp_RxPostToWorkerThread
0x14003e0f1  nop     dword ptr [rax+rax+00h]
0x14003e0f6  jmp     short loc_14003E0A3
0x14003e0f8  mov     ecx, 3
0x14003e0fd  int     29h; Win8: RtlFailFast(ecx)
0x14003e0ff  cmp     r14, rsi
0x14003e102  jz      short loc_14003E139
0x14003e104  mov     [rsp+50h+var_20], 1
0x14003e109  lea     r8, [rdi+7C8h]
0x14003e110  mov     [rsp+50h+var_28], 2FAF080h
0x14003e119  lea     r9, SmbCepRestartExchangeTimer
0x14003e120  mov     edx, 3
0x14003e125  mov     [rsp+50h+pContext], rdi
0x14003e12a  mov     rcx, rdi
0x14003e12d  call    cs:__imp_RxPostPreAllocatedOneShotTimerRequest
0x14003e134  nop     dword ptr [rax+rax+00h]
0x14003e139  add     rsp, 50h
0x14003e13d  pop     r15
0x14003e13f  pop     r14
0x14003e141  pop     rdi
0x14003e142  pop     rsi
0x14003e143  pop     rbp
0x14003e144  retn
```
