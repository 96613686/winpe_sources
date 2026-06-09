# RxFindOrCreateConnections

- ea: `0x14005f400`
- end: `0x14006054b`
- name: `RxFindOrCreateConnections`
- size: `4427`
- prototype: `NTSTATUS __stdcall(PRX_CONTEXT RxContext, PIRP Irp, PUNICODE_STRING CanonicalName, NET_ROOT_TYPE NetRootType, BOOLEAN TreeConnect, PUNICODE_STRING LocalNetRootName, PUNICODE_STRING FilePathName, PLOCK_HOLDING_STATE LockState, PRX_CONNECTION_ID RxConnectionId)`
- caller_count: `1`
- callee_count: `27`
- tags: ``

## callers

- `0x140078fe0`

## callees

- `0x14000b950`
- `0x140010e40`
- `0x140012370`
- `0x140016e20`
- `0x140016e70`
- `0x140017280`
- `0x140017a8c`
- `0x14001b178`
- `0x140020f2c`
- `0x140021178`
- `0x140021710`
- `0x140021cd0`
- `0x140021f0c`
- `0x140025d00`
- `0x140058f00`
- `0x14005f110`
- `0x14005f400`
- `0x140060f10`
- `0x140061620`
- `0x140061b00`
- `0x1400621c0`
- `0x14006e0d0`
- `0x140072070`
- `0x140077c50`
- `0x140078460`
- `0x140078a90`
- `0x14007a310`

## import_xrefs

- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14005fdae`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14006014e`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14006028d`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14005fdae`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14006014e`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14006028d`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005f924`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005fb16`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005fbbf`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005fd88`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005ffec`
- `ntoskrnl!ExReleaseResourceLite` at `0x140060128`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006045a`
- `ntoskrnl!ExReleaseResourceLite` at `0x14007afd7`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005f924`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005fb16`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005fbbf`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005fd88`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005ffec`
- `ntoskrnl!ExReleaseResourceLite` at `0x140060128`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006045a`
- `ntoskrnl!ExReleaseResourceLite` at `0x14007afd7`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14005f995`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14005facc`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14005fb91`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14005fd63`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400600c2`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14005f995`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14005facc`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14005fb91`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14005fd63`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400600c2`
- `ntoskrnl!KeBugCheckEx` at `0x14005ff89`
- `ntoskrnl!KeBugCheckEx` at `0x14005ff89`

## pseudocode

