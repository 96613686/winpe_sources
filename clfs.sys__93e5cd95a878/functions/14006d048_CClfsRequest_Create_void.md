# CClfsRequest::Create(void)

- ea: `0x14006d048`
- end: `0x14006dda9`
- name: `?Create@CClfsRequest@@AEAAJXZ`
- size: `3425`
- prototype: `int(CClfsRequest *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14006c874`

## callees

- `0x1400011c0`
- `0x140005840`
- `0x140005f1c`
- `0x140007f2c`
- `0x14000b840`
- `0x14000ed64`
- `0x140017f20`
- `0x14003ff1c`
- `0x14003ff34`
- `0x14006d048`
- `0x140076e00`

## import_xrefs

- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x14006d6a0`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x14006d6a0`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x14006dadf`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x14006dadf`
- `ntoskrnl!KeWaitForSingleObject` at `0x14006d506`
- `ntoskrnl!KeWaitForSingleObject` at `0x14006d739`
- `ntoskrnl!KeWaitForSingleObject` at `0x14006d930`
- `ntoskrnl!KeWaitForSingleObject` at `0x14006d506`
- `ntoskrnl!KeWaitForSingleObject` at `0x14006d739`
- `ntoskrnl!KeWaitForSingleObject` at `0x14006d930`
- `ntoskrnl!RtlIsSandboxedToken` at `0x14006d0fe`
- `ntoskrnl!RtlIsSandboxedToken` at `0x14006d0fe`
- `ntoskrnl!FsRtlGetEcpListFromIrp` at `0x14006d1b9`
- `ntoskrnl!FsRtlGetEcpListFromIrp` at `0x14006d1b9`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x14006d1f1`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x14006d228`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x14006d1f1`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x14006d228`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14006d38d`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14006d5df`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14006d7fe`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14006da0f`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14006daba`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14006d38d`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14006d5df`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14006d7fe`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14006da0f`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14006daba`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14006d4d1`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14006d704`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14006d8fb`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14006db0b`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14006dd46`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14007b87e`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14006d4d1`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14006d704`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14006d8fb`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14006db0b`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14006dd46`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14007b87e`
- `ntoskrnl!RtlLookupElementGenericTableFullAvl` at `0x14006d410`
- `ntoskrnl!RtlLookupElementGenericTableFullAvl` at `0x14006d840`
- `ntoskrnl!RtlLookupElementGenericTableFullAvl` at `0x14006d410`
- `ntoskrnl!RtlLookupElementGenericTableFullAvl` at `0x14006d840`
- `ntoskrnl!RtlInsertElementGenericTableFullAvl` at `0x14006d45a`
- `ntoskrnl!RtlInsertElementGenericTableFullAvl` at `0x14006d88a`
- `ntoskrnl!RtlInsertElementGenericTableFullAvl` at `0x14006d45a`
- `ntoskrnl!RtlInsertElementGenericTableFullAvl` at `0x14006d88a`

## string_xrefs

- `0x14006d150`: `CClfsRequest::Create`

## pseudocode

