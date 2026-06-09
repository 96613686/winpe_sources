# RxpDereferenceAndFinalizeNetFcb

- ea: `0x140058540`
- end: `0x140058eeb`
- name: `RxpDereferenceAndFinalizeNetFcb`
- size: `2475`
- prototype: `BOOLEAN __stdcall(PFCB ThisFcb, PRX_CONTEXT RxContext, BOOLEAN RecursiveFinalize, BOOLEAN ForceFinalize)`
- caller_count: `14`
- callee_count: `13`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140001b70`
- `0x140008910`
- `0x14000d7c0`
- `0x14004dd60`
- `0x14004eb28`
- `0x140053400`
- `0x140054ca0`
- `0x140055950`
- `0x1400581a0`
- `0x14005e2b0`
- `0x14005e810`
- `0x1400649a0`
- `0x14006a520`
- `0x14006f9e0`

## callees

- `0x140009b80`
- `0x14000f180`
- `0x140014d10`
- `0x140014ec0`
- `0x140016e70`
- `0x140017370`
- `0x140022ccc`
- `0x140025d00`
- `0x140057660`
- `0x140058540`
- `0x140058f00`
- `0x140059660`
- `0x140059d10`

## import_xrefs

- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400587e9`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140058c8e`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400587e9`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140058c8e`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400586ff`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400586ff`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x1400587c9`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x1400587c9`
- `ntoskrnl!ExDeleteResourceLite` at `0x140058a53`
- `ntoskrnl!ExDeleteResourceLite` at `0x140058a63`
- `ntoskrnl!ExDeleteResourceLite` at `0x140058a53`
- `ntoskrnl!ExDeleteResourceLite` at `0x140058a63`
- `ntoskrnl!ExFreePoolWithTag` at `0x140058e46`
- `ntoskrnl!ExFreePoolWithTag` at `0x140058e46`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400588da`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400588da`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140058902`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140058902`
- `ntoskrnl!FsRtlUninitializeFileLock` at `0x140058c4a`
- `ntoskrnl!FsRtlUninitializeFileLock` at `0x140058c4a`
- `ntoskrnl!FsRtlUninitializeOplock` at `0x140058a73`
- `ntoskrnl!FsRtlUninitializeOplock` at `0x140058a73`
- `ntoskrnl!RtlRbRemoveNode` at `0x1400589b3`
- `ntoskrnl!RtlRbRemoveNode` at `0x1400589b3`
- `ntoskrnl!KeBugCheckEx` at `0x140058789`
- `ntoskrnl!KeBugCheckEx` at `0x140058bc1`
- `ntoskrnl!KeBugCheckEx` at `0x140058d65`
- `ntoskrnl!KeBugCheckEx` at `0x140058789`
- `ntoskrnl!KeBugCheckEx` at `0x140058bc1`
- `ntoskrnl!KeBugCheckEx` at `0x140058d65`
- `ntoskrnl!KeReleaseMutex` at `0x140058688`
- `ntoskrnl!KeReleaseMutex` at `0x140058688`
- `ntoskrnl!KeWaitForSingleObject` at `0x140058c26`
- `ntoskrnl!KeWaitForSingleObject` at `0x140058c26`

## pseudocode

```c
BOOLEAN __stdcall RxpDereferenceAndFinalizeNetFcb(
        PFCB ThisFcb,
        PRX_CONTEXT RxContext,
        BOOLEAN RecursiveFinalize,
        BOOLEAN ForceFinalize)
{
  unsigned __int16 *v4; // rsi
  PFCB v5; // rbx
  char v6; // r14
  signed __int64 v7; // rax
  signed __int64 v8; // rdi
  const CHAR *v9; // r9
  int v10; // edx
  unsigned int v11; // r8d
  __int64 v12; // rax
  _DWORD *v13; // rbp
  _DWORD *v14; // rbp
  unsigned __int16 *v15; // rdi
  __int64 v16; // rcx
  unsigned __int16 **v17; // rax
  BOOLEAN v18; // bp
  char v19; // r12
  unsigned int v20; // r13d
  __int64 v21; // r8
  signed __int32 v22; // edi
  void *v24; // r15
  ULONG v25; // r8d
  const CHAR *v26; // r9
  struct _FCB *v27; // rdx
  char v28; // cl
  __int64 v29; // rdi
  PMINIRDR_DISPATCH *p_MRxDispatch; // r14
  _QWORD *i; // rdx
  __int64 v32; // r9
  unsigned __int64 v33; // r8
  __int64 v34; // rsi
  __int64 v35; // rax
  __int64 v36; // rcx
  __int64 v37; // rax
  __int64 v38; // rax
  unsigned __int64 MRxFastIoDispatch; // r8
  _QWORD *v40; // r9
  unsigned __int64 v41; // rax
  PMINIRDR_DISPATCH **v42; // rcx
  const CHAR *BugCheckParameter4; // [rsp+20h] [rbp-68h]
  PCSTR BugCheckParameter4a; // [rsp+20h] [rbp-68h]
  ULONG v45; // [rsp+28h] [rbp-60h]
  int v46; // [rsp+30h] [rbp-58h]
  const CHAR *v47; // [rsp+38h] [rbp-50h]
  unsigned __int16 *v48; // [rsp+40h] [rbp-48h]
  struct _FCB *v49; // [rsp+48h] [rbp-40h]
  signed __int64 v50; // [rsp+90h] [rbp+8h]
  char v51; // [rsp+90h] [rbp+8h]

  v4 = (unsigned __int16 *)*((_QWORD *)&ThisFcb->1 + 15);
  v5 = ThisFcb;
  v48 = v4;
  v6 = 0;
  v7 = *(_QWORD *)v4;
  v50 = *(_QWORD *)v4;
  do
  {
    v8 = v7;
    if ( (v7 & 0x1000) != 0 )
    {
      LOWORD(v50) = v7 & 0xEFFF;
      if ( !v6 )
      {
        KeWaitForSingleObject(&RxScavengerMutex, Executive, 0, 0, 0);
        v6 = 1;
      }
    }
    else
    {
      HIDWORD(v50) = HIDWORD(v7) + 1;
    }
    v7 = _InterlockedCompareExchange64((volatile signed __int64 *)v4, v50, v8);
    v50 = v7;
  }
  while ( v8 != v7 );
  v9 = (const CHAR *)&WPP_GLOBAL_Control;
  if ( (v8 & 0x1000) == 0 )
    goto LABEL_16;
  v10 = *v4;
  v11 = v10 & 0xEFFF;
  if ( v11 != 60178 )
  {
    if ( v11 <= 0xEB1C )
    {
      switch ( v11 )
      {
        case 0xEB1Cu:
          v12 = *(_QWORD *)(*((_QWORD *)v4 + 4) + 400LL);
          goto LABEL_8;
        case 0xEB10u:
          v12 = *((_QWORD *)v4 + 6);
          goto LABEL_8;
        case 0xEB11u:
          v12 = *(_QWORD *)(*((_QWORD *)v4 + 4) + 48LL);
          goto LABEL_8;
        case 0xEB13u:
          v12 = *((_QWORD *)v4 + 10);
          goto LABEL_8;
      }
    }
    else
    {
      if ( v11 == 60449 || v11 == 60450 )
      {
        v12 = *((_QWORD *)v4 + 50);
        goto LABEL_8;
      }
      if ( v11 == 60464 )
      {
        v12 = *((_QWORD *)v4 + 31);
        goto LABEL_8;
      }
    }
    v12 = 0;
    goto LABEL_8;
  }
  v12 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v4 + 4) + 32LL) + 48LL);
