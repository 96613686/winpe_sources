# NcsiConfigData::InternalQueryGPParamRegistry(void)

- ea: `0x180015794`
- end: `0x180016454`
- name: `?InternalQueryGPParamRegistry@NcsiConfigData@@AEAAXXZ`
- size: `3264`
- prototype: `void __fastcall(NcsiConfigData *__hidden this)`
- caller_count: `2`
- callee_count: `28`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001572c`
- `0x180052920`

## callees

- `0x18000afdc`
- `0x18000b0f4`
- `0x18000de10`
- `0x180010200`
- `0x180015794`
- `0x18001a0e0`
- `0x18001a1b4`
- `0x18001a5fc`
- `0x18002cd60`
- `0x18002d6a0`
- `0x18002e70c`
- `0x18002e894`
- `0x18003f2b8`
- `0x18004031c`
- `0x1800416ec`
- `0x180042ec8`
- `0x1800430e8`
- `0x180047240`
- `0x180047f60`
- `0x180047f78`
- `0x18004b570`
- `0x18004b5c4`
- `0x180051ca8`
- `0x180051df8`
- `0x180051f34`
- `0x180052250`
- `0x180053448`
- `0x180062764`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001583f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180015a88`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001583f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180015a88`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800157ed`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800157ed`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180015b1f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180015b47`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180015b72`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180015bda`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180015b1f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180015b47`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180015b72`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180015bda`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001619d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001619d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015e6e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015e6e`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall NcsiConfigData::InternalQueryGPParamRegistry(NcsiConfigData *this)
{
  char v1; // r13
  int v2; // esi
  const WCHAR *v3; // rdx
  NcsiConfigData *v4; // rcx
  __int32 v5; // edi
  int v6; // ebx
  bool IsDisableNCSIConnectivityEvaluationSet; // al
  bool v8; // cl
  __int64 v9; // r8
  __int64 v10; // rdi
  const WCHAR *v11; // rdx
  unsigned int DWordValue; // ebx
  unsigned int v13; // eax
  char v14; // r15
  char v15; // r14
  __int64 v16; // rcx
  bool CorpDnsProbeData; // si
  bool CorpWebProbeData; // r12
  char *v19; // rbx
  NcsiConfigData *v20; // rcx
  NcsiConfigData *v21; // rcx
  __int64 v22; // rcx
  struct _NCSI_WEB_PROBE_CONFIG *v23; // rbx
  char v24; // si
  struct NCSI_DNS_PROBE_CONFIG *v25; // rax
  int *v26; // rcx
  __int64 v27; // rbx
  int *v28; // rcx
  _OWORD *v29; // rax
  __int64 v30; // rcx
  __int64 v31; // r8
  char v32; // di
  bool v33; // bl
  bool v34; // di
  __int64 v35; // r8
  __int64 v36; // rcx
  __int64 v37; // r8
  __int64 v38; // rcx
  int v39; // ecx
  __int64 v40; // rcx
  bool CorpLocationProbeData; // [rsp+30h] [rbp-D0h]
  _DWORD v42[3]; // [rsp+34h] [rbp-CCh] BYREF
  _BYTE v43[1568]; // [rsp+40h] [rbp-C0h] BYREF
  HKEY phkResult; // [rsp+660h] [rbp+560h] BYREF
  HKEY hKey; // [rsp+668h] [rbp+568h] BYREF
  void *Src[2]; // [rsp+670h] [rbp+570h] BYREF
  __int64 v47; // [rsp+680h] [rbp+580h]
  struct _NCSI_WEB_PROBE_CONFIG *v48[2]; // [rsp+688h] [rbp+588h] BYREF
  __int64 v49; // [rsp+698h] [rbp+598h]
  struct NCSI_DNS_PROBE_CONFIG *v50[2]; // [rsp+6A0h] [rbp+5A0h] BYREF
  __int64 v51; // [rsp+6B0h] [rbp+5B0h]
  __int128 v52; // [rsp+6B8h] [rbp+5B8h] BYREF
  __int64 v53; // [rsp+6C8h] [rbp+5C8h]
  _BYTE v54[64]; // [rsp+6D0h] [rbp+5D0h] BYREF
  int v55; // [rsp+710h] [rbp+610h]
  __int128 v56; // [rsp+720h] [rbp+620h] BYREF
  char v57; // [rsp+730h] [rbp+630h]

  v1 = 0;
  v2 = dword_18009B3DC;
  hKey = 0;
  v3 = (const WCHAR *)&lpSubKey;
  if ( (unsigned __int64)qword_18009AAF8 > 7 )
    v3 = lpSubKey;
  RegOpenKeyExW(HKEY_LOCAL_MACHINE, v3, 0, 0x20019u, &hKey);
  v56 = *(_OWORD *)&c_regValueGpNoActiveProbe;
  _InterlockedExchange(&dword_18009B3DC, GetDWordValue(hKey, &v56, 0));
  v56 = *(_OWORD *)&c_regValueGpUseGlobalDns;
  _InterlockedExchange(&dword_18009B408, GetDWordValue(hKey, &v56, 0));
  v56 = *(_OWORD *)&c_regValueGpDisablePassivePolling;
  v5 = _InterlockedExchange(&dword_18009B3E0, GetDWordValue(hKey, &v56, 0));
  v6 = dword_18009B3E0;
  if ( dword_18009B3E0
    || (IsDisableNCSIConnectivityEvaluationSet = NcsiConfigData::IsDisableNCSIConnectivityEvaluationSet(v4),
        v8 = 1,
        IsDisableNCSIConnectivityEvaluationSet) )
  {
    v8 = 0;
  }
  Ncsi::PassivePoll::PassivePollManager::EnablePolling(v8);
  if ( v5 != v6 )
  {
    v42[0] = v6 != 0;
    memset_0(v54, 0, sizeof(v54));
    v55 = 8;
    std::any::operator=<_NcsiPassivePollingConfigChangeMetadata,0>((__int64)v54, v42);
    v57 = 0;
    NlmManager::PublishDiagnosticsNotificationToNlm((struct std::any *)v54);
    std::any::reset((std::any *)v54);
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
    && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u )
  {
    WPP_SF_l(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 57, v9, (unsigned int)dword_18009B3DC);
  }
  v10 = 4;
  if ( v2 != dword_18009B3DC )
  {
    v42[0] = dword_18009B3DC != 0;
    memset_0(v54, 0, sizeof(v54));
    v55 = 4;
    std::any::operator=<_NcsiActiveProbeConfigChangeMetadata,0>((__int64)v54, v42);
    v57 = 0;
    NlmManager::PublishDiagnosticsNotificationToNlm((struct std::any *)v54);
    std::any::reset((std::any *)v54);
  }
  phkResult = 0;
  v11 = (const WCHAR *)&qword_18009AB00;
  if ( (unsigned __int64)qword_18009AB18 > 7 )
    v11 = qword_18009AB00;
  RegOpenKeyExW(HKEY_LOCAL_MACHINE, v11, 0, 0x20019u, &phkResult);
  v56 = *(_OWORD *)&c_regValueCorpLocationTcpInitialRtt;
  DWordValue = GetDWordValue(phkResult, &v56, 1000);
  v56 = *(_OWORD *)&c_regValueCorpLocationTcpInitialMaxSynRetransmissions;
  v13 = GetDWordValue(phkResult, &v56, 3);
  if ( DWordValue > 0xFFFF )
    DWordValue = 0xFFFF;
  v42[0] = DWordValue;
  if ( v13 > 0xFF )
    v13 = 255;
  LODWORD(v56) = v13;
  v14 = 0;
  if ( RegQueryValueExW(phkResult, c_regValueDnsProbeHost, 0, 0, 0, 0)
    || RegQueryValueExW(phkResult, c_regValueDnsProbeContent, 0, 0, 0, 0)
    || (v15 = 0, RegQueryValueExW(phkResult, c_regValueCorpSitePrefixes, 0, 0, 0, 0)) )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 3u )
    {
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 58, &WPP_5540ffa188b23fc0b8d03d8186783076_Traceguids);
    }
    v15 = 1;
  }
  if ( RegQueryValueExW(phkResult, c_regValueCorpLocationProbeUrl, 0, 0, 0, 0) )
  {
    v16 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 3u )
    {
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 59, &WPP_5540ffa188b23fc0b8d03d8186783076_Traceguids);
      v16 = WPP_GLOBAL_Control;
    }
    v14 = 1;
  }
  else
  {
    v16 = WPP_GLOBAL_Control;
  }
  *(_OWORD *)v50 = 0;
  v51 = 0;
  *(_OWORD *)Src = 0;
  v47 = 0;
  *(_OWORD *)v48 = 0;
  v49 = 0;
  v52 = 0;
  v53 = 0;
  CorpDnsProbeData = 0;
  CorpWebProbeData = 0;
  CorpLocationProbeData = 0;
  if ( !v15 )
  {
    std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(v50, 548);
    v19 = (char *)Src[1];
    v20 = (NcsiConfigData *)((char *)Src[1] - (char *)Src[0]);
    if ( (void *)((char *)Src[1] - (char *)Src[0]) > (void *)0x61A )
    {
      v19 = (char *)Src[0] + 1562;
LABEL_42:
      Src[1] = v19;
      goto LABEL_43;
    }
    if ( (void *)((char *)Src[1] - (char *)Src[0]) < (void *)0x61A )
    {
      if ( v47 - (unsigned __int64)Src[0] >= 0x61A )
      {
        v19 = (char *)Src[0] + 1562;
        memset_0(Src[1], 0, 1562LL - (_QWORD)v20);
        goto LABEL_42;
      }
      std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(Src, 1562);
      v19 = (char *)Src[1];
    }
LABEL_43:
    if ( v50[0] == v50[1] || Src[0] == v19 )
    {
      v16 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
        && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
      {
        WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 60, &WPP_5540ffa188b23fc0b8d03d8186783076_Traceguids);
        v16 = WPP_GLOBAL_Control;
      }
      v15 = 1;
    }
    else
    {
      CorpDnsProbeData = NcsiConfigData::LoadCorpDnsProbeData(v20, phkResult, v50[0]);
      CorpWebProbeData = NcsiConfigData::LoadCorpWebProbeData(v21, phkResult, (struct _NCSI_WEB_PROBE_CONFIG *)Src[0]);
      v1 = NcsiConfigData::LoadCorpSitePrefixes(v22, phkResult, &v52);
      v16 = WPP_GLOBAL_Control;
    }
  }
  if ( v14 )
    goto LABEL_66;
  v23 = v48[1];
  if ( (struct _NCSI_WEB_PROBE_CONFIG *)(v48[1] - v48[0]) <= (struct _NCSI_WEB_PROBE_CONFIG *)0x61A )
  {
    if ( (struct _NCSI_WEB_PROBE_CONFIG *)(v48[1] - v48[0]) >= (struct _NCSI_WEB_PROBE_CONFIG *)0x61A )
      goto LABEL_59;
    if ( v49 - (unsigned __int64)v48[0] < 0x61A )
    {
      std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(v48, 1562);
      v16 = WPP_GLOBAL_Control;
      v23 = v48[1];
      goto LABEL_59;
    }
    v23 = (struct _NCSI_WEB_PROBE_CONFIG *)((char *)v48[0] + 1562);
    memset_0(v48[1], 0, 1562 - (unsigned __int64)(v48[1] - v48[0]));
    v16 = WPP_GLOBAL_Control;
  }
  else
  {
    v23 = (struct _NCSI_WEB_PROBE_CONFIG *)((char *)v48[0] + 1562);
  }
  v48[1] = v23;
