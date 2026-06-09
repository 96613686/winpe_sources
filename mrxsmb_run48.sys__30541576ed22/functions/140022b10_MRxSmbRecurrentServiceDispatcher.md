# MRxSmbRecurrentServiceDispatcher

- ea: `0x140022b10`
- end: `0x140022bb1`
- name: `MRxSmbRecurrentServiceDispatcher`
- size: `161`
- prototype: `__int64 __fastcall(PVOID pContext)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, installer_update`

## callees

- `0x140022b10`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140022b19`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140022b19`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140022b3a`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140022b3a`
- `rdbss!RxPostToWorkerThread` at `0x140022b7b`
- `rdbss!RxPostToWorkerThread` at `0x140022b7b`

## pseudocode

```c
void __fastcall MRxSmbRecurrentServiceDispatcher(char *pContext)
{
  int v2; // eax
  int v3; // eax
  int v4; // eax

  KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)pContext);
  if ( *((_DWORD *)pContext + 2) == 12 )
  {
    v2 = *((_DWORD *)pContext + 66);
    if ( v2 )
    {
      v3 = v2 - 1;
      if ( !v3 )
        goto LABEL_6;
      v4 = v3 - 1;
      if ( v4 )
      {
        if ( v4 != 1 )
          goto LABEL_2;
        goto LABEL_6;
      }
    }
    if ( RxPostToWorkerThread(
           *((PRDBSS_DEVICE_OBJECT *)pContext + 34),
           NormalWorkQueue,
           (PRX_WORK_QUEUE_ITEM)(pContext + 168),
           MRxSmbRecurrentServiceWorkItem,
           pContext) >= 0 )
    {
      *((_DWORD *)pContext + 2) = 14;
      goto LABEL_2;
    }
LABEL_6:
    *((_DWORD *)pContext + 2) = 11;
  }
LABEL_2:
  *((_DWORD *)pContext + 66) = 0;
  KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)pContext);
}

```

## disassembly

```asm
0x140022b10  push    rbx
0x140022b12  sub     rsp, 30h
0x140022b16  mov     rbx, rcx
0x140022b19  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140022b20  nop     dword ptr [rax+rax+00h]
0x140022b25  mov     eax, [rbx+8]
0x140022b28  cmp     eax, 0Ch
0x140022b2b  jz      short loc_140022B4D
0x140022b2d  mov     rcx, rbx; SpinLock
0x140022b30  mov     dword ptr [rbx+108h], 0
0x140022b3a  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140022b41  nop     dword ptr [rax+rax+00h]
0x140022b46  add     rsp, 30h
0x140022b4a  pop     rbx
0x140022b4b  retn
0x140022b4d  cmp     eax, 0Ah
0x140022b50  jz      short loc_140022B2D
0x140022b52  mov     eax, [rbx+108h]
0x140022b58  test    eax, eax
0x140022b5a  jnz     short loc_140022B9D
0x140022b5c  mov     rcx, [rbx+110h]; pMRxDeviceObject
0x140022b63  lea     r8, [rbx+0A8h]; pWorkQueueItem
0x140022b6a  lea     r9, MRxSmbRecurrentServiceWorkItem; Routine
0x140022b71  mov     [rsp+38h+pContext], rbx; pContext
0x140022b76  mov     edx, 3; WorkQueueType
0x140022b7b  call    cs:__imp_RxPostToWorkerThread
0x140022b82  nop     dword ptr [rax+rax+00h]
0x140022b87  test    eax, eax
0x140022b89  js      short loc_140022B94
0x140022b8b  mov     dword ptr [rbx+8], 0Eh
0x140022b92  jmp     short loc_140022B2D
0x140022b94  mov     dword ptr [rbx+8], 0Bh
0x140022b9b  jmp     short loc_140022B2D
0x140022b9d  sub     eax, 1
0x140022ba0  jz      short loc_140022B94
0x140022ba2  sub     eax, 1
0x140022ba5  jz      short loc_140022B5C
0x140022ba7  cmp     eax, 1
0x140022baa  jz      short loc_140022B94
0x140022bac  jmp     loc_140022B2D
```
