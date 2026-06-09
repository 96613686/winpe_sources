# RefsReadUsnJournal(_IRP_CONTEXT *,_IRP *,uchar,uchar)

- ea: `0x1402e3ff0`
- end: `0x1402e525c`
- name: `?RefsReadUsnJournal@@YAJPEAU_IRP_CONTEXT@@PEAU_IRP@@EE@Z`
- size: `4716`
- prototype: `__int64 __usercall@<rax>(struct _IRP_CONTEXT *@<rcx>, PIRP Irp@<rdx>, unsigned __int8@<r8b>, unsigned __int8@<r9b>)`
- caller_count: `2`
- callee_count: `21`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140320e78`
- `0x140332394`

## callees

- `0x1400409a0`
- `0x140041b40`
- `0x140081670`
- `0x140087ee0`
- `0x14008c400`
- `0x14008dbd0`
- `0x140093360`
- `0x140096fd0`
- `0x1400ac190`
- `0x1400ca788`
- `0x1400d9ba0`
- `0x1401e9ce0`
- `0x1401e9d10`
- `0x1401e9e40`
- `0x1401ea140`
- `0x1402e3ff0`
- `0x1402e5fc0`
- `0x140302dbc`
- `0x1403033f0`
- `0x14031ac80`
- `0x14031c8e0`

## import_xrefs

- `ntoskrnl!ExRaiseStatus` at `0x1402e522c`
- `ntoskrnl!ExRaiseStatus` at `0x1402e522c`
- `ntoskrnl!CcUnpinData` at `0x1402e4ab8`
- `ntoskrnl!CcUnpinData` at `0x1402e4e7c`
- `ntoskrnl!CcUnpinData` at `0x1402e5090`
- `ntoskrnl!CcUnpinData` at `0x1403466a6`
- `ntoskrnl!CcUnpinData` at `0x1402e4ab8`
- `ntoskrnl!CcUnpinData` at `0x1402e4e7c`
- `ntoskrnl!CcUnpinData` at `0x1402e5090`
- `ntoskrnl!CcUnpinData` at `0x1403466a6`
- `ntoskrnl!CcMapData` at `0x1402e4a49`
- `ntoskrnl!CcMapData` at `0x1402e4a49`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x1402e408a`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x1402e408a`
- `ntoskrnl!ProbeForRead` at `0x1402e42a6`
- `ntoskrnl!ProbeForRead` at `0x1402e42a6`
- `ntoskrnl!ProbeForWrite` at `0x1402e42cb`
- `ntoskrnl!ProbeForWrite` at `0x1402e42cb`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1402e5133`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1402e5133`
- `ntoskrnl!ExReleaseFastResource` at `0x1402e4af0`
- `ntoskrnl!ExReleaseFastResource` at `0x1402e50c1`
- `ntoskrnl!ExReleaseFastResource` at `0x1403466e5`
- `ntoskrnl!ExReleaseFastResource` at `0x1402e4af0`
- `ntoskrnl!ExReleaseFastResource` at `0x1402e50c1`
- `ntoskrnl!ExReleaseFastResource` at `0x1403466e5`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x1402e433c`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x1402e433c`

## pseudocode

```c
__int64 __fastcall RefsReadUsnJournal(struct _IRP_CONTEXT *a1, PIRP Irp, char a3, char a4)
{
  PIRP v6; // r13
  struct _IRP_CONTEXT *v7; // rsi
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r14
  int v9; // edx
  NTSTATUS v10; // ebx
  __int64 v12; // rax
  char v13; // r12
  struct _IRP_CONTEXT *v14; // rcx
  unsigned int v15; // edx
  unsigned int v16; // r8d
  __int64 v17; // r8
  _WORD *v18; // r9
  bool v19; // zf
  struct _VCB *v20; // r15
  int v21; // ecx
  unsigned int v22; // r9d
  unsigned int Options; // eax
  unsigned int v24; // r9d
  size_t v25; // r8
  PNAMED_PIPE_CREATE_PARAMETERS Parameters; // rdx
  unsigned int Length; // r14d
  unsigned int v28; // r14d
  _WORD *v29; // r12
  __int64 v30; // rdx
  bool v31; // sf
  unsigned int v32; // r9d
  int v33; // edx
  int v34; // eax
  __int64 v35; // r14
  __int64 v36; // r14
  char *v37; // rcx
  __int64 v38; // rdx
  bool v39; // r14
  unsigned int *v40; // rcx
  __int64 v41; // rdx
  __int64 v42; // r8
  unsigned int v43; // r10d
  int v44; // eax
  int v45; // r14d
  unsigned int v46; // r14d
  char *v47; // rax
  char v48; // r11
  void *v49; // rcx
  int v50; // r14d
  char v51; // al
  __int64 v52; // rax
  int v53; // eax
  IRP *v54; // rdx
  bool v55; // [rsp+44h] [rbp-164h]
  unsigned __int8 v56; // [rsp+49h] [rbp-15Fh]
  char v57[8]; // [rsp+50h] [rbp-158h] BYREF
  char v58; // [rsp+58h] [rbp-150h]
  int v59; // [rsp+5Ch] [rbp-14Ch]
  PVOID Buffer; // [rsp+60h] [rbp-148h] BYREF
  PIRP Irpa; // [rsp+68h] [rbp-140h]
  int v62; // [rsp+70h] [rbp-138h]
  unsigned int v63; // [rsp+74h] [rbp-134h]
  __int64 v64; // [rsp+78h] [rbp-130h]
  char v65; // [rsp+80h] [rbp-128h]
  PVOID Bcb; // [rsp+88h] [rbp-120h] BYREF
  struct _VCB *v67; // [rsp+90h] [rbp-118h] BYREF
  _WORD *v68; // [rsp+98h] [rbp-110h]
  __int64 v69; // [rsp+A0h] [rbp-108h]
  __int64 v70; // [rsp+A8h] [rbp-100h] BYREF
  union _LARGE_INTEGER FileOffset; // [rsp+B0h] [rbp-F8h] BYREF
  struct _IRP_CONTEXT *v72; // [rsp+B8h] [rbp-F0h]
  __int64 v73; // [rsp+C0h] [rbp-E8h] BYREF
  _WORD *v74; // [rsp+C8h] [rbp-E0h]
  __int64 v75; // [rsp+D0h] [rbp-D8h]
  __int64 v76[10]; // [rsp+E0h] [rbp-C8h] BYREF
  __int128 v77; // [rsp+130h] [rbp-78h] BYREF
  __int128 v78; // [rsp+140h] [rbp-68h]
  __int128 v79; // [rsp+150h] [rbp-58h] BYREF

  v57[1] = a4;
  v58 = a3;
  v6 = Irp;
  Irpa = Irp;
  v7 = a1;
  v72 = a1;
  Buffer = 0;
  Bcb = 0;
  v77 = 0;
  v78 = 0;
  v79 = 0;
  v67 = 0;
  FileOffset.QuadPart = 0;
  v68 = 0;
  memset(v76, 0, 0x48u);
  ExInitializeFastOwnerEntry(v76);
  CurrentStackLocation = v6->Tail.Overlay.CurrentStackLocation;
  RefsDecodeFileObject(v7, CurrentStackLocation->FileObject, &v67, &v73);
  if ( !a4 && (!v68 || (v68[44] & 0x200) == 0 && (v6->RequestorMode || CurrentStackLocation->MinorFunction != 4)) )
  {
    v10 = -1073741790;
    RefsCompleteRequest((PSECURITY_SUBJECT_CONTEXT *)v7, v6, -1073741790);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_2b67ce2bc1f03db543291d529fa9643f_Traceguids, 3221225506LL);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741790, 0, "UsnSup.c", 0x47Cu);
    return (unsigned int)v10;
  }
  v55 = 0;
  v56 = 0;
  LOBYTE(v9) = 1;
  v62 = v9;
  if ( a3 )
  {
    LOBYTE(v9) = (*((_BYTE *)v7 + 8) & 1) != 0;
    v62 = v9;
  }
  v12 = *((_QWORD *)v7 + 1);
  v73 = (v12 & 1) == 0;
  v75 = v73;
  *((_QWORD *)v7 + 1) = v12 | 1;
  v13 = RefsEffectiveMode(v6, CurrentStackLocation);
  v10 = RefsLockUserBuffer(v14, v6, IoWriteAccess, CurrentStackLocation->Parameters.Read.Length);
  if ( v10 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        18,
        WPP_2b67ce2bc1f03db543291d529fa9643f_Traceguids,
        (unsigned int)v10);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
      RefsStatusDebug(v10, v7, "UsnSup.c", 0x4A3u);
    RefsRaiseStatusInternal(v7, v10, v16);
  }
  v18 = RefsMapUserBuffer(v6, v15);
  v68 = v18;
  if ( v6->RequestorMode )
  {
    if ( a3 )
    {
      ProbeForRead(
        CurrentStackLocation->Parameters.CreatePipe.Parameters,
        CurrentStackLocation->Parameters.Create.Options,
        4u);
      v18 = v68;
    }
    if ( !v6->MdlAddress )
      ProbeForWrite(v18, CurrentStackLocation->Parameters.Read.Length, 4u);
  }
  else if ( CurrentStackLocation->Parameters.CreatePipe.Parameters != (PNAMED_PIPE_CREATE_PARAMETERS)(((unsigned __int64)&CurrentStackLocation->Parameters.CreatePipe.Parameters->NamedPipeType + 3) & 0xFFFFFFFFFFFFFFFCuLL)
         || !v6->MdlAddress && v18 != (_WORD *)(((unsigned __int64)v18 + 3) & 0xFFFFFFFFFFFFFFFCuLL) )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    {
      v10 = -1073741811;
    }
    else
    {
      v10 = -1073741811;
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_2b67ce2bc1f03db543291d529fa9643f_Traceguids, 3221225485LL);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741811, 0, "UsnSup.c", 0x4BFu);
    v20 = v67;
    goto LABEL_214;
  }
  v19 = a3 == 0;
  v20 = v67;
  if ( !v19 )
    v56 = RefsAcquireSharedVcb(v7, v67, 1u);
  LOBYTE(v17) = 1;
  ExAcquireFastResourceShared((char *)v20 + 1208, v76, v17);
  *((_DWORD *)v7 + 1) |= 0x2000u;
  v55 = 1;
  v21 = *((_DWORD *)v20 + 6);
  if ( (v21 & 0x100000) != 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_2b67ce2bc1f03db543291d529fa9643f_Traceguids, 3221226167LL);
    }
    if ( !(_BYTE)RefsStatusDebugEnabled )
      goto LABEL_41;
    v22 = 1238;
