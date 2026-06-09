# RxCreateRxContextEx

- ea: `0x140003ae0`
- end: `0x140003ea0`
- name: `RxCreateRxContextEx`
- size: `960`
- prototype: `__int64 __fastcall(PIRP Irp, PRDBSS_DEVICE_OBJECT RxDeviceObject, ULONG InitialContextFlags, PRX_CONTEXT RxContext)`
- caller_count: `4`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140001b70`
- `0x140008910`
- `0x14000d1e0`
- `0x140015290`

## callees

- `0x140003ae0`
- `0x140003eb0`
- `0x140025c20`
- `0x140025d00`
- `0x140026080`
- `0x1400623c0`

## import_xrefs

- `ntoskrnl!EtwActivityIdControl` at `0x140003c87`
- `ntoskrnl!EtwActivityIdControl` at `0x140003cb8`
- `ntoskrnl!EtwActivityIdControl` at `0x140003c87`
- `ntoskrnl!EtwActivityIdControl` at `0x140003cb8`
- `ntoskrnl!EtwWriteTransfer` at `0x140003d9a`
- `ntoskrnl!EtwWriteTransfer` at `0x140003d9a`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140003e4c`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140003e4c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003c66`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003c66`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140003b15`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140003b15`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140003b60`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140003b60`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140003ca0`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140003ca0`
- `ntoskrnl!EtwWrite` at `0x140003df8`
- `ntoskrnl!EtwWrite` at `0x140003df8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003c27`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003c27`
- `ntoskrnl!KeWaitForSingleObject` at `0x140003e7e`
- `ntoskrnl!KeWaitForSingleObject` at `0x140003e7e`

## pseudocode

```c
PRX_CONTEXT __fastcall RxCreateRxContextEx(
        PIRP Irp,
        PRDBSS_DEVICE_OBJECT RxDeviceObject,
        ULONG InitialContextFlags,
        PRX_CONTEXT RxContext)
{
  int v8; // edi
  USHORT CurrentNodeNumber; // ax
  int LockArray_high; // r14d
  USHORT v11; // r13
  ULONGLONG v12; // rbx
  LIST_ENTRY *v13; // r14
  KIRQL v14; // al
  struct _LIST_ENTRY *Blink; // rdx
  struct _LIST_ENTRY *v16; // rcx
  struct _LIST_ENTRY *v17; // rax
  const GUID *v19; // r8
  const GUID *v20; // r8
  UCHAR MajorFunction; // cl
  int v22; // [rsp+30h] [rbp-49h] BYREF
  GUID ActivityId; // [rsp+38h] [rbp-41h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+48h] [rbp-31h] BYREF
  int *v25; // [rsp+58h] [rbp-21h]
  __int64 v26; // [rsp+60h] [rbp-19h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+68h] [rbp-11h] BYREF
  int *v28; // [rsp+78h] [rbp-1h]
  __int64 v29; // [rsp+80h] [rbp+7h]

  v8 = 0;
  CurrentNodeNumber = KeGetCurrentNodeNumber();
  LockArray_high = HIDWORD(KeGetPcr()[1].LockArray);
  v11 = CurrentNodeNumber;
  if ( RxContext )
    goto LABEL_6;
  v12 = RxContextLookasideList.L.ListHead.Alignment + ((unsigned __int64)(unsigned int)(LockArray_high + 1) << 7);
  if ( !*(_BYTE *)(v12 + 176) )
    PplpLazyInitializeLookasideList(RxContextLookasideList.L.ListHead.Alignment, v12 + 64);
  RxContext = (PRX_CONTEXT)ExAllocateFromLookasideListEx((PLOOKASIDE_LIST_EX)(v12 + 64));
  if ( RxContext )
  {
    v8 = 1;
LABEL_6:
    *(_OWORD *)&RxContext->NodeTypeCode = 0;
    *(_OWORD *)&RxContext->ContextListEntry.Blink = 0;
    *(_OWORD *)&RxContext->RealDevice = 0;
    *(_OWORD *)&RxContext->CurrentIrpSp = 0;
    *(_OWORD *)&RxContext->pFobx = 0;
    *(_OWORD *)&RxContext->NonPagedFcb = 0;
    *(_OWORD *)&RxContext->OriginalThread = 0;
    RxContext->LockManagerContext = 0;
    memset((char *)&RxContext->RdbssDbgExtension + 4, 0, 0x13Cu);
    memset(&RxContext->LowIoContext.ParamsFor.IoCtl.FsControlCode, 0, 0x1C4u);
    LODWORD(RxContext->RdbssDbgExtension) = v8;
    LOWORD(RxContext->LowIoContext.ParamsFor.ReadWrite.Flags) = v11;
    WORD1(RxContext->LowIoContext.ParamsFor.Locks.Length) = LockArray_high;
    RxInitializeContext(Irp, RxDeviceObject, InitialContextFlags, RxContext);
    v13 = &RxActiveContexts
        + 12
        * (((unsigned __int8)(WORD1(RxContext->LowIoContext.ParamsFor.Locks.Length)
                            % (unsigned int)RxActiveContextNodeBucketSize)
          + (unsigned __int8)RxActiveContextNodeBucketSize
          * (unsigned __int8)LOWORD(RxContext->LowIoContext.ParamsFor.ReadWrite.Flags))
         & 0x3F);
    v14 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&v13[4]);
    Blink = v13->Blink;
    if ( Blink->Flink != v13 )
      __fastfail(3u);
    RxContext->ContextListEntry.Flink = v13;
    RxContext->ContextListEntry.Blink = Blink;
    Blink->Flink = &RxContext->ContextListEntry;
    v13->Blink = &RxContext->ContextListEntry;
    KeReleaseSpinLock((PKSPIN_LOCK)&v13[4], v14);
    if ( Irp )
    {
      ActivityId = 0;
      EtwActivityIdControl(1u, &ActivityId);
      if ( (int)IoGetActivityIdIrp(Irp, &RxContext->LowIoContext.Flags + 1) < 0 )
        EtwActivityIdControl(3u, (LPGUID)(&RxContext->LowIoContext.Flags + 1));
      if ( Microsoft_Windows_Networking_CorrelationEnabled )
      {
        v20 = (const GUID *)(&RxContext->LowIoContext.Flags + 1);
        v22 = 0;
        if ( Microsoft_Windows_Networking_CorrelationTraceActivityPayload )
        {
          *(_QWORD *)&EventDescriptor.Id = &Microsoft_Windows_Networking_ProviderId;
          v25 = &v22;
          EventDescriptor.Keyword = 16;
          v26 = 4;
          EtwWrite(
            Microsoft_Windows_Networking_CorrelationHandle,
            &ActivityStart,
            v20,
            2u,
            (PEVENT_DATA_DESCRIPTOR)&EventDescriptor);
        }
        else
        {
          EtwWrite(Microsoft_Windows_Networking_CorrelationHandle, &ActivityStart, v20, 0, 0);
        }
      }
      if ( Microsoft_Windows_Networking_CorrelationEnabled )
      {
        *(_QWORD *)&EventDescriptor.Id = ActivityTransfer;
        v19 = (const GUID *)(&RxContext->LowIoContext.Flags + 1);
        v22 = 0;
        EventDescriptor.Keyword = 0x8000000000000001uLL;
        if ( Microsoft_Windows_Networking_CorrelationTraceActivityPayload )
        {
          UserData.Ptr = (ULONGLONG)&Microsoft_Windows_Networking_ProviderId;
          v28 = &v22;
          *(_QWORD *)&UserData.Size = 16;
          v29 = 4;
          EtwWriteTransfer(
            Microsoft_Windows_Networking_CorrelationHandle,
            &EventDescriptor,
            v19,
            &ActivityId,
            2u,
            &UserData);
        }
        else
        {
          EtwWriteTransfer(Microsoft_Windows_Networking_CorrelationHandle, &EventDescriptor, v19, &ActivityId, 0, 0);
        }
      }
    }
    v16 = RxContext->NonPagedFcb->AdvancedFcbHeaderMutex.Event.Header.WaitListHead.Blink;
    if ( v16 )
    {
      v17 = v16[41].Blink;
      if ( v17 )
        ((void (__fastcall *)(PRX_CONTEXT, _QWORD))v17)(RxContext, 0);
    }
    return RxContext;
  }
  if ( Irp )
  {
    MajorFunction = Irp->Tail.Overlay.CurrentStackLocation->MajorFunction;
    if ( MajorFunction == 2 || MajorFunction == 18 )
    {
      do
      {
        RxContext = (PRX_CONTEXT)ExpInterlockedPopEntrySList(&MustSucceedRxContextSList);
        if ( RxContext )
        {
          v8 = 0x8000000;
          goto LABEL_6;
        }
      }
      while ( !KeWaitForSingleObject(&MustSucceedRxContextEvent, Executive, 0, 0, 0) );
      return 0;
    }
  }
  return RxContext;
}

