# HitTestHelper::HitTestRequestWithRetry(HitTestHelper::HitTestRequest const &,IDWMInputProxy *,InputSiteManager *,IInputSiteHierarchyManager *)

- ea: `0x1800150f0`
- end: `0x180015b48`
- name: `?HitTestRequestWithRetry@HitTestHelper@@SA?AUHitTestResult@@AEBUHitTestRequest@1@PEAUIDWMInputProxy@@PEAVInputSiteManager@@PEAUIInputSiteHierarchyManager@@@Z`
- size: `2648`
- prototype: ``
- caller_count: `7`
- callee_count: `21`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180014530`
- `0x18019ff10`
- `0x1801a00e0`
- `0x1801a0160`
- `0x1801a01d0`
- `0x1801a08ac`
- `0x1801a0b84`

## callees

- `0x18000c5bc`
- `0x1800150b8`
- `0x1800150f0`
- `0x180016180`
- `0x1800163b0`
- `0x180016b90`
- `0x180016bbc`
- `0x180016c00`
- `0x1800170a0`
- `0x180026be0`
- `0x18004b210`
- `0x18005131c`
- `0x18008941c`
- `0x1800899c8`
- `0x18008e194`
- `0x1800af59c`
- `0x1800f08d8`
- `0x1800f0990`
- `0x1800f0a90`
- `0x18019f064`
- `0x1801ce010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001591f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001591f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001590c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001590c`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180015aab`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180015af0`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180015aab`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180015af0`
- `win32u!NtCloseCompositionInputSink` at `0x180015901`
- `win32u!NtCloseCompositionInputSink` at `0x180015917`
- `win32u!NtCloseCompositionInputSink` at `0x180015901`
- `win32u!NtCloseCompositionInputSink` at `0x180015917`

## string_xrefs

- `0x180015ab8`: `onecoreuap\windows\moderncore\inputv2\systeminputrouters\components\hittesthelper\hittesthelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
_QWORD *__fastcall HitTestHelper::HitTestRequestWithRetry(
        void *a1,
        __int128 *a2,
        __int64 (__fastcall ***a3)(_QWORD, __int128 *),
        __int64 a4,
        __int64 a5)
{
  __int64 v8; // r12
  __int64 v9; // rdi
  __int64 v10; // r13
  __int64 v11; // rbx
  char *v12; // rsi
  char *v13; // r14
  unsigned __int64 i; // r13
  __int64 v15; // rax
  __int64 v16; // r15
  void *v17; // r14
  signed __int64 v18; // rbx
  unsigned __int64 v19; // rsi
  unsigned __int64 v20; // r8
  __int64 v21; // rax
  char *v22; // rdi
  char *v23; // rbx
  void *v24; // rdx
  char *v25; // r8
  void *v26; // rcx
  __int64 *v27; // rbx
  __int64 *v28; // rdi
  __int64 v29; // rcx
  const struct std::nothrow_t *v30; // rdx
  __int64 *v31; // rbx
  __int64 *v32; // rdi
  __int64 v33; // rcx
  void *v34; // rcx
  const struct std::nothrow_t *v35; // rdx
  _QWORD *v36; // rsi
  char *v37; // rdi
  char *v38; // r14
  __int64 *v39; // rbx
  __int64 *j; // rsi
  __int64 v41; // rcx
  _QWORD *v42; // rcx
  void *v43; // rdx
  void *v44; // rdx
  __int64 v46; // rcx
  __int64 v47; // rdx
  char v48; // al
  char v49; // cl
  __int64 v50; // rdx
  __int64 v51; // rax
  __int64 v52; // r12
  void *v53; // r15
  signed __int64 v54; // rbx
  unsigned __int64 v55; // r14
  unsigned __int64 v56; // r8
  unsigned __int64 v57; // rdi
  __int64 size_of; // rax
  char *v59; // rsi
  char *v60; // rbx
  void *v61; // rdx
  char *v62; // r8
  void *v63; // rcx
  __int64 *v64; // rbx
  __int64 *v65; // rdi
  __int64 v66; // rcx
  const struct std::nothrow_t *v67; // rdx
  DWORD LastError; // ebx
  _BYTE *v69; // rdi
  _BYTE *v70; // rbx
  void *v71; // [rsp+20h] [rbp-E0h] BYREF
  unsigned __int64 v72; // [rsp+28h] [rbp-D8h] BYREF
  void *v73; // [rsp+30h] [rbp-D0h] BYREF
  void *v74; // [rsp+38h] [rbp-C8h] BYREF
  void *v75[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v76; // [rsp+50h] [rbp-B0h]
  __int64 v77; // [rsp+58h] [rbp-A8h]
  void *v78; // [rsp+60h] [rbp-A0h] BYREF
  __int64 *v79; // [rsp+68h] [rbp-98h]
  __int64 v80; // [rsp+70h] [rbp-90h]
  __int64 v81; // [rsp+78h] [rbp-88h]
  _QWORD v82[2]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v83; // [rsp+90h] [rbp-70h]
  __int64 v84; // [rsp+A0h] [rbp-60h]
  char *v85; // [rsp+A8h] [rbp-58h]
  char v86; // [rsp+B0h] [rbp-50h]
  int v87; // [rsp+B1h] [rbp-4Fh]
  __int16 v88; // [rsp+B5h] [rbp-4Bh]
  char v89; // [rsp+B7h] [rbp-49h]
  __int64 v90; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v91; // [rsp+C0h] [rbp-40h]
  __int128 v92; // [rsp+D0h] [rbp-30h]
  __int128 v93; // [rsp+E0h] [rbp-20h]
  __int128 v94; // [rsp+F0h] [rbp-10h]
  __int128 v95; // [rsp+100h] [rbp+0h]
  void *v96[2]; // [rsp+110h] [rbp+10h] BYREF
  char *v97; // [rsp+120h] [rbp+20h]
  __int128 v98; // [rsp+130h] [rbp+30h] BYREF
  __int128 v99; // [rsp+140h] [rbp+40h]
  __int128 v100; // [rsp+150h] [rbp+50h]
  __int128 v101; // [rsp+160h] [rbp+60h]
  __int128 v102; // [rsp+170h] [rbp+70h]
  __int128 v103; // [rsp+180h] [rbp+80h]
  __int128 v104; // [rsp+190h] [rbp+90h]
  __int128 v105; // [rsp+1A0h] [rbp+A0h]
  __int64 v106; // [rsp+1B0h] [rbp+B0h]
  _BYTE v107[64]; // [rsp+1C0h] [rbp+C0h] BYREF
  _BYTE v108[160]; // [rsp+200h] [rbp+100h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2F8h] [rbp+1F8h]

  v74 = a1;
  v8 = a5;
  v81 = a5;
  InputTraceLogging::PerfRegion::PerfRegion((InputTraceLogging::PerfRegion *)v107, "ISMHitTest", 0);
  v86 = 0;
  v87 = 0;
  v88 = 0;
  v89 = 0;
  v90 = 0;
  v91 = 0;
  v92 = 0;
  v93 = 0;
  v94 = 0;
  v95 = 0;
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned int const,ForegroundManager::TargetingInfo>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned int const,ForegroundManager::TargetingInfo>>>>>>(v96);
  v98 = *a2;
  v99 = a2[1];
  v100 = a2[2];
  v101 = a2[3];
  v102 = a2[4];
  v103 = a2[5];
  v104 = a2[6];
  v105 = a2[7];
  v106 = *((_QWORD *)a2 + 16);
  memset_0(v108, 0, sizeof(v108));
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned int const,ForegroundManager::TargetingInfo>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned int const,ForegroundManager::TargetingInfo>>>>>>(v82);
  *((_QWORD *)&v105 + 1) = v108;
  LODWORD(v106) = 20;
  v86 = (**a3)(a3, &v98);
  v9 = *((_QWORD *)&v99 + 1);
  v10 = v90;
  if ( (unsigned __int64)(v90 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = GetLastError();
    NtCloseCompositionInputSink(v10);
    SetLastError(LastError);
  }
  v90 = v9;
  if ( (unsigned int)v106 > 0x14 )
  {
    *(_OWORD *)v75 = 0;
    v76 = 0;
    std::vector<_LUID>::_Construct_n<>(v75, (unsigned int)v106);
    std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<unsigned __int64>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<unsigned __int64>>,std::_Iterator_base0>>>(v82);
    v69 = v75[0];
    v73 = v75[0];
    v82[0] = v75[0];
    v70 = v75[1];
    v82[1] = v75[1];
    v77 = v76;
    v83 = v76;
    *(_OWORD *)v75 = 0;
    v76 = 0;
    std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<unsigned __int64>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<unsigned __int64>>,std::_Iterator_base0>>>(v75);
    v98 = *a2;
    v99 = a2[1];
    v100 = a2[2];
    v101 = a2[3];
    v102 = a2[4];
    v103 = a2[5];
    v104 = a2[6];
    v105 = a2[7];
    HIDWORD(v106) = HIDWORD(*((_QWORD *)a2 + 16));
    *((_QWORD *)&v105 + 1) = v69;
    LODWORD(v106) = (v70 - v69) >> 3;
    v86 = (**a3)(a3, &v98);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<long (*)(void *),&long NtCloseCompositionInputSink(void *)>>::reset(
      &v90,
      *((_QWORD *)&v99 + 1));
    v11 = v77;
  }
  else
  {
    v11 = v83;
    v77 = v83;
    v73 = (void *)v82[0];
  }
  if ( v86 )
  {
    v91 = v100;
    v92 = v101;
    v93 = v102;
    v94 = v103;
    *(_QWORD *)&v95 = v99;
    BYTE8(v95) = (BYTE4(v104) & 1) != 0;
    HIDWORD(v95) = v104;
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)a5 + 40LL))(a5);
  if ( v86 )
  {
    InputSiteManager::GetInputSiteForEvaluationListFromDITCallbackStruct(a4, v75, &v98);
    v12 = (char *)v75[0];
    v71 = v75[0];
    v13 = (char *)v75[1];
    v85 = (char *)v75[1];
    for ( i = 0xAAAAAAAAAAAAAAALL; v12 != v13; v8 = v81 )
    {
      v46 = *(_QWORD *)(*(_QWORD *)v12 + 16LL);
      v47 = *(_QWORD *)(*(_QWORD *)v12 + 24LL);
      if ( v46 == v47 )
      {
LABEL_62:
        v48 = 0;
        v49 = 1;
        v50 = v84;
      }
      else
      {
        while ( *(_DWORD *)v46 )
        {
          v46 += 16;
          if ( v46 == v47 )
            goto LABEL_62;
        }
        v50 = *(_QWORD *)(v46 + 8);
        v84 = v50;
        v48 = 1;
        v49 = 0;
      }
      if ( v49 )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0xEF,
          (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\components\\hittesthelper\\hittesthelper.cpp",
          (const char *)retaddr);
      if ( !v48 )
        std::_Throw_bad_optional_access();
      v51 = (*(__int64 (__fastcall **)(__int64, void **, __int64, wil::details::in1diag3 *))(*(_QWORD *)v8 + 24LL))(
              v8,
              &v78,
              v50,
              retaddr);
      v52 = v51;
      v53 = v96[1];
      if ( v96[1] == v97 )
      {
        v54 = ((char *)v96[1] - (char *)v96[0]) / 24;
        if ( v54 == 0xAAAAAAAAAAAAAAALL )
          std::_Xlength_error("vector too long");
        v55 = v54 + 1;
        v56 = 0xAAAAAAAAAAAAAAABuLL * ((v97 - (char *)v96[0]) >> 3);
        if ( v56 > 0xAAAAAAAAAAAAAAALL - (v56 >> 1) )
        {
          v57 = 0xAAAAAAAAAAAAAAALL;
        }
        else
        {
          v57 = (v56 >> 1) - 0x5555555555555555LL * ((v97 - (char *)v96[0]) >> 3);
          if ( v57 < v55 )
            v57 = v54 + 1;
        }
        size_of = std::_Get_size_of_n<24>(v57);
        v59 = (char *)std::_Allocate<16,std::_Default_allocate_traits>(size_of);
        v60 = &v59[24 * v54];
        std::vector<InputProvider>::vector<InputProvider>(v60, v52);
        v61 = v96[1];
        v62 = v59;
        v63 = v96[0];
        if ( v53 != v96[1] )
        {
          std::_Uninitialized_move<std::vector<Microsoft::WRL::ComPtr<InputSite>> *,std::allocator<std::vector<Microsoft::WRL::ComPtr<InputSite>>>>(
            v96[0],
            v53,
            v59);
          v62 = v60 + 24;
          v61 = v96[1];
          v63 = v53;
        }
        std::_Uninitialized_move<std::vector<Microsoft::WRL::ComPtr<InputSite>> *,std::allocator<std::vector<Microsoft::WRL::ComPtr<InputSite>>>>(
          v63,
          v61,
          v62);
        if ( v96[0] )
        {
          std::_Destroy_range<std::allocator<std::vector<Microsoft::WRL::ComPtr<InputSite>>>>(v96[0], v96[1]);
          std::_Deallocate<16>(v96[0], 8 * ((v97 - (char *)v96[0]) >> 3));
        }
        v96[0] = v59;
        v96[1] = &v59[24 * v55];
        v97 = &v59[24 * v57];
        v12 = (char *)v71;
        v13 = v85;
      }
      else
      {
        std::vector<InputProvider>::vector<InputProvider>(v96[1], v51);
        v96[1] = (char *)v96[1] + 24;
      }
      v64 = (__int64 *)v78;
      if ( v78 )
      {
        v65 = v79;
        if ( v78 != v79 )
        {
          do
          {
            v66 = *v64;
            if ( *v64 )
            {
              *v64 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v66 + 16LL))(v66);
            }
            ++v64;
          }
          while ( v64 != v65 );
          v64 = (__int64 *)v78;
        }
        v67 = (const struct std::nothrow_t *)((v80 - (_QWORD)v64) & 0xFFFFFFFFFFFFFFF8uLL);
        v72 = (unsigned __int64)v67;
        v71 = v64;
        if ( (unsigned __int64)v67 >= 0x1000 )
        {
          std::_Adjust_manually_vector_aligned(&v71, &v72);
          v67 = (const struct std::nothrow_t *)v72;
          v64 = (__int64 *)v71;
        }
        operator delete(v64, v67);
      }
      v12 += 8;
      v71 = v12;
    }
    if ( v96[0] == v96[1] )
    {
      v15 = std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned int const,ForegroundManager::TargetingInfo>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned int const,ForegroundManager::TargetingInfo>>>>>>(&v78);
      v16 = v15;
      v17 = v96[1];
      if ( v96[1] == v97 )
      {
        v18 = ((char *)v96[1] - (char *)v96[0]) / 24;
        if ( v18 == 0xAAAAAAAAAAAAAAALL )
          std::_Xlength_error("vector too long");
        v19 = v18 + 1;
        v20 = 0xAAAAAAAAAAAAAAABuLL * ((v97 - (char *)v96[0]) >> 3);
        if ( v20 <= 0xAAAAAAAAAAAAAAALL - (v20 >> 1) )
        {
          i = (v20 >> 1) - 0x5555555555555555LL * ((v97 - (char *)v96[0]) >> 3);
          if ( i < v19 )
            i = v18 + 1;
        }
        v21 = std::_Get_size_of_n<24>(i);
        v22 = (char *)std::_Allocate<16,std::_Default_allocate_traits>(v21);
        v23 = &v22[24 * v18];
        std::vector<InputProvider>::vector<InputProvider>(v23, v16);
        v24 = v96[1];
        v25 = v22;
        v26 = v96[0];
        if ( v17 != v96[1] )
        {
          std::_Uninitialized_move<std::vector<Microsoft::WRL::ComPtr<InputSite>> *,std::allocator<std::vector<Microsoft::WRL::ComPtr<InputSite>>>>(
            v96[0],
            v17,
            v22);
          v25 = v23 + 24;
          v24 = v96[1];
          v26 = v17;
        }
        std::_Uninitialized_move<std::vector<Microsoft::WRL::ComPtr<InputSite>> *,std::allocator<std::vector<Microsoft::WRL::ComPtr<InputSite>>>>(
          v26,
          v24,
          v25);
        if ( v96[0] )
        {
          std::_Destroy_range<std::allocator<std::vector<Microsoft::WRL::ComPtr<InputSite>>>>(v96[0], v96[1]);
          std::_Deallocate<16>(v96[0], 8 * ((v97 - (char *)v96[0]) >> 3));
        }
        v96[0] = v22;
        v96[1] = &v22[24 * v19];
        v97 = &v22[24 * i];
      }
      else
      {
        std::vector<InputProvider>::vector<InputProvider>(v96[1], v15);
        v96[1] = (char *)v96[1] + 24;
      }
      v27 = (__int64 *)v78;
      if ( v78 )
      {
        v28 = v79;
        if ( v78 != v79 )
        {
          do
          {
            v29 = *v27;
            if ( *v27 )
            {
              *v27 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
            }
            ++v27;
          }
          while ( v27 != v28 );
          v27 = (__int64 *)v78;
        }
        v30 = (const struct std::nothrow_t *)((v80 - (_QWORD)v27) & 0xFFFFFFFFFFFFFFF8uLL);
        v72 = (unsigned __int64)v30;
        v71 = v27;
        if ( (unsigned __int64)v30 >= 0x1000 )
        {
          std::_Adjust_manually_vector_aligned(&v71, &v72);
          v27 = (__int64 *)v71;
          v30 = (const struct std::nothrow_t *)v72;
        }
        operator delete(v27, v30);
      }
    }
    v31 = (__int64 *)v75[0];
    if ( v75[0] )
    {
      v32 = (__int64 *)v75[1];
      if ( v75[0] != v75[1] )
      {
        do
        {
          v33 = *v31;
          if ( *v31 )
          {
            *v31 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
          }
          ++v31;
        }
        while ( v31 != v32 );
      }
      v34 = v75[0];
      v35 = (const struct std::nothrow_t *)((v76 - (unsigned __int64)v75[0]) & 0xFFFFFFFFFFFFFFF8uLL);
      v72 = (unsigned __int64)v35;
      v71 = v75[0];
      if ( (unsigned __int64)v35 >= 0x1000 )
      {
        std::_Adjust_manually_vector_aligned(&v71, &v72);
        v34 = v71;
        v35 = (const struct std::nothrow_t *)v72;
      }
      operator delete(v34, v35);
    }
    v11 = v77;
  }
  v36 = v74;
  *(_BYTE *)v74 = v86;
  v36[1] = v90;
  v90 = 0;
  *((_OWORD *)v36 + 1) = v91;
  *((_OWORD *)v36 + 2) = v92;
  *((_OWORD *)v36 + 3) = v93;
  *((_OWORD *)v36 + 4) = v94;
  v36[10] = v95;
  *((_BYTE *)v36 + 88) = BYTE8(v95);
  *((_DWORD *)v36 + 23) = HIDWORD(v95);
  std::vector<InputProvider>::vector<InputProvider>(v36 + 12, v96);
  if ( v73 )
    std::_Deallocate<16>(v73, (v11 - (_QWORD)v73) & 0xFFFFFFFFFFFFFFF8uLL);
  v37 = (char *)v96[0];
  if ( v96[0] )
  {
    v38 = (char *)v96[1];
    if ( v96[0] != v96[1] )
    {
      do
      {
        v39 = *(__int64 **)v37;
        if ( *(_QWORD *)v37 )
        {
          for ( j = (__int64 *)*((_QWORD *)v37 + 1); v39 != j; ++v39 )
          {
            v41 = *v39;
            if ( *v39 )
            {
              *v39 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
            }
          }
          v42 = *(_QWORD **)v37;
          v43 = (void *)((*((_QWORD *)v37 + 2) - *(_QWORD *)v37) & 0xFFFFFFFFFFFFFFF8uLL);
          v71 = v43;
          v73 = v42;
          if ( (unsigned __int64)v43 >= 0x1000 )
          {
            std::_Adjust_manually_vector_aligned(&v73, (unsigned __int64 *)&v71);
            v42 = v73;
            v43 = v71;
          }
          operator delete(v42, (const struct std::nothrow_t *)v43);
          *(_QWORD *)v37 = 0;
          *((_QWORD *)v37 + 1) = 0;
          *((_QWORD *)v37 + 2) = 0;
        }
        v37 += 24;
      }
      while ( v37 != v38 );
      v37 = (char *)v96[0];
      v36 = v74;
    }
    v44 = (void *)(8 * ((v97 - v37) >> 3));
    v73 = v44;
    v74 = v37;
    if ( (unsigned __int64)v44 >= 0x1000 )
    {
      std::_Adjust_manually_vector_aligned(&v74, (unsigned __int64 *)&v73);
      v37 = (char *)v74;
      v44 = v73;
    }
    operator delete(v37, (const struct std::nothrow_t *)v44);
    *(_OWORD *)v96 = 0;
    v97 = 0;
  }
  if ( (unsigned __int64)(v90 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    NtCloseCompositionInputSink(v90);
  InputTraceLogging::PerfRegion::~PerfRegion((InputTraceLogging::PerfRegion *)v107);
  return v36;
}

```

## disassembly

```asm
0x1800150f0  push    rbp
0x1800150f2  push    rbx
0x1800150f3  push    rsi
0x1800150f4  push    rdi
0x1800150f5  push    r12
0x1800150f7  push    r13
0x1800150f9  push    r14
0x1800150fb  push    r15
0x1800150fd  lea     rbp, [rsp-1B8h]
0x180015105  sub     rsp, 2B8h
0x18001510c  mov     rax, cs:__security_cookie
0x180015113  xor     rax, rsp
0x180015116  mov     [rbp+1F0h+var_50], rax
0x18001511d  mov     r14, r9
0x180015120  mov     r15, r8
0x180015123  mov     rsi, rdx
0x180015126  mov     [rsp+2F0h+var_2B8], rcx
0x18001512b  mov     [rsp+2F0h+var_278], rcx
0x180015130  mov     r12, [rbp+1F0h+arg_20]
0x180015137  mov     [rsp+2F0h+var_278], r12
0x18001513c  xor     ebx, ebx
0x18001513e  xor     r8d, r8d; struct InputTraceLogging::PerfRegion *
0x180015141  lea     rdx, aIsmhittest; "ISMHitTest"
0x180015148  lea     rcx, [rbp+1F0h+var_130]; this
0x18001514f  call    ??0PerfRegion@InputTraceLogging@@QEAA@PEBDPEBU01@@Z; InputTraceLogging::PerfRegion::PerfRegion(char const *,InputTraceLogging::PerfRegion const *)
0x180015154  nop
0x180015155  mov     [rbp+1F0h+var_240], bl
0x180015158  xor     eax, eax
0x18001515a  mov     [rbp+1F0h+var_23F], eax
0x18001515d  mov     [rbp+1F0h+var_23B], ax
0x180015161  mov     [rbp+1F0h+var_239], al
0x180015164  mov     [rbp+1F0h+var_238], rbx
0x180015168  xorps   xmm0, xmm0
0x18001516b  movups  [rbp+1F0h+var_230], xmm0
0x18001516f  movups  [rbp+1F0h+var_220], xmm0
0x180015173  movups  [rbp+1F0h+var_210], xmm0
0x180015177  movups  [rbp+1F0h+var_200], xmm0
0x18001517b  movups  [rbp+1F0h+var_1F0], xmm0
0x18001517f  lea     rcx, [rbp+1F0h+var_1E0]
0x180015183  call    ??$?0AEBV?$allocator@U?$pair@$$CBIUTargetingInfo@ForegroundManager@@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBIUTargetingInfo@ForegroundManager@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@AEBV?$allocator@U?$pair@$$CBIUTargetingInfo@ForegroundManager@@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<uint const,ForegroundManager::TargetingInfo>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<uint const,ForegroundManager::TargetingInfo>>>>>>(std::allocator<std::pair<uint const,ForegroundManager::TargetingInfo>> const &)
0x180015188  nop
0x180015189  movups  xmm0, xmmword ptr [rsi]
0x18001518c  movaps  [rbp+1F0h+var_1C0], xmm0
0x180015190  movups  xmm1, xmmword ptr [rsi+10h]
0x180015194  movaps  [rbp+1F0h+var_1B0], xmm1
0x180015198  movups  xmm0, xmmword ptr [rsi+20h]
0x18001519c  movaps  [rbp+1F0h+var_1A0], xmm0
0x1800151a0  movups  xmm1, xmmword ptr [rsi+30h]
0x1800151a4  movaps  [rbp+1F0h+var_190], xmm1
0x1800151a8  movups  xmm0, xmmword ptr [rsi+40h]
0x1800151ac  movaps  [rbp+1F0h+var_180], xmm0
0x1800151b0  movups  xmm1, xmmword ptr [rsi+50h]
0x1800151b4  movaps  [rbp+1F0h+var_170], xmm1
0x1800151bb  movups  xmm0, xmmword ptr [rsi+60h]
0x1800151bf  movaps  [rbp+1F0h+var_160], xmm0
0x1800151c6  movups  xmm1, xmmword ptr [rsi+70h]
0x1800151ca  movaps  [rbp+1F0h+var_150], xmm1
0x1800151d1  movsd   xmm0, qword ptr [rsi+80h]
0x1800151d9  movsd   [rbp+1F0h+var_140], xmm0
0x1800151e1  xor     edx, edx; Val
0x1800151e3  mov     r8d, 0A0h; Size
0x1800151e9  lea     rcx, [rbp+1F0h+var_F0]; void *
0x1800151f0  call    memset_0
0x1800151f5  lea     rcx, [rbp+1F0h+var_270]
0x1800151f9  call    ??$?0AEBV?$allocator@U?$pair@$$CBIUTargetingInfo@ForegroundManager@@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBIUTargetingInfo@ForegroundManager@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@AEBV?$allocator@U?$pair@$$CBIUTargetingInfo@ForegroundManager@@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<uint const,ForegroundManager::TargetingInfo>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<uint const,ForegroundManager::TargetingInfo>>>>>>(std::allocator<std::pair<uint const,ForegroundManager::TargetingInfo>> const &)
0x1800151fe  nop
0x1800151ff  lea     rax, [rbp+1F0h+var_F0]
0x180015206  mov     qword ptr [rbp+1F0h+var_150+8], rax
0x18001520d  mov     dword ptr [rbp+1F0h+var_140], 14h
0x180015217  mov     rax, [r15]
0x18001521a  lea     rdx, [rbp+1F0h+var_1C0]
0x18001521e  mov     rcx, r15
0x180015221  mov     rax, [rax]
0x180015224  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015229  mov     [rbp+1F0h+var_240], al
0x18001522c  mov     rdi, qword ptr [rbp+1F0h+var_1B0+8]
0x180015230  mov     r13, [rbp+1F0h+var_238]
0x180015234  lea     rax, [r13-1]
0x180015238  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001523c  jbe     loc_18001590C
0x180015242  mov     [rbp+1F0h+var_238], rdi
0x180015246  mov     eax, dword ptr [rbp+1F0h+var_140]
0x18001524c  cmp     eax, 14h
0x18001524f  ja      loc_18001592C
0x180015255  mov     rbx, [rbp+1F0h+var_260]
0x180015259  mov     [rsp+2F0h+var_298], rbx
0x18001525e  mov     rdi, [rbp+1F0h+var_270]
0x180015262  mov     [rsp+2F0h+var_2C0], rdi
0x180015267  cmp     [rbp+1F0h+var_240], 0
0x18001526b  jz      short loc_1800152B2
0x18001526d  movaps  xmm0, [rbp+1F0h+var_1A0]
0x180015271  movaps  [rbp+1F0h+var_230], xmm0
0x180015275  movaps  xmm1, [rbp+1F0h+var_190]
0x180015279  movaps  [rbp+1F0h+var_220], xmm1
0x18001527d  movaps  xmm0, [rbp+1F0h+var_180]
0x180015281  movaps  [rbp+1F0h+var_210], xmm0
0x180015285  movaps  xmm1, [rbp+1F0h+var_170]
0x18001528c  movaps  [rbp+1F0h+var_200], xmm1
0x180015290  mov     rax, qword ptr [rbp+1F0h+var_1B0]
0x180015294  mov     qword ptr [rbp+1F0h+var_1F0], rax
0x180015298  test    byte ptr [rbp+1F0h+var_160+4], 1
0x18001529f  jnz     loc_1800158DA
0x1800152a5  mov     byte ptr [rbp+1F0h+var_1F0+8], 0
0x1800152a9  mov     eax, dword ptr [rbp+1F0h+var_160]
0x1800152af  mov     dword ptr [rbp+1F0h+var_1F0+0Ch], eax
0x1800152b2  mov     rax, [r12]
0x1800152b6  mov     rcx, r12
0x1800152b9  mov     rax, [rax+28h]
0x1800152bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800152c2  mov     rdi, 0AAAAAAAAAAAAAAABh
0x1800152cc  cmp     [rbp+1F0h+var_240], 0
0x1800152d0  jz      loc_18001569F
0x1800152d6  lea     r8, [rbp+1F0h+var_1C0]
0x1800152da  lea     rdx, [rsp+2F0h+var_2B0]
0x1800152df  mov     rcx, r14
0x1800152e2  call    ?GetInputSiteForEvaluationListFromDITCallbackStruct@InputSiteManager@@QEAA?AV?$vector@V?$ComPtr@VInputSite@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VInputSite@@@WRL@Microsoft@@@std@@@std@@AEBUtagDITCALLBACKSTRUCT@@@Z; InputSiteManager::GetInputSiteForEvaluationListFromDITCallbackStruct(tagDITCALLBACKSTRUCT const &)
0x1800152e7  nop
0x1800152e8  mov     rsi, [rsp+2F0h+var_2B0]
0x1800152ed  mov     [rsp+2F0h+var_2D0], rsi
0x1800152f2  mov     r14, [rsp+2F0h+var_2B0+8]
0x1800152f7  mov     [rbp+1F0h+var_248], r14
0x1800152fb  mov     rbx, 2AAAAAAAAAAAAAABh
0x180015305  mov     r13, 0AAAAAAAAAAAAAAAh
0x18001530f  cmp     rsi, r14
0x180015312  jnz     loc_1800156B0
0x180015318  mov     rax, [rbp+1F0h+var_1E0+8]
0x18001531c  cmp     [rbp+1F0h+var_1E0], rax
0x180015320  jnz     loc_18001547D
0x180015326  lea     rcx, [rsp+2F0h+var_290]
0x18001532b  call    ??$?0AEBV?$allocator@U?$pair@$$CBIUTargetingInfo@ForegroundManager@@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBIUTargetingInfo@ForegroundManager@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@AEBV?$allocator@U?$pair@$$CBIUTargetingInfo@ForegroundManager@@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<uint const,ForegroundManager::TargetingInfo>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<uint const,ForegroundManager::TargetingInfo>>>>>>(std::allocator<std::pair<uint const,ForegroundManager::TargetingInfo>> const &)
0x180015330  mov     r15, rax
0x180015333  mov     r8, [rbp+1F0h+var_1D0]
0x180015337  mov     r14, [rbp+1F0h+var_1E0+8]
0x18001533b  mov     rcx, r14
0x18001533e  cmp     r14, r8
0x180015341  jnz     loc_180015ACD
0x180015347  mov     r9, [rbp+1F0h+var_1E0]
0x18001534b  sub     rcx, r9
0x18001534e  mov     rax, rbx
0x180015351  imul    rcx
0x180015354  mov     rbx, rdx
0x180015357  sar     rbx, 2
0x18001535b  mov     rax, rbx
0x18001535e  shr     rax, 3Fh
0x180015362  add     rbx, rax
0x180015365  cmp     rbx, r13
0x180015368  jz      loc_180015AE9
0x18001536e  lea     rsi, [rbx+1]
0x180015372  sub     r8, r9
0x180015375  sar     r8, 3
0x180015379  imul    r8, rdi
0x18001537d  mov     rcx, r8
0x180015380  shr     rcx, 1
0x180015383  mov     rax, r13
0x180015386  sub     rax, rcx
0x180015389  cmp     r8, rax
0x18001538c  ja      short loc_180015399
0x18001538e  lea     r13, [rcx+r8]
0x180015392  cmp     r13, rsi
0x180015395  cmovb   r13, rsi
0x180015399  mov     rcx, r13
0x18001539c  call    ??$_Get_size_of_n@$0BI@@std@@YA_K_K@Z; std::_Get_size_of_n<24>(unsigned __int64)
0x1800153a1  mov     rcx, rax
0x1800153a4  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1800153a9  mov     rdi, rax
0x1800153ac  lea     rax, [rbx+rbx*2]
0x1800153b0  lea     rbx, [rdi+rax*8]
0x1800153b4  mov     rdx, r15
0x1800153b7  mov     rcx, rbx
0x1800153ba  call    ??0?$vector@UInputProvider@@V?$allocator@UInputProvider@@@std@@@std@@QEAA@$$QEAV01@@Z; std::vector<InputProvider>::vector<InputProvider>(std::vector<InputProvider> &&)
0x1800153bf  mov     rdx, [rbp+1F0h+var_1E0+8]
0x1800153c3  mov     r8, rdi
0x1800153c6  mov     rcx, [rbp+1F0h+var_1E0]
0x1800153ca  cmp     r14, rdx
0x1800153cd  jnz     loc_180015AF7
0x1800153d3  call    ??$_Uninitialized_move@PEAV?$vector@V?$ComPtr@VInputSite@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VInputSite@@@WRL@Microsoft@@@std@@@std@@V?$allocator@V?$vector@V?$ComPtr@VInputSite@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VInputSite@@@WRL@Microsoft@@@std@@@std@@@2@@std@@YAPEAV?$vector@V?$ComPtr@VInputSite@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VInputSite@@@WRL@Microsoft@@@std@@@0@QEAV10@0PEAV10@AEAV?$allocator@V?$vector@V?$ComPtr@VInputSite@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VInputSite@@@WRL@Microsoft@@@std@@@std@@@0@@Z; std::_Uninitialized_move<std::vector<Microsoft::WRL::ComPtr<InputSite>> *,std::allocator<std::vector<Microsoft::WRL::ComPtr<InputSite>>>>(std::vector<Microsoft::WRL::ComPtr<InputSite>> * const,std::vector<Microsoft::WRL::ComPtr<InputSite>> * const,std::vector<Microsoft::WRL::ComPtr<InputSite>> *,std::allocator<std::vector<Microsoft::WRL::ComPtr<InputSite>>> &)
0x1800153d8  mov     rcx, [rbp+1F0h+var_1E0]
0x1800153dc  test    rcx, rcx
0x1800153df  jnz     loc_180015B0F
0x1800153e5  mov     r12, 0AAAAAAAAAAAAAAABh
0x1800153ef  mov     [rbp+1F0h+var_1E0], rdi
0x1800153f3  lea     rax, [rsi+rsi*2]
0x1800153f7  lea     rcx, [rdi+rax*8]
0x1800153fb  mov     [rbp+1F0h+var_1E0+8], rcx
0x1800153ff  lea     rax, ds:0[r13*2]
0x180015407  add     rax, r13
0x18001540a  lea     rcx, [rdi+rax*8]
0x18001540e  mov     [rbp+1F0h+var_1D0], rcx
0x180015412  mov     rbx, [rsp+2F0h+var_290]
0x180015417  test    rbx, rbx
0x18001541a  jz      short loc_180015487
0x18001541c  mov     rdi, [rsp+2F0h+var_288]
0x180015421  cmp     rbx, rdi
0x180015424  jz      short loc_180015450
0x180015426  mov     rcx, [rbx]
0x180015429  test    rcx, rcx
0x18001542c  jz      short loc_180015442
0x18001542e  mov     qword ptr [rbx], 0
0x180015435  mov     rax, [rcx]
0x180015438  mov     rax, [rax+10h]
0x18001543c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015441  nop
0x180015442  add     rbx, 8
0x180015446  cmp     rbx, rdi
0x180015449  jnz     short loc_180015426
0x18001544b  mov     rbx, [rsp+2F0h+var_290]
0x180015450  mov     rdx, [rsp+2F0h+var_280]
0x180015455  sub     rdx, rbx
0x180015458  and     rdx, 0FFFFFFFFFFFFFFF8h; struct std::nothrow_t *
0x18001545c  mov     [rsp+2F0h+var_2C8], rdx
0x180015461  mov     [rsp+2F0h+var_2D0], rbx
0x180015466  cmp     rdx, 1000h
0x18001546d  jnb     loc_1800158BC
0x180015473  mov     rcx, rbx; void *
0x180015476  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001547b  jmp     short loc_180015487
0x18001547d  mov     r12, 0AAAAAAAAAAAAAAABh
0x180015487  mov     rbx, [rsp+2F0h+var_2B0]
0x18001548c  test    rbx, rbx
0x18001548f  jz      short loc_1800154ED
0x180015491  mov     rdi, [rsp+2F0h+var_2B0+8]
0x180015496  cmp     rbx, rdi
0x180015499  jz      short loc_1800154C0
0x18001549b  mov     rcx, [rbx]
0x18001549e  test    rcx, rcx
0x1800154a1  jz      short loc_1800154B7
0x1800154a3  mov     qword ptr [rbx], 0
0x1800154aa  mov     rax, [rcx]
0x1800154ad  mov     rax, [rax+10h]
0x1800154b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800154b6  nop
0x1800154b7  add     rbx, 8
0x1800154bb  cmp     rbx, rdi
0x1800154be  jnz     short loc_18001549B
0x1800154c0  mov     rcx, [rsp+2F0h+var_2B0]; void *
0x1800154c5  mov     rdx, [rsp+2F0h+var_2A0]
0x1800154ca  sub     rdx, rcx
0x1800154cd  and     rdx, 0FFFFFFFFFFFFFFF8h; struct std::nothrow_t *
0x1800154d1  mov     [rsp+2F0h+var_2C8], rdx
0x1800154d6  mov     [rsp+2F0h+var_2D0], rcx
0x1800154db  cmp     rdx, 1000h
0x1800154e2  jnb     loc_18001589E
0x1800154e8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800154ed  mov     rbx, [rsp+2F0h+var_298]
0x1800154f2  movzx   eax, [rbp+1F0h+var_240]
0x1800154f6  mov     rsi, [rsp+2F0h+var_2B8]
0x1800154fb  mov     [rsi], al
0x1800154fd  mov     rax, [rbp+1F0h+var_238]
0x180015501  mov     [rsi+8], rax
0x180015505  xor     r15d, r15d
0x180015508  mov     [rbp+1F0h+var_238], r15
0x18001550c  movaps  xmm0, [rbp+1F0h+var_230]
0x180015510  movups  xmmword ptr [rsi+10h], xmm0
0x180015514  movaps  xmm1, [rbp+1F0h+var_220]
0x180015518  movups  xmmword ptr [rsi+20h], xmm1
0x18001551c  movaps  xmm0, [rbp+1F0h+var_210]
0x180015520  movups  xmmword ptr [rsi+30h], xmm0
0x180015524  movaps  xmm1, [rbp+1F0h+var_200]
0x180015528  movups  xmmword ptr [rsi+40h], xmm1
0x18001552c  mov     rax, qword ptr [rbp+1F0h+var_1F0]
0x180015530  mov     [rsi+50h], rax
0x180015534  movzx   eax, byte ptr [rbp+1F0h+var_1F0+8]
0x180015538  mov     [rsi+58h], al
0x18001553b  mov     eax, dword ptr [rbp+1F0h+var_1F0+0Ch]
0x18001553e  mov     [rsi+5Ch], eax
0x180015541  lea     rcx, [rsi+60h]
0x180015545  lea     rdx, [rbp+1F0h+var_1E0]
0x180015549  call    ??0?$vector@UInputProvider@@V?$allocator@UInputProvider@@@std@@@std@@QEAA@$$QEAV01@@Z; std::vector<InputProvider>::vector<InputProvider>(std::vector<InputProvider> &&)
0x18001554e  nop
0x18001554f  mov     rax, [rsp+2F0h+var_2C0]
0x180015554  test    rax, rax
0x180015557  jz      short loc_18001556C
0x180015559  sub     rbx, rax
0x18001555c  and     rbx, 0FFFFFFFFFFFFFFF8h
0x180015560  mov     rdx, rbx
0x180015563  mov     rcx, rax
0x180015566  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001556b  nop
0x18001556c  mov     rdi, [rbp+1F0h+var_1E0]
0x180015570  test    rdi, rdi
0x180015573  jz      loc_18001563D
0x180015579  mov     r14, [rbp+1F0h+var_1E0+8]
0x18001557d  cmp     rdi, r14
0x180015580  jz      short loc_1800155FB
0x180015582  mov     rbx, [rdi]
0x180015585  test    rbx, rbx
0x180015588  jz      short loc_1800155E9
0x18001558a  mov     rsi, [rdi+8]
0x18001558e  cmp     rbx, rsi
0x180015591  jz      short loc_1800155B4
0x180015593  mov     rcx, [rbx]
0x180015596  test    rcx, rcx
0x180015599  jz      short loc_1800155AB
0x18001559b  mov     [rbx], r15
0x18001559e  mov     rax, [rcx]
0x1800155a1  mov     rax, [rax+10h]
0x1800155a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800155aa  nop
0x1800155ab  add     rbx, 8
0x1800155af  cmp     rbx, rsi
  ... truncated ...
```
