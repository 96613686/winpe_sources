# win_musl::consumption::ZipConsumptionContext::AddFile_win_scope::scope_win_musl::consumption::_anonymous_namespace_::ZipFileSender___win_scope::const_policies_win_scope::com_policies_____

- ea: `0x18000e504`
- end: `0x18000ef20`
- name: `win_musl::consumption::ZipConsumptionContext::AddFile_win_scope::scope_win_musl::consumption::_anonymous_namespace_::ZipFileSender___win_scope::const_policies_win_scope::com_policies_____`
- size: `2588`
- prototype: ``
- caller_count: `1`
- callee_count: `25`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18001f158`

## callees

- `0x18000531c`
- `0x18000df04`
- `0x18000e038`
- `0x18000e200`
- `0x18000e504`
- `0x18000ef28`
- `0x18000f188`
- `0x18000f9a0`
- `0x180011b14`
- `0x180012468`
- `0x18001d3c0`
- `0x18001f50c`
- `0x180021eb8`
- `0x180024acc`
- `0x18002db70`
- `0x1800311d4`
- `0x180074dc4`
- `0x180099e0c`
- `0x1800cd1c4`
- `0x1800cd6fc`
- `0x1800cded0`
- `0x1800d6354`
- `0x1801178c6`
- `0x1801178f0`
- `0x18012a010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000e7a1`
- `msvcrt!memcpy_s` at `0x18000e91e`
- `msvcrt!memcpy_s` at `0x18000eae6`
- `msvcrt!memcpy_s` at `0x18000e7a1`
- `msvcrt!memcpy_s` at `0x18000e91e`
- `msvcrt!memcpy_s` at `0x18000eae6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e5a2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e5a2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ebf7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ebf7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e58f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e58f`

## pseudocode

```c
// Hidden C++ exception states: #wind=26
__int64 __fastcall win_musl::consumption::ZipConsumptionContext::AddFile_win_scope::scope_win_musl::consumption::_anonymous_namespace_::ZipFileSender___win_scope::const_policies_win_scope::com_policies_____(
        _QWORD *a1,
        __int64 *a2,
        volatile signed __int32 **a3,
        _QWORD *a4)
{
  __int64 v7; // rbx
  bool v8; // dl
  int v9; // ecx
  win_dox *v10; // rcx
  volatile signed __int32 *v11; // r8
  unsigned int v12; // r10d
  unsigned __int8 v13; // cl
  int v14; // edx
  volatile signed __int32 *v15; // r9
  volatile signed __int32 *v16; // rcx
  win_scope::counted_strong_weak_base *v17; // rdx
  __int64 *v18; // r14
  __int64 *v19; // rdi
  __int64 *v20; // rsi
  size_t v21; // r12
  const void *v22; // rdx
  size_t v23; // r8
  _QWORD *v24; // rcx
  int v25; // eax
  volatile signed __int32 **v26; // r12
  volatile signed __int32 *v27; // rcx
  win_scope::counted_strong_weak_base *v28; // rdx
  rsize_t v29; // r14
  rsize_t v30; // rdx
  rsize_t v31; // rdi
  rsize_t v32; // rsi
  _QWORD *v33; // r8
  void **v34; // rcx
  void **v35; // rax
  __int64 v36; // rcx
  __int64 v37; // rdx
  rsize_t v38; // rdx
  rsize_t v39; // rdi
  void **v40; // r8
  void **v41; // rcx
  void **v42; // rax
  __int64 v43; // rdx
  __int64 v44; // r8
  volatile signed __int32 *v45; // rcx
  win_scope::counted_strong_weak_base *v46; // rdx
  _QWORD *v47; // rcx
  _QWORD *v48; // rdi
  __int128 v49; // xmm6
  __int128 v50; // xmm7
  __int128 v51; // xmm8
  __int128 v52; // xmm9
  __int64 v53; // xmm10_8
  _QWORD *v54; // rdi
  void **v55; // rcx
  void **v56; // rax
  _QWORD *v57; // rcx
  _QWORD *v58; // rdi
  _QWORD *v59; // rax
  _QWORD *v60; // rdi
  win_scope::counted_strong_weak_base *v61; // rcx
  __int64 v62; // rax
  void **v63; // rdx
  signed int v64; // esi
  __int64 result; // rax
  _QWORD *v67; // rbx
  __int64 v68; // rcx
  _QWORD *v69; // rax
  int v70; // eax
  __int64 v71; // r9
  _QWORD *v72; // [rsp+48h] [rbp-C0h] BYREF
  win_scope::counted_strong_weak_base *v73[2]; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v74; // [rsp+60h] [rbp-A8h]
  _QWORD *v75; // [rsp+68h] [rbp-A0h] BYREF
  volatile signed __int32 **v76; // [rsp+70h] [rbp-98h]
  __int64 v77; // [rsp+78h] [rbp-90h] BYREF
  void *Destination[2]; // [rsp+80h] [rbp-88h] BYREF
  rsize_t v79; // [rsp+90h] [rbp-78h]
  unsigned __int64 v80; // [rsp+98h] [rbp-70h]
  win_scope::counted_strong_weak_base **v81; // [rsp+A0h] [rbp-68h] BYREF
  win_scope::counted_strong_weak_base **v82; // [rsp+A8h] [rbp-60h] BYREF
  _QWORD *v83; // [rsp+B8h] [rbp-50h]
  _QWORD *v84; // [rsp+C0h] [rbp-48h] BYREF
  __int64 v85; // [rsp+C8h] [rbp-40h]
  __int64 v86; // [rsp+D0h] [rbp-38h]
  _QWORD *v87; // [rsp+D8h] [rbp-30h]
  volatile signed __int32 **v88; // [rsp+E0h] [rbp-28h]
  _QWORD *v89; // [rsp+E8h] [rbp-20h]
  char v90[8]; // [rsp+F0h] [rbp-18h] BYREF
  void *v91[2]; // [rsp+F8h] [rbp-10h] BYREF
  rsize_t v92; // [rsp+108h] [rbp+0h]
  unsigned __int64 v93; // [rsp+110h] [rbp+8h]
  char v94[8]; // [rsp+118h] [rbp+10h] BYREF
  void *Block[2]; // [rsp+120h] [rbp+18h] BYREF
  rsize_t v96; // [rsp+130h] [rbp+28h]
  unsigned __int64 v97; // [rsp+138h] [rbp+30h]
  __int128 v98; // [rsp+140h] [rbp+38h] BYREF
  void *Source[2]; // [rsp+158h] [rbp+50h] BYREF
  __int128 v100; // [rsp+168h] [rbp+60h]
  __m256i v101; // [rsp+178h] [rbp+70h] BYREF
  __int64 v102; // [rsp+198h] [rbp+90h]
  _BYTE pExceptionObject[160]; // [rsp+1A8h] [rbp+A0h] BYREF
  wchar_t v104[512]; // [rsp+248h] [rbp+140h] BYREF

  v86 = -2;
  v83 = a4;
  v76 = a3;
  v87 = a1;
  v88 = a3;
  v89 = a4;
  LODWORD(v74) = 0;
  v7 = a1[1] + 40LL;
  v85 = v7;
  EnterCriticalSection((LPCRITICAL_SECTION)v7);
  v9 = *(_DWORD *)(v7 + 44);
  *(_DWORD *)(v7 + 44) = v9 + 1;
  if ( !v9 )
    *(_DWORD *)(v7 + 40) = GetCurrentThreadId();
  v10 = (win_dox *)a1[1];
  LOBYTE(v10) = *((_BYTE *)v10 + 96);
  win_dox::ThrowIfFailed(v10, v8);
  v11 = a3[1];
  v75 = v11 + 54;
  v12 = 1;
  if ( *((_DWORD *)v11 + 102) )
  {
    v13 = *((_BYTE *)v11 + 420);
    v14 = v13 != 11 ? 2 : 0;
    if ( v13 <= 0x14u )
    {
      v68 = *((_QWORD *)v11 + 31);
      if ( v68 )
      {
        v69 = v11 + 58;
        if ( *((_QWORD *)v11 + 32) >= 0x10u )
          v69 = (_QWORD *)*v69;
        if ( *((_BYTE *)v69 + v68 - 1) == 47 )
          v14 = 1;
      }
    }
    *((_DWORD *)v11 + 84) = v14;
  }
  else
  {
    v75 = v11 + 2;
    if ( !*((_DWORD *)v11 + 50) )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x1B1u,
        0x8000FFFF,
        (struct win_musl::TStringEllipseBase *)L"Can't add file without header.");
      throw (SplException::THResultException *)pExceptionObject;
    }
  }
  v15 = a3[1];
  if ( *((_DWORD *)v15 + 50) )
  {
    v70 = win_musl::consumption::ZipFileContext::DetermineDesignation(v15 + 2);
    *(_DWORD *)(v71 + 128) = v70;
  }
  *(_OWORD *)v73 = 0;
  v16 = *a3;
  if ( *a3 )
  {
    v17 = (win_scope::counted_strong_weak_base *)a3[1];
    if ( v12 + _InterlockedExchangeAdd(v16 + 2, v12) == v12 )
      _InterlockedAdd(v16 + 3, v12);
    v73[0] = (win_scope::counted_strong_weak_base *)v16;
    v73[1] = v17;
  }
  win_musl::consumption::ZipFileContext::TestValidity(v73);
  v72 = (_QWORD *)a1[1];
  v18 = (__int64 *)v72[3];
  v19 = (__int64 *)v18[1];
  v20 = v18;
  if ( *((_BYTE *)v19 + 81) )
  {
LABEL_27:
    v20 = (__int64 *)v72[3];
    goto LABEL_28;
  }
  v21 = a2[3];
  do
  {
    if ( (unsigned __int64)a2[4] < 0x10 )
      v22 = a2 + 1;
    else
      v22 = (const void *)a2[1];
    v23 = v21;
    if ( v19[6] < v21 )
      v23 = v19[6];
    v24 = v19 + 4;
    if ( (unsigned __int64)v19[7] >= 0x10 )
      v24 = (_QWORD *)*v24;
    v25 = memcmp_0(v24, v22, v23);
    if ( v25 )
    {
      if ( v25 < 0 )
        goto LABEL_22;
    }
    else if ( v19[6] < v21 )
    {
LABEL_22:
      v19 = (__int64 *)v19[2];
      continue;
    }
    v20 = v19;
    v19 = (__int64 *)*v19;
  }
  while ( !*((_BYTE *)v19 + 81) );
  v7 = v85;
  if ( v20 == v18 || (int)std::string::compare(a2, v20 + 3) < 0 )
    goto LABEL_27;
