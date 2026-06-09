# NtfsReadUsnJournal

- ea: `0x1401e55bc`
- end: `0x1401e697b`
- name: `NtfsReadUsnJournal`
- size: `5055`
- prototype: `__int64 __fastcall(__int64, IRP *, char, char)`
- caller_count: `2`
- callee_count: `22`
- tags: `broker_com_uri`

## callers

- `0x1401e52d0`
- `0x1401f5890`

## callees

- `0x140007ea0`
- `0x1400082b0`
- `0x1400085e0`
- `0x140009830`
- `0x14000c290`
- `0x140020de0`
- `0x140025830`
- `0x14002b4a0`
- `0x140041d28`
- `0x140048a74`
- `0x140059250`
- `0x1400592c0`
- `0x1400596c0`
- `0x1400bdc7c`
- `0x1400bdd90`
- `0x1400bde74`
- `0x1400bdebc`
- `0x1400bdf00`
- `0x1401aab20`
- `0x1401e55bc`
- `0x1401e6984`
- `0x1401e6c80`

## import_xrefs

- `ntoskrnl!CcMapData` at `0x1401e5c13`
- `ntoskrnl!CcMapData` at `0x1401e5c13`
- `ntoskrnl!ProbeForWrite` at `0x1401e6297`
- `ntoskrnl!ProbeForWrite` at `0x1401e6297`
- `ntoskrnl!ProbeForRead` at `0x1401e626c`
- `ntoskrnl!ProbeForRead` at `0x1401e626c`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x1401e60f0`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x1401e60f0`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x1401e59fc`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x1401e59fc`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1401e651e`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1401e651e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401e60dd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401e60dd`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1401e5950`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1401e5950`
- `ntoskrnl!CcUnpinData` at `0x1401e5fb5`
- `ntoskrnl!CcUnpinData` at `0x1401e6931`
- `ntoskrnl!CcUnpinData` at `0x1402b10f3`
- `ntoskrnl!CcUnpinData` at `0x1401e5fb5`
- `ntoskrnl!CcUnpinData` at `0x1401e6931`
- `ntoskrnl!CcUnpinData` at `0x1402b10f3`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401e5aa8`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401e6899`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402b1136`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401e5aa8`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401e6899`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402b1136`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401e5858`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401e5b21`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401e5858`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401e5b21`
- `ntoskrnl!ExRaiseStatus` at `0x1401e66a8`
- `ntoskrnl!ExRaiseStatus` at `0x1401e66a8`

## pseudocode

