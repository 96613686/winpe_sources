# NetworkIncident::FindRepairOptions(int *,int * *)

- ea: `0x18000b098`
- end: `0x18000bc98`
- name: `?FindRepairOptions@NetworkIncident@@QEAAJPEAHPEAPEAH@Z`
- size: `3072`
- prototype: `__int64 __fastcall(NetworkIncident *__hidden this, int *, int **)`
- caller_count: `1`
- callee_count: `20`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180018ae4`

## callees

- `0x1800035a8`
- `0x18000579c`
- `0x180005ff8`
- `0x180006d58`
- `0x180008354`
- `0x1800083a0`
- `0x1800083e0`
- `0x180008d38`
- `0x18000ac48`
- `0x18000ade4`
- `0x18000b098`
- `0x18000bca0`
- `0x18000d634`
- `0x18001006c`
- `0x1800101f0`
- `0x180010254`
- `0x180010368`
- `0x18002c802`
- `0x18002c840`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ba24`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ba24`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b2ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000bc45`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b2ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000bc45`

## string_xrefs

- `0x18000b35b`: `%s returned 0 repairs (E_NOTIMPL).`
- `0x18000b37a`: `GetRepairInfo failed for %s. HR:0x%x`
- `0x18000b3d6`: `%s returned %i repairs %s.`
- `0x18000b57a`: `Leaf node is not confirmed and does not have repairs. Removed from tree. Helper Class: %s`
- `0x18000b596`: `Leaf node is confirmed but without repairs. Verifying whether it should be surfaced. Helper Class: %s`
- `0x18000b699`: `Confirmed leaf node without repairs has cache hits in its path, will not add as Root Cause. Helper Class: %s`
- `0x18000b8e9`: `Leaf node already in root cause list. Helper Class: %s`
- `0x18000b9ed`: `Warning: Maximum number of repairs reached (%i), some repairs may not be available.`

## pseudocode

```c
__int64 __fastcall NetworkIncident::FindRepairOptions(NetworkIncident *this, int *a2, int **a3)
{
  NetworkIncident *v3; // r15
  unsigned int v4; // esi
  __int64 v5; // r8
  __int64 **v6; // rdi
  struct ProblemNode *v7; // r13
  __int64 *v8; // rbx
  __int64 *v9; // rbx
  int v10; // ecx
  int v11; // ecx
  unsigned int *v12; // r12
  LPVOID *v13; // r14
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  int v17; // ecx
  int v18; // ecx
  int v19; // ecx
  int v20; // r13d
  __int64 v21; // r8
  unsigned int i; // edx
  __int64 v23; // r8
  __int64 v24; // r9
  __int64 v25; // rbx
  unsigned int j; // ebx
  unsigned int *v27; // r12
  struct ProblemNode *v28; // r14
  __int64 *v29; // rax
  __int64 v30; // r8
  __int64 v31; // rbx
  _QWORD *v32; // rbx
  NetworkIncident *v33; // rbx
  unsigned int *v34; // rbx
  char *v35; // r13
  _QWORD *v36; // rdi
  struct ProblemNode *v37; // rax
  LPVOID *v38; // rdi
  int v39; // edi
  unsigned int v40; // ecx
  char *v41; // r13
  __int64 v42; // r8
  __int64 *v43; // rax
  __int64 v44; // r8
  __int64 **v45; // rbx
  int *v46; // rax
  LPVOID *v47; // r13
  int v48; // ebx
  __int64 v49; // rcx
  unsigned int v50; // edx
  __int64 v51; // r8
  _DWORD *v52; // r9
  unsigned int v53; // r8d
  _DWORD *v54; // rax
  bool v55; // zf
  struct ProblemNode *LCA; // rdx
  __int64 v57; // rcx
  __int64 v58; // rcx
  __int64 v59; // rdx
  _QWORD **v60; // rbx
  int v62; // [rsp+30h] [rbp-288h]
  unsigned int v63; // [rsp+30h] [rbp-288h]
  unsigned int *v64; // [rsp+38h] [rbp-280h]
  int v65; // [rsp+38h] [rbp-280h]
  int *v66; // [rsp+40h] [rbp-278h]
  __int64 v67; // [rsp+48h] [rbp-270h] BYREF
  int **v68; // [rsp+50h] [rbp-268h]
  __int64 **v69; // [rsp+58h] [rbp-260h] BYREF
  struct ProblemNode *v70; // [rsp+60h] [rbp-258h] BYREF
  unsigned int *v71; // [rsp+68h] [rbp-250h]
  NetworkIncident *v72; // [rsp+70h] [rbp-248h]
  int *v73; // [rsp+78h] [rbp-240h]
  int **v74; // [rsp+80h] [rbp-238h]
  _DWORD *v75; // [rsp+88h] [rbp-230h] BYREF
  NetworkIncident *v76; // [rsp+90h] [rbp-228h] BYREF
  LPVOID *v77; // [rsp+98h] [rbp-220h] BYREF
  __int128 v78; // [rsp+A0h] [rbp-218h] BYREF
  __int64 v79; // [rsp+B0h] [rbp-208h]
  char *v80; // [rsp+C0h] [rbp-1F8h] BYREF
  __int64 *v81; // [rsp+C8h] [rbp-1F0h] BYREF
  __int64 v82; // [rsp+D0h] [rbp-1E8h]
  unsigned __int64 v83; // [rsp+D8h] [rbp-1E0h]
  __int128 v84; // [rsp+E0h] [rbp-1D8h] BYREF
  __int64 v85; // [rsp+F0h] [rbp-1C8h]
  NetworkIncident *v86; // [rsp+F8h] [rbp-1C0h]
  NetworkIncident *v87; // [rsp+100h] [rbp-1B8h]
  _QWORD v88[4]; // [rsp+108h] [rbp-1B0h] BYREF
  __int64 v89; // [rsp+128h] [rbp-190h]
  _BYTE v90[32]; // [rsp+130h] [rbp-188h] BYREF
  unsigned __int16 v91[128]; // [rsp+150h] [rbp-168h] BYREF
  __int64 v92; // [rsp+250h] [rbp-68h] BYREF
  ATL::CAtlException *v93; // [rsp+258h] [rbp-60h] BYREF
  ATL::CAtlException *v94; // [rsp+260h] [rbp-58h] BYREF
  ATL::CAtlException *v95; // [rsp+268h] [rbp-50h] BYREF
  ATL::CAtlException *v96; // [rsp+270h] [rbp-48h] BYREF

  v68 = a3;
  v66 = a2;
  v3 = this;
  v86 = this;
  v72 = this;
  v73 = a2;
  v74 = a3;
  v4 = 0;
  if ( !a2 || !a3 )
    return 2147942487LL;
  v76 = this;
  v87 = this;
  v75 = (_DWORD *)((char *)this + 112);
  *((_DWORD *)this + 28) = 0;
  *a2 = 0;
  *a3 = 0;
  std::queue<int>::queue<int,std::deque<int>>(v88);
  v84 = 0;
  v85 = 0;
  std::deque<ProblemNode *>::push_back(v88, v3);
  while ( v89 && *((_DWORD *)v3 + 6) != 13 )
  {
    std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<ProblemNode *>>>::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<ProblemNode *>>>(
      (std::_Iterator_base12 *)v90,
      v89 + v88[3],
      (const struct std::_Container_base12 *)v88);
    std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<ProblemNode *>>>::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<ProblemNode *>>>(
      &v78,
      v90);
    --v79;
    std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<ProblemNode *>>>::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<ProblemNode *>>>(
      &v81,
      &v78);
    if ( v81 )
      v5 = *v81;
    else
      v5 = 0;
    v69 = *(__int64 ***)(*(_QWORD *)(*(_QWORD *)(v5 + 8) + 8 * ((v83 >> 1) & (*(_QWORD *)(v5 + 16) - 1LL)))
                       + 8 * (v83 & 1));
    v6 = v69;
    std::deque<ProblemNode *>::pop_back(v88);
    if ( *((_DWORD *)v6 + 24) != 1 )
    {
      *((_DWORD *)v6 + 24) = 1;
      v7 = (struct ProblemNode *)((char *)v6 + 44);
      v70 = (struct ProblemNode *)((char *)v6 + 44);
      ++*((_DWORD *)v6 + 11);
      v62 = 1;
      v8 = v6[6];
      while ( 1 )
      {
        v8 = (__int64 *)*v8;
        if ( v8 == v6[6] )
          break;
        if ( *(_DWORD *)(v8[2] + 96) != 1 )
        {
          std::deque<ProblemNode *>::push_back(v88, v8 + 2);
          v62 = 0;
        }
      }
      v9 = *v6;
      v10 = *((_DWORD *)v6 + 7);
      if ( ((v10 - 1) & 0xFFFFFFFC) != 0 || v10 == 3 )
        v11 = *((_DWORD *)v9 + 25);
      else
        v11 = *((_DWORD *)v9 + 24);
      v12 = (unsigned int *)(v9 + 13);
      v71 = (unsigned int *)(v9 + 13);
      v13 = (LPVOID *)(v9 + 14);
      v77 = (LPVOID *)(v9 + 14);
      v14 = v11 - 3;
      if ( !v14 )
        goto LABEL_187;
      v15 = v14 - 1;
      if ( !v15 )
        goto LABEL_50;
      v16 = v15 - 1;
      if ( !v16 )
        goto LABEL_50;
      v17 = v16 - 1;
      if ( !v17 )
        goto LABEL_50;
      v18 = v17 - 3;
      if ( v18 && (v19 = v18 - 1) != 0 )
      {
        if ( v19 == 1 )
        {
          *v12 = 0;
          if ( *v13 )
            CoTaskMemFree(*v13);
          *v13 = 0;
          goto LABEL_50;
        }
      }
      else
      {
LABEL_187:
        if ( *v13 )
        {
          FreeRepairInfos((struct tagRepairInfo *)*v13, *v12, 1);
          *v12 = 0;
          *v13 = 0;
        }
        v20 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *, __int64 *))(*(_QWORD *)v9[9] + 88LL))(
                v9[9],
                *((unsigned int *)v6 + 7),
                v9 + 13,
                v9 + 14);
        *v75 += *v12;
        if ( *((_QWORD *)v3 + 27) )
        {
          if ( __eh34_try(-1, 0) )
          {
            __eh34_scope_strut(0);
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v67);
            if ( v20 >= 0 )
            {
              for ( i = 0; i < *v12 && *((int *)*v13 + 28 * i + 10) >= 0; ++i )
                ;
              v23 = v9[2];
              if ( !*(_DWORD *)(v23 - 16) )
                v23 = *v9;
              ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
                (__int64)&v67,
                (__int64)L"%s returned %i repairs %s.",
                v23);
            }
            else
            {
              v21 = v9[2];
              if ( v20 == -2147467263 )
              {
                if ( !*(_DWORD *)(v21 - 16) )
                  v21 = *v9;
                ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
                  (__int64)&v67,
                  (__int64)L"%s returned 0 repairs (E_NOTIMPL).",
                  v21);
              }
              else
              {
                if ( !*(_DWORD *)(v21 - 16) )
                  v21 = *v9;
                ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
                  (__int64)&v67,
                  (__int64)L"GetRepairInfo failed for %s. HR:0x%x",
                  v21,
                  (unsigned int)v20);
              }
            }
            v24 = v9[5];
            v25 = v67;
            (*(void (__fastcall **)(_QWORD, _QWORD, __int64, __int64))(**((_QWORD **)v3 + 27) + 112LL))(
              *((_QWORD *)v3 + 27),
              0,
              v67,
              v24);
            ATL::CStringData::Release((ATL::CStringData *)(v25 - 24));
          }
          if ( __eh34_catch(0) )
          {
            if ( __eh34_catch_type(0, &ATL::CAtlException `RTTI Type Descriptor', (ATL::CAtlException *)&v92) )
            {
              v4 = 0;
              v6 = v69;
              v12 = v71;
              v13 = v77;
              v3 = v72;
              v66 = v73;
              v68 = v74;
              __eh34_try_continuation(0, &ATL::CAtlException `RTTI Type Descriptor', &loc_18000B415);
            }
          }
        }
        if ( v20 >= 0 )
        {
          v7 = v70;
LABEL_50:
          if ( *v12 )
          {
            if ( v6[7] )
              *((_DWORD *)*v13 + 10) |= 0x40000000u;
            if ( *((_QWORD *)v3 + 15) )
            {
              if ( *v13 )
              {
                if ( *(_DWORD *)v7 == 1 )
                {
                  for ( j = 0; j < *v12; ++j )
                  {
                    v78 = *((_OWORD *)*v13 + 7 * j);
                    (*(void (__fastcall **)(_QWORD, __int128 *))(**((_QWORD **)v3 + 15) + 168LL))(
                      *((_QWORD *)v3 + 15),
                      &v78);
                  }
                }
              }
            }
          }
        }
        if ( !v6[7] || v62 )
          std::vector<CHostDLLInfo *>::push_back(&v84, &v69);
      }
    }
  }
  v63 = 0;
  v27 = (unsigned int *)((char *)v76 + 216);
  while ( v63 < (unsigned __int64)((__int64)(*((_QWORD *)&v84 + 1) - v84) >> 3) )
  {
    v28 = *(struct ProblemNode **)(v84 + 8LL * v63);
    v70 = v28;
    if ( *(_DWORD *)(*(_QWORD *)v28 + 104LL) || v28 == *(struct ProblemNode **)v86 )
      goto LABEL_95;
    v27 = (unsigned int *)((char *)v3 + 216);
    v64 = (unsigned int *)((char *)v3 + 216);
    if ( *((_QWORD *)v3 + 27) )
    {
      if ( __eh34_try(-1, 2) )
      {
        __eh34_scope_strut(2);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v67);
        v29 = *(__int64 **)v28;
        v30 = *(_QWORD *)(*(_QWORD *)v28 + 16LL);
        if ( *(_DWORD *)(*(_QWORD *)v28 + 236LL) == 1 )
        {
          if ( !*(_DWORD *)(v30 - 16) )
            v30 = *v29;
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
            (__int64)&v67,
            (__int64)L"Leaf node is confirmed but without repairs. Verifying whether it should be surfaced. Helper Class: %s",
            v30);
        }
        else
        {
          if ( !*(_DWORD *)(v30 - 16) )
            v30 = *v29;
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
            (__int64)&v67,
            (__int64)L"Leaf node is not confirmed and does not have repairs. Removed from tree. Helper Class: %s",
            v30);
        }
        v31 = v67;
        (*(void (__fastcall **)(_QWORD, _QWORD, __int64, _QWORD))(**(_QWORD **)v27 + 112LL))(
          *(_QWORD *)v27,
          0,
          v67,
          *(_QWORD *)(*(_QWORD *)v28 + 40LL));
        ATL::CStringData::Release((ATL::CStringData *)(v31 - 24));
      }
      if ( __eh34_catch(2) )
      {
        if ( __eh34_catch_type(2, &ATL::CAtlException `RTTI Type Descriptor', &v93) )
        {
          v4 = 0;
          v28 = v70;
          v27 = (unsigned int *)((char *)v3 + 216);
          v3 = v72;
          v66 = v73;
          v68 = v74;
          __eh34_try_continuation(2, &ATL::CAtlException `RTTI Type Descriptor', &loc_18000B5D5);
        }
      }
    }
    if ( *(_DWORD *)(*(_QWORD *)v28 + 236LL) == 1 )
    {
      if ( *((_QWORD *)v28 + 7) )
      {
        v32 = (_QWORD *)*((_QWORD *)v28 + 6);
        while ( 1 )
        {
          v32 = (_QWORD *)*v32;
          if ( v32 == *((_QWORD **)v28 + 6) )
            break;
          v81 = (__int64 *)v32[2];
          v82 = 0;
          if ( (int)IterateOverNodes(1, v28, &v81, SearchForNode, 1) >= 0 && !(_DWORD)v82 )
          {
            if ( *(_QWORD *)v27 )
            {
              ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v76);
              if ( __eh34_try(-1, 4) )
              {
                __eh34_scope_strut(4);
                ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
                  (__int64)&v76,
                  (__int64)L"Confirmed leaf node without repairs has cache hits in its path, will not add as Root Cause. Helper Class: %s");
                v33 = v76;
                (*(void (__fastcall **)(_QWORD, _QWORD, NetworkIncident *, _QWORD))(**(_QWORD **)v27 + 112LL))(
                  *(_QWORD *)v27,
                  0,
                  v76,
                  *(_QWORD *)(*(_QWORD *)v28 + 40LL));
                ATL::CStringData::Release((NetworkIncident *)((char *)v33 - 24));
              }
              if ( __eh34_catch(4) )
              {
                if ( __eh34_catch_type(4, &ATL::CAtlException `RTTI Type Descriptor', &v94) )
                {
                  v4 = 0;
                  v27 = v64;
                  v3 = v72;
                  v66 = v73;
                  v68 = v74;
                  __eh34_try_continuation(4, &ATL::CAtlException `RTTI Type Descriptor', &loc_18000B6E1);
                }
              }
            }
            goto LABEL_112;
          }
        }
      }
