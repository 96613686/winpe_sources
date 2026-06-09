# PublicNetworkListManager::ClientHandleIpHlpEvent(void)

- ea: `0x180020388`
- end: `0x1800210a7`
- name: `?ClientHandleIpHlpEvent@PublicNetworkListManager@@AEAAJXZ`
- size: `3359`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `2`
- callee_count: `27`
- tags: `broker_com_uri`

## callers

- `0x180021360`
- `0x18002a48c`

## callees

- `0x180006770`
- `0x180006810`
- `0x1800086b0`
- `0x18000a894`
- `0x18000a908`
- `0x18000ad84`
- `0x18000c650`
- `0x1800120d0`
- `0x180012f40`
- `0x180013fa1`
- `0x18001e70c`
- `0x18001e79c`
- `0x18001e8b8`
- `0x18001ec18`
- `0x18001ede0`
- `0x180020388`
- `0x1800210b0`
- `0x180021774`
- `0x1800256b4`
- `0x180025b74`
- `0x180026644`
- `0x180028738`
- `0x18002a978`
- `0x18002aae0`
- `0x18002ab14`
- `0x18002af50`
- `0x180043010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020d3c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020d3c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002050e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002050e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800207c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800207f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800207c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800207f5`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800204df`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800204df`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x18002072b`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x18002072b`
- `IPHLPAPI!GetIfEntry2Ex` at `0x18002076d`
- `IPHLPAPI!GetIfEntry2Ex` at `0x18002076d`

## pseudocode

