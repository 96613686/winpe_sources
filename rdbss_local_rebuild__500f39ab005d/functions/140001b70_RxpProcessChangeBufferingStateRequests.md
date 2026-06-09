# RxpProcessChangeBufferingStateRequests

- ea: `0x140001b70`
- end: `0x140001fd2`
- name: `RxpProcessChangeBufferingStateRequests`
- size: `1122`
- prototype: `void __stdcall(PSRV_CALL SrvCall, BOOLEAN UpdateHandlerState)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x140001b10`

## callees

- `0x140001b70`
- `0x140002120`
- `0x1400037e0`
- `0x140003ae0`
- `0x140008f60`
- `0x140009b80`
- `0x140009ea0`
- `0x140011e30`
- `0x140016e70`
- `0x140017190`
- `0x140017280`
- `0x14001810c`
- `0x140023da4`
- `0x1400511d0`
- `0x140057660`
- `0x140058540`
- `0x140058f00`
- `0x14005f110`
- `0x140071590`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140001ea9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001ea9`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001d00`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001d00`
- `ntoskrnl!ExAcquireFastMutex` at `0x140001c53`
- `ntoskrnl!ExAcquireFastMutex` at `0x140001c53`
- `ntoskrnl!ExReleaseFastMutex` at `0x140001d13`
- `ntoskrnl!ExReleaseFastMutex` at `0x140001d13`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001c66`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001c66`

## pseudocode

```c
void __stdcall RxpProcessChangeBufferingStateRequests(PSRV_CALL SrvCall, BOOLEAN UpdateHandlerState)
{
  char v2; // r8
  enum _RX_BLOCK_CONDITION *RxContext; // rdi
  LIST_ENTRY *p_HandlerList; // r14
  struct _LIST_ENTRY *v6; // r15
  KIRQL v7; // al
  __int64 Flink; // rsi
  KIRQL v9; // dl
  struct _LIST_ENTRY *v10; // rax
  char v11; // bp
  struct _LIST_ENTRY *Blink; // rcx
  LIST_ENTRY *p_LastChanceHandlerList; // rax
  __int64 v14; // rdx
  __int64 v15; // rax
  char v16; // cl
  char v17; // al
  char v18; // bp
  __int64 v19; // rbp
  __int64 v20; // r15
  __int64 v21; // r8
  __int64 v22; // rdx
  ULONG v23; // r8d
  const CHAR *v24; // r9
  const CHAR *pContext; // [rsp+20h] [rbp-48h]
  ULONG SerialNumber[2]; // [rsp+28h] [rbp-40h]
  struct _LIST_ENTRY *v27; // [rsp+70h] [rbp+8h]
  __int64 v28; // [rsp+78h] [rbp+10h] BYREF
  char v29; // [rsp+80h] [rbp+18h]

  v29 = v2;
  LOBYTE(v28) = UpdateHandlerState;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_2a2c931366f233ae252535abde3f9a0d_Traceguids, SrvCall);
  }
  RxContext = (enum _RX_BLOCK_CONDITION *)RxCreateRxContextEx(0, (PRDBSS_DEVICE_OBJECT)SrvCall->pDomainName, 2u, 0);
  if ( !RxContext )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_2a2c931366f233ae252535abde3f9a0d_Traceguids);
    }
    return;
  }
  p_HandlerList = &SrvCall->BufferingManager.HandlerList;
  v6 = 0;
  v27 = 0;
  v29 = 0;
  while ( 1 )
  {
    ExAcquireFastMutex((PFAST_MUTEX)&SrvCall[1]);
    v7 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&SrvCall->BufferingManager.CumulativeNumberOfBufferingChangeRequests);
    Flink = (__int64)p_HandlerList->Flink;
    v9 = v7;
    if ( p_HandlerList->Flink == p_HandlerList )
    {
      Flink = 0;
    }
    else
    {
      if ( *(LIST_ENTRY **)(Flink + 8) != p_HandlerList
        || (v10 = *(struct _LIST_ENTRY **)Flink, *(_QWORD *)(*(_QWORD *)Flink + 8LL) != Flink) )
      {
LABEL_59:
        __fastfail(3u);
      }
      p_HandlerList->Flink = v10;
      v10->Blink = p_HandlerList;
    }
    v11 = 0;
    if ( v6 )
    {
      Blink = SrvCall->BufferingManager.LastChanceHandlerList.Blink;
      p_LastChanceHandlerList = &SrvCall->BufferingManager.LastChanceHandlerList;
      if ( Blink->Flink != &SrvCall->BufferingManager.LastChanceHandlerList )
        goto LABEL_59;
      v6->Flink = p_LastChanceHandlerList;
      v6->Blink = Blink;
      Blink->Flink = v6;
      SrvCall->BufferingManager.LastChanceHandlerList.Blink = v6;
      v27 = 0;
      if ( !BYTE2(SrvCall->BufferingManager.SpinLock) && p_LastChanceHandlerList->Flink != p_LastChanceHandlerList )
      {
        BYTE2(SrvCall->BufferingManager.SpinLock) = 1;
        v11 = 1;
      }
    }
    if ( !Flink )
      BYTE1(SrvCall->BufferingManager.SpinLock) = 0;
    KeReleaseSpinLock((PKSPIN_LOCK)&SrvCall->BufferingManager.CumulativeNumberOfBufferingChangeRequests, v9);
    ExReleaseFastMutex((PFAST_MUTEX)&SrvCall[1]);
    if ( v11 )
    {
      RxReference(SrvCall);
      RxPostToWorkerThread(
        RxFileSystemDeviceObject,
        RealTimeWorkQueue,
        (PRX_WORK_QUEUE_ITEM)&SrvCall->BufferingManager.Mutex.Owner,
        RxLastChanceHandlerForChangeBufferingStateRequests,
        SrvCall);
    }
    if ( !Flink )
      break;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      *(_QWORD *)SerialNumber = *(_QWORD *)(Flink + 32);
      pContext = *(const CHAR **)(Flink + 40);
      WPP_SF_qqq(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_2a2c931366f233ae252535abde3f9a0d_Traceguids);
    }
    *(_DWORD *)(Flink + 16) |= 0x10000000u;
    v14 = *(_QWORD *)(Flink + 40);
    v15 = *(_QWORD *)(v14 + 128);
    v16 = v15 == 0;
    LOBYTE(v28) = v15 == 0;
    if ( v15 )
    {
      v17 = RxWaitForStableLViewOnFcbAndAcquireRundown(RxContext, (PMRX_FCB)v14, (__int64)&v28);
      v16 = v28;
      v18 = v17;
      v29 = v17;
    }
    else
    {
      v18 = v29;
    }
    if ( (v18 || v16)
      && !_RxAcquireFcb(*(PFCB *)(Flink + 40), (PRX_CONTEXT)0xFFFFFFFFFFFFFFFFLL, 1u, 0, pContext, SerialNumber[0]) )
    {
      v19 = *(_QWORD *)(Flink + 40);
      v20 = *(_QWORD *)(Flink + 32);
      RxpReferenceNetFcb((PFCB)v19);
      RxDecrementOutstandingBufferingChangesOnFcb(v19);
      v22 = *(unsigned int *)(v19 + 156);
      if ( (v22 & 0x10) != 0 || v20 && (*(_DWORD *)(v20 + 72) & 4) == 0 )
      {
        if ( (unsigned int)RxDowngradeOplockState(Flink, 0, v21) != 259 )
          goto LABEL_44;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          SerialNumber[0] = v20;
          LODWORD(pContext) = *(_DWORD *)(v19 + 156);
          WPP_SF_qdq(WPP_GLOBAL_Control->AttachedDevice, v22, v21, v19);
        }
LABEL_44:
        RxPrepareRequestForReuse((PCHANGE_BUFFERING_STATE_REQUEST)Flink);
        ExFreePoolWithTag((PVOID)Flink, 0);
      }
      if ( !RxpDereferenceAndFinalizeNetFcb((PFCB)v19, (PRX_CONTEXT)0xFFFFFFFFFFFFFFFELL, 0, 0) )
        _RxReleaseFcb((PRX_CONTEXT)0xFFFFFFFFFFFFFFFFLL, (PMRX_FCB)v19, v23, v24, (ULONG)pContext);
      v18 = v29;
      v6 = v27;
      goto LABEL_48;
    }
    v6 = (struct _LIST_ENTRY *)Flink;
    v27 = (struct _LIST_ENTRY *)Flink;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      *(_QWORD *)SerialNumber = *(_QWORD *)(Flink + 32);
      pContext = *(const CHAR **)(Flink + 40);
      WPP_SF_qqq(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_2a2c931366f233ae252535abde3f9a0d_Traceguids);
    }