LABEL_95:
      v39 = 0;
      v65 = 0;
      v40 = 0;
      v41 = (char *)v87 + 32;
      v80 = (char *)v87 + 32;
      v42 = *((_QWORD *)v87 + 4);
      while ( v40 < (unsigned __int64)((*((_QWORD *)v87 + 5) - v42) >> 3) )
      {
        if ( *(struct ProblemNode **)(v42 + 8LL * v40) == v28 )
        {
          v39 = 1;
          v65 = 1;
          break;
        }
        ++v40;
      }
      v27 = (unsigned int *)((char *)v3 + 216);
      v71 = (unsigned int *)((char *)v3 + 216);
      if ( *((_QWORD *)v3 + 27) )
      {
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v69);
        if ( __eh34_try(-1, 8) )
        {
          __eh34_scope_strut(8);
          v43 = *(__int64 **)v28;
          v44 = *(_QWORD *)(*(_QWORD *)v28 + 16LL);
          if ( v39 )
          {
            if ( !*(_DWORD *)(v44 - 16) )
              v44 = *v43;
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
              (__int64)&v69,
              (__int64)L"Leaf node already in root cause list. Helper Class: %s",
              v44);
          }
          else
          {
            if ( !*(_DWORD *)(v44 - 16) )
              v44 = *v43;
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
              (__int64)&v69,
              (__int64)L"Leaf node added to root cause list. Helper Class: %s",
              v44);
          }
          v45 = v69;
          (*(void (__fastcall **)(_QWORD, _QWORD, __int64 **, _QWORD))(**(_QWORD **)v27 + 112LL))(
            *(_QWORD *)v27,
            0,
            v69,
            *(_QWORD *)(*(_QWORD *)v28 + 40LL));
          ATL::CStringData::Release((ATL::CStringData *)(v45 - 3));
        }
        if ( __eh34_catch(8) )
        {
          if ( __eh34_catch_type(8, &ATL::CAtlException `RTTI Type Descriptor', &v96) )
          {
            v4 = 0;
            v39 = v65;
            v41 = v80;
            v3 = v72;
            v66 = v73;
            v68 = v74;
            v27 = v71;
            __eh34_try_continuation(8, &ATL::CAtlException `RTTI Type Descriptor', &loc_18000B928);
          }
        }
      }
      if ( !v39 )
        std::vector<CHostDLLInfo *>::push_back(v41, &v70);
      goto LABEL_112;
    }
    v34 = (unsigned int *)*((_QWORD *)v28 + 8);
