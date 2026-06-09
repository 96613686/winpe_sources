# CscSurrogatePostProcess

- ea: `0x140009320`
- end: `0x140009f0d`
- name: `CscSurrogatePostProcess`
- size: `3053`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `broker_com_uri`

## callees

- `0x140009320`
- `0x140009f20`
- `0x14000a4f0`
- `0x14000a5f0`
- `0x14000a64c`
- `0x1400169d4`
- `0x1400190ec`
- `0x14001a548`
- `0x14001a624`
- `0x14001dce4`
- `0x14001dd70`
- `0x14001dec8`
- `0x1400277c0`
- `0x14002f440`
- `0x1400460c4`
- `0x14004a4f4`
- `0x140075350`
- `0x14008a5dc`
- `0x14008d3e0`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1400095ec`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400097c5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140009881`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400095ec`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400097c5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140009881`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140009700`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140009700`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x1400095bf`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x1400095bf`
- `ntoskrnl!ExReleaseResourceLite` at `0x140009764`
- `ntoskrnl!ExReleaseResourceLite` at `0x140009764`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009c5e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009c5e`
- `ntoskrnl!KeInitializeEvent` at `0x140009a8e`
- `ntoskrnl!KeInitializeEvent` at `0x140009a8e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000967e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140009846`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400098a2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400099ec`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000967e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140009846`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400098a2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400099ec`
- `ntoskrnl!KeBugCheckEx` at `0x140009ede`
- `ntoskrnl!KeBugCheckEx` at `0x140009ede`
- `ntoskrnl!IofCallDriver` at `0x140009b0f`
- `ntoskrnl!IofCallDriver` at `0x140009b0f`
- `ntoskrnl!KeAreApcsDisabled` at `0x14000936c`
- `ntoskrnl!KeAreApcsDisabled` at `0x14000944b`
- `ntoskrnl!KeAreApcsDisabled` at `0x14000936c`
- `ntoskrnl!KeAreApcsDisabled` at `0x14000944b`
- `rdbss!RxQueryDeepestLViewInPath` at `0x1400097e1`
- `rdbss!RxQueryDeepestLViewInPath` at `0x1400097e1`
- `rdbss!RxFindRegisteredMiniRedir` at `0x140009891`
- `rdbss!RxFindRegisteredMiniRedir` at `0x140009990`
- `rdbss!RxFindRegisteredMiniRedir` at `0x140009891`
- `rdbss!RxFindRegisteredMiniRedir` at `0x140009990`
- `rdbss!RxDoesRedirSupportLogicalViews` at `0x1400094dc`
- `rdbss!RxDoesRedirSupportLogicalViews` at `0x1400098bf`
- `rdbss!RxDoesRedirSupportLogicalViews` at `0x1400094dc`
- `rdbss!RxDoesRedirSupportLogicalViews` at `0x1400098bf`
- `MUP!MupSurrogateRestartIo` at `0x140009c2b`
- `MUP!MupSurrogateRestartIo` at `0x140009c2b`
- `MUP!MupSurrogateGetUncProviderDeviceObject` at `0x1400093e4`
- `MUP!MupSurrogateGetUncProviderDeviceObject` at `0x1400093e4`

## pseudocode