LABEL_40:
    RefsStatusDebug(-1073741129, 0, "UsnSup.c", v22);
LABEL_41:
    v10 = -1073741129;
    goto LABEL_223;
  }
  if ( !*((_QWORD *)v20 + 5) || (v21 & 0x80000) == 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    {
      v10 = -1073741128;
    }
    else
    {
      v10 = -1073741128;
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_2b67ce2bc1f03db543291d529fa9643f_Traceguids, 3221226168LL);
    }
    if ( !(_BYTE)RefsStatusDebugEnabled )
      goto LABEL_214;
    v24 = 1247;
    goto LABEL_213;
  }
  Options = CurrentStackLocation->Parameters.Create.Options;
  if ( Options >= 0x28 )
  {
    v25 = 48;
    if ( Options != 48 )
    {
      DWORD2(v79) = 131074;
      v25 = 40;
    }
    Parameters = CurrentStackLocation->Parameters.CreatePipe.Parameters;
    if ( v13 )
      RtlCopyFromUser(&v77, Parameters, v25);
    else
      RtlCopyVolatileMemory(&v77, Parameters, v25);
    if ( (_QWORD)v79 != *((_QWORD *)v20 + 113) )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        v10 = -1073741811;
      }
      else
      {
        v10 = -1073741811;
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_2b67ce2bc1f03db543291d529fa9643f_Traceguids, 3221225485LL);
      }
      if ( !(_BYTE)RefsStatusDebugEnabled )
        goto LABEL_214;
      v24 = 1290;
      goto LABEL_213;
    }
    if ( WORD4(v79) > WORD5(v79) )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        v10 = -1073741811;
      }
      else
      {
        v10 = -1073741811;
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_2b67ce2bc1f03db543291d529fa9643f_Traceguids, 3221225485LL);
      }
      if ( !(_BYTE)RefsStatusDebugEnabled )
        goto LABEL_214;
      v24 = 1299;
      goto LABEL_213;
    }
    if ( WORD4(v79) > 3u || WORD5(v79) < 2u )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        v10 = -1073741811;
      }
      else
      {
        v10 = -1073741811;
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_2b67ce2bc1f03db543291d529fa9643f_Traceguids, 3221225485LL);
      }
      if ( !(_BYTE)RefsStatusDebugEnabled )
        goto LABEL_214;
      v24 = 1308;
      goto LABEL_213;
    }
    Length = CurrentStackLocation->Parameters.Read.Length;
    if ( Length < 8 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        v10 = -1073741789;
      }
      else
      {
        v10 = -1073741789;
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_2b67ce2bc1f03db543291d529fa9643f_Traceguids, 3221225507LL);
      }
      if ( !(_BYTE)RefsStatusDebugEnabled )
        goto LABEL_214;
      v24 = 1318;
      goto LABEL_213;
    }
    v28 = Length - 8;
    *(_DWORD *)&v57[4] = v28;
    v29 = v68 + 4;
    v74 = v68 + 4;
    v63 = 8;
    if ( v56 )
    {
      RefsReleaseVcb(v7, v20);
      v56 = 0;
    }
    if ( (*(_DWORD *)(*((_QWORD *)v20 + 5) + 300LL) & 0x4000) != 0 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        v10 = -1073741202;
      }
      else
      {
        v10 = -1073741202;
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_2b67ce2bc1f03db543291d529fa9643f_Traceguids, 3221226094LL);
      }
      if ( !(_BYTE)RefsStatusDebugEnabled )
        goto LABEL_214;
      v24 = 1340;
      goto LABEL_213;
    }
    v30 = v77;
    v31 = (__int64)v77 < 0;
    if ( !(_QWORD)v77 )
    {
      v30 = *((_QWORD *)v20 + 115);
      *(_QWORD *)&v77 = v30;
      v31 = v30 < 0;
    }
    if ( v31 || *((_QWORD *)&v78 + 1) > 0x7FFFFFFFFFFFFFFFuLL || v30 + *((_QWORD *)&v78 + 1) < 0 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        v10 = -1073741811;
      }
      else
      {
        v10 = -1073741811;
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_2b67ce2bc1f03db543291d529fa9643f_Traceguids, 3221225485LL);
      }
      if ( !(_BYTE)RefsStatusDebugEnabled )
        goto LABEL_214;
      v24 = 1362;
      goto LABEL_213;
    }
    while ( 1 )
    {
      if ( v30 >= *((_QWORD *)v20 + 116) )
      {
        if ( (*((_DWORD *)v20 + 6) & 0x2000000) != 0 )
        {
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
          {
            v10 = -1073741662;
          }
          else
          {
            v10 = -1073741662;
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              29,
              WPP_2b67ce2bc1f03db543291d529fa9643f_Traceguids,
              3221225634LL);
          }
          if ( !(_BYTE)RefsStatusDebugEnabled )
            goto LABEL_223;
          v32 = 1385;
          goto LABEL_108;
        }
        if ( !*((_QWORD *)&v78 + 1) )
          goto LABEL_191;
        v33 = (unsigned __int8)v62;
        if ( Irpa != *((PIRP *)v7 + 9) )
          v33 = 0;
        v62 = v33;
        v65 = v33;
        v69 = *((_QWORD *)v20 + 5);
        v34 = RefsWaitForUsn((int)v7, Irpa, (int)v20, v57[1], v33, (__int64)&v77, (__int64)v76);
        v10 = v34;
        if ( !(_BYTE)v62 )
        {
          if ( v34 == 259 || v34 == -1073741536 || v34 == -1073741129 )
            v55 = Irpa != *((PIRP *)v7 + 9);
          goto LABEL_223;
        }
        if ( v34 < 0 )
        {
LABEL_223:
          v39 = v55;
LABEL_224:
          v6 = Irpa;
          goto LABEL_225;
        }
        if ( v69 != *((_QWORD *)v20 + 5) )
        {
          if ( (*((_DWORD *)v20 + 6) & 0x100000) != 0 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_d(
                WPP_GLOBAL_Control->AttachedDevice,
                30,
                WPP_2b67ce2bc1f03db543291d529fa9643f_Traceguids,
                3221226167LL);
            }
            if ( !(_BYTE)RefsStatusDebugEnabled )
              goto LABEL_41;
            v22 = 1451;
            goto LABEL_40;
          }
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
          {
            v10 = -1073741128;
          }
          else
          {
            v10 = -1073741128;
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              31,
              WPP_2b67ce2bc1f03db543291d529fa9643f_Traceguids,
              3221226168LL);
          }
          if ( !(_BYTE)RefsStatusDebugEnabled )
            goto LABEL_223;
          v32 = 1453;