```c
NTSTATUS __stdcall RxFindOrCreateConnections(
        PRX_CONTEXT RxContext,
        PIRP Irp,
        PUNICODE_STRING CanonicalName,
        NET_ROOT_TYPE NetRootType,
        BOOLEAN TreeConnect,
        PUNICODE_STRING LocalNetRootName,
        PUNICODE_STRING FilePathName,
        PLOCK_HOLDING_STATE LockState,
        PRX_CONNECTION_ID RxConnectionId)
{
  PUNICODE_STRING v9; // r9
  PRX_CONTEXT v10; // rdx
  int AdditionalReferenceForDeleteFsctlTaken; // edi
  PV_NET_ROOT VNetRoot; // r15
  struct _LIST_ENTRY *Flink; // r14
  PRX_CONNECTION_ID v14; // rbx
  wchar_t *Buffer; // r8
  wchar_t *v16; // rcx
  unsigned int v17; // eax
  unsigned int Length; // edx
  unsigned __int16 v19; // ax
  unsigned __int16 v20; // ax
  LOCK_HOLDING_STATE *v21; // rsi
  PRX_CONTEXT v22; // rdx
  PNET_ROOT v23; // r14
  PV_NET_ROOT v24; // rbx
  int v25; // ecx
  ULONG PrefixOffsetInBytes; // eax
  int v27; // ebx
  PRX_CONTEXT v28; // r15
  int v29; // ecx
  __int64 v30; // rbx
  __int64 v31; // rsi
  LONG HighPart; // ecx
  int Flink_high; // eax
  int v34; // edi
  struct _RX_CONNECTION_ID *v35; // r9
  wchar_t *v36; // rcx
  wchar_t *v37; // r8
  wchar_t *v38; // rax
  wchar_t *i; // rdx
  PSRV_CALL v40; // rax
  int v41; // r8d
  PNON_PAGED_FCB NonPagedFcb; // rsi
  struct _LIST_ENTRY *v43; // r14
  __int64 v44; // rdx
  __int64 ConnectionConstructionContext; // rbx
  __int64 v46; // r8
  PRX_CONTEXT v47; // r9
  struct _LIST_ENTRY *v48; // rax
  enum _LOCK_HOLDING_STATE v49; // eax
  char v50; // si
  struct _SRV_CALL *v51; // rdx
  enum _LOCK_HOLDING_STATE v52; // eax
  int v53; // eax
  int v54; // eax
  int NodeTypeCode; // ecx
  int v56; // eax
  PNET_ROOT v57; // rcx
  __int64 v58; // rdx
  __int64 v59; // r8
  __int64 v61; // r8
  PSZ FileName; // rdx
  __int64 v63; // rax
  enum _LOCK_HOLDING_STATE *FilePath; // [rsp+20h] [rbp-D8h]
  __int64 v65; // [rsp+40h] [rbp-B8h]
  void *v66; // [rsp+48h] [rbp-B0h]
  void *v67; // [rsp+50h] [rbp-A8h]
  PV_NET_ROOT v68; // [rsp+58h] [rbp-A0h]
  wchar_t *v69; // [rsp+60h] [rbp-98h]
  UNICODE_STRING Name; // [rsp+70h] [rbp-88h] BYREF
  __int64 v71; // [rsp+80h] [rbp-78h]
  UNICODE_STRING v72; // [rsp+88h] [rbp-70h] BYREF
  UNICODE_STRING v73; // [rsp+A0h] [rbp-58h] BYREF
  char v74[72]; // [rsp+B0h] [rbp-48h] BYREF
  struct _LIST_ENTRY *v76; // [rsp+108h] [rbp+10h]
  int TreeConnecta; // [rsp+120h] [rbp+28h]

  v9 = CanonicalName;
  v10 = RxContext;
  AdditionalReferenceForDeleteFsctlTaken = -1073741823;
  VNetRoot = 0;
  TreeConnecta = 0;
  Flink = RxContext->NonPagedFcb[1].HeaderResource.SystemResourcesList.Flink;
  v76 = Flink;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) == 0
    || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
  {
    v14 = RxConnectionId;
  }
  else
  {
    v14 = RxConnectionId;
    WPP_SF_iiZ(
      WPP_GLOBAL_Control->AttachedDevice,
      (_DWORD)RxContext,
      (_DWORD)CanonicalName,
      *RxConnectionId,
      *(_QWORD *)&RxConnectionId[1],
      (__int64)CanonicalName);
    v9 = CanonicalName;
    v10 = RxContext;
  }
  if ( FilePathName )
    *FilePathName = *v9;
  if ( LocalNetRootName )
    *LocalNetRootName = 0;
  Buffer = v9->Buffer;
  if ( Buffer[1] == 59 )
  {
    v16 = Buffer + 2;
    v17 = 0;
    Length = v9->Length;
    if ( Length > 4 )
      v17 = Length - 4;
    while ( 1 )
    {
      if ( !v17 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            12,
            WPP_8f40199b670e3a186f0ad2764a4463aa_Traceguids,
            3221225523LL);
        }
        return -1073741773;
      }
      if ( *v16 == 92 )
        break;
      v17 -= 2;
      ++v16;
    }
    if ( LocalNetRootName )
    {
      LocalNetRootName->Buffer = Buffer;
      v19 = (_WORD)v16 - LOWORD(v9->Buffer);
      LocalNetRootName->Length = v19;
      LocalNetRootName->MaximumLength = v19;
    }
    v10 = RxContext;
    if ( FilePathName )
    {
      FilePathName->Buffer = v16;
      v20 = LOWORD(v9->Buffer) + v9->Length - (_WORD)v16;
      FilePathName->Length = v20;
      FilePathName->MaximumLength = v20;
    }
  }
  Name = 0;
  v72 = 0;
  v21 = LockState;
LABEL_18:
  if ( VNetRoot )
  {
    NodeTypeCode = VNetRoot->NodeTypeCode;
    if ( NodeTypeCode != 60176 && NodeTypeCode != 60177 && NodeTypeCode != 60178 )
      KeBugCheckEx(0x27u, 0x3A4u, (ULONG_PTR)VNetRoot, VNetRoot->NodeTypeCode, 0);
    RxDereference(VNetRoot, LHS_LockNotHeld);
    v10 = RxContext;
  }
  if ( v10->TrackerHistory[4].Flags <= 8 )
  {
    LOBYTE(FilePath) = 0;
    VNetRoot = (PV_NET_ROOT)RxPrefixTableLookupNameEx(Flink, FilePathName, v74, v14, (_DWORD)FilePath);
    v68 = VNetRoot;
    v22 = RxContext;
    ++RxContext->TrackerHistory[4].Flags;
    while ( 1 )
    {
      while ( 1 )
      {
        v23 = 0;
        v67 = 0;
        v24 = 0;
        v66 = 0;
        *(_QWORD *)&v22->TrackerHistory[0].Flags = 0;
        v22->TrackerHistory[0].FileName = 0;
        *(_QWORD *)&v22->TrackerHistory[0].AcquireRelease = 0;
        BYTE4(v22->TrackerHistory[4].FileName) = NetRootType;
        if ( VNetRoot )
        {
          v25 = VNetRoot->NodeTypeCode;
          if ( v25 == 60176 )
          {
            v24 = VNetRoot;
            v66 = VNetRoot;
            if ( (BYTE6(v22->TrackerHistory[4].FileName) & 0x10) == 0
              || LOWORD(VNetRoot->PrefixEntry.MemberQLinks.Flink) < WORD1(VNetRoot->PrefixEntry.MemberQLinks.Flink) )
            {
              while ( 1 )
              {
                PrefixOffsetInBytes = VNetRoot->PrefixOffsetInBytes;
                if ( PrefixOffsetInBytes != 1 )
                  break;
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                {
                  WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_8f40199b670e3a186f0ad2764a4463aa_Traceguids);
                }
                ExReleaseResourceLite((PERESOURCE)&v76[1].Blink);
                HIDWORD(v65) = ++TreeConnecta;
                *LockState = LHS_LockNotHeld;
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                {
                  WPP_SF_qqZ(
                    WPP_GLOBAL_Control->AttachedDevice,
                    17,
                    (unsigned int)WPP_8f40199b670e3a186f0ad2764a4463aa_Traceguids,
                    (_DWORD)RxContext,
                    (char)VNetRoot,
                    (__int64)VNetRoot->pUserName);
                }
                RxWaitForStableCondition(
                  (PRX_BLOCK_CONDITION)RxContext,
                  (PLIST_ENTRY)&VNetRoot->PrefixOffsetInBytes,
                  (PRX_CONTEXT)&VNetRoot->NetRootListEntry.Blink,
                  0);
                AdditionalReferenceForDeleteFsctlTaken = v53;
                LODWORD(v65) = v53;
                if ( v53 )
                {
                  v21 = LockState;
                  RxDereference(VNetRoot, *LockState);
                  v27 = 1172;
                  goto LABEL_29;
                }
                ExAcquireResourceSharedLite((PERESOURCE)&v76[1].Blink, 1u);
                v21 = LockState;
                *LockState = LHS_SharedLockHeld;
              }
              AdditionalReferenceForDeleteFsctlTaken = 0;
              if ( PrefixOffsetInBytes == 3 )
                goto LABEL_45;
              AdditionalReferenceForDeleteFsctlTaken = VNetRoot->AdditionalReferenceForDeleteFsctlTaken;
              if ( AdditionalReferenceForDeleteFsctlTaken >= 0 )
                AdditionalReferenceForDeleteFsctlTaken = -1073741634;
              LODWORD(v65) = AdditionalReferenceForDeleteFsctlTaken;
              RxDereference(VNetRoot, *v21);
              v27 = 1194;
              goto LABEL_29;
            }
            RxDereference(VNetRoot, *v21);
            VNetRoot = 0;
            v68 = 0;
            v24 = 0;
            v66 = 0;
            v67 = 0;
LABEL_45:
            v22 = RxContext;
          }
          else
          {
            v29 = v25 - 60177;
            if ( v29 )
            {
              if ( v29 == 1 )
              {
                v30 = *((_QWORD *)&VNetRoot->1 + 4);
                v67 = (void *)v30;
                v31 = *(_QWORD *)(v30 + 32);
                v66 = (void *)v31;
                while ( 1 )
                {
                  HighPart = VNetRoot->PrefixEntry.ConnectionId.Luid.HighPart;
                  if ( HighPart != 1 )
                    break;
                  Flink = v76;
                  ExReleaseResourceLite((PERESOURCE)&v76[1].Blink);
                  *LockState = LHS_LockNotHeld;
                  HIDWORD(v65) = ++TreeConnecta;
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
                    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                  {
                    WPP_SF_qqZ(
                      WPP_GLOBAL_Control->AttachedDevice,
                      13,
                      (unsigned int)WPP_8f40199b670e3a186f0ad2764a4463aa_Traceguids,
                      (_DWORD)RxContext,
                      (char)VNetRoot,
                      (__int64)&VNetRoot->PrefixOffsetInBytes);
                  }
                  RxWaitForStableCondition(
                    (PRX_BLOCK_CONDITION)RxContext,
                    (PLIST_ENTRY)&VNetRoot->PrefixEntry.ConnectionId.Luid.HighPart,
                    (PRX_CONTEXT)((char *)&VNetRoot[1].1 + 72),
                    0);
                  AdditionalReferenceForDeleteFsctlTaken = v54;
                  LODWORD(v65) = v54;
                  if ( v54 )
                  {
                    RxDereference(VNetRoot, *LockState);
                    v27 = 1014;
                    v21 = LockState;
                    goto LABEL_31;
                  }
                  ExAcquireResourceSharedLite((PERESOURCE)&v76[1].Blink, 1u);
                  *LockState = LHS_SharedLockHeld;
                }
                if ( HighPart == 3
                  && *(_DWORD *)(v30 + 148) == 3
                  && *(_DWORD *)(v31 + 224) == 3
                  && *(PNON_PAGED_FCB *)(v31 + 48) == RxContext->NonPagedFcb )
                {
                  *(_QWORD *)&RxContext->TrackerHistory[0].AcquireRelease = v31;
                  RxContext->TrackerHistory[0].FileName = (PSZ)v30;
                  *(_QWORD *)&RxContext->TrackerHistory[0].Flags = VNetRoot;
                  AdditionalReferenceForDeleteFsctlTaken = 0;
                  LODWORD(v65) = 0;
                  v27 = 1035;
                  v21 = LockState;
                }
                else
                {
                  AdditionalReferenceForDeleteFsctlTaken = -1073741634;
                  LODWORD(v65) = -1073741634;
                  if ( HighPart != 3 )
                  {
                    AdditionalReferenceForDeleteFsctlTaken = *(_DWORD *)&VNetRoot->NamePrefix.Length;
                    LODWORD(v65) = AdditionalReferenceForDeleteFsctlTaken;
                  }
                  RxDereference(VNetRoot, *LockState);
                  v27 = 1049;
                  v21 = LockState;
                }
                goto LABEL_30;
              }
            }
            else
            {
              v23 = (PNET_ROOT)VNetRoot;
              v67 = VNetRoot;
              v24 = (PV_NET_ROOT)*((_QWORD *)&VNetRoot->1 + 4);
              v66 = v24;
              while ( 1 )
              {
                Flink_high = HIDWORD(VNetRoot->PrefixEntry.MemberQLinks.Flink);
                if ( Flink_high != 1 )
                  break;
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                {
                  WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_8f40199b670e3a186f0ad2764a4463aa_Traceguids);
                }
                ExReleaseResourceLite((PERESOURCE)&v76[1].Blink);
                *LockState = LHS_LockNotHeld;
                HIDWORD(v65) = ++TreeConnecta;
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                {
                  WPP_SF_qqZ(
                    WPP_GLOBAL_Control->AttachedDevice,
                    15,
                    (unsigned int)WPP_8f40199b670e3a186f0ad2764a4463aa_Traceguids,
                    (_DWORD)RxContext,
                    (char)VNetRoot,
                    (__int64)&VNetRoot->NamePrefix.Buffer);
                }
                RxWaitForStableCondition(
                  (PRX_BLOCK_CONDITION)RxContext,
                  (PLIST_ENTRY)((char *)&VNetRoot->PrefixEntry.MemberQLinks.Flink + 4),
                  (PRX_CONTEXT)&VNetRoot->PrefixEntry.Prefix,
                  0);
                AdditionalReferenceForDeleteFsctlTaken = v56;
                LODWORD(v65) = v56;
                if ( v56 )
                {
                  RxDereference(VNetRoot, *LockState);
                  v67 = 0;
                  v27 = 1080;
                  v21 = LockState;
                  goto LABEL_30;
                }
                ExAcquireResourceSharedLite((PERESOURCE)&v76[1].Blink, 1u);
                v21 = LockState;
                *LockState = LHS_SharedLockHeld;
              }
              if ( Flink_high != 3 )
              {
                AdditionalReferenceForDeleteFsctlTaken = (int)VNetRoot->PrefixEntry.MemberQLinks.Blink;
                goto LABEL_45;
              }
              AdditionalReferenceForDeleteFsctlTaken = 0;
              v22 = RxContext;
              if ( (BYTE6(RxContext->TrackerHistory[4].FileName) & 0x10) != 0
                && LOWORD(v24->PrefixEntry.MemberQLinks.Flink) >= WORD1(v24->PrefixEntry.MemberQLinks.Flink) )
              {
                if ( *v21 == LHS_SharedLockHeld )
                {
LABEL_107:
                  Flink = v76;
                  ExReleaseResourceLite((PERESOURCE)&v76[1].Blink);
                  HIDWORD(v65) = ++TreeConnecta;
                  ExAcquireResourceExclusiveLite((PERESOURCE)&v76[1].Blink, 1u);
                  *v21 = LHS_ExclusiveLockHeld;
                }
                else
                {
                  RxUpperFinalizeNetRoot(VNetRoot);
                  RxDereference(VNetRoot, *v21);
                  VNetRoot = 0;
                  v68 = 0;
                  v66 = 0;
                  v67 = 0;
                  Flink = v76;
                }
                v10 = RxContext;
                v14 = RxConnectionId;
                goto LABEL_18;
              }
            }
          }
        }
        if ( v24 && v24->PrefixOffsetInBytes == 3 && (PNON_PAGED_FCB)*((_QWORD *)&v24->1 + 6) != v22->NonPagedFcb )
        {
          RxDereference(v24, *v21);
          AdditionalReferenceForDeleteFsctlTaken = -1073741620;
          LODWORD(v65) = -1073741620;
          v27 = 1211;
          goto LABEL_30;
        }
        if ( *v21 == LHS_SharedLockHeld )
          goto LABEL_107;
        v34 = TreeConnecta;
        if ( TreeConnecta )
        {
          if ( !VNetRoot )
            goto LABEL_117;
          if ( VNetRoot->NodeTypeCode == 60176 )
          {
            v57 = (PNET_ROOT)v24;
LABEL_159:
            RxDereference(v57, LHS_LockNotHeld);
          }
          else if ( VNetRoot->NodeTypeCode == 60177 )
          {
            v57 = v23;
            goto LABEL_159;
          }
LABEL_117:
          v68 = 0;
          v66 = 0;
          v67 = 0;
          AdditionalReferenceForDeleteFsctlTaken = -1069481980;
          LODWORD(v65) = -1069481980;
          v27 = 1256;
LABEL_30:
          Flink = v76;
          goto LABEL_31;
        }
        if ( !VNetRoot )
          break;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_8f40199b670e3a186f0ad2764a4463aa_Traceguids, v24);
        }
        (*(void (__fastcall **)(PUNICODE_STRING, PV_NET_ROOT, UNICODE_STRING *, _QWORD))(*(_QWORD *)(*((_QWORD *)&v24->1 + 6) + 352LL)
                                                                                       + 488LL))(
          FilePathName,
          v24,
          &v72,
          0);
        if ( v23 )
        {
          v50 = 0;
        }
        else
        {
          v23 = RxCreateNetRoot((PSRV_CALL)v24, &v72, 0, RxConnectionId);
          v67 = v23;
          if ( !v23 )
          {
            AdditionalReferenceForDeleteFsctlTaken = -1073741670;
            LODWORD(v65) = -1073741670;
            v27 = 1292;
            goto LABEL_30;
          }
          *((_BYTE *)&v23->1 + 77) = NetRootType;
          if ( NetRootType && NetRootType == 1 )
            v23->ParameterValidationStamp = 17;
          else
            v23->ParameterValidationStamp = 7;
          RxReference(v23);
          RxDereference(v24, *v21);
          v50 = 1;
        }
        VNetRoot = RxCreateVNetRoot(RxContext, v23, CanonicalName, LocalNetRootName, (PUNICODE_STRING)RxConnectionId, 0);
        RxDereference(v23, *LockState);
        if ( !VNetRoot )
        {
          AdditionalReferenceForDeleteFsctlTaken = -1073741670;
          LODWORD(v65) = -1073741670;
          v27 = 1353;
          v21 = LockState;
          goto LABEL_30;
        }
        RxReference(VNetRoot);
        *(_QWORD *)&RxContext->TrackerHistory[0].AcquireRelease = v24;
        RxContext->TrackerHistory[0].FileName = (PSZ)v23;
        *(_QWORD *)&RxContext->TrackerHistory[0].Flags = VNetRoot;
        TreeConnecta = 1;
        HIDWORD(v65) = 1;
        v51 = 0;
        if ( v50 )
          v51 = (struct _SRV_CALL *)v23;
        AdditionalReferenceForDeleteFsctlTaken = RxConstructNetRoot(
                                                   RxContext,
                                                   v51,
                                                   (PNET_ROOT)VNetRoot,
                                                   (PV_NET_ROOT)LockState,
                                                   FilePath);
        LODWORD(v65) = AdditionalReferenceForDeleteFsctlTaken;
        v52 = *LockState;
        if ( AdditionalReferenceForDeleteFsctlTaken < 0 )
        {
          if ( v52 == LHS_LockNotHeld )
          {
            ExAcquireResourceExclusiveLite((PERESOURCE)&v76[1].Blink, 1u);
            *LockState = LHS_ExclusiveLockHeld;
          }
          if ( v50 )
            RxHandleFailedFirstNetRootConstruction(v23, VNetRoot);
          RxOrphanVNetRoot(VNetRoot, (unsigned int)AdditionalReferenceForDeleteFsctlTaken);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            WPP_SF_qqDd(
              WPP_GLOBAL_Control->AttachedDevice,
              v58,
              v59,
              RxContext,
              VNetRoot,
              AdditionalReferenceForDeleteFsctlTaken,
              VNetRoot->PrefixEntry.ConnectionId.Luid.HighPart);
          }
          v21 = LockState;
          RxDereference(VNetRoot, *LockState);
          v28 = RxContext;
          RxContext->TrackerHistory[0].FileName = 0;
          *(_QWORD *)&RxContext->TrackerHistory[0].Flags = 0;
          v27 = 1423;
          Flink = v76;
          goto LABEL_189;
        }
        if ( v52 )
        {
          v21 = LockState;
        }
        else
        {
          ExAcquireResourceSharedLite((PERESOURCE)&v76[1].Blink, 1u);
          v21 = LockState;
          *LockState = LHS_SharedLockHeld;
        }
        v68 = VNetRoot;
        v22 = RxContext;
      }
      v35 = (struct _RX_CONNECTION_ID *)BYTE6(v22->TrackerHistory[4].FileName);
      v36 = FilePathName->Buffer;
      v69 = v36;
      v37 = (wchar_t *)((char *)v36 + FilePathName->Length);
      Name.Buffer = v36;
      if ( v36 < v37 && *v36 == 92 )
      {
        v38 = v36 + 1;
        v36 = v38;
        v69 = v38;
        goto LABEL_53;
      }
      while ( 1 )
      {
        v38 = v36;
LABEL_53:
        if ( v38 >= v37 || *v36 == 92 )
          break;
        v36 = v38 + 1;
        v69 = v38 + 1;
      }
      LODWORD(i) = (unsigned __int16)v38;
      LOWORD(i) = (_WORD)v38 - LOWORD(FilePathName->Buffer);
      Name.MaximumLength = (unsigned __int16)i;
      Name.Length = (unsigned __int16)i;
      if ( ((unsigned __int8)v35 & 0x10) != 0 )
      {
        if ( v38 < v37 && *v36 == 92 )
        {
          v36 = v38 + 1;
          v69 = ++v38;
        }
        for ( i = v38; i < v37 && *v36 != 92; ++i )
        {
          v36 = i + 1;
          v69 = i + 1;
        }
        LOWORD(i) = (_WORD)i - LOWORD(FilePathName->Buffer);
        Name.MaximumLength = (unsigned __int16)i;
      }
      v73 = Name;
      v73.Length = (unsigned __int16)i;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_ZZZZ(
          WPP_GLOBAL_Control->AttachedDevice,
          (_DWORD)i,
          (_DWORD)v37,
          (_DWORD)FilePathName,
          (__int64)&Name,
          (__int64)&v73,
          0);
      }
      v40 = RxCreateSrvCall(RxContext, &Name, (PUNICODE_STRING)RxConnectionId, v35);
      VNetRoot = (PV_NET_ROOT)v40;
      v66 = v40;
      if ( !v40 )
      {
        AdditionalReferenceForDeleteFsctlTaken = -1073741670;
        LODWORD(v65) = -1073741670;
        v27 = 1462;
        goto LABEL_30;
      }
      RxReference(v40);
      BYTE4(RxContext->TrackerHistory[4].FileName) = NetRootType;
      *(_QWORD *)&RxContext->TrackerHistory[0].AcquireRelease = 0;
      RxContext->TrackerHistory[0].FileName = 0;
      *(_QWORD *)&RxContext->TrackerHistory[0].Flags = 0;
      ++TreeConnecta;
      HIDWORD(v65) = v34 + 1;
      NonPagedFcb = RxContext->NonPagedFcb;
      v43 = NonPagedFcb[1].HeaderResource.SystemResourcesList.Flink;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qZZ(
          WPP_GLOBAL_Control->AttachedDevice,
          (_DWORD)NonPagedFcb + 360,
          v41,
          (_DWORD)VNetRoot,
          (__int64)&NonPagedFcb->AdvancedFcbHeaderMutex.OldIrql,
          (__int64)&VNetRoot->PrefixEntry.MemberQLinks);
      }
      AdditionalReferenceForDeleteFsctlTaken = 0;
      v71 = 0;
      ConnectionConstructionContext = RxpAllocateConnectionConstructionContext(RxContext, 288);
      v71 = ConnectionConstructionContext;
      v47 = RxContext;
      if ( ConnectionConstructionContext )
      {
        if ( (unsigned __int8)RfsAcquireRundownProtectionCacheAware(
                                *(_QWORD *)&RxContext->NonPagedFcb[2].AdvancedFcbHeaderMutex.OldIrql,
                                v44,
                                v46) )
        {
          *(_QWORD *)(ConnectionConstructionContext + 272) = RxFinishSrvCallConstruction;
          *(_QWORD *)(ConnectionConstructionContext + 264) = VNetRoot;
          *(_DWORD *)(ConnectionConstructionContext + 280) = -1073741634;
          RxReference(VNetRoot);
          v47 = RxContext;
          goto LABEL_67;
        }
        AdditionalReferenceForDeleteFsctlTaken = -1073741573;
      }
      else
      {
        AdditionalReferenceForDeleteFsctlTaken = -1073741670;
      }
      if ( ConnectionConstructionContext )
      {
        RxpFreeConnectionConstructionContext((PVOID)ConnectionConstructionContext);
        ConnectionConstructionContext = 0;
        v71 = 0;
        v47 = RxContext;
      }
LABEL_67:
      if ( AdditionalReferenceForDeleteFsctlTaken < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_qqD(
            WPP_GLOBAL_Control->AttachedDevice,
            23,
            WPP_8f40199b670e3a186f0ad2764a4463aa_Traceguids,
            v47,
            VNetRoot,
            AdditionalReferenceForDeleteFsctlTaken);
        }
        VNetRoot->PrefixOffsetInBytes = 4;
        *((_QWORD *)&VNetRoot->1 + 4) = 0;
        if ( ConnectionConstructionContext )
        {
          RxDereference(VNetRoot, LHS_LockNotHeld);
          RxpFreeConnectionConstructionContext((PVOID)ConnectionConstructionContext);
        }
      }
      else
      {
        VNetRoot->PrefixOffsetInBytes = 1;
        *((_QWORD *)&VNetRoot->1 + 4) = 0;
        ExReleaseResourceLite((PERESOURCE)&v43[1].Blink);
        *LockState = LHS_LockNotHeld;
        v48 = NonPagedFcb->AdvancedFcbHeaderMutex.Event.Header.WaitListHead.Blink[34].Flink;
        if ( v48 )
        {
          AdditionalReferenceForDeleteFsctlTaken = ((__int64 (__fastcall *)(PV_NET_ROOT, __int64))v48)(
                                                     VNetRoot,
                                                     ConnectionConstructionContext);
          if ( AdditionalReferenceForDeleteFsctlTaken == 259 )
            goto LABEL_70;
        }
        else
        {
          AdditionalReferenceForDeleteFsctlTaken = -1073741822;
        }
        *(_DWORD *)(ConnectionConstructionContext + 280) = AdditionalReferenceForDeleteFsctlTaken;
        RxFinishSrvCallConstruction((PVOID)ConnectionConstructionContext);
        AdditionalReferenceForDeleteFsctlTaken = 259;
      }
LABEL_70:
      LODWORD(v65) = AdditionalReferenceForDeleteFsctlTaken;
      v21 = LockState;
      v49 = *LockState;
      if ( AdditionalReferenceForDeleteFsctlTaken < 0 )
      {
        RxDereference(VNetRoot, v49);
        v27 = 1485;
LABEL_29:
        v66 = 0;
        goto LABEL_30;
      }
      if ( v49 == LHS_LockNotHeld )
      {
        ExAcquireResourceSharedLite((PERESOURCE)&v76[1].Blink, 1u);
        *LockState = LHS_SharedLockHeld;
      }
      v68 = VNetRoot;
      v22 = RxContext;
    }
  }
  if ( AdditionalReferenceForDeleteFsctlTaken >= 0 )
    AdditionalReferenceForDeleteFsctlTaken = -1073741634;
  LODWORD(v65) = AdditionalReferenceForDeleteFsctlTaken;
  v27 = 946;
LABEL_31:
  v28 = RxContext;
LABEL_189:
  if ( AdditionalReferenceForDeleteFsctlTaken && *v21 )
  {
    ExReleaseResourceLite((PERESOURCE)&Flink[1].Blink);
    *v21 = LHS_LockNotHeld;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    if ( AdditionalReferenceForDeleteFsctlTaken == 259 )
      v61 = 0;
    else
      v61 = *(_QWORD *)&v28->TrackerHistory[0].Flags;
    if ( AdditionalReferenceForDeleteFsctlTaken == 259 )
      FileName = 0;
    else
      FileName = v28->TrackerHistory[0].FileName;
    if ( AdditionalReferenceForDeleteFsctlTaken == 259 )
      v63 = 0;
    else
      v63 = *(_QWORD *)&v28->TrackerHistory[0].AcquireRelease;
    LODWORD(FilePath) = v27;
    WPP_SF_Ddqqq(
      WPP_GLOBAL_Control->AttachedDevice,
      FileName,
      v61,
      (unsigned int)AdditionalReferenceForDeleteFsctlTaken,
      FilePath,
      v63,
      FileName,
      v61,
      v65,
      v66,
      v67,
      v68,
      v69);
  }
  return AdditionalReferenceForDeleteFsctlTaken;
}

```