LABEL_84:
    while ( 1 )
    {
      v34 = *(unsigned int **)v34;
      v71 = v34;
      if ( v34 == *((unsigned int **)v28 + 8) )
        break;
      v35 = (char *)*((_QWORD *)v34 + 2);
      v80 = v35;
      v36 = (_QWORD *)*((_QWORD *)v35 + 6);
      while ( 1 )
      {
        v36 = (_QWORD *)*v36;
        if ( v36 == *((_QWORD **)v35 + 6) )
          break;
        v37 = (struct ProblemNode *)v36[2];
        if ( v37 != v28 )
        {
          v78 = (unsigned __int64)v37;
          if ( (int)IterateOverNodes(1, v35, &v78, SearchForNode, 1) >= 0 && !DWORD2(v78) )
            goto LABEL_84;
        }
      }
      if ( *(_QWORD *)v27 )
      {
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v77);
        if ( __eh34_try(-1, 6) )
        {
          __eh34_scope_strut(6);
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
            (__int64)&v77,
            (__int64)L"After removal its parent node is a leaf, will check whether its removal is necessary. Helper Class: %s");
          v38 = v77;
          (*(void (__fastcall **)(_QWORD, _QWORD, LPVOID *, _QWORD))(**(_QWORD **)v27 + 112LL))(
            *(_QWORD *)v27,
            0,
            v77,
            *(_QWORD *)(*(_QWORD *)v35 + 40LL));
          ATL::CStringData::Release((ATL::CStringData *)(v38 - 3));
        }
        if ( __eh34_catch(6) )
        {
          if ( __eh34_catch_type(6, &ATL::CAtlException `RTTI Type Descriptor', &v95) )
          {
            v4 = 0;
            v28 = v70;
            v34 = v71;
            v27 = v64;
            v3 = v72;
            v66 = v73;
            v68 = v74;
            __eh34_try_continuation(6, &ATL::CAtlException `RTTI Type Descriptor', &loc_18000B80C);
          }
        }
      }
      std::vector<CHostDLLInfo *>::push_back(&v84, &v80);
    }
    DisconnectNodeFromDiagGraph(v28);
    *((_DWORD *)v28 + 8) = 8;
