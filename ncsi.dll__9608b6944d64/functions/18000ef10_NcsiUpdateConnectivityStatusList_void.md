# NcsiUpdateConnectivityStatusList(void)

- ea: `0x18000ef10`
- end: `0x18000fb87`
- name: `?NcsiUpdateConnectivityStatusList@@YAXXZ`
- size: `3191`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `30`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18002e9c0`

## callees

- `0x18000da48`
- `0x18000ddd0`
- `0x18000de10`
- `0x18000de6c`
- `0x18000e36c`
- `0x18000e384`
- `0x18000ef10`
- `0x18000fb90`
- `0x18000fc00`
- `0x180010060`
- `0x180010200`
- `0x180011040`
- `0x180011504`
- `0x180011a58`
- `0x180011ab4`
- `0x180012708`
- `0x180013eb0`
- `0x18001d634`
- `0x18001da50`
- `0x180021e64`
- `0x180021e7c`
- `0x180027b6c`
- `0x1800297f4`
- `0x18003f2d8`
- `0x180041530`
- `0x180041fa4`
- `0x180047240`
- `0x18004f7bc`
- `0x180053260`
- `0x1800646d8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000efdb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000eff8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f1dc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f2e5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f36c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000efdb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000eff8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f1dc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f2e5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f36c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ef67`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000efca`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000efe7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f1c0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f294`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ef67`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000efca`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000efe7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f1c0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f294`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000f11f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000f1b0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000f3bb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000f3f7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000f11f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000f1b0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000f3bb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000f3f7`

## string_xrefs

- `0x18000f127`: ` - path processing will not be carried out.`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void NcsiUpdateConnectivityStatusList(void)
{
  __int64 v0; // r9
  unsigned __int8 IsV4DeadForMaxPollCount; // bl
  char IsV6DeadForMaxPollCount; // bl
  NCSI_INTERFACE_ATTRIBUTES *v3; // rbx
  unsigned int v4; // r14d
  __int64 v5; // r15
  __int64 v6; // r13
  unsigned int v7; // esi
  __int64 v8; // rdi
  unsigned int v9; // r14d
  __int64 v10; // r15
  __int64 v11; // r13
  unsigned int v12; // esi
  __int64 v13; // rdi
  DWORD TickCount; // eax
  int v15; // edx
  int v16; // r8d
  unsigned int v17; // ebx
  const char *v18; // rsi
  __int64 v19; // rcx
  DWORD v20; // edi
  char v21; // al
  unsigned int v22; // edi
  char v23; // bl
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // rdx
  struct NCSI_INTERFACE_ATTRIBUTES *v27; // rbx
  struct NCSI_INTERFACE_ATTRIBUTES *j; // rdi
  __int64 v29; // rdx
  char v30; // bl
  __int64 v31; // rcx
  bool v32; // si
  NCSI_INTERFACE_ATTRIBUTES *v33; // rbx
  struct NCSI_INTERFACE_ATTRIBUTES *k; // rdi
  DWORD v35; // eax
  unsigned int v36; // eax
  int v37; // edx
  int v38; // r8d
  DWORD v39; // eax
  unsigned int v40; // eax
  int v41; // edx
  int v42; // r8d
  __int64 v43; // r11
  int v44; // r10d
  int v45; // r9d
  int v46; // edx
  unsigned __int64 v47; // r8
  unsigned __int64 v48; // rcx
  unsigned __int64 v49; // rdx
  unsigned __int64 v50; // rcx
  unsigned __int64 v51; // r8
  unsigned __int64 v52; // rdx
  unsigned __int64 v53; // rcx
  __int64 v54; // r12
  __int64 v55; // r11
  int v56; // r10d
  int v57; // r9d
  int v58; // edx
  unsigned __int64 v59; // r8
  unsigned __int64 v60; // rcx
  unsigned __int64 v61; // rdx
  unsigned __int64 v62; // rcx
  unsigned __int64 v63; // r8
  unsigned __int64 v64; // rdx
  unsigned __int64 v65; // rcx
  __int64 v66; // r12
  __int64 v67; // rax
  bool v68; // zf
  const char *v69; // rax
  __int64 v70; // r9
  __int64 v71; // r9
  __int64 v72; // r9
  struct NCSI_INTERFACE_ATTRIBUTES *i; // [rsp+48h] [rbp-41h]
  __int64 v74; // [rsp+58h] [rbp-31h] BYREF
  __int16 v75; // [rsp+60h] [rbp-29h]
  __int64 v76; // [rsp+68h] [rbp-21h] BYREF
  _QWORD v77[3]; // [rsp+70h] [rbp-19h] BYREF
  __int64 v78; // [rsp+88h] [rbp-1h]

  if ( _InterlockedExchange(&dword_18009DAF4, 1) != 1 )
  {
    if ( (unsigned int)std::_Atomic_storage<enum _NCSI_CLIENT_PRESENCE,4>::load() != 1 )
    {
LABEL_50:
      _InterlockedExchange(&dword_18009DAF4, 0);
      return;
    }
    EnterCriticalSection(&g_ncsiLock);
    v0 = (unsigned int)++dword_18009DAF0;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x40) != 0
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u )
    {
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 32, WPP_908899ae445231599b715923bce5511e_Traceguids, v0);
    }
    std::vector<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::_Grp_t,std::allocator<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::_Grp_t>>::vector<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::_Grp_t,std::allocator<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::_Grp_t>>(v77);
    v78 = 0;
    v74 = 0;
    v75 = 0;
    EnterCriticalSection(&stru_18009D7F8);
    IsV4DeadForMaxPollCount = anonymous_namespace_::PassivePollState::IsV4DeadForMaxPollCount();
    LeaveCriticalSection(&stru_18009D7F8);
    v76 = IsV4DeadForMaxPollCount;
    EnterCriticalSection(&stru_18009D7F8);
    IsV6DeadForMaxPollCount = anonymous_namespace_::PassivePollState::IsV6DeadForMaxPollCount();
    LeaveCriticalSection(&stru_18009D7F8);
    BYTE1(v76) = IsV6DeadForMaxPollCount;
    ObtainPacketCountDataFromNSI();
    v3 = g_ncsiInterfaceList;
    for ( i = xmmword_18009DCC0; v3 != i; v3 = (NCSI_INTERFACE_ATTRIBUTES *)((char *)v3 + 12888) )
    {
      TracePerInterfaceData(v3);
      *((_QWORD *)v3 + 556) = 0;
      *((_QWORD *)v3 + 557) = 0;
      if ( (_BYTE)v76 )
      {
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x40) != 0
          && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u )
        {
          WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 33, WPP_908899ae445231599b715923bce5511e_Traceguids, 0);
        }
      }
      else
      {
        v4 = g_nsiSubIfaceTableForCountv4;
        v5 = qword_18009DD98;
        v6 = qword_18009DDA8;
        v7 = 0;
        if ( g_nsiSubIfaceTableForCountv4 )
        {
          v8 = 0;
          do
          {
            if ( *(_QWORD *)v3 == *(_QWORD *)(v5 + 16 * v8) )
            {
              v43 = v6 + 96 * v8;
              v44 = *(_DWORD *)(v43 + 48);
              v45 = *(_DWORD *)(v43 + 44);
              v46 = *(_DWORD *)(v43 + 40);
              v47 = *(_QWORD *)(v43 + 24) - *((_QWORD *)v3 + 554);
              *((_QWORD *)v3 + 554) = *(_QWORD *)(v43 + 24);
              v48 = (unsigned int)(v46 - *((_DWORD *)v3 + 1116));
              *((_DWORD *)v3 + 1116) = v46;
              v49 = v47 - v48;
              if ( v47 <= v48 )
                v49 = 0;
              v50 = (unsigned int)(v45 - *((_DWORD *)v3 + 1117));
              *((_DWORD *)v3 + 1117) = v45;
              v51 = v49 - v50;
              if ( v49 <= v50 )
                v51 = 0;
              v52 = (unsigned int)(v44 - *((_DWORD *)v3 + 1118));
              *((_DWORD *)v3 + 1118) = v44;
              v53 = v51 - v52;
              if ( v51 <= v52 )
                v53 = 0;
              *((_QWORD *)v3 + 556) = v53;
              v54 = *(_QWORD *)(v43 + 32);
              if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
                && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u )
              {
                WPP_SF_ii(
                  *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                  15,
                  WPP_d2174b9e5b313c7131b16cc52be830be_Traceguids,
                  *((_QWORD *)v3 + 555),
                  *(_QWORD *)(v43 + 32));
              }
              *((_QWORD *)v3 + 557) = *((_QWORD *)v3 + 555) - v54;
              *((_QWORD *)v3 + 555) = v54;
            }
            ++v7;
            ++v8;
          }
          while ( v7 < v4 );
        }
      }
      *((_QWORD *)v3 + 1049) = 0;
      *((_QWORD *)v3 + 1050) = 0;
      if ( BYTE1(v76) )
      {
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x40) != 0
          && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u )
        {
          WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 34, WPP_908899ae445231599b715923bce5511e_Traceguids, 1);
        }
      }
      else
      {
        v9 = g_nsiSubIfaceTableForCountv6;
        v10 = qword_18009DDC0;
        v11 = qword_18009DDD0;
        v12 = 0;
        if ( g_nsiSubIfaceTableForCountv6 )
        {
          v13 = 0;
          do
          {
            if ( *(_QWORD *)v3 == *(_QWORD *)(v10 + 16 * v13) )
            {
              v55 = v11 + 96 * v13;
              v56 = *(_DWORD *)(v55 + 48);
              v57 = *(_DWORD *)(v55 + 44);
              v58 = *(_DWORD *)(v55 + 40);
              v59 = *(_QWORD *)(v55 + 24) - *((_QWORD *)v3 + 1047);
              *((_QWORD *)v3 + 1047) = *(_QWORD *)(v55 + 24);
              v60 = (unsigned int)(v58 - *((_DWORD *)v3 + 2102));
              *((_DWORD *)v3 + 2102) = v58;
              v61 = v59 - v60;
              if ( v59 <= v60 )
                v61 = 0;
              v62 = (unsigned int)(v57 - *((_DWORD *)v3 + 2103));
              *((_DWORD *)v3 + 2103) = v57;
              v63 = v61 - v62;
              if ( v61 <= v62 )
                v63 = 0;
              v64 = (unsigned int)(v56 - *((_DWORD *)v3 + 2104));
              *((_DWORD *)v3 + 2104) = v56;
              v65 = v63 - v64;
              if ( v63 <= v64 )
                v65 = 0;
              *((_QWORD *)v3 + 1049) = v65;
              v66 = *(_QWORD *)(v55 + 32);
              if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
                && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u )
              {
                WPP_SF_ii(
                  *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                  15,
                  WPP_d2174b9e5b313c7131b16cc52be830be_Traceguids,
                  *((_QWORD *)v3 + 1048),
                  *(_QWORD *)(v55 + 32));
              }
              *((_QWORD *)v3 + 1050) = *((_QWORD *)v3 + 1048) - v66;
              *((_QWORD *)v3 + 1048) = v66;
            }
            ++v12;
            ++v13;
          }
          while ( v12 < v9 );
        }
      }
      if ( !*((_DWORD *)v3 + 6) )
      {
        if ( (_BYTE)v74 )
          LOBYTE(v74) = 1;
        else
          LOBYTE(v74) = *((_BYTE *)v3 + 4353);
        if ( BYTE2(v74) )
          BYTE2(v74) = 1;
        else
          BYTE2(v74) = *((_BYTE *)v3 + 8297);
        BYTE1(v74) = BYTE1(v74) || *((_WORD *)v3 + 2180) || NCSI_INTERFACE_ATTRIBUTES::GetIfaceType(v3) == 23;
        BYTE3(v74) = BYTE3(v74)
                  || *((_WORD *)v3 + 4152)
                  || (v67 = *((_QWORD *)v3 + 1596)) != 0 && *(_DWORD *)(v67 + 100) == 23;
        if ( BYTE4(v74) || (v68 = *((_QWORD *)v3 + 557) == 0, BYTE4(v74) = 0, !v68) )
          BYTE4(v74) = 1;
        BYTE5(v74) = BYTE5(v74) || *((_QWORD *)v3 + 1050);
        if ( BYTE6(v74) || (v68 = *((_QWORD *)v3 + 556) == 0, BYTE6(v74) = 0, !v68) )
          BYTE6(v74) = 1;
        HIBYTE(v74) = HIBYTE(v74) || *((_QWORD *)v3 + 1049);
      }
    }
    TickCount = GetTickCount();
    v17 = TickCount;
    v18 = ".";
    v19 = WPP_GLOBAL_Control;
    if ( BYTE4(v74) )
    {
      v20 = TickCount;
    }
    else
    {
      v20 = 0;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x40) != 0
        && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u )
      {
        v69 = ".";
        if ( v17 >= 0x7530 )
          v69 = " - path processing will not be carried out.";
        WPP_SF_Lds(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), v15, v16, 0, v17, (__int64)v69);
        v19 = WPP_GLOBAL_Control;
      }
    }
    v21 = v17 - v20 < 0x7530;
    BYTE2(v76) = v21;
    if ( BYTE5(v74) )
    {
      v22 = v17;
    }
    else
    {
      v22 = 0;
      if ( (_UNKNOWN *)v19 != &WPP_GLOBAL_Control && (*(_BYTE *)(v19 + 28) & 0x40) != 0 && *(_BYTE *)(v19 + 25) >= 5u )
      {
        if ( v17 >= 0x7530 )
          v18 = " - path processing will not be carried out.";
        WPP_SF_Lds(*(_QWORD *)(v19 + 16), v15, v16, 1, v17, (__int64)v18);
        v21 = BYTE2(v76);
        v19 = WPP_GLOBAL_Control;
      }
    }
    BYTE3(v76) = v17 - v22 < 0x7530;
    if ( v21 )
    {
      if ( (_UNKNOWN *)v19 != &WPP_GLOBAL_Control && (*(_BYTE *)(v19 + 28) & 0x40) != 0 && *(_BYTE *)(v19 + 25) >= 5u )
        WPP_SF_(*(_QWORD *)(v19 + 16), 35, WPP_908899ae445231599b715923bce5511e_Traceguids);
      ObtainPathDataV4();
    }
    else
    {
      if ( (_UNKNOWN *)v19 == &WPP_GLOBAL_Control || (*(_BYTE *)(v19 + 28) & 0x40) == 0 || *(_BYTE *)(v19 + 25) < 5u )
      {
LABEL_23:
        if ( BYTE3(v76) )
        {
          if ( (_UNKNOWN *)v19 != &WPP_GLOBAL_Control
            && (*(_BYTE *)(v19 + 28) & 0x40) != 0
            && *(_BYTE *)(v19 + 25) >= 5u )
          {
            WPP_SF_(*(_QWORD *)(v19 + 16), 37, WPP_908899ae445231599b715923bce5511e_Traceguids);
          }
          ObtainPathDataV6();
        }
        else if ( (_UNKNOWN *)v19 != &WPP_GLOBAL_Control
               && (*(_BYTE *)(v19 + 28) & 0x40) != 0
               && *(_BYTE *)(v19 + 25) >= 5u )
        {
          WPP_SF_(*(_QWORD *)(v19 + 16), 38, WPP_908899ae445231599b715923bce5511e_Traceguids);
        }
        LODWORD(v78) = GetTickCount();
        EnterCriticalSection(&stru_18009D378);
        v23 = std::_Atomic_storage<bool,1>::load(&byte_18009B3C4);
        LeaveCriticalSection(&stru_18009D378);
        if ( v23 )
        {
          NcsiConfigData::GetCorpSitePrefixes(v25, v77);
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x40) != 0
            && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u )
          {
            WPP_SF_i(
              *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
              39,
              WPP_908899ae445231599b715923bce5511e_Traceguids,
              0x8E38E38E38E38E39uLL * ((__int64)(v77[1] - v77[0]) >> 1));
          }
        }
        NcsiNsiTable::AllocateAndGetTable(&g_nsiIpv4IfaceTableForHops, v24, &NPI_MS_IPV4_MODULEID, 24, 8, 1);
        NcsiNsiTable::AllocateAndGetTable(&g_nsiIpv6IfaceTableForHops, v26, &NPI_MS_IPV6_MODULEID, 24, 8, 1);
        v27 = g_ncsiInterfaceList;
        for ( j = xmmword_18009DCC0; v27 != j; v27 = (struct NCSI_INTERFACE_ATTRIBUTES *)((char *)v27 + 12888) )
          Ncsi::PassivePoll::PassivePollManager::PassiveProbe(
            (const struct NCSI_PASSIVE_POLL_DATA_IN *)&v76,
            (struct NCSI_PASSIVE_POLL_DATA_OUT *)&v74,
            v27);
        _InterlockedExchange(&g_unreachablePathsLastProcessedTime, v78);
        if ( (_BYTE)v74 || (LOBYTE(v76) = 1, BYTE6(v74)) )
          LOBYTE(v76) = 0;
        BYTE1(v76) = !BYTE2(v74) && !HIBYTE(v74);
        EnterCriticalSection(&stru_18009D7F8);
        v30 = BYTE1(v76);
        if ( (_BYTE)v76 )
        {
          v72 = (unsigned int)(qword_18009A1F0 + 1);
          LODWORD(qword_18009A1F0) = qword_18009A1F0 + 1;
          v31 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x40) == 0
            || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 5u )
          {
            goto LABEL_38;
          }
          WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 18, WPP_908899ae445231599b715923bce5511e_Traceguids, v72);
        }
        else
        {
          LODWORD(qword_18009A1F0) = 0;
        }
        v31 = WPP_GLOBAL_Control;
LABEL_38:
        if ( v30 )
        {
          v71 = (unsigned int)++HIDWORD(qword_18009A1F0);
          if ( (_UNKNOWN *)v31 != &WPP_GLOBAL_Control
            && (*(_BYTE *)(v31 + 28) & 0x40) != 0
            && *(_BYTE *)(v31 + 25) >= 5u )
          {
            WPP_SF_d(*(_QWORD *)(v31 + 16), 19, WPP_908899ae445231599b715923bce5511e_Traceguids, v71);
            v31 = WPP_GLOBAL_Control;
          }
        }
        else
        {
          HIDWORD(qword_18009A1F0) = 0;
        }
        if ( !byte_18009A1EF )
        {
          v70 = (unsigned int)++dword_18009A1F8;
          if ( (_UNKNOWN *)v31 != &WPP_GLOBAL_Control
            && (*(_BYTE *)(v31 + 28) & 0x40) != 0
            && *(_BYTE *)(v31 + 25) >= 5u )
          {
            WPP_SF_d(*(_QWORD *)(v31 + 16), 20, WPP_908899ae445231599b715923bce5511e_Traceguids, v70);
          }
        }
        anonymous_namespace_::PassivePollState::ReconcileRunningState(v31, v29);
        LeaveCriticalSection(&stru_18009D7F8);
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x40) != 0
          && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u )
        {
          WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 40, WPP_908899ae445231599b715923bce5511e_Traceguids);
        }
        v32 = v75 != 0;
        v33 = g_ncsiInterfaceList;
        for ( k = xmmword_18009DCC0; v33 != k; v33 = (NCSI_INTERFACE_ATTRIBUTES *)((char *)v33 + 12888) )
        {
          if ( !*((_DWORD *)v33 + 6) )
          {
            if ( NCSI_INTERFACE_ATTRIBUTES::ConsiderEndSuspectState(v33) )
              v32 = 1;
            if ( NCSI_INTERFACE_ATTRIBUTES::SuspectCorporateStateExpired(v33) )
            {
              if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x40) != 0
                && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u )
              {
                WPP_SF_i(
                  *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                  41,
                  WPP_908899ae445231599b715923bce5511e_Traceguids,
                  *(_QWORD *)v33);
              }
              NCSI_INTERFACE_ATTRIBUTES::CancelSuspectCorporateState(v33, 1);
              _InterlockedExchange((volatile __int32 *)v33 + 2913, 0);
              NcsiQueueActiveCorpProbe(v33);
            }
            v35 = GetTickCount();
            v36 = std::_Atomic_storage<enum Ncsi::Power::PowerState,4>::load(
                    &dword_18009B3B0,
                    *((unsigned int *)v33 + 1081),
                    v35);
            if ( (v38 - v37) / 0x3E8u > v36 && !*((_BYTE *)v33 + 4352) )
            {
              *((_BYTE *)v33 + 4352) = 1;
              if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x40) != 0
                && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u )
              {
                WPP_SF_i(
                  *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                  42,
                  WPP_908899ae445231599b715923bce5511e_Traceguids,
                  *(_QWORD *)v33);
              }
              v32 = 1;
            }
            v39 = GetTickCount();
            v40 = std::_Atomic_storage<enum Ncsi::Power::PowerState,4>::load(
                    &dword_18009B3B0,
                    *((unsigned int *)v33 + 2067),
                    v39);
            if ( (v42 - v41) / 0x3E8u > v40 && !*((_BYTE *)v33 + 8296) )
            {
              *((_BYTE *)v33 + 8296) = 1;
              if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x40) != 0
                && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u )
              {
                WPP_SF_i(
                  *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                  43,
                  WPP_908899ae445231599b715923bce5511e_Traceguids,
                  *(_QWORD *)v33);
              }
              v32 = 1;
            }
          }
        }
        ConsiderRetryFailedActiveProbes();
        if ( v32 && CheckIfClientPresent() )
          NcsiSignalEvent();
        std::vector<CORPSITEPREFIXV6>::_Tidy(v77);
        LeaveCriticalSection(&g_ncsiLock);
        goto LABEL_50;
      }
      WPP_SF_(*(_QWORD *)(v19 + 16), 36, WPP_908899ae445231599b715923bce5511e_Traceguids);
    }
    v19 = WPP_GLOBAL_Control;
    goto LABEL_23;
  }
}

```

