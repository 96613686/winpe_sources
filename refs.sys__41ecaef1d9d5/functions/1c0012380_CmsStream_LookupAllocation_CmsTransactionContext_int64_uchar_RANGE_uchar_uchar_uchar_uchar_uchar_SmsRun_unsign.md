# CmsStream::LookupAllocation(CmsTransactionContext *,__int64,uchar,_RANGE *,uchar *,uchar *,uchar *,uchar *,uchar,SmsRun * *,unsigned __int64 *,uchar *,uchar,uchar)

- ea: `0x1c0012380`
- end: `0x1c0013040`
- name: `?LookupAllocation@CmsStream@@QEAAJPEAVCmsTransactionContext@@_JEPEAU_RANGE@@PEAE333EPEAPEAUSmsRun@@PEA_K3EE@Z`
- size: `3264`
- prototype: `__int64 __usercall@<rax>(CmsStream *__hidden this@<rcx>, struct CmsTransactionContext *@<rdx>, unsigned __int64@<r8>, unsigned __int8@<r9b>, struct _RANGE *, unsigned __int8 *, unsigned __int8 *, unsigned __int8 *, unsigned __int8 *, unsigned __int8, struct SmsRun **, unsigned __int64 *, unsigned __int8 *, unsigned __int8, unsigned __int8)`
- caller_count: `18`
- callee_count: `14`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1c0001344`
- `0x1c0010b30`
- `0x1c002839c`
- `0x1c0040310`
- `0x1c00d1d1c`
- `0x1c00e2cf8`
- `0x1c00e3074`
- `0x1c00e3fa0`
- `0x1c00f006c`
- `0x1c00f1794`
- `0x1c00f24ec`
- `0x1c00f25e4`
- `0x1c00f2858`
- `0x1c00f2c5c`
- `0x1c00f32f0`
- `0x1c00f469c`
- `0x1c00f4a0c`
- `0x1c00f547c`

## callees

- `0x1c0002b40`
- `0x1c0004e1c`
- `0x1c0004eb4`
- `0x1c0012380`
- `0x1c001be64`
- `0x1c0028050`
- `0x1c002d170`
- `0x1c0036a10`
- `0x1c0060068`
- `0x1c0060264`
- `0x1c0068960`
- `0x1c006ac80`
- `0x1c006acc0`
- `0x1c00f0aec`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c0012b48`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c0012b48`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c0012e75`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c0012e75`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c0012769`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c0012c98`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c0012769`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c0012c98`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c0012d68`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c0012dcc`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c0012d68`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c0012dcc`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1c0012d27`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1c0012d27`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1c00126d2`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1c00126d2`

## pseudocode

```c
__int64 __fastcall CmsStream::LookupAllocation(
        CmsStream *this,
        struct CmsTransactionContext *a2,
        signed __int64 a3,
        char a4,
        struct _RANGE *a5,
        unsigned __int8 *a6,
        unsigned __int8 *a7,
        unsigned __int8 *a8,
        unsigned __int8 *a9,
        unsigned __int8 a10,
        struct SmsRun **a11,
        unsigned __int64 *a12,
        unsigned __int8 *a13,
        unsigned __int8 a14)
{
  signed __int64 v14; // rbx
  CmsStream *v15; // r15
  __int64 v17; // rax
  bool v18; // r13
  __int64 v19; // r8
  int v20; // edx
  __int64 v21; // r12
  __int64 v23; // rax
  int v24; // r12d
  int v25; // edx
  unsigned int v26; // edx
  unsigned int v27; // eax
  struct _RANGE *v28; // r14
  unsigned __int64 v29; // rax
  __int128 v30; // xmm0
  CmsRangeMap *v31; // rbx
  CmsRangeMap *v32; // r14
  __int64 v33; // rax
  __int64 v34; // rdx
  struct _RANGE *v35; // rcx
  __int64 v36; // rcx
  int StreamReservedRegion; // esi
  unsigned int v38; // r10d
  __int64 *v39; // r8
  __int64 v40; // rcx
  unsigned __int64 v41; // rdx
  char v42; // r12
  char *v43; // r14
  unsigned __int16 ChecksumSizeInBytes; // ax
  unsigned __int64 v45; // rdx
  __int16 v46; // ax
  unsigned __int64 v47; // r8
  __int64 v48; // rcx
  struct _RANGE *v49; // r12
  _BYTE *v50; // r9
  char *v51; // rdx
  __int16 v52; // cx
  char v53; // al
  struct SmsRun **v54; // r8
  int v55; // ecx
  unsigned int v56; // ebx
  int v57; // ecx
  __int64 v58; // rax
  unsigned int v59; // eax
  CmsRangeMap *v60; // r12
  char v61; // r13
  _SmsIndexEntry *v62; // rcx
  unsigned __int8 ChecksumType; // al
  __int64 v64; // r8
  __int64 v65; // r9
  void *v66; // rcx
  __int16 v67; // ax
  __int16 v68; // dx
  bool v69; // zf
  char v70; // al
  unsigned __int16 v71; // dx
  size_t v72; // r13
  size_t v73; // r12
  unsigned int *v74; // rbx
  struct _PAGED_LOOKASIDE_LIST *v75; // rcx
  _QWORD *PoolWithTag; // rax
  int v77; // eax
  char v78; // al
  SIZE_T v79; // r12
  __int16 v80; // ax
  signed __int64 v81; // rcx
  __int64 v82; // rax
  struct _RANGE *v83; // rdx
  signed __int64 v84; // rax
  _BYTE *v85; // rcx
  __int16 v86; // ax
  char v87; // al
  __int16 v88; // ax
  int v89; // eax
  unsigned __int64 v90; // rcx
  struct _SmsQuickIndex *v91; // [rsp+40h] [rbp-C0h]
  unsigned __int8 v92; // [rsp+48h] [rbp-B8h]
  char v94; // [rsp+50h] [rbp-B0h]
  char v95; // [rsp+50h] [rbp-B0h]
  unsigned __int8 v96[7]; // [rsp+51h] [rbp-AFh] BYREF
  struct _RANGE *v97; // [rsp+58h] [rbp-A8h]
  signed __int64 v98; // [rsp+60h] [rbp-A0h]
  signed __int64 v99; // [rsp+68h] [rbp-98h]
  int v100; // [rsp+70h] [rbp-90h]
  unsigned __int8 *v101; // [rsp+78h] [rbp-88h]
  unsigned __int8 *v102; // [rsp+80h] [rbp-80h]
  __int64 v103; // [rsp+88h] [rbp-78h]
  unsigned __int8 *v104; // [rsp+90h] [rbp-70h]
  struct SmsRun **v105; // [rsp+98h] [rbp-68h]
  unsigned __int8 *v106; // [rsp+A0h] [rbp-60h]
  unsigned __int64 v107; // [rsp+A8h] [rbp-58h]
  __int128 v108; // [rsp+B0h] [rbp-50h] BYREF
  _DWORD v109[2]; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD *v110; // [rsp+C8h] [rbp-38h]
  int v111; // [rsp+D0h] [rbp-30h]
  int v112; // [rsp+D4h] [rbp-2Ch]
  _QWORD *v113; // [rsp+D8h] [rbp-28h]
  unsigned __int64 *v114; // [rsp+E0h] [rbp-20h]
  unsigned __int8 *v115; // [rsp+E8h] [rbp-18h]
  char *v116; // [rsp+F0h] [rbp-10h]
  CmsStream *v117; // [rsp+F8h] [rbp-8h]
  __int128 v118; // [rsp+100h] [rbp+0h] BYREF
  __int128 v119; // [rsp+110h] [rbp+10h] BYREF
  void *Src[2]; // [rsp+120h] [rbp+20h]
  _QWORD v121[2]; // [rsp+130h] [rbp+30h] BYREF
  signed __int64 v122; // [rsp+140h] [rbp+40h] BYREF
  __int128 v124; // [rsp+150h] [rbp+50h] BYREF
  SmsRunHeader *v125[2]; // [rsp+160h] [rbp+60h]
  _QWORD v126[2]; // [rsp+170h] [rbp+70h] BYREF
  __int128 v127; // [rsp+180h] [rbp+80h] BYREF
  unsigned __int64 v128; // [rsp+190h] [rbp+90h]
  unsigned __int8 v129[16]; // [rsp+1A0h] [rbp+A0h] BYREF
  __int128 v130; // [rsp+1B0h] [rbp+B0h]
  __int128 v131; // [rsp+1C0h] [rbp+C0h]
  __int128 v132; // [rsp+1D0h] [rbp+D0h]
  __int64 v133; // [rsp+1E0h] [rbp+E0h]
  void **v134; // [rsp+1F0h] [rbp+F0h] BYREF
  int v135; // [rsp+1F8h] [rbp+F8h]
  __int64 v136; // [rsp+200h] [rbp+100h]
  int v137; // [rsp+208h] [rbp+108h]
  __int64 v138; // [rsp+210h] [rbp+110h]
  char v139; // [rsp+278h] [rbp+178h]

  v14 = a3;
  v15 = this;
  v114 = a12;
  v115 = a13;
  v117 = this;
  v133 = 0;
  v17 = *((_QWORD *)this + 2);
  v99 = a3;
  v104 = a9;
  v97 = a5;
  v101 = a6;
  v106 = a7;
  v102 = a8;
  v105 = a11;
  v126[0] = a3;
  v126[1] = 1;
  v109[1] = 0;
  v112 = 0;
  v119 = 0;
  *(_OWORD *)Src = 0;
  *(_OWORD *)v129 = 0;
  v130 = 0;
  v131 = 0;
  v132 = 0;
  v108 = 0;
  v18 = a4 && *(_BYTE *)(v17 + 153);
  if ( a11 )
    *a11 = 0;
  *(_QWORD *)a5 = -1;
  *((_QWORD *)a5 + 1) = 1;
  *a6 = 0;
  *a7 = 0;
  *a8 = 0;
  *a9 = 0;
  v19 = *((_QWORD *)this + 2);
  v20 = *((_DWORD *)this + 3);
  v110 = v126;
  v109[0] = 16;
  v113 = v126;
  v111 = 16;
  v21 = 0x7FFFFFFFFFFFFFFFLL >> *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v19 + 96) + 24LL) + 64LL);
  v98 = v21;
  v107 = v21 - v14;
  if ( (v20 & 1) != 0 )
    return 0;
  v96[0] = 0;
  v103 = v21;
  if ( a2 && *((_QWORD *)a2 + 326) && *((CmsStream **)a2 + 327) == this )
  {
    v121[0] = v14;
    v121[1] = v21 - v14;
    CmsStream::FindMappedValueInRsvpMap(this, a2, (const struct _RANGE *)v121, (struct _RANGE *)&v108, v96, 0);
    if ( v96[0] )
    {
      v28 = v97;
      v29 = (unsigned __int64)v108 >> 63;
      *(_QWORD *)&v108 = v108 & 0x3FFFFFFFFFFFFFFFLL;
      v30 = v108;
      *v101 = v29;
      *(_OWORD *)v28 = v30;
      goto LABEL_44;
    }
    if ( *((_QWORD *)&v108 + 1) < (unsigned __int64)(v21 - v14) )
    {
      v98 = *((_QWORD *)&v108 + 1) + v14;
      v103 = *((_QWORD *)&v108 + 1) + v14;
    }
    v19 = *((_QWORD *)v15 + 2);
    v20 = *((_DWORD *)v15 + 3);
  }
  v23 = *(_QWORD *)(v19 + 96);
  v24 = -1073741772;
  v118 = 0;
  v138 = *(_QWORD *)(v23 + 24);
  v134 = &CmsTransactionCore::`vftable';
  v136 = 0;
  v137 = 0;
  v139 = 0;
  v135 = 0;
  v25 = v20 & 0x8000;
  if ( v25 )
    goto LABEL_23;
  if ( byte_1C01368A0 )
    goto LABEL_49;
  if ( !*(_BYTE *)(v19 + 153) )
  {
LABEL_21:
    if ( a2 && (*((_QWORD *)a2 + 2) & 0x200000000000LL) != 0 )
      goto LABEL_49;
LABEL_23:
    if ( v25 )
      goto LABEL_32;
    if ( !a2 )
      goto LABEL_32;
    v26 = *((_DWORD *)a2 + 688);
    if ( !v26 )
      goto LABEL_32;
    v27 = 0;
    while ( *((CmsStream **)a2 + v27 + 340) != v15 )
    {
      if ( ++v27 >= v26 )
        goto LABEL_32;
    }
    v31 = (CmsRangeMap *)*((_QWORD *)a2 + v27 + 342);
    if ( !v31 )
    {
LABEL_32:
      v31 = (CmsStream *)((char *)v15 + 136);
      if ( v15 == (CmsStream *)-136LL )
        goto LABEL_48;
    }
    v32 = (CmsStream *)((char *)v15 + 136);
    v33 = *(_QWORD *)(v19 + 96);
    v122 = v99;
    if ( (0x7FFFFFFFFFFFFFFFLL >> *(_DWORD *)(*(_QWORD *)(v33 + 24) + 64LL)) - v99 )
    {
      if ( v31 == v32 )
        ExAcquirePushLockSharedEx((char *)v15 + 200, 0);
      if ( *((_QWORD *)v31 + 3)
        && CmsRangeMap::FindMappedValueInternal(
             v31,
             (struct CmsTransactionCore *)&v134,
             (const struct _RANGE *)&v122,
             (struct _RANGE *)&v118,
             1,
             0,
             0,
             0,
             v91,
             v92) )
      {
        v34 = v118;
        v35 = v97;
        *(_QWORD *)v97 = v118 & 0x3FFFFFFFFFFFFFFFLL;
        *((_QWORD *)v35 + 1) = *((_QWORD *)&v118 + 1);
        *v101 = v34 < 0;
        *v102 = (v34 & 0x4000000000000000LL) != 0;
        v24 = 0;
      }
      if ( v31 == v32 )
        ExReleasePushLockEx((char *)v15 + 200, 0);
      v14 = v99;
      if ( v24 >= 0 )
      {
LABEL_42:
        v28 = v97;
LABEL_43:
        v21 = v98;
LABEL_44:
        v36 = v14 + *((_QWORD *)v28 + 1);
        if ( v36 < v14 )
        {
          return (unsigned int)-1073741437;
        }
        else
        {
          if ( v36 > v21 )
            *((_QWORD *)v28 + 1) = v21 - v14;
          return 0;
        }
      }
LABEL_49:
      if ( !a2 )
        return (unsigned int)-1073741802;
      v38 = 0;
      v39 = (__int64 *)((char *)a2 + 2760);
      while ( 1 )
      {
        v40 = *v39;
        if ( *v39 )
        {
          v41 = *(_QWORD *)(v40 + 12);
          if ( (unsigned int)v14 >= v41 && (unsigned int)v14 < v41 + *(unsigned int *)(v40 + 20) )
            break;
        }
        ++v38;
        ++v39;
        if ( v38 )
        {
          v42 = a4;
          goto LABEL_57;
        }
      }
      v46 = *(_WORD *)(v40 + 8);
      v47 = v14 - v41;
      if ( (v46 & 0x20) != 0 || (v46 & 0x200) != 0 )
        v48 = -1;
      else
        v48 = v47 + *(_QWORD *)v40;
      v49 = v97;
      v50 = v106;
      *(_QWORD *)v97 = v48;
      v51 = (char *)a2 + 8 * v38 + 2760;
      *((_QWORD *)v49 + 1) = *(unsigned int *)(*(_QWORD *)v51 + 20LL) - v47;
      *v101 = (*(_BYTE *)(*(_QWORD *)v51 + 8LL) & 0x10) != 0;
      *v50 = (*(_BYTE *)(*(_QWORD *)v51 + 8LL) & 0x20) != 0;
      v52 = *(_WORD *)(*(_QWORD *)v51 + 8LL);
      if ( (v52 & 0x180) != 0 )
        v53 = ((v52 & 0x80u) == 0) + 1;
      else
        v53 = 0;
      v54 = v105;
      *v102 = v53 != 0;
      *v104 = (*(_WORD *)(*(_QWORD *)v51 + 8LL) & 0x200) != 0;
      if ( v54 && (*(_WORD *)(*(_QWORD *)v51 + 8LL) & 0x800) == 0 )
        *v54 = *(struct SmsRun **)v51;
      if ( !*v50 )
        goto LABEL_42;
      v42 = a4;
      if ( !a4 )
        goto LABEL_42;
      CmsTransactionContext::FreeRunCopies(a2);
LABEL_57:
      v100 = (*(__int64 (__fastcall **)(_QWORD, struct CmsTransactionContext *, _DWORD *, bool, __int128 *))(**((_QWORD **)v15 + 2) + 120LL))(
               *((_QWORD *)v15 + 2),
               a2,
               v109,
               v18,
               &v119);
      StreamReservedRegion = v100;
      if ( v100 >= 0 )
      {
        while ( 1 )
        {
          v43 = (char *)Src[1];
          v116 = (char *)Src[1];
          ChecksumSizeInBytes = SmsRunHeader::GetChecksumSizeInBytes((SmsRunHeader *)Src[1]);
          if ( LODWORD(Src[0]) < (unsigned int)ChecksumSizeInBytes + 24 )
            return (unsigned int)-1073740520;
          if ( !v42 || (v43[8] & 0x20) == 0 )
            break;
          if ( v18 )
          {
            StreamReservedRegion = CmsStream::AllocateStreamReservedRegion(
                                     v15,
                                     a2,
                                     v14,
                                     (const struct SmsRunHeader *)v43,
                                     v114,
                                     (unsigned __int8)v129);
            (*(void (__fastcall **)(_QWORD, struct CmsTransactionContext *, unsigned __int8 *))(**((_QWORD **)v15 + 2)
                                                                                              + 168LL))(
              *((_QWORD *)v15 + 2),
              a2,
              v129);
            if ( StreamReservedRegion < 0 )
              return (unsigned int)StreamReservedRegion;
            if ( v115 )
              *v115 = 1;
          }
          else
          {
            v18 = 1;
            (*(void (__fastcall **)(_QWORD, struct CmsTransactionContext *, unsigned __int8 *))(**((_QWORD **)v15 + 2)
                                                                                              + 168LL))(
              *((_QWORD *)v15 + 2),
              a2,
              v129);
          }
          v100 = (*(__int64 (__fastcall **)(_QWORD, struct CmsTransactionContext *, _DWORD *, bool, __int128 *))(**((_QWORD **)v15 + 2) + 120LL))(
                   *((_QWORD *)v15 + 2),
                   a2,
                   v109,
                   v18,
                   &v119);
          StreamReservedRegion = v100;
          if ( v100 < 0 )
            goto LABEL_153;
        }
        if ( !a14 )
        {
          v55 = *((_DWORD *)v15 + 3);
          v56 = DWORD2(v132);
          v128 = 0;
          v124 = 0;
          *(_OWORD *)v125 = 0;
          v127 = 0;
          v57 = v55 & 0x8000;
          if ( v57
            || ((v45 = *((_QWORD *)a2 + 2), v58 = *((_QWORD *)v15 + 2), (v45 & 0x400000000000LL) == 0)
             || *(__int64 *)(v58 + 56) <= 5000)
            && !byte_1C01368A0
            && (!*(_BYTE *)(v58 + 153) || *((_DWORD *)a2 + 688))
            && (v45 & 0x200000000000LL) == 0 )
          {
            if ( v57 )
              goto LABEL_96;
            v45 = *((unsigned int *)a2 + 688);
            if ( !(_DWORD)v45 )
              goto LABEL_96;
            v59 = 0;
            while ( *((CmsStream **)a2 + v59 + 340) != v15 )
            {
              if ( ++v59 >= (unsigned int)v45 )
                goto LABEL_96;
            }
            v60 = (CmsRangeMap *)*((_QWORD *)a2 + v59 + 342);
            if ( !v60 )
            {
LABEL_96:
              v60 = (CmsStream *)((char *)v15 + 136);
              if ( v15 == (CmsStream *)-136LL )
                goto LABEL_110;
            }
            if ( v60 == (CmsStream *)((char *)v15 + 136) )
            {
              v61 = 0;
              v94 = 0;
              ExAcquirePushLockExclusiveEx((char *)v15 + 200, 0);
            }
            else
            {
              v61 = 1;
              v94 = 1;
            }
            if ( (*((_DWORD *)v60 + 10) >= (unsigned int)dword_1C01368A4 || v61) && (*((_DWORD *)v15 + 3) & 0x8000) == 0 )
              CmsRangeMap::DeleteAll(v60, (struct CmsTransactionCore *)v45);
            while ( v56 < *(_DWORD *)(*((_QWORD *)&v131 + 1) + 20LL) )
            {
              v62 = (_SmsIndexEntry *)(*((_QWORD *)&v131 + 1)
                                     + *(unsigned __int16 *)(*((_QWORD *)&v131 + 1)
                                                           + *(unsigned int *)(*((_QWORD *)&v131 + 1) + 16LL)
                                                           + 4LL * v56));
              if ( !v62 )
                break;
              _SmsIndexEntry::MmsRowFromIndexEntry(v62, (struct _CmsRow *)&v124);
              ++v56;
              if ( (*((_WORD *)v125[1] + 4) & 0x220) == 0 )
              {
                *((_QWORD *)&v127 + 1) = *((unsigned int *)v125[1] + 5);
                *(_QWORD *)&v127 = *(_QWORD *)((char *)v125[1] + 12);
                ChecksumType = SmsRunHeader::GetChecksumType(v125[1]);
                v128 = v65
                     & (*(_QWORD *)v64 & 0x3FFFFFFFFFFFFFFFLL
                      | -(__int64)((*(_BYTE *)(v64 + 8) & 0x10) != 0) & 0x8000000000000000uLL)
                     | -(__int64)(ChecksumType != 0) & 0x4000000000000000LL;
                if ( (*(int (__fastcall **)(CmsRangeMap *, struct CmsTransactionContext *, __int128 *, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v60 + 8LL))(
                       v60,
                       a2,
                       &v127,
                       0,
                       0,
                       0,
                       0,
                       0) < 0 )
                  break;
              }
            }
            StreamReservedRegion = v100;
            v43 = v116;
            v15 = v117;
            if ( !v94 )
              ExReleasePushLockEx((char *)v117 + 200, 0);
          }
        }
LABEL_110:
        v95 = 0;
        if ( (*((_QWORD *)a2 + 2) & 0x18000000000LL) == 0 )
        {
LABEL_144:
          v14 = v99;
          v80 = *((_WORD *)v43 + 4);
          v81 = v99 - *(_QWORD *)(v43 + 12);
          if ( (v80 & 0x20) != 0 || (v80 & 0x200) != 0 )
            v82 = -1;
          else
            v82 = v81 + *(_QWORD *)v43;
          v83 = v97;
          *(_QWORD *)v97 = v82;
          v84 = *((unsigned int *)v43 + 5) - v81;
          v85 = v101;
          *((_QWORD *)v83 + 1) = v84;
          *v85 = (v43[8] & 0x10) != 0;
          *v106 = (v43[8] & 0x20) != 0;
          v86 = *((_WORD *)v43 + 4);
          if ( (v86 & 0x180) != 0 )
            v87 = ((v86 & 0x80u) == 0) + 1;
          else
            v87 = 0;
          *v102 = v87 != 0;
          v88 = *((_WORD *)v43 + 4);
          v28 = v83;
          *v104 = (v88 & 0x200) != 0;
LABEL_163:
          (*(void (__fastcall **)(_QWORD, struct CmsTransactionContext *, unsigned __int8 *))(**((_QWORD **)v15 + 2)
                                                                                            + 168LL))(
            *((_QWORD *)v15 + 2),
            a2,
            v129);
          if ( StreamReservedRegion < 0 )
            return (unsigned int)StreamReservedRegion;
          goto LABEL_43;
        }
        v66 = (void *)*((_QWORD *)a2 + 345);
        if ( v66 )
        {
          CmsLookasides::Free(v66);
          LOWORD(v66) = 0;
          *((_QWORD *)a2 + 345) = 0;
        }
        v67 = *((_WORD *)v43 + 4);
        if ( (v67 & 0x180) != 0 )
        {
          v69 = (v67 & 0x80u) == 0;
          v70 = 2;
          if ( v69 )
            v70 = 5;
          v68 = *((_WORD *)v43 + 10) << v70;
        }
        else
        {
          v68 = (__int16)v66;
        }
        v71 = v68 + 24;
        if ( v71 > (unsigned int)dword_1C01368A8 )
        {
          v71 = 24;
          v95 = 1;
        }
        v72 = v71;
        v73 = v71;
        v74 = (unsigned int *)(qword_1C0136F38 + 192LL * (KeGetCurrentProcessorNumberEx(0) % NumProcessors));
        if ( v72 > *v74 )
        {
          v74 = 0;
          v79 = v73 + 8;
LABEL_142:
          PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)512, v79, 0x6950534Du);
          if ( !PoolWithTag )
          {
LABEL_133:
            *((_QWORD *)a2 + 345) = PoolWithTag;
            if ( PoolWithTag )
            {
              memmove(PoolWithTag, v43, v72);
              v78 = v95;
              if ( v95 )
              {
                *(_WORD *)(*((_QWORD *)a2 + 345) + 8LL) |= 0x800u;
                v78 = v95;
              }
              if ( v105 && !v78 )
                *v105 = (struct SmsRun *)*((_QWORD *)a2 + 345);
            }
            goto LABEL_144;
          }
LABEL_132:
          *PoolWithTag++ = v74;
          goto LABEL_133;
        }
        if ( *((_BYTE *)v74 + 8) )
        {
          v75 = (struct _PAGED_LOOKASIDE_LIST *)(v74 + 16);
          if ( *((_BYTE *)v74 + 9) )
          {
            ++v74[21];
            PoolWithTag = ExpInterlockedPopEntrySList(&v75->L.ListHead);
            if ( !PoolWithTag )
            {
              ++v74[22];
              PoolWithTag = (_QWORD *)(*((__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))v74 + 14))(
                                        v74[25],
                                        v74[27],
                                        v74[26]);
            }
            v72 = v73;
          }
          else
          {
            PoolWithTag = ExAllocateFromPagedLookasideList(v75);
            v72 = v73;
          }
LABEL_131:
          if ( PoolWithTag )
            goto LABEL_132;
          goto LABEL_140;
        }
        if ( (int)v74[20] > (int)v74[22] )
        {
          v77 = _InterlockedDecrement((volatile signed __int32 *)v74 + 20);
          if ( v77 >= (int)v74[22] && v77 >= 0 )
          {
            PoolWithTag = ExpInterlockedPopEntrySList((PSLIST_HEADER)v74 + 4);
            v98 = v103;
            goto LABEL_131;
          }
          _InterlockedIncrement((volatile signed __int32 *)v74 + 20);
          v98 = v103;
        }
LABEL_140:
        v79 = v74[1];
        goto LABEL_142;
      }
LABEL_153:
      if ( StreamReservedRegion != -1073741772 )
      {
        v28 = v97;
        goto LABEL_163;
      }
      v89 = (*(__int64 (__fastcall **)(_QWORD, struct CmsTransactionContext *, _DWORD *, __int64, _DWORD, __int128 *, unsigned __int8 *, _QWORD))(**((_QWORD **)v15 + 2) + 128LL))(
              *((_QWORD *)v15 + 2),
              a2,
              v109,
              1,
              0,
              &v119,
              v129,
              0);
      v28 = v97;
      StreamReservedRegion = v89;
      if ( v89 < 0 )
      {
        if ( v89 == -1073741197 )
        {
          *((_QWORD *)v97 + 1) = v107;
          StreamReservedRegion = 0;
LABEL_159:
          *v101 = 0;
          *v102 = 0;
          *v104 = 0;
          goto LABEL_163;
        }
      }
      else
      {
        v90 = *(_QWORD *)((char *)Src[1] + 12) - v14;
        if ( v90 > v107 )
          v90 = v107;
        *((_QWORD *)v97 + 1) = v90;
      }
      if ( v89 < 0 )
        goto LABEL_163;
      goto LABEL_159;
    }
LABEL_48:
    v14 = v99;
    goto LABEL_49;
  }
  if ( a2 )
  {
    if ( !*((_DWORD *)a2 + 688) )
      goto LABEL_49;
    goto LABEL_21;
  }
  return (unsigned int)-1073741802;
}

```