LABEL_112:
    ++v63;
  }
  if ( *(_QWORD *)v27 )
  {
    memset_0(v91, 0, sizeof(v91));
    if ( (unsigned __int64)((__int64)(*((_QWORD *)v3 + 5) - *((_QWORD *)v3 + 4)) >> 3) > 0xC )
    {
      StringCchPrintfW(
        v91,
        0x80u,
        L"Warning: Maximum number of root causes reached (%i), some diagnosis results may not be available.");
      (*(void (__fastcall **)(_QWORD, _QWORD, unsigned __int16 *))(**(_QWORD **)v27 + 96LL))(*(_QWORD *)v27, 0, v91);
    }
    if ( *v75 > 0xCu )
    {
      StringCchPrintfW(
        v91,
        0x80u,
        L"Warning: Maximum number of repairs reached (%i), some repairs may not be available.");
      (*(void (__fastcall **)(_QWORD, _QWORD, unsigned __int16 *))(**(_QWORD **)v27 + 96LL))(*(_QWORD *)v27, 0, v91);
    }
  }
  v46 = (int *)CoTaskMemAlloc(0x30u);
  v47 = (LPVOID *)v68;
  *v68 = v46;
  if ( !v46 )
  {
    v48 = -2147024882;
    goto LABEL_156;
  }
  v49 = *((_QWORD *)v3 + 4);
  if ( (*((_QWORD *)v3 + 5) - v49) >> 3 )
  {
    v50 = 0;
    v51 = 0;
    while ( *v66 < 12 )
    {
      *((_DWORD *)*v47 + (*v66)++) = v50;
LABEL_137:
      ++v50;
      v49 = *((_QWORD *)v3 + 4);
      v51 = v50;
      if ( v50 >= (unsigned __int64)((*((_QWORD *)v3 + 5) - v49) >> 3) )
        goto LABEL_138;
    }
    v52 = *(_DWORD **)(v49 + 8 * v51);
    v53 = 0;
    while ( 2 )
    {
      if ( v53 >= 0xC )
        goto LABEL_137;
      v54 = *(_DWORD **)(v49 + 8LL * *((int *)*v47 + v53));
      if ( v52[8] == 9 )
      {
        if ( *(int *)(*(_QWORD *)v52 + 240LL) >= 0 && v54[8] == 9 && !*(_QWORD *)(*(_QWORD *)v54 + 112LL) )
        {
          v55 = *(_QWORD *)(*(_QWORD *)v52 + 112LL) == 0;
          goto LABEL_134;
        }
      }
      else
      {
        if ( v54[8] == 9 )
          goto LABEL_136;
        if ( !*(_QWORD *)(*(_QWORD *)v54 + 112LL) )
        {
          v55 = *(_QWORD *)(*(_QWORD *)v52 + 112LL) == 0;
LABEL_134:
          if ( !v55 )
          {
LABEL_136:
            *((_DWORD *)*v47 + v53) = v50;
            goto LABEL_137;
          }
        }
      }
      ++v53;
      continue;
    }
  }
