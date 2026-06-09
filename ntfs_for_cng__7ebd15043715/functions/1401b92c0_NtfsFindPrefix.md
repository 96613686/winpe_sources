# NtfsFindPrefix

- ea: `0x1401b92c0`
- end: `0x1401ba61c`
- name: `NtfsFindPrefix`
- size: `4956`
- prototype: `_QWORD *__fastcall(__int64, __int64, __int64, _QWORD *, UNICODE_STRING *, UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `15`
- tags: `reparse_path, installer_update`

## callers

- `0x14019f300`

## callees

- `0x140007ea0`
- `0x14000c290`
- `0x14000cb80`
- `0x14000d510`
- `0x14001c2e0`
- `0x14001e840`
- `0x140021b10`
- `0x1400232f0`
- `0x1400300bc`
- `0x140059250`
- `0x1400593c0`
- `0x1401633d0`
- `0x14019a718`
- `0x1401b92c0`
- `0x1401ba624`

## import_xrefs

- `ntoskrnl!IoGetIrpExtraCreateParameter` at `0x1401b9551`
- `ntoskrnl!IoGetIrpExtraCreateParameter` at `0x1401b99e8`
- `ntoskrnl!IoGetIrpExtraCreateParameter` at `0x1401b9551`
- `ntoskrnl!IoGetIrpExtraCreateParameter` at `0x1401b99e8`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x1401b9585`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x1401b9a1c`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x1401b9585`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x1401b9a1c`
- `ntoskrnl!FsRtlIsNonEmptyDirectoryReparsePointAllowed` at `0x1401b990e`
- `ntoskrnl!FsRtlIsNonEmptyDirectoryReparsePointAllowed` at `0x1401b9bc3`
- `ntoskrnl!FsRtlIsNonEmptyDirectoryReparsePointAllowed` at `0x1401b990e`
- `ntoskrnl!FsRtlIsNonEmptyDirectoryReparsePointAllowed` at `0x1401b9bc3`
- `ntoskrnl!FsRtlDissectName` at `0x1401b93b4`
- `ntoskrnl!FsRtlDissectName` at `0x1401b97bb`
- `ntoskrnl!FsRtlDissectName` at `0x1401b93b4`
- `ntoskrnl!FsRtlDissectName` at `0x1401b97bb`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1401b93fd`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1401b97f4`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1401b9a70`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1401b9adf`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1401ba200`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1401ba2b7`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1402ae71b`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1402ae773`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1401b93fd`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1401b97f4`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1401b9a70`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1401b9adf`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1401ba200`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1401ba2b7`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1402ae71b`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1402ae773`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x1401b9caa`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x1401b9e4c`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x1401b9f64`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x1401b9ffd`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x1401b9caa`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x1401b9e4c`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x1401b9f64`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x1401b9ffd`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401b94bd`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401b96d4`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401b98b7`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401b9a90`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401b9aff`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401ba225`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401ba241`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401ba2dc`
- `ntoskrnl!ExReleasePushLockEx` at `0x1402ae743`
- `ntoskrnl!ExReleasePushLockEx` at `0x1402ae790`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401b94bd`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401b96d4`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401b98b7`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401b9a90`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401b9aff`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401ba225`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401ba241`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401ba2dc`
- `ntoskrnl!ExReleasePushLockEx` at `0x1402ae743`
- `ntoskrnl!ExReleasePushLockEx` at `0x1402ae790`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401b9cfb`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401b9d4d`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401b9e9e`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401b9f19`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401b9fb5`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401ba04e`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401ba121`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401ba4a1`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401b9cfb`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401b9d4d`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401b9e9e`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401b9f19`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401b9fb5`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401ba04e`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401ba121`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401ba4a1`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401b9ccc`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401b9d23`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401b9e6f`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401b9ec6`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401b9f86`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401ba01f`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401b9ccc`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401b9d23`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401b9e6f`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401b9ec6`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401b9f86`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401ba01f`

## pseudocode

```c
_QWORD *__fastcall NtfsFindPrefix(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4,
        UNICODE_STRING *a5,
        UNICODE_STRING *a6)
{
  __int16 *Scb; // rbx
  bool v8; // r15
  __int64 v9; // r14
  __int64 v10; // rcx
  int v11; // r14d
  __int64 v12; // r12
  _QWORD *ExistingLcb; // r14
  __int64 v14; // rax
  __int64 v15; // rdx
  __int64 v16; // rax
  __int64 MatchingElementGenericTableAvl; // rax
  __int64 v19; // r14
  __int64 v20; // rcx
  int v21; // r14d
  NTSTATUS v22; // eax
  _DWORD *k; // rax
  PVOID v24; // rdx
  __int64 v25; // rax
  int v26; // r15d
  struct _ECP_LIST *v27; // r12
  volatile signed __int32 *v28; // r13
  __int64 v29; // r14
  PVOID v30; // rax
  bool v31; // r13
  __int64 v32; // rcx
  int v33; // ebx
  _QWORD *v34; // r15
  __int64 v35; // r13
  __int64 v36; // rax
  __int64 v37; // rdx
  __int64 v38; // rax
  bool v39; // cl
  bool v40; // al
  __int64 v41; // rcx
  __int64 v42; // rbx
  __int64 v43; // rcx
  int v44; // ebx
  NTSTATUS v45; // eax
  _DWORD *j; // rax
  __int64 v47; // rcx
  bool v48; // cl
  bool v49; // al
  BOOL v50; // r13d
  int v51; // r12d
  __int64 v52; // rcx
  __int64 v53; // rcx
  __int64 *v54; // rdx
  __int64 *v55; // rax
  __int64 v56; // rcx
  BOOL v57; // r14d
  __int64 v58; // r15
  int v59; // ebx
  __int64 v60; // rcx
  __int64 *v61; // rbx
  __int64 *v62; // rcx
  __int64 *i; // rdx
  __int16 v64; // ax
  __int64 v65; // rcx
  BOOL v66; // r12d
  int v67; // r13d
  __int64 v68; // rcx
  BOOL v69; // r15d
  __int64 v70; // r12
  int v71; // r14d
  __int64 v72; // rcx
  __int64 *v73; // r13
  __int16 v74; // r8
  __int64 v75; // rcx
  bool v76; // zf
  __int64 v77; // rax
  __int64 v78; // rdx
  int v79; // edx
  int v80; // edx
  __int64 v81; // rdx
  __int64 v82; // rax
  __int64 v83; // rdx
  __int64 v84; // rax
  char v85; // [rsp+40h] [rbp-118h]
  int v86; // [rsp+44h] [rbp-114h] BYREF
  int v87[2]; // [rsp+48h] [rbp-110h]
  PVOID EcpContext; // [rsp+50h] [rbp-108h] BYREF
  struct _UNICODE_STRING FirstName; // [rsp+60h] [rbp-F8h] BYREF
  PVOID v90; // [rsp+70h] [rbp-E8h] BYREF
  struct _ECP_LIST *v91; // [rsp+78h] [rbp-E0h]
  struct _ECP_LIST *ExtraCreateParameter[2]; // [rsp+80h] [rbp-D8h] BYREF
  PECP_LIST EcpList; // [rsp+90h] [rbp-C8h] BYREF
  struct _UNICODE_STRING RemainingName; // [rsp+98h] [rbp-C0h] BYREF
  _QWORD *v95; // [rsp+A8h] [rbp-B0h]
  UNICODE_STRING Path; // [rsp+B0h] [rbp-A8h] BYREF
  PVOID v97; // [rsp+C0h] [rbp-98h]
  struct _UNICODE_STRING v98; // [rsp+D0h] [rbp-88h] BYREF
  struct _UNICODE_STRING v99; // [rsp+E0h] [rbp-78h]
  _BYTE v100[32]; // [rsp+F0h] [rbp-68h] BYREF

  v95 = a4;
  Scb = (__int16 *)a2;
  *(_QWORD *)v87 = a1;
  FirstName = 0;
  RemainingName = 0;
  v99 = 0;
  memset(v100, 0, sizeof(v100));
  *a6 = *a5;
  if ( !a6->Length || *(_DWORD *)(a2 + 256) != 160 || *a6->Buffer == 58 )
    return 0;
  v8 = 0;
  v9 = *(_QWORD *)(a3 + 96);
  v10 = *(_QWORD *)(v9 + 328);
  if ( !v10 )
    goto LABEL_5;
  v50 = 1;
  v91 = *(struct _ECP_LIST **)(a3 + 184);
  v51 = 0;
  if ( !ExIsResourceAcquiredSharedLite(*(PERESOURCE *)(v10 + 136)) )
  {
    ExAcquireResourceSharedLite(*(PERESOURCE *)(*(_QWORD *)(v9 + 328) + 136LL), 1u);
    v51 = 1;
  }
  v52 = *(_QWORD *)(v9 + 328);
  if ( (*(_DWORD *)(v52 + 4) & 1) != 0 )
  {
    v81 = *(_QWORD *)(v52 + 24);
    if ( v81 )
      v50 = v91 == *(struct _ECP_LIST **)(v81 + 232);
  }
  if ( v51 == 1 )
    ExReleaseResourceLite(*(PERESOURCE *)(v52 + 136));
  if ( v50 )
    goto LABEL_5;
  ExAcquireResourceSharedLite(*(PERESOURCE *)(*(_QWORD *)(v9 + 328) + 136LL), 1u);
  v53 = *(_QWORD *)(v9 + 328);
  v54 = (__int64 *)(v53 + 88);
  v55 = *(__int64 **)(v53 + 88);
  if ( v55 == (__int64 *)(v53 + 88) )
    goto LABEL_129;
  do
  {
    v73 = v55;
    v74 = *((_WORD *)v55 + 39);
    if ( (v74 & 1) != 0 && (v74 & 8) == 0 )
      break;
    v55 = (__int64 *)*v55;
  }
  while ( v55 != v54 );
  if ( v55 == v54 )
  {
LABEL_129:
    ExReleaseResourceLite(*(PERESOURCE *)(v53 + 136));
LABEL_5:
    v11 = *(_DWORD *)(v9 + 176);
    goto LABEL_6;
  }
  if ( !v73 )
    goto LABEL_5;
  v11 = *((_DWORD *)v73 + 16);
  ExReleaseResourceLite(*(PERESOURCE *)(v53 + 136));
LABEL_6:
  if ( (v11 & 0x400) == 0 )
  {
    v12 = *(_QWORD *)v87;
LABEL_8:
    ExistingLcb = 0;
    if ( v8 )
      return 0;
LABEL_9:
    Path = *a6;
    FsRtlDissectName(&Path, &FirstName, &RemainingName);
    if ( !RemainingName.Length || *RemainingName.Buffer != 92 )
    {
      v14 = *(_QWORD *)(a3 + 232);
      if ( v14
        && *(_WORD *)v14 >= 8u
        && (*(_DWORD *)(v14 + 4) & 0x10) != 0
        && (*(_DWORD *)(*((_QWORD *)Scb + 23) + 16LL) & 0x400) != 0 )
      {
        if ( NtfsStatusDebugFlags )
          NtfsStatusTraceAndDebugInternal(v12, 0xC00004BA, 0x1B0190u);
        NtfsRaiseStatusInternal(v12, -1073740614, 0, 0, 1769872);
      }
      ExAcquirePushLockSharedEx(*((_QWORD *)Scb + 23) + 344LL, 0);
      v99 = FirstName;
      v15 = *(unsigned int *)(a3 + 156);
      if ( (v15 & 0x20) != 0
        && ((v16 = *(_QWORD *)(a3 + 232)) != 0 && *(_WORD *)v16 >= 8u && (*(_DWORD *)(v16 + 4) & 8) != 0
         || (*(_DWORD *)(*((_QWORD *)Scb + 23) + 16LL) & 0x400) == 0) )
      {
        if ( (*(_DWORD *)(*((_QWORD *)Scb + 23) + 16LL) & 0x400) != 0 )
        {
          LODWORD(v15) = v15 | 0x1000;
          *(_DWORD *)(a3 + 156) = v15;
        }
        MatchingElementGenericTableAvl = (__int64)FsLibLookupFirstMatchingElementGenericTableAvl(
                                                    (__int64)(Scb + 348),
                                                    v15,
                                                    (__int64)v100,
                                                    ExtraCreateParameter);
      }
      else
      {
        LODWORD(v15) = v15 | 0x1000;
        *(_DWORD *)(a3 + 156) = v15;
        MatchingElementGenericTableAvl = FsLibLookupElementGenericTableAvl((__int64)(Scb + 348), v15, (__int64)v100);
      }
      if ( !MatchingElementGenericTableAvl )
      {
        ExReleasePushLockEx(*((_QWORD *)Scb + 23) + 344LL, 0);
        return ExistingLcb;
      }
      while ( 1 )
      {
        v24 = (PVOID)(MatchingElementGenericTableAvl - 88);
        EcpContext = (PVOID)(MatchingElementGenericTableAvl - 88);
        if ( (*(_DWORD *)(a3 + 156) & 0x20) != 0
          && ((v25 = *(_QWORD *)(a3 + 232)) != 0 && *(_WORD *)v25 >= 8u && (*(_DWORD *)(v25 + 4) & 8) != 0
           || (*(_DWORD *)(*((_QWORD *)Scb + 23) + 16LL) & 0x400) == 0) )
        {
          memmove(FirstName.Buffer, *((const void **)v24 + 10), FirstName.Length);
          v24 = EcpContext;
        }
        *a6 = RemainingName;
        v98 = FirstName;
        if ( ExistingLcb && (*(_BYTE *)(ExistingLcb[24] + 65LL) & 3) == 2 )
          *(_DWORD *)(a3 + 156) |= 1u;
        if ( RemainingName.Length && (*(_DWORD *)(a3 + 156) & 0x400) != 0 )
        {
          v26 = 16;
        }
        else
        {
          v26 = 0;
          *(_DWORD *)(a3 + 156) &= ~0x400u;
        }
        v86 = v26;
        v27 = (struct _ECP_LIST *)*((_QWORD *)v24 + 6);
        ExtraCreateParameter[0] = v27;
        v91 = v27;
        v28 = (volatile signed __int32 *)*((_QWORD *)Scb + 23);
        *(_QWORD *)&Path.Length = v28;
        EcpList = (PECP_LIST)v28;
        v85 = *(_BYTE *)(*((_QWORD *)v24 + 24) + 65LL);
        v29 = *(_QWORD *)v87;
        if ( (unsigned __int8)NtfsAcquireFcbWithPaging(*(__int64 *)v87, (__int64)v27, 0, v26 | 2u) )
        {
          ExReleasePushLockEx(*((_QWORD *)Scb + 23) + 344LL, 0);
          NtfsReleaseScbWithPaging(v29, (__int64)Scb);
          v30 = EcpContext;
        }
        else
        {
          ExAcquirePushLockSharedEx(*((_QWORD *)v27 + 12) + 656LL, 0);
          _InterlockedIncrement((volatile signed __int32 *)v27 + 7);
          _InterlockedIncrement(v28 + 7);
          ExReleasePushLockEx(*((_QWORD *)v27 + 12) + 656LL, 0);
          ExReleasePushLockEx(*((_QWORD *)Scb + 23) + 344LL, 0);
          if ( *((_QWORD *)v27 + 14) )
            *(_DWORD *)(v29 + 4) |= 0x10000u;
          NtfsReleaseScbWithPaging(v29, (__int64)Scb);
          NtfsAcquireFcbWithPaging(v29, (__int64)v27, 0, v26);
          *(_QWORD *)(a3 + 96) = v27;
          EcpContext = NtfsFindExistingLcb(v75, (__int64)v28, (__int64)v27, (const void **)&FirstName, v85, 0);
          v97 = EcpContext;
          ExAcquirePushLockSharedEx(*((_QWORD *)v27 + 12) + 656LL, 0);
          _InterlockedDecrement((volatile signed __int32 *)v27 + 7);
          _InterlockedDecrement(v28 + 7);
          ExReleasePushLockEx(*((_QWORD *)v27 + 12) + 656LL, 0);
          v30 = EcpContext;
          if ( !EcpContext )
            NtfsRaiseStatusInternal(v29, -1073741608, 0, 0, 1770079);
        }
        *v95 = v30;
        *(_QWORD *)(a3 + 96) = v27;
        if ( (*((_DWORD *)v27 + 1) & 8) == 0 || (*((_DWORD *)v27 + 44) & 0x10000000) == 0 || !a6->Length )
          return EcpContext;
        v31 = 0;
        v32 = *((_QWORD *)v27 + 41);
        if ( !v32 )
          goto LABEL_49;
        v57 = 1;
        v58 = *(_QWORD *)(a3 + 184);
        v59 = 0;
        if ( !ExIsResourceAcquiredSharedLite(*(PERESOURCE *)(v32 + 136)) )
        {
          ExAcquireResourceSharedLite(*(PERESOURCE *)(*((_QWORD *)v27 + 41) + 136LL), 1u);
          v59 = 1;
        }
        v60 = *((_QWORD *)v27 + 41);
        if ( (*(_DWORD *)(v60 + 4) & 1) != 0 )
        {
          v82 = *(_QWORD *)(v60 + 24);
          if ( v82 )
            v57 = v58 == *(_QWORD *)(v82 + 232);
        }
        if ( v59 == 1 )
          ExReleaseResourceLite(*(PERESOURCE *)(v60 + 136));
        if ( v57 )
          goto LABEL_49;
        v61 = 0;
        ExAcquireResourceSharedLite(*(PERESOURCE *)(*((_QWORD *)v27 + 41) + 136LL), 1u);
        v62 = (__int64 *)(*((_QWORD *)v27 + 41) + 88LL);
        for ( i = (__int64 *)*v62; i != v62; i = (__int64 *)*i )
        {
          v61 = i;
          v64 = *((_WORD *)i + 39);
          if ( (v64 & 1) != 0 && (v64 & 8) == 0 )
            break;
        }
        v65 = *((_QWORD *)v27 + 41);
        if ( i == (__int64 *)(v65 + 88) )
          break;
        if ( !v61 )
          goto LABEL_49;
        v33 = *((_DWORD *)v61 + 16);
        ExReleaseResourceLite(*(PERESOURCE *)(v65 + 136));
LABEL_50:
        if ( (v33 & 0x400) != 0 )
        {
          v42 = *(_QWORD *)(a3 + 96);
          LODWORD(v90) = 0;
          v43 = *(_QWORD *)(v42 + 328);
          if ( !v43 )
            goto LABEL_83;
          v69 = 1;
          v70 = *(_QWORD *)(a3 + 184);
          v71 = 0;
          if ( !ExIsResourceAcquiredSharedLite(*(PERESOURCE *)(v43 + 136)) )
          {
            ExAcquireResourceSharedLite(*(PERESOURCE *)(*(_QWORD *)(v42 + 328) + 136LL), 1u);
            v71 = 1;
          }
          v72 = *(_QWORD *)(v42 + 328);
          if ( (*(_DWORD *)(v72 + 4) & 1) != 0 )
          {
            v84 = *(_QWORD *)(v72 + 24);
            if ( v84 )
              v69 = v70 == *(_QWORD *)(v84 + 232);
          }
          if ( v71 == 1 )
            ExReleaseResourceLite(*(PERESOURCE *)(v72 + 136));
          if ( v69 )
          {
LABEL_83:
            v44 = *(_DWORD *)(v42 + 180);
          }
          else
          {
            TxfGetTransFileInfo(v42, &EcpList, &v90);
            v44 = (int)v90;
          }
          EcpList = 0;
          v90 = 0;
          if ( *(_DWORD *)(a3 + 200) != v44 )
          {
            *(_DWORD *)(a3 + 200) = v44;
            *(_QWORD *)(a3 + 216) = 0;
            if ( IoGetIrpExtraCreateParameter(*(PIRP *)(*(_QWORD *)v87 + 112LL), &EcpList) >= 0 )
            {
              if ( EcpList )
              {
                v45 = FsRtlFindExtraCreateParameter(EcpList, &ECP_TYPE_OPEN_REPARSE_GUID, &v90, 0);
                if ( v45 < 0 )
                {
                  if ( NtfsStatusDebugFlags
                    && (unsigned int)v45 < 0xFFFFFFED
                    && v45 != -1073741802
                    && v45 != -1073741807
                    && (unsigned int)(v45 + 2147483643) > 1
                    && v45 != -1073741608 )
                  {
                    NtfsStatusTraceAndDebugInternal(0, v45, 0xA0980u);
                  }
                }
                else
                {
                  for ( j = *(_DWORD **)v90; j != v90; j = *(_DWORD **)j )
                  {
                    if ( j[4] == v44 )
                    {
                      *(_QWORD *)(a3 + 216) = j;
                      break;
                    }
                  }
                }
              }
            }
          }
          v48 = (*(_DWORD *)(*(_QWORD *)(a3 + 96) + 176LL) & 0x10000000) != 0
             && (unsigned __int8)FsRtlIsNonEmptyDirectoryReparsePointAllowed(*(unsigned int *)(a3 + 200));
          v49 = !a6->Length || *a6->Buffer == 58;
          if ( !v48 )
          {
            v56 = *(_QWORD *)(a3 + 216);
            if ( v49 )
            {
              v80 = *(_DWORD *)(*(_QWORD *)(a3 + 176) + 16LL) & 0x200000;
              if ( !v56 )
              {
                v31 = v80 == 0;
                v27 = ExtraCreateParameter[0];
                goto LABEL_51;
              }
              if ( v80 && (*(_DWORD *)(v56 + 20) & 0x40) == 0 )
                goto LABEL_112;
              v76 = (*(_DWORD *)(v56 + 20) & 0x20) == 0;
            }
            else
            {
              if ( !v56 )
                return EcpContext;
              v76 = (*(_DWORD *)(v56 + 20) & 0x10) == 0;
            }
            if ( !v76 )
              return EcpContext;
          }
LABEL_112:
          v27 = ExtraCreateParameter[0];
        }
LABEL_51:
        if ( v31 )
          return EcpContext;
        v34 = EcpContext;
        Scb = (__int16 *)*((_QWORD *)EcpContext + 17);
        v35 = *(_QWORD *)v87;
        if ( Scb || (Scb = NtfsCreateScb(*(__int64 *)v87, (__int64)v27, 160, &NtfsFileNameIndex, v86 != 0, 0, 0)) != 0 )
        {
          v36 = *(_QWORD *)(a3 + 232);
          if ( v36 )
          {
            if ( *(_WORD *)v36 >= 8u
              && (*(_DWORD *)(v36 + 4) & 0x10) != 0
              && (*(_DWORD *)(*((_QWORD *)Scb + 23) + 16LL) & 0x400) != 0 )
            {
              if ( NtfsStatusDebugFlags )
                NtfsStatusTraceAndDebugInternal(v35, 0xC00004BA, 0x1B02B9u);
              NtfsRaiseStatusInternal(v35, -1073740614, 0, 0, 1770169);
            }
          }
        }
        ExistingLcb = v34;
        if ( !Scb )
          goto LABEL_92;
        if ( !Scb[328] )
          goto LABEL_66;
        *(UNICODE_STRING *)ExtraCreateParameter = *a6;
        FsRtlDissectName((UNICODE_STRING *)ExtraCreateParameter, &FirstName, &RemainingName);
        if ( RemainingName.Length && *RemainingName.Buffer == 92 )
        {
          if ( NtfsStatusDebugFlags )
            NtfsStatusTraceAndDebugInternal(0, 0xC0000033, 0x442EA3u);
          if ( NtfsStatusDebugFlags )
            NtfsStatusTraceAndDebugInternal(v35, 0xC0000033, 0x1B02D7u);
          NtfsRaiseStatusInternal(v35, -1073741773, 0, 0, 1770199);
        }
        ExAcquirePushLockSharedEx(*((_QWORD *)Scb + 23) + 344LL, 0);
        v34 = 0;
        v99 = FirstName;
        v37 = *(unsigned int *)(a3 + 156);
        if ( (v37 & 0x20) != 0
          && ((v38 = *(_QWORD *)(a3 + 232)) != 0 && *(_WORD *)v38 >= 8u && (*(_DWORD *)(v38 + 4) & 8) != 0
           || (*(_DWORD *)(*((_QWORD *)Scb + 23) + 16LL) & 0x400) == 0) )
        {
          if ( (*(_DWORD *)(*((_QWORD *)Scb + 23) + 16LL) & 0x400) != 0 )
          {
            LODWORD(v37) = v37 | 0x1000;
            *(_DWORD *)(a3 + 156) = v37;
          }
          MatchingElementGenericTableAvl = (__int64)FsLibLookupFirstMatchingElementGenericTableAvl(
                                                      (__int64)(Scb + 348),
                                                      v37,
                                                      (__int64)v100,
                                                      ExtraCreateParameter);
        }
        else
        {
          LODWORD(v37) = v37 | 0x1000;
          *(_DWORD *)(a3 + 156) = v37;
          MatchingElementGenericTableAvl = FsLibLookupElementGenericTableAvl((__int64)(Scb + 348), v37, (__int64)v100);
        }
        if ( !MatchingElementGenericTableAvl )
        {
          ExReleasePushLockEx(*((_QWORD *)Scb + 23) + 344LL, 0);
LABEL_66:
          if ( v34 && (Scb[328] || !*(_WORD *)(ExistingLcb[3] + 656LL)) )
          {
            v12 = *(_QWORD *)v87;
            goto LABEL_9;
          }
LABEL_92:
          if ( v86 )
          {
            ExAcquirePushLockSharedEx(*((_QWORD *)v27 + 12) + 656LL, 0);
            _InterlockedIncrement((volatile signed __int32 *)v27 + 7);
            ExReleasePushLockEx(*((_QWORD *)v27 + 12) + 656LL, 0);
            if ( Scb )
              _InterlockedIncrement((volatile signed __int32 *)Scb + 53);
            NtfsReleaseFcbWithPaging(v35, (__int64)v27);
            NtfsAcquireFcbWithPaging(v35, (__int64)v27, 0, 0);
            if ( Scb )
              _InterlockedDecrement((volatile signed __int32 *)Scb + 53);
            ExAcquirePushLockSharedEx(*((_QWORD *)v27 + 12) + 656LL, 0);
            _InterlockedDecrement((volatile signed __int32 *)v27 + 7);
            ExReleasePushLockEx(*((_QWORD *)v27 + 12) + 656LL, 0);
            *(_DWORD *)(a3 + 156) &= ~0x400u;
            ExistingLcb = NtfsFindExistingLcb(v47, *(__int64 *)&Path.Length, (__int64)v27, (const void **)&v98, v85, 0);
            if ( !ExistingLcb )
              NtfsRaiseStatusInternal(v35, -1073741608, 0, 0, 1770349);
          }
          if ( Scb )
          {
            NtfsSnapshotScb(v35, (__int64)Scb);
          }
          else
          {
            Scb = NtfsCreateScb(v35, (__int64)v27, 160, &NtfsFileNameIndex, 0, 0, 0);
            if ( Scb )
            {
              v77 = *(_QWORD *)(a3 + 232);
              if ( v77 )
              {
                if ( *(_WORD *)v77 >= 8u
                  && (*(_DWORD *)(v77 + 4) & 0x10) != 0
                  && (*(_DWORD *)(*((_QWORD *)Scb + 23) + 16LL) & 0x400) != 0 )
                {
                  if ( NtfsStatusDebugFlags )
                    NtfsStatusTraceAndDebugInternal(v35, 0xC00004BA, 0x1B038Au);
                  NtfsRaiseStatusInternal(v35, -1073740614, 0, 0, 1770378);
                }
              }
            }
          }
          if ( !Scb[328] )
          {
            v78 = ExistingLcb[3];
            if ( *(_WORD *)(v78 + 656) )
            {
              NtfsAcquireFcbWithPaging(v35, *(_QWORD *)(v78 + 184), 0, 0);
              NtfsUpdateNormalizedName(v35, ExistingLcb[3], (__int64)Scb, 0, 0);
              NtfsReleaseScbWithPaging(v35, ExistingLcb[3]);
            }
          }
          v12 = *(_QWORD *)v87;
          if ( !v34 )
            return ExistingLcb;
          goto LABEL_9;
        }
      }
      ExReleaseResourceLite(*(PERESOURCE *)(v65 + 136));
LABEL_49:
      v33 = *((_DWORD *)v27 + 44);
      goto LABEL_50;
    }
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(0, 0xC0000033, 0x442EA3u);
    return 0;
  }
  v19 = *(_QWORD *)(a3 + 96);
  v86 = 0;
  v20 = *(_QWORD *)(v19 + 328);
  if ( !v20 )
    goto LABEL_24;
  v66 = 1;
  v91 = *(struct _ECP_LIST **)(a3 + 184);
  v67 = 0;
  if ( !ExIsResourceAcquiredSharedLite(*(PERESOURCE *)(v20 + 136)) )
  {
    ExAcquireResourceSharedLite(*(PERESOURCE *)(*(_QWORD *)(v19 + 328) + 136LL), 1u);
    v67 = 1;
  }
  v68 = *(_QWORD *)(v19 + 328);
  if ( (*(_DWORD *)(v68 + 4) & 1) != 0 )
  {
    v83 = *(_QWORD *)(v68 + 24);
    if ( v83 )
      v66 = v91 == *(struct _ECP_LIST **)(v83 + 232);
  }
  if ( v67 == 1 )
    ExReleaseResourceLite(*(PERESOURCE *)(v68 + 136));
  if ( v66 )
  {
LABEL_24:
    v21 = *(_DWORD *)(v19 + 180);
  }
  else
  {
    TxfGetTransFileInfo(v19, &v90, &v86);
    v21 = v86;
  }
  ExtraCreateParameter[0] = 0;
  EcpContext = 0;
  v12 = *(_QWORD *)v87;
  if ( *(_DWORD *)(a3 + 200) != v21 )
  {
    *(_DWORD *)(a3 + 200) = v21;
    *(_QWORD *)(a3 + 216) = 0;
    if ( IoGetIrpExtraCreateParameter(*(PIRP *)(v12 + 112), ExtraCreateParameter) >= 0 )
    {
      if ( ExtraCreateParameter[0] )
      {
        v22 = FsRtlFindExtraCreateParameter(ExtraCreateParameter[0], &ECP_TYPE_OPEN_REPARSE_GUID, &EcpContext, 0);
        if ( v22 < 0 )
        {
          if ( NtfsStatusDebugFlags
            && (unsigned int)v22 < 0xFFFFFFED
            && v22 != -1073741802
            && v22 != -1073741807
            && (unsigned int)(v22 + 2147483643) > 1
            && v22 != -1073741608 )
          {
            NtfsStatusTraceAndDebugInternal(0, v22, 0xA0980u);
          }
        }
        else
        {
          for ( k = *(_DWORD **)EcpContext; k != EcpContext; k = *(_DWORD **)k )
          {
            if ( k[4] == v21 )
            {
              *(_QWORD *)(a3 + 216) = k;
              break;
            }
          }
        }
      }
    }
  }
  v39 = (*(_DWORD *)(*(_QWORD *)(a3 + 96) + 176LL) & 0x10000000) != 0
     && (unsigned __int8)FsRtlIsNonEmptyDirectoryReparsePointAllowed(*(unsigned int *)(a3 + 200));
  v40 = !a6->Length || *a6->Buffer == 58;
  if ( v39 )
    goto LABEL_8;
  v41 = *(_QWORD *)(a3 + 216);
  if ( v40 )
  {
    v79 = *(_DWORD *)(*(_QWORD *)(a3 + 176) + 16LL) & 0x200000;
    if ( !v41 )
    {
      v8 = v79 == 0;
      goto LABEL_8;
    }
    if ( v79 && (*(_DWORD *)(v41 + 20) & 0x40) == 0 || (*(_DWORD *)(v41 + 20) & 0x20) == 0 )
      goto LABEL_8;
    return 0;
  }
  if ( !v41 )
    return 0;
  if ( (*(_DWORD *)(v41 + 20) & 0x10) == 0 )
    goto LABEL_8;
  return 0;
}

