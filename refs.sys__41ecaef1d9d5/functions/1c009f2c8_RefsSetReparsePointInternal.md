# RefsSetReparsePointInternal

- ea: `0x1c009f2c8`
- end: `0x1c00a031e`
- name: `RefsSetReparsePointInternal`
- size: `4182`
- prototype: `__int64 __usercall@<rax>(PVOID Context1@<rcx>, __int16, PREPARSE_DATA_BUFFER ReparseBuffer, __int64)`
- caller_count: `2`
- callee_count: `24`
- tags: `reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1c016752c`
- `0x1c01c3dc4`

## callees

- `0x1c0003658`
- `0x1c0005768`
- `0x1c000f770`
- `0x1c003af60`
- `0x1c003b21c`
- `0x1c00595d0`
- `0x1c0063db0`
- `0x1c0068168`
- `0x1c0068960`
- `0x1c006af80`
- `0x1c00925e8`
- `0x1c009f2c8`
- `0x1c00a29c4`
- `0x1c00ac1e8`
- `0x1c00ad610`
- `0x1c014fe2c`
- `0x1c015ac58`
- `0x1c015d78c`
- `0x1c015dfe8`
- `0x1c01632d4`
- `0x1c01634c8`
- `0x1c016598c`
- `0x1c018d1e4`
- `0x1c018d9d4`

## import_xrefs

- `ntoskrnl!FsRtlIsNonEmptyDirectoryReparsePointAllowed` at `0x1c009f7d3`
- `ntoskrnl!FsRtlIsNonEmptyDirectoryReparsePointAllowed` at `0x1c009f8cf`
- `ntoskrnl!FsRtlIsNonEmptyDirectoryReparsePointAllowed` at `0x1c009f7d3`
- `ntoskrnl!FsRtlIsNonEmptyDirectoryReparsePointAllowed` at `0x1c009f8cf`
- `ntoskrnl!FsRtlValidateReparsePointBuffer` at `0x1c009f362`
- `ntoskrnl!FsRtlValidateReparsePointBuffer` at `0x1c009f362`
- `ntoskrnl!CcCanIWrite` at `0x1c009fc74`
- `ntoskrnl!CcCanIWrite` at `0x1c009fedc`
- `ntoskrnl!CcCanIWrite` at `0x1c009fc74`
- `ntoskrnl!CcCanIWrite` at `0x1c009fedc`
- `ntoskrnl!SePrivilegeCheck` at `0x1c009f59e`
- `ntoskrnl!SePrivilegeCheck` at `0x1c009f59e`
- `ntoskrnl!CcDeferWrite` at `0x1c009fcfd`
- `ntoskrnl!CcDeferWrite` at `0x1c009ff60`
- `ntoskrnl!CcDeferWrite` at `0x1c009fcfd`
- `ntoskrnl!CcDeferWrite` at `0x1c009ff60`

## string_xrefs

- `0x1c009f3c8`: `MountSup.c`
- `0x1c009f467`: `MountSup.c`
- `0x1c009f503`: `MountSup.c`
- `0x1c009f5ff`: `MountSup.c`
- `0x1c009f6b7`: `MountSup.c`
- `0x1c009f723`: `MountSup.c`
- `0x1c009f79c`: `MountSup.c`
- `0x1c009f858`: `MountSup.c`
- `0x1c009f9d3`: `MountSup.c`
- `0x1c009fa56`: `MountSup.c`
- `0x1c009fb55`: `MountSup.c`
- `0x1c009fc27`: `MountSup.c`
- `0x1c009fd58`: `MountSup.c`
- `0x1c00a01ee`: `MountSup.c`
- `0x1c00a0216`: `MountSup.c`
- `0x1c00a028b`: `MountSup.c`
- `0x1c00a02b3`: `MountSup.c`

## pseudocode