LABEL_138:
  if ( !*v66
    || *((_DWORD *)v3 + 6) == 13
    || (*v66 <= 1
      ? (LCA = *(struct ProblemNode **)(v49 + 8LL * *(int *)*v47))
      : (LCA = NetworkIncident::FindLCA(v3, *v66, (int *)*v47)),
        *((_QWORD *)v3 + 7) = 0,
        !LCA) )
  {
    v48 = -2147467259;
LABEL_156:
    if ( *v47 )
    {
      CoTaskMemFree(*v47);
      *v47 = 0;
      *v66 = 0;
    }
    std::vector<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> *,std::allocator<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> *>>::~vector<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> *,std::allocator<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> *>>((__int64)&v84);
    std::deque<ProblemNode *>::~deque<ProblemNode *>((__int64)v88);
    return (unsigned int)v48;
  }
  v57 = *(_QWORD *)LCA;
  *((_QWORD *)v3 + 7) = *(_QWORD *)LCA;
  if ( *(_DWORD *)(*(_QWORD *)(v57 + 80) - 16LL) && (*(_DWORD *)(v57 + 96) != 9 || *v66 != 1) )
    goto LABEL_150;
  v75 = 0;
  v48 = IterateOverNodes(1, LCA, &v75, FindRepairDescOwnerCallback, 0);
  if ( v48 < 0 )
    goto LABEL_156;
  if ( v75 )
    *((_QWORD *)v3 + 7) = *(_QWORD *)v75;
LABEL_150:
  if ( *((_QWORD *)v3 + 15) )
  {
    v58 = *((_QWORD *)v3 + 4);
    if ( (*((_QWORD *)v3 + 5) - v58) >> 3 )
    {
      v59 = 0;
      do
      {
        v60 = *(_QWORD ***)(v58 + 8 * v59);
        (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)v3 + 15) + 48LL))(
          *((_QWORD *)v3 + 15),
          **v60,
          (*v60)[1]);
        v78 = *((_OWORD *)*v60 + 16);
        (*(void (__fastcall **)(_QWORD, __int128 *))(**((_QWORD **)v3 + 15) + 104LL))(*((_QWORD *)v3 + 15), &v78);
        ++v4;
        v58 = *((_QWORD *)v3 + 4);
        v59 = v4;
      }
      while ( v4 < (unsigned __int64)((*((_QWORD *)v3 + 5) - v58) >> 3) );
    }
  }
  std::vector<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> *,std::allocator<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> *>>::~vector<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> *,std::allocator<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> *>>((__int64)&v84);
  std::deque<ProblemNode *>::~deque<ProblemNode *>((__int64)v88);
  return 0;
}

