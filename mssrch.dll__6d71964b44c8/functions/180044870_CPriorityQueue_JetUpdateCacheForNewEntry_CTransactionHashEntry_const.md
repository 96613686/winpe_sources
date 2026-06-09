# CPriorityQueue::JetUpdateCacheForNewEntry(CTransactionHashEntry const &)

- ea: `0x180044870`
- end: `0x1800452e0`
- name: `?JetUpdateCacheForNewEntry@CPriorityQueue@@QEAAXAEBVCTransactionHashEntry@@@Z`
- size: `2672`
- prototype: `void __fastcall(CPriorityQueue *__hidden this, const struct CTransactionHashEntry *)`
- caller_count: `2`
- callee_count: `22`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18002379c`
- `0x180043a14`

## callees

- `0x18000bf8c`
- `0x18001d880`
- `0x180033158`
- `0x180034964`
- `0x180034a48`
- `0x180034b1c`
- `0x180034c7c`
- `0x18003bbe4`
- `0x18003db14`
- `0x180044870`
- `0x1800452e8`
- `0x180078774`
- `0x18008fde0`
- `0x1800c9f50`
- `0x1800cf6f4`
- `0x1800d0914`
- `0x1800dbea4`
- `0x1800ddce4`
- `0x180109ebc`
- `0x18011eb58`
- `0x18012540e`
- `0x1801299d3`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800452ab`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800452ab`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x180044c6f`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x180044e75`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x1800450b5`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x180044c6f`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x180044e75`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x1800450b5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044be5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044be5`

## string_xrefs

- `0x180044bd4`: `CPriorityQueue::UpdateCache, SendingCloudNotification for wid: %d`
- `0x180044969`: `CPriorityQueue::UpdateCache, wid: %d, updating CLOUD flags %ws`
- `0x180045265`: `onecoreuap\base\appmodel\Search\common\include\sparse_bit.h`
- `0x180045277`: `onecoreuap\base\appmodel\Search\common\include\sparse_bit.h`
- `0x180045292`: `onecoreuap\base\appmodel\Search\common\include\sparse_bit.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CPriorityQueue::JetUpdateCacheForNewEntry(CPriorityQueue *this, const struct CTransactionHashEntry *a2)
{
  enum QUEUE_TYPE Queue; // eax
  enum QUEUE_TYPE v5; // r15d
  unsigned int *v6; // rdi
  unsigned int v7; // ebx
  _QWORD *v8; // rbx
  _QWORD *v9; // rax
  _QWORD *v10; // rax
  CPriorityQueue *v11; // rcx
  char *v12; // rbx
  unsigned int v13; // r14d
  unsigned int v14; // edx
  const struct CTransactionHashEntry **v15; // rax
  unsigned int *v16; // r14
  __int64 v17; // rax
  __int64 v18; // r12
  __int64 v19; // rcx
  __int64 v20; // r8
  const char *v21; // r9
  const struct CTransactionHashEntry *v22; // r15
  _QWORD *v23; // rax
  const struct CTransactionHashEntry **v24; // rdx
  unsigned __int64 v25; // r14
  __int64 v26; // rcx
  __int64 v27; // rdi
  __int64 v28; // rax
  void *v29; // rbx
  unsigned int v30; // ecx
  const struct CTransactionHashEntry **v31; // r12
  unsigned __int64 v32; // rdx
  __int64 v33; // r8
  __int64 v34; // rax
  char *v35; // rbx
  unsigned int v36; // r14d
  unsigned int v37; // edx
  const struct CTransactionHashEntry **v38; // rax
  unsigned int *v39; // r14
  __int64 v40; // rax
  __int64 v41; // r12
  __int64 v42; // rcx
  __int64 v43; // r8
  const char *v44; // r9
  const struct CTransactionHashEntry *v45; // r15
  _QWORD *v46; // rax
  const struct CTransactionHashEntry **v47; // rdx
  unsigned __int64 v48; // r14
  __int64 v49; // rcx
  __int64 v50; // rdi
  __int64 v51; // rax
  void *v52; // rbx
  unsigned int v53; // ecx
  const struct CTransactionHashEntry **v54; // r12
  unsigned __int64 v55; // r8
  __int64 v56; // rdx
  __int64 v57; // rax
  char *v58; // rbx
  unsigned int v59; // r14d
  unsigned int v60; // edx
  unsigned int *v61; // rax
  unsigned int *v62; // r14
  __int64 v63; // rax
  __int64 v64; // r12
  __int64 v65; // rcx
  __int64 v66; // r8
  const char *v67; // r9
  unsigned int *v68; // r15
  _QWORD *v69; // rax
  unsigned int **v70; // rdx
  unsigned __int64 v71; // r14
  __int64 v72; // rcx
  __int64 v73; // rdi
  __int64 size_of; // rax
  void *v75; // rbx
  int v76; // ecx
  unsigned int *v77; // rdi
  unsigned __int64 v78; // rdx
  char v79; // r14
  __int64 v80; // rax
  unsigned int *v81; // [rsp+20h] [rbp-30h] BYREF
  const struct CTransactionHashEntry *v82; // [rsp+28h] [rbp-28h] BYREF
  unsigned int v83; // [rsp+30h] [rbp-20h]
  __int64 v84; // [rsp+38h] [rbp-18h] BYREF
  __int64 v85; // [rsp+40h] [rbp-10h]
  unsigned __int64 v86; // [rsp+48h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+38h]
  LPVOID pv; // [rsp+90h] [rbp+40h] BYREF
  const struct CTransactionHashEntry **v89; // [rsp+A0h] [rbp+50h]
  unsigned int *v90; // [rsp+A8h] [rbp+58h]

  Queue = CPriorityQueue::GetQueue(this, a2);
  v5 = Queue;
  LODWORD(v89) = Queue;
  if ( !*((_BYTE *)this + 336) && (unsigned int)(Queue - 1) <= 1 )
  {
    v58 = (char *)this + 312;
    v59 = *((_DWORD *)a2 + 40);
    LODWORD(pv) = v59;
    v60 = v59 >> *(_DWORD *)(*((_QWORD *)this + 39) + 20LL);
    if ( v60 < *((_DWORD *)this + 80) )
    {
      v61 = (unsigned int *)_sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToStart((char *)this + 312);
    }
    else if ( v60 >= *((_DWORD *)this + 81) )
    {
      v61 = (unsigned int *)_sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToEnd((char *)this + 312);
    }
    else
    {
      v61 = (unsigned int *)(*((_QWORD *)this + 41) + 8LL * (v60 - *((_DWORD *)this + 80)));
    }
    v90 = v61;
    if ( *(_QWORD *)v61 )
    {
      v77 = v90;
    }
    else
    {
      v62 = *(unsigned int **)v58;
      v82 = (const struct CTransactionHashEntry *)v62;
      v63 = TPUtils::combinable<sparse_bit_allocator<unsigned __int64>::CAllocatorState>::local(v62 + 12);
      v64 = v63;
      v65 = *(_QWORD *)(v63 + 24);
      if ( *(_QWORD *)(v63 + 16) == v65 )
      {
        v66 = *(unsigned int *)(v63 + 8);
        if ( (unsigned int)v66 < v62[7] )
        {
          v68 = (unsigned int *)(*(_QWORD *)v63 + 8 * v66);
          v76 = v66 + v62[2];
        }
        else
        {
          v68 = (unsigned int *)_aligned_malloc(8LL * v62[7], v62[8]);
          v81 = v68;
          if ( !v68 )
            wil::details::in1diag3::_Throw_NullAlloc(
              retaddr,
              (void *)0x430,
              (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\sparse_bit.h",
              v67);
          v69 = (_QWORD *)(v64 + 40);
          v70 = *(unsigned int ***)(v64 + 48);
          if ( v70 == *(unsigned int ***)(v64 + 56) )
          {
            std::vector<unsigned __int64 *>::_Emplace_reallocate<unsigned __int64 * const &>(v69, v70, &v81);
            v68 = v81;
            v69 = (_QWORD *)(v64 + 40);
          }
          else
          {
            *v70 = v68;
            *(_QWORD *)(v64 + 48) += 8LL;
          }
          v71 = *((unsigned int *)v82 + 6) * ((__int64)(v69[1] - *v69) >> 3);
          v72 = *(_QWORD *)(v64 + 16);
          if ( v71 > (*(_QWORD *)(v64 + 32) - v72) >> 3 )
          {
            if ( v71 > 0x1FFFFFFFFFFFFFFFLL )
              goto LABEL_90;
            v73 = (*(_QWORD *)(v64 + 24) - v72) >> 3;
            size_of = std::_Get_size_of_n<8>(v71);
            v75 = (void *)std::_Allocate<16,std::_Default_allocate_traits>(size_of);
            v84 = v64 + 16;
            v86 = v71;
            memmove_0(v75, *(const void **)(v64 + 16), *(_QWORD *)(v64 + 24) - *(_QWORD *)(v64 + 16));
            v85 = 0;
            std::vector<unsigned __int64 *>::_Change_array(v64 + 16, v75, v73, v71);
            std::vector<wchar_t const *>::_Reallocation_guard::~_Reallocation_guard(&v84);
            v58 = (char *)this + 312;
          }
          *(_QWORD *)v64 = v68;
          v62 = (unsigned int *)v82;
          v76 = *((_DWORD *)v82 + 2);
        }
        *(_DWORD *)(v64 + 8) = v76;
      }
      else
      {
        v68 = *(unsigned int **)(v65 - 8);
        *(_QWORD *)(v63 + 24) = v65 - 8;
      }
      v77 = v90;
      *(_QWORD *)v90 = v68;
      memset_0(v68, 0, v62[1]);
      v59 = (unsigned int)pv;
      v5 = (int)v89;
    }
    v78 = ((unsigned __int64)v59 >> 6) & *(unsigned int *)(*(_QWORD *)v58 + 16LL);
    v79 = v59 & 0x3F;
    v80 = *(_QWORD *)(*(_QWORD *)v77 + 8 * v78);
    if ( (v80 & (1LL << v79)) == 0 )
      *(_QWORD *)(*(_QWORD *)v77 + 8 * v78) = (1LL << v79) | v80;
  }
  CPriorityQueue::AddEntryToQueue(this, v5, a2);
  v6 = (unsigned int *)((char *)a2 + 160);
  v90 = (unsigned int *)((char *)a2 + 160);
  if ( (*((_DWORD *)a2 + 37) & 0x400000) != 0 )
  {
    v35 = (char *)this + 344;
    v36 = *v6;
    LODWORD(pv) = v36;
    v37 = v36 >> *(_DWORD *)(*((_QWORD *)this + 43) + 20LL);
    if ( v37 < *((_DWORD *)this + 88) )
    {
      v38 = (const struct CTransactionHashEntry **)_sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToStart((char *)this + 344);
    }
    else if ( v37 >= *((_DWORD *)this + 89) )
    {
      v38 = (const struct CTransactionHashEntry **)_sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToEnd((char *)this + 344);
    }
    else
    {
      v38 = (const struct CTransactionHashEntry **)(*((_QWORD *)this + 45) + 8LL * (v37 - *((_DWORD *)this + 88)));
    }
    v89 = v38;
    if ( *v38 )
    {
      v54 = v89;
    }
    else
    {
      v39 = *(unsigned int **)v35;
      v81 = v39;
      v40 = TPUtils::combinable<sparse_bit_allocator<unsigned __int64>::CAllocatorState>::local(v39 + 12);
      v41 = v40;
      v42 = *(_QWORD *)(v40 + 24);
      if ( *(_QWORD *)(v40 + 16) == v42 )
      {
        v43 = *(unsigned int *)(v40 + 8);
        if ( (unsigned int)v43 < v39[7] )
        {
          v45 = (const struct CTransactionHashEntry *)(*(_QWORD *)v40 + 8 * v43);
          v53 = v43 + v39[2];
        }
        else
        {
          v45 = (const struct CTransactionHashEntry *)_aligned_malloc(8LL * v39[7], v39[8]);
          v82 = v45;
          if ( !v45 )
            wil::details::in1diag3::_Throw_NullAlloc(
              retaddr,
              (void *)0x430,
              (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\sparse_bit.h",
              v44);
          v46 = (_QWORD *)(v41 + 40);
          v47 = *(const struct CTransactionHashEntry ***)(v41 + 48);
          if ( v47 == *(const struct CTransactionHashEntry ***)(v41 + 56) )
          {
            std::vector<unsigned __int64 *>::_Emplace_reallocate<unsigned __int64 * const &>(v46, v47, &v82);
            v45 = v82;
            v46 = (_QWORD *)(v41 + 40);
          }
          else
          {
            *v47 = v45;
            *(_QWORD *)(v41 + 48) += 8LL;
          }
          v48 = v81[6] * ((__int64)(v46[1] - *v46) >> 3);
          v49 = *(_QWORD *)(v41 + 16);
          if ( v48 > (*(_QWORD *)(v41 + 32) - v49) >> 3 )
          {
            if ( v48 > 0x1FFFFFFFFFFFFFFFLL )
              goto LABEL_90;
            v50 = (*(_QWORD *)(v41 + 24) - v49) >> 3;
            v51 = std::_Get_size_of_n<8>(v48);
            v52 = (void *)std::_Allocate<16,std::_Default_allocate_traits>(v51);
            v84 = v41 + 16;
            v86 = v48;
            memmove_0(v52, *(const void **)(v41 + 16), *(_QWORD *)(v41 + 24) - *(_QWORD *)(v41 + 16));
            v85 = 0;
            std::vector<unsigned __int64 *>::_Change_array(v41 + 16, v52, v50, v48);
            std::vector<wchar_t const *>::_Reallocation_guard::~_Reallocation_guard(&v84);
            v35 = (char *)this + 344;
          }
          *(_QWORD *)v41 = v45;
          v39 = v81;
          v53 = v81[2];
        }
        *(_DWORD *)(v41 + 8) = v53;
      }
      else
      {
        v45 = *(const struct CTransactionHashEntry **)(v42 - 8);
        *(_QWORD *)(v40 + 24) = v42 - 8;
      }
      v54 = v89;
      *v89 = v45;
      memset_0(v45, 0, v39[1]);
      v6 = (unsigned int *)((char *)a2 + 160);
      v36 = (unsigned int)pv;
    }
    v55 = *(unsigned int *)(*(_QWORD *)v35 + 16LL) & ((unsigned __int64)v36 >> 6);
    v56 = 1LL << (v36 & 0x3F);
    v57 = *((_QWORD *)*v54 + v55);
    if ( (v57 & v56) != 0 )
      v90 = v6;
    else
      *((_QWORD *)*v54 + v55) = v56 | v57;
  }
  if ( (*((_DWORD *)a2 + 37) & 0x10000000) == 0 )
    goto LABEL_4;
  v12 = (char *)this + 368;
  v13 = *v6;
  LODWORD(pv) = v13;
  v14 = v13 >> *(_DWORD *)(*((_QWORD *)this + 46) + 20LL);
  if ( v14 < *((_DWORD *)this + 94) )
  {
    v15 = (const struct CTransactionHashEntry **)_sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToStart((char *)this + 368);
  }
  else if ( v14 >= *((_DWORD *)this + 95) )
  {
    v15 = (const struct CTransactionHashEntry **)_sparse_bit<dynamic_sparse_bit<unsigned __int64>>::_AddPagesToEnd((char *)this + 368);
  }
  else
  {
    v15 = (const struct CTransactionHashEntry **)(*((_QWORD *)this + 48) + 8LL * (v14 - *((_DWORD *)this + 94)));
  }
  v89 = v15;
  if ( !*v15 )
  {
    v16 = *(unsigned int **)v12;
    v81 = v16;
    v17 = TPUtils::combinable<sparse_bit_allocator<unsigned __int64>::CAllocatorState>::local(v16 + 12);
    v18 = v17;
    v19 = *(_QWORD *)(v17 + 24);
    if ( *(_QWORD *)(v17 + 16) != v19 )
    {
      v22 = *(const struct CTransactionHashEntry **)(v19 - 8);
      *(_QWORD *)(v17 + 24) = v19 - 8;
      goto LABEL_29;
    }
    v20 = *(unsigned int *)(v17 + 8);
    if ( (unsigned int)v20 < v16[7] )
    {
      v22 = (const struct CTransactionHashEntry *)(*(_QWORD *)v17 + 8 * v20);
      v30 = v20 + v16[2];
      goto LABEL_28;
    }
    v22 = (const struct CTransactionHashEntry *)_aligned_malloc(8LL * v16[7], v16[8]);
    v82 = v22;
    if ( !v22 )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0x430,
        (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\sparse_bit.h",
        v21);
    v23 = (_QWORD *)(v18 + 40);
    v24 = *(const struct CTransactionHashEntry ***)(v18 + 48);
    if ( v24 == *(const struct CTransactionHashEntry ***)(v18 + 56) )
    {
      std::vector<unsigned __int64 *>::_Emplace_reallocate<unsigned __int64 * const &>(v23, v24, &v82);
      v22 = v82;
      v23 = (_QWORD *)(v18 + 40);
    }
    else
    {
      *v24 = v22;
      *(_QWORD *)(v18 + 48) += 8LL;
    }
    v25 = v81[6] * ((__int64)(v23[1] - *v23) >> 3);
    v26 = *(_QWORD *)(v18 + 16);
    if ( v25 <= (*(_QWORD *)(v18 + 32) - v26) >> 3 )
    {
LABEL_27:
      *(_QWORD *)v18 = v22;
      v16 = v81;
      v30 = v81[2];
LABEL_28:
      *(_DWORD *)(v18 + 8) = v30;
LABEL_29:
      v31 = v89;
      *v89 = v22;
      memset_0(v22, 0, v16[1]);
      v6 = v90;
      v13 = (unsigned int)pv;
      goto LABEL_34;
    }
    if ( v25 <= 0x1FFFFFFFFFFFFFFFLL )
    {
      v27 = (*(_QWORD *)(v18 + 24) - v26) >> 3;
      v28 = std::_Get_size_of_n<8>(v25);
      v29 = (void *)std::_Allocate<16,std::_Default_allocate_traits>(v28);
      v84 = v18 + 16;
      v86 = v25;
      memmove_0(v29, *(const void **)(v18 + 16), *(_QWORD *)(v18 + 24) - *(_QWORD *)(v18 + 16));
      v85 = 0;
      std::vector<unsigned __int64 *>::_Change_array(v18 + 16, v29, v27, v25);
      std::vector<wchar_t const *>::_Reallocation_guard::~_Reallocation_guard(&v84);
      v12 = (char *)this + 368;
      goto LABEL_27;
    }
LABEL_90:
    std::_Xlength_error("vector too long");
  }
  v31 = v89;
LABEL_34:
  v32 = ((unsigned __int64)v13 >> 6) & *(unsigned int *)(*(_QWORD *)v12 + 16LL);
  v33 = 1LL << (v13 & 0x3F);
  v34 = *((_QWORD *)*v31 + v32);
  if ( (v34 & v33) == 0 )
    *((_QWORD *)*v31 + v32) = v33 | v34;
LABEL_4:
  v7 = *((_DWORD *)a2 + 43);
  if ( v7 )
  {
    v10 = (_QWORD *)CalculatedCloudPropertyFlagsToString<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(
                      &pv,
                      v7);
    ETWLog::Log(L"CPriorityQueue::UpdateCache, wid: %d, updating CLOUD flags %ws", *v6, *v10);
    if ( pv )
      CoTaskMemFree(pv);
    v82 = a2;
    v83 = v7;
    lambda_d3fabef4439850f5940b90554a5ae656_::operator()(&v82, 2, (char *)this + 560);
    lambda_d3fabef4439850f5940b90554a5ae656_::operator()(&v82, 0x4000000, (char *)this + 584);
    lambda_d3fabef4439850f5940b90554a5ae656_::operator()(&v82, 0x8000000, (char *)this + 608);
    lambda_d3fabef4439850f5940b90554a5ae656_::operator()(&v82, 64, (char *)this + 824);
    lambda_d3fabef4439850f5940b90554a5ae656_::operator()(&v82, 0x1000000, (char *)this + 848);
    lambda_d3fabef4439850f5940b90554a5ae656_::operator()(&v82, 0x2000000, (char *)this + 872);
    lambda_d3fabef4439850f5940b90554a5ae656_::operator()(&v82, 0x100000, (char *)this + 896);
    lambda_d3fabef4439850f5940b90554a5ae656_::operator()(&v82, 0x200000, (char *)this + 920);
    lambda_d3fabef4439850f5940b90554a5ae656_::operator()(&v82, 1, (char *)this + 536);
    lambda_d3fabef4439850f5940b90554a5ae656_::operator()(&v82, 4, (char *)this + 632);
    lambda_d3fabef4439850f5940b90554a5ae656_::operator()(&v82, 16, (char *)this + 656);
    lambda_d3fabef4439850f5940b90554a5ae656_::operator()(&v82, 32, (char *)this + 680);
    lambda_d3fabef4439850f5940b90554a5ae656_::operator()(&v82, 0x8000, (char *)this + 704);
    lambda_d3fabef4439850f5940b90554a5ae656_::operator()(&v82, 0x10000, (char *)this + 752);
    lambda_d3fabef4439850f5940b90554a5ae656_::operator()(&v82, 0x20000, (char *)this + 728);
    lambda_d3fabef4439850f5940b90554a5ae656_::operator()(&v82, 0x40000, (char *)this + 776);
    lambda_d3fabef4439850f5940b90554a5ae656_::operator()(&v82, 0x80000, (char *)this + 800);
    lambda_d3fabef4439850f5940b90554a5ae656_::operator()(&v82, 128, (char *)this + 392);
    lambda_d3fabef4439850f5940b90554a5ae656_::operator()(&v82, 256, (char *)this + 416);
    lambda_d3fabef4439850f5940b90554a5ae656_::operator()(&v82, 512, (char *)this + 440);
    lambda_d3fabef4439850f5940b90554a5ae656_::operator()(&v82, 1024, (char *)this + 464);
    lambda_d3fabef4439850f5940b90554a5ae656_::operator()(&v82, 2048, (char *)this + 488);
    lambda_d3fabef4439850f5940b90554a5ae656_::operator()(&v82, 4096, (char *)this + 512);
    lambda_d3fabef4439850f5940b90554a5ae656_::operator()(&v82, 0x2000, (char *)this + 944);
    lambda_d3fabef4439850f5940b90554a5ae656_::operator()(&v82, 0x4000, (char *)this + 968);
    lambda_d3fabef4439850f5940b90554a5ae656_::operator()(&v82, 0x400000, (char *)this + 992);
    lambda_d3fabef4439850f5940b90554a5ae656_::operator()(&v82, 0x800000, (char *)this + 1016);
    if ( (v7 & 0xF300042) != 0 )
    {
      CPriorityQueue::SendCloudNotification(v11);
      ETWLog::Log(L"CPriorityQueue::UpdateCache, SendingCloudNotification for wid: %d", *v6);
    }
  }
  if ( *((_QWORD *)a2 + 24) )
  {
    v8 = (_QWORD *)((char *)a2 + 176);
    if ( *((_QWORD *)a2 + 25) > 7u )
      v8 = (_QWORD *)*v8;
    LODWORD(pv) = *v6;
    v9 = (_QWORD *)std::map<unsigned long,std::wstring>::_Try_emplace<unsigned long,>((char *)this + 1072, &v82, &pv);
    std::wstring::assign(*v9 + 40LL, v8);
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_55904201>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_55904201>::GetImpl'::`2'::impl)
    && !*(_DWORD *)CTransactionHashEntry::RequiredTransactionPasses(a2, &pv)
    && *((_DWORD *)a2 + 41) != -1 )
  {
    ++*((_DWORD *)this + 273);
  }
}

```

## disassembly

```asm
0x180044870  mov     [rsp-38h+arg_8], rbx
0x180044875  push    rbp
0x180044876  push    rsi
0x180044877  push    rdi
0x180044878  push    r12
0x18004487a  push    r13
0x18004487c  push    r14
0x18004487e  push    r15
0x180044880  mov     rbp, rsp
0x180044883  sub     rsp, 50h
0x180044887  mov     rsi, rdx
0x18004488a  mov     r13, rcx
0x18004488d  call    ?GetQueue@CPriorityQueue@@QEAA?AW4QUEUE_TYPE@@AEBVCTransactionHashEntry@@@Z; CPriorityQueue::GetQueue(CTransactionHashEntry const &)
0x180044892  mov     r15d, eax
0x180044895  mov     dword ptr [rbp+arg_10], eax
0x180044898  cmp     byte ptr [r13+150h], 0
0x1800448a0  jz      loc_180045254
0x1800448a6  mov     r8, rsi; struct CTransactionHashEntry *
0x1800448a9  mov     edx, r15d; enum QUEUE_TYPE
0x1800448ac  mov     rcx, r13; this
0x1800448af  call    ?AddEntryToQueue@CPriorityQueue@@AEAAXW4QUEUE_TYPE@@AEBVCTransactionHashEntry@@@Z; CPriorityQueue::AddEntryToQueue(QUEUE_TYPE,CTransactionHashEntry const &)
0x1800448b4  lea     rdi, [rsi+0A0h]
0x1800448bb  mov     [rbp+arg_18], rdi
0x1800448bf  test    dword ptr [rsi+94h], 400000h
0x1800448c9  jnz     loc_180044DF6
0x1800448cf  test    dword ptr [rsi+94h], 10000000h
0x1800448d9  jnz     loc_180044BF0
0x1800448df  mov     ebx, [rsi+0ACh]
0x1800448e5  test    ebx, ebx
0x1800448e7  jnz     short loc_180044958
0x1800448e9  cmp     qword ptr [rsi+0C0h], 0
0x1800448f1  jz      short loc_18004492C
0x1800448f3  lea     rbx, [rsi+0B0h]
0x1800448fa  cmp     qword ptr [rbx+18h], 7
0x1800448ff  jbe     short loc_180044904
0x180044901  mov     rbx, [rbx]
0x180044904  mov     eax, [rdi]
0x180044906  mov     dword ptr [rbp+pv], eax
0x180044909  lea     rcx, [r13+430h]
0x180044910  lea     r8, [rbp+pv]
0x180044914  lea     rdx, [rbp+var_28]
0x180044918  call    ??$_Try_emplace@K$$V@?$map@KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBKV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@PEAX@std@@_N@1@$$QEAK@Z; std::map<ulong,std::wstring>::_Try_emplace<ulong,>(ulong &&)
0x18004491d  mov     rcx, [rax]
0x180044920  add     rcx, 28h ; '('
0x180044924  mov     rdx, rbx
0x180044927  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x18004492c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_55904201@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_55904201@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_55904201> `wil::Feature<__WilFeatureTraits_Feature_55904201>::GetImpl(void)'::`2'::impl
0x180044933  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_55904201@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_55904201>::__private_IsEnabled(void)
0x180044938  test    al, al
0x18004493a  jnz     loc_1800452B2
0x180044940  mov     rbx, [rsp+50h+arg_8]
0x180044948  add     rsp, 50h
0x18004494c  pop     r15
0x18004494e  pop     r14
0x180044950  pop     r13
0x180044952  pop     r12
0x180044954  pop     rdi
0x180044955  pop     rsi
0x180044956  pop     rbp
0x180044957  retn
0x180044958  mov     edx, ebx
0x18004495a  lea     rcx, [rbp+pv]
0x18004495e  call    ??$CalculatedCloudPropertyFlagsToString@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@K@Z; CalculatedCloudPropertyFlagsToString<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(ulong)
0x180044963  nop
0x180044964  mov     r8, [rax]
0x180044967  mov     edx, [rdi]
0x180044969  lea     rcx, aCpriorityqueue_0; "CPriorityQueue::UpdateCache, wid: %d, u"...
0x180044970  call    ?Log@ETWLog@@SAXPEB_WZZ; ETWLog::Log(wchar_t const *,...)
0x180044975  nop
0x180044976  mov     rcx, [rbp+pv]; pv
0x18004497a  test    rcx, rcx
0x18004497d  jnz     loc_180044BE5
0x180044983  mov     [rbp+var_28], rsi
0x180044987  mov     [rbp+var_20], ebx
0x18004498a  lea     r8, [r13+230h]
0x180044991  mov     edx, 2
0x180044996  lea     rcx, [rbp+var_28]
0x18004499a  call    _lambda_d3fabef4439850f5940b90554a5ae656___operator__
0x18004499f  lea     r8, [r13+248h]
0x1800449a6  mov     edx, 4000000h
0x1800449ab  lea     rcx, [rbp+var_28]
0x1800449af  call    _lambda_d3fabef4439850f5940b90554a5ae656___operator__
0x1800449b4  lea     r8, [r13+260h]
0x1800449bb  mov     edx, 8000000h
0x1800449c0  lea     rcx, [rbp+var_28]
0x1800449c4  call    _lambda_d3fabef4439850f5940b90554a5ae656___operator__
0x1800449c9  lea     r8, [r13+338h]
0x1800449d0  mov     edx, 40h ; '@'
0x1800449d5  lea     rcx, [rbp+var_28]
0x1800449d9  call    _lambda_d3fabef4439850f5940b90554a5ae656___operator__
0x1800449de  lea     r8, [r13+350h]
0x1800449e5  mov     edx, 1000000h
0x1800449ea  lea     rcx, [rbp+var_28]
0x1800449ee  call    _lambda_d3fabef4439850f5940b90554a5ae656___operator__
0x1800449f3  lea     r8, [r13+368h]
0x1800449fa  mov     edx, 2000000h
0x1800449ff  lea     rcx, [rbp+var_28]
0x180044a03  call    _lambda_d3fabef4439850f5940b90554a5ae656___operator__
0x180044a08  lea     r8, [r13+380h]
0x180044a0f  mov     edx, 100000h
0x180044a14  lea     rcx, [rbp+var_28]
0x180044a18  call    _lambda_d3fabef4439850f5940b90554a5ae656___operator__
0x180044a1d  lea     r8, [r13+398h]
0x180044a24  mov     edx, 200000h
0x180044a29  lea     rcx, [rbp+var_28]
0x180044a2d  call    _lambda_d3fabef4439850f5940b90554a5ae656___operator__
0x180044a32  lea     r8, [r13+218h]
0x180044a39  mov     edx, 1
0x180044a3e  lea     rcx, [rbp+var_28]
0x180044a42  call    _lambda_d3fabef4439850f5940b90554a5ae656___operator__
0x180044a47  lea     r8, [r13+278h]
0x180044a4e  mov     edx, 4
0x180044a53  lea     rcx, [rbp+var_28]
0x180044a57  call    _lambda_d3fabef4439850f5940b90554a5ae656___operator__
0x180044a5c  lea     r8, [r13+290h]
0x180044a63  mov     edx, 10h
0x180044a68  lea     rcx, [rbp+var_28]
0x180044a6c  call    _lambda_d3fabef4439850f5940b90554a5ae656___operator__
0x180044a71  lea     r8, [r13+2A8h]
0x180044a78  mov     edx, 20h ; ' '
0x180044a7d  lea     rcx, [rbp+var_28]
0x180044a81  call    _lambda_d3fabef4439850f5940b90554a5ae656___operator__
0x180044a86  lea     r8, [r13+2C0h]
0x180044a8d  mov     edx, 8000h
0x180044a92  lea     rcx, [rbp+var_28]
0x180044a96  call    _lambda_d3fabef4439850f5940b90554a5ae656___operator__
0x180044a9b  lea     r8, [r13+2F0h]
0x180044aa2  mov     edx, 10000h
0x180044aa7  lea     rcx, [rbp+var_28]
0x180044aab  call    _lambda_d3fabef4439850f5940b90554a5ae656___operator__
0x180044ab0  lea     r8, [r13+2D8h]
0x180044ab7  mov     edx, 20000h
0x180044abc  lea     rcx, [rbp+var_28]
0x180044ac0  call    _lambda_d3fabef4439850f5940b90554a5ae656___operator__
0x180044ac5  lea     r8, [r13+308h]
0x180044acc  mov     edx, 40000h
0x180044ad1  lea     rcx, [rbp+var_28]
0x180044ad5  call    _lambda_d3fabef4439850f5940b90554a5ae656___operator__
0x180044ada  lea     r8, [r13+320h]
0x180044ae1  mov     edx, 80000h
0x180044ae6  lea     rcx, [rbp+var_28]
0x180044aea  call    _lambda_d3fabef4439850f5940b90554a5ae656___operator__
0x180044aef  lea     r8, [r13+188h]
0x180044af6  mov     edx, 80h
0x180044afb  lea     rcx, [rbp+var_28]
0x180044aff  call    _lambda_d3fabef4439850f5940b90554a5ae656___operator__
0x180044b04  lea     r8, [r13+1A0h]
0x180044b0b  mov     edx, 100h
0x180044b10  lea     rcx, [rbp+var_28]
0x180044b14  call    _lambda_d3fabef4439850f5940b90554a5ae656___operator__
0x180044b19  lea     r8, [r13+1B8h]
0x180044b20  mov     edx, 200h
0x180044b25  lea     rcx, [rbp+var_28]
0x180044b29  call    _lambda_d3fabef4439850f5940b90554a5ae656___operator__
0x180044b2e  lea     r8, [r13+1D0h]
0x180044b35  mov     edx, 400h
0x180044b3a  lea     rcx, [rbp+var_28]
0x180044b3e  call    _lambda_d3fabef4439850f5940b90554a5ae656___operator__
0x180044b43  lea     r8, [r13+1E8h]
0x180044b4a  mov     edx, 800h
0x180044b4f  lea     rcx, [rbp+var_28]
0x180044b53  call    _lambda_d3fabef4439850f5940b90554a5ae656___operator__
0x180044b58  lea     r8, [r13+200h]
0x180044b5f  mov     edx, 1000h
0x180044b64  lea     rcx, [rbp+var_28]
0x180044b68  call    _lambda_d3fabef4439850f5940b90554a5ae656___operator__
0x180044b6d  lea     r8, [r13+3B0h]
0x180044b74  mov     edx, 2000h
0x180044b79  lea     rcx, [rbp+var_28]
0x180044b7d  call    _lambda_d3fabef4439850f5940b90554a5ae656___operator__
0x180044b82  lea     r8, [r13+3C8h]
0x180044b89  mov     edx, 4000h
0x180044b8e  lea     rcx, [rbp+var_28]
0x180044b92  call    _lambda_d3fabef4439850f5940b90554a5ae656___operator__
0x180044b97  lea     r8, [r13+3E0h]
0x180044b9e  mov     edx, 400000h
0x180044ba3  lea     rcx, [rbp+var_28]
0x180044ba7  call    _lambda_d3fabef4439850f5940b90554a5ae656___operator__
0x180044bac  lea     r8, [r13+3F8h]
0x180044bb3  mov     edx, 800000h
0x180044bb8  lea     rcx, [rbp+var_28]
0x180044bbc  call    _lambda_d3fabef4439850f5940b90554a5ae656___operator__
0x180044bc1  test    ebx, 0F300042h
0x180044bc7  jz      loc_1800448E9
0x180044bcd  call    ?SendCloudNotification@CPriorityQueue@@AEAAXXZ; CPriorityQueue::SendCloudNotification(void)
0x180044bd2  mov     edx, [rdi]
0x180044bd4  lea     rcx, aCpriorityqueue_4; "CPriorityQueue::UpdateCache, SendingClo"...
0x180044bdb  call    ?Log@ETWLog@@SAXPEB_WZZ; ETWLog::Log(wchar_t const *,...)
0x180044be0  jmp     loc_1800448E9
0x180044be5  call    cs:__imp_CoTaskMemFree
0x180044beb  jmp     loc_180044983
0x180044bf0  lea     rbx, [r13+170h]
0x180044bf7  mov     r14d, [rdi]
0x180044bfa  mov     dword ptr [rbp+pv], r14d
0x180044bfe  mov     rcx, [rbx]
0x180044c01  mov     ecx, [rcx+14h]
0x180044c04  mov     edx, r14d
0x180044c07  shr     edx, cl
0x180044c09  cmp     edx, [rbx+8]
0x180044c0c  jb      loc_180045025
0x180044c12  cmp     edx, [rbx+0Ch]
0x180044c15  jnb     loc_180045018
0x180044c1b  sub     edx, [rbx+8]
0x180044c1e  mov     rax, [rbx+10h]
0x180044c22  lea     rax, [rax+rdx*8]
0x180044c26  mov     [rbp+arg_10], rax
0x180044c2a  cmp     qword ptr [rax], 0
0x180044c2e  jnz     loc_180044DB5
0x180044c34  mov     r14, [rbx]
0x180044c37  mov     [rbp+var_30], r14
0x180044c3b  lea     rcx, [r14+30h]
0x180044c3f  call    ?local@?$combinable@UCAllocatorState@?$sparse_bit_allocator@_K@@@TPUtils@@QEAAAEAUCAllocatorState@?$sparse_bit_allocator@_K@@XZ; TPUtils::combinable<sparse_bit_allocator<unsigned __int64>::CAllocatorState>::local(void)
0x180044c44  mov     r12, rax
0x180044c47  mov     rcx, [rax+18h]
0x180044c4b  cmp     [rax+10h], rcx
0x180044c4f  jnz     loc_180044DA7
0x180044c55  mov     r8d, [rax+8]
0x180044c59  cmp     r8d, [r14+1Ch]
0x180044c5d  jb      loc_180044D7D
0x180044c63  mov     edx, [r14+20h]; Alignment
0x180044c67  mov     ecx, [r14+1Ch]
0x180044c6b  shl     rcx, 3; Size
0x180044c6f  call    cs:__imp__aligned_malloc
0x180044c75  mov     r15, rax
0x180044c78  mov     [rbp+var_28], rax
0x180044c7c  mov     rcx, [rbp+38h]; this
0x180044c80  test    rax, rax
0x180044c83  jz      loc_180045292
0x180044c89  lea     rax, [r12+28h]
0x180044c8e  mov     rdx, [rax+8]
0x180044c92  cmp     rdx, [rax+10h]
0x180044c96  jz      loc_180044D8D
0x180044c9c  mov     [rdx], r15
0x180044c9f  add     qword ptr [rax+8], 8
0x180044ca4  mov     r14, [rax+8]
0x180044ca8  sub     r14, [rax]
0x180044cab  sar     r14, 3
0x180044caf  mov     rax, [rbp+var_30]
0x180044cb3  mov     eax, [rax+18h]
0x180044cb6  imul    r14, rax
0x180044cba  mov     rcx, [r12+10h]
0x180044cbf  mov     rax, [r12+20h]
0x180044cc4  sub     rax, rcx
0x180044cc7  sar     rax, 3
0x180044ccb  cmp     r14, rax
0x180044cce  jbe     short loc_180044D4C
0x180044cd0  mov     rax, 1FFFFFFFFFFFFFFFh
0x180044cda  cmp     r14, rax
0x180044cdd  ja      loc_1800452A4
0x180044ce3  mov     rdi, [r12+18h]
0x180044ce8  sub     rdi, rcx
0x180044ceb  sar     rdi, 3
0x180044cef  mov     rcx, r14
0x180044cf2  call    ??$_Get_size_of_n@$07@std@@YA_K_K@Z; std::_Get_size_of_n<8>(unsigned __int64)
0x180044cf7  mov     rcx, rax
0x180044cfa  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180044cff  mov     rbx, rax
0x180044d02  lea     rax, [r12+10h]
0x180044d07  mov     [rbp+var_18], rax
0x180044d0b  mov     [rbp+var_8], r14
0x180044d0f  mov     r8, [rax+8]
0x180044d13  sub     r8, [rax]; Size
0x180044d16  mov     rdx, [rax]; Src
0x180044d19  mov     rcx, rbx; void *
0x180044d1c  call    memmove_0
0x180044d21  mov     [rbp+var_10], 0
0x180044d29  mov     r9, r14
0x180044d2c  mov     r8, rdi
0x180044d2f  mov     rdx, rbx
0x180044d32  lea     rcx, [r12+10h]
0x180044d37  call    ?_Change_array@?$vector@PEA_KV?$allocator@PEA_K@std@@@std@@AEAAXQEAPEA_K_K1@Z; std::vector<unsigned __int64 *>::_Change_array(unsigned __int64 * * const,unsigned __int64,unsigned __int64)
0x180044d3c  lea     rcx, [rbp+var_18]
0x180044d40  call    ??1_Reallocation_guard@?$vector@PEB_WV?$allocator@PEB_W@std@@@std@@QEAA@XZ; std::vector<wchar_t const *>::_Reallocation_guard::~_Reallocation_guard(void)
0x180044d45  lea     rbx, [r13+170h]
0x180044d4c  mov     [r12], r15
0x180044d50  mov     r14, [rbp+var_30]
0x180044d54  mov     ecx, [r14+8]
0x180044d58  mov     [r12+8], ecx
0x180044d5d  mov     r12, [rbp+arg_10]
0x180044d61  mov     [r12], r15
0x180044d65  mov     r8d, [r14+4]; Size
0x180044d69  xor     edx, edx; Val
0x180044d6b  mov     rcx, r15; void *
0x180044d6e  call    memset_0
0x180044d73  mov     rdi, [rbp+arg_18]
0x180044d77  mov     r14d, dword ptr [rbp+pv]
0x180044d7b  jmp     short loc_180044DB9
0x180044d7d  mov     rcx, [rax]
0x180044d80  lea     r15, [rcx+r8*8]
0x180044d84  mov     ecx, [r14+8]
0x180044d88  add     ecx, r8d
0x180044d8b  jmp     short loc_180044D58
0x180044d8d  lea     r8, [rbp+var_28]
0x180044d91  mov     rcx, rax
0x180044d94  call    ??$_Emplace_reallocate@AEBQEA_K@?$vector@PEA_KV?$allocator@PEA_K@std@@@std@@AEAAPEAPEA_KQEAPEA_KAEBQEA_K@Z; std::vector<unsigned __int64 *>::_Emplace_reallocate<unsigned __int64 * const &>(unsigned __int64 * * const,unsigned __int64 * const &)
0x180044d99  mov     r15, [rbp+var_28]
0x180044d9d  lea     rax, [r12+28h]
0x180044da2  jmp     loc_180044CA4
0x180044da7  lea     rax, [rcx-8]
0x180044dab  mov     r15, [rax]
  ... truncated ...
```
