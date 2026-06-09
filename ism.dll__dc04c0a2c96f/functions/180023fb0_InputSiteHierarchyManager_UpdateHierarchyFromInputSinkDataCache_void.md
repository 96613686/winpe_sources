# InputSiteHierarchyManager::UpdateHierarchyFromInputSinkDataCache(void)

- ea: `0x180023fb0`
- end: `0x180024b33`
- name: `?UpdateHierarchyFromInputSinkDataCache@InputSiteHierarchyManager@@UEAAXXZ`
- size: `2947`
- prototype: `void __fastcall(InputSiteHierarchyManager *__hidden this)`
- caller_count: `0`
- callee_count: `30`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callees

- `0x18000b0ec`
- `0x18000c5bc`
- `0x18001277c`
- `0x180012b74`
- `0x180013e14`
- `0x1800150b8`
- `0x1800170a0`
- `0x1800188a0`
- `0x180023fb0`
- `0x180024b3c`
- `0x180024b68`
- `0x180024d08`
- `0x180024fe4`
- `0x180025338`
- `0x180025364`
- `0x180025cd4`
- `0x18005e004`
- `0x180062ca0`
- `0x1800886d0`
- `0x1800887d8`
- `0x1800899c8`
- `0x18008dcac`
- `0x1800f0354`
- `0x1800f0990`
- `0x1800f0a90`
- `0x1800f0c5c`
- `0x1800f0cc4`
- `0x1800f2749`
- `0x1800f9758`
- `0x1801ce010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180024055`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180024055`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180024020`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180024020`
- `win32u!NtCloseCompositionInputSink` at `0x180024713`
- `win32u!NtCloseCompositionInputSink` at `0x180024713`

## string_xrefs

- `0x180024b21`: `onecoreuap\windows\moderncore\inputv2\components\inputsitemanager\server\inputsitehierarchymanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall InputSiteHierarchyManager::UpdateHierarchyFromInputSinkDataCache(InputSiteHierarchyManager *this)
{
  InputSiteHierarchyManager *v1; // r13
  unsigned int v2; // r12d
  unsigned __int64 v3; // rcx
  _QWORD *v4; // rdx
  _QWORD *v5; // r15
  _QWORD *v6; // rbx
  _QWORD *v7; // rdi
  __int64 v8; // rcx
  void *v9; // rcx
  const struct std::nothrow_t *v10; // rdx
  int v11; // ecx
  _QWORD *v12; // r8
  _QWORD *v13; // rdx
  _QWORD *v14; // rax
  __int64 v15; // rdx
  __int128 v16; // xmm2
  int v17; // r12d
  __int64 v18; // rdx
  __int64 v19; // rsi
  __int64 i; // r14
  int (__fastcall ***v21)(_QWORD, GUID *, __int64 *); // rdi
  int (__fastcall *v22)(_QWORD, GUID *, __int64 *); // rbx
  __int64 v23; // rcx
  _QWORD *v24; // rbx
  _QWORD *v25; // rdi
  _QWORD *v26; // rdi
  int v27; // ecx
  __int64 v28; // rsi
  __int64 v29; // rdi
  unsigned __int64 v30; // rdx
  __int64 *v31; // r14
  __int64 *v32; // r11
  char v33; // al
  __int64 v34; // rbx
  __int64 v35; // rax
  __int64 v36; // r10
  _QWORD *v37; // r11
  _QWORD *v38; // rsi
  _QWORD *v39; // rdx
  _QWORD *v40; // rdi
  _QWORD *v41; // rax
  size_t v42; // rbx
  __int64 v43; // rdi
  __int64 j; // rbx
  __int64 **v45; // rdx
  __int64 *v46; // rax
  __int64 *v47; // rax
  __int64 v48; // rcx
  struct InputSiteManager *InputSiteManager; // rdx
  unsigned __int64 v50; // r13
  __int64 *v51; // r15
  __int64 *v52; // r12
  __int64 v53; // r14
  _DWORD *v54; // rdx
  _DWORD *v55; // rsi
  _DWORD *v56; // rax
  struct InputSiteManager *v57; // rax
  _QWORD *v58; // rax
  unsigned __int64 v59; // rcx
  __int64 v60; // rbx
  __int64 v61; // rax
  __int64 v62; // rcx
  unsigned __int64 *v63; // rdx
  _QWORD *v64; // r9
  _QWORD *v65; // r8
  _QWORD *v66; // rax
  __int64 v67; // rbx
  __int64 v68; // rax
  _OWORD *v69; // rax
  size_t v70; // rbx
  unsigned __int64 v71; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v72; // [rsp+28h] [rbp-D8h] BYREF
  unsigned __int64 v73; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD *v74; // [rsp+38h] [rbp-C8h]
  void *v75; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v76[3]; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v77; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v78; // [rsp+70h] [rbp-90h]
  void *v79; // [rsp+78h] [rbp-88h] BYREF
  _QWORD *v80; // [rsp+80h] [rbp-80h]
  __int64 v81; // [rsp+88h] [rbp-78h]
  __int64 v82; // [rsp+90h] [rbp-70h] BYREF
  _QWORD *v83; // [rsp+98h] [rbp-68h]
  char v84[16]; // [rsp+A8h] [rbp-58h] BYREF
  char v85[16]; // [rsp+B8h] [rbp-48h] BYREF
  char v86[16]; // [rsp+C8h] [rbp-38h] BYREF
  char v87[16]; // [rsp+D8h] [rbp-28h] BYREF
  char v88[16]; // [rsp+E8h] [rbp-18h] BYREF
  char v89[16]; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v90; // [rsp+108h] [rbp+8h] BYREF
  char v91; // [rsp+110h] [rbp+10h]
  char v92; // [rsp+11Ch] [rbp+1Ch]
  char v93; // [rsp+121h] [rbp+21h]
  char v94; // [rsp+12Ch] [rbp+2Ch]
  char v95; // [rsp+168h] [rbp+68h]
  char v96; // [rsp+1A8h] [rbp+A8h]
  char v97; // [rsp+1E8h] [rbp+E8h]
  char v98; // [rsp+228h] [rbp+128h]
  char v99; // [rsp+268h] [rbp+168h]
  char v100; // [rsp+2B0h] [rbp+1B0h]
  __int128 v101; // [rsp+2C0h] [rbp+1C0h] BYREF
  __int128 v102; // [rsp+2D0h] [rbp+1D0h]
  __int128 v103; // [rsp+2E0h] [rbp+1E0h]
  __int128 v104; // [rsp+2F0h] [rbp+1F0h]
  wil::details::in1diag3 *retaddr; // [rsp+358h] [rbp+258h]

  v1 = this;
  v75 = this;
  v2 = 0;
  LODWORD(v72) = 0;
  LODWORD(v74) = 0;
  if ( dword_180244880 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 32LL) )
  {
    Init_thread_header(&dword_180244880);
    if ( dword_180244880 == -1 )
    {
      SRWLock.Ptr = 0;
      std::unordered_map<unsigned __int64,unsigned __int64>::unordered_map<unsigned __int64,unsigned __int64>(&qword_180244818);
      std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned int const,ForegroundManager::TargetingInfo>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned int const,ForegroundManager::TargetingInfo>>>>>>(&qword_180244858);
      qword_180244870 = 0;
      byte_180244878 = 0;
      atexit(InputSinkDataCache::GetInstance_::_2_::_dynamic_atexit_destructor_for__instance__);
      Init_thread_footer(&dword_180244880);
    }
  }
  AcquireSRWLockExclusive(&SRWLock);
  std::vector<InputProvider>::vector<InputProvider>(&v79, &qword_180244858);
  if ( qword_180244858 != qword_180244860 )
  {
    std::_Destroy_range<std::allocator<NotificationData>>();
    qword_180244860 = qword_180244858;
  }
  ReleaseSRWLockExclusive(&SRWLock);
  if ( v79 != v80 )
  {
    v3 = *((_QWORD *)v1 + 12);
    if ( v3 )
    {
      v4 = (_QWORD *)*((_QWORD *)v1 + 11);
      if ( *((_QWORD *)v1 + 17) >> 3 <= v3 )
      {
        std::_List_node<std::pair<unsigned __int64 const,std::vector<Microsoft::WRL::ComPtr<InputSite>>>,void *>::_Free_non_head<std::allocator<std::_List_node<std::pair<unsigned __int64 const,std::vector<Microsoft::WRL::ComPtr<InputSite>>>,void *>>>(
          v3,
          v4);
        **((_QWORD **)v1 + 11) = *((_QWORD *)v1 + 11);
        *(_QWORD *)(*((_QWORD *)v1 + 11) + 8LL) = *((_QWORD *)v1 + 11);
        *((_QWORD *)v1 + 12) = 0;
        v73 = *((_QWORD *)v1 + 11);
        std::fill<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,IMPCTarget *>>>> *,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,IMPCTarget *>>>>>(
          *((_QWORD *)v1 + 13),
          *((_QWORD *)v1 + 14),
          &v73);
      }
      else
      {
        std::_Hash<std::_Umap_traits<unsigned __int64,std::vector<Microsoft::WRL::ComPtr<InputSite>>,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,std::vector<Microsoft::WRL::ComPtr<InputSite>>>>,0>>::_Unchecked_erase(
          (char *)v1 + 80,
          *v4,
          *((_QWORD *)v1 + 11));
      }
    }
    ++*((_QWORD *)v1 + 18);
  }
  v5 = v79;
  v74 = v79;
  v83 = v80;
  if ( v79 != v80 )
  {
    while ( 1 )
    {
      v71 = v5[1];
      v76[0] = v5[3];
      v11 = *(_DWORD *)v5;
      if ( *(_DWORD *)v5 == 2 )
      {
        _mm_lfence();
        v12 = (_QWORD *)(*((_QWORD *)v1 + 5)
                       + 16
                       * (*((_QWORD *)v1 + 8)
                        & (0x100000001B3LL
                         * (HIBYTE(v71)
                          ^ (0x100000001B3LL
                           * (BYTE6(v71)
                            ^ (0x100000001B3LL
                             * (BYTE5(v71)
                              ^ (0x100000001B3LL
                               * (BYTE4(v71)
                                ^ (0x100000001B3LL
                                 * (BYTE3(v71)
                                  ^ (0x100000001B3LL
                                   * (BYTE2(v71)
                                    ^ (0x100000001B3LL
                                     * (BYTE1(v71) ^ (0x100000001B3LL * ((unsigned __int8)v71 ^ 0xCBF29CE484222325uLL))))))))))))))))));
        v13 = (_QWORD *)v12[1];
        v14 = (_QWORD *)*((_QWORD *)v1 + 3);
        if ( v13 == v14 )
        {
LABEL_23:
          v13 = 0;
        }
        else
        {
          while ( v71 != v13[2] )
          {
            if ( v13 == (_QWORD *)*v12 )
              goto LABEL_23;
            v13 = (_QWORD *)v13[1];
          }
        }
        if ( v13 )
        {
          if ( v13 != v14 )
          {
            v15 = v13[3];
            v16 = *((_OWORD *)v5 + 2);
            v101 = v16;
            v102 = *((_OWORD *)v5 + 3);
            v103 = *((_OWORD *)v5 + 4);
            v104 = *((_OWORD *)v5 + 5);
            if ( *(_BYTE *)(v15 + 480) )
            {
              *(_OWORD *)(v15 + 408) = v16;
              *(_OWORD *)(v15 + 424) = v102;
              *(_OWORD *)(v15 + 440) = v103;
              *(_OWORD *)(v15 + 456) = v104;
              if ( !*(_BYTE *)(v15 + 472) )
                *(_BYTE *)(v15 + 472) = 1;
              std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned int const,ForegroundManager::TargetingInfo>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned int const,ForegroundManager::TargetingInfo>>>>>>(&v77);
              v17 = v2 | 4;
              LODWORD(v74) = v17;
              v72 = 0;
              v19 = *(_QWORD *)(v18 + 488);
              for ( i = *(_QWORD *)(v18 + 496); v19 != i; v19 += 16 )
              {
                v21 = *(int (__fastcall ****)(_QWORD, GUID *, __int64 *))(v19 + 8);
                v22 = **v21;
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v72);
                if ( v22(v21, &GUID_ae83b6cb_def2_49fe_9564_e870d32281a5, &v72) >= 0 )
                {
                  if ( *((_QWORD *)&v77 + 1) == v78 )
                  {
                    std::vector<Microsoft::WRL::ComPtr<IInputSiteTransformClientPrivate>>::_Emplace_reallocate<Microsoft::WRL::ComPtr<IInputSiteTransformClientPrivate> const &>(
                      &v77,
                      *((_QWORD *)&v77 + 1),
                      &v72);
                  }
                  else
                  {
                    **((_QWORD **)&v77 + 1) = v72;
                    if ( v72 )
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 8LL))(v72);
                    *((_QWORD *)&v77 + 1) += 8LL;
                  }
                }
              }
              v23 = v72;
              if ( v72 )
              {
                v72 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
              }
              v25 = (_QWORD *)*((_QWORD *)&v77 + 1);
              v24 = (_QWORD *)v77;
              if ( (_QWORD)v77 != *((_QWORD *)&v77 + 1) )
              {
                do
                {
                  (*(void (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)*v24 + 24LL))(*v24, &v101);
                  ++v24;
                }
                while ( v24 != v25 );
                v24 = (_QWORD *)v77;
              }
              v2 = v17 & 0xFFFFFFFB;
              LODWORD(v72) = v2;
              if ( v24 )
              {
                v26 = (_QWORD *)*((_QWORD *)&v77 + 1);
                if ( v24 != *((_QWORD **)&v77 + 1) )
                {
                  do
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v24++);
                  while ( v24 != v26 );
                  v24 = (_QWORD *)v77;
                }
                std::_Deallocate<16>(v24, (v78 - (_QWORD)v24) & 0xFFFFFFFFFFFFFFF8uLL);
                v77 = 0;
                v78 = 0;
              }
            }
          }
        }
        goto LABEL_40;
      }
      if ( !v11 )
        break;
      v27 = v11 - 1;
      if ( !v27 )
      {
        _mm_lfence();
        v64 = (_QWORD *)(*((_QWORD *)v1 + 5)
                       + 16
                       * (*((_QWORD *)v1 + 8)
                        & (0x100000001B3LL
                         * (HIBYTE(v71)
                          ^ (0x100000001B3LL
                           * (BYTE6(v71)
                            ^ (0x100000001B3LL
                             * (BYTE5(v71)
                              ^ (0x100000001B3LL
                               * (BYTE4(v71)
                                ^ (0x100000001B3LL
                                 * (BYTE3(v71)
                                  ^ (0x100000001B3LL
                                   * (BYTE2(v71)
                                    ^ (0x100000001B3LL
                                     * (BYTE1(v71) ^ (0x100000001B3LL * ((unsigned __int8)v71 ^ 0xCBF29CE484222325uLL))))))))))))))))));
        v65 = (_QWORD *)v64[1];
        v66 = (_QWORD *)*((_QWORD *)v1 + 3);
        if ( v65 == v66 )
        {
LABEL_94:
          v65 = 0;
        }
        else
        {
          while ( v71 != v65[2] )
          {
            if ( v65 == (_QWORD *)*v64 )
              goto LABEL_94;
            v65 = (_QWORD *)v65[1];
          }
        }
        if ( v65 && v65 != v66 )
          InputSiteHierarchyManager::RemoveInputSinkFromParentList(v1, v71, v65[4]);
        v67 = v76[0];
        *(_QWORD *)(*(_QWORD *)std::_Hash<std::_Umap_traits<unsigned __int64,InputSiteHierarchyManager::InputSiteHierarchyEntry,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,InputSiteHierarchyManager::InputSiteHierarchyEntry>>,0>>::_Try_emplace<unsigned __int64 const &,>(
                                 (char *)v1 + 16,
                                 v85,
                                 &v71)
                  + 32LL) = v67;
        v68 = std::_Hash<std::_Umap_traits<unsigned __int64,InputSiteHierarchyManager::InputSiteHierarchyEntry,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,InputSiteHierarchyManager::InputSiteHierarchyEntry>>,0>>::_Try_emplace<unsigned __int64 const &,>(
                (char *)v1 + 16,
                v86,
                v76);
        v62 = *(_QWORD *)v68 + 40LL;
        v63 = *(unsigned __int64 **)(*(_QWORD *)v68 + 48LL);
        if ( v63 == *(unsigned __int64 **)(*(_QWORD *)v68 + 56LL) )
        {
LABEL_99:
          std::vector<InputSite *>::_Emplace_reallocate<InputSite *>(v62, v63, &v71);
          goto LABEL_40;
        }
        goto LABEL_89;
      }
      if ( v27 == 2 )
      {
        _mm_lfence();
        v28 = *((_QWORD *)v1 + 8);
        v29 = *((_QWORD *)v1 + 5);
        v30 = 0x100000001B3LL
            * (BYTE6(v71)
             ^ (0x100000001B3LL
              * (BYTE5(v71)
               ^ (0x100000001B3LL
                * (BYTE4(v71)
                 ^ (0x100000001B3LL
                  * (BYTE3(v71)
                   ^ (0x100000001B3LL
                    * (BYTE2(v71)
                     ^ (0x100000001B3LL
                      * (BYTE1(v71) ^ (0x100000001B3LL * ((unsigned __int8)v71 ^ 0xCBF29CE484222325uLL)))))))))))));
        v31 = *(__int64 **)(v29 + 16 * (v28 & (0x100000001B3LL * (v30 ^ HIBYTE(v71)))) + 8);
        v32 = (__int64 *)*((_QWORD *)v1 + 3);
        if ( v31 == v32 )
        {
LABEL_50:
          v31 = 0;
        }
        else
        {
          while ( v71 != v31[2] )
          {
            if ( v31 == *(__int64 **)(v29 + 16 * (v28 & (0x100000001B3LL * (v30 ^ HIBYTE(v71))))) )
              goto LABEL_50;
            v31 = (__int64 *)v31[1];
          }
        }
        if ( v31 )
        {
          if ( v31 != v32 )
          {
            v33 = 0;
LABEL_54:
            if ( v33 )
              wil::details::in1diag3::FailFast_Hr(
                retaddr,
                (void *)0x77,
                (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\components\\inputsitemanager\\server\\inputsiteh"
                              "ierarchymanager.cpp",
                (const char *)0x8000FFFFLL,
                v71);
            v34 = v31[4];
            v82 = v34;
            v35 = 2
                * (v28
                 & std::_Uhash_compare<IInputTarget *,std::hash<IInputTarget *>,std::equal_to<IInputTarget *>>::operator()<IInputTarget *>(
                     retaddr,
                     &v82,
                     0xCBF29CE484222325uLL));
            v38 = *(_QWORD **)(v29 + 8 * v35 + 8);
            if ( v38 == v37 )
            {
LABEL_59:
              v38 = 0;
            }
            else
            {
              while ( v34 != v38[2] )
              {
                if ( v38 == *(_QWORD **)(v29 + 8 * v35) )
                  goto LABEL_59;
                v38 = (_QWORD *)v38[1];
              }
            }
            if ( v38 )
            {
              if ( v38 != v37 )
              {
                v39 = (_QWORD *)v38[6];
                v40 = (_QWORD *)v38[5];
                if ( v40 != v39 )
                {
                  do
                  {
                    if ( *v40 == v36 )
                      break;
                    ++v40;
                  }
                  while ( v40 != v39 );
                  if ( v40 != v39 )
                  {
                    v41 = v40 + 1;
                    if ( v40 + 1 == v39 )
                      goto LABEL_71;
                    do
                    {
                      if ( *v41 != v36 )
                        *v40++ = *v41;
                      ++v41;
                    }
                    while ( v41 != v39 );
                    if ( v40 != v39 )
                    {
LABEL_71:
                      v42 = v38[6] - (_QWORD)v39;
                      memmove_0(v40, v39, v42);
                      v38[6] = (char *)v40 + v42;
                    }
                  }
                }
              }
            }
            v43 = v31[6];
            for ( j = v31[5]; j != v43; j += 8 )
              *(_QWORD *)(*(_QWORD *)std::_Hash<std::_Umap_traits<unsigned __int64,InputSiteHierarchyManager::InputSiteHierarchyEntry,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,InputSiteHierarchyManager::InputSiteHierarchyEntry>>,0>>::_Try_emplace<unsigned __int64 const &,>(
                                       (char *)v1 + 16,
                                       v84,
                                       j)
                        + 32LL) = 0;
            _mm_lfence();
            v45 = (__int64 **)(*((_QWORD *)v1 + 5)
                             + 16
                             * (*((_QWORD *)v1 + 8)
                              & (0x100000001B3LL
                               * (*((unsigned __int8 *)v31 + 23)
                                ^ (0x100000001B3LL
                                 * (*((unsigned __int8 *)v31 + 22)
                                  ^ (0x100000001B3LL
                                   * (*((unsigned __int8 *)v31 + 21)
                                    ^ (0x100000001B3LL
                                     * (*((unsigned __int8 *)v31 + 20)
                                      ^ (0x100000001B3LL
                                       * (*((unsigned __int8 *)v31 + 19)
                                        ^ (0x100000001B3LL
                                         * (*((unsigned __int8 *)v31 + 18)
                                          ^ (0x100000001B3LL
                                           * (*((unsigned __int8 *)v31 + 17)
                                            ^ (0x100000001B3LL * (*((unsigned __int8 *)v31 + 16) ^ 0xCBF29CE484222325uLL))))))))))))))))));
            v46 = *v45;
            if ( v45[1] == v31 )
            {
              if ( v46 == v31 )
              {
                v47 = (__int64 *)*((_QWORD *)v1 + 3);
                *v45 = v47;
              }
              else
              {
                v47 = (__int64 *)v31[1];
              }
              v45[1] = v47;
            }
            else if ( v46 == v31 )
            {
              *v45 = (__int64 *)*v31;
            }
            v48 = *v31;
            --*((_QWORD *)v1 + 4);
            *(_QWORD *)v31[1] = v48;
            *(_QWORD *)(v48 + 8) = v31[1];
            std::_List_node<std::pair<unsigned __int64 const,InputSiteHierarchyManager::InputSiteHierarchyEntry>,void *>::_Freenode<std::allocator<std::_List_node<std::pair<unsigned __int64 const,InputSiteHierarchyManager::InputSiteHierarchyEntry>,void *>>>(
              v48,
              v31);
            InputSiteManager = ISMStatics::GetInputSiteManager();
            v76[2] = v71;
            v50 = v71;
            v51 = (__int64 *)*((_QWORD *)InputSiteManager + 7);
            v52 = (__int64 *)*((_QWORD *)InputSiteManager + 8);
            if ( v51 == v52 )
            {
              v5 = v74;
              v2 = v72;
              v1 = (InputSiteHierarchyManager *)v75;
            }
            else
            {
              do
              {
                v53 = *v51;
                v54 = *(_DWORD **)(*v51 + 24);
                v55 = *(_DWORD **)(*v51 + 16);
                v56 = v55;
                if ( v55 != v54 )
                {
                  while ( *v56 )
                  {
                    v56 += 4;
                    if ( v56 == v54 )
                      goto LABEL_81;
                  }
                  if ( *((_QWORD *)v56 + 1) == v50 )
                  {
                    do
                    {
                      if ( !*v55 )
                        break;
                      v55 += 4;
                    }
                    while ( v55 != v54 );
                    if ( v55 != v54 )
                    {
                      v69 = v55 + 4;
                      if ( v55 + 4 == v54 )
                        goto LABEL_110;
                      do
                      {
                        if ( *(_DWORD *)v69 )
                        {
                          *(_OWORD *)v55 = *v69;
                          v55 += 4;
                        }
                        ++v69;
                      }
                      while ( v69 != (_OWORD *)v54 );
                      if ( v55 != v54 )
                      {
LABEL_110:
                        v70 = *(_QWORD *)(v53 + 24) - (_QWORD)v54;
                        memmove_0(v55, v54, v70);
                        *(_QWORD *)(v53 + 24) = (char *)v55 + v70;
                      }
                    }
                    std::_Optional_destruct_base<LegacyInputSinkData,0>::reset(v53 + 48);
                  }
                }
LABEL_81:
                ++v51;
              }
              while ( v51 != v52 );
              v5 = v74;
              v2 = v72;
              v1 = (InputSiteHierarchyManager *)v75;
            }
            goto LABEL_40;
          }
        }
        else
        {
          v31 = (__int64 *)*((_QWORD *)v1 + 3);
        }
        v33 = 1;
        goto LABEL_54;
      }
LABEL_40:
      v5 += 12;
      v74 = v5;
      if ( v5 == v83 )
        goto LABEL_10;
    }
    v57 = ISMStatics::GetInputSiteManager();
    v90 = v5[2];
    v5[2] = 0;
    v91 = 1;
    v92 = 0;
    v93 = 0;
    v94 = 0;
    v95 = 0;
    v96 = 0;
    v97 = 0;
    v98 = 0;
    v99 = 0;
    v100 = 0;
    InputSiteManager::GetInputSiteFromInputSinkData(v57, &v73, &v90, 1);
    v2 |= 3u;
    LODWORD(v72) = v2;
    std::_Deleted_copy_assign<std::_Variant_destroy_layer_<void *,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<long (*)(void *),&long NtCloseCompositionInputSink(void *)>>>>,void *,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<long (*)(void *),&long NtCloseCompositionInputSink(void *)>>>>::~_Deleted_copy_assign<std::_Variant_destroy_layer_<void *,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<long (*)(void *),&long NtCloseCompositionInputSink(void *)>>>>,void *,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<long (*)(void *),&long NtCloseCompositionInputSink(void *)>>>>(&v90);
    v58 = (_QWORD *)std::_Hash<std::_Umap_traits<unsigned __int64,InputSiteHierarchyManager::InputSiteHierarchyEntry,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,InputSiteHierarchyManager::InputSiteHierarchyEntry>>,0>>::_Try_emplace<unsigned __int64 const &,>(
                      (char *)v1 + 16,
                      v87,
                      &v71);
    Microsoft::WRL::ComPtr<InputSite>::operator=(*v58 + 24LL, &v73);
    v59 = v73;
    if ( v73 )
    {
      v73 = 0;
      (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v59 + 16LL))(v59);
    }
    v60 = v76[0];
    *(_QWORD *)(*(_QWORD *)std::_Hash<std::_Umap_traits<unsigned __int64,InputSiteHierarchyManager::InputSiteHierarchyEntry,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,InputSiteHierarchyManager::InputSiteHierarchyEntry>>,0>>::_Try_emplace<unsigned __int64 const &,>(
                             (char *)v1 + 16,
                             v88,
                             &v71)
              + 32LL) = v60;
    v61 = std::_Hash<std::_Umap_traits<unsigned __int64,InputSiteHierarchyManager::InputSiteHierarchyEntry,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,InputSiteHierarchyManager::InputSiteHierarchyEntry>>,0>>::_Try_emplace<unsigned __int64 const &,>(
            (char *)v1 + 16,
            v89,
            v76);
    v62 = *(_QWORD *)v61 + 40LL;
    v63 = *(unsigned __int64 **)(*(_QWORD *)v61 + 48LL);
    if ( v63 == *(unsigned __int64 **)(*(_QWORD *)v61 + 56LL) )
      goto LABEL_99;
