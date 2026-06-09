# HNS::Service::Core::NetworkEntityManager::CreateNonHnsNetworks(void)

- ea: `0x1800c33f0`
- end: `0x1800c3e66`
- name: `?CreateNonHnsNetworks@NetworkEntityManager@Core@Service@HNS@@QEAAXXZ`
- size: `2678`
- prototype: `void __fastcall(HNS::Service::Core::NetworkEntityManager *__hidden this)`
- caller_count: `2`
- callee_count: `29`
- tags: `file_ops, registry_config, service_task`

## callers

- `0x1800c8520`
- `0x1800ceef0`

## callees

- `0x18005f0c0`
- `0x18005f560`
- `0x18005f59c`
- `0x18005ffa0`
- `0x18005ffac`
- `0x18005ffc4`
- `0x1800666b4`
- `0x1800677fc`
- `0x1800684d0`
- `0x18006c530`
- `0x18006cc2c`
- `0x18006cd80`
- `0x1800759d8`
- `0x180075aac`
- `0x180076f1c`
- `0x1800773cc`
- `0x1800776c0`
- `0x18007fb74`
- `0x18008af3c`
- `0x18008c66c`
- `0x1800b8a30`
- `0x1800bcdcc`
- `0x1800c2984`
- `0x1800c33f0`
- `0x1800c3e90`
- `0x1800c6d50`
- `0x1800c7f50`
- `0x18028aad0`
- `0x1802b7010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800c372d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800c372d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800c34a7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800c34a7`
- `NetMgmtIF!NetMgmtMemFree` at `0x1800c3abf`
- `NetMgmtIF!NetMgmtMemFree` at `0x1800c3deb`
- `NetMgmtIF!NetMgmtMemFree` at `0x1800c3abf`
- `NetMgmtIF!NetMgmtMemFree` at `0x1800c3deb`
- `NetMgmtIF!NetMgmtEnumerateVirtualSwitch` at `0x1800c3754`
- `NetMgmtIF!NetMgmtEnumerateVirtualSwitch` at `0x1800c3754`
- `NetMgmtIF!NetMgmtEnumerateVirtualSwitchPorts` at `0x1800c3911`
- `NetMgmtIF!NetMgmtEnumerateVirtualSwitchPorts` at `0x1800c3911`
- `NetMgmtIF!NetMgmtFindInternalNicByName` at `0x1800c3965`
- `NetMgmtIF!NetMgmtFindInternalNicByName` at `0x1800c3965`
- `NetMgmtIF!NetMgmtUnbindExternalAdapter` at `0x1800c39ff`
- `NetMgmtIF!NetMgmtUnbindExternalAdapter` at `0x1800c39ff`
- `NetMgmtIF!NetMgmtDeleteVirtualSwitchPort` at `0x1800c3a48`
- `NetMgmtIF!NetMgmtDeleteVirtualSwitchPort` at `0x1800c3a48`
- `NetMgmtIF!NetMgmtDeleteVirtualSwitch` at `0x1800c3a90`
- `NetMgmtIF!NetMgmtDeleteVirtualSwitch` at `0x1800c3a90`
- `NetMgmtIF!NetMgmtDeleteInternalEthernetAdapter` at `0x1800c3976`
- `NetMgmtIF!NetMgmtDeleteInternalEthernetAdapter` at `0x1800c3976`

## string_xrefs

