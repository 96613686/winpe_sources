# Microsoft::Basix::Dct::SmilesV3::MarkSwitchToNoLock(Microsoft::Basix::Dct::SmilesV3::SwitchInfo const &,std::shared_ptr<Microsoft::Basix::Dct::LinkDataV3>)

- ea: `0x18026c8c8`
- end: `0x18026d8d0`
- name: `?MarkSwitchToNoLock@SmilesV3@Dct@Basix@Microsoft@@AEAA?AV?$shared_ptr@VLinkDataV3@Dct@Basix@Microsoft@@@std@@AEBUSwitchInfo@1234@V56@@Z`
- size: `4104`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `25`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18025e404`
- `0x18025ff00`
- `0x18026da30`
- `0x18027de7c`

## callees

- `0x180008f80`
- `0x18000d9c0`
- `0x180015bb8`
- `0x180017338`
- `0x180018d1c`
- `0x18001902c`
- `0x18001ab4c`
- `0x180028100`
- `0x18002a8f4`
- `0x18003c308`
- `0x1800c3bc8`
- `0x1800d621c`
- `0x1801cda84`
- `0x18024e7c0`
- `0x18024e950`
- `0x18024f790`
- `0x180251ae4`
- `0x18026c8c8`
- `0x18027f2f8`
- `0x18027f518`
- `0x18027f5c0`
- `0x18032f050`
- `0x18032f0b0`
- `0x180330b40`
- `0x180375c40`

## string_xrefs

- `0x18026ca24`: `SmilesV3: minDelay(%f) on link(%d), linkType(%s)`
- `0x18026ce84`: `SmilesV3: minDelay(%f) on link(%d), linkType(%s)`
- `0x18026cc43`: `SmilesV3::MarkSwitchToNoLock: no UDP links, current inPrimary is Rendezvous and still active. ignore the switch`
- `0x18026cca7`: `SmilesV3::MarkSwitchToNoLock: the only ICE link is the current primary link and in norm al state, ignore the switch`
- `0x18026d2dc`: `SmilesV3: minDelay(%f) on link(%d)`

## pseudocode

```c
// Hidden C++ exception states: #wind=34
_QWORD *__fastcall Microsoft::Basix::Dct::SmilesV3::MarkSwitchToNoLock(
        __int64 a1,
        _QWORD *a2,
        __int64 a3,
        __int128 *a4)
{
  double v4; // xmm2_8
  __int128 *v5; // r14
  _QWORD *v6; // r12
  __int64 v7; // r15
  char v8; // xmm7_1
  double v9; // xmm8_8
  __int128 v10; // rdi
  _QWORD *v11; // r14
  __int64 v12; // r15
  __int64 v13; // rbx
  int v14; // r12d
  int v15; // r9d
  int v16; // r9d
  volatile signed __int32 *v17; // rbx
  __int64 v18; // rbx
  double v19; // xmm0_8
  __int64 v20; // rbx
  __int64 v21; // rax
  volatile signed __int32 *v22; // rbx
  __int64 v23; // rcx
  volatile signed __int32 *v24; // rbx
  volatile signed __int32 *v25; // rbx
  _QWORD *v26; // r14
  __int64 v27; // r15
  __int64 v28; // rbx
  int v29; // r12d
  int v30; // r9d
  int v31; // r9d
  volatile signed __int32 *v32; // rbx
  __int64 v33; // rbx
  double v34; // xmm0_8
  __int64 v35; // rbx
  __int64 v36; // rax
  volatile signed __int32 *v37; // rbx
  int v38; // r9d
  double v39; // xmm0_8
  char v40; // xmm6_1
  __int64 *v41; // rax
  __int64 v42; // rbx
  double v43; // xmm0_8
  int v44; // r14d
  int v45; // ebx
  volatile signed __int32 *v46; // rbx
  _BYTE *v47; // rbx
  char v48; // xmm6_1
  double v49; // xmm8_8
  _QWORD *v50; // r14
  __int64 v51; // rbx
  int v52; // r15d
  int v53; // r9d
  int v54; // r9d
  volatile signed __int32 *v55; // rbx
  __int64 v56; // rbx
  double v57; // xmm0_8
  __int64 v58; // rbx
  __int64 v59; // rax
  volatile signed __int32 *v60; // rbx
  int v61; // r9d
  double v62; // xmm0_8
  char v63; // xmm7_1
  __int64 *v64; // rax
  __int64 v65; // rbx
  double v66; // xmm0_8
  int v67; // r14d
  int v68; // ebx
  volatile signed __int32 *v69; // rbx
  __int64 v70; // rax
  int v71; // r9d
  int v72; // r14d
  __int64 v73; // rax
  int v74; // ebx
  volatile signed __int32 *v75; // rbx
  volatile signed __int32 *v76; // rbx
  volatile signed __int32 *v77; // rbx
  const char *v79; // [rsp+20h] [rbp-E0h]
  double v80; // [rsp+28h] [rbp-D8h]
  __int128 v81; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v82; // [rsp+50h] [rbp-B0h]
  __int128 *v83; // [rsp+60h] [rbp-A0h]
  __int128 v84; // [rsp+68h] [rbp-98h] BYREF
  __int16 v85; // [rsp+78h] [rbp-88h] BYREF
  _QWORD *v86; // [rsp+80h] [rbp-80h]
  __int64 v87; // [rsp+88h] [rbp-78h]
  __int128 pExceptionObject; // [rsp+90h] [rbp-70h]
  _BYTE *v89; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v90; // [rsp+B8h] [rbp-48h]
  __int128 *v91; // [rsp+C0h] [rbp-40h]
  _BYTE v92[32]; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v93; // [rsp+E8h] [rbp-18h] BYREF
  __int128 v94; // [rsp+F8h] [rbp-8h] BYREF

  v5 = a4;
  v83 = a4;
  v90 = a3;
  v6 = a2;
  v86 = a2;
  v7 = a1;
  v87 = a1;
  v91 = a4;
  v84 = 0;
  if ( !Microsoft::Basix::Dct::s_bugfixenabled_RendezvousLinkSwitch_61430490 )
  {
    if ( !(unsigned __int8)std::operator==<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceCheckpoint>>(
                             a4,
                             0) )
    {
      v70 = *((_QWORD *)v5 + 1);
      if ( v70 )
        _InterlockedIncrement((volatile signed __int32 *)(v70 + 8));
      v10 = *v5;
      v84 = *v5;
      v93 = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(&v93);
      if ( (_QWORD)v93 && *(_BYTE *)(v93 + 128) )
      {
        if ( (_QWORD)v10 )
          v72 = *(_DWORD *)(v10 + 152);
        else
          LOBYTE(v72) = 0;
        v73 = *(_QWORD *)(v7 + 1824);
        if ( *(_QWORD *)v73 )
          v74 = *(_DWORD *)(*(_QWORD *)v73 + 152LL);
        else
          v74 = 0;
        v81 = 0;
        v82 = 0;
        std::string::_Construct<1,char const *>(
          &v81,
          "SmilesV3::MarkSwitching for Peer to the prefered: old=%d, new=%d",
          64,
          v71);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,unsigned int,unsigned int>(
          (unsigned int)&v93,
          (unsigned int)"BASIX_DCT",
          (unsigned int)&v81,
          v74,
          v72);
        std::string::_Tidy_deallocate(&v81);
        v5 = v83;
      }
      v75 = (volatile signed __int32 *)*((_QWORD *)&v93 + 1);
      if ( *((_QWORD *)&v93 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v93 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v75)(v75);
          if ( _InterlockedExchangeAdd(v75 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v75 + 8LL))(v75);
        }
      }
LABEL_104:
      if ( (_QWORD)v10 )
      {
        v85 = 0;
        if ( (unsigned __int8)std::_Atomic_storage<unsigned short,2>::compare_exchange_strong(
                                v7 + 3088,
                                &v85,
                                *(unsigned __int16 *)(v10 + 152),
                                5) )
        {
          v47 = (_BYTE *)v90;
          if ( v7 + 3064 != v90 + 8 )
            std::vector<short>::_Assign_counted_range<short *>(
              v7 + 3064,
              *(_QWORD *)(v90 + 8),
              (__int64)(*(_QWORD *)(v90 + 16) - *(_QWORD *)(v90 + 8)) >> 1);
          *(_BYTE *)(v7 + 3056) = *v47;
          ++*(_BYTE *)(v7 + 3090);
          *(_QWORD *)(v7 + 3096) = *(_QWORD *)std::chrono::steady_clock::now(&v89) / 1000000LL - *(_QWORD *)(v7 + 3008);
        }
        else
        {
          v84 = 0u;
          v76 = (volatile signed __int32 *)*((_QWORD *)&v10 + 1);
          v10 = 0u;
          if ( v76 )
          {
            if ( _InterlockedExchangeAdd(v76 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v76)(v76);
              if ( _InterlockedExchangeAdd(v76 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v76 + 8LL))(v76);
            }
          }
          v93 = 0;
          Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(&v93);
          if ( (_QWORD)v93 && *(_BYTE *)(v93 + 128) )
          {
            v81 = 0;
            v82 = 0;
            std::string::_Construct<1,char const *>(
              &v81,
              "SmilesV3: outstanding markToSwitch still active, ignore this switch",
              67);
            Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,>(
              &v93,
              "BASIX_DCT",
              &v81);
            std::string::_Tidy_deallocate(&v81);
          }
          v77 = (volatile signed __int32 *)*((_QWORD *)&v93 + 1);
          if ( *((_QWORD *)&v93 + 1) )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v93 + 1) + 8LL), 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v77)(v77);
              if ( _InterlockedExchangeAdd(v77 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v77 + 8LL))(v77);
            }
          }
        }
      }
      *(_OWORD *)v6 = v10;
      v25 = (volatile signed __int32 *)*((_QWORD *)v5 + 1);
      if ( v25 )
      {
        if ( _InterlockedExchangeAdd(v25 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v25)(v25);
          if ( _InterlockedExchangeAdd(v25 + 3, 0xFFFFFFFF) == 1 )
            goto LABEL_187;
        }
      }
      return v6;
    }
    v48 = LOBYTE(DOUBLE_1000_0);
    v49 = DOUBLE_1000_0;
    v94 = 0;
    Microsoft::Basix::Containers::IterationSafeStore<std::shared_ptr<Microsoft::Basix::Dct::FailoverBridge::Transport>,std::equal_to<std::shared_ptr<Microsoft::Basix::Dct::FailoverBridge::Transport>>>::iterator::iterator(
      &v94,
      v7 + 1528);
    pExceptionObject = 0;
    v10 = v84;
    while ( (_QWORD)v94 )
    {
      v93 = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceDebug>(&v93);
      v50 = (_QWORD *)*((_QWORD *)&v94 + 1);
      if ( (_QWORD)v93 && *(_BYTE *)(v93 + 128) )
      {
        v51 = **((_QWORD **)&v94 + 1);
        v52 = *(_DWORD *)(**((_QWORD **)&v94 + 1) + 152LL);
        if ( (unsigned int)Microsoft::Basix::Algorithm::SlidingStats<double,5,1,1>::num(*(_QWORD *)(**((_QWORD **)&v94 + 1)
                                                                                                  + 192LL)) )
          Microsoft::Basix::Algorithm::SlidingStats<double,20,1,1>::nmin(*(_QWORD *)(v51 + 192));
        v81 = 0;
        v82 = 0;
        std::string::_Construct<1,char const *>(&v81, "SmilesV3: minDelay(%f) on link(%d)", v4, v53);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceDebug,double,unsigned int>(
          (unsigned int)&v93,
          (unsigned int)"BASIX_DCT",
          (unsigned int)&v81,
          v54,
          v52);
        std::string::_Tidy_deallocate(&v81);
        v7 = v87;
      }
      v55 = (volatile signed __int32 *)*((_QWORD *)&v93 + 1);
      if ( *((_QWORD *)&v93 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v93 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v55)(v55);
          if ( _InterlockedExchangeAdd(v55 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v55 + 8LL))(v55);
        }
      }
      v56 = *v50;
      if ( !*(_DWORD *)(*v50 + 280LL)
        && !(unsigned __int8)boost::multi_index::detail::operator==<boost::multi_index::detail::ordered_index_node<boost::multi_index::detail::null_augment_policy,boost::multi_index::detail::index_node_base<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>,std::allocator<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>>>>>(
                               v50,
                               *(_QWORD *)(v7 + 1824)) )
      {
        v57 = (unsigned int)Microsoft::Basix::Algorithm::SlidingStats<double,5,1,1>::num(*(_QWORD *)(v56 + 192))
            ? Microsoft::Basix::Algorithm::SlidingStats<double,20,1,1>::nmin(*(_QWORD *)(v56 + 192))
            : DOUBLE_1000_0;
        if ( v49 > v57 )
        {
          v58 = *v50;
          if ( (unsigned int)Microsoft::Basix::Algorithm::SlidingStats<double,5,1,1>::num(*(_QWORD *)(*v50 + 192LL)) )
            v49 = Microsoft::Basix::Algorithm::SlidingStats<double,20,1,1>::nmin(*(_QWORD *)(v58 + 192));
          else
            v49 = DOUBLE_1000_0;
          v59 = v50[1];
          if ( v59 )
            _InterlockedIncrement((volatile signed __int32 *)(v59 + 8));
          *(_QWORD *)&v10 = *v50;
          *(_QWORD *)&v84 = *v50;
          v60 = (volatile signed __int32 *)*((_QWORD *)&v10 + 1);
          *((_QWORD *)&v10 + 1) = v50[1];
          *((_QWORD *)&v84 + 1) = *((_QWORD *)&v10 + 1);
          if ( v60 )
          {
            if ( _InterlockedExchangeAdd(v60 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v60)(v60);
              if ( _InterlockedExchangeAdd(v60 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v60 + 8LL))(v60);
            }
          }
        }
      }
      Microsoft::Basix::Containers::IterationSafeStore<std::weak_ptr<Microsoft::Basix::Instrumentation::IActivityListener>,Microsoft::Basix::Algorithm::owner_equals<std::weak_ptr<Microsoft::Basix::Instrumentation::IActivityListener>>>::iterator::operator++(&v94);
    }
    v93 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(&v93);
    if ( (_QWORD)v93 && *(_BYTE *)(v93 + 128) )
    {
      if ( (_QWORD)v10
        && (unsigned int)Microsoft::Basix::Algorithm::SlidingStats<double,5,1,1>::num(*(_QWORD *)(v10 + 192)) )
      {
        v62 = Microsoft::Basix::Algorithm::SlidingStats<double,20,1,1>::nmin(*(_QWORD *)(v10 + 192));
        v63 = LOBYTE(v62);
      }
      else
      {
        v63 = LOBYTE(DOUBLE_1000_0);
      }
      v64 = *(__int64 **)(v7 + 1824);
      v65 = *v64;
      if ( *v64 )
      {
        if ( (unsigned int)Microsoft::Basix::Algorithm::SlidingStats<double,5,1,1>::num(*(_QWORD *)(v65 + 192)) )
        {
          v66 = Microsoft::Basix::Algorithm::SlidingStats<double,20,1,1>::nmin(*(_QWORD *)(v65 + 192));
          v48 = LOBYTE(v66);
        }
        v64 = *(__int64 **)(v7 + 1824);
      }
      if ( (_QWORD)v10 )
        v67 = *(_DWORD *)(v10 + 152);
      else
        LOBYTE(v67) = 0;
      if ( *v64 )
        v68 = *(_DWORD *)(*v64 + 152);
      else
        v68 = 0;
      v81 = 0;
      v82 = 0;
      std::string::_Construct<1,char const *>(
        &v81,
        "SmilesV3::MarkSwitching for the peer to the best one: old=%d, new=%d, oldDelay=%f, newDelay=%f",
        94,
        v61,
        *(double *)&v79,
        v80);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,unsigned int,unsigned int,double,double>(
        (unsigned int)&v93,
        (unsigned int)"BASIX_DCT",
        (unsigned int)&v81,
        v68,
        v67,
        v48,
        v63);
      std::string::_Tidy_deallocate(&v81);
    }
    v69 = (volatile signed __int32 *)*((_QWORD *)&v93 + 1);
    if ( *((_QWORD *)&v93 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v93 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v69)(v69);
        if ( _InterlockedExchangeAdd(v69 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v69 + 8LL))(v69);
      }
    }
