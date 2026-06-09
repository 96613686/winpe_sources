# PreProcessPaths<_IPV4_PATH_KEY,_IPV4_PATH_ROD>(TNcsiNsiTable<_IPV4_PATH_KEY,_IPV4_PATH_ROD> const &,NcsiCantConnectList<_IPV4_PATH_KEY> &,LocalConnects &,LocalNets &)

- ea: `0x180012950`
- end: `0x18001334b`
- name: `??$PreProcessPaths@U_IPV4_PATH_KEY@@U_IPV4_PATH_ROD@@@@YAXAEBV?$TNcsiNsiTable@U_IPV4_PATH_KEY@@U_IPV4_PATH_ROD@@@@AEAV?$NcsiCantConnectList@U_IPV4_PATH_KEY@@@@AEAVLocalConnects@@AEAVLocalNets@@@Z`
- size: `2555`
- prototype: `void()`
- caller_count: `1`
- callee_count: `17`
- tags: ``

## callers

- `0x180012708`

## callees

- `0x180010200`
- `0x180011a58`
- `0x1800128d0`
- `0x180012950`
- `0x180013360`
- `0x1800134a0`
- `0x1800134fc`
- `0x180013548`
- `0x180013814`
- `0x1800138cc`
- `0x1800139e0`
- `0x180013f0c`
- `0x1800228ec`
- `0x180022c2c`
- `0x18003eca8`
- `0x180047240`
- `0x180047f54`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012ab5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012c18`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012ddf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012f0b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001301b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013270`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800132d2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012ab5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012c18`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012ddf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012f0b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001301b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013270`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800132d2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001298a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012ae2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012ca9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012e5a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800131e5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001298a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012ae2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012ca9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012e5a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800131e5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180012977`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180012977`

## pseudocode