```c
__int64 __fastcall NtfsReadUsnJournal(__int64 a1, IRP *a2, char a3, char a4)
{
  __int64 v6; // r15
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rdx
  PFILE_OBJECT FileObject; // rcx
  union _LARGE_INTEGER *FsContext; // r8
  unsigned __int8 *FsContext2; // rcx
  __int64 QuadPart; // r14
  int v12; // eax
  int v13; // edi
  unsigned int v14; // edi
  __int64 v15; // rsi
  __int64 *v16; // r9
  int v17; // eax
  KPROCESSOR_MODE v18; // bl
  PNAMED_PIPE_CREATE_PARAMETERS Parameters; // rdx
  struct _IO_STACK_LOCATION *v20; // rcx
  unsigned int Length; // eax
  __int64 v22; // rcx
  __int64 v23; // rdx
  bool v24; // sf
  __int64 v25; // rbx
  _QWORD *PoolWithTag; // r14
  struct _IO_STACK_LOCATION *v27; // rax
  _QWORD *v28; // rdx
  struct _ERESOURCE *v29; // rcx
  int v30; // r9d
  __int64 v31; // rcx
  __int64 v32; // rax
  __int64 v33; // rbx
  __int64 v34; // rbx
  unsigned __int16 *v35; // rbx
  unsigned __int16 v36; // r8
  __int64 v37; // rax
  __int64 v38; // rcx
  unsigned int v39; // eax
  unsigned __int16 v40; // cx
  unsigned int v41; // r14d
  int v42; // eax
  size_t v43; // r8
  char *v44; // rdx
  char *v45; // rbx
  void *v46; // rcx
  bool v47; // zf
  PNAMED_PIPE_CREATE_PARAMETERS v48; // rax
  PNAMED_PIPE_CREATE_PARAMETERS v49; // rax
  __int16 UShortFromUser; // ax
  unsigned __int16 NamedPipeType_high; // ax
  unsigned int v52; // r8d
  int v53; // r14d
  __int64 v54; // rax
  char *v55; // rax
  _WORD *v56; // rcx
  __int64 v57; // rcx
  IRP *v58; // rax
  IRP *v59; // rdx
  struct _ERESOURCE *v61; // rcx
  __int16 v62; // si
  unsigned __int8 *v63; // r9
  __int64 v64; // r10
  unsigned __int16 v65; // ax
  int Buffer; // [rsp+28h] [rbp-1C0h]
  KPROCESSOR_MODE RequestorMode; // [rsp+71h] [rbp-177h]
  char v69; // [rsp+73h] [rbp-175h]
  char v70; // [rsp+74h] [rbp-174h]
  char v71; // [rsp+75h] [rbp-173h]
  bool v72; // [rsp+7Ch] [rbp-16Ch]
  char v73[3]; // [rsp+7Dh] [rbp-16Bh] BYREF
  unsigned int v74; // [rsp+80h] [rbp-168h]
  int v75; // [rsp+84h] [rbp-164h]
  void *v76; // [rsp+88h] [rbp-160h]
  PVOID Src; // [rsp+90h] [rbp-158h] BYREF
  unsigned int v78; // [rsp+98h] [rbp-150h]
  struct _IO_STACK_LOCATION *v79; // [rsp+A0h] [rbp-148h]
  __int64 v80; // [rsp+A8h] [rbp-140h]
  union _LARGE_INTEGER FileOffset; // [rsp+B0h] [rbp-138h] BYREF
  __int64 v82; // [rsp+B8h] [rbp-130h]
  __int64 v83; // [rsp+C0h] [rbp-128h]
  __int64 *v84; // [rsp+C8h] [rbp-120h]
  PNAMED_PIPE_CREATE_PARAMETERS v85; // [rsp+D0h] [rbp-118h]
  int v86; // [rsp+D8h] [rbp-110h]
  int v87; // [rsp+DCh] [rbp-10Ch]
  __int64 v88; // [rsp+E0h] [rbp-108h]
  __int64 v89; // [rsp+E8h] [rbp-100h] BYREF
  __int64 v90; // [rsp+F0h] [rbp-F8h]
  __int64 v91; // [rsp+F8h] [rbp-F0h]
  __int64 v92; // [rsp+100h] [rbp-E8h]
  __int128 v93; // [rsp+108h] [rbp-E0h]
  PVOID Bcb[2]; // [rsp+118h] [rbp-D0h] BYREF
  __int128 v95; // [rsp+128h] [rbp-C0h] BYREF
  __int128 v96; // [rsp+138h] [rbp-B0h] BYREF
  __int128 v97; // [rsp+148h] [rbp-A0h]
  _QWORD v98[10]; // [rsp+160h] [rbp-88h] BYREF

  v6 = a1;
  v91 = a1;
  Src = 0;
  v93 = 0;
  *(_OWORD *)Bcb = 0;
  v95 = 0;
  v96 = 0;
  v97 = 0;
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v79 = CurrentStackLocation;
  FileObject = CurrentStackLocation->FileObject;
  FsContext = (union _LARGE_INTEGER *)FileObject->FsContext;
  if ( FsContext )
  {
    FsContext2 = (unsigned __int8 *)FileObject->FsContext2;
    QuadPart = FsContext[24].QuadPart;
    v88 = QuadPart;
    v12 = *(_DWORD *)(QuadPart + 4);
    if ( (v12 & 1) == 0 && (!FsContext2 || FsContext2[88] != 4 || (v12 & 2) == 0) )
      NtfsRaiseStatusInternal(v6, -1073741202, 0, 0, 0);
    v90 = QuadPart;
    FileOffset = FsContext[23];
    if ( FsContext2 )
      v13 = FsContext2[88];
    else
      v13 = 5;
  }
  else
  {
    QuadPart = 0;
    v88 = 0;
    v90 = 0;
    FsContext2 = 0;
    FileOffset.QuadPart = 0;
    v13 = 1;
  }
  if ( !a4
    && (!FsContext2
     || !_bittest16((const signed __int16 *)FsContext2 + 52, 9u)
     && (a2->RequestorMode || CurrentStackLocation->MinorFunction != 4)) )
  {
    if ( (!v6 || (*(_DWORD *)(v6 + 16) & 0x100000) == 0)
      && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x20) != 0 )
    {
      if ( FsContext2 )
        v62 = *((_WORD *)FsContext2 + 52);
      else
        LOBYTE(v62) = 0;
      v63 = FsContext2 + 16;
      if ( !FsContext2 )
        v63 = 0;
      v64 = *(_QWORD *)(QuadPart + 248);
      v65 = *(_WORD *)(v64 + 6);
      if ( v65 > 0x40u || (v65 & 1) != 0 )
        v65 = 0;
      McTemplateU0pdpwwpiwd_EtwWriteTransfer(
        FsContext[23].QuadPart,
        (const EVENT_DESCRIPTOR *)usnsup_c334,
        (__int64)KeGetCurrentThread(),
        v13,
        QuadPart,
        *(_WORD *)(QuadPart + 7872) >> 1,
        *(_QWORD *)(QuadPart + 7880),
        v65 >> 1,
        v64 + 32,
        FileOffset.QuadPart,
        *(_QWORD *)(FsContext[23].QuadPart + 8),
        *(_WORD *)v63 >> 1,
        *((_QWORD *)v63 + 1),
        v62);
    }
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(v6, 0xC0000022, 0x2B015Fu);
    NtfsExtendedCompleteRequestInternal(v6, a2, -1073741790, a2 != 0, 0);
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(0, 0xC0000022, 0x2B0160u);
    return 3221225506LL;
  }
  v14 = 0;
  v15 = 0;
  v80 = 0;
  v69 = 0;
  v70 = 0;
  v71 = 0;
  DWORD2(v97) = 131074;
  v72 = 1;
  if ( a3 )
    v72 = (*(_BYTE *)(v6 + 12) & 1) != 0;
  v16 = (__int64 *)NtfsMapUserBuffer((__int64)a2, 16);
  v84 = v16;
  if ( a2->MdlAddress )
    RequestorMode = 0;
  else
    RequestorMode = a2->RequestorMode;
  v17 = *(_DWORD *)(v6 + 12);
  v86 = (v17 & 1) == 0;
  v87 = v86;
  *(_DWORD *)(v6 + 12) = v17 | 1;
  if ( a2->RequestorMode )
  {
    if ( a3 )
    {
      ProbeForRead(v79->Parameters.CreatePipe.Parameters, v79->Parameters.Create.Options, 4u);
      v16 = v84;
    }
    if ( !a2->MdlAddress )
      ProbeForWrite(v16, v79->Parameters.Read.Length, 4u);
  }
  else if ( v79->Parameters.CreatePipe.Parameters != (PNAMED_PIPE_CREATE_PARAMETERS)(((unsigned __int64)&v79->Parameters.CreatePipe.Parameters->NamedPipeType
                                                                                    + 3)
                                                                                   & 0xFFFFFFFFFFFFFFFCuLL)
         || !a2->MdlAddress && v16 != (__int64 *)(((unsigned __int64)v16 + 3) & 0xFFFFFFFFFFFFFFFCuLL) )
  {
    v14 = -1073741811;
    if ( NtfsStatusDebugFlags )
    {
      v52 = 2818466;
      goto LABEL_102;
    }
    goto LABEL_188;
  }
  if ( !a3 || (v71 = NtfsAcquireSharedVcb(v6, QuadPart, 1), (*(_DWORD *)(QuadPart + 4) & 0x80000) != 0) )
    v15 = *(_QWORD *)(QuadPart + 40);
  else
    v15 = 0;
  v80 = v15;
  if ( (*(_DWORD *)(QuadPart + 4) & 0x100000) == 0 && *(int *)(QuadPart + 24) >= 0 )
  {
    if ( !v15 )
    {
      v14 = -1073741128;
      if ( NtfsStatusDebugFlags )
      {
        v52 = 2818512;
        goto LABEL_102;
      }
      goto LABEL_188;
    }
    if ( v79->Parameters.Create.Options < 0x28 )
    {
      v14 = -1073741592;
      if ( NtfsStatusDebugFlags )
      {
        v52 = 2818522;
        goto LABEL_102;
      }
      goto LABEL_188;
    }
    if ( a3 )
      v18 = a2->RequestorMode;
    else
      v18 = 0;
    Parameters = v79->Parameters.CreatePipe.Parameters;
    if ( v18 )
      RtlCopyFromUser(&v95, Parameters, 0x28u);
    else
      RtlCopyVolatileMemory(&v95, Parameters, 0x28u);
    v20 = v79;
    if ( v79->Parameters.Create.Options >= 0x30 )
    {
      v49 = v79->Parameters.CreatePipe.Parameters;
      v85 = v49;
      if ( v18 )
        UShortFromUser = RtlReadUShortFromUser((unsigned __int16 *)&v49[1]);
      else
        UShortFromUser = v49[1].NamedPipeType;
      WORD4(v97) = UShortFromUser;
      if ( v18 )
        NamedPipeType_high = RtlReadUShortFromUser((unsigned __int16 *)&v85[1].NamedPipeType + 1);
      else
        NamedPipeType_high = HIWORD(v85[1].NamedPipeType);
      WORD5(v97) = NamedPipeType_high;
      if ( WORD4(v97) > NamedPipeType_high )
      {
        v14 = -1073741811;
        if ( NtfsStatusDebugFlags )
        {
          v52 = 2818550;
          goto LABEL_102;
        }
        goto LABEL_188;
      }
      if ( WORD4(v97) > 3u || NamedPipeType_high < 2u )
      {
        v14 = -1073741811;
        if ( NtfsStatusDebugFlags )
        {
          v52 = 2818560;
          goto LABEL_102;
        }
        goto LABEL_188;
      }
      v20 = v79;
    }
    if ( (_QWORD)v97 != *(_QWORD *)(QuadPart + 1912) )
    {
      v14 = -1073741811;
      if ( NtfsStatusDebugFlags )
      {
        v52 = 2818581;
        goto LABEL_102;
      }
      goto LABEL_188;
    }
    Length = v20->Parameters.Read.Length;
    if ( Length < 8 )
    {
      v14 = -1073741789;
      if ( NtfsStatusDebugFlags )
      {
        v52 = 2818592;
        goto LABEL_102;
      }
      goto LABEL_188;
    }
    v74 = Length - 8;
    v76 = v84 + 1;
    v78 = 8;
    v22 = v15;
    if ( *(_WORD *)v15 != 1794 )
      v22 = *(_QWORD *)(v15 + 184);
    ExAcquireResourceSharedLite((PERESOURCE)(*(_QWORD *)(v22 + 104) + 64LL), 1u);
    v69 = 1;
    if ( v71 )
    {
      NtfsReleaseVcb(v6, QuadPart);
      v71 = 0;
    }
    if ( (*(_DWORD *)(v15 + 512) & 0x10000) != 0 )
    {
      v14 = -1073741202;
      if ( NtfsStatusDebugFlags )
      {
        v52 = 2818618;
        goto LABEL_102;
      }
      goto LABEL_188;
    }
    v23 = v95;
    v24 = (__int64)v95 < 0;
    if ( !(_QWORD)v95 )
    {
      v23 = *(_QWORD *)(QuadPart + 1928);
      *(_QWORD *)&v95 = v23;
      v24 = v23 < 0;
    }
    if ( v24 || *((_QWORD *)&v96 + 1) > 0x7FFFFFFFFFFFFFFFuLL || v23 + *((_QWORD *)&v96 + 1) < 0 )
    {
      v14 = -1073741811;
      if ( NtfsStatusDebugFlags )
      {
        v52 = 2818640;
        goto LABEL_102;
      }
      goto LABEL_188;
    }
    while ( 1 )
    {
      if ( v23 < *(_QWORD *)(QuadPart + 1928) )
      {
        *(_QWORD *)&v95 = *(_QWORD *)(QuadPart + 1928);
        v14 = -1073741105;
        if ( NtfsStatusDebugFlags )
          NtfsStatusTraceAndDebugInternal(0, 0xC00002CF, 0x2B0260u);
        v23 = v95;
LABEL_130:
        a2->IoStatus.Information = v78;
        if ( RequestorMode )
          RtlWriteULong64ToUser(v84, v23);
        else
          *v84 = v23;
        goto LABEL_188;
      }
      if ( v23 >= *(_QWORD *)(v15 + 32) )
      {
        if ( (*(_DWORD *)(QuadPart + 4) & 0x2000000) != 0 )
        {
          v14 = -1073741662;
          if ( NtfsStatusDebugFlags )
          {
            v52 = 2818673;
            goto LABEL_102;
          }
          goto LABEL_188;
        }
        if ( !*((_QWORD *)&v96 + 1) )
          goto LABEL_130;
        _InterlockedIncrement((volatile signed __int32 *)(v15 + 212));
        v70 = 1;
        if ( !v72 || a2 != *(IRP **)(v6 + 112) )
        {
          v25 = v95 + *((_QWORD *)&v96 + 1);
          v14 = 259;
          PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)528, 0x78u, 0x7646744Eu);
          memset(PoolWithTag, 0, 0x48u);
          *(_OWORD *)(PoolWithTag + 9) = v95;
          *(_OWORD *)(PoolWithTag + 11) = v96;
          *(_OWORD *)(PoolWithTag + 13) = v97;
          v27 = v79;
          v79->Parameters.CreatePipe.Parameters = (PNAMED_PIPE_CREATE_PARAMETERS)(PoolWithTag + 9);
          v27->Parameters.Create.Options = 48;
          PoolWithTag[6] = a2;
          PoolWithTag[2] = v25;
          PoolWithTag[7] = v15;
          *((_DWORD *)PoolWithTag + 16) = 0;
          *((_DWORD *)PoolWithTag + 17) = 5;
          if ( a4 )
            *((_DWORD *)PoolWithTag + 17) = 7;
          if ( *(IRP **)(v6 + 112) == a2 )
            NtfsPrePostIrpInternal(v6, (__int64)a2, 0, 0, 1);
          FsRtlAcquireHeaderMutex(v15 + 120, v15 + 160);
          if ( NtfsSetCancelRoutine((__int64)a2, (__int64)NtfsCancelReadUsnJournal, (__int64)PoolWithTag, 1) )
          {
            v28 = *(_QWORD **)(v15 + 600);
            if ( *v28 != v15 + 592 )
              __fastfail(3u);
            *PoolWithTag = v15 + 592;
            PoolWithTag[1] = v28;
            *v28 = PoolWithTag;
            *(_QWORD *)(v15 + 600) = PoolWithTag;
          }
          else
          {
            v14 = -1073741536;
            if ( NtfsStatusDebugFlags )
              NtfsStatusTraceAndDebugInternal(0, 0xC0000120, 0x2C04B6u);
            ExFreePoolWithTag(PoolWithTag, 0);
          }
          FsRtlReleaseHeaderMutex(v15 + 120, v15 + 160);
          if ( v14 == 259 )
            v70 = 0;
          goto LABEL_188;
        }
        if ( *(_WORD *)v15 == 1794 )
          v29 = (struct _ERESOURCE *)(*(_QWORD *)(v15 + 104) + 64LL);
        else
          v29 = *(struct _ERESOURCE **)(v15 + 8);
        ExReleaseResourceLite(v29);
        v69 = 0;
        LOBYTE(v30) = a4;
        v14 = NtOfsWaitForNewLength(
                v15,
                (int)v95 + DWORD2(v96),
                (unsigned __int64)&v96 & -(__int64)((_QWORD)v96 != 0),
                v30,
                (__int64)a2,
                Buffer,
                (PLARGE_INTEGER)((unsigned __int64)&v96 & -(__int64)((_QWORD)v96 != 0)));
        if ( v14 )
          goto LABEL_188;
        v31 = v15;
        if ( *(_WORD *)v15 != 1794 )
          v31 = *(_QWORD *)(v15 + 184);
        ExAcquireResourceSharedLite((PERESOURCE)(*(_QWORD *)(v31 + 104) + 64LL), 1u);
        v69 = 1;
        _InterlockedDecrement((volatile signed __int32 *)(v15 + 212));
        v70 = 0;
        v32 = *(_QWORD *)(v15 + 192);
        if ( v15 != *(_QWORD *)(v32 + 40) )
        {
          if ( (*(_DWORD *)(v32 + 4) & 0x100000) != 0 || *(int *)(QuadPart + 24) < 0 )
          {
            v14 = -1073741129;
            if ( NtfsStatusDebugFlags )
            {
              v52 = 2818784;
              goto LABEL_102;
            }
          }
          else
          {
            v14 = -1073741128;
            if ( NtfsStatusDebugFlags )
            {
              v52 = 2818786;
              goto LABEL_102;
            }
          }
          goto LABEL_188;
        }
        v23 = v95;
      }
LABEL_62:
      if ( !v74 )
        goto LABEL_130;
      v33 = *(_QWORD *)(v15 + 32);
      if ( v23 < v33 )
        break;
      if ( v78 != 8 )
        goto LABEL_130;
    }
    FileOffset.QuadPart = 0;
    v73[0] = 0;
    v89 = 0;
    v34 = v33 - v23;
    v82 = v34;
    if ( v34 > 0x40000 - ((unsigned int)v23 & 0x3FFFF) )
      v34 = 0x40000 - ((unsigned int)v23 & 0x3FFFF);
    v83 = v34;
    v82 = v34;
    FileOffset.QuadPart = v23 - *(_QWORD *)(QuadPart + 1952);
    NtfsPerformPrefetch(*(PFILE_OBJECT *)(v15 + 280), FileOffset.QuadPart, v34);
    CcMapData(*(PFILE_OBJECT *)(v15 + 280), &FileOffset, v34, 1u, &Bcb[1], &Src);
    *(union _LARGE_INTEGER *)&v93 = FileOffset;
    DWORD2(v93) = v34;
    LODWORD(v34) = (_DWORD)Src;
    Bcb[0] = Src;
    LODWORD(v23) = v95;
LABEL_67:
    if ( !(unsigned __int8)NtfsValidateUsnPage(
                             (unsigned int)v34 & 0xFFFFF000,
                             (unsigned int)v23 & 0xFFFFF000,
                             (unsigned int)&v95,
                             *(_QWORD *)(v15 + 32),
                             (__int64)v73,
                             (__int64)&v89) )
    {
      v14 = -1073741762;
      if ( !NtfsStatusDebugFlags )
        goto LABEL_188;
      v52 = 2818869;
      goto LABEL_102;
    }
    if ( !v73[0] )
    {
      v14 = -1073741811;
      if ( !NtfsStatusDebugFlags )
        goto LABEL_188;
      v52 = 2818879;
LABEL_102:
      NtfsStatusTraceAndDebugInternal(0, v14, v52);
      goto LABEL_188;
    }
    v35 = (unsigned __int16 *)Src;
    v36 = WORD5(v97);
    v23 = v95;
    v37 = v89;
    v92 = v89;
    v38 = v83;
    while ( 1 )
    {
      if ( v23 >= v37 )
      {
        if ( !v74 )
          goto LABEL_104;
        v54 = -(int)v37 & 0xFFF;
        if ( v54 > v38 )
          v54 = (unsigned int)v38;
        v34 = (__int64)v35 + v54;
        Src = (PVOID)v34;
        v23 += v54;
        *(_QWORD *)&v95 = v23;
        v83 = v38 - v54;
        v82 = v38 - v54;
        if ( v38 == v54 )
          goto LABEL_104;
        goto LABEL_67;
      }
      v75 = 0;
      v39 = *(_DWORD *)v35;
      LODWORD(v82) = *(_DWORD *)v35;
      v40 = v35[2];
      if ( v36 >= 3u && v40 == 2 )
      {
        v53 = 76;
        v75 = 76;
        if ( !a4 )
        {
          v53 = v35[28] + 76;
          v75 = v53;
        }
        v41 = (v53 + 7) & 0xFFFFFFF8;
      }
      else
      {
        v41 = v39;
        v75 = v39;
        if ( v40 != 2 )
          goto LABEL_73;
        if ( a4 )
          v41 = 64;
      }
      v75 = v41;
LABEL_73:
      v42 = *((_DWORD *)v35 + 10);
      if ( (v42 & DWORD2(v95)) != 0 && (!HIDWORD(v95) || v42 < 0) && (unsigned __int16)(v40 - 2) <= 2u && v36 >= v40 )
      {
        if ( v41 > v74 )
        {
          v74 = 0;
LABEL_104:
          if ( Bcb[1] )
          {
            CcUnpinData(Bcb[1]);
            Bcb[1] = 0;
            v23 = v95;
          }
          QuadPart = v88;
          goto LABEL_62;
        }
        if ( v36 >= 3u && v40 == 2 )
        {
          memset(v98, 0, sizeof(v98));
          v98[0] = v41 | 0x300000000LL;
          v98[2] = 0;
          v98[1] = *((_QWORD *)v35 + 1);
          v98[4] = 0;
          v98[3] = *((_QWORD *)v35 + 2);
          *(_OWORD *)&v98[5] = *(_OWORD *)(v35 + 12);
          *(_OWORD *)&v98[7] = *(_OWORD *)(v35 + 20);
          LOWORD(v98[9]) = v35[28];
          WORD1(v98[9]) = 76;
          v43 = 80;
          v44 = (char *)v98;
          if ( a4 )
          {
            LOWORD(v98[9]) = 0;
            v47 = RequestorMode == 0;
            v46 = v76;
          }
          else
          {
            v45 = (char *)v76;
            if ( RequestorMode )
              RtlCopyToUser(v76, v98, 0x50u);
            else
              RtlCopyVolatileMemory(v76, v98, 0x50u);
            v43 = *((unsigned __int16 *)Src + 28);
            v44 = (char *)Src + 60;
            v46 = v45 + 76;
            v47 = RequestorMode == 0;
          }
          if ( v47 )
            RtlCopyVolatileMemory(v46, v44, v43);
          else
            RtlCopyToUser(v46, v44, v43);
          v48 = (PNAMED_PIPE_CREATE_PARAMETERS)v41;
LABEL_87:
          v35 = (unsigned __int16 *)Src;
        }
        else
        {
          v85 = (PNAMED_PIPE_CREATE_PARAMETERS)v41;
          if ( RequestorMode )
            RtlCopyToUser(v76, v35, v41);
          else
            RtlCopyVolatileMemory(v76, v35, v41);
          v48 = (PNAMED_PIPE_CREATE_PARAMETERS)v41;
          v35 = (unsigned __int16 *)Src;
          if ( a4 && *((_WORD *)Src + 2) == 2 )
          {
            if ( RequestorMode )
            {
              RtlWriteULongToUser(v76, v41);
              v55 = (char *)v76;
            }
            else
            {
              v55 = (char *)v76;
              *(_DWORD *)v76 = v41;
            }
            v56 = v55 + 56;
            if ( RequestorMode )
              RtlWriteUShortToUser(v56, 0);
            else
              *v56 = 0;
            v48 = v85;
            goto LABEL_87;
          }
        }
        v74 -= v41;
        v78 += v41;
        v76 = (char *)v76 + (_QWORD)v48;
        v36 = WORD5(v97);
        v23 = v95;
      }
      v23 += (unsigned int)v82;
      *(_QWORD *)&v95 = v23;
      v35 = (unsigned __int16 *)((char *)v35 + (unsigned int)v82);
      Src = v35;
      v38 = v83 - (unsigned int)v82;
      v83 = v38;
      v82 = v38;
      v37 = v92;
    }
  }
  v14 = -1073741129;
  if ( NtfsStatusDebugFlags )
  {
    v52 = 2818502;
    goto LABEL_102;
  }
LABEL_188:
  if ( Bcb[1] )
  {
    CcUnpinData(Bcb[1]);
    Bcb[1] = 0;
  }
  if ( v69 )
  {
    if ( *(_WORD *)v15 == 1794 )
      v61 = (struct _ERESOURCE *)(*(_QWORD *)(v15 + 104) + 64LL);
    else
      v61 = *(struct _ERESOURCE **)(v15 + 8);
    ExReleaseResourceLite(v61);
  }
  if ( v70 )
    _InterlockedDecrement((volatile signed __int32 *)(v15 + 212));
  if ( v71 )
    NtfsReleaseVcb(v6, v88);
  *(_DWORD *)(v6 + 12) &= ~v86;
  v57 = v6;
  if ( a2 != *(IRP **)(v6 + 112) )
    v57 = 0;
  if ( NtfsStatusDebugFlags
    && v14
    && v14 != 294
    && v14 - 298 > 1
    && v14 < 0xFFFFFFED
    && v14 != -1073741608
    && v14 != -1073741802
    && v14 != -1073741807
    && v14 + 2147483643 > 1
    && v14 != 259 )
  {
    NtfsStatusTraceAndDebugInternal(v57, v14, 0x2B044Au);
  }
  v58 = 0;
  if ( v14 != 259 )
    v58 = a2;
  v59 = 0;
  if ( v14 != 259 )
    v59 = a2;
  if ( a2 != *(IRP **)(v6 + 112) )
    v6 = 0;
  NtfsExtendedCompleteRequestInternal(v6, v59, v14, v58 != 0, (v14 & 0x80000000) == 0);
  return v14;
}

```

