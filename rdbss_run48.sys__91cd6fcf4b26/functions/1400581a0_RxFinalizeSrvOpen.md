# RxFinalizeSrvOpen

- ea: `0x1400581a0`
- end: `0x140058532`
- name: `RxFinalizeSrvOpen`
- size: `914`
- prototype: `BOOLEAN __stdcall(PSRV_OPEN ThisSrvOpen, BOOLEAN RecursiveFinalize, BOOLEAN ForceFinalize)`
- caller_count: `3`
- callee_count: `12`
- tags: ``

## callers

- `0x140058f00`
- `0x14005be90`
- `0x14006ba40`

## callees

- `0x14000c1c0`
- `0x140014d10`
- `0x140017190`
- `0x14001976c`
- `0x140022d34`
- `0x140022e40`
- `0x140025d00`
- `0x1400581a0`
- `0x140058540`
- `0x140058f00`
- `0x140059660`
- `0x140074ec0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400584e4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400584e4`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400583e1`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400583e1`
- `ntoskrnl!ExReleaseFastMutex` at `0x14005843c`
- `ntoskrnl!ExReleaseFastMutex` at `0x14005843c`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
BOOLEAN __stdcall RxFinalizeSrvOpen(PSRV_OPEN ThisSrvOpen, BOOLEAN RecursiveFinalize, BOOLEAN ForceFinalize)
{
  _QWORD *Context2; // rsi
  int v5; // edi
  bool v6; // zf
  void (__fastcall *v7)(PSRV_OPEN, _QWORD, _QWORD); // rax
  LIST_ENTRY *p_ScavengerFinalizationList; // rax
  struct _LIST_ENTRY *v9; // rcx
  struct _LIST_ENTRY *Blink; // rdx
  PMRXSHADOW_SRV_OPEN ShadowContext; // rax
  LIST_ENTRY *v12; // rax
  struct _SRV_OPEN *v13; // rcx
  struct _LIST_ENTRY *v14; // rdx
  __int64 v15; // rax
  void (__fastcall *v16)(_QWORD, PSRV_OPEN, _QWORD); // rax
  BOOLEAN v17; // bl
  __int64 v19; // rbp
  PLIST_ENTRY v20; // r8
  NTSTATUS *p_OpenStatus; // rax
  __int64 v22; // rdx
  NTSTATUS **v23; // r8
  struct _LIST_ENTRY *Flink; // r14
  __int64 v25; // r9
  struct _LIST_ENTRY DiscardedRequests; // [rsp+30h] [rbp-28h] BYREF

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qZl(
      WPP_GLOBAL_Control->AttachedDevice,
      67,
      *((_DWORD *)&ThisSrvOpen->1 + 8) + 336,
      (_DWORD)ThisSrvOpen,
      (__int64)ThisSrvOpen->Context2 + 336,
      ThisSrvOpen->NodeReferenceCount);
  }
  if ( !ThisSrvOpen->NodeReferenceCount )
  {
    Context2 = ThisSrvOpen->Context2;
    v5 = *(_DWORD *)(&ThisSrvOpen->1 + 3) & 0x10000;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qZ(
        WPP_GLOBAL_Control->AttachedDevice,
        68,
        (unsigned int)&WPP_e7aebc7caeed3866654dc8faf8a6aa71_Traceguids,
        (_DWORD)ThisSrvOpen,
        (__int64)(Context2 + 42));
    }
    if ( !LOBYTE(ThisSrvOpen->TransitionWaitList.Blink)
      && (HIDWORD(ThisSrvOpen->TransitionWaitList.Blink) != 3 || (*(_DWORD *)(&ThisSrvOpen->1 + 3) & 4) != 0) )
    {
      v6 = (*(_DWORD *)(&ThisSrvOpen->1 + 3) & 0x100) == 0;
      DiscardedRequests = 0;
      if ( !v6 )
      {
        v19 = *((_QWORD *)ThisSrvOpen->ShadowContext->FastIoWrite + 4);
        DiscardedRequests.Blink = &DiscardedRequests;
        DiscardedRequests.Flink = &DiscardedRequests;
        ExAcquireFastMutex((PFAST_MUTEX)(v19 + 520));
        RxGatherRequestsForSrvOpen((PSRV_CALL)ThisSrvOpen, (PSRV_OPEN)&DiscardedRequests, v20);
        p_OpenStatus = &ThisSrvOpen->OpenStatus;
        v22 = *(_QWORD *)&ThisSrvOpen->OpenStatus;
        if ( *(PSRV_OPEN *)(v22 + 8) != (PSRV_OPEN)&ThisSrvOpen->OpenStatus )
          goto LABEL_33;
        v23 = (NTSTATUS **)ThisSrvOpen[1].0;
        if ( *v23 != p_OpenStatus )
          goto LABEL_33;
        *v23 = (NTSTATUS *)v22;
        *(_QWORD *)(v22 + 8) = v23;
        ThisSrvOpen[1].0 = (MRX_NORMAL_NODE_HEADER)&ThisSrvOpen->OpenStatus;
        *(_QWORD *)p_OpenStatus = p_OpenStatus;
        *((_DWORD *)&ThisSrvOpen->1 + 18) &= ~0x100u;
        ExReleaseFastMutex((PFAST_MUTEX)(v19 + 520));
        Flink = DiscardedRequests.Flink;
        if ( DiscardedRequests.Flink != &DiscardedRequests )
        {
          do
          {
            RxDecrementOutstandingBufferingChangesOnFcb(ThisSrvOpen->Context2);
            Flink = Flink->Flink;
          }
          while ( Flink != &DiscardedRequests );
          RxpDiscardChangeBufferingStateRequests(&DiscardedRequests);
        }
      }
      if ( (*((_DWORD *)Context2 + 39) & 0x80u) == 0 )
      {
        v7 = *(void (__fastcall **)(PSRV_OPEN, _QWORD, _QWORD))(Context2[49] + 160LL);
        if ( v7 )
          v7(ThisSrvOpen, RecursiveFinalize, ForceFinalize);
      }
      p_ScavengerFinalizationList = &ThisSrvOpen->ScavengerFinalizationList;
      v9 = ThisSrvOpen->ScavengerFinalizationList.Flink;
      if ( v9->Blink != &ThisSrvOpen->ScavengerFinalizationList
        || (Blink = ThisSrvOpen->ScavengerFinalizationList.Blink, Blink->Flink != p_ScavengerFinalizationList) )
      {
LABEL_33:
        __fastfail(3u);
      }
      Blink->Flink = v9;
      v9->Blink = Blink;
      ThisSrvOpen->ScavengerFinalizationList.Blink = &ThisSrvOpen->ScavengerFinalizationList;
      p_ScavengerFinalizationList->Flink = p_ScavengerFinalizationList;
      ShadowContext = ThisSrvOpen->ShadowContext;
      if ( ShadowContext )
      {
        _InterlockedDecrement((volatile signed __int32 *)ShadowContext->FastIoWrite + 16);
        _InterlockedDecrement((volatile signed __int32 *)&ThisSrvOpen->ShadowContext[1].UnderlyingDeviceObject + 1);
        RxDereference(ThisSrvOpen->ShadowContext, LHS_LockNotHeld);
        ThisSrvOpen->ShadowContext = 0;
      }
      LOBYTE(ThisSrvOpen->TransitionWaitList.Blink) = 1;
    }
    v12 = &ThisSrvOpen->ScavengerFinalizationList;
    v13 = (struct _SRV_OPEN *)ThisSrvOpen->ScavengerFinalizationList.Flink;
    if ( v13 == (struct _SRV_OPEN *)&ThisSrvOpen->ScavengerFinalizationList )
      goto LABEL_22;
    if ( (LIST_ENTRY *)v13->pFcb == v12 )
    {
      v14 = ThisSrvOpen->ScavengerFinalizationList.Blink;
      if ( v14->Flink == v12 )
      {
        v14->Flink = (struct _LIST_ENTRY *)v13;
        v13->pFcb = (PMRX_FCB)v14;
        ThisSrvOpen->ScavengerFinalizationList.Blink = &ThisSrvOpen->ScavengerFinalizationList;
        v12->Flink = v12;
LABEL_22:
        v15 = Context2[49];
        if ( v15 )
        {
          v16 = *(void (__fastcall **)(_QWORD, PSRV_OPEN, _QWORD))(v15 + 136);
          if ( v16 )
            v16(0, ThisSrvOpen, ForceFinalize);
        }
        if ( (*(_DWORD *)(&ThisSrvOpen->1 + 3) & 0x80000) != 0 )
        {
          ExFreePoolWithTag(*((PVOID *)&ThisSrvOpen->1 + 10), 0);
          *((_QWORD *)&ThisSrvOpen->1 + 10) = 0;
        }
        if ( v5 )
          *((_DWORD *)Context2 + 39) &= ~0x80000000;
        else
          RxFreeFcbObject(ThisSrvOpen);
        RxpDereferenceAndFinalizeNetFcb((PFCB)Context2, 0, 0, 0);
        v17 = 1;
        goto LABEL_30;
      }
    }
    goto LABEL_33;
  }
  v17 = 0;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    return v17;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_h(WPP_GLOBAL_Control->AttachedDevice, RecursiveFinalize, ForceFinalize);