## disassembly

```asm
0x18000ef10  push    rbp
0x18000ef12  push    rbx
0x18000ef13  push    rsi
0x18000ef14  push    rdi
0x18000ef15  push    r12
0x18000ef17  push    r13
0x18000ef19  push    r14
0x18000ef1b  push    r15
0x18000ef1d  lea     rbp, [rsp-1Fh]
0x18000ef22  sub     rsp, 0A8h
0x18000ef29  mov     rax, cs:__security_cookie
0x18000ef30  xor     rax, rsp
0x18000ef33  mov     [rbp+57h+var_50], rax
0x18000ef37  mov     eax, 1
0x18000ef3c  xchg    eax, cs:dword_18009DAF4
0x18000ef42  cmp     eax, 1
0x18000ef45  jz      loc_18000F37B
0x18000ef4b  mov     [rbp+57h+var_9F], 1
0x18000ef4f  call    ?load@?$_Atomic_storage@W4_NCSI_CLIENT_PRESENCE@@$03@std@@QEBA?AW4_NCSI_CLIENT_PRESENCE@@W4memory_order@2@@Z; std::_Atomic_storage<_NCSI_CLIENT_PRESENCE,4>::load(std::memory_order)
0x18000ef54  cmp     eax, 1
0x18000ef57  jnz     loc_18000F373
0x18000ef5d  lea     r13, ?g_ncsiLock@@3Vcritical_section@wil@@A; wil::critical_section g_ncsiLock
0x18000ef64  mov     rcx, r13; lpCriticalSection
0x18000ef67  call    cs:__imp_EnterCriticalSection
0x18000ef6d  mov     [rbp+57h+var_90], r13
0x18000ef71  mov     r9d, cs:dword_18009DAF0
0x18000ef78  inc     r9d
0x18000ef7b  mov     cs:dword_18009DAF0, r9d
0x18000ef82  lea     r15, WPP_GLOBAL_Control
0x18000ef89  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ef90  cmp     rcx, r15
0x18000ef93  jnz     loc_18000F756
0x18000ef99  mov     [rbp+57h+var_78], 0
0x18000efa1  lea     rcx, [rbp+57h+var_70]
0x18000efa5  call    ??0?$vector@U_Grp_t@?$_Tgt_state_t@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@V?$allocator@U_Grp_t@?$_Tgt_state_t@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@@3@@std@@QEAA@XZ; std::vector<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::_Grp_t,std::allocator<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::_Grp_t>>::vector<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::_Grp_t,std::allocator<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::_Grp_t>>(void)
0x18000efaa  mov     [rbp+57h+var_58], 0
0x18000efb2  mov     [rbp+57h+var_88], 0
0x18000efba  mov     [rbp+57h+var_80], 0
0x18000efc0  lea     r12, stru_18009D7F8
0x18000efc7  mov     rcx, r12; lpCriticalSection
0x18000efca  call    cs:__imp_EnterCriticalSection
0x18000efd0  call    _anonymous_namespace___PassivePollState__IsV4DeadForMaxPollCount
0x18000efd5  movzx   ebx, al
0x18000efd8  mov     rcx, r12; lpCriticalSection
0x18000efdb  call    cs:__imp_LeaveCriticalSection
0x18000efe1  mov     byte ptr [rbp+57h+var_78], bl
0x18000efe4  mov     rcx, r12; lpCriticalSection
0x18000efe7  call    cs:__imp_EnterCriticalSection
0x18000efed  call    _anonymous_namespace___PassivePollState__IsV6DeadForMaxPollCount
0x18000eff2  movzx   ebx, al
0x18000eff5  mov     rcx, r12; lpCriticalSection
0x18000eff8  call    cs:__imp_LeaveCriticalSection
0x18000effe  mov     byte ptr [rbp+57h+var_78+1], bl
0x18000f001  call    ?ObtainPacketCountDataFromNSI@@YAXXZ; ObtainPacketCountDataFromNSI(void)
0x18000f006  mov     rbx, cs:?g_ncsiInterfaceList@@3V?$vector@VNCSI_INTERFACE_ATTRIBUTES@@V?$allocator@VNCSI_INTERFACE_ATTRIBUTES@@@std@@@std@@A; std::vector<NCSI_INTERFACE_ATTRIBUTES> g_ncsiInterfaceList
0x18000f00d  mov     rax, qword ptr cs:xmmword_18009DCC0
0x18000f014  mov     [rbp+57h+var_98], rax
0x18000f018  cmp     rbx, rax
0x18000f01b  jz      loc_18000F11F
0x18000f021  mov     rcx, rbx; struct NCSI_INTERFACE_ATTRIBUTES *
0x18000f024  call    ?TracePerInterfaceData@@YAXAEBVNCSI_INTERFACE_ATTRIBUTES@@@Z; TracePerInterfaceData(NCSI_INTERFACE_ATTRIBUTES const &)
0x18000f029  mov     qword ptr [rbx+1160h], 0
0x18000f034  mov     qword ptr [rbx+1168h], 0
0x18000f03f  cmp     byte ptr [rbp+57h+var_78], 0
0x18000f043  jnz     loc_18000F9BE
0x18000f049  mov     r14d, cs:?g_nsiSubIfaceTableForCountv4@@3V?$TNcsiNsiTable@U_NL_SUBINTERFACE_KEY@@U_NL_SUBINTERFACE_ROD@@@@A; TNcsiNsiTable<_NL_SUBINTERFACE_KEY,_NL_SUBINTERFACE_ROD> g_nsiSubIfaceTableForCountv4
0x18000f050  mov     r15, cs:qword_18009DD98
0x18000f057  mov     r13, cs:qword_18009DDA8
0x18000f05e  xor     esi, esi
0x18000f060  test    r14d, r14d
0x18000f063  jz      short loc_18000F08D
0x18000f065  xor     edi, edi
0x18000f067  nop     word ptr [rax+rax+00000000h]
0x18000f070  mov     rax, rdi
0x18000f073  add     rax, rax
0x18000f076  mov     rax, [r15+rax*8]
0x18000f07a  cmp     [rbx], rax
0x18000f07d  jz      loc_18000F476
0x18000f083  inc     esi
0x18000f085  inc     rdi
0x18000f088  cmp     esi, r14d
0x18000f08b  jb      short loc_18000F070
0x18000f08d  lea     r15, WPP_GLOBAL_Control
0x18000f094  mov     qword ptr [rbx+20C8h], 0
0x18000f09f  mov     qword ptr [rbx+20D0h], 0
0x18000f0aa  cmp     byte ptr [rbp+57h+var_78+1], 0
0x18000f0ae  jnz     loc_18000F7BB
0x18000f0b4  mov     r14d, cs:?g_nsiSubIfaceTableForCountv6@@3V?$TNcsiNsiTable@U_NL_SUBINTERFACE_KEY@@U_NL_SUBINTERFACE_ROD@@@@A; TNcsiNsiTable<_NL_SUBINTERFACE_KEY,_NL_SUBINTERFACE_ROD> g_nsiSubIfaceTableForCountv6
0x18000f0bb  mov     r15, cs:qword_18009DDC0
0x18000f0c2  mov     r13, cs:qword_18009DDD0
0x18000f0c9  xor     esi, esi
0x18000f0cb  test    r14d, r14d
0x18000f0ce  jz      short loc_18000F0EF
0x18000f0d0  xor     edi, edi
0x18000f0d2  mov     rax, rdi
0x18000f0d5  add     rax, rax
0x18000f0d8  mov     rax, [r15+rax*8]
0x18000f0dc  cmp     [rbx], rax
0x18000f0df  jz      loc_18000F561
0x18000f0e5  inc     esi
0x18000f0e7  inc     rdi
0x18000f0ea  cmp     esi, r14d
0x18000f0ed  jb      short loc_18000F0D2
0x18000f0ef  lea     r15, WPP_GLOBAL_Control
0x18000f0f6  cmp     dword ptr [rbx+18h], 0
0x18000f0fa  jz      loc_18000F64C
0x18000f100  add     rbx, 3258h
0x18000f107  cmp     rbx, [rbp+57h+var_98]
0x18000f10b  jnz     loc_18000F021
0x18000f111  lea     r12, stru_18009D7F8
0x18000f118  lea     r13, ?g_ncsiLock@@3Vcritical_section@wil@@A; wil::critical_section g_ncsiLock
0x18000f11f  call    cs:__imp_GetTickCount
0x18000f125  mov     ebx, eax
0x18000f127  lea     r14, aPathProcessing; " - path processing will not be carried "...
0x18000f12e  lea     rsi, asc_18007F284; "."
0x18000f135  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f13c  cmp     byte ptr [rbp+57h+var_88+4], 0
0x18000f140  jz      loc_18000F812
0x18000f146  mov     edi, eax
0x18000f148  mov     eax, ebx
0x18000f14a  sub     eax, edi
0x18000f14c  cmp     eax, 7530h
0x18000f151  setb    al
0x18000f154  mov     byte ptr [rbp+57h+var_78+2], al
0x18000f157  cmp     byte ptr [rbp+57h+var_88+5], 0
0x18000f15b  jz      loc_18000F85F
0x18000f161  mov     edi, ebx
0x18000f163  sub     ebx, edi
0x18000f165  cmp     ebx, 7530h
0x18000f16b  setb    byte ptr [rbp+57h+var_78+3]
0x18000f16f  test    al, al
0x18000f171  jnz     loc_18000F784
0x18000f177  cmp     rcx, r15
0x18000f17a  jnz     loc_18000F9FF
0x18000f180  cmp     byte ptr [rbp+57h+var_78+3], 0
0x18000f184  jnz     loc_18000F7FF
0x18000f18a  cmp     rcx, r15
0x18000f18d  jz      short loc_18000F1B0
0x18000f18f  test    byte ptr [rcx+1Ch], 40h
0x18000f193  jz      short loc_18000F1B0
0x18000f195  cmp     byte ptr [rcx+19h], 5
0x18000f199  jb      short loc_18000F1B0
0x18000f19b  mov     edx, 26h ; '&'
0x18000f1a0  lea     r8, WPP_908899ae445231599b715923bce5511e_Traceguids
0x18000f1a7  mov     rcx, [rcx+10h]
0x18000f1ab  call    WPP_SF_
0x18000f1b0  call    cs:__imp_GetTickCount
0x18000f1b6  mov     dword ptr [rbp+57h+var_58], eax
0x18000f1b9  lea     rcx, stru_18009D378; lpCriticalSection
0x18000f1c0  call    cs:__imp_EnterCriticalSection
0x18000f1c6  lea     rcx, byte_18009B3C4
0x18000f1cd  call    ?load@?$_Atomic_storage@_N$00@std@@QEBA_NW4memory_order@2@@Z; std::_Atomic_storage<bool,1>::load(std::memory_order)
0x18000f1d2  movzx   ebx, al
0x18000f1d5  lea     rcx, stru_18009D378; lpCriticalSection
0x18000f1dc  call    cs:__imp_LeaveCriticalSection
0x18000f1e2  test    bl, bl
0x18000f1e4  jnz     loc_18000FA2D
0x18000f1ea  mov     dword ptr [rsp+0E0h+var_B8], 1
0x18000f1f2  mov     dword ptr [rsp+0E0h+var_C0], 8
0x18000f1fa  mov     r9d, 18h
0x18000f200  lea     r8, NPI_MS_IPV4_MODULEID
0x18000f207  lea     rcx, ?g_nsiIpv4IfaceTableForHops@@3V?$TNcsiNsiTable@U_NL_INTERFACE_KEY@@U_NL_INTERFACE_HOP_ROD@@@@A; TNcsiNsiTable<_NL_INTERFACE_KEY,_NL_INTERFACE_HOP_ROD> g_nsiIpv4IfaceTableForHops
0x18000f20e  call    ?AllocateAndGetTable@NcsiNsiTable@@QEAAKW4_NSI_STORE@@PEBU_NPI_MODULEID@@KKKE@Z; NcsiNsiTable::AllocateAndGetTable(_NSI_STORE,_NPI_MODULEID const *,ulong,ulong,ulong,uchar)
0x18000f213  mov     dword ptr [rsp+0E0h+var_B8], 1
0x18000f21b  mov     dword ptr [rsp+0E0h+var_C0], 8
0x18000f223  mov     r9d, 18h
0x18000f229  lea     r8, NPI_MS_IPV6_MODULEID
0x18000f230  lea     rcx, ?g_nsiIpv6IfaceTableForHops@@3V?$TNcsiNsiTable@U_NL_INTERFACE_KEY@@U_NL_INTERFACE_HOP_ROD@@@@A; TNcsiNsiTable<_NL_INTERFACE_KEY,_NL_INTERFACE_HOP_ROD> g_nsiIpv6IfaceTableForHops
0x18000f237  call    ?AllocateAndGetTable@NcsiNsiTable@@QEAAKW4_NSI_STORE@@PEBU_NPI_MODULEID@@KKKE@Z; NcsiNsiTable::AllocateAndGetTable(_NSI_STORE,_NPI_MODULEID const *,ulong,ulong,ulong,uchar)
0x18000f23c  mov     rbx, cs:?g_ncsiInterfaceList@@3V?$vector@VNCSI_INTERFACE_ATTRIBUTES@@V?$allocator@VNCSI_INTERFACE_ATTRIBUTES@@@std@@@std@@A; std::vector<NCSI_INTERFACE_ATTRIBUTES> g_ncsiInterfaceList
0x18000f243  mov     rdi, qword ptr cs:xmmword_18009DCC0
0x18000f24a  cmp     rbx, rdi
0x18000f24d  jz      short loc_18000F26C
0x18000f24f  nop
0x18000f250  mov     r8, rbx; struct NCSI_INTERFACE_ATTRIBUTES *
0x18000f253  lea     rdx, [rbp+57h+var_88]; struct NCSI_PASSIVE_POLL_DATA_OUT *
0x18000f257  lea     rcx, [rbp+57h+var_78]; struct NCSI_PASSIVE_POLL_DATA_IN *
0x18000f25b  call    ?PassiveProbe@PassivePollManager@PassivePoll@Ncsi@@SAXAEBUNCSI_PASSIVE_POLL_DATA_IN@@AEAUNCSI_PASSIVE_POLL_DATA_OUT@@PEAVNCSI_INTERFACE_ATTRIBUTES@@@Z; Ncsi::PassivePoll::PassivePollManager::PassiveProbe(NCSI_PASSIVE_POLL_DATA_IN const &,NCSI_PASSIVE_POLL_DATA_OUT &,NCSI_INTERFACE_ATTRIBUTES *)
0x18000f260  add     rbx, 3258h
0x18000f267  cmp     rbx, rdi
0x18000f26a  jnz     short loc_18000F250
0x18000f26c  mov     eax, dword ptr [rbp+57h+var_58]
0x18000f26f  xchg    eax, cs:?g_unreachablePathsLastProcessedTime@@3U?$atomic@K@std@@A; std::atomic<ulong> g_unreachablePathsLastProcessedTime
0x18000f275  cmp     byte ptr [rbp+57h+var_88], 0
0x18000f279  jz      loc_18000FA8D
0x18000f27f  mov     byte ptr [rbp+57h+var_78], 0
0x18000f283  cmp     byte ptr [rbp+57h+var_88+2], 0
0x18000f287  jz      loc_18000F926
0x18000f28d  mov     byte ptr [rbp+57h+var_78+1], 0
0x18000f291  mov     rcx, r12; lpCriticalSection
0x18000f294  call    cs:__imp_EnterCriticalSection
0x18000f29a  mov     [rbp+57h+var_98], r12
0x18000f29e  movzx   ebx, byte ptr [rbp+57h+var_78+1]
0x18000f2a2  cmp     byte ptr [rbp+57h+var_78], 0
0x18000f2a6  jnz     loc_18000FAA0
0x18000f2ac  mov     dword ptr cs:qword_18009A1F0, 0
0x18000f2b6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f2bd  test    bl, bl
0x18000f2bf  jnz     loc_18000F958
0x18000f2c5  mov     dword ptr cs:qword_18009A1F0+4, 0
0x18000f2cf  cmp     cs:byte_18009A1EF, 0
0x18000f2d6  jz      loc_18000F8DE
0x18000f2dc  call    _anonymous_namespace___PassivePollState__ReconcileRunningState
0x18000f2e1  nop
0x18000f2e2  mov     rcx, r12; lpCriticalSection
0x18000f2e5  call    cs:__imp_LeaveCriticalSection
0x18000f2eb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f2f2  cmp     rcx, r15
0x18000f2f5  jz      short loc_18000F318
0x18000f2f7  test    byte ptr [rcx+1Ch], 40h
0x18000f2fb  jz      short loc_18000F318
0x18000f2fd  cmp     byte ptr [rcx+19h], 5
0x18000f301  jb      short loc_18000F318
0x18000f303  mov     edx, 28h ; '('
0x18000f308  lea     r8, WPP_908899ae445231599b715923bce5511e_Traceguids
0x18000f30f  mov     rcx, [rcx+10h]
0x18000f313  call    WPP_SF_
0x18000f318  cmp     byte ptr [rbp+57h+var_80], 0
0x18000f31c  jnz     short loc_18000F329
0x18000f31e  cmp     byte ptr [rbp+57h+var_80+1], 0
0x18000f322  jnz     short loc_18000F329
0x18000f324  xor     sil, sil
0x18000f327  jmp     short loc_18000F32C
0x18000f329  mov     sil, 1
0x18000f32c  mov     rbx, cs:?g_ncsiInterfaceList@@3V?$vector@VNCSI_INTERFACE_ATTRIBUTES@@V?$allocator@VNCSI_INTERFACE_ATTRIBUTES@@@std@@@std@@A; std::vector<NCSI_INTERFACE_ATTRIBUTES> g_ncsiInterfaceList
0x18000f333  mov     rdi, qword ptr cs:xmmword_18009DCC0
0x18000f33a  cmp     rbx, rdi
0x18000f33d  jz      short loc_18000F351
0x18000f33f  cmp     dword ptr [rbx+18h], 0
0x18000f343  jz      short loc_18000F39B
0x18000f345  add     rbx, 3258h
0x18000f34c  cmp     rbx, rdi
0x18000f34f  jnz     short loc_18000F33F
0x18000f351  call    ?ConsiderRetryFailedActiveProbes@@YAXXZ; ConsiderRetryFailedActiveProbes(void)
0x18000f356  test    sil, sil
0x18000f359  jnz     loc_18000FB6F
0x18000f35f  lea     rcx, [rbp+57h+var_70]
0x18000f363  call    ?_Tidy@?$vector@UCORPSITEPREFIXV6@@V?$allocator@UCORPSITEPREFIXV6@@@std@@@std@@AEAAXXZ; std::vector<CORPSITEPREFIXV6>::_Tidy(void)
0x18000f368  nop
0x18000f369  mov     rcx, r13; lpCriticalSection
0x18000f36c  call    cs:__imp_LeaveCriticalSection
0x18000f372  nop
0x18000f373  xor     eax, eax
0x18000f375  xchg    eax, cs:dword_18009DAF4
0x18000f37b  mov     rcx, [rbp+57h+var_50]
0x18000f37f  xor     rcx, rsp; StackCookie
0x18000f382  call    __security_check_cookie
0x18000f387  add     rsp, 0A8h
0x18000f38e  pop     r15
0x18000f390  pop     r14
0x18000f392  pop     r13
0x18000f394  pop     r12
0x18000f396  pop     rdi
0x18000f397  pop     rsi
0x18000f398  pop     rbx
0x18000f399  pop     rbp
0x18000f39a  retn
0x18000f39b  mov     rcx, rbx; this
0x18000f39e  call    ?ConsiderEndSuspectState@NCSI_INTERFACE_ATTRIBUTES@@QEAA_NXZ; NCSI_INTERFACE_ATTRIBUTES::ConsiderEndSuspectState(void)
0x18000f3a3  test    al, al
0x18000f3a5  jnz     loc_18000F9A7
0x18000f3ab  mov     rcx, rbx; this
0x18000f3ae  call    ?SuspectCorporateStateExpired@NCSI_INTERFACE_ATTRIBUTES@@QEAA_NXZ; NCSI_INTERFACE_ATTRIBUTES::SuspectCorporateStateExpired(void)
0x18000f3b3  test    al, al
0x18000f3b5  jnz     loc_18000FAEF
0x18000f3bb  call    cs:__imp_GetTickCount
0x18000f3c1  mov     r8d, eax
0x18000f3c4  mov     edx, [rbx+10E4h]
0x18000f3ca  lea     rcx, dword_18009B3B0
0x18000f3d1  call    ?load@?$_Atomic_storage@W4PowerState@Power@Ncsi@@$03@std@@QEBA?AW4PowerState@Power@Ncsi@@W4memory_order@2@@Z; std::_Atomic_storage<Ncsi::Power::PowerState,4>::load(std::memory_order)
0x18000f3d6  mov     ecx, eax
0x18000f3d8  sub     r8d, edx
0x18000f3db  mov     eax, 10624DD3h
0x18000f3e0  mul     r8d
0x18000f3e3  shr     edx, 6
0x18000f3e6  cmp     edx, ecx
0x18000f3e8  jbe     short loc_18000F3F7
0x18000f3ea  cmp     byte ptr [rbx+1100h], 0
0x18000f3f1  jz      loc_18000F939
0x18000f3f7  call    cs:__imp_GetTickCount
0x18000f3fd  mov     r8d, eax
0x18000f400  mov     edx, [rbx+204Ch]
0x18000f406  lea     rcx, dword_18009B3B0
0x18000f40d  call    ?load@?$_Atomic_storage@W4PowerState@Power@Ncsi@@$03@std@@QEBA?AW4PowerState@Power@Ncsi@@W4memory_order@2@@Z; std::_Atomic_storage<Ncsi::Power::PowerState,4>::load(std::memory_order)
0x18000f412  mov     ecx, eax
0x18000f414  sub     r8d, edx
0x18000f417  mov     eax, 10624DD3h
0x18000f41c  mul     r8d
0x18000f41f  shr     edx, 6
0x18000f422  cmp     edx, ecx
0x18000f424  jbe     loc_18000F345
0x18000f42a  cmp     byte ptr [rbx+2068h], 0
0x18000f431  jnz     loc_18000F345
0x18000f437  mov     byte ptr [rbx+2068h], 1
0x18000f43e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f445  cmp     rcx, r15
0x18000f448  jz      short loc_18000F46E
0x18000f44a  test    byte ptr [rcx+1Ch], 40h
0x18000f44e  jz      short loc_18000F46E
0x18000f450  cmp     byte ptr [rcx+19h], 5
  ... truncated ...
```