LABEL_48:
    if ( v18 )
    {
      RxReleaseLViewRundown(RxContext);
      v29 = 0;
    }
  }
  RxDereference(SrvCall, LHS_LockNotHeld);
  RxDereferenceAndDeleteRxContext_Real((PRX_CONTEXT)RxContext);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_2a2c931366f233ae252535abde3f9a0d_Traceguids, SrvCall);
  }
}

```

## disassembly

```asm
0x140001b70  mov     [rsp+arg_10], r8b
0x140001b75  mov     byte ptr [rsp+arg_8], dl
0x140001b79  push    rbx
0x140001b7a  push    rsi
0x140001b7b  push    rdi
0x140001b7c  sub     rsp, 50h
0x140001b80  mov     rbx, rcx
0x140001b83  mov     rcx, cs:WPP_GLOBAL_Control
0x140001b8a  lea     rsi, WPP_GLOBAL_Control
0x140001b91  cmp     rcx, rsi
0x140001b94  jz      short loc_140001BBB
0x140001b96  mov     eax, [rcx+2Ch]
0x140001b99  test    al, 40h
0x140001b9b  jz      short loc_140001BBB
0x140001b9d  cmp     byte ptr [rcx+29h], 2
0x140001ba1  jb      short loc_140001BBB
0x140001ba3  mov     rcx, [rcx+18h]
0x140001ba7  lea     r8, WPP_2a2c931366f233ae252535abde3f9a0d_Traceguids
0x140001bae  mov     edx, 15h
0x140001bb3  mov     r9, rbx
0x140001bb6  call    WPP_SF_q
0x140001bbb  mov     rdx, [rbx+30h]; RxDeviceObject
0x140001bbf  xor     r9d, r9d; RxContext
0x140001bc2  mov     r8d, 2; InitialContextFlags
0x140001bc8  xor     ecx, ecx; Irp
0x140001bca  call    RxCreateRxContextEx
0x140001bcf  mov     rdi, rax
0x140001bd2  test    rax, rax
0x140001bd5  jnz     short loc_140001C16
0x140001bd7  mov     rcx, cs:WPP_GLOBAL_Control
0x140001bde  cmp     rcx, rsi
0x140001be1  jz      loc_140001FC2
0x140001be7  mov     eax, [rcx+2Ch]
0x140001bea  test    al, 40h
0x140001bec  jz      loc_140001FC2
0x140001bf2  cmp     byte ptr [rcx+29h], 2
0x140001bf6  jb      loc_140001FC2
0x140001bfc  mov     rcx, [rcx+18h]
0x140001c00  lea     r8, WPP_2a2c931366f233ae252535abde3f9a0d_Traceguids
0x140001c07  mov     edx, 16h
0x140001c0c  call    WPP_SF_
0x140001c11  jmp     loc_140001FC2
0x140001c16  mov     [rsp+68h+arg_18], rbp
0x140001c1e  xor     bpl, bpl
0x140001c21  mov     [rsp+68h+var_20], r12
0x140001c26  mov     [rsp+68h+var_28], r13
0x140001c2b  mov     [rsp+68h+var_30], r14
0x140001c30  lea     r14, [rbx+128h]
0x140001c37  mov     [rsp+68h+var_38], r15
0x140001c3c  xor     r15d, r15d
0x140001c3f  mov     [rsp+68h+arg_0], r15
0x140001c44  mov     [rsp+68h+arg_10], bpl
0x140001c4c  lea     rcx, [rbx+208h]; FastMutex
0x140001c53  call    cs:__imp_ExAcquireFastMutex
0x140001c5a  nop     dword ptr [rax+rax+00h]
0x140001c5f  lea     rcx, [rbx+108h]; SpinLock
0x140001c66  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140001c6d  nop     dword ptr [rax+rax+00h]
0x140001c72  mov     rsi, [r14]
0x140001c75  movzx   edx, al; NewIrql
0x140001c78  cmp     rsi, r14
0x140001c7b  jnz     short loc_140001C81
0x140001c7d  xor     esi, esi
0x140001c7f  jmp     short loc_140001C9F
0x140001c81  cmp     [rsi+8], r14
0x140001c85  jnz     loc_140001FCB
0x140001c8b  mov     rax, [rsi]
0x140001c8e  cmp     [rax+8], rsi
0x140001c92  jnz     loc_140001FCB
0x140001c98  mov     [r14], rax
0x140001c9b  mov     [rax+8], r14
0x140001c9f  xor     bpl, bpl
0x140001ca2  test    r15, r15
0x140001ca5  jz      short loc_140001CED
0x140001ca7  mov     rcx, [rbx+140h]
0x140001cae  lea     rax, [rbx+138h]
0x140001cb5  cmp     [rcx], rax
0x140001cb8  jnz     loc_140001FCB
0x140001cbe  mov     [r15], rax
0x140001cc1  mov     [r15+8], rcx
0x140001cc5  mov     [rcx], r15
0x140001cc8  mov     [rax+8], r15
0x140001ccc  mov     [rsp+68h+arg_0], 0
0x140001cd5  cmp     [rbx+102h], bpl
0x140001cdc  jnz     short loc_140001CED
0x140001cde  cmp     [rax], rax
0x140001ce1  jz      short loc_140001CED
0x140001ce3  mov     byte ptr [rbx+102h], 1
0x140001cea  mov     bpl, 1
0x140001ced  test    rsi, rsi
0x140001cf0  jnz     short loc_140001CF9
0x140001cf2  mov     [rbx+101h], sil
0x140001cf9  lea     rcx, [rbx+108h]; SpinLock
0x140001d00  call    cs:__imp_KeReleaseSpinLock
0x140001d07  nop     dword ptr [rax+rax+00h]
0x140001d0c  lea     rcx, [rbx+208h]; FastMutex
0x140001d13  call    cs:__imp_ExReleaseFastMutex
0x140001d1a  nop     dword ptr [rax+rax+00h]
0x140001d1f  test    bpl, bpl
0x140001d22  jz      short loc_140001D50
0x140001d24  mov     rcx, rbx; Instance
0x140001d27  call    RxReference
0x140001d2c  mov     rcx, cs:RxFileSystemDeviceObject; pMRxDeviceObject
0x140001d33  lea     r8, [rbx+1C8h]; pWorkQueueItem
0x140001d3a  lea     r9, RxLastChanceHandlerForChangeBufferingStateRequests; Routine
0x140001d41  mov     [rsp+68h+pContext], rbx; pContext
0x140001d46  mov     edx, 5; WorkQueueType
0x140001d4b  call    RxPostToWorkerThread
0x140001d50  test    rsi, rsi
0x140001d53  jz      loc_140001F5C
0x140001d59  mov     rcx, cs:WPP_GLOBAL_Control
0x140001d60  lea     rax, WPP_GLOBAL_Control
0x140001d67  cmp     rcx, rax
0x140001d6a  jz      short loc_140001DA3
0x140001d6c  mov     eax, [rcx+2Ch]
0x140001d6f  test    al, 40h
0x140001d71  jz      short loc_140001DA3
0x140001d73  cmp     byte ptr [rcx+29h], 2
0x140001d77  jb      short loc_140001DA3
0x140001d79  mov     rax, [rsi+20h]
0x140001d7d  lea     r8, WPP_2a2c931366f233ae252535abde3f9a0d_Traceguids
0x140001d84  mov     rcx, [rcx+18h]
0x140001d88  mov     edx, 17h
0x140001d8d  mov     qword ptr [rsp+68h+SerialNumber], rax; SerialNumber
0x140001d92  mov     r9, rsi
0x140001d95  mov     rax, [rsi+28h]
0x140001d99  mov     [rsp+68h+pContext], rax; SerialNumber
0x140001d9e  call    WPP_SF_qqq
0x140001da3  or      dword ptr [rsi+10h], 10000000h
0x140001daa  mov     rdx, [rsi+28h]; MrxFcb
0x140001dae  mov     rax, [rdx+80h]
0x140001db5  test    rax, rax
0x140001db8  setz    cl
0x140001dbb  mov     byte ptr [rsp+68h+arg_8], cl
0x140001dbf  test    rax, rax
0x140001dc2  jz      short loc_140001DEE
0x140001dc4  mov     r9b, 1
0x140001dc7  lea     rax, [rsp+68h+arg_8]
0x140001dcc  movzx   r8d, r9b
0x140001dd0  mov     [rsp+68h+pContext], rax; __int64
0x140001dd5  mov     rcx, rdi; Condition
0x140001dd8  call    RxWaitForStableLViewOnFcbAndAcquireRundown
0x140001ddd  movzx   ecx, byte ptr [rsp+68h+arg_8]
0x140001de2  movzx   ebp, al
0x140001de5  mov     [rsp+68h+arg_10], al
0x140001dec  jmp     short loc_140001DF6
0x140001dee  movzx   ebp, [rsp+68h+arg_10]
0x140001df6  test    bpl, bpl
0x140001df9  jnz     short loc_140001E03
0x140001dfb  test    cl, cl
0x140001dfd  jz      loc_140001F08
0x140001e03  mov     rcx, [rsi+28h]; Fcb
0x140001e07  xor     r9d, r9d; LineNumber
0x140001e0a  mov     rdx, 0FFFFFFFFFFFFFFFFh; RxContext
0x140001e11  mov     r8d, 1; Mode
0x140001e17  call    __RxAcquireFcb
0x140001e1c  test    eax, eax
0x140001e1e  jnz     loc_140001F08
0x140001e24  mov     rbp, [rsi+28h]
0x140001e28  mov     r15, [rsi+20h]
0x140001e2c  mov     rcx, rbp; Fcb
0x140001e2f  call    RxpReferenceNetFcb
0x140001e34  mov     rcx, rbp
0x140001e37  call    RxDecrementOutstandingBufferingChangesOnFcb
0x140001e3c  mov     edx, [rbp+9Ch]
0x140001e42  test    dl, 10h
0x140001e45  jnz     short loc_140001E8B
0x140001e47  test    r15, r15
0x140001e4a  jz      short loc_140001E54
0x140001e4c  mov     eax, [r15+48h]
0x140001e50  test    al, 4
0x140001e52  jz      short loc_140001E8B
0x140001e54  mov     rcx, cs:WPP_GLOBAL_Control
0x140001e5b  lea     rax, WPP_GLOBAL_Control
0x140001e62  cmp     rcx, rax
0x140001e65  jz      short loc_140001E9C
0x140001e67  mov     eax, [rcx+2Ch]
0x140001e6a  test    al, 40h
0x140001e6c  jz      short loc_140001E9C
0x140001e6e  cmp     byte ptr [rcx+29h], 2
0x140001e72  jb      short loc_140001E9C
0x140001e74  mov     rcx, [rcx+18h]
0x140001e78  mov     r9, rbp
0x140001e7b  mov     qword ptr [rsp+68h+SerialNumber], r15
0x140001e80  mov     dword ptr [rsp+68h+pContext], edx
0x140001e84  call    WPP_SF_qdq
0x140001e89  jmp     short loc_140001E9C
0x140001e8b  xor     edx, edx
0x140001e8d  mov     rcx, rsi
0x140001e90  call    RxDowngradeOplockState
0x140001e95  cmp     eax, 103h
0x140001e9a  jz      short loc_140001EB5
0x140001e9c  mov     rcx, rsi; Request
0x140001e9f  call    RxPrepareRequestForReuse
0x140001ea4  xor     edx, edx; Tag
0x140001ea6  mov     rcx, rsi; P
0x140001ea9  call    cs:__imp_ExFreePoolWithTag
0x140001eb0  nop     dword ptr [rax+rax+00h]
0x140001eb5  xor     r9d, r9d; ForceFinalize
0x140001eb8  xor     r8d, r8d; RecursiveFinalize
0x140001ebb  mov     rdx, 0FFFFFFFFFFFFFFFEh; RxContext
0x140001ec2  mov     rcx, rbp; ThisFcb
0x140001ec5  call    RxpDereferenceAndFinalizeNetFcb
0x140001eca  test    al, al
0x140001ecc  jnz     short loc_140001EDD
0x140001ece  mov     rdx, rbp; MrxFcb
0x140001ed1  mov     rcx, 0FFFFFFFFFFFFFFFFh; RxContext
0x140001ed8  call    __RxReleaseFcb
0x140001edd  movzx   ebp, [rsp+68h+arg_10]
0x140001ee5  mov     r15, [rsp+68h+arg_0]
0x140001eea  test    bpl, bpl
0x140001eed  jz      loc_140001C4C
0x140001ef3  mov     rcx, rdi
0x140001ef6  call    RxReleaseLViewRundown
0x140001efb  mov     [rsp+68h+arg_10], 0
0x140001f03  jmp     loc_140001C4C
0x140001f08  mov     r15, rsi
0x140001f0b  mov     [rsp+68h+arg_0], rsi
0x140001f10  mov     rcx, cs:WPP_GLOBAL_Control
0x140001f17  lea     rax, WPP_GLOBAL_Control
0x140001f1e  cmp     rcx, rax
0x140001f21  jz      short loc_140001EEA
0x140001f23  mov     eax, [rcx+2Ch]
0x140001f26  test    al, 40h
0x140001f28  jz      short loc_140001EEA
0x140001f2a  cmp     byte ptr [rcx+29h], 2
0x140001f2e  jb      short loc_140001EEA
0x140001f30  mov     rax, [rsi+20h]
0x140001f34  lea     r8, WPP_2a2c931366f233ae252535abde3f9a0d_Traceguids
0x140001f3b  mov     rcx, [rcx+18h]
0x140001f3f  mov     edx, 19h
0x140001f44  mov     qword ptr [rsp+68h+SerialNumber], rax
0x140001f49  mov     r9, rsi
0x140001f4c  mov     rax, [rsi+28h]
0x140001f50  mov     [rsp+68h+pContext], rax
0x140001f55  call    WPP_SF_qqq
0x140001f5a  jmp     short loc_140001EEA
0x140001f5c  xor     edx, edx; LockHoldingState
0x140001f5e  mov     rcx, rbx; Instance
0x140001f61  call    RxDereference
0x140001f66  mov     rcx, rdi; RxContext
0x140001f69  call    RxDereferenceAndDeleteRxContext_Real
0x140001f6e  mov     rcx, cs:WPP_GLOBAL_Control
0x140001f75  lea     rax, WPP_GLOBAL_Control
0x140001f7c  cmp     rcx, rax
0x140001f7f  jz      short loc_140001FA6
0x140001f81  mov     eax, [rcx+2Ch]
0x140001f84  test    al, 40h
0x140001f86  jz      short loc_140001FA6
0x140001f88  cmp     byte ptr [rcx+29h], 2
0x140001f8c  jb      short loc_140001FA6
0x140001f8e  mov     rcx, [rcx+18h]
0x140001f92  lea     r8, WPP_2a2c931366f233ae252535abde3f9a0d_Traceguids
0x140001f99  mov     edx, 1Ah
0x140001f9e  mov     r9, rbx
0x140001fa1  call    WPP_SF_q
0x140001fa6  mov     r14, [rsp+68h+var_30]
0x140001fab  mov     r13, [rsp+68h+var_28]
0x140001fb0  mov     r12, [rsp+68h+var_20]
0x140001fb5  mov     rbp, [rsp+68h+arg_18]
0x140001fbd  mov     r15, [rsp+68h+var_38]
0x140001fc2  add     rsp, 50h
0x140001fc6  pop     rdi
0x140001fc7  pop     rsi
0x140001fc8  pop     rbx
0x140001fc9  retn
0x140001fcb  mov     ecx, 3
0x140001fd0  int     29h; Win8: RtlFailFast(ecx)
```