LABEL_59:
  if ( v48[0] == v23 )
  {
    if ( (_UNKNOWN *)v16 != &WPP_GLOBAL_Control && (*(_BYTE *)(v16 + 28) & 0x10) != 0 && *(_BYTE *)(v16 + 25) >= 2u )
      WPP_SF_(*(_QWORD *)(v16 + 16), 61, &WPP_5540ffa188b23fc0b8d03d8186783076_Traceguids);
    v14 = 1;
  }
  else
  {
    CorpLocationProbeData = NcsiConfigData::LoadCorpLocationProbeData((NcsiConfigData *)v16, phkResult, v48[0]);
  }
LABEL_66:
  EnterCriticalSection(&stru_18009D378);
  LOWORD(dword_18009D370) = v42[0];
  BYTE2(dword_18009D370) = v56;
  if ( CorpDnsProbeData )
  {
    v24 = 0;
    v25 = v50[0];
    v26 = &dword_18009C4DC;
    do
    {
      *(_OWORD *)v26 = *(_OWORD *)v25;
      *((_OWORD *)v26 + 1) = *((_OWORD *)v25 + 1);
      *((_OWORD *)v26 + 2) = *((_OWORD *)v25 + 2);
      *((_OWORD *)v26 + 3) = *((_OWORD *)v25 + 3);
      *((_OWORD *)v26 + 4) = *((_OWORD *)v25 + 4);
      *((_OWORD *)v26 + 5) = *((_OWORD *)v25 + 5);
      *((_OWORD *)v26 + 6) = *((_OWORD *)v25 + 6);
      *((_OWORD *)v26 + 7) = *((_OWORD *)v25 + 7);
      v26 += 32;
      v25 = (struct NCSI_DNS_PROBE_CONFIG *)((char *)v25 + 128);
      --v10;
    }
    while ( v10 );
    *(_OWORD *)v26 = *(_OWORD *)v25;
    *((_OWORD *)v26 + 1) = *((_OWORD *)v25 + 1);
    v26[8] = *((_DWORD *)v25 + 8);
    v27 = WPP_GLOBAL_Control;
  }
  else
  {
    memset_0(v43, 0, 0x224u);
    v28 = &dword_18009C4DC;
    v29 = v43;
    do
    {
      *(_OWORD *)v28 = *v29;
      *((_OWORD *)v28 + 1) = v29[1];
      *((_OWORD *)v28 + 2) = v29[2];
      *((_OWORD *)v28 + 3) = v29[3];
      *((_OWORD *)v28 + 4) = v29[4];
      *((_OWORD *)v28 + 5) = v29[5];
      *((_OWORD *)v28 + 6) = v29[6];
      *((_OWORD *)v28 + 7) = v29[7];
      v28 += 32;
      v29 += 8;
      --v10;
    }
    while ( v10 );
    *(_OWORD *)v28 = *v29;
    *((_OWORD *)v28 + 1) = v29[1];
    v28[8] = *((_DWORD *)v29 + 8);
    v27 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 62, &WPP_5540ffa188b23fc0b8d03d8186783076_Traceguids);
      v27 = WPP_GLOBAL_Control;
    }
    v24 = 1;
  }
  if ( CorpWebProbeData )
  {
    memcpy_0(qword_18009C700, Src[0], 0x61Au);
  }
  else
  {
    memset_0(v43, 0, 0x61Au);
    memcpy_0(qword_18009C700, v43, 0x61Au);
    if ( (_UNKNOWN *)v27 != &WPP_GLOBAL_Control && (*(_BYTE *)(v27 + 28) & 0x10) != 0 && *(_BYTE *)(v27 + 25) >= 3u )
    {
      WPP_SF_(*(_QWORD *)(v27 + 16), 63, &WPP_5540ffa188b23fc0b8d03d8186783076_Traceguids);
      v27 = WPP_GLOBAL_Control;
    }
  }
  if ( v1 )
  {
    std::vector<CORPSITEPREFIXV6>::operator=(&qword_18009CD20, &v52);
    v27 = WPP_GLOBAL_Control;
  }
  else
  {
    if ( qword_18009CD20 != qword_18009CD28 )
      qword_18009CD28 = qword_18009CD20;
    if ( (_UNKNOWN *)v27 != &WPP_GLOBAL_Control && (*(_BYTE *)(v27 + 28) & 0x10) != 0 && *(_BYTE *)(v27 + 25) >= 2u )
    {
      WPP_SF_(*(_QWORD *)(v27 + 16), 64, &WPP_5540ffa188b23fc0b8d03d8186783076_Traceguids);
      v27 = WPP_GLOBAL_Control;
    }
    if ( (Microsoft_Windows_NCSIEnableBits & 1) != 0 )
    {
      LOBYTE(v31) = 2;
      McTemplateU0u_EtwEventWriteTransfer(v30, CorporateCheckDisabled, v31);
      v27 = WPP_GLOBAL_Control;
    }
    v24 = 1;
  }
  if ( CorpLocationProbeData )
  {
    v32 = 0;
    memcpy_0(qword_18009CD38, v48[0], 0x61Au);
  }
  else
  {
    memset_0(v43, 0, 0x61Au);
    memcpy_0(qword_18009CD38, v43, 0x61Au);
    if ( (_UNKNOWN *)v27 != &WPP_GLOBAL_Control && (*(_BYTE *)(v27 + 28) & 0x10) != 0 && *(_BYTE *)(v27 + 25) >= 2u )
      WPP_SF_(*(_QWORD *)(v27 + 16), 65, &WPP_5540ffa188b23fc0b8d03d8186783076_Traceguids);
    v32 = 1;
  }
  v33 = !v15 && !v24;
  v34 = !v14 && !v32;
  byte_18009B3C4 = v33;
  byte_18009B3C5 = v34;
  LeaveCriticalSection(&stru_18009D378);
  if ( v33 )
  {
    v36 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u )
    {
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 66, &WPP_5540ffa188b23fc0b8d03d8186783076_Traceguids);
      v36 = WPP_GLOBAL_Control;
    }
    if ( (Microsoft_Windows_NCSIEnableBits & 2) != 0 )
    {
      McGenEventWrite_EtwEventWriteTransfer(v36, (unsigned int)CorporateCheckEnabled, v35, 1, (__int64)&v56);
      v36 = WPP_GLOBAL_Control;
    }
    if ( (_UNKNOWN *)v36 != &WPP_GLOBAL_Control && (*(_BYTE *)(v36 + 28) & 0x10) != 0 && *(_BYTE *)(v36 + 25) >= 5u )
      WPP_SF_(*(_QWORD *)(v36 + 16), 67, &WPP_5540ffa188b23fc0b8d03d8186783076_Traceguids);
    Ncsi::Ipsec::SubscribeToSaNotifications((Ncsi::Ipsec *)v36);
    goto LABEL_140;
  }
  if ( v15 )
  {
    v38 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 3u )
    {
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 68, &WPP_5540ffa188b23fc0b8d03d8186783076_Traceguids);
      v38 = WPP_GLOBAL_Control;
    }
    if ( (Microsoft_Windows_NCSIEnableBits & 1) == 0 )
      goto LABEL_135;
    LOBYTE(v35) = 1;
  }
  else
  {
    v38 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 3u )
    {
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 69, &WPP_5540ffa188b23fc0b8d03d8186783076_Traceguids);
      v38 = WPP_GLOBAL_Control;
    }
    if ( (Microsoft_Windows_NCSIEnableBits & 1) == 0 )
      goto LABEL_135;
    LOBYTE(v35) = 2;
  }
  McTemplateU0u_EtwEventWriteTransfer(v38, CorporateCheckDisabled, v35);
  v38 = WPP_GLOBAL_Control;
