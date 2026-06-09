# RefsSetLinkInfo

- ea: `0x1402a5720`
- end: `0x1402a6dca`
- name: `RefsSetLinkInfo`
- size: `5802`
- prototype: `__int64 __usercall@<rax>(struct _IRP_CONTEXT *@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `38`
- tags: `reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140319a38`

## callees

- `0x140038f80`
- `0x140081670`
- `0x14008dbd0`
- `0x14008f870`
- `0x140098160`
- `0x140099960`
- `0x1400a3bec`
- `0x1400ad0c8`
- `0x1400ae8fc`
- `0x1400aee68`
- `0x1400bd6f0`
- `0x1400ca788`
- `0x1400e1534`
- `0x1400f00b0`
- `0x14010ec14`
- `0x1401e9cb2`
- `0x1401e9ce0`
- `0x1401e9e40`
- `0x1401ea140`
- `0x1401ea660`
- `0x140285008`
- `0x1402853d4`
- `0x140285fa0`
- `0x1402877f8`
- `0x1402a3624`
- `0x1402a5720`
- `0x1402d1b48`
- `0x1402fec90`
- `0x1403000b0`
- `0x140308080`
- `0x14030fee0`
- `0x14031c8e0`
- `0x140324180`
- `0x140324c10`
- `0x1403277e4`
- `0x140327cf0`
- `0x140335bb4`
- `0x140338cb4`

## import_xrefs

- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x1402a6d03`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x140344540`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x1402a6d03`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x140344540`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1402a5b7f`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1402a5b7f`
- `ntoskrnl!SeAuditingHardLinkEventsWithContext` at `0x1402a6907`
- `ntoskrnl!SeAuditingHardLinkEventsWithContext` at `0x1402a6907`
- `ntoskrnl!SeAuditHardLinkCreation` at `0x1402a6bb0`
- `ntoskrnl!SeAuditHardLinkCreation` at `0x1402a6bb0`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x1402a68d6`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x1402a68d6`
- `ntoskrnl!ExReleaseFastResource` at `0x1402a6d1c`
- `ntoskrnl!ExReleaseFastResource` at `0x14034455d`
- `ntoskrnl!ExReleaseFastResource` at `0x1402a6d1c`
- `ntoskrnl!ExReleaseFastResource` at `0x14034455d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a6661`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a6bcb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a6be2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a6bf9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a6c9a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a6cb4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a6cd6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140344477`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034448f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403444a7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403444d4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403444ef`
- `ntoskrnl!ExFreePoolWithTag` at `0x140344513`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a6661`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a6bcb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a6be2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a6bf9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a6c9a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a6cb4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a6cd6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140344477`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034448f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403444a7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403444d4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403444ef`
- `ntoskrnl!ExFreePoolWithTag` at `0x140344513`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1402a634c`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1402a63cb`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1402a65c9`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1402a6a21`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1402a6b04`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1402a634c`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1402a63cb`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1402a65c9`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1402a6a21`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1402a6b04`

## pseudocode

