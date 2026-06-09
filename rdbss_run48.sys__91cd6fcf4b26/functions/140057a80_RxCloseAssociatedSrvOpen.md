# RxCloseAssociatedSrvOpen

- ea: `0x140057a80`
- end: `0x140057f48`
- name: `RxCloseAssociatedSrvOpen`
- size: `1224`
- prototype: `NTSTATUS __stdcall(PRX_CONTEXT RxContext, PFOBX Fobx)`
- caller_count: `4`
- callee_count: `18`
- tags: `installer_update`

## callers

- `0x14005b620`
- `0x1400649a0`
- `0x14006aa40`
- `0x14006c010`

## callees

- `0x140003410`
- `0x1400037e0`
- `0x14000c1c0`
- `0x14000dcc0`
- `0x14000df50`
- `0x140016e20`
- `0x140016e70`
- `0x140017190`
- `0x14001810c`
- `0x14001828c`
- `0x1400183f4`
- `0x140025d00`
- `0x140057a80`
- `0x140057f50`
- `0x140058130`
- `0x140058f00`
- `0x140059d10`
- `0x140074ec0`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutex` at `0x140057d75`
- `ntoskrnl!ExAcquireFastMutex` at `0x140057d75`
- `ntoskrnl!ExReleaseFastMutex` at `0x140057dc4`
- `ntoskrnl!ExReleaseFastMutex` at `0x140057dc4`

## pseudocode

```c
NTSTATUS __stdcall RxCloseAssociatedSrvOpen(PRX_CONTEXT RxContext, PFOBX Fobx)
{
  __int64 v2; // r8
  NTSTATUS v3; // r14d
  ULONG FobxSerialNumber; // ecx
  unsigned int *Context2; // rbx
  PMRX_FCB pFcb; // rsi
  PRX_CONTEXT v9; // rbp
  unsigned int v10; // eax
  int v11; // edx
  int v12; // r8d
  bool v13; // zf
  PRX_CONTEXT v15; // rax
  __int64 v16; // r12
  PLIST_ENTRY v17; // r8
  _QWORD *v18; // rax
  __int64 v19; // r8
  _QWORD *v20; // rdx
  struct _LIST_ENTRY *Flink; // r12
  __int64 v22; // rdx
  int PagingIoResource; // eax
  struct _LIST_ENTRY DiscardedRequests; // [rsp+40h] [rbp-58h] BYREF

  v3 = 0;
  if ( Fobx )
  {
    FobxSerialNumber = Fobx->FobxSerialNumber;
    if ( (FobxSerialNumber & 0x1000000) != 0 )
      goto LABEL_30;
    Context2 = (unsigned int *)Fobx->Context2;
    if ( (Context2[18] & 4) != 0 )
    {
      Fobx->FobxSerialNumber = FobxSerialNumber | 0x1000000;
      _InterlockedDecrement((volatile signed __int32 *)Context2 + 23);
      if ( (Fobx->FobxSerialNumber & 0x40000000) != 0 )
        _InterlockedDecrement((volatile signed __int32 *)Context2 + 25);
      goto LABEL_30;
    }
    pFcb = (PMRX_FCB)*((_QWORD *)Context2 + 4);
  }
  else
  {
    if ( !RxContext )
      goto LABEL_30;
    pFcb = RxContext->pFcb;
    Context2 = 0;
  }
  v9 = RxContext;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    if ( Context2 )
      v22 = Context2[23];
    else
      v22 = 0xFFFFFFFFLL;
    if ( pFcb )
      PagingIoResource = (int)pFcb[1].Header.PagingIoResource;
    else
      PagingIoResource = 0;
    WPP_SF_qdqdq(WPP_GLOBAL_Control->AttachedDevice, v22, v2, pFcb, PagingIoResource, Context2, v22, Fobx);
  }
  if ( RxContext )
  {
    if ( Fobx )
      goto LABEL_9;
    goto LABEL_61;
  }
  v15 = RxCreateRxContext(0, *(PRDBSS_DEVICE_OBJECT *)(*((_QWORD *)Context2 + 4) + 400LL), 2u);
  v9 = v15;
  if ( v15 )
  {
    LOBYTE(v15->RealDevice) = 2;
    v15->pFcb = pFcb;
    v15->pFobx = (PMRX_FOBX)&Fobx->0;
    if ( Fobx )
    {
      v15->pRelevantSrvOpen = (PMRX_SRV_OPEN)Fobx->Context2;
      goto LABEL_9;
    }
LABEL_61:
    _InterlockedDecrement((volatile signed __int32 *)&pFcb[1].Header.PagingIoResource);
LABEL_9:
    if ( !Context2 )
    {
      _InterlockedDecrement((volatile signed __int32 *)&pFcb->SrvOpenList);
LABEL_28:
      if ( v9 != RxContext )
        RxDereferenceAndDeleteRxContext_Real(v9);
      goto LABEL_30;
    }
    if ( Context2[41] != 3 )
    {
      RxClearDirectExtents((__int64)Context2, (__int64)pFcb);
LABEL_24:
      if ( !(LODWORD(pFcb[1].Header.PagingIoResource) + HIDWORD(pFcb[1].Header.PagingIoResource)) )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 26, &WPP_36817ce08eb83f0e99a0e799ed379106_Traceguids, pFcb);
        }
        HIDWORD(pFcb->SrvOpenList.Flink) &= ~0x40000u;
        RxDeregisterFcbWithBufferingManager(pFcb);
      }
      goto LABEL_28;
    }
    _InterlockedDecrement((volatile signed __int32 *)Context2 + 23);
    if ( (Fobx->FobxSerialNumber & 0x40000000) != 0 )
      --Context2[25];
    if ( Context2[23] && (Context2[18] & 0x400) == 0 || (v10 = Context2[18], (v10 & 4) != 0) )
    {
LABEL_23:
      Fobx->FobxSerialNumber |= 0x1000000u;
      goto LABEL_24;
    }
    if ( (v10 & 8) != 0 )
    {
      _InterlockedDecrement((volatile signed __int32 *)&pFcb[1].Header.PagingIoResource + 1);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          24,
          &WPP_36817ce08eb83f0e99a0e799ed379106_Traceguids,
          HIDWORD(pFcb[1].Header.PagingIoResource));
      }
    }
    RxClearDirectExtents((__int64)Context2, (__int64)pFcb);
    if ( *(_QWORD *)(v9->pFcb[2].Header.ValidDataLength.QuadPart + 112) )
    {
      if ( ((__int64)v9->ScavengerEntry.List.Flink & 2) != 0 )
      {
        v3 = -1073741536;
      }
      else
      {
        *(_OWORD *)&v9->MRxContext[2] = 0;
        *(_OWORD *)&v9->WriteOnlyOpenRetryContext = 0;
        v9->ResumeRoutine = 0;
        v3 = (*(__int64 (__fastcall **)(PRX_CONTEXT))(v9->pFcb[2].Header.ValidDataLength.QuadPart + 112))(v9);
        if ( v3 >= 0 )
        {
LABEL_19:
          Context2[18] |= 4u;
          if ( (Context2[18] & 8) != 0 )
          {
            _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)(*(_QWORD *)&pFcb->UncleanCount + 32LL) + 232LL));
            Context2[18] &= ~8u;
          }
          RxRemoveShareAccess(*((_QWORD *)Context2 + 4) + 452LL, Context2[30], Context2[31]);
          RxRemoveOplockStateForSrvOpen(Context2);
          RxUpdateFcbLocalCachingState(pFcb);
          v13 = (Context2[18] & 0x100) == 0;
          DiscardedRequests = 0;
          if ( !v13 )
          {
            v16 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)Context2 + 5) + 32LL) + 32LL);
            DiscardedRequests.Blink = &DiscardedRequests;
            DiscardedRequests.Flink = &DiscardedRequests;
            ExAcquireFastMutex((PFAST_MUTEX)(v16 + 520));
            RxGatherRequestsForSrvOpen((PSRV_CALL)Context2, (PSRV_OPEN)&DiscardedRequests, v17);
            v18 = Context2 + 52;
            v19 = *((_QWORD *)Context2 + 26);
            if ( *(unsigned int **)(v19 + 8) != Context2 + 52
              || (v20 = (_QWORD *)*((_QWORD *)Context2 + 27), (_QWORD *)*v20 != v18) )
            {
              __fastfail(3u);
            }
            *v20 = v19;
            *(_QWORD *)(v19 + 8) = v20;
            *((_QWORD *)Context2 + 27) = Context2 + 52;
            *v18 = v18;
            Context2[18] &= ~0x100u;
            ExReleaseFastMutex((PFAST_MUTEX)(v16 + 520));
            Flink = DiscardedRequests.Flink;
            if ( DiscardedRequests.Flink != &DiscardedRequests )
            {
              do
              {
                RxDecrementOutstandingBufferingChangesOnFcb(*((_QWORD *)Context2 + 4));
                Flink = Flink->Flink;
              }
              while ( Flink != &DiscardedRequests );
              RxpDiscardChangeBufferingStateRequests(&DiscardedRequests);
            }
          }
          RxDereference(Context2, LHS_ExclusiveLockHeld);
          goto LABEL_23;
        }
      }
    }
    else
    {
      v3 = -1073741822;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_LqqZ(
        WPP_GLOBAL_Control->AttachedDevice,
        v11,
        v12,
        v3,
        (char)pFcb,
        (char)Context2,
        *((_QWORD *)Context2 + 10));
    }
    goto LABEL_19;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_qqq(
      WPP_GLOBAL_Control->AttachedDevice,
      23,
      &WPP_36817ce08eb83f0e99a0e799ed379106_Traceguids,
      Fobx,
      Fobx->Context2,
      pFcb);
  }
  v3 = -1073741670;
