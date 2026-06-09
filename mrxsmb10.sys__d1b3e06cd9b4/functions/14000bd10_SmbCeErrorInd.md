# SmbCeErrorInd

- ea: `0x14000bd10`
- end: `0x14000be3e`
- name: `SmbCeErrorInd`
- size: `302`
- prototype: `__int64 __fastcall(PVOID pContext)`
- caller_count: `3`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x1400043a0`
- `0x140008840`
- `0x140014f70`

## callees

- `0x140001e40`
- `0x140002470`
- `0x14000bd10`
- `0x14000ebd8`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14000bd69`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000bdb9`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000bd69`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000bdb9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000bd48`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000bd48`
- `ntoskrnl!DbgPrint` at `0x14000bdf5`
- `ntoskrnl!DbgPrint` at `0x14000bdf5`
- `rdbss!RxDispatchToWorkerThread` at `0x14000bdde`
- `rdbss!RxDispatchToWorkerThread` at `0x14000bdde`
- `mrxsmb!MRxSmbLegacyPerfCtrs` at `0x14000bd24`
- `mrxsmb!MRxSmbDeviceObject` at `0x14000bdc5`

## pseudocode

```c
__int64 __fastcall SmbCeErrorInd(char *pContext, int a2)
{
  KIRQL v3; // al
  bool v4; // zf

  _InterlockedIncrement((volatile signed __int32 *)(((unsigned __int64)HIDWORD(KeGetPcr()[1].LockArray) << 8)
                                                  + MRxSmbLegacyPerfCtrs
                                                  + 144));
  *((_DWORD *)pContext + 82) = a2;
  v3 = KeAcquireSpinLockRaiseToDpc(&s_SmbCeDbSpinLock);
  v4 = *((_DWORD *)pContext + 3) == 9;
  s_SmbCeDbSpinLockSavedIrql = v3;
  if ( v4 )
  {
    KeReleaseSpinLock(&s_SmbCeDbSpinLock, v3);
  }
  else
  {
    MRxSmbTrackRefCount(pContext, "SmbCeErrorInd", 1280);
    SmbReferenceRecord(pContext + 792, "SmbCeErrorInd", 1280);
    _InterlockedIncrement((volatile signed __int32 *)pContext + 2);
    KeReleaseSpinLock(&s_SmbCeDbSpinLock, s_SmbCeDbSpinLockSavedIrql);
    if ( RxDispatchToWorkerThread(
           MRxSmbDeviceObject,
           NormalWorkQueue,
           SmbCeResumeAllOutstandingRequestsOnError,
           pContext) )
    {
      DbgPrint("Error Indication not dispatched\n");
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_96809d50ffaa30ffc961a4216fa88776_Traceguids, pContext);
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14000bd10  push    rbx
0x14000bd12  sub     rsp, 20h
0x14000bd16  mov     eax, gs:1A4h
0x14000bd1e  mov     rbx, rcx
0x14000bd21  mov     r9d, eax
0x14000bd24  mov     rax, cs:__imp_MRxSmbLegacyPerfCtrs
0x14000bd2b  shl     r9, 8
0x14000bd2f  mov     r8, [rax]
0x14000bd32  lock inc dword ptr [r9+r8+90h]
0x14000bd3b  mov     [rcx+148h], edx
0x14000bd41  lea     rcx, s_SmbCeDbSpinLock; SpinLock
0x14000bd48  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000bd4f  nop     dword ptr [rax+rax+00h]
0x14000bd54  cmp     dword ptr [rbx+0Ch], 9
0x14000bd58  mov     cs:s_SmbCeDbSpinLockSavedIrql, al
0x14000bd5e  jnz     short loc_14000BD7A
0x14000bd60  mov     dl, al; NewIrql
0x14000bd62  lea     rcx, s_SmbCeDbSpinLock; SpinLock
0x14000bd69  call    cs:__imp_KeReleaseSpinLock
0x14000bd70  nop     dword ptr [rax+rax+00h]
0x14000bd75  jmp     loc_14000BE35
0x14000bd7a  mov     r8d, 500h
0x14000bd80  lea     rdx, aSmbceerrorind; "SmbCeErrorInd"
0x14000bd87  mov     rcx, rbx
0x14000bd8a  call    MRxSmbTrackRefCount
0x14000bd8f  lea     rcx, [rbx+318h]
0x14000bd96  mov     r8d, 500h
0x14000bd9c  lea     rdx, aSmbceerrorind; "SmbCeErrorInd"
0x14000bda3  call    SmbReferenceRecord
0x14000bda8  lock inc dword ptr [rbx+8]
0x14000bdac  mov     dl, cs:s_SmbCeDbSpinLockSavedIrql; NewIrql
0x14000bdb2  lea     rcx, s_SmbCeDbSpinLock; SpinLock
0x14000bdb9  call    cs:__imp_KeReleaseSpinLock
0x14000bdc0  nop     dword ptr [rax+rax+00h]
0x14000bdc5  mov     rcx, cs:__imp_MRxSmbDeviceObject
0x14000bdcc  lea     r8, SmbCeResumeAllOutstandingRequestsOnError; Routine
0x14000bdd3  mov     r9, rbx; pContext
0x14000bdd6  mov     edx, 3; WorkQueueType
0x14000bddb  mov     rcx, [rcx]; pMRxDeviceObject
0x14000bdde  call    cs:__imp_RxDispatchToWorkerThread
0x14000bde5  nop     dword ptr [rax+rax+00h]
0x14000bdea  test    eax, eax
0x14000bdec  jz      short loc_14000BE35
0x14000bdee  lea     rcx, aErrorIndicatio; "Error Indication not dispatched\n"
0x14000bdf5  call    cs:__imp_DbgPrint
0x14000bdfc  nop     dword ptr [rax+rax+00h]
0x14000be01  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000be08  lea     rax, WPP_GLOBAL_Control
0x14000be0f  cmp     rcx, rax
0x14000be12  jz      short loc_14000BE35
0x14000be14  test    dword ptr [rcx+2Ch], 200h
0x14000be1b  jz      short loc_14000BE35
0x14000be1d  mov     rcx, [rcx+18h]
0x14000be21  lea     r8, WPP_96809d50ffaa30ffc961a4216fa88776_Traceguids
0x14000be28  mov     edx, 14h
0x14000be2d  mov     r9, rbx
0x14000be30  call    WPP_SF_q
0x14000be35  xor     eax, eax
0x14000be37  add     rsp, 20h
0x14000be3b  pop     rbx
0x14000be3c  retn
```
