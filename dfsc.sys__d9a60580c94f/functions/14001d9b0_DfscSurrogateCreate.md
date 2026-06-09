# DfscSurrogateCreate

- ea: `0x14001d9b0`
- end: `0x14001e3c3`
- name: `DfscSurrogateCreate`
- size: `2579`
- prototype: `__int64 __fastcall(struct _ECP_LIST *Size)`
- caller_count: `1`
- callee_count: `26`
- tags: `installer_update`

## callers

- `0x14001d950`

## callees

- `0x140001010`
- `0x140001408`
- `0x140002340`
- `0x140002570`
- `0x1400025f4`
- `0x1400026a4`
- `0x1400027f8`
- `0x140002cd0`
- `0x1400038ac`
- `0x140003904`
- `0x1400039f0`
- `0x140005fb0`
- `0x140011c80`
- `0x1400124c8`
- `0x14001abc0`
- `0x14001d9b0`
- `0x14001e3d0`
- `0x14001f8a0`
- `0x14001fb50`
- `0x140020e10`
- `0x140023010`
- `0x1400239b0`
- `0x140024e34`
- `0x140026fd0`
- `0x140026fe0`
- `0x1400284a0`

## import_xrefs

- `ntoskrnl!FsRtlAllocateExtraCreateParameterList` at `0x14001df7b`
- `ntoskrnl!FsRtlAllocateExtraCreateParameterList` at `0x14001df7b`
- `ntoskrnl!FsRtlAllocateExtraCreateParameter` at `0x14001dc22`
- `ntoskrnl!FsRtlAllocateExtraCreateParameter` at `0x14001dc22`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x14001dfcb`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x14001dfcb`
- `ntoskrnl!FsRtlFreeExtraCreateParameterList` at `0x14001dfb2`
- `ntoskrnl!FsRtlFreeExtraCreateParameterList` at `0x14001dfb2`
- `ntoskrnl!IoGetIrpExtraCreateParameter` at `0x14001d9ed`
- `ntoskrnl!IoGetIrpExtraCreateParameter` at `0x14001dbc1`
- `ntoskrnl!IoGetIrpExtraCreateParameter` at `0x14001d9ed`
- `ntoskrnl!IoGetIrpExtraCreateParameter` at `0x14001dbc1`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x14001da1f`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x14001dbee`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x14001da1f`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x14001dbee`
- `ntoskrnl!FsRtlFreeExtraCreateParameter` at `0x14001e16a`
- `ntoskrnl!FsRtlFreeExtraCreateParameter` at `0x14001e1d9`
- `ntoskrnl!FsRtlFreeExtraCreateParameter` at `0x14001e16a`
- `ntoskrnl!FsRtlFreeExtraCreateParameter` at `0x14001e1d9`
- `ntoskrnl!IoSetIrpExtraCreateParameter` at `0x14001df98`
- `ntoskrnl!IoSetIrpExtraCreateParameter` at `0x14001df98`
- `ntoskrnl!PsDereferenceSiloContext` at `0x14001e350`
- `ntoskrnl!PsDereferenceSiloContext` at `0x14001e350`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001dd0d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001e2f9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001dd0d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001e2f9`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001dd01`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001e2ed`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001dd01`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001e2ed`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14001dcc6`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14001e238`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14001dcc6`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14001e238`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001dcb1`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001e226`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001dcb1`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001e226`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001db5d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001dd24`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001ddf7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001de19`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001de87`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001df13`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e05c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e2d4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001db5d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001dd24`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001ddf7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001de19`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001de87`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001df13`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e05c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e2d4`

## pseudocode