LABEL_30:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    v25 = 89;
    if ( !v17 )
      v25 = 78;
    WPP_SF_c(WPP_GLOBAL_Control->AttachedDevice, 70, &WPP_e7aebc7caeed3866654dc8faf8a6aa71_Traceguids, v25);
  }
  return v17;
}

```

## disassembly

```asm
0x1400581a0  push    rbx
0x1400581a2  push    r15
0x1400581a4  sub     rsp, 48h
0x1400581a8  mov     rbx, rcx
0x1400581ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1400581b2  lea     r15, WPP_GLOBAL_Control
0x1400581b9  cmp     rcx, r15
0x1400581bc  jz      short loc_1400581CB
0x1400581be  test    dword ptr [rcx+2Ch], 100h
0x1400581c5  jnz     loc_140058461
0x1400581cb  cmp     dword ptr [rbx+4], 0
0x1400581cf  mov     [rsp+58h+arg_0], rbp
0x1400581d4  mov     [rsp+58h+arg_8], rsi
0x1400581d9  mov     [rsp+58h+arg_10], rdi
0x1400581de  jnz     loc_140058383
0x1400581e4  mov     edi, [rbx+48h]
0x1400581e7  mov     rsi, [rbx+20h]
0x1400581eb  and     edi, 10000h
0x1400581f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400581f8  cmp     rcx, r15
0x1400581fb  jz      short loc_14005820A
0x1400581fd  test    dword ptr [rcx+2Ch], 100h
0x140058204  jnz     loc_140058498
0x14005820a  cmp     byte ptr [rbx+0A0h], 0
0x140058211  jnz     loc_1400582C7
0x140058217  cmp     dword ptr [rbx+0A4h], 3
0x14005821e  jnz     short loc_14005822B
0x140058220  mov     eax, [rbx+48h]
0x140058223  test    al, 4
0x140058225  jz      loc_1400582C7
0x14005822b  test    dword ptr [rbx+48h], 100h
0x140058232  xorps   xmm0, xmm0
0x140058235  movups  xmmword ptr [rsp+58h+DiscardedRequests.Flink], xmm0
0x14005823a  jnz     loc_1400583BA
0x140058240  mov     eax, [rsi+9Ch]
0x140058246  test    al, al
0x140058248  js      short loc_140058265
0x14005824a  mov     rax, [rsi+188h]
0x140058251  mov     rax, [rax+0A0h]
0x140058258  test    rax, rax
0x14005825b  jz      short loc_140058265
0x14005825d  mov     rcx, rbx
0x140058260  call    _guard_dispatch_icall
0x140058265  lea     rax, [rbx+88h]
0x14005826c  mov     rcx, [rax]
0x14005826f  cmp     [rcx+8], rax
0x140058273  jnz     loc_14005837C
0x140058279  mov     rdx, [rax+8]
0x14005827d  cmp     [rdx], rax
0x140058280  jnz     loc_14005837C
0x140058286  mov     [rdx], rcx
0x140058289  mov     [rcx+8], rdx
0x14005828d  mov     [rax+8], rax
0x140058291  mov     [rax], rax
0x140058294  mov     rax, [rbx+28h]
0x140058298  test    rax, rax
0x14005829b  jz      short loc_1400582C0
0x14005829d  mov     rax, [rax+20h]
0x1400582a1  xor     edx, edx; LockHoldingState
0x1400582a3  lock dec dword ptr [rax+40h]
0x1400582a7  mov     rax, [rbx+28h]
0x1400582ab  lock dec dword ptr [rax+3Ch]
0x1400582af  mov     rcx, [rbx+28h]; Instance
0x1400582b3  call    RxDereference
0x1400582b8  mov     qword ptr [rbx+28h], 0
0x1400582c0  mov     byte ptr [rbx+0A0h], 1
0x1400582c7  lea     rax, [rbx+88h]
0x1400582ce  mov     rcx, [rax]
0x1400582d1  cmp     rcx, rax
0x1400582d4  jz      short loc_1400582FB
0x1400582d6  cmp     [rcx+8], rax
0x1400582da  jnz     loc_14005837C
0x1400582e0  mov     rdx, [rax+8]
0x1400582e4  cmp     [rdx], rax
0x1400582e7  jnz     loc_14005837C
0x1400582ed  mov     [rdx], rcx
0x1400582f0  mov     [rcx+8], rdx
0x1400582f4  mov     [rax+8], rax
0x1400582f8  mov     [rax], rax
0x1400582fb  mov     rax, [rsi+188h]
0x140058302  test    rax, rax
0x140058305  jz      short loc_14005831D
0x140058307  mov     rax, [rax+88h]
0x14005830e  test    rax, rax
0x140058311  jz      short loc_14005831D
0x140058313  mov     rdx, rbx
0x140058316  xor     ecx, ecx
0x140058318  call    _guard_dispatch_icall
0x14005831d  test    dword ptr [rbx+48h], 80000h
0x140058324  jnz     loc_1400584DE
0x14005832a  test    edi, edi
0x14005832c  jnz     short loc_1400583AB
0x14005832e  mov     rcx, rbx; Object
0x140058331  call    RxFreeFcbObject
0x140058336  xor     r9d, r9d; ForceFinalize
0x140058339  xor     r8d, r8d; RecursiveFinalize
0x14005833c  xor     edx, edx; RxContext
0x14005833e  mov     rcx, rsi; ThisFcb
0x140058341  call    RxpDereferenceAndFinalizeNetFcb
0x140058346  mov     bl, 1
0x140058348  mov     rcx, cs:WPP_GLOBAL_Control
0x14005834f  cmp     rcx, r15
0x140058352  jz      short loc_140058361
0x140058354  test    dword ptr [rcx+2Ch], 100h
0x14005835b  jnz     loc_1400584FD
0x140058361  mov     rdi, [rsp+58h+arg_10]
0x140058366  movzx   eax, bl
0x140058369  mov     rsi, [rsp+58h+arg_8]
0x14005836e  mov     rbp, [rsp+58h+arg_0]
0x140058373  add     rsp, 48h
0x140058377  pop     r15
0x140058379  pop     rbx
0x14005837a  retn
0x14005837c  mov     ecx, 3
0x140058381  int     29h; Win8: RtlFailFast(ecx)
0x140058383  mov     rcx, cs:WPP_GLOBAL_Control
0x14005838a  xor     bl, bl
0x14005838c  cmp     rcx, r15
0x14005838f  jz      short loc_140058361
0x140058391  test    dword ptr [rcx+2Ch], 100h
0x140058398  jz      short loc_140058348
0x14005839a  cmp     byte ptr [rcx+29h], 4
0x14005839e  jb      short loc_140058348
0x1400583a0  mov     rcx, [rcx+18h]
0x1400583a4  call    WPP_SF_h
0x1400583a9  jmp     short loc_140058348
0x1400583ab  and     dword ptr [rsi+9Ch], 7FFFFFFFh
0x1400583b5  jmp     loc_140058336
0x1400583ba  mov     rax, [rbx+28h]
0x1400583be  mov     rcx, [rax+20h]
0x1400583c2  mov     rbp, [rcx+20h]
0x1400583c6  lea     rcx, [rsp+58h+DiscardedRequests]
0x1400583cb  mov     [rsp+58h+DiscardedRequests.Blink], rcx
0x1400583d0  lea     rcx, [rsp+58h+DiscardedRequests]
0x1400583d5  mov     [rsp+58h+DiscardedRequests.Flink], rcx
0x1400583da  lea     rcx, [rbp+208h]; FastMutex
0x1400583e1  call    cs:__imp_ExAcquireFastMutex
0x1400583e8  nop     dword ptr [rax+rax+00h]
0x1400583ed  lea     rdx, [rsp+58h+DiscardedRequests]; SrvOpen
0x1400583f2  mov     rcx, rbx; SrvCall
0x1400583f5  call    RxGatherRequestsForSrvOpen
0x1400583fa  lea     rax, [rbx+0D0h]
0x140058401  mov     rdx, [rax]
0x140058404  cmp     [rdx+8], rax
0x140058408  jnz     loc_14005837C
0x14005840e  mov     r8, [rax+8]
0x140058412  cmp     [r8], rax
0x140058415  jnz     loc_14005837C
0x14005841b  mov     [r8], rdx
0x14005841e  lea     rcx, [rbp+208h]; FastMutex
0x140058425  mov     [rdx+8], r8
0x140058429  mov     [rax+8], rax
0x14005842d  mov     [rax], rax
0x140058430  and     dword ptr [rbx+48h], 0FFFFFEFFh
0x140058437  mov     [rsp+58h+var_18], r14
0x14005843c  call    cs:__imp_ExReleaseFastMutex
0x140058443  nop     dword ptr [rax+rax+00h]
0x140058448  mov     r14, [rsp+58h+DiscardedRequests.Flink]
0x14005844d  lea     rax, [rsp+58h+DiscardedRequests]
0x140058452  cmp     r14, rax
0x140058455  jnz     short loc_1400584CB
0x140058457  mov     r14, [rsp+58h+var_18]
0x14005845c  jmp     loc_140058240
0x140058461  cmp     byte ptr [rcx+29h], 4
0x140058465  jb      loc_1400581CB
0x14005846b  mov     r8, [rbx+20h]
0x14005846f  mov     edx, 43h ; 'C'
0x140058474  mov     eax, [rbx+4]
0x140058477  add     r8, 150h
0x14005847e  mov     rcx, [rcx+18h]
0x140058482  mov     r9, rbx
0x140058485  mov     [rsp+58h+var_30], eax
0x140058489  mov     [rsp+58h+var_38], r8
0x14005848e  call    WPP_SF_qZl
0x140058493  jmp     loc_1400581CB
0x140058498  cmp     byte ptr [rcx+29h], 2
0x14005849c  jb      loc_14005820A
0x1400584a2  mov     rcx, [rcx+18h]
0x1400584a6  lea     rax, [rsi+150h]
0x1400584ad  mov     edx, 44h ; 'D'
0x1400584b2  mov     [rsp+58h+var_38], rax
0x1400584b7  mov     r9, rbx
0x1400584ba  lea     r8, WPP_e7aebc7caeed3866654dc8faf8a6aa71_Traceguids
0x1400584c1  call    WPP_SF_qZ
0x1400584c6  jmp     loc_14005820A
0x1400584cb  lea     rax, [rsp+58h+DiscardedRequests]
0x1400584d0  cmp     r14, rax
0x1400584d3  jnz     loc_14007CC22
0x1400584d9  jmp     loc_14007CC38
0x1400584de  mov     rcx, [rbx+50h]; P
0x1400584e2  xor     edx, edx; Tag
0x1400584e4  call    cs:__imp_ExFreePoolWithTag
0x1400584eb  nop     dword ptr [rax+rax+00h]
0x1400584f0  mov     qword ptr [rbx+50h], 0
0x1400584f8  jmp     loc_14005832A
0x1400584fd  cmp     byte ptr [rcx+29h], 2
0x140058501  jb      loc_140058361
0x140058507  mov     rcx, [rcx+18h]
0x14005850b  lea     r8, WPP_e7aebc7caeed3866654dc8faf8a6aa71_Traceguids
0x140058512  test    bl, bl
0x140058514  mov     eax, 4Eh ; 'N'
0x140058519  mov     r9d, 59h ; 'Y'
0x14005851f  mov     edx, 46h ; 'F'
0x140058524  cmovz   r9d, eax
0x140058528  call    WPP_SF_c
0x14005852d  jmp     loc_140058361
0x14007cc22  mov     rcx, [rbx+20h]
0x14007cc26  call    RxDecrementOutstandingBufferingChangesOnFcb
0x14007cc2b  mov     r14, [r14]
0x14007cc2e  lea     rax, [rsp+58h+DiscardedRequests]
0x14007cc33  cmp     r14, rax
0x14007cc36  jnz     short loc_14007CC22
0x14007cc38  lea     rcx, [rsp+58h+DiscardedRequests]; DiscardedRequests
0x14007cc3d  call    RxpDiscardChangeBufferingStateRequests
0x14007cc42  nop
0x14007cc43  jmp     loc_140058457
```