```c
__int64 __fastcall CscSurrogatePostProcess(__int64 a1)
{
  IRP *v1; // rbx
  int v2; // r15d
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r14
  char MajorFunction; // r12
  BOOLEAN v6; // al
  PFILE_OBJECT FileObject; // r13
  ULONG_PTR v8; // rsi
  UNICODE_STRING *v9; // rax
  UNICODE_STRING v10; // xmm0
  NTSTATUS restarted; // ebx
  int v12; // r14d
  _QWORD *FsContext; // rcx
  _DWORD *v15; // rax
  int v16; // r12d
  __int64 v17; // r12
  int v18; // r14d
  __int64 v19; // rdx
  int v20; // ecx
  int v21; // r8d
  int v22; // eax
  __int64 v23; // rcx
  __int64 v24; // rax
  struct _ERESOURCE *v25; // rcx
  __int64 v26; // rdx
  __int64 v27; // r8
  int Entry; // r14d
  __int64 v29; // r8
  USHORT v30; // r14
  USHORT Length; // bx
  PIRP v32; // r15
  struct _IO_STACK_LOCATION *v33; // rax
  struct _IO_STACK_LOCATION *v34; // rax
  __int64 v35; // rcx
  __int64 v36; // rcx
  __int64 v37; // rax
  __int64 v38; // rax
  int v39; // r8d
  int v40; // eax
  __int64 SurrogateContext; // rax
  ULONG_PTR BugCheckParameter4; // [rsp+20h] [rbp-E0h]
  char v43; // [rsp+30h] [rbp-D0h]
  int v44; // [rsp+60h] [rbp-A0h]
  int v45; // [rsp+60h] [rbp-A0h]
  struct _DEVICE_OBJECT *RegisteredMiniRedir; // [rsp+68h] [rbp-98h]
  UNICODE_STRING String2; // [rsp+70h] [rbp-90h] BYREF
  __int64 v48; // [rsp+80h] [rbp-80h]
  __int64 UncProviderDeviceObject; // [rsp+90h] [rbp-70h]
  _DWORD *FsContext2; // [rsp+98h] [rbp-68h]
  PIRP Irp; // [rsp+A0h] [rbp-60h]
  __int64 v52; // [rsp+A8h] [rbp-58h]
  __int64 v53; // [rsp+B0h] [rbp-50h] BYREF
  struct _DEVICE_OBJECT *v54; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v55; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v56; // [rsp+C8h] [rbp-38h] BYREF
  UNICODE_STRING v57; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v58; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v59; // [rsp+F0h] [rbp-10h]
  __int64 v60; // [rsp+F8h] [rbp-8h]
  __int64 v61; // [rsp+100h] [rbp+0h]
  __int64 v62; // [rsp+108h] [rbp+8h]
  __int64 v63; // [rsp+110h] [rbp+10h]
  struct _KEVENT Event; // [rsp+118h] [rbp+18h] BYREF
  __int128 v65; // [rsp+130h] [rbp+30h] BYREF
  UNICODE_STRING v66[8]; // [rsp+140h] [rbp+40h] BYREF
  __int128 v67; // [rsp+1C0h] [rbp+C0h]
  __int64 v68; // [rsp+230h] [rbp+130h] BYREF
  char v69; // [rsp+238h] [rbp+138h] BYREF
  USHORT v70; // [rsp+240h] [rbp+140h] BYREF
  __int64 v71; // [rsp+248h] [rbp+148h]

  v1 = *(IRP **)a1;
  v2 = *(_DWORD *)(a1 + 60);
  Irp = v1;
  CurrentStackLocation = v1->Tail.Overlay.CurrentStackLocation;
  memset(&Event, 0, sizeof(Event));
  MajorFunction = CurrentStackLocation->MajorFunction;
  LODWORD(v68) = CurrentStackLocation->Parameters.Create.Options;
  v6 = KeAreApcsDisabled();
  FileObject = CurrentStackLocation->FileObject;
  v8 = v6;
  memset(v66, 0, 88);
  FsContext2 = FileObject->FsContext2;
  v71 = 0;
  v56 = 0;
  v53 = 0;
  v9 = *(UNICODE_STRING **)(a1 + 24);
  v58 = 0;
  v10 = *v9;
  v70 = 0;
  String2 = v10;
  v69 = 0;
  UncProviderDeviceObject = MupSurrogateGetUncProviderDeviceObject(a1, &v69);
  v54 = 0;
  v55 = 0;
  v57 = 0;
  v65 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
  {
    v39 = 89;
    if ( !FileObject->RelatedFileObject )
      v39 = 78;
    WPP_SF_DqDqZc(
      WPP_GLOBAL_Control->AttachedDevice,
      (unsigned int)&WPP_GLOBAL_Control,
      v39,
      v2,
      (char)v1,
      MajorFunction,
      (char)FileObject,
      (__int64)&FileObject->FileName,
      v39);
  }
  if ( v2 == -1073741802 && MajorFunction )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_1c04d61f243e374fc6e85b4fffeef555_Traceguids);
    restarted = MupSurrogateRestartIo(a1);
    v12 = 1845;
    if ( !restarted )
      restarted = -1073741802;
    goto LABEL_6;
  }
  restarted = -1073741802;
  if ( MajorFunction )
  {
LABEL_5:
    v12 = 1922;
    goto LABEL_6;
  }
  v16 = v68 & 0x400;
  LODWORD(v68) = v16;
  if ( v2 >= 0 )
    goto LABEL_13;
  if ( (unsigned __int8)CscTransitnOKToGoOffline((unsigned int)v2) )
  {
    v15 = FsContext2;
    goto LABEL_27;
  }
  if ( v2 != -1073741439 || (v15 = FsContext2) == 0 || *(_WORD *)FsContext2 != 0xEB0F || FsContext2[1] != -977269668 )
  {
LABEL_13:
    if ( !v16 && v2 >= 0 )
    {
      if ( v2 == 260 )
      {
        CscOfflineLviewCacheRemoveOfflineEcps(Irp);
      }
      else
      {
        FsContext = CurrentStackLocation->FileObject->FsContext;
        if ( FsContext
          && (unsigned __int16)(*(_WORD *)FsContext + 5087) <= 1u
          && (unsigned __int8)RxDoesRedirSupportLogicalViews(*(_QWORD *)(*(_QWORD *)(FsContext[15] + 32LL) + 48LL)) )
        {
          *(_BYTE *)(a1 + 78) = 1;
        }
        CscSurrogateCheckAndProcessPipeOrIPC(&String2, 0, 0, v43);
      }
    }
    goto LABEL_5;
  }
LABEL_27:
  if ( v15 && *((_BYTE *)v15 + 21) )
  {
    ExFreePoolWithTag(FileObject->FsContext2, 0);
    FileObject->FsContext2 = 0;
    restarted = -1073741634;
    v12 = 1935;
    goto LABEL_6;
  }
  v17 = v71;
  RegisteredMiniRedir = 0;
  if ( v15 )
  {
    v38 = *((_QWORD *)v15 + 3);
    if ( v38 )
      v17 = v38;
    v56 = v17;
  }
  v18 = v68;
  if ( (_DWORD)v68 )
  {
    if ( (unsigned __int8)CscTransitnOKToGoOffline((unsigned int)v2) )
      CscOfflineLviewCacheHandleFailedRemoteBypassOpen(Irp, *(_QWORD *)(a1 + 24));
  }
  else
  {
    if ( !UncProviderDeviceObject )
      goto LABEL_31;
    KeEnterCriticalRegion();
    RegisteredMiniRedir = (struct _DEVICE_OBJECT *)RxFindRegisteredMiniRedir(UncProviderDeviceObject);
    KeLeaveCriticalRegion();
    if ( !RegisteredMiniRedir )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_1c04d61f243e374fc6e85b4fffeef555_Traceguids);
      restarted = -1073741634;
      v12 = 1978;
      if ( v2 != -1073741439 )
        restarted = -1073741802;
      goto LABEL_45;
    }
    if ( !(unsigned __int8)RxDoesRedirSupportLogicalViews(RegisteredMiniRedir) )
    {
      if ( CscDeviceObject != RegisteredMiniRedir )
      {
        v40 = -1073741802;
        if ( v2 == -1073741439 )
          v40 = -1073741634;
        restarted = v40;
      }
      goto LABEL_85;
    }
    if ( CscDeviceObject == RegisteredMiniRedir )
    {
LABEL_85:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_1c04d61f243e374fc6e85b4fffeef555_Traceguids);
      v12 = 2002;
      goto LABEL_45;
    }
  }
LABEL_31:
  if ( RtlPrefixUnicodeString(&CscDclMRxPrefixes, &String2, 1u) )
  {
    restarted = -1073741811;
    v12 = 2027;
    goto LABEL_45;
  }
  if ( v2 != -1073741439 )
  {
    LOBYTE(v71) = 0;
    LOBYTE(v68) = 0;
    KeEnterCriticalRegion();
    v52 = qword_14003BC08;
    v67 = 0;
    if ( qword_14003BC08 )
    {
      ExAcquireResourceSharedLite(*(PERESOURCE *)(*(_QWORD *)(qword_14003BC08 + 8) + 120LL), 1u);
      v23 = *(_QWORD *)(v52 + 8);
      v45 = *(_DWORD *)(v23 + 144);
      v63 = *(_QWORD *)(v23 + 152);
      v62 = *(_QWORD *)(v23 + 160);
      v61 = *(_QWORD *)(v23 + 168);
      v48 = *(_QWORD *)(v23 + 192);
      v60 = *(_QWORD *)(v23 + 200);
      v24 = *(_QWORD *)(v23 + 208);
      v25 = *(struct _ERESOURCE **)(v23 + 120);
      v59 = v24;
      ExReleaseResourceLite(v25);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
      {
        v43 = v62;
        WPP_SF_qDIIIIIID(WPP_GLOBAL_Control->AttachedDevice, v26, v27, v52, v45, v63);
      }
      v19 = v48;
      v20 = 0;
      v21 = 0;
    }
    else
    {
      v19 = v67;
      v48 = v67;
      v20 = -1073741573;
      v21 = 685;
    }
    v44 = v20;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
    {
      WPP_SF_Dd(
        WPP_GLOBAL_Control->AttachedDevice,
        22,
        WPP_3bd1e00568fe30bc384778544301c268_Traceguids,
        (unsigned int)v20,
        v21);
      v20 = v44;
      v19 = v48;
    }
    if ( v20 >= 0 )
    {
      v22 = (unsigned __int8)v71;
      if ( v19 )
        v22 = 1;
      LODWORD(v71) = v22;
    }
    if ( UncProviderDeviceObject && !RegisteredMiniRedir )
      RxFindRegisteredMiniRedir(UncProviderDeviceObject);
    KeLeaveCriticalRegion();
    CscSurrogateCheckAndProcessPipeOrIPC(&String2, (__int64)&v68, 0, v43);
    if ( (_BYTE)v68 )
    {
      v12 = 2116;
      goto LABEL_45;
    }
  }
  if ( v18 )
  {
    v12 = 2127;
    goto LABEL_45;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 30, WPP_1c04d61f243e374fc6e85b4fffeef555_Traceguids);
  KeEnterCriticalRegion();
  LODWORD(v71) = RxQueryDeepestLViewInPath(&String2, &v70, &v54);
  Entry = CscStorepFindOrCreateEntryEx((unsigned int)&v53, 0, 0, (unsigned int)&String2, 128, 0, 0, 0, (__int64)&v58, 0);
  if ( Entry < 0
    || (v29 = *(unsigned __int16 *)(a1 + 76), (_WORD)v29 != 0xFFFF) && (unsigned __int16)v58 < String2.Length - (int)v29 )
  {
    KeLeaveCriticalRegion();
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    {
      LODWORD(BugCheckParameter4) = (unsigned __int16)v58;
      WPP_SF_DDDD(
        WPP_GLOBAL_Control->AttachedDevice,
        31,
        WPP_1c04d61f243e374fc6e85b4fffeef555_Traceguids,
        (unsigned int)Entry,
        BugCheckParameter4,
        String2.Length - *(unsigned __int16 *)(a1 + 76),
        *(unsigned __int16 *)(a1 + 76));
    }
    if ( v2 == -1073741439 )
    {
      restarted = -1073741634;
      if ( Entry )
        restarted = Entry;
    }
    v12 = 2226;
    goto LABEL_45;
  }
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0 )
  {
    v30 = v58;
  }
  else
  {
    WPP_SF_ddd(
      WPP_GLOBAL_Control->AttachedDevice,
      (unsigned __int16)v58,
      v29,
      (unsigned __int16)v58,
      String2.Length - (_DWORD)v29,
      *(unsigned __int16 *)(a1 + 76));
    v30 = v58;
  }
  v57 = String2;
  CscEnDereferenceEntry((__int64)&v53);
  KeLeaveCriticalRegion();
  if ( (int)v71 < 0 || (Length = v70, v30 >= v70) )
  {
    Length = v30;
LABEL_72:
    v57.Length = Length;
    goto LABEL_73;
  }
  if ( v54 == CscDeviceObject )
    goto LABEL_72;
  Length = v57.Length;
LABEL_73:
  memset(v66, 0, 0x58u);
  *(UNICODE_STRING *)&v66[2].Buffer = String2;
  v66[1].Buffer = (PWSTR)289687123;
  *(_DWORD *)&v66[1].Length = -1145324613;
  LOWORD(v66[3].Buffer) = String2.Length - Length;
  FileObject->FsContext = v66;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_1c04d61f243e374fc6e85b4fffeef555_Traceguids, &v57);
  if ( FsContext2 )
    goto LABEL_75;
  SurrogateContext = CscAllocateSurrogateContext();
  if ( SurrogateContext )
  {
    *(_DWORD *)(SurrogateContext + 16) = v2;
    FileObject->FsContext2 = (PVOID)SurrogateContext;
LABEL_75:
    KeInitializeEvent(&Event, SynchronizationEvent, 0);
    v32 = Irp;
    v33 = Irp->Tail.Overlay.CurrentStackLocation;
    *(_OWORD *)&v33[-1].MajorFunction = *(_OWORD *)&v33->MajorFunction;
    *(_OWORD *)&v33[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v33->Parameters.NotifyDirectoryEx.CompletionFilter;
    *(_OWORD *)(&v33[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v33->Parameters.SetQuota + 6);
    v33[-1].FileObject = v33->FileObject;
    v33[-1].Control = 0;
    v34 = v32->Tail.Overlay.CurrentStackLocation;
    v34[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)&CscSurrogateCompletionRoutine;
    v34[-1].Context = &Event;
    v34[-1].Control = -32;
    restarted = CscSurrogatePostpConvertToAbsolutePathCreate(a1, &v65, &v55);
    if ( restarted < 0 )
    {
      v12 = 2389;
    }
    else
    {
      v12 = 0;
      restarted = IofCallDriver(CscDeviceObject, v32);
      if ( restarted == 259 )
      {
        CscCancellableIrpWait(v32, &Event);
        restarted = v32->IoStatus.Status;
      }
      v35 = *(_QWORD *)(*(_QWORD *)a1 + 184LL);
      if ( !*(_BYTE *)v35 )
      {
        v36 = *(_QWORD *)(v35 + 48);
        v37 = v55;
        *(_OWORD *)(v36 + 88) = v65;
        *(_QWORD *)(v36 + 64) = v37;
      }
      *(_BYTE *)(a1 + 78) = restarted >= 0 && restarted != 260;
    }
    goto LABEL_45;
  }
  restarted = -1073741670;
  v12 = 2346;
LABEL_45:
  if ( v17 )
    CscOfflineLviewCacheReleaseEntry(&v56);
LABEL_6:
  if ( KeAreApcsDisabled() != (_BYTE)v8 )
    KeBugCheckEx(0x27u, 0xC5C10991, v8, 0, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_Dd(
      WPP_GLOBAL_Control->AttachedDevice,
      34,
      WPP_1c04d61f243e374fc6e85b4fffeef555_Traceguids,
      (unsigned int)restarted,
      v12);
  return (unsigned int)restarted;
}

```

