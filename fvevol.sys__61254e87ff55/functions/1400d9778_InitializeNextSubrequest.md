# InitializeNextSubrequest

- ea: `0x1400d9778`
- end: `0x1400da174`
- name: `InitializeNextSubrequest`
- size: `2556`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400d94a0`
- `0x1400d95c0`

## callees

- `0x140001b20`
- `0x140001f0c`
- `0x140006730`
- `0x140006760`
- `0x1400067e0`
- `0x1400070ac`
- `0x140008348`
- `0x140008d68`
- `0x140009cb4`
- `0x14000b998`
- `0x14000c224`
- `0x140022bf0`
- `0x1400d9778`
- `0x1400dba60`
- `0x1400dbc70`
- `0x1400e07fc`

## import_xrefs

- `ntoskrnl!IoReuseIrp` at `0x1400d98dc`
- `ntoskrnl!IoReuseIrp` at `0x1400d98dc`
- `ntoskrnl!IoSetIoPriorityHint` at `0x1400d9eff`
- `ntoskrnl!IoSetIoPriorityHint` at `0x1400d9eff`
- `ntoskrnl!IoBuildPartialMdl` at `0x1400d9d66`
- `ntoskrnl!IoBuildPartialMdl` at `0x1400d9d66`
- `ntoskrnl!IoGetIoPriorityHint` at `0x1400d9eee`
- `ntoskrnl!IoGetIoPriorityHint` at `0x1400d9eee`
- `ntoskrnl!IoPropagateIrpExtensionEx` at `0x1400d9daf`
- `ntoskrnl!IoPropagateIrpExtensionEx` at `0x1400d9de5`
- `ntoskrnl!IoPropagateIrpExtensionEx` at `0x1400d9daf`
- `ntoskrnl!IoPropagateIrpExtensionEx` at `0x1400d9de5`
- `ntoskrnl!KeBugCheckEx` at `0x1400d99e2`
- `ntoskrnl!KeBugCheckEx` at `0x1400d9d03`
- `ntoskrnl!KeBugCheckEx` at `0x1400d9e0b`
- `ntoskrnl!KeBugCheckEx` at `0x1400da121`
- `ntoskrnl!KeBugCheckEx` at `0x1400da144`
- `ntoskrnl!KeBugCheckEx` at `0x1400da167`
- `ntoskrnl!KeBugCheckEx` at `0x1400d99e2`
- `ntoskrnl!KeBugCheckEx` at `0x1400d9d03`
- `ntoskrnl!KeBugCheckEx` at `0x1400d9e0b`
- `ntoskrnl!KeBugCheckEx` at `0x1400da121`
- `ntoskrnl!KeBugCheckEx` at `0x1400da144`
- `ntoskrnl!KeBugCheckEx` at `0x1400da167`

## pseudocode

```c
__int64 __fastcall InitializeNextSubrequest(__int64 a1, __int64 a2, char a3)
{
  ULONG v3; // r15d
  __int64 v4; // rdi
  __int64 v6; // rcx
  ULONGLONG v7; // r9
  ULONGLONG v8; // rsi
  ULONGLONG v9; // r14
  ULONG v10; // r12d
  struct _MDL *MdlAddress; // rdx
  __int64 v12; // rax
  int v13; // ecx
  char v14; // r15
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // rax
  unsigned __int64 v18; // r8
  __int64 v19; // rdx
  unsigned int v20; // eax
  __int64 v21; // rdx
  __int64 v22; // rax
  unsigned int v23; // eax
  IRP *v24; // r13
  __int64 v25; // rdx
  __int64 v26; // rcx
  int IsEnabledDeviceUsageNoInline; // eax
  __int64 v28; // rdx
  __int64 v29; // rcx
  __int64 v30; // rax
  NTSTATUS v31; // eax
  int RedirectedBlockSize; // eax
  __int64 v33; // rcx
  __int64 v34; // rdx
  ULONGLONG v35; // rcx
  ULONG v36; // r12d
  ULONGLONG v37; // r8
  int RedirectedBlockOffset; // eax
  __int64 v39; // rcx
  ULONG v40; // eax
  int v41; // r15d
  bool v42; // r14
  __int64 v43; // rcx
  __int64 Bitmap; // rax
  char v45; // r11
  bool v46; // zf
  __int64 v47; // r10
  unsigned int v48; // r8d
  __int64 v49; // r9
  __int64 v50; // rcx
  __int64 v51; // rdx
  __int64 v52; // rax
  __int64 v53; // rax
  __int64 v54; // rax
  __int64 v55; // rdx
  __int64 v56; // rcx
  __int64 v57; // r9
  int v58; // edx
  ULONGLONG v59; // rsi
  __int64 v60; // rdx
  unsigned __int64 v61; // rcx
  __int64 v62; // rdx
  __int64 v63; // rcx
  __int64 v64; // r8
  __int64 v65; // rax
  char v66; // si
  __int64 v67; // rax
  unsigned __int64 v68; // rax
  unsigned __int64 v69; // rcx
  PMDL v70; // rsi
  unsigned __int64 v71; // r8
  PIRP v72; // rsi
  __int64 v73; // rdx
  __int64 v74; // rcx
  int v75; // eax
  char v76; // si
  int v77; // eax
  __int64 v78; // rcx
  __int64 *v79; // rdx
  __int64 v80; // rcx
  __int64 v81; // r8
  __int64 v82; // rdx
  int v83; // eax
  __int64 v84; // r8
  unsigned __int64 v85; // rax
  __int64 v86; // rdx
  __int64 v87; // rcx
  PIRP v88; // r15
  IRP *v89; // rcx
  IO_PRIORITY_HINT IoPriorityHint; // eax
  __int64 CurrentLocation; // rdx
  __int64 StackCount; // r8
  struct _IRP *MasterIrp; // rax
  struct _IO_STACK_LOCATION *v94; // rcx
  struct _IO_STACK_LOCATION *v95; // r9
  struct _FILE_OBJECT *FileObject; // rax
  char v97; // r14
  char v98; // cl
  char v99; // al
  unsigned int v100; // r8d
  unsigned __int8 v101; // dl
  unsigned __int8 v102; // al
  unsigned int v103; // edx
  __int64 *v104; // rdx
  char v106; // [rsp+70h] [rbp-90h]
  char v107; // [rsp+71h] [rbp-8Fh]
  ULONG v109; // [rsp+74h] [rbp-8Ch] BYREF
  ULONG pulResult; // [rsp+78h] [rbp-88h] BYREF
  ULONGLONG v111; // [rsp+80h] [rbp-80h] BYREF
  PMDL SourceMdl; // [rsp+88h] [rbp-78h]
  PMDL TargetMdl; // [rsp+90h] [rbp-70h]
  ULONGLONG v114; // [rsp+98h] [rbp-68h]
  unsigned __int64 v115; // [rsp+A0h] [rbp-60h] BYREF
  PIRP Irp; // [rsp+A8h] [rbp-58h]
  ULONGLONG v117; // [rsp+B0h] [rbp-50h] BYREF
  struct _IO_STACK_LOCATION *CurrentStackLocation; // [rsp+B8h] [rbp-48h]
  _QWORD v119[10]; // [rsp+C0h] [rbp-40h] BYREF

  v4 = a2;
  v6 = *(_QWORD *)(a1 + 48);
  LOBYTE(a2) = a3;
  v115 = 0;
  FvePerfReportSubRequest(v6, a2);
  v8 = (unsigned int)v7;
  Irp = *(PIRP *)a1;
  v9 = (unsigned int)v7;
  v109 = v7;
  v10 = v7;
  v111 = v7;
  MdlAddress = Irp->MdlAddress;
  v12 = *(_QWORD *)(a1 + 48);
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  v114 = v7;
  pulResult = v7;
  v13 = *(_DWORD *)(v12 + 808);
  SourceMdl = MdlAddress;
  if ( (v13 & 0x17F) == 0 || (v13 & 0x40) != 0 )
  {
    v14 = v7;
    v107 = v7;
  }
  else
  {
    v14 = 1;
    v107 = 1;
  }
  v15 = *(_QWORD *)(v4 + 48);
  v117 = v7;
  if ( v15 )
  {
    v16 = *(_QWORD *)(v4 + 16);
    v17 = *(_QWORD *)(v4 + 56);
    v18 = MEMORY[0xFFFFF78000000008] - v15;
    if ( v17 )
    {
      v19 = *(_QWORD *)(v4 + 64);
      if ( v19 )
      {
        _InterlockedAdd64((volatile signed __int64 *)(v16 + 32), v19 - v17);
        v20 = *(_DWORD *)(v4 + 88);
        if ( v20 )
          _InterlockedAdd((volatile signed __int32 *)(v16 + 40), v20);
      }
    }
    v21 = *(_QWORD *)(v4 + 72);
    if ( v21 )
    {
      v22 = *(_QWORD *)(v4 + 80);
      if ( v22 )
      {
        _InterlockedAdd64((volatile signed __int64 *)(v16 + 24), v22 - v21);
        v23 = *(_DWORD *)(v4 + 92);
        if ( v23 )
          _InterlockedAdd((volatile signed __int32 *)(v16 + 44), v23);
      }
    }
    _InterlockedAdd64((volatile signed __int64 *)(v16 + 16), v18);
    *(_QWORD *)(v4 + 48) = v7;
    *(_QWORD *)(v4 + 56) = v7;
    *(_QWORD *)(v4 + 64) = v7;
    *(_QWORD *)(v4 + 72) = v7;
    *(_QWORD *)(v4 + 80) = v7;
    *(_QWORD *)(v4 + 88) = v7;
  }
  v24 = *(IRP **)(v4 + 40);
  *(_QWORD *)(v4 + 48) = MEMORY[0xFFFFF78000000008];
  *(_QWORD *)(v4 + 56) = v7;
  *(_QWORD *)(v4 + 64) = v7;
  *(_QWORD *)(v4 + 72) = v7;
  *(_QWORD *)(v4 + 80) = v7;
  *(_QWORD *)(v4 + 88) = v7;
  TargetMdl = v24->MdlAddress;
  IoReuseIrp(v24, -1073741637);
  v24->MdlAddress = TargetMdl;
  if ( v14 )
  {
    v3 = 1;
    v26 = *(_QWORD *)(*(_QWORD *)(a1 + 48) + 976LL);
    if ( *(_WORD *)(v26 + 10) > 1u )
    {
      IsEnabledDeviceUsageNoInline = Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline(
                                       v26,
                                       v25);
      v28 = *(_QWORD *)(a1 + 48);
      v29 = *(_QWORD *)(v28 + 976);
      if ( IsEnabledDeviceUsageNoInline && (*(_BYTE *)(v28 + 4419) & 8) != 0 || *(_WORD *)(v29 + 10) == 1 )
      {
        v30 = 0;
      }
      else
      {
        v30 = *(unsigned int *)(v29 + 28);
        if ( !(_DWORD)v30 )
          v30 = 1;
      }
      v9 = *(_QWORD *)(v29 + 56);
      v8 = v30 * *(unsigned int *)(v28 + 1308);
      v114 = v9;
    }
    v31 = RtlULongLongToULong(v8, &pulResult);
    if ( v31 < 0 )
      KeBugCheckEx(0x120u, 0xCu, 0, 0, v31);
    if ( v9 < v8 )
      goto LABEL_84;
    v10 = pulResult;
  }
  RedirectedBlockSize = FveGetRedirectedBlockSize(*(_QWORD *)(a1 + 112));
  if ( RedirectedBlockSize < 0 )
    KeBugCheckEx(0x120u, 0xCu, 0, 0, RedirectedBlockSize);
  v33 = *(_QWORD *)(a1 + 112);
  LOBYTE(v3) = 0;
  pulResult = v3;
  IntersectRegion(v33, &v109, v9, v10);
  v35 = *(_QWORD *)(a1 + 112);
  v36 = v109;
  if ( v35 >= v9 + v8 || v35 + v109 <= v9 )
  {
    RedirectedBlockOffset = FveGetRedirectedBlockOffset(v35, v8, v9, &v111);
    if ( RedirectedBlockOffset < 0 )
      KeBugCheckEx(0x120u, 0xCu, 0, 0, RedirectedBlockOffset);
    v37 = v111;
    pulResult = v39 != v111;
  }
  else
  {
    v37 = *(_QWORD *)(a1 + 112);
    v111 = v37;
  }
  if ( !v36 )
    goto LABEL_84;
  v40 = *(_DWORD *)(v4 + 120);
  v41 = 0;
  *(_QWORD *)(v4 + 24) = 0;
  v42 = 0;
  v43 = *(_QWORD *)(a1 + 48);
  v106 = 0;
  if ( v36 > v40 )
    v36 = v40;
  v109 = v36;
  if ( (*(_DWORD *)(v43 + 808) & 0x100) != 0 )
  {
    v43 = *(_QWORD *)(v43 + 736);
    if ( v43 )
    {
      if ( *(_QWORD *)v43 )
      {
        v34 = *(_QWORD *)(a1 + 56);
        if ( v34 )
        {
          Bitmap = FveEowFindBitmap(v43, *(_DWORD *)(v34 + 80), v37, v36, (__int64)&v109);
          v36 = v109;
          *(_QWORD *)(v4 + 24) = Bitmap;
        }
      }
    }
  }
  if ( (unsigned int)Feature_BitLockerHwAccelCryptoSupport__private_IsEnabledDeviceUsageNoInline(v43, v34, v37) )
  {
    if ( !v107 )
      goto LABEL_90;
    v45 = a3;
    if ( a3 || *(_QWORD *)(*(_QWORD *)(a1 + 48) + 4752LL) )
      goto LABEL_51;
    v46 = *(_BYTE *)(a1 + 277) == 0;
  }
  else
  {
    if ( !v107 )
      goto LABEL_90;
    v45 = a3;
    if ( a3 )
      goto LABEL_51;
    v46 = *(_QWORD *)(*(_QWORD *)(a1 + 48) + 4752LL) == 0;
  }
  if ( v46 )
    goto LABEL_90;
LABEL_51:
  v47 = *(_QWORD *)(a1 + 48);
  v48 = 0;
  v49 = 0;
  do
  {
    v50 = *(_QWORD *)(v47 + 24 * v49 + 1056);
    v51 = 2 * v49;
    v52 = 3 * v49;
    ++v48;
    ++v49;
    v119[v51] = v50;
    v119[v51 + 1] = *(unsigned int *)(v47 + 8 * v52 + 1064);
  }
  while ( v48 < 3 );
  if ( !(_BYTE)pulResult && v8 && v48 < 5 )
  {
    v53 = 2LL * v48++;
    v119[v53] = v114;
    v119[v53 + 1] = v8;
  }
  v54 = *(_QWORD *)(v47 + 976);
  if ( *(_WORD *)(v54 + 12) == 2 )
  {
    v55 = *(unsigned int *)(v54 + 24);
    if ( (_DWORD)v55 )
    {
      if ( v48 < 5 )
      {
        v56 = 2LL * v48++;
        v119[v56] = *(_QWORD *)(v54 + 16);
        v119[v56 + 1] = v55;
      }
    }
  }
  v57 = *(_QWORD *)(v47 + 736);
  v58 = v45 != 0 ? 3 : 5;
  if ( v57 )
  {
    v58 |= 8u;
    if ( (*(_BYTE *)(*(_QWORD *)v57 + 48LL) & 1) != 0 )
      v58 |= 0x10u;
  }
  v59 = v111;
  v41 = FveLibIdentifyCurrentRegionTypeAndEnd(
          v111,
          v36,
          *(_QWORD *)(v47 + 1048),
          *(_DWORD *)(v47 + 1308),
          v48,
          (__int64)v119,
          *(_QWORD *)(v47 + 1040),
          1,
          *(_QWORD *)(v47 + 1008),
          v57,
          *(_QWORD *)(a1 + 56),
          (__int64)&v117,
          v58,
          (__int64)&v115);
  v61 = v59 + v36;
  if ( v61 > v115 )
  {
    v60 = 0xFFFFFFFFLL;
    v61 = v115 - v59;
    if ( v115 - v59 >= 0xFFFFFFFF )
      goto LABEL_84;
    v36 = v115 - v59;
  }
  if ( (unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v61, v60) )
  {
    if ( !v41 || v41 == 3 )
    {
      v67 = *(_QWORD *)(a1 + 48);
      v62 = *(_QWORD *)(v67 + 4752);
      if ( v62 && ((v63 = *(unsigned int *)(*(_QWORD *)(v67 + 8) + 9928LL), (v63 & 0x10) == 0) || *(_DWORD *)(v62 + 88)) )
      {
        v66 = 1;
        v106 = 1;
      }
      else
      {
        v66 = 0;
      }
      if ( v41 == 3 && v62 && *(_DWORD *)(v62 + 88) && !v66 )
        goto LABEL_84;
      goto LABEL_86;
    }
    goto LABEL_85;
  }
  if ( v41 && v41 != 3
    || (v65 = *(_QWORD *)(a1 + 48), !*(_QWORD *)(v65 + 4752))
    || (v63 = *(unsigned int *)(*(_QWORD *)(v65 + 8) + 9928LL), (v63 & 0x10) != 0) )
  {
LABEL_85:
    v66 = 0;
    goto LABEL_86;
  }
  v66 = 1;
  v106 = 1;
LABEL_86:
  if ( (unsigned int)Feature_BitLockerHwAccelCryptoSupport__private_IsEnabledDeviceUsageNoInline(v63, v62, v64)
    && !v66
    && v41 == 3 )
  {
    v42 = *(_BYTE *)(a1 + 277) != 0;
  }
LABEL_90:
  v68 = *(_QWORD *)(a1 + 64);
  v69 = *(_QWORD *)(a1 + 112);
  if ( v69 < v68 )
    goto LABEL_84;
  v70 = TargetMdl;
  IoBuildPartialMdl(SourceMdl, TargetMdl, (char *)SourceMdl->StartVa + SourceMdl->ByteOffset - v68 + v69, v36);
  v71 = (unsigned __int64)v70->StartVa
      + v70->ByteOffset
      - (unsigned __int64)SourceMdl->ByteOffset
      - (unsigned __int64)SourceMdl->StartVa;
  v72 = Irp;
  if ( (int)IoPropagateIrpExtensionEx(Irp, v24, v71, *(_QWORD *)(*(_QWORD *)(a1 + 48) + 4752LL) != 0 ? -5 : -1) < 0 )
  {
    v75 = IoPropagateIrpExtensionEx(
            v72,
            v24,
            (char *)TargetMdl->StartVa
          + TargetMdl->ByteOffset
          - (unsigned __int64)SourceMdl->ByteOffset
          - (unsigned __int64)SourceMdl->StartVa,
            1);
    if ( v75 < 0 )
      KeBugCheckEx(0x120u, 0xCu, 0, 0, v75);
  }
  v76 = v106;
  if ( !v106 )
    goto LABEL_114;
  v77 = Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v74, v73);
  v78 = *(_QWORD *)(*(_QWORD *)(a1 + 48) + 8LL);
  if ( v77 )
  {
    if ( !(unsigned __int8)FveSimulateResourceStress(v78) || *v79 && *(_DWORD *)(*v79 + 88) )
    {
      if ( v41 == 3 )
        v82 = *v79;
      else
        v82 = 0;
      v83 = FveIceSetIrpExtensionSteelix(v24, v82, v111, v81);
      goto LABEL_108;
    }
  }
  else if ( !(unsigned __int8)FveSimulateResourceStress(v78) )
  {
    if ( v41 == 3 )
    {
      v85 = v111 / *(unsigned int *)(v84 + 1308);
      v86 = *(_QWORD *)(v84 + 4752);
    }
    else
    {
      v85 = 0;
      v86 = 0;
    }
    v83 = FveIceSetIrpExtension(v24, v86, v85);
LABEL_108:
    if ( v83 >= 0 )
      goto LABEL_114;
  }
  if ( (unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v80, v79) )
  {
    if ( v41 == 3 )
    {
      v87 = *(_QWORD *)(*(_QWORD *)(a1 + 48) + 4752LL);
      if ( v87 )
      {
        if ( *(_DWORD *)(v87 + 88) )
          goto LABEL_84;
      }
    }
  }
  v76 = 0;