LABEL_135:
  if ( (_UNKNOWN *)v38 != &WPP_GLOBAL_Control && (*(_BYTE *)(v38 + 28) & 0x10) != 0 && *(_BYTE *)(v38 + 25) >= 5u )
    WPP_SF_(*(_QWORD *)(v38 + 16), 70, &WPP_5540ffa188b23fc0b8d03d8186783076_Traceguids);
  Ncsi::Ipsec::UnsubscribeFromSaNotifications((Ncsi::Ipsec *)v38);
LABEL_140:
  if ( v34 )
  {
    v39 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u )
    {
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 71, &WPP_5540ffa188b23fc0b8d03d8186783076_Traceguids);
    }
    if ( (Microsoft_Windows_NCSIEnableBits & 2) != 0 )
      McGenEventWrite_EtwEventWriteTransfer(v39, (unsigned int)CorporateLocationCheckEnabled, v37, 1, (__int64)&v56);
    goto LABEL_161;
  }
  if ( v14 )
  {
    v40 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 3u )
    {
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 72, &WPP_5540ffa188b23fc0b8d03d8186783076_Traceguids);
    }
    if ( (Microsoft_Windows_NCSIEnableBits & 1) != 0 )
    {
      LOBYTE(v37) = 1;
LABEL_160:
      McTemplateU0u_EtwEventWriteTransfer(v40, CorporateLocationCheckDisabled, v37);
    }
  }
  else
  {
    v40 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 3u )
    {
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 73, &WPP_5540ffa188b23fc0b8d03d8186783076_Traceguids);
    }
    if ( (Microsoft_Windows_NCSIEnableBits & 1) != 0 )
    {
      LOBYTE(v37) = 2;
      goto LABEL_160;
    }
  }
