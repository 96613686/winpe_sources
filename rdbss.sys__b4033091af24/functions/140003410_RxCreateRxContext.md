# RxCreateRxContext

- ea: `0x140003410`
- end: `0x1400037d6`
- name: `RxCreateRxContext`
- size: `966`
- prototype: `PRX_CONTEXT __stdcall(PIRP Irp, PRDBSS_DEVICE_OBJECT RxDeviceObject, ULONG InitialContextFlags)`
- caller_count: `13`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14004bed8`
- `0x14004cac0`
- `0x14004d498`
- `0x14004dff0`
- `0x14004fef0`
- `0x140050414`
- `0x1400511d0`
- `0x140057a80`
- `0x140063090`
- `0x140072d20`
- `0x140075940`
- `0x140075b10`
- `0x140077390`

## callees

- `0x140003410`
- `0x140003eb0`
- `0x140025c20`
- `0x140025d00`
- `0x140026080`
- `0x1400623c0`

## import_xrefs

- `ntoskrnl!EtwActivityIdControl` at `0x1400035b2`
- `ntoskrnl!EtwActivityIdControl` at `0x1400035e3`
- `ntoskrnl!EtwActivityIdControl` at `0x1400035b2`
- `ntoskrnl!EtwActivityIdControl` at `0x1400035e3`
- `ntoskrnl!EtwWriteTransfer` at `0x1400036cb`
- `ntoskrnl!EtwWriteTransfer` at `0x1400036cb`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14000377d`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14000377d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003591`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003591`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14000343e`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14000343e`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14000348a`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14000348a`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1400035cb`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1400035cb`
- `ntoskrnl!EtwWrite` at `0x140003729`
- `ntoskrnl!EtwWrite` at `0x140003729`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003552`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003552`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400037b4`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400037b4`

## pseudocode

