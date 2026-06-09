# RefsScrubHandleInternal(_IRP_CONTEXT *,_IRP *,_SmsCancelScrub *,_SCB *,_TYPE_OF_OPEN)

- ea: `0x1402baa48`
- end: `0x1402bc01a`
- name: `?RefsScrubHandleInternal@@YAJPEAU_IRP_CONTEXT@@PEAU_IRP@@PEAU_SmsCancelScrub@@PEAU_SCB@@W4_TYPE_OF_OPEN@@@Z`
- size: `5586`
- prototype: ``
- caller_count: `1`
- callee_count: `26`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1402ba570`

## callees

- `0x14000cd70`
- `0x140081670`
- `0x14008dbd0`
- `0x1400ca788`
- `0x1400e6d98`
- `0x1400f2104`
- `0x1400f31a0`
- `0x1400f31fc`
- `0x1400f341c`
- `0x1400f3488`
- `0x140114418`
- `0x140115768`
- `0x1401157bc`
- `0x1401157ec`
- `0x140115824`
- `0x140115834`
- `0x140115884`
- `0x1401158ac`
- `0x1401e9ce0`
- `0x1401e9e40`
- `0x1401ea140`
- `0x1402966c4`
- `0x1402995a8`
- `0x140299694`
- `0x1402baa48`
- `0x1402fec90`

## import_xrefs

- `ntoskrnl!PsIsThreadTerminating` at `0x1402bb2c6`
- `ntoskrnl!PsIsThreadTerminating` at `0x1402bb3b4`
- `ntoskrnl!PsIsThreadTerminating` at `0x1402bb485`
- `ntoskrnl!PsIsThreadTerminating` at `0x1402bb589`
- `ntoskrnl!PsIsThreadTerminating` at `0x1402bb641`
- `ntoskrnl!PsIsThreadTerminating` at `0x1402bb6f9`
- `ntoskrnl!PsIsThreadTerminating` at `0x1402bb79b`
- `ntoskrnl!PsIsThreadTerminating` at `0x1402bb86f`
- `ntoskrnl!PsIsThreadTerminating` at `0x1402bb99d`
- `ntoskrnl!PsIsThreadTerminating` at `0x1402bb2c6`
- `ntoskrnl!PsIsThreadTerminating` at `0x1402bb3b4`
- `ntoskrnl!PsIsThreadTerminating` at `0x1402bb485`
- `ntoskrnl!PsIsThreadTerminating` at `0x1402bb589`
- `ntoskrnl!PsIsThreadTerminating` at `0x1402bb641`
- `ntoskrnl!PsIsThreadTerminating` at `0x1402bb6f9`
- `ntoskrnl!PsIsThreadTerminating` at `0x1402bb79b`
- `ntoskrnl!PsIsThreadTerminating` at `0x1402bb86f`
- `ntoskrnl!PsIsThreadTerminating` at `0x1402bb99d`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1402bba0c`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1402bba0c`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402bba1b`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402bba1b`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402bba46`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402bba46`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402bba52`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402bba52`

## pseudocode

```c
__int64 __fastcall RefsScrubHandleInternal(
        struct CmsTransactionContext **a1,
        struct _IRP *a2,
        __int64 a3,
        __int16 *a4,
        unsigned __int8 a5)
{
  NTSTATUS v8; // r14d
  struct _IO_STACK_LOCATION *v9; // r8
  unsigned int Options; // edx
  unsigned int v11; // r9d
  struct _IRP *MasterIrp; // r15
  _DWORD *v13; // rbx
  _DWORD *v15; // rsi
  int v16; // ecx
  unsigned int v17; // eax
  __int64 v18; // rax
  struct _LIST_ENTRY *Blink; // rdx
  __int64 v20; // rax
  __int64 v21; // r8
  int MdlAddress; // eax
  unsigned int v23; // r8d
  struct _MDL **v24; // r9
  ULONG v25; // ecx
  _DWORD *v26; // rcx
  __int64 v27; // rdx
  unsigned int Length; // ecx
  unsigned int v29; // ecx
  unsigned int v30; // ecx
  unsigned int v31; // ecx
  int v32; // r9d
  __int64 v33; // rcx
  bool v34; // zf
  unsigned int v35; // ecx
  unsigned int v36; // ecx
  _QWORD *v37; // rdi
  struct CmsTransactionContext **v38; // rbx
  __int64 v39; // rcx
  __int64 v40; // rcx
  __int64 v41; // rax
  __int64 v42; // rcx
  __int64 v43; // rcx
  unsigned int v44; // ecx
  unsigned int v45; // ecx
  struct CmsTransactionContext **v46; // rbx
  unsigned int v47; // ecx
  unsigned int v48; // ecx
  __int64 v49; // rcx
  __int64 v50; // rcx
  __int64 v51; // rcx
  __int64 v52; // rcx
  __int64 v53; // rcx
  __int64 v54; // rcx
  int v55; // r9d
  __int64 v56; // rcx
  __int64 v57; // rcx
  __int64 v58; // r8
  NTSTATUS v59; // r9d
  __int64 v60; // rcx
  __int64 v61; // rcx
  __int64 v62; // rcx
  struct _FAST_MUTEX *v63; // rbx
  __int64 v64; // rbx
  unsigned __int64 v65; // rdx
  __int16 *v66; // rbx
  CmsStream *v67; // r8
  struct _LIST_ENTRY *Flink; // rbx
  struct _IRP *v69; // r13
  unsigned __int16 *v70; // rdx
  __int64 Information_low; // rbx
  size_t v72; // rdi
  struct _VCB *v73; // rcx
  __int128 v74; // xmm0
  __int128 v75; // xmm1
  struct _IRP *v76; // r13
  unsigned __int16 *v77; // rdx
  size_t v78; // rbx
  void **v79; // [rsp+30h] [rbp-288h]
  __int64 v80; // [rsp+40h] [rbp-278h]
  unsigned int v82; // [rsp+50h] [rbp-268h] BYREF
  __int64 v83; // [rsp+58h] [rbp-260h]
  __int16 *v84; // [rsp+60h] [rbp-258h]
  unsigned __int64 v85; // [rsp+68h] [rbp-250h]
  void *v86; // [rsp+70h] [rbp-248h] BYREF
  struct _IO_STACK_LOCATION *CurrentStackLocation; // [rsp+78h] [rbp-240h]
  struct _IRP *v88; // [rsp+80h] [rbp-238h]
  __int64 v89; // [rsp+88h] [rbp-230h]
  __int64 v90; // [rsp+90h] [rbp-228h]
  __int128 v91; // [rsp+A8h] [rbp-210h]
  _OWORD v92[11]; // [rsp+B8h] [rbp-200h] BYREF
  __int128 v93; // [rsp+178h] [rbp-140h]
  _OWORD v94[11]; // [rsp+188h] [rbp-130h] BYREF
  __int128 v95; // [rsp+238h] [rbp-80h] BYREF
  __int128 v96; // [rsp+248h] [rbp-70h]
  __int128 v97; // [rsp+258h] [rbp-60h]
  __int64 v98; // [rsp+268h] [rbp-50h]

  v84 = a4;
  v88 = a2;
  v8 = 0;
  v86 = 0;
  v82 = 0x100000;
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v9 = CurrentStackLocation;
  v95 = 0;
  v96 = 0;
  v97 = 0;
  v98 = 0;
  Options = CurrentStackLocation->Parameters.Create.Options;
  if ( Options < 0xC0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 471, WPP_9a30568c93c333a296ab3c507849cc83_Traceguids, 3221225485LL);
    }
    if ( !(_BYTE)RefsStatusDebugEnabled )
      return 3221225485LL;
    v11 = 16951;