```

## disassembly

```asm
0x140003ae0  push    rbp
0x140003ae2  push    rbx
0x140003ae3  push    rsi
0x140003ae4  push    rdi
0x140003ae5  push    r12
0x140003ae7  push    r13
0x140003ae9  push    r14
0x140003aeb  push    r15
0x140003aed  lea     rbp, [rsp-1Fh]
0x140003af2  sub     rsp, 98h
0x140003af9  mov     rax, cs:__security_cookie
0x140003b00  xor     rax, rsp
0x140003b03  mov     [rbp+57h+var_48], rax
0x140003b07  mov     rbx, r9
0x140003b0a  mov     r12d, r8d
0x140003b0d  mov     r15, rdx
0x140003b10  mov     rsi, rcx
0x140003b13  xor     edi, edi
0x140003b15  call    cs:__imp_KeGetCurrentNodeNumber
0x140003b1c  nop     dword ptr [rax+rax+00h]
0x140003b21  mov     r14d, gs:1A4h
0x140003b2a  movzx   r13d, ax
0x140003b2e  test    rbx, rbx
0x140003b31  jnz     short loc_140003B7D
0x140003b33  mov     r8, qword ptr cs:RxContextLookasideList.L
0x140003b3a  lea     ebx, [r14+1]
0x140003b3e  shl     rbx, 7
0x140003b42  add     rbx, r8
0x140003b45  movzx   eax, byte ptr [rbx+0B0h]
0x140003b4c  test    al, al
0x140003b4e  jnz     short loc_140003B5C
0x140003b50  lea     rdx, [rbx+40h]
0x140003b54  mov     rcx, r8
0x140003b57  call    PplpLazyInitializeLookasideList
0x140003b5c  lea     rcx, [rbx+40h]; Lookaside
0x140003b60  call    cs:__imp_ExAllocateFromLookasideListEx
0x140003b67  nop     dword ptr [rax+rax+00h]
0x140003b6c  mov     rbx, rax
0x140003b6f  test    rax, rax
0x140003b72  jz      loc_140003E2D
0x140003b78  mov     edi, 1
0x140003b7d  xorps   xmm0, xmm0
0x140003b80  lea     rcx, [rbx+7Ch]; void *
0x140003b84  movups  xmmword ptr [rbx], xmm0
0x140003b87  xor     eax, eax
0x140003b89  xor     edx, edx; Val
0x140003b8b  movups  xmmword ptr [rbx+10h], xmm0
0x140003b8f  mov     r8d, 13Ch; Size
0x140003b95  movups  xmmword ptr [rbx+20h], xmm0
0x140003b99  movups  xmmword ptr [rbx+30h], xmm0
0x140003b9d  movups  xmmword ptr [rbx+40h], xmm0
0x140003ba1  movups  xmmword ptr [rbx+50h], xmm0
0x140003ba5  movups  xmmword ptr [rbx+60h], xmm0
0x140003ba9  mov     [rbx+70h], rax
0x140003bad  call    memset
0x140003bb2  lea     rcx, [rbx+1BCh]; void *
0x140003bb9  xor     edx, edx; Val
0x140003bbb  mov     r8d, 1C4h; Size
0x140003bc1  call    memset
0x140003bc6  mov     r9, rbx; RxContext
0x140003bc9  mov     [rbx+78h], edi
0x140003bcc  mov     r8d, r12d; InitialContextFlags
0x140003bcf  mov     [rbx+1B8h], r13w
0x140003bd7  mov     rdx, r15; RxDeviceObject
0x140003bda  mov     [rbx+1BAh], r14w
0x140003be2  mov     rcx, rsi; Irp
0x140003be5  call    RxInitializeContext
0x140003bea  movzx   eax, word ptr [rbx+1BAh]
0x140003bf1  lea     r15, RxActiveContexts
0x140003bf8  movzx   r8d, word ptr [rbx+1B8h]
0x140003c00  xor     edx, edx
0x140003c02  div     cs:RxActiveContextNodeBucketSize
0x140003c08  imul    r8d, cs:RxActiveContextNodeBucketSize
0x140003c10  lea     eax, [rdx+r8]
0x140003c14  and     eax, 3Fh
0x140003c17  lea     rdi, [rax+rax*2]
0x140003c1b  shl     rdi, 6
0x140003c1f  lea     r14, [rdi+r15]
0x140003c23  lea     rcx, [r14+40h]; SpinLock
0x140003c27  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140003c2e  nop     dword ptr [rax+rax+00h]
0x140003c33  mov     rdx, [rdi+r15+8]
0x140003c38  lea     rcx, [rdi+r15]
0x140003c3c  movzx   r8d, al
0x140003c40  cmp     [rdx], rcx
0x140003c43  jz      short loc_140003C4C
0x140003c45  mov     ecx, 3
0x140003c4a  int     29h; Win8: RtlFailFast(ecx)
0x140003c4c  lea     rax, [rbx+8]
0x140003c50  mov     [rax], rcx
0x140003c53  mov     [rax+8], rdx
0x140003c57  mov     [rdx], rax
0x140003c5a  movzx   edx, r8b; NewIrql
0x140003c5e  mov     [rcx+8], rax
0x140003c62  lea     rcx, [r14+40h]; SpinLock
0x140003c66  call    cs:__imp_KeReleaseSpinLock
0x140003c6d  nop     dword ptr [rax+rax+00h]
0x140003c72  test    rsi, rsi
0x140003c75  jz      short loc_140003CE3
0x140003c77  xorps   xmm0, xmm0
0x140003c7a  lea     rdx, [rbp+57h+ActivityId]; ActivityId
0x140003c7e  mov     ecx, 1; ControlCode
0x140003c83  movups  xmmword ptr [rbp+57h+ActivityId.Data1], xmm0
0x140003c87  call    cs:__imp_EtwActivityIdControl
0x140003c8e  nop     dword ptr [rax+rax+00h]
0x140003c93  lea     rdi, [rbx+19Ch]
0x140003c9a  mov     rcx, rsi
0x140003c9d  mov     rdx, rdi
0x140003ca0  call    cs:__imp_IoGetActivityIdIrp
0x140003ca7  nop     dword ptr [rax+rax+00h]
0x140003cac  test    eax, eax
0x140003cae  jns     short loc_140003CC4
0x140003cb0  mov     rdx, rdi; ActivityId
0x140003cb3  mov     ecx, 3; ControlCode
0x140003cb8  call    cs:__imp_EtwActivityIdControl
0x140003cbf  nop     dword ptr [rax+rax+00h]
0x140003cc4  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x140003cca  lea     rsi, Microsoft_Windows_Networking_ProviderId
0x140003cd1  test    eax, eax
0x140003cd3  jnz     loc_140003DAB
0x140003cd9  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x140003cdf  test    eax, eax
0x140003ce1  jnz     short loc_140003D2D
0x140003ce3  mov     rax, [rbx+50h]
0x140003ce7  mov     rcx, [rax+160h]
0x140003cee  test    rcx, rcx
0x140003cf1  jz      short loc_140003D09
0x140003cf3  mov     rax, [rcx+298h]
0x140003cfa  test    rax, rax
0x140003cfd  jz      short loc_140003D09
0x140003cff  xor     edx, edx
0x140003d01  mov     rcx, rbx
0x140003d04  call    _guard_dispatch_icall
0x140003d09  mov     rax, rbx
0x140003d0c  mov     rcx, [rbp+57h+var_48]
0x140003d10  xor     rcx, rsp; StackCookie
0x140003d13  call    __security_check_cookie
0x140003d18  add     rsp, 98h
0x140003d1f  pop     r15
0x140003d21  pop     r14
0x140003d23  pop     r13
0x140003d25  pop     r12
0x140003d27  pop     rdi
0x140003d28  pop     rsi
0x140003d29  pop     rbx
0x140003d2a  pop     rbp
0x140003d2b  retn
0x140003d2d  mov     rax, cs:ActivityTransfer
0x140003d34  lea     r9, [rbp+57h+ActivityId]; RelatedActivityId
0x140003d38  mov     rcx, cs:Microsoft_Windows_Networking_CorrelationHandle; RegHandle
0x140003d3f  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x140003d43  mov     qword ptr [rbp+57h+EventDescriptor.Id], rax
0x140003d47  mov     r8, rdi; ActivityId
0x140003d4a  mov     rax, 8000000000000001h
0x140003d54  mov     [rbp+57h+var_A0], 0
0x140003d5b  mov     [rbp+57h+EventDescriptor.Keyword], rax
0x140003d5f  mov     eax, cs:Microsoft_Windows_Networking_CorrelationTraceActivityPayload
0x140003d65  test    eax, eax
0x140003d67  jz      loc_140003E17
0x140003d6d  lea     rax, [rbp+57h+var_A0]
0x140003d71  mov     [rbp+57h+var_68.Ptr], rsi
0x140003d75  mov     [rbp+57h+var_58], rax
0x140003d79  lea     rax, [rbp+57h+var_68]
0x140003d7d  mov     [rsp+0D0h+UserData], rax; UserData
0x140003d82  mov     [rsp+0D0h+UserDataCount], 2; UserDataCount
0x140003d8a  mov     qword ptr [rbp+57h+var_68.Size], 10h
0x140003d92  mov     [rbp+57h+var_50], 4
0x140003d9a  call    cs:__imp_EtwWriteTransfer
0x140003da1  nop     dword ptr [rax+rax+00h]
0x140003da6  jmp     loc_140003CE3
0x140003dab  mov     eax, cs:Microsoft_Windows_Networking_CorrelationTraceActivityPayload
0x140003db1  lea     rdx, ActivityStart; EventDescriptor
0x140003db8  mov     rcx, cs:Microsoft_Windows_Networking_CorrelationHandle; RegHandle
0x140003dbf  mov     r8, rdi; ActivityId
0x140003dc2  mov     [rbp+57h+var_A0], 0
0x140003dc9  test    eax, eax
0x140003dcb  jz      short loc_140003E09
0x140003dcd  lea     rax, [rbp+57h+var_A0]
0x140003dd1  mov     qword ptr [rbp+57h+EventDescriptor.Id], rsi
0x140003dd5  mov     [rbp+57h+var_78], rax
0x140003dd9  mov     r9d, 2; UserDataCount
0x140003ddf  lea     rax, [rbp+57h+EventDescriptor]
0x140003de3  mov     [rbp+57h+EventDescriptor.Keyword], 10h
0x140003deb  mov     qword ptr [rsp+0D0h+UserDataCount], rax; UserData
0x140003df0  mov     [rbp+57h+var_70], 4
0x140003df8  call    cs:__imp_EtwWrite
0x140003dff  nop     dword ptr [rax+rax+00h]
0x140003e04  jmp     loc_140003CD9
0x140003e09  mov     qword ptr [rsp+0D0h+UserDataCount], 0
0x140003e12  xor     r9d, r9d
0x140003e15  jmp     short loc_140003DF8
0x140003e17  mov     [rsp+0D0h+UserData], 0
0x140003e20  mov     [rsp+0D0h+UserDataCount], 0
0x140003e28  jmp     loc_140003D9A
0x140003e2d  test    rsi, rsi
0x140003e30  jz      loc_140003D09
0x140003e36  mov     rax, [rsi+0B8h]
0x140003e3d  movzx   ecx, byte ptr [rax]
0x140003e40  cmp     cl, 2
0x140003e43  jnz     short loc_140003E95
0x140003e45  lea     rcx, MustSucceedRxContextSList; ListHead
0x140003e4c  call    cs:__imp_ExpInterlockedPopEntrySList
0x140003e53  nop     dword ptr [rax+rax+00h]
0x140003e58  mov     rbx, rax
0x140003e5b  test    rax, rax
0x140003e5e  jz      short loc_140003E6A
0x140003e60  mov     edi, 8000000h
0x140003e65  jmp     loc_140003B7D
0x140003e6a  xor     r9d, r9d; Alertable
0x140003e6d  mov     qword ptr [rsp+0D0h+UserDataCount], rdi; Timeout
0x140003e72  xor     r8d, r8d; WaitMode
0x140003e75  lea     rcx, MustSucceedRxContextEvent; Object
0x140003e7c  xor     edx, edx; WaitReason
0x140003e7e  call    cs:__imp_KeWaitForSingleObject
0x140003e85  nop     dword ptr [rax+rax+00h]
0x140003e8a  test    eax, eax
0x140003e8c  jz      short loc_140003E45
0x140003e8e  xor     ebx, ebx
0x140003e90  jmp     loc_140003D09
0x140003e95  cmp     cl, 12h
0x140003e98  jnz     loc_140003D09
0x140003e9e  jmp     short loc_140003E45
```