```c
__int64 __fastcall PublicNetworkListManager::ClientHandleIpHlpEvent(struct _RTL_CRITICAL_SECTION *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // r13
  int v2; // r15d
  HRESULT v3; // eax
  int NetworkConnectionEnumRemote; // r12d
  _QWORD *p_Type; // rbx
  __int64 v6; // r9
  int v7; // r14d
  int InterfaceStackPerDestination; // eax
  PublicNetworkListManager *v9; // rcx
  __int128 v10; // xmm1
  __int64 v11; // xmm2_8
  __int64 v12; // rax
  unsigned int v13; // eax
  GUID v14; // xmm2
  __int64 v15; // r8
  unsigned int *v16; // rdi
  __int64 v17; // rax
  struct NLM_DATAPLAN_STATUS *v18; // rsi
  __int64 *v19; // rax
  __int64 v20; // rdx
  GUID *v21; // r14
  unsigned int v22; // edi
  int Value; // r13d
  char IsEnabled; // al
  __int64 v25; // rcx
  int IfEntry2; // eax
  signed int LastError; // eax
  __int64 v28; // rdx
  int v29; // eax
  int v30; // edx
  __int64 *i; // rax
  int v32; // eax
  int v33; // edi
  int v34; // esi
  __int64 v35; // rax
  int v36; // eax
  _QWORD *v37; // rcx
  __int64 v38; // rdx
  PublicNetworkListManager *v39; // rcx
  __int128 v40; // xmm1
  __int64 v41; // xmm2_8
  __int64 v42; // rax
  __int128 v43; // xmm1
  __int128 v44; // xmm2
  __int64 v45; // xmm3_8
  __int64 v46; // rax
  int v47; // edi
  int v48; // esi
  __int64 v49; // rax
  __int64 *v50; // rbx
  __int64 v51; // rbx
  char v52; // r15
  char v53; // r14
  char v54; // si
  char v55; // di
  PVOID *v56; // rcx
  PVOID v57; // rcx
  __int64 v58; // rcx
  __int64 v59; // rcx
  unsigned __int8 v61; // [rsp+80h] [rbp-80h]
  char v62; // [rsp+81h] [rbp-7Fh]
  char v63; // [rsp+82h] [rbp-7Eh]
  char v64; // [rsp+83h] [rbp-7Dh]
  unsigned int v65; // [rsp+84h] [rbp-7Ch]
  __int16 v66; // [rsp+84h] [rbp-7Ch]
  unsigned int v67; // [rsp+88h] [rbp-78h] BYREF
  int v68; // [rsp+8Ch] [rbp-74h]
  unsigned int v69; // [rsp+90h] [rbp-70h]
  int v70; // [rsp+98h] [rbp-68h] BYREF
  __int128 v71; // [rsp+9Ch] [rbp-64h]
  __int128 *v72; // [rsp+B0h] [rbp-50h] BYREF
  struct _GUID v73; // [rsp+C0h] [rbp-40h] BYREF
  PublicNetworkListManager *v74; // [rsp+D0h] [rbp-30h]
  _QWORD v75[2]; // [rsp+D8h] [rbp-28h] BYREF
  _QWORD v76[2]; // [rsp+E8h] [rbp-18h] BYREF
  _OWORD Buf1[3]; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v78; // [rsp+128h] [rbp+28h]
  NET_LUID InterfaceLuid; // [rsp+130h] [rbp+30h] BYREF
  struct IEnumNetworkConnections *v80; // [rsp+138h] [rbp+38h] BYREF
  __int128 v81; // [rsp+140h] [rbp+40h] BYREF
  __int128 v82; // [rsp+150h] [rbp+50h] BYREF
  unsigned int v83[12]; // [rsp+160h] [rbp+60h] BYREF
  __int128 v84; // [rsp+190h] [rbp+90h] BYREF
  unsigned int v85; // [rsp+1A0h] [rbp+A0h]
  GUID InterfaceGuid; // [rsp+1A4h] [rbp+A4h]
  __int128 v87; // [rsp+1B4h] [rbp+B4h]
  __int128 v88; // [rsp+1C4h] [rbp+C4h]
  __int64 v89; // [rsp+1D4h] [rbp+D4h]
  __int64 v90; // [rsp+1DCh] [rbp+DCh]
  __int128 v91; // [rsp+1F0h] [rbp+F0h] BYREF
  __int128 v92; // [rsp+200h] [rbp+100h] BYREF
  int v93; // [rsp+210h] [rbp+110h]
  GUID pguid; // [rsp+218h] [rbp+118h] BYREF
  NLM_DATAPLAN_STATUS v95; // [rsp+228h] [rbp+128h] BYREF
  _QWORD v96[141]; // [rsp+260h] [rbp+160h] BYREF
  int v97; // [rsp+6C8h] [rbp+5C8h]
  int v98; // [rsp+6ECh] [rbp+5ECh]
  unsigned int v99[4]; // [rsp+7B0h] [rbp+6B0h] BYREF
  struct NLM_DATAPLAN_STATUS v100[2]; // [rsp+7C0h] [rbp+6C0h] BYREF

  v1 = this;
  v74 = (PublicNetworkListManager *)this;
  v2 = 0;
  v67 = 0;
  memset(&v95, 0, sizeof(v95));
  v82 = 0;
  std::list<CLIENT_NODE_COST_DATA>::list<CLIENT_NODE_COST_DATA>(&v82);
  v81 = 0;
  std::list<CLIENT_NODE_COST_DATA>::list<CLIENT_NODE_COST_DATA>(&v81);
  v84 = 0;
  v85 = 0;
  InterfaceGuid = 0;
  v87 = 0;
  v88 = 0;
  v89 = 0;
  v90 = 0;
  v80 = 0;
  memset_0(v96, 0, 0x548u);
  v70 = 0;
  v71 = 0;
  v91 = 0;
  std::list<CLIENT_INTF_COUNTER>::_Construct_range_unchecked<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<CLIENT_INTF_COUNTER>>,std::_Iterator_base0>,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<CLIENT_INTF_COUNTER>>,std::_Iterator_base0>>(
    &v91,
    *(_QWORD *)qword_180060170,
    qword_180060170);
  memset(v83, 0, 40);
  pguid = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 178, &WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids);
  std::list<CLIENT_INTF_COUNTER>::clear(&qword_180060170);
  v3 = CoCreateGuid(&pguid);
  NetworkConnectionEnumRemote = v3;
  if ( v3 >= 0 )
  {
    NetworkConnectionEnumRemote = PublicNetworkListManager::GetNetworkConnectionEnumRemote(
                                    (PublicNetworkListManager *)v1,
                                    &v80);
    if ( NetworkConnectionEnumRemote < 0 )
      goto LABEL_121;
    EnterCriticalSection(v1 + 14);
    p_Type = &v1[15].DebugInfo->Type;
    while ( 1 )
    {
      p_Type = (_QWORD *)*p_Type;
      if ( p_Type == (_QWORD *)v1[15].DebugInfo )
      {
        LeaveCriticalSection(v1 + 14);
        v50 = (__int64 *)v81;
        while ( 1 )
        {
          v50 = (__int64 *)*v50;
          if ( v50 == (__int64 *)v81 )
            break;
          if ( *((_DWORD *)v50 + 23) )
          {
            v73 = (struct _GUID)*((_OWORD *)v50 + 1);
            PublicNetworkListManager::PostNetworkCostManagerEvent(
              (PublicNetworkListManager *)v1,
              &v73,
              0x801u,
              *((_DWORD *)v50 + 8));
          }
          if ( *((_DWORD *)v50 + 24) )
          {
            v73 = (struct _GUID)*((_OWORD *)v50 + 1);
            PublicNetworkListManager::PostNetworkCostManagerEvent((PublicNetworkListManager *)v1, &v73, 0x802u, 0);
          }
        }
        v51 = qword_180060170;
        while ( 1 )
        {
          v51 = *(_QWORD *)v51;
          if ( v51 == qword_180060170 )
            break;
          if ( *(_DWORD *)(v51 + 32) > 0xAu )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              WPP_SF_DDDDDDDDDDDLD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                190,
                *(unsigned __int8 *)(v51 + 29),
                *(_DWORD *)(v51 + 16),
                *(_WORD *)(v51 + 20),
                *(_WORD *)(v51 + 22),
                *(_BYTE *)(v51 + 24),
                *(_BYTE *)(v51 + 25),
                *(_BYTE *)(v51 + 26),
                *(_BYTE *)(v51 + 27),
                *(_BYTE *)(v51 + 28),
                *(_BYTE *)(v51 + 29),
                *(_BYTE *)(v51 + 30),
                *(_BYTE *)(v51 + 31),
                *(_DWORD *)(v51 + 32),
                NetworkConnectionEnumRemote);
          }
          else
          {
            v70 = 4;
            v68 = *(_DWORD *)(v51 + 16);
            LODWORD(v71) = v68;
            v66 = *(_WORD *)(v51 + 20);
            WORD2(v71) = v66;
            LOWORD(InterfaceLuid.Value) = *(_WORD *)(v51 + 22);
            WORD3(v71) = InterfaceLuid.Value;
            v64 = *(_BYTE *)(v51 + 24);
            BYTE8(v71) = v64;
            v52 = *(_BYTE *)(v51 + 25);
            BYTE9(v71) = v52;
            v53 = *(_BYTE *)(v51 + 26);
            BYTE10(v71) = v53;
            v54 = *(_BYTE *)(v51 + 27);
            BYTE11(v71) = v54;
            v55 = *(_BYTE *)(v51 + 28);
            BYTE12(v71) = v55;
            v63 = *(_BYTE *)(v51 + 29);
            BYTE13(v71) = v63;
            v62 = *(_BYTE *)(v51 + 30);
            BYTE14(v71) = v62;
            v61 = *(_BYTE *)(v51 + 31);
            HIBYTE(v71) = v61;
            NetworkConnectionEnumRemote = PublicNetworkListManager::ClientPostDestEventToDestEventMgr(
                                            (PublicNetworkListManager *)v1,
                                            (struct CLIENT_DEST_EVENT *)&v70);
            v67 = NetworkConnectionEnumRemote;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            {
              WPP_SF_DDDDDDDDDDDLD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                189,
                v61,
                v68,
                v66,
                InterfaceLuid.Value,
                v64,
                v52,
                v53,
                v54,
                v55,
                v63,
                v62,
                v61,
                *(_DWORD *)(v51 + 32),
                v67);
              NetworkConnectionEnumRemote = v67;
            }
          }
          v1 = (struct _RTL_CRITICAL_SECTION *)v74;
        }
        if ( NetworkConnectionEnumRemote < 0 )
        {
LABEL_121:
          v56 = (PVOID *)WPP_GLOBAL_Control;
          goto LABEL_122;
        }
        goto LABEL_125;
      }
      v6 = p_Type[2];
      v7 = *(_DWORD *)(v6 + 184);
      v68 = v7;
      Buf1[0] = *(_OWORD *)(v6 + 188);
      Buf1[1] = *(_OWORD *)(v6 + 204);
      Buf1[2] = *(_OWORD *)(v6 + 220);
      v78 = *(_QWORD *)(v6 + 236);
      InterfaceStackPerDestination = PublicNetworkListManager::GetInterfaceStackPerDestination(
                                       (PublicNetworkListManager *)v1,
                                       (struct sockaddr_storage *)(v6 + 16),
                                       &pguid,
                                       (struct ADDRESS_INTERFACE_DATA *)v6,
                                       1,
                                       (struct INTERFACE_STACK *)v83);
      NetworkConnectionEnumRemote = InterfaceStackPerDestination;
      if ( InterfaceStackPerDestination < 0 )
      {
        if ( InterfaceStackPerDestination == -2147023899 )
          goto LABEL_99;
        v39 = (PublicNetworkListManager *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            186,
            &WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids,
            (unsigned int)InterfaceStackPerDestination);
        v36 = PublicNetworkListManager::ClientHandleUnderminedDestinationCost(
                v39,
                v80,
                (struct INTERFACE_STACK *)v83,
                &v67,
                &v95);
        NetworkConnectionEnumRemote = v36;
        if ( v36 < 0 )
        {
          v37 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v38 = 188;
            goto LABEL_95;
          }
        }
        else
        {
          v40 = *(_OWORD *)&v83[4];
          v41 = *(_QWORD *)&v83[8];
          v42 = p_Type[2];
          *(_OWORD *)(v42 + 144) = *(_OWORD *)v83;
          *(_OWORD *)(v42 + 160) = v40;
          *(_QWORD *)(v42 + 176) = v41;
          *(_DWORD *)(p_Type[2] + 184LL) = v67;
          v43 = *(_OWORD *)&v95.UsageData.UsageInMegabytes;
          v44 = *(_OWORD *)&v95.InboundBandwidthInKbps;
          v45 = *(_QWORD *)&v95.MaxTransferSizeInMegabytes;
          v46 = p_Type[2];
          *(GUID *)(v46 + 188) = v95.InterfaceGuid;
          *(_OWORD *)(v46 + 204) = v43;
          *(_OWORD *)(v46 + 220) = v44;
          *(_QWORD *)(v46 + 236) = v45;
          v84 = *(_OWORD *)p_Type[2];
          v47 = 0;
          v90 = 0;
          v48 = 0;
          if ( v7 != *(_DWORD *)(p_Type[2] + 184LL) )
          {
            v47 = 1;
            LODWORD(v90) = 1;
            v85 = *(_DWORD *)(p_Type[2] + 184LL);
          }
          if ( memcmp_0(Buf1, (const void *)(p_Type[2] + 188LL), 0x38u) )
          {
            v48 = 1;
            HIDWORD(v90) = 1;
            v49 = p_Type[2];
            InterfaceGuid = *(GUID *)(v49 + 188);
            v87 = *(_OWORD *)(v49 + 204);
            v88 = *(_OWORD *)(v49 + 220);
            v89 = *(_QWORD *)(v49 + 236);
          }
          if ( v47 || v48 )
          {
            *(_QWORD *)&v73.Data1 = &v81;
            *(_QWORD *)v73.Data4 = &v84;
            v36 = wil::ResultFromException__PublicNetworkListManager::ClientHandleIpHlpEvent_::_99_::_lambda_4___(&v73);
            NetworkConnectionEnumRemote = v36;
            if ( v36 < 0 )
            {
              v37 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v38 = 187;
                goto LABEL_95;
              }
            }
          }
        }
      }
      else
      {
        v65 = 1;
        v10 = *(_OWORD *)&v83[4];
        v11 = *(_QWORD *)&v83[8];
        v12 = p_Type[2];
        *(_OWORD *)(v12 + 144) = *(_OWORD *)v83;
        *(_OWORD *)(v12 + 160) = v10;
        *(_QWORD *)(v12 + 176) = v11;
        v13 = 0;
        v69 = 0;
        if ( v83[0] )
        {
          v14 = GUID_NULL;
          while ( 1 )
          {
            if ( NetworkConnectionEnumRemote < 0 )
              goto LABEL_99;
            v15 = v13;
            v16 = &v99[v13];
            *v16 = 0;
            v17 = v13;
            v18 = &v100[v17];
            v100[v17].InterfaceGuid = v14;
            v100[v17].UsageData.UsageInMegabytes = -1;
            v100[v17].UsageData.LastSyncTime = 0;
            v100[v17].DataLimitInMegabytes = -1;
            v100[v17].InboundBandwidthInKbps = -1;
            v100[v17].OutboundBandwidthInKbps = -1;
            v100[v17].NextBillingCycle = 0;
            v100[v17].MaxTransferSizeInMegabytes = -1;
            v100[v17].Reserved = 0;
            v19 = (__int64 *)v82;
            v20 = 4LL * (unsigned int)v15;
            while ( 1 )
            {
              v19 = (__int64 *)*v19;
              v72 = (__int128 *)(v20 * 4);
              if ( v19 == (__int64 *)v82 )
                break;
              v20 = 4 * v15;
              v21 = (GUID *)&v83[4 * v15 + 1];
              v9 = (PublicNetworkListManager *)v19[2];
              if ( v9 == *(PublicNetworkListManager **)&v21->Data1 )
              {
                v9 = (PublicNetworkListManager *)v19[3];
                if ( v9 == *(PublicNetworkListManager **)v21->Data4 )
                {
                  v9 = (PublicNetworkListManager *)*((unsigned int *)v19 + 8);
                  *v16 = (unsigned int)v9;
                  v18->InterfaceGuid = *(GUID *)((char *)v19 + 36);
                  *(_OWORD *)&v18->UsageData.UsageInMegabytes = *(_OWORD *)((char *)v19 + 52);
                  *(_OWORD *)&v18->InboundBandwidthInKbps = *(_OWORD *)((char *)v19 + 68);
                  *(_QWORD *)&v18->MaxTransferSizeInMegabytes = *(__int64 *)((char *)v19 + 84);
                  goto LABEL_18;
                }
              }
            }
            v21 = (GUID *)&v83[v20 + 1];
LABEL_18:
            if ( *v16 != -1 )
              break;
            v9 = 0;
            v65 = 0;
LABEL_66:
            v13 = v69 + 1;
            v69 = v13;
            if ( v13 >= v83[0] )
            {
              if ( NetworkConnectionEnumRemote >= 0 && (_DWORD)v9 )
              {
                v7 = v68;
                goto LABEL_70;
              }
              goto LABEL_99;
            }
          }
          if ( v19 != (__int64 *)v82 )
            goto LABEL_65;
          LODWORD(InterfaceLuid.Value) = 0;
          NetworkConnectionEnumRemote = PublicNetworkListManager::GetInterfaceCostAndDataPlanStatus(
                                          v9,
                                          v80,
                                          1u,
                                          v21,
                                          v16,
                                          v18,
                                          &InterfaceLuid);
          if ( NetworkConnectionEnumRemote < 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                184,
                &WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids,
                (unsigned int)NetworkConnectionEnumRemote);
            goto LABEL_64;
          }
          v22 = *v16;
          Value = InterfaceLuid.Value;
          if ( LODWORD(InterfaceLuid.Value) )
            goto LABEL_43;
          InterfaceLuid.Value = 0;
          if ( ConvertInterfaceGuidToLuid(v21, &InterfaceLuid) )
          {
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_43;
            LastError = GetLastError();
            if ( LastError > 0 )
              LastError = (unsigned __int16)LastError | 0x80070000;
            v28 = 181;
          }
          else
          {
            v96[0] = InterfaceLuid.Value;
            IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_NLM_Fix_DestinationCallbackDrainRace>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_NLM_Fix_DestinationCallbackDrainRace>::GetImpl'::`2'::impl);
            v25 = (unsigned int)(Value + 2);
            if ( IsEnabled )
              IfEntry2 = ((__int64 (__fastcall *)(__int64, _QWORD *))qword_180060580)(v25, v96);
            else
              IfEntry2 = GetIfEntry2Ex(v25, v96);
            if ( !IfEntry2 )
            {
              if ( v98 == 1 && v97 != 131 && v97 != 24 )
              {
                v2 = 1;
                v22 = -1;
              }
LABEL_43:
              v84 = *(_OWORD *)((char *)&v83[1] + (_QWORD)v72);
              v85 = v22;
              InterfaceGuid = v18->InterfaceGuid;
              v87 = *(_OWORD *)&v18->UsageData.UsageInMegabytes;
              v88 = *(_OWORD *)&v18->InboundBandwidthInKbps;
              v89 = *(_QWORD *)&v18->MaxTransferSizeInMegabytes;
              v75[0] = &v82;
              v75[1] = &v84;
              v29 = wil::ResultFromException__PublicNetworkListManager::ClientHandleIpHlpEvent_::_99_::_lambda_4___(v75);
              NetworkConnectionEnumRemote = v29;
              if ( v29 < 0
                && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  182,
                  &WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids,
                  (unsigned int)v29);
              }
              if ( !Value && v2 )
              {
                v2 = 0;
                v30 = 0;
                v92 = 0;
                v93 = 0;
                for ( i = *(__int64 **)v91; i != (__int64 *)v91; i = (__int64 *)*i )
                {
                  if ( i[2] == *(_QWORD *)&v21->Data1 && i[3] == *(_QWORD *)v21->Data4 )
                  {
                    v30 = *((_DWORD *)i + 8) + 1;
                    break;
                  }
                }
                v92 = *(_OWORD *)((char *)&v83[1] + (_QWORD)v72);
                v93 = v30;
                v72 = &v92;
                v32 = wil::ResultFromException__PublicNetworkListManager::ClientHandleIpHlpEvent_::_58_::_lambda_2___(&v72);
                NetworkConnectionEnumRemote = v32;
                if ( v32 < 0
                  && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                {
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    183,
                    &WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids,
                    (unsigned int)v32);
                }
                v9 = 0;
                v65 = 0;
                v14 = GUID_NULL;
                goto LABEL_66;
              }
              v2 = 0;
