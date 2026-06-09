# Windows::ChangeTracking::CChangeMonitor::QueryChanges(ushort,wchar_t const *,IStream *,wchar_t const *)

- ea: `0x180091d40`
- end: `0x180092bb8`
- name: `?QueryChanges@CChangeMonitor@ChangeTracking@Windows@@UEAA?AV?$shared_ptr@UIChangeMonitorQuery@ChangeTracking@Windows@@@std@@GPEB_WPEAUIStream@@0@Z`
- size: `3704`
- prototype: `__int64 __fastcall(int, int, int, int, IStream *pstm, __int64)`
- caller_count: `0`
- callee_count: `32`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180012120`
- `0x180012318`
- `0x18001b470`
- `0x18001d8a0`
- `0x18003f130`
- `0x18006f728`
- `0x18006f8cc`
- `0x180091d40`
- `0x180092e8c`
- `0x180092eb0`
- `0x1800932e0`
- `0x1800935d4`
- `0x180093708`
- `0x1800a3a38`
- `0x1800a718c`
- `0x1800dbbb0`
- `0x1800dbd9c`
- `0x1800e1194`
- `0x1800e2374`
- `0x1800f0290`
- `0x1800f0f34`
- `0x1800f1b04`
- `0x1801020c0`
- `0x18010627c`
- `0x180108c3c`
- `0x1801244c0`
- `0x1801244f0`
- `0x18014c1b0`
- `0x18014e874`
- `0x18014ee90`
- `0x18014fc30`
- `0x180241010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180091ea2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180092aaf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180092abe`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180091ea2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180092aaf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180092abe`
- `api-ms-win-shcore-stream-l1-1-0!IStream_WriteStr` at `0x18009250a`
- `api-ms-win-shcore-stream-l1-1-0!IStream_WriteStr` at `0x180092787`
- `api-ms-win-shcore-stream-l1-1-0!IStream_WriteStr` at `0x1800927c7`
- `api-ms-win-shcore-stream-l1-1-0!IStream_WriteStr` at `0x180092807`
- `api-ms-win-shcore-stream-l1-1-0!IStream_WriteStr` at `0x18009250a`
- `api-ms-win-shcore-stream-l1-1-0!IStream_WriteStr` at `0x180092787`
- `api-ms-win-shcore-stream-l1-1-0!IStream_WriteStr` at `0x1800927c7`
- `api-ms-win-shcore-stream-l1-1-0!IStream_WriteStr` at `0x180092807`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x18009291c`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x18009291c`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x1800923fa`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180092445`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x18009263d`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x18009274a`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180092847`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x1800928a0`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x1800928dd`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x1800923fa`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180092445`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x18009263d`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x18009274a`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180092847`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x1800928a0`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x1800928dd`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
_QWORD *__fastcall Windows::ChangeTracking::CChangeMonitor::QueryChanges(
        __int64 a1,
        _QWORD *a2,
        unsigned __int16 a3,
        __int64 a4,
        IStream *pstm,
        __int64 a6)
{
  _QWORD *v7; // rsi
  IStream *v9; // r12
  RTL_SRWLOCK *v10; // r14
  __int64 *v11; // rcx
  __int64 *v12; // rax
  __int64 *v13; // rdx
  _QWORD *v14; // rax
  __int64 v15; // rdi
  __int64 v16; // rdx
  __int64 v17; // r13
  __int64 v18; // rsi
  __int64 v19; // rax
  std::_Ref_count_base *v20; // rcx
  std::_Ref_count_base *v21; // rdx
  std::_Ref_count_base *v22; // rcx
  RTL_SRWLOCK *v23; // r15
  RTL_SRWLOCK *v24; // rdi
  __int64 v25; // rcx
  __int64 v26; // rax
  __int64 v27; // r8
  _QWORD *v28; // rdx
  char v29; // r13
  char v30; // cl
  __int64 v31; // rax
  _QWORD *v32; // rdx
  unsigned __int64 v33; // rdi
  unsigned __int64 v34; // rax
  char *v35; // rsi
  _QWORD *v36; // r8
  int v37; // ecx
  Windows::ChangeTracking::SWalkRecord *v38; // rcx
  __int64 v39; // r9
  HRESULT v40; // eax
  HRESULT v41; // eax
  int v42; // eax
  int v43; // eax
  const WCHAR *v44; // rdx
  HRESULT v45; // eax
  Windows::ChangeTracking::SWalkRecord *j; // rdi
  int v47; // eax
  int v48; // eax
  int v49; // eax
  HRESULT v50; // eax
  int v51; // eax
  HRESULT v52; // eax
  const WCHAR *v53; // rdx
  HRESULT v54; // eax
  const WCHAR *v55; // rdx
  HRESULT v56; // eax
  const WCHAR *v57; // rdx
  HRESULT v58; // eax
  HRESULT v59; // eax
  HRESULT v60; // eax
  HRESULT v61; // eax
  HRESULT v62; // eax
  __int64 v63; // rsi
  std::_Ref_count_base *v64; // r12
  std::_Ref_count_base *v65; // rax
  int v66; // ecx
  __int64 v67; // r8
  std::_Ref_count_base *v68; // rcx
  __int64 v69; // r9
  __int64 v70; // rdi
  int v71; // ecx
  int v73; // [rsp+20h] [rbp-228h]
  int v74; // [rsp+20h] [rbp-228h]
  bool v75; // [rsp+31h] [rbp-217h] BYREF
  Windows::ChangeTracking::CChangeMonitor *v76; // [rsp+38h] [rbp-210h]
  unsigned __int64 i; // [rsp+40h] [rbp-208h] BYREF
  unsigned int v78; // [rsp+48h] [rbp-200h]
  int v79; // [rsp+4Ch] [rbp-1FCh]
  Windows::ChangeTracking::SWalkRecord *v80; // [rsp+50h] [rbp-1F8h] BYREF
  Windows::ChangeTracking::SWalkRecord *v81; // [rsp+58h] [rbp-1F0h]
  __int64 v82; // [rsp+60h] [rbp-1E8h]
  std::_Ref_count_base *v83[2]; // [rsp+68h] [rbp-1E0h] BYREF
  unsigned int pv; // [rsp+78h] [rbp-1D0h] BYREF
  int v85; // [rsp+7Ch] [rbp-1CCh] BYREF
  std::_Ref_count_base *v86[2]; // [rsp+80h] [rbp-1C8h] BYREF
  Windows::ChangeTracking::SWalkRecord *v87; // [rsp+90h] [rbp-1B8h] BYREF
  Windows::ChangeTracking::SWalkRecord *v88; // [rsp+98h] [rbp-1B0h]
  __int64 v89; // [rsp+A0h] [rbp-1A8h]
  __int64 v90; // [rsp+A8h] [rbp-1A0h] BYREF
  RTL_SRWLOCK *v91; // [rsp+B0h] [rbp-198h] BYREF
  __int128 v92; // [rsp+B8h] [rbp-190h]
  unsigned __int64 v93; // [rsp+C8h] [rbp-180h] BYREF
  __int16 v94; // [rsp+D0h] [rbp-178h] BYREF
  char v95; // [rsp+D2h] [rbp-176h]
  const size_t *v96; // [rsp+D8h] [rbp-170h]
  __int128 v97; // [rsp+E0h] [rbp-168h]
  _BYTE *v98; // [rsp+F0h] [rbp-158h]
  _QWORD *v99; // [rsp+F8h] [rbp-150h]
  unsigned int *v100; // [rsp+100h] [rbp-148h]
  __int64 v101; // [rsp+108h] [rbp-140h]
  IStream *v102; // [rsp+110h] [rbp-138h]
  RTL_SRWLOCK *v103; // [rsp+118h] [rbp-130h]
  __int64 v104; // [rsp+120h] [rbp-128h] BYREF
  std::_Ref_count_base *v105; // [rsp+128h] [rbp-120h]
  _BYTE *v106; // [rsp+130h] [rbp-118h]
  _QWORD *v107; // [rsp+138h] [rbp-110h]
  Windows::ChangeTracking::CChangeMonitor *v108; // [rsp+140h] [rbp-108h]
  _BYTE v109[12]; // [rsp+148h] [rbp-100h] BYREF
  int v110; // [rsp+154h] [rbp-F4h]
  _QWORD v111[4]; // [rsp+160h] [rbp-E8h] BYREF
  _QWORD v112[7]; // [rsp+180h] [rbp-C8h] BYREF
  _QWORD *v113; // [rsp+1B8h] [rbp-90h]
  _QWORD v114[7]; // [rsp+1C0h] [rbp-88h] BYREF
  _QWORD *v115; // [rsp+1F8h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+248h] [rbp+0h]

  v7 = a2;
  v99 = a2;
  v76 = (Windows::ChangeTracking::CChangeMonitor *)a1;
  v108 = (Windows::ChangeTracking::CChangeMonitor *)a1;
  v107 = a2;
  v90 = a4;
  v9 = pstm;
  v102 = pstm;
  v104 = a6;
  *a2 = 0;
  a2[1] = 0;
  v79 = 1;
  v97 = 0;
  *(_OWORD *)v86 = 0;
  v10 = (RTL_SRWLOCK *)(a1 + 24);
  CSRWLock::AcquireExclusive((CSRWLock *)(a1 + 24));
  v11 = *(__int64 **)(a1 + 40);
  v12 = (__int64 *)v11[1];
  v110 = 0;
  v13 = v11;
  while ( !*((_BYTE *)v12 + 25) )
  {
    if ( *((_WORD *)v12 + 16) >= a3 )
    {
      v13 = v12;
      v12 = (__int64 *)*v12;
    }
    else
    {
      v12 = (__int64 *)v12[2];
    }
  }
  if ( *((_BYTE *)v13 + 25) || a3 < *((_WORD *)v13 + 16) )
    v13 = v11;
  if ( v13 == v11 )
  {
    v15 = v97;
    v92 = v97;
  }
  else
  {
    v14 = (_QWORD *)std::shared_ptr<std::unique_ptr<unsigned char [0]>>::shared_ptr<std::unique_ptr<unsigned char [0]>>(
                      v83,
                      v13 + 5);
    *(_QWORD *)&v92 = *v14;
    v15 = v92;
    *v14 = 0;
    *(_QWORD *)&v97 = v15;
    *((_QWORD *)&v92 + 1) = v14[1];
    v16 = *((_QWORD *)&v92 + 1);
    v14[1] = 0;
    *((_QWORD *)&v97 + 1) = v16;
    if ( v83[1] )
      std::_Ref_count_base::_Decref(v83[1]);
  }
  if ( v10 )
    ReleaseSRWLockExclusive(v10);
  if ( v15 )
  {
    v93 = (unsigned __int64)v10;
    v17 = v15;
    v101 = v15;
    v18 = a1 + 112;
    v19 = (*(__int64 (__fastcall **)(_QWORD, std::_Ref_count_base **, _QWORD))(**(_QWORD **)(a1 + 112) + 8LL))(
            *(_QWORD *)(a1 + 112),
            v83,
            *(unsigned __int16 *)(v15 + 24));
    v20 = *(std::_Ref_count_base **)v19;
    v21 = *(std::_Ref_count_base **)(v19 + 8);
    *(_QWORD *)v19 = 0;
    *(_QWORD *)(v19 + 8) = 0;
    v86[0] = v20;
    v22 = v86[1];
    v86[1] = v21;
    if ( v22 )
      std::_Ref_count_base::_Decref(v22);
    if ( v83[1] )
      std::_Ref_count_base::_Decref(v83[1]);
    v23 = (RTL_SRWLOCK *)(v15 + 176);
    v103 = (RTL_SRWLOCK *)(v15 + 176);
    CSRWLock::AcquireExclusive((CSRWLock *)(v15 + 176));
    v24 = v10;
    v91 = v10;
    CSRWLock::AcquireExclusive((CSRWLock *)v10);
    v98 = (_BYTE *)(v17 + 192);
    *(_BYTE *)(v17 + 192) = 0;
    v100 = (unsigned int *)(v17 + 32);
    if ( (*(_BYTE *)(v17 + 32) & 0x10) != 0 )
      Windows::ChangeTracking::CChangeMonitor::_CleanFailure(v76, (struct Windows::ChangeTracking::SChangeRoot *)v17);
    if ( *(_QWORD *)(v17 + 8) )
    {
      v26 = std::shared_ptr<std::unique_ptr<unsigned char [0]>>::shared_ptr<std::unique_ptr<unsigned char [0]>>(
              v83,
              v18);
      Windows::ChangeTracking::CRootAggregator::EnsureCounterInitialization(v27, v26);
      v25 = *(_QWORD *)(v17 + 8);
      if ( *(_DWORD *)(v25 + 4) >= Windows::ChangeTracking::CRootAggregator::s_Threshold )
      {
        *(_DWORD *)(v25 + 4) = 0;
        v114[0] = &std::_Func_impl_no_alloc<_lambda_f8509d485024d063c80adfb112d3e611_,void,unsigned short>::`vftable';
        v114[1] = v76;
        v115 = v114;
        Windows::ChangeTracking::CRootAggregator::WalkClients(*(_QWORD *)(v17 + 8), v114);
        LODWORD(v25) = (_DWORD)v115;
        if ( v115 )
        {
          v28 = v114;
          LOBYTE(v28) = v115 != v114;
          (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v115 + 32LL))(v115, v28);
        }
      }
    }
    v83[0] = (std::_Ref_count_base *)(v17 + 28);
    Windows::ChangeTracking::CChangeMonitor::_CompleteChanges(v25, (unsigned int)v86, 0, *(_DWORD *)(v17 + 28), v17);
    *v100 = *v100 & 0xFFFFFFFA | 1;
    *(_BYTE *)(v17 + 37) = 0;
    if ( (unsigned __int8)Windows::ChangeTracking::CChangeMonitor::_VerifyTracking(v76) )
    {
      v106 = (_BYTE *)(v17 + 192);
      v75 = (*(_BYTE *)(v17 + 36) & 2) != 0;
      std::vector<unique_ptr_bytes_buffer>::vector<unique_ptr_bytes_buffer>(&v80);
      Windows::ChangeTracking::CFilePrivilegeChecker::CFilePrivilegeChecker((Windows::ChangeTracking::CFilePrivilegeChecker *)v109);
      v30 = *(_BYTE *)(v17 + 26);
      LOWORD(v87) = *(_WORD *)v17;
      BYTE2(v87) = v30;
      v88 = (Windows::ChangeTracking::SWalkRecord *)&cchOriginalDestLength;
      v94 = (__int16)v87;
      v95 = v30 + 1;
      v96 = &cchOriginalDestLength;
      Windows::ChangeTracking::CStoreTransaction::CStoreTransaction(v111, v86);
      v31 = *(_QWORD *)v86[0];
      v112[0] = &std::_Func_impl_no_alloc<_lambda_4c7eb133c9a4eb60dfe14e7a6bfc514f_,bool,Windows::ChangeTracking::SStoredChangeRecordKey &,Windows::ChangeTracking::SChangeRecordValue &>::`vftable';
      v112[1] = &v80;
      v112[2] = v109;
      v112[3] = &v90;
      v112[4] = v76;
      v112[5] = &v75;
      v112[6] = v17;
      v113 = v112;
      (*(void (__fastcall **)(std::_Ref_count_base *, Windows::ChangeTracking::SWalkRecord **, __int16 *, _QWORD *))(v31 + 88))(
        v86[0],
        &v87,
        &v94,
        v112);
      if ( v113 )
      {
        v32 = v112;
        LOBYTE(v32) = v113 != v112;
        (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v113 + 32LL))(v113, v32);
      }
      Windows::ChangeTracking::CStoreTransaction::~CStoreTransaction((Windows::ChangeTracking::CStoreTransaction *)v111);
      Microsoft::WRL::Wrappers::Details::SyncLockExclusive::~SyncLockExclusive((Microsoft::WRL::Wrappers::Details::SyncLockExclusive *)&v91);
      if ( (*(_BYTE *)(v17 + 36) & 1) != 0 )
      {
        std::wstring::wstring(v111, v90);
        v33 = 0xF0F0F0F0F0F0F0F1uLL * ((v81 - v80) >> 4);
        v34 = 0;
        for ( i = 0; v34 < v33; i = v34 )
        {
          if ( *(_BYTE *)(v17 + 192) )
            break;
          v35 = (char *)v80 + 272 * v34;
          if ( (*((_DWORD *)v35 + 14) & 0x2000) != 0 && (v35[60] & 0x10) != 0 && !*((_QWORD *)v35 + 21) )
          {
            v36 = v111;
            if ( v111[3] > 7u )
              v36 = (_QWORD *)v111[0];
            Windows::ChangeTracking::CChangeMonitor::_LogMessage(v76, L"EXPANDING: %s%s", v36);
            std::vector<unique_ptr_bytes_buffer>::vector<unique_ptr_bytes_buffer>(&v87);
            Windows::ChangeTracking::CChangeMonitor::_ExpandDirectoryChanges(
              v37,
              (unsigned int)v111,
              (_DWORD)v35,
              i,
              (__int64)&v80,
              (__int64)&v87);
            v38 = v87;
            if ( v87 != v88 )
            {
              std::vector<Windows::ChangeTracking::SWalkRecord>::insert<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<Windows::ChangeTracking::SWalkRecord>>>,0>(
                (unsigned int)&v80,
                (unsigned int)&v94,
                (_DWORD)v81,
                (_DWORD)v87,
                (__int64)v88);
              v33 = 0xF0F0F0F0F0F0F0F1uLL * ((v81 - v80) >> 4);
              v38 = v87;
            }
            if ( v38 )
            {
              std::_Destroy_range<std::allocator<Windows::ChangeTracking::SWalkRecord>>(v38);
              std::_Deallocate<16>(v87, 16 * ((v89 - (__int64)v87) >> 4));
            }
          }
          v34 = i + 1;
        }
        ReIndexPatternInfo::~ReIndexPatternInfo((ReIndexPatternInfo *)v111);
      }
      Windows::ChangeTracking::CFilePrivilegeChecker::~CFilePrivilegeChecker((Windows::ChangeTracking::CFilePrivilegeChecker *)v109);
      if ( *(_BYTE *)(v17 + 192) )
      {
        v29 = 0;
      }
      else
      {
        LOBYTE(v39) = v75;
        std::_Sort_unchecked<Windows::ChangeTracking::SWalkRecord *,_lambda_b48eeea205f7c2a4175cb86452de926a_>(
          v80,
          v81,
          0xF0F0F0F0F0F0F0F1uLL * ((v81 - v80) >> 4),
          v39);
        v40 = IStream_Write(pstm, &dword_180267304, 4u);
        if ( v40 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x48A,
            (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\changetracking\\core\\changemonitor.cpp",
            (const char *)(unsigned int)v40,
            v73);
        pv = -252645135 * ((v81 - v80) >> 4);
        v41 = IStream_Write(pstm, &pv, 4u);
        if ( v41 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x48C,
            (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\changetracking\\core\\changemonitor.cpp",
            (const char *)(unsigned int)v41,
            v73);
        v87 = 0;
        v42 = (*(__int64 (__fastcall **)(IStream *, _QWORD, __int64, Windows::ChangeTracking::SWalkRecord **))(*(_QWORD *)pstm + 40LL))(
                pstm,
                0,
                1,
                &v87);
        if ( v42 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x490,
            (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\changetracking\\core\\changemonitor.cpp",
            (const char *)(unsigned int)v42,
            v73);
        v43 = (*(__int64 (__fastcall **)(IStream *, __int64, __int64))(*(_QWORD *)pstm + 40LL))(pstm, 4LL * pv, 1);
        if ( v43 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x494,
            (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\changetracking\\core\\changemonitor.cpp",
            (const char *)(unsigned int)v43,
            v73);
        v44 = (const WCHAR *)(v17 + 40);
        if ( *(_QWORD *)(v17 + 64) > 7u )
          v44 = *(const WCHAR **)v44;
        v45 = IStream_WriteStr(pstm, v44);
        if ( v45 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x496,
            (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\changetracking\\core\\changemonitor.cpp",
            (const char *)(unsigned int)v45,
            v73);
        v78 = 0;
        for ( j = v80; ; j = (Windows::ChangeTracking::SWalkRecord *)((char *)j + 272) )
        {
          v111[0] = j;
          if ( j == v81 || *v98 )
          {
            v29 = 0;
            goto LABEL_97;
          }
          i = 0;
          v47 = (*(__int64 (__fastcall **)(IStream *, _QWORD, __int64, unsigned __int64 *))(*(_QWORD *)v9 + 40LL))(
                  v9,
                  0,
                  1,
                  &i);
          if ( v47 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x49D,
              (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\changetracking\\core\\changemonitor.cpp",
              (const char *)(unsigned int)v47,
              v73);
          if ( i >= 0xFFFFFFFF )
            break;
          v49 = (*(__int64 (__fastcall **)(IStream *, char *, _QWORD, _QWORD))(*(_QWORD *)v9 + 40LL))(
                  v9,
                  (char *)v87 + 4 * v78,
                  0,
                  0);
          if ( v49 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x4A8,
              (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\changetracking\\core\\changemonitor.cpp",
              (const char *)(unsigned int)v49,
              v73);
          v50 = IStream_Write(v9, &i, 4u);
          if ( v50 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x4A9,
              (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\changetracking\\core\\changemonitor.cpp",
              (const char *)(unsigned int)v50,
              v73);
          v51 = (*(__int64 (__fastcall **)(IStream *, unsigned __int64, _QWORD, _QWORD))(*(_QWORD *)v9 + 40LL))(
                  v9,
                  i,
                  0,
                  0);
          if ( v51 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x4AC,
              (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\changetracking\\core\\changemonitor.cpp",
              (const char *)(unsigned int)v51,
              v73);
          try
          {
            Windows::ChangeTracking::CChangeMonitor::_ProcessFileExtents(v76, (__int64)j);
          }
          catch ( ... )
          {
            if ( (*(_BYTE *)(v101 + 36) & 8) != 0 )
              throw;
            *(_DWORD *)v111[0] &= ~8u;
            v92 = v97;
            v23 = v103;
            j = (Windows::ChangeTracking::SWalkRecord *)v111[0];
            v98 = v106;
            v99 = v107;
            v76 = v108;
            v9 = v102;
            v10 = (RTL_SRWLOCK *)v93;
          }
          v52 = IStream_Write(v9, j, 0x78u);
          if ( v52 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x4BE,
              (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\changetracking\\core\\changemonitor.cpp",
              (const char *)(unsigned int)v52,
              v73);
          if ( (*(_BYTE *)j & 1) != 0 )
          {
            v53 = (const WCHAR *)((char *)j + 120);
            if ( *((_QWORD *)j + 18) > 7u )
              v53 = *(const WCHAR **)v53;
            v54 = IStream_WriteStr(v9, v53);
            if ( v54 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x4C1,
                (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\changetracking\\core\\changemonitor.cpp",
                (const char *)(unsigned int)v54,
                v73);
          }
          if ( (*(_BYTE *)j & 4) != 0 )
          {
            v55 = (const WCHAR *)((char *)j + 184);
            if ( *((_QWORD *)j + 26) > 7u )
              v55 = *(const WCHAR **)v55;
            v56 = IStream_WriteStr(v9, v55);
            if ( v56 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x4C5,
                (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\changetracking\\core\\changemonitor.cpp",
                (const char *)(unsigned int)v56,
                v73);
          }
          if ( (*(_BYTE *)j & 2) != 0 )
          {
            v57 = (const WCHAR *)((char *)j + 152);
            if ( *((_QWORD *)j + 22) > 7u )
              v57 = *(const WCHAR **)v57;
            v58 = IStream_WriteStr(v9, v57);
            if ( v58 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x4C9,
                (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\changetracking\\core\\changemonitor.cpp",
                (const char *)(unsigned int)v58,
                v73);
          }
          if ( (*(_BYTE *)j & 8) != 0 )
          {
            v59 = IStream_Write(v9, (char *)j + 264, 8u);
            if ( v59 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x4CD,
                (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\changetracking\\core\\changemonitor.cpp",
                (const char *)(unsigned int)v59,
                v73);
            v85 = -1431655765 * ((__int64)(*((_QWORD *)j + 31) - *((_QWORD *)j + 30)) >> 3);
            v60 = IStream_Write(v9, &v85, 4u);
            if ( v60 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x4CF,
                (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\changetracking\\core\\changemonitor.cpp",
                (const char *)(unsigned int)v60,
                v73);
            v61 = IStream_Write(v9, *((const void **)j + 30), 24 * v85);
            if ( v61 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x4D1,
                (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\changetracking\\core\\changemonitor.cpp",
                (const char *)(unsigned int)v61,
                v73);
          }
          ++v78;
        }
        v48 = (*(__int64 (__fastcall **)(IStream *, _QWORD))(*(_QWORD *)v9 + 48LL))(v9, 0);
        v29 = 1;
        if ( v48 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x4D8,
            (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\changetracking\\core\\changemonitor.cpp",
            (const char *)(unsigned int)v48,
            v73);
LABEL_97:
        v62 = IStream_Reset(v9);
        if ( v62 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x4DC,
            (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\changetracking\\core\\changemonitor.cpp",
            (const char *)(unsigned int)v62,
            v73);
        v93 = 0xF0F0F0F0F0F0F0F1uLL * ((v81 - v80) >> 4);
        SearchIndexerDiagnosticTelemetry::FileChangeTrackingClientGetChanges<wchar_t const * &,unsigned __int64>(
          &v104,
          &v93);
      }
      if ( v80 )
      {
        std::_Destroy_range<std::allocator<Windows::ChangeTracking::SWalkRecord>>(v80);
        std::_Deallocate<16>(v80, 16 * ((v82 - (__int64)v80) >> 4));
      }
      v24 = v91;
    }
    else
    {
      v29 = 1;
    }
    v63 = std::enable_shared_from_this<Windows::ChangeTracking::CChangeMonitor>::shared_from_this(
            (char *)v76 + 8,
            &v104);
    v64 = v83[0];
    ++*(_DWORD *)v83[0];
    v65 = (std::_Ref_count_base *)operator new(0x38u);
    v83[0] = v65;
    *(_OWORD *)v65 = 0;
    *((_DWORD *)v65 + 2) = 1;
    *((_DWORD *)v65 + 3) = 1;
    *(_QWORD *)v65 = &std::_Ref_count_obj2<Windows::ChangeTracking::CChangeMonitor::CChangeMonitorQuery>::`vftable';
    v66 = *(_DWORD *)v64;
    *((_QWORD *)v65 + 2) = &Windows::ChangeTracking::CChangeMonitor::CChangeMonitorQuery::`vftable';
    *((_WORD *)v65 + 12) = a3;
    *((_DWORD *)v65 + 7) = v66;
    *((_BYTE *)v65 + 32) = v29;
    *((_DWORD *)v65 + 9) = 0;
    std::weak_ptr<Windows::ChangeTracking::CChangeMonitor>::weak_ptr<Windows::ChangeTracking::CChangeMonitor>(
      (char *)v65 + 40,
      v63);
    v79 |= 4u;
    v7 = v99;
    *v99 = v67;
    v68 = (std::_Ref_count_base *)v7[1];
    v7[1] = v69;
    if ( v68 )
      std::_Ref_count_base::_Decref(v68);
    if ( v105 )
      std::_Ref_count_base::_Decref(v105);
    if ( v29 )
      (*(void (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v7 + 32LL))(*v7, (unsigned int)((*v100 & 0x20) != 0) + 1);
    if ( v24 )
      ReleaseSRWLockExclusive(v24);
    if ( v23 )
      ReleaseSRWLockExclusive(v23);
    v70 = v92;
    if ( (_QWORD)v92 && *(_BYTE *)(v92 + 192) )
    {
      *(_OWORD *)v83 = 0;
      std::shared_ptr<Windows::ChangeTracking::SChange>::operator=(v7, v83);
      if ( v83[1] )
        std::_Ref_count_base::_Decref(v83[1]);
      v83[0] = (std::_Ref_count_base *)v10;
      CSRWLock::AcquireExclusive((CSRWLock *)v10);
      Windows::ChangeTracking::CChangeMonitor::_CompleteChanges(v71, (unsigned int)v86, 0, *(_DWORD *)(v70 + 28), v70);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4F2,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\changetracking\\core\\changemonitor.cpp",
        (const char *)0x800704C7LL,
        v74);
    }
  }
  if ( !*v7 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x4F7,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\changetracking\\core\\changemonitor.cpp",
      (const char *)0x80070057LL,
      v73);
  if ( v86[1] )
    std::_Ref_count_base::_Decref(v86[1]);
  if ( *((_QWORD *)&v92 + 1) )
    std::_Ref_count_base::_Decref(*((std::_Ref_count_base **)&v92 + 1));
  return v7;
}

```

## disassembly

```asm
0x180091d40  mov     r11, rsp
0x180091d43  mov     [r11+18h], r8w
0x180091d48  push    rbx
0x180091d49  push    rsi
0x180091d4a  push    rdi
0x180091d4b  push    r12
0x180091d4d  push    r13
0x180091d4f  push    r14
0x180091d51  push    r15
0x180091d53  sub     rsp, 210h
0x180091d5a  mov     rax, cs:__security_cookie
0x180091d61  xor     rax, rsp
0x180091d64  mov     [rsp+248h+var_48], rax
0x180091d6c  movzx   edi, r8w
0x180091d70  mov     rsi, rdx
0x180091d73  mov     [r11-150h], rdx
0x180091d7a  mov     r15, rcx
0x180091d7d  mov     [rsp+248h+var_210], rcx
0x180091d82  mov     [rsp+248h+var_108], rcx
0x180091d8a  mov     [r11-110h], rdx
0x180091d91  mov     [r11-1A0h], r9
0x180091d98  mov     r12, [rsp+248h+pstm]
0x180091da0  mov     [rsp+248h+var_138], r12
0x180091da8  mov     rax, [rsp+248h+arg_28]
0x180091db0  mov     [r11-128h], rax
0x180091db7  xor     ebx, ebx
0x180091db9  mov     [rsp+248h+var_1FC], ebx
0x180091dbd  mov     [rdx], rbx
0x180091dc0  mov     [rdx+8], rbx
0x180091dc4  mov     [rsp+248h+var_1FC], 1
0x180091dcc  xorps   xmm0, xmm0
0x180091dcf  movdqu  [rsp+248h+var_168], xmm0
0x180091dd8  movdqu  xmmword ptr [rsp+248h+var_1C8], xmm0
0x180091de1  lea     r14, [rcx+18h]
0x180091de5  mov     rcx, r14; this
0x180091de8  call    ?AcquireExclusive@CSRWLock@@QEAAXXZ; CSRWLock::AcquireExclusive(void)
0x180091ded  mov     rcx, [r15+28h]
0x180091df1  mov     rax, [rcx+8]
0x180091df5  xor     edx, edx
0x180091df7  mov     [rsp+248h+var_F4], edx
0x180091dfe  mov     rdx, rcx
0x180091e01  jmp     short loc_180091E15
0x180091e03  cmp     [rax+20h], di
0x180091e07  jnb     short loc_180091E0F
0x180091e09  mov     rax, [rax+10h]
0x180091e0d  jmp     short loc_180091E15
0x180091e0f  mov     rdx, rax
0x180091e12  mov     rax, [rax]
0x180091e15  cmp     [rax+19h], bl
0x180091e18  jz      short loc_180091E03
0x180091e1a  cmp     [rdx+19h], bl
0x180091e1d  jnz     short loc_180091E25
0x180091e1f  cmp     di, [rdx+20h]
0x180091e23  jnb     short loc_180091E28
0x180091e25  mov     rdx, rcx
0x180091e28  cmp     rdx, rcx
0x180091e2b  jz      short loc_180091E7A
0x180091e2d  add     rdx, 28h ; '('
0x180091e31  lea     rcx, [rsp+248h+var_1E0]
0x180091e36  call    ??0?$shared_ptr@V?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<std::unique_ptr<uchar [0]>>::shared_ptr<std::unique_ptr<uchar [0]>>(std::shared_ptr<std::unique_ptr<uchar [0]>> const &)
0x180091e3b  mov     rdi, [rax]
0x180091e3e  mov     qword ptr [rsp+248h+var_190], rdi
0x180091e46  mov     [rax], rbx
0x180091e49  mov     qword ptr [rsp+248h+var_168], rdi
0x180091e51  mov     rdx, [rax+8]
0x180091e55  mov     qword ptr [rsp+248h+var_190+8], rdx
0x180091e5d  mov     [rax+8], rbx
0x180091e61  mov     qword ptr [rsp+248h+var_168+8], rdx
0x180091e69  mov     rcx, [rsp+248h+var_1E0+8]; this
0x180091e6e  test    rcx, rcx
0x180091e71  jz      short loc_180091E9A
0x180091e73  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180091e78  jmp     short loc_180091E9A
0x180091e7a  mov     rax, qword ptr [rsp+248h+var_168+8]
0x180091e82  mov     qword ptr [rsp+248h+var_190+8], rax
0x180091e8a  mov     rdi, qword ptr [rsp+248h+var_168]
0x180091e92  mov     qword ptr [rsp+248h+var_190], rdi
0x180091e9a  test    r14, r14
0x180091e9d  jz      short loc_180091EA8
0x180091e9f  mov     rcx, r14; SRWLock
0x180091ea2  call    cs:__imp_ReleaseSRWLockExclusive
0x180091ea8  test    rdi, rdi
0x180091eab  jz      loc_180092B45
0x180091eb1  mov     [rsp+248h+var_180], r14
0x180091eb9  mov     r13, rdi
0x180091ebc  mov     [rsp+248h+var_140], rdi
0x180091ec4  lea     rsi, [r15+70h]
0x180091ec8  mov     rcx, [rsi]
0x180091ecb  mov     rax, [rcx]
0x180091ece  movzx   r8d, word ptr [rdi+18h]
0x180091ed3  lea     rdx, [rsp+248h+var_1E0]
0x180091ed8  mov     rax, [rax+8]
0x180091edc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091ee1  mov     rcx, [rax]
0x180091ee4  mov     rdx, [rax+8]
0x180091ee8  mov     [rax], rbx
0x180091eeb  mov     [rax+8], rbx
0x180091eef  mov     [rsp+248h+var_1C8], rcx
0x180091ef7  mov     rcx, [rsp+248h+var_1C8+8]; this
0x180091eff  mov     [rsp+248h+var_1C8+8], rdx
0x180091f07  test    rcx, rcx
0x180091f0a  jz      short loc_180091F11
0x180091f0c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180091f11  mov     rcx, [rsp+248h+var_1E0+8]; this
0x180091f16  test    rcx, rcx
0x180091f19  jz      short loc_180091F20
0x180091f1b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180091f20  lea     r15, [rdi+0B0h]
0x180091f27  mov     [rsp+248h+var_130], r15
0x180091f2f  mov     rcx, r15; this
0x180091f32  call    ?AcquireExclusive@CSRWLock@@QEAAXXZ; CSRWLock::AcquireExclusive(void)
0x180091f37  nop
0x180091f38  mov     rdi, r14
0x180091f3b  mov     [rsp+248h+var_198], r14
0x180091f43  mov     rcx, r14; this
0x180091f46  call    ?AcquireExclusive@CSRWLock@@QEAAXXZ; CSRWLock::AcquireExclusive(void)
0x180091f4b  nop
0x180091f4c  lea     rax, [r13+0C0h]
0x180091f53  mov     [rsp+248h+var_158], rax
0x180091f5b  mov     [rax], bl
0x180091f5d  lea     rax, [r13+20h]
0x180091f61  mov     [rsp+248h+var_148], rax
0x180091f69  test    byte ptr [rax], 10h
0x180091f6c  jz      short loc_180091F7B
0x180091f6e  mov     rdx, r13; struct Windows::ChangeTracking::SChangeRoot *
0x180091f71  mov     rcx, [rsp+248h+var_210]; this
0x180091f76  call    ?_CleanFailure@CChangeMonitor@ChangeTracking@Windows@@AEAAXAEAUSChangeRoot@23@@Z; Windows::ChangeTracking::CChangeMonitor::_CleanFailure(Windows::ChangeTracking::SChangeRoot &)
0x180091f7b  mov     r8, [r13+8]
0x180091f7f  test    r8, r8
0x180091f82  jz      loc_180092017
0x180091f88  mov     rdx, rsi
0x180091f8b  lea     rcx, [rsp+248h+var_1E0]
0x180091f90  call    ??0?$shared_ptr@V?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<std::unique_ptr<uchar [0]>>::shared_ptr<std::unique_ptr<uchar [0]>>(std::shared_ptr<std::unique_ptr<uchar [0]>> const &)
0x180091f95  mov     rdx, rax
0x180091f98  mov     rcx, r8
0x180091f9b  call    ?EnsureCounterInitialization@CRootAggregator@ChangeTracking@Windows@@QEAAXV?$shared_ptr@UIChangeMonitorStoreRetriever@ChangeTracking@Windows@@@std@@@Z; Windows::ChangeTracking::CRootAggregator::EnsureCounterInitialization(std::shared_ptr<Windows::ChangeTracking::IChangeMonitorStoreRetriever>)
0x180091fa0  mov     rcx, [r13+8]
0x180091fa4  mov     eax, cs:?s_Threshold@CRootAggregator@ChangeTracking@Windows@@2KA; ulong Windows::ChangeTracking::CRootAggregator::s_Threshold
0x180091faa  cmp     [rcx+4], eax
0x180091fad  jb      short loc_180092017
0x180091faf  mov     [rcx+4], ebx
0x180091fb2  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_f8509d485024d063c80adfb112d3e611_@@XG@std@@6B@; const std::_Func_impl_no_alloc<_lambda_f8509d485024d063c80adfb112d3e611_,void,ushort>::`vftable'
0x180091fb9  mov     [rsp+248h+var_88], rax
0x180091fc1  mov     rax, [rsp+248h+var_210]
0x180091fc6  mov     [rsp+248h+var_80], rax
0x180091fce  lea     rax, [rsp+248h+var_88]
0x180091fd6  mov     [rsp+248h+var_50], rax
0x180091fde  lea     rdx, [rsp+248h+var_88]
0x180091fe6  mov     rcx, [r13+8]
0x180091fea  call    ?WalkClients@CRootAggregator@ChangeTracking@Windows@@QEAAXAEBV?$function@$$A6AXG@Z@std@@@Z; Windows::ChangeTracking::CRootAggregator::WalkClients(std::function<void (ushort)> const &)
0x180091fef  nop
0x180091ff0  mov     rcx, [rsp+248h+var_50]
0x180091ff8  test    rcx, rcx
0x180091ffb  jz      short loc_180092017
0x180091ffd  mov     rax, [rcx]
0x180092000  lea     rdx, [rsp+248h+var_88]
0x180092008  cmp     rcx, rdx
0x18009200b  setnz   dl
0x18009200e  mov     rax, [rax+20h]
0x180092012  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092017  lea     rax, [r13+1Ch]
0x18009201b  mov     [rsp+248h+var_1E0], rax
0x180092020  mov     [rsp+248h+var_228], r13; int
0x180092025  mov     r9d, [rax]
0x180092028  xor     r8d, r8d
0x18009202b  lea     rdx, [rsp+248h+var_1C8]
0x180092033  call    ?_CompleteChanges@CChangeMonitor@ChangeTracking@Windows@@AEAAXAEBV?$shared_ptr@UIChangeMonitorStore@ChangeTracking@Windows@@@std@@W4CompletionType@23@IAEAUSChangeRoot@23@@Z; Windows::ChangeTracking::CChangeMonitor::_CompleteChanges(std::shared_ptr<Windows::ChangeTracking::IChangeMonitorStore> const &,Windows::ChangeTracking::CompletionType,uint,Windows::ChangeTracking::SChangeRoot &)
0x180092038  mov     rcx, [rsp+248h+var_148]
0x180092040  mov     eax, [rcx]
0x180092042  and     eax, 0FFFFFFFBh
0x180092045  or      eax, 1
0x180092048  mov     [rcx], eax
0x18009204a  mov     [r13+25h], bl
0x18009204e  mov     r8, r13
0x180092051  lea     rdx, [rsp+248h+var_1C8]
0x180092059  mov     rcx, [rsp+248h+var_210]
0x18009205e  call    ?_VerifyTracking@CChangeMonitor@ChangeTracking@Windows@@AEAA_NAEBV?$shared_ptr@UIChangeMonitorStore@ChangeTracking@Windows@@@std@@AEAUSChangeRoot@23@@Z; Windows::ChangeTracking::CChangeMonitor::_VerifyTracking(std::shared_ptr<Windows::ChangeTracking::IChangeMonitorStore> const &,Windows::ChangeTracking::SChangeRoot &)
0x180092063  test    al, al
0x180092065  jnz     short loc_18009206F
0x180092067  mov     r13b, 1
0x18009206a  jmp     loc_1800929C0
0x18009206f  lea     rax, [r13+0C0h]
0x180092076  mov     [rsp+248h+var_118], rax
0x18009207e  mov     [rsp+248h+var_218], bl
0x180092082  mov     al, [r13+24h]
0x180092086  shr     al, 1
0x180092088  and     al, 1
0x18009208a  mov     [rsp+248h+var_217], al
0x18009208e  lea     rcx, [rsp+248h+var_1F8]; void *
0x180092093  call    ??0?$vector@Uunique_ptr_bytes_buffer@@V?$allocator@Uunique_ptr_bytes_buffer@@@std@@@std@@QEAA@XZ; std::vector<unique_ptr_bytes_buffer>::vector<unique_ptr_bytes_buffer>(void)
0x180092098  nop
0x180092099  lea     rcx, [rsp+248h+var_100]; this
0x1800920a1  call    ??0CFilePrivilegeChecker@ChangeTracking@Windows@@QEAA@XZ; Windows::ChangeTracking::CFilePrivilegeChecker::CFilePrivilegeChecker(void)
0x1800920a6  nop
0x1800920a7  mov     cl, [r13+1Ah]
0x1800920ab  movzx   eax, word ptr [r13+0]
0x1800920b0  mov     word ptr [rsp+248h+var_1B8], ax
0x1800920b8  mov     byte ptr [rsp+248h+var_1B8+2], cl
0x1800920bf  lea     rdx, cchOriginalDestLength
0x1800920c6  mov     [rsp+248h+var_1B0], rdx
0x1800920ce  mov     [rsp+248h+var_178], ax
0x1800920d6  inc     cl
0x1800920d8  mov     [rsp+248h+var_176], cl
0x1800920df  mov     [rsp+248h+var_170], rdx
0x1800920e7  lea     rdx, [rsp+248h+var_1C8]
0x1800920ef  lea     rcx, [rsp+248h+var_E8]
0x1800920f7  call    ??0CStoreTransaction@ChangeTracking@Windows@@QEAA@AEBV?$shared_ptr@UIChangeMonitorStore@ChangeTracking@Windows@@@std@@@Z; Windows::ChangeTracking::CStoreTransaction::CStoreTransaction(std::shared_ptr<Windows::ChangeTracking::IChangeMonitorStore> const &)
0x1800920fc  nop
0x1800920fd  mov     rcx, [rsp+248h+var_1C8]
0x180092105  mov     rax, [rcx]
0x180092108  lea     rdx, ??_7?$_Func_impl_no_alloc@V_lambda_4c7eb133c9a4eb60dfe14e7a6bfc514f_@@_NAEAUSStoredChangeRecordKey@ChangeTracking@Windows@@AEAUSChangeRecordValue@34@@std@@6B@; const std::_Func_impl_no_alloc<_lambda_4c7eb133c9a4eb60dfe14e7a6bfc514f_,bool,Windows::ChangeTracking::SStoredChangeRecordKey &,Windows::ChangeTracking::SChangeRecordValue &>::`vftable'
0x18009210f  mov     [rsp+248h+var_C8], rdx
0x180092117  lea     rdx, [rsp+248h+var_1F8]
0x18009211c  mov     [rsp+248h+var_C0], rdx
0x180092124  lea     rdx, [rsp+248h+var_100]
0x18009212c  mov     [rsp+248h+var_B8], rdx
0x180092134  lea     rdx, [rsp+248h+var_1A0]
0x18009213c  mov     [rsp+248h+var_B0], rdx
0x180092144  mov     r8, [rsp+248h+var_210]
0x180092149  mov     [rsp+248h+var_A8], r8
0x180092151  lea     rdx, [rsp+248h+var_217]
0x180092156  mov     [rsp+248h+var_A0], rdx
0x18009215e  mov     [rsp+248h+var_98], r13
0x180092166  lea     rdx, [rsp+248h+var_C8]
0x18009216e  mov     [rsp+248h+var_90], rdx
0x180092176  lea     r9, [rsp+248h+var_C8]
0x18009217e  lea     r8, [rsp+248h+var_178]
0x180092186  lea     rdx, [rsp+248h+var_1B8]
0x18009218e  mov     rax, [rax+58h]
0x180092192  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092197  nop
0x180092198  mov     rcx, [rsp+248h+var_90]
0x1800921a0  test    rcx, rcx
0x1800921a3  jz      short loc_1800921C0
0x1800921a5  mov     rax, [rcx]
0x1800921a8  lea     rdx, [rsp+248h+var_C8]
0x1800921b0  cmp     rcx, rdx
0x1800921b3  setnz   dl
0x1800921b6  mov     rax, [rax+20h]
0x1800921ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800921bf  nop
0x1800921c0  lea     rcx, [rsp+248h+var_E8]; this
0x1800921c8  call    ??1CStoreTransaction@ChangeTracking@Windows@@QEAA@XZ; Windows::ChangeTracking::CStoreTransaction::~CStoreTransaction(void)
0x1800921cd  lea     rcx, [rsp+248h+var_198]; this
0x1800921d5  call    ??1SyncLockExclusive@Details@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::Details::SyncLockExclusive::~SyncLockExclusive(void)
0x1800921da  test    byte ptr [r13+24h], 1
0x1800921df  jz      loc_1800923A4
0x1800921e5  mov     rdx, [rsp+248h+var_1A0]
0x1800921ed  lea     rcx, [rsp+248h+var_E8]
0x1800921f5  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800921fa  nop
0x1800921fb  mov     rdi, [rsp+248h+var_1F0]
0x180092200  sub     rdi, [rsp+248h+var_1F8]
0x180092205  sar     rdi, 4
0x180092209  mov     rsi, 0F0F0F0F0F0F0F0F1h
0x180092213  imul    rdi, rsi
0x180092217  mov     rax, rbx
0x18009221a  mov     [rsp+248h+var_208], rbx
0x18009221f  test    rdi, rdi
0x180092222  jz      loc_180092395
0x180092228  cmp     [r13+0C0h], bl
0x18009222f  jnz     loc_18009238B
0x180092235  imul    rsi, rax, 110h
0x18009223c  add     rsi, [rsp+248h+var_1F8]
0x180092241  test    dword ptr [rsi+38h], 2000h
0x180092248  jz      loc_180092375
0x18009224e  test    byte ptr [rsi+3Ch], 10h
0x180092252  jz      loc_180092375
0x180092258  cmp     [rsi+0A8h], rbx
0x18009225f  jnz     loc_180092375
0x180092265  lea     r9, [rsi+78h]
0x180092269  cmp     qword ptr [r9+18h], 7
0x18009226e  jbe     short loc_180092273
0x180092270  mov     r9, [r9]
0x180092273  lea     r8, [rsp+248h+var_E8]
0x18009227b  cmp     [rsp+248h+var_D0], 7
0x180092284  cmova   r8, [rsp+248h+var_E8]
0x18009228d  lea     rdx, aExpandingSS; "EXPANDING: %s%s"
0x180092294  mov     rcx, [rsp+248h+var_210]; this
0x180092299  call    ?_LogMessage@CChangeMonitor@ChangeTracking@Windows@@AEAAXPEB_WZZ; Windows::ChangeTracking::CChangeMonitor::_LogMessage(wchar_t const *,...)
0x18009229e  lea     rcx, [rsp+248h+var_1B8]; void *
0x1800922a6  call    ??0?$vector@Uunique_ptr_bytes_buffer@@V?$allocator@Uunique_ptr_bytes_buffer@@@std@@@std@@QEAA@XZ; std::vector<unique_ptr_bytes_buffer>::vector<unique_ptr_bytes_buffer>(void)
0x1800922ab  nop
0x1800922ac  lea     rax, [rsp+248h+var_1B8]
0x1800922b4  mov     [rsp+248h+var_220], rax
0x1800922b9  lea     rax, [rsp+248h+var_1F8]
0x1800922be  mov     [rsp+248h+var_228], rax
0x1800922c3  mov     r9, [rsp+248h+var_208]
0x1800922c8  mov     r8, rsi
0x1800922cb  lea     rdx, [rsp+248h+var_E8]
0x1800922d3  call    ?_ExpandDirectoryChanges@CChangeMonitor@ChangeTracking@Windows@@AEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBUSWalkRecord@23@_KAEAV?$vector@USWalkRecord@ChangeTracking@Windows@@V?$allocator@USWalkRecord@ChangeTracking@Windows@@@std@@@5@3@Z; Windows::ChangeTracking::CChangeMonitor::_ExpandDirectoryChanges(std::wstring const &,Windows::ChangeTracking::SWalkRecord const &,unsigned __int64,std::vector<Windows::ChangeTracking::SWalkRecord> &,std::vector<Windows::ChangeTracking::SWalkRecord> &)
0x1800922d8  mov     rcx, [rsp+248h+var_1B8]; this
0x1800922e0  mov     rdx, [rsp+248h+var_1B0]
0x1800922e8  cmp     rcx, rdx
0x1800922eb  jz      short loc_18009233A
0x1800922ed  mov     [rsp+248h+var_228], rdx
0x1800922f2  mov     r9, rcx
0x1800922f5  mov     r8, [rsp+248h+var_1F0]
0x1800922fa  lea     rdx, [rsp+248h+var_178]
0x180092302  lea     rcx, [rsp+248h+var_1F8]
  ... truncated ...
```
