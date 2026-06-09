# DusmGetAttributedNetworkUsageImpl(DusmConnection const &,int,_SYSTEMTIME const &,_SYSTEMTIME const &,int const *)

- ea: `0x180022d90`
- end: `0x1800235dd`
- name: `?DusmGetAttributedNetworkUsageImpl@@YA?AV?$map@UDusmAppInfo@@UDUSM_NETWORK_USAGE@@UDusmAppInfoComparator@@V?$allocator@U?$pair@$$CBUDusmAppInfo@@UDUSM_NETWORK_USAGE@@@std@@@std@@@std@@AEBVDusmConnection@@HAEBU_SYSTEMTIME@@1PEBH@Z`
- size: `2125`
- prototype: ``
- caller_count: `1`
- callee_count: `36`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180013e20`

## callees

- `0x180004b10`
- `0x180004f40`
- `0x1800050a4`
- `0x180007c90`
- `0x18000809c`
- `0x180008704`
- `0x18000dc74`
- `0x18000de6c`
- `0x18000ee34`
- `0x18000f820`
- `0x180012fcc`
- `0x180013444`
- `0x18001742c`
- `0x180018bdc`
- `0x180020a30`
- `0x1800210cc`
- `0x180021204`
- `0x180021e60`
- `0x180021ea8`
- `0x180021f14`
- `0x180022058`
- `0x1800220a4`
- `0x180022174`
- `0x180022728`
- `0x180022750`
- `0x1800227cc`
- `0x1800229b0`
- `0x180022b70`
- `0x180022c50`
- `0x180022d90`
- `0x180024898`
- `0x18002a1c4`
- `0x18002a534`
- `0x18003f300`
- `0x180040120`
- `0x180041778`

## pseudocode

```c
// Hidden C++ exception states: #wind=21
__int64 *__fastcall DusmGetAttributedNetworkUsageImpl(__int64 *a1, __int64 a2, int a3, __int64 a4, __int64 a5, int *a6)
{
  __int64 v6; // r12
  const struct _GUID *v7; // r15
  __int64 *v8; // rsi
  __int64 v9; // r13
  __int64 v10; // rdi
  int v11; // r14d
  __int64 ResetTime; // rbx
  __int64 *v13; // rax
  __int64 v14; // rcx
  __int64 *v15; // rax
  __int64 v16; // rcx
  __int64 ProfileIndexList; // rax
  __int64 *v18; // rax
  __int64 v19; // rcx
  __int64 *v20; // rax
  __int64 v21; // rcx
  __int64 *v22; // rax
  __int64 v23; // rcx
  _DWORD *v24; // rax
  __int64 *v25; // rax
  __int64 v26; // rcx
  unsigned int Data1; // ebx
  _DWORD *v28; // rax
  __int64 v29; // r15
  __int64 v30; // r12
  __int64 v31; // r13
  __int64 v32; // rbx
  __int64 v33; // rdi
  __int64 v34; // r14
  __int64 v35; // rdx
  __int64 v36; // rcx
  int v37; // esi
  __int64 v38; // rdx
  __int64 v39; // rcx
  __int64 v40; // r8
  __int64 v41; // r9
  __int64 v42; // r8
  __int64 v43; // r9
  __int64 v44; // rdx
  __int64 v45; // rcx
  __int64 v46; // rax
  __int64 v47; // rbx
  __int64 v48; // rdi
  __int64 v49; // rsi
  __int64 v50; // r8
  __int64 v51; // r9
  __int64 v53; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v54; // [rsp+68h] [rbp-98h] BYREF
  __int64 v55; // [rsp+70h] [rbp-90h] BYREF
  __int64 v56; // [rsp+78h] [rbp-88h] BYREF
  int v57; // [rsp+80h] [rbp-80h]
  int v58; // [rsp+84h] [rbp-7Ch]
  __int64 v59; // [rsp+88h] [rbp-78h] BYREF
  __int64 v60; // [rsp+90h] [rbp-70h] BYREF
  __int64 v61; // [rsp+98h] [rbp-68h] BYREF
  __int64 v62; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v63; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v64; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v65; // [rsp+B8h] [rbp-48h] BYREF
  __int64 *v66; // [rsp+C0h] [rbp-40h]
  __int64 v67; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v68; // [rsp+D0h] [rbp-30h]
  __int64 v69; // [rsp+D8h] [rbp-28h]
  __int64 v70; // [rsp+E0h] [rbp-20h]
  __int64 *v71; // [rsp+E8h] [rbp-18h]
  __int128 v72; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v73; // [rsp+100h] [rbp+0h]
  __int128 v74; // [rsp+108h] [rbp+8h] BYREF
  __int64 v75; // [rsp+118h] [rbp+18h]
  unsigned int *v76; // [rsp+120h] [rbp+20h] BYREF
  _DWORD *v77; // [rsp+128h] [rbp+28h] BYREF
  __int128 v78; // [rsp+130h] [rbp+30h] BYREF
  __int64 v79; // [rsp+140h] [rbp+40h]
  __int64 v80; // [rsp+150h] [rbp+50h] BYREF
  __int64 v81; // [rsp+158h] [rbp+58h]
  __int64 v82; // [rsp+160h] [rbp+60h]
  __int64 v83; // [rsp+168h] [rbp+68h]
  _QWORD v84[6]; // [rsp+190h] [rbp+90h] BYREF
  int v85; // [rsp+1C0h] [rbp+C0h]
  int v86; // [rsp+1E0h] [rbp+E0h]
  _BYTE v87[16]; // [rsp+1E8h] [rbp+E8h] BYREF
  __int64 v88; // [rsp+1F8h] [rbp+F8h]

  v6 = a4;
  v62 = a4;
  v58 = a3;
  v7 = (const struct _GUID *)a2;
  v61 = a2;
  v8 = a1;
  v66 = a1;
  v71 = a1;
  v9 = a5;
  v59 = a5;
  v10 = (__int64)a6;
  v11 = 0;
  v57 = 0;
  v77 = 0;
  DusmSruQueryStats(&v77, a4, a5, 0);
  v72 = 0;
  v73 = 0;
  ResetTime = (__int64)DusmStore::QueryResetTime((const struct DusmConnection *)v7);
  v55 = ResetTime;
  if ( ResetTime )
  {
    v13 = std::make_unique<DusmResetTimeFilter,_FILETIME &,0>(&v54, &v55);
    v14 = *v13;
    *v13 = 0;
    v53 = v14;
    if ( *((_QWORD *)&v72 + 1) == v73 )
    {
      std::vector<std::unique_ptr<DusmFilter>>::_Emplace_reallocate<std::unique_ptr<DusmFilter>>(
        (__int64 *)&v72,
        *((__int64 *)&v72 + 1),
        &v53);
    }
    else
    {
      v53 = 0;
      **((_QWORD **)&v72 + 1) = v14;
      *((_QWORD *)&v72 + 1) += 8LL;
    }
    std::unique_ptr<DusmFilter>::~unique_ptr<DusmFilter>(&v53);
    std::unique_ptr<DusmFilter>::~unique_ptr<DusmFilter>(&v54);
  }
  if ( v7[1].Data1 == 3 )
  {
    memset_0(&v80, 0, 0x40u);
    DusmStore::QueryProfileIndexList((__int64)&v80, (__int64)v7);
    v15 = std::make_unique<DusmProfileIndexAppFilter,std::unordered_set<unsigned long> &,0>(&v54, (__int64)&v80);
    v16 = *v15;
    *v15 = 0;
    v53 = v16;
    if ( *((_QWORD *)&v72 + 1) != v73 )
    {
      v53 = 0;
      **((_QWORD **)&v72 + 1) = v16;
      *((_QWORD *)&v72 + 1) += 8LL;
LABEL_15:
      std::unique_ptr<DusmFilter>::~unique_ptr<DusmFilter>(&v53);
      std::unique_ptr<DusmFilter>::~unique_ptr<DusmFilter>(&v54);
      std::_Hash<std::_Uset_traits<unsigned long,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<unsigned long>,0>>::~_Hash<std::_Uset_traits<unsigned long,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<unsigned long>,0>>((__int64)&v80);
      goto LABEL_20;
    }
    goto LABEL_14;
  }
  if ( v58 && v7[1].Data1 == 2 )
  {
    ProfileIndexList = DusmConnection::GetProfileIndexList(v7, &v80);
    v18 = std::make_unique<DusmProfileIndexAppFilter,std::unordered_set<unsigned long>,0>(&v54, ProfileIndexList);
    v19 = *v18;
    *v18 = 0;
    v53 = v19;
    if ( *((_QWORD *)&v72 + 1) != v73 )
    {
      v53 = 0;
      **((_QWORD **)&v72 + 1) = v19;
      *((_QWORD *)&v72 + 1) += 8LL;
      goto LABEL_15;
    }
LABEL_14:
    std::vector<std::unique_ptr<DusmFilter>>::_Emplace_reallocate<std::unique_ptr<DusmFilter>>(
      (__int64 *)&v72,
      *((__int64 *)&v72 + 1),
      &v53);
    goto LABEL_15;
  }
  v20 = std::make_unique<DusmInterfaceFilter,_GUID const &,0>(&v54, v7 + 2);
  v21 = *v20;
  *v20 = 0;
  v53 = v21;
  if ( *((_QWORD *)&v72 + 1) == v73 )
  {
    std::vector<std::unique_ptr<DusmFilter>>::_Emplace_reallocate<std::unique_ptr<DusmFilter>>(
      (__int64 *)&v72,
      *((__int64 *)&v72 + 1),
      &v53);
  }
  else
  {
    v53 = 0;
    **((_QWORD **)&v72 + 1) = v21;
    *((_QWORD *)&v72 + 1) += 8LL;
  }
  std::unique_ptr<DusmFilter>::~unique_ptr<DusmFilter>(&v53);
  std::unique_ptr<DusmFilter>::~unique_ptr<DusmFilter>(&v54);
LABEL_20:
  if ( a6 )
  {
    v22 = std::make_unique<DusmRoamingFilter,int const &,0>(&v54, a6);
    v23 = *v22;
    v10 = 0;
    *v22 = 0;
    v53 = v23;
    if ( *((_QWORD *)&v72 + 1) == v73 )
    {
      std::vector<std::unique_ptr<DusmFilter>>::_Emplace_reallocate<std::unique_ptr<DusmFilter>>(
        (__int64 *)&v72,
        *((__int64 *)&v72 + 1),
        &v53);
    }
    else
    {
      v53 = 0;
      **((_QWORD **)&v72 + 1) = v23;
      *((_QWORD *)&v72 + 1) += 8LL;
    }
    std::unique_ptr<DusmFilter>::~unique_ptr<DusmFilter>(&v53);
    std::unique_ptr<DusmFilter>::~unique_ptr<DusmFilter>(&v54);
  }
  v78 = 0;
  v79 = 0;
  std::map<DusmAppInfo,DUSM_NETWORK_USAGE,DusmAppInfoComparator,std::allocator<std::pair<DusmAppInfo const,DUSM_NETWORK_USAGE>>>::map<DusmAppInfo,DUSM_NETWORK_USAGE,DusmAppInfoComparator,std::allocator<std::pair<DusmAppInfo const,DUSM_NETWORK_USAGE>>>(&v78);
  v24 = v77;
  if ( v77 )
  {
    if ( *v77 )
    {
      do
      {
        DusmRecord::DusmRecord(v84, *((_QWORD *)v24 + 1) + ((unsigned __int64)(unsigned int)v10 << 6), 0);
        if ( (unsigned int)DusmIsRecordAllowed(v84, &v72) )
          DusmRecordBucketer<std::map<DusmAppInfo,DUSM_NETWORK_USAGE,DusmAppInfoComparator,std::allocator<std::pair<DusmAppInfo const,DUSM_NETWORK_USAGE>>>,DusmAppInfoExtractor>::BucketUsageRecord(
            &v78,
            v84);
        DusmRecord::~DusmRecord((DusmRecord *)v84);
        LODWORD(v10) = v10 + 1;
        v24 = v77;
      }
      while ( (unsigned int)v10 < *v77 );
    }
    v10 = 0;
  }
  v76 = (unsigned int *)v10;
  DusmSruQueryStats(&v76, v6, a5, 2u);
  if ( v76 && *v76 > (unsigned int)v10 )
  {
    v74 = 0;
    v75 = v10;
    if ( HIDWORD(v55) != (_DWORD)v10 || (_DWORD)ResetTime )
    {
      v25 = std::make_unique<DusmResetTimeFilter,_FILETIME &,0>(&v54, &v55);
      v26 = *v25;
      *v25 = v10;
      v53 = v26;
      if ( *((_QWORD *)&v74 + 1) == v75 )
      {
        std::vector<std::unique_ptr<DusmFilter>>::_Emplace_reallocate<std::unique_ptr<DusmFilter>>(
          (__int64 *)&v74,
          *((__int64 *)&v74 + 1),
          &v53);
      }
      else
      {
        v53 = v10;
        **((_QWORD **)&v74 + 1) = v26;
        *((_QWORD *)&v74 + 1) += 8LL;
      }
      std::unique_ptr<DusmFilter>::~unique_ptr<DusmFilter>(&v53);
      std::unique_ptr<DusmFilter>::~unique_ptr<DusmFilter>(&v54);
    }
    Data1 = v7[1].Data1;
    v28 = operator new(0x10u);
    v56 = (__int64)v28;
    *(_QWORD *)v28 = &DusmMediaTypeFilter::`vftable';
    v28[2] = Data1;
    v11 = 2;
    LODWORD(v53) = 2;
    v57 = 2;
    v54 = v10;
    v55 = (__int64)v28;
    if ( *((_QWORD *)&v74 + 1) == v75 )
    {
      std::vector<std::unique_ptr<DusmFilter>>::_Emplace_reallocate<std::unique_ptr<DusmFilter>>(
        (__int64 *)&v74,
        *((__int64 *)&v74 + 1),
        &v55);
    }
    else
    {
      v55 = v10;
      **((_QWORD **)&v74 + 1) = v28;
      *((_QWORD *)&v74 + 1) += 8LL;
    }
    std::unique_ptr<DusmFilter>::~unique_ptr<DusmFilter>(&v55);
    std::unique_ptr<DusmFilter>::~unique_ptr<DusmFilter>(&v54);
    v29 = v10;
    v67 = v10;
    v30 = v10;
    v68 = v10;
    v31 = v10;
    v69 = v10;
    v70 = v10;
    v32 = *((_QWORD *)v76 + 1);
    v33 = v32 + ((unsigned __int64)*v76 << 6);
    if ( v32 != v33 )
    {
      v34 = v31;
      do
      {
        DusmRecord::DusmRecord(v84, v32, 2);
        if ( !v88 || v86 == 1 )
        {
          if ( **(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get(v36, v35) + 8) > 5u )
          {
            v56 = v84[0];
            LODWORD(v55) = v85;
            LODWORD(v54) = v86;
            v60 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v87);
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
              v42,
              (int)&dword_180057B24,
              v42,
              v43,
              (const WCHAR **)&v60,
              (__int64)&v54,
              (__int64)&v55,
              (__int64)&v56);
          }
        }
        else
        {
          DusmRecord::GetNetworkUsage(v84, &v80);
          v37 = 0;
          if ( (unsigned int)DusmIsRecordAllowed(v84, &v74) )
          {
            DusmRecordBucketer<std::map<DusmAppInfo,DUSM_NETWORK_USAGE,DusmAppInfoComparator,std::allocator<std::pair<DusmAppInfo const,DUSM_NETWORK_USAGE>>>,DusmAppInfoExtractor>::BucketUsageRecord(
              &v78,
              v84);
            if ( v86 == 3 || (v37 = 1, v86 == 2) )
            {
              v29 += v80;
              v30 += v81;
              v31 += v82;
              v34 += v83;
              v70 = v34;
              v37 = 1;
            }
          }
          if ( **(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get(v39, v38) + 8) > 5u )
          {
            v64 = v84[0];
            v65 = v80;
            v60 = v81;
            LODWORD(v63) = v85;
            LODWORD(v54) = v86;
            v56 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v87);
            LODWORD(v55) = v37;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
              v40,
              (int)byte_180057A95,
              v40,
              v41,
              (__int64)&v55,
              (const WCHAR **)&v56,
              (__int64)&v54,
              (__int64)&v63,
              (__int64)&v60,
              (__int64)&v65,
              (__int64)&v64);
          }
        }
        DusmRecord::~DusmRecord((DusmRecord *)v84);
        v32 += 64;
      }
      while ( v32 != v33 );
      v67 = v29;
      v68 = v30;
      v69 = v31;
      v11 = v53;
      v8 = v66;
    }
    DusmRecordBucketer<std::map<DusmAppInfo,DUSM_NETWORK_USAGE,DusmAppInfoComparator,std::allocator<std::pair<DusmAppInfo const,DUSM_NETWORK_USAGE>>>,DusmAppInfoExtractor>::DedupUsageFromWnsService(
      &v78,
      &v67);
    v10 = 0;
    if ( (_QWORD)v74 )
    {
      std::_Destroy_range<std::allocator<std::unique_ptr<DusmFilter>>>(v74, *((__int64 *)&v74 + 1));
      std::_Deallocate<16>((void *)v74, (v75 - v74) & 0xFFFFFFFFFFFFFFF8uLL);
    }
    v9 = v59;
    v6 = v62;
    v7 = (const struct _GUID *)v61;
  }
  *(_OWORD *)v8 = 0;
  std::_Tree<std::_Tmap_traits<DusmAppInfo,DUSM_NETWORK_USAGE,DusmAppInfoComparator,std::allocator<std::pair<DusmAppInfo const,DUSM_NETWORK_USAGE>>,0>>::_Tree<std::_Tmap_traits<DusmAppInfo,DUSM_NETWORK_USAGE,DusmAppInfoComparator,std::allocator<std::pair<DusmAppInfo const,DUSM_NETWORK_USAGE>>,0>>(
    v8,
    &v78);
  v57 = v11 | 5;
  ApplyAttributionMapping(v8);
  v46 = *(_QWORD *)*v8;
  v59 = v46;
  while ( *(_BYTE *)(v46 + 25) == (_BYTE)v10 )
  {
    v47 = v46 + 32;
    v48 = *(_QWORD *)(v46 + 72);
    v49 = *(_QWORD *)(v46 + 80);
    if ( **(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get(v45, v44) + 8) > 5u )
    {
      v56 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v47);
      v60 = v49 + v48;
      v65 = v9;
      v64 = v6;
      v62 = DusmMediaTypeToSz(v7[1].Data1);
      LODWORD(v53) = v58;
      v61 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(&v7[3]);
      v55 = (__int64)&v7[2];
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>>(
        v50,
        (int)&byte_180057A0B,
        v50,
        v51,
        &v55,
        (const WCHAR **)&v61,
        (__int64)&v53,
        (const WCHAR **)&v62,
        &v64,
        &v65,
        (__int64)&v60,
        (const WCHAR **)&v56);
    }
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<DusmAppInfo const,DUSM_NETWORK_USAGE>>>,std::_Iterator_base0>::operator++(&v59);
    v46 = v59;
    v10 = 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<_SRU_STATS_RECORD_SET *,void (*)(_SRU_STATS_RECORD_SET *),&void SruFreeRecordSet(_SRU_STATS_RECORD_SET *),wistd::integral_constant<unsigned __int64,0>,_SRU_STATS_RECORD_SET *,_SRU_STATS_RECORD_SET *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SRU_STATS_RECORD_SET *,void (*)(_SRU_STATS_RECORD_SET *),&void SruFreeRecordSet(_SRU_STATS_RECORD_SET *),wistd::integral_constant<unsigned __int64,0>,_SRU_STATS_RECORD_SET *,_SRU_STATS_RECORD_SET *,0,std::nullptr_t>>(&v76);
  std::_Tree_val<std::_Tree_simple_types<std::pair<DusmAppInfo const,DUSM_NETWORK_USAGE>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<DusmAppInfo const,DUSM_NETWORK_USAGE>,void *>>>(
    &v78,
    &v78);
  if ( (_QWORD)v72 )
  {
    std::_Destroy_range<std::allocator<std::unique_ptr<DusmFilter>>>(v72, *((__int64 *)&v72 + 1));
    std::_Deallocate<16>((void *)v72, (v73 - v72) & 0xFFFFFFFFFFFFFFF8uLL);
    v72 = 0;
    v73 = v10;
  }
  wil::details::unique_storage<wil::details::resource_policy<_SRU_STATS_RECORD_SET *,void (*)(_SRU_STATS_RECORD_SET *),&void SruFreeRecordSet(_SRU_STATS_RECORD_SET *),wistd::integral_constant<unsigned __int64,0>,_SRU_STATS_RECORD_SET *,_SRU_STATS_RECORD_SET *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SRU_STATS_RECORD_SET *,void (*)(_SRU_STATS_RECORD_SET *),&void SruFreeRecordSet(_SRU_STATS_RECORD_SET *),wistd::integral_constant<unsigned __int64,0>,_SRU_STATS_RECORD_SET *,_SRU_STATS_RECORD_SET *,0,std::nullptr_t>>(&v77);
  return v66;
}

```

## disassembly

```asm
0x180022d90  mov     [rsp-8+arg_10], rbx
0x180022d95  push    rbp
0x180022d96  push    rsi
0x180022d97  push    rdi
0x180022d98  push    r12
0x180022d9a  push    r13
0x180022d9c  push    r14
0x180022d9e  push    r15
0x180022da0  lea     rbp, [rsp-120h]
0x180022da8  sub     rsp, 220h
0x180022daf  mov     rax, cs:__security_cookie
0x180022db6  xor     rax, rsp
0x180022db9  mov     [rbp+150h+var_40], rax
0x180022dc0  mov     r12, r9
0x180022dc3  mov     [rbp+150h+var_1B0], r9
0x180022dc7  mov     [rbp+150h+var_1CC], r8d
0x180022dcb  mov     r15, rdx
0x180022dce  mov     [rbp+150h+var_1B8], rdx
0x180022dd2  mov     rsi, rcx
0x180022dd5  mov     [rbp+150h+var_190], rcx
0x180022dd9  mov     [rbp+150h+var_168], rcx
0x180022ddd  mov     r13, [rbp+150h+arg_20]
0x180022de4  mov     [rbp+150h+var_1C8], r13
0x180022de8  mov     rdi, [rbp+150h+arg_28]
0x180022def  xor     r14d, r14d
0x180022df2  mov     [rbp+150h+var_1D0], r14d
0x180022df6  mov     [rbp+150h+var_128], r14
0x180022dfa  xor     r9d, r9d
0x180022dfd  mov     r8, r13
0x180022e00  mov     rdx, r12
0x180022e03  lea     rcx, [rbp+150h+var_128]
0x180022e07  call    ?DusmSruQueryStats@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_SRU_STATS_RECORD_SET@@P6AXPEAU1@@Z$1?SruFreeRecordSet@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBU_SYSTEMTIME@@0W4_SRU_PROVIDER_CLASS@@@Z; DusmSruQueryStats(_SYSTEMTIME const &,_SYSTEMTIME const &,_SRU_PROVIDER_CLASS)
0x180022e0c  nop
0x180022e0d  xor     eax, eax
0x180022e0f  xorps   xmm1, xmm1
0x180022e12  movdqu  [rbp+150h+var_160], xmm1
0x180022e17  mov     [rbp+150h+var_150], rax
0x180022e1b  mov     rcx, r15; struct DusmConnection *
0x180022e1e  call    ?QueryResetTime@DusmStore@@SA?AU_FILETIME@@AEBVDusmConnection@@@Z; DusmStore::QueryResetTime(DusmConnection const &)
0x180022e23  mov     rbx, rax
0x180022e26  mov     [rsp+250h+var_1E0], rax
0x180022e2b  shr     rax, 20h
0x180022e2f  test    eax, eax
0x180022e31  jnz     short loc_180022E37
0x180022e33  test    ebx, ebx
0x180022e35  jz      short loc_180022E97
0x180022e37  lea     rdx, [rsp+250h+var_1E0]
0x180022e3c  lea     rcx, [rsp+250h+var_1E8]
0x180022e41  call    ??$make_unique@VDusmResetTimeFilter@@AEAU_FILETIME@@$0A@@std@@YA?AV?$unique_ptr@VDusmResetTimeFilter@@U?$default_delete@VDusmResetTimeFilter@@@std@@@0@AEAU_FILETIME@@@Z; std::make_unique<DusmResetTimeFilter,_FILETIME &,0>(_FILETIME &)
0x180022e46  nop
0x180022e47  mov     rcx, [rax]
0x180022e4a  mov     qword ptr [rax], 0
0x180022e51  mov     [rsp+250h+var_1F0], rcx
0x180022e56  mov     rdx, qword ptr [rbp+150h+var_160+8]
0x180022e5a  cmp     rdx, [rbp+150h+var_150]
0x180022e5e  jz      short loc_180022E73
0x180022e60  mov     [rsp+250h+var_1F0], 0
0x180022e69  mov     [rdx], rcx
0x180022e6c  add     qword ptr [rbp+150h+var_160+8], 8
0x180022e71  jmp     short loc_180022E82
0x180022e73  lea     r8, [rsp+250h+var_1F0]
0x180022e78  lea     rcx, [rbp+150h+var_160]
0x180022e7c  call    ??$_Emplace_reallocate@V?$unique_ptr@VDusmFilter@@U?$default_delete@VDusmFilter@@@std@@@std@@@?$vector@V?$unique_ptr@VDusmFilter@@U?$default_delete@VDusmFilter@@@std@@@std@@V?$allocator@V?$unique_ptr@VDusmFilter@@U?$default_delete@VDusmFilter@@@std@@@std@@@2@@std@@AEAAPEAV?$unique_ptr@VDusmFilter@@U?$default_delete@VDusmFilter@@@std@@@1@QEAV21@$$QEAV21@@Z; std::vector<std::unique_ptr<DusmFilter>>::_Emplace_reallocate<std::unique_ptr<DusmFilter>>(std::unique_ptr<DusmFilter> * const,std::unique_ptr<DusmFilter> &&)
0x180022e81  nop
0x180022e82  lea     rcx, [rsp+250h+var_1F0]
0x180022e87  call    ??1?$unique_ptr@VDusmFilter@@U?$default_delete@VDusmFilter@@@std@@@std@@QEAA@XZ; std::unique_ptr<DusmFilter>::~unique_ptr<DusmFilter>(void)
0x180022e8c  nop
0x180022e8d  lea     rcx, [rsp+250h+var_1E8]
0x180022e92  call    ??1?$unique_ptr@VDusmFilter@@U?$default_delete@VDusmFilter@@@std@@@std@@QEAA@XZ; std::unique_ptr<DusmFilter>::~unique_ptr<DusmFilter>(void)
0x180022e97  cmp     dword ptr [r15+10h], 3
0x180022e9c  jnz     short loc_180022F1C
0x180022e9e  xor     edx, edx; Val
0x180022ea0  lea     r8d, [rdx+40h]; Size
0x180022ea4  lea     rcx, [rbp+150h+var_100]; void *
0x180022ea8  call    memset_0
0x180022ead  mov     rdx, r15
0x180022eb0  lea     rcx, [rbp+150h+var_100]
0x180022eb4  call    ?QueryProfileIndexList@DusmStore@@SA?AV?$unordered_set@KU?$hash@K@std@@U?$equal_to@K@2@V?$allocator@K@2@@std@@AEBVDusmConnection@@@Z; DusmStore::QueryProfileIndexList(DusmConnection const &)
0x180022eb9  nop
0x180022eba  lea     rdx, [rbp+150h+var_100]
0x180022ebe  lea     rcx, [rsp+250h+var_1E8]
0x180022ec3  call    ??$make_unique@VDusmProfileIndexAppFilter@@AEAV?$unordered_set@KU?$hash@K@std@@U?$equal_to@K@2@V?$allocator@K@2@@std@@$0A@@std@@YA?AV?$unique_ptr@VDusmProfileIndexAppFilter@@U?$default_delete@VDusmProfileIndexAppFilter@@@std@@@0@AEAV?$unordered_set@KU?$hash@K@std@@U?$equal_to@K@2@V?$allocator@K@2@@0@@Z; std::make_unique<DusmProfileIndexAppFilter,std::unordered_set<ulong> &,0>(std::unordered_set<ulong> &)
0x180022ec8  nop
0x180022ec9  mov     rcx, [rax]
0x180022ecc  mov     qword ptr [rax], 0
0x180022ed3  mov     [rsp+250h+var_1F0], rcx
0x180022ed8  mov     rdx, qword ptr [rbp+150h+var_160+8]
0x180022edc  cmp     rdx, [rbp+150h+var_150]
0x180022ee0  jz      short loc_180022EF5
0x180022ee2  mov     [rsp+250h+var_1F0], 0
0x180022eeb  mov     [rdx], rcx
0x180022eee  add     qword ptr [rbp+150h+var_160+8], 8
0x180022ef3  jmp     short loc_180022F04
0x180022ef5  lea     r8, [rsp+250h+var_1F0]
0x180022efa  lea     rcx, [rbp+150h+var_160]
0x180022efe  call    ??$_Emplace_reallocate@V?$unique_ptr@VDusmFilter@@U?$default_delete@VDusmFilter@@@std@@@std@@@?$vector@V?$unique_ptr@VDusmFilter@@U?$default_delete@VDusmFilter@@@std@@@std@@V?$allocator@V?$unique_ptr@VDusmFilter@@U?$default_delete@VDusmFilter@@@std@@@std@@@2@@std@@AEAAPEAV?$unique_ptr@VDusmFilter@@U?$default_delete@VDusmFilter@@@std@@@1@QEAV21@$$QEAV21@@Z; std::vector<std::unique_ptr<DusmFilter>>::_Emplace_reallocate<std::unique_ptr<DusmFilter>>(std::unique_ptr<DusmFilter> * const,std::unique_ptr<DusmFilter> &&)
0x180022f03  nop
0x180022f04  lea     rcx, [rsp+250h+var_1F0]
0x180022f09  call    ??1?$unique_ptr@VDusmFilter@@U?$default_delete@VDusmFilter@@@std@@@std@@QEAA@XZ; std::unique_ptr<DusmFilter>::~unique_ptr<DusmFilter>(void)
0x180022f0e  nop
0x180022f0f  lea     rcx, [rsp+250h+var_1E8]
0x180022f14  call    ??1?$unique_ptr@VDusmFilter@@U?$default_delete@VDusmFilter@@@std@@@std@@QEAA@XZ; std::unique_ptr<DusmFilter>::~unique_ptr<DusmFilter>(void)
0x180022f19  nop
0x180022f1a  jmp     short loc_180022F95
0x180022f1c  cmp     [rbp+150h+var_1CC], 0
0x180022f20  jz      short loc_180022FA0
0x180022f22  cmp     dword ptr [r15+10h], 2
0x180022f27  jnz     short loc_180022FA0
0x180022f29  lea     rdx, [rbp+150h+var_100]
0x180022f2d  mov     rcx, r15
0x180022f30  call    ?GetProfileIndexList@DusmConnection@@QEBA?AV?$unordered_set@KU?$hash@K@std@@U?$equal_to@K@2@V?$allocator@K@2@@std@@XZ; DusmConnection::GetProfileIndexList(void)
0x180022f35  nop
0x180022f36  mov     rdx, rax
0x180022f39  lea     rcx, [rsp+250h+var_1E8]
0x180022f3e  call    ??$make_unique@VDusmProfileIndexAppFilter@@V?$unordered_set@KU?$hash@K@std@@U?$equal_to@K@2@V?$allocator@K@2@@std@@$0A@@std@@YA?AV?$unique_ptr@VDusmProfileIndexAppFilter@@U?$default_delete@VDusmProfileIndexAppFilter@@@std@@@0@$$QEAV?$unordered_set@KU?$hash@K@std@@U?$equal_to@K@2@V?$allocator@K@2@@0@@Z; std::make_unique<DusmProfileIndexAppFilter,std::unordered_set<ulong>,0>(std::unordered_set<ulong> &&)
0x180022f43  nop
0x180022f44  mov     rcx, [rax]
0x180022f47  mov     qword ptr [rax], 0
0x180022f4e  mov     [rsp+250h+var_1F0], rcx
0x180022f53  mov     rdx, qword ptr [rbp+150h+var_160+8]
0x180022f57  cmp     rdx, [rbp+150h+var_150]
0x180022f5b  jz      short loc_180022F70
0x180022f5d  mov     [rsp+250h+var_1F0], 0
0x180022f66  mov     [rdx], rcx
0x180022f69  add     qword ptr [rbp+150h+var_160+8], 8
0x180022f6e  jmp     short loc_180022F7F
0x180022f70  lea     r8, [rsp+250h+var_1F0]
0x180022f75  lea     rcx, [rbp+150h+var_160]
0x180022f79  call    ??$_Emplace_reallocate@V?$unique_ptr@VDusmFilter@@U?$default_delete@VDusmFilter@@@std@@@std@@@?$vector@V?$unique_ptr@VDusmFilter@@U?$default_delete@VDusmFilter@@@std@@@std@@V?$allocator@V?$unique_ptr@VDusmFilter@@U?$default_delete@VDusmFilter@@@std@@@std@@@2@@std@@AEAAPEAV?$unique_ptr@VDusmFilter@@U?$default_delete@VDusmFilter@@@std@@@1@QEAV21@$$QEAV21@@Z; std::vector<std::unique_ptr<DusmFilter>>::_Emplace_reallocate<std::unique_ptr<DusmFilter>>(std::unique_ptr<DusmFilter> * const,std::unique_ptr<DusmFilter> &&)
0x180022f7e  nop
0x180022f7f  lea     rcx, [rsp+250h+var_1F0]
0x180022f84  call    ??1?$unique_ptr@VDusmFilter@@U?$default_delete@VDusmFilter@@@std@@@std@@QEAA@XZ; std::unique_ptr<DusmFilter>::~unique_ptr<DusmFilter>(void)
0x180022f89  nop
0x180022f8a  lea     rcx, [rsp+250h+var_1E8]
0x180022f8f  call    ??1?$unique_ptr@VDusmFilter@@U?$default_delete@VDusmFilter@@@std@@@std@@QEAA@XZ; std::unique_ptr<DusmFilter>::~unique_ptr<DusmFilter>(void)
0x180022f94  nop
0x180022f95  lea     rcx, [rbp+150h+var_100]
0x180022f99  call    ??1?$_Hash@V?$_Uset_traits@KV?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@std@@V?$allocator@K@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Uset_traits<ulong,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<ulong>,0>>::~_Hash<std::_Uset_traits<ulong,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<ulong>,0>>(void)
0x180022f9e  jmp     short loc_180022FFF
0x180022fa0  lea     rdx, [r15+20h]
0x180022fa4  lea     rcx, [rsp+250h+var_1E8]
0x180022fa9  call    ??$make_unique@VDusmInterfaceFilter@@AEBU_GUID@@$0A@@std@@YA?AV?$unique_ptr@VDusmInterfaceFilter@@U?$default_delete@VDusmInterfaceFilter@@@std@@@0@AEBU_GUID@@@Z; std::make_unique<DusmInterfaceFilter,_GUID const &,0>(_GUID const &)
0x180022fae  nop
0x180022faf  mov     rcx, [rax]
0x180022fb2  mov     qword ptr [rax], 0
0x180022fb9  mov     [rsp+250h+var_1F0], rcx
0x180022fbe  mov     rdx, qword ptr [rbp+150h+var_160+8]
0x180022fc2  cmp     rdx, [rbp+150h+var_150]
0x180022fc6  jz      short loc_180022FDB
0x180022fc8  mov     [rsp+250h+var_1F0], 0
0x180022fd1  mov     [rdx], rcx
0x180022fd4  add     qword ptr [rbp+150h+var_160+8], 8
0x180022fd9  jmp     short loc_180022FEA
0x180022fdb  lea     r8, [rsp+250h+var_1F0]
0x180022fe0  lea     rcx, [rbp+150h+var_160]
0x180022fe4  call    ??$_Emplace_reallocate@V?$unique_ptr@VDusmFilter@@U?$default_delete@VDusmFilter@@@std@@@std@@@?$vector@V?$unique_ptr@VDusmFilter@@U?$default_delete@VDusmFilter@@@std@@@std@@V?$allocator@V?$unique_ptr@VDusmFilter@@U?$default_delete@VDusmFilter@@@std@@@std@@@2@@std@@AEAAPEAV?$unique_ptr@VDusmFilter@@U?$default_delete@VDusmFilter@@@std@@@1@QEAV21@$$QEAV21@@Z; std::vector<std::unique_ptr<DusmFilter>>::_Emplace_reallocate<std::unique_ptr<DusmFilter>>(std::unique_ptr<DusmFilter> * const,std::unique_ptr<DusmFilter> &&)
0x180022fe9  nop
0x180022fea  lea     rcx, [rsp+250h+var_1F0]
0x180022fef  call    ??1?$unique_ptr@VDusmFilter@@U?$default_delete@VDusmFilter@@@std@@@std@@QEAA@XZ; std::unique_ptr<DusmFilter>::~unique_ptr<DusmFilter>(void)
0x180022ff4  nop
0x180022ff5  lea     rcx, [rsp+250h+var_1E8]
0x180022ffa  call    ??1?$unique_ptr@VDusmFilter@@U?$default_delete@VDusmFilter@@@std@@@std@@QEAA@XZ; std::unique_ptr<DusmFilter>::~unique_ptr<DusmFilter>(void)
0x180022fff  test    rdi, rdi
0x180023002  jz      short loc_18002305C
0x180023004  mov     rdx, rdi
0x180023007  lea     rcx, [rsp+250h+var_1E8]
0x18002300c  call    ??$make_unique@VDusmRoamingFilter@@AEBH$0A@@std@@YA?AV?$unique_ptr@VDusmRoamingFilter@@U?$default_delete@VDusmRoamingFilter@@@std@@@0@AEBH@Z; std::make_unique<DusmRoamingFilter,int const &,0>(int const &)
0x180023011  nop
0x180023012  mov     rcx, [rax]
0x180023015  xor     edi, edi
0x180023017  mov     [rax], rdi
0x18002301a  mov     [rsp+250h+var_1F0], rcx
0x18002301f  mov     rdx, qword ptr [rbp+150h+var_160+8]
0x180023023  cmp     rdx, [rbp+150h+var_150]
0x180023027  jz      short loc_180023038
0x180023029  mov     [rsp+250h+var_1F0], rdi
0x18002302e  mov     [rdx], rcx
0x180023031  add     qword ptr [rbp+150h+var_160+8], 8
0x180023036  jmp     short loc_180023047
0x180023038  lea     r8, [rsp+250h+var_1F0]
0x18002303d  lea     rcx, [rbp+150h+var_160]
0x180023041  call    ??$_Emplace_reallocate@V?$unique_ptr@VDusmFilter@@U?$default_delete@VDusmFilter@@@std@@@std@@@?$vector@V?$unique_ptr@VDusmFilter@@U?$default_delete@VDusmFilter@@@std@@@std@@V?$allocator@V?$unique_ptr@VDusmFilter@@U?$default_delete@VDusmFilter@@@std@@@std@@@2@@std@@AEAAPEAV?$unique_ptr@VDusmFilter@@U?$default_delete@VDusmFilter@@@std@@@1@QEAV21@$$QEAV21@@Z; std::vector<std::unique_ptr<DusmFilter>>::_Emplace_reallocate<std::unique_ptr<DusmFilter>>(std::unique_ptr<DusmFilter> * const,std::unique_ptr<DusmFilter> &&)
0x180023046  nop
0x180023047  lea     rcx, [rsp+250h+var_1F0]
0x18002304c  call    ??1?$unique_ptr@VDusmFilter@@U?$default_delete@VDusmFilter@@@std@@@std@@QEAA@XZ; std::unique_ptr<DusmFilter>::~unique_ptr<DusmFilter>(void)
0x180023051  nop
0x180023052  lea     rcx, [rsp+250h+var_1E8]
0x180023057  call    ??1?$unique_ptr@VDusmFilter@@U?$default_delete@VDusmFilter@@@std@@@std@@QEAA@XZ; std::unique_ptr<DusmFilter>::~unique_ptr<DusmFilter>(void)
0x18002305c  xorps   xmm0, xmm0
0x18002305f  xor     eax, eax
0x180023061  movups  [rbp+150h+var_120], xmm0
0x180023065  mov     [rbp+150h+var_110], rax
0x180023069  lea     rcx, [rbp+150h+var_120]
0x18002306d  call    ??0?$map@UDusmAppInfo@@UDUSM_NETWORK_USAGE@@UDusmAppInfoComparator@@V?$allocator@U?$pair@$$CBUDusmAppInfo@@UDUSM_NETWORK_USAGE@@@std@@@std@@@std@@QEAA@XZ; std::map<DusmAppInfo,DUSM_NETWORK_USAGE,DusmAppInfoComparator,std::allocator<std::pair<DusmAppInfo const,DUSM_NETWORK_USAGE>>>::map<DusmAppInfo,DUSM_NETWORK_USAGE,DusmAppInfoComparator,std::allocator<std::pair<DusmAppInfo const,DUSM_NETWORK_USAGE>>>(void)
0x180023072  nop
0x180023073  mov     rax, [rbp+150h+var_128]
0x180023077  test    rax, rax
0x18002307a  jz      short loc_1800230D8
0x18002307c  cmp     dword ptr [rax], 0
0x18002307f  jbe     short loc_1800230D6
0x180023081  mov     edx, edi
0x180023083  shl     rdx, 6
0x180023087  add     rdx, [rax+8]
0x18002308b  xor     r8d, r8d
0x18002308e  lea     rcx, [rbp+150h+var_C0]
0x180023095  call    ??0DusmRecord@@QEAA@AEBU_SRU_STATS_RECORD@@W4_SRU_PROVIDER_CLASS@@@Z; DusmRecord::DusmRecord(_SRU_STATS_RECORD const &,_SRU_PROVIDER_CLASS)
0x18002309a  nop
0x18002309b  lea     rdx, [rbp+150h+var_160]
0x18002309f  lea     rcx, [rbp+150h+var_C0]
0x1800230a6  call    ?DusmIsRecordAllowed@@YAHAEBVDusmRecord@@AEBV?$vector@V?$unique_ptr@VDusmFilter@@U?$default_delete@VDusmFilter@@@std@@@std@@V?$allocator@V?$unique_ptr@VDusmFilter@@U?$default_delete@VDusmFilter@@@std@@@std@@@2@@std@@W4DusmFilterMatchType@@@Z; DusmIsRecordAllowed(DusmRecord const &,std::vector<std::unique_ptr<DusmFilter>> const &,DusmFilterMatchType)
0x1800230ab  test    eax, eax
0x1800230ad  jz      short loc_1800230C0
0x1800230af  lea     rdx, [rbp+150h+var_C0]
0x1800230b6  lea     rcx, [rbp+150h+var_120]
0x1800230ba  call    ?BucketUsageRecord@?$DusmRecordBucketer@V?$map@UDusmAppInfo@@UDUSM_NETWORK_USAGE@@UDusmAppInfoComparator@@V?$allocator@U?$pair@$$CBUDusmAppInfo@@UDUSM_NETWORK_USAGE@@@std@@@std@@@std@@VDusmAppInfoExtractor@@@@QEAAXAEBVDusmRecord@@@Z; DusmRecordBucketer<std::map<DusmAppInfo,DUSM_NETWORK_USAGE,DusmAppInfoComparator,std::allocator<std::pair<DusmAppInfo const,DUSM_NETWORK_USAGE>>>,DusmAppInfoExtractor>::BucketUsageRecord(DusmRecord const &)
0x1800230bf  nop
0x1800230c0  lea     rcx, [rbp+150h+var_C0]; this
0x1800230c7  call    ??1DusmRecord@@QEAA@XZ; DusmRecord::~DusmRecord(void)
0x1800230cc  inc     edi
0x1800230ce  mov     rax, [rbp+150h+var_128]
0x1800230d2  cmp     edi, [rax]
0x1800230d4  jb      short loc_180023081
0x1800230d6  xor     edi, edi
0x1800230d8  mov     [rbp+150h+var_130], rdi
0x1800230dc  mov     r9d, 2
0x1800230e2  mov     r8, r13
0x1800230e5  mov     rdx, r12
0x1800230e8  lea     rcx, [rbp+150h+var_130]
0x1800230ec  call    ?DusmSruQueryStats@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_SRU_STATS_RECORD_SET@@P6AXPEAU1@@Z$1?SruFreeRecordSet@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBU_SYSTEMTIME@@0W4_SRU_PROVIDER_CLASS@@@Z; DusmSruQueryStats(_SYSTEMTIME const &,_SYSTEMTIME const &,_SRU_PROVIDER_CLASS)
0x1800230f1  nop
0x1800230f2  mov     rax, [rbp+150h+var_130]
0x1800230f6  test    rax, rax
0x1800230f9  jz      loc_18002344B
0x1800230ff  cmp     [rax], edi
0x180023101  jbe     loc_18002344B
0x180023107  xorps   xmm1, xmm1
0x18002310a  movdqu  [rbp+150h+var_148], xmm1
0x18002310f  mov     [rbp+150h+var_138], rdi
0x180023113  cmp     dword ptr [rsp+250h+var_1E0+4], edi
0x180023117  jnz     short loc_18002311D
0x180023119  test    ebx, ebx
0x18002311b  jz      short loc_180023175
0x18002311d  lea     rdx, [rsp+250h+var_1E0]
0x180023122  lea     rcx, [rsp+250h+var_1E8]
0x180023127  call    ??$make_unique@VDusmResetTimeFilter@@AEAU_FILETIME@@$0A@@std@@YA?AV?$unique_ptr@VDusmResetTimeFilter@@U?$default_delete@VDusmResetTimeFilter@@@std@@@0@AEAU_FILETIME@@@Z; std::make_unique<DusmResetTimeFilter,_FILETIME &,0>(_FILETIME &)
0x18002312c  nop
0x18002312d  mov     rcx, [rax]
0x180023130  mov     [rax], rdi
0x180023133  mov     [rsp+250h+var_1F0], rcx
0x180023138  mov     rdx, qword ptr [rbp+150h+var_148+8]
0x18002313c  cmp     rdx, [rbp+150h+var_138]
0x180023140  jz      short loc_180023151
0x180023142  mov     [rsp+250h+var_1F0], rdi
0x180023147  mov     [rdx], rcx
0x18002314a  add     qword ptr [rbp+150h+var_148+8], 8
0x18002314f  jmp     short loc_180023160
0x180023151  lea     r8, [rsp+250h+var_1F0]
0x180023156  lea     rcx, [rbp+150h+var_148]
0x18002315a  call    ??$_Emplace_reallocate@V?$unique_ptr@VDusmFilter@@U?$default_delete@VDusmFilter@@@std@@@std@@@?$vector@V?$unique_ptr@VDusmFilter@@U?$default_delete@VDusmFilter@@@std@@@std@@V?$allocator@V?$unique_ptr@VDusmFilter@@U?$default_delete@VDusmFilter@@@std@@@std@@@2@@std@@AEAAPEAV?$unique_ptr@VDusmFilter@@U?$default_delete@VDusmFilter@@@std@@@1@QEAV21@$$QEAV21@@Z; std::vector<std::unique_ptr<DusmFilter>>::_Emplace_reallocate<std::unique_ptr<DusmFilter>>(std::unique_ptr<DusmFilter> * const,std::unique_ptr<DusmFilter> &&)
0x18002315f  nop
0x180023160  lea     rcx, [rsp+250h+var_1F0]
0x180023165  call    ??1?$unique_ptr@VDusmFilter@@U?$default_delete@VDusmFilter@@@std@@@std@@QEAA@XZ; std::unique_ptr<DusmFilter>::~unique_ptr<DusmFilter>(void)
0x18002316a  nop
0x18002316b  lea     rcx, [rsp+250h+var_1E8]
0x180023170  call    ??1?$unique_ptr@VDusmFilter@@U?$default_delete@VDusmFilter@@@std@@@std@@QEAA@XZ; std::unique_ptr<DusmFilter>::~unique_ptr<DusmFilter>(void)
0x180023175  mov     ebx, [r15+10h]
0x180023179  mov     ecx, 10h; Size
0x18002317e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180023183  mov     [rsp+250h+var_1D8], rax
0x180023188  lea     rcx, ??_7DusmMediaTypeFilter@@6B@; const DusmMediaTypeFilter::`vftable'
0x18002318f  mov     [rax], rcx
0x180023192  mov     [rax+8], ebx
0x180023195  mov     r14d, 2
0x18002319b  mov     dword ptr [rsp+250h+var_1F0], r14d
0x1800231a0  mov     [rbp+150h+var_1D0], r14d
0x1800231a4  mov     [rsp+250h+var_1E8], rdi
0x1800231a9  mov     [rsp+250h+var_1E0], rax
0x1800231ae  mov     rdx, qword ptr [rbp+150h+var_148+8]
0x1800231b2  cmp     rdx, [rbp+150h+var_138]
0x1800231b6  jz      short loc_1800231C7
0x1800231b8  mov     [rsp+250h+var_1E0], rdi
0x1800231bd  mov     [rdx], rax
0x1800231c0  add     qword ptr [rbp+150h+var_148+8], 8
0x1800231c5  jmp     short loc_1800231D6
0x1800231c7  lea     r8, [rsp+250h+var_1E0]
0x1800231cc  lea     rcx, [rbp+150h+var_148]
0x1800231d0  call    ??$_Emplace_reallocate@V?$unique_ptr@VDusmFilter@@U?$default_delete@VDusmFilter@@@std@@@std@@@?$vector@V?$unique_ptr@VDusmFilter@@U?$default_delete@VDusmFilter@@@std@@@std@@V?$allocator@V?$unique_ptr@VDusmFilter@@U?$default_delete@VDusmFilter@@@std@@@std@@@2@@std@@AEAAPEAV?$unique_ptr@VDusmFilter@@U?$default_delete@VDusmFilter@@@std@@@1@QEAV21@$$QEAV21@@Z; std::vector<std::unique_ptr<DusmFilter>>::_Emplace_reallocate<std::unique_ptr<DusmFilter>>(std::unique_ptr<DusmFilter> * const,std::unique_ptr<DusmFilter> &&)
0x1800231d5  nop
0x1800231d6  lea     rcx, [rsp+250h+var_1E0]
0x1800231db  call    ??1?$unique_ptr@VDusmFilter@@U?$default_delete@VDusmFilter@@@std@@@std@@QEAA@XZ; std::unique_ptr<DusmFilter>::~unique_ptr<DusmFilter>(void)
0x1800231e0  nop
0x1800231e1  lea     rcx, [rsp+250h+var_1E8]
0x1800231e6  call    ??1?$unique_ptr@VDusmFilter@@U?$default_delete@VDusmFilter@@@std@@@std@@QEAA@XZ; std::unique_ptr<DusmFilter>::~unique_ptr<DusmFilter>(void)
0x1800231eb  mov     r15, rdi
0x1800231ee  mov     [rbp+150h+var_188], rdi
0x1800231f2  mov     r12, rdi
0x1800231f5  mov     [rbp+150h+var_180], rdi
0x1800231f9  mov     r13, rdi
0x1800231fc  mov     [rbp+150h+var_178], rdi
0x180023200  mov     [rbp+150h+var_170], rdi
  ... truncated ...
```