LABEL_108:
          RefsStatusDebug(v10, 0, "UsnSup.c", v32);
          goto LABEL_223;
        }
        v30 = v77;
      }
      if ( v30 < *((_QWORD *)v20 + 115) )
      {
        *(_QWORD *)&v77 = *((_QWORD *)v20 + 115);
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
        {
          v10 = -1073741105;
        }
        else
        {
          v10 = -1073741105;
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            32,
            WPP_2b67ce2bc1f03db543291d529fa9643f_Traceguids,
            3221226191LL);
        }
        if ( (_BYTE)RefsStatusDebugEnabled )
          RefsStatusDebug(-1073741105, 0, "UsnSup.c", 0x5D1u);
        v30 = v77;
LABEL_191:
        v6 = Irpa;
        Irpa->IoStatus.Information = v63;
        *(_QWORD *)v68 = v30;
        goto LABEL_214;
      }
LABEL_144:
      if ( !v28 )
        goto LABEL_191;
      v35 = *((_QWORD *)v20 + 116);
      if ( v30 < v35 )
        break;
      v28 = *(_DWORD *)&v57[4];
      if ( !*(_DWORD *)&v57[4] || v63 != 8 )
        goto LABEL_191;
    }
    FileOffset.QuadPart = 0;
    v57[0] = 0;
    v70 = 0;
    v36 = v35 - v30;
    v64 = v36;
    if ( v36 > 0x40000 - ((unsigned int)v30 & 0x3FFFF) )
      v36 = 0x40000 - ((unsigned int)v30 & 0x3FFFF);
    v69 = v36;
    v64 = v36;
    FileOffset.QuadPart = RefsFileOffsetFromUsn(v20, v30);
    CcMapData(*(PFILE_OBJECT *)(*((_QWORD *)v20 + 5) + 240LL), &FileOffset, v36, 0x11u, &Bcb, &Buffer);
    LODWORD(v37) = (_DWORD)Buffer;
    LODWORD(v38) = v77;
