# MRxDAVDevFcbXXXControlFile

- ea: `0x14000f120`
- end: `0x14000f76b`
- name: `MRxDAVDevFcbXXXControlFile`
- size: `1611`
- prototype: `__int64 __fastcall(PRX_CONTEXT RxContext, int, int)`
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation`

## callees

- `0x140001290`
- `0x1400015f0`
- `0x14000163c`
- `0x140001680`
- `0x140001770`
- `0x1400017e4`
- `0x1400062b0`
- `0x14000f120`
- `0x14000fde4`
- `0x140010168`
- `0x14001046c`
- `0x140010554`
- `0x1400262c4`
- `0x1400269d8`
- `0x140028510`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x14000f17c`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14000f1bc`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14000f20c`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14000f27d`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14000f30e`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14000f48a`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14000f549`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14000f5ca`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14000f72c`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14000f17c`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14000f1bc`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14000f20c`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14000f27d`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14000f30e`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14000f48a`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14000f549`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14000f5ca`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14000f72c`
- `ntoskrnl!IoGetRequestorProcess` at `0x14000f6f9`
- `ntoskrnl!IoGetRequestorProcess` at `0x14000f6f9`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000f456`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000f456`

## pseudocode

```c
__int64 __fastcall MRxDAVDevFcbXXXControlFile(PRX_CONTEXT RxContext, int a2, int a3)
{
  PNON_PAGED_FCB NonPagedFcb; // rsi
  PMRX_FOBX pFobx; // r14
  int RealDevice_low; // r13d
  int v7; // r12d
  int v8; // r15d
  __int64 v9; // rbx
  HANDLE CurrentThreadId; // rax
  __int64 v11; // rbx
  HANDLE v12; // rax
  __int64 v13; // rsi
  HANDLE v14; // rax
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // rbx
  HANDLE v18; // rax
  NTSTATUS Status; // edi
  __int64 v20; // rbx
  HANDLE v21; // rax
  __int64 v22; // rdx
  int IsCallerPrivileged; // eax
  __int64 v24; // r8
  _QWORD *v25; // rcx
  __int64 v26; // rdx
  __int64 v27; // rcx
  PIRP CurrentIrp; // rax
  PVOID MappedSystemVa; // r9
  PMDL MdlAddress; // rcx
  __int64 v31; // rbx
  HANDLE v32; // rax
  __int64 v33; // rdi
  HANDLE v34; // rax
  __int64 v36; // rbx
  HANDLE v37; // rax
  struct _NON_PAGED_FCB *v38; // [rsp+90h] [rbp+8h]

  NonPagedFcb = RxContext->NonPagedFcb;
  pFobx = RxContext->pFobx;
  RealDevice_low = LOBYTE(RxContext->RealDevice);
  v7 = *((unsigned __int8 *)&RxContext->9 + 176);
  v8 = *((_DWORD *)&RxContext->9 + 35);
  v38 = NonPagedFcb;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
    {
      v9 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      CurrentThreadId = PsGetCurrentThreadId();
      WPP_SF_q(v9, 10, WPP_c9ea18f8c0d9351c3b8fa09e3aa5b77e_Traceguids, CurrentThreadId);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
      {
        v11 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v12 = PsGetCurrentThreadId();
        WPP_SF_qq(v11, 11, WPP_c9ea18f8c0d9351c3b8fa09e3aa5b77e_Traceguids, v12, RxContext);
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
      {
        v13 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v14 = PsGetCurrentThreadId();
        WPP_SF_qddL(v13, v15, v16, v14, RealDevice_low, v7, v8);
        NonPagedFcb = v38;
      }
    }
  }
  if ( RealDevice_low == 13 )
  {
    if ( (_BYTE)v7 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
      {
        v33 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v34 = PsGetCurrentThreadId();
        WPP_SF_qD(v33, 16, WPP_c9ea18f8c0d9351c3b8fa09e3aa5b77e_Traceguids, v34, v7);
      }
    }
    else
    {
      switch ( v8 )
      {
        case 1311628:
          IsCallerPrivileged = MRxDavIsCallerPrivileged();
          Status = IsCallerPrivileged;
          if ( IsCallerPrivileged < 0 )
          {
            v25 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
              goto LABEL_93;
            if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x1000) != 0 )
            {
              v26 = 13;
              goto LABEL_30;
            }
            goto LABEL_90;
          }
          if ( !pFobx )
          {
            Status = MRxDAVOuterStart(RxContext);
            if ( Status >= 0 )
              MRxDAVWebclientProcess = (__int64)IoGetRequestorProcess(RxContext->CurrentIrp);
            goto LABEL_90;
          }
          break;
        case 1311632:
          IsCallerPrivileged = MRxDavIsCallerPrivileged();
          Status = IsCallerPrivileged;
          if ( IsCallerPrivileged < 0 )
          {
            v25 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
              goto LABEL_93;
            if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x1000) != 0 )
            {
              v26 = 14;
              goto LABEL_30;
            }
            goto LABEL_90;
          }
          if ( !pFobx )
          {
            if ( LODWORD(RxContext->NonPagedFcb->BufferedLocksResource.ExclusiveWaiters) )
              return 2147483683LL;
            Status = MRxDAVOuterStop(RxContext);
            if ( Status >= 0 )
              MRxDAVWebclientProcess = 0;
            goto LABEL_90;
          }
          break;
        case 67108896:
          if ( pFobx )
          {
            Status = MRxDavDeleteConnection(RxContext);
            goto LABEL_90;
          }
          break;
        case 67108992:
          Status = UMRxAsyncEngOuterWrapper(
                     (_DWORD)RxContext,
                     a2,
                     a3,
                     17,
                     (__int64)MRxDAVFsCtlContinuation,
                     (__int64)"MRxDAVDevFcbXXXControlFile");
          if ( Status < 0 )
            RxContext->InformationToReturn = 0;
          goto LABEL_90;
        default:
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) == 0 )
          {
            goto LABEL_15;
          }
          v20 = *((_QWORD *)WPP_GLOBAL_Control + 3);
          v21 = PsGetCurrentThreadId();
          v22 = 15;
          goto LABEL_69;
      }
    }
    Status = -1073741808;
    goto LABEL_90;
  }
  if ( (unsigned int)(RealDevice_low - 14) >= 2 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    {
      v17 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v18 = PsGetCurrentThreadId();
      WPP_SF_qD(v17, 23, WPP_c9ea18f8c0d9351c3b8fa09e3aa5b77e_Traceguids, v18, RealDevice_low);
    }
    goto LABEL_15;
  }
  switch ( v8 )
  {
    case 1311608:
      IsCallerPrivileged = MRxDavIsCallerPrivileged();
      Status = IsCallerPrivileged;
      if ( IsCallerPrivileged >= 0 )
      {
        UMRxReleaseCapturedThreads(NonPagedFcb);
        goto LABEL_32;
      }
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        goto LABEL_93;
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x1000) != 0 )
      {
        v26 = 17;
        goto LABEL_30;
      }
      goto LABEL_90;
    case 1311614:
    case 1311618:
    case 1311622:
      IsCallerPrivileged = MRxDavIsCallerPrivileged();
      Status = IsCallerPrivileged;
      if ( IsCallerPrivileged >= 0 )
      {
        MappedSystemVa = 0;
        MdlAddress = RxContext->CurrentIrp->MdlAddress;
        if ( !MdlAddress
          || ((MdlAddress->MdlFlags & 5) == 0
            ? (MappedSystemVa = MmMapLockedPagesSpecifyCache(MdlAddress, 0, MmCached, 0, 0, 0x40000000u))
            : (MappedSystemVa = MdlAddress->MappedSystemVa),
              MappedSystemVa) )
        {
          UMRxAssignWork(
            NonPagedFcb,
            RxContext->CurrentIrp->AssociatedIrp.MasterIrp,
            RxContext->CurrentIrpSp->Parameters.Create.Options,
            MappedSystemVa,
            RxContext->CurrentIrpSp->Parameters.Read.Length,
            &RxContext->CurrentIrp->IoStatus);
          Status = RxContext->CurrentIrp->IoStatus.Status;
        }
        else
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
          {
            v31 = *((_QWORD *)WPP_GLOBAL_Control + 3);
            v32 = PsGetCurrentThreadId();
            WPP_SF_q(v31, 20, WPP_c9ea18f8c0d9351c3b8fa09e3aa5b77e_Traceguids, v32);
          }
          Status = -1073741670;
        }
        goto LABEL_90;
      }
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        goto LABEL_93;
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x1000) != 0 )
      {
        v26 = 19;
        goto LABEL_30;
      }