LABEL_64:
              v14 = GUID_NULL;
LABEL_65:
              v9 = (PublicNetworkListManager *)v65;
              goto LABEL_66;
            }
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_43;
            LastError = GetLastError();
            if ( LastError > 0 )
              LastError = (unsigned __int16)LastError | 0x80070000;
            v28 = 180;
          }
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v28,
            &WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids,
            (unsigned int)LastError);
          goto LABEL_43;
        }
LABEL_70:
        *(_DWORD *)(p_Type[2] + 184LL) = DERIVE_COST_FROM_COST_ARRAY(v83[0], v99);
        GetFirstValidDataPlanStatus(v83[0], v100, (struct NLM_DATAPLAN_STATUS *)(p_Type[2] + 188LL));
        v84 = *(_OWORD *)p_Type[2];
        v33 = 0;
        v90 = 0;
        v34 = 0;
        if ( v7 != *(_DWORD *)(p_Type[2] + 184LL) )
        {
          v33 = 1;
          LODWORD(v90) = 1;
          v85 = *(_DWORD *)(p_Type[2] + 184LL);
        }
        if ( memcmp_0(Buf1, (const void *)(p_Type[2] + 188LL), 0x38u) )
        {
          v34 = 1;
          HIDWORD(v90) = 1;
          v35 = p_Type[2];
          InterfaceGuid = *(GUID *)(v35 + 188);
          v87 = *(_OWORD *)(v35 + 204);
          v88 = *(_OWORD *)(v35 + 220);
          v89 = *(_QWORD *)(v35 + 236);
        }
        if ( v33 || v34 )
        {
          v76[0] = &v81;
          v76[1] = &v84;
          v36 = wil::ResultFromException__PublicNetworkListManager::ClientHandleIpHlpEvent_::_99_::_lambda_4___(v76);
          NetworkConnectionEnumRemote = v36;
          if ( v36 < 0 )
          {
            v37 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v38 = 185;
LABEL_95:
              WPP_SF_d(v37[2], v38, &WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids, (unsigned int)v36);
            }
          }
        }
      }
