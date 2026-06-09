# CClfsBaseFilePersisted::LoadContainerQ(ulong * const,ulong,uchar,uchar,_CLS_LSN,ulong &,ulong &,unsigned __int64 &)

- ea: `0x14005ed70`
- end: `0x14005fbe0`
- name: `?LoadContainerQ@CClfsBaseFilePersisted@@QEAAJQEAKKEET_CLS_LSN@@AEAK2AEA_K@Z`
- size: `3696`
- prototype: `__int64 __usercall@<rax>(CClfsBaseFilePersisted *__hidden this@<rcx>, unsigned int *const@<rdx>, unsigned int@<r8d>, unsigned __int8@<r9b>, char, union _CLS_LSN, unsigned int *, unsigned int *, unsigned __int64 *)`
- caller_count: `3`
- callee_count: `35`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x140005f1c`
- `0x140040444`
- `0x140076e00`

## callees

- `0x14000b6b0`
- `0x14000d71c`
- `0x14000f7bc`
- `0x1400121e4`
- `0x14001228c`
- `0x140012384`
- `0x140012418`
- `0x140017f20`
- `0x140017f80`
- `0x140018280`
- `0x140034558`
- `0x140039a00`
- `0x14003a7cc`
- `0x14003be24`
- `0x14003be98`
- `0x14003c9fc`
- `0x14003ed2c`
- `0x14005ed70`
- `0x140060154`
- `0x1400616cc`
- `0x140061e00`
- `0x140062a30`
- `0x140062ad8`
- `0x140062c20`
- `0x140062c60`
- `0x140062df0`
- `0x140063844`
- `0x140063b84`
- `0x14006a6fc`
- `0x14006c210`
- `0x14006e00c`
- `0x14007493c`
- `0x140075d10`
- `0x14007634c`
- `0x140078d5c`

## import_xrefs

- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14005ee55`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14005ee55`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14005f3b2`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14005f544`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14005f3b2`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14005f544`
- `ntoskrnl!RtlSetBits` at `0x14005f99f`
- `ntoskrnl!RtlSetBits` at `0x14005f99f`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14005f73f`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14005f73f`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14005f710`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14005f710`
- `ntoskrnl!SeLockSubjectContext` at `0x14005f724`
- `ntoskrnl!SeLockSubjectContext` at `0x14005f724`
- `ntoskrnl!SeAccessCheck` at `0x14005f798`
- `ntoskrnl!SeAccessCheck` at `0x14005f798`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14005f7ae`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14005f7ae`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14005f7c2`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14005f7c2`
- `ntoskrnl!RtlInitUnicodeString` at `0x14005f15a`
- `ntoskrnl!RtlInitUnicodeString` at `0x14005f348`
- `ntoskrnl!RtlInitUnicodeString` at `0x14005f15a`
- `ntoskrnl!RtlInitUnicodeString` at `0x14005f348`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005f108`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005f7d3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005f876`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005fa87`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005fba6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005fbbe`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007a2da`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007a2f2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005f108`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005f7d3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005f876`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005fa87`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005fba6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005fbbe`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007a2da`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007a2f2`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14005f02b`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14005fa09`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14005f02b`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14005fa09`

## pseudocode

