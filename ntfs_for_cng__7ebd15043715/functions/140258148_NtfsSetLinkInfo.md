# NtfsSetLinkInfo

- ea: `0x140258148`
- end: `0x140259ea7`
- name: `NtfsSetLinkInfo`
- size: `7519`
- prototype: `__int64 __fastcall(__int64, IRP *, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `49`
- tags: `reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140202288`

## callees

- `0x140007ea0`
- `0x140009c80`
- `0x14000c290`
- `0x14000cb00`
- `0x14000d1e0`
- `0x14000d510`
- `0x14001ea30`
- `0x140021e60`
- `0x14003ebc4`
- `0x140047440`
- `0x140059250`
- `0x1400593c0`
- `0x1400596c0`
- `0x140059be0`
- `0x1400d2158`
- `0x1400d2654`
- `0x1400f400c`
- `0x14011e31c`
- `0x140121590`
- `0x140128d50`
- `0x14012baf8`
- `0x14012d150`
- `0x14012f930`
- `0x140140380`
- `0x14014a7d0`
- `0x14014b5a8`
- `0x14014bae0`
- `0x140154d10`
- `0x1401841d0`
- `0x140185788`
- `0x14018751c`
- `0x140187570`
- `0x14018bf40`
- `0x14018c610`
- `0x140190410`
- `0x140192470`
- `0x1401990f0`
- `0x14019b330`
- `0x14019f220`
- `0x1401eaf08`
- `0x1401fc460`
- `0x140204dac`
- `0x140221668`
- `0x140227518`
- `0x14022ce80`
- `0x140237294`
- `0x140258148`
- `0x14027369c`
- `0x14029f6d4`

## import_xrefs

- `ntoskrnl!SeCaptureSubjectContext` at `0x140258672`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140258672`
- `ntoskrnl!RtlIsNonEmptyDirectoryReparsePointAllowed` at `0x140258d7b`
- `ntoskrnl!RtlIsNonEmptyDirectoryReparsePointAllowed` at `0x140258d7b`
- `ntoskrnl!SeAuditingHardLinkEventsWithContext` at `0x1402599a2`
- `ntoskrnl!SeAuditingHardLinkEventsWithContext` at `0x1402599a2`
- `ntoskrnl!SeAuditHardLinkCreationWithTransaction` at `0x140259c76`
- `ntoskrnl!SeAuditHardLinkCreationWithTransaction` at `0x140259c76`
- `ntoskrnl!SeAuditHardLinkCreation` at `0x140259c97`
- `ntoskrnl!SeAuditHardLinkCreation` at `0x140259c97`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140259da1`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1402b94f1`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140259da1`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1402b94f1`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1402586ac`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1402586ac`
- `ntoskrnl!ExReleasePushLockEx` at `0x140259dbe`
- `ntoskrnl!ExReleasePushLockEx` at `0x1402b9511`
- `ntoskrnl!ExReleasePushLockEx` at `0x140259dbe`
- `ntoskrnl!ExReleasePushLockEx` at `0x1402b9511`
- `ntoskrnl!ExFreePoolWithTag` at `0x140259cb3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140259cce`
- `ntoskrnl!ExFreePoolWithTag` at `0x140259ce9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140259d4b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140259d61`
- `ntoskrnl!ExFreePoolWithTag` at `0x140259d7f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140259df3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b9417`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b9432`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b944d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b9495`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b94b0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b94cb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b9543`
- `ntoskrnl!ExFreePoolWithTag` at `0x140259cb3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140259cce`
- `ntoskrnl!ExFreePoolWithTag` at `0x140259ce9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140259d4b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140259d61`
- `ntoskrnl!ExFreePoolWithTag` at `0x140259d7f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140259df3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b9417`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b9432`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b944d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b9495`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b94b0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b94cb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b9543`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140258658`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140258f71`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140259029`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140259347`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140259a9e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140259b5f`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140258658`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140258f71`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140259029`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140259347`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140259a9e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140259b5f`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1402595cb`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1402595cb`
- `ntoskrnl!CcUnpinData` at `0x1402593ec`
- `ntoskrnl!CcUnpinData` at `0x1402593ec`
- `ntoskrnl!ExReleaseResourceLite` at `0x14025849e`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402596a7`
- `ntoskrnl!ExReleaseResourceLite` at `0x14025849e`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402596a7`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x140259908`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x140259908`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14025844a`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14025844a`
- `ntoskrnl!ExRaiseStatus` at `0x1402591d1`
- `ntoskrnl!ExRaiseStatus` at `0x1402591d1`

## pseudocode

