# NcsiConfigData::Dump(void)

- ea: `0x18001450c`
- end: `0x180015009`
- name: `?Dump@NcsiConfigData@@QEAAXXZ`
- size: `2813`
- prototype: `void __fastcall(NcsiConfigData *__hidden this)`
- caller_count: `4`
- callee_count: `28`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001572c`
- `0x180052920`
- `0x1800529ac`
- `0x1800537dc`

## callees

- `0x18000c5f0`
- `0x18000de10`
- `0x18000e36c`
- `0x180010200`
- `0x180011a58`
- `0x180013e48`
- `0x18001450c`
- `0x1800150c0`
- `0x1800150f8`
- `0x180015614`
- `0x180017e68`
- `0x180023304`
- `0x18002a754`
- `0x18002aa70`
- `0x18002cd80`
- `0x18002db14`
- `0x18002e788`
- `0x18003f298`
- `0x18003f2d8`
- `0x180041774`
- `0x180041dd8`
- `0x180041fa4`
- `0x180047240`
- `0x180047f60`
- `0x180047f78`
- `0x180051ab8`
- `0x180053354`
- `0x1800533a4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800149a8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014a5c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014abf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014b37`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014c54`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014d69`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800149a8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014a5c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014abf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014b37`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014c54`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014d69`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001492e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800149e7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014a9b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014b18`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014c35`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014d43`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001492e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800149e7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014a9b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014b18`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014c35`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014d43`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall NcsiConfigData::Dump(NcsiConfigData *this, __int64 a2, __int64 a3)
{
  __int64 v3; // rax
  const char *v4; // rsi
  int v5; // eax
  const char *v6; // r9
  bool active; // al
  const char *v8; // r9
  unsigned int v9; // eax
  unsigned int v10; // eax
  unsigned int v11; // eax
  bool IsPassivePollingDisabled; // al
  const char *v13; // r9
  unsigned int v14; // eax
  bool DoesPassivePollRequireActiveSession; // al
  const char *v16; // r9
  unsigned int v17; // eax
  unsigned int v18; // eax
  unsigned int v19; // eax
  unsigned int v20; // eax
  union _SOCKADDR_INET *InternetDestinationAddress; // rbx
  __int64 v22; // rcx
  int v23; // eax
  _OWORD *v24; // rcx
  __int64 *v25; // rax
  __int64 v26; // rdx
  int v27; // r8d
  _OWORD *v28; // rcx
  int *v29; // rax
  __int64 v30; // rdx
  int v31; // r8d
  NcsiConfigData *v32; // rcx
  NcsiConfigData *v33; // rcx
  int v34; // r8d
  __int64 v35; // rcx
  __int64 v36; // rcx
  __int64 v37; // rdx
  __int64 v38; // r8
  __int64 v39; // rbx
  __int64 v40; // rdi
  __int64 v41; // rcx
  __int64 v42; // rdx
  __int64 v43; // r8
  __int64 v44; // rcx
  bool v45; // al
  const char *v46; // r9
  unsigned int v47; // eax
  unsigned int v48; // eax
  unsigned int v49; // eax
  __int64 v50; // rax
  int v51; // ebx
  NcsiConfigData *v52; // rcx
  unsigned __int16 *v53; // rax
  unsigned int v54; // eax
  _BYTE v55[32]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v56[32]; // [rsp+68h] [rbp-98h] BYREF
  __int128 v57; // [rsp+88h] [rbp-78h] BYREF
  __int64 v58; // [rsp+98h] [rbp-68h]
  _BYTE v59[520]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v60[40]; // [rsp+2A8h] [rbp+1A8h] BYREF
  _BYTE v61[520]; // [rsp+2D0h] [rbp+1D0h] BYREF
  _BYTE v62[520]; // [rsp+4D8h] [rbp+3D8h] BYREF
  _BYTE v63[520]; // [rsp+6E0h] [rbp+5E0h] BYREF
  __int16 v64; // [rsp+8E8h] [rbp+7E8h]
  int v65; // [rsp+8F0h] [rbp+7F0h] BYREF
  _BYTE v66[524]; // [rsp+8F4h] [rbp+7F4h] BYREF

  v3 = WPP_GLOBAL_Control;
  if ( *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u )
  {
    v4 = "true";
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0 )
      {
        WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 82, &WPP_5540ffa188b23fc0b8d03d8186783076_Traceguids);
        v3 = WPP_GLOBAL_Control;
      }
      if ( (_UNKNOWN *)v3 != &WPP_GLOBAL_Control )
      {
        if ( (*(_BYTE *)(v3 + 28) & 0x10) != 0 && *(_BYTE *)(v3 + 25) >= 4u )
        {
          v5 = std::_Atomic_storage<enum Ncsi::Power::PowerState,4>::load(&g_ncsiConfigData, a2, a3);
          v6 = "true";
          if ( !v5 )
            v6 = "false";
          WPP_SF_s(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 83, &WPP_5540ffa188b23fc0b8d03d8186783076_Traceguids, v6);
          v3 = WPP_GLOBAL_Control;
        }
        if ( (_UNKNOWN *)v3 != &WPP_GLOBAL_Control )
        {
          if ( (*(_BYTE *)(v3 + 28) & 0x10) != 0 && *(_BYTE *)(v3 + 25) >= 4u )
          {
            active = NcsiConfigData::ActiveProbesGPDisabled(this);
            v8 = "true";
            if ( !active )
              v8 = "false";
            WPP_SF_s(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 84, &WPP_5540ffa188b23fc0b8d03d8186783076_Traceguids, v8);
            v3 = WPP_GLOBAL_Control;
          }
          if ( (_UNKNOWN *)v3 != &WPP_GLOBAL_Control )
          {
            if ( (*(_BYTE *)(v3 + 28) & 0x10) != 0 && *(_BYTE *)(v3 + 25) >= 4u )
            {
              v9 = std::_Atomic_storage<enum Ncsi::Power::PowerState,4>::load(&dword_18009B3A4, a2, a3);
              WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 85, &WPP_5540ffa188b23fc0b8d03d8186783076_Traceguids, v9);
              v3 = WPP_GLOBAL_Control;
            }
            if ( (_UNKNOWN *)v3 != &WPP_GLOBAL_Control )
            {
              if ( (*(_BYTE *)(v3 + 28) & 0x10) != 0 && *(_BYTE *)(v3 + 25) >= 4u )
              {
                v10 = std::_Atomic_storage<enum Ncsi::Power::PowerState,4>::load(&dword_18009B3B4, a2, a3);
                WPP_SF_d(
                  *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                  86,
                  &WPP_5540ffa188b23fc0b8d03d8186783076_Traceguids,
                  v10);
                v3 = WPP_GLOBAL_Control;
              }
              if ( (_UNKNOWN *)v3 != &WPP_GLOBAL_Control )
              {
                if ( (*(_BYTE *)(v3 + 28) & 0x10) != 0 && *(_BYTE *)(v3 + 25) >= 4u )
                {
                  v11 = std::_Atomic_storage<enum Ncsi::Power::PowerState,4>::load(&dword_18009B3BC, a2, a3);
                  WPP_SF_d(
                    *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                    87,
                    &WPP_5540ffa188b23fc0b8d03d8186783076_Traceguids,
                    v11);
                  v3 = WPP_GLOBAL_Control;
                }
                if ( (_UNKNOWN *)v3 != &WPP_GLOBAL_Control )
                {
                  if ( (*(_BYTE *)(v3 + 28) & 0x10) != 0 && *(_BYTE *)(v3 + 25) >= 4u )
                  {
                    IsPassivePollingDisabled = NcsiConfigData::IsPassivePollingDisabled(this);
                    v13 = "true";
                    if ( !IsPassivePollingDisabled )
                      v13 = "false";
                    WPP_SF_s(
                      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                      88,
                      &WPP_5540ffa188b23fc0b8d03d8186783076_Traceguids,
                      v13);
                    v3 = WPP_GLOBAL_Control;
                  }
                  if ( (_UNKNOWN *)v3 != &WPP_GLOBAL_Control )
                  {
                    if ( (*(_BYTE *)(v3 + 28) & 0x10) != 0 && *(_BYTE *)(v3 + 25) >= 4u )
                    {
                      v14 = std::_Atomic_storage<enum Ncsi::Power::PowerState,4>::load(&dword_18009B3A8, a2, a3);
                      WPP_SF_d(
                        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                        89,
                        &WPP_5540ffa188b23fc0b8d03d8186783076_Traceguids,
                        v14);
                      v3 = WPP_GLOBAL_Control;
                    }
                    if ( (_UNKNOWN *)v3 != &WPP_GLOBAL_Control )
                    {
                      if ( (*(_BYTE *)(v3 + 28) & 0x10) != 0 && *(_BYTE *)(v3 + 25) >= 4u )
                      {
                        DoesPassivePollRequireActiveSession = NcsiConfigData::DoesPassivePollRequireActiveSession(this);
                        v16 = "true";
                        if ( !DoesPassivePollRequireActiveSession )
                          v16 = "false";
                        WPP_SF_s(
                          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                          90,
                          &WPP_5540ffa188b23fc0b8d03d8186783076_Traceguids,
                          v16);
                        v3 = WPP_GLOBAL_Control;
                      }
                      if ( (_UNKNOWN *)v3 != &WPP_GLOBAL_Control )
                      {
                        if ( (*(_BYTE *)(v3 + 28) & 0x10) != 0 && *(_BYTE *)(v3 + 25) >= 4u )
                        {
                          v17 = NcsiConfigData::MaxDeadNetPollCount(this);
                          WPP_SF_d(
                            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                            91,
                            &WPP_5540ffa188b23fc0b8d03d8186783076_Traceguids,
                            v17);
                          v3 = WPP_GLOBAL_Control;
                        }
                        if ( (_UNKNOWN *)v3 != &WPP_GLOBAL_Control )
                        {
                          if ( (*(_BYTE *)(v3 + 28) & 0x10) != 0 && *(_BYTE *)(v3 + 25) >= 4u )
                          {
                            v18 = NcsiConfigData::MaxDeadUserPollCount(this);
                            WPP_SF_d(
                              *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                              92,
                              &WPP_5540ffa188b23fc0b8d03d8186783076_Traceguids,
                              v18);
                            v3 = WPP_GLOBAL_Control;
                          }
                          if ( (_UNKNOWN *)v3 != &WPP_GLOBAL_Control )
                          {
                            if ( (*(_BYTE *)(v3 + 28) & 0x10) != 0 && *(_BYTE *)(v3 + 25) >= 4u )
                            {
                              v19 = std::_Atomic_storage<enum Ncsi::Power::PowerState,4>::load(&dword_18009B3B0, a2, a3);
                              WPP_SF_d(
                                *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                                93,
                                &WPP_5540ffa188b23fc0b8d03d8186783076_Traceguids,
                                v19);
                              v3 = WPP_GLOBAL_Control;
                            }
                            if ( (_UNKNOWN *)v3 != &WPP_GLOBAL_Control )
                            {
                              if ( (*(_BYTE *)(v3 + 28) & 0x10) != 0 && *(_BYTE *)(v3 + 25) >= 4u )
                              {
                                v20 = std::_Atomic_storage<enum Ncsi::Power::PowerState,4>::load(
                                        &dword_18009B400,
                                        a2,
                                        a3);
                                WPP_SF_d(
                                  *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                                  94,
                                  &WPP_5540ffa188b23fc0b8d03d8186783076_Traceguids,
                                  v20);
                                v3 = WPP_GLOBAL_Control;
                              }
                              if ( (_UNKNOWN *)v3 != &WPP_GLOBAL_Control
                                && (*(_BYTE *)(v3 + 28) & 0x10) != 0
                                && *(_BYTE *)(v3 + 25) >= 4u )
                              {
                                InternetDestinationAddress = (union _SOCKADDR_INET *)NcsiConfigData::GetInternetDestinationAddress(
                                                                                       this,
                                                                                       v55,
                                                                                       1);
                                v23 = NcsiConfigData::GetInternetDestinationAddress(v22, v56, 0);
                                WPP_SF__SOCKADDRINET__SOCKADDRINET_(
                                  *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                                  95,
                                  (int)&WPP_5540ffa188b23fc0b8d03d8186783076_Traceguids,
                                  v23,
                                  InternetDestinationAddress);
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
    memset_0(v59, 0, 0x224u);
    memset_0(v61, 0, 0x61Au);
    EnterCriticalSection(&stru_18009D378);
    v24 = v59;
    v25 = qword_18009B460;
    v26 = 4;
    do
    {
      *v24 = *(_OWORD *)v25;
      v24[1] = *((_OWORD *)v25 + 1);
      v24[2] = *((_OWORD *)v25 + 2);
      v24[3] = *((_OWORD *)v25 + 3);
      v24[4] = *((_OWORD *)v25 + 4);
      v24[5] = *((_OWORD *)v25 + 5);
      v24[6] = *((_OWORD *)v25 + 6);
      v24[7] = *((_OWORD *)v25 + 7);
      v24 += 8;
      v25 += 16;
      --v26;
    }
    while ( v26 );
    *v24 = *(_OWORD *)v25;
    v24[1] = *((_OWORD *)v25 + 1);
    *((_DWORD *)v24 + 8) = *((_DWORD *)v25 + 8);
    LeaveCriticalSection(&stru_18009D378);
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u )
    {
      WPP_SF_S_SOCKADDRINET_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 96, v27, (unsigned int)v59, (__int64)v60);
    }
    EnterCriticalSection(&stru_18009D378);
    v28 = v59;
    v29 = &dword_18009B684;
    v30 = 4;
    do
    {
      *v28 = *(_OWORD *)v29;
      v28[1] = *((_OWORD *)v29 + 1);
      v28[2] = *((_OWORD *)v29 + 2);
      v28[3] = *((_OWORD *)v29 + 3);
      v28[4] = *((_OWORD *)v29 + 4);
      v28[5] = *((_OWORD *)v29 + 5);
      v28[6] = *((_OWORD *)v29 + 6);
      v28[7] = *((_OWORD *)v29 + 7);
      v28 += 8;
      v29 += 32;
      --v30;
    }
    while ( v30 );
    *v28 = *(_OWORD *)v29;
    v28[1] = *((_OWORD *)v29 + 1);
    *((_DWORD *)v28 + 8) = v29[8];
    LeaveCriticalSection(&stru_18009D378);
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u )
    {
      WPP_SF_S_SOCKADDRINET_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 97, v31, (unsigned int)v59, (__int64)v60);
    }
    EnterCriticalSection(&stru_18009D378);
    memcpy_0(v61, qword_18009B8A8, 0x61Au);
    LeaveCriticalSection(&stru_18009D378);
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u )
    {
      WPP_SF_SSds(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        98,
        (unsigned int)v63,
        (unsigned int)v61,
        (__int64)v62,
        v64,
        (__int64)v63);
    }
    EnterCriticalSection(&stru_18009D378);
    memcpy_0(v61, word_18009BEC2, 0x61Au);
    LeaveCriticalSection(&stru_18009D378);
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u )
    {
      WPP_SF_SSds(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        99,
        (unsigned int)v63,
        (unsigned int)v61,
        (__int64)v62,
        v64,
        (__int64)v63);
    }
    v65 = 0;
    memset_0(v66, 0, 0x208u);
    NcsiConfigData::GetManualProxies(v32, (struct NCSI_MANUAL_PROXIES *)&v65);
    v33 = (NcsiConfigData *)WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u )
    {
      WPP_SF_dS(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        100,
        (unsigned int)&WPP_5540ffa188b23fc0b8d03d8186783076_Traceguids,
        v65,
        (__int64)v66);
    }
    NcsiConfigData::GetCorpDnsProbeData(v33, (struct NCSI_DNS_PROBE_CONFIG *)v59);
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u )
    {
      WPP_SF_S_SOCKADDRINET_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 101, v34, (unsigned int)v59, (__int64)v60);
    }
    EnterCriticalSection(&stru_18009D378);
    memcpy_0(v61, qword_18009C700, 0x61Au);
    LeaveCriticalSection(&stru_18009D378);
    v35 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0 && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u )
      {
        WPP_SF_SSds(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          102,
          (unsigned int)v63,
          (unsigned int)v61,
          (__int64)v62,
          v64,
          (__int64)v63);
        v35 = WPP_GLOBAL_Control;
      }
      if ( (_UNKNOWN *)v35 != &WPP_GLOBAL_Control && (*(_BYTE *)(v35 + 28) & 0x10) != 0 && *(_BYTE *)(v35 + 25) >= 4u )
        WPP_SF_(*(_QWORD *)(v35 + 16), 103, &WPP_5540ffa188b23fc0b8d03d8186783076_Traceguids);
    }
    v57 = 0;
    v58 = 0;
    std::vector<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::_Grp_t,std::allocator<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::_Grp_t>>::vector<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::_Grp_t,std::allocator<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::_Grp_t>>(&v57);
    NcsiConfigData::GetCorpSitePrefixes(v36, &v57);
    v40 = *((_QWORD *)&v57 + 1);
    v39 = v57;
    if ( (_QWORD)v57 != *((_QWORD *)&v57 + 1) )
    {
      v41 = WPP_GLOBAL_Control;
      do
      {
        if ( (_UNKNOWN *)v41 != &WPP_GLOBAL_Control && (*(_BYTE *)(v41 + 28) & 0x10) != 0 && *(_BYTE *)(v41 + 25) >= 4u )
        {
          WPP_SF__IPV6_d(*(_QWORD *)(v41 + 16), v37, v38, v39, *(unsigned __int8 *)(v39 + 16));
          v41 = WPP_GLOBAL_Control;
        }
        v39 += 18;
      }
      while ( v39 != v40 );
    }
    EnterCriticalSection(&stru_18009D378);
    memcpy_0(v61, qword_18009CD38, 0x61Au);
    LeaveCriticalSection(&stru_18009D378);
    v44 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0 && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u )
      {
        WPP_SF_SSds(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          105,
          (unsigned int)v63,
          (unsigned int)v61,
          (__int64)v62,
          v64,
          (__int64)v63);
        v44 = WPP_GLOBAL_Control;
      }
      if ( (_UNKNOWN *)v44 != &WPP_GLOBAL_Control )
      {
        if ( (*(_BYTE *)(v44 + 28) & 0x10) != 0 && *(_BYTE *)(v44 + 25) >= 4u )
        {
          v45 = NcsiConfigData::CorpProbeEnabled((NcsiConfigData *)v44);
          v46 = "true";
          if ( !v45 )
            v46 = "false";
          WPP_SF_s(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 106, &WPP_5540ffa188b23fc0b8d03d8186783076_Traceguids, v46);
          v44 = WPP_GLOBAL_Control;
        }
        if ( (_UNKNOWN *)v44 != &WPP_GLOBAL_Control )
        {
          if ( (*(_BYTE *)(v44 + 28) & 0x10) != 0 && *(_BYTE *)(v44 + 25) >= 4u )
          {
            if ( !NcsiConfigData::CorpLocationProbeEnabled((NcsiConfigData *)v44) )
              v4 = "false";
            WPP_SF_s(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 107, &WPP_5540ffa188b23fc0b8d03d8186783076_Traceguids, v4);
            v44 = WPP_GLOBAL_Control;
          }
          if ( (_UNKNOWN *)v44 != &WPP_GLOBAL_Control )
          {
            if ( (*(_BYTE *)(v44 + 28) & 0x10) != 0 && *(_BYTE *)(v44 + 25) >= 4u )
            {
              v47 = std::_Atomic_storage<enum Ncsi::Power::PowerState,4>::load(&dword_18009B3CC, v42, v43);
              WPP_SF_d(
                *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                108,
                &WPP_5540ffa188b23fc0b8d03d8186783076_Traceguids,
                v47);
              v44 = WPP_GLOBAL_Control;
            }
            if ( (_UNKNOWN *)v44 != &WPP_GLOBAL_Control )
            {
              if ( (*(_BYTE *)(v44 + 28) & 0x10) != 0 && *(_BYTE *)(v44 + 25) >= 4u )
              {
                v48 = std::_Atomic_storage<enum Ncsi::Power::PowerState,4>::load(&dword_18009B3D0, v42, v43);
                WPP_SF_d(
                  *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                  109,
                  &WPP_5540ffa188b23fc0b8d03d8186783076_Traceguids,
                  v48);
                v44 = WPP_GLOBAL_Control;
              }
              if ( (_UNKNOWN *)v44 != &WPP_GLOBAL_Control )
              {
                if ( (*(_BYTE *)(v44 + 28) & 0x10) != 0 && *(_BYTE *)(v44 + 25) >= 4u )
                {
                  v49 = std::_Atomic_storage<enum Ncsi::Power::PowerState,4>::load(&dword_18009B3D4, v42, v43);
                  WPP_SF_d(
                    *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                    110,
                    &WPP_5540ffa188b23fc0b8d03d8186783076_Traceguids,
                    v49);
                  v44 = WPP_GLOBAL_Control;
                }
                if ( (_UNKNOWN *)v44 != &WPP_GLOBAL_Control )
                {
                  if ( (*(_BYTE *)(v44 + 28) & 0x10) != 0 && *(_BYTE *)(v44 + 25) >= 4u )
                  {
                    LODWORD(v50) = NcsiConfigData::GetCorpLocationTcpRtoParameters((NcsiConfigData *)v44);
                    v51 = *(unsigned __int8 *)(v50 + 2);
                    LODWORD(v53) = NcsiConfigData::GetCorpLocationTcpRtoParameters(v52);
                    WPP_SF_dd(
                      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                      111,
                      &WPP_5540ffa188b23fc0b8d03d8186783076_Traceguids,
                      *v53,
                      v51);
                    v44 = WPP_GLOBAL_Control;
                  }
                  if ( (_UNKNOWN *)v44 != &WPP_GLOBAL_Control )
                  {
                    if ( (*(_BYTE *)(v44 + 28) & 0x10) != 0 && *(_BYTE *)(v44 + 25) >= 4u )
                    {
                      v54 = std::_Atomic_storage<enum Ncsi::Power::PowerState,4>::load(&dword_18009B3E4, v42, v43);
                      WPP_SF_d(
                        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                        112,
                        &WPP_5540ffa188b23fc0b8d03d8186783076_Traceguids,
                        v54);
                      v44 = WPP_GLOBAL_Control;
                    }
                    if ( (_UNKNOWN *)v44 != &WPP_GLOBAL_Control
                      && (*(_BYTE *)(v44 + 28) & 0x10) != 0
                      && *(_BYTE *)(v44 + 25) >= 4u )
                    {
                      WPP_SF_(*(_QWORD *)(v44 + 16), 113, &WPP_5540ffa188b23fc0b8d03d8186783076_Traceguids);
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
    std::vector<CORPSITEPREFIXV6>::_Tidy(&v57);
  }
}

```

## disassembly

```asm
0x18001450c  push    rbp
0x18001450e  push    rbx
0x18001450f  push    rsi
0x180014510  push    rdi
0x180014511  push    r12
0x180014513  push    r13
0x180014515  push    r14
0x180014517  push    r15
0x180014519  lea     rbp, [rsp-0A18h]
0x180014521  sub     rsp, 0B18h
0x180014528  mov     rax, cs:__security_cookie
0x18001452f  xor     rax, rsp
0x180014532  mov     [rbp+0A50h+var_50], rax
0x180014539  mov     r14d, 4
0x18001453f  mov     rax, cs:WPP_GLOBAL_Control
0x180014546  cmp     [rax+19h], r14b
0x18001454a  jb      loc_180014FE6
0x180014550  lea     r12, WPP_GLOBAL_Control
0x180014557  lea     rbx, aFalse; "false"
0x18001455e  lea     rsi, aTrue_0; "true"
0x180014565  mov     r15b, 10h
0x180014568  lea     r13, WPP_5540ffa188b23fc0b8d03d8186783076_Traceguids
0x18001456f  cmp     rax, r12
0x180014572  jz      loc_1800148FF
0x180014578  test    [rax+1Ch], r15b
0x18001457c  jz      short loc_180014595
0x18001457e  lea     edx, [r14+4Eh]
0x180014582  mov     r8, r13
0x180014585  mov     rcx, [rax+10h]
0x180014589  call    WPP_SF_
0x18001458e  mov     rax, cs:WPP_GLOBAL_Control
0x180014595  cmp     rax, r12
0x180014598  jz      loc_1800148FF
0x18001459e  test    [rax+1Ch], r15b
0x1800145a2  jz      short loc_1800145DE
0x1800145a4  cmp     [rax+19h], r14b
0x1800145a8  jb      short loc_1800145DE
0x1800145aa  lea     rcx, ?g_ncsiConfigData@@3VNcsiConfigData@@A; NcsiConfigData g_ncsiConfigData
0x1800145b1  call    ?load@?$_Atomic_storage@W4PowerState@Power@Ncsi@@$03@std@@QEBA?AW4PowerState@Power@Ncsi@@W4memory_order@2@@Z; std::_Atomic_storage<Ncsi::Power::PowerState,4>::load(std::memory_order)
0x1800145b6  mov     r9, rsi
0x1800145b9  test    eax, eax
0x1800145bb  cmovz   r9, rbx
0x1800145bf  mov     edx, 53h ; 'S'
0x1800145c4  mov     r8, r13
0x1800145c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800145ce  mov     rcx, [rcx+10h]
0x1800145d2  call    WPP_SF_s
0x1800145d7  mov     rax, cs:WPP_GLOBAL_Control
0x1800145de  cmp     rax, r12
0x1800145e1  jz      loc_1800148FF
0x1800145e7  test    [rax+1Ch], r15b
0x1800145eb  jz      short loc_180014620
0x1800145ed  cmp     [rax+19h], r14b
0x1800145f1  jb      short loc_180014620
0x1800145f3  call    ?ActiveProbesGPDisabled@NcsiConfigData@@QEAA_NXZ; NcsiConfigData::ActiveProbesGPDisabled(void)
0x1800145f8  mov     r9, rsi
0x1800145fb  test    al, al
0x1800145fd  cmovz   r9, rbx
0x180014601  mov     edx, 54h ; 'T'
0x180014606  mov     r8, r13
0x180014609  mov     rcx, cs:WPP_GLOBAL_Control
0x180014610  mov     rcx, [rcx+10h]
0x180014614  call    WPP_SF_s
0x180014619  mov     rax, cs:WPP_GLOBAL_Control
0x180014620  cmp     rax, r12
0x180014623  jz      loc_1800148FF
0x180014629  test    [rax+1Ch], r15b
0x18001462d  jz      short loc_180014663
0x18001462f  cmp     [rax+19h], r14b
0x180014633  jb      short loc_180014663
0x180014635  lea     rcx, dword_18009B3A4
0x18001463c  call    ?load@?$_Atomic_storage@W4PowerState@Power@Ncsi@@$03@std@@QEBA?AW4PowerState@Power@Ncsi@@W4memory_order@2@@Z; std::_Atomic_storage<Ncsi::Power::PowerState,4>::load(std::memory_order)
0x180014641  mov     edx, 55h ; 'U'
0x180014646  mov     r9d, eax
0x180014649  mov     r8, r13
0x18001464c  mov     rcx, cs:WPP_GLOBAL_Control
0x180014653  mov     rcx, [rcx+10h]
0x180014657  call    WPP_SF_d
0x18001465c  mov     rax, cs:WPP_GLOBAL_Control
0x180014663  cmp     rax, r12
0x180014666  jz      loc_1800148FF
0x18001466c  test    [rax+1Ch], r15b
0x180014670  jz      short loc_1800146A6
0x180014672  cmp     [rax+19h], r14b
0x180014676  jb      short loc_1800146A6
0x180014678  lea     rcx, dword_18009B3B4
0x18001467f  call    ?load@?$_Atomic_storage@W4PowerState@Power@Ncsi@@$03@std@@QEBA?AW4PowerState@Power@Ncsi@@W4memory_order@2@@Z; std::_Atomic_storage<Ncsi::Power::PowerState,4>::load(std::memory_order)
0x180014684  mov     edx, 56h ; 'V'
0x180014689  mov     r9d, eax
0x18001468c  mov     r8, r13
0x18001468f  mov     rcx, cs:WPP_GLOBAL_Control
0x180014696  mov     rcx, [rcx+10h]
0x18001469a  call    WPP_SF_d
0x18001469f  mov     rax, cs:WPP_GLOBAL_Control
0x1800146a6  cmp     rax, r12
0x1800146a9  jz      loc_1800148FF
0x1800146af  test    [rax+1Ch], r15b
0x1800146b3  jz      short loc_1800146E9
0x1800146b5  cmp     [rax+19h], r14b
0x1800146b9  jb      short loc_1800146E9
0x1800146bb  lea     rcx, dword_18009B3BC
0x1800146c2  call    ?load@?$_Atomic_storage@W4PowerState@Power@Ncsi@@$03@std@@QEBA?AW4PowerState@Power@Ncsi@@W4memory_order@2@@Z; std::_Atomic_storage<Ncsi::Power::PowerState,4>::load(std::memory_order)
0x1800146c7  mov     edx, 57h ; 'W'
0x1800146cc  mov     r9d, eax
0x1800146cf  mov     r8, r13
0x1800146d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800146d9  mov     rcx, [rcx+10h]
0x1800146dd  call    WPP_SF_d
0x1800146e2  mov     rax, cs:WPP_GLOBAL_Control
0x1800146e9  cmp     rax, r12
0x1800146ec  jz      loc_1800148FF
0x1800146f2  test    [rax+1Ch], r15b
0x1800146f6  jz      short loc_18001472B
0x1800146f8  cmp     [rax+19h], r14b
0x1800146fc  jb      short loc_18001472B
0x1800146fe  call    ?IsPassivePollingDisabled@NcsiConfigData@@QEAA_NXZ; NcsiConfigData::IsPassivePollingDisabled(void)
0x180014703  mov     r9, rsi
0x180014706  test    al, al
0x180014708  cmovz   r9, rbx
0x18001470c  mov     edx, 58h ; 'X'
0x180014711  mov     r8, r13
0x180014714  mov     rcx, cs:WPP_GLOBAL_Control
0x18001471b  mov     rcx, [rcx+10h]
0x18001471f  call    WPP_SF_s
0x180014724  mov     rax, cs:WPP_GLOBAL_Control
0x18001472b  cmp     rax, r12
0x18001472e  jz      loc_1800148FF
0x180014734  test    [rax+1Ch], r15b
0x180014738  jz      short loc_18001476E
0x18001473a  cmp     [rax+19h], r14b
0x18001473e  jb      short loc_18001476E
0x180014740  lea     rcx, dword_18009B3A8
0x180014747  call    ?load@?$_Atomic_storage@W4PowerState@Power@Ncsi@@$03@std@@QEBA?AW4PowerState@Power@Ncsi@@W4memory_order@2@@Z; std::_Atomic_storage<Ncsi::Power::PowerState,4>::load(std::memory_order)
0x18001474c  mov     edx, 59h ; 'Y'
0x180014751  mov     r9d, eax
0x180014754  mov     r8, r13
0x180014757  mov     rcx, cs:WPP_GLOBAL_Control
0x18001475e  mov     rcx, [rcx+10h]
0x180014762  call    WPP_SF_d
0x180014767  mov     rax, cs:WPP_GLOBAL_Control
0x18001476e  cmp     rax, r12
0x180014771  jz      loc_1800148FF
0x180014777  test    [rax+1Ch], r15b
0x18001477b  jz      short loc_1800147B0
0x18001477d  cmp     [rax+19h], r14b
0x180014781  jb      short loc_1800147B0
0x180014783  call    ?DoesPassivePollRequireActiveSession@NcsiConfigData@@QEBA_NXZ; NcsiConfigData::DoesPassivePollRequireActiveSession(void)
0x180014788  mov     r9, rsi
0x18001478b  test    al, al
0x18001478d  cmovz   r9, rbx
0x180014791  mov     edx, 5Ah ; 'Z'
0x180014796  mov     r8, r13
0x180014799  mov     rcx, cs:WPP_GLOBAL_Control
0x1800147a0  mov     rcx, [rcx+10h]
0x1800147a4  call    WPP_SF_s
0x1800147a9  mov     rax, cs:WPP_GLOBAL_Control
0x1800147b0  cmp     rax, r12
0x1800147b3  jz      loc_1800148FF
0x1800147b9  test    [rax+1Ch], r15b
0x1800147bd  jz      short loc_1800147EC
0x1800147bf  cmp     [rax+19h], r14b
0x1800147c3  jb      short loc_1800147EC
0x1800147c5  call    ?MaxDeadNetPollCount@NcsiConfigData@@QEBAKXZ; NcsiConfigData::MaxDeadNetPollCount(void)
0x1800147ca  mov     edx, 5Bh ; '['
0x1800147cf  mov     r9d, eax
0x1800147d2  mov     r8, r13
0x1800147d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800147dc  mov     rcx, [rcx+10h]
0x1800147e0  call    WPP_SF_d
0x1800147e5  mov     rax, cs:WPP_GLOBAL_Control
0x1800147ec  cmp     rax, r12
0x1800147ef  jz      loc_1800148FF
0x1800147f5  test    [rax+1Ch], r15b
0x1800147f9  jz      short loc_180014828
0x1800147fb  cmp     [rax+19h], r14b
0x1800147ff  jb      short loc_180014828
0x180014801  call    ?MaxDeadUserPollCount@NcsiConfigData@@QEBAKXZ; NcsiConfigData::MaxDeadUserPollCount(void)
0x180014806  mov     edx, 5Ch ; '\'
0x18001480b  mov     r9d, eax
0x18001480e  mov     r8, r13
0x180014811  mov     rcx, cs:WPP_GLOBAL_Control
0x180014818  mov     rcx, [rcx+10h]
0x18001481c  call    WPP_SF_d
0x180014821  mov     rax, cs:WPP_GLOBAL_Control
0x180014828  cmp     rax, r12
0x18001482b  jz      loc_1800148FF
0x180014831  test    [rax+1Ch], r15b
0x180014835  jz      short loc_18001486B
0x180014837  cmp     [rax+19h], r14b
0x18001483b  jb      short loc_18001486B
0x18001483d  lea     rcx, dword_18009B3B0
0x180014844  call    ?load@?$_Atomic_storage@W4PowerState@Power@Ncsi@@$03@std@@QEBA?AW4PowerState@Power@Ncsi@@W4memory_order@2@@Z; std::_Atomic_storage<Ncsi::Power::PowerState,4>::load(std::memory_order)
0x180014849  mov     edx, 5Dh ; ']'
0x18001484e  mov     r9d, eax
0x180014851  mov     r8, r13
0x180014854  mov     rcx, cs:WPP_GLOBAL_Control
0x18001485b  mov     rcx, [rcx+10h]
0x18001485f  call    WPP_SF_d
0x180014864  mov     rax, cs:WPP_GLOBAL_Control
0x18001486b  cmp     rax, r12
0x18001486e  jz      loc_1800148FF
0x180014874  test    [rax+1Ch], r15b
0x180014878  jz      short loc_1800148AE
0x18001487a  cmp     [rax+19h], r14b
0x18001487e  jb      short loc_1800148AE
0x180014880  lea     rcx, dword_18009B400
0x180014887  call    ?load@?$_Atomic_storage@W4PowerState@Power@Ncsi@@$03@std@@QEBA?AW4PowerState@Power@Ncsi@@W4memory_order@2@@Z; std::_Atomic_storage<Ncsi::Power::PowerState,4>::load(std::memory_order)
0x18001488c  mov     edx, 5Eh ; '^'
0x180014891  mov     r9d, eax
0x180014894  mov     r8, r13
0x180014897  mov     rcx, cs:WPP_GLOBAL_Control
0x18001489e  mov     rcx, [rcx+10h]
0x1800148a2  call    WPP_SF_d
0x1800148a7  mov     rax, cs:WPP_GLOBAL_Control
0x1800148ae  cmp     rax, r12
0x1800148b1  jz      short loc_1800148FF
0x1800148b3  test    [rax+1Ch], r15b
0x1800148b7  jz      short loc_1800148FF
0x1800148b9  cmp     [rax+19h], r14b
0x1800148bd  jb      short loc_1800148FF
0x1800148bf  mov     r8d, 1
0x1800148c5  lea     rdx, [rsp+0B50h+var_B08]
0x1800148ca  call    ?GetInternetDestinationAddress@NcsiConfigData@@QEAA?AT_SOCKADDR_INET@@W4_NLA_CONNECTIVITY_FAMILY@@@Z; NcsiConfigData::GetInternetDestinationAddress(_NLA_CONNECTIVITY_FAMILY)
0x1800148cf  mov     rbx, rax
0x1800148d2  xor     r8d, r8d
0x1800148d5  lea     rdx, [rsp+0B50h+var_AE8]
0x1800148da  call    ?GetInternetDestinationAddress@NcsiConfigData@@QEAA?AT_SOCKADDR_INET@@W4_NLA_CONNECTIVITY_FAMILY@@@Z; NcsiConfigData::GetInternetDestinationAddress(_NLA_CONNECTIVITY_FAMILY)
0x1800148df  mov     edx, 5Fh ; '_'; int
0x1800148e4  mov     [rsp+0B50h+var_B30], rbx; union _SOCKADDR_INET *
0x1800148e9  mov     r9, rax; int
0x1800148ec  mov     r8, r13; int
0x1800148ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800148f6  mov     rcx, [rcx+10h]; int
0x1800148fa  call    WPP_SF__SOCKADDRINET__SOCKADDRINET_
0x1800148ff  xor     edx, edx; Val
0x180014901  mov     r8d, 224h; Size
0x180014907  lea     rcx, [rbp+0A50h+var_AB0]; void *
0x18001490b  call    memset_0
0x180014910  xor     edx, edx; Val
0x180014912  mov     r8d, 61Ah; Size
0x180014918  lea     rcx, [rbp+0A50h+var_880]; void *
0x18001491f  call    memset_0
0x180014924  lea     rbx, stru_18009D378
0x18001492b  mov     rcx, rbx; lpCriticalSection
0x18001492e  call    cs:__imp_EnterCriticalSection
0x180014934  lea     rcx, [rbp+0A50h+var_AB0]
0x180014938  lea     rax, qword_18009B460
0x18001493f  mov     rdx, r14
0x180014942  mov     edi, 80h
0x180014947  movups  xmm0, xmmword ptr [rax]
0x18001494a  movups  xmmword ptr [rcx], xmm0
0x18001494d  movups  xmm1, xmmword ptr [rax+10h]
0x180014951  movups  xmmword ptr [rcx+10h], xmm1
0x180014955  movups  xmm0, xmmword ptr [rax+20h]
0x180014959  movups  xmmword ptr [rcx+20h], xmm0
0x18001495d  movups  xmm1, xmmword ptr [rax+30h]
0x180014961  movups  xmmword ptr [rcx+30h], xmm1
0x180014965  movups  xmm0, xmmword ptr [rax+40h]
0x180014969  movups  xmmword ptr [rcx+40h], xmm0
0x18001496d  movups  xmm1, xmmword ptr [rax+50h]
0x180014971  movups  xmmword ptr [rcx+50h], xmm1
0x180014975  movups  xmm0, xmmword ptr [rax+60h]
0x180014979  movups  xmmword ptr [rcx+60h], xmm0
0x18001497d  movups  xmm1, xmmword ptr [rax+70h]
0x180014981  movups  xmmword ptr [rcx+70h], xmm1
0x180014985  add     rcx, rdi
0x180014988  add     rax, rdi
0x18001498b  sub     rdx, 1
0x18001498f  jnz     short loc_180014947
0x180014991  movups  xmm0, xmmword ptr [rax]
0x180014994  movups  xmmword ptr [rcx], xmm0
0x180014997  movups  xmm1, xmmword ptr [rax+10h]
0x18001499b  movups  xmmword ptr [rcx+10h], xmm1
0x18001499f  mov     eax, [rax+20h]
0x1800149a2  mov     [rcx+20h], eax
0x1800149a5  mov     rcx, rbx; lpCriticalSection
0x1800149a8  call    cs:__imp_LeaveCriticalSection
0x1800149ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800149b5  cmp     rcx, r12
0x1800149b8  jz      short loc_1800149E4
0x1800149ba  test    [rcx+1Ch], r15b
0x1800149be  jz      short loc_1800149E4
0x1800149c0  cmp     [rcx+19h], r14b
0x1800149c4  jb      short loc_1800149E4
0x1800149c6  mov     edx, 60h ; '`'
0x1800149cb  lea     rax, [rbp+0A50h+var_8A8]
0x1800149d2  mov     [rsp+0B50h+var_B30], rax
0x1800149d7  lea     r9, [rbp+0A50h+var_AB0]
0x1800149db  mov     rcx, [rcx+10h]
0x1800149df  call    WPP_SF_S_SOCKADDRINET_
0x1800149e4  mov     rcx, rbx; lpCriticalSection
0x1800149e7  call    cs:__imp_EnterCriticalSection
0x1800149ed  lea     rcx, [rbp+0A50h+var_AB0]
0x1800149f1  lea     rax, dword_18009B684
0x1800149f8  mov     rdx, r14
0x1800149fb  movups  xmm0, xmmword ptr [rax]
0x1800149fe  movups  xmmword ptr [rcx], xmm0
0x180014a01  movups  xmm1, xmmword ptr [rax+10h]
0x180014a05  movups  xmmword ptr [rcx+10h], xmm1
0x180014a09  movups  xmm0, xmmword ptr [rax+20h]
  ... truncated ...
```