LABEL_28:
  v72 = (_QWORD *)(a1[1] + 16LL);
  v26 = v76;
  if ( v20 == (__int64 *)v72[1] )
  {
    v82 = v73;
    *(_OWORD *)v73 = 0;
    v27 = *v76;
    if ( *v76 )
    {
      v28 = (win_scope::counted_strong_weak_base *)v76[1];
      if ( _InterlockedIncrement(v27 + 2) == 1 )
        _InterlockedAdd(v27 + 3, 1u);
      v73[0] = (win_scope::counted_strong_weak_base *)v27;
      v73[1] = v28;
    }
    v81 = v73;
    v29 = 15;
    v30 = 15;
    v80 = 15;
    v79 = 0;
    LOBYTE(Destination[0]) = 0;
    v31 = a2[3];
    v32 = -1;
    if ( &v77 == a2 )
    {
      std::string::erase(&v77, a2[3], -1);
      std::string::erase(&v77, 0, 0);
    }
    else
    {
      if ( v31 == -1 )
        std::_String_base::_Xlen();
      if ( v31 > 0xF )
      {
        std::string::_Copy(&v77, v31, 0);
        v30 = v80;
LABEL_37:
        v33 = a2 + 1;
        if ( (unsigned __int64)a2[4] >= 0x10 )
          v33 = (_QWORD *)*v33;
        v34 = Destination;
        if ( v30 >= 0x10 )
          v34 = (void **)Destination[0];
        memcpy_s(v34, v30, v33, v31);
        v35 = Destination;
        if ( v80 >= 0x10 )
          v35 = (void **)Destination[0];
        v79 = v31;
        *((_BYTE *)v35 + v31) = 0;
      }
      else
      {
        if ( v31 )
          goto LABEL_37;
        v79 = 0;
        LOBYTE(Destination[0]) = 0;
      }
    }
    v82 = (win_scope::counted_strong_weak_base **)&v77;
    std::string::string(Source, &v77);
    *(_OWORD *)&v101.m256i_u64[1] = 0;
    if ( v73[0] )
    {
      win_scope::counted_strong_weak_base::AddRef(v73[0]);
      v101.m256i_i64[1] = v36;
      v101.m256i_i64[2] = v37;
    }
    LODWORD(v74) = 1;
    if ( v80 >= 0x10 )
      operator delete(Destination[0]);
    v80 = 15;
    v79 = 0;
    LOBYTE(Destination[0]) = 0;
    win_scope::detail::scope_helper<win_musl::consumption::ZipFileContext *,win_scope::const_policies<win_scope::shared_policies>>::destruct<win_musl::consumption::ZipFileContext *,win_scope::const_policies<win_scope::shared_policies>>(v73);
    v38 = 15;
    v97 = 15;
    v96 = 0;
    LOBYTE(Block[0]) = 0;
    v39 = *((_QWORD *)&v100 + 1);
    if ( *((_QWORD *)&v100 + 1) == -1 )
      std::_String_base::_Xlen();
    if ( *((_QWORD *)&v100 + 1) > 0xFu )
    {
      std::string::_Copy(v94, *((_QWORD *)&v100 + 1), 0);
      v38 = v97;
      if ( v39 )
      {
LABEL_57:
        v40 = &Source[1];
        if ( v101.m256i_i64[0] >= 0x10uLL )
          v40 = (void **)Source[1];
        v41 = Block;
        if ( v38 >= 0x10 )
          v41 = (void **)Block[0];
        memcpy_s(v41, v38, v40, v39);
        v42 = Block;
        if ( v97 >= 0x10 )
          v42 = (void **)Block[0];
        v96 = v39;
        *((_BYTE *)v42 + v39) = 0;
      }
    }
    else
    {
      if ( *((_QWORD *)&v100 + 1) )
        goto LABEL_57;
      v96 = 0;
      LOBYTE(Block[0]) = 0;
    }
    v98 = 0;
    v43 = v101.m256i_i64[1];
    if ( v101.m256i_i64[1] )
    {
      v44 = v101.m256i_i64[2];
      if ( _InterlockedIncrement((volatile signed __int32 *)(v101.m256i_i64[1] + 8)) == 1 )
        _InterlockedAdd((volatile signed __int32 *)(v43 + 12), 1u);
      *(_QWORD *)&v98 = v43;
      *((_QWORD *)&v98 + 1) = v44;
    }
    std::_Tree<std::_Tmap_traits<std::string,win_scope::scope<win_musl::consumption::ZipFileContext *,win_scope::const_policies<win_scope::shared_policies>>,std::less<std::string>,std::allocator<std::pair<std::string const,win_scope::scope<win_musl::consumption::ZipFileContext *,win_scope::const_policies<win_scope::shared_policies>>>>,0>>::insert(
      v72,
      &v82,
      v94);
    win_scope::detail::scope_helper<win_musl::consumption::ZipFileContext *,win_scope::const_policies<win_scope::shared_policies>>::destruct<win_musl::consumption::ZipFileContext *,win_scope::const_policies<win_scope::shared_policies>>(&v98);
    if ( v97 >= 0x10 )
      operator delete(Block[0]);
    v97 = 15;
    v96 = 0;
    LOBYTE(Block[0]) = 0;
    win_scope::detail::scope_helper<win_musl::consumption::ZipFileContext *,win_scope::const_policies<win_scope::shared_policies>>::destruct<win_musl::consumption::ZipFileContext *,win_scope::const_policies<win_scope::shared_policies>>(&v101.m256i_u64[1]);
    if ( v101.m256i_i64[0] >= 0x10uLL )
      operator delete(Source[1]);
    *(_OWORD *)v73 = 0;
    v45 = *v26;
    if ( *v26 )
    {
      v46 = (win_scope::counted_strong_weak_base *)v26[1];
      if ( _InterlockedIncrement(v45 + 2) == 1 )
        _InterlockedAdd(v45 + 3, 1u);
      v73[0] = (win_scope::counted_strong_weak_base *)v45;
      v73[1] = v46;
    }
    win_musl::consumption::ZipFileContext::AdvanceState(v73, 5);
    v82 = *(win_scope::counted_strong_weak_base ***)(a1[1] + 8LL);
    v81 = (win_scope::counted_strong_weak_base **)&v72;
    v47 = 0;
    v72 = 0;
    v48 = (_QWORD *)*v83;
    if ( *v83 )
    {
      (*(void (__fastcall **)(_QWORD))(*v48 + 8LL))(*v83);
      v47 = v72;
    }
    v72 = v48;
    if ( v47 )
      (*(void (__fastcall **)(_QWORD *))(*v47 + 16LL))(v47);
    v73[0] = (win_scope::counted_strong_weak_base *)&v72;
    v49 = *((_OWORD *)v75 + 8);
    v50 = *((_OWORD *)v75 + 9);
    v51 = *((_OWORD *)v75 + 10);
    v52 = *((_OWORD *)v75 + 11);
    v53 = v75[24];
    LODWORD(v74) = *((_DWORD *)v75 + 30);
    v54 = a2 + 1;
    if ( (unsigned __int64)a2[4] >= 0x10 )
      v54 = (_QWORD *)*v54;
    v93 = 15;
    v92 = 0;
    LOBYTE(v91[0]) = 0;
    do
      ++v32;
    while ( *((_BYTE *)v54 + v32) );
    if ( v32 == -1 )
      std::_String_base::_Xlen();
    if ( v32 > 0xF )
    {
      std::string::_Copy(v90, v32, 0);
      v29 = v93;
LABEL_87:
      v55 = v91;
      if ( v29 >= 0x10 )
        v55 = (void **)v91[0];
      memcpy_s(v55, v29, v54, v32);
      v56 = v91;
      if ( v93 >= 0x10 )
        v56 = (void **)v91[0];
      v92 = v32;
      *((_BYTE *)v56 + v32) = 0;
    }
    else
    {
      if ( v32 )
        goto LABEL_87;
      v92 = 0;
      LOBYTE(v91[0]) = 0;
    }
    v76 = 0;
    v57 = 0;
    v75 = 0;
    v58 = v72;
    if ( v72 )
    {
      (*(void (__fastcall **)(_QWORD *))(*v72 + 8LL))(v72);
      v57 = v75;
    }
    else
    {
      v58 = 0;
    }
    v75 = v58;
    if ( v57 )
      (*(void (__fastcall **)(_QWORD *))(*v57 + 16LL))(v57);
    v59 = (_QWORD *)win_musl::UnknownOnly_win_musl::detail::SendCom_win_scope::scope_win_musl::consumption::_anonymous_namespace_::ZipFileSender___win_scope::const_policies_win_scope::com_policies____IWin7ZipFileSender_win_musl::ZipFileReceiver_win_mp_lib::type_list_IWin7ZipFileSender_win_mp_lib::null_type__win_musl::InnerCom_win_scope::scope_win_musl::consumption::_anonymous_namespace_::ZipFileSender___win_scope::const_policies_win_scope::com_policies____IWin7ZipFileSender_win_scope::report_policy_throw____win_mp_lib::type_list_IWin7ZipFileSender_win_mp_lib::null_type__win_mp_lib::null_type_::CreateInstance_win_scope::scope_win_musl::consumption::_anonymous_namespace_::ZipFileSender___win_scope::const_policies_win_scope::com_policies_____(
                      &v81,
                      &v75);
    v76 = 0;
    win_musl::com_object_cast_win_scope::scope_IWin7ZipFileSender___win_scope::const_policies_win_scope::com_policies____win_musl::detail::SendCom_win_scope::scope_win_musl::consumption::_anonymous_namespace_::ZipFileSender___win_scope::const_policies_win_scope::com_policies____IWin7ZipFileSender_win_musl::ZipFileReceiver_win_mp_lib::type_list_IWin7ZipFileSender_win_mp_lib::null_type__win_musl::InnerCom_win_scope::scope_win_musl::consumption::_anonymous_namespace_::ZipFileSender___win_scope::const_policies_win_scope::com_policies____IWin7ZipFileSender_win_scope::report_policy_throw____win_mp_lib::type_list_IWin7ZipFileSender_win_mp_lib::null_type__win_mp_lib::null_type_(
      &v84,
      *v59);
    v60 = v84;
    v76 = (volatile signed __int32 **)v84;
    if ( v81 )
      (*((void (__fastcall **)(win_scope::counted_strong_weak_base **))*v81 + 2))(v81);
    v61 = v82[2];
    v62 = *(_QWORD *)v61;
    v63 = v91;
    if ( v93 >= 0x10 )
      v63 = (void **)v91[0];
    *(_OWORD *)Source = v49;
    v100 = v50;
    *(_OWORD *)v101.m256i_i8 = v51;
    *(_OWORD *)&v101.m256i_u64[2] = v52;
    v102 = v53;
    v64 = (*(__int64 (__fastcall **)(win_scope::counted_strong_weak_base *, void **, _QWORD, void **, _QWORD *))(v62 + 56))(
            v61,
            v63,
            (unsigned int)v74,
            Source,
            v60);
    if ( v64 < 0 )
    {
      memset_0(v104, 0, sizeof(v104));
      StringCchPrintfW(v104, 0x200u, L"Call to AddFile failed with HResult 0x%X.", (unsigned int)v64);
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x3Du,
        v64,
        (struct win_musl::TStringEllipseBase *)v104);
      throw (SplException::THResultException *)pExceptionObject;
    }
    if ( v60 )
      (*(void (__fastcall **)(_QWORD *))(*v60 + 16LL))(v60);
    if ( v72 )
    {
      (*(void (__fastcall **)(_QWORD *))(*v72 + 16LL))(v72);
      v72 = 0;
    }
    if ( v93 >= 0x10 )
      operator delete(v91[0]);
  }
  if ( (*(_DWORD *)(v7 + 44))-- == 1 )
    *(_DWORD *)(v7 + 40) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)v7);
  if ( *a1 && a1[1] )
  {
    win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>((__int64)a1);
    *a1 = 0;
    a1[1] = 0;
  }
  result = win_scope::detail::scope_helper<win_musl::consumption::ZipFileContext *,win_scope::const_policies<win_scope::shared_policies>>::destruct<win_musl::consumption::ZipFileContext *,win_scope::const_policies<win_scope::shared_policies>>(v26);
  v67 = v83;
  if ( *v83 )
  {
    result = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v83 + 16LL))(*v83);
    *v67 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000e504  mov     rax, rsp