LABEL_161:
  std::vector<CORPSITEPREFIXV6>::_Tidy(&v52);
  std::vector<unsigned char>::_Tidy(v48);
  std::vector<unsigned char>::_Tidy(Src);
  std::vector<unsigned char>::_Tidy(v50);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
}

```

## disassembly

```asm
0x180015794  push    rbp
0x180015796  push    rbx
0x180015797  push    rsi
0x180015798  push    rdi
0x180015799  push    r12
0x18001579b  push    r13
0x18001579d  push    r14
0x18001579f  push    r15
0x1800157a1  lea     rbp, [rsp-658h]
0x1800157a9  sub     rsp, 758h
0x1800157b0  mov     rax, cs:__security_cookie
0x1800157b7  xor     rax, rsp
0x1800157ba  mov     [rbp+690h+var_50], rax
0x1800157c1  xor     r13d, r13d
0x1800157c4  mov     [rbp+690h+hKey], r13
0x1800157cb  mov     esi, cs:dword_18009B3DC
0x1800157d1  nop
0x1800157d2  mov     rbx, [rbp+690h+hKey]
0x1800157d9  test    rbx, rbx
0x1800157dc  jz      short loc_1800157FF
0x1800157de  lea     rcx, [rbp+690h+var_70]; this
0x1800157e5  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800157ea  mov     rcx, rbx; hKey
0x1800157ed  call    cs:__imp_RegCloseKey
0x1800157f3  lea     rcx, [rbp+690h+var_70]; this
0x1800157fa  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800157ff  mov     [rbp+690h+hKey], r13
0x180015806  lea     rdx, lpSubKey
0x18001580d  cmp     cs:qword_18009AAF8, 7
0x180015815  cmova   rdx, cs:lpSubKey; lpSubKey
0x18001581d  lea     rax, [rbp+690h+hKey]
0x180015824  mov     [rsp+790h+phkResult], rax; phkResult
0x180015829  mov     r14d, 20019h
0x18001582f  mov     r9d, r14d; samDesired
0x180015832  xor     r8d, r8d; ulOptions
0x180015835  mov     r15, 0FFFFFFFF80000002h
0x18001583c  mov     rcx, r15; hKey
0x18001583f  call    cs:__imp_RegOpenKeyExW
0x180015845  movups  xmm0, xmmword ptr cs:?c_regValueGpNoActiveProbe@@3V?$basic_zstring_view@G@wil@@B; wil::basic_zstring_view<ushort> const c_regValueGpNoActiveProbe
0x18001584c  movdqu  [rbp+690h+var_70], xmm0
0x180015854  xor     r8d, r8d
0x180015857  lea     rdx, [rbp+690h+var_70]
0x18001585e  mov     rcx, [rbp+690h+hKey]
0x180015865  call    GetDWordValue
0x18001586a  xchg    eax, cs:dword_18009B3DC
0x180015870  movups  xmm0, xmmword ptr cs:?c_regValueGpUseGlobalDns@@3V?$basic_zstring_view@G@wil@@B; wil::basic_zstring_view<ushort> const c_regValueGpUseGlobalDns
0x180015877  movdqu  [rbp+690h+var_70], xmm0
0x18001587f  xor     r8d, r8d
0x180015882  lea     rdx, [rbp+690h+var_70]
0x180015889  mov     rcx, [rbp+690h+hKey]
0x180015890  call    GetDWordValue
0x180015895  xchg    eax, cs:dword_18009B408
0x18001589b  movups  xmm0, xmmword ptr cs:?c_regValueGpDisablePassivePolling@@3V?$basic_zstring_view@G@wil@@B; wil::basic_zstring_view<ushort> const c_regValueGpDisablePassivePolling
0x1800158a2  movdqu  [rbp+690h+var_70], xmm0
0x1800158aa  xor     r8d, r8d
0x1800158ad  lea     rdx, [rbp+690h+var_70]
0x1800158b4  mov     rcx, [rbp+690h+hKey]
0x1800158bb  call    GetDWordValue
0x1800158c0  mov     edi, eax
0x1800158c2  xchg    edi, cs:dword_18009B3E0
0x1800158c8  mov     ebx, cs:dword_18009B3E0
0x1800158ce  nop
0x1800158cf  test    ebx, ebx
0x1800158d1  jnz     short loc_1800158DE
0x1800158d3  call    ?IsDisableNCSIConnectivityEvaluationSet@NcsiConfigData@@QEAA_NXZ; NcsiConfigData::IsDisableNCSIConnectivityEvaluationSet(void)
0x1800158d8  test    al, al
0x1800158da  mov     cl, 1
0x1800158dc  jz      short loc_1800158E1
0x1800158de  mov     cl, r13b; bool
0x1800158e1  call    ?EnablePolling@PassivePollManager@PassivePoll@Ncsi@@SAX_N@Z; Ncsi::PassivePoll::PassivePollManager::EnablePolling(bool)
0x1800158e6  cmp     edi, ebx
0x1800158e8  jz      loc_180015976
0x1800158ee  mov     eax, r13d
0x1800158f1  test    ebx, ebx
0x1800158f3  setnz   al
0x1800158f6  mov     [rsp+790h+var_75C], eax
0x1800158fa  xor     edx, edx; Val
0x1800158fc  lea     r8d, [rdx+40h]; Size
0x180015900  lea     rcx, [rbp+690h+var_C0]; void *
0x180015907  call    memset_0
0x18001590c  mov     [rbp+690h+var_80], 8
0x180015916  lea     rdx, [rsp+790h+var_75C]
0x18001591b  lea     rcx, [rbp+690h+var_C0]
0x180015922  call    ??$?4U_NcsiPassivePollingConfigChangeMetadata@@$0A@@any@std@@QEAAAEAV01@$$QEAU_NcsiPassivePollingConfigChangeMetadata@@@Z; std::any::operator=<_NcsiPassivePollingConfigChangeMetadata,0>(_NcsiPassivePollingConfigChangeMetadata &&)
0x180015927  movups  xmm0, [rbp+690h+var_70]
0x18001592e  movdqu  [rbp+690h+var_70], xmm0
0x180015936  mov     [rbp+690h+var_60], r13b
0x18001593d  movzx   eax, [rbp+690h+var_5F]
0x180015944  mov     [rbp+690h+var_5F], ax
0x18001594b  mov     al, [rbp+690h+var_5D]
0x180015951  mov     [rbp+690h+var_5D], al
0x180015957  lea     rdx, [rbp+690h+var_70]
0x18001595e  lea     rcx, [rbp+690h+var_C0]; struct std::any *
0x180015965  call    ?PublishDiagnosticsNotificationToNlm@NlmManager@@SAX$$QEAUNotification@Diagnostics@@V?$optional@U_GUID@@@std@@@Z; NlmManager::PublishDiagnosticsNotificationToNlm(Diagnostics::Notification &&,std::optional<_GUID>)
0x18001596a  lea     rcx, [rbp+690h+var_C0]; this
0x180015971  call    ?reset@any@std@@QEAAXXZ; std::any::reset(void)
0x180015976  lea     rcx, WPP_GLOBAL_Control
0x18001597d  mov     r12b, 10h
0x180015980  mov     rax, cs:WPP_GLOBAL_Control
0x180015987  cmp     rax, rcx
0x18001598a  jz      short loc_1800159B5
0x18001598c  test    [rax+1Ch], r12b
0x180015990  jz      short loc_1800159B5
0x180015992  cmp     byte ptr [rax+19h], 5
0x180015996  jb      short loc_1800159B5
0x180015998  mov     r9d, cs:dword_18009B3DC
0x18001599f  nop
0x1800159a0  mov     edx, 39h ; '9'
0x1800159a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800159ac  mov     rcx, [rcx+10h]
0x1800159b0  call    WPP_SF_l
0x1800159b5  mov     eax, cs:dword_18009B3DC
0x1800159bb  nop
0x1800159bc  mov     edi, 4
0x1800159c1  cmp     esi, eax
0x1800159c3  jz      loc_180015A55
0x1800159c9  mov     eax, cs:dword_18009B3DC
0x1800159cf  nop
0x1800159d0  mov     ecx, r13d
0x1800159d3  test    eax, eax
0x1800159d5  setnz   cl
0x1800159d8  mov     [rsp+790h+var_75C], ecx
0x1800159dc  xor     edx, edx; Val
0x1800159de  lea     r8d, [rdi+3Ch]; Size
0x1800159e2  lea     rcx, [rbp+690h+var_C0]; void *
0x1800159e9  call    memset_0
0x1800159ee  mov     [rbp+690h+var_80], edi
0x1800159f4  lea     rdx, [rsp+790h+var_75C]
0x1800159f9  lea     rcx, [rbp+690h+var_C0]
0x180015a00  call    ??$?4U_NcsiActiveProbeConfigChangeMetadata@@$0A@@any@std@@QEAAAEAV01@$$QEAU_NcsiActiveProbeConfigChangeMetadata@@@Z; std::any::operator=<_NcsiActiveProbeConfigChangeMetadata,0>(_NcsiActiveProbeConfigChangeMetadata &&)
0x180015a05  movups  xmm0, [rbp+690h+var_70]
0x180015a0c  movdqu  [rbp+690h+var_70], xmm0
0x180015a14  mov     [rbp+690h+var_60], r13b
0x180015a1b  movzx   eax, [rbp+690h+var_5F]
0x180015a22  mov     [rbp+690h+var_5F], ax
0x180015a29  mov     al, [rbp+690h+var_5D]
0x180015a2f  mov     [rbp+690h+var_5D], al
0x180015a35  lea     rdx, [rbp+690h+var_70]
0x180015a3c  lea     rcx, [rbp+690h+var_C0]; struct std::any *
0x180015a43  call    ?PublishDiagnosticsNotificationToNlm@NlmManager@@SAX$$QEAUNotification@Diagnostics@@V?$optional@U_GUID@@@std@@@Z; NlmManager::PublishDiagnosticsNotificationToNlm(Diagnostics::Notification &&,std::optional<_GUID>)
0x180015a48  lea     rcx, [rbp+690h+var_C0]; this
0x180015a4f  call    ?reset@any@std@@QEAAXXZ; std::any::reset(void)
0x180015a54  nop
0x180015a55  mov     [rbp+690h+var_130], r13
0x180015a5c  lea     rdx, qword_18009AB00
0x180015a63  cmp     cs:qword_18009AB18, 7
0x180015a6b  cmova   rdx, cs:qword_18009AB00; lpSubKey
0x180015a73  lea     rax, [rbp+690h+var_130]
0x180015a7a  mov     [rsp+790h+phkResult], rax; phkResult
0x180015a7f  mov     r9d, r14d; samDesired
0x180015a82  xor     r8d, r8d; ulOptions
0x180015a85  mov     rcx, r15; hKey
0x180015a88  call    cs:__imp_RegOpenKeyExW
0x180015a8e  movups  xmm0, xmmword ptr cs:?c_regValueCorpLocationTcpInitialRtt@@3V?$basic_zstring_view@G@wil@@B; wil::basic_zstring_view<ushort> const c_regValueCorpLocationTcpInitialRtt
0x180015a95  movdqu  [rbp+690h+var_70], xmm0
0x180015a9d  mov     r8d, 3E8h
0x180015aa3  lea     rdx, [rbp+690h+var_70]
0x180015aaa  mov     rcx, [rbp+690h+var_130]
0x180015ab1  call    GetDWordValue
0x180015ab6  mov     ebx, eax
0x180015ab8  movups  xmm0, xmmword ptr cs:?c_regValueCorpLocationTcpInitialMaxSynRetransmissions@@3V?$basic_zstring_view@G@wil@@B; wil::basic_zstring_view<ushort> const c_regValueCorpLocationTcpInitialMaxSynRetransmissions
0x180015abf  movdqu  [rbp+690h+var_70], xmm0
0x180015ac7  mov     r8d, 3
0x180015acd  lea     rdx, [rbp+690h+var_70]
0x180015ad4  mov     rcx, [rbp+690h+var_130]
0x180015adb  call    GetDWordValue
0x180015ae0  mov     ecx, 0FFFFh
0x180015ae5  cmp     ebx, ecx
0x180015ae7  cmova   ebx, ecx
0x180015aea  mov     [rsp+790h+var_75C], ebx
0x180015aee  mov     ecx, 0FFh
0x180015af3  cmp     eax, ecx
0x180015af5  cmova   eax, ecx
0x180015af8  mov     dword ptr [rbp+690h+var_70], eax
0x180015afe  mov     r15b, r13b
0x180015b01  mov     [rsp+790h+lpcbData], r13; lpcbData
0x180015b06  mov     [rsp+790h+phkResult], r13; lpData
0x180015b0b  xor     r9d, r9d; lpType
0x180015b0e  xor     r8d, r8d; lpReserved
0x180015b11  mov     rdx, cs:?c_regValueDnsProbeHost@@3V?$basic_zstring_view@G@wil@@B; lpValueName
0x180015b18  mov     rcx, [rbp+690h+var_130]; hKey
0x180015b1f  call    cs:__imp_RegQueryValueExW
0x180015b25  test    eax, eax
0x180015b27  jnz     short loc_180015B7C
0x180015b29  mov     [rsp+790h+lpcbData], r13; lpcbData
0x180015b2e  mov     [rsp+790h+phkResult], r13; lpData
0x180015b33  xor     r9d, r9d; lpType
0x180015b36  xor     r8d, r8d; lpReserved
0x180015b39  mov     rdx, cs:?c_regValueDnsProbeContent@@3V?$basic_zstring_view@G@wil@@B; lpValueName
0x180015b40  mov     rcx, [rbp+690h+var_130]; hKey
0x180015b47  call    cs:__imp_RegQueryValueExW
0x180015b4d  test    eax, eax
0x180015b4f  jnz     short loc_180015B7C
0x180015b51  mov     r14b, r13b
0x180015b54  mov     [rsp+790h+lpcbData], r13; lpcbData
0x180015b59  mov     [rsp+790h+phkResult], r13; lpData
0x180015b5e  xor     r9d, r9d; lpType
0x180015b61  xor     r8d, r8d; lpReserved
0x180015b64  mov     rdx, cs:?c_regValueCorpSitePrefixes@@3V?$basic_zstring_view@G@wil@@B; lpValueName
0x180015b6b  mov     rcx, [rbp+690h+var_130]; hKey
0x180015b72  call    cs:__imp_RegQueryValueExW
0x180015b78  test    eax, eax
0x180015b7a  jz      short loc_180015BB5
0x180015b7c  mov     rcx, cs:WPP_GLOBAL_Control
0x180015b83  lea     rbx, WPP_GLOBAL_Control
0x180015b8a  cmp     rcx, rbx
0x180015b8d  jz      short loc_180015BB0
0x180015b8f  test    [rcx+1Ch], r12b
0x180015b93  jz      short loc_180015BB0
0x180015b95  cmp     byte ptr [rcx+19h], 3
0x180015b99  jb      short loc_180015BB0
0x180015b9b  mov     edx, 3Ah ; ':'
0x180015ba0  lea     r8, WPP_5540ffa188b23fc0b8d03d8186783076_Traceguids
0x180015ba7  mov     rcx, [rcx+10h]
0x180015bab  call    WPP_SF_
0x180015bb0  mov     r14b, 1
0x180015bb3  jmp     short loc_180015BBC
0x180015bb5  lea     rbx, WPP_GLOBAL_Control
0x180015bbc  mov     [rsp+790h+lpcbData], r13; lpcbData
0x180015bc1  mov     [rsp+790h+phkResult], r13; lpData
0x180015bc6  xor     r9d, r9d; lpType
0x180015bc9  xor     r8d, r8d; lpReserved
0x180015bcc  mov     rdx, cs:?c_regValueCorpLocationProbeUrl@@3V?$basic_zstring_view@G@wil@@B; lpValueName
0x180015bd3  mov     rcx, [rbp+690h+var_130]; hKey
0x180015bda  call    cs:__imp_RegQueryValueExW
0x180015be0  test    eax, eax
0x180015be2  jz      short loc_180015C1D
0x180015be4  mov     rcx, cs:WPP_GLOBAL_Control
0x180015beb  cmp     rcx, rbx
0x180015bee  jz      short loc_180015C18
0x180015bf0  test    [rcx+1Ch], r12b
0x180015bf4  jz      short loc_180015C18
0x180015bf6  cmp     byte ptr [rcx+19h], 3
0x180015bfa  jb      short loc_180015C18
0x180015bfc  mov     edx, 3Bh ; ';'
0x180015c01  lea     r8, WPP_5540ffa188b23fc0b8d03d8186783076_Traceguids
0x180015c08  mov     rcx, [rcx+10h]
0x180015c0c  call    WPP_SF_
0x180015c11  mov     rcx, cs:WPP_GLOBAL_Control
0x180015c18  mov     r15b, 1
0x180015c1b  jmp     short loc_180015C24
0x180015c1d  mov     rcx, cs:WPP_GLOBAL_Control
0x180015c24  xorps   xmm1, xmm1
0x180015c27  movdqu  xmmword ptr [rbp+690h+var_F0], xmm1
0x180015c2f  mov     [rbp+690h+var_E0], r13
0x180015c36  movdqu  xmmword ptr [rbp+690h+Src], xmm1
0x180015c3e  mov     [rbp+690h+var_110], r13
0x180015c45  movdqu  xmmword ptr [rbp+690h+var_108], xmm1
0x180015c4d  mov     [rbp+690h+var_F8], r13
0x180015c54  movdqu  [rbp+690h+var_D8], xmm1
0x180015c5c  mov     [rbp+690h+var_C8], r13
0x180015c63  mov     sil, r13b
0x180015c66  mov     r12b, r13b
0x180015c69  mov     [rsp+790h+var_760], r13b
0x180015c6e  mov     r10d, 61Ah
0x180015c74  test    r14b, r14b
0x180015c77  jnz     loc_180015D9A
0x180015c7d  mov     edx, 224h
0x180015c82  lea     rcx, [rbp+690h+var_F0]
0x180015c89  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180015c8e  mov     rdx, [rbp+690h+Src]
0x180015c95  mov     rbx, [rbp+690h+Src+8]
0x180015c9c  mov     r9, rbx
0x180015c9f  mov     rcx, rbx
0x180015ca2  sub     rcx, rdx
0x180015ca5  mov     r8d, 61Ah
0x180015cab  cmp     rcx, r8
0x180015cae  jbe     short loc_180015CB9
0x180015cb0  lea     rbx, [rdx+61Ah]
0x180015cb7  jmp     short loc_180015CF2
0x180015cb9  jnb     short loc_180015CF9
0x180015cbb  mov     rax, [rbp+690h+var_110]
0x180015cc2  sub     rax, rdx
0x180015cc5  cmp     rax, r8
0x180015cc8  jnb     short loc_180015CE2
0x180015cca  mov     rdx, r8
0x180015ccd  lea     rcx, [rbp+690h+Src]
0x180015cd4  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180015cd9  mov     rbx, [rbp+690h+Src+8]
0x180015ce0  jmp     short loc_180015CF9
0x180015ce2  sub     r8, rcx; Size
0x180015ce5  add     rbx, r8
0x180015ce8  xor     edx, edx; Val
0x180015cea  mov     rcx, r9; void *
0x180015ced  call    memset_0
0x180015cf2  mov     [rbp+690h+Src+8], rbx
0x180015cf9  mov     r8, [rbp+690h+var_F0]; struct NCSI_DNS_PROBE_CONFIG *
0x180015d00  cmp     r8, [rbp+690h+var_F0+8]
0x180015d07  jz      short loc_180015D56
0x180015d09  cmp     [rbp+690h+Src], rbx
0x180015d10  jz      short loc_180015D56
0x180015d12  mov     rdx, [rbp+690h+var_130]; HKEY
0x180015d19  call    ?LoadCorpDnsProbeData@NcsiConfigData@@AEAA_NPEAUHKEY__@@PEAUNCSI_DNS_PROBE_CONFIG@@@Z; NcsiConfigData::LoadCorpDnsProbeData(HKEY__ *,NCSI_DNS_PROBE_CONFIG *)
0x180015d1e  mov     sil, al
0x180015d21  mov     r8, [rbp+690h+Src]; struct _NCSI_WEB_PROBE_CONFIG *
0x180015d28  mov     rdx, [rbp+690h+var_130]; HKEY
0x180015d2f  call    ?LoadCorpWebProbeData@NcsiConfigData@@AEAA_NPEAUHKEY__@@PEAU_NCSI_WEB_PROBE_CONFIG@@@Z; NcsiConfigData::LoadCorpWebProbeData(HKEY__ *,_NCSI_WEB_PROBE_CONFIG *)
0x180015d34  mov     r12b, al
0x180015d37  lea     r8, [rbp+690h+var_D8]
0x180015d3e  mov     rdx, [rbp+690h+var_130]
  ... truncated ...
```