```c
__int64 __fastcall CClfsBaseFilePersisted::LoadContainerQ(
        CClfsBaseFilePersisted *this,
        unsigned int *const a2,
        int a3,
        unsigned __int8 a4,
        char a5,
        union _CLS_LSN a6,
        unsigned int *a7,
        unsigned int *a8,
        unsigned __int64 *a9)
{
  unsigned int *v9; // r14
  struct _CLFS_CLIENT_CONTEXT *v11; // r12
  unsigned __int64 v12; // rdi
  int v13; // esi
  unsigned int *v14; // r13
  unsigned int i; // ecx
  unsigned __int64 v16; // rcx
  struct _CLFS_BASE_RECORD_HEADER *BaseLogRecord; // rbx
  unsigned __int64 v18; // r8
  int Symbol; // edi
  __int64 v20; // rdx
  unsigned int j; // r14d
  int v22; // edx
  _OWORD *v23; // rbx
  unsigned int v24; // ecx
  unsigned int k; // edi
  int v26; // edx
  unsigned int *PoolWithTag; // rax
  unsigned int *v28; // rsi
  unsigned int v29; // r8d
  _OWORD *v30; // rax
  __int64 v31; // rcx
  __int64 v32; // r13
  int v33; // esi
  unsigned int v34; // ebx
  _DWORD *v35; // rax
  const WCHAR *v36; // rax
  const WCHAR *v37; // rbx
  struct _CLFS_CONTAINER_CONTEXT *v38; // rsi
  unsigned __int64 v39; // rax
  int v40; // eax
  struct _UNICODE_STRING v41; // xmm0
  PVOID v42; // rax
  __int64 v43; // rdx
  CClfsAuthContainer *v44; // rcx
  unsigned __int8 v45; // r12
  int v46; // eax
  unsigned int *v47; // rbx
  PVOID v48; // rax
  __int64 v49; // rdx
  unsigned int *v50; // r8
  CClfsContainer *v51; // rcx
  int v52; // eax
  int v53; // ebx
  int IsEnabledDeviceUsageNoInline; // eax
  const unsigned __int64 *v55; // r12
  unsigned __int64 v56; // rcx
  struct CClfsAuthContainer *v57; // rcx
  KPROCESSOR_MODE AccessMode; // bl
  struct _GENERIC_MAPPING *GenericMapping; // rax
  PSECURITY_DESCRIPTOR v60; // rdi
  BOOLEAN v61; // bl
  __int64 v62; // rbx
  struct _CLFS_BASE_RECORD_HEADER *v63; // rax
  __int64 v64; // rax
  unsigned int v65; // eax
  unsigned int v66; // eax
  char v67; // al
  char v68; // r12
  SIZE_T v69; // rax
  PVOID v70; // rax
  void *v71; // rbx
  int v72; // edx
  int v73; // r8d
  int v74; // r9d
  int PreviouslyGrantedAccess; // [rsp+20h] [rbp-138h]
  BOOLEAN v77; // [rsp+50h] [rbp-108h]
  struct _CLFS_CLIENT_CONTEXT *v78; // [rsp+58h] [rbp-100h] BYREF
  char v79; // [rsp+60h] [rbp-F8h]
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+68h] [rbp-F0h] BYREF
  int v81; // [rsp+70h] [rbp-E8h]
  int v82; // [rsp+74h] [rbp-E4h]
  unsigned int v83; // [rsp+78h] [rbp-E0h]
  PVOID P; // [rsp+80h] [rbp-D8h] BYREF
  int AccessStatus; // [rsp+88h] [rbp-D0h] BYREF
  DWORD GrantedAccess; // [rsp+8Ch] [rbp-CCh] BYREF
  unsigned int v87; // [rsp+90h] [rbp-C8h]
  struct _CLFS_CONTAINER_CONTEXT *v88; // [rsp+98h] [rbp-C0h] BYREF
  UNICODE_STRING DestinationString; // [rsp+A0h] [rbp-B8h] BYREF
  struct _UNICODE_STRING v90; // [rsp+B0h] [rbp-A8h] BYREF
  unsigned __int64 v91; // [rsp+C0h] [rbp-98h] BYREF
  struct _UNICODE_STRING v92; // [rsp+D0h] [rbp-88h] BYREF
  void *Src; // [rsp+E0h] [rbp-78h]
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+E8h] [rbp-70h] BYREF
  unsigned __int64 v95; // [rsp+108h] [rbp-50h] BYREF
  unsigned int v96[2]; // [rsp+110h] [rbp-48h]
  int v98; // [rsp+170h] [rbp+18h] BYREF
  unsigned __int8 v99; // [rsp+178h] [rbp+20h]

  v99 = a4;
  v98 = a3;
  v9 = a2;
  v91 = 0;
  *(_QWORD *)&v90.Length = 0;
  v90.Buffer = 0;
  *(_QWORD *)&DestinationString.Length = 0;
  DestinationString.Buffer = 0;
  *(_QWORD *)&v92.Length = 0;
  v92.Buffer = 0;
  v11 = 0;
  v78 = 0;
  v12 = *(_QWORD *)(*((_QWORD *)this + 6) + 48LL);
  P = 0;
  SecurityDescriptor = 0;
  v13 = 0;
  a6.offset.idxRecord = 0;
  LOBYTE(v98) = 0;
  v79 = 0;
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  GrantedAccess = 0;
  AccessStatus = 0;
  *a9 = 0;
  v14 = a7;
  *a7 = -1;
  *a8 = 0;
  for ( i = 0; i < 0x400; ++i )
    a2[i] = -1;
  v77 = ExAcquireResourceExclusiveLite(*((PERESOURCE *)this + 4), 1u);
  BaseLogRecord = CClfsBaseFile::GetBaseLogRecord(this);
  if ( !BaseLogRecord || (v20 = *(unsigned int *)(v12 + 104), (unsigned int)v20 > *(unsigned __int16 *)(v12 + 4) << 9) )
  {
    Symbol = -1072037875;
    v9 = a2;
LABEL_160:
    v47 = a8;
    goto LABEL_161;
  }
  v16 = (unsigned __int64)BaseLogRecord + 4920;
  v18 = (unsigned __int64)BaseLogRecord + *((unsigned int *)BaseLogRecord + 1226) + 4920;
  if ( v18 < (unsigned __int64)BaseLogRecord + 4920 || (v16 = v20 + v12, v20 + v12 < v12) || v18 > v16 )
  {
LABEL_29:
    Symbol = -1072037875;
    goto LABEL_158;
  }
  Symbol = CClfsBaseFile::ValidateOffsets(this, BaseLogRecord);
  if ( Symbol < 0 )
  {
LABEL_159:
    LOBYTE(v18) = v77;
    goto LABEL_160;
  }
  Src = (char *)BaseLogRecord + 808;
  v87 = CClfsBaseFile::ContainerCount(this);
  LODWORD(v18) = 0;
  for ( j = 0; ; ++j )
  {
    v82 = v18;
    if ( j >= 0x400 )
      break;
    v16 = j;
    v22 = *((_DWORD *)BaseLogRecord + j + 202);
    if ( v22 )
    {
      v88 = 0;
      Symbol = CClfsBaseFile::GetSymbol(this, v22, v18, &v88);
      if ( Symbol < 0 )
        goto LABEL_14;
      if ( (*((_BYTE *)v88 + 36) & 1) == 0 )
        v81 = ++v13;
    }
    LODWORD(v18) = j + 1;
  }
  if ( !v87 )
  {
    *v14 = 0;
    if ( v13 )
      Symbol = -1072037875;
    goto LABEL_15;
  }
  if ( v13 != v87 )
  {
LABEL_14:
    Symbol = -1072037875;
LABEL_15:
    v11 = v78;
LABEL_158:
    v9 = a2;
    goto LABEL_159;
  }
  v23 = (_OWORD *)((char *)BaseLogRecord + 312);
  v24 = 0;
  for ( k = 0; ; ++k )
  {
    v82 = v24;
    if ( k >= 0x7C )
      break;
    v26 = *((_DWORD *)v23 + k);
    if ( (unsigned int)(v26 - 1) <= 0xFFFFFFFD )
    {
      v78 = 0;
      if ( (int)CClfsBaseFile::GetSymbol(this, v26, v24, &v78) < 0 )
      {
        v11 = 0;
        v78 = 0;
        goto LABEL_29;
      }
    }
    v24 = k + 1;
  }
  v11 = 0;
  v78 = 0;
  PoolWithTag = (unsigned int *)ExAllocatePoolWithTag(PagedPool, 0x11F0u, 0x73666C43u);
  v28 = PoolWithTag;
  if ( !PoolWithTag )
  {
    Symbol = -1073741670;
    goto LABEL_158;
  }
  memmove(PoolWithTag, Src, 0x1000u);
  v30 = v28 + 1024;
  v31 = 3;
  do
  {
    *v30 = *v23;
    v30[1] = v23[1];
    v30[2] = v23[2];
    v30[3] = v23[3];
    v30[4] = v23[4];
    v30[5] = v23[5];
    v30[6] = v23[6];
    v30[7] = v23[7];
    v30 += 8;
    v23 += 8;
    --v31;
  }
  while ( v31 );
  *v30 = *v23;
  v30[1] = v23[1];
  v30[2] = v23[2];
  v30[3] = v23[3];
  v30[4] = v23[4];
  v30[5] = v23[5];
  v30[6] = v23[6];
  Symbol = CClfsBaseFile::ValidateRgOffsets(this, v28, v29);
  ExFreePoolWithTag(v28, 0);
  if ( Symbol < 0 )
    goto LABEL_158;
  v32 = 0;
  v83 = 0;
  v33 = 0;
  v81 = 0;
  while ( 1 )
  {
    LODWORD(v18) = 1024;
    if ( (unsigned int)v32 >= 0x400 )
      break;
    v88 = 0;
    RtlInitUnicodeString(&DestinationString, &word_14001C188);
    v34 = *((_DWORD *)Src + v32);
    if ( !v34 )
      goto LABEL_141;
    if ( v34 < 0x1338 )
      goto LABEL_40;
    if ( (int)CClfsBaseFile::GetSymbol(this, v34, v32, &v88) < 0 )
      goto LABEL_40;
    v35 = CClfsBaseFile::OffsetToAddr(this, v34);
    if ( !v35 )
      goto LABEL_40;
    v36 = (const WCHAR *)CClfsBaseFile::OffsetToAddr(this, *(v35 - 4));
    v37 = v36;
    if ( !v36 )
      goto LABEL_40;
    if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
    {
      WPP_SF_slS(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        39,
        (unsigned int)WPP_1169606c7f2f3d218636bb1790f0fe72_Traceguids,
        (unsigned int)"CClfsBaseFilePersisted::LoadContainerQ",
        231,
        (__int64)v36);
    }
    v38 = v88;
    if ( *((_DWORD *)v88 + 5) == -1 )
    {
      *((_QWORD *)v88 + 3) = 0;
      Symbol = CClfsBaseFilePersisted::RemoveContainer(this, v32);
      if ( Symbol < 0 )
        goto LABEL_41;
      v33 = v81;
      goto LABEL_141;
    }
    v16 = (unsigned __int64)a9;
    if ( *a9 )
    {
      if ( *a9 != *((_QWORD *)v88 + 1) )
        goto LABEL_40;
    }
    else
    {
      v39 = *((_QWORD *)v88 + 1);
      if ( !v39 || (v39 & 0x7FFFF) != 0 )
        goto LABEL_40;
      *a9 = v39;
    }
    v40 = *((_DWORD *)v38 + 9);
    if ( (v40 & 8) != 0 )
    {
      if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x8000000) != 0 )
      {
        WPP_SF_slid(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          40,
          (unsigned int)WPP_1169606c7f2f3d218636bb1790f0fe72_Traceguids,
          (unsigned int)"CClfsBaseFilePersisted::LoadContainerQ",
          61,
          (char)this,
          *((_DWORD *)v38 + 5));
      }
      *((_DWORD *)v38 + 9) &= ~8u;
      v40 = *((_DWORD *)v38 + 9);
    }
    if ( (v40 & 0x20) != 0 )
    {
      if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x8000000) != 0 )
      {
        WPP_SF_slid(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          41,
          (unsigned int)WPP_1169606c7f2f3d218636bb1790f0fe72_Traceguids,
          (unsigned int)"CClfsBaseFilePersisted::LoadContainerQ",
          73,
          (char)this,
          *((_DWORD *)v38 + 5));
      }
      *((_DWORD *)v38 + 9) &= ~0x20u;
    }
    RtlInitUnicodeString(&DestinationString, v37);
    if ( ClfsIsContainerPathRelative(&DestinationString) )
    {
      Symbol = CClfsBaseFilePersisted::CreateAbsoluteContainerPath(this, &DestinationString, &v92);
      if ( Symbol < 0 )
        goto LABEL_41;
      v79 = 1;
      v41 = v92;
    }
    else
    {
      v41 = DestinationString;
    }
    v90 = v41;
    v42 = ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)&WPP_MAIN_CB.DeviceQueue.32);
    if ( v42 )
      v16 = CClfsAuthContainer::CClfsAuthContainer(v42, v43, *((unsigned int *)this + 58), *((_QWORD *)this + 30));
    else
      v16 = 0;
    *((_QWORD *)v38 + 3) = v16;
    if ( !v16 )
    {
LABEL_74:
      Symbol = -1073741670;
      goto LABEL_41;
    }
    v95 = 2;
    *(_QWORD *)v96 = (unsigned int)v32;
    (**(void (__fastcall ***)(CClfsBaseFile *))v16)((CClfsBaseFile *)v16);
    Symbol = CClfsAuthContainer::Initialize(*((CClfsAuthContainer **)v38 + 3), &v95, 2u);
    v44 = (CClfsAuthContainer *)*((_QWORD *)v38 + 3);
    if ( Symbol < 0 )
      goto LABEL_76;
    v45 = v99;
    v46 = CClfsAuthContainer::Open(
            v44,
            &v90,
            (CClfsBaseFilePersisted *)((char *)this + 176),
            v99,
            *((_QWORD *)this + 31),
            (unsigned __int8 *)&v98);
    Symbol = v46;
    if ( v46 < 0 )
    {
      if ( v46 != -1073741772 && v46 != -1073741807 && v46 != -1072037875 )
      {
        if ( v46 == -1073741766 )
          Symbol = -1072037873;
        goto LABEL_83;
      }
      if ( (*((_BYTE *)v38 + 36) & 1) == 0 )
      {
        v14 = a7;
        v47 = a8;
        if ( v46 != -1072037875 )
          Symbol = -1072037873;
        goto LABEL_87;
      }
      if ( v46 == -1073741807 || v46 == -1072037875 )
        CClfsAuthContainer::Remove(*((CClfsAuthContainer **)v38 + 3), &v90);
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v38 + 3) + 8LL))(*((_QWORD *)v38 + 3));
      *((_QWORD *)v38 + 3) = 0;
      v48 = ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)&WPP_MAIN_CB.DeviceQueue.32);
      if ( v48 )
        v16 = CClfsAuthContainer::CClfsAuthContainer(v48, v49, *((unsigned int *)this + 58), *((_QWORD *)this + 30));
      else
        v16 = 0;
      *((_QWORD *)v38 + 3) = v16;
      if ( !v16 )
        goto LABEL_74;
      (**(void (__fastcall ***)(CClfsBaseFile *))v16)((CClfsBaseFile *)v16);
      Symbol = CClfsAuthContainer::Initialize(*((CClfsAuthContainer **)v38 + 3), &v95, 2u);
      if ( Symbol < 0 )
        goto LABEL_83;
      if ( !P )
      {
        if ( a5 )
        {
          a6.offset.idxRecord = 0;
          v51 = *(CClfsContainer **)(*((_QWORD *)this + 19) + 120LL);
          if ( !v51 || (int)CClfsContainer::DuplicateSecurityDescriptor(v51, &P, v50, 0) < 0 )
          {
            Symbol = -1073741703;
LABEL_83:
            v44 = (CClfsAuthContainer *)*((_QWORD *)v38 + 3);
LABEL_76:
            (*(void (__fastcall **)(CClfsAuthContainer *))(*(_QWORD *)v44 + 8LL))(v44);
            *((_QWORD *)v38 + 3) = 0;
LABEL_41:
            v14 = a7;
            goto LABEL_15;
          }
        }
        else
        {
          v52 = CClfsContainer::DuplicateNullSecurityDescriptor(&P, 0);
          if ( v52 < 0 )
          {
            Symbol = v52;
            goto LABEL_83;
          }
        }
      }
      if ( (int)CClfsAuthContainer::Create(
                  *((CClfsAuthContainer **)v38 + 3),
                  &v90,
                  (const unsigned __int64 *)v38 + 1,
                  (CClfsBaseFilePersisted *)((char *)this + 176),
                  P,
                  v45,
                  *((_QWORD *)this + 31),
                  (unsigned __int8 *)&v98) < 0 )
      {
        Symbol = -1072037874;
        goto LABEL_83;
      }
    }
    v53 = *((_DWORD *)this + 36);
    if ( CClfsAuthContainer::GetRawSectorSize(*((CClfsAuthContainer **)v38 + 3)) != v53 )
    {
      Symbol = -1072037887;
      goto LABEL_83;
    }
    CClfsAuthContainer::GetContainerSize(*((CClfsAuthContainer **)v38 + 3), &v91);
    IsEnabledDeviceUsageNoInline = Feature_CLFS_AuthenticationExemptions__private_IsEnabledDeviceUsageNoInline();
    v55 = a9;
    v56 = *a9;
    if ( IsEnabledDeviceUsageNoInline )
    {
      if ( v56 > v91 )
      {
        if ( (*((_BYTE *)v38 + 36) & 1) == 0 )
          goto LABEL_110;
        v57 = (struct CClfsAuthContainer *)*((_QWORD *)v38 + 3);
        if ( !*((_DWORD *)v57 + 34) )
          goto LABEL_110;
        if ( (_BYTE)v98 )
        {
LABEL_132:
          Symbol = CClfsBaseFilePersisted::QueryContainerSecurity(v57, &SecurityDescriptor, 0, (unsigned int *)&a6);
          if ( Symbol < 0 )
          {
            (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v38 + 3) + 8LL))(*((_QWORD *)v38 + 3));
            *((_QWORD *)v38 + 3) = 0;
            goto LABEL_41;
          }
          SeCaptureSubjectContext(&SubjectContext);
          SeLockSubjectContext(&SubjectContext);
          AccessMode = *((_BYTE *)KeGetCurrentThread() + 562);
          GenericMapping = IoGetFileObjectGenericMapping();
          v60 = SecurityDescriptor;
          v61 = SeAccessCheck(
                  SecurityDescriptor,
                  &SubjectContext,
                  1u,
                  3u,
                  0,
                  0,
                  GenericMapping,
                  AccessMode,
                  &GrantedAccess,
                  &AccessStatus);
          SeUnlockSubjectContext(&SubjectContext);
          SeReleaseSubjectContext(&SubjectContext);
          ExFreePoolWithTag(v60, 0);
          if ( !v61 )
          {
            SecurityDescriptor = 0;
            (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v38 + 3) + 8LL))(*((_QWORD *)v38 + 3));
            *((_QWORD *)v38 + 3) = 0;
            Symbol = -1073741790;
            goto LABEL_41;
          }
          SecurityDescriptor = 0;
        }
        goto LABEL_118;
      }
    }
    else if ( v56 > v91 )
    {
      if ( (*((_BYTE *)v38 + 36) & 1) == 0 || !*((_DWORD *)this + 58) )
      {
LABEL_110:
        Symbol = -1072037875;
        goto LABEL_83;
      }
      if ( (_BYTE)v98 )
      {
        v57 = (struct CClfsAuthContainer *)*((_QWORD *)v38 + 3);
        goto LABEL_132;
      }
LABEL_118:
      Symbol = CClfsAuthContainer::FinishInitializeFile(*((CClfsAuthContainer **)v38 + 3), v55, *((_QWORD *)this + 31));
      if ( Symbol < 0 )
        goto LABEL_83;
    }
    if ( !a5 && (_BYTE)v98 )
    {
      Symbol = CClfsBaseFilePersisted::QueryContainerSecurity(
                 *((struct CClfsAuthContainer **)v38 + 3),
                 &SecurityDescriptor,
                 0,
                 (unsigned int *)&a6);
      if ( Symbol < 0 )
        goto LABEL_83;
      ExFreePoolWithTag(SecurityDescriptor, 0);
      SecurityDescriptor = 0;
    }
    if ( (*((_BYTE *)v38 + 36) & 1) != 0 )
    {
      *((_DWORD *)v38 + 9) = 2;
      v62 = *((_QWORD *)v38 + 3);
      Symbol = CClfsBaseFilePersisted::FlushImage(this);
      if ( Symbol < 0 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v62 + 8LL))(v62);
        v63 = CClfsBaseFile::GetBaseLogRecord(this);
        v14 = a7;
        v47 = a8;
        if ( v63 )
          *((_QWORD *)v38 + 3) = 0;
        goto LABEL_87;
      }
    }
    v64 = *((_DWORD *)v38 + 5) & 0x3FF;
    if ( a2[v64] != -1 )
      goto LABEL_110;
    a2[v64] = v32;
    v65 = *((_DWORD *)v38 + 5);
    if ( v65 < *a7 )
      *a7 = v65;
    v66 = *((_DWORD *)v38 + 5);
    if ( v66 >= *a8 )
      *a8 = v66 + 1;
    RtlSetBits((PRTL_BITMAP)this + 16, v32, 1u);
    v67 = *((_BYTE *)v38 + 36);
    v33 = v81;
    if ( (v67 & 1) == 0 )
      v33 = ++v81;
LABEL_141:
    v32 = (unsigned int)(v32 + 1);
    v83 = v32;
  }
  v68 = v87;
  if ( v33 != v87 )
  {
    v69 = 2 * (((unsigned __int64)*((unsigned __int16 *)this + 108) >> 1) + 1);
    if ( !is_mul_ok(((unsigned __int64)*((unsigned __int16 *)this + 108) >> 1) + 1, 2u) )
      v69 = -1;
    v70 = ExAllocatePoolWithTag(PagedPool, v69, 0x73666C43u);
    v71 = v70;
    if ( v70 )
    {
      memset(v70, 0, *((unsigned __int16 *)this + 108) + 2LL);
      memmove(v71, *((const void **)this + 28), *((unsigned __int16 *)this + 108));
      if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x8000000) != 0 )
      {
        WPP_SF_sdiSdd(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v72,
          v73,
          v74,
          PreviouslyGrantedAccess,
          (char)this,
          (__int64)v71,
          v33,
          v68);
      }
      ExFreePoolWithTag(v71, 0);
    }
    else
    {
      v16 = (unsigned __int64)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x8000000) != 0 )
      {
        WPP_SF_sdidd(*((_QWORD *)WPP_GLOBAL_Control + 3));
      }
    }
LABEL_40:
    Symbol = -1072037875;
    goto LABEL_41;
  }
  v14 = a7;
  v16 = *a7;
  v83 = *a7;
  v47 = a8;
  while ( (unsigned int)v16 < *a8 )
  {
    if ( a2[v16 & 0x3FF] >= 0x400 )
    {
      Symbol = -1072037875;
      break;
    }
    v16 = (unsigned int)(v16 + 1);
    v83 = v16;
  }
LABEL_87:
  v11 = v78;
  v9 = a2;
  LOBYTE(v18) = v77;
LABEL_161:
  if ( (_BYTE)v18 )
    CClfsBaseFile::UnlockImage(this);
  if ( v79 )
    CClfsBaseFilePersisted::DestroyAbsoluteContainerPath((CClfsBaseFilePersisted *)v16, &v92);
  if ( Symbol < 0 )
  {
    if ( *v14 != -1 )
      CClfsBaseFilePersisted::UnloadContainerQ(this, v9, v18, *v14, *v47);
    *v47 = 0;
    *v14 = 0;
  }
  if ( v11 )
    CClfsBaseFile::ReleaseClientContext(this, &v78);
  if ( P )
    ExFreePoolWithTag(P, 0);
  if ( SecurityDescriptor )
    ExFreePoolWithTag(SecurityDescriptor, 0);
  return (unsigned int)Symbol;
}

```