LABEL_8:
  v13 = *(_DWORD **)(v12 + 832);
  switch ( v10 & 0xFFFFEFFF )
  {
    case 0xEB12u:
      v14 = v13 + 5;
      break;
    case 0xEB10u:
      v14 = v13 + 3;
      break;
    case 0xEB11u:
      v14 = v13 + 4;
      break;
    case 0xEB13u:
      v14 = v13 + 8;
      break;
    case 0xEB1Cu:
      v14 = v13 + 6;
      break;
    case 0xEC30u:
      v14 = v13 + 7;
      break;
    default:
      KeBugCheckEx(0x27u, 0x1021Cu, (ULONG_PTR)v4, *v4, 0);
  }
  v15 = v4 + 8;
  if ( *(unsigned __int16 **)v15 == v15 )
    KeBugCheckEx(0x27u, 0x10225u, (ULONG_PTR)v4, *v4, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    LODWORD(BugCheckParameter4) = *v4 & 0xEFFF;
    WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_7cd1a4145ac63a5107541aa80a8a6609_Traceguids, v4);
    v9 = (const CHAR *)&WPP_GLOBAL_Control;
  }
  _InterlockedAnd((volatile signed __int32 *)v4, 0xFFFFEFFF);
  --*v14;
  v16 = *(_QWORD *)v15;
  if ( *(unsigned __int16 **)(*(_QWORD *)v15 + 8LL) != v15
    || (v17 = (unsigned __int16 **)*((_QWORD *)v4 + 3), *v17 != v15) )
  {
    __fastfail(3u);
  }
  *v17 = (unsigned __int16 *)v16;
  *(_QWORD *)(v16 + 8) = v17;
  *((_QWORD *)v4 + 3) = v4 + 8;
  *(_QWORD *)v15 = v15;