LABEL_149:
    if ( !(unsigned __int8)RefsValidateUsnPage(
                             (_DWORD)v7,
                             (unsigned int)v37 & 0xFFFFF000,
                             (unsigned int)v38 & 0xFFFFF000,
                             (unsigned int)&v77,
                             *((_QWORD *)v20 + 116),
                             (__int64)v57,
                             (__int64)&v70) )
    {
      CcUnpinData(Bcb);
      Bcb = 0;
      *((_DWORD *)v7 + 1) &= 0xFFFFCFFF;
      ExReleaseFastResource((char *)v20 + 1208, v76);
      v39 = 0;
      v10 = RefsRepairUsnJournal(v7, (__int64)&v79, v58, (__int64)v57, (__int64)&v70);
      if ( v10 < 0 )
        goto LABEL_224;
      v55 = 1;
      v30 = v77;
      v28 = *(_DWORD *)&v57[4];
      goto LABEL_144;
    }
    if ( !v57[0] )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        v10 = -1073741811;
      }
      else
      {
        v10 = -1073741811;
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_2b67ce2bc1f03db543291d529fa9643f_Traceguids, 3221225485LL);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
      {
        v32 = 1596;
        goto LABEL_108;
      }
      goto LABEL_223;
    }
    v40 = (unsigned int *)Buffer;
    v41 = v77;
    v42 = v70;
    while ( 1 )
    {
      if ( v41 >= v42 )
      {
        if ( !*(_DWORD *)&v57[4] )
          goto LABEL_187;
        v52 = -(int)v42 & 0xFFF;
        if ( v52 > v36 )
          v52 = (unsigned int)v36;
        v37 = (char *)v40 + v52;
        Buffer = v37;
        v38 = v52 + v41;
        *(_QWORD *)&v77 = v38;
        v36 -= v52;
        v69 = v36;
        v64 = v36;
        if ( !v36 )
        {
LABEL_187:
          v28 = *(_DWORD *)&v57[4];
          goto LABEL_188;
        }
        goto LABEL_149;
      }
      v59 = 0;
      v43 = *v40;
      LODWORD(v64) = *v40;
      v44 = v40[14];
      if ( (v44 & DWORD2(v77)) != 0 && (!HIDWORD(v77) || v44 < 0) && *((_WORD *)v40 + 2) == 3 )
        break;
LABEL_182:
      v41 += v43;
      *(_QWORD *)&v77 = v41;
      v40 = (unsigned int *)((char *)v40 + v43);
      Buffer = v40;
      v36 -= v43;
      v69 = v36;
      v64 = v36;
    }
    if ( WORD5(v79) >= 3u )
    {
      v50 = 76;
      v59 = 76;
      v51 = v57[1];
      if ( !v57[1] )
      {
        v50 = *((unsigned __int16 *)v40 + 36) + 76;
        v59 = v50;
      }
      v46 = (v50 + 7) & 0xFFFFFFF8;
      v59 = v46;
      if ( v46 > *(_DWORD *)&v57[4] )
      {
LABEL_170:
        v28 = 0;
        *(_DWORD *)&v57[4] = 0;
LABEL_188:
        CcUnpinData(Bcb);
        Bcb = 0;
        v30 = v77;
        goto LABEL_144;
      }
      *(_OWORD *)v29 = *(_OWORD *)v40;
      *((_OWORD *)v29 + 1) = *((_OWORD *)v40 + 1);
      *((_OWORD *)v29 + 2) = *((_OWORD *)v40 + 2);
      *((_OWORD *)v29 + 3) = *((_OWORD *)v40 + 3);
      *((_QWORD *)v29 + 8) = *((_QWORD *)v40 + 8);
      *(_DWORD *)v29 = v46;
      v29[37] = 76;
      if ( v51 )
      {
        v29[36] = 0;
        goto LABEL_181;
      }
      v29[36] = *((_WORD *)Buffer + 36);
      v49 = v29 + 38;
    }
    else
    {
      v45 = 60;
      v59 = 60;
      if ( !v57[1] )
      {
        v45 = *((unsigned __int16 *)v40 + 36) + 60;
        v59 = v45;
      }
      v46 = (v45 + 7) & 0xFFFFFFF8;
      v59 = v46;
      if ( v46 > *(_DWORD *)&v57[4] )
        goto LABEL_170;
      *(_DWORD *)v29 = v46;
      *((_DWORD *)v29 + 1) = 2;
      *((_QWORD *)v29 + 1) = RefsPackFileId((const struct _REFS_FILE_REFERENCE *)((char *)Buffer + 8));
      *((_QWORD *)v29 + 2) = RefsPackFileId((const struct _REFS_FILE_REFERENCE *)((char *)Buffer + 24));
      v47 = (char *)Buffer;
      *(_OWORD *)(v29 + 12) = *(_OWORD *)((char *)Buffer + 40);
      *(_OWORD *)(v29 + 20) = *(_OWORD *)(v47 + 56);
      v29[29] = 60;
      if ( v48 )
      {
        v29[28] = 0;
LABEL_181:
        v29 = (_WORD *)((char *)v29 + v46);
        v74 = v29;
        *(_DWORD *)&v57[4] -= v46;
        v63 += v46;
        v40 = (unsigned int *)Buffer;
        v41 = v77;
        v42 = v70;
        v36 = v69;
        goto LABEL_182;
      }
      v29[28] = *((_WORD *)Buffer + 36);
      v49 = v29 + 30;
    }
    memmove(v49, (char *)Buffer + 76, *((unsigned __int16 *)Buffer + 36));
    v43 = v64;
    goto LABEL_181;
  }
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
    || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
  {
    v10 = -1073741592;
  }
  else
  {
    v10 = -1073741592;
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_2b67ce2bc1f03db543291d529fa9643f_Traceguids, 3221225704LL);
  }
  if ( !(_BYTE)RefsStatusDebugEnabled )
    goto LABEL_214;
  v24 = 1256;