```

## disassembly

```asm
0x1401b92c0  mov     r11, rsp
0x1401b92c3  push    rbx
0x1401b92c4  push    rsi
0x1401b92c5  push    rdi
0x1401b92c6  push    r12
0x1401b92c8  push    r13
0x1401b92ca  push    r14
0x1401b92cc  push    r15
0x1401b92ce  sub     rsp, 120h
0x1401b92d5  mov     rax, cs:__security_cookie
0x1401b92dc  xor     rax, rsp
0x1401b92df  mov     [rsp+158h+var_48], rax
0x1401b92e7  mov     [rsp+158h+var_B0], r9
0x1401b92ef  mov     rdi, r8
0x1401b92f2  mov     rbx, rdx
0x1401b92f5  mov     qword ptr [rsp+158h+var_110], rcx
0x1401b92fa  mov     rsi, [rsp+158h+arg_28]
0x1401b9302  xorps   xmm0, xmm0
0x1401b9305  movups  xmmword ptr [rsp+158h+FirstName.Length], xmm0
0x1401b930a  xorps   xmm1, xmm1
0x1401b930d  movups  xmmword ptr [rsp+158h+RemainingName.Length], xmm1
0x1401b9315  movups  xmmword ptr [r11-78h], xmm0
0x1401b931a  movups  xmmword ptr [r11-68h], xmm0
0x1401b931f  movups  xmmword ptr [r11-58h], xmm0
0x1401b9324  mov     rax, [rsp+158h+arg_20]
0x1401b932c  movups  xmm0, xmmword ptr [rax]
0x1401b932f  movups  xmmword ptr [rsi], xmm0
0x1401b9332  cmp     word ptr [rsi], 0
0x1401b9336  jz      loc_1401B94E1
0x1401b933c  cmp     dword ptr [rdx+100h], 0A0h
0x1401b9346  jnz     loc_1401B94E1
0x1401b934c  mov     rax, [rsi+8]
0x1401b9350  cmp     word ptr [rax], 3Ah ; ':'
0x1401b9354  jz      loc_1401B94E1
0x1401b935a  xor     r15b, r15b
0x1401b935d  mov     r14, [r8+60h]
0x1401b9361  mov     rcx, [r14+148h]
0x1401b9368  test    rcx, rcx
0x1401b936b  jnz     loc_1401B9C8E
0x1401b9371  mov     r14d, [r14+0B0h]
0x1401b9378  bt      r14d, 0Ah
0x1401b937d  jb      loc_1401B94E8
0x1401b9383  mov     r12, qword ptr [rsp+158h+var_110]
0x1401b9388  xor     r14d, r14d
0x1401b938b  test    r15b, r15b
0x1401b938e  jnz     loc_1401B94E1
0x1401b9394  movups  xmm0, xmmword ptr [rsi]
0x1401b9397  movaps  xmmword ptr [rsp+158h+Path.Length], xmm0
0x1401b939f  lea     r8, [rsp+158h+RemainingName]; RemainingName
0x1401b93a7  lea     rdx, [rsp+158h+FirstName]; FirstName
0x1401b93ac  lea     rcx, [rsp+158h+Path]; Path
0x1401b93b4  call    cs:__imp_FsRtlDissectName
0x1401b93bb  nop     dword ptr [rax+rax+00h]
0x1401b93c0  cmp     [rsp+158h+RemainingName.Length], 0
0x1401b93c9  jz      short loc_1401B93DD
0x1401b93cb  mov     rax, [rsp+158h+RemainingName.Buffer]
0x1401b93d3  cmp     word ptr [rax], 5Ch ; '\'
0x1401b93d7  jz      loc_1401B94D2
0x1401b93dd  mov     rax, [rdi+0E8h]
0x1401b93e4  test    rax, rax
0x1401b93e7  jnz     loc_1401BA09B
0x1401b93ed  mov     rcx, [rbx+0B8h]
0x1401b93f4  add     rcx, 158h
0x1401b93fb  xor     edx, edx
0x1401b93fd  call    cs:__imp_ExAcquirePushLockSharedEx
0x1401b9404  nop     dword ptr [rax+rax+00h]
0x1401b9409  movzx   eax, [rsp+158h+FirstName.Length]
0x1401b940e  mov     [rsp+158h+var_78], ax
0x1401b9416  mov     eax, dword ptr [rsp+158h+FirstName.MaximumLength]
0x1401b941a  mov     [rsp+158h+var_76], eax
0x1401b9421  movzx   eax, word ptr [rsp+158h+FirstName+6]
0x1401b9426  mov     [rsp+158h+var_72], ax
0x1401b942e  mov     rax, [rsp+158h+FirstName.Buffer]
0x1401b9433  mov     [rsp+158h+var_70], rax
0x1401b943b  mov     edx, [rdi+9Ch]
0x1401b9441  test    dl, 20h
0x1401b9444  jz      loc_1401B9B7F
0x1401b944a  mov     rax, [rdi+0E8h]
0x1401b9451  test    rax, rax
0x1401b9454  jnz     loc_1401BA081
0x1401b945a  mov     rax, [rbx+0B8h]
0x1401b9461  test    dword ptr [rax+10h], 400h
0x1401b9468  jnz     loc_1401B9B7F
0x1401b946e  mov     rax, [rbx+0B8h]
0x1401b9475  test    dword ptr [rax+10h], 400h
0x1401b947c  jz      short loc_1401B9488
0x1401b947e  bts     edx, 0Ch
0x1401b9482  mov     [rdi+9Ch], edx
0x1401b9488  lea     rcx, [rbx+2B8h]
0x1401b948f  lea     r9, [rsp+158h+ExtraCreateParameter]
0x1401b9497  lea     r8, [rsp+158h+var_68]
0x1401b949f  call    FsLibLookupFirstMatchingElementGenericTableAvl
0x1401b94a4  test    rax, rax
0x1401b94a7  jnz     loc_1401B95BD
0x1401b94ad  mov     rcx, [rbx+0B8h]
0x1401b94b4  add     rcx, 158h
0x1401b94bb  xor     edx, edx
0x1401b94bd  call    cs:__imp_ExReleasePushLockEx
0x1401b94c4  nop     dword ptr [rax+rax+00h]
0x1401b94c9  mov     rax, r14
0x1401b94cc  jmp     loc_1401BA5F9
0x1401b94d2  movzx   eax, cs:NtfsStatusDebugFlags
0x1401b94d9  test    al, al
0x1401b94db  jnz     loc_1401BA5BE
0x1401b94e1  xor     eax, eax
0x1401b94e3  jmp     loc_1401BA5F9
0x1401b94e8  mov     r14, [rdi+60h]
0x1401b94ec  mov     [rsp+158h+var_114], 0
0x1401b94f4  mov     rcx, [r14+148h]
0x1401b94fb  test    rcx, rcx
0x1401b94fe  jnz     loc_1401B9F48
0x1401b9504  mov     r14d, [r14+0B4h]
0x1401b950b  mov     [rsp+158h+ExtraCreateParameter], 0
0x1401b9517  mov     [rsp+158h+EcpContext], 0
0x1401b9520  mov     r12, qword ptr [rsp+158h+var_110]
0x1401b9525  cmp     [rdi+0C8h], r14d
0x1401b952c  jz      loc_1401B98F4
0x1401b9532  mov     [rdi+0C8h], r14d
0x1401b9539  mov     qword ptr [rdi+0D8h], 0
0x1401b9544  lea     rdx, [rsp+158h+ExtraCreateParameter]; ExtraCreateParameter
0x1401b954c  mov     rcx, [r12+70h]; Irp
0x1401b9551  call    cs:__imp_IoGetIrpExtraCreateParameter
0x1401b9558  nop     dword ptr [rax+rax+00h]
0x1401b955d  test    eax, eax
0x1401b955f  js      loc_1401B98F4
0x1401b9565  mov     rcx, [rsp+158h+ExtraCreateParameter]; EcpList
0x1401b956d  test    rcx, rcx
0x1401b9570  jz      loc_1401B98F4
0x1401b9576  xor     r9d, r9d; EcpContextSize
0x1401b9579  lea     r8, [rsp+158h+EcpContext]; EcpContext
0x1401b957e  lea     rdx, ECP_TYPE_OPEN_REPARSE_GUID; EcpType
0x1401b9585  call    cs:__imp_FsRtlFindExtraCreateParameter
0x1401b958c  nop     dword ptr [rax+rax+00h]
0x1401b9591  mov     edx, eax
0x1401b9593  test    eax, eax
0x1401b9595  js      loc_1401B9C08
0x1401b959b  mov     rcx, [rsp+158h+EcpContext]
0x1401b95a0  mov     rax, [rcx]
0x1401b95a3  xchg    ax, ax
0x1401b95a5  cmp     rax, rcx
0x1401b95a8  jz      loc_1401B98F4
0x1401b95ae  cmp     [rax+10h], r14d
0x1401b95b2  jz      loc_1401B98ED
0x1401b95b8  mov     rax, [rax]
0x1401b95bb  jmp     short loc_1401B95A5
0x1401b95bd  lea     rdx, [rax-58h]
0x1401b95c1  mov     [rsp+158h+EcpContext], rdx
0x1401b95c6  mov     eax, [rdi+9Ch]
0x1401b95cc  test    al, 20h
0x1401b95ce  jz      short loc_1401B9609
0x1401b95d0  mov     rax, [rdi+0E8h]
0x1401b95d7  test    rax, rax
0x1401b95da  jnz     loc_1401BA132
0x1401b95e0  mov     rax, [rbx+0B8h]
0x1401b95e7  test    dword ptr [rax+10h], 400h
0x1401b95ee  jnz     short loc_1401B9609
0x1401b95f0  movzx   r8d, [rsp+158h+FirstName.Length]; Size
0x1401b95f6  mov     rdx, [rdx+50h]; Src
0x1401b95fa  mov     rcx, [rsp+158h+FirstName.Buffer]; void *
0x1401b95ff  call    memmove
0x1401b9604  mov     rdx, [rsp+158h+EcpContext]
0x1401b9609  movups  xmm0, xmmword ptr [rsp+158h+RemainingName.Length]
0x1401b9611  movups  xmmword ptr [rsi], xmm0
0x1401b9614  movaps  xmm1, xmmword ptr [rsp+158h+FirstName.Length]
0x1401b9619  movdqa  [rsp+158h+var_88], xmm1
0x1401b9622  test    r14, r14
0x1401b9625  jz      short loc_1401B9641
0x1401b9627  mov     rax, [r14+0C0h]
0x1401b962e  movzx   ecx, byte ptr [rax+41h]
0x1401b9632  and     cl, 3
0x1401b9635  cmp     cl, 2
0x1401b9638  jnz     short loc_1401B9641
0x1401b963a  or      dword ptr [rdi+9Ch], 1
0x1401b9641  cmp     [rsp+158h+RemainingName.Length], 0
0x1401b964a  jbe     loc_1401B9970
0x1401b9650  test    dword ptr [rdi+9Ch], 400h
0x1401b965a  jz      loc_1401B9970
0x1401b9660  mov     r15d, 10h
0x1401b9666  mov     [rsp+158h+var_114], r15d
0x1401b966b  mov     r12, [rdx+30h]
0x1401b966f  mov     [rsp+158h+ExtraCreateParameter], r12
0x1401b9677  mov     [rsp+158h+var_E0], r12
0x1401b967c  mov     r13, [rbx+0B8h]
0x1401b9683  mov     qword ptr [rsp+158h+Path.Length], r13
0x1401b968b  mov     [rsp+158h+EcpList], r13
0x1401b9693  mov     rax, [rdx+0C0h]
0x1401b969a  movzx   eax, byte ptr [rax+41h]
0x1401b969e  mov     [rsp+158h+var_118], al
0x1401b96a2  mov     r9d, r15d
0x1401b96a5  or      r9d, 2
0x1401b96a9  xor     r8d, r8d
0x1401b96ac  mov     rdx, r12
0x1401b96af  mov     r14, qword ptr [rsp+158h+var_110]
0x1401b96b4  mov     rcx, r14
0x1401b96b7  call    NtfsAcquireFcbWithPaging
0x1401b96bc  xor     edx, edx
0x1401b96be  test    al, al
0x1401b96c0  jz      loc_1401BA1F4
0x1401b96c6  mov     rcx, [rbx+0B8h]
0x1401b96cd  add     rcx, 158h
0x1401b96d4  call    cs:__imp_ExReleasePushLockEx
0x1401b96db  nop     dword ptr [rax+rax+00h]
0x1401b96e0  mov     rdx, rbx
0x1401b96e3  mov     rcx, r14
0x1401b96e6  call    NtfsReleaseScbWithPaging
0x1401b96eb  mov     rax, [rsp+158h+EcpContext]
0x1401b96f0  mov     rcx, [rsp+158h+var_B0]
0x1401b96f8  mov     [rcx], rax
0x1401b96fb  mov     [rdi+60h], r12
0x1401b96ff  mov     eax, [r12+4]
0x1401b9704  test    al, 8
0x1401b9706  jz      loc_1401B9E2C
0x1401b970c  mov     eax, [r12+0B0h]
0x1401b9714  bt      eax, 1Ch
0x1401b9718  jnb     loc_1401B9E2C
0x1401b971e  cmp     word ptr [rsi], 0
0x1401b9722  jz      loc_1401B9E2C
0x1401b9728  xor     r13b, r13b
0x1401b972b  mov     rcx, [r12+148h]
0x1401b9733  test    rcx, rcx
0x1401b9736  jnz     loc_1401B9E36
0x1401b973c  mov     ebx, [r12+0B0h]
0x1401b9744  bt      ebx, 0Ah
0x1401b9748  jb      loc_1401B9982
0x1401b974e  test    r13b, r13b
0x1401b9751  jnz     loc_1401B9E2C
0x1401b9757  mov     r15, [rsp+158h+EcpContext]
0x1401b975c  mov     rbx, [r15+88h]
0x1401b9763  mov     r13, qword ptr [rsp+158h+var_110]
0x1401b9768  test    rbx, rbx
0x1401b976b  jz      loc_1401BA33B
0x1401b9771  mov     rax, [rdi+0E8h]
0x1401b9778  test    rax, rax
0x1401b977b  jnz     loc_1401BA188
0x1401b9781  mov     r14, r15
0x1401b9784  test    rbx, rbx
0x1401b9787  jz      loc_1401B9A57
0x1401b978d  cmp     word ptr [rbx+290h], 0
0x1401b9795  jz      loc_1401B98C3
0x1401b979b  movups  xmm0, xmmword ptr [rsi]
0x1401b979e  movaps  xmmword ptr [rsp+158h+ExtraCreateParameter], xmm0
0x1401b97a6  lea     r8, [rsp+158h+RemainingName]; RemainingName
0x1401b97ae  lea     rdx, [rsp+158h+FirstName]; FirstName
0x1401b97b3  lea     rcx, [rsp+158h+ExtraCreateParameter]; Path
0x1401b97bb  call    cs:__imp_FsRtlDissectName
0x1401b97c2  nop     dword ptr [rax+rax+00h]
0x1401b97c7  cmp     [rsp+158h+RemainingName.Length], 0
0x1401b97d0  jz      short loc_1401B97E4
0x1401b97d2  mov     rax, [rsp+158h+RemainingName.Buffer]
0x1401b97da  cmp     word ptr [rax], 5Ch ; '\'
0x1401b97de  jz      loc_1401B9D5E
0x1401b97e4  mov     rcx, [rbx+0B8h]
0x1401b97eb  add     rcx, 158h
0x1401b97f2  xor     edx, edx
0x1401b97f4  call    cs:__imp_ExAcquirePushLockSharedEx
0x1401b97fb  nop     dword ptr [rax+rax+00h]
0x1401b9800  xor     r15d, r15d
0x1401b9803  movzx   eax, [rsp+158h+FirstName.Length]
0x1401b9808  mov     [rsp+158h+var_78], ax
0x1401b9810  mov     eax, dword ptr [rsp+158h+FirstName.MaximumLength]
0x1401b9814  mov     [rsp+158h+var_76], eax
0x1401b981b  movzx   eax, word ptr [rsp+158h+FirstName+6]
0x1401b9820  mov     [rsp+158h+var_72], ax
0x1401b9828  mov     rax, [rsp+158h+FirstName.Buffer]
0x1401b982d  mov     [rsp+158h+var_70], rax
0x1401b9835  mov     edx, [rdi+9Ch]
0x1401b983b  test    dl, 20h
0x1401b983e  jz      loc_1401B9C64
0x1401b9844  mov     rax, [rdi+0E8h]
0x1401b984b  test    rax, rax
0x1401b984e  jnz     loc_1401BA16E
0x1401b9854  mov     rax, [rbx+0B8h]
0x1401b985b  test    dword ptr [rax+10h], 400h
0x1401b9862  jnz     loc_1401B9C64
0x1401b9868  mov     rax, [rbx+0B8h]
0x1401b986f  test    dword ptr [rax+10h], 400h
0x1401b9876  jz      short loc_1401B9882
0x1401b9878  bts     edx, 0Ch
0x1401b987c  mov     [rdi+9Ch], edx
0x1401b9882  lea     rcx, [rbx+2B8h]
0x1401b9889  lea     r9, [rsp+158h+ExtraCreateParameter]
0x1401b9891  lea     r8, [rsp+158h+var_68]
0x1401b9899  call    FsLibLookupFirstMatchingElementGenericTableAvl
0x1401b989e  test    rax, rax
0x1401b98a1  jnz     loc_1401B95BD
0x1401b98a7  mov     rcx, [rbx+0B8h]
0x1401b98ae  add     rcx, 158h
0x1401b98b5  xor     edx, edx
0x1401b98b7  call    cs:__imp_ExReleasePushLockEx
0x1401b98be  nop     dword ptr [rax+rax+00h]
0x1401b98c3  test    rbx, rbx
0x1401b98c6  jz      loc_1401B9A57
0x1401b98cc  test    r15, r15
0x1401b98cf  jz      loc_1401B9A57
0x1401b98d5  cmp     word ptr [rbx+290h], 0
0x1401b98dd  jz      loc_1401BA1DD
0x1401b98e3  mov     r12, qword ptr [rsp+158h+var_110]
0x1401b98e8  jmp     loc_1401B9394
0x1401b98ed  mov     [rdi+0D8h], rax
0x1401b98f4  mov     rax, [rdi+60h]
  ... truncated ...
```