LABEL_16:
  v18 = 0;
  v19 = 0;
  v20 = 0;
  v47 = (const CHAR *)v5;
  v46 = 0;
  v51 = 0;
  if ( v6 )
  {
    KeReleaseMutex(&RxScavengerMutex, 0);
    v9 = (const CHAR *)&WPP_GLOBAL_Control;
  }
  while ( 1 )
  {
    v21 = 60450;
    if ( !v5 )
      break;
    v22 = _InterlockedDecrement((volatile signed __int32 *)&v5->1 + 38);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qDD(
        WPP_GLOBAL_Control->AttachedDevice,
        17,
        WPP_e7aebc7caeed3866654dc8faf8a6aa71_Traceguids,
        v5,
        v5->ScavengerFinalizationList.Flink,
        v22);
      v9 = (const CHAR *)&WPP_GLOBAL_Control;
      v21 = 60450;
    }
    if ( v22 )
    {
      if ( v22 != 1 || (*((_DWORD *)&v5->1 + 39) & 0x10000000) != 0 )
        goto LABEL_23;
      v24 = (void *)*((_QWORD *)&v5->1 + 16);
    }
    else
    {
      v24 = (void *)*((_QWORD *)&v5->1 + 16);
      if ( (*((_DWORD *)&v5->1 + 39) & 0x10000000) != 0 )
        goto LABEL_42;
    }
    if ( !ExIsResourceAcquiredExclusiveLite((PERESOURCE)(v4 + 172)) )
    {
      _InterlockedIncrement((volatile signed __int32 *)&v5->1 + 38);
      if ( !ExAcquireResourceExclusiveLite((PERESOURCE)(v4 + 172), 0) )
      {
        if ( (unsigned __int64)&RxContext[-1].TrackerHistory[31].Flags + 7 <= 0xFFFFFFFFFFFFFFFCuLL )
          LODWORD(RxContext->RdbssDbgExtension) |= 0x400000u;
        _RxReleaseFcb(0, (PMRX_FCB)&v5->Header, v25, v26, (ULONG)BugCheckParameter4);
        ExAcquireResourceExclusiveLite((PERESOURCE)(v4 + 172), 1u);
        _RxAcquireFcb(v5, 0, 1u, 0, BugCheckParameter4a, v45);
      }
      v22 = _InterlockedDecrement((volatile signed __int32 *)&v5->1 + 38);
      v51 = 1;
    }
    v21 = 60450;
    v9 = (const CHAR *)&WPP_GLOBAL_Control;