```c
PRX_CONTEXT __stdcall RxCreateRxContext(PIRP Irp, PRDBSS_DEVICE_OBJECT RxDeviceObject, ULONG InitialContextFlags)
{
  USHORT CurrentNodeNumber; // ax
  int LockArray_high; // edi
  USHORT v8; // r13
  ULONGLONG v9; // rbx
  char *v10; // rbx
  int v11; // r14d
  LIST_ENTRY *v12; // r14
  KIRQL v13; // al
  struct _LIST_ENTRY *Blink; // rdx
  __int64 v15; // rcx
  void (__fastcall *v16)(char *, _QWORD); // rax
  const GUID *v18; // r8
  const GUID *v19; // r8
  UCHAR MajorFunction; // cl
  int v21; // [rsp+30h] [rbp-39h] BYREF
  GUID ActivityId; // [rsp+38h] [rbp-31h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+48h] [rbp-21h] BYREF
  int *v24; // [rsp+58h] [rbp-11h]
  __int64 v25; // [rsp+60h] [rbp-9h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+68h] [rbp-1h] BYREF
  int *v27; // [rsp+78h] [rbp+Fh]
  __int64 v28; // [rsp+80h] [rbp+17h]

  CurrentNodeNumber = KeGetCurrentNodeNumber();
  LockArray_high = HIDWORD(KeGetPcr()[1].LockArray);
  v8 = CurrentNodeNumber;
  v9 = RxContextLookasideList.L.ListHead.Alignment + ((unsigned __int64)(unsigned int)(LockArray_high + 1) << 7);
  if ( !*(_BYTE *)(v9 + 176) )
    PplpLazyInitializeLookasideList(RxContextLookasideList.L.ListHead.Alignment, v9 + 64);
  v10 = (char *)ExAllocateFromLookasideListEx((PLOOKASIDE_LIST_EX)(v9 + 64));
  if ( v10 )
  {
    v11 = 1;
LABEL_5:
    *(_OWORD *)v10 = 0;
    *((_OWORD *)v10 + 1) = 0;
    *((_OWORD *)v10 + 2) = 0;
    *((_OWORD *)v10 + 3) = 0;
    *((_OWORD *)v10 + 4) = 0;
    *((_OWORD *)v10 + 5) = 0;
    *((_OWORD *)v10 + 6) = 0;
    *((_QWORD *)v10 + 14) = 0;
    memset(v10 + 124, 0, 0x13Cu);
    memset(v10 + 444, 0, 0x1C4u);
    *((_DWORD *)v10 + 30) = v11;
    *((_WORD *)v10 + 220) = v8;
    *((_WORD *)v10 + 221) = LockArray_high;
    RxInitializeContext(Irp, RxDeviceObject, InitialContextFlags, (PRX_CONTEXT)v10);
    v12 = &RxActiveContexts
        + 12
        * (((unsigned __int8)(*((unsigned __int16 *)v10 + 221) % (unsigned int)RxActiveContextNodeBucketSize)
          + (unsigned __int8)RxActiveContextNodeBucketSize * (unsigned __int8)*((_WORD *)v10 + 220))
         & 0x3F);
    v13 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&v12[4]);
    Blink = v12->Blink;
    if ( Blink->Flink != v12 )
      __fastfail(3u);
    *((_QWORD *)v10 + 1) = v12;
    *((_QWORD *)v10 + 2) = Blink;
    Blink->Flink = (struct _LIST_ENTRY *)(v10 + 8);
    v12->Blink = (struct _LIST_ENTRY *)(v10 + 8);
    KeReleaseSpinLock((PKSPIN_LOCK)&v12[4], v13);
    if ( Irp )
    {
      ActivityId = 0;
      EtwActivityIdControl(1u, &ActivityId);
      if ( (int)IoGetActivityIdIrp(Irp, v10 + 412) < 0 )
        EtwActivityIdControl(3u, (LPGUID)(v10 + 412));
      if ( Microsoft_Windows_Networking_CorrelationEnabled )
      {
        v19 = (const GUID *)(v10 + 412);
        v21 = 0;
        if ( Microsoft_Windows_Networking_CorrelationTraceActivityPayload )
        {
          *(_QWORD *)&EventDescriptor.Id = &Microsoft_Windows_Networking_ProviderId;
          v24 = &v21;
          EventDescriptor.Keyword = 16;
          v25 = 4;
          EtwWrite(
            Microsoft_Windows_Networking_CorrelationHandle,
            &ActivityStart,
            v19,
            2u,
            (PEVENT_DATA_DESCRIPTOR)&EventDescriptor);
        }
        else
        {
          EtwWrite(Microsoft_Windows_Networking_CorrelationHandle, &ActivityStart, v19, 0, 0);
        }
      }
      if ( Microsoft_Windows_Networking_CorrelationEnabled )
      {
        *(_QWORD *)&EventDescriptor.Id = ActivityTransfer;
        v18 = (const GUID *)(v10 + 412);
        v21 = 0;
        EventDescriptor.Keyword = 0x8000000000000001uLL;
        if ( Microsoft_Windows_Networking_CorrelationTraceActivityPayload )
        {
          UserData.Ptr = (ULONGLONG)&Microsoft_Windows_Networking_ProviderId;
          v27 = &v21;
          *(_QWORD *)&UserData.Size = 16;
          v28 = 4;
          EtwWriteTransfer(
            Microsoft_Windows_Networking_CorrelationHandle,
            &EventDescriptor,
            v18,
            &ActivityId,
            2u,
            &UserData);
        }
        else
        {
          EtwWriteTransfer(Microsoft_Windows_Networking_CorrelationHandle, &EventDescriptor, v18, &ActivityId, 0, 0);
        }
      }
    }
    v15 = *(_QWORD *)(*((_QWORD *)v10 + 10) + 352LL);
    if ( v15 )
    {
      v16 = *(void (__fastcall **)(char *, _QWORD))(v15 + 664);
      if ( v16 )
        v16(v10, 0);
    }
  }
  else if ( Irp )
  {
    MajorFunction = Irp->Tail.Overlay.CurrentStackLocation->MajorFunction;
    if ( MajorFunction == 2 || MajorFunction == 18 )
    {
      do
      {
        v10 = (char *)ExpInterlockedPopEntrySList(&MustSucceedRxContextSList);
        if ( v10 )
        {
          v11 = 0x8000000;
          goto LABEL_5;
        }
      }
      while ( !KeWaitForSingleObject(&MustSucceedRxContextEvent, Executive, 0, 0, 0) );
      return 0;
    }
  }
  return (PRX_CONTEXT)v10;
}

```