- `0x1800c3790`: `onecore\vm\dv\net\hns\service\core\networkentitymanager.cpp`
- `0x1800c3e54`: `onecore\vm\dv\net\hns\service\core\networkentitymanager.cpp`
- `0x1800c343f`: `HNS::Service::Core::NetworkEntityManager::CreateNonHnsNetworks`
- `0x1800c3dd6`: `HNS::Service::Core::NetworkEntityManager::CreateNonHnsNetworks`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
void __fastcall HNS::Service::Core::NetworkEntityManager::CreateNonHnsNetworks(RTL_SRWLOCK **this)
{
  _QWORD *v2; // rax
  RTL_SRWLOCK *v3; // rdi
  RTL_SRWLOCK *v4; // r14
  __int64 **Ptr; // rdi
  __int64 *v6; // rbx
  GUID v7; // xmm6
  __int64 v8; // rax
  volatile signed __int32 *v9; // r14
  __int64 v10; // rcx
  struct _GUID *v11; // rax
  char *v12; // r13
  volatile signed __int32 *v13; // r15
  void *v14; // r13
  _OWORD *v15; // r15
  int v16; // eax
  _OWORD *v17; // rdi
  unsigned int v18; // r15d
  _QWORD *v19; // rdi
  _QWORD *v20; // r14
  _QWORD *v21; // rbx
  __int64 **v22; // rcx
  _QWORD *v23; // rdx
  __int64 j; // rax
  __int64 *k; // rcx
  _QWORD *v26; // rdi
  volatile signed __int32 *v27; // rbx
  volatile signed __int32 *v28; // rbx
  unsigned int v29; // edi
  volatile signed __int32 *v30; // r14
  int v31; // eax
  int v32; // eax
  __int128 *v33; // rcx
  int v34; // eax
  int v35; // eax
  int v36; // eax
  __int64 v37; // rax
  volatile signed __int32 *v38; // rbx
  __int64 *v39; // rbx
  HNS::Service::Interface::IManager *v40; // r13
  __int64 v41; // rax
  __int64 v42; // r13
  volatile signed __int32 *v43; // rdi
  volatile signed __int32 *v44; // r14
  __int64 *v45; // r15
  __int64 *v46; // rax
  const struct _GUID *v47; // rdi
  struct _GUID *v48; // r14
  const char *v49; // r9
  __int64 **v50; // rcx
  __int64 *n; // rax
  __int64 *m; // rcx
  int v53; // [rsp+20h] [rbp-19F8h]
  int i; // [rsp+20h] [rbp-19F8h]
  __int64 *v55; // [rsp+20h] [rbp-19F8h]
  unsigned int v56; // [rsp+28h] [rbp-19F0h] BYREF
  unsigned int v57; // [rsp+2Ch] [rbp-19ECh] BYREF
  _OWORD *p_Data1; // [rsp+30h] [rbp-19E8h]
  volatile signed __int32 *v59; // [rsp+38h] [rbp-19E0h] BYREF
  void *v60; // [rsp+48h] [rbp-19D0h] BYREF
  __int64 v61; // [rsp+50h] [rbp-19C8h]
  HNS::Service::Interface::IManager *v62; // [rsp+58h] [rbp-19C0h]
  struct _GUID *v63[2]; // [rsp+60h] [rbp-19B8h] BYREF
  struct _GUID *v64; // [rsp+70h] [rbp-19A8h]
  __int64 *v65; // [rsp+78h] [rbp-19A0h]
  RTL_SRWLOCK *v66; // [rsp+80h] [rbp-1998h]
  volatile signed __int32 *v67; // [rsp+90h] [rbp-1988h] BYREF
  unsigned __int64 v68; // [rsp+98h] [rbp-1980h]
  _OWORD *v69; // [rsp+A0h] [rbp-1978h] BYREF
  GUID v70; // [rsp+A8h] [rbp-1970h] BYREF
  char v71[8]; // [rsp+B8h] [rbp-1960h] BYREF
  volatile signed __int32 *v72; // [rsp+C0h] [rbp-1958h]
  __int64 *v73; // [rsp+C8h] [rbp-1950h] BYREF
  __int64 *v74; // [rsp+D0h] [rbp-1948h]
  RTL_SRWLOCK *v75; // [rsp+D8h] [rbp-1940h]
  HNS::Service::Interface::IManager *v76; // [rsp+E0h] [rbp-1938h]
  __int128 v77; // [rsp+E8h] [rbp-1930h]
  __int64 *v78; // [rsp+F8h] [rbp-1920h]
  volatile signed __int32 *v79; // [rsp+100h] [rbp-1918h]
  PSRWLOCK SRWLock[3]; // [rsp+108h] [rbp-1910h] BYREF
  struct _GUID Buf2; // [rsp+120h] [rbp-18F8h] BYREF
  __int128 v82; // [rsp+130h] [rbp-18E8h] BYREF
  __int64 v83; // [rsp+140h] [rbp-18D8h]
  unsigned __int64 v84; // [rsp+148h] [rbp-18D0h]
  unsigned __int16 v85[128]; // [rsp+150h] [rbp-18C8h] BYREF
  _WORD v86[1688]; // [rsp+250h] [rbp-17C8h] BYREF
  unsigned int v87; // [rsp+F80h] [rbp-A98h]
  _BYTE v88[2624]; // [rsp+F90h] [rbp-A88h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A18h] [rbp+0h]

  v62 = (HNS::Service::Interface::IManager *)this;
  v76 = (HNS::Service::Interface::IManager *)this;
  HNSTraceProvider::TraceEnter("HNS::Service::Core::NetworkEntityManager::CreateNonHnsNetworks", 0x870u);
  memset_0(v88, 0, 0xA34u);
  v56 = 0;
  v61 = 0;
  v2 = operator new(0x40u);
  *v2 = v2;
  v2[1] = v2;
  v2[2] = v2;
  *((_WORD *)v2 + 12) = 257;
  v60 = v2;
  v3 = this[52];
  v4 = v3 + 18;
  SRWLock[0] = v3 + 18;
  AcquireSRWLockExclusive(v3 + 18);
  Ptr = (__int64 **)v3[20].Ptr;
  v6 = *Ptr;
  v73 = *Ptr;
  v74 = (__int64 *)Ptr;
  v75 = v4;
  v7 = GUID_NULL;
  while ( v6 != (__int64 *)Ptr )
  {
    v77 = *((_OWORD *)v6 + 1);
    v8 = v6[5];
    if ( v8 )
    {
      _InterlockedIncrement((volatile signed __int32 *)(v8 + 8));
      v7 = GUID_NULL;
    }
    v65 = (__int64 *)v6[4];
    v78 = v65;
    v9 = (volatile signed __int32 *)v6[5];
    v79 = v9;
    v10 = v65[154];
    if ( v10 )
    {
      HNSObject::Get<_GUID>(*(_QWORD *)(v10 + 1304), v71, v10 + 1248);
      v11 = (struct _GUID *)v71;
      v7 = GUID_NULL;
    }
    else
    {
      v70 = v7;
      v11 = &v70;
    }
    p_Data1 = &v11->Data1;
    Buf2 = *v11;
    v12 = (char *)v60;
    v13 = (volatile signed __int32 *)*((_QWORD *)v60 + 1);
    v53 = 0;
    v66 = 0;
    if ( *((_BYTE *)v13 + 25) )
    {
      v59 = v13;
    }
    else
    {
      do
      {
        v59 = v13;
        *(_QWORD *)&v82 = v13;
        if ( memcmp_0((const void *)(v13 + 8), &Buf2, 0x10u) >= 0 )
        {
          v53 = 1;
          v12 = (char *)v13;
          v13 = *(volatile signed __int32 **)v13;
        }
        else
        {
          v53 = 0;
          v13 = (volatile signed __int32 *)*((_QWORD *)v13 + 2);
        }
      }
      while ( !*((_BYTE *)v13 + 25) );
    }
    if ( v12[25] || memcmp_0(&Buf2, v12 + 32, 0x10u) < 0 )
    {
      if ( v61 == 0x3FFFFFFFFFFFFFFLL )
        std::_Throw_tree_length_error();
      v14 = v60;
      v63[0] = (struct _GUID *)&v60;
      v63[1] = 0;
      v15 = operator new(0x40u);
      v15[2] = *p_Data1;
      *((_QWORD *)v15 + 6) = 0;
      *((_QWORD *)v15 + 7) = 0;
      if ( v9 )
        _InterlockedIncrement(v9 + 2);
      *((_QWORD *)v15 + 6) = v65;
      *((_QWORD *)v15 + 7) = v9;
      *(_QWORD *)v15 = v14;
      *((_QWORD *)v15 + 1) = v14;
      *((_QWORD *)v15 + 2) = v14;
      *((_WORD *)v15 + 12) = 0;
      v63[1] = 0;
      std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<_GUID const,std::shared_ptr<HNS::Service::Resource::PortResource>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<_GUID const,std::shared_ptr<HNS::Service::Resource::PortResource>>,void *>>>(v63);
      v67 = v59;
      v68 = __PAIR64__((unsigned int)v66, v53);
      std::_Tree_val<std::_Tree_simple_types<unsigned short>>::_Insert_node(&v60, &v67, v15);
      v7 = GUID_NULL;
    }
    if ( v9 )
    {
      if ( !_InterlockedDecrement(v9 + 2) )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v9)(v9);
        if ( !_InterlockedDecrement(v9 + 3) )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
      }
      v7 = GUID_NULL;
    }
    v6 = (__int64 *)*v6;
  }
  if ( SRWLock[0] )
    ReleaseSRWLockExclusive(SRWLock[0]);
  v57 = 0;
  v68 = 0;
  v69 = 0;
  v16 = NetMgmtEnumerateVirtualSwitch(&v69, &v57);
  if ( v16 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x889,
      (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\core\\networkentitymanager.cpp",
      (const char *)(unsigned int)v16,
      v53);
  v17 = v69;
  p_Data1 = v69;
  v68 = (unsigned __int64)v69;
  v18 = 0;
  for ( i = 0; v18 < v57; v17 = p_Data1 )
  {
    memcpy_0(v85, (char *)v17 + 3640 * v18, 0xE38u);
    *(_OWORD *)SRWLock = 0;
    StringToGuid(v85, (struct _GUID *)SRWLock);
    v19 = v60;
    v20 = (_QWORD *)*((_QWORD *)v60 + 1);
    HIDWORD(v82) = 0;
    v21 = v60;
    while ( !*((_BYTE *)v20 + 25) )
    {
      if ( memcmp_0(v20 + 4, SRWLock, 0x10u) >= 0 )
      {
        v21 = v20;
        v20 = (_QWORD *)*v20;
      }
      else
      {
        v20 = (_QWORD *)v20[2];
      }
    }
    if ( *((_BYTE *)v21 + 25) || memcmp_0(SRWLock, v21 + 4, 0x10u) < 0 || v21 == v19 )
    {
      if ( v87 == 1 )
      {
        v28 = 0;
        v59 = 0;
        if ( (int)NetMgmtEnumerateVirtualSwitchPorts(v85, &v59, &v56) >= 0 )
        {
          v28 = v59;
          v72 = v59;
          v29 = 0;
          if ( v56 )
          {
            do
            {
              v30 = &v28[2387 * v29];
              v31 = (unsigned __int16)*((_DWORD *)v30 + 2381);
              if ( v31 == 2 )
              {
                if ( (int)NetMgmtFindInternalNicByName((char *)v30 + 1542, v88) >= 0 )
                {
                  v32 = NetMgmtDeleteInternalEthernetAdapter((char *)v30 + 1542);
                  if ( v32 < 0 )
                    wil::details::in1diag3::_Log_Hr(
                      retaddr,
                      (void *)0x8B7,
                      (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\core\\networkentitymanager.cpp",
                      (const char *)(unsigned int)v32,
                      i);
                }
              }
              else if ( v31 == 1 )
              {
                v82 = 0;
                v83 = 0;
                v84 = 7;
                LOWORD(v82) = 0;
                IPHelper::ParseInterfaceGuid((char *)v30 + 1542);
                v33 = &v82;
                if ( v84 > 7 )
                  v33 = (__int128 *)v82;
                v34 = NetMgmtUnbindExternalAdapter(v33);
                if ( v34 < 0 )
                  wil::details::in1diag3::_Log_Hr(
                    retaddr,
                    (void *)0x8BE,
                    (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\core\\networkentitymanager.cpp",
                    (const char *)(unsigned int)v34,
                    i);
                std::wstring::~wstring(&v82);
              }
              v35 = NetMgmtDeleteVirtualSwitchPort(v85, &v28[2387 * v29], 1, v87);
              if ( v35 < 0 )
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x8C3,
                  (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\core\\networkentitymanager.cpp",
                  (const char *)(unsigned int)v35,
                  i);
              ++v29;
            }
            while ( v29 < v56 );
            v18 = i;
          }
        }
        v36 = NetMgmtDeleteVirtualSwitch(v85, 3640, v87);
        if ( v36 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x8CC,
            (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\core\\networkentitymanager.cpp",
            (const char *)(unsigned int)v36,
            i);
        if ( v28 )
          NetMgmtMemFree(v28);
      }
      else
      {
        v37 = -1;
        do
          ++v37;
        while ( v86[v37] );
        *(_QWORD *)&Buf2.Data1 = v86;
        *(_QWORD *)Buf2.Data4 = v37;
        HNS::Service::Core::NetworkEntityManager::CreateNonHnsNetwork(v62);
        v38 = *(volatile signed __int32 **)v70.Data4;
        if ( *(_QWORD *)v70.Data4 )
        {
          if ( !_InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)v70.Data4 + 8LL)) )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v38)(v38);
            if ( !_InterlockedDecrement(v38 + 3) )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v38 + 8LL))(v38);
          }
        }
      }
    }
    else
    {
      v22 = (__int64 **)v21[2];
      v23 = v21;
      if ( *((_BYTE *)v22 + 25) )
      {
        for ( j = v21[1]; !*(_BYTE *)(j + 25) && v21 == *(_QWORD **)(j + 16); j = *(_QWORD *)(j + 8) )
          v21 = (_QWORD *)j;
      }
      else
      {
        for ( k = *v22; !*((_BYTE *)k + 25); k = (__int64 *)*k )
          ;
      }
      v26 = (_QWORD *)std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,HNSObjectProperty>>>::_Extract(
                        &v60,
                        v23);
      v27 = (volatile signed __int32 *)v26[7];
      if ( v27 )
      {
        if ( _InterlockedExchangeAdd(v27 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v27)(v27);
          if ( _InterlockedExchangeAdd(v27 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v27 + 8LL))(v27);
        }
      }
      operator delete(v26, (const struct std::nothrow_t *)0x40);
    }
    i = ++v18;
  }
  if ( v61 )
  {
    v39 = *(__int64 **)v60;
    v40 = v62;
LABEL_82:
    v55 = v39;
    while ( !*((_BYTE *)v39 + 25) )
    {
      try
      {
        *(_OWORD *)v63 = 0;
        v64 = 0;
        HNS::Service::Core::EntityManager<std::shared_ptr<HNS::Service::Network::BaseNetwork>>::Enumerate(v40, &v73);
        v45 = v73;
        v46 = v74;
        v65 = v74;
        while ( v45 != v46 )
        {
          v41 = v45[1];
          if ( v41 )
            _InterlockedIncrement((volatile signed __int32 *)(v41 + 8));
          v42 = *v45;
          *(_QWORD *)&v70.Data1 = v42;
          v43 = (volatile signed __int32 *)v45[1];
          *(_QWORD *)v70.Data4 = v43;
          v66 = *(RTL_SRWLOCK **)HNS::Service::Network::BaseNetwork::GetLayer(v42, v71);
          SRWLock[0] = (PSRWLOCK)v39[6];
          v44 = v72;
          if ( v72 )
          {
            if ( _InterlockedExchangeAdd(v72 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v44)(v44);
              if ( _InterlockedExchangeAdd(v44 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v44 + 8LL))(v44);
            }
          }
          if ( v66 == SRWLock[0] )
          {
            HNSObject::Get<_GUID>(*(_QWORD *)(v42 + 808), &Buf2, v42 + 752);
            if ( v63[1] == v64 )
              std::vector<_GUID>::_Emplace_reallocate<_GUID &>(v63, v63[1], &Buf2);
            else
              *v63[1]++ = Buf2;
          }
          if ( v43 )
          {
            if ( _InterlockedExchangeAdd(v43 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v43)(v43);
              if ( _InterlockedExchangeAdd(v43 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v43 + 8LL))(v43);
            }
          }
          v45 += 2;
          v46 = v65;
        }
        std::vector<std::shared_ptr<HNS::Service::Policy::DependentRuleInfo>>::~vector<std::shared_ptr<HNS::Service::Policy::DependentRuleInfo>>(&v73);
        v47 = v63[0];
        v48 = v63[1];
        v40 = v62;
        while ( v47 != v48 )
          HNS::Service::Core::NetworkEntityManager::Destroy(v40, v47++);
        std::vector<_GUID>::~vector<_GUID>(v63);
        v17 = p_Data1;
      }
      catch ( ... )
      {
        wil::details::in1diag3::Log_CaughtException(
          retaddr,
          (void *)0x8EB,
          (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\core\\networkentitymanager.cpp",
          v49);
        v17 = (_OWORD *)v68;
        p_Data1 = (_OWORD *)v68;
        v39 = v55;
        v40 = v76;
        v62 = v76;
      }
      v50 = (__int64 **)v39[2];
      if ( !*((_BYTE *)v50 + 25) )
      {
        v39 = (__int64 *)v39[2];
        for ( m = *v50; !*((_BYTE *)m + 25); m = (__int64 *)*m )
          v39 = m;
        goto LABEL_82;
      }
      for ( n = (__int64 *)v39[1]; !*((_BYTE *)n + 25) && v39 == (__int64 *)n[2]; n = (__int64 *)n[1] )
        v39 = n;
      v39 = n;
      v55 = n;
    }
  }
  HNSTraceProvider::TraceSuccess("HNS::Service::Core::NetworkEntityManager::CreateNonHnsNetworks", 0x8EFu);
  if ( v17 )
    NetMgmtMemFree(v17);
  std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<HNS::Service::Events::IEventProducer>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<_GUID const,std::shared_ptr<HNS::Service::Events::IEventProducer>>,void *>>>(
    (__int64)&v60,
    (__int64)&v60,
    *((_QWORD *)v60 + 1));
  operator delete(v60, (const struct std::nothrow_t *)0x40);
}