LABEL_42:
    v27 = *(struct _FCB **)&v5->UpperFinalizationDone;
    v49 = v27;
    if ( !v22 || (v28 = 0, v22 == 1) && (*((_DWORD *)&v5->1 + 39) & 0x10000000) == 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qZ(
          WPP_GLOBAL_Control->AttachedDevice,
          62,
          (unsigned int)WPP_e7aebc7caeed3866654dc8faf8a6aa71_Traceguids,
          (_DWORD)v5,
          (__int64)&v5->InternalFobx);
        v9 = (const CHAR *)&WPP_GLOBAL_Control;
        v21 = 60450;
      }
      if ( LODWORD(v5->ScavengerFinalizationList.Flink)
        || LODWORD(v5->NonPaged)
        || *((_DWORD *)&v5->1 + 38) > 1u
        || *((_DWORD *)&v5->1 + 38) == 1 && (*((_DWORD *)&v5->1 + 39) & 0x10000000) != 0 )
      {
        KeBugCheckEx(
          0x27u,
          0xFCB0151D,
          (ULONG_PTR)v5,
          SLODWORD(v5->ScavengerFinalizationList.Flink),
          *((unsigned int *)&v5->1 + 38));
      }
      if ( !LOBYTE(v5->ShareAccessPerSrvOpens.Readers) )
      {
        if ( v5->Header.NodeTypeCode == -5086 )
        {
          FsRtlUninitializeFileLock((PFILE_LOCK)&v5->FileLock.LockRequestsInProgress);
          v9 = (const CHAR *)&WPP_GLOBAL_Control;
        }
        if ( (*((_DWORD *)&v5->1 + 39) & 0x10000000) == 0 )
        {
          v29 = *((_QWORD *)&v5->1 + 15);
          p_MRxDispatch = &v5->MRxDispatch;
          ExAcquirePushLockExclusiveEx(v29 + 320, 0);
          for ( i = *(_QWORD **)(v29 + 328); i != (_QWORD *)(v29 + 328); i = (_QWORD *)*i )
          {
            if ( (PMINIRDR_DISPATCH *)i[5] == p_MRxDispatch )
            {
              MRxFastIoDispatch = (unsigned __int64)v5->MRxFastIoDispatch;
              if ( MRxFastIoDispatch )
              {
                v40 = *(_QWORD **)MRxFastIoDispatch;
                if ( *(_QWORD *)MRxFastIoDispatch )
                {
                  do
                  {
                    MRxFastIoDispatch = (unsigned __int64)v40;
                    v40 = (_QWORD *)*v40;
                  }
                  while ( v40 );
                }
              }
              else
              {
                v41 = (unsigned __int64)&v5->MRxDispatch;
                for ( MRxFastIoDispatch = (unsigned __int64)v5->InternalSrvOpen & 0xFFFFFFFFFFFFFFFCuLL;
                      MRxFastIoDispatch;
                      MRxFastIoDispatch = *(_QWORD *)(MRxFastIoDispatch + 16) & 0xFFFFFFFFFFFFFFFCuLL )
                {
                  if ( *(_QWORD *)MRxFastIoDispatch == v41 )
                    break;
                  v41 = MRxFastIoDispatch;
                }
              }
              i[5] = MRxFastIoDispatch;
            }
          }
          ExReleasePushLockExclusiveEx(v29 + 320, 0);
          v32 = *(_QWORD *)(v29 + 464);
          if ( v32 )
          {
            v33 = ((v5->ShareAccess.Deleters
                  & 0xFC
                  ^ ((unsigned __int64)(((unsigned __int16)v5->ShareAccess.Deleters
                                       ^ (unsigned __int16)((unsigned __int64)v5->ShareAccess.Deleters >> 6))
                                      & 0x3F00) >> 6)) >> 2)
                ^ (v5->ShareAccess.Deleters
                 & 3
                 ^ (unsigned __int8)((v5->ShareAccess.Deleters ^ ((unsigned __int64)v5->ShareAccess.Deleters >> 6)) >> 20))
                & 0x3F;
            if ( (PMINIRDR_DISPATCH *)(*(_QWORD *)(v32 + 8 * v33) & 0xFFFFFFFFFFFFFFFEuLL) == p_MRxDispatch )
              *(_QWORD *)(v32 + 8 * v33) = 0;
            v34 = 0;
            do
            {
              if ( !LOWORD(v5->ShareAccess.Writers) )
                break;
              v35 = *(_QWORD *)(v29 + 464);
              v36 = *(_QWORD *)(v35 + 8 * v34);
              if ( v36 )
              {
                if ( (v36 & 1) != 0 )
                {
                  v42 = (PMINIRDR_DISPATCH **)(v36 & 0xFFFFFFFFFFFFFFFEuLL);
                  if ( *v42 == p_MRxDispatch )
                  {
                    *(_QWORD *)(v35 + 8 * v34) = 0;
                    ExFreePoolWithTag(v42, 0);
                    --LOWORD(v5->ShareAccess.Writers);
                  }
                }
              }
              v34 = (unsigned int)(v34 + 1);
            }
            while ( (int)v34 < 64 );
            v4 = v48;
            v20 = v46;
          }
          RtlRbRemoveNode(v29 + 448, &v5->MRxDispatch);
          *(_OWORD *)p_MRxDispatch = 0;
          v5->InternalSrvOpen = 0;
          v9 = (const CHAR *)&WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_qZ(
              WPP_GLOBAL_Control->AttachedDevice,
              14,
              (unsigned int)WPP_518c92af35303f374eeedacc3593600d_Traceguids,
              (_DWORD)v5,
              (__int64)&v5->InternalFobx);
            v9 = (const CHAR *)&WPP_GLOBAL_Control;
          }
          --*(_DWORD *)(v29 + 312);
          _InterlockedIncrement((volatile signed __int32 *)(v29 + 300));
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 63, WPP_e7aebc7caeed3866654dc8faf8a6aa71_Traceguids, v5);
        }
        LOBYTE(v5->ShareAccessPerSrvOpens.Readers) = 1;
      }
      RxCloseFcbForTurboIo(v5, v27, v21, v9);
      RxDeregisterFcbWithBufferingManager(v5);
      v37 = *(_QWORD *)&v5->ShareAccessPerSrvOpens.SharedWrite;
      WORD1(v5->PrivateAlreadyPrefixedName.Buffer) = 0;
      if ( v37 )
        (*(void (__fastcall **)(_QWORD, PFCB))(v37 + 128))(0, v5);
      ExDeleteResourceLite(v5->Header.Resource);
      ExDeleteResourceLite(v5->Header.PagingIoResource);
      FsRtlUninitializeOplock((POPLOCK)&v5->pNetRoot);
      v38 = *((_QWORD *)&v5->1 + 15);
      if ( v38 )
      {
        _InterlockedDecrement((volatile signed __int32 *)(v38 + 60));
        RxDereference(*((PVOID *)&v5->1 + 15), LHS_LockNotHeld);
        *((_QWORD *)&v5->1 + 15) = 0;
      }
      RxFreeFcbObject(v5);
      v27 = v49;
      v28 = 1;
    }
    if ( !v20 )
      v18 = v28;
    if ( !v28 )
    {
LABEL_23:
      if ( v19 )
        _RxReleaseFcb(0, (PMRX_FCB)&v5->Header, v21, v9, (ULONG)BugCheckParameter4);
      break;
    }
    v19 = 0;
    v5 = v27;
    if ( v24 )
      RxDereference(v24, LHS_LockNotHeld);
    v9 = (const CHAR *)&WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v45 = (unsigned int)v5;
      BugCheckParameter4 = v47;
      WPP_SF_dqq(WPP_GLOBAL_Control->AttachedDevice, v27, v21, v20);
      v9 = (const CHAR *)&WPP_GLOBAL_Control;
    }
    v47 = (const CHAR *)v5;
    if ( v5 )
    {
      _RxAcquireFcb(v5, 0, 1u, 0, BugCheckParameter4, v45);
      v9 = (const CHAR *)&WPP_GLOBAL_Control;
      v19 = 1;
    }
    v46 = ++v20;
  }
  if ( v51 )
    ExReleaseResourceLite((PERESOURCE)(v4 + 172));
  if ( v18 && (unsigned __int64)&RxContext[-1].TrackerHistory[31].Flags + 7 <= 0xFFFFFFFFFFFFFFFCuLL )
    LOBYTE(RxContext->Flags) = 0;
  RxDereference(v4, LHS_LockNotHeld);
  return v18;
}