## disassembly

```asm
0x1401e55bc  mov     [rsp+arg_10], rbx
0x1401e55c1  push    rsi
0x1401e55c2  push    rdi
0x1401e55c3  push    r13
0x1401e55c5  push    r14
0x1401e55c7  push    r15
0x1401e55c9  sub     rsp, 1C0h
0x1401e55d0  mov     rax, cs:__security_cookie
0x1401e55d7  xor     rax, rsp
0x1401e55da  mov     [rsp+1E8h+var_38], rax
0x1401e55e2  mov     r10b, r9b
0x1401e55e5  mov     byte ptr [rsp+1E8h+var_176], r9b
0x1401e55ea  mov     bl, r8b
0x1401e55ed  mov     r13, rdx
0x1401e55f0  mov     r15, rcx
0x1401e55f3  mov     [rsp+1E8h+var_F0], rcx
0x1401e55fb  xor     r11d, r11d
0x1401e55fe  mov     [rsp+1E8h+Src], r11
0x1401e5606  xorps   xmm0, xmm0
0x1401e5609  movups  [rsp+1E8h+var_E0], xmm0
0x1401e5611  movups  xmmword ptr [rsp+1E8h+var_D0], xmm0
0x1401e5619  xorps   xmm1, xmm1
0x1401e561c  movups  [rsp+1E8h+var_C0], xmm1
0x1401e5624  movups  [rsp+1E8h+var_B0], xmm1
0x1401e562c  movups  [rsp+1E8h+var_A0], xmm1
0x1401e5634  mov     rdx, [rdx+0B8h]
0x1401e563b  mov     [rsp+1E8h+var_148], rdx
0x1401e5643  mov     rcx, [rdx+30h]
0x1401e5647  mov     r8, [rcx+18h]
0x1401e564b  test    r8, r8
0x1401e564e  jz      loc_1401E6909
0x1401e5654  mov     rcx, [rcx+20h]
0x1401e5658  mov     r14, [r8+0C0h]
0x1401e565f  mov     [rsp+1E8h+var_108], r14
0x1401e5667  mov     eax, [r14+4]
0x1401e566b  test    al, 1
0x1401e566d  jz      loc_1401E68D6
0x1401e5673  mov     [rsp+1E8h+var_F8], r14
0x1401e567b  mov     rax, [r8+0B8h]
0x1401e5682  mov     qword ptr [rsp+1E8h+FileOffset], rax
0x1401e568a  test    rcx, rcx
0x1401e568d  jz      loc_1401E68CC
0x1401e5693  movzx   edi, byte ptr [rcx+58h]
0x1401e5697  test    r10b, r10b
0x1401e569a  jz      loc_1401E6779
0x1401e56a0  mov     edi, r11d
0x1401e56a3  mov     rsi, r11
0x1401e56a6  mov     [rsp+1E8h+var_140], r11
0x1401e56ae  mov     byte ptr [rsp+1E8h+var_176+1], r11b
0x1401e56b3  mov     [rsp+1E8h+var_178], r11b
0x1401e56b8  mov     byte ptr [rsp+1E8h+var_176+2], r11b
0x1401e56bd  mov     byte ptr [rsp+1E8h+var_176+3], r11b
0x1401e56c2  mov     dword ptr [rsp+1E8h+var_A0+8], 20002h
0x1401e56cd  mov     cl, 1
0x1401e56cf  mov     [rsp+1E8h+var_16C], cl
0x1401e56d3  test    bl, bl
0x1401e56d5  jnz     loc_1401E68B7
0x1401e56db  mov     edx, 10h
0x1401e56e0  mov     rcx, r13
0x1401e56e3  call    NtfsMapUserBuffer
0x1401e56e8  mov     r9, rax
0x1401e56eb  mov     [rsp+1E8h+var_120], rax
0x1401e56f3  cmp     [r13+8], rsi
0x1401e56f7  jz      loc_1401E68AA
0x1401e56fd  mov     [rsp+1E8h+var_177], sil
0x1401e5702  mov     eax, [r15+0Ch]
0x1401e5706  mov     ecx, eax
0x1401e5708  not     ecx
0x1401e570a  and     ecx, 1
0x1401e570d  mov     [rsp+1E8h+var_110], ecx
0x1401e5714  mov     [rsp+1E8h+var_10C], ecx
0x1401e571b  or      eax, 1
0x1401e571e  mov     [r15+0Ch], eax
0x1401e5722  mov     [rsp+1E8h+var_178], 1
0x1401e5727  cmp     byte ptr [r13+40h], 0
0x1401e572c  jnz     loc_1401E6253
0x1401e5732  mov     rcx, [rsp+1E8h+var_148]
0x1401e573a  mov     rcx, [rcx+20h]
0x1401e573e  lea     rax, [rcx+3]
0x1401e5742  and     rax, 0FFFFFFFFFFFFFFFCh
0x1401e5746  cmp     rcx, rax
0x1401e5749  jnz     loc_1401E5A70
0x1401e574f  cmp     qword ptr [r13+8], 0
0x1401e5754  jz      loc_1401E5A5F
0x1401e575a  mov     [rsp+1E8h+var_178], 0
0x1401e575f  test    bl, bl
0x1401e5761  jnz     loc_1401E6037
0x1401e5767  mov     rsi, [r14+28h]
0x1401e576b  mov     [rsp+1E8h+var_140], rsi
0x1401e5773  test    dword ptr [r14+4], 100000h
0x1401e577b  jnz     loc_1401E6457
0x1401e5781  cmp     dword ptr [r14+18h], 0
0x1401e5786  jl      loc_1401E6457
0x1401e578c  test    rsi, rsi
0x1401e578f  jz      loc_1401E62A8
0x1401e5795  mov     r8d, 28h ; '('; Size
0x1401e579b  mov     rax, [rsp+1E8h+var_148]
0x1401e57a3  cmp     [rax+10h], r8d
0x1401e57a7  jb      loc_1401E62C6
0x1401e57ad  test    bl, bl
0x1401e57af  jz      loc_1401E5A43
0x1401e57b5  mov     bl, [r13+40h]
0x1401e57b9  mov     [rsp+1E8h+var_178], 1
0x1401e57be  mov     rdx, [rax+20h]; Src
0x1401e57c2  lea     rcx, [rsp+1E8h+var_C0]; void *
0x1401e57ca  test    bl, bl
0x1401e57cc  jnz     loc_1401E605E
0x1401e57d2  call    RtlCopyVolatileMemory
0x1401e57d7  mov     rcx, [rsp+1E8h+var_148]
0x1401e57df  cmp     dword ptr [rcx+10h], 30h ; '0'
0x1401e57e3  jnb     loc_1401E5F10
0x1401e57e9  nop
0x1401e57ea  mov     [rsp+1E8h+var_178], 0
0x1401e57ef  mov     rax, qword ptr [rsp+1E8h+var_A0]
0x1401e57f7  cmp     rax, [r14+778h]
0x1401e57fe  jnz     loc_1401E6320
0x1401e5804  mov     eax, [rcx+8]
0x1401e5807  cmp     eax, 8
0x1401e580a  jb      loc_1401E633E
0x1401e5810  add     eax, 0FFFFFFF8h
0x1401e5813  mov     [rsp+1E8h+var_168], eax
0x1401e581a  mov     rax, [rsp+1E8h+var_120]
0x1401e5822  add     rax, 8
0x1401e5826  mov     [rsp+1E8h+var_160], rax
0x1401e582e  mov     [rsp+1E8h+var_150], 8
0x1401e5839  mov     eax, 702h
0x1401e583e  cmp     ax, [rsi]
0x1401e5841  mov     rcx, rsi
0x1401e5844  jnz     loc_1401E6117
0x1401e584a  mov     rcx, [rcx+68h]
0x1401e584e  mov     ebx, 40h ; '@'
0x1401e5853  add     rcx, rbx; Resource
0x1401e5856  mov     dl, 1; Wait
0x1401e5858  call    cs:__imp_ExAcquireResourceSharedLite
0x1401e585f  nop     dword ptr [rax+rax+00h]
0x1401e5864  mov     byte ptr [rsp+1E8h+var_176+1], 1
0x1401e5869  cmp     byte ptr [rsp+1E8h+var_176+3], 0
0x1401e586e  jnz     loc_1401E5A4A
0x1401e5874  test    dword ptr [rsi+200h], 10000h
0x1401e587e  jz      short loc_1401E589C
0x1401e5880  mov     al, cs:NtfsStatusDebugFlags
0x1401e5886  mov     edi, 0C000026Eh
0x1401e588b  test    al, al
0x1401e588d  jnz     loc_1401E5F86
0x1401e5893  mov     [rsp+1E8h+var_170], edi
0x1401e5897  jmp     loc_1401E64E4
0x1401e589c  mov     rdx, qword ptr [rsp+1E8h+var_C0]
0x1401e58a4  test    rdx, rdx
0x1401e58a7  jz      loc_1401E6475
0x1401e58ad  js      loc_1401E6439
0x1401e58b3  mov     rcx, 7FFFFFFFFFFFFFFFh
0x1401e58bd  mov     rax, qword ptr [rsp+1E8h+var_B0+8]
0x1401e58c5  cmp     rax, rcx
0x1401e58c8  ja      loc_1401E6439
0x1401e58ce  add     rax, rdx
0x1401e58d1  js      loc_1401E6439
0x1401e58d7  mov     rax, [r14+788h]
0x1401e58de  cmp     rdx, rax
0x1401e58e1  jl      loc_1401E635C
0x1401e58e7  cmp     rdx, [rsi+20h]
0x1401e58eb  jl      loc_1401E5B57
0x1401e58f1  test    dword ptr [r14+4], 2000000h
0x1401e58f9  jnz     loc_1401E6393
0x1401e58ff  cmp     qword ptr [rsp+1E8h+var_B0+8], 0
0x1401e5908  jz      loc_1401E6132
0x1401e590e  lock inc dword ptr [rsi+0D4h]
0x1401e5915  mov     byte ptr [rsp+1E8h+var_176+2], 1
0x1401e591a  cmp     [rsp+1E8h+var_16C], 0
0x1401e591f  jnz     loc_1401E5A8C
0x1401e5925  mov     rbx, qword ptr [rsp+1E8h+var_B0+8]
0x1401e592d  add     rbx, qword ptr [rsp+1E8h+var_C0]
0x1401e5935  mov     al, cs:NtfsStatusDebugFlags
0x1401e593b  mov     edi, 103h
0x1401e5940  mov     edx, 78h ; 'x'; NumberOfBytes
0x1401e5945  mov     ecx, 210h; PoolType
0x1401e594a  mov     r8d, 7646744Eh; Tag
0x1401e5950  call    cs:__imp_ExAllocatePoolWithTag
0x1401e5957  nop     dword ptr [rax+rax+00h]
0x1401e595c  mov     r14, rax
0x1401e595f  xor     edx, edx; Val
0x1401e5961  lea     r8d, [rdx+48h]; Size
0x1401e5965  mov     rcx, rax; void *
0x1401e5968  call    memset
0x1401e596d  lea     rcx, [r14+48h]
0x1401e5971  movups  xmm0, [rsp+1E8h+var_C0]
0x1401e5979  movups  xmmword ptr [rcx], xmm0
0x1401e597c  movups  xmm1, [rsp+1E8h+var_B0]
0x1401e5984  movups  xmmword ptr [rcx+10h], xmm1
0x1401e5988  movups  xmm0, [rsp+1E8h+var_A0]
0x1401e5990  movups  xmmword ptr [rcx+20h], xmm0
0x1401e5994  mov     rax, [rsp+1E8h+var_148]
0x1401e599c  mov     [rax+20h], rcx
0x1401e59a0  mov     dword ptr [rax+10h], 30h ; '0'
0x1401e59a7  mov     [r14+30h], r13
0x1401e59ab  mov     [r14+10h], rbx
0x1401e59af  mov     [r14+38h], rsi
0x1401e59b3  mov     dword ptr [r14+40h], 0
0x1401e59bb  mov     dword ptr [r14+44h], 5
0x1401e59c3  cmp     byte ptr [rsp+1E8h+var_176], 0
0x1401e59c8  jz      short loc_1401E59D2
0x1401e59ca  mov     dword ptr [r14+44h], 7
0x1401e59d2  cmp     [r15+70h], r13
0x1401e59d6  jnz     short loc_1401E59EE
0x1401e59d8  mov     byte ptr [rsp+1E8h+Bcb], 1
0x1401e59dd  xor     r9d, r9d
0x1401e59e0  xor     r8d, r8d
0x1401e59e3  mov     rdx, r13
0x1401e59e6  mov     rcx, r15
0x1401e59e9  call    NtfsPrePostIrpInternal
0x1401e59ee  lea     rbx, [rsi+0A0h]
0x1401e59f5  lea     rcx, [rsi+78h]
0x1401e59f9  mov     rdx, rbx
0x1401e59fc  call    cs:__imp_FsRtlAcquireHeaderMutex
0x1401e5a03  nop     dword ptr [rax+rax+00h]
0x1401e5a08  mov     r9d, 1
0x1401e5a0e  mov     r8, r14
0x1401e5a11  lea     rdx, NtfsCancelReadUsnJournal
0x1401e5a18  mov     rcx, r13
0x1401e5a1b  call    NtfsSetCancelRoutine
0x1401e5a20  test    al, al
0x1401e5a22  jz      loc_1401E60C5
0x1401e5a28  lea     rax, [rsi+250h]
0x1401e5a2f  mov     rdx, [rax+8]
0x1401e5a33  cmp     [rdx], rax
0x1401e5a36  jz      loc_1401E622C
0x1401e5a3c  mov     ecx, 3
0x1401e5a41  int     29h; Win8: RtlFailFast(ecx)
0x1401e5a43  xor     bl, bl
0x1401e5a45  jmp     loc_1401E57B9
0x1401e5a4a  mov     rdx, r14
0x1401e5a4d  mov     rcx, r15
0x1401e5a50  call    NtfsReleaseVcb
0x1401e5a55  mov     byte ptr [rsp+1E8h+var_176+3], 0
0x1401e5a5a  jmp     loc_1401E5874
0x1401e5a5f  lea     rax, [r9+3]
0x1401e5a63  and     rax, 0FFFFFFFFFFFFFFFCh
0x1401e5a67  cmp     r9, rax
0x1401e5a6a  jz      loc_1401E575A
0x1401e5a70  mov     al, cs:NtfsStatusDebugFlags
0x1401e5a76  mov     edi, 0C000000Dh
0x1401e5a7b  test    al, al
0x1401e5a7d  jnz     loc_1401E618A
0x1401e5a83  mov     [rsp+1E8h+var_170], edi
0x1401e5a87  jmp     loc_1401E610D
0x1401e5a8c  cmp     r13, [r15+70h]
0x1401e5a90  jnz     loc_1401E5925
0x1401e5a96  mov     eax, 702h
0x1401e5a9b  cmp     ax, [rsi]
0x1401e5a9e  jz      loc_1401E648C
0x1401e5aa4  mov     rcx, [rsi+8]; Resource
0x1401e5aa8  call    cs:__imp_ExReleaseResourceLite
0x1401e5aaf  nop     dword ptr [rax+rax+00h]
0x1401e5ab4  mov     byte ptr [rsp+1E8h+var_176+1], 0
0x1401e5ab9  mov     rax, qword ptr [rsp+1E8h+var_B0]
0x1401e5ac1  neg     rax
0x1401e5ac4  sbb     r8, r8
0x1401e5ac7  lea     rax, [rsp+1E8h+var_B0]
0x1401e5acf  and     r8, rax; int
0x1401e5ad2  mov     rdx, qword ptr [rsp+1E8h+var_B0+8]
0x1401e5ada  add     rdx, qword ptr [rsp+1E8h+var_C0]; int
0x1401e5ae2  mov     [rsp+1E8h+var_1B8], r8; PLARGE_INTEGER
0x1401e5ae7  mov     [rsp+1E8h+Bcb], r13; __int64
0x1401e5aec  mov     r9b, byte ptr [rsp+1E8h+var_176]; int
0x1401e5af1  mov     rcx, rsi; int
0x1401e5af4  call    NtOfsWaitForNewLength
0x1401e5af9  mov     edi, eax
0x1401e5afb  mov     [rsp+1E8h+var_170], eax
0x1401e5aff  test    eax, eax
0x1401e5b01  jnz     loc_1401E64E4
0x1401e5b07  mov     eax, 702h
0x1401e5b0c  cmp     ax, [rsi]
0x1401e5b0f  mov     rcx, rsi
0x1401e5b12  jnz     loc_1401E6220
0x1401e5b18  mov     rcx, [rcx+68h]
0x1401e5b1c  add     rcx, rbx; Resource
0x1401e5b1f  mov     dl, 1; Wait
0x1401e5b21  call    cs:__imp_ExAcquireResourceSharedLite
0x1401e5b28  nop     dword ptr [rax+rax+00h]
0x1401e5b2d  mov     byte ptr [rsp+1E8h+var_176+1], 1
0x1401e5b32  lock dec dword ptr [rsi+0D4h]
0x1401e5b39  mov     byte ptr [rsp+1E8h+var_176+2], 0
0x1401e5b3e  mov     rax, [rsi+0C0h]
0x1401e5b45  cmp     rsi, [rax+28h]
0x1401e5b49  jnz     loc_1401E6498
0x1401e5b4f  mov     rdx, qword ptr [rsp+1E8h+var_C0]
0x1401e5b57  mov     eax, [rsp+1E8h+var_168]
0x1401e5b5e  test    eax, eax
0x1401e5b60  jz      loc_1401E612D
0x1401e5b66  mov     rbx, [rsi+20h]
0x1401e5b6a  cmp     rdx, rbx
0x1401e5b6d  jge     loc_1401E61EE
0x1401e5b73  mov     qword ptr [rsp+1E8h+FileOffset], 0
0x1401e5b7f  mov     [rsp+1E8h+var_16B], 0
0x1401e5b84  mov     [rsp+1E8h+var_100], 0
0x1401e5b90  sub     rbx, rdx
0x1401e5b93  mov     [rsp+1E8h+var_130], rbx
0x1401e5b9b  mov     ecx, edx
0x1401e5b9d  and     ecx, 3FFFFh
0x1401e5ba3  mov     eax, 40000h
0x1401e5ba8  sub     eax, ecx
  ... truncated ...
```