```

## disassembly

```asm
0x1800c33f0  mov     [rsp+arg_8], rbx
0x1800c33f5  mov     [rsp+arg_10], rsi
0x1800c33fa  push    rdi
0x1800c33fb  push    r12
0x1800c33fd  push    r13
0x1800c33ff  push    r14
0x1800c3401  push    r15
0x1800c3403  mov     eax, 19F0h
0x1800c3408  call    _alloca_probe
0x1800c340d  sub     rsp, rax
0x1800c3410  movaps  [rsp+1A18h+var_38], xmm6
0x1800c3418  mov     rax, cs:__security_cookie
0x1800c341f  xor     rax, rsp
0x1800c3422  mov     [rsp+1A18h+var_48], rax
0x1800c342a  mov     r13, rcx
0x1800c342d  mov     [rsp+1A18h+var_19C0], rcx
0x1800c3432  mov     [rsp+1A18h+var_1938], rcx
0x1800c343a  mov     edx, 870h; unsigned int
0x1800c343f  lea     rcx, aHnsServiceCore_38; "HNS::Service::Core::NetworkEntityManage"...
0x1800c3446  call    ?TraceEnter@HNSTraceProvider@@SAXPEBDI@Z; HNSTraceProvider::TraceEnter(char const *,uint)
0x1800c344b  xor     edx, edx; Val
0x1800c344d  mov     r8d, 0A34h; Size
0x1800c3453  lea     rcx, [rsp+1A18h+var_A88]; void *
0x1800c345b  call    memset_0
0x1800c3460  xor     esi, esi
0x1800c3462  mov     [rsp+1A18h+var_19F0], esi
0x1800c3466  mov     [rsp+1A18h+var_19D0], rsi
0x1800c346b  mov     [rsp+1A18h+var_19C8], rsi
0x1800c3470  lea     ecx, [rsi+40h]; Size
0x1800c3473  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800c3478  mov     [rax], rax
0x1800c347b  mov     [rax+8], rax
0x1800c347f  mov     [rax+10h], rax
0x1800c3483  mov     word ptr [rax+18h], 101h
0x1800c3489  mov     [rsp+1A18h+var_19D0], rax
0x1800c348e  mov     rdi, [r13+1A0h]
0x1800c3495  lea     r14, [rdi+90h]
0x1800c349c  mov     [rsp+1A18h+SRWLock], r14
0x1800c34a4  mov     rcx, r14; SRWLock
0x1800c34a7  call    cs:__imp_AcquireSRWLockExclusive
0x1800c34ad  mov     rdi, [rdi+0A0h]
0x1800c34b4  mov     rbx, [rdi]
0x1800c34b7  mov     [rsp+1A18h+var_1950], rbx
0x1800c34bf  mov     [rsp+1A18h+var_1948], rdi
0x1800c34c7  mov     [rsp+1A18h+var_1940], r14
0x1800c34cf  or      r12, 0FFFFFFFFFFFFFFFFh
0x1800c34d3  movups  xmm6, xmmword ptr cs:GUID_NULL.Data1
0x1800c34da  cmp     rbx, rdi
0x1800c34dd  jz      loc_1800C371D
0x1800c34e3  movups  xmm0, xmmword ptr [rbx+10h]
0x1800c34e7  movdqu  [rsp+1A18h+var_1930], xmm0
0x1800c34f0  mov     rax, [rbx+28h]
0x1800c34f4  test    rax, rax
0x1800c34f7  jz      short loc_1800C3504
0x1800c34f9  lock inc dword ptr [rax+8]
0x1800c34fd  movups  xmm6, xmmword ptr cs:GUID_NULL.Data1
0x1800c3504  mov     rax, [rbx+20h]
0x1800c3508  mov     [rsp+1A18h+var_19A0], rax
0x1800c350d  mov     [rsp+1A18h+var_1920], rax
0x1800c3515  mov     r14, [rbx+28h]
0x1800c3519  mov     [rsp+1A18h+var_1918], r14
0x1800c3521  mov     rcx, [rax+4D0h]
0x1800c3528  test    rcx, rcx
0x1800c352b  jz      short loc_1800C355A
0x1800c352d  lea     r8, [rcx+4E0h]
0x1800c3534  lea     rdx, [rsp+1A18h+var_1960]
0x1800c353c  mov     rcx, [rcx+518h]
0x1800c3543  call    ??$Get@U_GUID@@@HNSObject@@QEAA?AU_GUID@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; HNSObject::Get<_GUID>(std::wstring const &)
0x1800c3548  nop
0x1800c3549  lea     rax, [rsp+1A18h+var_1960]
0x1800c3551  movups  xmm6, xmmword ptr cs:GUID_NULL.Data1
0x1800c3558  jmp     short loc_1800C356B
0x1800c355a  movdqu  [rsp+1A18h+var_1970], xmm6
0x1800c3563  lea     rax, [rsp+1A18h+var_1970]
0x1800c356b  mov     [rsp+1A18h+var_19E8], rax
0x1800c3570  movups  xmm0, xmmword ptr [rax]
0x1800c3573  movdqu  [rsp+1A18h+Buf2], xmm0
0x1800c357c  mov     r13, [rsp+1A18h+var_19D0]
0x1800c3581  mov     r15, [r13+8]
0x1800c3585  mov     dword ptr [rsp+1A18h+var_19F8], esi
0x1800c3589  xor     eax, eax
0x1800c358b  mov     [rsp+1A18h+var_1998], rax
0x1800c3593  cmp     [r15+19h], sil
0x1800c3597  jnz     short loc_1800C35E1
0x1800c3599  mov     [rsp+1A18h+var_19E0], r15
0x1800c359e  mov     qword ptr [rsp+1A18h+var_18E8], r15
0x1800c35a6  lea     rcx, [r15+20h]; Buf1
0x1800c35aa  mov     r8d, 10h; Size
0x1800c35b0  lea     rdx, [rsp+1A18h+Buf2]; Buf2
0x1800c35b8  call    memcmp_0
0x1800c35bd  test    eax, eax
0x1800c35bf  jns     short loc_1800C35CB
0x1800c35c1  mov     dword ptr [rsp+1A18h+var_19F8], esi
0x1800c35c5  mov     r15, [r15+10h]
0x1800c35c9  jmp     short loc_1800C35D9
0x1800c35cb  mov     dword ptr [rsp+1A18h+var_19F8], 1
0x1800c35d3  mov     r13, r15
0x1800c35d6  mov     r15, [r15]
0x1800c35d9  cmp     [r15+19h], sil
0x1800c35dd  jz      short loc_1800C3599
0x1800c35df  jmp     short loc_1800C35E6
0x1800c35e1  mov     [rsp+1A18h+var_19E0], r15
0x1800c35e6  cmp     [r13+19h], sil
0x1800c35ea  jnz     short loc_1800C360B
0x1800c35ec  lea     rdx, [r13+20h]; Buf2
0x1800c35f0  mov     r8d, 10h; Size
0x1800c35f6  lea     rcx, [rsp+1A18h+Buf2]; Buf1
0x1800c35fe  call    memcmp_0
0x1800c3603  test    eax, eax
0x1800c3605  jns     loc_1800C36D0
0x1800c360b  mov     rax, 3FFFFFFFFFFFFFFh
0x1800c3615  cmp     [rsp+1A18h+var_19C8], rax
0x1800c361a  jz      loc_1800C3E4B
0x1800c3620  mov     r13, [rsp+1A18h+var_19D0]
0x1800c3625  lea     rax, [rsp+1A18h+var_19D0]
0x1800c362a  mov     [rsp+1A18h+var_19B8], rax
0x1800c362f  mov     [rsp+1A18h+var_19B8+8], rsi
0x1800c3634  mov     ecx, 40h ; '@'; Size
0x1800c3639  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800c363e  mov     r15, rax
0x1800c3641  mov     rax, [rsp+1A18h+var_19E8]
0x1800c3646  movups  xmm0, xmmword ptr [rax]
0x1800c3649  movdqu  xmmword ptr [r15+20h], xmm0
0x1800c364f  mov     [r15+30h], rsi
0x1800c3653  mov     [r15+38h], rsi
0x1800c3657  test    r14, r14
0x1800c365a  jz      short loc_1800C3661
0x1800c365c  lock inc dword ptr [r14+8]
0x1800c3661  mov     rax, [rsp+1A18h+var_19A0]
0x1800c3666  mov     [r15+30h], rax
0x1800c366a  mov     [r15+38h], r14
0x1800c366e  mov     [r15], r13
0x1800c3671  mov     [r15+8], r13
0x1800c3675  mov     [r15+10h], r13
0x1800c3679  mov     [r15+18h], si
0x1800c367e  mov     [rsp+1A18h+var_19B8+8], rsi
0x1800c3683  lea     rcx, [rsp+1A18h+var_19B8]
0x1800c3688  call    ??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBU_GUID@@V?$shared_ptr@VPortResource@Resource@Service@HNS@@@std@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<_GUID const,std::shared_ptr<HNS::Service::Resource::PortResource>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<_GUID const,std::shared_ptr<HNS::Service::Resource::PortResource>>,void *>>>(void)
0x1800c368d  mov     rax, [rsp+1A18h+var_19E0]
0x1800c3692  mov     [rsp+1A18h+var_1988], rax
0x1800c369a  mov     eax, dword ptr [rsp+1A18h+var_19F8]
0x1800c369e  mov     dword ptr [rsp+1A18h+var_1980], eax
0x1800c36a5  mov     rax, [rsp+1A18h+var_1998]
0x1800c36ad  mov     dword ptr [rsp+1A18h+var_1980+4], eax
0x1800c36b4  mov     r8, r15
0x1800c36b7  lea     rdx, [rsp+1A18h+var_1988]
0x1800c36bf  lea     rcx, [rsp+1A18h+var_19D0]
0x1800c36c4  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@G@std@@@std@@QEAAPEAU?$_Tree_node@GPEAX@2@U?$_Tree_id@PEAU?$_Tree_node@GPEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<ushort>>::_Insert_node(std::_Tree_id<std::_Tree_node<ushort,void *> *>,std::_Tree_node<ushort,void *> * const)
0x1800c36c9  movups  xmm6, xmmword ptr cs:GUID_NULL.Data1
0x1800c36d0  test    r14, r14
0x1800c36d3  jz      short loc_1800C3715
0x1800c36d5  mov     eax, r12d
0x1800c36d8  lock xadd [r14+8], eax
0x1800c36de  add     eax, r12d
0x1800c36e1  jnz     short loc_1800C370E
0x1800c36e3  mov     rax, [r14]
0x1800c36e6  mov     rcx, r14
0x1800c36e9  mov     rax, [rax]
0x1800c36ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c36f1  mov     eax, r12d
0x1800c36f4  lock xadd [r14+0Ch], eax
0x1800c36fa  add     eax, r12d
0x1800c36fd  jnz     short loc_1800C370E
0x1800c36ff  mov     rax, [r14]
0x1800c3702  mov     rcx, r14
0x1800c3705  mov     rax, [rax+8]
0x1800c3709  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c370e  movups  xmm6, xmmword ptr cs:GUID_NULL.Data1
0x1800c3715  mov     rbx, [rbx]
0x1800c3718  jmp     loc_1800C34DA
0x1800c371d  mov     r14, [rsp+1A18h+SRWLock]
0x1800c3725  test    r14, r14
0x1800c3728  jz      short loc_1800C3733
0x1800c372a  mov     rcx, r14; SRWLock
0x1800c372d  call    cs:__imp_ReleaseSRWLockExclusive
0x1800c3733  mov     [rsp+1A18h+var_19EC], esi
0x1800c3737  mov     [rsp+1A18h+var_1980], rsi
0x1800c373f  mov     [rsp+1A18h+var_1978], rsi
0x1800c3747  lea     rdx, [rsp+1A18h+var_19EC]
0x1800c374c  lea     rcx, [rsp+1A18h+var_1978]
0x1800c3754  call    cs:__imp_NetMgmtEnumerateVirtualSwitch
0x1800c375a  mov     rcx, [rsp+1A18h]; this
0x1800c3762  test    eax, eax
0x1800c3764  js      loc_1800C3E51
0x1800c376a  mov     rdi, [rsp+1A18h+var_1978]
0x1800c3772  mov     [rsp+1A18h+var_19E8], rdi
0x1800c3777  mov     [rsp+1A18h+var_1980], rdi
0x1800c377f  mov     r15d, esi
0x1800c3782  mov     dword ptr [rsp+1A18h+var_19F8], esi
0x1800c3786  cmp     [rsp+1A18h+var_19EC], esi
0x1800c378a  jbe     loc_1800C3B74
0x1800c3790  lea     r13, aOnecoreVmDvNet_188; "onecore\\vm\\dv\\net\\hns\\service\\cor"...
0x1800c3797  mov     eax, r15d
0x1800c379a  imul    rdx, rax, 0E38h
0x1800c37a1  lea     rcx, [rsp+1A18h+var_18C8]; void *
0x1800c37a9  add     rdx, rdi; Src
0x1800c37ac  mov     r8d, 0E38h; Size
0x1800c37b2  call    memcpy_0
0x1800c37b7  xorps   xmm0, xmm0
0x1800c37ba  movups  xmmword ptr [rsp+1A18h+SRWLock], xmm0
0x1800c37c2  lea     rdx, [rsp+1A18h+SRWLock]; struct _GUID *
0x1800c37ca  lea     rcx, [rsp+1A18h+var_18C8]; unsigned __int16 *
0x1800c37d2  call    ?StringToGuid@@YAXPEBGPEAU_GUID@@@Z; StringToGuid(ushort const *,_GUID *)
0x1800c37d7  mov     rdi, [rsp+1A18h+var_19D0]
0x1800c37dc  mov     r14, [rdi+8]
0x1800c37e0  xor     eax, eax
0x1800c37e2  mov     dword ptr [rsp+1A18h+var_18E8+0Ch], eax
0x1800c37e9  mov     rbx, rdi
0x1800c37ec  jmp     short loc_1800C3815
0x1800c37ee  lea     rcx, [r14+20h]; Buf1
0x1800c37f2  mov     r8d, 10h; Size
0x1800c37f8  lea     rdx, [rsp+1A18h+SRWLock]; Buf2
0x1800c3800  call    memcmp_0
0x1800c3805  test    eax, eax
0x1800c3807  jns     short loc_1800C380F
0x1800c3809  mov     r14, [r14+10h]
0x1800c380d  jmp     short loc_1800C3815
0x1800c380f  mov     rbx, r14
0x1800c3812  mov     r14, [r14]
0x1800c3815  cmp     [r14+19h], sil
0x1800c3819  jz      short loc_1800C37EE
0x1800c381b  cmp     [rbx+19h], sil
0x1800c381f  jnz     loc_1800C38E9
0x1800c3825  lea     rdx, [rbx+20h]; Buf2
0x1800c3829  mov     r8d, 10h; Size
0x1800c382f  lea     rcx, [rsp+1A18h+SRWLock]; Buf1
0x1800c3837  call    memcmp_0
0x1800c383c  test    eax, eax
0x1800c383e  js      loc_1800C38E9
0x1800c3844  cmp     rbx, rdi
0x1800c3847  jz      loc_1800C38E9
0x1800c384d  mov     rcx, [rbx+10h]
0x1800c3851  mov     rdx, rbx
0x1800c3854  cmp     [rcx+19h], sil
0x1800c3858  jz      short loc_1800C3875
0x1800c385a  mov     rax, [rbx+8]
0x1800c385e  jmp     short loc_1800C386D
0x1800c3860  cmp     rbx, [rax+10h]
0x1800c3864  jnz     short loc_1800C388A
0x1800c3866  mov     rbx, rax
0x1800c3869  mov     rax, [rax+8]
0x1800c386d  cmp     [rax+19h], sil
0x1800c3871  jz      short loc_1800C3860
0x1800c3873  jmp     short loc_1800C388A
0x1800c3875  mov     rcx, [rcx]
0x1800c3878  cmp     [rcx+19h], sil
0x1800c387c  jnz     short loc_1800C388A
0x1800c387e  mov     rax, [rcx]
0x1800c3881  mov     rcx, rax
0x1800c3884  cmp     [rax+19h], sil
0x1800c3888  jz      short loc_1800C387E
0x1800c388a  lea     rcx, [rsp+1A18h+var_19D0]
0x1800c388f  call    ?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VHNSObjectProperty@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VHNSObjectProperty@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VHNSObjectProperty@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,HNSObjectProperty>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,HNSObjectProperty>>>,std::_Iterator_base0>)
0x1800c3894  mov     rdi, rax
0x1800c3897  mov     rbx, [rax+38h]
0x1800c389b  test    rbx, rbx
0x1800c389e  jz      short loc_1800C38D7
0x1800c38a0  mov     ecx, r12d
0x1800c38a3  lock xadd [rbx+8], ecx
0x1800c38a8  add     ecx, r12d
0x1800c38ab  jnz     short loc_1800C38D7
0x1800c38ad  mov     rdx, [rbx]
0x1800c38b0  mov     rcx, rbx
0x1800c38b3  mov     rax, [rdx]
0x1800c38b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c38bb  mov     eax, r12d
0x1800c38be  lock xadd [rbx+0Ch], eax
0x1800c38c3  add     eax, r12d
0x1800c38c6  jnz     short loc_1800C38D7
0x1800c38c8  mov     rax, [rbx]
0x1800c38cb  mov     rcx, rbx
0x1800c38ce  mov     rax, [rax+8]
0x1800c38d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c38d7  mov     edx, 40h ; '@'; struct std::nothrow_t *
0x1800c38dc  mov     rcx, rdi; void *
0x1800c38df  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800c38e4  jmp     loc_1800C3B5C
0x1800c38e9  cmp     [rsp+1A18h+var_A98], 1
0x1800c38f1  jnz     loc_1800C3ACA
0x1800c38f7  mov     rbx, rsi
0x1800c38fa  mov     [rsp+1A18h+var_19E0], rsi
0x1800c38ff  lea     r8, [rsp+1A18h+var_19F0]
0x1800c3904  lea     rdx, [rsp+1A18h+var_19E0]
0x1800c3909  lea     rcx, [rsp+1A18h+var_18C8]
0x1800c3911  call    cs:__imp_NetMgmtEnumerateVirtualSwitchPorts
0x1800c3917  test    eax, eax
0x1800c3919  js      loc_1800C3A7B
0x1800c391f  mov     rbx, [rsp+1A18h+var_19E0]
0x1800c3924  mov     [rsp+1A18h+var_1958], rbx
0x1800c392c  mov     edi, esi
0x1800c392e  cmp     [rsp+1A18h+var_19F0], esi
0x1800c3932  jbe     loc_1800C3A7B
0x1800c3938  mov     eax, edi
0x1800c393a  imul    r14, rax, 254Ch
0x1800c3941  add     r14, rbx
0x1800c3944  mov     eax, [r14+2534h]
0x1800c394b  movzx   eax, ax
0x1800c394e  cmp     eax, 2
0x1800c3951  jnz     short loc_1800C39A1
0x1800c3953  lea     r15, [r14+606h]
  ... truncated ...
```