```c
__int64 __fastcall CClfsRequest::Create(CClfsRequest *this, __int64 a2)
{
  char v3; // r12
  unsigned int v4; // esi
  unsigned int v5; // r14d
  __int64 v6; // rcx
  __int64 v7; // r13
  char v8; // di
  int v9; // ebx
  struct _FILE_OBJECT *RelatedFileObject; // rbx
  __int64 v11; // rdx
  unsigned int v12; // eax
  __int64 v13; // rcx
  int v14; // eax
  struct _CLFS_FILTER_CONTEXT *v15; // rbx
  int v16; // eax
  __int64 v17; // rax
  int v18; // ebx
  int v19; // ebx
  int v20; // ebx
  bool v21; // sf
  PVOID inserted; // rax
  unsigned __int8 v23; // cl
  CClfsLogFcbPhysical *v24; // rbx
  int v25; // ebx
  char v26; // dl
  int v27; // eax
  struct _FILE_OBJECT *v28; // r13
  PVOID v29; // rax
  CClfsLogFcbPhysical *v30; // rbx
  int v31; // ebx
  PVOID v32; // rax
  unsigned __int8 v33; // cl
  CClfsLogFcbPhysical *v34; // rbx
  int v35; // ebx
  char v36; // r9
  __int64 v37; // rax
  struct _ACCESS_STATE *v38; // r14
  int v39; // ebx
  int v40; // ebx
  int v41; // ebx
  char v42; // cl
  int v43; // eax
  void *v44; // r8
  char v45; // cl
  int v46; // eax
  int v47; // eax
  char v48; // dl
  CClfsLogFcbPhysical *v50; // [rsp+68h] [rbp-100h] BYREF
  char v51; // [rsp+70h] [rbp-F8h]
  char v52; // [rsp+71h] [rbp-F7h]
  char v53; // [rsp+72h] [rbp-F6h]
  __int16 v54; // [rsp+74h] [rbp-F4h]
  ACCESS_MASK DesiredAccess; // [rsp+78h] [rbp-F0h]
  PFAST_MUTEX FastMutex; // [rsp+80h] [rbp-E8h] BYREF
  TABLE_SEARCH_RESULT SearchResult; // [rsp+88h] [rbp-E0h] BYREF
  int v58; // [rsp+8Ch] [rbp-DCh]
  struct _FILE_OBJECT *v59; // [rsp+90h] [rbp-D8h]
  UNICODE_STRING Buffer; // [rsp+98h] [rbp-D0h] BYREF
  struct _FILE_OBJECT *v61; // [rsp+A8h] [rbp-C0h]
  struct _CLFS_FILTER_CONTEXT *v62; // [rsp+B0h] [rbp-B8h]
  ULONG EcpContextSize; // [rsp+B8h] [rbp-B0h] BYREF
  PVOID NodeOrParent; // [rsp+C0h] [rbp-A8h] BYREF
  struct _ACCESS_STATE *v65; // [rsp+C8h] [rbp-A0h]
  PECP_LIST EcpList; // [rsp+D0h] [rbp-98h] BYREF
  struct _UNICODE_STRING FileName; // [rsp+D8h] [rbp-90h] BYREF
  PVOID EcpContext; // [rsp+E8h] [rbp-80h] BYREF
  __int128 v69; // [rsp+F0h] [rbp-78h] BYREF
  __int64 v70; // [rsp+100h] [rbp-68h]
  _BYTE v71[24]; // [rsp+108h] [rbp-60h] BYREF
  struct _CLFS_FILTER_CONTEXT *v72; // [rsp+120h] [rbp-48h]
  struct _SECURITY_SUBJECT_CONTEXT *p_SubjectSecurityContext; // [rsp+128h] [rbp-40h]
  unsigned __int8 NewElement; // [rsp+178h] [rbp+10h] BYREF
  char v75; // [rsp+180h] [rbp+18h]
  __int64 v76; // [rsp+188h] [rbp+20h]

  Buffer = (UNICODE_STRING)0LL;
  *(_QWORD *)&FileName.Length = 0;
  FileName.Buffer = 0;
  v69 = 0;
  v70 = 0;
  NodeOrParent = 0;
  v61 = 0;
  v50 = 0;
  FastMutex = 0;
  v62 = 0;
  v75 = 0;
  v3 = 0;
  NewElement = 0;
  v4 = 0;
  v58 = 0;
  SearchResult = TableEmptyTree;
  EcpList = 0;
  EcpContext = 0;
  EcpContextSize = 0;
  v5 = 0;
  v6 = *((_QWORD *)this + 6);
  v7 = *(_QWORD *)(v6 + 184);
  v8 = 1;
  LOBYTE(a2) = 1;
  if ( (*(_BYTE *)(v7 + 2) & 1) == 0 )
    LOBYTE(a2) = *(_BYTE *)(v6 + 64);
  if ( (unsigned __int8)RtlIsSandboxedToken(0, a2) )
  {
    v9 = -1073741790;
    if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
    {
      WPP_SF_slD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        21,
        (unsigned int)WPP_e99822b18e20334f40b669f21686eb29_Traceguids,
        (unsigned int)"CClfsRequest::Create",
        107,
        34);
    }
    goto LABEL_113;
  }
  v59 = *(struct _FILE_OBJECT **)(v7 + 48);
  RelatedFileObject = v59->RelatedFileObject;
  v61 = RelatedFileObject;
  Buffer = v59->FileName;
  if ( !(unsigned __int16)_mm_cvtsi128_si32((__m128i)Buffer)
    || !Buffer.Buffer
    || FsRtlGetEcpListFromIrp(*((PIRP *)this + 6), &EcpList) >= 0
    && EcpList
    && (FsRtlFindExtraCreateParameter(EcpList, &ECP_TYPE_CLFS_OPEN_CONTAINER, &EcpContext, &EcpContextSize) >= 0
     || FsRtlFindExtraCreateParameter(EcpList, &ECP_TYPE_CLFS_CREATE_CONTAINER, &EcpContext, &EcpContextSize) >= 0) )
  {
    v9 = -1073741767;
    goto LABEL_113;
  }
  if ( !RelatedFileObject )
  {
    v11 = *((_QWORD *)this + 6);
    v76 = *(_QWORD *)(v11 + 88);
    v12 = *(_DWORD *)(v7 + 32);
    if ( !v12 )
    {
LABEL_32:
      v17 = *(_QWORD *)(v7 + 8);
      v65 = *(struct _ACCESS_STATE **)(v17 + 8);
      DesiredAccess = *(_DWORD *)(v17 + 16);
      v54 = *(_WORD *)(v7 + 24) & 0x121;
      LOWORD(v76) = *(_WORD *)(v7 + 26);
      v18 = *(unsigned __int8 *)(v7 + 19);
      FastMutex = (PFAST_MUTEX)(&CClfsRequest::m_rgFcbTable + 22 * ((unsigned __int16)ClfsHashPJW(&Buffer) % 5u));
      ExAcquireFastMutexUnsafe(FastMutex);
      v3 = 1;
      lambda_c8958e9c1d0b82f8e9508895af63ee77_::_lambda_c8958e9c1d0b82f8e9508895af63ee77_(
        v71,
        &v50,
        &FastMutex,
        &Buffer);
      v19 = v18 - 1;
      if ( v19 )
      {
        v20 = v19 - 1;
        if ( v20 )
        {
          if ( v20 != 1 )
          {
            v9 = -1073741811;
LABEL_36:
            v21 = v9 < 0;
            goto LABEL_110;
          }
          v51 = 0;
          while ( 1 )
          {
            inserted = RtlLookupElementGenericTableFullAvl(
                         (PRTL_AVL_TABLE)&FastMutex[1],
                         &Buffer,
                         &NodeOrParent,
                         &SearchResult);
            if ( SearchResult == TableFoundNode )
            {
              v23 = NewElement;
            }
            else
            {
              inserted = RtlInsertElementGenericTableFullAvl(
                           (PRTL_AVL_TABLE)&FastMutex[1],
                           &Buffer,
                           0x10u,
                           &NewElement,
                           NodeOrParent,
                           SearchResult);
              v23 = 1;
              NewElement = 1;
            }
            if ( !inserted )
              goto LABEL_42;
            v24 = (CClfsLogFcbPhysical *)*((_QWORD *)inserted + 17);
            v50 = v24;
            if ( !v23 )
            {
              if ( (unsigned __int8)lambda_c8958e9c1d0b82f8e9508895af63ee77_::operator()(v71) )
                goto LABEL_55;
              (*(void (__fastcall **)(CClfsLogFcbPhysical *))(*(_QWORD *)v50 + 64LL))(v50);
              v24 = v50;
            }
            v25 = *((_DWORD *)v24 + 236);
            ExReleaseFastMutexUnsafe(FastMutex);
            v3 = 0;
            if ( v25 )
              KeWaitForSingleObject((char *)v50 + 920, Executive, 0, 0, 0);
            v26 = 1;
            if ( (*(_BYTE *)(v7 + 2) & 1) == 0 )
              v26 = *(_BYTE *)(*((_QWORD *)this + 6) + 64LL);
            p_SubjectSecurityContext = &v65->SubjectSecurityContext;
            v27 = CClfsLogFcbPhysical::Initialize(
                    v50,
                    (__int64)v65->SecurityDescriptor,
                    &v65->SubjectSecurityContext,
                    DesiredAccess,
                    (unsigned __int16)v76,
                    v65,
                    v26,
                    v62,
                    v59,
                    v5);
            v9 = v27;
            if ( v51
              || (*((_DWORD *)v50 + 91) & 0x1000) == 0
              || v27 != -1073741202
              || !(unsigned __int8)lambda_c8958e9c1d0b82f8e9508895af63ee77_::operator()(v71) )
            {
              if ( v9 == -1073741772 )
                v9 = CClfsLogFcbPhysical::Initialize(
                       v50,
                       v65->SecurityDescriptor,
                       p_SubjectSecurityContext,
                       v54,
                       DesiredAccess,
                       (unsigned __int16)v76,
                       v62,
                       v59,
                       v5);
              goto LABEL_36;
            }
            v51 = 1;
            (*(void (__fastcall **)(CClfsLogFcbPhysical *))(*(_QWORD *)v50 + 72LL))(v50);
            v50 = 0;
            ExAcquireFastMutexUnsafe(FastMutex);
            v3 = 1;
LABEL_55:
            SearchResult = TableEmptyTree;
          }
        }
        v52 = 0;
        v28 = v59;
        while ( 1 )
        {
          while ( 1 )
          {
            v29 = RtlInsertElementGenericTableAvl((PRTL_AVL_TABLE)&FastMutex[1], &Buffer, 0x10u, &NewElement);
            if ( !v29 )
              goto LABEL_42;
            v30 = (CClfsLogFcbPhysical *)*((_QWORD *)v29 + 17);
            v50 = v30;
            if ( !NewElement )
              break;
LABEL_63:
            v31 = *((_DWORD *)v30 + 236);
            ExReleaseFastMutexUnsafe(FastMutex);
            v3 = 0;
            if ( v31 )
              KeWaitForSingleObject((char *)v50 + 920, Executive, 0, 0, 0);
            v9 = CClfsLogFcbPhysical::Initialize(
                   v50,
                   v65->SecurityDescriptor,
                   &v65->SubjectSecurityContext,
                   v54,
                   DesiredAccess,
                   (unsigned __int16)v76,
                   v62,
                   v28,
                   v5);
            if ( v52
              || (*((_DWORD *)v50 + 91) & 0x1000) == 0
              || v9 != -1073741202
              || !(unsigned __int8)lambda_c8958e9c1d0b82f8e9508895af63ee77_::operator()(v71) )
            {
              goto LABEL_36;
            }
            v52 = 1;
            (*(void (__fastcall **)(CClfsLogFcbPhysical *))(*(_QWORD *)v50 + 72LL))(v50);
            v50 = 0;
            ExAcquireFastMutexUnsafe(FastMutex);
            v3 = 1;
          }
          if ( !(unsigned __int8)lambda_c8958e9c1d0b82f8e9508895af63ee77_::operator()(v71) )
          {
            (*(void (__fastcall **)(CClfsLogFcbPhysical *))(*(_QWORD *)v50 + 64LL))(v50);
            v30 = v50;
            goto LABEL_63;
          }
        }
      }
      v53 = 0;
      while ( 1 )
      {
        v32 = RtlLookupElementGenericTableFullAvl((PRTL_AVL_TABLE)&FastMutex[1], &Buffer, &NodeOrParent, &SearchResult);
        if ( SearchResult == TableFoundNode )
        {
          v33 = NewElement;
        }
        else
        {
          v32 = RtlInsertElementGenericTableFullAvl(
                  (PRTL_AVL_TABLE)&FastMutex[1],
                  &Buffer,
                  0x10u,
                  &NewElement,
                  NodeOrParent,
                  SearchResult);
          v33 = 1;
          NewElement = 1;
        }
        if ( !v32 )
        {
LABEL_42:
          v9 = -1073741670;
          goto LABEL_113;
        }
        v34 = (CClfsLogFcbPhysical *)*((_QWORD *)v32 + 17);
        v50 = v34;
        if ( !v33 )
        {
          if ( (unsigned __int8)lambda_c8958e9c1d0b82f8e9508895af63ee77_::operator()(v71) )
            goto LABEL_88;
          (*(void (__fastcall **)(CClfsLogFcbPhysical *))(*(_QWORD *)v50 + 64LL))(v50);
          v34 = v50;
        }
        v35 = *((_DWORD *)v34 + 236);
        ExReleaseFastMutexUnsafe(FastMutex);
        v3 = 0;
        if ( v35 )
          KeWaitForSingleObject((char *)v50 + 920, Executive, 0, 0, 0);
        v36 = 1;
        if ( (*(_BYTE *)(v7 + 2) & 1) == 0 )
          v36 = *(_BYTE *)(*((_QWORD *)this + 6) + 64LL);
        v9 = CClfsLogFcbPhysical::Initialize(
               v50,
               (__int64)v65->SecurityDescriptor,
               &v65->SubjectSecurityContext,
               DesiredAccess,
               (unsigned __int16)v76,
               v65,
               v36,
               v62,
               v59,
               v5);
        if ( v53
          || (*((_DWORD *)v50 + 91) & 0x1000) == 0
          || v9 != -1073741202
          || !(unsigned __int8)lambda_c8958e9c1d0b82f8e9508895af63ee77_::operator()(v71) )
        {
          goto LABEL_36;
        }
        v53 = 1;
        (*(void (__fastcall **)(CClfsLogFcbPhysical *))(*(_QWORD *)v50 + 72LL))(v50);
        v50 = 0;
        ExAcquireFastMutexUnsafe(FastMutex);
        v3 = 1;
LABEL_88:
        SearchResult = TableEmptyTree;
      }
    }
    if ( v12 < 0x20 )
    {
LABEL_16:
      v9 = -1073741811;
      goto LABEL_113;
    }
    v13 = *(_QWORD *)(v11 + 24);
    if ( !v13 )
    {
      v9 = -1073741743;
      goto LABEL_113;
    }
    v14 = *(_DWORD *)(v13 + 16);
    if ( (v14 & 0x1000318) == 0 )
    {
      v9 = -2147483627;
      goto LABEL_113;
    }
    if ( *(_BYTE *)(v11 + 64) == 1 )
    {
      v9 = -1073741745;
      goto LABEL_113;
    }
    if ( (v14 & 0x10) != 0 )
    {
      v69 = *(unsigned __int64 *)(v13 + 24);
      LODWORD(v70) = 0;
      v15 = (struct _CLFS_FILTER_CONTEXT *)&v69;
    }
    else
    {
      if ( (v14 & 0x100) == 0 )
      {
LABEL_28:
        v16 = *(_DWORD *)(v13 + 16);
        v5 = v16 & 0x200;
        if ( (v16 & 0x1000000) != 0 )
          v5 |= 0x1000000u;
        if ( (v16 & 8) != 0 )
          v5 |= 8u;
        goto LABEL_32;
      }
      v15 = *(struct _CLFS_FILTER_CONTEXT **)(v13 + 24);
    }
    v72 = v15;
    v62 = v15;
    goto LABEL_28;
  }
  FileName = RelatedFileObject->FileName;
  v76 = *(_QWORD *)(*((_QWORD *)this + 6) + 88LL);
  v37 = *(_QWORD *)(v7 + 8);
  v38 = *(struct _ACCESS_STATE **)(v37 + 8);
  DesiredAccess = *(_DWORD *)(v37 + 16);
  v54 = *(_WORD *)(v7 + 24) & 0x21;
  LOWORD(v76) = *(_WORD *)(v7 + 26);
  v39 = *(unsigned __int8 *)(v7 + 19);
  FastMutex = (PFAST_MUTEX)(&CClfsRequest::m_rgFcbTable + 22 * ((unsigned __int16)ClfsHashPJW(&FileName) % 5u));
  ExAcquireFastMutexUnsafe(FastMutex);
  v50 = (CClfsLogFcbPhysical *)*((_QWORD *)RtlLookupElementGenericTableAvl((PRTL_AVL_TABLE)&FastMutex[1], &FileName) + 17);
  (*(void (__fastcall **)(CClfsLogFcbPhysical *))(*(_QWORD *)v50 + 64LL))(v50);
  ExReleaseFastMutexUnsafe(FastMutex);
  v3 = 0;
  v40 = v39 - 1;
  if ( !v40 )
  {
    v48 = 1;
    if ( (*(_BYTE *)(v7 + 2) & 1) == 0 )
      v48 = *(_BYTE *)(*((_QWORD *)this + 6) + 64LL);
    v46 = CClfsLogFcbPhysical::OpenClient(
            v50,
            &Buffer,
            v61,
            &v38->SubjectSecurityContext,
            DesiredAccess,
            (unsigned __int16)v76,
            v38,
            v48,
            v61,
            v59);
LABEL_109:
    v9 = v46;
    v21 = v46 < 0;
LABEL_110:
    if ( !v21 )
    {
      v4 = 1;
      v58 = 1;
    }
    goto LABEL_113;
  }
  v41 = v40 - 1;
  if ( v41 )
  {
    if ( v41 != 1 )
      goto LABEL_16;
    v42 = 1;
    if ( (*(_BYTE *)(v7 + 2) & 1) == 0 )
      v42 = *(_BYTE *)(*((_QWORD *)this + 6) + 64LL);
    v43 = CClfsLogFcbPhysical::AddClient(
            v50,
            &Buffer,
            v61,
            &v38->SubjectSecurityContext,
            v54,
            DesiredAccess,
            (unsigned __int16)v76,
            v38,
            v42,
            v61,
            v59);
    v9 = v43;
    if ( v43 < 0 )
    {
      if ( v43 != -1073741635 )
        goto LABEL_113;
      v45 = 1;
      if ( (*(_BYTE *)(v7 + 2) & 1) == 0 )
        v45 = *(_BYTE *)(*((_QWORD *)this + 6) + 64LL);
      v46 = CClfsLogFcbPhysical::OpenClient(
              v50,
              &Buffer,
              v44,
              &v38->SubjectSecurityContext,
              DesiredAccess,
              (unsigned __int16)v76,
              v38,
              v45,
              v61,
              v59);
      goto LABEL_109;
    }
    goto LABEL_104;
  }
  if ( (*(_BYTE *)(v7 + 2) & 1) == 0 )
    v8 = *(_BYTE *)(*((_QWORD *)this + 6) + 64LL);
  v47 = CClfsLogFcbPhysical::AddClient(
          v50,
          &Buffer,
          v61,
          &v38->SubjectSecurityContext,
          v54,
          DesiredAccess,
          (unsigned __int16)v76,
          v38,
          v8,
          v61,
          v59);
  v9 = v47;
  if ( v47 >= 0 )
  {
LABEL_104:
    v9 = (*(__int64 (__fastcall **)(CClfsLogFcbPhysical *))(*(_QWORD *)v50 + 112LL))(v50);
    if ( v9 >= 0 )
    {
      v4 = 2;
      v58 = 2;
    }
    goto LABEL_113;
  }
  if ( v47 == -1073741635 )
  {
    v4 = 4;
    v58 = 4;
    v9 = -1073741771;
  }
LABEL_113:
  if ( v3 && FastMutex )
    ExReleaseFastMutexUnsafe(FastMutex);
  if ( v50 && (v61 || v9 < 0) )
    (*(void (__fastcall **)(CClfsLogFcbPhysical *))(*(_QWORD *)v50 + 72LL))(v50);
  if ( (*((_DWORD *)this + 4) & 4) == 0 )
  {
    *(_DWORD *)(*((_QWORD *)this + 6) + 48LL) = v9;
    *(_QWORD *)(*((_QWORD *)this + 6) + 56LL) = v4;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14006d048  mov     rax, rsp
0x14006d04b  mov     [rax+8], rcx
0x14006d04f  push    rbx
0x14006d050  push    rsi
0x14006d051  push    rdi
0x14006d052  push    r12
0x14006d054  push    r13
0x14006d056  push    r14
0x14006d058  push    r15
0x14006d05a  sub     rsp, 130h
0x14006d061  mov     r15, rcx
0x14006d064  xor     ebx, ebx
0x14006d066  mov     [rax-0D0h], rbx
0x14006d06d  mov     [rax-0C8h], rbx
0x14006d074  mov     [rax-90h], rbx
0x14006d07b  mov     [rax-88h], rbx
0x14006d082  xorps   xmm0, xmm0
0x14006d085  movdqu  xmmword ptr [rax-78h], xmm0
0x14006d08a  mov     [rax-68h], rbx
0x14006d08e  mov     [rax-0A8h], rbx
0x14006d095  mov     [rax-0C0h], rbx
0x14006d09c  mov     [rsp+168h+var_100], rbx
0x14006d0a1  mov     [rax-0E8h], rbx
0x14006d0a8  mov     [rax-0B8h], rbx
0x14006d0af  mov     [rsp+168h+var_104], ebx
0x14006d0b3  mov     [rax+18h], bl
0x14006d0b6  mov     r12b, bl
0x14006d0b9  mov     [rsp+168h+var_108], bl
0x14006d0bd  mov     [rax+10h], bl
0x14006d0c0  mov     esi, ebx
0x14006d0c2  mov     [rax-0DCh], ebx
0x14006d0c8  mov     [rax-0E0h], ebx
0x14006d0ce  mov     [rax-98h], rbx
0x14006d0d5  mov     [rax-80h], rbx
0x14006d0d9  mov     [rax-0B0h], ebx
0x14006d0df  mov     r14d, ebx
0x14006d0e2  mov     rcx, [rcx+30h]
0x14006d0e6  mov     r13, [rcx+0B8h]
0x14006d0ed  lea     edi, [rbx+1]
0x14006d0f0  test    [r13+2], dil
0x14006d0f4  mov     dl, dil
0x14006d0f7  jnz     short loc_14006D0FC
0x14006d0f9  mov     dl, [rcx+40h]
0x14006d0fc  xor     ecx, ecx
0x14006d0fe  call    cs:__imp_RtlIsSandboxedToken
0x14006d105  nop     dword ptr [rax+rax+00h]
0x14006d10a  test    al, al
0x14006d10c  jz      short loc_14006D16C
0x14006d10e  mov     ebx, 0C0000022h
0x14006d113  mov     [rsp+168h+var_104], ebx
0x14006d117  lea     rax, WPP_GLOBAL_Control
0x14006d11e  mov     rcx, cs:WPP_GLOBAL_Control
0x14006d125  cmp     rcx, rax
0x14006d128  jz      loc_14006DD34
0x14006d12e  test    dword ptr [rcx+2Ch], 4000000h
0x14006d135  jz      loc_14006DD34
0x14006d13b  mov     edx, 15h
0x14006d140  mov     [rsp+168h+var_140], 0C0000022h
0x14006d148  mov     dword ptr [rsp+168h+var_148], 0A6Bh
0x14006d150  lea     r9, aCclfsrequestCr; "CClfsRequest::Create"
0x14006d157  lea     r8, WPP_e99822b18e20334f40b669f21686eb29_Traceguids
0x14006d15e  mov     rcx, [rcx+18h]
0x14006d162  call    WPP_SF_slD
0x14006d167  jmp     loc_14006DD34
0x14006d16c  mov     rax, [r13+30h]
0x14006d170  mov     [rsp+168h+var_D8], rax
0x14006d178  mov     rbx, [rax+40h]
0x14006d17c  mov     [rsp+168h+var_C0], rbx
0x14006d184  movups  xmm0, xmmword ptr [rax+58h]
0x14006d188  movups  [rsp+168h+Buffer], xmm0
0x14006d190  xor     ecx, ecx
0x14006d192  movd    eax, xmm0
0x14006d196  cmp     cx, ax
0x14006d199  jz      loc_14006DD2B
0x14006d19f  cmp     qword ptr [rsp+168h+Buffer+8], rcx
0x14006d1a7  jz      loc_14006DD2B
0x14006d1ad  lea     rdx, [rsp+168h+EcpList]; EcpList
0x14006d1b5  mov     rcx, [r15+30h]; Irp
0x14006d1b9  call    cs:__imp_FsRtlGetEcpListFromIrp
0x14006d1c0  nop     dword ptr [rax+rax+00h]
0x14006d1c5  mov     [rsp+168h+var_104], eax
0x14006d1c9  test    eax, eax
0x14006d1cb  js      short loc_14006D240
0x14006d1cd  mov     rcx, [rsp+168h+EcpList]; EcpList
0x14006d1d5  test    rcx, rcx
0x14006d1d8  jz      short loc_14006D240
0x14006d1da  lea     r9, [rsp+168h+EcpContextSize]; EcpContextSize
0x14006d1e2  lea     r8, [rsp+168h+EcpContext]; EcpContext
0x14006d1ea  lea     rdx, ECP_TYPE_CLFS_OPEN_CONTAINER; EcpType
0x14006d1f1  call    cs:__imp_FsRtlFindExtraCreateParameter
0x14006d1f8  nop     dword ptr [rax+rax+00h]
0x14006d1fd  mov     [rsp+168h+var_104], eax
0x14006d201  test    eax, eax
0x14006d203  jns     loc_14006DD2B
0x14006d209  lea     r9, [rsp+168h+EcpContextSize]; EcpContextSize
0x14006d211  lea     r8, [rsp+168h+EcpContext]; EcpContext
0x14006d219  lea     rdx, ECP_TYPE_CLFS_CREATE_CONTAINER; EcpType
0x14006d220  mov     rcx, [rsp+168h+EcpList]; EcpList
0x14006d228  call    cs:__imp_FsRtlFindExtraCreateParameter
0x14006d22f  nop     dword ptr [rax+rax+00h]
0x14006d234  mov     [rsp+168h+var_104], eax
0x14006d238  test    eax, eax
0x14006d23a  jns     loc_14006DD2B
0x14006d240  test    rbx, rbx
0x14006d243  jnz     loc_14006DA33
0x14006d249  mov     rdx, [r15+30h]
0x14006d24d  mov     rax, [rdx+58h]
0x14006d251  mov     [rsp+168h+arg_18], rax
0x14006d259  mov     eax, [r13+20h]
0x14006d25d  test    eax, eax
0x14006d25f  jz      loc_14006D317
0x14006d265  cmp     eax, 20h ; ' '
0x14006d268  jnb     short loc_14006D274
0x14006d26a  mov     ebx, 0C000000Dh
0x14006d26f  jmp     loc_14006DD30
0x14006d274  mov     rcx, [rdx+18h]
0x14006d278  test    rcx, rcx
0x14006d27b  jnz     short loc_14006D287
0x14006d27d  mov     ebx, 0C0000051h
0x14006d282  jmp     loc_14006DD30
0x14006d287  mov     eax, [rcx+10h]
0x14006d28a  test    eax, 1000318h
0x14006d28f  jnz     short loc_14006D29B
0x14006d291  mov     ebx, 80000015h
0x14006d296  jmp     loc_14006DD30
0x14006d29b  cmp     [rdx+40h], dil
0x14006d29f  jnz     short loc_14006D2AB
0x14006d2a1  mov     ebx, 0C000004Fh
0x14006d2a6  jmp     loc_14006DD30
0x14006d2ab  test    al, 10h
0x14006d2ad  jz      short loc_14006D2DC
0x14006d2af  mov     rax, [rcx+18h]
0x14006d2b3  mov     [rsp+168h+var_78], rax
0x14006d2bb  mov     [rsp+168h+var_70], 0
0x14006d2c7  mov     dword ptr [rsp+168h+var_68], 0
0x14006d2d2  lea     rbx, [rsp+168h+var_78]
0x14006d2da  jmp     short loc_14006D2E6
0x14006d2dc  bt      eax, 8
0x14006d2e0  jnb     short loc_14006D2F6
0x14006d2e2  mov     rbx, [rcx+18h]
0x14006d2e6  mov     [rsp+168h+var_48], rbx
0x14006d2ee  mov     [rsp+168h+var_B8], rbx
0x14006d2f6  mov     eax, [rcx+10h]
0x14006d2f9  mov     r14d, eax
0x14006d2fc  and     r14d, 200h
0x14006d303  mov     ecx, 1000000h
0x14006d308  test    ecx, eax
0x14006d30a  jz      short loc_14006D30F
0x14006d30c  or      r14d, ecx
0x14006d30f  test    al, 8
0x14006d311  jz      short loc_14006D317
0x14006d313  or      r14d, 8
0x14006d317  mov     rax, [r13+8]
0x14006d31b  mov     rdx, [rax+8]
0x14006d31f  mov     [rsp+168h+var_A0], rdx
0x14006d327  mov     eax, [rax+10h]
0x14006d32a  mov     [rsp+168h+DesiredAccess], eax
0x14006d32e  movzx   eax, word ptr [r13+18h]
0x14006d333  mov     ecx, 121h
0x14006d338  and     ax, cx
0x14006d33b  mov     [rsp+168h+var_F4], ax
0x14006d340  movzx   eax, word ptr [r13+1Ah]
0x14006d345  mov     word ptr [rsp+168h+arg_18], ax
0x14006d34d  movzx   ebx, byte ptr [r13+13h]
0x14006d352  lea     rcx, [rsp+168h+Buffer]; struct _UNICODE_STRING *
0x14006d35a  call    ?ClfsHashPJW@@YAKAEBU_UNICODE_STRING@@@Z; ClfsHashPJW(_UNICODE_STRING const &)
0x14006d35f  movzx   ecx, ax
0x14006d362  mov     eax, 0CCCCCCCDh
0x14006d367  mul     ecx
0x14006d369  shr     edx, 2
0x14006d36c  lea     eax, [rdx+rdx*4]
0x14006d36f  sub     ecx, eax
0x14006d371  movzx   eax, cx
0x14006d374  imul    rcx, rax, 0B0h
0x14006d37b  lea     rax, ?m_rgFcbTable@CClfsRequest@@0PAU_CLFS_FCB_TABLE_HEADER@@A; _CLFS_FCB_TABLE_HEADER near * CClfsRequest::m_rgFcbTable
0x14006d382  add     rcx, rax; FastMutex
0x14006d385  mov     [rsp+168h+FastMutex], rcx
0x14006d38d  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14006d394  nop     dword ptr [rax+rax+00h]
0x14006d399  mov     r12b, dil
0x14006d39c  mov     [rsp+168h+var_108], dil
0x14006d3a1  lea     r9, [rsp+168h+Buffer]
0x14006d3a9  lea     r8, [rsp+168h+FastMutex]
0x14006d3b1  lea     rdx, [rsp+168h+var_100]
0x14006d3b6  lea     rcx, [rsp+168h+var_60]
0x14006d3be  call    _lambda_c8958e9c1d0b82f8e9508895af63ee77____lambda_c8958e9c1d0b82f8e9508895af63ee77_
0x14006d3c3  sub     ebx, edi
0x14006d3c5  jz      loc_14006D817
0x14006d3cb  sub     ebx, edi
0x14006d3cd  jz      loc_14006D671
0x14006d3d3  cmp     ebx, edi
0x14006d3d5  jz      short loc_14006D3E7
0x14006d3d7  mov     ebx, 0C000000Dh
0x14006d3dc  mov     [rsp+168h+var_104], ebx
0x14006d3e0  test    ebx, ebx
0x14006d3e2  jmp     loc_14006DD1E
0x14006d3e7  mov     [rsp+168h+var_F8], 0
0x14006d3ec  mov     rcx, [rsp+168h+FastMutex]
0x14006d3f4  add     rcx, 38h ; '8'; Table
0x14006d3f8  lea     r9, [rsp+168h+SearchResult]; SearchResult
0x14006d400  lea     r8, [rsp+168h+NodeOrParent]; NodeOrParent
0x14006d408  lea     rdx, [rsp+168h+Buffer]; Buffer
0x14006d410  call    cs:__imp_RtlLookupElementGenericTableFullAvl
0x14006d417  nop     dword ptr [rax+rax+00h]
0x14006d41c  mov     edx, [rsp+168h+SearchResult]
0x14006d423  cmp     edx, edi
0x14006d425  jz      short loc_14006D472
0x14006d427  mov     rcx, [rsp+168h+FastMutex]
0x14006d42f  add     rcx, 38h ; '8'; Table
0x14006d433  mov     [rsp+168h+var_140], edx; SearchResult
0x14006d437  mov     rax, [rsp+168h+NodeOrParent]
0x14006d43f  mov     [rsp+168h+var_148], rax; NodeOrParent
0x14006d444  lea     r9, [rsp+168h+NewElement]; NewElement
0x14006d44c  mov     r8d, 10h; BufferSize
0x14006d452  lea     rdx, [rsp+168h+Buffer]; Buffer
0x14006d45a  call    cs:__imp_RtlInsertElementGenericTableFullAvl
0x14006d461  nop     dword ptr [rax+rax+00h]
0x14006d466  mov     cl, dil
0x14006d469  mov     [rsp+168h+NewElement], cl
0x14006d470  jmp     short loc_14006D479
0x14006d472  mov     cl, [rsp+168h+NewElement]
0x14006d479  test    rax, rax
0x14006d47c  jnz     short loc_14006D488
0x14006d47e  mov     ebx, 0C000009Ah
0x14006d483  jmp     loc_14006DD30
0x14006d488  mov     rbx, [rax+88h]
0x14006d48f  mov     [rsp+168h+var_100], rbx
0x14006d494  test    cl, cl
0x14006d496  jnz     short loc_14006D4C3
0x14006d498  lea     rcx, [rsp+168h+var_60]
0x14006d4a0  call    _lambda_c8958e9c1d0b82f8e9508895af63ee77___operator__
0x14006d4a5  test    al, al
0x14006d4a7  jnz     loc_14006D5F3
0x14006d4ad  mov     rcx, [rsp+168h+var_100]
0x14006d4b2  mov     rax, [rcx]
0x14006d4b5  mov     rax, [rax+40h]
0x14006d4b9  call    _guard_dispatch_icall
0x14006d4be  mov     rbx, [rsp+168h+var_100]
0x14006d4c3  mov     ebx, [rbx+3B0h]
0x14006d4c9  mov     rcx, [rsp+168h+FastMutex]; FastMutex
0x14006d4d1  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14006d4d8  nop     dword ptr [rax+rax+00h]
0x14006d4dd  xor     r12b, r12b
0x14006d4e0  mov     [rsp+168h+var_108], r12b
0x14006d4e5  test    ebx, ebx
0x14006d4e7  jz      short loc_14006D512
0x14006d4e9  mov     rcx, [rsp+168h+var_100]
0x14006d4ee  add     rcx, 398h; Object
0x14006d4f5  mov     [rsp+168h+var_148], 0; Timeout
0x14006d4fe  xor     r9d, r9d; Alertable
0x14006d501  xor     r8d, r8d; WaitMode
0x14006d504  xor     edx, edx; WaitReason
0x14006d506  call    cs:__imp_KeWaitForSingleObject
0x14006d50d  nop     dword ptr [rax+rax+00h]
0x14006d512  mov     dl, dil
0x14006d515  test    [r13+2], dil
0x14006d519  jnz     short loc_14006D522
0x14006d51b  mov     rax, [r15+30h]
0x14006d51f  mov     dl, [rax+40h]
0x14006d522  movzx   r8d, word ptr [rsp+168h+arg_18]
0x14006d52b  mov     rcx, [rsp+168h+var_A0]
0x14006d533  lea     r10, [rcx+20h]
0x14006d537  mov     [rsp+168h+var_40], r10
0x14006d53f  mov     dword ptr [rsp+168h+var_120], r14d; unsigned int
0x14006d544  mov     rax, [rsp+168h+var_D8]
0x14006d54c  mov     [rsp+168h+var_128], rax; struct _FILE_OBJECT *
0x14006d551  mov     rax, [rsp+168h+var_B8]
0x14006d559  mov     [rsp+168h+var_130], rax; struct _CLFS_FILTER_CONTEXT *
0x14006d55e  mov     byte ptr [rsp+168h+var_138], dl; char
0x14006d562  mov     qword ptr [rsp+168h+var_140], rcx; struct _ACCESS_STATE *
0x14006d567  mov     dword ptr [rsp+168h+var_148], r8d; DesiredShareAccess
0x14006d56c  mov     r9d, [rsp+168h+DesiredAccess]; unsigned int
0x14006d571  mov     r8, r10; struct _SECURITY_SUBJECT_CONTEXT *
0x14006d574  mov     rdx, [rcx+40h]; void *
0x14006d578  mov     rcx, [rsp+168h+var_100]; this
0x14006d57d  call    ?Initialize@CClfsLogFcbPhysical@@QEAAJPEAXAEAU_SECURITY_SUBJECT_CONTEXT@@KKPEAU_ACCESS_STATE@@DPEAU_CLFS_FILTER_CONTEXT@@PEAU_FILE_OBJECT@@K@Z; CClfsLogFcbPhysical::Initialize(void *,_SECURITY_SUBJECT_CONTEXT &,ulong,ulong,_ACCESS_STATE *,char,_CLFS_FILTER_CONTEXT *,_FILE_OBJECT *,ulong)
0x14006d582  mov     ebx, eax
0x14006d584  mov     [rsp+168h+var_104], eax
0x14006d588  cmp     [rsp+168h+var_F8], r12b
0x14006d58d  jnz     short loc_14006D603
0x14006d58f  mov     rcx, [rsp+168h+var_100]
0x14006d594  test    dword ptr [rcx+16Ch], 1000h
0x14006d59e  jz      short loc_14006D603
0x14006d5a0  cmp     eax, 0C000026Eh
0x14006d5a5  jnz     short loc_14006D603
0x14006d5a7  lea     rcx, [rsp+168h+var_60]
0x14006d5af  call    _lambda_c8958e9c1d0b82f8e9508895af63ee77___operator__
0x14006d5b4  test    al, al
0x14006d5b6  jz      short loc_14006D603
0x14006d5b8  mov     [rsp+168h+var_F8], dil
0x14006d5bd  mov     rcx, [rsp+168h+var_100]
0x14006d5c2  mov     rax, [rcx]
0x14006d5c5  mov     rax, [rax+48h]
0x14006d5c9  call    _guard_dispatch_icall
0x14006d5ce  mov     [rsp+168h+var_100], 0
0x14006d5d7  mov     rcx, [rsp+168h+FastMutex]; FastMutex
0x14006d5df  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14006d5e6  nop     dword ptr [rax+rax+00h]
0x14006d5eb  mov     r12b, dil
0x14006d5ee  mov     [rsp+168h+var_108], dil
  ... truncated ...
```