LABEL_77:
    RefsStatusDebug(-1073741811, 0, "FsCtrl.c", v11);
    return 3221225485LL;
  }
  MasterIrp = a2->AssociatedIrp.MasterIrp;
  if ( *(_DWORD *)&MasterIrp->Type != 1232 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 472, WPP_9a30568c93c333a296ab3c507849cc83_Traceguids, 3221225485LL);
    }
    if ( !(_BYTE)RefsStatusDebugEnabled )
      return 3221225485LL;
    v11 = 16960;
    goto LABEL_77;
  }
  v83 = *((_QWORD *)a4 + 18);
  v13 = &MasterIrp->Size + 1;
  if ( *(_DWORD *)(v83 + 392) < 2u && (*v13 & 8) == 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 473, WPP_9a30568c93c333a296ab3c507849cc83_Traceguids, 3221226617LL);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
      RefsStatusDebug(-1073740679, 0, "FsCtrl.c", 0x4251u);
    return 3221226617LL;
  }
  v15 = &MasterIrp->Tail.CompletionKey + 9;
  v16 = *v13 & 1;
  if ( v16 )
  {
    v17 = *((_DWORD *)&MasterIrp->Tail.CompletionKey + 21);
    if ( v17 > 0x280 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 474, WPP_9a30568c93c333a296ab3c507849cc83_Traceguids, 3221225485LL);
      }
      if ( !(_BYTE)RefsStatusDebugEnabled )
        return 3221225485LL;
      v11 = 16989;
      goto LABEL_77;
    }
    if ( Options < v17 + 296 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 475, WPP_9a30568c93c333a296ab3c507849cc83_Traceguids, 3221225485LL);
      }
      if ( !(_BYTE)RefsStatusDebugEnabled )
        return 3221225485LL;
      v11 = 16997;
      goto LABEL_77;
    }
  }
  if ( CurrentStackLocation->Parameters.Read.Length < 0x4D0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 476, WPP_9a30568c93c333a296ab3c507849cc83_Traceguids, 3221225507LL);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741789, 0, "FsCtrl.c", 0x4270u);
    return 3221225507LL;
  }
  v89 = *((_QWORD *)a4 + 17);
  if ( v16 )
  {
    if ( *v15 != 2
      || *((_BYTE *)&MasterIrp->Tail.CompletionKey + 76) >= 0x17u
      || *((_BYTE *)&MasterIrp->Tail.CompletionKey + 77) >= 5u
      || *((_BYTE *)&MasterIrp->Tail.CompletionKey + 78) >= 0xAu
      || (v18 = *((unsigned int *)&MasterIrp->Tail.CompletionKey + 21), (unsigned int)v18 > 0x4D0)
      || (_DWORD *)((char *)v15 + v18 + 104) > (_DWORD *)&MasterIrp[6].Tail.CompletionKey + 14 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 477, WPP_9a30568c93c333a296ab3c507849cc83_Traceguids, 3221225485LL);
      }
      if ( !(_BYTE)RefsStatusDebugEnabled )
        return 3221225485LL;
      v11 = 17026;
      goto LABEL_77;
    }
  }
  else
  {
    *((_WORD *)&MasterIrp->Tail.CompletionKey + 38) = 0;
    *((_BYTE *)&MasterIrp->Tail.CompletionKey + 78) = 9;
    MsInitializeScrubKey(&MasterIrp->Tail.CompletionKey + 9);
    memset(&MasterIrp[1].MdlAddress, 0, 0x50u);
  }
  Blink = MasterIrp->ThreadListEntry.Blink;
  if ( !Blink )
  {
LABEL_90:
    v85 = 0xFFFFFFFF00000000uLL;
    MasterIrp[4].CancelRoutine = (PDRIVER_CANCEL)MasterIrp->ThreadListEntry.Flink;
    MasterIrp[4].UserBuffer = MasterIrp->ThreadListEntry.Blink;
    *v15 = 2;
    MdlAddress = (int)MasterIrp->MdlAddress;
    *((_DWORD *)&MasterIrp->Tail.CompletionKey + 20) = MdlAddress;
    if ( !MdlAddress )
    {
      MdlAddress = 0x7FFFFFFF;
      *((_DWORD *)&MasterIrp->Tail.CompletionKey + 20) = 0x7FFFFFFF;
    }
    if ( MdlAddress < 2 )
      *((_DWORD *)&MasterIrp->Tail.CompletionKey + 20) = 2;
    memset(v92, 0, sizeof(v92));
    v24 = 0;
    LODWORD(v91) = 0;
    *((_QWORD *)&v91 + 1) = 0;
    *(_DWORD *)((char *)&v92[3] + 2) = 0;
    WORD3(v92[3]) = 0;
    MasterIrp[4].Tail.Overlay.DeviceQueueEntry.DeviceListEntry = 0;
    *((_OWORD *)&MasterIrp[4].Tail.CompletionKey + 1) = v91;
    *((_OWORD *)&MasterIrp[4].Tail.CompletionKey + 2) = v92[0];
    *((_OWORD *)&MasterIrp[4].Tail.CompletionKey + 3) = v92[1];
    *((_OWORD *)&MasterIrp[4].Tail.CompletionKey + 4) = v92[2];
    *((_OWORD *)&MasterIrp[4].Tail.CompletionKey + 5) = v92[3];
    *(_OWORD *)&MasterIrp[5].MdlAddress = v92[4];
    *(_OWORD *)&MasterIrp[5].AssociatedIrp.MasterIrp = v92[5];
    *(_OWORD *)&MasterIrp[5].ThreadListEntry.Blink = v92[6];
    *(_OWORD *)&MasterIrp[5].IoStatus.Information = v92[7];
    *(_OWORD *)&MasterIrp[5].UserIosb = v92[8];
    *(_OWORD *)&MasterIrp[5].Overlay.AsynchronousParameters.UserApcRoutine = v92[9];
    *(_OWORD *)&MasterIrp[5].CancelRoutine = v92[10];
    MasterIrp[4].Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Blink = (struct _LIST_ENTRY *)&MasterIrp[1].Overlay;
    v25 = *((_DWORD *)&MasterIrp->Tail.CompletionKey + 21);
    LODWORD(MasterIrp[4].Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink) = v25;
    WORD2(MasterIrp[4].Tail.CompletionKey) = MasterIrp[1].Type;
    MasterIrp[4].Tail.Overlay.DriverContext[3] = &MasterIrp[1].Overlay;
    MasterIrp[4].Tail.Overlay.DeviceQueueEntry.SortKey = v25;
    v26 = &MasterIrp[4].Tail.CompletionKey + 4;
    v27 = 1;
    if ( (*v13 & 2) != 0 )
      *v26 |= 1u;
    if ( (*v13 & 4) != 0 )
    {
      v26 = &MasterIrp[4].Tail.CompletionKey + 4;
      *((_DWORD *)&MasterIrp[4].Tail.CompletionKey + 8) |= 4u;
    }
    if ( (*v13 & 8) != 0 )
      *v26 |= 8u;
    if ( (*v13 & 0x40) != 0 )
      *v26 |= 0x10u;
    MasterIrp[5].MdlAddress = (PMDL)&MasterIrp[5].Tail;
    LOWORD(MasterIrp[5].Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink) = 24;
    WORD1(MasterIrp[5].MdlAddress->Next) = 0;
    WORD2(MasterIrp[5].MdlAddress->Next) = 0;
    HIWORD(MasterIrp[5].MdlAddress->Next) = 4;
    Length = CurrentStackLocation->Parameters.Read.Length;
    if ( Length > 0x4D0 )
    {
      v29 = Length - 1232;
      if ( v29 >= 0x4000 )
        LOWORD(v29) = 0x4000;
      HIWORD(MasterIrp[5].MdlAddress->Next) += (unsigned __int16)v29 >> 4;
    }
    *(_QWORD *)&MasterIrp[5].Type = &v95;
    v95 = 0;
    v96 = 0;
    v97 = 0;
    v98 = 0;
    if ( a5 == 4 )
    {
      BYTE4(v80) = 0;
      v30 = *((unsigned __int8 *)&MasterIrp->Tail.CompletionKey + 76);
      if ( v30 > 0xB )
      {
        if ( v30 > 0x11 )
        {
          v44 = v30 - 18;
          if ( v44 )
          {
            v45 = v44 - 1;
            v46 = a1;
            if ( v45 )
            {
              v47 = v45 - 1;
              if ( v47 )
              {
                v48 = v47 - 1;
                if ( v48 )
                {
                  if ( v48 != 1 )
                    goto LABEL_252;
LABEL_200:
                  v23 = v83;
                  if ( *(struct _MDL ***)(v83 + 40) != v24 )
                  {
                    MsScrubSetTableIndex(22, &MasterIrp->Tail.CompletionKey + 9);
                    if ( !*((_BYTE *)&MasterIrp->Tail.CompletionKey + 77)
                      || *((_BYTE *)&MasterIrp->Tail.CompletionKey + 77) == 1 )
                    {
                      v8 = MsScrubTable(
                             v46[3],
                             a3,
                             *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v58 + 40) + 136LL) + 264LL),
                             &MasterIrp->Tail.CompletionKey + 9);
                      if ( v8 < 0 )
                      {
LABEL_216:
                        MsScrubClearTableIndex(&MasterIrp->Tail.CompletionKey + 9);
                        goto LABEL_217;
                      }
                      if ( *((int *)&MasterIrp->Tail.CompletionKey + 20) <= 0
                        || **(_BYTE **)a3
                        || (**(_DWORD **)(a3 + 8) & *(_DWORD *)(a3 + 16)) != 0
                        || PsIsThreadTerminating(KeGetCurrentThread())
                        || (unsigned __int8)MsScrubContextFoundError(&MasterIrp->Tail.CompletionKey + 9)
                        || (unsigned __int8)MsScrubContextParityExtentDataFull(v60) )
                      {
                        v8 = -2147483643;
                        goto LABEL_216;
                      }
                      *((_BYTE *)&MasterIrp->Tail.CompletionKey + 77) = 2;
                      MsInitializeScrubKey(v61);
                    }
                    else if ( *((_BYTE *)&MasterIrp->Tail.CompletionKey + 77) != 2
                           && *((_BYTE *)&MasterIrp->Tail.CompletionKey + 77) != 4 )
                    {
                      goto LABEL_216;
                    }
                    v8 = v59;
                    goto LABEL_216;
                  }
LABEL_217:
                  v46 = a1;
                  goto LABEL_252;
                }
LABEL_192:
                v8 = RefsScrubVerifyBlock(
                       (struct _IRP_CONTEXT *)v46,
                       v88,
                       (struct _SmsScrubContext *)(&MasterIrp->Tail.CompletionKey + 9));
                *((_WORD *)&MasterIrp->Tail.CompletionKey + 38) = 22;
                MsInitializeScrubKey(&MasterIrp->Tail.CompletionKey + 9);
                if ( v8 < 0 )
                  goto LABEL_217;
                if ( *((_DWORD *)&MasterIrp->Tail.CompletionKey + 20) <= v55
                  || **(_BYTE **)a3 != (_BYTE)v55
                  || (**(_DWORD **)(a3 + 8) & *(_DWORD *)(a3 + 16)) != 0
                  || PsIsThreadTerminating(KeGetCurrentThread())
                  || (unsigned __int8)MsScrubContextFoundError(&MasterIrp->Tail.CompletionKey + 9)
                  || (unsigned __int8)MsScrubContextParityExtentDataFull(v56) )
                {
                  goto LABEL_253;
                }
                *((_WORD *)&MasterIrp->Tail.CompletionKey + 38) = 22;
                MsInitializeScrubKey(v57);
                goto LABEL_200;
              }
              v37 = (_QWORD *)v83;
LABEL_182:
              if ( (struct _MDL **)v37[23] != v24 )
              {
                MsScrubSetTableIndex(20, &MasterIrp->Tail.CompletionKey + 9);
                v8 = MsScrubTable(v46[3], a3, v37[23], &MasterIrp->Tail.CompletionKey + 9);
                MsScrubClearTableIndex(&MasterIrp->Tail.CompletionKey + 9);
                LODWORD(v24) = 0;
              }
              if ( v8 < 0 )
                goto LABEL_217;
              if ( *((_DWORD *)&MasterIrp->Tail.CompletionKey + 20) <= (int)v24
                || **(_BYTE **)a3 != (_BYTE)v24
                || (**(_DWORD **)(a3 + 8) & *(_DWORD *)(a3 + 16)) != 0
                || PsIsThreadTerminating(KeGetCurrentThread())
                || (unsigned __int8)MsScrubContextFoundError(&MasterIrp->Tail.CompletionKey + 9)
                || (unsigned __int8)MsScrubContextParityExtentDataFull(v53) )
              {
                goto LABEL_253;
              }
              *((_WORD *)&MasterIrp->Tail.CompletionKey + 38) = 21;
              MsInitializeScrubKey(v54);
              goto LABEL_192;
            }
            v37 = (_QWORD *)v83;
LABEL_172:
            if ( (struct _MDL **)v37[22] != v24 )
            {
              MsScrubSetTableIndex(19, &MasterIrp->Tail.CompletionKey + 9);
              v8 = MsScrubTable(v46[3], a3, v37[22], &MasterIrp->Tail.CompletionKey + 9);
              MsScrubClearTableIndex(&MasterIrp->Tail.CompletionKey + 9);
              LODWORD(v24) = 0;
            }
            if ( v8 < 0 )
              goto LABEL_217;
            if ( *((_DWORD *)&MasterIrp->Tail.CompletionKey + 20) <= (int)v24
              || **(_BYTE **)a3 != (_BYTE)v24
              || (**(_DWORD **)(a3 + 8) & *(_DWORD *)(a3 + 16)) != 0
              || PsIsThreadTerminating(KeGetCurrentThread())
              || (unsigned __int8)MsScrubContextFoundError(&MasterIrp->Tail.CompletionKey + 9)
              || (unsigned __int8)MsScrubContextParityExtentDataFull(v51) )
            {
              goto LABEL_253;
            }
            *((_WORD *)&MasterIrp->Tail.CompletionKey + 38) = 20;
            MsInitializeScrubKey(v52);
            goto LABEL_182;
          }
          v37 = (_QWORD *)v83;
LABEL_161:
          if ( (struct _MDL **)v37[13] == v24 )
          {
            v46 = a1;
          }
          else
          {
            MsScrubSetTableIndex(18, &MasterIrp->Tail.CompletionKey + 9);
            v46 = a1;
            v8 = MsScrubTable(a1[3], a3, v37[13], &MasterIrp->Tail.CompletionKey + 9);
            MsScrubClearTableIndex(&MasterIrp->Tail.CompletionKey + 9);
            LODWORD(v24) = 0;
          }
          if ( v8 < 0 )
            goto LABEL_217;
          if ( *((_DWORD *)&MasterIrp->Tail.CompletionKey + 20) <= (int)v24
            || **(_BYTE **)a3 != (_BYTE)v24
            || (**(_DWORD **)(a3 + 8) & *(_DWORD *)(a3 + 16)) != 0
            || PsIsThreadTerminating(KeGetCurrentThread()) )
          {
            v8 = -2147483643;
            goto LABEL_217;
          }
          if ( (unsigned __int8)MsScrubContextFoundError(&MasterIrp->Tail.CompletionKey + 9)
            || (unsigned __int8)MsScrubContextParityExtentDataFull(v49) )
          {
            goto LABEL_253;
          }
          *((_WORD *)&MasterIrp->Tail.CompletionKey + 38) = 19;
          MsInitializeScrubKey(v50);
          goto LABEL_172;
        }
        if ( v30 == 17 )
        {
          v38 = a1;
          v37 = (_QWORD *)v83;
LABEL_141:
          v41 = v37[11];
          if ( v41 && *(struct _MDL ***)(v41 + 416) != v24 )
          {
            MsScrubSetTableIndex(17, &MasterIrp->Tail.CompletionKey + 9);
            v8 = MsScrubTable(v38[3], a3, *(_QWORD *)(v37[11] + 416LL), &MasterIrp->Tail.CompletionKey + 9);
            MsScrubClearTableIndex(&MasterIrp->Tail.CompletionKey + 9);
            LODWORD(v24) = 0;
          }
          if ( v8 < 0 )
            goto LABEL_217;
          if ( *((_DWORD *)&MasterIrp->Tail.CompletionKey + 20) <= (int)v24
            || **(_BYTE **)a3 != (_BYTE)v24
            || (**(_DWORD **)(a3 + 8) & *(_DWORD *)(a3 + 16)) != 0
            || PsIsThreadTerminating(KeGetCurrentThread())
            || (unsigned __int8)MsScrubContextFoundError(&MasterIrp->Tail.CompletionKey + 9)
            || (unsigned __int8)MsScrubContextParityExtentDataFull(v42) )
          {
            goto LABEL_253;
          }
          *((_WORD *)&MasterIrp->Tail.CompletionKey + 38) = 18;
          MsInitializeScrubKey(v43);
          goto LABEL_161;
        }
        v35 = v30 - 12;
        v34 = v35 == 0;
      }
      else
      {
        if ( v30 == 11 )
          goto LABEL_132;
        if ( v30 <= 5 )
        {
          if ( v30 != 5 )
          {
            if ( !*((_BYTE *)&MasterIrp->Tail.CompletionKey + 76) || (v31 = v30 - 1) == 0 )
            {
              if ( (*(_DWORD *)(&MasterIrp[4].Tail.CompletionKey + 4) & 1) == 0 )
                v8 = RefsScrubBootSector(
                       (struct _IRP_CONTEXT *)a1,
                       (struct _SmsScrubContext *)(&MasterIrp->Tail.CompletionKey + 9));
              *((_WORD *)&MasterIrp->Tail.CompletionKey + 38) = 2;
              MsInitializeScrubKey(&MasterIrp->Tail.CompletionKey + 9);
              if ( v8 < 0 )
                goto LABEL_217;
              if ( *((_DWORD *)&MasterIrp->Tail.CompletionKey + 20) <= v32
                || **(_BYTE **)a3 != (_BYTE)v32
                || (**(_DWORD **)(a3 + 8) & *(_DWORD *)(a3 + 16)) != 0
                || PsIsThreadTerminating(KeGetCurrentThread())
                || (unsigned __int8)MsScrubContextFoundError(&MasterIrp->Tail.CompletionKey + 9)
                || (unsigned __int8)MsScrubContextParityExtentDataFull(&MasterIrp->Tail.CompletionKey + 9) )
              {
                goto LABEL_253;
              }
              *((_WORD *)&MasterIrp->Tail.CompletionKey + 38) = 2;
              MsInitializeScrubKey(v33);
              goto LABEL_132;
            }
LABEL_130:
            v36 = v31 - 1;
            if ( v36 && v36 - 1 > 1 )
              goto LABEL_217;
          }
LABEL_132:
          v37 = (_QWORD *)v83;
          v38 = a1;
          v8 = MsScrubVolumeMetaData(a1[3], (struct _SmsCancelScrub *)a3, *(CmsVolume **)(v83 + 112));
          if ( v8 < 0 )
            goto LABEL_217;
          RefsCheckpointCurrentTransaction((struct _IRP_CONTEXT *)a1);
          RefsBindMinstoreTransaction((struct _IRP_CONTEXT *)a1);
          if ( *((int *)&MasterIrp->Tail.CompletionKey + 20) <= 0
            || **(_BYTE **)a3
            || (**(_DWORD **)(a3 + 8) & *(_DWORD *)(a3 + 16)) != 0
            || PsIsThreadTerminating(KeGetCurrentThread())
            || (unsigned __int8)MsScrubContextFoundError(&MasterIrp->Tail.CompletionKey + 9)
            || (unsigned __int8)MsScrubContextParityExtentDataFull(v39) )
          {
            goto LABEL_253;
          }
          *((_WORD *)&MasterIrp->Tail.CompletionKey + 38) = 17;
          MsInitializeScrubKey(v40);
          goto LABEL_141;
        }
        v35 = v30 - 6;
        v34 = v35 == 0;
      }
      if ( !v34 )
      {
        v31 = v35 - 1;
        if ( v31 )
          goto LABEL_130;
      }
      goto LABEL_132;
    }
    if ( (unsigned __int16)(*a4 - 2051) <= 1u )
    {
      BYTE4(v80) = 0;
      v46 = a1;
      v8 = MsScrubTable(a1[3], a3, *((_QWORD *)a4 + 52), &MasterIrp->Tail.CompletionKey + 9);
      goto LABEL_252;
    }
    BYTE4(v80) = 1;
    if ( (*((_DWORD *)a4 + 38) & 8) != 0 && (*((_DWORD *)a4 + 38) & 0x40) == 0 )
    {
      v8 = 0;
      goto LABEL_217;
    }
    if ( !*((_BYTE *)&MasterIrp->Tail.CompletionKey + 77) || *((_BYTE *)&MasterIrp->Tail.CompletionKey + 77) == 1 )
    {
      v46 = a1;
      v8 = MsScrubTable(a1[3], a3, *(_QWORD *)(v89 + 264), &MasterIrp->Tail.CompletionKey + 9);
      if ( v8 < 0 )
        goto LABEL_217;
      if ( *((int *)&MasterIrp->Tail.CompletionKey + 20) <= 0
        || **(_BYTE **)a3
        || (**(_DWORD **)(a3 + 8) & *(_DWORD *)(a3 + 16)) != 0
        || PsIsThreadTerminating(KeGetCurrentThread()) )
      {
        v8 = -2147483643;
        goto LABEL_252;
      }
      if ( (unsigned __int8)MsScrubContextFoundError(&MasterIrp->Tail.CompletionKey + 9)
        || (unsigned __int8)((__int64 (*)(void))MsScrubContextParityExtentDataFull)() )
      {
        goto LABEL_253;
      }
      *((_BYTE *)&MasterIrp->Tail.CompletionKey + 77) = 2;
      MsInitializeScrubKey(v62);
    }
    else
    {
      v46 = a1;
      if ( *((_BYTE *)&MasterIrp->Tail.CompletionKey + 77) != 2 && *((_BYTE *)&MasterIrp->Tail.CompletionKey + 77) != 4 )
        goto LABEL_252;
    }
    RefsCreateMdlAndBuffer((struct _IRP_CONTEXT *)v46, (struct _SCB *)v27, 2u, 1u, &v82, v24, &v86);
    v63 = (struct _FAST_MUTEX *)*((_QWORD *)a4 + 6);
    KeEnterGuardedRegion();
    ExAcquireFastMutexUnsafe(v63);
    _InterlockedAdd((volatile signed __int32 *)a4 + 43, 1u);
    v64 = *((_QWORD *)a4 + 3);
    ++*((_DWORD *)a4 + 43);
    ExReleaseFastMutexUnsafe(*((PFAST_MUTEX *)a4 + 6));
    KeLeaveGuardedRegion();
    v65 = ~(*(unsigned int *)(v83 + 276) - 1LL) & (v64 + (unsigned int)(*(_DWORD *)(v83 + 276) - 1));
    v85 = v65;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      v66 = v84;
    }
    else
    {
      v66 = v84;
      WPP_SF_qDi(WPP_GLOBAL_Control->AttachedDevice, v65, v83, *((_QWORD *)v84 + 54), v82, v65);
      v65 = v85;
    }
    if ( (*(_DWORD *)(v89 + 152) & 0x20000) != 0 )
    {
      BYTE5(v80) = 1;
    }
    else
    {
      BYTE5(v80) = 0;
      if ( (*(_DWORD *)(&MasterIrp->Size + 1) & 0x10) == 0 )
      {
LABEL_245:
        if ( (*(_DWORD *)(&MasterIrp->Size + 1) & 8) != 0 )
          *((_DWORD *)&MasterIrp[4].Tail.CompletionKey + 8) |= 0x20u;
        v79 = (void **)v66;
        v67 = (CmsStream *)*((_QWORD *)v66 + 54);
        v46 = a1;
        v8 = MsScrubStream(
               a1[3],
               (struct _SmsCancelScrub *)a3,
               v67,
               v82,
               v65,
               v79,
               (struct _SmsScrubContext *)(&MasterIrp->Tail.CompletionKey + 9));
        if ( BYTE5(v80) || (*(_DWORD *)(&MasterIrp->Size + 1) & 0x10) != 0 )
          *((_DWORD *)&MasterIrp[4].Tail.CompletionKey + 8) &= ~2u;
LABEL_252:
        if ( v8 != -2147483643 )
        {
          if ( v8 < 0 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_d(
                WPP_GLOBAL_Control->AttachedDevice,
                484,
                WPP_9a30568c93c333a296ab3c507849cc83_Traceguids,
                (unsigned int)v8);
            }
            if ( (_BYTE)RefsStatusDebugEnabled )
              RefsStatusDebug(v8, (struct _IRP_CONTEXT *)v46, "FsCtrl.c", 0x44C6u);
            RefsRaiseStatusInternal((struct _IRP_CONTEXT *)v46, v8, v23);
          }
          *(_QWORD *)&MasterIrp->Type = 1232;
          LODWORD(MasterIrp->MdlAddress) = 0;
          v76 = v88;
          v88->IoStatus.Information = 192;
          v77 = (unsigned __int16 *)MasterIrp[5].MdlAddress;
          if ( v77[2] )
          {
            v78 = 16LL * v77[2] + 8;
            memmove(&MasterIrp->Tail.CompletionKey + 9, v77, v78);
            WORD1(MasterIrp->IoStatus.Information) = 192;
            *(_DWORD *)(&MasterIrp->Size + 1) |= 0x20000u;
            v76->IoStatus.Information += v78;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            {
              WPP_SF_d(
                WPP_GLOBAL_Control->AttachedDevice,
                485,
                WPP_9a30568c93c333a296ab3c507849cc83_Traceguids,
                WORD2(MasterIrp[5].MdlAddress->Next));
            }
          }
          MasterIrp->UserIosb = (PIO_STATUS_BLOCK)(v85 & -(__int64)(BYTE4(v80) != 0));
          RefsScrubConvertMsScrubContextToScrubOutput((struct _SCRUB_DATA_INPUT *)MasterIrp, BYTE4(v80));
          memset(v94, 0, sizeof(v94));
          LODWORD(v93) = 0;
          *((_QWORD *)&v93 + 1) = 0;
          *(_DWORD *)((char *)&v94[3] + 2) = 0;
          WORD3(v94[3]) = 0;
          MasterIrp[4].Tail.Overlay.DeviceQueueEntry.DeviceListEntry = 0;
          *((_OWORD *)&MasterIrp[4].Tail.CompletionKey + 1) = v93;
          *((_OWORD *)&MasterIrp[4].Tail.CompletionKey + 2) = v94[0];
          *((_OWORD *)&MasterIrp[4].Tail.CompletionKey + 3) = v94[1];
          *((_OWORD *)&MasterIrp[4].Tail.CompletionKey + 4) = v94[2];
          *((_OWORD *)&MasterIrp[4].Tail.CompletionKey + 5) = v94[3];
          *(_OWORD *)&MasterIrp[5].MdlAddress = v94[4];
          *(_OWORD *)&MasterIrp[5].AssociatedIrp.MasterIrp = v94[5];
          *(_OWORD *)&MasterIrp[5].ThreadListEntry.Blink = v94[6];
          *(_OWORD *)&MasterIrp[5].IoStatus.Information = v94[7];
          *(_OWORD *)&MasterIrp[5].UserIosb = v94[8];
          v74 = v94[9];
          v75 = v94[10];
          goto LABEL_276;
        }
LABEL_253:
        Flink = 0;
        v89 = 0;
        v90 = 0;
        *(_DWORD *)&MasterIrp->Type = 1232;
        *(_QWORD *)(&MasterIrp->Size + 1) = 1;
        v8 = 0;
        LODWORD(v80) = 0;
        if ( LODWORD(MasterIrp[4].Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink) == 16 )
          Flink = MasterIrp[4].Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Blink->Flink;
        MasterIrp->UserIosb = (PIO_STATUS_BLOCK)(v85 & -(__int64)(BYTE4(v80) != 0));
        RefsScrubConvertMsScrubContextToScrubOutput((struct _SCRUB_DATA_INPUT *)MasterIrp, BYTE4(v80));
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_iDLLD(
            WPP_GLOBAL_Control->AttachedDevice,
            *((unsigned __int8 *)&MasterIrp->Tail.CompletionKey + 76),
            WPP_GLOBAL_Control,
            Flink,
            MasterIrp[4].Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink,
            *((unsigned __int8 *)&MasterIrp->Tail.CompletionKey + 76),
            *((unsigned __int8 *)&MasterIrp->Tail.CompletionKey + 77),
            WORD2(MasterIrp[5].MdlAddress->Next),
            v80);
        }
        *((_DWORD *)&MasterIrp->Tail.CompletionKey + 21) = MasterIrp[4].Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink;
        v69 = v88;
        v88->IoStatus.Information = 192;
        v69->IoStatus.Information = 296;
        v69->IoStatus.Information = *((unsigned int *)&MasterIrp->Tail.CompletionKey + 21) + 296LL;
        LOWORD(MasterIrp->IoStatus.Information) = *((_WORD *)&MasterIrp->Tail.CompletionKey + 42) + 104;
        *(_DWORD *)(&MasterIrp->Size + 1) |= 0x40000u;
        v70 = (unsigned __int16 *)MasterIrp[5].MdlAddress;
        if ( v70[2] )
        {
          Information_low = LOWORD(v69->IoStatus.Information);
          v72 = 16LL * v70[2] + 8;
          memmove((char *)MasterIrp + Information_low, v70, v72);
          WORD1(MasterIrp->IoStatus.Information) = Information_low;
          *(_DWORD *)(&MasterIrp->Size + 1) |= 0x20000u;
          v69->IoStatus.Information += v72;
        }
        memset(v92, 0, sizeof(v92));
        LODWORD(v91) = 0;
        *((_QWORD *)&v91 + 1) = 0;
        *(_DWORD *)((char *)&v92[3] + 2) = 0;
        WORD3(v92[3]) = 0;
        MasterIrp[4].Tail.Overlay.DeviceQueueEntry.DeviceListEntry = 0;
        *((_OWORD *)&MasterIrp[4].Tail.CompletionKey + 1) = v91;
        *((_OWORD *)&MasterIrp[4].Tail.CompletionKey + 2) = v92[0];
        *((_OWORD *)&MasterIrp[4].Tail.CompletionKey + 3) = v92[1];
        *((_OWORD *)&MasterIrp[4].Tail.CompletionKey + 4) = v92[2];
        *((_OWORD *)&MasterIrp[4].Tail.CompletionKey + 5) = v92[3];
        *(_OWORD *)&MasterIrp[5].MdlAddress = v92[4];
        *(_OWORD *)&MasterIrp[5].AssociatedIrp.MasterIrp = v92[5];
        *(_OWORD *)&MasterIrp[5].ThreadListEntry.Blink = v92[6];
        *(_OWORD *)&MasterIrp[5].IoStatus.Information = v92[7];
        *(_OWORD *)&MasterIrp[5].UserIosb = v92[8];
        v74 = v92[9];
        v75 = v92[10];