## disassembly

```asm
0x140003410  push    rbp
0x140003412  push    rbx
0x140003413  push    rsi
0x140003414  push    rdi
0x140003415  push    r12
0x140003417  push    r13
0x140003419  push    r15
0x14000341b  lea     rbp, [rsp-27h]
0x140003420  sub     rsp, 90h
0x140003427  mov     rax, cs:__security_cookie
0x14000342e  xor     rax, rsp
0x140003431  mov     [rbp+57h+var_38], rax
0x140003435  mov     r12d, r8d
0x140003438  mov     r15, rdx
0x14000343b  mov     rsi, rcx
0x14000343e  call    cs:__imp_KeGetCurrentNodeNumber
0x140003445  nop     dword ptr [rax+rax+00h]
0x14000344a  mov     edi, gs:1A4h
0x140003452  movzx   r13d, ax
0x140003456  mov     r8, qword ptr cs:RxContextLookasideList.L
0x14000345d  lea     ebx, [rdi+1]
0x140003460  shl     rbx, 7
0x140003464  add     rbx, r8
0x140003467  movzx   ecx, byte ptr [rbx+0B0h]
0x14000346e  test    cl, cl
0x140003470  jnz     short loc_14000347E
0x140003472  lea     rdx, [rbx+40h]
0x140003476  mov     rcx, r8
0x140003479  call    PplpLazyInitializeLookasideList
0x14000347e  lea     rcx, [rbx+40h]; Lookaside
0x140003482  mov     [rsp+0C0h+arg_18], r14
0x14000348a  call    cs:__imp_ExAllocateFromLookasideListEx
0x140003491  nop     dword ptr [rax+rax+00h]
0x140003496  mov     rbx, rax
0x140003499  test    rax, rax
0x14000349c  jz      loc_14000375E
0x1400034a2  mov     r14d, 1
0x1400034a8  xorps   xmm0, xmm0
0x1400034ab  lea     rcx, [rbx+7Ch]; void *
0x1400034af  movups  xmmword ptr [rbx], xmm0
0x1400034b2  xor     eax, eax
0x1400034b4  xor     edx, edx; Val
0x1400034b6  movups  xmmword ptr [rbx+10h], xmm0
0x1400034ba  mov     r8d, 13Ch; Size
0x1400034c0  movups  xmmword ptr [rbx+20h], xmm0
0x1400034c4  movups  xmmword ptr [rbx+30h], xmm0
0x1400034c8  movups  xmmword ptr [rbx+40h], xmm0
0x1400034cc  movups  xmmword ptr [rbx+50h], xmm0
0x1400034d0  movups  xmmword ptr [rbx+60h], xmm0
0x1400034d4  mov     [rbx+70h], rax
0x1400034d8  call    memset
0x1400034dd  lea     rcx, [rbx+1BCh]; void *
0x1400034e4  xor     edx, edx; Val
0x1400034e6  mov     r8d, 1C4h; Size
0x1400034ec  call    memset
0x1400034f1  mov     r9, rbx; RxContext
0x1400034f4  mov     [rbx+78h], r14d
0x1400034f8  mov     r8d, r12d; InitialContextFlags
0x1400034fb  mov     [rbx+1B8h], r13w
0x140003503  mov     rdx, r15; RxDeviceObject
0x140003506  mov     [rbx+1BAh], di
0x14000350d  mov     rcx, rsi; Irp
0x140003510  call    RxInitializeContext
0x140003515  movzx   eax, word ptr [rbx+1BAh]
0x14000351c  lea     r15, RxActiveContexts
0x140003523  movzx   r8d, word ptr [rbx+1B8h]
0x14000352b  xor     edx, edx
0x14000352d  div     cs:RxActiveContextNodeBucketSize
0x140003533  imul    r8d, cs:RxActiveContextNodeBucketSize
0x14000353b  lea     eax, [rdx+r8]
0x14000353f  and     eax, 3Fh
0x140003542  lea     rdi, [rax+rax*2]
0x140003546  shl     rdi, 6
0x14000354a  lea     r14, [rdi+r15]
0x14000354e  lea     rcx, [r14+40h]; SpinLock
0x140003552  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140003559  nop     dword ptr [rax+rax+00h]
0x14000355e  mov     rdx, [rdi+r15+8]
0x140003563  lea     rcx, [rdi+r15]
0x140003567  movzx   r8d, al
0x14000356b  cmp     [rdx], rcx
0x14000356e  jz      short loc_140003577
0x140003570  mov     ecx, 3
0x140003575  int     29h; Win8: RtlFailFast(ecx)
0x140003577  lea     rax, [rbx+8]
0x14000357b  mov     [rax], rcx
0x14000357e  mov     [rax+8], rdx
0x140003582  mov     [rdx], rax
0x140003585  movzx   edx, r8b; NewIrql
0x140003589  mov     [rcx+8], rax
0x14000358d  lea     rcx, [r14+40h]; SpinLock
0x140003591  call    cs:__imp_KeReleaseSpinLock
0x140003598  nop     dword ptr [rax+rax+00h]
0x14000359d  test    rsi, rsi
0x1400035a0  jz      short loc_14000360E
0x1400035a2  xorps   xmm0, xmm0
0x1400035a5  lea     rdx, [rbp+57h+ActivityId]; ActivityId
0x1400035a9  mov     ecx, 1; ControlCode
0x1400035ae  movups  xmmword ptr [rbp+57h+ActivityId.Data1], xmm0
0x1400035b2  call    cs:__imp_EtwActivityIdControl
0x1400035b9  nop     dword ptr [rax+rax+00h]
0x1400035be  lea     rdi, [rbx+19Ch]
0x1400035c5  mov     rcx, rsi
0x1400035c8  mov     rdx, rdi
0x1400035cb  call    cs:__imp_IoGetActivityIdIrp
0x1400035d2  nop     dword ptr [rax+rax+00h]
0x1400035d7  test    eax, eax
0x1400035d9  jns     short loc_1400035EF
0x1400035db  mov     rdx, rdi; ActivityId
0x1400035de  mov     ecx, 3; ControlCode
0x1400035e3  call    cs:__imp_EtwActivityIdControl
0x1400035ea  nop     dword ptr [rax+rax+00h]
0x1400035ef  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x1400035f5  lea     rsi, Microsoft_Windows_Networking_ProviderId
0x1400035fc  test    eax, eax
0x1400035fe  jnz     loc_1400036DC
0x140003604  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x14000360a  test    eax, eax
0x14000360c  jnz     short loc_14000365E
0x14000360e  mov     rax, [rbx+50h]
0x140003612  mov     rcx, [rax+160h]
0x140003619  test    rcx, rcx
0x14000361c  jz      short loc_140003634
0x14000361e  mov     rax, [rcx+298h]
0x140003625  test    rax, rax
0x140003628  jz      short loc_140003634
0x14000362a  xor     edx, edx
0x14000362c  mov     rcx, rbx
0x14000362f  call    _guard_dispatch_icall
0x140003634  mov     r14, [rsp+0C0h+arg_18]
0x14000363c  mov     rax, rbx
0x14000363f  mov     rcx, [rbp+57h+var_38]
0x140003643  xor     rcx, rsp; StackCookie
0x140003646  call    __security_check_cookie
0x14000364b  add     rsp, 90h
0x140003652  pop     r15
0x140003654  pop     r13
0x140003656  pop     r12
0x140003658  pop     rdi
0x140003659  pop     rsi
0x14000365a  pop     rbx
0x14000365b  pop     rbp
0x14000365c  retn
0x14000365e  mov     rax, cs:ActivityTransfer
0x140003665  lea     r9, [rbp+57h+ActivityId]; RelatedActivityId
0x140003669  mov     rcx, cs:Microsoft_Windows_Networking_CorrelationHandle; RegHandle
0x140003670  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x140003674  mov     qword ptr [rbp+57h+EventDescriptor.Id], rax
0x140003678  mov     r8, rdi; ActivityId
0x14000367b  mov     rax, 8000000000000001h
0x140003685  mov     [rbp+57h+var_90], 0
0x14000368c  mov     [rbp+57h+EventDescriptor.Keyword], rax
0x140003690  mov     eax, cs:Microsoft_Windows_Networking_CorrelationTraceActivityPayload
0x140003696  test    eax, eax
0x140003698  jz      loc_140003748
0x14000369e  lea     rax, [rbp+57h+var_90]
0x1400036a2  mov     [rbp+57h+var_58.Ptr], rsi
0x1400036a6  mov     [rbp+57h+var_48], rax
0x1400036aa  lea     rax, [rbp+57h+var_58]
0x1400036ae  mov     [rsp+0C0h+UserData], rax; UserData
0x1400036b3  mov     [rsp+0C0h+UserDataCount], 2; UserDataCount
0x1400036bb  mov     qword ptr [rbp+57h+var_58.Size], 10h
0x1400036c3  mov     [rbp+57h+var_40], 4
0x1400036cb  call    cs:__imp_EtwWriteTransfer
0x1400036d2  nop     dword ptr [rax+rax+00h]
0x1400036d7  jmp     loc_14000360E
0x1400036dc  mov     eax, cs:Microsoft_Windows_Networking_CorrelationTraceActivityPayload
0x1400036e2  lea     rdx, ActivityStart; EventDescriptor
0x1400036e9  mov     rcx, cs:Microsoft_Windows_Networking_CorrelationHandle; RegHandle
0x1400036f0  mov     r8, rdi; ActivityId
0x1400036f3  mov     [rbp+57h+var_90], 0
0x1400036fa  test    eax, eax
0x1400036fc  jz      short loc_14000373A
0x1400036fe  lea     rax, [rbp+57h+var_90]
0x140003702  mov     qword ptr [rbp+57h+EventDescriptor.Id], rsi
0x140003706  mov     [rbp+57h+var_68], rax
0x14000370a  mov     r9d, 2; UserDataCount
0x140003710  lea     rax, [rbp+57h+EventDescriptor]
0x140003714  mov     [rbp+57h+EventDescriptor.Keyword], 10h
0x14000371c  mov     qword ptr [rsp+0C0h+UserDataCount], rax; UserData
0x140003721  mov     [rbp+57h+var_60], 4
0x140003729  call    cs:__imp_EtwWrite
0x140003730  nop     dword ptr [rax+rax+00h]
0x140003735  jmp     loc_140003604
0x14000373a  mov     qword ptr [rsp+0C0h+UserDataCount], 0
0x140003743  xor     r9d, r9d
0x140003746  jmp     short loc_140003729
0x140003748  mov     [rsp+0C0h+UserData], 0
0x140003751  mov     [rsp+0C0h+UserDataCount], 0
0x140003759  jmp     loc_1400036CB
0x14000375e  test    rsi, rsi
0x140003761  jz      loc_140003634
0x140003767  mov     rax, [rsi+0B8h]
0x14000376e  movzx   ecx, byte ptr [rax]
0x140003771  cmp     cl, 2
0x140003774  jnz     short loc_1400037CB
0x140003776  lea     rcx, MustSucceedRxContextSList; ListHead
0x14000377d  call    cs:__imp_ExpInterlockedPopEntrySList
0x140003784  nop     dword ptr [rax+rax+00h]
0x140003789  mov     rbx, rax
0x14000378c  test    rax, rax
0x14000378f  jz      short loc_14000379C
0x140003791  mov     r14d, 8000000h
0x140003797  jmp     loc_1400034A8
0x14000379c  xor     r9d, r9d; Alertable
0x14000379f  mov     qword ptr [rsp+0C0h+UserDataCount], 0; Timeout
0x1400037a8  xor     r8d, r8d; WaitMode
0x1400037ab  lea     rcx, MustSucceedRxContextEvent; Object
0x1400037b2  xor     edx, edx; WaitReason
0x1400037b4  call    cs:__imp_KeWaitForSingleObject
0x1400037bb  nop     dword ptr [rax+rax+00h]
0x1400037c0  test    eax, eax
0x1400037c2  jz      short loc_140003776
0x1400037c4  xor     ebx, ebx
0x1400037c6  jmp     loc_140003634
0x1400037cb  cmp     cl, 12h
0x1400037ce  jnz     loc_140003634
0x1400037d4  jmp     short loc_140003776
```