```

## disassembly

```asm
0x18000b098  push    rbx
0x18000b09a  push    rsi
0x18000b09b  push    rdi
0x18000b09c  push    r12
0x18000b09e  push    r13
0x18000b0a0  push    r14
0x18000b0a2  push    r15
0x18000b0a4  sub     rsp, 280h
0x18000b0ab  mov     rax, cs:__security_cookie
0x18000b0b2  xor     rax, rsp
0x18000b0b5  mov     [rsp+2B8h+var_40], rax
0x18000b0bd  mov     [rsp+2B8h+var_268], r8
0x18000b0c2  mov     [rsp+2B8h+var_278], rdx
0x18000b0c7  mov     r15, rcx
0x18000b0ca  mov     [rsp+2B8h+var_1C0], rcx
0x18000b0d2  mov     [rsp+2B8h+var_248], rcx
0x18000b0d7  mov     [rsp+2B8h+var_240], rdx
0x18000b0dc  mov     [rsp+2B8h+var_238], r8
0x18000b0e4  xor     esi, esi
0x18000b0e6  test    rdx, rdx
0x18000b0e9  jz      loc_18000BC70
0x18000b0ef  test    r8, r8
0x18000b0f2  jz      loc_18000BC70
0x18000b0f8  mov     [rsp+2B8h+var_228], rcx
0x18000b100  mov     [rsp+2B8h+var_1B8], rcx
0x18000b108  lea     rax, [rcx+70h]
0x18000b10c  mov     [rsp+2B8h+var_230], rax
0x18000b114  mov     [rax], esi
0x18000b116  mov     [rdx], esi
0x18000b118  mov     [r8], rsi
0x18000b11b  lea     rcx, [rsp+2B8h+var_1B0]
0x18000b123  call    ??0?$queue@HV?$deque@HV?$allocator@H@std@@@std@@@std@@QEAA@XZ; std::queue<int>::queue<int,std::deque<int>>(void)
0x18000b128  nop
0x18000b129  xorps   xmm0, xmm0
0x18000b12c  movdqu  [rsp+2B8h+var_1D8], xmm0
0x18000b135  mov     [rsp+2B8h+var_1C8], rsi
0x18000b13d  mov     rdx, r15
0x18000b140  lea     rcx, [rsp+2B8h+var_1B0]
0x18000b148  call    ?push_back@?$deque@PEAVProblemNode@@V?$allocator@PEAVProblemNode@@@std@@@std@@QEAAXAEBQEAVProblemNode@@@Z; std::deque<ProblemNode *>::push_back(ProblemNode * const &)
0x18000b14d  mov     rcx, [rsp+2B8h+var_190]
0x18000b155  test    rcx, rcx
0x18000b158  jz      loc_18000B4E2
0x18000b15e  cmp     dword ptr [r15+18h], 0Dh
0x18000b163  jz      loc_18000B4E2
0x18000b169  mov     rdx, [rsp+2B8h+var_198]
0x18000b171  add     rdx, rcx
0x18000b174  lea     r8, [rsp+2B8h+var_1B0]
0x18000b17c  lea     rcx, [rsp+2B8h+var_188]
0x18000b184  call    ??0?$_Deque_iterator@V?$_Deque_val@U?$_Deque_simple_types@PEAVProblemNode@@@std@@@std@@@std@@QEAA@_KPEBU_Container_base12@1@@Z; std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<ProblemNode *>>>::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<ProblemNode *>>>(unsigned __int64,std::_Container_base12 const *)
0x18000b189  nop
0x18000b18a  lea     rdx, [rsp+2B8h+var_188]
0x18000b192  lea     rcx, [rsp+2B8h+var_218]
0x18000b19a  call    ??0?$_Deque_iterator@V?$_Deque_val@U?$_Deque_simple_types@PEAVProblemNode@@@std@@@std@@@std@@QEAA@AEBV01@@Z; std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<ProblemNode *>>>::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<ProblemNode *>>>(std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<ProblemNode *>>> const &)
0x18000b19f  dec     [rsp+2B8h+var_208]
0x18000b1a7  lea     rdx, [rsp+2B8h+var_218]
0x18000b1af  lea     rcx, [rsp+2B8h+var_1F0]
0x18000b1b7  call    ??0?$_Deque_iterator@V?$_Deque_val@U?$_Deque_simple_types@PEAVProblemNode@@@std@@@std@@@std@@QEAA@AEBV01@@Z; std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<ProblemNode *>>>::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<ProblemNode *>>>(std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<ProblemNode *>>> const &)
0x18000b1bc  mov     r8, [rsp+2B8h+var_1F0]
0x18000b1c4  test    r8, r8
0x18000b1c7  jnz     short loc_18000B1CE
0x18000b1c9  mov     r8, rsi
0x18000b1cc  jmp     short loc_18000B1D1
0x18000b1ce  mov     r8, [r8]
0x18000b1d1  mov     rdx, [r8+10h]
0x18000b1d5  dec     rdx
0x18000b1d8  mov     rcx, [rsp+2B8h+var_1E0]
0x18000b1e0  mov     rax, rcx
0x18000b1e3  shr     rax, 1
0x18000b1e6  and     rdx, rax
0x18000b1e9  mov     rax, [r8+8]
0x18000b1ed  and     ecx, 1
0x18000b1f0  mov     rax, [rax+rdx*8]
0x18000b1f4  mov     rdi, [rax+rcx*8]
0x18000b1f8  mov     [rsp+2B8h+var_260], rdi
0x18000b1fd  lea     rcx, [rsp+2B8h+var_1B0]
0x18000b205  call    ?pop_back@?$deque@PEAVProblemNode@@V?$allocator@PEAVProblemNode@@@std@@@std@@QEAAXXZ; std::deque<ProblemNode *>::pop_back(void)
0x18000b20a  cmp     dword ptr [rdi+60h], 1
0x18000b20e  jz      loc_18000B14D
0x18000b214  mov     dword ptr [rdi+60h], 1
0x18000b21b  lea     r13, [rdi+2Ch]
0x18000b21f  mov     [rsp+2B8h+var_258], r13
0x18000b224  inc     dword ptr [r13+0]
0x18000b228  mov     [rsp+2B8h+var_288], 1
0x18000b230  mov     rbx, [rdi+30h]
0x18000b234  mov     rbx, [rbx]
0x18000b237  cmp     rbx, [rdi+30h]
0x18000b23b  jz      short loc_18000B25D
0x18000b23d  lea     rdx, [rbx+10h]
0x18000b241  mov     rax, [rdx]
0x18000b244  cmp     dword ptr [rax+60h], 1
0x18000b248  jz      short loc_18000B234
0x18000b24a  lea     rcx, [rsp+2B8h+var_1B0]
0x18000b252  call    ?push_back@?$deque@PEAVProblemNode@@V?$allocator@PEAVProblemNode@@@std@@@std@@QEAAXAEBQEAVProblemNode@@@Z; std::deque<ProblemNode *>::push_back(ProblemNode * const &)
0x18000b257  mov     [rsp+2B8h+var_288], esi
0x18000b25b  jmp     short loc_18000B234
0x18000b25d  mov     rbx, [rdi]
0x18000b260  mov     ecx, [rdi+1Ch]
0x18000b263  lea     eax, [rcx-1]
0x18000b266  test    eax, 0FFFFFFFCh
0x18000b26b  jnz     short loc_18000B277
0x18000b26d  cmp     ecx, 3
0x18000b270  jz      short loc_18000B277
0x18000b272  mov     ecx, [rbx+60h]
0x18000b275  jmp     short loc_18000B27A
0x18000b277  mov     ecx, [rbx+64h]
0x18000b27a  lea     r12, [rbx+68h]
0x18000b27e  mov     [rsp+2B8h+var_250], r12
0x18000b283  lea     r14, [rbx+70h]
0x18000b287  mov     [rsp+2B8h+var_220], r14
0x18000b28f  sub     ecx, 3
0x18000b292  jz      short loc_18000B2DC
0x18000b294  sub     ecx, 1
0x18000b297  jz      loc_18000B454
0x18000b29d  sub     ecx, 1
0x18000b2a0  jz      loc_18000B454
0x18000b2a6  sub     ecx, 1
0x18000b2a9  jz      loc_18000B454
0x18000b2af  sub     ecx, 3
0x18000b2b2  jz      short loc_18000B2DC
0x18000b2b4  sub     ecx, 1
0x18000b2b7  jz      short loc_18000B2DC
0x18000b2b9  cmp     ecx, 1
0x18000b2bc  jnz     loc_18000B14D
0x18000b2c2  mov     [r12], esi
0x18000b2c6  cmp     [r14], rsi
0x18000b2c9  jz      short loc_18000B2D4
0x18000b2cb  mov     rcx, [r14]; pv
0x18000b2ce  call    cs:__imp_CoTaskMemFree
0x18000b2d4  mov     [r14], rsi
0x18000b2d7  jmp     loc_18000B454
0x18000b2dc  cmp     [r14], rsi
0x18000b2df  jz      short loc_18000B2FA
0x18000b2e1  mov     r8d, 1; int
0x18000b2e7  mov     edx, [r12]; unsigned int
0x18000b2eb  mov     rcx, [r14]; pv
0x18000b2ee  call    ?FreeRepairInfos@@YAXPEAUtagRepairInfo@@KH@Z; FreeRepairInfos(tagRepairInfo *,ulong,int)
0x18000b2f3  mov     [r12], esi
0x18000b2f7  mov     [r14], rsi
0x18000b2fa  mov     rcx, [rbx+48h]
0x18000b2fe  mov     rax, [rcx]
0x18000b301  mov     r9, r14
0x18000b304  mov     r8, r12
0x18000b307  mov     edx, [rdi+1Ch]
0x18000b30a  mov     rax, [rax+58h]
0x18000b30e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b313  mov     r13d, eax
0x18000b316  mov     dword ptr [rsp+2B8h+var_280], eax
0x18000b31a  mov     edx, [r12]
0x18000b31e  mov     rcx, [rsp+2B8h+var_230]
0x18000b326  add     [rcx], edx
0x18000b328  cmp     [r15+0D8h], rsi
0x18000b32f  jz      loc_18000B44A
0x18000b335  lea     rcx, [rsp+2B8h+var_270]
0x18000b33a  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18000b33f  nop
0x18000b340  test    r13d, r13d
0x18000b343  jns     short loc_18000B38D
0x18000b345  mov     r8, [rbx+10h]
0x18000b349  cmp     r13d, 80004001h
0x18000b350  jnz     short loc_18000B36E
0x18000b352  cmp     [r8-10h], esi
0x18000b356  jnz     short loc_18000B35B
0x18000b358  mov     r8, [rbx]
0x18000b35b  lea     rdx, aSReturned0Repa; "%s returned 0 repairs (E_NOTIMPL)."
0x18000b362  lea     rcx, [rsp+2B8h+var_270]
0x18000b367  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x18000b36c  jmp     short loc_18000B38B
0x18000b36e  cmp     [r8-10h], esi
0x18000b372  jnz     short loc_18000B377
0x18000b374  mov     r8, [rbx]
0x18000b377  mov     r9d, r13d
0x18000b37a  lea     rdx, aGetrepairinfoF; "GetRepairInfo failed for %s. HR:0x%x"
0x18000b381  lea     rcx, [rsp+2B8h+var_270]
0x18000b386  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x18000b38b  jmp     short loc_18000B3E7
0x18000b38d  mov     r9d, [r12]
0x18000b391  mov     edx, esi
0x18000b393  cmp     edx, r9d
0x18000b396  jnb     short loc_18000B3AE
0x18000b398  mov     eax, edx
0x18000b39a  imul    rcx, rax, 70h ; 'p'
0x18000b39e  mov     rax, [r14]
0x18000b3a1  cmp     [rcx+rax+28h], esi
0x18000b3a5  jl      short loc_18000B3AB
0x18000b3a7  inc     edx
0x18000b3a9  jmp     short loc_18000B393
0x18000b3ab  mov     r9d, edx
0x18000b3ae  lea     rcx, dword_180033E1C
0x18000b3b5  lea     rax, aCatchAllsPrese; "(catch-alls present)"
0x18000b3bc  cmp     [r12], r9d
0x18000b3c0  cmovz   rax, rcx
0x18000b3c4  mov     r8, [rbx+10h]
0x18000b3c8  cmp     [r8-10h], esi
0x18000b3cc  jnz     short loc_18000B3D1
0x18000b3ce  mov     r8, [rbx]
0x18000b3d1  mov     [rsp+2B8h+var_298], rax
0x18000b3d6  lea     rdx, aSReturnedIRepa; "%s returned %i repairs %s."
0x18000b3dd  lea     rcx, [rsp+2B8h+var_270]
0x18000b3e2  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x18000b3e7  mov     rcx, [r15+0D8h]
0x18000b3ee  mov     rax, [rcx]
0x18000b3f1  mov     r9, [rbx+28h]
0x18000b3f5  mov     rbx, [rsp+2B8h+var_270]
0x18000b3fa  mov     r8, rbx
0x18000b3fd  xor     edx, edx
0x18000b3ff  mov     rax, [rax+70h]
0x18000b403  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b408  nop
0x18000b409  lea     rcx, [rbx-18h]; this
0x18000b40d  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18000b412  nop
0x18000b413  jmp     short loc_18000B44A
0x18000b415  xor     esi, esi
0x18000b417  mov     rdi, [rsp+2B8h+var_260]
0x18000b41c  mov     r12, [rsp+2B8h+var_250]
0x18000b421  mov     r14, [rsp+2B8h+var_220]
0x18000b429  mov     r13d, dword ptr [rsp+2B8h+var_280]
0x18000b42e  mov     r15, [rsp+2B8h+var_248]
0x18000b433  mov     rax, [rsp+2B8h+var_240]
0x18000b438  mov     [rsp+2B8h+var_278], rax
0x18000b43d  mov     rax, [rsp+2B8h+var_238]
0x18000b445  mov     [rsp+2B8h+var_268], rax
0x18000b44a  test    r13d, r13d
0x18000b44d  js      short loc_18000B4BB
0x18000b44f  mov     r13, [rsp+2B8h+var_258]
0x18000b454  cmp     [r12], esi
0x18000b458  jbe     short loc_18000B4BB
0x18000b45a  cmp     [rdi+38h], rsi
0x18000b45e  jz      short loc_18000B468
0x18000b460  mov     rax, [r14]
0x18000b463  bts     dword ptr [rax+28h], 1Eh
0x18000b468  cmp     [r15+78h], rsi
0x18000b46c  jz      short loc_18000B4BB
0x18000b46e  cmp     [r14], rsi
0x18000b471  jz      short loc_18000B4BB
0x18000b473  cmp     dword ptr [r13+0], 1
0x18000b478  jnz     short loc_18000B4BB
0x18000b47a  mov     ebx, esi
0x18000b47c  cmp     [r12], esi
0x18000b480  jbe     short loc_18000B4BB
0x18000b482  mov     eax, ebx
0x18000b484  imul    rcx, rax, 70h ; 'p'
0x18000b488  mov     rax, [r14]
0x18000b48b  movups  xmm0, xmmword ptr [rcx+rax]
0x18000b48f  movdqu  [rsp+2B8h+var_218], xmm0
0x18000b498  mov     rcx, [r15+78h]
0x18000b49c  mov     rax, [rcx]
0x18000b49f  lea     rdx, [rsp+2B8h+var_218]
0x18000b4a7  mov     rax, [rax+0A8h]
0x18000b4ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b4b3  inc     ebx
0x18000b4b5  cmp     ebx, [r12]
0x18000b4b9  jb      short loc_18000B482
0x18000b4bb  cmp     [rdi+38h], rsi
0x18000b4bf  jz      short loc_18000B4CB
0x18000b4c1  cmp     [rsp+2B8h+var_288], esi
0x18000b4c5  jz      loc_18000B14D
0x18000b4cb  lea     rdx, [rsp+2B8h+var_260]
0x18000b4d0  lea     rcx, [rsp+2B8h+var_1D8]
0x18000b4d8  call    ?push_back@?$vector@PEAVCHostDLLInfo@@V?$allocator@PEAVCHostDLLInfo@@@std@@@std@@QEAAXAEBQEAVCHostDLLInfo@@@Z; std::vector<CHostDLLInfo *>::push_back(CHostDLLInfo * const &)
0x18000b4dd  jmp     loc_18000B14D
0x18000b4e2  mov     [rsp+2B8h+var_288], esi
0x18000b4e6  mov     r12, [rsp+2B8h+var_228]
0x18000b4ee  add     r12, 0D8h
0x18000b4f5  mov     r14d, [rsp+2B8h+var_288]
0x18000b4fa  mov     rax, qword ptr [rsp+2B8h+var_1D8+8]
0x18000b502  mov     rcx, qword ptr [rsp+2B8h+var_1D8]
0x18000b50a  sub     rax, rcx
0x18000b50d  sar     rax, 3
0x18000b511  cmp     r14, rax
0x18000b514  jnb     loc_18000B971
0x18000b51a  mov     r14, [rcx+r14*8]
0x18000b51e  mov     [rsp+2B8h+var_258], r14
0x18000b523  mov     rax, [r14]
0x18000b526  cmp     [rax+68h], esi
0x18000b529  jnz     loc_18000B853
0x18000b52f  mov     rax, [rsp+2B8h+var_1C0]
0x18000b537  cmp     r14, [rax]
0x18000b53a  jz      loc_18000B853
0x18000b540  lea     r12, [r15+0D8h]
0x18000b547  mov     [rsp+2B8h+var_280], r12
0x18000b54c  cmp     [r12], rsi
0x18000b550  jz      loc_18000B5FD
0x18000b556  lea     rcx, [rsp+2B8h+var_270]
0x18000b55b  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18000b560  nop
0x18000b561  mov     rax, [r14]
0x18000b564  mov     r8, [rax+10h]
0x18000b568  cmp     dword ptr [rax+0ECh], 1
0x18000b56f  jz      short loc_18000B58D
0x18000b571  cmp     [r8-10h], esi
0x18000b575  jnz     short loc_18000B57A
0x18000b577  mov     r8, [rax]
0x18000b57a  lea     rdx, aLeafNodeIsNotC; "Leaf node is not confirmed and does not"...
0x18000b581  lea     rcx, [rsp+2B8h+var_270]
0x18000b586  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x18000b58b  jmp     short loc_18000B5A7
0x18000b58d  cmp     [r8-10h], esi
0x18000b591  jnz     short loc_18000B596
0x18000b593  mov     r8, [rax]
  ... truncated ...
```