0x18000e507  push    rbp
0x18000e508  push    rbx
0x18000e509  push    rsi
0x18000e50a  push    rdi
0x18000e50b  push    r12
0x18000e50d  push    r13
0x18000e50f  push    r14
0x18000e511  push    r15
0x18000e513  lea     rbp, [rax-5E8h]
0x18000e51a  sub     rsp, 6A8h
0x18000e521  mov     [rbp+5E0h+var_618], 0FFFFFFFFFFFFFFFEh
0x18000e529  movaps  xmmword ptr [rax-58h], xmm6
0x18000e52d  movaps  xmmword ptr [rax-68h], xmm7
0x18000e531  movaps  xmmword ptr [rax-78h], xmm8
0x18000e536  movaps  xmmword ptr [rax-88h], xmm9
0x18000e53e  movaps  xmmword ptr [rax-98h], xmm10
0x18000e546  mov     rax, cs:__security_cookie
0x18000e54d  xor     rax, rsp
0x18000e550  mov     [rbp+5E0h+var_A0], rax
0x18000e557  mov     rax, r9
0x18000e55a  mov     [rbp+5E0h+var_630], rax
0x18000e55e  mov     rdi, r8
0x18000e561  mov     [rsp+6E0h+var_678], r8
0x18000e566  mov     r13, rdx
0x18000e569  mov     r15, rcx
0x18000e56c  mov     [rbp+5E0h+var_610], rcx
0x18000e570  mov     [rbp+5E0h+var_608], r8
0x18000e574  mov     [rbp+5E0h+var_600], rax
0x18000e578  xor     r12d, r12d
0x18000e57b  mov     dword ptr [rsp+6E0h+var_688], r12d
0x18000e580  mov     rbx, [rcx+8]
0x18000e584  add     rbx, 28h ; '('
0x18000e588  mov     [rbp+5E0h+var_620], rbx
0x18000e58c  mov     rcx, rbx; lpCriticalSection
0x18000e58f  call    cs:__imp_EnterCriticalSection
0x18000e595  mov     ecx, [rbx+2Ch]
0x18000e598  lea     eax, [rcx+1]
0x18000e59b  mov     [rbx+2Ch], eax
0x18000e59e  test    ecx, ecx
0x18000e5a0  jnz     short loc_18000E5AB
0x18000e5a2  call    cs:__imp_GetCurrentThreadId
0x18000e5a8  mov     [rbx+28h], eax
0x18000e5ab  mov     rcx, [r15+8]
0x18000e5af  mov     cl, [rcx+60h]; this
0x18000e5b2  call    ?ThrowIfFailed@win_dox@@YAX_N@Z; win_dox::ThrowIfFailed(bool)
0x18000e5b7  mov     r8, [rdi+8]
0x18000e5bb  lea     rax, [r8+0D8h]
0x18000e5c2  mov     [rsp+6E0h+var_680], rax
0x18000e5c7  mov     r10d, 1
0x18000e5cd  cmp     [rax+0C0h], r12d
0x18000e5d4  jz      loc_18000E7E6
0x18000e5da  mov     cl, [r8+1A4h]
0x18000e5e1  lea     eax, [rcx-0Bh]
0x18000e5e4  neg     al
0x18000e5e6  sbb     edx, edx
0x18000e5e8  and     edx, 2
0x18000e5eb  cmp     cl, 14h
0x18000e5ee  jbe     loc_18000ED56
0x18000e5f4  mov     [r8+150h], edx
0x18000e5fb  mov     r9, [rdi+8]
0x18000e5ff  lea     rcx, [r9+8]
0x18000e603  cmp     [rcx+0C0h], r12d
0x18000e60a  jnz     loc_18000EE21
0x18000e610  xorps   xmm0, xmm0
0x18000e613  movdqu  xmmword ptr [rsp+6E0h+var_6A0+8], xmm0
0x18000e619  mov     rcx, [rdi]
0x18000e61c  test    rcx, rcx
0x18000e61f  jz      short loc_18000E643
0x18000e621  mov     rdx, [rdi+8]
0x18000e625  mov     eax, r10d
0x18000e628  lock xadd [rcx+8], eax
0x18000e62d  add     eax, r10d
0x18000e630  cmp     eax, r10d
0x18000e633  jz      loc_18000EC7C
0x18000e639  mov     [rsp+6E0h+var_6A0+8], rcx
0x18000e63e  mov     qword ptr [rsp+6E0h+var_690], rdx
0x18000e643  lea     rcx, [rsp+6E0h+var_6A0+8]
0x18000e648  call    ?TestValidity@ZipFileContext@consumption@win_musl@@SAXV?$scope@PEAUZipFileContext@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@Z; win_musl::consumption::ZipFileContext::TestValidity(win_scope::scope<win_musl::consumption::ZipFileContext *,win_scope::const_policies<win_scope::shared_policies>>)
0x18000e64d  mov     rdi, [r15+8]
0x18000e651  mov     [rsp+6E0h+var_6A0], rdi
0x18000e656  mov     r14, [rdi+18h]
0x18000e65a  mov     rdi, [r14+8]
0x18000e65e  mov     rsi, r14
0x18000e661  cmp     [rdi+51h], r12b
0x18000e665  jnz     short loc_18000E6C4
0x18000e667  mov     r12, [r13+18h]
0x18000e66b  cmp     qword ptr [r13+20h], 10h
0x18000e670  jb      loc_18000E7C4
0x18000e676  mov     rdx, [r13+8]; Buf2
0x18000e67a  mov     r8, r12
0x18000e67d  cmp     [rdi+30h], r12
0x18000e681  cmovb   r8, [rdi+30h]; Size
0x18000e686  lea     rcx, [rdi+20h]
0x18000e68a  cmp     qword ptr [rdi+38h], 10h
0x18000e68f  jb      short loc_18000E694
0x18000e691  mov     rcx, [rcx]; Buf1
0x18000e694  call    memcmp_0
0x18000e699  test    eax, eax
0x18000e69b  jz      short loc_18000E6A5
0x18000e69d  jns     short loc_18000E6AB
0x18000e69f  mov     rdi, [rdi+10h]
0x18000e6a3  jmp     short loc_18000E6B1
0x18000e6a5  cmp     [rdi+30h], r12
0x18000e6a9  jb      short loc_18000E69F
0x18000e6ab  mov     rsi, rdi
0x18000e6ae  mov     rdi, [rdi]
0x18000e6b1  cmp     byte ptr [rdi+51h], 0
0x18000e6b5  jz      short loc_18000E66B
0x18000e6b7  cmp     rsi, r14
0x18000e6ba  mov     rbx, [rbp+5E0h+var_620]
0x18000e6be  jnz     loc_18000E7CD
0x18000e6c4  mov     rsi, [rsp+6E0h+var_6A0]
0x18000e6c9  mov     rsi, [rsi+18h]
0x18000e6cd  mov     rax, [r15+8]
0x18000e6d1  add     rax, 10h
0x18000e6d5  mov     [rsp+6E0h+var_6A0], rax
0x18000e6da  mov     r12, [rsp+6E0h+var_678]
0x18000e6df  cmp     rsi, [rax+8]
0x18000e6e3  jnz     loc_18000ED88
0x18000e6e9  lea     rax, [rsp+6E0h+var_6A0+8]
0x18000e6ee  mov     [rbp+5E0h+var_640], rax
0x18000e6f2  xorps   xmm0, xmm0
0x18000e6f5  movdqu  xmmword ptr [rsp+6E0h+var_6A0+8], xmm0
0x18000e6fb  mov     rcx, [r12]
0x18000e6ff  test    rcx, rcx
0x18000e702  jz      short loc_18000E72D
0x18000e704  mov     rdx, [r12+8]
0x18000e709  mov     r8d, 1
0x18000e70f  mov     eax, r8d
0x18000e712  lock xadd [rcx+8], eax
0x18000e717  add     eax, r8d
0x18000e71a  cmp     eax, r8d
0x18000e71d  jz      loc_18000ECCF
0x18000e723  mov     [rsp+6E0h+var_6A0+8], rcx
0x18000e728  mov     qword ptr [rsp+6E0h+var_690], rdx
0x18000e72d  lea     rax, [rsp+6E0h+var_6A0+8]
0x18000e732  mov     [rbp+5E0h+var_648], rax
0x18000e736  mov     r14d, 0Fh
0x18000e73c  mov     edx, r14d; DestinationSize
0x18000e73f  mov     [rbp+5E0h+var_650], rdx
0x18000e743  xor     r8d, r8d
0x18000e746  mov     [rbp+5E0h+var_658], r8
0x18000e74a  mov     byte ptr [rsp+6E0h+Destination], r8b
0x18000e74f  mov     rdi, [r13+18h]
0x18000e753  lea     rax, [rsp+6E0h+var_670]
0x18000e758  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000e75c  cmp     rax, r13
0x18000e75f  jz      loc_18000EE32
0x18000e765  cmp     rdi, 0FFFFFFFFFFFFFFFEh
0x18000e769  ja      loc_18000EE56
0x18000e76f  cmp     rdx, rdi
0x18000e772  jb      loc_18000E846
0x18000e778  test    rdi, rdi
0x18000e77b  jz      loc_18000EDCC
0x18000e781  lea     r8, [r13+8]
0x18000e785  cmp     qword ptr [r13+20h], 10h
0x18000e78a  jb      short loc_18000E78F
0x18000e78c  mov     r8, [r8]; Source
0x18000e78f  lea     rcx, [rsp+6E0h+Destination]
0x18000e794  cmp     rdx, 10h
0x18000e798  cmovnb  rcx, [rsp+6E0h+Destination]; Destination
0x18000e79e  mov     r9, rdi; SourceSize
0x18000e7a1  call    cs:__imp_memcpy_s
0x18000e7a7  lea     rax, [rsp+6E0h+Destination]
0x18000e7ac  cmp     [rbp+5E0h+var_650], 10h
0x18000e7b1  cmovnb  rax, [rsp+6E0h+Destination]
0x18000e7b7  mov     [rbp+5E0h+var_658], rdi
0x18000e7bb  mov     byte ptr [rdi+rax], 0
0x18000e7bf  jmp     loc_18000E860
0x18000e7c4  lea     rdx, [r13+8]
0x18000e7c8  jmp     loc_18000E67A
0x18000e7cd  lea     rdx, [rsi+18h]
0x18000e7d1  mov     rcx, r13
0x18000e7d4  call    ?compare@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@QEBAHAEBV12@@Z; std::string::compare(std::string const &)
0x18000e7d9  test    eax, eax
0x18000e7db  jns     loc_18000E6CD
0x18000e7e1  jmp     loc_18000E6C4
0x18000e7e6  lea     rax, [r8+8]
0x18000e7ea  mov     [rsp+6E0h+var_680], rax
0x18000e7ef  cmp     [rax+0C0h], r12d
0x18000e7f6  jnz     loc_18000E5FB
0x18000e7fc  lea     rax, aCanTAddFileWit; "Can't add file without header."
0x18000e803  mov     [rsp+6E0h+var_6B0], rax; struct win_musl::TStringEllipseBase *
0x18000e808  mov     [rsp+6E0h+var_6B8], 8000FFFFh; unsigned int
0x18000e810  mov     [rsp+6E0h+var_6C0], 1B1h; unsigned int
0x18000e818  lea     r9, word_180139126
0x18000e81f  lea     r8, aNoFilename; "(no filename)"
0x18000e826  lea     rcx, [rbp+5E0h+pExceptionObject]; this
0x18000e82d  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18000e832  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18000e839  lea     rcx, [rbp+5E0h+pExceptionObject]; pExceptionObject
0x18000e840  call    _CxxThrowException_0
0x18000e846  mov     rdx, rdi
0x18000e849  lea     rcx, [rsp+6E0h+var_670]
0x18000e84e  call    ?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@IEAAX_K0@Z; std::string::_Copy(unsigned __int64,unsigned __int64)
0x18000e853  mov     rdx, [rbp+5E0h+var_650]
0x18000e857  test    rdi, rdi
0x18000e85a  jnz     loc_18000E781
0x18000e860  lea     rax, [rsp+6E0h+var_670]
0x18000e865  mov     [rbp+5E0h+var_640], rax
0x18000e869  lea     rdx, [rsp+6E0h+var_670]
0x18000e86e  lea     rcx, [rbp+5E0h+Source]
0x18000e872  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x18000e877  nop
0x18000e878  xorps   xmm0, xmm0
0x18000e87b  movdqu  [rbp+5E0h+var_570+8], xmm0
0x18000e880  mov     rcx, [rsp+6E0h+var_6A0+8]; this
0x18000e885  test    rcx, rcx
0x18000e888  jz      short loc_18000E89F
0x18000e88a  mov     rdx, qword ptr [rsp+6E0h+var_690]
0x18000e88f  call    ?AddRef@counted_strong_weak_base@win_scope@@QEAAKXZ; win_scope::counted_strong_weak_base::AddRef(void)
0x18000e894  mov     qword ptr [rbp+5E0h+var_570+8], rcx
0x18000e898  mov     qword ptr [rbp+5E0h+var_560], rdx
0x18000e89f  mov     dword ptr [rsp+6E0h+var_688], 1
0x18000e8a7  cmp     [rbp+5E0h+var_650], 10h
0x18000e8ac  jnb     loc_18000ED1D
0x18000e8b2  mov     [rbp+5E0h+var_650], r14
0x18000e8b6  mov     [rbp+5E0h+var_658], 0
0x18000e8be  mov     byte ptr [rsp+6E0h+Destination], 0
0x18000e8c3  lea     rcx, [rsp+6E0h+var_6A0+8]
0x18000e8c8  call    ??$destruct@PEAUZipFileContext@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@?$scope_helper@PEAUZipFileContext@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@detail@win_scope@@SAXPEAV?$scope@PEAUZipFileContext@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@2@@Z; win_scope::detail::scope_helper<win_musl::consumption::ZipFileContext *,win_scope::const_policies<win_scope::shared_policies>>::destruct<win_musl::consumption::ZipFileContext *,win_scope::const_policies<win_scope::shared_policies>>(win_scope::scope<win_musl::consumption::ZipFileContext *,win_scope::const_policies<win_scope::shared_policies>> *)
0x18000e8cd  nop
0x18000e8ce  mov     rdx, r14; DestinationSize
0x18000e8d1  mov     [rbp+5E0h+var_5B0], rdx
0x18000e8d5  xor     r8d, r8d
0x18000e8d8  mov     [rbp+5E0h+var_5B8], r8
0x18000e8dc  mov     byte ptr [rbp+5E0h+Block], r8b
0x18000e8e0  mov     rdi, [rbp+5E0h+SourceSize]
0x18000e8e4  cmp     rdi, 0FFFFFFFFFFFFFFFEh
0x18000e8e8  ja      loc_18000EE68
0x18000e8ee  cmp     rdx, rdi
0x18000e8f1  jb      loc_18000ED90
0x18000e8f7  test    rdi, rdi
0x18000e8fa  jz      loc_18000EDEB
0x18000e900  lea     r8, [rbp+5E0h+Source+8]
0x18000e904  cmp     qword ptr [rbp+5E0h+var_570], 10h
0x18000e909  cmovnb  r8, [rbp+5E0h+Source+8]; Source
0x18000e90e  lea     rcx, [rbp+5E0h+Block]
0x18000e912  cmp     rdx, 10h
0x18000e916  cmovnb  rcx, [rbp+5E0h+Block]; Destination
0x18000e91b  mov     r9, rdi; SourceSize
0x18000e91e  call    cs:__imp_memcpy_s
0x18000e924  lea     rax, [rbp+5E0h+Block]
0x18000e928  cmp     [rbp+5E0h+var_5B0], 10h
0x18000e92d  cmovnb  rax, [rbp+5E0h+Block]
0x18000e932  mov     [rbp+5E0h+var_5B8], rdi
0x18000e936  mov     byte ptr [rax+rdi], 0
0x18000e93a  xorps   xmm0, xmm0
0x18000e93d  movdqu  [rbp+5E0h+var_5A8], xmm0
0x18000e942  mov     rdx, qword ptr [rbp+5E0h+var_570+8]
0x18000e946  mov     edi, 1
0x18000e94b  test    rdx, rdx
0x18000e94e  jz      short loc_18000E970
0x18000e950  mov     r8, qword ptr [rbp+5E0h+var_560]
0x18000e957  mov     eax, edi
0x18000e959  lock xadd [rdx+8], eax
0x18000e95e  add     eax, edi
0x18000e960  cmp     eax, edi
0x18000e962  jz      loc_18000ECD9
0x18000e968  mov     qword ptr [rbp+5E0h+var_5A8], rdx
0x18000e96c  mov     qword ptr [rbp+5E0h+var_5A8+8], r8
0x18000e970  lea     r8, [rbp+5E0h+var_5D0]
0x18000e974  lea     rdx, [rbp+5E0h+var_640]
0x18000e978  mov     rcx, [rsp+6E0h+var_6A0]
0x18000e97d  call    ?insert@?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@V?$scope@PEAUZipFileContext@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@V?$scope@PEAUZipFileContext@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@Viterator@?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@V?$scope@PEAUZipFileContext@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@V?$scope@PEAUZipFileContext@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@std@@@2@$0A@@std@@@std@@_N@2@AEBU?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@V?$scope@PEAUZipFileContext@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@2@@Z; std::_Tree<std::_Tmap_traits<std::string,win_scope::scope<win_musl::consumption::ZipFileContext *,win_scope::const_policies<win_scope::shared_policies>>,std::less<std::string>,std::allocator<std::pair<std::string const,win_scope::scope<win_musl::consumption::ZipFileContext *,win_scope::const_policies<win_scope::shared_policies>>>>,0>>::insert(std::pair<std::string const,win_scope::scope<win_musl::consumption::ZipFileContext *,win_scope::const_policies<win_scope::shared_policies>>> const &)
0x18000e982  nop
0x18000e983  lea     rcx, [rbp+5E0h+var_5A8]
0x18000e987  call    ??$destruct@PEAUZipFileContext@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@?$scope_helper@PEAUZipFileContext@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@detail@win_scope@@SAXPEAV?$scope@PEAUZipFileContext@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@2@@Z; win_scope::detail::scope_helper<win_musl::consumption::ZipFileContext *,win_scope::const_policies<win_scope::shared_policies>>::destruct<win_musl::consumption::ZipFileContext *,win_scope::const_policies<win_scope::shared_policies>>(win_scope::scope<win_musl::consumption::ZipFileContext *,win_scope::const_policies<win_scope::shared_policies>> *)
0x18000e98c  nop
0x18000e98d  cmp     [rbp+5E0h+var_5B0], 10h
0x18000e992  jnb     loc_18000ED2C
0x18000e998  mov     [rbp+5E0h+var_5B0], r14
0x18000e99c  mov     [rbp+5E0h+var_5B8], 0
0x18000e9a4  mov     byte ptr [rbp+5E0h+Block], 0
0x18000e9a8  lea     rcx, [rbp+5E0h+var_570+8]
0x18000e9ac  call    ??$destruct@PEAUZipFileContext@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@?$scope_helper@PEAUZipFileContext@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@detail@win_scope@@SAXPEAV?$scope@PEAUZipFileContext@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@2@@Z; win_scope::detail::scope_helper<win_musl::consumption::ZipFileContext *,win_scope::const_policies<win_scope::shared_policies>>::destruct<win_musl::consumption::ZipFileContext *,win_scope::const_policies<win_scope::shared_policies>>(win_scope::scope<win_musl::consumption::ZipFileContext *,win_scope::const_policies<win_scope::shared_policies>> *)
0x18000e9b1  nop
0x18000e9b2  cmp     qword ptr [rbp+5E0h+var_570], 10h
0x18000e9b7  jnb     loc_18000ED3A
0x18000e9bd  xorps   xmm0, xmm0
0x18000e9c0  movdqu  xmmword ptr [rsp+6E0h+var_6A0+8], xmm0
0x18000e9c6  mov     rcx, [r12]
0x18000e9ca  test    rcx, rcx
0x18000e9cd  jz      short loc_18000E9EF
0x18000e9cf  mov     rdx, [r12+8]
0x18000e9d4  mov     eax, edi
0x18000e9d6  lock xadd [rcx+8], eax
0x18000e9db  add     eax, edi
0x18000e9dd  cmp     eax, edi
0x18000e9df  jz      loc_18000ECE2
0x18000e9e5  mov     [rsp+6E0h+var_6A0+8], rcx
0x18000e9ea  mov     qword ptr [rsp+6E0h+var_690], rdx
0x18000e9ef  mov     edx, 5
0x18000e9f4  lea     rcx, [rsp+6E0h+var_6A0+8]
0x18000e9f9  call    ?AdvanceState@ZipFileContext@consumption@win_musl@@SAXV?$scope@PEAUZipFileContext@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@W4type@ZipFileState@23@@Z; win_musl::consumption::ZipFileContext::AdvanceState(win_scope::scope<win_musl::consumption::ZipFileContext *,win_scope::const_policies<win_scope::shared_policies>>,win_musl::consumption::ZipFileState::type)
0x18000e9fe  mov     rax, [r15+8]
0x18000ea02  mov     rax, [rax+8]
0x18000ea06  mov     [rbp+5E0h+var_640], rax
0x18000ea0a  lea     rcx, [rsp+6E0h+var_6A0]
  ... truncated ...
```
