# RxPostToWorkerThread

- ea: `0x140002120`
- end: `0x14000215c`
- name: `RxPostToWorkerThread`
- size: `60`
- prototype: `NTSTATUS __stdcall(PRDBSS_DEVICE_OBJECT pMRxDeviceObject, WORK_QUEUE_TYPE WorkQueueType, PRX_WORK_QUEUE_ITEM pWorkQueueItem, PRX_WORKERTHREAD_ROUTINE Routine, PVOID pContext)`
- caller_count: `9`
- callee_count: `3`
- tags: ``

## callers

- `0x140001b70`
- `0x140002050`
- `0x14000c000`
- `0x14000c2f0`
- `0x14000c660`
- `0x1400119a0`
- `0x140013260`
- `0x140020910`
- `0x140076f60`

## callees

- `0x140002120`
- `0x140002580`
- `0x14001810c`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x140026cec`
- `ntoskrnl!KeBugCheckEx` at `0x140026cec`

## pseudocode

```c
NTSTATUS __stdcall RxPostToWorkerThread(
        PRDBSS_DEVICE_OBJECT pMRxDeviceObject,
        WORK_QUEUE_TYPE WorkQueueType,
        PRX_WORK_QUEUE_ITEM pWorkQueueItem,
        PRX_WORKERTHREAD_ROUTINE Routine,
        PVOID pContext)
{
  if ( pWorkQueueItem->pDeviceObject == pMRxDeviceObject
    && (void (__fastcall *)(_BYTE *))pWorkQueueItem->WorkerRoutine == RxpProcessWorkItem
    && pWorkQueueItem->Parameter == pWorkQueueItem )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_qqq(
        WPP_GLOBAL_Control->AttachedDevice,
        16,
        &WPP_91b9b20a3d1f3beba865abbaf8105594_Traceguids,
        pWorkQueueItem,
        pWorkQueueItem[1].List.Flink,
        pWorkQueueItem[1].List.Blink);
    }
    KeBugCheckEx(
      0x27u,
      0x80233u,
      (ULONG_PTR)pWorkQueueItem,
      (ULONG_PTR)pWorkQueueItem[1].List.Flink,
      (ULONG_PTR)pWorkQueueItem[1].List.Blink);
  }
  return RxpPostToWorkerThread(pMRxDeviceObject, (__int64)pContext, 0);
}

```

## disassembly

```asm
0x140002120  push    rbx
0x140002122  sub     rsp, 30h
0x140002126  mov     rbx, r8
0x140002129  cmp     [r8+20h], rcx
0x14000212d  jz      short loc_14000214A
0x14000212f  mov     rax, [rsp+38h+pContext]
0x140002134  mov     [rsp+38h+var_10], 0; char
0x140002139  mov     [rsp+38h+BugCheckParameter4], rax; __int64
0x14000213e  call    RxpPostToWorkerThread
0x140002143  add     rsp, 30h
0x140002147  pop     rbx
0x140002148  retn
0x14000214a  lea     rax, RxpProcessWorkItem
0x140002151  cmp     [r8+10h], rax
0x140002155  jnz     short loc_14000212F
0x140002157  jmp     loc_140026C7E
0x140026c7e  cmp     [r8+18h], rbx
0x140026c82  jnz     loc_14000212F
0x140026c88  mov     rcx, cs:WPP_GLOBAL_Control
0x140026c8f  lea     rax, WPP_GLOBAL_Control
0x140026c96  cmp     rcx, rax
0x140026c99  jz      short loc_140026CD2
0x140026c9b  mov     eax, [rcx+2Ch]
0x140026c9e  test    al, 1
0x140026ca0  jz      short loc_140026CD2
0x140026ca2  cmp     byte ptr [rcx+29h], 1
0x140026ca6  jb      short loc_140026CD2
0x140026ca8  mov     rax, [r8+30h]
0x140026cac  mov     edx, 10h
0x140026cb1  mov     rcx, [rcx+18h]
0x140026cb5  mov     r9, rbx
0x140026cb8  mov     qword ptr [rsp+38h+var_10], rax
0x140026cbd  mov     rax, [r8+28h]
0x140026cc1  lea     r8, WPP_91b9b20a3d1f3beba865abbaf8105594_Traceguids
0x140026cc8  mov     [rsp+38h+BugCheckParameter4], rax
0x140026ccd  call    WPP_SF_qqq
0x140026cd2  mov     rax, [rbx+30h]
0x140026cd6  mov     r8, rbx; BugCheckParameter2
0x140026cd9  mov     r9, [rbx+28h]; BugCheckParameter3
0x140026cdd  mov     edx, 80233h; BugCheckParameter1
0x140026ce2  mov     ecx, 27h ; '''; BugCheckCode
0x140026ce7  mov     [rsp+38h+BugCheckParameter4], rax; BugCheckParameter4
0x140026cec  call    cs:__imp_KeBugCheckEx
```