```c
__int64 __fastcall RefsSetReparsePointInternal(
        _DWORD *Context1,
        IRP *a2,
        __int64 a3,
        __int64 a4,
        unsigned __int16 a5,
        PREPARSE_DATA_BUFFER ReparseBuffer,
        _BYTE *a7)
{
  __int64 v11; // rbx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r15
  NTSTATUS v13; // eax
  __int64 v14; // rdx
  __int64 result; // rax
  ULONG ReparseTag; // r12d
  struct _IRP *MasterIrp; // rsi
  __int64 v18; // rcx
  KPROCESSOR_MODE v19; // al
  int v20; // eax
  __int64 v21; // r9
  PDEVICE_OBJECT *v22; // rcx
  __int64 v23; // r8
  char v24; // al
  char IsNonEmptyDirectoryReparsePointAllowed; // al
  char IsFileDeleteable; // al
  int v27; // eax
  char v28; // al
  char v29; // al
  char v30; // al
  __int64 v31; // r8
  __int64 v32; // r9
  int v33; // ecx
  ULONG BytesToWrite; // esi
  __int64 v35; // rcx
  int v36; // ebx
  _DWORD *v37; // rax
  int v38; // edx
  __int64 v39; // rax
  __int64 v40; // r8
  int v41; // edx
  __int64 v42; // rcx
  NTSTATUS v43; // esi
  bool v44; // sf
  __int64 v45; // rcx
  int v46; // ebx
  _DWORD *v47; // rax
  int v48; // edx
  __int64 v49; // rax
  int v50; // edx
  NTSTATUS v51; // esi
  bool v52; // sf
  __int64 v53; // rcx
  NTSTATUS v54; // eax
  NTSTATUS v55; // eax
  __int64 v56; // rdx
  __int64 v57; // rbp
  __int64 v58; // rcx
  __int64 v59; // rcx
  unsigned int Status; // [rsp+50h] [rbp-188h]
  char v61; // [rsp+54h] [rbp-184h]
  char v62; // [rsp+58h] [rbp-180h] BYREF
  char v63; // [rsp+59h] [rbp-17Fh] BYREF
  char v64; // [rsp+5Ah] [rbp-17Eh] BYREF
  _BYTE v65[5]; // [rsp+5Bh] [rbp-17Dh] BYREF
  __int64 v66; // [rsp+60h] [rbp-178h] BYREF
  __int64 v67; // [rsp+68h] [rbp-170h] BYREF
  __int128 v68; // [rsp+70h] [rbp-168h] BYREF
  PIRP Irp; // [rsp+80h] [rbp-158h]
  PREPARSE_DATA_BUFFER v70; // [rsp+88h] [rbp-150h]
  _BYTE *v71; // [rsp+90h] [rbp-148h]
  _DWORD *v72; // [rsp+98h] [rbp-140h]
  struct _PRIVILEGE_SET RequiredPrivileges; // [rsp+A0h] [rbp-138h] BYREF
  _BYTE v74[208]; // [rsp+C0h] [rbp-118h] BYREF

  Irp = a2;
  v72 = Context1;
  v70 = ReparseBuffer;
  v71 = a7;
  v11 = *(_QWORD *)(a3 + 120);
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  memset(v74, 0, sizeof(v74));
  v68 = 0;
  v61 = 0;
  v13 = FsRtlValidateReparsePointBuffer(a5, ReparseBuffer);
  Status = v13;
  if ( v13 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(
        WPP_GLOBAL_Control->AttachedDevice,
        16,
        WPP_3e5fcb63d1a135eac59067d9d65bc2e5_Traceguids,
        (unsigned int)v13);
    }
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(Status);
    return Status;
  }
  ReparseTag = ReparseBuffer->ReparseTag;
  MasterIrp = a2->AssociatedIrp.MasterIrp;
  if ( ReparseBuffer->ReparseTag == -1610612733 && *(_BYTE *)(a4 + 80) != 3 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_3e5fcb63d1a135eac59067d9d65bc2e5_Traceguids, 3221225731LL);
    }
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741565);
    return 3221225731LL;
  }
  if ( ReparseTag != -1610612724 )
    goto LABEL_39;
  v70->SymbolicLinkReparseBuffer.Flags &= 0xFFFFFFFu;
  if ( *((_BYTE *)Context1 + 40) == 13 )
  {
    if ( (*(_WORD *)(a4 + 88) & 0x400) == 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_3e5fcb63d1a135eac59067d9d65bc2e5_Traceguids, 3221225506LL);
      }
      if ( RefsStatusDebugEnabled )
        RefsStatusDebug(-1073741790);
      return 3221225506LL;
    }
LABEL_39:
    Context1[2] |= 1u;
    Context1[50] = *(_DWORD *)(a4 + 84);
    v20 = *(_DWORD *)(a3 + 304);
    if ( (v20 & 0x10000) != 0 )
      v21 = 3221226094LL;
    else
      v21 = (v20 & 0x1000000) != 0 ? 0xC0000008 : 0;
    Status = v21;
    if ( (int)v21 < 0 )
    {
      v22 = &WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_3e5fcb63d1a135eac59067d9d65bc2e5_Traceguids, v21);
      }
      if ( RefsStatusDebugEnabled )
        RefsStatusDebug(Status);
      goto LABEL_187;
    }
    if ( (*(_DWORD *)(v11 + 4) & 1) != 0 )
    {
      v22 = &WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_3e5fcb63d1a135eac59067d9d65bc2e5_Traceguids, 3221225763LL);
      }
      if ( RefsStatusDebugEnabled )
        RefsStatusDebug(-1073741533);
      Status = -1073741533;
      goto LABEL_187;
    }
    if ( !(unsigned __int8)RefsIsFileOpen(v11, v14, 0) )
    {
      v22 = &WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_3e5fcb63d1a135eac59067d9d65bc2e5_Traceguids, 3221225768LL);
      }
      if ( RefsStatusDebugEnabled )
        RefsStatusDebug(-1073741528);
      Status = -1073741528;
      goto LABEL_187;
    }
    v24 = *(_BYTE *)(a4 + 80);
    if ( v24 == 3 )
    {
      v63 = v23;
      v62 = v23;
      IsNonEmptyDirectoryReparsePointAllowed = FsRtlIsNonEmptyDirectoryReparsePointAllowed(ReparseTag);
      v23 = 0;
      if ( !IsNonEmptyDirectoryReparsePointAllowed )
      {
        IsFileDeleteable = RefsIsFileDeleteable(Context1, v11, &v63, &v62);
        v23 = 0;
        if ( !IsFileDeleteable )
        {
          v22 = &WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_D(
              WPP_GLOBAL_Control->AttachedDevice,
              23,
              WPP_3e5fcb63d1a135eac59067d9d65bc2e5_Traceguids,
              3221225729LL);
          }
          if ( !RefsStatusDebugEnabled )
            goto LABEL_74;
          goto LABEL_73;
        }
      }
    }
    else if ( v24 == 2 )
    {
      if ( RefsDisallowInvalidReparsePoint )
      {
        v65[0] = v23;
        v64 = v23;
        v27 = *(_DWORD *)(a3 + 200);
        if ( (v27 == 128 || v27 == 176)
          && *(_WORD *)(a3 + 208) != (_WORD)v23
          && (*(_DWORD *)(v11 + 160) & 0x10000000) != 0 )
        {
          v28 = FsRtlIsNonEmptyDirectoryReparsePointAllowed(ReparseTag);
          v23 = 0;
          if ( !v28 )
          {
            v29 = RefsIsFileDeleteable(Context1, v11, v65, &v64);
            v23 = 0;
            if ( !v29 )
            {
              v22 = &WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
              {
                WPP_SF_D(
                  WPP_GLOBAL_Control->AttachedDevice,
                  24,
                  WPP_3e5fcb63d1a135eac59067d9d65bc2e5_Traceguids,
                  3221225729LL);
              }
              if ( !RefsStatusDebugEnabled )
                goto LABEL_74;
LABEL_73:
              RefsStatusDebug(-1073741567);
LABEL_74:
              Status = -1073741567;
LABEL_187:
              RefsUnmapAttribute(v22, v74, &v68);
              if ( (v61 & 2) != 0 )
                RefsUnmapAttribute(v53, v74, &v68);
              if ( (v61 & 1) != 0 )
                RefsCleanupAttributeContext(Context1, v74);
              return Status;
            }
          }
        }
      }
      if ( ReparseTag == -1610612724 )
      {
        if ( (*(_DWORD *)(a3 + 136) & 0x20) == 0 )
        {
          RefsUpdateScbFromAttribute(Context1, a3, 0);
          v23 = 0;
        }
        if ( *(_QWORD *)(a3 + 32) != v23 )
        {
          v22 = &WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_D(
              WPP_GLOBAL_Control->AttachedDevice,
              25,
              WPP_3e5fcb63d1a135eac59067d9d65bc2e5_Traceguids,
              3221226104LL);
          }
          if ( RefsStatusDebugEnabled )
            RefsStatusDebug(-1073741192);
          Status = -1073741192;
          goto LABEL_187;
        }
      }
    }
    if ( (*(_DWORD *)(v11 + 160) & 0x400) == 0 && *(_WORD *)(v11 + 164) > (unsigned __int16)v23 )
    {
      v22 = &WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_3e5fcb63d1a135eac59067d9d65bc2e5_Traceguids, 3221225551LL);
      }
      if ( RefsStatusDebugEnabled )
        RefsStatusDebug(-1073741745);
      Status = -1073741745;
      goto LABEL_187;
    }
    v30 = RefsLookupInFileRecord((_DWORD)Context1, v11, v23, 192, v23);
    v33 = *(_DWORD *)(v11 + 160) & 0x400;
    if ( v30 )
    {
      LODWORD(v66) = 0;
      if ( !v33 )
      {
        v54 = RefsQueueTriageForDeadFcb(Context1, v11, v31, v32);
        v43 = v54;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_qd(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_3e5fcb63d1a135eac59067d9d65bc2e5_Traceguids, v11, v54);
        }
        if ( RefsStatusDebugEnabled )
          RefsStatusDebug(v43);
        RefsRaiseStatusInternal(Context1, (unsigned int)v43);
LABEL_198:
        if ( RefsStatusDebugEnabled )
          RefsStatusDebug(v43);
        RefsRaiseStatusInternal(Context1, (unsigned int)v43);
        goto LABEL_201;
      }
      v67 = 0;
      RefsMapAttributeValue((_DWORD)Context1, v11, (unsigned int)&v67, (unsigned int)&v66, (__int64)&v68, (__int64)v74);
      v61 = 3;
      if ( ReparseTag != *(_DWORD *)v67 )
      {
        v22 = &WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_D(
            WPP_GLOBAL_Control->AttachedDevice,
            28,
            WPP_3e5fcb63d1a135eac59067d9d65bc2e5_Traceguids,
            3221226103LL);
        }
        if ( RefsStatusDebugEnabled )
          RefsStatusDebug(-1073741193);
        Status = -1073741193;
        goto LABEL_187;
      }
      if ( (ReparseTag & 0x80000000) == 0
        && (LODWORD(MasterIrp->MdlAddress) != *(_DWORD *)(v67 + 8)
         || WORD2(MasterIrp->MdlAddress) != *(_WORD *)(v67 + 12)
         || HIWORD(MasterIrp->MdlAddress) != *(_WORD *)(v67 + 14)
         || LOBYTE(MasterIrp->Flags) != *(_BYTE *)(v67 + 16)
         || BYTE1(MasterIrp->Flags) != *(_BYTE *)(v67 + 17)
         || BYTE2(MasterIrp->Flags) != *(_BYTE *)(v67 + 18)
         || HIBYTE(MasterIrp->Flags) != *(_BYTE *)(v67 + 19)
         || *((_BYTE *)&MasterIrp->Flags + 4) != *(_BYTE *)(v67 + 20)
         || *((_BYTE *)&MasterIrp->Flags + 5) != *(_BYTE *)(v67 + 21)
         || *((_BYTE *)&MasterIrp->Flags + 6) != *(_BYTE *)(v67 + 22)
         || *((_BYTE *)&MasterIrp->Flags + 7) != *(_BYTE *)(v67 + 23)) )
      {
        v22 = &WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_D(
            WPP_GLOBAL_Control->AttachedDevice,
            29,
            WPP_3e5fcb63d1a135eac59067d9d65bc2e5_Traceguids,
            3221226162LL);
        }
        if ( RefsStatusDebugEnabled )
          RefsStatusDebug(-1073741134);
        Status = -1073741134;
        goto LABEL_187;
      }
      if ( a5 > (unsigned int)v66 )
      {
        BytesToWrite = a5 - (_DWORD)v66;
        if ( !CcCanIWrite(*(PFILE_OBJECT *)(a4 + 96), BytesToWrite, 0, (Context1[1] & 8) != 0) )
        {
          v36 = Context1[1];
          RefsUnmapAttribute(v35, v74, &v68);
          RefsCleanupAttributeContext(Context1, v74);
          v61 = 0;
          RefsPrePostIrp(Context1, Irp);
          *v71 = 0;
          Context1[1] |= 8u;
          CcDeferWrite(*(PFILE_OBJECT *)(a4 + 96), RefsAddToWorkque, Context1, Irp, BytesToWrite, (v36 & 8) != 0);
          v22 = &WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
          {
            WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 30, WPP_3e5fcb63d1a135eac59067d9d65bc2e5_Traceguids, 259);
          }
          if ( !RefsStatusDebugEnabled )
            goto LABEL_146;
          goto LABEL_145;
        }
      }
      v37 = (_DWORD *)RefsAddStructToRollbackList(Context1, 2083, v11, 1);
      v38 = ~(unsigned __int16)v37[11] & 0x400;
      v37[11] |= v38;
      v37[10] |= *(_DWORD *)(v11 + 160) & v38;
      v37[1] |= 0x10u;
      v39 = RefsAddStructToRollbackList(Context1, 2083, v11, 1);
      v41 = *(_DWORD *)(v39 + 4);
      if ( (v41 & 0x40) == 0 )
      {
        *(_DWORD *)(v39 + 56) = *(_DWORD *)(v11 + 164);
        *(_DWORD *)(v39 + 4) = v41 | 0x40;
      }
      RefsChangeAttributeValue(Context1, v11, v40, v70, a5);
      RefsUnmapAttribute(v42, v74, &v68);
      RefsCleanupAttributeContext(Context1, v74);
      v61 = 0;
      RefsUpdateStandardInformation(Context1, v11);
      if ( *((_BYTE *)Context1 + 40) )
      {
        RefsPostUsnChangeWithOverrideOption(Context1, a3, 0x100000);
        v43 = *(_DWORD *)(*((_QWORD *)Context1 + 13) + 16LL);
        v44 = v43 < 0;
        if ( v43 >= 0 )
        {
          RefsCheckpointCurrentTransaction(Context1);
          v44 = v43 < 0;
        }
        if ( !v44 )
          v43 = 0;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        {
LABEL_159:
          if ( v43 >= 0 )
            goto LABEL_183;
          goto LABEL_198;
        }
        if ( v43 < 0 )
        {
          if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            WPP_SF_D(
              WPP_GLOBAL_Control->AttachedDevice,
              31,
              WPP_3e5fcb63d1a135eac59067d9d65bc2e5_Traceguids,
              (unsigned int)v43);
          goto LABEL_159;
        }
      }
LABEL_183:
      v22 = (PDEVICE_OBJECT *)*(unsigned int *)(a4 + 4);
      if ( (*(_DWORD *)(v11 + 160) & 0x10000000) == 0 )
      {
        LODWORD(v22) = (unsigned int)v22 | 0x400000;
        *(_DWORD *)(a4 + 4) = (_DWORD)v22;
      }
      LODWORD(v22) = (unsigned int)v22 | 0x200000;
      *(_DWORD *)(a4 + 4) = (_DWORD)v22;
      if ( *((_BYTE *)Context1 + 40) )
        RefsFlushForWriteThrough(Context1, v11);
      goto LABEL_187;
    }
    if ( v33 )
    {
LABEL_201:
      v55 = RefsQueueTriageForDeadFcb(Context1, v11, v31, v32);
      v51 = v55;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_qd(WPP_GLOBAL_Control->AttachedDevice, 32, WPP_3e5fcb63d1a135eac59067d9d65bc2e5_Traceguids, v11, v55);
      }
      if ( RefsStatusDebugEnabled )
        RefsStatusDebug(v51);
      RefsRaiseStatusInternal(Context1, (unsigned int)v51);
      goto LABEL_208;
    }
    if ( !CcCanIWrite(*(PFILE_OBJECT *)(a4 + 96), a5, 0, (Context1[1] & 8) != 0) )
    {
      v46 = Context1[1];
      RefsUnmapAttribute(v45, v74, &v68);
      RefsCleanupAttributeContext(Context1, v74);
      v61 = 0;
      RefsPrePostIrp(Context1, Irp);
      *v71 = 0;
      Context1[1] |= 8u;
      CcDeferWrite(*(PFILE_OBJECT *)(a4 + 96), RefsAddToWorkque, Context1, Irp, a5, (v46 & 8) != 0);
      v22 = &WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_3e5fcb63d1a135eac59067d9d65bc2e5_Traceguids, 259);
      }
      if ( !RefsStatusDebugEnabled )
        goto LABEL_146;
LABEL_145:
      RefsStatusDebug(259);
LABEL_146:
      Status = 259;
      goto LABEL_187;
    }
    RefsCleanupAttributeContext(Context1, v74);
    memset(v74, 0, sizeof(v74));
    v47 = (_DWORD *)RefsAddStructToRollbackList(Context1, 2083, v11, 1);
    v48 = ~(unsigned __int16)v47[11] & 0x400;
    v47[11] |= v48;
    v47[10] |= *(_DWORD *)(v11 + 160) & v48;
    v47[1] |= 0x10u;
    v49 = RefsAddStructToRollbackList(Context1, 2083, v11, 1);
    v50 = *(_DWORD *)(v49 + 4);
    if ( (v50 & 0x40) == 0 )
    {
      *(_DWORD *)(v49 + 56) = *(_DWORD *)(v11 + 164);
      *(_DWORD *)(v49 + 4) = v50 | 0x40;
    }
    RefsCreateReparsePointInternal((_DWORD)Context1, v11, (_DWORD)v70, a5, ReparseTag);
    RefsCleanupAttributeContext(Context1, v74);
    v61 = 0;
    *(_DWORD *)(a4 + 4) |= 0x210000u;
    RefsUpdateStandardInformation(Context1, v11);
    if ( *((_BYTE *)Context1 + 40) )
    {
      RefsPostUsnChangeWithOverrideOption(Context1, a3, 0x100000);
      v51 = *(_DWORD *)(*((_QWORD *)Context1 + 13) + 16LL);
      v52 = v51 < 0;
      if ( v51 >= 0 )
      {
        RefsCheckpointCurrentTransaction(Context1);
        v52 = v51 < 0;
      }
      if ( !v52 )
        v51 = 0;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
LABEL_181:
        if ( v51 < 0 )
        {
LABEL_208:
          if ( RefsStatusDebugEnabled )
            RefsStatusDebug(v51);
          RefsRaiseStatusInternal(Context1, (unsigned int)v51);
          __debugbreak();
          v57 = v56;
          result = RefsUnmapAttribute(v58, v56 + 192, v56 + 112);
          if ( (*(_BYTE *)(v57 + 84) & 2) != 0 )
            result = RefsUnmapAttribute(v59, v57 + 192, v57 + 112);
          if ( (*(_BYTE *)(v57 + 84) & 1) != 0 )
            return RefsCleanupAttributeContext(*(_QWORD *)(v57 + 152), v57 + 192);
          return result;
        }
        goto LABEL_182;
      }
      if ( v51 < 0 )
      {
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          WPP_SF_D(
            WPP_GLOBAL_Control->AttachedDevice,
            34,
            WPP_3e5fcb63d1a135eac59067d9d65bc2e5_Traceguids,
            (unsigned int)v51);
        goto LABEL_181;
      }
    }
LABEL_182:
    *(_DWORD *)(v11 + 168) |= 4u;
    goto LABEL_183;
  }
  v18 = *(_QWORD *)(CurrentStackLocation->Parameters.WMI.ProviderId + 8);
  v67 = v18;
  RequiredPrivileges.PrivilegeCount = 1;
  RequiredPrivileges.Control = 1;
  v66 = 35;
  RequiredPrivileges.Privilege[0].Luid = (LUID)35LL;
  RequiredPrivileges.Privilege[0].Attributes = 0;
  if ( (*(_DWORD *)(v18 + 20) & 0x10102) != 0 && (*(_DWORD *)(v18 + 12) & 4) != 0
    || (v19 = RefsEffectiveMode(Irp, Irp->Tail.Overlay.CurrentStackLocation, 0),
        SePrivilegeCheck(&RequiredPrivileges, (PSECURITY_SUBJECT_CONTEXT)(v67 + 32), v19)) )
  {
    *(_WORD *)(a4 + 88) |= 0x400u;
    goto LABEL_39;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_3e5fcb63d1a135eac59067d9d65bc2e5_Traceguids, 3221225569LL);
  }
  if ( RefsStatusDebugEnabled )
    RefsStatusDebug(-1073741727);
  return 3221225569LL;
}

```