```

## disassembly

```asm
0x140058540  mov     [rsp+arg_8], rdx
0x140058545  push    rbx
0x140058546  push    rbp
0x140058547  push    rsi
0x140058548  push    rdi
0x140058549  push    r14
0x14005854b  push    r15
0x14005854d  sub     rsp, 58h
0x140058551  mov     rsi, [rcx+78h]
0x140058555  mov     rbx, rcx
0x140058558  mov     [rsp+88h+var_48], rsi
0x14005855d  xor     r14b, r14b
0x140058560  mov     r15d, 0EFFFh
0x140058566  mov     rax, [rsi]
0x140058569  mov     [rsp+88h+arg_0], rax
0x140058571  bt      ax, 0Ch
0x140058576  mov     rdi, rax
0x140058579  movzx   ecx, ax
0x14005857c  jb      loc_140058BF9
0x140058582  shr     rax, 20h
0x140058586  inc     eax
0x140058588  mov     dword ptr [rsp+88h+arg_0+4], eax
0x14005858f  mov     rcx, [rsp+88h+arg_0]
0x140058597  mov     rax, rdi
0x14005859a  lock cmpxchg [rsi], rcx
0x14005859f  mov     [rsp+88h+arg_0], rax
0x1400585a7  jnz     short loc_140058571
0x1400585a9  bt      di, 0Ch
0x1400585ae  lea     r9, WPP_GLOBAL_Control
0x1400585b5  jnb     loc_140058652
0x1400585bb  movzx   edx, word ptr [rsi]
0x1400585be  mov     r8d, edx
0x1400585c1  btr     r8d, 0Ch
0x1400585c6  cmp     r8d, 0EB12h
0x1400585cd  jnz     loc_140058B2C
0x1400585d3  mov     rax, [rsi+20h]
0x1400585d7  mov     rcx, [rax+20h]
0x1400585db  mov     rax, [rcx+30h]
0x1400585df  mov     rbp, [rax+340h]
0x1400585e6  mov     ecx, edx
0x1400585e8  btr     ecx, 0Ch
0x1400585ec  cmp     ecx, 0EB12h
0x1400585f2  jnz     loc_14005873D
0x1400585f8  add     rbp, 14h
0x1400585fc  lea     rdi, [rsi+10h]
0x140058600  cmp     [rdi], rdi
0x140058603  jz      loc_140058D4C
0x140058609  mov     rcx, cs:WPP_GLOBAL_Control
0x140058610  cmp     rcx, r9
0x140058613  jz      short loc_140058620
0x140058615  mov     eax, [rcx+2Ch]
0x140058618  test    al, al
0x14005861a  js      loc_140058D72
0x140058620  lock and dword ptr [rsi], 0FFFFEFFFh
0x140058627  dec     dword ptr [rbp+0]
0x14005862a  mov     rcx, [rdi]
0x14005862d  cmp     [rcx+8], rdi
0x140058631  jnz     loc_140058BD7
0x140058637  mov     rax, [rdi+8]
0x14005863b  cmp     [rax], rdi
0x14005863e  jnz     loc_140058BD7
0x140058644  mov     [rax], rcx
0x140058647  mov     [rcx+8], rax
0x14005864b  mov     [rdi+8], rdi
0x14005864f  mov     [rdi], rdi
0x140058652  mov     [rsp+88h+arg_10], r12
0x14005865a  xor     bpl, bpl
0x14005865d  mov     [rsp+88h+var_38], r13
0x140058662  xor     r12b, r12b
0x140058665  xor     r13d, r13d
0x140058668  mov     [rsp+88h+var_50], rbx
0x14005866d  mov     [rsp+88h+var_58], r13d
0x140058672  mov     byte ptr [rsp+88h+arg_0], bpl
0x14005867a  test    r14b, r14b
0x14005867d  jz      short loc_14005869B
0x14005867f  xor     edx, edx; Wait
0x140058681  lea     rcx, RxScavengerMutex; Mutex
0x140058688  call    cs:__imp_KeReleaseMutex
0x14005868f  nop     dword ptr [rax+rax+00h]
0x140058694  lea     r9, WPP_GLOBAL_Control; FileName
0x14005869b  mov     r8d, 0EC22h; LineNumber
0x1400586a1  test    rbx, rbx
0x1400586a4  jz      short loc_1400586EE
0x1400586a6  mov     edi, 0FFFFFFFFh
0x1400586ab  lock xadd [rbx+98h], edi
0x1400586b3  dec     edi
0x1400586b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400586bc  cmp     rcx, r9
0x1400586bf  jz      short loc_1400586CE
0x1400586c1  test    dword ptr [rcx+2Ch], 100h
0x1400586c8  jnz     loc_140058DA5
0x1400586ce  test    edi, edi
0x1400586d0  jz      loc_1400587AF
0x1400586d6  cmp     edi, 1
0x1400586d9  jz      loc_140058796
0x1400586df  test    r12b, r12b
0x1400586e2  jz      short loc_1400586EE
0x1400586e4  mov     rdx, rbx; MrxFcb
0x1400586e7  xor     ecx, ecx; RxContext
0x1400586e9  call    __RxReleaseFcb
0x1400586ee  cmp     byte ptr [rsp+88h+arg_0], 0
0x1400586f6  jz      short loc_14005870B
0x1400586f8  lea     rcx, [rsi+158h]; Resource
0x1400586ff  call    cs:__imp_ExReleaseResourceLite
0x140058706  nop     dword ptr [rax+rax+00h]
0x14005870b  test    bpl, bpl
0x14005870e  jnz     loc_140058B6A
0x140058714  xor     edx, edx; LockHoldingState
0x140058716  mov     rcx, rsi; Instance
0x140058719  call    RxDereference
0x14005871e  mov     r12, [rsp+88h+arg_10]
0x140058726  movzx   eax, bpl
0x14005872a  mov     r13, [rsp+88h+var_38]
0x14005872f  add     rsp, 58h
0x140058733  pop     r15
0x140058735  pop     r14
0x140058737  pop     rdi
0x140058738  pop     rsi
0x140058739  pop     rbp
0x14005873a  pop     rbx
0x14005873b  retn
0x14005873d  sub     ecx, 0EB10h
0x140058743  jz      loc_140058B61
0x140058749  sub     ecx, 1
0x14005874c  jz      loc_140058D43
0x140058752  sub     ecx, 2
0x140058755  jz      loc_140058BCE
0x14005875b  sub     ecx, 9
0x14005875e  jz      loc_140058D3A
0x140058764  cmp     ecx, 114h
0x14005876a  jz      loc_140058C3A
0x140058770  mov     r9, rdx; BugCheckParameter3
0x140058773  mov     [rsp+88h+BugCheckParameter4], 0; BugCheckParameter4
0x14005877c  mov     edx, 1021Ch; BugCheckParameter1
0x140058781  mov     r8, rsi; BugCheckParameter2
0x140058784  mov     ecx, 27h ; '''; BugCheckCode
0x140058789  call    cs:__imp_KeBugCheckEx
0x140058796  test    dword ptr [rbx+9Ch], 10000000h
0x1400587a0  jnz     loc_1400586DF
0x1400587a6  mov     r15, [rbx+80h]
0x1400587ad  jmp     short loc_1400587C2
0x1400587af  test    dword ptr [rbx+9Ch], 10000000h
0x1400587b9  mov     r15, [rbx+80h]
0x1400587c0  jnz     short loc_140058821
0x1400587c2  lea     rcx, [rsi+158h]; Resource
0x1400587c9  call    cs:__imp_ExIsResourceAcquiredExclusiveLite
0x1400587d0  nop     dword ptr [rax+rax+00h]
0x1400587d5  test    al, al
0x1400587d7  jnz     short loc_140058814
0x1400587d9  lock inc dword ptr [rbx+98h]
0x1400587e0  xor     edx, edx; Wait
0x1400587e2  lea     rcx, [rsi+158h]; Resource
0x1400587e9  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1400587f0  nop     dword ptr [rax+rax+00h]
0x1400587f5  test    al, al
0x1400587f7  jz      loc_140058C62
0x1400587fd  mov     edi, 0FFFFFFFFh
0x140058802  lock xadd [rbx+98h], edi
0x14005880a  dec     edi
0x14005880c  mov     byte ptr [rsp+88h+arg_0], 1
0x140058814  mov     r8d, 0EC22h
0x14005881a  lea     r9, WPP_GLOBAL_Control
0x140058821  mov     rdx, [rbx+120h]
0x140058828  mov     [rsp+88h+var_40], rdx
0x14005882d  test    edi, edi
0x14005882f  jz      short loc_14005884C
0x140058831  xor     cl, cl
0x140058833  cmp     edi, 1
0x140058836  jnz     loc_140058AAE
0x14005883c  test    dword ptr [rbx+9Ch], 10000000h
0x140058846  jnz     loc_140058AAE
0x14005884c  mov     rcx, cs:WPP_GLOBAL_Control
0x140058853  cmp     rcx, r9
0x140058856  jz      short loc_140058865
0x140058858  test    dword ptr [rcx+2Ch], 100h
0x14005885f  jnz     loc_140058DE7
0x140058865  movsxd  rcx, dword ptr [rbx+0C0h]
0x14005886c  test    ecx, ecx
0x14005886e  jnz     loc_140058BA6
0x140058874  cmp     [rbx+0B8h], ecx
0x14005887a  jnz     loc_140058BA6
0x140058880  cmp     dword ptr [rbx+98h], 1
0x140058887  ja      loc_140058BA6
0x14005888d  jnz     short loc_14005889F
0x14005888f  test    dword ptr [rbx+9Ch], 10000000h
0x140058899  jnz     loc_140058BA6
0x14005889f  cmp     byte ptr [rbx+178h], 0
0x1400588a6  jnz     loc_140058A19
0x1400588ac  cmp     [rbx], r8w
0x1400588b0  jz      loc_140058C43
0x1400588b6  test    dword ptr [rbx+9Ch], 10000000h
0x1400588c0  jnz     loc_1400589F9
0x1400588c6  mov     rdi, [rbx+78h]
0x1400588ca  lea     r14, [rbx+138h]
0x1400588d1  xor     edx, edx
0x1400588d3  lea     rcx, [rdi+140h]
0x1400588da  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400588e1  nop     dword ptr [rax+rax+00h]
0x1400588e6  lea     rcx, [rdi+148h]
0x1400588ed  mov     rdx, [rcx]
0x1400588f0  cmp     rdx, rcx
0x1400588f3  jnz     loc_140058CC2
0x1400588f9  xor     edx, edx
0x1400588fb  lea     rcx, [rdi+140h]
0x140058902  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140058909  nop     dword ptr [rax+rax+00h]
0x14005890e  mov     r9, [rdi+1D0h]
0x140058915  test    r9, r9
0x140058918  jz      loc_1400589A9
0x14005891e  mov     ecx, [r14+2Ch]
0x140058922  mov     eax, ecx
0x140058924  mov     r8d, ecx
0x140058927  shr     r8, 6
0x14005892b  and     eax, 0FCh
0x140058930  mov     rdx, r8
0x140058933  xor     r8, rcx
0x140058936  xor     rdx, rcx
0x140058939  shr     r8, 14h
0x14005893d  and     edx, 3F00h
0x140058943  and     ecx, 3
0x140058946  shr     rdx, 6
0x14005894a  xor     r8, rcx
0x14005894d  xor     rdx, rax
0x140058950  and     r8d, 3Fh
0x140058954  shr     rdx, 2
0x140058958  xor     r8, rdx
0x14005895b  mov     rax, [r9+r8*8]
0x14005895f  and     rax, 0FFFFFFFFFFFFFFFEh
0x140058963  cmp     rax, r14
0x140058966  jnz     short loc_140058970
0x140058968  mov     qword ptr [r9+r8*8], 0
0x140058970  xor     esi, esi
0x140058972  mov     r13d, 0FFFFh
0x140058978  cmp     word ptr [r14+28h], 0
0x14005897e  jbe     short loc_14005899F
0x140058980  mov     rax, [rdi+1D0h]
0x140058987  mov     rcx, [rax+rsi*8]
0x14005898b  lea     rdx, [rax+rsi*8]
0x14005898f  test    rcx, rcx
0x140058992  jnz     loc_140058E27
0x140058998  inc     esi
0x14005899a  cmp     esi, 40h ; '@'
0x14005899d  jl      short loc_140058978
0x14005899f  mov     rsi, [rsp+88h+var_48]
0x1400589a4  mov     r13d, [rsp+88h+var_58]
0x1400589a9  lea     rcx, [rdi+1C0h]
0x1400589b0  mov     rdx, r14
0x1400589b3  call    cs:__imp_RtlRbRemoveNode
0x1400589ba  nop     dword ptr [rax+rax+00h]
0x1400589bf  xorps   xmm0, xmm0
0x1400589c2  xor     eax, eax
0x1400589c4  movups  xmmword ptr [r14], xmm0
0x1400589c8  mov     [r14+10h], rax
0x1400589cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400589d3  lea     r9, WPP_GLOBAL_Control
0x1400589da  cmp     rcx, r9
0x1400589dd  jz      short loc_1400589EC
0x1400589df  test    dword ptr [rcx+2Ch], 100h
0x1400589e6  jnz     loc_140058E5C
0x1400589ec  dec     dword ptr [rdi+138h]
0x1400589f2  lock inc dword ptr [rdi+12Ch]
0x1400589f9  mov     rcx, cs:WPP_GLOBAL_Control
0x140058a00  cmp     rcx, r9
0x140058a03  jz      short loc_140058A12
0x140058a05  test    dword ptr [rcx+2Ch], 100h
0x140058a0c  jnz     loc_140058E93
0x140058a12  mov     byte ptr [rbx+178h], 1
0x140058a19  mov     rcx, rbx
0x140058a1c  call    RxCloseFcbForTurboIo
0x140058a21  mov     rcx, rbx; Instance
0x140058a24  call    RxDeregisterFcbWithBufferingManager
0x140058a29  mov     rax, [rbx+188h]
0x140058a30  mov     word ptr [rbx+11Ah], 0
0x140058a39  test    rax, rax
0x140058a3c  jz      short loc_140058A4F
0x140058a3e  mov     rax, [rax+80h]
0x140058a45  mov     rdx, rbx
0x140058a48  xor     ecx, ecx
0x140058a4a  call    _guard_dispatch_icall
0x140058a4f  mov     rcx, [rbx+8]; Resource
0x140058a53  call    cs:__imp_ExDeleteResourceLite
0x140058a5a  nop     dword ptr [rax+rax+00h]
0x140058a5f  mov     rcx, [rbx+10h]; Resource
0x140058a63  call    cs:__imp_ExDeleteResourceLite
0x140058a6a  nop     dword ptr [rax+rax+00h]
0x140058a6f  lea     rcx, [rbx+58h]; Oplock
0x140058a73  call    cs:__imp_FsRtlUninitializeOplock
0x140058a7a  nop     dword ptr [rax+rax+00h]
0x140058a7f  mov     rax, [rbx+78h]
0x140058a83  test    rax, rax
0x140058a86  jz      short loc_140058A9F
0x140058a88  lock dec dword ptr [rax+3Ch]
0x140058a8c  xor     edx, edx; LockHoldingState
0x140058a8e  mov     rcx, [rbx+78h]; Instance
0x140058a92  call    RxDereference
0x140058a97  mov     qword ptr [rbx+78h], 0
0x140058a9f  mov     rcx, rbx; Object
0x140058aa2  call    RxFreeFcbObject
0x140058aa7  mov     rdx, [rsp+88h+var_40]
0x140058aac  mov     cl, 1
  ... truncated ...
```