LABEL_89:
    *v63 = v71;
    *(_QWORD *)(v62 + 8) += 8LL;
    goto LABEL_40;
  }
LABEL_10:
  v6 = v79;
  if ( v79 )
  {
    v7 = v80;
    if ( v79 != v80 )
    {
      do
      {
        v8 = v6[2];
        if ( (unsigned __int64)(v8 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          NtCloseCompositionInputSink(v8);
        v6 += 12;
      }
      while ( v6 != v7 );
    }
    v9 = v79;
    v10 = (const struct std::nothrow_t *)(32 * ((v81 - (__int64)v79) >> 5));
    v73 = (unsigned __int64)v10;
    v75 = v79;
    if ( (unsigned __int64)v10 >= 0x1000 )
    {
      std::_Adjust_manually_vector_aligned(&v75, &v73);
      v9 = v75;
      v10 = (const struct std::nothrow_t *)v73;
    }
    operator delete(v9, v10);
  }
}

```

## disassembly

```asm
0x180023fb0  push    rbp
0x180023fb2  push    rbx
0x180023fb3  push    rsi
0x180023fb4  push    rdi
0x180023fb5  push    r12
0x180023fb7  push    r13
0x180023fb9  push    r14
0x180023fbb  push    r15
0x180023fbd  lea     rbp, [rsp-218h]
0x180023fc5  sub     rsp, 318h
0x180023fcc  mov     rax, cs:__security_cookie
0x180023fd3  xor     rax, rsp
0x180023fd6  mov     [rbp+250h+var_50], rax
0x180023fdd  mov     r13, rcx
0x180023fe0  mov     [rsp+350h+var_310], rcx
0x180023fe5  xor     r12d, r12d
0x180023fe8  mov     dword ptr [rsp+350h+var_328], r12d
0x180023fed  mov     dword ptr [rsp+350h+var_318], r12d
0x180023ff2  mov     edx, cs:_tls_index
0x180023ff8  mov     rax, gs:58h
0x180024001  mov     ecx, 20h ; ' '
0x180024006  mov     rax, [rax+rdx*8]
0x18002400a  mov     eax, [rcx+rax]
0x18002400d  cmp     cs:dword_180244880, eax
0x180024013  jg      loc_180024A19
0x180024019  lea     rcx, SRWLock; SRWLock
0x180024020  call    cs:__imp_AcquireSRWLockExclusive
0x180024026  lea     rdx, qword_180244858
0x18002402d  lea     rcx, [rsp+350h+var_2D8]
0x180024032  call    ??0?$vector@UInputProvider@@V?$allocator@UInputProvider@@@std@@@std@@QEAA@$$QEAV01@@Z; std::vector<InputProvider>::vector<InputProvider>(std::vector<InputProvider> &&)
0x180024037  mov     rdx, cs:qword_180244860
0x18002403e  mov     rcx, cs:qword_180244858
0x180024045  cmp     rcx, rdx
0x180024048  jnz     loc_180024A83
0x18002404e  lea     rcx, SRWLock; SRWLock
0x180024055  call    cs:__imp_ReleaseSRWLockExclusive
0x18002405b  nop
0x18002405c  mov     rax, [rbp+250h+var_2D0]
0x180024060  cmp     [rsp+350h+var_2D8], rax
0x180024065  jz      short loc_18002409E
0x180024067  mov     rcx, [r13+60h]
0x18002406b  test    rcx, rcx
0x18002406e  jz      short loc_180024097
0x180024070  mov     rdx, [r13+58h]
0x180024074  mov     rax, [r13+88h]
0x18002407b  shr     rax, 3
0x18002407f  cmp     rax, rcx
0x180024082  jbe     loc_180024492
0x180024088  mov     r8, rdx
0x18002408b  mov     rdx, [rdx]
0x18002408e  lea     rcx, [r13+50h]
0x180024092  call    ?_Unchecked_erase@?$_Hash@V?$_Umap_traits@_KV?$vector@V?$ComPtr@VInputSite@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VInputSite@@@WRL@Microsoft@@@std@@@std@@V?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@2@V?$allocator@U?$pair@$$CB_KV?$vector@V?$ComPtr@VInputSite@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VInputSite@@@WRL@Microsoft@@@std@@@std@@@std@@@2@$0A@@std@@@std@@AEAAPEAU?$_List_node@U?$pair@$$CB_KV?$vector@V?$ComPtr@VInputSite@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VInputSite@@@WRL@Microsoft@@@std@@@std@@@std@@PEAX@2@PEAU32@QEAU32@@Z; std::_Hash<std::_Umap_traits<unsigned __int64,std::vector<Microsoft::WRL::ComPtr<InputSite>>,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,std::vector<Microsoft::WRL::ComPtr<InputSite>>>>,0>>::_Unchecked_erase(std::_List_node<std::pair<unsigned __int64 const,std::vector<Microsoft::WRL::ComPtr<InputSite>>>,void *> *,std::_List_node<std::pair<unsigned __int64 const,std::vector<Microsoft::WRL::ComPtr<InputSite>>>,void *> * const)
0x180024097  inc     qword ptr [r13+90h]
0x18002409e  mov     r15, [rsp+350h+var_2D8]
0x1800240a3  mov     [rsp+350h+var_318], r15
0x1800240a8  mov     rax, [rbp+250h+var_2D0]
0x1800240ac  mov     [rbp+250h+var_2B8], rax
0x1800240b0  cmp     r15, rax
0x1800240b3  jnz     loc_180024152
0x1800240b9  mov     rbx, [rsp+350h+var_2D8]
0x1800240be  test    rbx, rbx
0x1800240c1  jnz     short loc_1800240E6
0x1800240c3  mov     rcx, [rbp+250h+var_50]
0x1800240ca  xor     rcx, rsp; StackCookie
0x1800240cd  call    __security_check_cookie
0x1800240d2  add     rsp, 318h
0x1800240d9  pop     r15
0x1800240db  pop     r14
0x1800240dd  pop     r13
0x1800240df  pop     r12
0x1800240e1  pop     rdi
0x1800240e2  pop     rsi
0x1800240e3  pop     rbx
0x1800240e4  pop     rbp
0x1800240e5  retn
0x1800240e6  mov     rdi, [rbp+250h+var_2D0]
0x1800240ea  cmp     rbx, rdi
0x1800240ed  jz      short loc_18002410B
0x1800240ef  nop
0x1800240f0  mov     rcx, [rbx+10h]
0x1800240f4  lea     rax, [rcx-1]
0x1800240f8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800240fc  jbe     loc_180024713
0x180024102  add     rbx, 60h ; '`'
0x180024106  cmp     rbx, rdi
0x180024109  jnz     short loc_1800240F0
0x18002410b  mov     rcx, [rsp+350h+var_2D8]; void *
0x180024110  mov     rax, [rbp+250h+var_2C8]
0x180024114  sub     rax, rcx
0x180024117  sar     rax, 5
0x18002411b  mov     rdx, 0AAAAAAAAAAAAAAABh
0x180024125  imul    rax, rdx
0x180024129  lea     rdx, [rax+rax*2]
0x18002412d  shl     rdx, 5; struct std::nothrow_t *
0x180024131  mov     [rsp+350h+var_320], rdx
0x180024136  mov     [rsp+350h+var_310], rcx
0x18002413b  cmp     rdx, 1000h
0x180024142  jnb     loc_180024747
0x180024148  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002414d  jmp     loc_1800240C3
0x180024152  mov     rbx, 100000001B3h
0x18002415c  mov     r8, 0CBF29CE484222325h
0x180024166  mov     rax, [r15+8]
0x18002416a  mov     [rsp+350h+var_330], rax; int
0x18002416f  mov     rax, [r15+18h]
0x180024173  mov     [rsp+350h+var_308], rax
0x180024178  mov     ecx, [r15]
0x18002417b  cmp     ecx, 2
0x18002417e  jnz     loc_1800243C7
0x180024184  lfence
0x180024187  mov     r9, [rsp+350h+var_330]
0x18002418c  movzx   ecx, r9b
0x180024190  xor     r8, rcx
0x180024193  imul    r8, rbx
0x180024197  movzx   eax, byte ptr [rsp+350h+var_330+1]
0x18002419c  xor     r8, rax
0x18002419f  imul    r8, rbx
0x1800241a3  movzx   eax, byte ptr [rsp+350h+var_330+2]
0x1800241a8  xor     r8, rax
0x1800241ab  imul    r8, rbx
0x1800241af  movzx   eax, byte ptr [rsp+350h+var_330+3]
0x1800241b4  xor     r8, rax
0x1800241b7  imul    r8, rbx
0x1800241bb  movzx   eax, byte ptr [rsp+350h+var_330+4]
0x1800241c0  xor     r8, rax
0x1800241c3  imul    r8, rbx
0x1800241c7  movzx   eax, byte ptr [rsp+350h+var_330+5]
0x1800241cc  xor     r8, rax
0x1800241cf  imul    r8, rbx
0x1800241d3  movzx   eax, byte ptr [rsp+350h+var_330+6]
0x1800241d8  xor     r8, rax
0x1800241db  imul    r8, rbx
0x1800241df  movzx   eax, byte ptr [rsp+350h+var_330+7]
0x1800241e4  xor     r8, rax
0x1800241e7  imul    r8, rbx
0x1800241eb  and     r8, [r13+40h]
0x1800241ef  shl     r8, 4
0x1800241f3  add     r8, [r13+28h]
0x1800241f7  mov     rdx, [r8+8]
0x1800241fb  mov     rax, [r13+18h]
0x1800241ff  cmp     rdx, rax
0x180024202  jz      short loc_180024215
0x180024204  cmp     r9, [rdx+10h]
0x180024208  jz      short loc_180024217
0x18002420a  cmp     rdx, [r8]
0x18002420d  jz      short loc_180024215
0x18002420f  mov     rdx, [rdx+8]
0x180024213  jmp     short loc_180024204
0x180024215  xor     edx, edx
0x180024217  test    rdx, rdx
0x18002421a  jz      loc_1800243A5
0x180024220  cmp     rdx, rax
0x180024223  jz      loc_1800243A5
0x180024229  mov     rdx, [rdx+18h]
0x18002422d  movups  xmm2, xmmword ptr [r15+20h]
0x180024232  movaps  [rbp+250h+var_90], xmm2
0x180024239  movups  xmm0, xmmword ptr [r15+30h]
0x18002423e  movaps  [rbp+250h+var_80], xmm0
0x180024245  movups  xmm1, xmmword ptr [r15+40h]
0x18002424a  movaps  [rbp+250h+var_70], xmm1
0x180024251  movups  xmm0, xmmword ptr [r15+50h]
0x180024256  movaps  [rbp+250h+var_60], xmm0
0x18002425d  cmp     byte ptr [rdx+1E0h], 0
0x180024264  jz      loc_1800243A5
0x18002426a  movups  xmmword ptr [rdx+198h], xmm2
0x180024271  movaps  xmm0, [rbp+250h+var_80]
0x180024278  movups  xmmword ptr [rdx+1A8h], xmm0
0x18002427f  movaps  xmm1, [rbp+250h+var_70]
0x180024286  movups  xmmword ptr [rdx+1B8h], xmm1
0x18002428d  movaps  xmm0, [rbp+250h+var_60]
0x180024294  movups  xmmword ptr [rdx+1C8h], xmm0
0x18002429b  cmp     byte ptr [rdx+1D8h], 0
0x1800242a2  jz      loc_18002473B
0x1800242a8  lea     rcx, [rsp+350h+var_2F0]
0x1800242ad  call    ??$?0AEBV?$allocator@U?$pair@$$CBIUTargetingInfo@ForegroundManager@@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBIUTargetingInfo@ForegroundManager@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@AEBV?$allocator@U?$pair@$$CBIUTargetingInfo@ForegroundManager@@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<uint const,ForegroundManager::TargetingInfo>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<uint const,ForegroundManager::TargetingInfo>>>>>>(std::allocator<std::pair<uint const,ForegroundManager::TargetingInfo>> const &)
0x1800242b2  or      r12d, 4
0x1800242b6  mov     dword ptr [rsp+350h+var_318], r12d
0x1800242bb  mov     [rsp+350h+var_328], 0
0x1800242c4  mov     rsi, [rdx+1E8h]
0x1800242cb  mov     r14, [rdx+1F0h]
0x1800242d2  cmp     rsi, r14
0x1800242d5  jz      short loc_180024314
0x1800242d7  mov     rdi, [rsi+8]
0x1800242db  mov     rax, [rdi]
0x1800242de  mov     rbx, [rax]
0x1800242e1  lea     rcx, [rsp+350h+var_328]
0x1800242e6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800242eb  lea     r8, [rsp+350h+var_328]
0x1800242f0  lea     rdx, _GUID_ae83b6cb_def2_49fe_9564_e870d32281a5
0x1800242f7  mov     rcx, rdi
0x1800242fa  mov     rax, rbx
0x1800242fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024302  nop
0x180024303  test    eax, eax
0x180024305  jns     loc_180024ACE
0x18002430b  add     rsi, 10h
0x18002430f  cmp     rsi, r14
0x180024312  jnz     short loc_1800242D7
0x180024314  mov     rcx, [rsp+350h+var_328]
0x180024319  test    rcx, rcx
0x18002431c  jz      short loc_180024334
0x18002431e  mov     [rsp+350h+var_328], 0
0x180024327  mov     rax, [rcx]
0x18002432a  mov     rax, [rax+10h]
0x18002432e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024333  nop
0x180024334  mov     rbx, qword ptr [rsp+350h+var_2F0]
0x180024339  mov     rdi, qword ptr [rsp+350h+var_2F0+8]
0x18002433e  cmp     rbx, rdi
0x180024341  jnz     loc_180024AF2
0x180024347  and     r12d, 0FFFFFFFBh
0x18002434b  mov     dword ptr [rsp+350h+var_328], r12d
0x180024350  test    rbx, rbx
0x180024353  jz      short loc_18002439B
0x180024355  mov     rdi, qword ptr [rsp+350h+var_2F0+8]
0x18002435a  cmp     rbx, rdi
0x18002435d  jz      short loc_180024375
0x18002435f  mov     rcx, rbx
0x180024362  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180024367  add     rbx, 8
0x18002436b  cmp     rbx, rdi
0x18002436e  jnz     short loc_18002435F
0x180024370  mov     rbx, qword ptr [rsp+350h+var_2F0]
0x180024375  mov     rdx, [rsp+350h+var_2E0]
0x18002437a  sub     rdx, rbx
0x18002437d  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180024381  mov     rcx, rbx
0x180024384  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180024389  xorps   xmm0, xmm0
0x18002438c  movdqu  [rsp+350h+var_2F0], xmm0
0x180024392  mov     [rsp+350h+var_2E0], 0
0x18002439b  mov     rbx, 100000001B3h
0x1800243a5  mov     r8, 0CBF29CE484222325h
0x1800243af  add     r15, 60h ; '`'
0x1800243b3  mov     [rsp+350h+var_318], r15
0x1800243b8  cmp     r15, [rbp+250h+var_2B8]
0x1800243bc  jz      loc_1800240B9
0x1800243c2  jmp     loc_180024166
0x1800243c7  test    ecx, ecx
0x1800243c9  jz      loc_180024765
0x1800243cf  sub     ecx, 1
0x1800243d2  jz      loc_180024873
0x1800243d8  cmp     ecx, 2
0x1800243db  jnz     short loc_1800243AF
0x1800243dd  lfence
0x1800243e0  mov     rsi, [r13+40h]
0x1800243e4  mov     rdi, [r13+28h]
0x1800243e8  mov     r10, [rsp+350h+var_330]
0x1800243ed  movzx   edx, r10b
0x1800243f1  xor     rdx, r8
0x1800243f4  imul    rdx, rbx
0x1800243f8  mov     rax, r10
0x1800243fb  shr     rax, 8
0x1800243ff  movzx   ecx, al
0x180024402  xor     rdx, rcx
0x180024405  imul    rdx, rbx
0x180024409  mov     rax, r10
0x18002440c  shr     rax, 10h
0x180024410  movzx   ecx, al
0x180024413  xor     rdx, rcx
0x180024416  imul    rdx, rbx
0x18002441a  mov     rax, r10
0x18002441d  shr     rax, 18h
0x180024421  movzx   ecx, al
0x180024424  xor     rdx, rcx
0x180024427  imul    rdx, rbx
0x18002442b  mov     rax, r10
0x18002442e  shr     rax, 20h
0x180024432  movzx   ecx, al
0x180024435  xor     rdx, rcx
0x180024438  imul    rdx, rbx
0x18002443c  mov     rax, r10
0x18002443f  shr     rax, 28h
0x180024443  movzx   ecx, al
0x180024446  xor     rdx, rcx
0x180024449  imul    rdx, rbx
0x18002444d  mov     rax, r10
0x180024450  shr     rax, 30h
0x180024454  movzx   ecx, al
0x180024457  xor     rdx, rcx
0x18002445a  imul    rdx, rbx
0x18002445e  mov     rax, r10
0x180024461  shr     rax, 38h
0x180024465  xor     rax, rdx
0x180024468  imul    rax, rbx
0x18002446c  and     rax, rsi
0x18002446f  add     rax, rax
0x180024472  mov     r14, [rdi+rax*8+8]
0x180024477  mov     r11, [r13+18h]
0x18002447b  cmp     r14, r11
0x18002447e  jz      short loc_1800244CE
0x180024480  cmp     r10, [r14+10h]
0x180024484  jz      short loc_1800244D1
0x180024486  cmp     r14, [rdi+rax*8]
0x18002448a  jz      short loc_1800244CE
0x18002448c  mov     r14, [r14+8]
0x180024490  jmp     short loc_180024480
0x180024492  call    ??$_Free_non_head@V?$allocator@U?$_List_node@U?$pair@$$CB_KV?$vector@V?$ComPtr@VInputSite@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VInputSite@@@WRL@Microsoft@@@std@@@std@@@std@@PEAX@std@@@std@@@?$_List_node@U?$pair@$$CB_KV?$vector@V?$ComPtr@VInputSite@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VInputSite@@@WRL@Microsoft@@@std@@@std@@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@U?$pair@$$CB_KV?$vector@V?$ComPtr@VInputSite@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VInputSite@@@WRL@Microsoft@@@std@@@std@@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::pair<unsigned __int64 const,std::vector<Microsoft::WRL::ComPtr<InputSite>>>,void *>::_Free_non_head<std::allocator<std::_List_node<std::pair<unsigned __int64 const,std::vector<Microsoft::WRL::ComPtr<InputSite>>>,void *>>>(std::allocator<std::_List_node<std::pair<unsigned __int64 const,std::vector<Microsoft::WRL::ComPtr<InputSite>>>,void *>> &,std::_List_node<std::pair<unsigned __int64 const,std::vector<Microsoft::WRL::ComPtr<InputSite>>>,void *> *)
0x180024497  mov     rax, [r13+58h]
0x18002449b  mov     [rax], rax
  ... truncated ...
```