LABEL_99:
      v1 = (struct _RTL_CRITICAL_SECTION *)v74;
    }
  }
  v56 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        179,
        &WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids,
        (unsigned int)v3);
      goto LABEL_121;
    }
LABEL_122:
    if ( v56 != &WPP_GLOBAL_Control && (*((_BYTE *)v56 + 28) & 1) != 0 )
      WPP_SF_d(v56[2], 191, &WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids, (unsigned int)NetworkConnectionEnumRemote);
  }
LABEL_125:
  std::list<CLIENT_NODE_COST_DATA>::clear(&v82);
  std::list<CLIENT_NODE_COST_DATA>::clear(&v81);
  std::list<CLIENT_INTF_COUNTER>::clear(&v91);
  v57 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      192,
      &WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids,
      (unsigned int)NetworkConnectionEnumRemote);
  std::_List_node<CLIENT_INTF_COUNTER,void *>::_Free_non_head<std::allocator<std::_List_node<CLIENT_INTF_COUNTER,void *>>>(
    v57,
    v91);
  std::_Deallocate<16>((void *)v91, 0x28u);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v80);
  std::_List_node<CLIENT_NODE_COST_DATA,void *>::_Free_non_head<std::allocator<std::_List_node<CLIENT_NODE_COST_DATA,void *>>>(
    v58,
    v81);
  std::_Deallocate<16>((void *)v81, 0x68u);
  std::_List_node<CLIENT_NODE_COST_DATA,void *>::_Free_non_head<std::allocator<std::_List_node<CLIENT_NODE_COST_DATA,void *>>>(
    v59,
    v82);
  std::_Deallocate<16>((void *)v82, 0x68u);
  return (unsigned int)NetworkConnectionEnumRemote;
}