```c
void PreProcessPaths<_IPV4_PATH_KEY,_IPV4_PATH_ROD>()
{
  LocalConnects *v0; // rcx
  __int64 v1; // r13
  __int64 v2; // r12
  __int64 v3; // rdi
  __int64 v4; // rsi
  __int64 v5; // r15
  int v6; // r10d
  struct in_addr v7; // r11d
  __int64 v8; // r14
  char v9; // bl
  unsigned int v10; // r8d
  _QWORD *v11; // rbx
  __int64 v12; // r11
  __int64 v13; // rcx
  __int64 v14; // r9
  __int64 v15; // rdi
  int v16; // r10d
  int v17; // r8d
  unsigned __int64 v18; // rax
  unsigned int v19; // eax
  unsigned __int64 v20; // rax
  unsigned int v21; // eax
  __int64 v22; // rcx
  int v23; // r8d
  unsigned __int64 v24; // rax
  unsigned int v25; // eax
  int v26; // r8d
  unsigned __int64 v27; // r9
  _QWORD *v28; // rbx
  __int64 v29; // r11
  __int64 v30; // rcx
  __int64 v31; // r9
  __int64 v32; // rdi
  unsigned __int64 *v33; // r12
  int v34; // r10d
  int v35; // r8d
  unsigned int v36; // eax
  unsigned __int64 v37; // rax
  unsigned int v38; // eax
  __int64 v39; // rcx
  int v40; // r8d
  unsigned __int64 v41; // rax
  unsigned int v42; // eax
  int v43; // eax
  __int64 j; // r8
  unsigned __int8 k; // r9
  unsigned __int8 v46; // r10
  unsigned __int8 v47; // r11
  char v48; // bl
  unsigned __int8 v49; // r9
  __int64 v50; // r9
  void *v51; // rax
  __int64 v52; // r9
  void *v53; // rax
  LocalConnects *v54; // rcx
  __int64 v55; // rcx
  __int64 v56; // r13
  __int64 v57; // rbx
  __int64 i; // rdi
  __int64 *v59; // rbx
  __int64 v60; // rdi
  __int64 v61; // rbx
  int v62; // [rsp+40h] [rbp-59h]
  const char *v63; // [rsp+48h] [rbp-51h]
  struct _RTL_CRITICAL_SECTION *v64; // [rsp+50h] [rbp-49h] BYREF
  DWORD TickCount; // [rsp+58h] [rbp-41h]
  __int64 v66; // [rsp+60h] [rbp-39h]
  __int64 v67; // [rsp+68h] [rbp-31h]
  struct _RTL_CRITICAL_SECTION *v68; // [rsp+70h] [rbp-29h]
  int v69; // [rsp+84h] [rbp-15h]
  __int128 v70; // [rsp+90h] [rbp-9h] BYREF
  int v71; // [rsp+A0h] [rbp+7h]

  TickCount = GetTickCount();
  EnterCriticalSection(&g_ncsiLock);
  v68 = &g_ncsiLock;
  NcsiCantConnectList<_IPV4_PATH_KEY>::ExpireConnections();
  LocalConnects::ExpireConnections(v0);
  v1 = qword_18009DD48;
  v66 = qword_18009DD48;
  v2 = qword_18009DD58;
  v67 = qword_18009DD58;
  v3 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0
    && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u )
  {
    WPP_SF_d(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      19,
      WPP_d2d73694d2e23c12fceb2d470f7bf333_Traceguids,
      g_nsiPathTablev4);
    v3 = WPP_GLOBAL_Control;
  }
  v4 = 0;
  while ( (unsigned int)v4 < g_nsiPathTablev4 )
  {
    v5 = 24 * v4 + v1;
    v6 = *(_DWORD *)(v5 + 20);
    v7 = *(struct in_addr *)(v5 + 16);
    if ( v6 != v7 )
    {
      v8 = v2 + 104LL * (unsigned int)v4;
      v9 = *(_BYTE *)(v8 + 20);
      if ( !v9 )
      {
        EnterCriticalSection(&g_ncsiCantConnectStoreIPv4);
        v11 = (_QWORD *)qword_18009D6A8;
        v12 = *(_QWORD *)(qword_18009D6A8 + 8);
        v13 = v12;
        v14 = qword_18009D6A8;
        v15 = qword_18009D6A8;
        if ( !*(_BYTE *)(v12 + 25) )
        {
          v16 = *(_DWORD *)v5;
          do
          {
            v17 = *(_DWORD *)(v13 + 32);
            if ( v17 < v16
              || v17 <= v16
              && (v18 = *(_QWORD *)(v5 + 8), *(_QWORD *)(v13 + 40) <= v18)
              && (*(_QWORD *)(v13 + 40) < v18
               || (v19 = *(_DWORD *)(v5 + 16), *(_DWORD *)(v13 + 48) <= v19)
               && (*(_DWORD *)(v13 + 48) < v19 || *(_DWORD *)(v13 + 52) < *(_DWORD *)(v5 + 20))) )
            {
              v13 += 16;
            }
            else
            {
              if ( *(_BYTE *)(v15 + 25) )
              {
                if ( v16 < v17
                  || (v20 = *(_QWORD *)(v13 + 40), *(_QWORD *)(v5 + 8) < v20)
                  || *(_QWORD *)(v5 + 8) <= v20
                  && ((v21 = *(_DWORD *)(v13 + 48), *(_DWORD *)(v5 + 16) < v21)
                   || *(_DWORD *)(v5 + 16) <= v21 && *(_DWORD *)(v5 + 20) < *(_DWORD *)(v13 + 52)) )
                {
                  v15 = v13;
                }
              }
              v14 = v13;
            }
            v13 = *(_QWORD *)v13;
          }
          while ( !*(_BYTE *)(v13 + 25) );
        }
        if ( *(_BYTE *)(v15 + 25) )
          v22 = *(_QWORD *)(qword_18009D6A8 + 8);
        else
          v22 = *(_QWORD *)v15;
        if ( !*(_BYTE *)(v22 + 25) )
        {
          v23 = *(_DWORD *)v5;
          do
          {
            if ( v23 >= *(_DWORD *)(v22 + 32)
              && (v23 > *(_DWORD *)(v22 + 32)
               || (v24 = *(_QWORD *)(v22 + 40), *(_QWORD *)(v5 + 8) > v24)
               || *(_QWORD *)(v5 + 8) >= v24
               && (v25 = *(_DWORD *)(v22 + 48), *(_DWORD *)(v5 + 16) >= v25)
               && (*(_DWORD *)(v5 + 16) > v25 || *(_DWORD *)(v5 + 20) >= *(_DWORD *)(v22 + 52))) )
            {
              v22 = *(_QWORD *)(v22 + 16);
            }
            else
            {
              v15 = v22;
              v22 = *(_QWORD *)v22;
            }
          }
          while ( !*(_BYTE *)(v22 + 25) );
        }
        v64 = (struct _RTL_CRITICAL_SECTION *)v14;
        if ( v14 == *(_QWORD *)qword_18009D6A8 && *(_BYTE *)(v15 + 25) )
        {
          std::_Tree_val<std::_Tree_simple_types<std::pair<_IPV4_PATH_KEY const,unsigned long>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<_IPV4_PATH_KEY const,unsigned long>,void *>>>(
            (__int64)&qword_18009D6A8,
            (__int64)&qword_18009D6A8,
            v12);
          v11[1] = v11;
          *v11 = v11;
          v11[2] = v11;
          qword_18009D6B0 = 0;
        }
        else
        {
          while ( v14 != v15 )
          {
            std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_IPV4_PATH_KEY const,unsigned long>>>,std::_Iterator_base0>::operator++(&v64);
            v51 = (void *)std::_Tree_val<std::_Tree_simple_types<std::pair<_IPV4_PATH_KEY const,unsigned long>>>::_Extract(
                            &qword_18009D6A8,
                            v50);
            std::_Deallocate<16>(v51, 0x40u);
            v14 = (__int64)v64;
          }
        }
        LeaveCriticalSection(&g_ncsiCantConnectStoreIPv4);
        v3 = WPP_GLOBAL_Control;
        if ( *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 5u
          || (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) == 0 )
        {
          goto LABEL_12;
        }
        v63 = "PathStateUnreachable";
        v62 = *(_DWORD *)(v8 + 16);
        goto LABEL_50;
      }
      if ( *(_BYTE *)(v8 + 21) )
      {
        if ( !LocalNets::AddressIsLocal((LocalNets *)(3 * v4), v7) )
          goto LABEL_134;
        v70 = 0;
        v71 = 0;
        LOWORD(v70) = 2;
        DWORD1(v70) = *(_DWORD *)(v5 + 16);
        EnterCriticalSection(&g_ncsiLocalConnects);
        v64 = &g_ncsiLocalConnects;
        v56 = qword_18009D668;
        v57 = *(_QWORD *)(qword_18009D668 + 8);
        v69 = 0;
        for ( i = qword_18009D668; !*(_BYTE *)(v57 + 25); v57 = *(_QWORD *)v57 )
        {
          if ( memcmp_0((const void *)(v57 + 32), (const void *)(v5 + 8), 8u) < 0 )
            v57 += 16;
          else
            i = v57;
        }
        if ( *(_BYTE *)(i + 25) || memcmp_0((const void *)(v5 + 8), (const void *)(i + 32), 8u) < 0 )
          i = v56;
        if ( i == v56 )
        {
          LeaveCriticalSection(&g_ncsiLocalConnects);
          goto LABEL_156;
        }
        v59 = (__int64 *)(i + 40);
        v60 = std::_Tree<std::_Tmap_traits<INX_ADDR,unsigned long,std::less<INX_ADDR>,std::allocator<std::pair<INX_ADDR const,unsigned long>>,0>>::_Find<INX_ADDR>(
                i + 40,
                &v70);
        v61 = *v59;
        LeaveCriticalSection(&g_ncsiLocalConnects);
        if ( v60 == v61 )
        {
LABEL_156:
          *(_DWORD *)(v8 + 16) = -1;
          v3 = WPP_GLOBAL_Control;
          if ( *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 5u
            || (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) == 0 )
          {
            goto LABEL_12;
          }
          v63 = "PathStateLocalNotConnected";
          LOBYTE(v62) = -1;
        }
        else
        {
LABEL_134:
          if ( (unsigned __int8)NcsiCantConnectList<_IPV4_PATH_KEY>::AddItem(v55, v5) )
          {
            *(_DWORD *)(v8 + 16) = 0;
            v3 = WPP_GLOBAL_Control;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
            {
              if ( *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 5u )
                goto LABEL_12;
              WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 20, WPP_d2d73694d2e23c12fceb2d470f7bf333_Traceguids);
              v3 = WPP_GLOBAL_Control;
            }
            if ( *(_BYTE *)(v3 + 25) < 5u )
              goto LABEL_12;
            VerboseMessage(v5, v8, 1);
            goto LABEL_11;
          }
          *(_DWORD *)(v8 + 16) = -1;
          v3 = WPP_GLOBAL_Control;
          if ( *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 5u
            || (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) == 0 )
          {
            goto LABEL_12;
          }
          v63 = "PathStateCantConnectItemOld";
          LOBYTE(v62) = -1;
        }
LABEL_50:
        v27 = *(_QWORD *)(v5 + 8);
LABEL_51:
        WPP_SF_iDDddds(
          *(_QWORD *)(v3 + 16),
          *(unsigned __int8 *)(v8 + 20),
          v26,
          v27,
          *(_DWORD *)(v5 + 20),
          *(_DWORD *)(v5 + 16),
          *(_BYTE *)(v8 + 20),
          *(_BYTE *)(v8 + 21),
          v62,
          (__int64)v63);
        goto LABEL_11;
      }
      v10 = *(_DWORD *)(v8 + 16);
      if ( v10 > 0xEA60 || TickCount < 0xEA60 )
      {
        if ( *(_BYTE *)(v3 + 25) < 5u || (_UNKNOWN *)v3 == &WPP_GLOBAL_Control || (*(_BYTE *)(v3 + 28) & 2) == 0 )
          goto LABEL_12;
        WPP_SF_iDDddds(
          *(_QWORD *)(v3 + 16),
          *(unsigned __int8 *)(104LL * (unsigned int)v4 + v2 + 21),
          v10,
          *(_QWORD *)(v1 + 24 * v4 + 8),
          v6,
          v7.S_un.S_un_b.s_b1,
          v9,
          *(_BYTE *)(104LL * (unsigned int)v4 + v2 + 21),
          v10,
          (__int64)"PathStateCanConnectTooOld");
        goto LABEL_11;
      }
      if ( v10 <= 0x3A98 )
      {
        if ( *(_BYTE *)(v3 + 25) < 5u || (_UNKNOWN *)v3 == &WPP_GLOBAL_Control || (*(_BYTE *)(v3 + 28) & 2) == 0 )
          goto LABEL_12;
        WPP_SF_iDDddds(
          *(_QWORD *)(v3 + 16),
          v5,
          v10,
          *(_QWORD *)(24 * v4 + v1 + 8),
          v6,
          v7.S_un.S_un_b.s_b1,
          v9,
          *(_BYTE *)(v8 + 21),
          v10,
          (__int64)"PathStateCanConnectTooNew");
        goto LABEL_11;
      }
      EnterCriticalSection(&g_ncsiCantConnectStoreIPv4);
      v28 = (_QWORD *)qword_18009D6A8;
      v29 = *(_QWORD *)(qword_18009D6A8 + 8);
      v30 = v29;
      v31 = qword_18009D6A8;
      v32 = qword_18009D6A8;
      v33 = (unsigned __int64 *)(v5 + 8);
      if ( !*(_BYTE *)(v29 + 25) )
      {
        v34 = *(_DWORD *)v5;
        do
        {
          v35 = *(_DWORD *)(v30 + 32);
          if ( v35 < v34
            || v35 <= v34
            && *(_QWORD *)(v30 + 40) <= *v33
            && (*(_QWORD *)(v30 + 40) < *v33
             || (v36 = *(_DWORD *)(v5 + 16), *(_DWORD *)(v30 + 48) <= v36)
             && (*(_DWORD *)(v30 + 48) < v36 || *(_DWORD *)(v30 + 52) < *(_DWORD *)(v5 + 20))) )
          {
            v30 += 16;
          }
          else
          {
            if ( *(_BYTE *)(v32 + 25) )
            {
              if ( v34 < v35
                || (v37 = *(_QWORD *)(v30 + 40), *v33 < v37)
                || *v33 <= v37
                && (v38 = *(_DWORD *)(v30 + 48), *(_DWORD *)(v5 + 16) <= v38)
                && (*(_DWORD *)(v5 + 16) < v38 || *(_DWORD *)(v5 + 20) < *(_DWORD *)(v30 + 52)) )
              {
                v32 = v30;
              }
            }
            v31 = v30;
          }
          v30 = *(_QWORD *)v30;
        }
        while ( !*(_BYTE *)(v30 + 25) );
      }
      if ( *(_BYTE *)(v32 + 25) )
        v39 = *(_QWORD *)(qword_18009D6A8 + 8);
      else
        v39 = *(_QWORD *)v32;
      if ( !*(_BYTE *)(v39 + 25) )
      {
        v40 = *(_DWORD *)v5;
        do
        {
          if ( v40 >= *(_DWORD *)(v39 + 32)
            && (v40 > *(_DWORD *)(v39 + 32)
             || (v41 = *(_QWORD *)(v39 + 40), *v33 > v41)
             || *v33 >= v41
             && (v42 = *(_DWORD *)(v39 + 48), *(_DWORD *)(v5 + 16) >= v42)
             && (*(_DWORD *)(v5 + 16) > v42 || *(_DWORD *)(v5 + 20) >= *(_DWORD *)(v39 + 52))) )
          {
            v39 = *(_QWORD *)(v39 + 16);
          }
          else
          {
            v32 = v39;
            v39 = *(_QWORD *)v39;
          }
        }
        while ( !*(_BYTE *)(v39 + 25) );
      }
      v64 = (struct _RTL_CRITICAL_SECTION *)v31;
      if ( v31 == *(_QWORD *)qword_18009D6A8 && *(_BYTE *)(v32 + 25) )
      {
        std::_Tree_val<std::_Tree_simple_types<std::pair<_IPV4_PATH_KEY const,unsigned long>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<_IPV4_PATH_KEY const,unsigned long>,void *>>>(
          (__int64)&qword_18009D6A8,
          (__int64)&qword_18009D6A8,
          v29);
        v28[1] = v28;
        *v28 = v28;
        v28[2] = v28;
        qword_18009D6B0 = 0;
      }
      else
      {
        while ( v31 != v32 )
        {
          std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_IPV4_PATH_KEY const,unsigned long>>>,std::_Iterator_base0>::operator++(&v64);
          v53 = (void *)std::_Tree_val<std::_Tree_simple_types<std::pair<_IPV4_PATH_KEY const,unsigned long>>>::_Extract(
                          &qword_18009D6A8,
                          v52);
          std::_Deallocate<16>(v53, 0x40u);
          v31 = (__int64)v64;
        }
      }
      LeaveCriticalSection(&g_ncsiCantConnectStoreIPv4);
      v43 = *(_DWORD *)(v5 + 16);
      if ( (_BYTE)v43 != 127
        && (unsigned __int16)v43 != 65193
        && (_BYTE)v43 != 10
        && (*(_DWORD *)(v5 + 16) & 0xF0FF) != 0x10AC
        && (unsigned __int16)v43 != 43200
        && (v43 & 0xF0) != 0xE0 )
      {
        v70 = 0;
        v71 = 0;
        LOWORD(v70) = 2;
        DWORD1(v70) = v43;
        EnterCriticalSection(&g_ncsiLocalNets);
        for ( j = qword_18009D628; j != qword_18009D630; j += 24 )
        {
          if ( *(_WORD *)j == 2 )
          {
            for ( k = 0; ; ++k )
            {
              if ( k == 4 )
              {
                v49 = 32;
                goto LABEL_102;
              }
              v46 = *((_BYTE *)&v70 + k + 4);
              v47 = *(_BYTE *)(j + k + 4);
              if ( v46 != v47 )
                break;
            }
            v48 = 0;
            if ( ((v46 ^ v47) & 0x80u) == 0 )
            {
              do
                ++v48;
              while ( (v46 & (unsigned __int8)(1 << (7 - v48))) == (v47 & (unsigned __int8)(1 << (7 - v48))) );
            }
            v49 = v48 + 8 * k;
LABEL_102:
            if ( v49 >= *(_BYTE *)(j + 20) )
            {
              LeaveCriticalSection(&g_ncsiLocalNets);
              goto LABEL_122;
            }
          }
        }
        LeaveCriticalSection(&g_ncsiLocalNets);
        v3 = WPP_GLOBAL_Control;
        if ( *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u
          && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
        {
          v63 = "PathStateCanConnect";
          v62 = *(_DWORD *)(v8 + 16);
          v27 = *v33;
          goto LABEL_51;
        }
        goto LABEL_12;
      }
LABEL_122:
      v54 = (LocalConnects *)WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0
        && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u )
      {
        WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 21, WPP_d2d73694d2e23c12fceb2d470f7bf333_Traceguids);
      }
      v70 = 0;
      v71 = 0;
      LOWORD(v70) = 2;
      DWORD1(v70) = *(_DWORD *)(v5 + 16);
      LocalConnects::StoreSuccessfulPath(v54, (const union _NET_LUID_LH *)(v5 + 8), (const struct INX_ADDR *)&v70);
      v3 = WPP_GLOBAL_Control;
      if ( *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u )
      {
        VerboseMessage(v5, v8, 5);
LABEL_11:
        v3 = WPP_GLOBAL_Control;
      }
    }
LABEL_12:
    v4 = (unsigned int)(v4 + 1);
    v1 = v66;
    v2 = v67;
  }
  LeaveCriticalSection(&g_ncsiLock);
}

```