## disassembly

```asm
0x1c009f2c8  push    rbx
0x1c009f2ca  push    rsi
0x1c009f2cb  push    rdi
0x1c009f2cc  push    r12
0x1c009f2ce  push    r13
0x1c009f2d0  push    r14
0x1c009f2d2  push    r15
0x1c009f2d4  sub     rsp, 1A0h
0x1c009f2db  mov     rax, cs:__security_cookie
0x1c009f2e2  xor     rax, rsp
0x1c009f2e5  mov     [rsp+1D8h+var_48], rax
0x1c009f2ed  mov     r14, r9
0x1c009f2f0  mov     r13, r8
0x1c009f2f3  mov     rsi, rdx
0x1c009f2f6  mov     [rsp+1D8h+Irp], rdx
0x1c009f2fe  mov     rdi, rcx
0x1c009f301  mov     [rsp+1D8h+var_140], rcx
0x1c009f309  mov     r12, [rsp+1D8h+ReparseBuffer]
0x1c009f311  mov     [rsp+1D8h+var_150], r12
0x1c009f319  mov     rax, [rsp+1D8h+arg_30]
0x1c009f321  mov     [rsp+1D8h+var_148], rax
0x1c009f329  mov     rbx, [r8+78h]
0x1c009f32d  mov     r15, [rdx+0B8h]
0x1c009f334  xor     edx, edx; Val
0x1c009f336  mov     r8d, 0D0h; Size
0x1c009f33c  lea     rcx, [rsp+1D8h+var_118]; void *
0x1c009f344  call    memset
0x1c009f349  xorps   xmm0, xmm0
0x1c009f34c  movups  [rsp+1D8h+var_168], xmm0
0x1c009f351  xor     eax, eax
0x1c009f353  mov     [rsp+1D8h+var_184], eax
0x1c009f357  movzx   ecx, [rsp+1D8h+arg_20]; BufferLength
0x1c009f35f  mov     rdx, r12; ReparseBuffer
0x1c009f362  call    cs:__imp_FsRtlValidateReparsePointBuffer
0x1c009f369  nop     dword ptr [rax+rax+00h]
0x1c009f36e  mov     [rsp+1D8h+Status], eax
0x1c009f372  xor     r8d, r8d
0x1c009f375  test    eax, eax
0x1c009f377  jns     loc_1C009F400
0x1c009f37d  lea     rcx, WPP_GLOBAL_Control
0x1c009f384  mov     r10, cs:WPP_GLOBAL_Control
0x1c009f38b  cmp     r10, rcx
0x1c009f38e  jz      short loc_1C009F3B8
0x1c009f390  test    dword ptr [r10+2Ch], 100h
0x1c009f398  jz      short loc_1C009F3B8
0x1c009f39a  cmp     byte ptr [r10+29h], 4
0x1c009f39f  jb      short loc_1C009F3B8
0x1c009f3a1  lea     edx, [r8+10h]
0x1c009f3a5  mov     r9d, eax
0x1c009f3a8  lea     r8, WPP_3e5fcb63d1a135eac59067d9d65bc2e5_Traceguids
0x1c009f3af  mov     rcx, [r10+18h]
0x1c009f3b3  call    WPP_SF_D
0x1c009f3b8  mov     al, cs:RefsStatusDebugEnabled
0x1c009f3be  test    al, al
0x1c009f3c0  jz      short loc_1C009F3D8
0x1c009f3c2  mov     r8d, 191h
0x1c009f3c8  lea     rdx, aMountsupC; "MountSup.c"
0x1c009f3cf  mov     ecx, [rsp+1D8h+Status]; Status
0x1c009f3d3  call    RefsStatusDebug
0x1c009f3d8  mov     eax, [rsp+1D8h+Status]
0x1c009f3dc  mov     rcx, [rsp+1D8h+var_48]
0x1c009f3e4  xor     rcx, rsp; StackCookie
0x1c009f3e7  call    __security_check_cookie
0x1c009f3ec  add     rsp, 1A0h
0x1c009f3f3  pop     r15
0x1c009f3f5  pop     r14
0x1c009f3f7  pop     r13
0x1c009f3f9  pop     r12
0x1c009f3fb  pop     rdi
0x1c009f3fc  pop     rsi
0x1c009f3fd  pop     rbx
0x1c009f3fe  retn
0x1c009f400  mov     r12d, [r12]
0x1c009f404  mov     rsi, [rsi+18h]
0x1c009f408  cmp     r12d, 0A0000003h
0x1c009f40f  jnz     short loc_1C009F482
0x1c009f411  cmp     byte ptr [r14+50h], 3
0x1c009f416  jz      short loc_1C009F482
0x1c009f418  lea     rcx, WPP_GLOBAL_Control
0x1c009f41f  mov     r10, cs:WPP_GLOBAL_Control
0x1c009f426  cmp     r10, rcx
0x1c009f429  jz      short loc_1C009F457
0x1c009f42b  test    dword ptr [r10+2Ch], 100h
0x1c009f433  jz      short loc_1C009F457
0x1c009f435  cmp     byte ptr [r10+29h], 4
0x1c009f43a  jb      short loc_1C009F457
0x1c009f43c  mov     edx, 11h
0x1c009f441  mov     r9d, 0C0000103h
0x1c009f447  lea     r8, WPP_3e5fcb63d1a135eac59067d9d65bc2e5_Traceguids
0x1c009f44e  mov     rcx, [r10+18h]
0x1c009f452  call    WPP_SF_D
0x1c009f457  mov     cl, cs:RefsStatusDebugEnabled
0x1c009f45d  test    cl, cl
0x1c009f45f  jz      short loc_1C009F478
0x1c009f461  mov     r8d, 1AEh
0x1c009f467  lea     rdx, aMountsupC; "MountSup.c"
0x1c009f46e  mov     ecx, 0C0000103h; Status
0x1c009f473  call    RefsStatusDebug
0x1c009f478  mov     eax, 0C0000103h
0x1c009f47d  jmp     loc_1C009F3DC
0x1c009f482  cmp     r12d, 0A000000Ch
0x1c009f489  jnz     loc_1C009F626
0x1c009f48f  mov     rax, [rsp+1D8h+var_150]
0x1c009f497  and     dword ptr [rax+10h], 0FFFFFFFh
0x1c009f49e  cmp     byte ptr [rdi+28h], 0Dh
0x1c009f4a2  jnz     short loc_1C009F51E
0x1c009f4a4  mov     ecx, 400h
0x1c009f4a9  test    [r14+58h], cx
0x1c009f4ae  jnz     loc_1C009F626
0x1c009f4b4  lea     rcx, WPP_GLOBAL_Control
0x1c009f4bb  mov     r10, cs:WPP_GLOBAL_Control
0x1c009f4c2  cmp     r10, rcx
0x1c009f4c5  jz      short loc_1C009F4F3
0x1c009f4c7  test    dword ptr [r10+2Ch], 100h
0x1c009f4cf  jz      short loc_1C009F4F3
0x1c009f4d1  cmp     byte ptr [r10+29h], 4
0x1c009f4d6  jb      short loc_1C009F4F3
0x1c009f4d8  mov     edx, 12h
0x1c009f4dd  mov     r9d, 0C0000022h
0x1c009f4e3  lea     r8, WPP_3e5fcb63d1a135eac59067d9d65bc2e5_Traceguids
0x1c009f4ea  mov     rcx, [r10+18h]
0x1c009f4ee  call    WPP_SF_D
0x1c009f4f3  mov     cl, cs:RefsStatusDebugEnabled
0x1c009f4f9  test    cl, cl
0x1c009f4fb  jz      short loc_1C009F514
0x1c009f4fd  mov     r8d, 1CAh
0x1c009f503  lea     rdx, aMountsupC; "MountSup.c"
0x1c009f50a  mov     ecx, 0C0000022h; Status
0x1c009f50f  call    RefsStatusDebug
0x1c009f514  mov     eax, 0C0000022h
0x1c009f519  jmp     loc_1C009F3DC
0x1c009f51e  mov     rax, [r15+8]
0x1c009f522  mov     rcx, [rax+8]
0x1c009f526  mov     [rsp+1D8h+var_170], rcx
0x1c009f52b  mov     r15d, 1
0x1c009f531  mov     [rsp+1D8h+RequiredPrivileges.PrivilegeCount], r15d
0x1c009f539  mov     [rsp+1D8h+RequiredPrivileges.Control], r15d
0x1c009f541  mov     [rsp+1D8h+var_178], 23h ; '#'
0x1c009f54a  mov     rax, [rsp+1D8h+var_178]
0x1c009f54f  mov     qword ptr [rsp+1D8h+RequiredPrivileges.Privilege.Luid.LowPart], rax
0x1c009f557  mov     [rsp+1D8h+RequiredPrivileges.Privilege.Attributes], r8d
0x1c009f55f  test    dword ptr [rcx+14h], 10102h
0x1c009f566  jz      short loc_1C009F573
0x1c009f568  mov     eax, [rcx+0Ch]
0x1c009f56b  test    al, 4
0x1c009f56d  jnz     loc_1C009F61A
0x1c009f573  mov     rax, [rsp+1D8h+Irp]
0x1c009f57b  mov     rdx, [rax+0B8h]
0x1c009f582  mov     rcx, rax
0x1c009f585  call    RefsEffectiveMode
0x1c009f58a  mov     r8b, al; AccessMode
0x1c009f58d  mov     rdx, [rsp+1D8h+var_170]
0x1c009f592  add     rdx, 20h ; ' '; SubjectSecurityContext
0x1c009f596  lea     rcx, [rsp+1D8h+RequiredPrivileges]; RequiredPrivileges
0x1c009f59e  call    cs:__imp_SePrivilegeCheck
0x1c009f5a5  nop     dword ptr [rax+rax+00h]
0x1c009f5aa  xor     r8d, r8d
0x1c009f5ad  test    al, al
0x1c009f5af  jnz     short loc_1C009F61A
0x1c009f5b1  lea     rcx, WPP_GLOBAL_Control
0x1c009f5b8  mov     r10, cs:WPP_GLOBAL_Control
0x1c009f5bf  cmp     r10, rcx
0x1c009f5c2  jz      short loc_1C009F5EF
0x1c009f5c4  test    dword ptr [r10+2Ch], 100h
0x1c009f5cc  jz      short loc_1C009F5EF
0x1c009f5ce  cmp     byte ptr [r10+29h], 4
0x1c009f5d3  jb      short loc_1C009F5EF
0x1c009f5d5  lea     edx, [r8+13h]
0x1c009f5d9  mov     r9d, 0C0000061h
0x1c009f5df  lea     r8, WPP_3e5fcb63d1a135eac59067d9d65bc2e5_Traceguids
0x1c009f5e6  mov     rcx, [r10+18h]
0x1c009f5ea  call    WPP_SF_D
0x1c009f5ef  mov     cl, cs:RefsStatusDebugEnabled
0x1c009f5f5  test    cl, cl
0x1c009f5f7  jz      short loc_1C009F610
0x1c009f5f9  mov     r8d, 1EDh
0x1c009f5ff  lea     rdx, aMountsupC; "MountSup.c"
0x1c009f606  mov     ecx, 0C0000061h; Status
0x1c009f60b  call    RefsStatusDebug
0x1c009f610  mov     eax, 0C0000061h
0x1c009f615  jmp     loc_1C009F3DC
0x1c009f61a  mov     ecx, 400h
0x1c009f61f  or      [r14+58h], cx
0x1c009f624  jmp     short loc_1C009F62C
0x1c009f626  mov     r15d, 1
0x1c009f62c  or      [rdi+8], r15d
0x1c009f630  mov     eax, [r14+54h]
0x1c009f634  mov     [rdi+0C8h], eax
0x1c009f63a  mov     eax, [r13+130h]
0x1c009f641  bt      eax, 10h
0x1c009f645  jnb     short loc_1C009F64F
0x1c009f647  mov     r9d, 0C000026Eh
0x1c009f64d  jmp     short loc_1C009F660
0x1c009f64f  and     eax, 1000000h
0x1c009f654  neg     eax
0x1c009f656  sbb     r9d, r9d
0x1c009f659  and     r9d, 0C0000008h
0x1c009f660  mov     [rsp+1D8h+Status], r9d
0x1c009f665  test    r9d, r9d
0x1c009f668  jns     short loc_1C009F6CC
0x1c009f66a  lea     rcx, WPP_GLOBAL_Control
0x1c009f671  mov     r10, cs:WPP_GLOBAL_Control
0x1c009f678  cmp     r10, rcx
0x1c009f67b  jz      short loc_1C009F6A3
0x1c009f67d  mov     eax, [r10+2Ch]
0x1c009f681  bt      eax, 8
0x1c009f685  jnb     short loc_1C009F6A3
0x1c009f687  cmp     byte ptr [r10+29h], 4
0x1c009f68c  jb      short loc_1C009F6A3
0x1c009f68e  mov     edx, 14h
0x1c009f693  lea     r8, WPP_3e5fcb63d1a135eac59067d9d65bc2e5_Traceguids
0x1c009f69a  mov     rcx, [r10+18h]
0x1c009f69e  call    WPP_SF_D
0x1c009f6a3  mov     al, cs:RefsStatusDebugEnabled
0x1c009f6a9  test    al, al
0x1c009f6ab  jz      loc_1C00A0149
0x1c009f6b1  mov     r8d, 214h
0x1c009f6b7  lea     rdx, aMountsupC; "MountSup.c"
0x1c009f6be  mov     ecx, [rsp+1D8h+Status]; Status
0x1c009f6c2  call    RefsStatusDebug
0x1c009f6c7  jmp     loc_1C00A0149
0x1c009f6cc  mov     eax, [rbx+4]
0x1c009f6cf  test    r15b, al
0x1c009f6d2  jz      short loc_1C009F741
0x1c009f6d4  lea     rcx, WPP_GLOBAL_Control
0x1c009f6db  mov     r10, cs:WPP_GLOBAL_Control
0x1c009f6e2  cmp     r10, rcx
0x1c009f6e5  jz      short loc_1C009F713
0x1c009f6e7  mov     eax, [r10+2Ch]
0x1c009f6eb  bt      eax, 8
0x1c009f6ef  jnb     short loc_1C009F713
0x1c009f6f1  cmp     byte ptr [r10+29h], 4
0x1c009f6f6  jb      short loc_1C009F713
0x1c009f6f8  mov     edx, 15h
0x1c009f6fd  mov     r9d, 0C0000123h
0x1c009f703  lea     r8, WPP_3e5fcb63d1a135eac59067d9d65bc2e5_Traceguids
0x1c009f70a  mov     rcx, [r10+18h]
0x1c009f70e  call    WPP_SF_D
0x1c009f713  mov     al, cs:RefsStatusDebugEnabled
0x1c009f719  test    al, al
0x1c009f71b  jz      short loc_1C009F734
0x1c009f71d  mov     r8d, 21Eh
0x1c009f723  lea     rdx, aMountsupC; "MountSup.c"
0x1c009f72a  mov     ecx, 0C0000123h; Status
0x1c009f72f  call    RefsStatusDebug
0x1c009f734  mov     [rsp+1D8h+Status], 0C0000123h
0x1c009f73c  jmp     loc_1C00A0149
0x1c009f741  mov     rcx, rbx
0x1c009f744  call    RefsIsFileOpen
0x1c009f749  test    al, al
0x1c009f74b  jnz     short loc_1C009F7BA
0x1c009f74d  lea     rcx, WPP_GLOBAL_Control
0x1c009f754  mov     r10, cs:WPP_GLOBAL_Control
0x1c009f75b  cmp     r10, rcx
0x1c009f75e  jz      short loc_1C009F78C
0x1c009f760  mov     eax, [r10+2Ch]
0x1c009f764  bt      eax, 8
0x1c009f768  jnb     short loc_1C009F78C
0x1c009f76a  cmp     byte ptr [r10+29h], 4
0x1c009f76f  jb      short loc_1C009F78C
0x1c009f771  mov     edx, 16h
0x1c009f776  mov     r9d, 0C0000128h
0x1c009f77c  lea     r8, WPP_3e5fcb63d1a135eac59067d9d65bc2e5_Traceguids
0x1c009f783  mov     rcx, [r10+18h]
0x1c009f787  call    WPP_SF_D
0x1c009f78c  mov     al, cs:RefsStatusDebugEnabled
0x1c009f792  test    al, al
0x1c009f794  jz      short loc_1C009F7AD
0x1c009f796  mov     r8d, 224h
0x1c009f79c  lea     rdx, aMountsupC; "MountSup.c"
0x1c009f7a3  mov     ecx, 0C0000128h; Status
0x1c009f7a8  call    RefsStatusDebug
0x1c009f7ad  mov     [rsp+1D8h+Status], 0C0000128h
0x1c009f7b5  jmp     loc_1C00A0149
0x1c009f7ba  mov     al, [r14+50h]
0x1c009f7be  cmp     al, 3
0x1c009f7c0  jnz     loc_1C009F876
0x1c009f7c6  mov     [rsp+1D8h+var_17F], r8b
0x1c009f7cb  mov     [rsp+1D8h+var_180], r8b
0x1c009f7d0  mov     ecx, r12d
0x1c009f7d3  call    cs:__imp_FsRtlIsNonEmptyDirectoryReparsePointAllowed
0x1c009f7da  nop     dword ptr [rax+rax+00h]
0x1c009f7df  xor     r8d, r8d
0x1c009f7e2  test    al, al
0x1c009f7e4  jnz     loc_1C009F9F1
0x1c009f7ea  lea     r9, [rsp+1D8h+var_180]
0x1c009f7ef  lea     r8, [rsp+1D8h+var_17F]
0x1c009f7f4  mov     rdx, rbx
0x1c009f7f7  mov     rcx, rdi
0x1c009f7fa  call    RefsIsFileDeleteable
0x1c009f7ff  xor     r8d, r8d
0x1c009f802  test    al, al
0x1c009f804  jnz     loc_1C009F9F1
0x1c009f80a  lea     rcx, WPP_GLOBAL_Control
0x1c009f811  mov     r10, cs:WPP_GLOBAL_Control
0x1c009f818  cmp     r10, rcx
0x1c009f81b  jz      short loc_1C009F848
0x1c009f81d  mov     eax, [r10+2Ch]
0x1c009f821  bt      eax, 8
0x1c009f825  jnb     short loc_1C009F848
  ... truncated ...
```