```

## disassembly

```asm
0x180020388  push    rbp
0x18002038a  push    rbx
0x18002038b  push    rsi
0x18002038c  push    rdi
0x18002038d  push    r12
0x18002038f  push    r13
0x180020391  push    r14
0x180020393  push    r15
0x180020395  lea     rbp, [rsp-748h]
0x18002039d  sub     rsp, 848h
0x1800203a4  mov     rax, cs:__security_cookie
0x1800203ab  xor     rax, rsp
0x1800203ae  mov     [rbp+780h+var_50], rax
0x1800203b5  mov     r13, rcx
0x1800203b8  mov     [rbp+780h+var_7B0], rcx
0x1800203bc  xor     r15d, r15d
0x1800203bf  mov     [rbp+780h+var_7F8], r15d
0x1800203c3  xorps   xmm0, xmm0
0x1800203c6  xor     eax, eax
0x1800203c8  movups  xmmword ptr [rbp+780h+var_658.InterfaceGuid.Data1], xmm0
0x1800203cf  movups  xmmword ptr [rbp+780h+var_658.UsageData.UsageInMegabytes], xmm0
0x1800203d6  movups  xmmword ptr [rbp+780h+var_658.InboundBandwidthInKbps], xmm0
0x1800203dd  mov     qword ptr [rbp+780h+var_658.MaxTransferSizeInMegabytes], rax
0x1800203e4  movups  [rbp+780h+var_730], xmm0
0x1800203e8  lea     rcx, [rbp+780h+var_730]
0x1800203ec  call    ??0?$list@UCLIENT_NODE_COST_DATA@@V?$allocator@UCLIENT_NODE_COST_DATA@@@std@@@std@@QEAA@XZ; std::list<CLIENT_NODE_COST_DATA>::list<CLIENT_NODE_COST_DATA>(void)
0x1800203f1  nop
0x1800203f2  xorps   xmm0, xmm0
0x1800203f5  movups  [rbp+780h+var_740], xmm0
0x1800203f9  lea     rcx, [rbp+780h+var_740]
0x1800203fd  call    ??0?$list@UCLIENT_NODE_COST_DATA@@V?$allocator@UCLIENT_NODE_COST_DATA@@@std@@@std@@QEAA@XZ; std::list<CLIENT_NODE_COST_DATA>::list<CLIENT_NODE_COST_DATA>(void)
0x180020402  nop
0x180020403  xorps   xmm0, xmm0
0x180020406  movups  [rbp+780h+var_6F0], xmm0
0x18002040d  mov     [rbp+780h+var_6E0], r15d
0x180020414  xorps   xmm1, xmm1
0x180020417  xor     eax, eax
0x180020419  movups  [rbp+780h+var_6DC], xmm1
0x180020420  movups  [rbp+780h+var_6CC], xmm1
0x180020427  movups  [rbp+780h+var_6BC], xmm1
0x18002042e  mov     [rbp+780h+var_6AC], rax
0x180020435  mov     [rbp+780h+var_6A4], r15
0x18002043c  mov     [rbp+780h+var_748], r15
0x180020440  xor     edx, edx; Val
0x180020442  mov     r8d, 548h; Size
0x180020448  lea     rcx, [rbp+780h+var_620]; void *
0x18002044f  call    memset_0
0x180020454  mov     [rbp+780h+var_7E8], r15d
0x180020458  xorps   xmm0, xmm0
0x18002045b  movups  [rbp+780h+var_7E4], xmm0
0x18002045f  movdqu  [rbp+780h+var_690], xmm0
0x180020467  mov     rdx, cs:qword_180060170
0x18002046e  mov     r8, rdx
0x180020471  mov     rdx, [rdx]
0x180020474  lea     rcx, [rbp+780h+var_690]
0x18002047b  call    ??$_Construct_range_unchecked@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@UCLIENT_INTF_COUNTER@@@std@@@std@@U_Iterator_base0@2@@std@@V12@@?$list@UCLIENT_INTF_COUNTER@@V?$allocator@UCLIENT_INTF_COUNTER@@@std@@@std@@AEAAXV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@UCLIENT_INTF_COUNTER@@@std@@@std@@U_Iterator_base0@2@@1@V21@@Z; std::list<CLIENT_INTF_COUNTER>::_Construct_range_unchecked<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<CLIENT_INTF_COUNTER>>,std::_Iterator_base0>,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<CLIENT_INTF_COUNTER>>,std::_Iterator_base0>>(std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<CLIENT_INTF_COUNTER>>,std::_Iterator_base0>,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<CLIENT_INTF_COUNTER>>,std::_Iterator_base0>)
0x180020480  nop
0x180020481  mov     [rbp+780h+var_720], r15d
0x180020485  xorps   xmm0, xmm0
0x180020488  movups  xmmword ptr [rbp+780h+var_720+4], xmm0
0x18002048c  movups  [rbp+780h+var_70C], xmm0
0x180020490  mov     [rbp+780h+var_6FC], r15d
0x180020497  movups  xmmword ptr [rbp+780h+pguid.Data1], xmm0
0x18002049e  lea     rsi, WPP_GLOBAL_Control
0x1800204a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800204ac  cmp     rcx, rsi
0x1800204af  jz      short loc_1800204CC
0x1800204b1  test    byte ptr [rcx+1Ch], 8
0x1800204b5  jz      short loc_1800204CC
0x1800204b7  mov     edx, 0B2h
0x1800204bc  lea     r8, WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids
0x1800204c3  mov     rcx, [rcx+10h]
0x1800204c7  call    WPP_SF_
0x1800204cc  lea     rcx, qword_180060170
0x1800204d3  call    ?clear@?$list@UCLIENT_INTF_COUNTER@@V?$allocator@UCLIENT_INTF_COUNTER@@@std@@@std@@QEAAXXZ; std::list<CLIENT_INTF_COUNTER>::clear(void)
0x1800204d8  lea     rcx, [rbp+780h+pguid]; pguid
0x1800204df  call    cs:__imp_CoCreateGuid
0x1800204e5  mov     r12d, eax
0x1800204e8  test    eax, eax
0x1800204ea  js      loc_180020F8E
0x1800204f0  lea     rdx, [rbp+780h+var_748]; struct IEnumNetworkConnections **
0x1800204f4  mov     rcx, r13; this
0x1800204f7  call    ?GetNetworkConnectionEnumRemote@PublicNetworkListManager@@AEAAJPEAPEAUIEnumNetworkConnections@@@Z; PublicNetworkListManager::GetNetworkConnectionEnumRemote(IEnumNetworkConnections * *)
0x1800204fc  mov     r12d, eax
0x1800204ff  test    eax, eax
0x180020501  js      loc_180020FB8
0x180020507  lea     rcx, [r13+230h]; lpCriticalSection
0x18002050e  call    cs:__imp_EnterCriticalSection
0x180020514  mov     rbx, [r13+258h]
0x18002051b  mov     rbx, [rbx]
0x18002051e  cmp     rbx, [r13+258h]
0x180020525  jz      loc_180020D35
0x18002052b  mov     r9, [rbx+10h]; struct ADDRESS_INTERFACE_DATA *
0x18002052f  mov     r14d, [r9+0B8h]
0x180020536  mov     [rbp+780h+var_7F4], r14d
0x18002053a  movups  xmm0, xmmword ptr [r9+0BCh]
0x180020542  movups  [rbp+780h+Buf1], xmm0
0x180020546  movups  xmm1, xmmword ptr [r9+0CCh]
0x18002054e  movups  [rbp+780h+var_778], xmm1
0x180020552  movups  xmm0, xmmword ptr [r9+0DCh]
0x18002055a  movups  [rbp+780h+var_768], xmm0
0x18002055e  movsd   xmm1, qword ptr [r9+0ECh]
0x180020567  movsd   [rbp+780h+var_758], xmm1
0x18002056c  lea     rdx, [r9+10h]; struct sockaddr_storage *
0x180020570  lea     rax, [rbp+780h+var_720]
0x180020574  mov     [rsp+880h+var_858], rax; struct INTERFACE_STACK *
0x180020579  mov     dword ptr [rsp+880h+var_860], 1; int
0x180020581  lea     r8, [rbp+780h+pguid]; struct _GUID *
0x180020588  mov     rcx, r13; this
0x18002058b  call    ?GetInterfaceStackPerDestination@PublicNetworkListManager@@AEAAJPEAUsockaddr_storage@@PEBU_GUID@@PEAUADDRESS_INTERFACE_DATA@@HPEAUINTERFACE_STACK@@@Z; PublicNetworkListManager::GetInterfaceStackPerDestination(sockaddr_storage *,_GUID const *,ADDRESS_INTERFACE_DATA *,int,INTERFACE_STACK *)
0x180020590  mov     r12d, eax
0x180020593  test    eax, eax
0x180020595  js      loc_180020B2D
0x18002059b  mov     [rbp+780h+var_7FC], 1
0x1800205a2  movups  xmm0, xmmword ptr [rbp+780h+var_720]
0x1800205a6  movups  xmm1, xmmword ptr [rbp+70h]
0x1800205aa  movsd   xmm2, qword ptr [rbp+780h+var_70C+0Ch]
0x1800205b2  mov     rax, [rbx+10h]
0x1800205b6  movups  xmmword ptr [rax+90h], xmm0
0x1800205bd  movups  xmmword ptr [rax+0A0h], xmm1
0x1800205c4  movsd   qword ptr [rax+0B0h], xmm2
0x1800205cc  mov     eax, r15d
0x1800205cf  mov     [rbp+780h+var_7F0], eax
0x1800205d2  cmp     [rbp+780h+var_720], r15d
0x1800205d6  jbe     loc_1800209ED
0x1800205dc  movups  xmm2, xmmword ptr cs:GUID_NULL.Data1
0x1800205e3  test    r12d, r12d
0x1800205e6  js      loc_180020D25
0x1800205ec  mov     r8d, eax
0x1800205ef  lea     rdi, [rbp+780h+var_D0]
0x1800205f6  lea     rdi, [rdi+r8*4]
0x1800205fa  mov     [rdi], r15d
0x1800205fd  imul    rax, r8, 38h ; '8'
0x180020601  lea     rsi, [rbp+780h+var_C0]
0x180020608  add     rsi, rax
0x18002060b  movdqu  xmmword ptr [rsi], xmm2
0x18002060f  or      r9d, 0FFFFFFFFh
0x180020613  mov     [rbp+rax+780h+var_C0.UsageData.UsageInMegabytes], r9d
0x18002061b  mov     qword ptr [rbp+rax+780h+var_C0.UsageData.LastSyncTime.dwLowDateTime], 0
0x180020627  mov     [rbp+rax+780h+var_C0.DataLimitInMegabytes], r9d
0x18002062f  mov     [rbp+rax+780h+var_C0.InboundBandwidthInKbps], r9d
0x180020637  mov     [rbp+rax+780h+var_C0.OutboundBandwidthInKbps], r9d
0x18002063f  mov     qword ptr [rbp+rax+780h+var_C0.NextBillingCycle.dwLowDateTime], 0
0x18002064b  mov     [rbp+rax+780h+var_C0.MaxTransferSizeInMegabytes], r9d
0x180020653  mov     [rbp+rax+780h+var_C0.Reserved], r15d
0x18002065b  mov     rax, qword ptr [rbp+780h+var_730]
0x18002065f  mov     edx, r8d
0x180020662  shl     rdx, 4
0x180020666  mov     rax, [rax]
0x180020669  mov     [rbp+780h+var_7D0], rdx
0x18002066d  lea     r14, [rbp+780h+var_720+4]
0x180020671  cmp     rax, qword ptr [rbp+780h+var_730]
0x180020675  jz      short loc_1800206BC
0x180020677  mov     rdx, r8
0x18002067a  shl     rdx, 4
0x18002067e  add     r14, rdx
0x180020681  mov     rcx, [rax+10h]
0x180020685  cmp     rcx, [r14]
0x180020688  jnz     short loc_180020666
0x18002068a  mov     rcx, [rax+18h]
0x18002068e  cmp     rcx, [r14+8]
0x180020692  jnz     short loc_180020666
0x180020694  mov     ecx, [rax+20h]
0x180020697  mov     [rdi], ecx
0x180020699  movups  xmm0, xmmword ptr [rax+24h]
0x18002069d  movups  xmmword ptr [rsi], xmm0
0x1800206a0  movups  xmm1, xmmword ptr [rax+34h]
0x1800206a4  movups  xmmword ptr [rsi+10h], xmm1
0x1800206a8  movups  xmm0, xmmword ptr [rax+44h]
0x1800206ac  movups  xmmword ptr [rsi+20h], xmm0
0x1800206b0  movsd   xmm1, qword ptr [rax+54h]
0x1800206b5  movsd   qword ptr [rsi+30h], xmm1
0x1800206ba  jmp     short loc_1800206BF
0x1800206bc  add     r14, rdx
0x1800206bf  cmp     [rdi], r9d
0x1800206c2  jnz     short loc_1800206CF
0x1800206c4  mov     ecx, r15d
0x1800206c7  mov     [rbp+780h+var_7FC], ecx
0x1800206ca  jmp     loc_1800209C7
0x1800206cf  cmp     rax, qword ptr [rbp+780h+var_730]
0x1800206d3  jnz     loc_1800209C4
0x1800206d9  mov     dword ptr [rbp+780h+InterfaceLuid], r15d
0x1800206dd  lea     rax, [rbp+780h+InterfaceLuid]
0x1800206e1  mov     [rsp+880h+var_850], rax; void *
0x1800206e6  mov     [rsp+880h+var_858], rsi; struct NLM_DATAPLAN_STATUS *
0x1800206eb  mov     [rsp+880h+var_860], rdi; unsigned int *
0x1800206f0  mov     r9, r14; struct _GUID *
0x1800206f3  mov     r8d, 1; unsigned int
0x1800206f9  mov     rdx, [rbp+780h+var_748]; struct IEnumNetworkConnections *
0x1800206fd  call    ?GetInterfaceCostAndDataPlanStatus@PublicNetworkListManager@@AEAAJPEAUIEnumNetworkConnections@@IPEAU_GUID@@PEAKPEAUNLM_DATAPLAN_STATUS@@PEAH@Z; PublicNetworkListManager::GetInterfaceCostAndDataPlanStatus(IEnumNetworkConnections *,uint,_GUID *,ulong *,NLM_DATAPLAN_STATUS *,int *)
0x180020702  mov     r12d, eax
0x180020705  test    eax, eax
0x180020707  js      loc_180020987
0x18002070d  mov     edi, [rdi]
0x18002070f  mov     r13d, dword ptr [rbp+780h+InterfaceLuid]
0x180020713  test    r13d, r13d
0x180020716  jnz     loc_180020826
0x18002071c  mov     qword ptr [rbp+780h+InterfaceLuid], 0
0x180020724  lea     rdx, [rbp+780h+InterfaceLuid]; InterfaceLuid
0x180020728  mov     rcx, r14; InterfaceGuid
0x18002072b  call    cs:__imp_ConvertInterfaceGuidToLuid
0x180020731  test    eax, eax
0x180020733  jnz     loc_1800207DC
0x180020739  mov     rax, qword ptr [rbp+780h+InterfaceLuid]
0x18002073d  mov     [rbp+780h+var_620], rax
0x180020744  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_NLM_Fix_DestinationCallbackDrainRace@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_NLM_Fix_DestinationCallbackDrainRace@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NLM_Fix_DestinationCallbackDrainRace> `wil::Feature<__WilFeatureTraits_Feature_NLM_Fix_DestinationCallbackDrainRace>::GetImpl(void)'::`2'::impl
0x18002074b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_NLM_Fix_DestinationCallbackDrainRace@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NLM_Fix_DestinationCallbackDrainRace>::__private_IsEnabled(void)
0x180020750  lea     rdx, [rbp+780h+var_620]
0x180020757  lea     ecx, [r13+2]
0x18002075b  test    al, al
0x18002075d  jz      short loc_18002076D
0x18002075f  mov     rax, cs:qword_180060580
0x180020766  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002076b  jmp     short loc_180020773
0x18002076d  call    cs:__imp_GetIfEntry2Ex
0x180020773  test    eax, eax
0x180020775  jnz     short loc_1800207AA
0x180020777  cmp     [rbp+780h+var_194], 1
0x18002077e  jnz     loc_180020826
0x180020784  cmp     [rbp+780h+var_1B8], 83h
0x18002078e  jz      loc_180020826
0x180020794  cmp     [rbp+780h+var_1B8], 18h
0x18002079b  jz      loc_180020826
0x1800207a1  lea     r15d, [rax+1]
0x1800207a5  or      edi, 0FFFFFFFFh
0x1800207a8  jmp     short loc_180020826
0x1800207aa  mov     rax, cs:WPP_GLOBAL_Control
0x1800207b1  lea     rcx, WPP_GLOBAL_Control
0x1800207b8  cmp     rax, rcx
0x1800207bb  jz      short loc_180020826
0x1800207bd  test    byte ptr [rax+1Ch], 1
0x1800207c1  jz      short loc_180020826
0x1800207c3  call    cs:__imp_GetLastError
0x1800207c9  test    eax, eax
0x1800207cb  jle     short loc_1800207D5
0x1800207cd  movzx   eax, ax
0x1800207d0  or      eax, 80070000h
0x1800207d5  mov     edx, 0B4h
0x1800207da  jmp     short loc_18002080C
0x1800207dc  mov     rax, cs:WPP_GLOBAL_Control
0x1800207e3  lea     rcx, WPP_GLOBAL_Control
0x1800207ea  cmp     rax, rcx
0x1800207ed  jz      short loc_180020826
0x1800207ef  test    byte ptr [rax+1Ch], 1
0x1800207f3  jz      short loc_180020826
0x1800207f5  call    cs:__imp_GetLastError
0x1800207fb  test    eax, eax
0x1800207fd  jle     short loc_180020807
0x1800207ff  movzx   eax, ax
0x180020802  or      eax, 80070000h
0x180020807  mov     edx, 0B5h
0x18002080c  mov     rcx, cs:WPP_GLOBAL_Control
0x180020813  mov     r9d, eax
0x180020816  lea     r8, WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids
0x18002081d  mov     rcx, [rcx+10h]
0x180020821  call    WPP_SF_d
0x180020826  mov     rax, [rbp+780h+var_7D0]
0x18002082a  movups  xmm0, xmmword ptr [rbp+rax+780h+var_720+4]
0x18002082f  movdqu  [rbp+780h+var_6F0], xmm0
0x180020837  mov     [rbp+780h+var_6E0], edi
0x18002083d  movups  xmm0, xmmword ptr [rsi]
0x180020840  movups  [rbp+780h+var_6DC], xmm0
0x180020847  movups  xmm1, xmmword ptr [rsi+10h]
0x18002084b  movups  [rbp+780h+var_6CC], xmm1
0x180020852  movups  xmm0, xmmword ptr [rsi+20h]
0x180020856  movups  [rbp+780h+var_6BC], xmm0
0x18002085d  movsd   xmm1, qword ptr [rsi+30h]
0x180020862  movsd   [rbp+780h+var_6AC], xmm1
0x18002086a  lea     rax, [rbp+780h+var_730]
0x18002086e  mov     [rbp+780h+var_7A8], rax
0x180020872  lea     rax, [rbp+780h+var_6F0]
0x180020879  mov     [rbp+780h+var_7A0], rax
0x18002087d  lea     rcx, [rbp+780h+var_7A8]
0x180020881  call    wil__ResultFromException__PublicNetworkListManager__ClientHandleIpHlpEvent____99____lambda_4___
0x180020886  mov     r12d, eax
0x180020889  test    eax, eax
0x18002088b  jns     short loc_1800208C0
0x18002088d  mov     rcx, cs:WPP_GLOBAL_Control
0x180020894  lea     rdi, WPP_GLOBAL_Control
0x18002089b  cmp     rcx, rdi
0x18002089e  jz      short loc_1800208C7
0x1800208a0  test    byte ptr [rcx+1Ch], 1
0x1800208a4  jz      short loc_1800208C7
0x1800208a6  mov     edx, 0B6h
0x1800208ab  mov     r9d, eax
0x1800208ae  lea     r8, WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids
0x1800208b5  mov     rcx, [rcx+10h]
0x1800208b9  call    WPP_SF_d
0x1800208be  jmp     short loc_1800208C7
0x1800208c0  lea     rdi, WPP_GLOBAL_Control
0x1800208c7  test    r13d, r13d
0x1800208ca  jnz     loc_1800209BA
0x1800208d0  test    r15d, r15d
0x1800208d3  jz      loc_1800209BA
0x1800208d9  xor     r15d, r15d
0x1800208dc  mov     edx, r15d
0x1800208df  xorps   xmm0, xmm0
0x1800208e2  movups  [rbp+780h+var_680], xmm0
0x1800208e9  mov     [rbp+780h+var_670], r15d
0x1800208f0  mov     r8, qword ptr [rbp+780h+var_690]
  ... truncated ...
```
