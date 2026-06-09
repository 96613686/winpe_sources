# NtfsSetLinkInfo

- ea: `0x140258148`
- end: `0x140259ea7`
- name: `NtfsSetLinkInfo`
- size: `7519`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, __int64)`
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
  __int64 v15; // r8
  int v16; // eax
  __int64 v17; // rdx
  unsigned __int16 v18; // ax
  __int64 v19; // r8
  __int64 v20; // r12
  __int64 v21; // rcx
  int v22; // edi
  __int64 v23; // rcx
  __int64 v24; // rdx
  unsigned __int16 v25; // ax
  unsigned int v26; // edi
  struct _SECURITY_SUBJECT_CONTEXT *PoolWithTag; // rax
  __int64 v28; // rax
  __int64 v29; // r12
  __int64 v30; // rbx
  __int64 v31; // rdi
  PGENERIC_MAPPING FileObjectGenericMapping; // rax
  __int64 v33; // rdx
  unsigned __int16 v34; // ax
  void *v35; // rbx
  __int64 v36; // rdx
  __int64 v37; // rax
  __int64 v38; // rdx
  __int64 v39; // r8
  size_t v40; // rdi
  char IsFileNameValid; // al
  __int64 v42; // r9
  char *v43; // rbx
  __int64 v44; // r11
  __int64 v45; // r10
  unsigned int v46; // eax
  __int64 v47; // r8
  int v48; // eax
  __int64 v49; // r11
  unsigned int v50; // eax
  unsigned __int16 v51; // dx
  _WORD *v52; // r12
  __int64 v53; // rdx
  unsigned int CurrentFileInfo; // eax
  int v55; // eax
  char v56; // al
  __int64 v57; // r13
  __int16 v58; // r12
  __int64 v59; // rcx
  char *v60; // rax
  unsigned __int16 v61; // cx
  unsigned int v62; // ecx
  __int16 v63; // r12
  __int64 v64; // rax
  char *v65; // rcx
  __int64 v66; // r12
  int v67; // ecx
  BOOL v68; // ecx
  BOOL v69; // ecx
  __int64 v70; // rax
  int v71; // edx
  __int64 v72; // rax
  __int64 v73; // rcx
  __int64 v74; // rax
  __int64 v75; // rax
  int v76; // edx
  int v77; // r8d
  PVOID v78; // r8
  _QWORD *v79; // rdx
  PVOID *v80; // r13
  unsigned __int16 v81; // ax
  unsigned int v82; // r12d
  __int64 v83; // r8
  size_t v84; // r13
  unsigned int v85; // r12d
  __int64 v86; // r8
  char *v87; // rcx
  __int64 v88; // rbx
  __int64 v89; // rax
  char v90; // [rsp+F8h] [rbp-218h] BYREF
  char v91[3]; // [rsp+F9h] [rbp-217h] BYREF
  int v92; // [rsp+FCh] [rbp-214h]
  char v93; // [rsp+100h] [rbp-210h]
  char v94; // [rsp+101h] [rbp-20Fh]
  char *v95; // [rsp+108h] [rbp-208h]
  int v96; // [rsp+110h] [rbp-200h]
  unsigned int v97; // [rsp+114h] [rbp-1FCh] BYREF
  void *Buf1[2]; // [rsp+118h] [rbp-1F8h] BYREF
  PVOID Context[2]; // [rsp+128h] [rbp-1E8h] BYREF
  int v100[4]; // [rsp+138h] [rbp-1D8h]
  PVOID Bcb[2]; // [rsp+148h] [rbp-1C8h] BYREF
  __int64 v102; // [rsp+158h] [rbp-1B8h]
  int v103; // [rsp+160h] [rbp-1B0h]
  char v104; // [rsp+164h] [rbp-1ACh]
  __int16 v105; // [rsp+168h] [rbp-1A8h] BYREF
  PVOID v106; // [rsp+170h] [rbp-1A0h] BYREF
  unsigned int v107; // [rsp+178h] [rbp-198h] BYREF
  PIRP Irp; // [rsp+180h] [rbp-190h]
  __int64 v109; // [rsp+188h] [rbp-188h]
  struct _UNICODE_STRING LinkName; // [rsp+190h] [rbp-180h] BYREF
  struct _UNICODE_STRING FileName; // [rsp+1A0h] [rbp-170h] BYREF
  char *v112; // [rsp+1B0h] [rbp-160h]
  PVOID v113; // [rsp+1B8h] [rbp-158h]
  __int64 v114; // [rsp+1C0h] [rbp-150h] BYREF
  PVOID v115; // [rsp+1C8h] [rbp-148h]
  int v116; // [rsp+1D0h] [rbp-140h]
  __int64 v117[2]; // [rsp+1D8h] [rbp-138h] BYREF
  PVOID P[2]; // [rsp+1E8h] [rbp-128h] BYREF
  __int64 v119; // [rsp+1F8h] [rbp-118h]
  _QWORD *v120; // [rsp+200h] [rbp-110h]
  __int128 v121; // [rsp+208h] [rbp-108h] BYREF
  _QWORD *v122; // [rsp+218h] [rbp-F8h] BYREF
  char *v123; // [rsp+220h] [rbp-F0h]
  __int64 v124; // [rsp+228h] [rbp-E8h]
  __int64 v125; // [rsp+230h] [rbp-E0h]
  LARGE_INTEGER ByteOffset; // [rsp+238h] [rbp-D8h]
  __int64 v127; // [rsp+240h] [rbp-D0h]
  __int64 v128; // [rsp+248h] [rbp-C8h]
  __int64 v129; // [rsp+250h] [rbp-C0h]
  _QWORD v130[14]; // [rsp+258h] [rbp-B8h] BYREF

  v109 = a4;
  Irp = a2;
  v129 = a1;
  v128 = a3;
  v8 = a5;
  v124 = a5;
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  *(_OWORD *)Buf1 = 0;
  v121 = 0;
  v106 = 0;
  v105 = 0;
  v90 = 0;
  P[0] = 0;
  *(_QWORD *)&LinkName.Length = 0;
  ByteOffset = CurrentStackLocation->Parameters.Read.ByteOffset;
  *(_OWORD *)v117 = 0;
  v114 = 0;
  v122 = 0;
  *(_OWORD *)Context = 0;
  *(_OWORD *)v100 = 0;
  *(_OWORD *)Bcb = 0;
  v102 = 0;
  v10 = *(_QWORD *)(a1 + 400);
  v119 = v10;
  if ( v10 )
    v11 = *(_QWORD *)(v10 + 232);
  else
    v11 = 0;
  memset(v130, 0, sizeof(v130));
  v12 = *(_BYTE **)(*(_QWORD *)(a1 + 112) + 24LL);
  if ( CurrentStackLocation->Parameters.Create.Options == 11 )
  {
    v96 = *v12 != 0;
  }
  else
  {
    v96 = *(_DWORD *)v12;
    if ( (v96 & 0xFFFFFE04) != 0 )
    {
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(0, 3221225659LL, 995983);
      return 3221225659LL;
    }
  }
  Context[0] = (PVOID)a1;
  v14 = *(int **)(a4 + 184);
  Context[1] = v14;
  v113 = 0;
  v115 = 0;
  if ( (*(_DWORD *)(a5 + 4) & 2) == 0 )
  {
    if ( NtfsStatusDebugFlags )
    {
      v15 = 996004;
LABEL_52:
      NtfsStatusTraceAndDebugInternal(0, 3221225485LL, v15);
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
        McTemplateU0ppwwpiw_EtwWriteTransfer(
          *(unsigned __int16 *)(a5 + 16) >> 1,
          (unsigned int)fileinfo_c12986,
          (unsigned int)KeGetCurrentThread(),
          a3,
          *(_WORD *)(a3 + 7872) >> 1,
          *(_QWORD *)(a3 + 7880),
          v18 >> 1,
          v17 + 32,
          (char)v14,
          *((_QWORD *)v14 + 1),
          *(_WORD *)(a5 + 16) >> 1,
          *(_QWORD *)(a5 + 24));
      }
      if ( NtfsStatusDebugFlags )
      {
        v19 = 996039;
LABEL_43:
        v26 = -1073741790;
        NtfsStatusTraceAndDebugInternal(0, 3221225506LL, v19);
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
        LODWORD(v14) = Context[1];
      }
      if ( !v11 )
        LODWORD(v11) = 1;
      v22 = TxfLinksVisibleToTransaction(a1, (_DWORD)v14, v11, 0, 0);
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
          McTemplateU0ppwwpiwd_EtwWriteTransfer(
            *(unsigned __int16 *)(a5 + 16) >> 1,
            (unsigned int)fileinfo_c13046,
            (unsigned int)KeGetCurrentThread(),
            a3,
            *(_WORD *)(a3 + 7872) >> 1,
            *(_QWORD *)(a3 + 7880),
            v25 >> 1,
            v24 + 32,
            *(_QWORD *)(v109 + 184),
            *(_QWORD *)(*(_QWORD *)(v109 + 184) + 8LL),
            *(_WORD *)(a5 + 16) >> 1,
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
      if ( !ByteOffset.QuadPart )
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
      *(_QWORD *)&v100[2] = *(_QWORD *)(v20 + 24);
    if ( (v14[1] & 0x100) != 0 )
    {
      if ( NtfsStatusDebugFlags )
      {
        v15 = 996130;
        goto LABEL_52;
      }
      return 3221225485LL;
    }
    if ( !byte_140095AD2 && (unsigned __int8)NtfsEffectiveMode(Irp) == 1 && (*(_WORD *)(a5 + 104) & 0x310) == 0 )
    {
      v107 = 0;
      v97 = 0;
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
      v28 = *(_QWORD *)(a1 + 400);
      if ( v28 )
        v29 = *(_QWORD *)(v28 + 232);
      else
        LODWORD(v29) = 0;
      v30 = *(_QWORD *)(a1 + 208);
      v31 = *(_QWORD *)(v109 + 184);
      FileObjectGenericMapping = IoGetFileObjectGenericMapping();
      if ( !(unsigned __int8)TxfAccessCheck(
                               a1,
                               v29,
                               v31,
                               v30,
                               0,
                               0,
                               256,
                               0,
                               0,
                               (__int64)FileObjectGenericMapping,
                               1,
                               (__int64)&v107,
                               0,
                               (__int64)&v97,
                               0) )
      {
        if ( (unsigned __int8)NtfsTelemetryGuard(512) )
          NtfsTelemetryHardLinkWithNoAccessFailed(a3);
        if ( (*(_DWORD *)(a1 + 16) & 0x100000) == 0
          && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x20) != 0 )
        {
          v33 = *(_QWORD *)(a3 + 248);
          v34 = *(_WORD *)(v33 + 6);
          if ( v34 > 0x40u || (v34 & 1) != 0 )
            v34 = 0;
          McTemplateU0ppwwpiwd_EtwWriteTransfer(
            *(unsigned __int16 *)(a5 + 16) >> 1,
            (unsigned int)fileinfo_c13141,
            (unsigned int)KeGetCurrentThread(),
            a3,
            *(_WORD *)(a3 + 7872) >> 1,
            *(_QWORD *)(a3 + 7880),
            v34 >> 1,
            v33 + 32,
            *(_QWORD *)(v109 + 184),
            *(_QWORD *)(*(_QWORD *)(v109 + 184) + 8LL),
            *(_WORD *)(a5 + 16) >> 1,
            *(_QWORD *)(a5 + 24),
            v97);
        }
        if ( NtfsStatusDebugFlags )
        {
          v19 = 996195;
          goto LABEL_43;
        }
        return (unsigned int)-1073741790;
      }
      v20 = *(_QWORD *)&FileName.Length;
    }
    if ( (*(_DWORD *)(a1 + 12) & 1) == 0 )
      return NtfsPostRequest((PVOID)a1);
    v92 = 0;
    v35 = 0;
    v95 = 0;
    v123 = 0;
    v94 = 10;
    v93 = 0;
    v120 = 0;
    v91[0] = 0;
    if ( (*(_DWORD *)(a5 + 4) & 8) == 0 && **(_WORD **)(a5 + 24) == 92 )
      BYTE1(Bcb[1]) |= 1u;
    *(_DWORD *)(a1 + 272) = *(_DWORD *)(a5 + 100);
    v36 = *(_QWORD *)(v109 + 184);
    v37 = *(_QWORD *)(v36 + 296);
    if ( v37 && *(_DWORD *)(v37 + 248) )
    {
      NtfsPostUsnChangeWithOverrideOption(a1, v36, 0x80000000, 0, 0, 0, 0);
      NtfsCheckpointCurrentTransaction(a1);
    }
    NtfsFindTargetElements(
      a1,
      ByteOffset.LowPart,
      v100[2],
      (unsigned int)P,
      (__int64)&LinkName,
      (__int64)&v121,
      (__int64)Buf1);
    v40 = LOWORD(Buf1[0]);
    if ( LOWORD(Buf1[0]) > 0x1FEu || (IsFileNameValid = NtfsIsFileNameValid(Buf1, 0), v39 = 0, !IsFileNameValid) )
    {
      v26 = -1073741773;
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(0, 3221225523LL, 996266);
      v92 = -1073741773;
      goto LABEL_274;
    }
    v43 = (char *)P[0];
    v44 = *((_QWORD *)P[0] + 23);
    if ( (*(_DWORD *)(v44 + 4) & 0x100) != 0 && P[0] != *(PVOID *)(a3 + 32) )
    {
      if ( (*(_DWORD *)(a1 + 16) & 0x100000LL) == 0
        && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x20) != 0 )
      {
        v45 = *(_QWORD *)(a3 + 248);
        v46 = *(unsigned __int16 *)(v45 + 6);
        if ( v46 > 0x40 || (v46 & 1) != 0 )
          v46 = 0;
        v107 = v46;
        LOWORD(ByteOffset.LowPart) = v46;
        v127 = v45 + 32;
        McTemplateU0ppwwpiw_EtwWriteTransfer(
          (unsigned int)v40 >> 1,
          (unsigned int)fileinfo_c13237,
          (unsigned int)KeGetCurrentThread(),
          a3,
          *(_WORD *)(a3 + 7872) >> 1,
          *(_QWORD *)(a3 + 7880),
          (unsigned __int16)v46 >> 1,
          v45 + 32,
          v44,
          *(_QWORD *)(v44 + 8),
          (unsigned int)v40 >> 1,
          (__int64)Buf1[1]);
      }
      v26 = -1073741790;
      if ( !NtfsStatusDebugFlags )
        goto LABEL_97;
      v47 = 996290;
      goto LABEL_96;
    }
    if ( *(int *)(v44 + 176) < 0 )
    {
      v38 = 4;
      if ( _InterlockedCompareExchange((volatile signed __int32 *)(*(_QWORD *)(v44 + 320) + 132LL), 4, 4)
        || (v48 = TxfConvertMungedNameToTxfFileId(0, Buf1, 0, v42), v39 = 0, v48 < 0) )
      {
        if ( (*(_DWORD *)(a1 + 16) & 0x100000LL) == 0
          && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x20) != 0 )
        {
          v49 = *(_QWORD *)(a3 + 248);
          v50 = *(unsigned __int16 *)(v49 + 6);
          if ( v50 > 0x40 || (v50 & 1) != 0 )
          {
            v51 = 0;
            v96 = 0;
          }
          else
          {
            v51 = *(_WORD *)(v49 + 6);
            v96 = v51;
          }
          LOWORD(v124) = v51;
          v125 = v49 + 32;
          McTemplateU0ppwwpiwd_EtwWriteTransfer(
            (unsigned int)v40 >> 1,
            (unsigned int)fileinfo_c13263,
            (unsigned int)KeGetCurrentThread(),
            a3,
            *(_WORD *)(a3 + 7872) >> 1,
            *(_QWORD *)(a3 + 7880),
            v51 >> 1,
            v49 + 32,
            *((_QWORD *)v43 + 23),
            *(_QWORD *)(*((_QWORD *)v43 + 23) + 8LL),
            (unsigned int)v40 >> 1,
            (__int64)Buf1[1],
            *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v43 + 23) + 320LL) + 132LL));
        }
        v26 = -1073741790;
        if ( !NtfsStatusDebugFlags )
          goto LABEL_97;
        v47 = 996317;
        goto LABEL_96;
      }
    }
    if ( (*(_DWORD *)(a1 + 12) & 0x100) != 0 )
    {
      NtfsAcquireExclusiveScbEx(a1, v43, 0);
    }
    else
    {
      if ( !(unsigned __int8)NtfsAcquireExclusiveFcb(a1, *((_QWORD *)v43 + 23), v43, 66) )
      {
        *(_DWORD *)(a1 + 12) |= 0x100u;
        NtfsRaiseStatusInternal(a1, -1073741608, 0, 0, 996342);
        __debugbreak();
        JUMPOUT(0x140259EA7LL);
      }
      if ( (*((_DWORD *)v43 + 50) & 0x200) != 0 )
        NtfsSnapshotScb(a1, v43);
    }
    v39 = *((_QWORD *)v43 + 23);
    if ( !*(_WORD *)(v39 + 188) )
    {
      v26 = -1073741738;
      if ( !NtfsStatusDebugFlags )
        goto LABEL_97;
      v47 = 996372;
LABEL_96:
      NtfsStatusTraceAndDebugInternal(0, v26, v47);
LABEL_97:
      v92 = v26;
LABEL_273:
      v35 = v95;
LABEL_274:
      NtfsRenameCleanup(Context, v38, v39);
      if ( v113 )
        ExFreePoolWithTag(v113, 0);
      if ( v35 )
        ExFreePoolWithTag(v35, 0);
      if ( v106 )
        ExFreePoolWithTag(v106, 0);
      if ( SLOBYTE(Bcb[1]) < 0 )
      {
        ExAcquirePushLockSharedEx(a3 + 656, 0);
        _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)v100 + 28LL));
        ExReleasePushLockEx(a3 + 656, 0);
      }
      if ( v120 == v130 && (_QWORD *)v130[3] != &v130[7] )
        ExFreePoolWithTag((PVOID)v130[3], 0);
      if ( v26 != 259 && ((__int64)Bcb[1] & 8) != 0 )
        NtfsTeardownStructures(a1, v100[0], 0);
      return v26;
    }
    if ( v119 )
    {
      if ( v43 == *(char **)&v100[2] )
        goto LABEL_122;
      TxfPrepareFileForTxfLogging(a1, 0, 0, 1, 0);
    }
    if ( v43 != *(char **)&v100[2] )
    {
      BYTE2(Bcb[1]) |= 0x10u;
      v53 = *((_QWORD *)v43 + 23);
      if ( (*(_DWORD *)(v53 + 176) & 0x400) != 0 )
      {
        CurrentFileInfo = TxfGetCurrentFileInfo(a1, v53, 0, 0, 0);
        if ( !(unsigned __int8)RtlIsNonEmptyDirectoryReparsePointAllowed(CurrentFileInfo) )
        {
          v26 = -1073741183;
          if ( !NtfsStatusDebugFlags )
            goto LABEL_97;
          v47 = 996458;
          goto LABEL_96;
        }
      }
      goto LABEL_127;
    }
LABEL_122:
    if ( (_WORD)v40 == *(_WORD *)(v20 + 72) && !memcmp(Buf1[1], *(const void **)(v20 + 80), v40) )
    {
      if ( (v96 & 1) == 0 )
      {
        v26 = -1073741771;
        if ( !NtfsStatusDebugFlags )
          goto LABEL_97;
        v47 = 996427;
        goto LABEL_96;
      }
      goto LABEL_148;
    }
LABEL_127:
    v52 = v43 + 656;
    v38 = 0;
    if ( !*((_WORD *)v43 + 328) )
    {
      NtfsBuildNormalizedNameWithTxfIsolation(a1, *((_QWORD *)v43 + 23), (_DWORD)v43, 0, 0, 0, (__int64)(v43 + 656));
      v38 = 0;
    }
    if ( !NtfsAllowMaximumSupportedHardLinks && *((_WORD *)Context[1] + 95) >= 0x400u )
    {
      v26 = -1073741211;
      if ( !NtfsStatusDebugFlags )
        goto LABEL_97;
      v47 = 996481;
      goto LABEL_96;
    }
    v55 = *(_DWORD *)(a5 + 4);
    LOBYTE(v39) = (v55 & 1) != 0 && ((v55 & 0x4000000) != 0 || (*(_DWORD *)(*((_QWORD *)v43 + 23) + 16LL) & 0x400) == 0);
    v56 = NtfsLookupEntry(
            a1,
            (_DWORD)v43,
            v39,
            (unsigned int)Buf1,
            (__int64)&v106,
            (__int64)&v105,
            0,
            (__int64)&v122,
            (__int64)Bcb,
            0);
    LOBYTE(Bcb[1]) = (__int64)Bcb[1] & 0xDF | (32 * (v56 & 1));
    v26 = TxfCheckTargetForRename(a1, Buf1, v43);
    v92 = v26;
    if ( v26 )
      goto LABEL_273;
    if ( ((__int64)Bcb[1] & 0x20) != 0 )
    {
      if ( (v96 & 1) == 0 )
      {
        v26 = -1073741771;
        if ( !NtfsStatusDebugFlags )
          goto LABEL_97;
        v47 = 996543;
        goto LABEL_96;
      }
      v57 = (__int64)(v122 + 2);
      if ( (unsigned __int8)NtfsCheckLinkForNewLink(
                              Context[1],
                              (int)v122 + 16,
                              *v122,
                              (unsigned int)Buf1,
                              (__int64)&Bcb[1]) )
      {
LABEL_148:
        v26 = 0;
        v92 = 0;
        goto LABEL_273;
      }
      v94 = *(_BYTE *)(v57 + 65);
      v104 = v94;
      if ( (BYTE1(Bcb[1]) & 1) != 0 )
      {
        v38 = *(unsigned __int16 *)(*(_QWORD *)&v100[2] + 656LL) + (unsigned int)LOWORD(Buf1[0]) + 2;
        if ( (unsigned int)v38 > 0xFFFE )
        {
          v26 = -1073741562;
          if ( !NtfsStatusDebugFlags )
            goto LABEL_97;
          v47 = 996614;
          goto LABEL_96;
        }
        v58 = *(_WORD *)(*(_QWORD *)&v100[2] + 656LL) + LOWORD(Buf1[0]) + 2;
        LOWORD(v114) = v58;
        WORD1(v114) = v38;
        v113 = ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), (unsigned __int16)v38, 0x4646744Eu);
        v115 = v113;
        memmove(v113, *(const void **)(*(_QWORD *)&v100[2] + 664LL), *(unsigned __int16 *)(*(_QWORD *)&v100[2] + 656LL));
        v59 = *(unsigned __int16 *)(*(_QWORD *)&v100[2] + 656LL);
        v60 = (char *)v113 + v59;
        v112 = (char *)v113 + v59;
        if ( (_WORD)v59 == 2 )
        {
          LOWORD(v114) = v58 - 2;
        }
        else
        {
          *(_WORD *)v60 = 92;
          v60 += 2;
          v112 = v60;
        }
        v117[1] = (__int64)v60;
        v61 = (unsigned __int16)Buf1[0];
      }
      else
      {
        v60 = (char *)ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), LOWORD(Buf1[0]), 0x4646744Eu);
        v113 = v60;
        v117[1] = (__int64)v60;
        v115 = v60;
        v61 = (unsigned __int16)Buf1[0];
        WORD1(v117[0]) = Buf1[0];
        LOWORD(v114) = Buf1[0];
      }
      WORD1(v117[0]) = v61;
      LOWORD(v117[0]) = v61;
      memmove(v60, (const void *)(v57 + 66), v61);
      if ( (BYTE1(Bcb[1]) & 2) != 0 )
      {
        if ( v119 )
        {
          v91[0] = 1;
          v93 = 1;
          NtfsCreateLcb(a1, (_DWORD)v43, Context[1], (unsigned int)v117, *(_BYTE *)(v57 + 65), (__int64)v91);
          v26 = TxfPrepareFileForPotentialTxLinkDelete(a1);
          v92 = v26;
          if ( (v26 & 0x80000000) != 0 )
          {
            if ( NtfsStatusDebugFlags
              && v26 < 0xFFFFFFED
              && v26 != -1073741802
              && v26 + 2147483643 > 1
              && v26 != -1073741807
              && v26 != -1073741608 )
            {
              NtfsStatusTraceAndDebugInternal(a1, v26, 996729);
            }
            ExRaiseStatus(v26);
          }
          v120 = v130;
          v130[1] = &v130[4];
          v130[3] = &v130[7];
          LODWORD(v130[0]) = 1572864;
          LODWORD(v130[2]) = 3407872;
          v91[0] = *(_BYTE *)(*(_QWORD *)(*(_QWORD *)&FileName.Length + 192LL) + 65LL);
          TxfRemoveLink(a1, (int)Context[1], 0);
        }
        else
        {
          NtfsRemoveLink(a1, (int)Context[1], 0, 0);
          ++WORD2(Bcb[1]);
        }
        *((_DWORD *)Context[1] + 1) &= ~0x4000u;
        *(PVOID *)v100 = Context[1];
      }
      else
      {
        v26 = NtfsRemoveSupersededTarget(
                a1,
                v57,
                Context[1],
                Irp,
                v124,
                (v96 & 2) != 0,
                (v96 & 0x40) != 0,
                (__int64)v117,
                (__int64)Context);
        v92 = v26;
        if ( v26 )
          goto LABEL_273;
      }
      v52 = v43 + 656;
      v8 = v124;
    }
    v38 = 65534;
    if ( *(_QWORD *)&LinkName.Length && (*(_DWORD *)(*(_QWORD *)&LinkName.Length + 4LL) & 8) != 0
      || (BYTE1(Bcb[1]) & 1) != 0 && !*((_QWORD *)&v121 + 1) )
    {
      v62 = (unsigned __int16)*v52 + LOWORD(Buf1[0]) + 2;
      if ( v62 > 0xFFFE )
      {
        v26 = -1073741562;
        if ( !NtfsStatusDebugFlags )
          goto LABEL_97;
        v47 = 996788;
        goto LABEL_96;
      }
      v63 = *v52 + LOWORD(Buf1[0]) + 2;
      LOWORD(v121) = v62;
      WORD1(v121) = v62;
      v95 = (char *)ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), (unsigned __int16)v62, 0x4646744Eu);
      *((_QWORD *)&v121 + 1) = v95;
      v123 = v95;
      memmove(v95, *((const void **)v43 + 83), *((unsigned __int16 *)v43 + 328));
      v64 = *((unsigned __int16 *)v43 + 328);
      v65 = &v95[v64];
      v112 = &v95[v64];
      if ( (_WORD)v64 == 2 )
      {
        LOWORD(v121) = v63 - 2;
      }
      else
      {
        *(_WORD *)v65 = 92;
        v65 += 2;
        v112 = v65;
      }
      memmove(v65, Buf1[1], LOWORD(Buf1[0]));
    }
    if ( Bcb[0] )
    {
      CcUnpinData(Bcb[0]);
      Bcb[0] = 0;
    }
    NtfsCheckIndexForAddOrDelete(a1, (_DWORD)Irp, *((_QWORD *)v43 + 23), 2, v8);
    v66 = v109;
    NtfsUpdateFileTimestampsForChange(*(_QWORD *)(v109 + 184), v8, 0x400000);
    NtfsAddLink(a1, Context[1], (__int64)v106, 0, (__int64)&v90, 0, 0, 0, 0);
    if ( v119 )
    {
      v67 = *(_DWORD *)(v8 + 4);
      if ( v93 )
      {
        v69 = (v67 & 1) != 0 && ((v67 & 0x4000000) != 0 || (*(_DWORD *)(*((_QWORD *)v43 + 23) + 16LL) & 0x400) == 0);
        TxfAddLinkForRename(a1, v91[0], v90, (__int64)v120, 0, 0, v69, Context[1]);
      }
      else
      {
        v68 = (v67 & 1) != 0 && ((v67 & 0x4000000) != 0 || (*(_DWORD *)(*((_QWORD *)v43 + 23) + 16LL) & 0x400) == 0);
        TxfAddHardLink(a1, 0, 0, v68, Context[1]);
      }
    }
    if ( v43 != *(char **)&v100[2]
      && *(_BYTE *)(*((_QWORD *)v43 + 23) + 38LL) != *((_BYTE *)Context[1] + 38)
      && (v96 & 8) == 0 )
    {
      ExAcquireResourceExclusiveLite((PERESOURCE)(a3 + 10688), 1u);
      BYTE2(Bcb[1]) |= 0x40u;
      v70 = *((unsigned __int8 *)Context[1] + 38);
      v71 = 0;
      if ( !(_BYTE)v70 || (v72 = *(_QWORD *)(a3 + 8 * v70 + 10904)) == 0 || (*(_DWORD *)(v72 + 4) & 0x40) == 0 )
      {
        v73 = *((_QWORD *)v43 + 23);
        v74 = *(unsigned __int8 *)(v73 + 38);
        if ( !(_BYTE)v74 || (v75 = *(_QWORD *)(a3 + 8 * v74 + 10904)) == 0 || (*(_DWORD *)(v75 + 4) & 0x80u) == 0 )
        {
          v103 = 0;
          if ( (v96 & 0x10) != 0 )
            v71 = 1;
          v103 = v71;
          if ( (v96 & 0x20) != 0 )
          {
            v71 |= 2u;
            v103 = v71;
          }
          if ( (v96 & 0x80u) != 0 )
          {
            v71 |= 4u;
            v103 = v71;
          }
          if ( (v96 & 0x100) != 0 )
          {
            v71 |= 8u;
            v103 = v71;
          }
          v26 = NtfsChangeStorageReserveId(a1, *(unsigned __int8 *)(v73 + 38), v71);
          v92 = v26;
          if ( v26 )
            goto LABEL_273;
        }
      }
      ExReleaseResourceLite((PERESOURCE)(a3 + 10688));
      BYTE2(Bcb[1]) &= ~0x40u;
      v66 = v109;
    }
    --WORD2(Bcb[1]);
    NtfsUpdateFcbTimestamps(*((_QWORD *)v43 + 23), 2684354576LL);
    if ( (BYTE1(Bcb[1]) & 2) != 0 )
      NtfsReplaceLinkInDir(a1, (_DWORD)v43, Context[1], (unsigned int)Buf1, v90, (__int64)v117, v94);
    if ( (unsigned __int8)NtfsTelemetryGuard(512) )
      ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))NtfsTelemetryHardLink)(
        a3,
        Buf1,
        (LARGE_INTEGER)ByteOffset.QuadPart,
        0);
    if ( (BYTE1(Bcb[1]) & 1) == 0 )
    {
LABEL_235:
      if ( (*(_DWORD *)(a3 + 4) & 0x80000) != 0 )
      {
        v78 = v106;
        if ( (*((_BYTE *)v106 + 65) & 3) == 2 )
          v78 = 0;
        NtfsPostUsnChangeWithOverrideOption(a1, v66, -2147418112, 0, 0, 0, (__int64)v78);
        if ( *(_QWORD *)(a1 + 240) )
        {
          NtfsCheckpointCurrentTransaction(a1);
          *(_DWORD *)(*(_QWORD *)(v66 + 184) + 4LL) &= ~0x4000u;
        }
      }
      FsRtlCheckOplockEx((POPLOCK)v43 + 11, Irp, 0x10u, 0, 0, 0);
      *((_WORD *)Context[1] + 95) -= WORD2(Bcb[1]);
      *((_WORD *)Context[1] + 94) -= WORD2(Bcb[1]);
      if ( *(_QWORD *)v100 && !*(_WORD *)(*(_QWORD *)v100 + 188LL) && *(_QWORD *)(*(_QWORD *)v100 + 120LL) )
        NtfsDereferenceQuotaControlBlock(a3, *(_QWORD *)v100 + 120LL, 0);
      v79 = Context[1];
      if ( !*((_QWORD *)Context[1] + 26) )
      {
        NtfsLoadSecurityDescriptor(a1, Context[1]);
        v79 = Context[1];
      }
      if ( !SeAuditingHardLinkEventsWithContext(1u, (PSECURITY_DESCRIPTOR)(v79[26] + 28LL), 0) )
        goto LABEL_273;
      P[0] = 0;
      *(_QWORD *)&FileName.Length = 0;
      *(_QWORD *)&LinkName.Length = 0;
      v97 = 0;
      P[1] = 0;
      FileName.Buffer = 0;
      LinkName.Buffer = 0;
      v80 = (PVOID *)(v8 + 16);
      v81 = *(_WORD *)v80;
      if ( !*(_WORD *)v80 )
      {
        NtfsBuildNormalizedNameWithTxfIsolation(a1, *(_QWORD *)(v66 + 184), 0, 0, 0, 0, (__int64)P);
        v80 = P;
        v81 = (unsigned __int16)P[0];
      }
      v82 = v81 + *(unsigned __int16 *)(a3 + 7856);
      v97 = v82;
      if ( v82 <= 0xFFFE )
      {
        FileName.Buffer = (PWSTR)ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), v82, 0x4646744Eu);
        FileName.MaximumLength = v82;
        FileName.Length = v82;
        memmove(FileName.Buffer, *(const void **)(a3 + 7864), *(unsigned __int16 *)(a3 + 7856));
        memmove((char *)FileName.Buffer + *(unsigned __int16 *)(a3 + 7856), v80[1], *(unsigned __int16 *)v80);
        v84 = LOWORD(Buf1[0]);
        v85 = LOWORD(Buf1[0]) + *((unsigned __int16 *)v43 + 328) + *(unsigned __int16 *)(a3 + 7856) + 2;
        v97 = v85;
        if ( v85 <= 0xFFFE )
        {
          LinkName.Buffer = (PWSTR)ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), v85, 0x4646744Eu);
          LinkName.MaximumLength = v85;
          LinkName.Length = v85;
          memmove(LinkName.Buffer, *(const void **)(a3 + 7864), *(unsigned __int16 *)(a3 + 7856));
          memmove(
            (char *)LinkName.Buffer + *(unsigned __int16 *)(a3 + 7856),
            *((const void **)v43 + 83),
            *((unsigned __int16 *)v43 + 328));
          v86 = *((unsigned __int16 *)v43 + 328);
          v87 = (char *)LinkName.Buffer + v86 + *(unsigned __int16 *)(a3 + 7856);
          v112 = v87;
          if ( (_WORD)v86 == 2 )
          {
            LinkName.Length -= 2;
          }
          else
          {
            *(_WORD *)v87 = 92;
            v87 += 2;
            v112 = v87;
          }
          memmove(v87, Buf1[1], v84);
          v88 = v109;
          v89 = *(_QWORD *)(v109 + 528);
          if ( v89 && *(_QWORD *)(*(_QWORD *)(v89 + 64) + 24LL) )
          {
            TxfSetupTransactionForAuditing();
            SeAuditHardLinkCreationWithTransaction(
              &FileName,
              &LinkName,
              1u,
              (GUID *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v88 + 528) + 64LL) + 24LL) + 256LL));
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
          v83 = 997214;
          goto LABEL_252;
        }
      }
      else
      {
        v26 = -1073741562;
        if ( NtfsStatusDebugFlags )
        {
          v83 = 997201;
LABEL_252:
          NtfsStatusTraceAndDebugInternal(0, 3221225734LL, v83);
        }
      }
      v92 = -1073741562;
LABEL_264:
      if ( P[1] )
        ExFreePoolWithTag(P[1], 0);
      if ( LinkName.Buffer )
        ExFreePoolWithTag(LinkName.Buffer, 0);
      if ( FileName.Buffer )
        ExFreePoolWithTag(FileName.Buffer, 0);
      goto LABEL_273;
    }
    v76 = 0;
    v116 = 0;
    if ( (BYTE1(Bcb[1]) & 4) != 0 )
    {
      v77 = 0;
      if ( (BYTE1(Bcb[1]) & 2) != 0 )
        goto LABEL_233;
      v76 = 508;
      v77 = 3;
    }
    else
    {
      if ( ((__int64)Bcb[1] & 0x20) != 0 )
      {
        NtfsReportDirNotify(
          a1,
          (_DWORD)v43,
          a3,
          (unsigned int)&v114,
          (unsigned __int16)v114 - LOWORD(v117[0]),
          0,
          ((*(_DWORD *)(*(_QWORD *)v100 + 176LL) & 0x10000000) != 0) + 1,
          2,
          *((_QWORD *)v43 + 23),
          *(__int64 *)v100);
        v113 = v115;
      }
      v76 = 1;
      v77 = 1;
    }
    v116 = v76;
LABEL_233:
    if ( v76 )
      NtfsReportDirNotify(
        a1,
        (_DWORD)v43,
        a3,
        (unsigned int)&v121,
        (unsigned __int16)v121 - LOWORD(Buf1[0]),
        0,
        v76,
        v77,
        *((_QWORD *)v43 + 23),
        (__int64)Context[1]);
    goto LABEL_235;
  }
  if ( NtfsStatusDebugFlags )
    NtfsStatusTraceAndDebugInternal(0, 3221225658LL, 996017);
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