## disassembly

```asm
0x180012950  push    rbp
0x180012952  push    rbx
0x180012953  push    rsi
0x180012954  push    rdi
0x180012955  push    r12
0x180012957  push    r13
0x180012959  push    r14
0x18001295b  push    r15
0x18001295d  lea     rbp, [rsp-1Fh]
0x180012962  sub     rsp, 0B8h
0x180012969  mov     rax, cs:__security_cookie
0x180012970  xor     rax, rsp
0x180012973  mov     [rbp+57h+var_48], rax
0x180012977  call    cs:__imp_GetTickCount
0x18001297d  mov     [rbp+57h+var_98], eax
0x180012980  lea     rbx, ?g_ncsiLock@@3Vcritical_section@wil@@A; wil::critical_section g_ncsiLock
0x180012987  mov     rcx, rbx; lpCriticalSection
0x18001298a  call    cs:__imp_EnterCriticalSection
0x180012990  mov     [rbp+57h+var_80], rbx
0x180012994  call    ?ExpireConnections@?$NcsiCantConnectList@U_IPV4_PATH_KEY@@@@QEAAXXZ; NcsiCantConnectList<_IPV4_PATH_KEY>::ExpireConnections(void)
0x180012999  call    ?ExpireConnections@LocalConnects@@QEAAXXZ; LocalConnects::ExpireConnections(void)
0x18001299e  mov     r13, cs:qword_18009DD48
0x1800129a5  mov     [rbp+57h+var_90], r13
0x1800129a9  mov     r12, cs:qword_18009DD58
0x1800129b0  mov     [rbp+57h+var_88], r12
0x1800129b4  lea     rax, WPP_GLOBAL_Control
0x1800129bb  mov     rdi, cs:WPP_GLOBAL_Control
0x1800129c2  cmp     rdi, rax
0x1800129c5  jnz     loc_18001317A
0x1800129cb  xor     esi, esi
0x1800129cd  cmp     cs:?g_nsiPathTablev4@@3V?$TNcsiNsiTable@U_IPV4_PATH_KEY@@U_IPV4_PATH_ROD@@@@A, esi; TNcsiNsiTable<_IPV4_PATH_KEY,_IPV4_PATH_ROD> g_nsiPathTablev4
0x1800129d3  jbe     loc_180012AB2
0x1800129d9  nop     dword ptr [rax+00000000h]
0x1800129e0  mov     eax, esi
0x1800129e2  lea     rcx, [rsi+rsi*2]; this
0x1800129e6  lea     r9, ds:0[rcx*8]
0x1800129ee  lea     r15, [r9+r13]
0x1800129f2  lea     rdx, [r9+r13]
0x1800129f6  mov     r10d, [r15+14h]
0x1800129fa  mov     r11d, [rdx+10h]
0x1800129fe  cmp     r10d, r11d
0x180012a01  jz      loc_180012A95
0x180012a07  imul    r14, rax, 68h ; 'h'
0x180012a0b  add     r14, r12
0x180012a0e  movzx   ebx, byte ptr [r14+14h]
0x180012a13  test    bl, bl
0x180012a15  jz      loc_180012ADB
0x180012a1b  cmp     byte ptr [r14+15h], 0
0x180012a20  jnz     loc_1800130E2
0x180012a26  mov     r8d, [r14+10h]
0x180012a2a  cmp     r8d, 0EA60h
0x180012a31  jbe     loc_180012C88
0x180012a37  cmp     byte ptr [rdi+19h], 5
0x180012a3b  jb      short loc_180012A95
0x180012a3d  lea     rcx, WPP_GLOBAL_Control
0x180012a44  cmp     rdi, rcx
0x180012a47  jz      short loc_180012A95
0x180012a49  test    byte ptr [rdi+1Ch], 2
0x180012a4d  jz      short loc_180012A95
0x180012a4f  imul    rcx, rax, 68h ; 'h'
0x180012a53  movzx   edx, byte ptr [rcx+r12+15h]
0x180012a59  lea     r9, [rsi+rsi*2]
0x180012a5d  mov     rax, cs:off_18007D108; "PathStateCanConnectTooOld"
0x180012a64  mov     [rsp+0F0h+var_A8], rax
0x180012a69  mov     [rsp+0F0h+var_B0], r8d
0x180012a6e  mov     [rsp+0F0h+var_B8], edx
0x180012a72  mov     [rsp+0F0h+var_C0], ebx
0x180012a76  mov     [rsp+0F0h+var_C8], r11d
0x180012a7b  mov     [rsp+0F0h+var_D0], r10d
0x180012a80  mov     r9, [r13+r9*8+8]
0x180012a85  mov     rcx, [rdi+10h]
0x180012a89  call    WPP_SF_iDDddds
0x180012a8e  mov     rdi, cs:WPP_GLOBAL_Control
0x180012a95  inc     esi
0x180012a97  cmp     esi, cs:?g_nsiPathTablev4@@3V?$TNcsiNsiTable@U_IPV4_PATH_KEY@@U_IPV4_PATH_ROD@@@@A; TNcsiNsiTable<_IPV4_PATH_KEY,_IPV4_PATH_ROD> g_nsiPathTablev4
0x180012a9d  mov     r13, [rbp+57h+var_90]
0x180012aa1  mov     r12, [rbp+57h+var_88]
0x180012aa5  jb      loc_1800129E0
0x180012aab  lea     rbx, ?g_ncsiLock@@3Vcritical_section@wil@@A; wil::critical_section g_ncsiLock
0x180012ab2  mov     rcx, rbx; lpCriticalSection
0x180012ab5  call    cs:__imp_LeaveCriticalSection
0x180012abb  mov     rcx, [rbp+57h+var_48]
0x180012abf  xor     rcx, rsp; StackCookie
0x180012ac2  call    __security_check_cookie
0x180012ac7  add     rsp, 0B8h
0x180012ace  pop     r15
0x180012ad0  pop     r14
0x180012ad2  pop     r13
0x180012ad4  pop     r12
0x180012ad6  pop     rdi
0x180012ad7  pop     rsi
0x180012ad8  pop     rbx
0x180012ad9  pop     rbp
0x180012ada  retn
0x180012adb  lea     rcx, ?g_ncsiCantConnectStoreIPv4@@3V?$NcsiCantConnectList@U_IPV4_PATH_KEY@@@@A; lpCriticalSection
0x180012ae2  call    cs:__imp_EnterCriticalSection
0x180012ae8  mov     rbx, cs:qword_18009D6A8
0x180012aef  mov     r11, [rbx+8]
0x180012af3  mov     rcx, r11
0x180012af6  mov     r9, rbx
0x180012af9  mov     rdi, rbx
0x180012afc  cmp     byte ptr [r11+19h], 0
0x180012b01  jnz     short loc_180012B7F
0x180012b03  mov     r10d, [r15]
0x180012b06  mov     r8d, [rcx+20h]
0x180012b0a  cmp     r8d, r10d
0x180012b0d  jl      loc_18001300B
0x180012b13  jg      short loc_180012B41
0x180012b15  mov     rax, [r15+8]
0x180012b19  cmp     [rcx+28h], rax
0x180012b1d  ja      short loc_180012B41
0x180012b1f  jb      loc_18001300B
0x180012b25  mov     eax, [r15+10h]
0x180012b29  cmp     [rcx+30h], eax
0x180012b2c  ja      short loc_180012B41
0x180012b2e  jb      loc_18001300B
0x180012b34  mov     eax, [r15+14h]
0x180012b38  cmp     [rcx+34h], eax
0x180012b3b  jb      loc_18001300B
0x180012b41  cmp     byte ptr [rdi+19h], 0
0x180012b45  jz      short loc_180012B73
0x180012b47  cmp     r10d, r8d
0x180012b4a  jl      loc_1800130DA
0x180012b50  mov     rax, [rcx+28h]
0x180012b54  cmp     [r15+8], rax
0x180012b58  jb      loc_1800130DA
0x180012b5e  ja      short loc_180012B73
0x180012b60  mov     eax, [rcx+30h]
0x180012b63  cmp     [r15+10h], eax
0x180012b67  jb      loc_1800130DA
0x180012b6d  jbe     loc_1800130CD
0x180012b73  mov     r9, rcx
0x180012b76  mov     rcx, [rcx]
0x180012b79  cmp     byte ptr [rcx+19h], 0
0x180012b7d  jz      short loc_180012B06
0x180012b7f  cmp     byte ptr [rdi+19h], 0
0x180012b83  jz      loc_180012FEB
0x180012b89  mov     rcx, r11
0x180012b8c  cmp     byte ptr [rcx+19h], 0
0x180012b90  jnz     short loc_180012BCE
0x180012b92  mov     r8d, [r15]
0x180012b95  cmp     r8d, [rcx+20h]
0x180012b99  jl      loc_180013000
0x180012b9f  jg      short loc_180012BC4
0x180012ba1  mov     rax, [rcx+28h]
0x180012ba5  cmp     [r15+8], rax
0x180012ba9  ja      short loc_180012BC4
0x180012bab  jb      loc_180013000
0x180012bb1  mov     eax, [rcx+30h]
0x180012bb4  cmp     [r15+10h], eax
0x180012bb8  jb      loc_180013000
0x180012bbe  jbe     loc_180012FF3
0x180012bc4  mov     rcx, [rcx+10h]
0x180012bc8  cmp     byte ptr [rcx+19h], 0
0x180012bcc  jz      short loc_180012B95
0x180012bce  mov     [rbp+57h+var_A0], r9
0x180012bd2  cmp     r9, [rbx]
0x180012bd5  jnz     loc_180012ED0
0x180012bdb  cmp     byte ptr [rdi+19h], 0
0x180012bdf  jz      loc_180012ED0
0x180012be5  mov     r8, r11
0x180012be8  lea     rdx, qword_18009D6A8
0x180012bef  lea     rcx, qword_18009D6A8
0x180012bf6  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBU_IPV4_PATH_KEY@@K@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_IPV4_PATH_KEY@@K@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBU_IPV4_PATH_KEY@@K@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBU_IPV4_PATH_KEY@@K@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_IPV4_PATH_KEY const,ulong>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<_IPV4_PATH_KEY const,ulong>,void *>>>(std::allocator<std::_Tree_node<std::pair<_IPV4_PATH_KEY const,ulong>,void *>> &,std::_Tree_node<std::pair<_IPV4_PATH_KEY const,ulong>,void *> *)
0x180012bfb  mov     [rbx+8], rbx
0x180012bff  mov     [rbx], rbx
0x180012c02  mov     [rbx+10h], rbx
0x180012c06  mov     cs:qword_18009D6B0, 0
0x180012c11  lea     rcx, ?g_ncsiCantConnectStoreIPv4@@3V?$NcsiCantConnectList@U_IPV4_PATH_KEY@@@@A; lpCriticalSection
0x180012c18  call    cs:__imp_LeaveCriticalSection
0x180012c1e  mov     rdi, cs:WPP_GLOBAL_Control
0x180012c25  cmp     byte ptr [rdi+19h], 5
0x180012c29  jb      loc_180012A95
0x180012c2f  lea     rax, WPP_GLOBAL_Control
0x180012c36  cmp     rdi, rax
0x180012c39  jz      loc_180012A95
0x180012c3f  test    byte ptr [rdi+1Ch], 2
0x180012c43  jz      loc_180012A95
0x180012c49  mov     rax, cs:off_18007D0E8; "PathStateUnreachable"
0x180012c50  mov     [rsp+0F0h+var_A8], rax
0x180012c55  mov     eax, [r14+10h]
0x180012c59  mov     [rsp+0F0h+var_B0], eax
0x180012c5d  mov     r9, [r15+8]
0x180012c61  movzx   ecx, byte ptr [r14+15h]
0x180012c66  mov     [rsp+0F0h+var_B8], ecx
0x180012c6a  movzx   edx, byte ptr [r14+14h]
0x180012c6f  mov     [rsp+0F0h+var_C0], edx
0x180012c73  mov     eax, [r15+10h]
0x180012c77  mov     [rsp+0F0h+var_C8], eax
0x180012c7b  mov     eax, [r15+14h]
0x180012c7f  mov     [rsp+0F0h+var_D0], eax
0x180012c83  jmp     loc_180012A85
0x180012c88  cmp     [rbp+57h+var_98], 0EA60h
0x180012c8f  jb      loc_180012A37
0x180012c95  cmp     r8d, 3A98h
0x180012c9c  jbe     loc_180012F59
0x180012ca2  lea     rcx, ?g_ncsiCantConnectStoreIPv4@@3V?$NcsiCantConnectList@U_IPV4_PATH_KEY@@@@A; lpCriticalSection
0x180012ca9  call    cs:__imp_EnterCriticalSection
0x180012caf  mov     rbx, cs:qword_18009D6A8
0x180012cb6  mov     r11, [rbx+8]
0x180012cba  mov     rcx, r11
0x180012cbd  mov     r9, rbx
0x180012cc0  mov     rdi, rbx
0x180012cc3  lea     r12, [r15+8]
0x180012cc7  cmp     byte ptr [r11+19h], 0
0x180012ccc  jnz     short loc_180012D46
0x180012cce  mov     r10d, [r15]
0x180012cd1  mov     r8d, [rcx+20h]
0x180012cd5  cmp     r8d, r10d
0x180012cd8  jl      loc_180013166
0x180012cde  jg      short loc_180012D0C
0x180012ce0  mov     rax, [r12]
0x180012ce4  cmp     [rcx+28h], rax
0x180012ce8  ja      short loc_180012D0C
0x180012cea  jb      loc_180013166
0x180012cf0  mov     eax, [r15+10h]
0x180012cf4  cmp     [rcx+30h], eax
0x180012cf7  ja      short loc_180012D0C
0x180012cf9  jb      loc_180013166
0x180012cff  mov     eax, [r15+14h]
0x180012d03  cmp     [rcx+34h], eax
0x180012d06  jb      loc_180013166
0x180012d0c  cmp     byte ptr [rdi+19h], 0
0x180012d10  jz      short loc_180012D3A
0x180012d12  cmp     r10d, r8d
0x180012d15  jl      short loc_180012D37
0x180012d17  mov     rax, [rcx+28h]
0x180012d1b  cmp     [r12], rax
0x180012d1f  jb      short loc_180012D37
0x180012d21  ja      short loc_180012D3A
0x180012d23  mov     eax, [rcx+30h]
0x180012d26  cmp     [r15+10h], eax
0x180012d2a  ja      short loc_180012D3A
0x180012d2c  jb      short loc_180012D37
0x180012d2e  mov     eax, [rcx+34h]
0x180012d31  cmp     [r15+14h], eax
0x180012d35  jnb     short loc_180012D3A
0x180012d37  mov     rdi, rcx
0x180012d3a  mov     r9, rcx
0x180012d3d  mov     rcx, [rcx]
0x180012d40  cmp     byte ptr [rcx+19h], 0
0x180012d44  jz      short loc_180012CD1
0x180012d46  cmp     byte ptr [rdi+19h], 0
0x180012d4a  jz      loc_1800130C5
0x180012d50  mov     rcx, r11
0x180012d53  cmp     byte ptr [rcx+19h], 0
0x180012d57  jnz     short loc_180012D95
0x180012d59  mov     r8d, [r15]
0x180012d5c  cmp     r8d, [rcx+20h]
0x180012d60  jl      loc_18001315B
0x180012d66  jg      short loc_180012D8B
0x180012d68  mov     rax, [rcx+28h]
0x180012d6c  cmp     [r12], rax
0x180012d70  ja      short loc_180012D8B
0x180012d72  jb      loc_18001315B
0x180012d78  mov     eax, [rcx+30h]
0x180012d7b  cmp     [r15+10h], eax
0x180012d7f  jb      loc_18001315B
0x180012d85  jbe     loc_18001314E
0x180012d8b  mov     rcx, [rcx+10h]
0x180012d8f  cmp     byte ptr [rcx+19h], 0
0x180012d93  jz      short loc_180012D5C
0x180012d95  mov     [rbp+57h+var_A0], r9
0x180012d99  cmp     r9, [rbx]
0x180012d9c  jnz     loc_180012FB7
0x180012da2  cmp     byte ptr [rdi+19h], 0
0x180012da6  jz      loc_180012FB7
0x180012dac  mov     r8, r11
0x180012daf  lea     rdx, qword_18009D6A8
0x180012db6  lea     rcx, qword_18009D6A8
0x180012dbd  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBU_IPV4_PATH_KEY@@K@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_IPV4_PATH_KEY@@K@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBU_IPV4_PATH_KEY@@K@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBU_IPV4_PATH_KEY@@K@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_IPV4_PATH_KEY const,ulong>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<_IPV4_PATH_KEY const,ulong>,void *>>>(std::allocator<std::_Tree_node<std::pair<_IPV4_PATH_KEY const,ulong>,void *>> &,std::_Tree_node<std::pair<_IPV4_PATH_KEY const,ulong>,void *> *)
0x180012dc2  mov     [rbx+8], rbx
0x180012dc6  mov     [rbx], rbx
0x180012dc9  mov     [rbx+10h], rbx
0x180012dcd  mov     cs:qword_18009D6B0, 0
0x180012dd8  lea     rcx, ?g_ncsiCantConnectStoreIPv4@@3V?$NcsiCantConnectList@U_IPV4_PATH_KEY@@@@A; lpCriticalSection
0x180012ddf  call    cs:__imp_LeaveCriticalSection
0x180012de5  mov     eax, [r15+10h]
0x180012de9  movzx   edx, ax
0x180012dec  cmp     al, 7Fh
0x180012dee  jz      loc_18001316F
0x180012df4  cmp     edx, 0FEA9h
0x180012dfa  jz      loc_18001316F
0x180012e00  cmp     al, 0Ah
0x180012e02  jz      loc_18001316F
0x180012e08  mov     ecx, eax
0x180012e0a  and     ecx, 0F0FFh
0x180012e10  cmp     ecx, 10ACh
0x180012e16  jz      loc_18001316F
0x180012e1c  cmp     edx, 0A8C0h
0x180012e22  jz      loc_18001316F
0x180012e28  mov     ecx, eax
0x180012e2a  and     ecx, 0F0h
0x180012e30  mov     r13d, 2
0x180012e36  cmp     cl, 0E0h
0x180012e39  jz      loc_180013021
0x180012e3f  xorps   xmm0, xmm0
0x180012e42  xor     ecx, ecx
0x180012e44  movups  [rbp+57h+var_60], xmm0
0x180012e48  mov     [rbp+57h+var_50], ecx
  ... truncated ...
```