```c
__int64 __fastcall NtfsSetLinkInfo(__int64 a1, IRP *a2, __int64 a3, __int64 a4, __int64 a5)
{
  __int64 v8; // r13
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbx
  __int64 v10; // rax
  __int64 v11; // rdi
  _BYTE *v12; // rcx
  int *v14; // rbx
  unsigned int v15; // r8d
  int v16; // eax
  __int64 v17; // rdx
  unsigned __int16 v18; // ax
  unsigned int v19; // r8d
  __int64 v20; // r12
  __int64 v21; // rcx
  int v22; // edi
  __int64 v23; // rcx
  __int64 v24; // rdx
  unsigned __int16 v25; // ax
  unsigned int v26; // edi
  IRP *v27; // rbx
  struct _SECURITY_SUBJECT_CONTEXT *PoolWithTag; // rax
  __int64 v29; // rax
  __int64 v30; // r12
  __int64 v31; // rbx
  _QWORD *v32; // rdi
  PGENERIC_MAPPING FileObjectGenericMapping; // rax
  __int64 v34; // rdx
  unsigned __int16 v35; // ax
  void *v36; // rbx
  __int64 v37; // rdx
  __int64 v38; // rax
  size_t v39; // rdi
  char *v40; // rbx
  __int64 v41; // r11
  __int64 v42; // r10
  unsigned int v43; // eax
  unsigned int v44; // r8d
  __int64 v45; // r11
  unsigned int v46; // eax
  unsigned __int16 v47; // dx
  __int64 v48; // r10
  __int64 v49; // r8
  _WORD *v50; // r12
  __int64 v51; // rdx
  unsigned int CurrentFileInfo; // eax
  int v53; // eax
  char v54; // al
  _QWORD *v55; // r12
  __int64 v56; // r13
  unsigned int v57; // edx
  __int16 v58; // r12
  __int64 v59; // rcx
  char *v60; // rax
  unsigned __int16 v61; // cx
  __int64 *Lcb; // rax
  unsigned int v63; // ecx
  __int16 v64; // r12
  __int64 v65; // rax
  char *v66; // rcx
  __int64 v67; // r12
  int v68; // ecx
  BOOL v69; // ecx
  BOOL v70; // ecx
  __int64 v71; // rax
  int v72; // edx
  __int64 v73; // rax
  __int64 v74; // rcx
  __int64 v75; // rax
  __int64 v76; // rax
  int v77; // edx
  int v78; // r8d
  PVOID v79; // r8
  _QWORD *v80; // rdx
  PVOID *v81; // r13
  unsigned __int16 v82; // ax
  unsigned int v83; // r12d
  unsigned int v84; // r8d
  size_t v85; // r13
  unsigned int v86; // r12d
  __int64 v87; // r8
  char *v88; // rcx
  __int64 v89; // rbx
  __int64 v90; // rax
  POPLOCK_WAIT_COMPLETE_ROUTINE CompletionRoutine; // [rsp+98h] [rbp-278h]
  POPLOCK_WAIT_COMPLETE_ROUTINE CompletionRoutinea; // [rsp+98h] [rbp-278h]
  POPLOCK_WAIT_COMPLETE_ROUTINE CompletionRoutineb; // [rsp+98h] [rbp-278h]
  PIRP v94; // [rsp+A8h] [rbp-268h]
  PIRP v95; // [rsp+A8h] [rbp-268h]
  __int64 v96; // [rsp+C8h] [rbp-248h]
  unsigned int v97; // [rsp+C8h] [rbp-248h]
  unsigned int v98; // [rsp+C8h] [rbp-248h]
  __int64 v99; // [rsp+D8h] [rbp-238h]
  char v100; // [rsp+F8h] [rbp-218h] BYREF
  char v101[3]; // [rsp+F9h] [rbp-217h] BYREF
  int v102; // [rsp+FCh] [rbp-214h]
  char v103; // [rsp+100h] [rbp-210h]
  char v104; // [rsp+101h] [rbp-20Fh]
  char *v105; // [rsp+108h] [rbp-208h]
  int v106; // [rsp+110h] [rbp-200h]
  unsigned int v107; // [rsp+114h] [rbp-1FCh] BYREF
  void *Buf1[2]; // [rsp+118h] [rbp-1F8h] BYREF
  PVOID Context[2]; // [rsp+128h] [rbp-1E8h] BYREF
  int v110[4]; // [rsp+138h] [rbp-1D8h]
  PVOID Bcb[2]; // [rsp+148h] [rbp-1C8h] BYREF
  __int64 v112; // [rsp+158h] [rbp-1B8h]
  int v113; // [rsp+160h] [rbp-1B0h]
  char v114; // [rsp+164h] [rbp-1ACh]
  __int16 v115; // [rsp+168h] [rbp-1A8h] BYREF
  PVOID v116; // [rsp+170h] [rbp-1A0h] BYREF
  unsigned int v117; // [rsp+178h] [rbp-198h] BYREF
  PIRP Irp; // [rsp+180h] [rbp-190h]
  __int64 v119; // [rsp+188h] [rbp-188h]
  struct _UNICODE_STRING LinkName; // [rsp+190h] [rbp-180h] BYREF
  struct _UNICODE_STRING FileName; // [rsp+1A0h] [rbp-170h] BYREF
  char *v122; // [rsp+1B0h] [rbp-160h]
  PVOID v123; // [rsp+1B8h] [rbp-158h]
  __int64 v124; // [rsp+1C0h] [rbp-150h] BYREF
  PVOID v125; // [rsp+1C8h] [rbp-148h]
  int v126; // [rsp+1D0h] [rbp-140h]
  __int64 v127[2]; // [rsp+1D8h] [rbp-138h] BYREF
  PVOID P[2]; // [rsp+1E8h] [rbp-128h] BYREF
  __int64 v129; // [rsp+1F8h] [rbp-118h]
  _QWORD *v130; // [rsp+200h] [rbp-110h]
  __int128 v131; // [rsp+208h] [rbp-108h] BYREF
  _QWORD *v132; // [rsp+218h] [rbp-F8h] BYREF
  char *v133; // [rsp+220h] [rbp-F0h]
  __int64 v134; // [rsp+228h] [rbp-E8h]
  __int64 v135; // [rsp+230h] [rbp-E0h]
  __int64 QuadPart; // [rsp+238h] [rbp-D8h]
  __int64 v137; // [rsp+240h] [rbp-D0h]
  __int64 v138; // [rsp+248h] [rbp-C8h]
  __int64 v139; // [rsp+250h] [rbp-C0h]
  _QWORD v140[14]; // [rsp+258h] [rbp-B8h] BYREF

  v119 = a4;
  Irp = a2;
  v139 = a1;
  v138 = a3;
  v8 = a5;
  v134 = a5;
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  *(_OWORD *)Buf1 = 0;
  v131 = 0;
  v116 = 0;
  v115 = 0;
  v100 = 0;
  P[0] = 0;
  *(_QWORD *)&LinkName.Length = 0;
  QuadPart = CurrentStackLocation->Parameters.Read.ByteOffset.QuadPart;
  *(_OWORD *)v127 = 0;
  v124 = 0;
  v132 = 0;
  *(_OWORD *)Context = 0;
  *(_OWORD *)v110 = 0;
  *(_OWORD *)Bcb = 0;
  v112 = 0;
  v10 = *(_QWORD *)(a1 + 400);
  v129 = v10;
  if ( v10 )
    v11 = *(_QWORD *)(v10 + 232);
  else
    v11 = 0;
  memset(v140, 0, sizeof(v140));
  v12 = *(_BYTE **)(*(_QWORD *)(a1 + 112) + 24LL);
  if ( CurrentStackLocation->Parameters.Create.Options == 11 )
  {
    v106 = *v12 != 0;
  }
  else
  {
    v106 = *(_DWORD *)v12;
    if ( (v106 & 0xFFFFFE04) != 0 )
    {
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(0, 0xC00000BB, 0xF328Fu);
      return 3221225659LL;
    }
  }
  Context[0] = (PVOID)a1;
  v14 = *(int **)(a4 + 184);
  Context[1] = v14;
  v123 = 0;
  v125 = 0;
  if ( (*(_DWORD *)(a5 + 4) & 2) == 0 )
  {
    if ( NtfsStatusDebugFlags )
    {
      v15 = 996004;
LABEL_52:
      NtfsStatusTraceAndDebugInternal(0, 0xC000000D, v15);
      return 3221225485LL;
    }
    return 3221225485LL;
  }
  v16 = v14[44];
  if ( (v16 & 0x10000000) == 0 && *(_BYTE *)(a5 + 88) == 2 )
  {
    if ( v16 < 0 )
    {
      if ( (*(_DWORD *)(a1 + 16) & 0x100000) == 0
        && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x20) != 0 )
      {
        v17 = *(_QWORD *)(a3 + 248);
        v18 = *(_WORD *)(v17 + 6);
        if ( v18 > 0x40u || (v18 & 1) != 0 )
          v18 = 0;
        v97 = *(unsigned __int16 *)(a5 + 16) >> 1;
        McTemplateU0ppwwpiw_EtwWriteTransfer(
          v97,
          (const EVENT_DESCRIPTOR *)fileinfo_c12986,
          KeGetCurrentThread(),
          a3,
          *(unsigned __int16 *)(a3 + 7872) >> 1,
          *(_QWORD *)(a3 + 7880),
          v18 >> 1,
          v17 + 32,
          v14,
          *((_QWORD *)v14 + 1),
          v97,
          *(_QWORD *)(a5 + 24));
      }
      if ( NtfsStatusDebugFlags )
      {
        v19 = 996039;
LABEL_43:
        v26 = -1073741790;
        NtfsStatusTraceAndDebugInternal(0, 0xC0000022, v19);
        return v26;
      }
      return (unsigned int)-1073741790;
    }
    v20 = *(_QWORD *)(a5 + 72);
    *(_QWORD *)&FileName.Length = v20;
    if ( !v20
      || (*(_DWORD *)(v20 + 4) & 1) != 0
      || (*(_BYTE *)(*(_QWORD *)(v20 + 192) + 65LL) & 3) != 0 && (*(_DWORD *)(*(_QWORD *)(v20 + 48) + 4LL) & 0x20) != 0 )
    {
      v21 = *((_QWORD *)v14 + 41);
      if ( v21 )
      {
        ExAcquireResourceSharedLite(*(PERESOURCE *)(v21 + 136), 1u);
        v14 = (int *)Context[1];
      }
      if ( !v11 )
        v11 = 1;
      v22 = TxfLinksVisibleToTransaction(a1, (__int64)v14, v11, 0, 0);
      v14 = (int *)Context[1];
      v23 = *((_QWORD *)Context[1] + 41);
      if ( v23 )
      {
        ExReleaseResourceLite(*(PERESOURCE *)(v23 + 136));
        v14 = (int *)Context[1];
      }
      if ( !v22 )
      {
        if ( (*(_DWORD *)(a1 + 16) & 0x100000) == 0
          && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x20) != 0 )
        {
          v24 = *(_QWORD *)(a3 + 248);
          v25 = *(_WORD *)(v24 + 6);
          if ( v25 > 0x40u || (v25 & 1) != 0 )
            v25 = 0;
          v98 = *(unsigned __int16 *)(a5 + 16) >> 1;
          LODWORD(CompletionRoutine) = *(unsigned __int16 *)(a3 + 7872) >> 1;
          McTemplateU0ppwwpiwd_EtwWriteTransfer(
            v98,
            (const EVENT_DESCRIPTOR *)fileinfo_c13046,
            KeGetCurrentThread(),
            a3,
            CompletionRoutine,
            *(_QWORD *)(a3 + 7880),
            v25 >> 1,
            v24 + 32,
            *(_QWORD *)(v119 + 184),
            *(_QWORD *)(*(_QWORD *)(v119 + 184) + 8LL),
            v98,
            *(_QWORD *)(a5 + 24),
            0);
        }
        if ( NtfsStatusDebugFlags )
        {
          v19 = 996101;
          goto LABEL_43;
        }
        return (unsigned int)-1073741790;
      }
      if ( !QuadPart )
      {
        if ( NtfsStatusDebugFlags )
        {
          v15 = 996112;
          goto LABEL_52;
        }
        return 3221225485LL;
      }
    }
    if ( v20 )
      *(_QWORD *)&v110[2] = *(_QWORD *)(v20 + 24);
    if ( (v14[1] & 0x100) != 0 )
    {
      if ( NtfsStatusDebugFlags )
      {
        v15 = 996130;
        goto LABEL_52;
      }
      return 3221225485LL;
    }
    v27 = Irp;
    if ( !byte_140095AD2 && NtfsEffectiveMode((__int64)Irp) == 1 && (*(_WORD *)(a5 + 104) & 0x310) == 0 )
    {
      v117 = 0;
      v107 = 0;
      if ( (*(_DWORD *)(a1 + 12) & 0x20) == 0 )
      {
        PoolWithTag = (struct _SECURITY_SUBJECT_CONTEXT *)ExAllocatePoolWithTag(
                                                            (POOL_TYPE)(PoolType | 0x10),
                                                            0x20u,
                                                            0x4646744Eu);
        *(_QWORD *)(a1 + 208) = PoolWithTag;
        *(_DWORD *)(a1 + 12) |= 0x20u;
        SeCaptureSubjectContext(PoolWithTag);
      }
      v29 = *(_QWORD *)(a1 + 400);
      if ( v29 )
        v30 = *(_QWORD *)(v29 + 232);
      else
        v30 = 0;
      v31 = *(_QWORD *)(a1 + 208);
      v32 = *(_QWORD **)(v119 + 184);
      FileObjectGenericMapping = IoGetFileObjectGenericMapping();
      if ( !(unsigned __int8)TxfAccessCheck(
                               a1,
                               v30,
                               v32,
                               v31,
                               0,
                               0,
                               0x100u,
                               0,
                               0,
                               (unsigned __int64)FileObjectGenericMapping,
                               1,
                               (__int64)&v117,
                               0,
                               (__int64)&v107,
                               0) )
      {
        if ( NtfsTelemetryGuard(0x200u) )
          NtfsTelemetryHardLinkWithNoAccessFailed(a3);
        if ( (*(_DWORD *)(a1 + 16) & 0x100000) == 0
          && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x20) != 0 )
        {
          v34 = *(_QWORD *)(a3 + 248);
          v35 = *(_WORD *)(v34 + 6);
          if ( v35 > 0x40u || (v35 & 1) != 0 )
            v35 = 0;
          LODWORD(v99) = v107;
          LODWORD(v96) = *(unsigned __int16 *)(a5 + 16) >> 1;
          LODWORD(v94) = v35 >> 1;
          LODWORD(CompletionRoutinea) = *(unsigned __int16 *)(a3 + 7872) >> 1;
          McTemplateU0ppwwpiwd_EtwWriteTransfer(
            (unsigned int)v96,
            (const EVENT_DESCRIPTOR *)fileinfo_c13141,
            KeGetCurrentThread(),
            a3,
            CompletionRoutinea,
            *(_QWORD *)(a3 + 7880),
            v94,
            v34 + 32,
            *(_QWORD *)(v119 + 184),
            *(_QWORD *)(*(_QWORD *)(v119 + 184) + 8LL),
            v96,
            *(_QWORD *)(a5 + 24),
            v99);
        }
        if ( NtfsStatusDebugFlags )
        {
          v19 = 996195;
          goto LABEL_43;
        }
        return (unsigned int)-1073741790;
      }
      v20 = *(_QWORD *)&FileName.Length;
      v27 = Irp;
    }
    if ( (*(_DWORD *)(a1 + 12) & 1) == 0 )
      return NtfsPostRequest((char *)a1, v27, 0, 0);
    v102 = 0;
    v36 = 0;
    v105 = 0;
    v133 = 0;
    v104 = 10;
    v103 = 0;
    v130 = 0;
    v101[0] = 0;
    if ( (*(_DWORD *)(a5 + 4) & 8) == 0 && **(_WORD **)(a5 + 24) == 92 )
      BYTE1(Bcb[1]) |= 1u;
    *(_DWORD *)(a1 + 272) = *(_DWORD *)(a5 + 100);
    v37 = *(_QWORD *)(v119 + 184);
    v38 = *(_QWORD *)(v37 + 296);
    if ( v38 && *(_DWORD *)(v38 + 248) )
    {
      NtfsPostUsnChangeWithOverrideOption(a1, v37, 0x80000000, 0, 0, 0, 0);
      NtfsCheckpointCurrentTransaction(a1);
    }
    NtfsFindTargetElements(a1, QuadPart, *(__int64 *)&v110[2], P, &LinkName, (__int64)&v131, (__int64)Buf1);
    v39 = LOWORD(Buf1[0]);
    if ( LOWORD(Buf1[0]) > 0x1FEu || !NtfsIsFileNameValid((unsigned __int16 *)Buf1, 0) )
    {
      v26 = -1073741773;
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(0, 0xC0000033, 0xF33AAu);
      v102 = -1073741773;
      goto LABEL_274;
    }
    v40 = (char *)P[0];
    v41 = *((_QWORD *)P[0] + 23);
    if ( (*(_DWORD *)(v41 + 4) & 0x100) != 0 && P[0] != *(PVOID *)(a3 + 32) )
    {
      if ( (*(_DWORD *)(a1 + 16) & 0x100000) == 0
        && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x20) != 0 )
      {
        v42 = *(_QWORD *)(a3 + 248);
        v43 = *(unsigned __int16 *)(v42 + 6);
        if ( v43 > 0x40 || (v43 & 1) != 0 )
          v43 = 0;
        v117 = v43;
        LOWORD(QuadPart) = v43;
        v137 = v42 + 32;
        LODWORD(v96) = (unsigned int)v39 >> 1;
        LODWORD(v95) = (unsigned __int16)v43 >> 1;
        LODWORD(CompletionRoutineb) = *(unsigned __int16 *)(a3 + 7872) >> 1;
        McTemplateU0ppwwpiw_EtwWriteTransfer(
          (unsigned int)v39 >> 1,
          (const EVENT_DESCRIPTOR *)fileinfo_c13237,
          KeGetCurrentThread(),
          a3,
          CompletionRoutineb,
          *(_QWORD *)(a3 + 7880),
          v95,
          v42 + 32,
          v41,
          *(_QWORD *)(v41 + 8),
          v96,
          Buf1[1]);
      }
      v26 = -1073741790;
      if ( !NtfsStatusDebugFlags )
        goto LABEL_97;
      v44 = 996290;
      goto LABEL_96;
    }
    if ( *(int *)(v41 + 176) < 0
      && (_InterlockedCompareExchange((volatile signed __int32 *)(*(_QWORD *)(v41 + 320) + 132LL), 4, 4)
       || (int)TxfConvertMungedNameToTxfFileId(0, (__int64)Buf1, 0) < 0) )
    {
      if ( (*(_DWORD *)(a1 + 16) & 0x100000) == 0
        && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x20) != 0 )
      {
        v45 = *(_QWORD *)(a3 + 248);
        v46 = *(unsigned __int16 *)(v45 + 6);
        if ( v46 > 0x40 || (v46 & 1) != 0 )
        {
          v47 = 0;
          v106 = 0;
        }
        else
        {
          v47 = *(_WORD *)(v45 + 6);
          v106 = v47;
        }
        LOWORD(v134) = v47;
        v135 = v45 + 32;
        v48 = *((_QWORD *)v40 + 23);
        LODWORD(v99) = *(_DWORD *)(*(_QWORD *)(v48 + 320) + 132LL);
        LODWORD(v96) = (unsigned int)v39 >> 1;
        LODWORD(v95) = v47 >> 1;
        LODWORD(CompletionRoutineb) = *(unsigned __int16 *)(a3 + 7872) >> 1;
        McTemplateU0ppwwpiwd_EtwWriteTransfer(
          (unsigned int)v39 >> 1,
          (const EVENT_DESCRIPTOR *)fileinfo_c13263,
          KeGetCurrentThread(),
          a3,
          CompletionRoutineb,
          *(_QWORD *)(a3 + 7880),
          v95,
          v45 + 32,
          v48,
          *(_QWORD *)(v48 + 8),
          v96,
          Buf1[1],
          v99);
      }
      v26 = -1073741790;
      if ( !NtfsStatusDebugFlags )
        goto LABEL_97;
      v44 = 996317;
      goto LABEL_96;
    }
    if ( (*(_DWORD *)(a1 + 12) & 0x100) != 0 )
    {
      NtfsAcquireExclusiveScbEx(a1, (__int64)v40, 0);
    }
    else
    {
      if ( !NtfsAcquireExclusiveFcb(a1, *((_QWORD *)v40 + 23), (__int64)v40, 66) )
      {
        *(_DWORD *)(a1 + 12) |= 0x100u;
        NtfsRaiseStatusInternal(a1, -1073741608, 0, 0, 996342);
      }
      if ( (*((_DWORD *)v40 + 50) & 0x200) != 0 )
        NtfsSnapshotScb(a1, (__int64)v40);
    }
    v49 = *((_QWORD *)v40 + 23);
    if ( !*(_WORD *)(v49 + 188) )
    {
      v26 = -1073741738;
      if ( !NtfsStatusDebugFlags )
        goto LABEL_97;
      v44 = 996372;
LABEL_96:
      NtfsStatusTraceAndDebugInternal(0, v26, v44);
LABEL_97:
      v102 = v26;
LABEL_273:
      v36 = v105;
LABEL_274:
      NtfsRenameCleanup((__int64)Context);
      if ( v123 )
        ExFreePoolWithTag(v123, 0);
      if ( v36 )
        ExFreePoolWithTag(v36, 0);
      if ( v116 )
        ExFreePoolWithTag(v116, 0);
      if ( SLOBYTE(Bcb[1]) < 0 )
      {
        ExAcquirePushLockSharedEx(a3 + 656, 0);
        _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)v110 + 28LL));
        ExReleasePushLockEx(a3 + 656, 0);
      }
      if ( v130 == v140 && (_QWORD *)v140[3] != &v140[7] )
        ExFreePoolWithTag((PVOID)v140[3], 0);
      if ( v26 != 259 && ((__int64)Bcb[1] & 8) != 0 )
        NtfsTeardownStructures(a1, *(__int64 *)v110, 0, 0, 0);
      return v26;
    }
    if ( v129 )
    {
      if ( v40 == *(char **)&v110[2] )
        goto LABEL_122;
      TxfPrepareFileForTxfLogging(a1, *(void **)(a1 + 400), v49, 0, 0, 0, 1, 0);
    }
    if ( v40 != *(char **)&v110[2] )
    {
      BYTE2(Bcb[1]) |= 0x10u;
      v51 = *((_QWORD *)v40 + 23);
      if ( (*(_DWORD *)(v51 + 176) & 0x400) != 0 )
      {
        CurrentFileInfo = TxfGetCurrentFileInfo(a1, v51, 0, 0, 0);
        if ( !(unsigned __int8)RtlIsNonEmptyDirectoryReparsePointAllowed(CurrentFileInfo) )
        {
          v26 = -1073741183;
          if ( !NtfsStatusDebugFlags )
            goto LABEL_97;
          v44 = 996458;
          goto LABEL_96;
        }
      }
      goto LABEL_127;
    }
LABEL_122:
    if ( (_WORD)v39 == *(_WORD *)(v20 + 72) && !memcmp(Buf1[1], *(const void **)(v20 + 80), v39) )
    {
      if ( (v106 & 1) == 0 )
      {
        v26 = -1073741771;
        if ( !NtfsStatusDebugFlags )
          goto LABEL_97;
        v44 = 996427;
        goto LABEL_96;
      }
      goto LABEL_148;
    }
LABEL_127:
    v50 = v40 + 656;
    if ( !*((_WORD *)v40 + 328) )
      NtfsBuildNormalizedNameWithTxfIsolation(a1, *((_QWORD *)v40 + 23), (__int64)v40, 0, 0, 0, (_QWORD *)v40 + 82);
    if ( !NtfsAllowMaximumSupportedHardLinks && *((_WORD *)Context[1] + 95) >= 0x400u )
    {
      v26 = -1073741211;
      if ( !NtfsStatusDebugFlags )
        goto LABEL_97;
      v44 = 996481;
      goto LABEL_96;
    }
    v53 = *(_DWORD *)(a5 + 4);
    LOBYTE(v49) = (v53 & 1) != 0 && ((v53 & 0x4000000) != 0 || (*(_DWORD *)(*((_QWORD *)v40 + 23) + 16LL) & 0x400) == 0);
    v54 = NtfsLookupEntry(
            a1,
            (__int64)v40,
            v49,
            (unsigned __int16 *)Buf1,
            &v116,
            &v115,
            0,
            (__int64)&v132,
            (__int64)Bcb,
            0);
    LOBYTE(Bcb[1]) = (__int64)Bcb[1] & 0xDF | (32 * (v54 & 1));
    v26 = TxfCheckTargetForRename(a1, (__int64)Buf1, (__int64)v40);
    v102 = v26;
    if ( v26 )
      goto LABEL_273;
    if ( ((__int64)Bcb[1] & 0x20) != 0 )
    {
      if ( (v106 & 1) == 0 )
      {
        v26 = -1073741771;
        if ( !NtfsStatusDebugFlags )
          goto LABEL_97;
        v44 = 996543;
        goto LABEL_96;
      }
      v55 = v132;
      v56 = (__int64)(v132 + 2);
      if ( NtfsCheckLinkForNewLink(
             (__int64)Context[1],
             (__int64)(v132 + 2),
             *v132,
             (const void **)Buf1,
             (__int64)&Bcb[1]) )
      {
LABEL_148:
        v26 = 0;
        v102 = 0;
        goto LABEL_273;
      }
      v104 = *(_BYTE *)(v56 + 65);
      v114 = v104;
      if ( (BYTE1(Bcb[1]) & 1) != 0 )
      {
        v57 = *(unsigned __int16 *)(*(_QWORD *)&v110[2] + 656LL) + LOWORD(Buf1[0]) + 2;
        if ( v57 > 0xFFFE )
        {
          v26 = -1073741562;
          if ( !NtfsStatusDebugFlags )
            goto LABEL_97;
          v44 = 996614;
          goto LABEL_96;
        }
        v58 = *(_WORD *)(*(_QWORD *)&v110[2] + 656LL) + LOWORD(Buf1[0]) + 2;
        LOWORD(v124) = v58;
        WORD1(v124) = v57;
        v123 = ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), (unsigned __int16)v57, 0x4646744Eu);
        v125 = v123;
        memmove(v123, *(const void **)(*(_QWORD *)&v110[2] + 664LL), *(unsigned __int16 *)(*(_QWORD *)&v110[2] + 656LL));
        v59 = *(unsigned __int16 *)(*(_QWORD *)&v110[2] + 656LL);
        v60 = (char *)v123 + v59;
        v122 = (char *)v123 + v59;
        if ( (_WORD)v59 == 2 )
        {
          LOWORD(v124) = v58 - 2;
        }
        else
        {
          *(_WORD *)v60 = 92;
          v60 += 2;
          v122 = v60;
        }
        v127[1] = (__int64)v60;
        v55 = v132;
        v61 = (unsigned __int16)Buf1[0];
      }
      else
      {
        v60 = (char *)ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), LOWORD(Buf1[0]), 0x4646744Eu);
        v123 = v60;
        v127[1] = (__int64)v60;
        v125 = v60;
        v61 = (unsigned __int16)Buf1[0];
        WORD1(v127[0]) = Buf1[0];
        LOWORD(v124) = Buf1[0];
      }
      WORD1(v127[0]) = v61;
      LOWORD(v127[0]) = v61;
      memmove(v60, (const void *)(v56 + 66), v61);
      if ( (BYTE1(Bcb[1]) & 2) != 0 )
      {
        if ( v129 )
        {
          v101[0] = 1;
          v103 = 1;
          Lcb = NtfsCreateLcb(
                  a1,
                  (__int64)v40,
                  (__int64)Context[1],
                  (const void **)v127,
                  *(_BYTE *)(v56 + 65),
                  (__int64)v101);
          v26 = TxfPrepareFileForPotentialTxLinkDelete(a1, Lcb);
          v102 = v26;
          if ( (v26 & 0x80000000) != 0 )
          {
            if ( NtfsStatusDebugFlags
              && v26 < 0xFFFFFFED
              && v26 != -1073741802
              && v26 + 2147483643 > 1
              && v26 != -1073741807
              && v26 != -1073741608 )
            {
              NtfsStatusTraceAndDebugInternal(a1, v26, 0xF3579u);
            }
            ExRaiseStatus(v26);
          }
          v130 = v140;
          v140[1] = &v140[4];
          v140[3] = &v140[7];
          LODWORD(v140[0]) = 1572864;
          LODWORD(v140[2]) = 3407872;
          v101[0] = *(_BYTE *)(*(_QWORD *)(*(_QWORD *)&FileName.Length + 192LL) + 65LL);
          TxfRemoveLink(a1, (__int64)Context[1], *(__int64 *)&FileName.Length, v140, 0);
        }
        else
        {
          NtfsRemoveLink(a1, (__int64)Context[1], (__int64)v40, (const void **)v127, 0, 0);
          ++WORD2(Bcb[1]);
        }
        *((_DWORD *)Context[1] + 1) &= ~0x4000u;
        *(PVOID *)v110 = Context[1];
      }
      else
      {
        v26 = NtfsRemoveSupersededTarget(
                (CLFS_LSN *)a1,
                v129,
                (__int64)v40,
                v55,
                v56,
                (_DWORD *)Context[1],
                Irp,
                v134,
                (v106 & 2) != 0,
                (v106 & 0x40) != 0,
                (const void **)v127,
                (__int64)Context);
        v102 = v26;
        if ( v26 )
          goto LABEL_273;
      }
      v50 = v40 + 656;
      v8 = v134;
    }
    if ( *(_QWORD *)&LinkName.Length && (*(_DWORD *)(*(_QWORD *)&LinkName.Length + 4LL) & 8) != 0
      || (BYTE1(Bcb[1]) & 1) != 0 && !*((_QWORD *)&v131 + 1) )
    {
      v63 = (unsigned __int16)*v50 + LOWORD(Buf1[0]) + 2;
      if ( v63 > 0xFFFE )
      {
        v26 = -1073741562;
        if ( !NtfsStatusDebugFlags )
          goto LABEL_97;
        v44 = 996788;
        goto LABEL_96;
      }
      v64 = *v50 + LOWORD(Buf1[0]) + 2;
      LOWORD(v131) = v63;
      WORD1(v131) = v63;
      v105 = (char *)ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), (unsigned __int16)v63, 0x4646744Eu);
      *((_QWORD *)&v131 + 1) = v105;
      v133 = v105;
      memmove(v105, *((const void **)v40 + 83), *((unsigned __int16 *)v40 + 328));
      v65 = *((unsigned __int16 *)v40 + 328);
      v66 = &v105[v65];
      v122 = &v105[v65];
      if ( (_WORD)v65 == 2 )
      {
        LOWORD(v131) = v64 - 2;
      }
      else
      {
        *(_WORD *)v66 = 92;
        v66 += 2;
        v122 = v66;
      }
      memmove(v66, Buf1[1], LOWORD(Buf1[0]));
    }
    if ( Bcb[0] )
    {
      CcUnpinData(Bcb[0]);
      Bcb[0] = 0;
    }
    NtfsCheckIndexForAddOrDelete(a1, (__int64)Irp, *((_QWORD *)v40 + 23), 2u, v8);
    v67 = v119;
    NtfsUpdateFileTimestampsForChange(*(_QWORD *)(v119 + 184), v8, 0x400000);
    NtfsAddLink(a1, 0, 0, (__int64)v40, (__int64)Context[1], (__int64)v116, 0, &v100, 0, 0, 0, 0);
    if ( v129 )
    {
      v68 = *(_DWORD *)(v8 + 4);
      if ( v103 )
      {
        v70 = (v68 & 1) != 0 && ((v68 & 0x4000000) != 0 || (*(_DWORD *)(*((_QWORD *)v40 + 23) + 16LL) & 0x400) == 0);
        TxfAddLinkForRename(
          (CLFS_LSN *)a1,
          *(_QWORD **)&v110[2],
          v40,
          (__int64)v116,
          v101[0],
          v100,
          (__int64)v130,
          0,
          0,
          v70,
          (__int64)Context[1]);
      }
      else
      {
        v69 = (v68 & 1) != 0 && ((v68 & 0x4000000) != 0 || (*(_DWORD *)(*((_QWORD *)v40 + 23) + 16LL) & 0x400) == 0);
        TxfAddHardLink(a1, (__int64)v40, (__int64)v116, v100, 0, 0, v69, (__int64)Context[1]);
      }
    }
    if ( v40 != *(char **)&v110[2]
      && *(_BYTE *)(*((_QWORD *)v40 + 23) + 38LL) != *((_BYTE *)Context[1] + 38)
      && (v106 & 8) == 0 )
    {
      ExAcquireResourceExclusiveLite((PERESOURCE)(a3 + 10688), 1u);
      BYTE2(Bcb[1]) |= 0x40u;
      v71 = *((unsigned __int8 *)Context[1] + 38);
      v72 = 0;
      if ( !(_BYTE)v71 || (v73 = *(_QWORD *)(a3 + 8 * v71 + 10904)) == 0 || (*(_DWORD *)(v73 + 4) & 0x40) == 0 )
      {
        v74 = *((_QWORD *)v40 + 23);
        v75 = *(unsigned __int8 *)(v74 + 38);
        if ( !(_BYTE)v75 || (v76 = *(_QWORD *)(a3 + 8 * v75 + 10904)) == 0 || (*(_DWORD *)(v76 + 4) & 0x80u) == 0 )
        {
          v113 = 0;
          if ( (v106 & 0x10) != 0 )
            v72 = 1;
          v113 = v72;
          if ( (v106 & 0x20) != 0 )
          {
            v72 |= 2u;
            v113 = v72;
          }
          if ( (v106 & 0x80u) != 0 )
          {
            v72 |= 4u;
            v113 = v72;
          }
          if ( (v106 & 0x100) != 0 )
          {
            v72 |= 8u;
            v113 = v72;
          }
          v26 = NtfsChangeStorageReserveId(
                  a1,
                  (__int64)Irp,
                  (__int64)Context[1],
                  v8,
                  *(unsigned __int8 *)(v74 + 38),
                  v72);
          v102 = v26;
          if ( v26 )
            goto LABEL_273;
        }
      }
      ExReleaseResourceLite((PERESOURCE)(a3 + 10688));
      BYTE2(Bcb[1]) &= ~0x40u;
      v67 = v119;
    }
    --WORD2(Bcb[1]);
    NtfsUpdateFcbTimestamps(*((_QWORD *)v40 + 23), -1610612720);
    if ( (BYTE1(Bcb[1]) & 2) != 0 )
      NtfsReplaceLinkInDir(a1, (int)v40, (__int64)Context[1], (int)Buf1, v100, (__int64)v127, v104);
    if ( NtfsTelemetryGuard(0x200u) )
      NtfsTelemetryHardLink(a3, Buf1, QuadPart, 0);
    if ( (BYTE1(Bcb[1]) & 1) == 0 )
    {
LABEL_235:
      if ( (*(_DWORD *)(a3 + 4) & 0x80000) != 0 )
      {
        v79 = v116;
        if ( (*((_BYTE *)v116 + 65) & 3) == 2 )
          v79 = 0;
        NtfsPostUsnChangeWithOverrideOption(a1, v67, -2147418112, 0, 0, 0, (__int64)v79);
        if ( *(_QWORD *)(a1 + 240) )
        {
          NtfsCheckpointCurrentTransaction(a1);
          *(_DWORD *)(*(_QWORD *)(v67 + 184) + 4LL) &= ~0x4000u;
        }
      }
      FsRtlCheckOplockEx((POPLOCK)v40 + 11, Irp, 0x10u, 0, 0, 0);
      *((_WORD *)Context[1] + 95) -= WORD2(Bcb[1]);
      *((_WORD *)Context[1] + 94) -= WORD2(Bcb[1]);
      if ( *(_QWORD *)v110 && !*(_WORD *)(*(_QWORD *)v110 + 188LL) && *(_QWORD *)(*(_QWORD *)v110 + 120LL) )
        NtfsDereferenceQuotaControlBlock(a3, (PVOID **)(*(_QWORD *)v110 + 120LL), 0);
      v80 = Context[1];
      if ( !*((_QWORD *)Context[1] + 26) )
      {
        NtfsLoadSecurityDescriptor(a1, (__int64)Context[1]);
        v80 = Context[1];
      }
      if ( !SeAuditingHardLinkEventsWithContext(1u, (PSECURITY_DESCRIPTOR)(v80[26] + 28LL), 0) )
        goto LABEL_273;
      P[0] = 0;
      *(_QWORD *)&FileName.Length = 0;
      *(_QWORD *)&LinkName.Length = 0;
      v107 = 0;
      P[1] = 0;
      FileName.Buffer = 0;
      LinkName.Buffer = 0;
      v81 = (PVOID *)(v8 + 16);
      v82 = *(_WORD *)v81;
      if ( !*(_WORD *)v81 )
      {
        NtfsBuildNormalizedNameWithTxfIsolation(a1, *(_QWORD *)(v67 + 184), 0, 0, 0, 0, P);
        v81 = P;
        v82 = (unsigned __int16)P[0];
      }
      v83 = v82 + *(unsigned __int16 *)(a3 + 7856);
      v107 = v83;
      if ( v83 <= 0xFFFE )
      {
        FileName.Buffer = (PWSTR)ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), v83, 0x4646744Eu);
        FileName.MaximumLength = v83;
        FileName.Length = v83;
        memmove(FileName.Buffer, *(const void **)(a3 + 7864), *(unsigned __int16 *)(a3 + 7856));
        memmove((char *)FileName.Buffer + *(unsigned __int16 *)(a3 + 7856), v81[1], *(unsigned __int16 *)v81);
        v85 = LOWORD(Buf1[0]);
        v86 = LOWORD(Buf1[0]) + *((unsigned __int16 *)v40 + 328) + *(unsigned __int16 *)(a3 + 7856) + 2;
        v107 = v86;
        if ( v86 <= 0xFFFE )
        {
          LinkName.Buffer = (PWSTR)ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), v86, 0x4646744Eu);
          LinkName.MaximumLength = v86;
          LinkName.Length = v86;
          memmove(LinkName.Buffer, *(const void **)(a3 + 7864), *(unsigned __int16 *)(a3 + 7856));
          memmove(
            (char *)LinkName.Buffer + *(unsigned __int16 *)(a3 + 7856),
            *((const void **)v40 + 83),
            *((unsigned __int16 *)v40 + 328));
          v87 = *((unsigned __int16 *)v40 + 328);
          v88 = (char *)LinkName.Buffer + v87 + *(unsigned __int16 *)(a3 + 7856);
          v122 = v88;
          if ( (_WORD)v87 == 2 )
          {
            LinkName.Length -= 2;
          }
          else
          {
            *(_WORD *)v88 = 92;
            v88 += 2;
            v122 = v88;
          }
          memmove(v88, Buf1[1], v85);
          v89 = v119;
          v90 = *(_QWORD *)(v119 + 528);
          if ( v90 && *(_QWORD *)(*(_QWORD *)(v90 + 64) + 24LL) )
          {
            TxfSetupTransactionForAuditing();
            SeAuditHardLinkCreationWithTransaction(
              &FileName,
              &LinkName,
              1u,
              (GUID *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v89 + 528) + 64LL) + 24LL) + 256LL));
          }
          else
          {
            SeAuditHardLinkCreation(&FileName, &LinkName, 1u);
          }
          goto LABEL_264;
        }
        v26 = -1073741562;
        if ( NtfsStatusDebugFlags )
        {
          v84 = 997214;
          goto LABEL_252;
        }
      }
      else
      {
        v26 = -1073741562;
        if ( NtfsStatusDebugFlags )
        {
          v84 = 997201;
LABEL_252:
          NtfsStatusTraceAndDebugInternal(0, 0xC0000106, v84);
        }
      }
      v102 = -1073741562;
LABEL_264:
      if ( P[1] )
        ExFreePoolWithTag(P[1], 0);
      if ( LinkName.Buffer )
        ExFreePoolWithTag(LinkName.Buffer, 0);
      if ( FileName.Buffer )
        ExFreePoolWithTag(FileName.Buffer, 0);
      goto LABEL_273;
    }
    v77 = 0;
    v126 = 0;
    if ( (BYTE1(Bcb[1]) & 4) != 0 )
    {
      v78 = 0;
      if ( (BYTE1(Bcb[1]) & 2) != 0 )
        goto LABEL_233;
      v77 = 508;
      v78 = 3;
    }
    else
    {
      if ( ((__int64)Bcb[1] & 0x20) != 0 )
      {
        NtfsReportDirNotify(
          a1,
          (__int64)v40,
          a3,
          (unsigned __int16 *)&v124,
          (unsigned __int16)v124 - LOWORD(v127[0]),
          0,
          ((*(_DWORD *)(*(_QWORD *)v110 + 176LL) & 0x10000000) != 0) + 1,
          2,
          *((_QWORD *)v40 + 23),
          *(__int64 *)v110);
        v123 = v125;
      }
      v77 = 1;
      v78 = 1;
    }
    v126 = v77;
LABEL_233:
    if ( v77 )
      NtfsReportDirNotify(
        a1,
        (__int64)v40,
        a3,
        (unsigned __int16 *)&v131,
        (unsigned __int16)v131 - LOWORD(Buf1[0]),
        0,
        v77,
        v78,
        *((_QWORD *)v40 + 23),
        (__int64)Context[1]);
    goto LABEL_235;
  }
  if ( NtfsStatusDebugFlags )
    NtfsStatusTraceAndDebugInternal(0, 0xC00000BA, 0xF32B1u);
  return 3221225658LL;
}

```