## disassembly

```asm
0x1c0012380  mov     [rsp-8+arg_18], rbx
0x1c0012385  push    rbp
0x1c0012386  push    rsi
0x1c0012387  push    rdi
0x1c0012388  push    r12
0x1c001238a  push    r13
0x1c001238c  push    r14
0x1c001238e  push    r15
0x1c0012390  lea     rbp, [rsp-190h]
0x1c0012398  sub     rsp, 290h
0x1c001239f  mov     rax, cs:__security_cookie
0x1c00123a6  xor     rax, rsp
0x1c00123a9  mov     [rbp+1C0h+var_40], rax
0x1c00123b0  mov     rax, [rbp+1C0h+arg_58]
0x1c00123b7  xorps   xmm1, xmm1
0x1c00123ba  mov     r11, [rbp+1C0h+arg_40]
0x1c00123c1  mov     rbx, r8
0x1c00123c4  mov     r8, [rbp+1C0h+arg_28]
0x1c00123cb  xor     r14d, r14d
0x1c00123ce  mov     rsi, [rbp+1C0h+arg_30]
0x1c00123d5  xorps   xmm0, xmm0
0x1c00123d8  mov     r10, [rbp+1C0h+arg_38]
0x1c00123df  mov     r15, rcx
0x1c00123e2  mov     [rbp+1C0h+var_1E0], rax
0x1c00123e6  mov     rdi, rdx
0x1c00123e9  mov     rax, [rbp+1C0h+arg_60]
0x1c00123f0  mov     rdx, [rbp+1C0h+arg_50]
0x1c00123f7  mov     [rbp+1C0h+var_1D8], rax
0x1c00123fb  xor     eax, eax
0x1c00123fd  mov     [rbp+1C0h+var_1C8], rcx
0x1c0012401  mov     rcx, [rbp+1C0h+arg_20]
0x1c0012408  mov     [rbp+1C0h+var_E0], rax
0x1c001240f  mov     rax, [r15+10h]
0x1c0012413  mov     [rsp+2C0h+var_270], r9b
0x1c0012418  mov     [rsp+2C0h+var_258], rbx
0x1c001241d  mov     [rbp+1C0h+var_230], r11
0x1c0012421  mov     [rsp+2C0h+var_268], rcx
0x1c0012426  mov     [rsp+2C0h+var_248], r8
0x1c001242b  mov     [rbp+1C0h+var_220], rsi
0x1c001242f  mov     [rbp+1C0h+var_240], r10
0x1c0012433  mov     [rbp+1C0h+var_228], rdx
0x1c0012437  mov     [rbp+1C0h+var_150], rbx
0x1c001243b  mov     [rbp+1C0h+var_148], 1
0x1c0012443  mov     [rbp+1C0h+var_1FC], r14d
0x1c0012447  mov     [rbp+1C0h+var_1EC], r14d
0x1c001244b  movups  [rbp+1C0h+var_1B0], xmm0
0x1c001244f  movups  xmmword ptr [rbp+1C0h+Src], xmm0
0x1c0012453  movups  xmmword ptr [rbp+1C0h+var_120], xmm1
0x1c001245a  movups  [rbp+1C0h+var_110], xmm1
0x1c0012461  movups  [rbp+1C0h+var_100], xmm1
0x1c0012468  movups  [rbp+1C0h+var_F0], xmm1
0x1c001246f  movups  [rbp+1C0h+var_210], xmm0
0x1c0012473  test    r9b, r9b
0x1c0012476  jz      short loc_1C0012486
0x1c0012478  cmp     [rax+99h], r14b
0x1c001247f  jz      short loc_1C0012486
0x1c0012481  mov     r13b, 1
0x1c0012484  jmp     short loc_1C0012489
0x1c0012486  xor     r13b, r13b
0x1c0012489  test    rdx, rdx
0x1c001248c  jz      short loc_1C0012491
0x1c001248e  mov     [rdx], r14
0x1c0012491  mov     qword ptr [rcx], 0FFFFFFFFFFFFFFFFh
0x1c0012498  lea     rax, [rbp+1C0h+var_150]
0x1c001249c  mov     qword ptr [rcx+8], 1
0x1c00124a4  mov     [r8], r14b
0x1c00124a7  mov     [rsi], r14b
0x1c00124aa  mov     rsi, 7FFFFFFFFFFFFFFFh
0x1c00124b4  mov     [r10], r14b
0x1c00124b7  mov     r12, rsi
0x1c00124ba  mov     [r11], r14b
0x1c00124bd  mov     r8, [r15+10h]
0x1c00124c1  mov     edx, [r15+0Ch]
0x1c00124c5  mov     [rbp+1C0h+var_1F8], rax
0x1c00124c9  lea     rax, [rbp+1C0h+var_150]
0x1c00124cd  mov     [rbp+1C0h+var_200], 10h
0x1c00124d4  mov     [rbp+1C0h+var_1E8], rax
0x1c00124d8  mov     [rbp+1C0h+var_1F0], 10h
0x1c00124df  mov     rax, [r8+60h]
0x1c00124e3  mov     rcx, [rax+18h]
0x1c00124e7  mov     ecx, [rcx+40h]
0x1c00124ea  sar     r12, cl
0x1c00124ed  mov     r14, r12
0x1c00124f0  mov     [rsp+2C0h+var_260], r12
0x1c00124f5  sub     r14, rbx
0x1c00124f8  mov     [rbp+1C0h+var_218], r14
0x1c00124fc  test    dl, 1
0x1c00124ff  jz      short loc_1C0012508
0x1c0012501  xor     eax, eax
0x1c0012503  jmp     loc_1C0013015
0x1c0012508  mov     [rsp+2C0h+var_26F], 0
0x1c001250d  mov     [rbp+1C0h+var_238], r12
0x1c0012511  test    rdi, rdi
0x1c0012514  jz      short loc_1C001257E
0x1c0012516  cmp     qword ptr [rdi+0A30h], 0
0x1c001251e  jz      short loc_1C001257E
0x1c0012520  cmp     [rdi+0A38h], r15
0x1c0012527  jnz     short loc_1C001257E
0x1c0012529  xor     eax, eax
0x1c001252b  mov     [rbp+1C0h+var_190], rbx
0x1c001252f  mov     [rsp+2C0h+var_298], rax; struct _SmsQuickIndex *
0x1c0012534  lea     r9, [rbp+1C0h+var_210]; struct _RANGE *
0x1c0012538  lea     rax, [rsp+2C0h+var_26F]
0x1c001253d  mov     [rbp+1C0h+var_188], r14
0x1c0012541  lea     r8, [rbp+1C0h+var_190]; struct _RANGE *
0x1c0012545  mov     [rsp+2C0h+var_2A0], rax; unsigned __int8 *
0x1c001254a  mov     rdx, rdi; struct CmsTransactionContext *
0x1c001254d  mov     rcx, r15; this
0x1c0012550  call    ?FindMappedValueInRsvpMap@CmsStream@@AEAAXPEAVCmsTransactionContext@@PEBU_RANGE@@PEAU3@PEAEPEAU_SmsQuickIndex@@@Z; CmsStream::FindMappedValueInRsvpMap(CmsTransactionContext *,_RANGE const *,_RANGE *,uchar *,_SmsQuickIndex *)
0x1c0012555  cmp     [rsp+2C0h+var_26F], 0
0x1c001255a  jnz     loc_1C0012644
0x1c0012560  mov     rax, qword ptr [rbp+1C0h+var_210+8]
0x1c0012564  cmp     rax, r14
0x1c0012567  jnb     short loc_1C0012576
0x1c0012569  lea     rcx, [rax+rbx]
0x1c001256d  mov     [rsp+2C0h+var_260], rcx
0x1c0012572  mov     [rbp+1C0h+var_238], rcx
0x1c0012576  mov     r8, [r15+10h]
0x1c001257a  mov     edx, [r15+0Ch]
0x1c001257e  mov     rax, [r8+60h]
0x1c0012582  xor     r11d, r11d
0x1c0012585  xorps   xmm0, xmm0
0x1c0012588  mov     r12d, 0C0000034h
0x1c001258e  movups  [rbp+1C0h+var_1C0], xmm0
0x1c0012592  mov     rcx, [rax+18h]
0x1c0012596  lea     rax, ??_7CmsTransactionCore@@6B@; const CmsTransactionCore::`vftable'
0x1c001259d  mov     [rbp+1C0h+var_B0], rcx
0x1c00125a4  mov     rcx, 200000000000h
0x1c00125ae  mov     [rbp+1C0h+var_D0], rax
0x1c00125b5  mov     [rbp+1C0h+var_C0], r11
0x1c00125bc  mov     [rbp+1C0h+var_B8], r11d
0x1c00125c3  mov     [rbp+1C0h+var_48], r11b
0x1c00125ca  mov     [rbp+1C0h+var_C8], r11d
0x1c00125d1  and     edx, 8000h
0x1c00125d7  jnz     short loc_1C0012614
0x1c00125d9  cmp     cs:byte_1C01368A0, r11b
0x1c00125e0  jnz     loc_1C00127B5
0x1c00125e6  cmp     [r8+99h], r11b
0x1c00125ed  jz      short loc_1C0012605
0x1c00125ef  test    rdi, rdi
0x1c00125f2  jz      loc_1C00127BA
0x1c00125f8  cmp     [rdi+0AC0h], r11d
0x1c00125ff  jz      loc_1C00127B5
0x1c0012605  test    rdi, rdi
0x1c0012608  jz      short loc_1C0012614
0x1c001260a  test    [rdi+10h], rcx
0x1c001260e  jnz     loc_1C00127B5
0x1c0012614  test    edx, edx
0x1c0012616  jnz     short loc_1C0012689
0x1c0012618  test    rdi, rdi
0x1c001261b  jz      short loc_1C0012689
0x1c001261d  mov     edx, [rdi+0AC0h]
0x1c0012623  test    edx, edx
0x1c0012625  jz      short loc_1C0012689
0x1c0012627  mov     eax, r11d
0x1c001262a  nop     word ptr [rax+rax+00h]
0x1c0012630  mov     ecx, eax
0x1c0012632  cmp     [rdi+rcx*8+0AA0h], r15
0x1c001263a  jz      short loc_1C001267C
0x1c001263c  inc     eax
0x1c001263e  cmp     eax, edx
0x1c0012640  jb      short loc_1C0012630
0x1c0012642  jmp     short loc_1C0012689
0x1c0012644  mov     rax, qword ptr [rbp+1C0h+var_210]
0x1c0012648  mov     rdx, 3FFFFFFFFFFFFFFFh
0x1c0012652  mov     r14, [rsp+2C0h+var_268]
0x1c0012657  mov     rcx, rax
0x1c001265a  and     rcx, rdx
0x1c001265d  shr     rax, 3Fh
0x1c0012661  mov     qword ptr [rbp+1C0h+var_210], rcx
0x1c0012665  xor     r11d, r11d
0x1c0012668  mov     rcx, [rsp+2C0h+var_248]
0x1c001266d  movups  xmm0, [rbp+1C0h+var_210]
0x1c0012671  mov     [rcx], al
0x1c0012673  movups  xmmword ptr [r14], xmm0
0x1c0012677  jmp     loc_1C001278C
0x1c001267c  mov     rbx, [rdi+rcx*8+0AB0h]
0x1c0012684  test    rbx, rbx
0x1c0012687  jnz     short loc_1C0012699
0x1c0012689  lea     rbx, [r15+88h]
0x1c0012690  test    rbx, rbx
0x1c0012693  jz      loc_1C00127B0
0x1c0012699  mov     rdx, [rsp+2C0h+var_258]
0x1c001269e  lea     r14, [r15+88h]
0x1c00126a5  mov     rax, [r8+60h]
0x1c00126a9  mov     [rbp+1C0h+var_180], rdx
0x1c00126ad  mov     rcx, [rax+18h]
0x1c00126b1  mov     ecx, [rcx+40h]
0x1c00126b4  sar     rsi, cl
0x1c00126b7  sub     rsi, rdx
0x1c00126ba  mov     [rbp+1C0h+var_178], rsi
0x1c00126be  jz      loc_1C00127B0
0x1c00126c4  cmp     rbx, r14
0x1c00126c7  jnz     short loc_1C00126E1
0x1c00126c9  xor     edx, edx
0x1c00126cb  lea     rcx, [r15+0C8h]
0x1c00126d2  call    cs:__imp_ExAcquirePushLockSharedEx
0x1c00126d9  nop     dword ptr [rax+rax+00h]
0x1c00126de  xor     r11d, r11d
0x1c00126e1  cmp     qword ptr [rbx+18h], 0
0x1c00126e6  jz      short loc_1C001275B
0x1c00126e8  mov     [rsp+2C0h+var_288], r11; unsigned __int64 *
0x1c00126ed  lea     r9, [rbp+1C0h+var_1C0]; struct _RANGE *
0x1c00126f1  mov     [rsp+2C0h+var_290], r11; unsigned __int64 *
0x1c00126f6  lea     r8, [rbp+1C0h+var_180]; struct _RANGE *
0x1c00126fa  mov     [rsp+2C0h+var_298], r11; struct _SmsQuickIndex *
0x1c00126ff  lea     rdx, [rbp+1C0h+var_D0]; struct CmsTransactionCore *
0x1c0012706  mov     rcx, rbx; this
0x1c0012709  mov     byte ptr [rsp+2C0h+var_2A0], 1; char
0x1c001270e  call    ?FindMappedValueInternal@CmsRangeMap@@IEAAEPEAVCmsTransactionCore@@PEBU_RANGE@@PEAU3@EPEAU_SmsQuickIndex@@PEA_K43E@Z; CmsRangeMap::FindMappedValueInternal(CmsTransactionCore *,_RANGE const *,_RANGE *,uchar,_SmsQuickIndex *,unsigned __int64 *,unsigned __int64 *,_SmsQuickIndex *,uchar)
0x1c0012713  test    al, al
0x1c0012715  jz      short loc_1C001275B
0x1c0012717  mov     rdx, qword ptr [rbp+1C0h+var_1C0]
0x1c001271b  mov     rcx, 3FFFFFFFFFFFFFFFh
0x1c0012725  mov     rax, rdx
0x1c0012728  and     rax, rcx
0x1c001272b  mov     rcx, [rsp+2C0h+var_268]
0x1c0012730  mov     [rcx], rax
0x1c0012733  mov     rax, qword ptr [rbp+1C0h+var_1C0+8]
0x1c0012737  mov     [rcx+8], rax
0x1c001273b  mov     rax, rdx
0x1c001273e  mov     rcx, [rsp+2C0h+var_248]
0x1c0012743  shr     rax, 3Fh
0x1c0012747  shr     rdx, 3Eh
0x1c001274b  and     dl, 1
0x1c001274e  mov     [rcx], al
0x1c0012750  mov     rax, [rbp+1C0h+var_240]
0x1c0012754  mov     [rax], dl
0x1c0012756  xor     eax, eax
0x1c0012758  mov     r12d, eax
0x1c001275b  cmp     rbx, r14
0x1c001275e  jnz     short loc_1C0012775
0x1c0012760  xor     edx, edx
0x1c0012762  lea     rcx, [r15+0C8h]
0x1c0012769  call    cs:__imp_ExReleasePushLockEx
0x1c0012770  nop     dword ptr [rax+rax+00h]
0x1c0012775  mov     rbx, [rsp+2C0h+var_258]
0x1c001277a  xor     r11d, r11d
0x1c001277d  test    r12d, r12d
0x1c0012780  js      short loc_1C00127B5
0x1c0012782  mov     r14, [rsp+2C0h+var_268]
0x1c0012787  mov     r12, [rsp+2C0h+var_260]
0x1c001278c  mov     rcx, [r14+8]
0x1c0012790  add     rcx, rbx
0x1c0012793  cmp     rcx, rbx
0x1c0012796  jl      loc_1C001300E
0x1c001279c  cmp     rcx, r12
0x1c001279f  jle     short loc_1C00127A8
0x1c00127a1  sub     r12, rbx
0x1c00127a4  mov     [r14+8], r12
0x1c00127a8  mov     esi, r11d
0x1c00127ab  jmp     loc_1C0013013
0x1c00127b0  mov     rbx, [rsp+2C0h+var_258]
0x1c00127b5  test    rdi, rdi
0x1c00127b8  jnz     short loc_1C00127C4
0x1c00127ba  mov     esi, 0C0000016h
0x1c00127bf  jmp     loc_1C0013013
0x1c00127c4  mov     r10d, r11d
0x1c00127c7  lea     r8, [rdi+0AC8h]
0x1c00127ce  xchg    ax, ax
0x1c00127d0  mov     rcx, [r8]
0x1c00127d3  mov     esi, 200h
0x1c00127d8  lea     r14d, [rsi-80h]
0x1c00127dc  test    rcx, rcx
0x1c00127df  jz      short loc_1C00127FC
0x1c00127e1  mov     rdx, [rcx+0Ch]
0x1c00127e5  mov     r9d, ebx
0x1c00127e8  cmp     r9, rdx
0x1c00127eb  jb      short loc_1C00127FC
0x1c00127ed  mov     eax, [rcx+14h]
0x1c00127f0  add     rax, rdx
0x1c00127f3  cmp     r9, rax
0x1c00127f6  jb      loc_1C00128C5
0x1c00127fc  inc     r10d
0x1c00127ff  add     r8, 8
0x1c0012803  cmp     r10d, 1
0x1c0012807  jb      short loc_1C00127D0
0x1c0012809  movzx   r12d, [rsp+2C0h+var_270]
0x1c001280f  mov     rcx, [r15+10h]
0x1c0012813  lea     rdx, [rbp+1C0h+var_120]
0x1c001281a  mov     [rsp+2C0h+var_290], r11
0x1c001281f  lea     r8, [rbp+1C0h+var_200]
0x1c0012823  mov     [rsp+2C0h+var_298], rdx; unsigned __int8
0x1c0012828  lea     rdx, [rbp+1C0h+var_1B0]
0x1c001282c  mov     [rsp+2C0h+var_2A0], rdx
0x1c0012831  mov     rdx, rdi
0x1c0012834  mov     rax, [rcx]
0x1c0012837  movzx   r9d, r13b
0x1c001283b  mov     rax, [rax+78h]
0x1c001283f  call    cs:__guard_dispatch_icall_fptr
0x1c0012845  mov     [rsp+2C0h+var_250], eax
0x1c0012849  mov     esi, eax
0x1c001284b  test    eax, eax
0x1c001284d  js      loc_1C0012F3B
0x1c0012853  nop     dword ptr [rax+00h]
0x1c0012857  nop     word ptr [rax+rax+00000000h]
0x1c0012860  mov     r14, [rbp+1C0h+Src+8]
0x1c0012864  mov     rcx, r14; this
0x1c0012867  mov     [rbp+1C0h+var_1D0], r14
0x1c001286b  call    ?GetChecksumSizeInBytes@SmsRunHeader@@QEBAGXZ; SmsRunHeader::GetChecksumSizeInBytes(void)
  ... truncated ...
```