## disassembly

```asm
0x14005ed70  mov     r11, rsp
0x14005ed73  mov     [r11+20h], r9b
0x14005ed77  mov     [r11+18h], r8d
0x14005ed7b  mov     [r11+10h], rdx
0x14005ed7f  mov     [r11+8], rcx
0x14005ed83  push    rbx
0x14005ed84  push    rsi
0x14005ed85  push    rdi
0x14005ed86  push    r12
0x14005ed88  push    r13
0x14005ed8a  push    r14
0x14005ed8c  push    r15
0x14005ed8e  sub     rsp, 120h
0x14005ed95  mov     r14, rdx
0x14005ed98  mov     r15, rcx
0x14005ed9b  xor     edx, edx
0x14005ed9d  mov     [r11-98h], rdx
0x14005eda4  mov     [r11-0A8h], rdx
0x14005edab  mov     [r11-0A0h], rdx
0x14005edb2  mov     [r11-0B8h], rdx
0x14005edb9  mov     [r11-0B0h], rdx
0x14005edc0  mov     [r11-88h], rdx
0x14005edc7  mov     [r11-80h], rdx
0x14005edcb  mov     r12d, edx
0x14005edce  mov     [rsp+158h+var_100], rdx
0x14005edd3  mov     rax, [rcx+30h]
0x14005edd7  mov     rdi, [rax+30h]
0x14005eddb  mov     [r11-0D8h], rdx
0x14005ede2  mov     [rsp+158h+SecurityDescriptor], rdx
0x14005ede7  mov     esi, edx
0x14005ede9  mov     [r11+30h], edx
0x14005eded  mov     [rsp+158h+var_104], edx
0x14005edf1  mov     [rsp+158h+var_108], dl
0x14005edf5  mov     [r11+18h], dl
0x14005edf9  mov     [rsp+158h+var_F8], dl
0x14005edfd  xorps   xmm0, xmm0
0x14005ee00  movups  xmmword ptr [r11-70h], xmm0
0x14005ee05  movups  xmmword ptr [r11-60h], xmm0
0x14005ee0a  mov     [rsp+158h+var_CC], edx
0x14005ee11  mov     [rsp+158h+var_D0], edx
0x14005ee18  mov     rcx, [rsp+158h+arg_40]
0x14005ee20  mov     [rcx], rdx
0x14005ee23  or      r8d, 0FFFFFFFFh
0x14005ee27  mov     r13, [rsp+158h+arg_30]
0x14005ee2f  mov     [r13+0], r8d
0x14005ee33  mov     rax, [rsp+158h+arg_38]
0x14005ee3b  mov     [rax], edx
0x14005ee3d  mov     ecx, edx
0x14005ee3f  mov     eax, ecx
0x14005ee41  mov     [r14+rax*4], r8d
0x14005ee45  inc     ecx
0x14005ee47  cmp     ecx, 400h
0x14005ee4d  jb      short loc_14005EE3F
0x14005ee4f  mov     dl, 1; Wait
0x14005ee51  mov     rcx, [r15+20h]; Resource
0x14005ee55  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14005ee5c  nop     dword ptr [rax+rax+00h]
0x14005ee61  mov     r8b, al
0x14005ee64  mov     [rsp+158h+var_108], al
0x14005ee68  mov     rcx, r15; this
0x14005ee6b  call    ?GetBaseLogRecord@CClfsBaseFile@@IEAAPEAU_CLFS_BASE_RECORD_HEADER@@XZ; CClfsBaseFile::GetBaseLogRecord(void)
0x14005ee70  mov     rbx, rax
0x14005ee73  test    rax, rax
0x14005ee76  jnz     short loc_14005EE93
0x14005ee78  mov     r14d, 0C01A000Dh
0x14005ee7e  mov     edi, r14d
0x14005ee81  mov     [rsp+158h+var_104], r14d
0x14005ee86  mov     r14, [rsp+158h+arg_8]
0x14005ee8e  jmp     loc_14005FB2F
0x14005ee93  mov     edx, [rdi+68h]
0x14005ee96  movzx   eax, word ptr [rdi+4]
0x14005ee9a  shl     eax, 9
0x14005ee9d  cmp     edx, eax
0x14005ee9f  ja      short loc_14005EE78
0x14005eea1  lea     rcx, [rbx+1338h]
0x14005eea8  mov     eax, [rbx+1328h]
0x14005eeae  lea     r8, [rax+rcx]
0x14005eeb2  cmp     r8, rcx
0x14005eeb5  jb      loc_14005EFF9
0x14005eebb  mov     eax, edx
0x14005eebd  lea     rcx, [rdx+rdi]
0x14005eec1  cmp     rcx, rdi
0x14005eec4  jb      loc_14005EFF9
0x14005eeca  cmp     r8, rcx
0x14005eecd  ja      loc_14005EFF9
0x14005eed3  mov     rdx, rbx; struct _CLFS_BASE_RECORD_HEADER *
0x14005eed6  mov     rcx, r15; this
0x14005eed9  call    ?ValidateOffsets@CClfsBaseFile@@IEAAJQEAU_CLFS_BASE_RECORD_HEADER@@@Z; CClfsBaseFile::ValidateOffsets(_CLFS_BASE_RECORD_HEADER * const)
0x14005eede  mov     edi, eax
0x14005eee0  mov     [rsp+158h+var_104], eax
0x14005eee4  test    eax, eax
0x14005eee6  js      loc_14005FB2A
0x14005eeec  lea     rax, [rbx+328h]
0x14005eef3  mov     [rsp+158h+Src], rax
0x14005eefb  mov     rcx, r15; this
0x14005eefe  call    ?ContainerCount@CClfsBaseFile@@QEAAKXZ; CClfsBaseFile::ContainerCount(void)
0x14005ef03  mov     [rsp+158h+var_C8], eax
0x14005ef0a  xor     r8d, r8d; unsigned int
0x14005ef0d  xor     r14d, r14d
0x14005ef10  mov     [rsp+158h+var_E4], r8d
0x14005ef15  cmp     r14d, 400h
0x14005ef1c  jnb     short loc_14005EF87
0x14005ef1e  mov     ecx, r14d
0x14005ef21  mov     edx, [rbx+rcx*4+328h]; int
0x14005ef28  test    edx, edx
0x14005ef2a  jz      short loc_14005EF7E
0x14005ef2c  mov     [rsp+158h+var_C0], 0
0x14005ef38  lea     r9, [rsp+158h+var_C0]; struct _CLFS_CONTAINER_CONTEXT **
0x14005ef40  mov     rcx, r15; this
0x14005ef43  call    ?GetSymbol@CClfsBaseFile@@QEAAJJKPEAPEAU_CLFS_CONTAINER_CONTEXT@@@Z; CClfsBaseFile::GetSymbol(long,ulong,_CLFS_CONTAINER_CONTEXT * *)
0x14005ef48  mov     edi, eax
0x14005ef4a  mov     [rsp+158h+var_104], eax
0x14005ef4e  test    eax, eax
0x14005ef50  jns     short loc_14005EF6A
0x14005ef52  mov     r14d, 0C01A000Dh
0x14005ef58  mov     edi, r14d
0x14005ef5b  mov     [rsp+158h+var_104], r14d
0x14005ef60  mov     r12, [rsp+158h+var_100]
0x14005ef65  jmp     loc_14005FB22
0x14005ef6a  mov     rax, [rsp+158h+var_C0]
0x14005ef72  test    byte ptr [rax+24h], 1
0x14005ef76  jnz     short loc_14005EF7E
0x14005ef78  inc     esi
0x14005ef7a  mov     [rsp+158h+var_E8], esi
0x14005ef7e  lea     r8d, [r14+1]
0x14005ef82  mov     r14d, r8d
0x14005ef85  jmp     short loc_14005EF10
0x14005ef87  mov     r12d, [rsp+158h+var_C8]
0x14005ef8f  test    r12d, r12d
0x14005ef92  jnz     short loc_14005EFAA
0x14005ef94  mov     [r13+0], r12d
0x14005ef98  mov     r14d, 0C01A000Dh
0x14005ef9e  test    esi, esi
0x14005efa0  cmovnz  edi, r14d
0x14005efa4  mov     [rsp+158h+var_104], edi
0x14005efa8  jmp     short loc_14005EF60
0x14005efaa  cmp     esi, r12d
0x14005efad  jnz     short loc_14005EF52
0x14005efaf  add     rbx, 138h
0x14005efb6  xor     ecx, ecx
0x14005efb8  xor     edi, edi
0x14005efba  mov     [rsp+158h+var_E4], ecx
0x14005efbe  cmp     edi, 7Ch ; '|'
0x14005efc1  jnb     short loc_14005F013
0x14005efc3  mov     eax, edi
0x14005efc5  mov     edx, [rbx+rax*4]; int
0x14005efc8  lea     eax, [rdx-1]
0x14005efcb  cmp     eax, 0FFFFFFFDh
0x14005efce  ja      short loc_14005F00C
0x14005efd0  mov     [rsp+158h+var_100], 0
0x14005efd9  lea     r9, [rsp+158h+var_100]; struct _CLFS_CLIENT_CONTEXT **
0x14005efde  mov     r8b, cl; unsigned __int8
0x14005efe1  mov     rcx, r15; this
0x14005efe4  call    ?GetSymbol@CClfsBaseFile@@QEAAJJEPEAPEAU_CLFS_CLIENT_CONTEXT@@@Z; CClfsBaseFile::GetSymbol(long,uchar,_CLFS_CLIENT_CONTEXT * *)
0x14005efe9  mov     [rsp+158h+var_104], eax
0x14005efed  test    eax, eax
0x14005efef  jns     short loc_14005F00C
0x14005eff1  xor     r12d, r12d
0x14005eff4  mov     [rsp+158h+var_100], r12
0x14005eff9  mov     r14d, 0C01A000Dh
0x14005efff  mov     edi, r14d
0x14005f002  mov     [rsp+158h+var_104], r14d
0x14005f007  jmp     loc_14005FB22
0x14005f00c  lea     ecx, [rdi+1]
0x14005f00f  mov     edi, ecx
0x14005f011  jmp     short loc_14005EFBA
0x14005f013  xor     r12d, r12d
0x14005f016  mov     [rsp+158h+var_100], r12
0x14005f01b  mov     edx, 11F0h; NumberOfBytes
0x14005f020  lea     ecx, [r12+1]; PoolType
0x14005f025  mov     r8d, 73666C43h; Tag
0x14005f02b  call    cs:__imp_ExAllocatePoolWithTag
0x14005f032  nop     dword ptr [rax+rax+00h]
0x14005f037  mov     rsi, rax
0x14005f03a  test    rax, rax
0x14005f03d  jnz     short loc_14005F04D
0x14005f03f  mov     edi, 0C000009Ah
0x14005f044  mov     [rsp+158h+var_104], edi
0x14005f048  jmp     loc_14005FB22
0x14005f04d  mov     r8d, 1000h; Size
0x14005f053  mov     rdx, [rsp+158h+Src]; Src
0x14005f05b  mov     rcx, rsi; void *
0x14005f05e  call    memmove
0x14005f063  lea     rax, [rsi+1000h]
0x14005f06a  mov     ecx, 3
0x14005f06f  lea     edx, [rcx+7Dh]
0x14005f072  movups  xmm0, xmmword ptr [rbx]
0x14005f075  movups  xmmword ptr [rax], xmm0
0x14005f078  movups  xmm1, xmmword ptr [rbx+10h]
0x14005f07c  movups  xmmword ptr [rax+10h], xmm1
0x14005f080  movups  xmm0, xmmword ptr [rbx+20h]
0x14005f084  movups  xmmword ptr [rax+20h], xmm0
0x14005f088  movups  xmm1, xmmword ptr [rbx+30h]
0x14005f08c  movups  xmmword ptr [rax+30h], xmm1
0x14005f090  movups  xmm0, xmmword ptr [rbx+40h]
0x14005f094  movups  xmmword ptr [rax+40h], xmm0
0x14005f098  movups  xmm1, xmmword ptr [rbx+50h]
0x14005f09c  movups  xmmword ptr [rax+50h], xmm1
0x14005f0a0  movups  xmm0, xmmword ptr [rbx+60h]
0x14005f0a4  movups  xmmword ptr [rax+60h], xmm0
0x14005f0a8  movups  xmm1, xmmword ptr [rbx+70h]
0x14005f0ac  movups  xmmword ptr [rax+70h], xmm1
0x14005f0b0  add     rax, rdx
0x14005f0b3  add     rbx, rdx
0x14005f0b6  sub     rcx, 1
0x14005f0ba  jnz     short loc_14005F072
0x14005f0bc  movups  xmm0, xmmword ptr [rbx]
0x14005f0bf  movups  xmmword ptr [rax], xmm0
0x14005f0c2  movups  xmm1, xmmword ptr [rbx+10h]
0x14005f0c6  movups  xmmword ptr [rax+10h], xmm1
0x14005f0ca  movups  xmm0, xmmword ptr [rbx+20h]
0x14005f0ce  movups  xmmword ptr [rax+20h], xmm0
0x14005f0d2  movups  xmm1, xmmword ptr [rbx+30h]
0x14005f0d6  movups  xmmword ptr [rax+30h], xmm1
0x14005f0da  movups  xmm0, xmmword ptr [rbx+40h]
0x14005f0de  movups  xmmword ptr [rax+40h], xmm0
0x14005f0e2  movups  xmm1, xmmword ptr [rbx+50h]
0x14005f0e6  movups  xmmword ptr [rax+50h], xmm1
0x14005f0ea  movups  xmm0, xmmword ptr [rbx+60h]
0x14005f0ee  movups  xmmword ptr [rax+60h], xmm0
0x14005f0f2  mov     rdx, rsi; Base
0x14005f0f5  mov     rcx, r15; this
0x14005f0f8  call    ?ValidateRgOffsets@CClfsBaseFile@@IEAAJPEAKK@Z; CClfsBaseFile::ValidateRgOffsets(ulong *,ulong)
0x14005f0fd  mov     edi, eax
0x14005f0ff  mov     [rsp+158h+var_104], eax
0x14005f103  xor     edx, edx; Tag
0x14005f105  mov     rcx, rsi; P
0x14005f108  call    cs:__imp_ExFreePoolWithTag
0x14005f10f  nop     dword ptr [rax+rax+00h]
0x14005f114  test    edi, edi
0x14005f116  js      loc_14005FB22
0x14005f11c  xor     r13d, r13d
0x14005f11f  mov     [rsp+158h+var_E0], r13d
0x14005f124  xor     esi, esi
0x14005f126  mov     [rsp+158h+var_E8], esi
0x14005f12a  mov     r14d, 0C01A000Dh
0x14005f130  mov     r8d, 400h
0x14005f136  cmp     r13d, r8d
0x14005f139  jnb     loc_14005F9C9
0x14005f13f  mov     [rsp+158h+var_C0], 0
0x14005f14b  lea     rdx, word_14001C188; SourceString
0x14005f152  lea     rcx, [rsp+158h+DestinationString]; DestinationString
0x14005f15a  call    cs:__imp_RtlInitUnicodeString
0x14005f161  nop     dword ptr [rax+rax+00h]
0x14005f166  mov     r12d, r13d
0x14005f169  mov     rax, [rsp+158h+Src]
0x14005f171  mov     ebx, [rax+r13*4]
0x14005f175  test    ebx, ebx
0x14005f177  jnz     short loc_14005F17E
0x14005f179  jmp     loc_14005F9BC
0x14005f17e  cmp     ebx, 1338h
0x14005f184  jnb     short loc_14005F19B
0x14005f186  mov     edi, r14d
0x14005f189  mov     [rsp+158h+var_104], r14d
0x14005f18e  mov     r13, [rsp+158h+arg_30]
0x14005f196  jmp     loc_14005EF60
0x14005f19b  lea     r9, [rsp+158h+var_C0]; struct _CLFS_CONTAINER_CONTEXT **
0x14005f1a3  mov     r8d, r13d; unsigned int
0x14005f1a6  mov     edx, ebx; int
0x14005f1a8  mov     rcx, r15; this
0x14005f1ab  call    ?GetSymbol@CClfsBaseFile@@QEAAJJKPEAPEAU_CLFS_CONTAINER_CONTEXT@@@Z; CClfsBaseFile::GetSymbol(long,ulong,_CLFS_CONTAINER_CONTEXT * *)
0x14005f1b0  mov     [rsp+158h+var_104], eax
0x14005f1b4  test    eax, eax
0x14005f1b6  js      short loc_14005F186
0x14005f1b8  mov     edx, ebx; unsigned int
0x14005f1ba  mov     rcx, r15; this
0x14005f1bd  call    ?OffsetToAddr@CClfsBaseFile@@IEAAPEAXK@Z; CClfsBaseFile::OffsetToAddr(ulong)
0x14005f1c2  test    rax, rax
0x14005f1c5  jz      short loc_14005F186
0x14005f1c7  mov     edx, [rax-10h]; unsigned int
0x14005f1ca  mov     rcx, r15; this
0x14005f1cd  call    ?OffsetToAddr@CClfsBaseFile@@IEAAPEAXK@Z; CClfsBaseFile::OffsetToAddr(ulong)
0x14005f1d2  mov     rbx, rax
0x14005f1d5  test    rax, rax
0x14005f1d8  jz      short loc_14005F186
0x14005f1da  mov     rcx, cs:WPP_GLOBAL_Control
0x14005f1e1  lea     rdx, WPP_GLOBAL_Control
0x14005f1e8  cmp     rcx, rdx
0x14005f1eb  jz      short loc_14005F226
0x14005f1ed  test    dword ptr [rcx+2Ch], 4000000h
0x14005f1f4  jz      short loc_14005F226
0x14005f1f6  mov     edx, 27h ; '''
0x14005f1fb  mov     [rsp+158h+Privileges], rax
0x14005f200  mov     [rsp+158h+PreviouslyGrantedAccess], 37E7h
0x14005f208  lea     r9, aCclfsbasefilep; "CClfsBaseFilePersisted::LoadContainerQ"
0x14005f20f  lea     r8, WPP_1169606c7f2f3d218636bb1790f0fe72_Traceguids
0x14005f216  mov     rcx, [rcx+18h]
0x14005f21a  call    WPP_SF_slS
0x14005f21f  lea     rdx, WPP_GLOBAL_Control
0x14005f226  mov     rsi, [rsp+158h+var_C0]
0x14005f22e  cmp     dword ptr [rsi+14h], 0FFFFFFFFh
0x14005f232  jnz     short loc_14005F25E
0x14005f234  mov     qword ptr [rsi+18h], 0
0x14005f23c  mov     edx, r13d; unsigned int
0x14005f23f  mov     rcx, r15; this
0x14005f242  call    ?RemoveContainer@CClfsBaseFilePersisted@@QEAAJK@Z; CClfsBaseFilePersisted::RemoveContainer(ulong)
0x14005f247  mov     edi, eax
0x14005f249  mov     [rsp+158h+var_104], eax
0x14005f24d  test    eax, eax
0x14005f24f  js      loc_14005F18E
  ... truncated ...
```