LABEL_103:
    v5 = v83;
    goto LABEL_104;
  }
  v8 = LOBYTE(DOUBLE_1000_0);
  v9 = DOUBLE_1000_0;
  v93 = 0;
  Microsoft::Basix::Containers::IterationSafeStore<std::shared_ptr<Microsoft::Basix::Dct::FailoverBridge::Transport>,std::equal_to<std::shared_ptr<Microsoft::Basix::Dct::FailoverBridge::Transport>>>::iterator::iterator(
    &v93,
    a1 + 1528);
  pExceptionObject = 0;
  v10 = v84;
  while ( (_QWORD)v93 )
  {
    v94 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceDebug>(&v94);
    v11 = (_QWORD *)*((_QWORD *)&v93 + 1);
    if ( (_QWORD)v94 && *(_BYTE *)(v94 + 128) )
    {
      v89 = v92;
      v12 = Microsoft::Basix::ToString<enum Microsoft::Basix::Dct::ISmiles::LinkType>(
              v92,
              **((_QWORD **)&v93 + 1) + 80LL,
              0,
              6);
      v13 = *v11;
      v14 = *(_DWORD *)(*v11 + 152LL);
      if ( (unsigned int)Microsoft::Basix::Algorithm::SlidingStats<double,5,1,1>::num(*(_QWORD *)(*v11 + 192LL)) )
        Microsoft::Basix::Algorithm::SlidingStats<double,20,1,1>::nmin(*(_QWORD *)(v13 + 192));
      v81 = 0;
      v82 = 0;
      std::string::_Construct<1,char const *>(&v81, "SmilesV3: minDelay(%f) on link(%d), linkType(%s)", v4, v15, v79);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceDebug,double,unsigned int,std::string>(
        (unsigned int)&v94,
        (unsigned int)"BASIX_DCT",
        (unsigned int)&v81,
        v16,
        v14,
        v12);
      std::string::_Tidy_deallocate(&v81);
      v7 = v87;
    }
    v17 = (volatile signed __int32 *)*((_QWORD *)&v94 + 1);
    if ( *((_QWORD *)&v94 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v94 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v17)(v17);
        if ( _InterlockedExchangeAdd(v17 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 8LL))(v17);
      }
    }
    v18 = *v11;
    if ( *(_DWORD *)(*v11 + 80LL) != 9
      && !*(_DWORD *)(v18 + 280)
      && !(unsigned __int8)boost::multi_index::detail::operator==<boost::multi_index::detail::ordered_index_node<boost::multi_index::detail::null_augment_policy,boost::multi_index::detail::index_node_base<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>,std::allocator<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>>>>>(
                             v11,
                             *(_QWORD *)(v7 + 1824)) )
    {
      v19 = (unsigned int)Microsoft::Basix::Algorithm::SlidingStats<double,5,1,1>::num(*(_QWORD *)(v18 + 192))
          ? Microsoft::Basix::Algorithm::SlidingStats<double,20,1,1>::nmin(*(_QWORD *)(v18 + 192))
          : DOUBLE_1000_0;
      if ( v9 > v19 )
      {
        v20 = *v11;
        if ( (unsigned int)Microsoft::Basix::Algorithm::SlidingStats<double,5,1,1>::num(*(_QWORD *)(*v11 + 192LL)) )
          v9 = Microsoft::Basix::Algorithm::SlidingStats<double,20,1,1>::nmin(*(_QWORD *)(v20 + 192));
        else
          v9 = DOUBLE_1000_0;
        v21 = v11[1];
        if ( v21 )
          _InterlockedIncrement((volatile signed __int32 *)(v21 + 8));
        *(_QWORD *)&v10 = *v11;
        *(_QWORD *)&v84 = *v11;
        v22 = (volatile signed __int32 *)*((_QWORD *)&v10 + 1);
        *((_QWORD *)&v10 + 1) = v11[1];
        *((_QWORD *)&v84 + 1) = *((_QWORD *)&v10 + 1);
        if ( v22 && _InterlockedExchangeAdd(v22 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v22)(v22);
          if ( _InterlockedExchangeAdd(v22 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v22 + 8LL))(v22);
        }
      }
    }
    Microsoft::Basix::Containers::IterationSafeStore<std::weak_ptr<Microsoft::Basix::Instrumentation::IActivityListener>,Microsoft::Basix::Algorithm::owner_equals<std::weak_ptr<Microsoft::Basix::Instrumentation::IActivityListener>>>::iterator::operator++(&v93);
  }
  if ( !(unsigned __int8)std::operator==<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceCheckpoint>>(
                           &v84,
                           0) )
  {
LABEL_81:
    v93 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(&v93);
    if ( (_QWORD)v93 && *(_BYTE *)(v93 + 128) )
    {
      if ( (_QWORD)v10
        && (unsigned int)Microsoft::Basix::Algorithm::SlidingStats<double,5,1,1>::num(*(_QWORD *)(v10 + 192)) )
      {
        v39 = Microsoft::Basix::Algorithm::SlidingStats<double,20,1,1>::nmin(*(_QWORD *)(v10 + 192));
        v40 = LOBYTE(v39);
      }
      else
      {
        v40 = LOBYTE(DOUBLE_1000_0);
      }
      v41 = *(__int64 **)(v7 + 1824);
      v42 = *v41;
      if ( *v41 )
      {
        if ( (unsigned int)Microsoft::Basix::Algorithm::SlidingStats<double,5,1,1>::num(*(_QWORD *)(v42 + 192)) )
        {
          v43 = Microsoft::Basix::Algorithm::SlidingStats<double,20,1,1>::nmin(*(_QWORD *)(v42 + 192));
          v8 = LOBYTE(v43);
        }
        v41 = *(__int64 **)(v7 + 1824);
      }
      if ( (_QWORD)v10 )
        v44 = *(_DWORD *)(v10 + 152);
      else
        LOBYTE(v44) = 0;
      if ( *v41 )
        v45 = *(_DWORD *)(*v41 + 152);
      else
        v45 = 0;
      v81 = 0;
      v82 = 0;
      std::string::_Construct<1,char const *>(
        &v81,
        "SmilesV3::MarkSwitching for the peer to the best one: old=%d, new=%d, oldDelay=%f, newDelay=%f",
        94,
        v38,
        *(double *)&v79,
        v80);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,unsigned int,unsigned int,double,double>(
        (unsigned int)&v93,
        (unsigned int)"BASIX_DCT",
        (unsigned int)&v81,
        v45,
        v44,
        v8,
        v40);
      std::string::_Tidy_deallocate(&v81);
    }
    v46 = (volatile signed __int32 *)*((_QWORD *)&v93 + 1);
    if ( *((_QWORD *)&v93 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v93 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v46)(v46);
        if ( _InterlockedExchangeAdd(v46 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v46 + 8LL))(v46);
      }
    }
    v6 = v86;
    goto LABEL_103;
  }
  v23 = **(_QWORD **)(v7 + 1824);
  if ( !v23 || *(_DWORD *)(v23 + 280) )
  {
    v94 = 0;
    Microsoft::Basix::Containers::IterationSafeStore<std::shared_ptr<Microsoft::Basix::Dct::FailoverBridge::Transport>,std::equal_to<std::shared_ptr<Microsoft::Basix::Dct::FailoverBridge::Transport>>>::iterator::iterator(
      &v94,
      v7 + 1528);
    pExceptionObject = 0;
    while ( (_QWORD)v94 )
    {
      v93 = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceDebug>(&v93);
      v26 = (_QWORD *)*((_QWORD *)&v94 + 1);
      if ( (_QWORD)v93 && *(_BYTE *)(v93 + 128) )
      {
        v89 = v92;
        v27 = Microsoft::Basix::ToString<enum Microsoft::Basix::Dct::ISmiles::LinkType>(
                v92,
                **((_QWORD **)&v94 + 1) + 80LL,
                0,
                6);
        v28 = *v26;
        v29 = *(_DWORD *)(*v26 + 152LL);
        if ( (unsigned int)Microsoft::Basix::Algorithm::SlidingStats<double,5,1,1>::num(*(_QWORD *)(*v26 + 192LL)) )
          Microsoft::Basix::Algorithm::SlidingStats<double,20,1,1>::nmin(*(_QWORD *)(v28 + 192));
        v81 = 0;
        v82 = 0;
        std::string::_Construct<1,char const *>(&v81, "SmilesV3: minDelay(%f) on link(%d), linkType(%s)", v4, v30, v79);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceDebug,double,unsigned int,std::string>(
          (unsigned int)&v93,
          (unsigned int)"BASIX_DCT",
          (unsigned int)&v81,
          v31,
          v29,
          v27);
        std::string::_Tidy_deallocate(&v81);
      }
      v32 = (volatile signed __int32 *)*((_QWORD *)&v93 + 1);
      if ( *((_QWORD *)&v93 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v93 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v32)(v32);
          if ( _InterlockedExchangeAdd(v32 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v32 + 8LL))(v32);
        }
      }
      v33 = *v26;
      if ( *(_DWORD *)(*v26 + 80LL) == 9 && !*(_DWORD *)(v33 + 280) )
      {
        v34 = (unsigned int)Microsoft::Basix::Algorithm::SlidingStats<double,5,1,1>::num(*(_QWORD *)(v33 + 192))
            ? Microsoft::Basix::Algorithm::SlidingStats<double,20,1,1>::nmin(*(_QWORD *)(v33 + 192))
            : DOUBLE_1000_0;
        if ( v9 > v34 )
        {
          v35 = *v26;
          if ( (unsigned int)Microsoft::Basix::Algorithm::SlidingStats<double,5,1,1>::num(*(_QWORD *)(*v26 + 192LL)) )
            v9 = Microsoft::Basix::Algorithm::SlidingStats<double,20,1,1>::nmin(*(_QWORD *)(v35 + 192));
          else
            v9 = DOUBLE_1000_0;
          v36 = v26[1];
          if ( v36 )
            _InterlockedIncrement((volatile signed __int32 *)(v36 + 8));
          *(_QWORD *)&v10 = *v26;
          *(_QWORD *)&v84 = *v26;
          v37 = (volatile signed __int32 *)*((_QWORD *)&v10 + 1);
          *((_QWORD *)&v10 + 1) = v26[1];
          *((_QWORD *)&v84 + 1) = *((_QWORD *)&v10 + 1);
          if ( v37 )
          {
            if ( _InterlockedExchangeAdd(v37 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v37)(v37);
              if ( _InterlockedExchangeAdd(v37 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v37 + 8LL))(v37);
            }
          }
        }
      }
      Microsoft::Basix::Containers::IterationSafeStore<std::weak_ptr<Microsoft::Basix::Instrumentation::IActivityListener>,Microsoft::Basix::Algorithm::owner_equals<std::weak_ptr<Microsoft::Basix::Instrumentation::IActivityListener>>>::iterator::operator++(&v94);
    }
    v7 = v87;
    goto LABEL_81;
  }
  v93 = 0;
  if ( *(_DWORD *)(v23 + 80) == 9 )
  {
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(&v93);
    if ( (_QWORD)v93 && *(_BYTE *)(v93 + 128) )
    {
      v81 = 0;
      v82 = 0;
      std::string::_Construct<1,char const *>(
        &v81,
        "SmilesV3::MarkSwitchToNoLock: no UDP links, current inPrimary is Rendezvous and still active. ignore the switch",
        111);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,>(
        &v93,
        "BASIX_DCT",
        &v81);
      std::string::_Tidy_deallocate(&v81);
    }
  }
  else
  {
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(&v93);
    if ( (_QWORD)v93 && *(_BYTE *)(v93 + 128) )
    {
      v81 = 0;
      v82 = 0;
      std::string::_Construct<1,char const *>(
        &v81,
        "SmilesV3::MarkSwitchToNoLock: the only ICE link is the current primary link and in norm al state, ignore the switch",
        115);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,>(
        &v93,
        "BASIX_DCT",
        &v81);
      std::string::_Tidy_deallocate(&v81);
    }
  }
  v24 = (volatile signed __int32 *)*((_QWORD *)&v93 + 1);
  if ( *((_QWORD *)&v93 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v93 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v24)(v24);
      if ( _InterlockedExchangeAdd(v24 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v24 + 8LL))(v24);
    }
  }
  v6 = v86;
  *v86 = 0;
  v6[1] = 0;
  if ( *((_QWORD *)&v10 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v10 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (***((void (__fastcall ****)(_QWORD))&v10 + 1))(*((_QWORD *)&v10 + 1));
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v10 + 1) + 12LL), 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v10 + 1) + 8LL))(*((_QWORD *)&v10 + 1));
    }
  }
  v25 = (volatile signed __int32 *)*((_QWORD *)v83 + 1);
  if ( v25 )
  {
    if ( _InterlockedExchangeAdd(v25 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v25)(v25);
      if ( _InterlockedExchangeAdd(v25 + 3, 0xFFFFFFFF) == 1 )
LABEL_187:
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v25 + 8LL))(v25);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x18026c8c8  push    rbp
0x18026c8ca  push    rbx
0x18026c8cb  push    rsi
0x18026c8cc  push    rdi
0x18026c8cd  push    r12
0x18026c8cf  push    r13
0x18026c8d1  push    r14
0x18026c8d3  push    r15
0x18026c8d5  lea     rbp, [rsp-48h]
0x18026c8da  mov     eax, 148h
0x18026c8df  call    _alloca_probe
0x18026c8e4  sub     rsp, rax
0x18026c8e7  movaps  [rsp+180h+var_50], xmm6
0x18026c8ef  movaps  [rsp+180h+var_60], xmm7
0x18026c8f7  movaps  [rsp+180h+var_70], xmm8
0x18026c900  mov     rax, cs:__security_cookie
0x18026c907  xor     rax, rsp
0x18026c90a  mov     [rbp+80h+var_78], rax
0x18026c90e  mov     r14, r9
0x18026c911  mov     [rsp+180h+var_120], r9
0x18026c916  mov     [rbp+80h+var_C8], r8
0x18026c91a  mov     r12, rdx
0x18026c91d  mov     [rbp+80h+var_100], rdx
0x18026c921  mov     r15, rcx
0x18026c924  mov     [rbp+80h+var_F8], rcx
0x18026c928  mov     [rbp+80h+var_C0], rdx
0x18026c92c  mov     [rbp+80h+var_C0], r9
0x18026c930  xor     r13d, r13d
0x18026c933  xorps   xmm0, xmm0
0x18026c936  xorps   xmm1, xmm1
0x18026c939  movdqu  [rsp+180h+var_118], xmm1
0x18026c93f  cmp     cs:?s_bugfixenabled_RendezvousLinkSwitch_61430490@Dct@Basix@Microsoft@@3_NA, r13b; bool Microsoft::Basix::Dct::s_bugfixenabled_RendezvousLinkSwitch_61430490
0x18026c946  jz      loc_18026D213
0x18026c94c  movsd   xmm7, cs:__real@408f400000000000
0x18026c954  movaps  xmm8, xmm7
0x18026c958  lea     rdx, [rcx+5F8h]
0x18026c95f  movups  [rbp+80h+var_98], xmm0
0x18026c963  lea     rcx, [rbp+80h+var_98]
0x18026c967  call    ??0iterator@?$IterationSafeStore@V?$shared_ptr@VTransport@FailoverBridge@Dct@Basix@Microsoft@@@std@@U?$equal_to@V?$shared_ptr@VTransport@FailoverBridge@Dct@Basix@Microsoft@@@std@@@2@@Containers@Basix@Microsoft@@QEAA@PEBV1234@@Z; Microsoft::Basix::Containers::IterationSafeStore<std::shared_ptr<Microsoft::Basix::Dct::FailoverBridge::Transport>,std::equal_to<std::shared_ptr<Microsoft::Basix::Dct::FailoverBridge::Transport>>>::iterator::iterator(Microsoft::Basix::Containers::IterationSafeStore<std::shared_ptr<Microsoft::Basix::Dct::FailoverBridge::Transport>,std::equal_to<std::shared_ptr<Microsoft::Basix::Dct::FailoverBridge::Transport>>> const *)
0x18026c96c  nop
0x18026c96d  xorps   xmm1, xmm1
0x18026c970  movdqu  [rbp+80h+pExceptionObject], xmm1
0x18026c975  mov     rsi, qword ptr [rsp+180h+var_118+8]
0x18026c97a  mov     rdi, qword ptr [rsp+180h+var_118]
0x18026c97f  mov     rcx, qword ptr [rbp+80h+var_98]
0x18026c983  test    rcx, rcx
0x18026c986  jz      loc_18026CBA0
0x18026c98c  xorps   xmm0, xmm0
0x18026c98f  movups  [rbp+80h+var_88], xmm0
0x18026c993  lea     rcx, [rbp+80h+var_88]
0x18026c997  call    ??$SelectEvent@VTraceDebug@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceDebug@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceDebug>(void)
0x18026c99c  nop
0x18026c99d  mov     r14, qword ptr [rbp+80h+var_98+8]
0x18026c9a1  mov     rax, qword ptr [rbp+80h+var_88]
0x18026c9a5  test    rax, rax
0x18026c9a8  jz      loc_18026CA67
0x18026c9ae  cmp     [rax+80h], r13b
0x18026c9b5  jz      loc_18026CA67
0x18026c9bb  lea     rax, [rbp+80h+var_B8]
0x18026c9bf  mov     [rbp+80h+var_D8], rax
0x18026c9c3  mov     rdx, [r14]
0x18026c9c6  add     rdx, 50h ; 'P'
0x18026c9ca  mov     r9d, 6
0x18026c9d0  xor     r8d, r8d
0x18026c9d3  lea     rcx, [rbp+80h+var_B8]
0x18026c9d7  call    ??$ToString@W4LinkType@ISmiles@Dct@Basix@Microsoft@@@Basix@Microsoft@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBW4LinkType@ISmiles@Dct@01@HH@Z; Microsoft::Basix::ToString<Microsoft::Basix::Dct::ISmiles::LinkType>(Microsoft::Basix::Dct::ISmiles::LinkType const &,int,int)
0x18026c9dc  mov     r15, rax
0x18026c9df  mov     rbx, [r14]
0x18026c9e2  mov     r12d, [rbx+98h]
0x18026c9e9  mov     rcx, [rbx+0C0h]
0x18026c9f0  call    ?num@?$SlidingStats@N$04$00$00@Algorithm@Basix@Microsoft@@QEAAHXZ; Microsoft::Basix::Algorithm::SlidingStats<double,5,1,1>::num(void)
0x18026c9f5  test    eax, eax
0x18026c9f7  jz      short loc_18026CA0A
0x18026c9f9  mov     rcx, [rbx+0C0h]
0x18026ca00  call    ?nmin@?$SlidingStats@N$0BE@$00$00@Algorithm@Basix@Microsoft@@QEAANXZ; Microsoft::Basix::Algorithm::SlidingStats<double,20,1,1>::nmin(void)
0x18026ca05  movaps  xmm6, xmm0
0x18026ca08  jmp     short loc_18026CA0D
0x18026ca0a  movaps  xmm6, xmm7
0x18026ca0d  xorps   xmm0, xmm0
0x18026ca10  movups  [rsp+180h+var_140], xmm0
0x18026ca15  xorps   xmm1, xmm1
0x18026ca18  movdqu  [rsp+180h+var_130], xmm1
0x18026ca1e  mov     r8d, 30h ; '0'
0x18026ca24  lea     rdx, aSmilesv3Mindel; "SmilesV3: minDelay(%f) on link(%d), lin"...
0x18026ca2b  lea     rcx, [rsp+180h+var_140]
0x18026ca30  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18026ca35  nop
0x18026ca36  mov     [rsp+180h+var_158], r15
0x18026ca3b  mov     dword ptr [rsp+180h+var_160], r12d
0x18026ca40  movaps  xmm3, xmm6
0x18026ca43  lea     r8, [rsp+180h+var_140]
0x18026ca48  lea     rdx, aBasixDct; "BASIX_DCT"
0x18026ca4f  lea     rcx, [rbp+80h+var_88]
0x18026ca53  call    ??$TraceMessage@VTraceDebug@Basix@Microsoft@@NIV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceDebug@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@NIV65@@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceDebug,double,uint,std::string>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceDebug>> const &,char const *,std::string const &,double,uint,std::string)
0x18026ca58  nop
0x18026ca59  lea     rcx, [rsp+180h+var_140]
0x18026ca5e  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18026ca63  mov     r15, [rbp+80h+var_F8]
0x18026ca67  mov     rbx, qword ptr [rbp+80h+var_88+8]
0x18026ca6b  or      r12d, 0FFFFFFFFh
0x18026ca6f  test    rbx, rbx
0x18026ca72  jz      short loc_18026CAAD
0x18026ca74  mov     eax, r12d
0x18026ca77  lock xadd [rbx+8], eax
0x18026ca7c  add     eax, r12d
0x18026ca7f  jnz     short loc_18026CAAD
0x18026ca81  mov     rax, [rbx]
0x18026ca84  mov     rcx, rbx
0x18026ca87  mov     rax, [rax]
0x18026ca8a  call    cs:__guard_dispatch_icall_fptr
0x18026ca90  mov     eax, r12d
0x18026ca93  lock xadd [rbx+0Ch], eax
0x18026ca98  add     eax, r12d
0x18026ca9b  jnz     short loc_18026CAAD
0x18026ca9d  mov     rax, [rbx]
0x18026caa0  mov     rcx, rbx
0x18026caa3  mov     rax, [rax+8]
0x18026caa7  call    cs:__guard_dispatch_icall_fptr
0x18026caad  mov     rbx, [r14]
0x18026cab0  cmp     dword ptr [rbx+50h], 9
0x18026cab4  jz      loc_18026CB92
0x18026caba  cmp     [rbx+118h], r13d
0x18026cac1  jnz     loc_18026CB92
0x18026cac7  mov     rdx, [r15+720h]
0x18026cace  mov     rcx, r14
0x18026cad1  call    ??$?8U?$ordered_index_node@Unull_augment_policy@detail@multi_index@boost@@U?$index_node_base@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@std@@@2@@234@@detail@multi_index@boost@@@detail@multi_index@boost@@YA_NAEBV?$bidir_node_iterator@U?$ordered_index_node@Unull_augment_policy@detail@multi_index@boost@@U?$index_node_base@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@std@@@2@@234@@detail@multi_index@boost@@@012@0@Z; boost::multi_index::detail::operator==<boost::multi_index::detail::ordered_index_node<boost::multi_index::detail::null_augment_policy,boost::multi_index::detail::index_node_base<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>,std::allocator<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>>>>>(boost::multi_index::detail::bidir_node_iterator<boost::multi_index::detail::ordered_index_node<boost::multi_index::detail::null_augment_policy,boost::multi_index::detail::index_node_base<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>,std::allocator<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>>>>> const &,boost::multi_index::detail::bidir_node_iterator<boost::multi_index::detail::ordered_index_node<boost::multi_index::detail::null_augment_policy,boost::multi_index::detail::index_node_base<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>,std::allocator<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>>>>> const &)
0x18026cad6  test    al, al
0x18026cad8  jnz     loc_18026CB92
0x18026cade  mov     rcx, [rbx+0C0h]
0x18026cae5  call    ?num@?$SlidingStats@N$04$00$00@Algorithm@Basix@Microsoft@@QEAAHXZ; Microsoft::Basix::Algorithm::SlidingStats<double,5,1,1>::num(void)
0x18026caea  test    eax, eax
0x18026caec  jz      short loc_18026CAFC
0x18026caee  mov     rcx, [rbx+0C0h]
0x18026caf5  call    ?nmin@?$SlidingStats@N$0BE@$00$00@Algorithm@Basix@Microsoft@@QEAANXZ; Microsoft::Basix::Algorithm::SlidingStats<double,20,1,1>::nmin(void)
0x18026cafa  jmp     short loc_18026CAFF
0x18026cafc  movaps  xmm0, xmm7
0x18026caff  comisd  xmm8, xmm0
0x18026cb04  jbe     loc_18026CB92
0x18026cb0a  mov     rbx, [r14]
0x18026cb0d  mov     rcx, [rbx+0C0h]
0x18026cb14  call    ?num@?$SlidingStats@N$04$00$00@Algorithm@Basix@Microsoft@@QEAAHXZ; Microsoft::Basix::Algorithm::SlidingStats<double,5,1,1>::num(void)
0x18026cb19  test    eax, eax
0x18026cb1b  jz      short loc_18026CB2F
0x18026cb1d  mov     rcx, [rbx+0C0h]
0x18026cb24  call    ?nmin@?$SlidingStats@N$0BE@$00$00@Algorithm@Basix@Microsoft@@QEAANXZ; Microsoft::Basix::Algorithm::SlidingStats<double,20,1,1>::nmin(void)
0x18026cb29  movaps  xmm8, xmm0
0x18026cb2d  jmp     short loc_18026CB33
0x18026cb2f  movaps  xmm8, xmm7
0x18026cb33  mov     rax, [r14+8]
0x18026cb37  test    rax, rax
0x18026cb3a  jz      short loc_18026CB40
0x18026cb3c  lock inc dword ptr [rax+8]
0x18026cb40  mov     rdi, [r14]
0x18026cb43  mov     qword ptr [rsp+180h+var_118], rdi
0x18026cb48  mov     rbx, rsi
0x18026cb4b  mov     rsi, [r14+8]
0x18026cb4f  mov     qword ptr [rsp+180h+var_118+8], rsi
0x18026cb54  test    rbx, rbx
0x18026cb57  jz      short loc_18026CB92
0x18026cb59  mov     eax, r12d
0x18026cb5c  lock xadd [rbx+8], eax
0x18026cb61  add     eax, r12d
0x18026cb64  jnz     short loc_18026CB92
0x18026cb66  mov     rax, [rbx]
0x18026cb69  mov     rcx, rbx
0x18026cb6c  mov     rax, [rax]
0x18026cb6f  call    cs:__guard_dispatch_icall_fptr
0x18026cb75  mov     eax, r12d
0x18026cb78  lock xadd [rbx+0Ch], eax
0x18026cb7d  add     eax, r12d
0x18026cb80  jnz     short loc_18026CB92
0x18026cb82  mov     rax, [rbx]
0x18026cb85  mov     rcx, rbx
0x18026cb88  mov     rax, [rax+8]
0x18026cb8c  call    cs:__guard_dispatch_icall_fptr
0x18026cb92  lea     rcx, [rbp+80h+var_98]
0x18026cb96  call    ??Eiterator@?$IterationSafeStore@V?$weak_ptr@VIActivityListener@Instrumentation@Basix@Microsoft@@@std@@U?$owner_equals@V?$weak_ptr@VIActivityListener@Instrumentation@Basix@Microsoft@@@std@@@Algorithm@Basix@Microsoft@@@Containers@Basix@Microsoft@@QEAAAEAV01234@XZ; Microsoft::Basix::Containers::IterationSafeStore<std::weak_ptr<Microsoft::Basix::Instrumentation::IActivityListener>,Microsoft::Basix::Algorithm::owner_equals<std::weak_ptr<Microsoft::Basix::Instrumentation::IActivityListener>>>::iterator::operator++(void)
0x18026cb9b  jmp     loc_18026C97F
0x18026cba0  or      r13d, 0FFFFFFFFh
0x18026cba4  xor     r12d, r12d
0x18026cba7  test    rcx, rcx
0x18026cbaa  jz      short loc_18026CBCB
0x18026cbac  add     rcx, 50h ; 'P'
0x18026cbb0  call    near ptr ??$launder@USecurityCookieHash@RdpNano@Microsoft@@@core@boost@@YAPEAUSecurityCookieHash@RdpNano@Microsoft@@PEAU234@@Z.Data1; boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>(Microsoft::RdpNano::SecurityCookieHash *)
0x18026cbb5  or      r14d, 0FFFFFFFFh
0x18026cbb9  mov     ecx, r14d
0x18026cbbc  lock xadd [rax], ecx
0x18026cbc0  cmp     ecx, r13d
0x18026cbc3  jz      loc_18026D88E
0x18026cbc9  jmp     short loc_18026CBCF
0x18026cbcb  or      r14d, 0FFFFFFFFh
0x18026cbcf  xor     edx, edx
0x18026cbd1  lea     rcx, [rsp+180h+var_118]
0x18026cbd6  call    ??$?8V?$Event@VTraceCheckpoint@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@YA_NAEBV?$shared_ptr@V?$Event@VTraceCheckpoint@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@0@$$T@Z; std::operator==<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceCheckpoint>>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceCheckpoint>> const &,std::nullptr_t)
0x18026cbdb  test    al, al
0x18026cbdd  jz      loc_18026D014
0x18026cbe3  mov     rax, [r15+720h]
0x18026cbea  mov     rcx, [rax]
0x18026cbed  test    rcx, rcx
0x18026cbf0  jz      loc_18026CDBF
0x18026cbf6  cmp     [rcx+118h], r12d
0x18026cbfd  jnz     loc_18026CDBF
0x18026cc03  xorps   xmm0, xmm0
0x18026cc06  movups  [rbp+80h+var_98], xmm0
0x18026cc0a  cmp     dword ptr [rcx+50h], 9
0x18026cc0e  lea     rcx, [rbp+80h+var_98]
0x18026cc12  jnz     short loc_18026CC78
0x18026cc14  call    ??$SelectEvent@VTraceNormal@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(void)
0x18026cc19  nop
0x18026cc1a  mov     rax, qword ptr [rbp+80h+var_98]
0x18026cc1e  test    rax, rax
0x18026cc21  jz      short loc_18026CC76
0x18026cc23  cmp     [rax+80h], r12b
0x18026cc2a  jz      short loc_18026CC76
0x18026cc2c  xorps   xmm0, xmm0
0x18026cc2f  movups  [rsp+180h+var_140], xmm0
0x18026cc34  xorps   xmm1, xmm1
0x18026cc37  movdqu  [rsp+180h+var_130], xmm1
0x18026cc3d  mov     r8d, 6Fh ; 'o'
0x18026cc43  lea     rdx, aSmilesv3Marksw_4; "SmilesV3::MarkSwitchToNoLock: no UDP li"...
0x18026cc4a  lea     rcx, [rsp+180h+var_140]
0x18026cc4f  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18026cc54  nop
0x18026cc55  lea     r8, [rsp+180h+var_140]
0x18026cc5a  lea     rdx, aBasixDct; "BASIX_DCT"
0x18026cc61  lea     rcx, [rbp+80h+var_98]
0x18026cc65  call    ??$TraceMessage@VTraceNormal@Basix@Microsoft@@$$V@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceNormal>> const &,char const *,std::string const &)
0x18026cc6a  nop
0x18026cc6b  lea     rcx, [rsp+180h+var_140]
0x18026cc70  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18026cc75  nop
0x18026cc76  jmp     short loc_18026CCDA
0x18026cc78  call    ??$SelectEvent@VTraceNormal@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(void)
0x18026cc7d  nop
0x18026cc7e  mov     rax, qword ptr [rbp+80h+var_98]
0x18026cc82  test    rax, rax
0x18026cc85  jz      short loc_18026CCDA
0x18026cc87  cmp     [rax+80h], r12b
0x18026cc8e  jz      short loc_18026CCDA
0x18026cc90  xorps   xmm0, xmm0
0x18026cc93  movups  [rsp+180h+var_140], xmm0
0x18026cc98  xorps   xmm1, xmm1
0x18026cc9b  movdqu  [rsp+180h+var_130], xmm1
0x18026cca1  mov     r8d, 73h ; 's'
0x18026cca7  lea     rdx, aSmilesv3Marksw_3; "SmilesV3::MarkSwitchToNoLock: the only "...
0x18026ccae  lea     rcx, [rsp+180h+var_140]
0x18026ccb3  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18026ccb8  nop
0x18026ccb9  lea     r8, [rsp+180h+var_140]
0x18026ccbe  lea     rdx, aBasixDct; "BASIX_DCT"
0x18026ccc5  lea     rcx, [rbp+80h+var_98]
0x18026ccc9  call    ??$TraceMessage@VTraceNormal@Basix@Microsoft@@$$V@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceNormal>> const &,char const *,std::string const &)
0x18026ccce  nop
0x18026cccf  lea     rcx, [rsp+180h+var_140]
0x18026ccd4  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18026ccd9  nop
0x18026ccda  mov     rbx, qword ptr [rbp+80h+var_98+8]
0x18026ccde  test    rbx, rbx
0x18026cce1  jz      short loc_18026CD1C
0x18026cce3  mov     eax, r14d
0x18026cce6  lock xadd [rbx+8], eax
0x18026cceb  add     eax, r14d
0x18026ccee  jnz     short loc_18026CD1C
0x18026ccf0  mov     rax, [rbx]
0x18026ccf3  mov     rcx, rbx
0x18026ccf6  mov     rax, [rax]
0x18026ccf9  call    cs:__guard_dispatch_icall_fptr
0x18026ccff  mov     eax, r14d
0x18026cd02  lock xadd [rbx+0Ch], eax
0x18026cd07  add     eax, r14d
0x18026cd0a  jnz     short loc_18026CD1C
0x18026cd0c  mov     rax, [rbx]
0x18026cd0f  mov     rcx, rbx
0x18026cd12  mov     rax, [rax+8]
0x18026cd16  call    cs:__guard_dispatch_icall_fptr
0x18026cd1c  mov     r12, [rbp+80h+var_100]
0x18026cd20  mov     qword ptr [r12], 0
0x18026cd28  mov     qword ptr [r12+8], 0
0x18026cd31  test    rsi, rsi
0x18026cd34  jz      short loc_18026CD70
0x18026cd36  mov     eax, r14d
0x18026cd39  lock xadd [rsi+8], eax
0x18026cd3e  add     eax, r14d
0x18026cd41  jnz     short loc_18026CD70
0x18026cd43  mov     rax, [rsi]
0x18026cd46  mov     rcx, rsi
0x18026cd49  mov     rax, [rax]
0x18026cd4c  call    cs:__guard_dispatch_icall_fptr
0x18026cd52  mov     eax, r14d
0x18026cd55  lock xadd [rsi+0Ch], eax
0x18026cd5a  add     eax, r14d
0x18026cd5d  jnz     short loc_18026CD70
0x18026cd5f  mov     rax, [rsi]
0x18026cd62  mov     rcx, rsi
0x18026cd65  mov     rax, [rax+8]
0x18026cd69  call    cs:__guard_dispatch_icall_fptr
0x18026cd6f  nop
0x18026cd70  mov     rbx, [rsp+180h+var_120]
0x18026cd75  mov     rbx, [rbx+8]
0x18026cd79  test    rbx, rbx
  ... truncated ...
```