LABEL_213:
  RefsStatusDebug(v10, 0, "UsnSup.c", v24);
LABEL_214:
  v39 = v55;
LABEL_225:
  if ( Bcb )
    CcUnpinData(Bcb);
  if ( v39 )
  {
    v53 = *((_DWORD *)v7 + 1);
    if ( (v53 & 0x2000) != 0 )
    {
      *((_DWORD *)v7 + 1) = v53 & 0xFFFFCFFF;
      ExReleaseFastResource((char *)v20 + 1208, v76);
    }
  }
  if ( v56 )
    RefsReleaseVcb(v7, v20);
  *((_QWORD *)v7 + 1) &= ~v73;
  v54 = 0;
  if ( v10 != 259 )
    v54 = v6;
  if ( v6 != *((PIRP *)v7 + 9) )
    v7 = 0;
  RefsCompleteRequest((PSECURITY_SUBJECT_CONTEXT *)v7, v54, v10);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1402e3ff0  mov     r11, rsp
0x1402e3ff3  push    rbx
0x1402e3ff4  push    rsi
0x1402e3ff5  push    rdi
0x1402e3ff6  push    r12
0x1402e3ff8  push    r13
0x1402e3ffa  push    r14
0x1402e3ffc  push    r15
0x1402e3ffe  sub     rsp, 170h
0x1402e4005  mov     rax, cs:__security_cookie
0x1402e400c  xor     rax, rsp
0x1402e400f  mov     [rsp+1A8h+var_48], rax
0x1402e4017  mov     bl, r9b
0x1402e401a  mov     [rsp+1A8h+var_158+1], bl
0x1402e401e  mov     r15b, r8b
0x1402e4021  mov     [rsp+1A8h+var_150], r8b
0x1402e4026  mov     r13, rdx
0x1402e4029  mov     [rsp+1A8h+Irp], rdx
0x1402e402e  mov     rsi, rcx
0x1402e4031  mov     [rsp+1A8h+var_F0], rcx
0x1402e4039  xor     r12d, r12d
0x1402e403c  mov     [rsp+1A8h+var_148], r12
0x1402e4041  mov     [r11-120h], r12
0x1402e4048  xorps   xmm0, xmm0
0x1402e404b  movups  xmmword ptr [r11-78h], xmm0
0x1402e4050  movups  xmmword ptr [r11-68h], xmm0
0x1402e4055  movups  xmmword ptr [r11-58h], xmm0
0x1402e405a  mov     [r11-118h], r12
0x1402e4061  mov     [r11-0F8h], r12
0x1402e4068  mov     [r11-110h], r12
0x1402e406f  xor     edx, edx; Val
0x1402e4071  lea     r8d, [r12+48h]; Size
0x1402e4076  lea     rcx, [r11-0C8h]; void *
0x1402e407d  call    memset
0x1402e4082  lea     rcx, [rsp+1A8h+var_C8]
0x1402e408a  call    cs:__imp_ExInitializeFastOwnerEntry
0x1402e4091  nop     dword ptr [rax+rax+00h]
0x1402e4096  mov     r14, [r13+0B8h]
0x1402e409d  mov     byte ptr [rsp+1A8h+var_178], 1
0x1402e40a2  lea     rax, [rsp+1A8h+var_110]
0x1402e40aa  mov     [rsp+1A8h+Buffer], rax
0x1402e40af  lea     rax, [rsp+1A8h+FileOffset]
0x1402e40b7  mov     [rsp+1A8h+Bcb], rax
0x1402e40bc  lea     r9, [rsp+1A8h+var_E8]
0x1402e40c4  lea     r8, [rsp+1A8h+var_118]
0x1402e40cc  mov     rdx, [r14+30h]
0x1402e40d0  mov     rcx, rsi
0x1402e40d3  call    ?RefsDecodeFileObject@@YA?AW4_TYPE_OF_OPEN@@PEAU_IRP_CONTEXT@@PEAU_FILE_OBJECT@@PEAPEAU_VCB@@PEAPEAU_FCB@@PEAPEAU_SCB@@PEAPEAU_CCB@@E@Z; RefsDecodeFileObject(_IRP_CONTEXT *,_FILE_OBJECT *,_VCB * *,_FCB * *,_SCB * *,_CCB * *,uchar)
0x1402e40d8  test    bl, bl
0x1402e40da  jnz     loc_1402E418D
0x1402e40e0  mov     rax, [rsp+1A8h+var_110]
0x1402e40e8  test    rax, rax
0x1402e40eb  jz      short loc_1402E4113
0x1402e40ed  movzx   eax, word ptr [rax+58h]
0x1402e40f1  bt      ax, 9
0x1402e40f6  jb      loc_1402E418D
0x1402e40fc  cmp     [r13+40h], r12b
0x1402e4100  jnz     short loc_1402E4113
0x1402e4102  lea     edi, [r12+4]
0x1402e4107  cmp     [r14+1], dil
0x1402e410b  jz      loc_1402E4192
0x1402e4111  jmp     short loc_1402E4118
0x1402e4113  mov     edi, 4
0x1402e4118  mov     ebx, 0C0000022h
0x1402e411d  mov     r8d, ebx; Status
0x1402e4120  mov     rdx, r13; Irp
0x1402e4123  mov     rcx, rsi; struct _IRP_CONTEXT *
0x1402e4126  call    ?RefsCompleteRequest@@YAXPEAU_IRP_CONTEXT@@PEAU_IRP@@J@Z; RefsCompleteRequest(_IRP_CONTEXT *,_IRP *,long)
0x1402e412b  lea     rax, WPP_GLOBAL_Control
0x1402e4132  mov     rcx, cs:WPP_GLOBAL_Control
0x1402e4139  cmp     rcx, rax
0x1402e413c  jz      short loc_1402E4165
0x1402e413e  test    dword ptr [rcx+2Ch], 100h
0x1402e4145  jz      short loc_1402E4165
0x1402e4147  cmp     [rcx+29h], dil
0x1402e414b  jb      short loc_1402E4165
0x1402e414d  mov     edx, 11h
0x1402e4152  mov     r9d, ebx
0x1402e4155  lea     r8, WPP_2b67ce2bc1f03db543291d529fa9643f_Traceguids
0x1402e415c  mov     rcx, [rcx+18h]
0x1402e4160  call    WPP_SF_d
0x1402e4165  mov     cl, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402e416b  test    cl, cl
0x1402e416d  jz      short loc_1402E4185
0x1402e416f  mov     r9d, 47Ch; unsigned int
0x1402e4175  lea     r8, aUsnsupC; "UsnSup.c"
0x1402e417c  xor     edx, edx; struct _IRP_CONTEXT *
0x1402e417e  mov     ecx, ebx; Status
0x1402e4180  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x1402e4185  mov     eax, ebx
0x1402e4187  jmp     loc_1402E5239
0x1402e418d  mov     edi, 4
0x1402e4192  mov     al, r12b
0x1402e4195  mov     [rsp+1A8h+var_164], eax
0x1402e4199  mov     [rsp+1A8h+var_160], al
0x1402e419d  mov     [rsp+1A8h+var_168], r12b
0x1402e41a2  mov     [rsp+1A8h+var_15F], r12b
0x1402e41a7  mov     dl, 1
0x1402e41a9  mov     [rsp+1A8h+var_138], edx
0x1402e41ad  test    r15b, r15b
0x1402e41b0  jz      short loc_1402E41C3
0x1402e41b2  mov     al, [rsi+8]
0x1402e41b5  and     al, dl
0x1402e41b7  neg     al
0x1402e41b9  sbb     al, al
0x1402e41bb  and     al, dl
0x1402e41bd  mov     dl, al
0x1402e41bf  mov     [rsp+1A8h+var_138], edx
0x1402e41c3  mov     rax, [rsi+8]
0x1402e41c7  mov     rcx, rax
0x1402e41ca  not     rcx
0x1402e41cd  and     ecx, 1
0x1402e41d0  mov     [rsp+1A8h+var_E8], rcx
0x1402e41d8  mov     [rsp+1A8h+var_D8], rcx
0x1402e41e0  or      rax, 1
0x1402e41e4  mov     [rsi+8], rax
0x1402e41e8  mov     rdx, r14; struct _IO_STACK_LOCATION *
0x1402e41eb  mov     rcx, r13; struct _IRP *
0x1402e41ee  call    ?RefsEffectiveMode@@YADPEAU_IRP@@PEAU_IO_STACK_LOCATION@@@Z; RefsEffectiveMode(_IRP *,_IO_STACK_LOCATION *)
0x1402e41f3  mov     r12b, al
0x1402e41f6  mov     [rsp+1A8h+var_168], 1
0x1402e41fb  mov     r9d, [r14+8]; unsigned int
0x1402e41ff  mov     r8d, 1; enum _LOCK_OPERATION
0x1402e4205  mov     rdx, r13; struct _IRP *
0x1402e4208  call    ?RefsLockUserBuffer@@YAJPEAU_IRP_CONTEXT@@PEAU_IRP@@W4_LOCK_OPERATION@@K@Z; RefsLockUserBuffer(_IRP_CONTEXT *,_IRP *,_LOCK_OPERATION,ulong)
0x1402e420d  mov     ebx, eax
0x1402e420f  mov     [rsp+1A8h+var_15C], eax
0x1402e4213  test    eax, eax
0x1402e4215  jns     short loc_1402E427C
0x1402e4217  lea     rax, WPP_GLOBAL_Control
0x1402e421e  mov     rcx, cs:WPP_GLOBAL_Control
0x1402e4225  cmp     rcx, rax
0x1402e4228  jz      short loc_1402E4251
0x1402e422a  test    dword ptr [rcx+2Ch], 100h
0x1402e4231  jz      short loc_1402E4251
0x1402e4233  cmp     [rcx+29h], dil
0x1402e4237  jb      short loc_1402E4251
0x1402e4239  mov     edx, 12h
0x1402e423e  mov     r9d, ebx
0x1402e4241  lea     r8, WPP_2b67ce2bc1f03db543291d529fa9643f_Traceguids
0x1402e4248  mov     rcx, [rcx+18h]
0x1402e424c  call    WPP_SF_d
0x1402e4251  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402e4257  test    al, al
0x1402e4259  jz      short loc_1402E4272
0x1402e425b  mov     r9d, 4A3h; unsigned int
0x1402e4261  lea     r8, aUsnsupC; "UsnSup.c"
0x1402e4268  mov     rdx, rsi; struct _IRP_CONTEXT *
0x1402e426b  mov     ecx, ebx; Status
0x1402e426d  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x1402e4272  mov     edx, ebx; int
0x1402e4274  mov     rcx, rsi; struct _IRP_CONTEXT *
0x1402e4277  call    ?RefsRaiseStatusInternal@@YAXPEAU_IRP_CONTEXT@@JK@Z; RefsRaiseStatusInternal(_IRP_CONTEXT *,long,ulong)
0x1402e427c  mov     rcx, r13; struct _IRP *
0x1402e427f  call    ?RefsMapUserBuffer@@YAPEAXPEAU_IRP@@K@Z; RefsMapUserBuffer(_IRP *,ulong)
0x1402e4284  mov     r9, rax
0x1402e4287  mov     [rsp+1A8h+var_110], rax
0x1402e428f  cmp     byte ptr [r13+40h], 0
0x1402e4294  jz      short loc_1402E42D9
0x1402e4296  test    r15b, r15b
0x1402e4299  jz      short loc_1402E42BA
0x1402e429b  mov     edx, [r14+10h]; Length
0x1402e429f  mov     r8d, edi; Alignment
0x1402e42a2  mov     rcx, [r14+20h]; Address
0x1402e42a6  call    cs:__imp_ProbeForRead
0x1402e42ad  nop     dword ptr [rax+rax+00h]
0x1402e42b2  mov     r9, [rsp+1A8h+var_110]
0x1402e42ba  cmp     qword ptr [r13+8], 0
0x1402e42bf  jnz     short loc_1402E4306
0x1402e42c1  mov     edx, [r14+8]; Length
0x1402e42c5  mov     r8d, edi; Alignment
0x1402e42c8  mov     rcx, r9; Address
0x1402e42cb  call    cs:__imp_ProbeForWrite
0x1402e42d2  nop     dword ptr [rax+rax+00h]
0x1402e42d7  jmp     short loc_1402E4306
0x1402e42d9  mov     rcx, [r14+20h]
0x1402e42dd  lea     rax, [rcx+3]
0x1402e42e1  and     rax, 0FFFFFFFFFFFFFFFCh
0x1402e42e5  cmp     rcx, rax
0x1402e42e8  jnz     loc_1402E5005
0x1402e42ee  cmp     qword ptr [r13+8], 0
0x1402e42f3  jnz     short loc_1402E4306
0x1402e42f5  lea     rax, [r9+3]
0x1402e42f9  and     rax, 0FFFFFFFFFFFFFFFCh
0x1402e42fd  cmp     r9, rax
0x1402e4300  jnz     loc_1402E5005
0x1402e4306  mov     [rsp+1A8h+var_168], 0
0x1402e430b  test    r15b, r15b
0x1402e430e  mov     r15, [rsp+1A8h+var_118]
0x1402e4316  jz      short loc_1402E432A
0x1402e4318  mov     r8b, 1; unsigned __int8
0x1402e431b  mov     rdx, r15; struct _VCB *
0x1402e431e  mov     rcx, rsi; struct _IRP_CONTEXT *
0x1402e4321  call    ?RefsAcquireSharedVcb@@YAEPEAU_IRP_CONTEXT@@PEAU_VCB@@E@Z; RefsAcquireSharedVcb(_IRP_CONTEXT *,_VCB *,uchar)
0x1402e4326  mov     [rsp+1A8h+var_15F], al
0x1402e432a  lea     rcx, [r15+4B8h]
0x1402e4331  mov     r8b, 1
0x1402e4334  lea     rdx, [rsp+1A8h+var_C8]
0x1402e433c  call    cs:__imp_ExAcquireFastResourceShared
0x1402e4343  nop     dword ptr [rax+rax+00h]
0x1402e4348  bts     dword ptr [rsi+4], 0Dh
0x1402e434d  mov     al, 1
0x1402e434f  mov     [rsp+1A8h+var_164], eax
0x1402e4353  mov     [rsp+1A8h+var_160], al
0x1402e4357  mov     ecx, [r15+18h]
0x1402e435b  mov     eax, ecx
0x1402e435d  and     eax, 100000h
0x1402e4362  jz      short loc_1402E43D9
0x1402e4364  lea     rax, WPP_GLOBAL_Control
0x1402e436b  mov     rcx, cs:WPP_GLOBAL_Control
0x1402e4372  cmp     rcx, rax
0x1402e4375  jz      short loc_1402E43A6
0x1402e4377  mov     eax, [rcx+2Ch]
0x1402e437a  bt      eax, 8
0x1402e437e  jnb     short loc_1402E43A6
0x1402e4380  cmp     [rcx+29h], dil
0x1402e4384  jb      short loc_1402E43A6
0x1402e4386  mov     edx, 14h
0x1402e438b  mov     r13d, 0C00002B7h
0x1402e4391  mov     r9d, r13d
0x1402e4394  lea     r8, WPP_2b67ce2bc1f03db543291d529fa9643f_Traceguids
0x1402e439b  mov     rcx, [rcx+18h]
0x1402e439f  call    WPP_SF_d
0x1402e43a4  jmp     short loc_1402E43AC
0x1402e43a6  mov     r13d, 0C00002B7h
0x1402e43ac  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402e43b2  test    al, al
0x1402e43b4  jz      short loc_1402E43CD
0x1402e43b6  mov     r9d, 4D6h; unsigned int
0x1402e43bc  lea     r8, aUsnsupC; "UsnSup.c"
0x1402e43c3  xor     edx, edx; struct _IRP_CONTEXT *
0x1402e43c5  mov     ecx, r13d; Status
0x1402e43c8  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x1402e43cd  mov     ebx, r13d
0x1402e43d0  mov     [rsp+1A8h+var_15C], ebx
0x1402e43d4  jmp     loc_1402E5079
0x1402e43d9  cmp     qword ptr [r15+28h], 0
0x1402e43de  jz      loc_1402E4F94
0x1402e43e4  and     ecx, 80000h
0x1402e43ea  jz      loc_1402E4F94
0x1402e43f0  mov     eax, [r14+10h]
0x1402e43f4  cmp     eax, 28h ; '('
0x1402e43f7  jnb     short loc_1402E4458
0x1402e43f9  lea     rax, WPP_GLOBAL_Control
0x1402e4400  mov     rcx, cs:WPP_GLOBAL_Control
0x1402e4407  cmp     rcx, rax
0x1402e440a  jz      short loc_1402E443A
0x1402e440c  mov     eax, [rcx+2Ch]
0x1402e440f  bt      eax, 8
0x1402e4413  jnb     short loc_1402E443A
0x1402e4415  cmp     [rcx+29h], dil
0x1402e4419  jb      short loc_1402E443A
0x1402e441b  mov     edx, 16h
0x1402e4420  mov     ebx, 0C00000E8h
0x1402e4425  mov     r9d, ebx
0x1402e4428  lea     r8, WPP_2b67ce2bc1f03db543291d529fa9643f_Traceguids
0x1402e442f  mov     rcx, [rcx+18h]
0x1402e4433  call    WPP_SF_d
0x1402e4438  jmp     short loc_1402E443F
0x1402e443a  mov     ebx, 0C00000E8h
0x1402e443f  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402e4445  test    al, al
0x1402e4447  jz      loc_1402E4FFA
0x1402e444d  mov     r9d, 4E8h
0x1402e4453  jmp     loc_1402E4FEA
0x1402e4458  mov     r8d, 30h ; '0'
0x1402e445e  cmp     eax, r8d
0x1402e4461  jz      short loc_1402E4474
0x1402e4463  mov     [rsp+1A8h+var_50], 20002h
0x1402e446e  mov     r8d, 28h ; '('; Size
0x1402e4474  mov     [rsp+1A8h+var_168], 1
0x1402e4479  mov     rdx, [r14+20h]; Src
0x1402e447d  lea     rcx, [rsp+1A8h+var_78]; void *
0x1402e4485  test    r12b, r12b
0x1402e4488  jz      short loc_1402E4491
0x1402e448a  call    RtlCopyFromUser
0x1402e448f  jmp     short loc_1402E4496
0x1402e4491  call    RtlCopyVolatileMemory
0x1402e4496  nop
0x1402e4497  mov     [rsp+1A8h+var_168], 0
0x1402e449c  mov     rax, [rsp+1A8h+var_58]
0x1402e44a4  cmp     rax, [r15+388h]
0x1402e44ab  jz      short loc_1402E450C
0x1402e44ad  lea     rax, WPP_GLOBAL_Control
0x1402e44b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1402e44bb  cmp     rcx, rax
0x1402e44be  jz      short loc_1402E44EE
0x1402e44c0  mov     eax, [rcx+2Ch]
0x1402e44c3  bt      eax, 8
0x1402e44c7  jnb     short loc_1402E44EE
0x1402e44c9  cmp     [rcx+29h], dil
0x1402e44cd  jb      short loc_1402E44EE
0x1402e44cf  mov     edx, 17h
0x1402e44d4  mov     ebx, 0C000000Dh
0x1402e44d9  mov     r9d, ebx
0x1402e44dc  lea     r8, WPP_2b67ce2bc1f03db543291d529fa9643f_Traceguids
0x1402e44e3  mov     rcx, [rcx+18h]
0x1402e44e7  call    WPP_SF_d
0x1402e44ec  jmp     short loc_1402E44F3
0x1402e44ee  mov     ebx, 0C000000Dh
  ... truncated ...
```