## disassembly

```asm
0x14005f400  mov     rax, rsp
0x14005f403  mov     [rax+20h], r9b
0x14005f407  mov     [rax+18h], r8
0x14005f40b  mov     [rax+10h], rdx
0x14005f40f  mov     [rax+8], rcx
0x14005f413  push    rbx
0x14005f414  push    rsi
0x14005f415  push    rdi
0x14005f416  push    r12
0x14005f418  push    r13
0x14005f41a  push    r14
0x14005f41c  push    r15
0x14005f41e  sub     rsp, 0C0h
0x14005f425  mov     r9, r8
0x14005f428  mov     rdx, rcx
0x14005f42b  mov     r12, [rsp+0F8h+FilePathName]
0x14005f433  mov     edi, 0C0000001h
0x14005f438  mov     [rsp+0F8h+var_B8], edi
0x14005f43c  xor     r15d, r15d
0x14005f43f  mov     [rax+28h], r15d
0x14005f443  mov     rax, [rcx+50h]
0x14005f447  mov     r14, [rax+1F8h]
0x14005f44e  mov     [rsp+0F8h+arg_8], r14
0x14005f456  mov     [rsp+0F8h+FilePathName], r14
0x14005f45e  lea     r10, WPP_GLOBAL_Control
0x14005f465  mov     rcx, cs:WPP_GLOBAL_Control
0x14005f46c  cmp     rcx, r10
0x14005f46f  jnz     loc_140060499
0x14005f475  mov     rbx, [rsp+0F8h+RxConnectionId]
0x14005f47d  test    r12, r12
0x14005f480  jz      short loc_14005F48B
0x14005f482  movups  xmm0, xmmword ptr [r9]
0x14005f486  movups  xmmword ptr [r12], xmm0
0x14005f48b  mov     r13, [rsp+0F8h+LocalNetRootName]
0x14005f493  test    r13, r13
0x14005f496  jz      short loc_14005F4A0
0x14005f498  xorps   xmm0, xmm0
0x14005f49b  movups  xmmword ptr [r13+0], xmm0
0x14005f4a0  mov     r8, [r9+8]
0x14005f4a4  cmp     word ptr [r8+2], 3Bh ; ';'
0x14005f4aa  jnz     short loc_14005F51B
0x14005f4ac  lea     rcx, [r8+4]
0x14005f4b0  xor     eax, eax
0x14005f4b2  movzx   edx, word ptr [r9]
0x14005f4b6  cmp     edx, 4
0x14005f4b9  jbe     short loc_14005F4C0
0x14005f4bb  lea     eax, [rdx-4]
0x14005f4be  xchg    ax, ax
0x14005f4c0  test    eax, eax
0x14005f4c2  jz      loc_1400604EC
0x14005f4c8  cmp     word ptr [rcx], 5Ch ; '\'
0x14005f4cc  jz      short loc_14005F4D7
0x14005f4ce  add     eax, 0FFFFFFFEh
0x14005f4d1  add     rcx, 2
0x14005f4d5  jmp     short loc_14005F4C0
0x14005f4d7  test    r13, r13
0x14005f4da  jz      short loc_14005F4F2
0x14005f4dc  mov     [r13+8], r8
0x14005f4e0  movzx   eax, cx
0x14005f4e3  sub     ax, [r9+8]
0x14005f4e8  mov     [r13+0], ax
0x14005f4ed  mov     [r13+2], ax
0x14005f4f2  mov     rdx, [rsp+0F8h+RxContext]
0x14005f4fa  test    r12, r12
0x14005f4fd  jz      short loc_14005F51B
0x14005f4ff  mov     [r12+8], rcx
0x14005f504  movzx   eax, word ptr [r9]
0x14005f508  sub     ax, cx
0x14005f50b  add     ax, [r9+8]
0x14005f510  mov     [r12], ax
0x14005f515  mov     [r12+2], ax
0x14005f51b  xorps   xmm0, xmm0
0x14005f51e  movups  xmmword ptr [rsp+0F8h+Name.Length], xmm0
0x14005f523  xorps   xmm1, xmm1
0x14005f526  movups  xmmword ptr [rsp+0F8h+var_70.Length], xmm1
0x14005f52e  mov     rsi, [rsp+0F8h+LockState]
0x14005f536  mov     eax, 0C00000BEh
0x14005f53b  nop     dword ptr [rax+rax+00h]
0x14005f540  test    r15, r15
0x14005f543  jnz     loc_14005FE8F
0x14005f549  cmp     dword ptr [rdx+2F0h], 8
0x14005f550  ja      loc_14005FF95
0x14005f556  mov     byte ptr [rsp+0F8h+FilePath], 0
0x14005f55b  mov     r9, rbx
0x14005f55e  lea     r8, [rsp+0F8h+var_48]
0x14005f566  mov     rdx, r12
0x14005f569  mov     rcx, r14
0x14005f56c  call    RxPrefixTableLookupNameEx
0x14005f571  mov     r15, rax
0x14005f574  mov     [rsp+0F8h+var_A0], rax
0x14005f579  mov     rdx, [rsp+0F8h+RxContext]
0x14005f581  inc     dword ptr [rdx+2F0h]
0x14005f587  xor     r10d, r10d
0x14005f58a  mov     r14d, r10d
0x14005f58d  mov     [rsp+0F8h+var_A8], r10
0x14005f592  mov     ebx, r10d
0x14005f595  mov     [rsp+0F8h+var_B0], rbx
0x14005f59a  mov     [rdx+290h], r10
0x14005f5a1  mov     [rdx+288h], r10
0x14005f5a8  mov     [rdx+280h], r10
0x14005f5af  movzx   eax, [rsp+0F8h+arg_18]
0x14005f5b7  mov     [rdx+2ECh], al
0x14005f5bd  test    r15, r15
0x14005f5c0  jz      loc_14005F73F
0x14005f5c6  movzx   ecx, word ptr [r15]
0x14005f5ca  cmp     ecx, 0EB10h
0x14005f5d0  jnz     loc_14005F657
0x14005f5d6  mov     rbx, r15
0x14005f5d9  mov     [rsp+0F8h+var_B0], rbx
0x14005f5de  movzx   eax, byte ptr [rdx+2EEh]
0x14005f5e5  test    al, 10h
0x14005f5e7  jnz     loc_140060193
0x14005f5ed  mov     eax, [r15+0E0h]
0x14005f5f4  cmp     eax, 1
0x14005f5f7  jz      loc_14005FAF3
0x14005f5fd  mov     edi, r10d
0x14005f600  mov     [rsp+0F8h+var_B8], r10d
0x14005f605  cmp     eax, 3
0x14005f608  jz      loc_14005F737
0x14005f60e  mov     edi, [r15+68h]
0x14005f612  mov     [rsp+0F8h+var_B8], edi
0x14005f616  test    edi, edi
0x14005f618  mov     eax, 0C00000BEh
0x14005f61d  cmovns  edi, eax
0x14005f620  mov     [rsp+0F8h+var_B8], edi
0x14005f624  mov     edx, [rsi]; LockHoldingState
0x14005f626  mov     rcx, rbx; Instance
0x14005f629  call    RxDereference
0x14005f62e  mov     ebx, 4AAh
0x14005f633  xor     r10d, r10d
0x14005f636  mov     [rsp+0F8h+var_B0], r10
0x14005f63b  mov     r14, [rsp+0F8h+arg_8]
0x14005f643  mov     r15, [rsp+0F8h+RxContext]
0x14005f64b  lea     r12, WPP_GLOBAL_Control
0x14005f652  jmp     loc_14006044D
0x14005f657  sub     ecx, 0EB11h
0x14005f65d  jz      loc_14005F702
0x14005f663  cmp     ecx, 1
0x14005f666  jnz     loc_14005F73F
0x14005f66c  mov     rbx, [r15+20h]
0x14005f670  mov     [rsp+0F8h+var_A8], rbx
0x14005f675  mov     rsi, [rbx+20h]
0x14005f679  mov     [rsp+0F8h+var_B0], rsi
0x14005f67e  mov     r12, [rsp+0F8h+LockState]
0x14005f686  mov     r13, [rsp+0F8h+RxContext]
0x14005f68e  mov     ecx, [r15+0CCh]
0x14005f695  cmp     ecx, 1
0x14005f698  jz      loc_14005FBB3
0x14005f69e  cmp     ecx, 3
0x14005f6a1  jnz     loc_14005FCE3
0x14005f6a7  cmp     [rbx+94h], ecx
0x14005f6ad  jnz     loc_14005FCE3
0x14005f6b3  cmp     [rsi+0E0h], ecx
0x14005f6b9  jnz     loc_14005FCE3
0x14005f6bf  mov     rdx, [rsp+0F8h+RxContext]
0x14005f6c7  mov     rax, [rdx+50h]
0x14005f6cb  cmp     [rsi+30h], rax
0x14005f6cf  jnz     loc_14005FCE3
0x14005f6d5  mov     [rdx+280h], rsi
0x14005f6dc  mov     [rdx+288h], rbx
0x14005f6e3  mov     [rdx+290h], r15
0x14005f6ea  xor     r10d, r10d
0x14005f6ed  mov     edi, r10d
0x14005f6f0  mov     [rsp+0F8h+var_B8], r10d
0x14005f6f5  mov     ebx, 40Bh
0x14005f6fa  mov     rsi, r12
0x14005f6fd  jmp     loc_14005F63B
0x14005f702  mov     r14, r15
0x14005f705  mov     [rsp+0F8h+var_A8], r15
0x14005f70a  mov     rbx, [r15+20h]
0x14005f70e  mov     [rsp+0F8h+var_B0], rbx
0x14005f713  mov     eax, [r15+94h]
0x14005f71a  cmp     eax, 1
0x14005f71d  jz      loc_14005FFAB
0x14005f723  cmp     eax, 3
0x14005f726  jz      loc_1400600E4
0x14005f72c  mov     edi, [r15+98h]
0x14005f733  mov     [rsp+0F8h+var_B8], edi
0x14005f737  mov     rdx, [rsp+0F8h+RxContext]
0x14005f73f  test    rbx, rbx
0x14005f742  jnz     loc_14005FCA8
0x14005f748  cmp     dword ptr [rsi], 1
0x14005f74b  jz      loc_14005FD7C
0x14005f751  mov     edi, [rsp+0F8h+TreeConnect]
0x14005f758  test    edi, edi
0x14005f75a  jnz     loc_14005FE64
0x14005f760  test    r15, r15
0x14005f763  jnz     loc_14005F9B9
0x14005f769  movzx   r9d, byte ptr [rdx+2EEh]; RxConnectionId
0x14005f771  movzx   r8d, word ptr [r12]
0x14005f776  mov     rcx, [r12+8]
0x14005f77b  mov     [rsp+0F8h+var_98], rcx
0x14005f780  add     r8, rcx
0x14005f783  mov     [rsp+0F8h+Name.Buffer], rcx
0x14005f788  cmp     rcx, r8
0x14005f78b  jnb     short loc_14005F7B4
0x14005f78d  cmp     word ptr [rcx], 5Ch ; '\'
0x14005f791  jnz     short loc_14005F7B4
0x14005f793  lea     rax, [rcx+2]
0x14005f797  mov     rcx, rax
0x14005f79a  mov     [rsp+0F8h+var_98], rax
0x14005f79f  nop
0x14005f7a0  cmp     rax, r8
0x14005f7a3  jnb     short loc_14005F7B9
0x14005f7a5  cmp     word ptr [rcx], 5Ch ; '\'
0x14005f7a9  jz      short loc_14005F7B9
0x14005f7ab  lea     rcx, [rax+2]
0x14005f7af  mov     [rsp+0F8h+var_98], rcx
0x14005f7b4  mov     rax, rcx
0x14005f7b7  jmp     short loc_14005F7A0
0x14005f7b9  movzx   edx, ax
0x14005f7bc  sub     dx, [r12+8]
0x14005f7c2  mov     [rsp+0F8h+Name.MaximumLength], dx
0x14005f7c7  mov     [rsp+0F8h+Name.Length], dx
0x14005f7cc  test    r9b, 10h
0x14005f7d0  jnz     loc_14006033E
0x14005f7d6  movaps  xmm0, xmmword ptr [rsp+0F8h+Name.Length]
0x14005f7db  movdqa  [rsp+0F8h+var_58], xmm0
0x14005f7e4  mov     word ptr [rsp+0F8h+var_58], dx
0x14005f7ec  mov     rcx, cs:WPP_GLOBAL_Control
0x14005f7f3  lea     rax, WPP_GLOBAL_Control
0x14005f7fa  cmp     rcx, rax
0x14005f7fd  jz      short loc_14005F80A
0x14005f7ff  mov     eax, [rcx+2Ch]
0x14005f802  test    al, al
0x14005f804  js      loc_140060381
0x14005f80a  mov     r8, [rsp+0F8h+RxConnectionId]; InnerNamePrefix
0x14005f812  lea     rdx, [rsp+0F8h+Name]; Name
0x14005f817  mov     rbx, [rsp+0F8h+RxContext]
0x14005f81f  mov     rcx, rbx; RxContext
0x14005f822  call    RxCreateSrvCall
0x14005f827  mov     r15, rax
0x14005f82a  mov     [rsp+0F8h+var_B0], rax
0x14005f82f  test    rax, rax
0x14005f832  jz      loc_14005FE4E
0x14005f838  mov     rcx, rax; Instance
0x14005f83b  call    RxReference
0x14005f840  movzx   eax, [rsp+0F8h+arg_18]
0x14005f848  mov     [rbx+2ECh], al
0x14005f84e  xor     edx, edx
0x14005f850  mov     [rbx+280h], rdx
0x14005f857  mov     [rbx+288h], rdx
0x14005f85e  mov     [rbx+290h], rdx
0x14005f865  inc     edi
0x14005f867  mov     [rsp+0F8h+TreeConnect], edi
0x14005f86e  mov     [rsp+0F8h+var_B4], edi
0x14005f872  mov     rsi, [rbx+50h]
0x14005f876  mov     r14, [rsi+1F8h]
0x14005f87d  mov     rcx, cs:WPP_GLOBAL_Control
0x14005f884  lea     rax, WPP_GLOBAL_Control
0x14005f88b  cmp     rcx, rax
0x14005f88e  jnz     loc_14005FEBB
0x14005f894  mov     edi, edx
0x14005f896  mov     [rsp+0F8h+var_78], rdx
0x14005f89e  mov     edx, 120h
0x14005f8a3  mov     rcx, rbx
0x14005f8a6  call    RxpAllocateConnectionConstructionContext
0x14005f8ab  mov     rbx, rax
0x14005f8ae  mov     [rsp+0F8h+var_78], rax
0x14005f8b6  mov     r9, [rsp+0F8h+RxContext]
0x14005f8be  test    rax, rax
0x14005f8c1  jz      loc_1400603B8
0x14005f8c7  mov     rcx, [r9+50h]
0x14005f8cb  mov     rcx, [rcx+518h]
0x14005f8d2  call    RfsAcquireRundownProtectionCacheAware
0x14005f8d7  test    al, al
0x14005f8d9  jnz     loc_1400603C2
0x14005f8df  mov     edi, 0C00000FBh
0x14005f8e4  test    rbx, rbx
0x14005f8e7  jz      loc_1400603F1
0x14005f8ed  mov     rcx, rbx; P
0x14005f8f0  call    RxpFreeConnectionConstructionContext
0x14005f8f5  xor     ecx, ecx
0x14005f8f7  mov     ebx, ecx
0x14005f8f9  mov     [rsp+0F8h+var_78], rcx
0x14005f901  mov     r9, [rsp+0F8h+RxContext]
0x14005f909  test    edi, edi
0x14005f90b  js      loc_14005FF0F
0x14005f911  mov     dword ptr [r15+0E0h], 1
0x14005f91c  mov     [r15+20h], rcx
0x14005f920  lea     rcx, [r14+18h]; Resource
0x14005f924  call    cs:__imp_ExReleaseResourceLite
0x14005f92b  nop     dword ptr [rax+rax+00h]
0x14005f930  mov     rax, [rsp+0F8h+LockState]
0x14005f938  mov     dword ptr [rax], 0
0x14005f93e  mov     rax, [rsi+160h]
0x14005f945  mov     rax, [rax+220h]
0x14005f94c  test    rax, rax
0x14005f94f  jz      loc_140060430
0x14005f955  mov     rdx, rbx
0x14005f958  mov     rcx, r15
0x14005f95b  call    _guard_dispatch_icall
0x14005f960  mov     edi, eax
0x14005f962  cmp     eax, 103h
0x14005f967  jnz     loc_140060435
0x14005f96d  mov     [rsp+0F8h+var_B8], edi
0x14005f971  mov     rsi, [rsp+0F8h+LockState]
0x14005f979  mov     eax, [rsi]
0x14005f97b  test    edi, edi
0x14005f97d  js      loc_14005FEFB
  ... truncated ...
```