LABEL_276:
        *(_OWORD *)&MasterIrp[5].Overlay.AsynchronousParameters.UserApcRoutine = v74;
        *(_OWORD *)&MasterIrp[5].CancelRoutine = v75;
        if ( v86 )
          RefsDeleteMdlAndBuffer(v73, 0, v86);
        return (unsigned int)v8;
      }
    }
    *((_DWORD *)&MasterIrp[4].Tail.CompletionKey + 8) |= 2u;
    goto LABEL_245;
  }
  if ( a5 != 4 && (unsigned __int16)(*a4 - 2051) > 1u )
  {
    v20 = *((_QWORD *)a4 + 18);
    v21 = *(unsigned int *)(v20 + 272);
    if ( (((_DWORD)v21 - 1) & (__int64)MasterIrp->ThreadListEntry.Flink) != 0
      || Blink != (struct _LIST_ENTRY *)-1LL && ((unsigned int)Blink & ((_DWORD)v21 - 1)) != 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_iiD(
          WPP_GLOBAL_Control->AttachedDevice,
          Blink,
          v21,
          MasterIrp->ThreadListEntry.Flink,
          Blink,
          *(_DWORD *)(v20 + 272));
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 481, WPP_9a30568c93c333a296ab3c507849cc83_Traceguids, 3221225485LL);
      }
      if ( !(_BYTE)RefsStatusDebugEnabled )
        return 3221225485LL;
      v11 = 17075;
      goto LABEL_77;
    }
    goto LABEL_90;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_dD(WPP_GLOBAL_Control->AttachedDevice, Blink, v9, a5, *v84);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 479, WPP_9a30568c93c333a296ab3c507849cc83_Traceguids, 3221225659LL);
  }
  if ( (_BYTE)RefsStatusDebugEnabled )
    RefsStatusDebug(-1073741637, 0, "FsCtrl.c", 0x42A1u);
  return 3221225659LL;
}