## disassembly

```asm
0x140009320  push    rbp
0x140009322  push    rbx
0x140009323  push    rsi
0x140009324  push    rdi
0x140009325  push    r12
0x140009327  push    r13
0x140009329  push    r14
0x14000932b  push    r15
0x14000932d  lea     rbp, [rsp-0E8h]
0x140009335  sub     rsp, 1E8h
0x14000933c  mov     rbx, [rcx]
0x14000933f  xor     eax, eax
0x140009341  mov     r15d, [rcx+3Ch]
0x140009345  xorps   xmm0, xmm0
0x140009348  mov     rdi, rcx
0x14000934b  mov     [rbp+120h+Irp], rbx
0x14000934f  mov     r14, [rbx+0B8h]
0x140009356  movups  xmmword ptr [rbp+120h+Event.Header], xmm0
0x14000935a  mov     [rbp+120h+Event.Header.WaitListHead.Blink], rax
0x14000935e  mov     eax, [r14+10h]
0x140009362  movzx   r12d, byte ptr [r14]
0x140009366  mov     dword ptr [rbp+120h+arg_0], eax
0x14000936c  call    cs:__imp_KeAreApcsDisabled
0x140009373  nop     dword ptr [rax+rax+00h]
0x140009378  mov     r13, [r14+30h]
0x14000937c  lea     rdx, [rbp+120h+arg_8]
0x140009383  xorps   xmm0, xmm0
0x140009386  movzx   esi, al
0x140009389  xor     eax, eax
0x14000938b  mov     rcx, rdi
0x14000938e  mov     [rbp+120h+var_90], rax
0x140009395  movups  [rbp+120h+var_E0], xmm0
0x140009399  movups  [rbp+120h+var_D0], xmm0
0x14000939d  movups  [rbp+120h+var_C0], xmm0
0x1400093a1  movups  [rbp+120h+var_B0], xmm0
0x1400093a5  movups  [rbp+120h+var_A0], xmm0
0x1400093ac  mov     rax, [r13+20h]
0x1400093b0  mov     [rbp+120h+var_188], rax
0x1400093b4  xor     eax, eax
0x1400093b6  mov     [rbp+120h+arg_18], rax
0x1400093bd  mov     [rbp+120h+var_158], rax
0x1400093c1  mov     [rbp+120h+var_170], rax
0x1400093c5  mov     rax, [rdi+18h]
0x1400093c9  movups  [rbp+120h+var_140], xmm0
0x1400093cd  movups  xmm0, xmmword ptr [rax]
0x1400093d0  xor     eax, eax
0x1400093d2  mov     [rbp+120h+arg_10], ax
0x1400093d9  movaps  xmmword ptr [rsp+220h+String2.Length], xmm0
0x1400093de  mov     [rbp+120h+arg_8], al
0x1400093e4  call    cs:__imp_MupSurrogateGetUncProviderDeviceObject
0x1400093eb  nop     dword ptr [rax+rax+00h]
0x1400093f0  mov     [rbp+120h+var_190], rax
0x1400093f4  xorps   xmm0, xmm0
0x1400093f7  xor     eax, eax
0x1400093f9  xorps   xmm1, xmm1
0x1400093fc  mov     [rbp+120h+var_168], rax
0x140009400  mov     [rbp+120h+var_160], rax
0x140009404  movups  [rbp+120h+var_150], xmm0
0x140009408  movups  [rbp+120h+var_F0], xmm1
0x14000940c  mov     r10, cs:WPP_GLOBAL_Control
0x140009413  lea     rdx, WPP_GLOBAL_Control
0x14000941a  cmp     r10, rdx
0x14000941d  jz      short loc_14000942C
0x14000941f  mov     ecx, [r10+2Ch]
0x140009423  test    cl, 20h
0x140009426  jnz     loc_140009BAE
0x14000942c  mov     eax, 0C0000016h
0x140009431  cmp     r15d, eax
0x140009434  jz      loc_140009BF7
0x14000943a  mov     ebx, eax
0x14000943c  test    r12b, r12b
0x14000943f  jz      loc_140009541
0x140009445  mov     r14d, 782h
0x14000944b  call    cs:__imp_KeAreApcsDisabled
0x140009452  nop     dword ptr [rax+rax+00h]
0x140009457  cmp     al, sil
0x14000945a  jnz     loc_140009EC5
0x140009460  mov     rcx, cs:WPP_GLOBAL_Control
0x140009467  lea     rax, WPP_GLOBAL_Control
0x14000946e  cmp     rcx, rax
0x140009471  jz      short loc_14000947E
0x140009473  mov     eax, [rcx+2Ch]
0x140009476  test    al, 20h
0x140009478  jnz     loc_140009EEB
0x14000947e  mov     eax, ebx
0x140009480  add     rsp, 1E8h
0x140009487  pop     r15
0x140009489  pop     r14
0x14000948b  pop     r13
0x14000948d  pop     r12
0x14000948f  pop     rdi
0x140009490  pop     rsi
0x140009491  pop     rbx
0x140009492  pop     rbp
0x140009493  retn
0x140009495  cmp     r15d, 0C0000181h
0x14000949c  jz      short loc_140009515
0x14000949e  test    r12d, r12d
0x1400094a1  jnz     short loc_140009445
0x1400094a3  test    r15d, r15d
0x1400094a6  js      short loc_140009445
0x1400094a8  cmp     r15d, 104h
0x1400094af  jz      loc_140009EB7
0x1400094b5  mov     rax, [r14+30h]
0x1400094b9  mov     rcx, [rax+18h]
0x1400094bd  test    rcx, rcx
0x1400094c0  jz      short loc_1400094EC
0x1400094c2  mov     eax, 13DFh
0x1400094c7  add     ax, [rcx]
0x1400094ca  cmp     ax, 1
0x1400094ce  ja      short loc_1400094EC
0x1400094d0  mov     rax, [rcx+78h]
0x1400094d4  mov     rcx, [rax+20h]
0x1400094d8  mov     rcx, [rcx+30h]
0x1400094dc  call    cs:__imp_RxDoesRedirSupportLogicalViews
0x1400094e3  nop     dword ptr [rax+rax+00h]
0x1400094e8  test    al, al
0x1400094ea  jnz     short loc_14000953B
0x1400094ec  mov     [rsp+220h+var_1F8], 0; __int64
0x1400094f5  lea     rcx, [rsp+220h+String2]; String2
0x1400094fa  xor     r9d, r9d
0x1400094fd  mov     [rsp+220h+BugCheckParameter4], 0; __int64
0x140009506  mov     r8b, 1
0x140009509  xor     edx, edx
0x14000950b  call    CscSurrogateCheckAndProcessPipeOrIPC
0x140009510  jmp     loc_140009445
0x140009515  mov     rax, [rbp+120h+var_188]
0x140009519  test    rax, rax
0x14000951c  jz      short loc_14000949E
0x14000951e  mov     ecx, 0EB0Fh
0x140009523  cmp     [rax], cx
0x140009526  jnz     loc_14000949E
0x14000952c  cmp     dword ptr [rax+4], 0C5C00C5Ch
0x140009533  jnz     loc_14000949E
0x140009539  jmp     short loc_140009573
0x14000953b  mov     byte ptr [rdi+4Eh], 1
0x14000953f  jmp     short loc_1400094EC
0x140009541  mov     r12d, dword ptr [rbp+120h+arg_0]
0x140009548  and     r12d, 400h
0x14000954f  mov     dword ptr [rbp+120h+arg_0], r12d
0x140009556  test    r15d, r15d
0x140009559  jns     loc_14000949E
0x14000955f  mov     ecx, r15d
0x140009562  call    CscTransitnOKToGoOffline
0x140009567  test    al, al
0x140009569  jz      loc_140009495
0x14000956f  mov     rax, [rbp+120h+var_188]
0x140009573  test    rax, rax
0x140009576  jnz     loc_140009C4E
0x14000957c  mov     r12, [rbp+120h+arg_18]
0x140009583  mov     [rsp+220h+var_1B8], 0
0x14000958c  test    rax, rax
0x14000958f  jnz     loc_140009B9A
0x140009595  mov     r14d, dword ptr [rbp+120h+arg_0]
0x14000959c  test    r14d, r14d
0x14000959f  jnz     loc_140009D0D
0x1400095a5  cmp     [rbp+120h+var_190], 0
0x1400095aa  jnz     loc_140009881
0x1400095b0  mov     r8b, 1; CaseInSensitive
0x1400095b3  lea     rdx, [rsp+220h+String2]; String2
0x1400095b8  lea     rcx, CscDclMRxPrefixes; String1
0x1400095bf  call    cs:__imp_RtlPrefixUnicodeString
0x1400095c6  nop     dword ptr [rax+rax+00h]
0x1400095cb  test    al, al
0x1400095cd  jnz     loc_140009D2F
0x1400095d3  cmp     r15d, 0C0000181h
0x1400095da  jz      loc_1400097A5
0x1400095e0  mov     byte ptr [rbp+120h+arg_18], al
0x1400095e6  mov     byte ptr [rbp+120h+arg_0], al
0x1400095ec  call    cs:__imp_KeEnterCriticalRegion
0x1400095f3  nop     dword ptr [rax+rax+00h]
0x1400095f8  mov     rax, cs:qword_14003BC08
0x1400095ff  xorps   xmm0, xmm0
0x140009602  mov     [rbp+120h+var_178], rax
0x140009606  movups  [rbp+120h+var_60], xmm0
0x14000960d  test    rax, rax
0x140009610  jnz     loc_1400096F6
0x140009616  mov     rdx, qword ptr [rbp+120h+var_60]
0x14000961d  lea     rax, WPP_GLOBAL_Control
0x140009624  mov     [rbp+120h+var_1A0], rdx
0x140009628  mov     ecx, 0C00000FBh
0x14000962d  mov     r8d, 2ADh
0x140009633  mov     [rsp+220h+var_1C0], ecx
0x140009637  mov     r10, cs:WPP_GLOBAL_Control
0x14000963e  cmp     r10, rax
0x140009641  jz      short loc_140009651
0x140009643  test    dword ptr [r10+2Ch], 40000h
0x14000964b  jnz     loc_140009D8F
0x140009651  mov     r8d, 1
0x140009657  test    ecx, ecx
0x140009659  js      short loc_140009671
0x14000965b  mov     eax, dword ptr [rbp+120h+arg_18]
0x140009661  test    rdx, rdx
0x140009664  movzx   eax, al
0x140009667  cmovnz  eax, r8d
0x14000966b  mov     dword ptr [rbp+120h+arg_18], eax
0x140009671  mov     rax, [rbp+120h+var_190]
0x140009675  test    rax, rax
0x140009678  jnz     loc_140009981
0x14000967e  call    cs:__imp_KeLeaveCriticalRegion
0x140009685  nop     dword ptr [rax+rax+00h]
0x14000968a  mov     rax, [rsp+220h+var_1B8]
0x14000968f  test    rax, rax
0x140009692  jnz     loc_14000996E
0x140009698  cmp     byte ptr [rbp+120h+arg_18], 0
0x14000969f  jnz     loc_140009957
0x1400096a5  xor     dl, dl
0x1400096a7  xor     r9d, r9d
0x1400096aa  lea     rax, [rbp+120h+arg_0]
0x1400096b1  mov     [rsp+220h+var_1F8], 0; __int64
0x1400096ba  xor     r8d, r8d
0x1400096bd  mov     [rsp+220h+BugCheckParameter4], rax; __int64
0x1400096c2  lea     rcx, [rsp+220h+String2]; String2
0x1400096c7  call    CscSurrogateCheckAndProcessPipeOrIPC
0x1400096cc  cmp     byte ptr [rbp+120h+arg_0], 0
0x1400096d3  jz      loc_1400097A5
0x1400096d9  mov     r14d, 844h
0x1400096df  test    r12, r12
0x1400096e2  jz      loc_14000944B
0x1400096e8  lea     rcx, [rbp+120h+var_158]
0x1400096ec  call    CscOfflineLviewCacheReleaseEntry
0x1400096f1  jmp     loc_14000944B
0x1400096f6  mov     rcx, [rax+8]
0x1400096fa  mov     dl, 1; Wait
0x1400096fc  mov     rcx, [rcx+78h]; Resource
0x140009700  call    cs:__imp_ExAcquireResourceSharedLite
0x140009707  nop     dword ptr [rax+rax+00h]
0x14000970c  mov     rax, [rbp+120h+var_178]
0x140009710  mov     rcx, [rax+8]
0x140009714  mov     eax, [rcx+90h]
0x14000971a  mov     [rsp+220h+var_1C0], eax
0x14000971e  mov     rax, [rcx+98h]
0x140009725  mov     [rbp+120h+var_110], rax
0x140009729  mov     rax, [rcx+0A0h]
0x140009730  mov     [rbp+120h+var_118], rax
0x140009734  mov     rax, [rcx+0A8h]
0x14000973b  mov     [rbp+120h+var_120], rax
0x14000973f  mov     rax, [rcx+0C0h]
0x140009746  mov     [rbp+120h+var_1A0], rax
0x14000974a  mov     rax, [rcx+0C8h]
0x140009751  mov     [rbp+120h+var_128], rax
0x140009755  mov     rax, [rcx+0D0h]
0x14000975c  mov     rcx, [rcx+78h]; Resource
0x140009760  mov     [rbp+120h+var_130], rax
0x140009764  call    cs:__imp_ExReleaseResourceLite
0x14000976b  nop     dword ptr [rax+rax+00h]
0x140009770  mov     rcx, cs:WPP_GLOBAL_Control
0x140009777  lea     rax, WPP_GLOBAL_Control
0x14000977e  cmp     rcx, rax
0x140009781  jz      short loc_140009797
0x140009783  test    dword ptr [rcx+2Ch], 40000h
0x14000978a  jnz     loc_140009D3F
0x140009790  lea     rax, WPP_GLOBAL_Control
0x140009797  mov     rdx, [rbp+120h+var_1A0]
0x14000979b  xor     ecx, ecx
0x14000979d  mov     r8d, ecx
0x1400097a0  jmp     loc_140009633
0x1400097a5  test    r14d, r14d
0x1400097a8  jnz     loc_140009DB9
0x1400097ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1400097b5  lea     rax, WPP_GLOBAL_Control
0x1400097bc  cmp     rcx, rax
0x1400097bf  jnz     loc_1400098EA
0x1400097c5  call    cs:__imp_KeEnterCriticalRegion
0x1400097cc  nop     dword ptr [rax+rax+00h]
0x1400097d1  lea     r8, [rbp+120h+var_168]
0x1400097d5  lea     rdx, [rbp+120h+arg_10]
0x1400097dc  lea     rcx, [rsp+220h+String2]
0x1400097e1  call    cs:__imp_RxQueryDeepestLViewInPath
0x1400097e8  nop     dword ptr [rax+rax+00h]
0x1400097ed  mov     [rsp+220h+var_1D8], 0
0x1400097f6  lea     r9, [rsp+220h+String2]
0x1400097fb  mov     dword ptr [rbp+120h+arg_18], eax
0x140009801  lea     rcx, [rbp+120h+var_170]
0x140009805  lea     rax, [rbp+120h+var_140]
0x140009809  xor     r8d, r8d
0x14000980c  mov     [rsp+220h+var_1E0], rax
0x140009811  xor     edx, edx
0x140009813  mov     [rsp+220h+var_1E8], 0
0x14000981c  mov     [rsp+220h+var_1F0], 0
0x140009825  mov     [rsp+220h+var_1F8], 0
0x14000982e  mov     dword ptr [rsp+220h+BugCheckParameter4], 80h
0x140009836  call    CscStorepFindOrCreateEntryEx
0x14000983b  mov     r14d, eax
0x14000983e  test    eax, eax
0x140009840  jns     loc_1400099A6
0x140009846  call    cs:__imp_KeLeaveCriticalRegion
0x14000984d  nop     dword ptr [rax+rax+00h]
0x140009852  mov     rcx, cs:WPP_GLOBAL_Control
0x140009859  lea     rax, WPP_GLOBAL_Control
0x140009860  cmp     rcx, rax
0x140009863  jnz     loc_14000990F
0x140009869  cmp     r15d, 0C0000181h
0x140009870  jz      loc_140009EA6
0x140009876  mov     r14d, 8B2h
0x14000987c  jmp     loc_1400096DF
0x140009881  call    cs:__imp_KeEnterCriticalRegion
0x140009888  nop     dword ptr [rax+rax+00h]
0x14000988d  mov     rcx, [rbp+120h+var_190]
0x140009891  call    cs:__imp_RxFindRegisteredMiniRedir
  ... truncated ...
```