```c
__int64 __fastcall RefsSetLinkInfo(struct _IRP_CONTEXT *a1, IRP *a2, struct _VCB *a3, struct _FCB *a4, __int64 a5)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbx
  LARGE_INTEGER ByteOffset; // r13
  _BYTE *v9; // rcx
  unsigned int v10; // r9d
  unsigned int v11; // r9d
  __int64 ActualAllocationLength; // r14
  __int64 v13; // rax
  char v15; // dl
  __int64 v16; // r12
  unsigned int v17; // edi
  unsigned int v18; // r9d
  struct _GENERIC_MAPPING *FileObjectGenericMapping; // rax
  ULONGLONG v20; // rdx
  __int64 v21; // rax
  struct _REFS_FILE_REFERENCE *v22; // rbx
  IndexSCB *v23; // r13
  __int64 v24; // rdx
  unsigned int v25; // r9d
  __int64 v26; // rdx
  WCHAR *v27; // rdx
  bool v28; // r12
  __int64 *v29; // rdx
  unsigned int v30; // r8d
  __int64 v31; // rcx
  __int64 v32; // r8
  unsigned int v33; // ecx
  int v34; // eax
  char v35; // al
  char v36; // bl
  struct _IRP_CONTEXT *v37; // rcx
  __int64 v38; // rcx
  struct _REFS_FILE_REFERENCE *v39; // rbx
  unsigned int v40; // ecx
  __int64 v41; // rcx
  WCHAR *PoolWithTag; // rax
  USHORT v43; // cx
  const struct _DIR_INDEX_ENTRY *v44; // rbx
  unsigned __int64 CmsKeyLength; // r9
  __int64 v46; // rax
  void *v47; // rsp
  PVOID v48; // rbx
  unsigned int v49; // edx
  __int64 v50; // rcx
  WCHAR *v51; // r9
  char *v52; // rbx
  int v53; // r12d
  __int64 v54; // rcx
  char v55; // dl
  ULONG v56; // r8d
  __int64 v57; // rcx
  ULONG v58; // edx
  ULONG v59; // r10d
  PVOID *v60; // r12
  unsigned __int16 v61; // ax
  unsigned int v62; // ebx
  unsigned int v63; // r9d
  struct _VCB *v64; // rbx
  unsigned int v65; // ebx
  struct _VCB *v66; // rbx
  __int64 v67; // rdx
  WCHAR *v68; // rcx
  __int64 v69; // r8
  __int64 v70; // rbx
  struct _SCB *CompletionRoutine; // [rsp+20h] [rbp-50h]
  __int64 v72; // [rsp+70h] [rbp+0h] BYREF
  PVOID P; // [rsp+78h] [rbp+8h] BYREF
  int v74; // [rsp+80h] [rbp+10h] BYREF
  bool v75; // [rsp+84h] [rbp+14h]
  unsigned int v76; // [rsp+88h] [rbp+18h]
  void *Buf1[2]; // [rsp+90h] [rbp+20h] BYREF
  unsigned int v78; // [rsp+A0h] [rbp+30h] BYREF
  struct _VCB *v79; // [rsp+A8h] [rbp+38h]
  struct _UNICODE_STRING LinkName; // [rsp+B0h] [rbp+40h] BYREF
  PIRP Irp[2]; // [rsp+C0h] [rbp+50h] BYREF
  struct _REFS_FILE_REFERENCE *v82; // [rsp+D0h] [rbp+60h] BYREF
  struct _UNICODE_STRING v83; // [rsp+D8h] [rbp+68h] BYREF
  PVOID v84[2]; // [rsp+E8h] [rbp+78h] BYREF
  int v85; // [rsp+F8h] [rbp+88h]
  struct _FCB *v86; // [rsp+100h] [rbp+90h]
  WCHAR *v87; // [rsp+108h] [rbp+98h]
  IndexSCB *v88; // [rsp+110h] [rbp+A0h]
  PVOID v89[2]; // [rsp+120h] [rbp+B0h] BYREF
  struct _UNICODE_STRING v90; // [rsp+130h] [rbp+C0h] BYREF
  __int64 v91; // [rsp+140h] [rbp+D0h]
  PVOID v92; // [rsp+148h] [rbp+D8h]
  PVOID v93; // [rsp+150h] [rbp+E0h]
  struct _UNICODE_STRING v94; // [rsp+158h] [rbp+E8h] BYREF
  __int64 v95[10]; // [rsp+170h] [rbp+100h] BYREF
  _OWORD v96[2]; // [rsp+1C0h] [rbp+150h] BYREF
  int v97; // [rsp+1E0h] [rbp+170h]

  v86 = a4;
  v79 = a3;
  Irp[0] = a2;
  v89[0] = (PVOID)a5;
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  *(_OWORD *)Buf1 = 0;
  v90 = 0;
  memset(v96, 0, sizeof(v96));
  v97 = 0;
  v88 = 0;
  *(_QWORD *)&LinkName.Length = 0;
  ByteOffset = CurrentStackLocation->Parameters.Read.ByteOffset;
  v83 = 0;
  *(_OWORD *)v84 = 0;
  P = 0;
  memset(v95, 0, 0x48u);
  v9 = *(_BYTE **)(*((_QWORD *)a1 + 9) + 24LL);
  if ( CurrentStackLocation->Parameters.Create.Options == 11 )
  {
    v76 = *v9 != 0;
  }
  else
  {
    v76 = *(_DWORD *)v9;
    if ( (v76 & 0xFFFFFE04) != 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 8u)
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 116, WPP_bbc83e81062238e0129655ea2ffc96b5_Traceguids, 3221225659LL);
      }
      if ( !(_BYTE)RefsStatusDebugEnabled )
        return 3221225659LL;
      v11 = 8025;
      goto LABEL_33;
    }
  }
  v95[0] = (__int64)a1;
  if ( (*(_DWORD *)(a5 + 4) & 2) == 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 8u)
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 117, WPP_bbc83e81062238e0129655ea2ffc96b5_Traceguids, 3221225485LL);
    }
    if ( !(_BYTE)RefsStatusDebugEnabled )
      return 3221225485LL;
    v10 = 8037;
LABEL_297:
    RefsStatusDebug(-1073741811, 0, "FileInfo.c", v10);
    return 3221225485LL;
  }
  ActualAllocationLength = a4->ActualAllocationLength;
  v13 = *(_QWORD *)(ActualAllocationLength + 88);
  if ( *(_QWORD *)(v13 + 248) || !*(_QWORD *)(v13 + 256) )
  {
    if ( !RefsHardlinksSupported(*((struct _VCB **)a1 + 8)) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 8u)
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 119, WPP_bbc83e81062238e0129655ea2ffc96b5_Traceguids, 3221225659LL);
      }
      if ( !(_BYTE)RefsStatusDebugEnabled )
        return 3221225659LL;
      v11 = 8056;
LABEL_33:
      RefsStatusDebug(-1073741637, 0, "FileInfo.c", v11);
      return 3221225659LL;
    }
    v16 = *(_QWORD *)(a5 + 72);
    if ( v16 )
    {
      v82 = *(struct _REFS_FILE_REFERENCE **)(v16 + 24);
      if ( !*(_DWORD *)(ActualAllocationLength + 176) )
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || !_bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 8u)
          || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
        {
          v17 = -1073741790;
        }
        else
        {
          v17 = -1073741790;
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            122,
            WPP_bbc83e81062238e0129655ea2ffc96b5_Traceguids,
            3221225506LL);
        }
        if ( !(_BYTE)RefsStatusDebugEnabled )
          return v17;
        v18 = 8101;
        goto LABEL_78;
      }
    }
    else
    {
      if ( !*(_DWORD *)(ActualAllocationLength + 176) && (v15 & 8) != 0 )
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || !_bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 8u)
          || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
        {
          v17 = -1073741790;
        }
        else
        {
          v17 = -1073741790;
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            120,
            WPP_bbc83e81062238e0129655ea2ffc96b5_Traceguids,
            3221225506LL);
        }
        if ( !(_BYTE)RefsStatusDebugEnabled )
          return v17;
        v18 = 8078;
LABEL_78:
        RefsStatusDebug(-1073741790, 0, "FileInfo.c", v18);
        return v17;
      }
      if ( !ByteOffset.QuadPart )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 8u)
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            121,
            WPP_bbc83e81062238e0129655ea2ffc96b5_Traceguids,
            3221225485LL);
        }
        if ( !(_BYTE)RefsStatusDebugEnabled )
          return 3221225485LL;
        v10 = 8086;
        goto LABEL_297;
      }
      v82 = 0;
    }
    if ( (*(_DWORD *)(ActualAllocationLength + 8) & 0x100LL) != 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 123, WPP_bbc83e81062238e0129655ea2ffc96b5_Traceguids, 3221225485LL);
      }
      if ( !(_BYTE)RefsStatusDebugEnabled )
        return 3221225485LL;
      v10 = 8115;
      goto LABEL_297;
    }
    if ( RefsEffectiveMode(Irp[0], CurrentStackLocation) == 1 && (*(_WORD *)(a5 + 88) & 0x310) == 0 )
    {
      v78 = 0;
      v74 = 0;
      FileObjectGenericMapping = IoGetFileObjectGenericMapping();
      if ( !RefsSeAccessCheck(
              a1,
              (struct _FCB *)ActualAllocationLength,
              *((struct _SECURITY_SUBJECT_CONTEXT **)a1 + 18),
              0,
              0,
              0x100u,
              0,
              0,
              FileObjectGenericMapping,
              1,
              &v78,
              0,
              &v74,
              0) )
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
        {
          v17 = -1073741790;
        }
        else
        {
          v17 = -1073741790;
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            124,
            WPP_bbc83e81062238e0129655ea2ffc96b5_Traceguids,
            3221225506LL);
        }
        if ( !(_BYTE)RefsStatusDebugEnabled )
          return v17;
        v18 = 8154;
        goto LABEL_78;
      }
    }
    if ( (*((_BYTE *)a1 + 8) & 1) == 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 125, WPP_bbc83e81062238e0129655ea2ffc96b5_Traceguids, 3221225485LL);
      }
      if ( !(_BYTE)RefsStatusDebugEnabled )
        return 3221225485LL;
      v10 = 8167;
      goto LABEL_297;
    }
    v17 = 0;
    LODWORD(v72) = 0;
    v74 = 0;
    v92 = 0;
    v93 = 0;
    if ( (*((_DWORD *)v89[0] + 1) & 8) == 0 && **((_WORD **)v89[0] + 3) == 92 )
      LOBYTE(v95[1]) |= 8u;
    *((_DWORD *)a1 + 158) = *((_DWORD *)v89[0] + 21);
    if ( (*(_DWORD *)(ActualAllocationLength + 8) & 0x10000000) == 0 )
      RefsLinkFileToSelf(a1, (struct _FCB *)ActualAllocationLength);
    v20 = v86->ActualAllocationLength;
    v21 = *(_QWORD *)(v20 + 232);
    if ( v21 && *(_DWORD *)(v21 + 104) )
    {
      RefsPostUsnChange(a1, (struct _FCB *)v20, 0x80000000, 0);
      RefsCheckpointCurrentTransaction(a1);
    }
    v22 = v82;
    RefsFindTargetElements(a1, (__int64)&LinkName, (__int64)&v90, (__int64)Buf1);
    if ( LOWORD(Buf1[0]) > 0x1FEu || !RefsIsFileNameValid((struct _UNICODE_STRING *)Buf1, 0) )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0 )
      {
        v17 = -1073741773;
      }
      else
      {
        v17 = -1073741773;
        if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            126,
            WPP_bbc83e81062238e0129655ea2ffc96b5_Traceguids,
            3221225523LL);
      }
      if ( !(_BYTE)RefsStatusDebugEnabled )
        goto LABEL_279;
      v25 = 8241;
      goto LABEL_278;
    }
    v23 = v88;
    v24 = *((_QWORD *)v88 + 17);
    if ( (*(_DWORD *)(v24 + 8) & 0x100LL) != 0 && v88 != *((IndexSCB **)v79 + 4) )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0 )
      {
        v17 = -1073741790;
      }
      else
      {
        v17 = -1073741790;
        if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            127,
            WPP_bbc83e81062238e0129655ea2ffc96b5_Traceguids,
            3221225506LL);
      }
      if ( !(_BYTE)RefsStatusDebugEnabled )
        goto LABEL_279;
      v25 = 8252;
      goto LABEL_278;
    }
    RefsAcquireFcbWithPaging((__int64)a1, v24, (__int64)v88, 0x34u);
    v95[3] = (__int64)v23;
    if ( *(_QWORD *)(*((_QWORD *)v23 + 17) + 96LL) )
    {
      v88 = (IndexSCB *)1;
      v95[3] = (unsigned __int64)v23 & 0xFFFFFFFFFFFFFFF8uLL | 1;
    }
    if ( v23 == v22 )
    {
      v26 = *(_QWORD *)(v16 + 148);
      v78 = *(_DWORD *)(v16 + 140) - 4;
      v94.MaximumLength = v78;
      v94.Length = v78;
      v27 = (WCHAR *)(v26 + 4);
      v94.Buffer = v27;
      if ( LOWORD(Buf1[0]) == (_WORD)v78 )
      {
        v28 = 0;
        if ( !memcmp(Buf1[1], v27, LOWORD(Buf1[0])) )
        {
          if ( (v76 & 1) == 0 )
          {
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
              || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
            {
              v17 = -1073741771;
            }
            else
            {
              v17 = -1073741771;
              WPP_SF_d(
                WPP_GLOBAL_Control->AttachedDevice,
                128,
                WPP_bbc83e81062238e0129655ea2ffc96b5_Traceguids,
                3221225525LL);
            }
            if ( !(_BYTE)RefsStatusDebugEnabled )
              goto LABEL_279;
            v25 = 8277;
LABEL_278:
            RefsStatusDebug(v17, 0, "FileInfo.c", v25);
LABEL_279:
            LODWORD(v72) = v17;
            goto LABEL_280;
          }
          goto LABEL_178;
        }
LABEL_115:
        if ( (*(_DWORD *)(ActualAllocationLength + 8) & 0x10000000) != 0 )
        {
          v29 = *(__int64 **)(ActualAllocationLength + 328);
          if ( v29 != (__int64 *)v23 )
          {
            if ( !(unsigned __int8)RefsAcquireFcbWithPaging(
                                     (__int64)a1,
                                     v29[17],
                                     0,
                                     (*((_DWORD *)a1 + 2) & 0x100LL) != 0 ? 53 : 51) )
            {
              *((_QWORD *)a1 + 1) |= 0x100uLL;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
              {
                WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 129, WPP_bbc83e81062238e0129655ea2ffc96b5_Traceguids);
              }
              if ( (_BYTE)RefsStatusDebugEnabled )
                RefsStatusDebug(-1073741608, a1, "FileInfo.c", 0x2077u);
              RefsRaiseStatusInternal(a1, -1073741608, v30);
            }
            v31 = *(_QWORD *)(ActualAllocationLength + 328);
            v95[4] = v31;
            if ( *(_QWORD *)(*(_QWORD *)(v31 + 136) + 96LL) )
            {
              v91 = 1;
              v95[4] = v31 & 0xFFFFFFFFFFFFFFF8uLL | 1;
            }
          }
        }
        if ( !*(_DWORD *)(*((_QWORD *)v23 + 17) + 176LL) )
        {
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
          {
            v17 = -1073741738;
          }
          else
          {
            v17 = -1073741738;
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              130,
              WPP_bbc83e81062238e0129655ea2ffc96b5_Traceguids,
              3221225558LL);
          }
          if ( !(_BYTE)RefsStatusDebugEnabled )
            goto LABEL_279;
          v25 = 8323;
          goto LABEL_278;
        }
        IndexSCB::EnsureDirectoryNormalizedName(v23, a1);
        v33 = *((unsigned __int8 *)v79 + 793) | (*((unsigned __int8 *)v79 + 792) << 8);
        if ( v33 >= 0x30B )
          v34 = v33 > 0x30B;
        else
          v34 = -1;
        if ( *(_DWORD *)(ActualAllocationLength + 180) >= 0x2000u )
        {
          if ( v34 < 0 )
          {
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
              || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
            {
              v17 = -1073741211;
            }
            else
            {
              v17 = -1073741211;
              WPP_SF_d(
                WPP_GLOBAL_Control->AttachedDevice,
                132,
                WPP_bbc83e81062238e0129655ea2ffc96b5_Traceguids,
                3221226085LL);
            }
            if ( !(_BYTE)RefsStatusDebugEnabled )
              goto LABEL_279;
            v25 = 8341;
          }
          else
          {
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
              || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
            {
              v17 = -1073741211;
            }
            else
            {
              v17 = -1073741211;
              WPP_SF_d(
                WPP_GLOBAL_Control->AttachedDevice,
                131,
                WPP_bbc83e81062238e0129655ea2ffc96b5_Traceguids,
                3221226085LL);
            }
            if ( !(_BYTE)RefsStatusDebugEnabled )
              goto LABEL_279;
            v25 = 8336;
          }
          goto LABEL_278;
        }
        P = 0;
        LOBYTE(v32) = (*((_DWORD *)v89[0] + 1) & 1) != 0
                   && ((*((_DWORD *)v89[0] + 1) & 0x4000000) != 0
                    || (*(_DWORD *)(*((_QWORD *)v23 + 17) + 8LL) & 0x400000) == 0);
        v35 = RefsLookupEntry(a1, v23, v32, Buf1, v96, &P);
        v36 = v95[1] & 0xFD | (2 * (v35 & 1));
        LOBYTE(v95[1]) = v36;
        if ( RefsIsTransactionActive(a1) )
        {
          RefsCheckpointCurrentTransaction(v37);
          v36 = v95[1];
        }
        if ( (v36 & 2) != 0 )
        {
          if ( (v76 & 1) == 0 )
          {
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
              || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
            {
              v17 = -1073741771;
            }
            else
            {
              v17 = -1073741771;
              WPP_SF_d(
                WPP_GLOBAL_Control->AttachedDevice,
                133,
                WPP_bbc83e81062238e0129655ea2ffc96b5_Traceguids,
                3221225525LL);
            }
            if ( !(_BYTE)RefsStatusDebugEnabled )
              goto LABEL_279;
            v25 = 8390;
            goto LABEL_278;
          }
          v75 = 0;
          v38 = *(_QWORD *)(ActualAllocationLength + 88);
          if ( *((_QWORD *)P + 1) == *(_QWORD *)(v38 + 256) && *(_QWORD *)P == *(_QWORD *)(v38 + 248) )
          {
            v36 |= 0x10u;
            LOBYTE(v95[1]) = v36;
          }
          if ( !memcmp(*(const void **)((char *)P + 84), Buf1[1], LOWORD(Buf1[0])) )
          {
            v36 |= 0x20u;
            LOBYTE(v95[1]) = v36;
          }
          if ( (v36 & 0x10) != 0 )
          {
            v28 = (v36 & 0x20) != 0;
            v75 = v28;
          }
          if ( v28 )
          {
LABEL_178:
            v17 = 0;
            LODWORD(v72) = 0;
LABEL_280:
            v48 = P;
LABEL_281:
            if ( v84[1] )
              ExFreePoolWithTag(v84[1], 0);
            if ( v92 )
              ExFreePoolWithTag(v92, 0);
            _FILE_NAME::CleanupFileName((_FILE_NAME *)v96);
            if ( v48 )
              ExFreePoolWithTag(v48, 0);
            if ( (v95[1] & 4) != 0 )
            {
              v70 = v95[7];
              LOBYTE(v69) = 1;
              ExAcquireFastResourceExclusive(*(_QWORD *)(v95[7] + 80) + 624LL, 0, v69);
              _InterlockedDecrement((volatile signed __int32 *)(v70 + 24));
              ExReleaseFastResource(*(_QWORD *)(v70 + 80) + 624LL, 0);
            }
            if ( v17 != 871 )
              RefsRenameCleanup((struct _REFS_RENAME_CLEANUP *)v95);
            return v17;
          }
          if ( (v36 & 8) != 0 )
          {
            v39 = v82;
            v40 = LOWORD(Buf1[0]) + 2 + *((unsigned __int16 *)v82 + 196);
            if ( v40 > 0xFFFE )
            {
              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
                || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
              {
                v17 = -1073741562;
              }
              else
              {
                v17 = -1073741562;
                WPP_SF_d(
                  WPP_GLOBAL_Control->AttachedDevice,
                  134,
                  WPP_bbc83e81062238e0129655ea2ffc96b5_Traceguids,
                  3221225734LL);
              }
              if ( !(_BYTE)RefsStatusDebugEnabled )
                goto LABEL_279;
              v25 = 8425;
              goto LABEL_278;
            }
            LOWORD(v84[0]) = LOWORD(Buf1[0]) + 2 + *((_WORD *)v82 + 196);
            WORD1(v84[0]) = v40;
            v84[1] = ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), (unsigned __int16)v40, 0x46466552u);
            memmove(v84[1], *((const void **)v39 + 50), *((unsigned __int16 *)v39 + 196));
            v41 = *((unsigned __int16 *)v39 + 196);
            PoolWithTag = (WCHAR *)((char *)v84[1] + v41);
            v87 = (WCHAR *)((char *)v84[1] + v41);
            if ( (_WORD)v41 == 2 )
            {
              LOWORD(v84[0]) -= 2;
            }
            else
            {
              *PoolWithTag++ = 92;
              v87 = PoolWithTag;
            }
            v83.Buffer = PoolWithTag;
            v43 = (USHORT)Buf1[0];
          }
          else
          {
            PoolWithTag = (WCHAR *)ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), LOWORD(Buf1[0]), 0x46466552u);
            v83.Buffer = PoolWithTag;
            v84[1] = PoolWithTag;
            v43 = (USHORT)Buf1[0];
            v83.MaximumLength = (USHORT)Buf1[0];
            LOWORD(v84[0]) = Buf1[0];
          }
          v83.MaximumLength = v43;
          v83.Length = v43;
          v44 = (const struct _DIR_INDEX_ENTRY *)P;
          memmove(PoolWithTag, *(const void **)((char *)P + 84), v43);
          if ( (v95[1] & 0x10) != 0 )
          {
            RefsRemoveLink(a1, (struct _FCB *)ActualAllocationLength, v23, &v83);
            v74 = 1;
            *(_QWORD *)(ActualAllocationLength + 8) &= ~0x4000uLL;
            v95[7] = ActualAllocationLength;
          }
          else
          {
            v82 = 0;
            CmsKeyLength = RefsGetCmsKeyLength(v44, &v83, &v82);
            v46 = CmsKeyLength + 15;
            if ( CmsKeyLength + 15 <= CmsKeyLength )
              v46 = 0xFFFFFFFFFFFFFF0LL;
            v47 = alloca(v46 & 0xFFFFFFFFFFFFFFF0uLL);
            RefsInitCmsKey((struct _CmsKey *)&v72, &v83, v82, CmsKeyLength);
            v48 = P;
            v17 = RefsRemoveSupersededTarget(
                    a1,
                    Irp[0],
                    (__int64)v89[0],
                    (__int64)&v72,
                    (v76 & 2) != 0,
                    (v76 & 0x40) != 0,
                    (__int64)v95,
                    &v83);
            LODWORD(v72) = v17;
            if ( v17 )
              goto LABEL_281;
          }
          v36 = v95[1];
        }
        if ( *(_QWORD *)&LinkName.Length && (*(_DWORD *)(*(_QWORD *)&LinkName.Length + 4LL) & 8) != 0
          || (v36 & 8) != 0 && !v90.Buffer )
        {
          v49 = LOWORD(Buf1[0]) + 2 + *((unsigned __int16 *)v23 + 196);
          if ( v49 > 0xFFFE )
          {
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
              || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
            {
              v17 = -1073741562;
            }
            else
            {
              v17 = -1073741562;
              WPP_SF_d(
                WPP_GLOBAL_Control->AttachedDevice,
                135,
                WPP_bbc83e81062238e0129655ea2ffc96b5_Traceguids,
                3221225734LL);
            }
            if ( !(_BYTE)RefsStatusDebugEnabled )
              goto LABEL_279;
            v25 = 8548;
            goto LABEL_278;
          }
          v90.Length = LOWORD(Buf1[0]) + 2 + *((_WORD *)v23 + 196);
          v90.MaximumLength = v49;
          v92 = ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), (unsigned __int16)v49, 0x46466552u);
          v90.Buffer = (PWSTR)v92;
          v93 = v92;
          memmove(v92, *((const void **)v23 + 50), *((unsigned __int16 *)v23 + 196));
          v50 = *((unsigned __int16 *)v23 + 196);
          v51 = (PWSTR)((char *)v90.Buffer + v50);
          v87 = (PWSTR)((char *)v90.Buffer + v50);
          if ( (_WORD)v50 == 2 )
          {
            v90.Length -= 2;
          }
          else
          {
            *v51++ = 92;
            v87 = v51;
          }
          memmove(v51, Buf1[1], LOWORD(Buf1[0]));
        }
        if ( P )
        {
          ExFreePoolWithTag(P, 0);
          P = 0;
        }
        v52 = (char *)v89[0];
        RefsCheckIndexForAddOrDelete(a1, Irp[0], *((struct _FCB **)v23 + 17), 2u, (struct _CCB *)v89[0]);
        RefsUpdateFileTimestampsForChange(v86->ActualAllocationLength, v52, 0x400000, 0);
        RefsAddLink(a1, v23, (struct _FCB *)ActualAllocationLength, (struct _FILE_NAME *)v96);
        v53 = --v74;
        RefsUpdateFcbTimestamps(*((_QWORD *)v23 + 17), 0, 2684354576LL);
        v55 = v95[1];
        if ( (v95[1] & 0x10) != 0 )
        {
          RefsReplaceLinkInDir((_DWORD)a1, (_DWORD)v23, ActualAllocationLength, (unsigned int)Buf1, (__int64)&v83);
          v55 = v95[1];
        }
        if ( (v55 & 2) != 0 && (v55 & 0x10) == 0 )
        {
          RefsUpdateFcbFromLinkRemoval(v54, v23, v95[7], &v83);
          v55 = v95[1];
        }
        if ( (v55 & 8) != 0 )
        {
          v56 = 0;
          v85 = 0;
          if ( (v55 & 0x20) != 0 )
          {
            v59 = 0;
            if ( (v55 & 0x10) == 0 )
            {
              v56 = 508;
              v85 = 508;
              v59 = 3;
            }
          }
          else
          {
            if ( (v55 & 2) != 0 )
            {
              v57 = *(_QWORD *)(v95[7] + 88);
              if ( *(_QWORD *)(v57 + 248) || (v58 = 2, !*(_QWORD *)(v57 + 256)) )
                v58 = 1;
              RefsReportDirNotify(
                (IndexSCB *)((char *)v23 + 392),
                v79,
                (struct _UNICODE_STRING *)v84,
                LOWORD(v84[0]) - v83.Length,
                0,
                (struct _UNICODE_STRING *)((char *)v23 + 392),
                v58,
                2u,
                *((struct _FCB **)v23 + 17));
            }
            v56 = 1;
            v85 = 1;
            v59 = 1;
          }
          if ( v56 )
            RefsReportDirNotify(
              (IndexSCB *)((char *)v23 + 392),
              v79,
              &v90,
              v90.Length - LOWORD(Buf1[0]),
              0,
              (struct _UNICODE_STRING *)((char *)v23 + 392),
              v56,
              v59,
              *((struct _FCB **)v23 + 17));
        }
        RefsPostUsnChange(a1, v86, 0x80010000, (const struct _FILE_NAME *)v96);
        RefsConvertToStandardInfoLinkCount(
          a1,
          ActualAllocationLength,
          (unsigned int)(*(_DWORD *)(ActualAllocationLength + 180) - v53),
          0);
        if ( *((_QWORD *)a1 + 76) )
        {
          RefsCheckpointCurrentTransaction(a1);
          *(_DWORD *)(ActualAllocationLength + 180) -= v53;
          *(_DWORD *)(ActualAllocationLength + 176) -= v53;
          v53 = 0;
          v74 = 0;
          *(_QWORD *)(v86->ActualAllocationLength + 8) &= ~0x4000uLL;
        }
        FsRtlCheckOplockEx((POPLOCK)v23 + 11, Irp[0], 0x10u, 0, 0, 0);
        if ( !*(_QWORD *)(ActualAllocationLength + 192) )
          RefsLoadSecurityDescriptor(a1, (struct _FCB *)ActualAllocationLength);
        if ( !SeAuditingHardLinkEventsWithContext(
                1u,
                (PSECURITY_DESCRIPTOR)(*(_QWORD *)(ActualAllocationLength + 192) + 20LL),
                0) )
        {
LABEL_270:
          RefsCheckpointCurrentTransaction(a1);
          *(_DWORD *)(ActualAllocationLength + 180) -= v53;
          *(_DWORD *)(ActualAllocationLength + 176) -= v53;
          goto LABEL_280;
        }
        v89[0] = 0;
        Irp[0] = 0;
        *(_QWORD *)&LinkName.Length = 0;
        v76 = 0;
        v89[1] = 0;
        Irp[1] = 0;
        LinkName.Buffer = 0;
        v60 = (PVOID *)(v52 + 16);
        v61 = *((_WORD *)v52 + 8);
        if ( !v61 )
        {
          *(struct _UNICODE_STRING *)v89 = *RefsBuildNormalizedName(
                                              &v94,
                                              a1,
                                              (struct _FCB *)v86->ActualAllocationLength,
                                              *((struct _LCB **)v52 + 9),
                                              CompletionRoutine);
          v60 = v89;
          v61 = _mm_cvtsi128_si32(*(__m128i *)v89);
        }
        v62 = v61 + *((unsigned __int16 *)v79 + 408);
        v76 = v62;
        if ( v62 <= 0xFFFE )
        {
          Irp[1] = (PIRP)ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), v62, 0x46466552u);
          WORD1(Irp[0]) = v62;
          LOWORD(Irp[0]) = v62;
          v64 = v79;
          memmove(Irp[1], *((const void **)v79 + 103), *((unsigned __int16 *)v79 + 408));
          memmove((char *)Irp[1] + *((unsigned __int16 *)v64 + 408), v60[1], *(unsigned __int16 *)v60);
          v65 = LOWORD(Buf1[0]) + *((unsigned __int16 *)v64 + 408) + *((unsigned __int16 *)v23 + 196) + 2;
          v76 = v65;
          if ( v65 <= 0xFFFE )
          {
            LinkName.Buffer = (PWSTR)ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), v65, 0x46466552u);
            LinkName.MaximumLength = v65;
            LinkName.Length = v65;
            v66 = v79;
            memmove(LinkName.Buffer, *((const void **)v79 + 103), *((unsigned __int16 *)v79 + 408));
            memmove(
              (char *)LinkName.Buffer + *((unsigned __int16 *)v66 + 408),
              *((const void **)v23 + 50),
              *((unsigned __int16 *)v23 + 196));
            v67 = *((unsigned __int16 *)v23 + 196);
            v68 = (PWSTR)((char *)LinkName.Buffer + *((unsigned __int16 *)v66 + 408) + v67);
            v87 = v68;
            if ( (_WORD)v67 == 2 )
            {
              LinkName.Length -= 2;
            }
            else
            {
              *v68++ = 92;
              v87 = v68;
            }
            memmove(v68, Buf1[1], LOWORD(Buf1[0]));
            SeAuditHardLinkCreation((PUNICODE_STRING)Irp, &LinkName, 1u);
            goto LABEL_263;
          }
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
          {
            v17 = -1073741562;
          }
          else
          {
            v17 = -1073741562;
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              137,
              WPP_bbc83e81062238e0129655ea2ffc96b5_Traceguids,
              3221225734LL);
          }
          if ( !(_BYTE)RefsStatusDebugEnabled )
          {
LABEL_250:
            LODWORD(v72) = -1073741562;
LABEL_263:
            if ( v89[1] )
              ExFreePoolWithTag(v89[1], 0);
            if ( LinkName.Buffer )
              ExFreePoolWithTag(LinkName.Buffer, 0);
            if ( Irp[1] )
              ExFreePoolWithTag(Irp[1], 0);
            v53 = v74;
            goto LABEL_270;
          }
          v63 = 8847;
        }
        else
        {
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
          {
            v17 = -1073741562;
          }
          else
          {
            v17 = -1073741562;
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              136,
              WPP_bbc83e81062238e0129655ea2ffc96b5_Traceguids,
              3221225734LL);
          }
          if ( !(_BYTE)RefsStatusDebugEnabled )
            goto LABEL_250;
          v63 = 8834;
        }
        RefsStatusDebug(-1073741562, 0, "FileInfo.c", v63);
        goto LABEL_250;
      }
    }
    else
    {
      BYTE1(v95[1]) |= 4u;
    }
    v28 = 0;
    goto LABEL_115;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 8u)
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 118, WPP_bbc83e81062238e0129655ea2ffc96b5_Traceguids, 3221225658LL);
  }
  if ( (_BYTE)RefsStatusDebugEnabled )
    RefsStatusDebug(-1073741638, 0, "FileInfo.c", 0x1F70u);
  return 3221225658LL;
}

```