```c
__int64 __fastcall DfscSurrogateCreate(struct _ECP_LIST *Size)
{
  PECP_LIST v1; // r15
  IRP *v2; // rcx
  char v3; // r14
  unsigned __int16 *v4; // rsi
  _QWORD *v5; // r12
  __int64 v6; // rdx
  int ContainerContextFromIrp; // edi
  __int64 v8; // r8
  __int64 v9; // r9
  int v10; // eax
  int v11; // ebx
  int v12; // edi
  __int64 v13; // r14
  int v14; // eax
  char v15; // al
  char v16; // bl
  __int64 v17; // rdx
  int v18; // eax
  IRP *v19; // rdi
  PVOID v20; // r14
  NTSTATUS IrpExtraCreateParameter; // ebx
  struct _ECP_LIST *v22; // rcx
  unsigned __int16 **v23; // r8
  PVOID *v24; // rdx
  void *v25; // rcx
  ULONG_PTR v26; // rbx
  struct _ERESOURCE *v27; // r14
  void *v28; // rcx
  void *v29; // rcx
  __int64 v30; // rbx
  volatile signed __int32 *v32; // r14
  NTSTATUS Parameter; // eax
  int v34; // edx
  int v35; // r9d
  int v36; // ecx
  int v37; // eax
  int v38; // eax
  int v39; // eax
  struct _ECP_LIST *ExtraCreateParameter; // [rsp+40h] [rbp-18h] BYREF
  PVOID EcpContext; // [rsp+48h] [rbp-10h] BYREF
  PECP_LIST EcpList; // [rsp+A0h] [rbp+48h] BYREF
  PVOID v43; // [rsp+A8h] [rbp+50h] BYREF
  PVOID P; // [rsp+B0h] [rbp+58h] BYREF
  __int64 v45; // [rsp+B8h] [rbp+60h] BYREF

  EcpList = Size;
  v1 = Size;
  P = 0;
  v2 = *(IRP **)Size;
  v3 = 0;
  v4 = 0;
  LOBYTE(v43) = 0;
  v45 = 0;
  ExtraCreateParameter = 0;
  EcpContext = 0;
  if ( !IoGetIrpExtraCreateParameter(v2, &ExtraCreateParameter) )
  {
    if ( ExtraCreateParameter )
    {
      EcpContext = 0;
      if ( !FsRtlFindExtraCreateParameter(ExtraCreateParameter, &DFSC_DFS_SHARE_CHECK_ECP_GUID, &EcpContext, 0) )
      {
        v38 = DfscRemoveEcpFromIrp(*(_QWORD *)v1, &DFSC_DFS_SHARE_CHECK_ECP_GUID);
        v3 = 1;
        LOBYTE(v43) = 1;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
        {
          WPP_SF_qD(
            WPP_GLOBAL_Control->AttachedDevice,
            19,
            WPP_eec51eedaa4835b9fabcddfcc06bf605_Traceguids,
            *(_QWORD *)v1,
            v38);
        }
      }
    }
  }
  v5 = 0;
  ContainerContextFromIrp = DfscGetContainerContextFromIrp(*(_QWORD *)v1, &v45);
  if ( ContainerContextFromIrp < 0
    || (v10 = DfscCmInitializeContext(0, 0, v45, 0, (size_t)v1, 0, (__int64)&P),
        v4 = (unsigned __int16 *)P,
        ContainerContextFromIrp = v10,
        v10 < 0) )
  {
LABEL_15:
    v16 = *((_BYTE *)v1 + 79);
    if ( v5 )
    {
      v17 = v5[1];
      if ( v17 )
      {
        LOBYTE(v9) = 1;
        DfscNetUseRelease(v45, v17, 0, v9);
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_eec51eedaa4835b9fabcddfcc06bf605_Traceguids, v5);
      }
      ExFreePoolWithTag(v5, 0);
      *((_QWORD *)v1 + 11) = 0;
    }
    if ( v16 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
      {
        if ( v4 )
          v39 = *((_DWORD *)v4 + 81);
        else
          v39 = -1;
        WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, v6, v8, (unsigned int)ContainerContextFromIrp, v39);
      }
      goto LABEL_38;
    }
    if ( !v4 || (v18 = *((_DWORD *)v4 + 81)) == 0 )
    {
      if ( ContainerContextFromIrp >= 0 )
        goto LABEL_38;
      v34 = 0;
      v35 = 5;
      while ( 1 )
      {
        v36 = (v35 + v34) / 2;
        if ( DfscCreatePathErrorList[v36] == ContainerContextFromIrp )
          goto LABEL_37;
        v37 = v36 - 1;
        if ( DfscCreatePathErrorList[v36] <= ContainerContextFromIrp )
          v37 = v35;
        v35 = v37;
        if ( DfscCreatePathErrorList[v36] <= ContainerContextFromIrp )
          v34 = v36 + 1;
        if ( v34 > v37 )
          goto LABEL_38;
      }
    }
    if ( v18 != 2 )
    {
LABEL_38:
      v15 = 0;
      goto LABEL_39;
    }
    if ( v3 )
    {
LABEL_37:
      ContainerContextFromIrp = -1073741802;
      goto LABEL_38;
    }
    v19 = *(IRP **)v1;
    v20 = 0;
    EcpList = 0;
    v43 = 0;
    if ( (v19->Flags & 0x80u) == 0 )
    {
      IrpExtraCreateParameter = -1073741808;
    }
    else
    {
      IrpExtraCreateParameter = IoGetIrpExtraCreateParameter(v19, &EcpList);
      if ( IrpExtraCreateParameter )
        goto LABEL_32;
      v22 = EcpList;
      if ( !EcpList )
      {
        IrpExtraCreateParameter = FsRtlAllocateExtraCreateParameterList(0, &EcpList);
        if ( IrpExtraCreateParameter )
          goto LABEL_32;
        Parameter = IoSetIrpExtraCreateParameter(v19, EcpList);
        v22 = EcpList;
        IrpExtraCreateParameter = Parameter;
        if ( Parameter )
        {
          FsRtlFreeExtraCreateParameterList(EcpList);
          goto LABEL_32;
        }
      }
      if ( !FsRtlFindExtraCreateParameter(v22, &DFSC_DFS_SHARE_CHECK_ECP_GUID, &v43, 0) )
        goto LABEL_120;
      IrpExtraCreateParameter = FsRtlAllocateExtraCreateParameter(
                                  &DFSC_DFS_SHARE_CHECK_ECP_GUID,
                                  0,
                                  0,
                                  0,
                                  0x48436644u,
                                  &v43);
      if ( IrpExtraCreateParameter )
      {
LABEL_32:
        if ( IrpExtraCreateParameter != 0x40000000 )
          goto LABEL_33;
LABEL_120:
        IrpExtraCreateParameter = DfscRemoveEcpFromIrp(v19, &DFSC_DFS_SHARE_CHECK_ECP_GUID);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
        {
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_eec51eedaa4835b9fabcddfcc06bf605_Traceguids, v19);
        }
        goto LABEL_33;
      }
      IrpExtraCreateParameter = FsRtlInsertExtraCreateParameter(EcpList, v43);
      if ( IrpExtraCreateParameter )
      {
        FsRtlFreeExtraCreateParameter(v43);
        goto LABEL_32;
      }
      v20 = v43;
    }
LABEL_33:
    if ( IrpExtraCreateParameter && v20 )
      FsRtlFreeExtraCreateParameter(v20);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
    {
      WPP_SF_qqd(WPP_GLOBAL_Control->AttachedDevice, v6, v8, v19, v20, IrpExtraCreateParameter);
    }
    goto LABEL_37;
  }
  v5 = (_QWORD *)*((_QWORD *)v1 + 11);
  v11 = 0;
  do
  {
    v12 = v11;
    v13 = v11;
    v14 = ((__int64 (__fastcall *)(unsigned __int16 *))DfscCmDispatchTable[v13])(v4);
    v11 = v14;
    *((_DWORD *)v4 + 78) = v12;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
    {
      WPP_SF_qDSS(
        WPP_GLOBAL_Control->AttachedDevice,
        v6,
        v8,
        (_DWORD)v4,
        *((_DWORD *)v4 + 79),
        (__int64)DfscStateTextTable[v13],
        (__int64)DfscStateTextTable[v14]);
    }
  }
  while ( v11 != 10 );
  ContainerContextFromIrp = *((_DWORD *)v4 + 79);
  v1 = EcpList;
  if ( ContainerContextFromIrp < 0 || ContainerContextFromIrp == 260 )
  {
    v3 = (char)v43;
    goto LABEL_15;
  }
  *v5 = *((_QWORD *)v4 + 34);
  DfscReferralReference();
  v15 = 1;
LABEL_39:
  *((_BYTE *)v1 + 78) = v15;
  if ( v4 && ContainerContextFromIrp != -1073741802 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_eec51eedaa4835b9fabcddfcc06bf605_Traceguids, v4[112]);
    }
    *((_WORD *)v1 + 38) = v4[112];
  }
  if ( v4 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
    {
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        15,
        WPP_eec51eedaa4835b9fabcddfcc06bf605_Traceguids,
        v4,
        *((_DWORD *)v4 + 1));
    }
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v4 + 1, 0xFFFFFFFF) == 1 )
    {
      KeEnterCriticalRegion();
      ExAcquireResourceExclusiveLite((PERESOURCE)&WPP_MAIN_CB.AlignmentRequirement, 1u);
      v23 = (unsigned __int16 **)*((_QWORD *)v4 + 46);
      if ( v23[1] != v4 + 184 || (v24 = (PVOID *)*((_QWORD *)v4 + 47), *v24 != v4 + 184) )
        __fastfail(3u);
      *v24 = v23;
      v23[1] = (unsigned __int16 *)v24;
      ExReleaseResourceLite((PERESOURCE)&WPP_MAIN_CB.AlignmentRequirement);
      KeLeaveCriticalRegion();
      v25 = (void *)*((_QWORD *)v4 + 13);
      if ( v25 )
        ExFreePoolWithTag(v25, 0);
      *((_OWORD *)v4 + 1) = 0;
      *((_OWORD *)v4 + 2) = 0;
      *((_OWORD *)v4 + 3) = 0;
      *((_OWORD *)v4 + 4) = 0;
      *((_OWORD *)v4 + 5) = 0;
      *((_OWORD *)v4 + 6) = 0;
      *((_OWORD *)v4 + 7) = 0;
      *((_OWORD *)v4 + 8) = 0;
      *((_OWORD *)v4 + 9) = 0;
      *((_OWORD *)v4 + 10) = 0;
      *((_OWORD *)v4 + 11) = 0;
      *((_OWORD *)v4 + 12) = 0;
      *((_OWORD *)v4 + 13) = 0;
      v4[113] = 0;
      v26 = *((_QWORD *)v4 + 29);
      if ( v26 )
      {
        v27 = *(struct _ERESOURCE **)(v26 + 24);
        if ( v27 )
        {
          KeEnterCriticalRegion();
          ExAcquireResourceExclusiveLite(v27 + 1, 1u);
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
        {
          WPP_SF_qD(
            WPP_GLOBAL_Control->AttachedDevice,
            16,
            WPP_dc6425c9357830de2cb01d836e426dd9_Traceguids,
            v26,
            *(_DWORD *)(v26 + 4));
        }
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v26 + 4), 0xFFFFFFFF) == 1 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
          {
            WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_dc6425c9357830de2cb01d836e426dd9_Traceguids, v26);
          }
          if ( v27 && *(_QWORD *)(v26 + 24) )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
            {
              WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_dc6425c9357830de2cb01d836e426dd9_Traceguids, v26);
            }
            DfscCredTableDelete(*(_QWORD *)(v26 + 24), v26);
          }
          v28 = *(void **)(v26 + 16);
          if ( v28 )
          {
            ExFreePoolWithTag(v28, 0);
            *(_QWORD *)(v26 + 16) = 0;
          }
          v29 = *(void **)(v26 + 64);
          if ( v29 )
          {
            ExFreePoolWithTag(v29, 0);
            *(_QWORD *)(v26 + 64) = 0;
          }
          ExFreePoolWithTag((PVOID)v26, 0);
        }
        if ( v27 )
        {
          ExReleaseResourceLite(v27 + 1);
          KeLeaveCriticalRegion();
        }
        *((_QWORD *)v4 + 29) = 0;
      }
      v30 = *((_QWORD *)v4 + 34);
      if ( v30 )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v30 + 4), 0xFFFFFFFF) == 1 )
        {
          v32 = *(volatile signed __int32 **)(v30 + 16);
          if ( v32 )
          {
            if ( _InterlockedExchangeAdd(v32 + 1, 0xFFFFFFFF) == 1 )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
              {
                WPP_SF_qZ(
                  WPP_GLOBAL_Control->AttachedDevice,
                  27,
                  (unsigned int)WPP_65d7788e2a383f8eac655d84410cd6ec_Traceguids,
                  (_DWORD)v32,
                  (__int64)(v32 + 36));
              }
              ExFreePoolWithTag((PVOID)v32, 0);
            }
            *(_QWORD *)(v30 + 16) = 0;
          }
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
          {
            WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_55706db06074317498eaf8c01331c814_Traceguids, v30);
          }
          ExFreePoolWithTag((PVOID)v30, 0);
        }
        *((_QWORD *)v4 + 34) = 0;
      }
      if ( *((_QWORD *)v4 + 31) )
      {
        PsDereferenceSiloContext();
        *((_QWORD *)v4 + 31) = 0;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_eec51eedaa4835b9fabcddfcc06bf605_Traceguids, v4);
      }
      ExFreePoolWithTag(v4, 0);
    }
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_eec51eedaa4835b9fabcddfcc06bf605_Traceguids);
  }
  return (unsigned int)ContainerContextFromIrp;
}

```