LABEL_90:
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
      {
        v36 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v37 = PsGetCurrentThreadId();
        WPP_SF_qD(v36, 24, WPP_c9ea18f8c0d9351c3b8fa09e3aa5b77e_Traceguids, v37, Status);
      }
      goto LABEL_93;
    case 1311624:
      IsCallerPrivileged = MRxDavIsCallerPrivileged();
      Status = IsCallerPrivileged;
      if ( IsCallerPrivileged >= 0 )
      {
        MRxDAVGetLockOwnerFromFileName(
          v27,
          RxContext->CurrentIrp->AssociatedIrp.MasterIrp,
          RxContext->CurrentIrpSp->Parameters.Create.Options,
          RxContext->CurrentIrp->AssociatedIrp.MasterIrp,
          RxContext->CurrentIrpSp->Parameters.Read.Length,
          &RxContext->CurrentIrp->IoStatus);
        CurrentIrp = RxContext->CurrentIrp;
        Status = CurrentIrp->IoStatus.Status;
        RxContext->InformationToReturn = CurrentIrp->IoStatus.Information;
      }
      else
      {
        v25 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          goto LABEL_93;
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x1000) != 0 )
        {
          v26 = 21;
LABEL_30:
          WPP_SF_d(v25[3], v26, v24, (unsigned int)IsCallerPrivileged);
          goto LABEL_90;
        }
      }
      goto LABEL_90;
  }
  if ( v8 != 1311636 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) == 0 )
      goto LABEL_15;
    v20 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v21 = PsGetCurrentThreadId();
    v22 = 22;