## disassembly

```asm
0x1402a5720  push    rbp
0x1402a5722  push    rbx
0x1402a5723  push    rsi
0x1402a5724  push    rdi
0x1402a5725  push    r12
0x1402a5727  push    r13
0x1402a5729  push    r14
0x1402a572b  push    r15
0x1402a572d  sub     rsp, 1F8h
0x1402a5734  lea     rbp, [rsp+70h]
0x1402a5739  mov     rax, cs:__security_cookie
0x1402a5740  xor     rax, rbp
0x1402a5743  mov     [rbp+1C0h+var_48], rax
0x1402a574a  mov     rsi, r9
0x1402a574d  mov     [rbp+1C0h+var_130], r9
0x1402a5754  mov     [rbp+1C0h+var_188], r8
0x1402a5758  mov     [rbp+1C0h+Irp], rdx
0x1402a575c  mov     r15, rcx
0x1402a575f  mov     rdi, [rbp+1C0h+arg_20]
0x1402a5766  mov     [rbp+1C0h+var_110], rdi
0x1402a576d  mov     rbx, [rdx+0B8h]
0x1402a5774  xorps   xmm0, xmm0
0x1402a5777  movups  xmmword ptr [rbp+1C0h+Buf1], xmm0
0x1402a577b  xorps   xmm1, xmm1
0x1402a577e  movups  xmmword ptr [rbp+1C0h+var_100.Length], xmm1
0x1402a5785  xor     eax, eax
0x1402a5787  movups  [rbp+1C0h+var_70], xmm0
0x1402a578e  movups  [rbp+1C0h+var_60], xmm0
0x1402a5795  mov     [rbp+1C0h+var_50], eax
0x1402a579b  xor     r12d, r12d
0x1402a579e  mov     [rbp+1C0h+var_120], r12
0x1402a57a5  mov     qword ptr [rbp+1C0h+LinkName.Length], r12
0x1402a57a9  mov     r13, [rbx+18h]
0x1402a57ad  movups  xmmword ptr [rbp+1C0h+var_158.Length], xmm0
0x1402a57b1  movups  xmmword ptr [rbp+1C0h+var_148], xmm1
0x1402a57b5  mov     [rbp+1C0h+P], r12
0x1402a57b9  xor     edx, edx; Val
0x1402a57bb  lea     r8d, [rax+48h]; Size
0x1402a57bf  lea     rcx, [rbp+1C0h+var_C0]; void *
0x1402a57c6  call    memset
0x1402a57cb  mov     rax, [r15+48h]
0x1402a57cf  mov     rcx, [rax+18h]
0x1402a57d3  cmp     dword ptr [rbx+10h], 0Bh
0x1402a57d7  jnz     short loc_1402A584C
0x1402a57d9  mov     eax, r12d
0x1402a57dc  cmp     [rcx], r12b
0x1402a57df  setnz   al
0x1402a57e2  mov     [rbp+1C0h+var_1A8], eax
0x1402a57e5  mov     [rbp+1C0h+var_C0], r15
0x1402a57ec  mov     edx, [rdi+4]
0x1402a57ef  test    dl, 2
0x1402a57f2  jnz     loc_1402A58AC
0x1402a57f8  lea     rax, WPP_GLOBAL_Control
0x1402a57ff  mov     rcx, cs:WPP_GLOBAL_Control
0x1402a5806  cmp     rcx, rax
0x1402a5809  jz      short loc_1402A5833
0x1402a580b  bt      dword ptr [rcx+2Ch], 8
0x1402a5810  jnb     short loc_1402A5833
0x1402a5812  cmp     byte ptr [rcx+29h], 4
0x1402a5816  jb      short loc_1402A5833
0x1402a5818  mov     edx, 75h ; 'u'
0x1402a581d  mov     r9d, 0C000000Dh
0x1402a5823  lea     r8, WPP_bbc83e81062238e0129655ea2ffc96b5_Traceguids
0x1402a582a  mov     rcx, [rcx+18h]
0x1402a582e  call    WPP_SF_d
0x1402a5833  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402a5839  test    al, al
0x1402a583b  jz      loc_1402A6DA1
0x1402a5841  mov     r9d, 1F65h
0x1402a5847  jmp     loc_1402A6D8E
0x1402a584c  mov     eax, [rcx]
0x1402a584e  mov     [rbp+1C0h+var_1A8], eax
0x1402a5851  test    eax, 0FFFFFE04h
0x1402a5856  jz      short loc_1402A57E5
0x1402a5858  lea     rax, WPP_GLOBAL_Control
0x1402a585f  mov     rcx, cs:WPP_GLOBAL_Control
0x1402a5866  cmp     rcx, rax
0x1402a5869  jz      short loc_1402A5893
0x1402a586b  bt      dword ptr [rcx+2Ch], 8
0x1402a5870  jnb     short loc_1402A5893
0x1402a5872  cmp     byte ptr [rcx+29h], 4
0x1402a5876  jb      short loc_1402A5893
0x1402a5878  mov     edx, 74h ; 't'
0x1402a587d  mov     r9d, 0C00000BBh
0x1402a5883  lea     r8, WPP_bbc83e81062238e0129655ea2ffc96b5_Traceguids
0x1402a588a  mov     rcx, [rcx+18h]
0x1402a588e  call    WPP_SF_d
0x1402a5893  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402a5899  test    al, al
0x1402a589b  jz      loc_1402A599C
0x1402a58a1  mov     r9d, 1F59h
0x1402a58a7  jmp     loc_1402A5989
0x1402a58ac  mov     r14, [rsi+88h]
0x1402a58b3  mov     rax, [r14+58h]
0x1402a58b7  cmp     [rax+0F8h], r12
0x1402a58be  jnz     short loc_1402A5931
0x1402a58c0  cmp     [rax+100h], r12
0x1402a58c7  jz      short loc_1402A5931
0x1402a58c9  lea     rax, WPP_GLOBAL_Control
0x1402a58d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1402a58d7  cmp     rcx, rax
0x1402a58da  jz      short loc_1402A5904
0x1402a58dc  bt      dword ptr [rcx+2Ch], 8
0x1402a58e1  jnb     short loc_1402A5904
0x1402a58e3  cmp     byte ptr [rcx+29h], 4
0x1402a58e7  jb      short loc_1402A5904
0x1402a58e9  mov     edx, 76h ; 'v'
0x1402a58ee  mov     r9d, 0C00000BAh
0x1402a58f4  lea     r8, WPP_bbc83e81062238e0129655ea2ffc96b5_Traceguids
0x1402a58fb  mov     rcx, [rcx+18h]
0x1402a58ff  call    WPP_SF_d
0x1402a5904  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402a590a  test    al, al
0x1402a590c  jz      short loc_1402A5927
0x1402a590e  mov     r9d, 1F70h; unsigned int
0x1402a5914  lea     r8, aFileinfoC; "FileInfo.c"
0x1402a591b  xor     edx, edx; struct _IRP_CONTEXT *
0x1402a591d  mov     ecx, 0C00000BAh; Status
0x1402a5922  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x1402a5927  mov     eax, 0C00000BAh
0x1402a592c  jmp     loc_1402A6DA6
0x1402a5931  mov     rcx, [r15+40h]; struct _VCB *
0x1402a5935  call    ?RefsHardlinksSupported@@YAEPEAU_VCB@@@Z; RefsHardlinksSupported(_VCB *)
0x1402a593a  test    al, al
0x1402a593c  jnz     short loc_1402A59A6
0x1402a593e  lea     rax, WPP_GLOBAL_Control
0x1402a5945  mov     rcx, cs:WPP_GLOBAL_Control
0x1402a594c  cmp     rcx, rax
0x1402a594f  jz      short loc_1402A5979
0x1402a5951  bt      dword ptr [rcx+2Ch], 8
0x1402a5956  jnb     short loc_1402A5979
0x1402a5958  cmp     byte ptr [rcx+29h], 4
0x1402a595c  jb      short loc_1402A5979
0x1402a595e  mov     edx, 77h ; 'w'
0x1402a5963  mov     r9d, 0C00000BBh
0x1402a5969  lea     r8, WPP_bbc83e81062238e0129655ea2ffc96b5_Traceguids
0x1402a5970  mov     rcx, [rcx+18h]
0x1402a5974  call    WPP_SF_d
0x1402a5979  mov     cl, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402a597f  test    cl, cl
0x1402a5981  jz      short loc_1402A599C
0x1402a5983  mov     r9d, 1F78h; unsigned int
0x1402a5989  lea     r8, aFileinfoC; "FileInfo.c"
0x1402a5990  xor     edx, edx; struct _IRP_CONTEXT *
0x1402a5992  mov     ecx, 0C00000BBh; Status
0x1402a5997  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x1402a599c  mov     eax, 0C00000BBh
0x1402a59a1  jmp     loc_1402A6DA6
0x1402a59a6  mov     r12, [rdi+48h]
0x1402a59aa  xor     ecx, ecx
0x1402a59ac  test    r12, r12
0x1402a59af  jnz     loc_1402A5AE0
0x1402a59b5  cmp     [r14+0B0h], ecx
0x1402a59bc  jnz     short loc_1402A5A20
0x1402a59be  test    dl, 8
0x1402a59c1  jz      short loc_1402A5A20
0x1402a59c3  lea     rax, WPP_GLOBAL_Control
0x1402a59ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1402a59d1  cmp     rcx, rax
0x1402a59d4  jz      short loc_1402A5A02
0x1402a59d6  bt      dword ptr [rcx+2Ch], 8
0x1402a59db  jnb     short loc_1402A5A02
0x1402a59dd  cmp     byte ptr [rcx+29h], 4
0x1402a59e1  jb      short loc_1402A5A02
0x1402a59e3  lea     edx, [r12+78h]
0x1402a59e8  mov     edi, 0C0000022h
0x1402a59ed  mov     r9d, edi
0x1402a59f0  lea     r8, WPP_bbc83e81062238e0129655ea2ffc96b5_Traceguids
0x1402a59f7  mov     rcx, [rcx+18h]
0x1402a59fb  call    WPP_SF_d
0x1402a5a00  jmp     short loc_1402A5A07
0x1402a5a02  mov     edi, 0C0000022h
0x1402a5a07  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402a5a0d  test    al, al
0x1402a5a0f  jz      loc_1402A5C3B
0x1402a5a15  mov     r9d, 1F8Eh
0x1402a5a1b  jmp     loc_1402A5C2B
0x1402a5a20  test    r13, r13
0x1402a5a23  jnz     short loc_1402A5A78
0x1402a5a25  lea     rax, WPP_GLOBAL_Control
0x1402a5a2c  mov     rcx, cs:WPP_GLOBAL_Control
0x1402a5a33  cmp     rcx, rax
0x1402a5a36  jz      short loc_1402A5A5F
0x1402a5a38  bt      dword ptr [rcx+2Ch], 8
0x1402a5a3d  jnb     short loc_1402A5A5F
0x1402a5a3f  cmp     byte ptr [rcx+29h], 4
0x1402a5a43  jb      short loc_1402A5A5F
0x1402a5a45  lea     edx, [r13+79h]
0x1402a5a49  mov     r9d, 0C000000Dh
0x1402a5a4f  lea     r8, WPP_bbc83e81062238e0129655ea2ffc96b5_Traceguids
0x1402a5a56  mov     rcx, [rcx+18h]
0x1402a5a5a  call    WPP_SF_d
0x1402a5a5f  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402a5a65  test    al, al
0x1402a5a67  jz      loc_1402A6DA1
0x1402a5a6d  mov     r9d, 1F96h
0x1402a5a73  jmp     loc_1402A6D8E
0x1402a5a78  mov     [rbp+1C0h+var_160], rcx
0x1402a5a7c  mov     eax, [r14+8]
0x1402a5a80  mov     esi, 100h
0x1402a5a85  test    rsi, rax
0x1402a5a88  jz      loc_1402A5B4F
0x1402a5a8e  lea     rax, WPP_GLOBAL_Control
0x1402a5a95  mov     rcx, cs:WPP_GLOBAL_Control
0x1402a5a9c  cmp     rcx, rax
0x1402a5a9f  jz      short loc_1402A5AC7
0x1402a5aa1  test    [rcx+2Ch], esi
0x1402a5aa4  jz      short loc_1402A5AC7
0x1402a5aa6  cmp     byte ptr [rcx+29h], 4
0x1402a5aaa  jb      short loc_1402A5AC7
0x1402a5aac  mov     edx, 7Bh ; '{'
0x1402a5ab1  mov     r9d, 0C000000Dh
0x1402a5ab7  lea     r8, WPP_bbc83e81062238e0129655ea2ffc96b5_Traceguids
0x1402a5abe  mov     rcx, [rcx+18h]
0x1402a5ac2  call    WPP_SF_d
0x1402a5ac7  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402a5acd  test    al, al
0x1402a5acf  jz      loc_1402A6DA1
0x1402a5ad5  mov     r9d, 1FB3h
0x1402a5adb  jmp     loc_1402A6D8E
0x1402a5ae0  mov     rax, [r12+18h]
0x1402a5ae5  mov     [rbp+1C0h+var_160], rax
0x1402a5ae9  cmp     [r14+0B0h], ecx
0x1402a5af0  jnz     short loc_1402A5A7C
0x1402a5af2  lea     rax, WPP_GLOBAL_Control
0x1402a5af9  mov     rcx, cs:WPP_GLOBAL_Control
0x1402a5b00  cmp     rcx, rax
0x1402a5b03  jz      short loc_1402A5B31
0x1402a5b05  bt      dword ptr [rcx+2Ch], 8
0x1402a5b0a  jnb     short loc_1402A5B31
0x1402a5b0c  cmp     byte ptr [rcx+29h], 4
0x1402a5b10  jb      short loc_1402A5B31
0x1402a5b12  mov     edx, 7Ah ; 'z'
0x1402a5b17  mov     edi, 0C0000022h
0x1402a5b1c  mov     r9d, edi
0x1402a5b1f  lea     r8, WPP_bbc83e81062238e0129655ea2ffc96b5_Traceguids
0x1402a5b26  mov     rcx, [rcx+18h]
0x1402a5b2a  call    WPP_SF_d
0x1402a5b2f  jmp     short loc_1402A5B36
0x1402a5b31  mov     edi, 0C0000022h
0x1402a5b36  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402a5b3c  test    al, al
0x1402a5b3e  jz      loc_1402A5C3B
0x1402a5b44  mov     r9d, 1FA5h
0x1402a5b4a  jmp     loc_1402A5C2B
0x1402a5b4f  mov     rdx, rbx; struct _IO_STACK_LOCATION *
0x1402a5b52  mov     rcx, [rbp+1C0h+Irp]; struct _IRP *
0x1402a5b56  call    ?RefsEffectiveMode@@YADPEAU_IRP@@PEAU_IO_STACK_LOCATION@@@Z; RefsEffectiveMode(_IRP *,_IO_STACK_LOCATION *)
0x1402a5b5b  mov     edx, 1
0x1402a5b60  xor     ebx, ebx
0x1402a5b62  cmp     al, dl
0x1402a5b64  jnz     loc_1402A5C47
0x1402a5b6a  mov     ecx, 310h
0x1402a5b6f  test    [rdi+58h], cx
0x1402a5b73  jnz     loc_1402A5C47
0x1402a5b79  mov     [rbp+1C0h+var_190], ebx
0x1402a5b7c  mov     [rbp+1C0h+var_1B0], ebx
0x1402a5b7f  call    cs:__imp_IoGetFileObjectGenericMapping
0x1402a5b86  nop     dword ptr [rax+rax+00h]
0x1402a5b8b  mov     [rsp+230h+var_1C8], rbx; struct _ACCESS_STATE *
0x1402a5b90  lea     rcx, [rbp+1C0h+var_1B0]
0x1402a5b94  mov     [rsp+230h+var_1D0], rcx; int *
0x1402a5b99  mov     [rsp+230h+var_1D8], rbx; struct _ACCESS_REASONS *
0x1402a5b9e  lea     rcx, [rbp+1C0h+var_190]
0x1402a5ba2  mov     [rsp+230h+var_1E0], rcx; unsigned int *
0x1402a5ba7  mov     [rsp+230h+var_1E8], 1; char
0x1402a5bac  mov     [rsp+230h+var_1F0], rax; struct _GENERIC_MAPPING *
0x1402a5bb1  mov     qword ptr [rsp+230h+var_1F8], rbx; struct _PRIVILEGE_SET **
0x1402a5bb6  mov     [rsp+230h+var_200], ebx; unsigned int
0x1402a5bba  mov     dword ptr [rsp+230h+PostIrpRoutine], esi; unsigned int
0x1402a5bbe  mov     byte ptr [rsp+230h+CompletionRoutine], bl; char
0x1402a5bc2  xor     r9d, r9d; unsigned __int8
0x1402a5bc5  mov     r8, [r15+90h]; struct _SECURITY_SUBJECT_CONTEXT *
0x1402a5bcc  mov     rdx, r14; struct _FCB *
0x1402a5bcf  mov     rcx, r15; struct _IRP_CONTEXT *
0x1402a5bd2  call    ?RefsSeAccessCheck@@YAEPEAU_IRP_CONTEXT@@PEAU_FCB@@PEAU_SECURITY_SUBJECT_CONTEXT@@EEKKPEAPEAU_PRIVILEGE_SET@@PEAU_GENERIC_MAPPING@@DPEAKPEAU_ACCESS_REASONS@@PEAJPEAU_ACCESS_STATE@@@Z; RefsSeAccessCheck(_IRP_CONTEXT *,_FCB *,_SECURITY_SUBJECT_CONTEXT *,uchar,uchar,ulong,ulong,_PRIVILEGE_SET * *,_GENERIC_MAPPING *,char,ulong *,_ACCESS_REASONS *,long *,_ACCESS_STATE *)
0x1402a5bd7  test    al, al
0x1402a5bd9  jnz     short loc_1402A5C42
0x1402a5bdb  lea     rax, WPP_GLOBAL_Control
0x1402a5be2  mov     rcx, cs:WPP_GLOBAL_Control
0x1402a5be9  cmp     rcx, rax
0x1402a5bec  jz      short loc_1402A5C16
0x1402a5bee  test    [rcx+2Ch], esi
0x1402a5bf1  jz      short loc_1402A5C16
0x1402a5bf3  cmp     byte ptr [rcx+29h], 4
0x1402a5bf7  jb      short loc_1402A5C16
0x1402a5bf9  lea     edx, [rbx+7Ch]
0x1402a5bfc  mov     edi, 0C0000022h
0x1402a5c01  mov     r9d, edi
0x1402a5c04  lea     r8, WPP_bbc83e81062238e0129655ea2ffc96b5_Traceguids
0x1402a5c0b  mov     rcx, [rcx+18h]
0x1402a5c0f  call    WPP_SF_d
0x1402a5c14  jmp     short loc_1402A5C1B
0x1402a5c16  mov     edi, 0C0000022h
0x1402a5c1b  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402a5c21  test    al, al
0x1402a5c23  jz      short loc_1402A5C3B
0x1402a5c25  mov     r9d, 1FDAh; unsigned int
0x1402a5c2b  lea     r8, aFileinfoC; "FileInfo.c"
0x1402a5c32  xor     edx, edx; struct _IRP_CONTEXT *
  ... truncated ...
```