LABEL_30:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 27, &WPP_36817ce08eb83f0e99a0e799ed379106_Traceguids, (unsigned int)v3);
  }
  return v3;
}

```

## disassembly

```asm
0x140057a80  push    rbx
0x140057a82  push    rbp
0x140057a83  push    rsi
0x140057a84  push    rdi
0x140057a85  push    r12
0x140057a87  push    r13
0x140057a89  push    r14
0x140057a8b  push    r15
0x140057a8d  sub     rsp, 58h
0x140057a91  xor     r14d, r14d
0x140057a94  lea     r13, WPP_GLOBAL_Control
0x140057a9b  mov     rdi, rdx
0x140057a9e  mov     r15, rcx
0x140057aa1  test    rdx, rdx
0x140057aa4  jz      loc_140057DFD
0x140057aaa  mov     ecx, [rdx+48h]
0x140057aad  bt      ecx, 18h
0x140057ab1  jb      loc_140057C55
0x140057ab7  mov     rbx, [rdx+20h]
0x140057abb  mov     eax, [rbx+48h]
0x140057abe  test    al, 4
0x140057ac0  jnz     loc_140057E12
0x140057ac6  mov     rsi, [rbx+20h]
0x140057aca  mov     rcx, cs:WPP_GLOBAL_Control
0x140057ad1  mov     rbp, r15
0x140057ad4  cmp     rcx, r13
0x140057ad7  jz      short loc_140057AE4
0x140057ad9  mov     eax, [rcx+2Ch]
0x140057adc  test    al, 8
0x140057ade  jnz     loc_140057E33
0x140057ae4  test    r15, r15
0x140057ae7  jz      loc_140057C81
0x140057aed  test    rdi, rdi
0x140057af0  jz      loc_140057E9F
0x140057af6  test    rbx, rbx
0x140057af9  jz      loc_140057D24
0x140057aff  cmp     dword ptr [rbx+0A4h], 3
0x140057b06  jnz     loc_140057D14
0x140057b0c  lock dec dword ptr [rbx+5Ch]
0x140057b10  test    dword ptr [rdi+48h], 40000000h
0x140057b17  jz      short loc_140057B1C
0x140057b19  dec     dword ptr [rbx+64h]
0x140057b1c  cmp     [rbx+5Ch], r14d
0x140057b20  jnz     loc_140057D30
0x140057b26  mov     eax, [rbx+48h]
0x140057b29  test    al, 4
0x140057b2b  jnz     loc_140057C0A
0x140057b31  test    al, 8
0x140057b33  jnz     loc_140057CC7
0x140057b39  mov     rdx, rsi
0x140057b3c  mov     rcx, rbx
0x140057b3f  call    RxClearDirectExtents
0x140057b44  mov     rax, [rbp+38h]
0x140057b48  mov     rcx, [rax+188h]
0x140057b4f  cmp     [rcx+70h], r14
0x140057b53  jz      loc_140057EAB
0x140057b59  mov     eax, [rbp+80h]
0x140057b5f  test    al, 2
0x140057b61  jnz     loc_140057D42
0x140057b67  xor     eax, eax
0x140057b69  xorps   xmm0, xmm0
0x140057b6c  movups  xmmword ptr [rbp+0D0h], xmm0
0x140057b73  movups  xmmword ptr [rbp+0E0h], xmm0
0x140057b7a  mov     [rbp+0F0h], rax
0x140057b81  mov     rax, [rbp+38h]
0x140057b85  mov     rcx, [rax+188h]
0x140057b8c  mov     rax, [rcx+70h]
0x140057b90  mov     rcx, rbp
0x140057b93  call    _guard_dispatch_icall
0x140057b98  mov     r14d, eax
0x140057b9b  test    eax, eax
0x140057b9d  js      loc_140057EB1
0x140057ba3  or      dword ptr [rbx+48h], 4
0x140057ba7  mov     eax, [rbx+48h]
0x140057baa  test    al, 8
0x140057bac  jz      short loc_140057BC1
0x140057bae  mov     rax, [rsi+78h]
0x140057bb2  mov     rcx, [rax+20h]
0x140057bb6  lock dec dword ptr [rcx+0E8h]
0x140057bbd  and     dword ptr [rbx+48h], 0FFFFFFF7h
0x140057bc1  mov     rcx, [rbx+20h]
0x140057bc5  mov     r8d, [rbx+7Ch]
0x140057bc9  add     rcx, 1C4h
0x140057bd0  mov     edx, [rbx+78h]
0x140057bd3  call    RxRemoveShareAccess
0x140057bd8  mov     rcx, rbx
0x140057bdb  call    RxRemoveOplockStateForSrvOpen
0x140057be0  mov     rcx, rsi
0x140057be3  call    RxUpdateFcbLocalCachingState
0x140057be8  test    dword ptr [rbx+48h], 100h
0x140057bef  xorps   xmm0, xmm0
0x140057bf2  movups  xmmword ptr [rsp+98h+DiscardedRequests.Flink], xmm0
0x140057bf7  jnz     loc_140057D4D
0x140057bfd  mov     edx, 2; LockHoldingState
0x140057c02  mov     rcx, rbx; Instance
0x140057c05  call    RxDereference
0x140057c0a  or      dword ptr [rdi+48h], 1000000h
0x140057c11  mov     eax, [rsi+0C4h]
0x140057c17  add     eax, [rsi+0C0h]
0x140057c1d  jnz     short loc_140057C48
0x140057c1f  mov     rcx, cs:WPP_GLOBAL_Control
0x140057c26  cmp     rcx, r13
0x140057c29  jz      short loc_140057C36
0x140057c2b  mov     eax, [rcx+2Ch]
0x140057c2e  test    al, 8
0x140057c30  jnz     loc_140057EFA
0x140057c36  and     dword ptr [rsi+9Ch], 0FFFBFFFFh
0x140057c40  mov     rcx, rsi; Instance
0x140057c43  call    RxDeregisterFcbWithBufferingManager
0x140057c48  cmp     rbp, r15
0x140057c4b  jz      short loc_140057C55
0x140057c4d  mov     rcx, rbp; RxContext
0x140057c50  call    RxDereferenceAndDeleteRxContext_Real
0x140057c55  mov     rcx, cs:WPP_GLOBAL_Control
0x140057c5c  cmp     rcx, r13
0x140057c5f  jz      short loc_140057C6C
0x140057c61  mov     eax, [rcx+2Ch]
0x140057c64  test    al, 8
0x140057c66  jnz     loc_140057F21
0x140057c6c  mov     eax, r14d
0x140057c6f  add     rsp, 58h
0x140057c73  pop     r15
0x140057c75  pop     r14
0x140057c77  pop     r13
0x140057c79  pop     r12
0x140057c7b  pop     rdi
0x140057c7c  pop     rsi
0x140057c7d  pop     rbp
0x140057c7e  pop     rbx
0x140057c7f  retn
0x140057c81  mov     rdx, [rbx+20h]
0x140057c85  mov     r8d, 2; InitialContextFlags
0x140057c8b  xor     ecx, ecx; Irp
0x140057c8d  mov     rdx, [rdx+190h]; RxDeviceObject
0x140057c94  call    RxCreateRxContext
0x140057c99  mov     rbp, rax
0x140057c9c  test    rax, rax
0x140057c9f  jz      loc_140057E4E
0x140057ca5  mov     byte ptr [rax+20h], 2
0x140057ca9  mov     [rax+38h], rsi
0x140057cad  mov     [rax+40h], rdi
0x140057cb1  test    rdi, rdi
0x140057cb4  jz      loc_140057E9F
0x140057cba  mov     rax, [rdi+20h]
0x140057cbe  mov     [rbp+48h], rax
0x140057cc2  jmp     loc_140057AF6
0x140057cc7  lock dec dword ptr [rsi+0C4h]
0x140057cce  mov     rcx, cs:WPP_GLOBAL_Control
0x140057cd5  cmp     rcx, r13
0x140057cd8  jz      loc_140057B39
0x140057cde  mov     eax, [rcx+2Ch]
0x140057ce1  test    al, 8
0x140057ce3  jz      loc_140057B39
0x140057ce9  cmp     byte ptr [rcx+29h], 2
0x140057ced  jb      loc_140057B39
0x140057cf3  mov     r9d, [rsi+0C4h]
0x140057cfa  lea     r8, WPP_36817ce08eb83f0e99a0e799ed379106_Traceguids
0x140057d01  mov     rcx, [rcx+18h]
0x140057d05  mov     edx, 18h
0x140057d0a  call    WPP_SF_d
0x140057d0f  jmp     loc_140057B39
0x140057d14  mov     rdx, rsi
0x140057d17  mov     rcx, rbx
0x140057d1a  call    RxClearDirectExtents
0x140057d1f  jmp     loc_140057C11
0x140057d24  lock dec dword ptr [rsi+98h]
0x140057d2b  jmp     loc_140057C48
0x140057d30  test    dword ptr [rbx+48h], 400h
0x140057d37  jz      loc_140057C0A
0x140057d3d  jmp     loc_140057B26
0x140057d42  mov     r14d, 0C0000120h
0x140057d48  jmp     loc_140057EB1
0x140057d4d  mov     rax, [rbx+28h]
0x140057d51  mov     rcx, [rax+20h]
0x140057d55  mov     r12, [rcx+20h]
0x140057d59  lea     rcx, [rsp+98h+DiscardedRequests]
0x140057d5e  mov     [rsp+98h+DiscardedRequests.Blink], rcx
0x140057d63  lea     rcx, [rsp+98h+DiscardedRequests]
0x140057d68  mov     [rsp+98h+DiscardedRequests.Flink], rcx
0x140057d6d  lea     rcx, [r12+208h]; FastMutex
0x140057d75  call    cs:__imp_ExAcquireFastMutex
0x140057d7c  nop     dword ptr [rax+rax+00h]
0x140057d81  lea     rdx, [rsp+98h+DiscardedRequests]; SrvOpen
0x140057d86  mov     rcx, rbx; SrvCall
0x140057d89  call    RxGatherRequestsForSrvOpen
0x140057d8e  lea     rax, [rbx+0D0h]
0x140057d95  mov     r8, [rax]
0x140057d98  cmp     [r8+8], rax
0x140057d9c  jnz     short loc_140057DF6
0x140057d9e  mov     rdx, [rax+8]
0x140057da2  cmp     [rdx], rax
0x140057da5  jnz     short loc_140057DF6
0x140057da7  mov     [rdx], r8
0x140057daa  lea     rcx, [r12+208h]; FastMutex
0x140057db2  mov     [r8+8], rdx
0x140057db6  mov     [rax+8], rax
0x140057dba  mov     [rax], rax
0x140057dbd  and     dword ptr [rbx+48h], 0FFFFFEFFh
0x140057dc4  call    cs:__imp_ExReleaseFastMutex
0x140057dcb  nop     dword ptr [rax+rax+00h]
0x140057dd0  mov     r12, [rsp+98h+DiscardedRequests.Flink]
0x140057dd5  lea     rax, [rsp+98h+DiscardedRequests]
0x140057dda  cmp     r12, rax
0x140057ddd  jz      loc_140057BFD
0x140057de3  lea     rax, [rsp+98h+DiscardedRequests]
0x140057de8  cmp     r12, rax
0x140057deb  jnz     loc_14007CBFA
0x140057df1  jmp     loc_14007CC11
0x140057df6  mov     ecx, 3
0x140057dfb  int     29h; Win8: RtlFailFast(ecx)
0x140057dfd  test    r15, r15
0x140057e00  jz      loc_140057C55
0x140057e06  mov     rsi, [rcx+38h]
0x140057e0a  mov     rbx, r14
0x140057e0d  jmp     loc_140057ACA
0x140057e12  bts     ecx, 18h
0x140057e16  mov     [rdx+48h], ecx
0x140057e19  lock dec dword ptr [rbx+5Ch]
0x140057e1d  test    dword ptr [rdx+48h], 40000000h
0x140057e24  jz      loc_140057C55
0x140057e2a  lock dec dword ptr [rbx+64h]
0x140057e2e  jmp     loc_140057C55
0x140057e33  cmp     byte ptr [rcx+29h], 2
0x140057e37  jb      loc_140057AE4
0x140057e3d  test    rbx, rbx
0x140057e40  jz      loc_14007CBB6
0x140057e46  mov     edx, [rbx+5Ch]
0x140057e49  jmp     loc_14007CBBB
0x140057e4e  mov     rcx, cs:WPP_GLOBAL_Control
0x140057e55  cmp     rcx, r13
0x140057e58  jz      loc_14007CBEF
0x140057e5e  mov     eax, [rcx+2Ch]
0x140057e61  test    al, 1
0x140057e63  jz      loc_14007CBEF
0x140057e69  cmp     byte ptr [rcx+29h], 1
0x140057e6d  jb      loc_14007CBEF
0x140057e73  mov     rax, [rdi+20h]
0x140057e77  lea     r8, WPP_36817ce08eb83f0e99a0e799ed379106_Traceguids
0x140057e7e  mov     rcx, [rcx+18h]
0x140057e82  mov     edx, 17h
0x140057e87  mov     [rsp+98h+var_70], rsi
0x140057e8c  mov     r9, rdi
0x140057e8f  mov     [rsp+98h+var_78], rax
0x140057e94  call    WPP_SF_qqq
0x140057e99  nop
0x140057e9a  jmp     loc_14007CBEF
0x140057e9f  lock dec dword ptr [rsi+0C0h]
0x140057ea6  jmp     loc_140057AF6
0x140057eab  mov     r14d, 0C0000002h
0x140057eb1  mov     rcx, cs:WPP_GLOBAL_Control
0x140057eb8  cmp     rcx, r13
0x140057ebb  jz      loc_140057BA3
0x140057ec1  mov     eax, [rcx+2Ch]
0x140057ec4  test    al, 1
0x140057ec6  jz      loc_140057BA3
0x140057ecc  cmp     byte ptr [rcx+29h], 1
0x140057ed0  jb      loc_140057BA3
0x140057ed6  mov     rax, [rbx+50h]
0x140057eda  mov     r9d, r14d
0x140057edd  mov     rcx, [rcx+18h]
0x140057ee1  mov     [rsp+98h+var_68], rax
0x140057ee6  mov     [rsp+98h+var_70], rbx
0x140057eeb  mov     [rsp+98h+var_78], rsi
0x140057ef0  call    WPP_SF_LqqZ
0x140057ef5  jmp     loc_140057BA3
0x140057efa  cmp     byte ptr [rcx+29h], 2
0x140057efe  jb      loc_140057C36
0x140057f04  mov     rcx, [rcx+18h]
0x140057f08  lea     r8, WPP_36817ce08eb83f0e99a0e799ed379106_Traceguids
0x140057f0f  mov     edx, 1Ah
0x140057f14  mov     r9, rsi
0x140057f17  call    WPP_SF_q
0x140057f1c  jmp     loc_140057C36
0x140057f21  cmp     byte ptr [rcx+29h], 2
0x140057f25  jb      loc_140057C6C
0x140057f2b  mov     rcx, [rcx+18h]
0x140057f2f  lea     r8, WPP_36817ce08eb83f0e99a0e799ed379106_Traceguids
0x140057f36  mov     edx, 1Bh
0x140057f3b  mov     r9d, r14d
0x140057f3e  call    WPP_SF_d
0x140057f43  jmp     loc_140057C6C
0x14007cbb6  mov     edx, 0FFFFFFFFh
0x14007cbbb  test    rsi, rsi
0x14007cbbe  jz      short loc_14007CBC8
0x14007cbc0  mov     eax, [rsi+0C0h]
0x14007cbc6  jmp     short loc_14007CBCB
0x14007cbc8  mov     eax, r14d
0x14007cbcb  mov     rcx, [rcx+18h]
0x14007cbcf  mov     r9, rsi
0x14007cbd2  mov     [rsp+98h+var_60], rdi
0x14007cbd7  mov     dword ptr [rsp+98h+var_68], edx
0x14007cbdb  mov     [rsp+98h+var_70], rbx
0x14007cbe0  mov     dword ptr [rsp+98h+var_78], eax
0x14007cbe4  call    WPP_SF_qdqdq
0x14007cbe9  nop
0x14007cbea  jmp     loc_140057AE4
0x14007cbef  mov     r14d, 0C000009Ah
0x14007cbf5  jmp     loc_140057C55
0x14007cbfa  mov     rcx, [rbx+20h]
0x14007cbfe  call    RxDecrementOutstandingBufferingChangesOnFcb
  ... truncated ...
```