LABEL_69:
    WPP_SF_qD(v20, v22, WPP_c9ea18f8c0d9351c3b8fa09e3aa5b77e_Traceguids, v21, v8);
LABEL_15:
    Status = -1073741808;
    goto LABEL_90;
  }
  IsCallerPrivileged = MRxDavIsCallerPrivileged();
  Status = IsCallerPrivileged;
  if ( IsCallerPrivileged >= 0 )
  {
    UMRxPrepareWorkerQueue(NonPagedFcb);
LABEL_32:
    Status = 0;
    RxContext->CurrentIrp->IoStatus.Status = 0;
    RxContext->CurrentIrp->IoStatus.Information = 0;
    goto LABEL_90;
  }
  v25 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x1000) == 0 )
      goto LABEL_90;
    v26 = 18;
    goto LABEL_30;
  }
LABEL_93:
  RxContext->pFobx = 0;
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x14000f120  push    rbx
0x14000f122  push    rbp
0x14000f123  push    rsi
0x14000f124  push    rdi
0x14000f125  push    r12
0x14000f127  push    r13
0x14000f129  push    r14
0x14000f12b  push    r15
0x14000f12d  sub     rsp, 48h
0x14000f131  mov     rsi, [rcx+50h]
0x14000f135  mov     rbp, rcx
0x14000f138  mov     r14, [rcx+40h]
0x14000f13c  movzx   r13d, byte ptr [rcx+20h]
0x14000f141  movzx   r12d, byte ptr [rcx+240h]
0x14000f149  mov     r15d, [rcx+21Ch]
0x14000f150  mov     [rsp+88h+arg_0], rsi
0x14000f158  mov     rbx, cs:WPP_GLOBAL_Control
0x14000f15f  lea     rdi, WPP_GLOBAL_Control
0x14000f166  cmp     rbx, rdi
0x14000f169  jz      loc_14000F23A
0x14000f16f  test    dword ptr [rbx+2Ch], 4000h
0x14000f176  jz      short loc_14000F19F
0x14000f178  mov     rbx, [rbx+18h]
0x14000f17c  call    cs:__imp_PsGetCurrentThreadId
0x14000f183  nop     dword ptr [rax+rax+00h]
0x14000f188  mov     edx, 0Ah
0x14000f18d  lea     r8, WPP_c9ea18f8c0d9351c3b8fa09e3aa5b77e_Traceguids
0x14000f194  mov     r9, rax
0x14000f197  mov     rcx, rbx
0x14000f19a  call    WPP_SF_q
0x14000f19f  mov     rbx, cs:WPP_GLOBAL_Control
0x14000f1a6  cmp     rbx, rdi
0x14000f1a9  jz      loc_14000F23A
0x14000f1af  test    dword ptr [rbx+2Ch], 2000h
0x14000f1b6  jz      short loc_14000F1E4
0x14000f1b8  mov     rbx, [rbx+18h]
0x14000f1bc  call    cs:__imp_PsGetCurrentThreadId
0x14000f1c3  nop     dword ptr [rax+rax+00h]
0x14000f1c8  mov     edx, 0Bh
0x14000f1cd  mov     qword ptr [rsp+88h+BugCheckOnFailure], rbp
0x14000f1d2  mov     r9, rax
0x14000f1d5  lea     r8, WPP_c9ea18f8c0d9351c3b8fa09e3aa5b77e_Traceguids
0x14000f1dc  mov     rcx, rbx
0x14000f1df  call    WPP_SF_qq
0x14000f1e4  mov     rsi, cs:WPP_GLOBAL_Control
0x14000f1eb  lea     rbx, WPP_GLOBAL_Control
0x14000f1f2  cmp     rsi, rbx
0x14000f1f5  jz      loc_14000F2AD
0x14000f1fb  test    dword ptr [rsi+2Ch], 4000h
0x14000f202  jz      loc_14000F2AD
0x14000f208  mov     rsi, [rsi+18h]
0x14000f20c  call    cs:__imp_PsGetCurrentThreadId
0x14000f213  nop     dword ptr [rax+rax+00h]
0x14000f218  mov     [rsp+88h+var_58], r15d
0x14000f21d  mov     rcx, rsi
0x14000f220  mov     r9, rax
0x14000f223  mov     [rsp+88h+Priority], r12d
0x14000f228  mov     [rsp+88h+BugCheckOnFailure], r13d
0x14000f22d  call    WPP_SF_qddL
0x14000f232  mov     rsi, [rsp+88h+arg_0]
0x14000f23a  lea     rbx, WPP_GLOBAL_Control
0x14000f241  mov     ecx, r13d
0x14000f244  mov     edi, r13d
0x14000f247  xor     r13d, r13d
0x14000f24a  sub     ecx, 0Dh
0x14000f24d  jz      loc_14000F52B
0x14000f253  sub     ecx, 1
0x14000f256  jz      short loc_14000F2B7
0x14000f258  cmp     ecx, 1
0x14000f25b  jz      short loc_14000F2B7
0x14000f25d  mov     rbx, cs:WPP_GLOBAL_Control
0x14000f264  lea     rsi, WPP_GLOBAL_Control
0x14000f26b  cmp     rbx, rsi
0x14000f26e  jz      short loc_14000F2A3
0x14000f270  test    dword ptr [rbx+2Ch], 2000h
0x14000f277  jz      short loc_14000F2A3
0x14000f279  mov     rbx, [rbx+18h]
0x14000f27d  call    cs:__imp_PsGetCurrentThreadId
0x14000f284  nop     dword ptr [rax+rax+00h]
0x14000f289  lea     edx, [r13+17h]
0x14000f28d  mov     [rsp+88h+BugCheckOnFailure], edi
0x14000f291  mov     r9, rax
0x14000f294  lea     r8, WPP_c9ea18f8c0d9351c3b8fa09e3aa5b77e_Traceguids
0x14000f29b  mov     rcx, rbx
0x14000f29e  call    WPP_SF_qD
0x14000f2a3  mov     edi, 0C0000010h
0x14000f2a8  jmp     loc_14000F713
0x14000f2ad  mov     rsi, [rsp+88h+arg_0]
0x14000f2b5  jmp     short loc_14000F241
0x14000f2b7  mov     eax, r15d
0x14000f2ba  sub     eax, 140378h
0x14000f2bf  jz      loc_14000F4EC
0x14000f2c5  sub     eax, 6
0x14000f2c8  jz      loc_14000F3F1
0x14000f2ce  sub     eax, 4
0x14000f2d1  jz      loc_14000F3F1
0x14000f2d7  sub     eax, 4
0x14000f2da  jz      loc_14000F3F1
0x14000f2e0  sub     eax, 2
0x14000f2e3  jz      loc_14000F382
0x14000f2e9  cmp     eax, 0Ch
0x14000f2ec  jz      short loc_14000F324
0x14000f2ee  mov     rbx, cs:WPP_GLOBAL_Control
0x14000f2f5  lea     rsi, WPP_GLOBAL_Control
0x14000f2fc  cmp     rbx, rsi
0x14000f2ff  jz      short loc_14000F2A3
0x14000f301  test    dword ptr [rbx+2Ch], 2000h
0x14000f308  jz      short loc_14000F2A3
0x14000f30a  mov     rbx, [rbx+18h]
0x14000f30e  call    cs:__imp_PsGetCurrentThreadId
0x14000f315  nop     dword ptr [rax+rax+00h]
0x14000f31a  mov     edx, 16h
0x14000f31f  jmp     loc_14000F5DB
0x14000f324  call    MRxDavIsCallerPrivileged
0x14000f329  mov     edi, eax
0x14000f32b  test    eax, eax
0x14000f32d  jns     short loc_14000F362
0x14000f32f  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f336  cmp     rcx, rbx
0x14000f339  jz      loc_14000F753
0x14000f33f  test    dword ptr [rcx+2Ch], 1000h
0x14000f346  jz      loc_14000F70C
0x14000f34c  mov     edx, 12h
0x14000f351  mov     rcx, [rcx+18h]
0x14000f355  mov     r9d, eax
0x14000f358  call    WPP_SF_d
0x14000f35d  jmp     loc_14000F70C
0x14000f362  mov     rcx, rsi
0x14000f365  call    UMRxPrepareWorkerQueue
0x14000f36a  mov     rax, [rbp+28h]
0x14000f36e  mov     edi, r13d
0x14000f371  mov     [rax+30h], r13d
0x14000f375  mov     rax, [rbp+28h]
0x14000f379  mov     [rax+38h], r13
0x14000f37d  jmp     loc_14000F70C
0x14000f382  call    MRxDavIsCallerPrivileged
0x14000f387  mov     edi, eax
0x14000f389  test    eax, eax
0x14000f38b  jns     short loc_14000F3B1
0x14000f38d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f394  cmp     rcx, rbx
0x14000f397  jz      loc_14000F753
0x14000f39d  test    dword ptr [rcx+2Ch], 1000h
0x14000f3a4  jz      loc_14000F70C
0x14000f3aa  mov     edx, 15h
0x14000f3af  jmp     short loc_14000F351
0x14000f3b1  mov     rax, [rbp+28h]
0x14000f3b5  mov     r8, [rbp+30h]
0x14000f3b9  mov     rdx, [rax+18h]
0x14000f3bd  add     rax, 30h ; '0'
0x14000f3c1  mov     qword ptr [rsp+88h+Priority], rax
0x14000f3c6  mov     r9, rdx
0x14000f3c9  mov     eax, [r8+8]
0x14000f3cd  mov     r8d, [r8+10h]
0x14000f3d1  mov     [rsp+88h+BugCheckOnFailure], eax
0x14000f3d5  call    MRxDAVGetLockOwnerFromFileName
0x14000f3da  mov     rax, [rbp+28h]
0x14000f3de  mov     edi, [rax+30h]
0x14000f3e1  mov     rax, [rax+38h]
0x14000f3e5  mov     [rbp+0B8h], rax
0x14000f3ec  jmp     loc_14000F70C
0x14000f3f1  call    MRxDavIsCallerPrivileged
0x14000f3f6  mov     edi, eax
0x14000f3f8  test    eax, eax
0x14000f3fa  jns     short loc_14000F423
0x14000f3fc  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f403  cmp     rcx, rbx
0x14000f406  jz      loc_14000F753
0x14000f40c  test    dword ptr [rcx+2Ch], 1000h
0x14000f413  jz      loc_14000F70C
0x14000f419  mov     edx, 13h
0x14000f41e  jmp     loc_14000F351
0x14000f423  mov     rax, [rbp+28h]
0x14000f427  mov     r9, r13; RequestedAddress
0x14000f42a  mov     rcx, [rax+8]; MemoryDescriptorList
0x14000f42e  test    rcx, rcx
0x14000f431  jz      loc_14000F4B7
0x14000f437  test    byte ptr [rcx+0Ah], 5
0x14000f43b  jz      short loc_14000F443
0x14000f43d  mov     r9, [rcx+18h]
0x14000f441  jmp     short loc_14000F465
0x14000f443  xor     edx, edx; AccessMode
0x14000f445  mov     [rsp+88h+Priority], 40000000h; Priority
0x14000f44d  mov     [rsp+88h+BugCheckOnFailure], r13d; BugCheckOnFailure
0x14000f452  lea     r8d, [rdx+1]; CacheType
0x14000f456  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14000f45d  nop     dword ptr [rax+rax+00h]
0x14000f462  mov     r9, rax
0x14000f465  test    r9, r9
0x14000f468  jnz     short loc_14000F4B7
0x14000f46a  mov     rbx, cs:WPP_GLOBAL_Control
0x14000f471  lea     rsi, WPP_GLOBAL_Control
0x14000f478  cmp     rbx, rsi
0x14000f47b  jz      short loc_14000F4AD
0x14000f47d  test    dword ptr [rbx+2Ch], 2000h
0x14000f484  jz      short loc_14000F4AD
0x14000f486  mov     rbx, [rbx+18h]
0x14000f48a  call    cs:__imp_PsGetCurrentThreadId
0x14000f491  nop     dword ptr [rax+rax+00h]
0x14000f496  mov     edx, 14h
0x14000f49b  lea     r8, WPP_c9ea18f8c0d9351c3b8fa09e3aa5b77e_Traceguids
0x14000f4a2  mov     r9, rax
0x14000f4a5  mov     rcx, rbx
0x14000f4a8  call    WPP_SF_q
0x14000f4ad  mov     edi, 0C000009Ah
0x14000f4b2  jmp     loc_14000F713
0x14000f4b7  mov     rdx, [rbp+28h]
0x14000f4bb  mov     rcx, rsi
0x14000f4be  mov     r8, [rbp+30h]
0x14000f4c2  lea     rax, [rdx+30h]
0x14000f4c6  mov     rdx, [rdx+18h]
0x14000f4ca  mov     qword ptr [rsp+88h+Priority], rax
0x14000f4cf  mov     eax, [r8+8]
0x14000f4d3  mov     r8d, [r8+10h]
0x14000f4d7  mov     [rsp+88h+BugCheckOnFailure], eax
0x14000f4db  call    UMRxAssignWork
0x14000f4e0  mov     rax, [rbp+28h]
0x14000f4e4  mov     edi, [rax+30h]
0x14000f4e7  jmp     loc_14000F70C
0x14000f4ec  call    MRxDavIsCallerPrivileged
0x14000f4f1  mov     edi, eax
0x14000f4f3  test    eax, eax
0x14000f4f5  jns     short loc_14000F51E
0x14000f4f7  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f4fe  cmp     rcx, rbx
0x14000f501  jz      loc_14000F753
0x14000f507  test    dword ptr [rcx+2Ch], 1000h
0x14000f50e  jz      loc_14000F70C
0x14000f514  mov     edx, 11h
0x14000f519  jmp     loc_14000F351
0x14000f51e  mov     rcx, rsi
0x14000f521  call    UMRxReleaseCapturedThreads
0x14000f526  jmp     loc_14000F36A
0x14000f52b  test    r12b, r12b
0x14000f52e  jz      short loc_14000F57B
0x14000f530  mov     rdi, cs:WPP_GLOBAL_Control
0x14000f537  cmp     rdi, rbx
0x14000f53a  jz      short loc_14000F571
0x14000f53c  test    dword ptr [rdi+2Ch], 2000h
0x14000f543  jz      short loc_14000F571
0x14000f545  mov     rdi, [rdi+18h]
0x14000f549  call    cs:__imp_PsGetCurrentThreadId
0x14000f550  nop     dword ptr [rax+rax+00h]
0x14000f555  mov     edx, 10h
0x14000f55a  mov     [rsp+88h+BugCheckOnFailure], r12d
0x14000f55f  mov     r9, rax
0x14000f562  lea     r8, WPP_c9ea18f8c0d9351c3b8fa09e3aa5b77e_Traceguids
0x14000f569  mov     rcx, rdi
0x14000f56c  call    WPP_SF_qD
0x14000f571  mov     edi, 0C0000010h
0x14000f576  jmp     loc_14000F70C
0x14000f57b  mov     eax, r15d
0x14000f57e  sub     eax, 14038Ch
0x14000f583  jz      loc_14000F6B0
0x14000f589  sub     eax, 4
0x14000f58c  jz      loc_14000F640
0x14000f592  sub     eax, 3EBFC90h
0x14000f597  jz      loc_14000F628
0x14000f59d  cmp     eax, 60h ; '`'
0x14000f5a0  jz      short loc_14000F5E5
0x14000f5a2  mov     rbx, cs:WPP_GLOBAL_Control
0x14000f5a9  lea     rsi, WPP_GLOBAL_Control
0x14000f5b0  cmp     rbx, rsi
0x14000f5b3  jz      loc_14000F2A3
0x14000f5b9  test    dword ptr [rbx+2Ch], 2000h
0x14000f5c0  jz      loc_14000F2A3
0x14000f5c6  mov     rbx, [rbx+18h]
0x14000f5ca  call    cs:__imp_PsGetCurrentThreadId
0x14000f5d1  nop     dword ptr [rax+rax+00h]
0x14000f5d6  mov     edx, 0Fh
0x14000f5db  mov     [rsp+88h+BugCheckOnFailure], r15d
0x14000f5e0  jmp     loc_14000F291
0x14000f5e5  lea     rax, aMrxdavdevfcbxx; "MRxDAVDevFcbXXXControlFile"
0x14000f5ec  mov     r9d, 11h
0x14000f5f2  mov     qword ptr [rsp+88h+Priority], rax
0x14000f5f7  mov     rcx, rbp
0x14000f5fa  lea     rax, MRxDAVFsCtlContinuation
0x14000f601  mov     qword ptr [rsp+88h+BugCheckOnFailure], rax
0x14000f606  call    UMRxAsyncEngOuterWrapper
0x14000f60b  lea     rsi, WPP_GLOBAL_Control
0x14000f612  mov     edi, eax
0x14000f614  test    eax, eax
0x14000f616  jns     loc_14000F713
0x14000f61c  mov     [rbp+0B8h], r13
0x14000f623  jmp     loc_14000F713
0x14000f628  test    r14, r14
0x14000f62b  jz      loc_14000F571
0x14000f631  mov     rcx, rbp
0x14000f634  call    MRxDavDeleteConnection
0x14000f639  mov     edi, eax
0x14000f63b  jmp     loc_14000F70C
0x14000f640  call    MRxDavIsCallerPrivileged
0x14000f645  mov     edi, eax
0x14000f647  test    eax, eax
0x14000f649  jns     short loc_14000F672
0x14000f64b  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f652  cmp     rcx, rbx
0x14000f655  jz      loc_14000F753
0x14000f65b  test    dword ptr [rcx+2Ch], 1000h
0x14000f662  jz      loc_14000F70C
  ... truncated ...
```