## disassembly

```asm
0x14001d9b0  mov     [rsp-40h+EcpList], rcx
0x14001d9b5  push    rbp
0x14001d9b6  push    rbx
0x14001d9b7  push    rsi
0x14001d9b8  push    rdi
0x14001d9b9  push    r12
0x14001d9bb  push    r13
0x14001d9bd  push    r14
0x14001d9bf  push    r15
0x14001d9c1  mov     rbp, rsp
0x14001d9c4  sub     rsp, 58h
0x14001d9c8  xor     edi, edi
0x14001d9ca  lea     rdx, [rbp+ExtraCreateParameter]; ExtraCreateParameter
0x14001d9ce  mov     r15, rcx
0x14001d9d1  mov     [rbp+P], rdi
0x14001d9d5  mov     rcx, [rcx]; Irp
0x14001d9d8  xor     r14b, r14b
0x14001d9db  mov     esi, edi
0x14001d9dd  mov     byte ptr [rbp+arg_8], r14b
0x14001d9e1  mov     [rbp+arg_18], rdi
0x14001d9e5  mov     [rbp+ExtraCreateParameter], rdi
0x14001d9e9  mov     [rbp+EcpContext], rdi
0x14001d9ed  call    cs:__imp_IoGetIrpExtraCreateParameter
0x14001d9f4  nop     dword ptr [rax+rax+00h]
0x14001d9f9  lea     rbx, WPP_GLOBAL_Control
0x14001da00  test    eax, eax
0x14001da02  jnz     short loc_14001DA33
0x14001da04  mov     rcx, [rbp+ExtraCreateParameter]; EcpList
0x14001da08  test    rcx, rcx
0x14001da0b  jz      short loc_14001DA33
0x14001da0d  xor     r9d, r9d; EcpContextSize
0x14001da10  mov     [rbp+EcpContext], rdi
0x14001da14  lea     r8, [rbp+EcpContext]; EcpContext
0x14001da18  lea     rdx, DFSC_DFS_SHARE_CHECK_ECP_GUID; EcpType
0x14001da1f  call    cs:__imp_FsRtlFindExtraCreateParameter
0x14001da26  nop     dword ptr [rax+rax+00h]
0x14001da2b  test    eax, eax
0x14001da2d  jz      loc_14001E06D
0x14001da33  mov     rcx, [r15]
0x14001da36  lea     rdx, [rbp+arg_18]
0x14001da3a  mov     r12, rdi
0x14001da3d  call    DfscGetContainerContextFromIrp
0x14001da42  mov     edi, eax
0x14001da44  mov     r13d, 0FFFFFFFFh
0x14001da4a  test    eax, eax
0x14001da4c  js      loc_14001DB1C
0x14001da52  mov     r8, [rbp+arg_18]; int
0x14001da56  lea     rax, [rbp+P]
0x14001da5a  mov     [rsp+58h+var_28], rax; __int64
0x14001da5f  xor     r9d, r9d; int
0x14001da62  mov     [rsp+58h+var_30], rsi; __int64
0x14001da67  xor     edx, edx; int
0x14001da69  xor     ecx, ecx; int
0x14001da6b  mov     qword ptr [rsp+58h+PoolTag], r15; Size
0x14001da70  call    DfscCmInitializeContext
0x14001da75  mov     rsi, [rbp+P]
0x14001da79  mov     edi, eax
0x14001da7b  test    eax, eax
0x14001da7d  js      loc_14001DB1C
0x14001da83  mov     r12, [r15+58h]
0x14001da87  lea     r13, WPP_GLOBAL_Control
0x14001da8e  lea     r15, cs:140000000h
0x14001da95  xor     ebx, ebx
0x14001da97  nop     word ptr [rax+rax+00000000h]
0x14001daa0  movsxd  rax, ebx
0x14001daa3  mov     rcx, rsi
0x14001daa6  mov     edi, ebx
0x14001daa8  lea     r14, ds:0[rax*8]
0x14001dab0  mov     rax, ds:(DfscCmDispatchTable - 140000000h)[r14+r15]
0x14001dab8  call    _guard_dispatch_icall
0x14001dabd  movsxd  rbx, eax
0x14001dac0  mov     [rsi+138h], edi
0x14001dac6  mov     rcx, cs:WPP_GLOBAL_Control
0x14001dacd  cmp     rcx, r13
0x14001dad0  jz      short loc_14001DADF
0x14001dad2  test    dword ptr [rcx+2Ch], 400000h
0x14001dad9  jnz     loc_14001E0C1
0x14001dadf  cmp     ebx, 0Ah
0x14001dae2  jnz     short loc_14001DAA0
0x14001dae4  mov     edi, [rsi+13Ch]
0x14001daea  mov     r13d, 0FFFFFFFFh
0x14001daf0  mov     r15, [rbp+EcpList]
0x14001daf4  test    edi, edi
0x14001daf6  js      short loc_14001DB17
0x14001daf8  cmp     edi, 104h
0x14001dafe  jz      short loc_14001DB17
0x14001db00  mov     rcx, [rsi+110h]
0x14001db07  mov     [r12], rcx
0x14001db0b  call    DfscReferralReference
0x14001db10  mov     al, 1
0x14001db12  jmp     loc_14001DC73
0x14001db17  movzx   r14d, byte ptr [rbp+arg_8]
0x14001db1c  movzx   ebx, byte ptr [r15+4Fh]
0x14001db21  test    r12, r12
0x14001db24  jz      loc_14001DFEA
0x14001db2a  mov     rdx, [r12+8]
0x14001db2f  test    rdx, rdx
0x14001db32  jnz     loc_14001DF61
0x14001db38  mov     rcx, cs:WPP_GLOBAL_Control
0x14001db3f  lea     rax, WPP_GLOBAL_Control
0x14001db46  cmp     rcx, rax
0x14001db49  jz      short loc_14001DB58
0x14001db4b  test    dword ptr [rcx+2Ch], 400000h
0x14001db52  jnz     loc_14001E0F6
0x14001db58  xor     edx, edx; Tag
0x14001db5a  mov     rcx, r12; P
0x14001db5d  call    cs:__imp_ExFreePoolWithTag
0x14001db64  nop     dword ptr [rax+rax+00h]
0x14001db69  xor     r12d, r12d
0x14001db6c  mov     [r15+58h], r12
0x14001db70  test    bl, bl
0x14001db72  jnz     loc_14001E113
0x14001db78  test    rsi, rsi
0x14001db7b  jz      loc_14001DFEF
0x14001db81  mov     eax, [rsi+144h]
0x14001db87  test    eax, eax
0x14001db89  jz      loc_14001DFEF
0x14001db8f  cmp     eax, 2
0x14001db92  jnz     loc_14001DC71
0x14001db98  test    r14b, r14b
0x14001db9b  jnz     loc_14001DC6C
0x14001dba1  mov     rdi, [r15]
0x14001dba4  mov     r14, r12
0x14001dba7  mov     [rbp+EcpList], r12
0x14001dbab  mov     [rbp+arg_8], r12
0x14001dbaf  mov     eax, [rdi+10h]
0x14001dbb2  test    al, al
0x14001dbb4  jns     loc_14001E15C
0x14001dbba  lea     rdx, [rbp+EcpList]; ExtraCreateParameter
0x14001dbbe  mov     rcx, rdi; Irp
0x14001dbc1  call    cs:__imp_IoGetIrpExtraCreateParameter
0x14001dbc8  nop     dword ptr [rax+rax+00h]
0x14001dbcd  mov     ebx, eax
0x14001dbcf  test    eax, eax
0x14001dbd1  jnz     short loc_14001DC38
0x14001dbd3  mov     rcx, [rbp+EcpList]; EcpList
0x14001dbd7  test    rcx, rcx
0x14001dbda  jz      loc_14001DF75
0x14001dbe0  xor     r9d, r9d; EcpContextSize
0x14001dbe3  lea     r8, [rbp+arg_8]; EcpContext
0x14001dbe7  lea     rdx, DFSC_DFS_SHARE_CHECK_ECP_GUID; EcpType
0x14001dbee  call    cs:__imp_FsRtlFindExtraCreateParameter
0x14001dbf5  nop     dword ptr [rax+rax+00h]
0x14001dbfa  test    eax, eax
0x14001dbfc  jz      loc_14001E17B
0x14001dc02  lea     rax, [rbp+arg_8]
0x14001dc06  xor     r9d, r9d; CleanupCallback
0x14001dc09  mov     [rsp+58h+var_30], rax; EcpContext
0x14001dc0e  lea     rcx, DFSC_DFS_SHARE_CHECK_ECP_GUID; EcpType
0x14001dc15  xor     r8d, r8d; Flags
0x14001dc18  mov     [rsp+58h+PoolTag], 48436644h; PoolTag
0x14001dc20  xor     edx, edx; SizeOfContext
0x14001dc22  call    cs:__imp_FsRtlAllocateExtraCreateParameter
0x14001dc29  nop     dword ptr [rax+rax+00h]
0x14001dc2e  mov     ebx, eax
0x14001dc30  test    eax, eax
0x14001dc32  jz      loc_14001DFC3
0x14001dc38  cmp     ebx, 40000000h
0x14001dc3e  jz      loc_14001E17B
0x14001dc44  lea     r12, WPP_GLOBAL_Control
0x14001dc4b  test    ebx, ebx
0x14001dc4d  jnz     loc_14001E1CD
0x14001dc53  mov     rcx, cs:WPP_GLOBAL_Control
0x14001dc5a  cmp     rcx, r12
0x14001dc5d  jz      short loc_14001DC6C
0x14001dc5f  test    dword ptr [rcx+2Ch], 400000h
0x14001dc66  jnz     loc_14001E1EA
0x14001dc6c  mov     edi, 0C0000016h
0x14001dc71  xor     al, al
0x14001dc73  mov     [r15+4Eh], al
0x14001dc77  test    rsi, rsi
0x14001dc7a  jnz     loc_14001DF24
0x14001dc80  lea     r12, WPP_GLOBAL_Control
0x14001dc87  test    rsi, rsi
0x14001dc8a  jz      loc_14001E38C
0x14001dc90  mov     rcx, cs:WPP_GLOBAL_Control
0x14001dc97  cmp     rcx, r12
0x14001dc9a  jnz     loc_14001DEA7
0x14001dca0  mov     eax, r13d
0x14001dca3  lock xadd [rsi+4], eax
0x14001dca8  cmp     eax, 1
0x14001dcab  jnz     loc_14001DE93
0x14001dcb1  call    cs:__imp_KeEnterCriticalRegion
0x14001dcb8  nop     dword ptr [rax+rax+00h]
0x14001dcbd  mov     dl, 1; Wait
0x14001dcbf  lea     rcx, WPP_MAIN_CB.AlignmentRequirement; Resource
0x14001dcc6  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14001dccd  nop     dword ptr [rax+rax+00h]
0x14001dcd2  lea     rax, [rsi+170h]
0x14001dcd9  mov     r8, [rax]
0x14001dcdc  cmp     [r8+8], rax
0x14001dce0  jnz     loc_14001E385
0x14001dce6  mov     rdx, [rax+8]
0x14001dcea  cmp     [rdx], rax
0x14001dced  jnz     loc_14001E385
0x14001dcf3  mov     [rdx], r8
0x14001dcf6  lea     rcx, WPP_MAIN_CB.AlignmentRequirement; Resource
0x14001dcfd  mov     [r8+8], rdx
0x14001dd01  call    cs:__imp_ExReleaseResourceLite
0x14001dd08  nop     dword ptr [rax+rax+00h]
0x14001dd0d  call    cs:__imp_KeLeaveCriticalRegion
0x14001dd14  nop     dword ptr [rax+rax+00h]
0x14001dd19  mov     rcx, [rsi+68h]; P
0x14001dd1d  test    rcx, rcx
0x14001dd20  jz      short loc_14001DD30
0x14001dd22  xor     edx, edx; Tag
0x14001dd24  call    cs:__imp_ExFreePoolWithTag
0x14001dd2b  nop     dword ptr [rax+rax+00h]
0x14001dd30  xorps   xmm0, xmm0
0x14001dd33  xorps   xmm1, xmm1
0x14001dd36  movups  xmmword ptr [rsi+10h], xmm0
0x14001dd3a  xor     r15d, r15d
0x14001dd3d  movups  xmmword ptr [rsi+20h], xmm0
0x14001dd41  movups  xmmword ptr [rsi+30h], xmm0
0x14001dd45  movups  xmmword ptr [rsi+40h], xmm0
0x14001dd49  movups  xmmword ptr [rsi+50h], xmm0
0x14001dd4d  movups  xmmword ptr [rsi+60h], xmm0
0x14001dd51  movups  xmmword ptr [rsi+70h], xmm1
0x14001dd55  movups  xmmword ptr [rsi+80h], xmm1
0x14001dd5c  movups  xmmword ptr [rsi+90h], xmm1
0x14001dd63  movups  xmmword ptr [rsi+0A0h], xmm1
0x14001dd6a  movups  xmmword ptr [rsi+0B0h], xmm1
0x14001dd71  movups  xmmword ptr [rsi+0C0h], xmm1
0x14001dd78  movups  xmmword ptr [rsi+0D0h], xmm0
0x14001dd7f  mov     [rsi+0E2h], r15w
0x14001dd87  mov     rbx, [rsi+0E8h]
0x14001dd8e  test    rbx, rbx
0x14001dd91  jz      loc_14001DE35
0x14001dd97  mov     r14, [rbx+18h]
0x14001dd9b  test    r14, r14
0x14001dd9e  jnz     loc_14001E226
0x14001dda4  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ddab  cmp     rcx, r12
0x14001ddae  jz      short loc_14001DDBD
0x14001ddb0  test    dword ptr [rcx+2Ch], 400000h
0x14001ddb7  jnz     loc_14001E249
0x14001ddbd  mov     eax, r13d
0x14001ddc0  lock xadd [rbx+4], eax
0x14001ddc5  cmp     eax, 1
0x14001ddc8  jnz     short loc_14001DE25
0x14001ddca  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ddd1  cmp     rcx, r12
0x14001ddd4  jz      short loc_14001DDE3
0x14001ddd6  test    dword ptr [rcx+2Ch], 400000h
0x14001dddd  jnz     loc_14001E26D
0x14001dde3  test    r14, r14
0x14001dde6  jnz     loc_14001E28A
0x14001ddec  mov     rcx, [rbx+10h]; P
0x14001ddf0  test    rcx, rcx
0x14001ddf3  jz      short loc_14001DE07
0x14001ddf5  xor     edx, edx; Tag
0x14001ddf7  call    cs:__imp_ExFreePoolWithTag
0x14001ddfe  nop     dword ptr [rax+rax+00h]
0x14001de03  mov     [rbx+10h], r15
0x14001de07  mov     rcx, [rbx+40h]; P
0x14001de0b  test    rcx, rcx
0x14001de0e  jnz     loc_14001E2D2
0x14001de14  xor     edx, edx; Tag
0x14001de16  mov     rcx, rbx; P
0x14001de19  call    cs:__imp_ExFreePoolWithTag
0x14001de20  nop     dword ptr [rax+rax+00h]
0x14001de25  test    r14, r14
0x14001de28  jnz     loc_14001E2E9
0x14001de2e  mov     [rsi+0E8h], r15
0x14001de35  mov     rbx, [rsi+110h]
0x14001de3c  test    rbx, rbx
0x14001de3f  jz      short loc_14001DE59
0x14001de41  mov     eax, r13d
0x14001de44  lock xadd [rbx+4], eax
0x14001de49  cmp     eax, 1
0x14001de4c  jz      loc_14001DED8
0x14001de52  mov     [rsi+110h], r15
0x14001de59  mov     rcx, [rsi+0F8h]
0x14001de60  test    rcx, rcx
0x14001de63  jnz     loc_14001E350
0x14001de69  mov     rcx, cs:WPP_GLOBAL_Control
0x14001de70  cmp     rcx, r12
0x14001de73  jz      short loc_14001DE82
0x14001de75  test    dword ptr [rcx+2Ch], 400000h
0x14001de7c  jnz     loc_14001E368
0x14001de82  xor     edx, edx; Tag
0x14001de84  mov     rcx, rsi; P
0x14001de87  call    cs:__imp_ExFreePoolWithTag
0x14001de8e  nop     dword ptr [rax+rax+00h]
0x14001de93  mov     eax, edi
0x14001de95  add     rsp, 58h
0x14001de99  pop     r15
0x14001de9b  pop     r14
0x14001de9d  pop     r13
0x14001de9f  pop     r12
0x14001dea1  pop     rdi
0x14001dea2  pop     rsi
0x14001dea3  pop     rbx
0x14001dea4  pop     rbp
0x14001dea5  retn
0x14001dea7  test    dword ptr [rcx+2Ch], 400000h
0x14001deae  jz      loc_14001DCA0
0x14001deb4  mov     eax, [rsi+4]
0x14001deb7  lea     r8, WPP_eec51eedaa4835b9fabcddfcc06bf605_Traceguids
0x14001debe  mov     rcx, [rcx+18h]
  ... truncated ...
```