LABEL_114:
  v88 = Irp;
  v89 = Irp;
  v24->Flags = Irp->Flags & 0x343;
  IoPriorityHint = IoGetIoPriorityHint(v89);
  IoSetIoPriorityHint(v24, IoPriorityHint);
  v24->RequestorMode = v88->RequestorMode;
  v24->Tail.Overlay.Thread = v88->Tail.Overlay.Thread;
  v24->Tail.Overlay.OriginalFileObject = v88->Tail.Overlay.OriginalFileObject;
  if ( (v88->Flags & 8) != 0 )
  {
    MasterIrp = v88->AssociatedIrp.MasterIrp;
    if ( MasterIrp )
      v24->Tail.Overlay.OriginalFileObject = MasterIrp->Tail.Overlay.OriginalFileObject;
  }
  v94 = v24->Tail.Overlay.CurrentStackLocation;
  v95 = CurrentStackLocation;
  *(_OWORD *)&v94[-1].MajorFunction = *(_OWORD *)&CurrentStackLocation->MajorFunction;
  *(_OWORD *)&v94[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v95->Parameters.NotifyDirectoryEx.CompletionFilter;
  *(_OWORD *)(&v94[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v95->Parameters.SetQuota + 6);
  v94[-1].FileObject = v95->FileObject;
  v94[-1].Control = 0;
  if ( !v24->Tail.Overlay.OriginalFileObject && !v94[-1].FileObject )
  {
    CurrentLocation = (unsigned __int8)v88->CurrentLocation;
    StackCount = (unsigned int)v88->StackCount;
    if ( (int)CurrentLocation <= (int)StackCount )
    {
      while ( 1 )
      {
        FileObject = v95->FileObject;
        if ( FileObject )
          break;
        LOBYTE(CurrentLocation) = CurrentLocation + 1;
        ++v95;
        if ( (unsigned __int8)CurrentLocation > (int)StackCount )
          goto LABEL_124;
      }
      v94[-1].FileObject = FileObject;
    }
  }
LABEL_124:
  LOBYTE(v94) = *(_BYTE *)(v4 + 136);
  *(_QWORD *)v4 = *(_QWORD *)(a1 + 112);
  *(_QWORD *)(v4 + 8) = v111;
  LOBYTE(v94) = (v76 << 7) | (unsigned __int8)v94 & 0x7F;
  *(_DWORD *)(v4 + 124) = v36;
  *(_BYTE *)(v4 + 136) = (_BYTE)v94;
  *(_DWORD *)(v4 + 132) = 1;
  *(_QWORD *)(v4 + 104) = 0;
  *(_DWORD *)(v4 + 128) = 0;
  if ( (unsigned int)Feature_BitLockerHwAccelCryptoSupport__private_IsEnabledDeviceUsageNoInline(
                       v94,
                       CurrentLocation,
                       StackCount) )
    v97 = *(_BYTE *)(v4 + 144) & 0xFB | (4 * v42);
  else
    v97 = *(_BYTE *)(v4 + 144) & 0xFB;
  *(_BYTE *)(v4 + 144) = v97 & 0xF7;
  if ( !v76 || *(_BYTE *)(a1 + 276) )
    v98 = 64;
  else
    v98 = 0;
  v99 = *(_BYTE *)(v4 + 136) & 0xBF;
  *(_BYTE *)(v4 + 144) = v97 & 0xF4;
  *(_BYTE *)(v4 + 136) = v98 | v99;
  *(_DWORD *)(a1 + 120) -= v36;
  *(_QWORD *)(a1 + 112) += v36;
  if ( *(_QWORD *)(a1 + 184) )
  {
    v100 = *(unsigned __int8 *)(a1 + 92);
    v101 = *(_BYTE *)(a1 + 265);
    if ( v101 < (unsigned __int8)v100 )
    {
      v102 = *(_BYTE *)(a1 + 264);
      if ( (unsigned __int8)(v101 + v102) < v102 )
        KeBugCheckEx(0x120u, 0xCu, 0, 0, 0xFFFFFFFFC0000095uLL);
      v103 = (unsigned __int8)(v101 + v102) % v100;
      if ( *(_BYTE *)((unsigned __int8)v103 + a1 + 232) == 0xFF )
      {
        *(_BYTE *)((unsigned __int8)v103 + a1 + 232) = *(_BYTE *)(v4 + 136) & 0x3F;
        ++*(_BYTE *)(a1 + 265);
        goto LABEL_136;
      }
    }
LABEL_84:
    KeBugCheckEx(0x120u, 0xCu, 0, 0, 0);
  }
LABEL_136:
  v104 = FVE_PERF_WRITE_SUBREQUEST_INIT;
  if ( !a3 )
    v104 = FVE_PERF_READ_SUBREQUEST_INIT;
  return FvePerfTraceDevPtrPtr(*(_QWORD *)(a1 + 48), v104, v88, v24);
}

```

## disassembly

```asm
0x1400d9778  mov     [rsp-8+arg_10], rbx
0x1400d977d  push    rbp
0x1400d977e  push    rsi
0x1400d977f  push    rdi
0x1400d9780  push    r12
0x1400d9782  push    r13
0x1400d9784  push    r14
0x1400d9786  push    r15
0x1400d9788  lea     rbp, [rsp-20h]
0x1400d978d  sub     rsp, 120h
0x1400d9794  mov     rax, cs:__security_cookie
0x1400d979b  xor     rax, rsp
0x1400d979e  mov     [rbp+50h+var_40], rax
0x1400d97a2  mov     rdi, rdx
0x1400d97a5  mov     [rsp+150h+var_DE], r8b
0x1400d97aa  mov     rbx, rcx
0x1400d97ad  xor     r9d, r9d
0x1400d97b0  mov     rcx, [rcx+30h]
0x1400d97b4  mov     dl, r8b
0x1400d97b7  mov     [rbp+50h+var_B0], r9
0x1400d97bb  call    FvePerfReportSubRequest
0x1400d97c0  mov     rax, [rbx]
0x1400d97c3  mov     esi, r9d
0x1400d97c6  mov     [rbp+50h+Irp], rax
0x1400d97ca  mov     r14d, r9d
0x1400d97cd  mov     [rsp+150h+var_DC], r9d
0x1400d97d2  mov     r12d, r9d
0x1400d97d5  mov     [rbp+50h+var_D0], r9
0x1400d97d9  mov     rcx, [rax+0B8h]
0x1400d97e0  mov     rdx, [rax+8]
0x1400d97e4  mov     rax, [rbx+30h]
0x1400d97e8  mov     [rbp+50h+var_98], rcx
0x1400d97ec  mov     [rbp+50h+var_B8], r9
0x1400d97f0  mov     [rsp+150h+pulResult], r9d
0x1400d97f5  mov     ecx, [rax+328h]
0x1400d97fb  mov     [rbp+50h+SourceMdl], rdx
0x1400d97ff  test    ecx, 17Fh
0x1400d9805  jz      short loc_1400D9816
0x1400d9807  test    cl, 40h
0x1400d980a  jnz     short loc_1400D9816
0x1400d980c  mov     r15b, 1
0x1400d980f  mov     [rsp+150h+var_DF], r15b
0x1400d9814  jmp     short loc_1400D981E
0x1400d9816  mov     r15b, r9b
0x1400d9819  mov     [rsp+150h+var_DF], r9b
0x1400d981e  mov     rdx, [rdi+30h]
0x1400d9822  mov     [rbp+50h+var_A0], r9
0x1400d9826  test    rdx, rdx
0x1400d9829  jz      short loc_1400D98A6
0x1400d982b  mov     rax, ds:0FFFFF78000000008h
0x1400d9835  mov     rcx, [rdi+10h]
0x1400d9839  mov     r8, rax
0x1400d983c  mov     rax, [rdi+38h]
0x1400d9840  sub     r8, rdx
0x1400d9843  test    rax, rax
0x1400d9846  jz      short loc_1400D9864
0x1400d9848  mov     rdx, [rdi+40h]
0x1400d984c  test    rdx, rdx
0x1400d984f  jz      short loc_1400D9864
0x1400d9851  sub     rdx, rax
0x1400d9854  lock add [rcx+20h], rdx
0x1400d9859  mov     eax, [rdi+58h]
0x1400d985c  test    eax, eax
0x1400d985e  jz      short loc_1400D9864
0x1400d9860  lock add [rcx+28h], eax
0x1400d9864  mov     rdx, [rdi+48h]
0x1400d9868  test    rdx, rdx
0x1400d986b  jz      short loc_1400D9889
0x1400d986d  mov     rax, [rdi+50h]
0x1400d9871  test    rax, rax
0x1400d9874  jz      short loc_1400D9889
0x1400d9876  sub     rax, rdx
0x1400d9879  lock add [rcx+18h], rax
0x1400d987e  mov     eax, [rdi+5Ch]
0x1400d9881  test    eax, eax
0x1400d9883  jz      short loc_1400D9889
0x1400d9885  lock add [rcx+2Ch], eax
0x1400d9889  lock add [rcx+10h], r8
0x1400d988e  mov     [rdi+30h], r9
0x1400d9892  mov     [rdi+38h], r9
0x1400d9896  mov     [rdi+40h], r9
0x1400d989a  mov     [rdi+48h], r9
0x1400d989e  mov     [rdi+50h], r9
0x1400d98a2  mov     [rdi+58h], r9
0x1400d98a6  mov     rax, ds:0FFFFF78000000008h
0x1400d98b0  mov     edx, 0C00000BBh; Iostatus
0x1400d98b5  mov     r13, [rdi+28h]
0x1400d98b9  mov     [rdi+30h], rax
0x1400d98bd  mov     rcx, r13; Irp
0x1400d98c0  mov     [rdi+38h], r9
0x1400d98c4  mov     [rdi+40h], r9
0x1400d98c8  mov     [rdi+48h], r9
0x1400d98cc  mov     [rdi+50h], r9
0x1400d98d0  mov     [rdi+58h], r9
0x1400d98d4  mov     rax, [r13+8]
0x1400d98d8  mov     [rbp+50h+TargetMdl], rax
0x1400d98dc  call    cs:__imp_IoReuseIrp
0x1400d98e3  nop     dword ptr [rax+rax+00h]
0x1400d98e8  mov     rcx, [rbp+50h+TargetMdl]
0x1400d98ec  mov     [r13+8], rcx
0x1400d98f0  test    r15b, r15b
0x1400d98f3  jz      short loc_1400D9970
0x1400d98f5  mov     rax, [rbx+30h]
0x1400d98f9  mov     r15d, 1
0x1400d98ff  mov     rcx, [rax+3D0h]
0x1400d9906  cmp     [rcx+0Ah], r15w
0x1400d990b  jbe     short loc_1400D9951
0x1400d990d  call    Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline
0x1400d9912  mov     rdx, [rbx+30h]
0x1400d9916  mov     rcx, [rdx+3D0h]
0x1400d991d  test    eax, eax
0x1400d991f  jz      short loc_1400D992A
0x1400d9921  test    byte ptr [rdx+1143h], 8
0x1400d9928  jnz     short loc_1400D9931
0x1400d992a  cmp     [rcx+0Ah], r15w
0x1400d992f  jnz     short loc_1400D9935
0x1400d9931  xor     eax, eax
0x1400d9933  jmp     short loc_1400D993F
0x1400d9935  mov     eax, [rcx+1Ch]
0x1400d9938  test    eax, eax
0x1400d993a  jnz     short loc_1400D993F
0x1400d993c  mov     eax, r15d
0x1400d993f  mov     esi, [rdx+51Ch]
0x1400d9945  mov     r14, [rcx+38h]
0x1400d9949  imul    rsi, rax
0x1400d994d  mov     [rbp+50h+var_B8], r14
0x1400d9951  lea     rdx, [rsp+150h+pulResult]; pulResult
0x1400d9956  mov     rcx, rsi; ullOperand
0x1400d9959  call    RtlULongLongToULong
0x1400d995e  test    eax, eax
0x1400d9960  js      short loc_1400D99CC
0x1400d9962  cmp     r14, rsi
0x1400d9965  jb      loc_1400D9CEB
0x1400d996b  mov     r12d, [rsp+150h+pulResult]
0x1400d9970  mov     edx, [rbx+78h]
0x1400d9973  lea     r9, [rsp+150h+var_DC]
0x1400d9978  mov     rcx, [rbx+70h]; ullSubtrahend
0x1400d997c  mov     r8, rsi
0x1400d997f  call    FveGetRedirectedBlockSize
0x1400d9984  test    eax, eax
0x1400d9986  js      loc_1400DA151
0x1400d998c  mov     rcx, [rbx+70h]
0x1400d9990  lea     rdx, [rsp+150h+var_DC]
0x1400d9995  xor     r15b, r15b
0x1400d9998  mov     r9d, r12d
0x1400d999b  mov     r8, r14
0x1400d999e  mov     [rsp+150h+pulResult], r15d
0x1400d99a3  call    IntersectRegion
0x1400d99a8  mov     rcx, [rbx+70h]
0x1400d99ac  lea     rax, [r14+rsi]
0x1400d99b0  mov     r12d, [rsp+150h+var_DC]
0x1400d99b5  cmp     rcx, rax
0x1400d99b8  jnb     short loc_1400D99EF
0x1400d99ba  lea     rax, [rcx+r12]
0x1400d99be  cmp     rax, r14
0x1400d99c1  jbe     short loc_1400D99EF
0x1400d99c3  mov     r8, rcx
0x1400d99c6  mov     [rbp+50h+var_D0], rcx
0x1400d99ca  jmp     short loc_1400D9A23
0x1400d99cc  xor     r9d, r9d; BugCheckParameter3
0x1400d99cf  cdqe
0x1400d99d1  xor     r8d, r8d; BugCheckParameter2
0x1400d99d4  mov     [rsp+150h+BugCheckParameter4], rax; BugCheckParameter4
0x1400d99d9  mov     ecx, 120h; BugCheckCode
0x1400d99de  lea     edx, [r9+0Ch]; BugCheckParameter1
0x1400d99e2  call    cs:__imp_KeBugCheckEx
0x1400d99ef  lea     r9, [rbp+50h+var_D0]
0x1400d99f3  mov     r8, r14
0x1400d99f6  mov     rdx, rsi
0x1400d99f9  call    FveGetRedirectedBlockOffset
0x1400d99fe  test    eax, eax
0x1400d9a00  js      loc_1400DA12E
0x1400d9a06  mov     r8, [rbp+50h+var_D0]
0x1400d9a0a  mov     eax, 1
0x1400d9a0f  cmp     rcx, r8
0x1400d9a12  movzx   r15d, r15b
0x1400d9a16  mov     [rbp+50h+var_D0], r8
0x1400d9a1a  cmovnz  r15d, eax
0x1400d9a1e  mov     [rsp+150h+pulResult], r15d
0x1400d9a23  test    r12d, r12d
0x1400d9a26  jz      loc_1400D9CEB
0x1400d9a2c  mov     eax, [rdi+78h]
0x1400d9a2f  xor     r15d, r15d
0x1400d9a32  mov     [rdi+18h], r15
0x1400d9a36  xor     r14b, r14b
0x1400d9a39  mov     rcx, [rbx+30h]
0x1400d9a3d  cmp     r12d, eax
0x1400d9a40  mov     [rsp+150h+var_E0], r15b
0x1400d9a45  cmova   r12d, eax
0x1400d9a49  mov     [rsp+150h+var_DC], r12d
0x1400d9a4e  test    dword ptr [rcx+328h], 100h
0x1400d9a58  jz      short loc_1400D9A92
0x1400d9a5a  mov     rcx, [rcx+2E0h]
0x1400d9a61  test    rcx, rcx
0x1400d9a64  jz      short loc_1400D9A92
0x1400d9a66  cmp     [rcx], r15
0x1400d9a69  jz      short loc_1400D9A92
0x1400d9a6b  mov     rdx, [rbx+38h]
0x1400d9a6f  test    rdx, rdx
0x1400d9a72  jz      short loc_1400D9A92
0x1400d9a74  mov     edx, [rdx+50h]
0x1400d9a77  lea     rax, [rsp+150h+var_DC]
0x1400d9a7c  mov     r9d, r12d
0x1400d9a7f  mov     [rsp+150h+BugCheckParameter4], rax
0x1400d9a84  call    FveEowFindBitmap
0x1400d9a89  mov     r12d, [rsp+150h+var_DC]
0x1400d9a8e  mov     [rdi+18h], rax
0x1400d9a92  call    Feature_BitLockerHwAccelCryptoSupport__private_IsEnabledDeviceUsageNoInline
0x1400d9a97  test    eax, eax
0x1400d9a99  jnz     short loc_1400D9ABD
0x1400d9a9b  cmp     [rsp+150h+var_DF], r14b
0x1400d9aa0  jz      loc_1400D9D3A
0x1400d9aa6  mov     r11b, [rsp+150h+var_DE]
0x1400d9aab  test    r11b, r11b
0x1400d9aae  jnz     short loc_1400D9AEC
0x1400d9ab0  mov     rax, [rbx+30h]
0x1400d9ab4  cmp     [rax+1290h], r15
0x1400d9abb  jmp     short loc_1400D9AE6
0x1400d9abd  cmp     [rsp+150h+var_DF], r14b
0x1400d9ac2  jz      loc_1400D9D3A
0x1400d9ac8  mov     r11b, [rsp+150h+var_DE]
0x1400d9acd  test    r11b, r11b
0x1400d9ad0  jnz     short loc_1400D9AEC
0x1400d9ad2  mov     rax, [rbx+30h]
0x1400d9ad6  cmp     [rax+1290h], r15
0x1400d9add  jnz     short loc_1400D9AEC
0x1400d9adf  cmp     [rbx+115h], r14b
0x1400d9ae6  jz      loc_1400D9D3A
0x1400d9aec  mov     r10, [rbx+30h]
0x1400d9af0  xor     r8d, r8d
0x1400d9af3  xor     r9d, r9d
0x1400d9af6  lea     r15d, [r8+1]
0x1400d9afa  lea     rax, [r9+r9*2]
0x1400d9afe  mov     rdx, r9
0x1400d9b01  mov     rcx, [r10+rax*8+420h]
0x1400d9b09  add     rdx, rdx
0x1400d9b0c  lea     rax, [r9+r9*2]
0x1400d9b10  add     r8d, r15d
0x1400d9b13  add     r9, r15
0x1400d9b16  mov     [rbp+rdx*8+50h+var_90], rcx
0x1400d9b1b  mov     ecx, [r10+rax*8+428h]
0x1400d9b23  mov     [rbp+rdx*8+50h+var_88], rcx
0x1400d9b28  cmp     r8d, 3
0x1400d9b2c  jb      short loc_1400D9AFA
0x1400d9b2e  cmp     byte ptr [rsp+150h+pulResult], r14b
0x1400d9b33  jnz     short loc_1400D9B57
0x1400d9b35  test    rsi, rsi
0x1400d9b38  jz      short loc_1400D9B57
0x1400d9b3a  cmp     r8d, 5
0x1400d9b3e  jnb     short loc_1400D9B57
0x1400d9b40  mov     rcx, [rbp+50h+var_B8]
0x1400d9b44  mov     eax, r8d
0x1400d9b47  add     rax, rax
0x1400d9b4a  add     r8d, r15d
0x1400d9b4d  mov     [rbp+rax*8+50h+var_90], rcx
0x1400d9b52  mov     [rbp+rax*8+50h+var_88], rsi
0x1400d9b57  mov     rax, [r10+3D0h]
0x1400d9b5e  cmp     word ptr [rax+0Ch], 2
0x1400d9b63  jnz     short loc_1400D9B89
0x1400d9b65  mov     edx, [rax+18h]
0x1400d9b68  test    edx, edx
0x1400d9b6a  jz      short loc_1400D9B89
0x1400d9b6c  cmp     r8d, 5
0x1400d9b70  jnb     short loc_1400D9B89
0x1400d9b72  mov     rax, [rax+10h]
0x1400d9b76  mov     ecx, r8d
0x1400d9b79  add     rcx, rcx
0x1400d9b7c  add     r8d, r15d
0x1400d9b7f  mov     [rbp+rcx*8+50h+var_90], rax
0x1400d9b84  mov     [rbp+rcx*8+50h+var_88], rdx
0x1400d9b89  mov     r9, [r10+2E0h]
0x1400d9b90  mov     al, r11b
0x1400d9b93  neg     al
0x1400d9b95  sbb     edx, edx
0x1400d9b97  and     edx, 0FFFFFFFEh
0x1400d9b9a  add     edx, 5
0x1400d9b9d  test    r9, r9
0x1400d9ba0  jz      short loc_1400D9BB1
0x1400d9ba2  mov     rax, [r9]
0x1400d9ba5  or      edx, 8
0x1400d9ba8  test    [rax+30h], r15b
0x1400d9bac  jz      short loc_1400D9BB1
0x1400d9bae  or      edx, 10h
0x1400d9bb1  mov     rsi, [rbp+50h+var_D0]
0x1400d9bb5  lea     rax, [rbp+50h+var_B0]
0x1400d9bb9  mov     [rsp+150h+var_E8], rax
0x1400d9bbe  mov     rcx, rsi
0x1400d9bc1  mov     [rsp+150h+var_F0], edx
0x1400d9bc5  lea     rax, [rbp+50h+var_A0]
0x1400d9bc9  mov     [rsp+150h+var_F8], rax
0x1400d9bce  mov     edx, r12d
0x1400d9bd1  mov     rax, [rbx+38h]
0x1400d9bd5  mov     [rsp+150h+var_100], rax
0x1400d9bda  mov     rax, [r10+3F0h]
0x1400d9be1  mov     [rsp+150h+var_108], r9
0x1400d9be6  mov     r9d, [r10+51Ch]
0x1400d9bed  mov     [rsp+150h+var_110], rax
0x1400d9bf2  mov     rax, [r10+410h]
0x1400d9bf9  mov     [rsp+150h+var_118], r15b
0x1400d9bfe  mov     [rsp+150h+var_120], rax
  ... truncated ...
```