```

## disassembly

```asm
0x1402baa48  mov     r11, rsp
0x1402baa4b  push    rbx
0x1402baa4c  push    rsi
0x1402baa4d  push    rdi
0x1402baa4e  push    r12
0x1402baa50  push    r13
0x1402baa52  push    r14
0x1402baa54  push    r15
0x1402baa56  sub     rsp, 280h
0x1402baa5d  mov     rax, cs:__security_cookie
0x1402baa64  xor     rax, rsp
0x1402baa67  mov     [rsp+2B8h+var_48], rax
0x1402baa6f  mov     rdi, r9
0x1402baa72  mov     [rsp+2B8h+var_258], r9
0x1402baa77  mov     r12, r8
0x1402baa7a  mov     rax, rdx
0x1402baa7d  mov     [rsp+2B8h+var_238], rdx
0x1402baa85  mov     [rsp+2B8h+var_270], rcx
0x1402baa8a  xor     r14d, r14d
0x1402baa8d  mov     [rsp+2B8h+var_248], r14
0x1402baa92  mov     [rsp+2B8h+var_268], 100000h
0x1402baa9a  mov     r8, [rdx+0B8h]
0x1402baaa1  mov     [rsp+2B8h+var_240], r8
0x1402baaa6  xorps   xmm0, xmm0
0x1402baaa9  xor     ecx, ecx
0x1402baaab  movups  xmmword ptr [r11-80h], xmm0
0x1402baab0  movups  xmmword ptr [r11-70h], xmm0
0x1402baab5  movups  xmmword ptr [r11-60h], xmm0
0x1402baaba  mov     [r11-50h], rcx
0x1402baabe  mov     edx, [r8+10h]
0x1402baac2  cmp     edx, 0C0h
0x1402baac8  jnb     short loc_1402BAB24
0x1402baaca  lea     rdi, WPP_GLOBAL_Control
0x1402baad1  mov     rcx, cs:WPP_GLOBAL_Control
0x1402baad8  cmp     rcx, rdi
0x1402baadb  jz      short loc_1402BAB0B
0x1402baadd  test    dword ptr [rcx+2Ch], 100h
0x1402baae4  jz      short loc_1402BAB0B
0x1402baae6  lea     r13d, [r14+4]
0x1402baaea  cmp     [rcx+29h], r13b
0x1402baaee  jb      short loc_1402BAB0B
0x1402baaf0  mov     edx, 1D7h
0x1402baaf5  mov     r9d, 0C000000Dh
0x1402baafb  lea     r8, WPP_9a30568c93c333a296ab3c507849cc83_Traceguids
0x1402bab02  mov     rcx, [rcx+18h]
0x1402bab06  call    WPP_SF_d
0x1402bab0b  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402bab11  test    al, al
0x1402bab13  jz      loc_1402BAF41
0x1402bab19  mov     r9d, 4237h
0x1402bab1f  jmp     loc_1402BAF2E
0x1402bab24  mov     r15, [rax+18h]
0x1402bab28  mov     r9d, 4D0h
0x1402bab2e  cmp     [r15], r9d
0x1402bab31  jz      short loc_1402BAB8F
0x1402bab33  lea     rdi, WPP_GLOBAL_Control
0x1402bab3a  mov     rcx, cs:WPP_GLOBAL_Control
0x1402bab41  cmp     rcx, rdi
0x1402bab44  jz      short loc_1402BAB76
0x1402bab46  test    dword ptr [rcx+2Ch], 100h
0x1402bab4d  jz      short loc_1402BAB76
0x1402bab4f  mov     r13d, 4
0x1402bab55  cmp     [rcx+29h], r13b
0x1402bab59  jb      short loc_1402BAB76
0x1402bab5b  mov     edx, 1D8h
0x1402bab60  mov     r9d, 0C000000Dh
0x1402bab66  lea     r8, WPP_9a30568c93c333a296ab3c507849cc83_Traceguids
0x1402bab6d  mov     rcx, [rcx+18h]
0x1402bab71  call    WPP_SF_d
0x1402bab76  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402bab7c  test    al, al
0x1402bab7e  jz      loc_1402BAF41
0x1402bab84  mov     r9d, 4240h
0x1402bab8a  jmp     loc_1402BAF2E
0x1402bab8f  mov     rax, [rdi+90h]
0x1402bab96  mov     [rsp+2B8h+var_260], rax
0x1402bab9b  lea     rbx, [r15+4]
0x1402bab9f  mov     r10d, 2
0x1402baba5  cmp     [rax+188h], r10d
0x1402babac  jnb     short loc_1402BAC23
0x1402babae  mov     eax, [rbx]
0x1402babb0  test    al, 8
0x1402babb2  jnz     short loc_1402BAC23
0x1402babb4  lea     rdi, WPP_GLOBAL_Control
0x1402babbb  mov     rcx, cs:WPP_GLOBAL_Control
0x1402babc2  cmp     rcx, rdi
0x1402babc5  jz      short loc_1402BABF5
0x1402babc7  test    dword ptr [rcx+2Ch], 100h
0x1402babce  jz      short loc_1402BABF5
0x1402babd0  lea     r13d, [r10+2]
0x1402babd4  cmp     [rcx+29h], r13b
0x1402babd8  jb      short loc_1402BABF5
0x1402babda  mov     edx, 1D9h
0x1402babdf  mov     r9d, 0C0000479h
0x1402babe5  lea     r8, WPP_9a30568c93c333a296ab3c507849cc83_Traceguids
0x1402babec  mov     rcx, [rcx+18h]
0x1402babf0  call    WPP_SF_d
0x1402babf5  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402babfb  test    al, al
0x1402babfd  jz      short loc_1402BAC18
0x1402babff  mov     r9d, 4251h; unsigned int
0x1402bac05  lea     r8, aFsctrlC; "FsCtrl.c"
0x1402bac0c  xor     edx, edx; struct _IRP_CONTEXT *
0x1402bac0e  mov     ecx, 0C0000479h; Status
0x1402bac13  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x1402bac18  mov     eax, 0C0000479h
0x1402bac1d  jmp     loc_1402BBFF7
0x1402bac23  lea     rsi, [r15+0C0h]
0x1402bac2a  mov     ecx, [rbx]
0x1402bac2c  mov     r11d, 1
0x1402bac32  and     ecx, r11d
0x1402bac35  jz      loc_1402BAD04
0x1402bac3b  mov     eax, [rsi+0Ch]
0x1402bac3e  cmp     eax, 280h
0x1402bac43  jbe     short loc_1402BAC9F
0x1402bac45  lea     rdi, WPP_GLOBAL_Control
0x1402bac4c  mov     rcx, cs:WPP_GLOBAL_Control
0x1402bac53  cmp     rcx, rdi
0x1402bac56  jz      short loc_1402BAC86
0x1402bac58  test    dword ptr [rcx+2Ch], 100h
0x1402bac5f  jz      short loc_1402BAC86
0x1402bac61  lea     r13d, [r11+3]
0x1402bac65  cmp     [rcx+29h], r13b
0x1402bac69  jb      short loc_1402BAC86
0x1402bac6b  mov     edx, 1DAh
0x1402bac70  mov     r9d, 0C000000Dh
0x1402bac76  lea     r8, WPP_9a30568c93c333a296ab3c507849cc83_Traceguids
0x1402bac7d  mov     rcx, [rcx+18h]
0x1402bac81  call    WPP_SF_d
0x1402bac86  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402bac8c  test    al, al
0x1402bac8e  jz      loc_1402BAF41
0x1402bac94  mov     r9d, 425Dh
0x1402bac9a  jmp     loc_1402BAF2E
0x1402bac9f  add     eax, 128h
0x1402baca4  cmp     edx, eax
0x1402baca6  jnb     short loc_1402BAD04
0x1402baca8  lea     rdi, WPP_GLOBAL_Control
0x1402bacaf  mov     rcx, cs:WPP_GLOBAL_Control
0x1402bacb6  cmp     rcx, rdi
0x1402bacb9  jz      short loc_1402BACEB
0x1402bacbb  test    dword ptr [rcx+2Ch], 100h
0x1402bacc2  jz      short loc_1402BACEB
0x1402bacc4  mov     r13d, 4
0x1402bacca  cmp     [rcx+29h], r13b
0x1402bacce  jb      short loc_1402BACEB
0x1402bacd0  mov     edx, 1DBh
0x1402bacd5  mov     r9d, 0C000000Dh
0x1402bacdb  lea     r8, WPP_9a30568c93c333a296ab3c507849cc83_Traceguids
0x1402bace2  mov     rcx, [rcx+18h]
0x1402bace6  call    WPP_SF_d
0x1402baceb  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402bacf1  test    al, al
0x1402bacf3  jz      loc_1402BAF41
0x1402bacf9  mov     r9d, 4265h
0x1402bacff  jmp     loc_1402BAF2E
0x1402bad04  cmp     [r8+8], r9d
0x1402bad08  jnb     short loc_1402BAD7A
0x1402bad0a  lea     rdi, WPP_GLOBAL_Control
0x1402bad11  mov     rcx, cs:WPP_GLOBAL_Control
0x1402bad18  cmp     rcx, rdi
0x1402bad1b  jz      short loc_1402BAD4D
0x1402bad1d  test    dword ptr [rcx+2Ch], 100h
0x1402bad24  jz      short loc_1402BAD4D
0x1402bad26  mov     r13d, 4
0x1402bad2c  cmp     [rcx+29h], r13b
0x1402bad30  jb      short loc_1402BAD4D
0x1402bad32  mov     edx, 1DCh
0x1402bad37  mov     r9d, 0C0000023h
0x1402bad3d  lea     r8, WPP_9a30568c93c333a296ab3c507849cc83_Traceguids
0x1402bad44  mov     rcx, [rcx+18h]
0x1402bad48  call    WPP_SF_d
0x1402bad4d  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402bad53  test    al, al
0x1402bad55  jz      short loc_1402BAD70
0x1402bad57  mov     r9d, 4270h; unsigned int
0x1402bad5d  lea     r8, aFsctrlC; "FsCtrl.c"
0x1402bad64  xor     edx, edx; struct _IRP_CONTEXT *
0x1402bad66  mov     ecx, 0C0000023h; Status
0x1402bad6b  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x1402bad70  mov     eax, 0C0000023h
0x1402bad75  jmp     loc_1402BBFF7
0x1402bad7a  mov     rax, [rdi+88h]
0x1402bad81  mov     [rsp+2B8h+var_230], rax
0x1402bad89  test    ecx, ecx
0x1402bad8b  jz      loc_1402BAE23
0x1402bad91  cmp     [rsi], r10d
0x1402bad94  jnz     short loc_1402BADC7
0x1402bad96  cmp     byte ptr [rsi+4], 17h
0x1402bad9a  jnb     short loc_1402BADC7
0x1402bad9c  cmp     byte ptr [rsi+5], 5
0x1402bada0  jnb     short loc_1402BADC7
0x1402bada2  cmp     byte ptr [rsi+6], 0Ah
0x1402bada6  jnb     short loc_1402BADC7
0x1402bada8  mov     eax, [rsi+0Ch]
0x1402badab  cmp     eax, r9d
0x1402badae  ja      short loc_1402BADC7
0x1402badb0  lea     rcx, [rax+68h]
0x1402badb4  add     rcx, rsi
0x1402badb7  lea     rax, [rsi+4D0h]
0x1402badbe  cmp     rcx, rax
0x1402badc1  jbe     loc_1402BAE4D
0x1402badc7  lea     rdi, WPP_GLOBAL_Control
0x1402badce  mov     rcx, cs:WPP_GLOBAL_Control
0x1402badd5  cmp     rcx, rdi
0x1402badd8  jz      short loc_1402BAE0A
0x1402badda  test    dword ptr [rcx+2Ch], 100h
0x1402bade1  jz      short loc_1402BAE0A
0x1402bade3  mov     r13d, 4
0x1402bade9  cmp     [rcx+29h], r13b
0x1402baded  jb      short loc_1402BAE0A
0x1402badef  mov     edx, 1DDh
0x1402badf4  mov     r9d, 0C000000Dh
0x1402badfa  lea     r8, WPP_9a30568c93c333a296ab3c507849cc83_Traceguids
0x1402bae01  mov     rcx, [rcx+18h]
0x1402bae05  call    WPP_SF_d
0x1402bae0a  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402bae10  test    al, al
0x1402bae12  jz      loc_1402BAF41
0x1402bae18  mov     r9d, 4282h
0x1402bae1e  jmp     loc_1402BAF2E
0x1402bae23  mov     [rsi+4], r14w
0x1402bae28  mov     byte ptr [rsi+6], 9
0x1402bae2c  mov     rcx, rsi
0x1402bae2f  call    MsInitializeScrubKey
0x1402bae34  lea     rcx, [rsi+18h]; void *
0x1402bae38  xor     edx, edx; Val
0x1402bae3a  lea     r8d, [rdx+50h]; Size
0x1402bae3e  call    memset
0x1402bae43  mov     r10d, 2
0x1402bae49  lea     r11d, [r10-1]
0x1402bae4d  mov     rdx, [r15+28h]
0x1402bae51  mov     r13d, 4
0x1402bae57  test    rdx, rdx
0x1402bae5a  jz      loc_1402BAFEE
0x1402bae60  cmp     [rsp+2B8h+arg_20], r13b
0x1402bae68  jz      loc_1402BAF4B
0x1402bae6e  mov     r9d, 803h
0x1402bae74  movzx   eax, word ptr [rdi]
0x1402bae77  sub     ax, r9w
0x1402bae7b  cmp     ax, r11w
0x1402bae7f  jbe     loc_1402BAF4B
0x1402bae85  mov     rax, [rdi+90h]
0x1402bae8c  mov     r8d, [rax+110h]
0x1402bae93  lea     ecx, [r8-1]
0x1402bae97  test    [r15+20h], ecx
0x1402bae9b  jnz     short loc_1402BAEAF
0x1402bae9d  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x1402baea1  jz      loc_1402BAFEE
0x1402baea7  test    ecx, edx
0x1402baea9  jz      loc_1402BAFEE
0x1402baeaf  lea     rdi, WPP_GLOBAL_Control
0x1402baeb6  mov     rcx, cs:WPP_GLOBAL_Control
0x1402baebd  cmp     rcx, rdi
0x1402baec0  jz      short loc_1402BAEE8
0x1402baec2  test    dword ptr [rcx+2Ch], 400h
0x1402baec9  jz      short loc_1402BAEE8
0x1402baecb  cmp     [rcx+29h], r10b
0x1402baecf  jb      short loc_1402BAEE8
0x1402baed1  mov     dword ptr [rsp+2B8h+var_290], r8d
0x1402baed6  mov     [rsp+2B8h+var_298], rdx
0x1402baedb  mov     r9, [r15+20h]
0x1402baedf  mov     rcx, [rcx+18h]
0x1402baee3  call    WPP_SF_iiD
0x1402baee8  mov     rcx, cs:WPP_GLOBAL_Control
0x1402baeef  cmp     rcx, rdi
0x1402baef2  jz      short loc_1402BAF1E
0x1402baef4  test    dword ptr [rcx+2Ch], 100h
0x1402baefb  jz      short loc_1402BAF1E
0x1402baefd  cmp     [rcx+29h], r13b
0x1402baf01  jb      short loc_1402BAF1E
0x1402baf03  mov     edx, 1E1h
0x1402baf08  mov     r9d, 0C000000Dh
0x1402baf0e  lea     r8, WPP_9a30568c93c333a296ab3c507849cc83_Traceguids
0x1402baf15  mov     rcx, [rcx+18h]
0x1402baf19  call    WPP_SF_d
0x1402baf1e  mov     cl, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402baf24  test    cl, cl
0x1402baf26  jz      short loc_1402BAF41
0x1402baf28  mov     r9d, 42B3h; unsigned int
0x1402baf2e  lea     r8, aFsctrlC; "FsCtrl.c"
0x1402baf35  xor     edx, edx; struct _IRP_CONTEXT *
0x1402baf37  mov     ecx, 0C000000Dh; Status
0x1402baf3c  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x1402baf41  mov     eax, 0C000000Dh
0x1402baf46  jmp     loc_1402BBFF7
0x1402baf4b  lea     rdi, WPP_GLOBAL_Control
0x1402baf52  mov     rcx, cs:WPP_GLOBAL_Control
0x1402baf59  cmp     rcx, rdi
0x1402baf5c  jz      short loc_1402BAF8B
0x1402baf5e  test    dword ptr [rcx+2Ch], 400h
0x1402baf65  jz      short loc_1402BAF8B
0x1402baf67  cmp     [rcx+29h], r10b
0x1402baf6b  jb      short loc_1402BAF8B
0x1402baf6d  mov     rbx, [rsp+2B8h+var_258]
0x1402baf72  movsx   eax, word ptr [rbx]
0x1402baf75  movzx   r9d, [rsp+2B8h+arg_20]
0x1402baf7e  mov     dword ptr [rsp+2B8h+var_298], eax
0x1402baf82  mov     rcx, [rcx+18h]
0x1402baf86  call    WPP_SF_dD
  ... truncated ...
```