## disassembly

```asm
0x140258148  mov     r11, rsp
0x14025814b  push    rbx
0x14025814c  push    rsi
0x14025814d  push    rdi
0x14025814e  push    r12
0x140258150  push    r13
0x140258152  push    r14
0x140258154  push    r15
0x140258156  sub     rsp, 260h
0x14025815d  mov     rax, cs:__security_cookie
0x140258164  xor     rax, rsp
0x140258167  mov     [rsp+298h+var_48], rax
0x14025816f  mov     r14, r9
0x140258172  mov     [rsp+298h+var_188], r9
0x14025817a  mov     r15, r8
0x14025817d  mov     [rsp+298h+Irp], rdx
0x140258185  mov     rsi, rcx
0x140258188  mov     [rsp+298h+var_C0], rcx
0x140258190  mov     [rsp+298h+var_C8], r8
0x140258198  mov     r13, [rsp+298h+arg_20]
0x1402581a0  mov     [rsp+298h+var_E8], r13
0x1402581a8  mov     rbx, [rdx+0B8h]
0x1402581af  xorps   xmm0, xmm0
0x1402581b2  movups  xmmword ptr [rsp+298h+Buf1], xmm0
0x1402581ba  xorps   xmm1, xmm1
0x1402581bd  movups  [rsp+298h+var_108], xmm1
0x1402581c5  xor     r12d, r12d
0x1402581c8  mov     [r11-1A0h], r12
0x1402581cf  mov     [r11-1A8h], r12w
0x1402581d7  mov     [r11-218h], r12b
0x1402581de  mov     [r11-128h], r12
0x1402581e5  mov     [r11-180h], r12
0x1402581ec  mov     rax, [rbx+18h]
0x1402581f0  mov     [rsp+298h+var_D8], rax
0x1402581f8  movups  xmmword ptr [rsp+298h+var_138], xmm0
0x140258200  mov     [r11-150h], r12
0x140258207  mov     [r11-0F8h], r12
0x14025820e  xor     eax, eax
0x140258210  movups  xmmword ptr [rsp+298h+Context], xmm0
0x140258218  movups  xmmword ptr [rsp+298h+var_1D8], xmm0
0x140258220  movups  xmmword ptr [rsp+298h+Bcb], xmm0
0x140258228  mov     [r11-1B8h], rax
0x14025822f  mov     rax, [rcx+190h]
0x140258236  mov     [rsp+298h+var_118], rax
0x14025823e  test    rax, rax
0x140258241  jz      short loc_14025824C
0x140258243  mov     rdi, [rax+0E8h]
0x14025824a  jmp     short loc_14025824F
0x14025824c  mov     rdi, r12
0x14025824f  xor     edx, edx; Val
0x140258251  lea     r8d, [rdx+70h]; Size
0x140258255  lea     rcx, [rsp+298h+var_B8]; void *
0x14025825d  call    memset
0x140258262  mov     rax, [rsi+70h]
0x140258266  mov     rcx, [rax+18h]
0x14025826a  cmp     dword ptr [rbx+10h], 0Bh
0x14025826e  jnz     short loc_140258285
0x140258270  xor     r8d, r8d
0x140258273  mov     edx, r8d
0x140258276  cmp     [rcx], r8b
0x140258279  setnz   dl
0x14025827c  mov     [rsp+298h+var_200], edx
0x140258283  jmp     short loc_1402582BE
0x140258285  mov     eax, [rcx]
0x140258287  mov     [rsp+298h+var_200], eax
0x14025828e  test    eax, 0FFFFFE04h
0x140258293  jz      short loc_1402582BB
0x140258295  mov     al, cs:NtfsStatusDebugFlags
0x14025829b  test    al, al
0x14025829d  jz      short loc_1402582B1
0x14025829f  mov     edx, 0C00000BBh
0x1402582a4  xor     ecx, ecx
0x1402582a6  mov     r8d, 0F328Fh
0x1402582ac  call    NtfsStatusTraceAndDebugInternal
0x1402582b1  mov     eax, 0C00000BBh
0x1402582b6  jmp     loc_140259E5A
0x1402582bb  xor     r8d, r8d
0x1402582be  mov     [rsp+298h+Context], rsi
0x1402582c6  mov     rbx, [r14+0B8h]
0x1402582cd  mov     [rsp+298h+Context+8], rbx
0x1402582d5  mov     rax, r8
0x1402582d8  mov     [rsp+298h+var_158], rax
0x1402582e0  mov     [rsp+298h+var_148], rax
0x1402582e8  mov     eax, [r13+4]
0x1402582ec  mov     ecx, 2
0x1402582f1  test    cl, al
0x1402582f3  jnz     short loc_14025830E
0x1402582f5  mov     al, cs:NtfsStatusDebugFlags
0x1402582fb  test    al, al
0x1402582fd  jz      loc_1402585EF
0x140258303  mov     r8d, 0F32A4h
0x140258309  jmp     loc_1402585E3
0x14025830e  mov     eax, [rbx+0B0h]
0x140258314  bt      eax, 1Ch
0x140258318  jb      loc_140259E39
0x14025831e  cmp     [r13+58h], cl
0x140258322  jnz     loc_140259E39
0x140258328  test    eax, eax
0x14025832a  jns     loc_1402583F0
0x140258330  mov     eax, [rsi+10h]
0x140258333  bt      rax, 14h
0x140258338  jb      loc_1402583D7
0x14025833e  mov     rax, cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits
0x140258345  test    al, 20h
0x140258347  jz      loc_1402583D7
0x14025834d  mov     rdx, [r15+0F8h]
0x140258354  movzx   eax, word ptr [rdx+6]
0x140258358  cmp     ax, 40h ; '@'
0x14025835c  ja      short loc_140258369
0x14025835e  mov     r14d, 1
0x140258364  test    r14b, al
0x140258367  jz      short loc_14025836C
0x140258369  mov     eax, r8d
0x14025836c  movzx   ecx, word ptr [r13+10h]
0x140258371  shr     ecx, 1
0x140258373  add     rdx, 20h ; ' '
0x140258377  movzx   r10d, ax
0x14025837b  shr     r10d, 1
0x14025837e  movzx   r11d, word ptr [r15+1EC0h]
0x140258386  shr     r11d, 1
0x140258389  mov     r8, gs:188h
0x140258392  mov     rax, [r13+18h]
0x140258396  mov     [rsp+298h+var_240], rax
0x14025839b  mov     dword ptr [rsp+298h+var_248], ecx
0x14025839f  mov     rax, [rbx+8]
0x1402583a3  mov     qword ptr [rsp+298h+var_250], rax
0x1402583a8  mov     qword ptr [rsp+298h+var_258], rbx
0x1402583ad  mov     qword ptr [rsp+298h+var_260], rdx
0x1402583b2  mov     dword ptr [rsp+298h+var_268], r10d
0x1402583b7  mov     rax, [r15+1EC8h]
0x1402583be  mov     [rsp+298h+PostIrpRoutine], rax
0x1402583c3  mov     dword ptr [rsp+298h+CompletionRoutine], r11d
0x1402583c8  mov     r9, r15
0x1402583cb  lea     rdx, fileinfo_c12986
0x1402583d2  call    McTemplateU0ppwwpiw_EtwWriteTransfer
0x1402583d7  mov     al, cs:NtfsStatusDebugFlags
0x1402583dd  test    al, al
0x1402583df  jz      loc_140258804
0x1402583e5  mov     r8d, 0F32C7h
0x1402583eb  jmp     loc_140258589
0x1402583f0  mov     r12, [r13+48h]
0x1402583f4  mov     qword ptr [rsp+298h+FileName.Length], r12
0x1402583fc  mov     r14d, 1
0x140258402  test    r12, r12
0x140258405  jz      short loc_140258434
0x140258407  mov     eax, [r12+4]
0x14025840c  test    r14b, al
0x14025840f  jnz     short loc_140258434
0x140258411  mov     rax, [r12+0C0h]
0x140258419  test    byte ptr [rax+41h], 3
0x14025841d  jz      loc_1402585B8
0x140258423  mov     rax, [r12+30h]
0x140258428  mov     ecx, [rax+4]
0x14025842b  test    cl, 20h
0x14025842e  jz      loc_1402585B8
0x140258434  mov     rcx, [rbx+148h]
0x14025843b  test    rcx, rcx
0x14025843e  jz      short loc_140258461
0x140258440  mov     dl, r14b; Wait
0x140258443  mov     rcx, [rcx+88h]; Resource
0x14025844a  call    cs:__imp_ExAcquireResourceSharedLite
0x140258451  nop     dword ptr [rax+rax+00h]
0x140258456  mov     rbx, [rsp+298h+Context+8]
0x14025845e  xor     r8d, r8d
0x140258461  test    rdi, rdi
0x140258464  cmovz   rdi, r14
0x140258468  mov     byte ptr [rsp+298h+CompletionRoutine], r8b
0x14025846d  xor     r9d, r9d
0x140258470  mov     r8, rdi
0x140258473  mov     rdx, rbx
0x140258476  mov     rcx, rsi
0x140258479  call    TxfLinksVisibleToTransaction
0x14025847e  mov     edi, eax
0x140258480  mov     rbx, [rsp+298h+Context+8]
0x140258488  mov     rcx, [rbx+148h]
0x14025848f  xor     r8d, r8d
0x140258492  test    rcx, rcx
0x140258495  jz      short loc_1402584B5
0x140258497  mov     rcx, [rcx+88h]; Resource
0x14025849e  call    cs:__imp_ExReleaseResourceLite
0x1402584a5  nop     dword ptr [rax+rax+00h]
0x1402584aa  mov     rbx, [rsp+298h+Context+8]
0x1402584b2  xor     r8d, r8d
0x1402584b5  test    edi, edi
0x1402584b7  jnz     loc_14025859C
0x1402584bd  mov     eax, [rsi+10h]
0x1402584c0  bt      rax, 14h
0x1402584c5  jb      loc_140258575
0x1402584cb  mov     rax, cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits
0x1402584d2  test    al, 20h
0x1402584d4  jz      loc_140258575
0x1402584da  mov     rdx, [r15+0F8h]
0x1402584e1  movzx   eax, word ptr [rdx+6]
0x1402584e5  cmp     ax, 40h ; '@'
0x1402584e9  ja      short loc_1402584F0
0x1402584eb  test    r14b, al
0x1402584ee  jz      short loc_1402584F3
0x1402584f0  mov     eax, r8d
0x1402584f3  mov     r11, [rsp+298h+var_188]
0x1402584fb  mov     r11, [r11+0B8h]
0x140258502  movzx   ecx, word ptr [r13+10h]
0x140258507  shr     ecx, 1
0x140258509  add     rdx, 20h ; ' '
0x14025850d  movzx   r9d, ax
0x140258511  shr     r9d, 1
0x140258514  movzx   r10d, word ptr [r15+1EC0h]
0x14025851c  shr     r10d, 1
0x14025851f  mov     r8, gs:188h
0x140258528  mov     dword ptr [rsp+298h+var_238], 0
0x140258530  mov     rax, [r13+18h]
0x140258534  mov     [rsp+298h+var_240], rax
0x140258539  mov     dword ptr [rsp+298h+var_248], ecx
0x14025853d  mov     rax, [r11+8]
0x140258541  mov     qword ptr [rsp+298h+var_250], rax
0x140258546  mov     qword ptr [rsp+298h+var_258], r11
0x14025854b  mov     qword ptr [rsp+298h+var_260], rdx
0x140258550  mov     dword ptr [rsp+298h+var_268], r9d
0x140258555  mov     rax, [r15+1EC8h]
0x14025855c  mov     [rsp+298h+PostIrpRoutine], rax
0x140258561  mov     dword ptr [rsp+298h+CompletionRoutine], r10d
0x140258566  mov     r9, r15
0x140258569  lea     rdx, fileinfo_c13046
0x140258570  call    McTemplateU0ppwwpiwd_EtwWriteTransfer
0x140258575  mov     al, cs:NtfsStatusDebugFlags
0x14025857b  test    al, al
0x14025857d  jz      loc_140258804
0x140258583  mov     r8d, 0F3305h
0x140258589  mov     edi, 0C0000022h
0x14025858e  mov     edx, edi
0x140258590  xor     ecx, ecx
0x140258592  call    NtfsStatusTraceAndDebugInternal
0x140258597  jmp     loc_140258809
0x14025859c  cmp     [rsp+298h+var_D8], r8
0x1402585a4  jnz     short loc_1402585B8
0x1402585a6  mov     al, cs:NtfsStatusDebugFlags
0x1402585ac  test    al, al
0x1402585ae  jz      short loc_1402585EF
0x1402585b0  mov     r8d, 0F3310h
0x1402585b6  jmp     short loc_1402585E3
0x1402585b8  test    r12, r12
0x1402585bb  jz      short loc_1402585CA
0x1402585bd  mov     rax, [r12+18h]
0x1402585c2  mov     qword ptr [rsp+298h+var_1D8+8], rax
0x1402585ca  test    dword ptr [rbx+4], 100h
0x1402585d1  jz      short loc_1402585F9
0x1402585d3  mov     al, cs:NtfsStatusDebugFlags
0x1402585d9  test    al, al
0x1402585db  jz      short loc_1402585EF
0x1402585dd  mov     r8d, 0F3322h
0x1402585e3  mov     edx, 0C000000Dh
0x1402585e8  xor     ecx, ecx
0x1402585ea  call    NtfsStatusTraceAndDebugInternal
0x1402585ef  mov     eax, 0C000000Dh
0x1402585f4  jmp     loc_140259E5A
0x1402585f9  mov     rbx, [rsp+298h+Irp]
0x140258601  cmp     cs:byte_140095AD2, 0
0x140258608  jnz     loc_140258825
0x14025860e  mov     rcx, rbx
0x140258611  call    NtfsEffectiveMode
0x140258616  cmp     al, r14b
0x140258619  jnz     loc_140258822
0x14025861f  mov     ecx, 310h
0x140258624  test    [r13+68h], cx
0x140258629  jnz     loc_140258822
0x14025862f  xor     ebx, ebx
0x140258631  mov     [rsp+298h+var_198], ebx
0x140258638  mov     [rsp+298h+var_1FC], ebx
0x14025863f  mov     eax, [rsi+0Ch]
0x140258642  test    al, 20h
0x140258644  jnz     short loc_14025867E
0x140258646  mov     ecx, cs:PoolType
0x14025864c  or      ecx, 10h; PoolType
0x14025864f  lea     edx, [rbx+20h]; NumberOfBytes
0x140258652  mov     r8d, 4646744Eh; Tag
0x140258658  call    cs:__imp_ExAllocatePoolWithTag
0x14025865f  nop     dword ptr [rax+rax+00h]
0x140258664  mov     [rsi+0D0h], rax
0x14025866b  or      dword ptr [rsi+0Ch], 20h
0x14025866f  mov     rcx, rax; SubjectContext
0x140258672  call    cs:__imp_SeCaptureSubjectContext
0x140258679  nop     dword ptr [rax+rax+00h]
0x14025867e  mov     rax, [rsi+190h]
0x140258685  test    rax, rax
0x140258688  jz      short loc_140258693
0x14025868a  mov     r12, [rax+0E8h]
0x140258691  jmp     short loc_140258696
0x140258693  mov     r12, rbx
0x140258696  mov     rbx, [rsi+0D0h]
0x14025869d  mov     rax, [rsp+298h+var_188]
0x1402586a5  mov     rdi, [rax+0B8h]
0x1402586ac  call    cs:__imp_IoGetFileObjectGenericMapping
0x1402586b3  nop     dword ptr [rax+rax+00h]
0x1402586b8  xor     edx, edx
0x1402586ba  mov     [rsp+298h+var_228], rdx
0x1402586bf  lea     rcx, [rsp+298h+var_1FC]
0x1402586c7  mov     [rsp+298h+var_230], rcx
0x1402586cc  mov     [rsp+298h+var_238], rdx
0x1402586d1  lea     rcx, [rsp+298h+var_198]
0x1402586d9  mov     [rsp+298h+var_240], rcx
0x1402586de  mov     byte ptr [rsp+298h+var_248], r14b
  ... truncated ...
```
