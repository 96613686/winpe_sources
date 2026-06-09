# PublicNetworkListManager::GetInterfaceStackPerDestination(sockaddr_storage *,_GUID const *,ADDRESS_INTERFACE_DATA *,int,INTERFACE_STACK *)

- ea: `0x180025b74`
- end: `0x1800262c9`
- name: `?GetInterfaceStackPerDestination@PublicNetworkListManager@@AEAAJPEAUsockaddr_storage@@PEBU_GUID@@PEAUADDRESS_INTERFACE_DATA@@HPEAUINTERFACE_STACK@@@Z`
- size: `1877`
- prototype: `int(PublicNetworkListManager *__hidden this, struct sockaddr_storage *, const struct _GUID *, struct ADDRESS_INTERFACE_DATA *, int, struct INTERFACE_STACK *)`
- caller_count: `3`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x180020388`
- `0x180024730`
- `0x180025390`

## callees

- `0x180006770`
- `0x180006810`
- `0x180008f10`
- `0x18000aa1c`
- `0x18000bf34`
- `0x1800120d0`
- `0x180012f40`
- `0x180023150`
- `0x180025b74`
- `0x18002a978`
- `0x180033ac4`
- `0x180043010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800261ef`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800261ef`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180025c50`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180025c50`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002626d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002626d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180025c95`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180025c95`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x180026086`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x180026086`
- `IPHLPAPI!CloseGetIPPhysicalInterfaceForDestination` at `0x180025d17`
- `IPHLPAPI!CloseGetIPPhysicalInterfaceForDestination` at `0x18002622f`
- `IPHLPAPI!CloseGetIPPhysicalInterfaceForDestination` at `0x180025d17`
- `IPHLPAPI!CloseGetIPPhysicalInterfaceForDestination` at `0x18002622f`
- `IPHLPAPI!InternalGetIPPhysicalInterfaceForDestination` at `0x180025fc7`
- `IPHLPAPI!InternalGetIPPhysicalInterfaceForDestination` at `0x180025fc7`
- `IPHLPAPI!GetIfEntry2Ex` at `0x180025e6e`
- `IPHLPAPI!GetIfEntry2Ex` at `0x1800260c8`
- `IPHLPAPI!GetIfEntry2Ex` at `0x180025e6e`
- `IPHLPAPI!GetIfEntry2Ex` at `0x1800260c8`
- `IPHLPAPI!GetBestInterfaceEx` at `0x180025de5`
- `IPHLPAPI!GetBestInterfaceEx` at `0x180025de5`

## pseudocode

```c
__int64 __fastcall PublicNetworkListManager::GetInterfaceStackPerDestination(
        PublicNetworkListManager *this,
        struct sockaddr *a2,
        const struct _GUID *a3,
        struct ADDRESS_INTERFACE_DATA *a4,
        int a5,
        struct INTERFACE_STACK *a6)
{
  PVOID *v9; // rcx
  unsigned int v10; // ebx
  __int64 v11; // rdx
  __int64 AddressInListNoLock; // rax
  struct ADDRESS_INTERFACE_DATA *v13; // rax
  char IsEnabled; // al
  char *v15; // rcx
  unsigned int IPPhysicalInterfaceForDestination; // eax
  signed int BestInterface; // eax
  _QWORD *v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // r9
  int IfEntry2; // eax
  __int64 v22; // rdx
  __int64 v23; // r8
  char *v24; // r13
  PublicNetworkListManager *v25; // rax
  unsigned int NdisPhysicalInterface; // eax
  bool v27; // cc
  char v29; // al
  char *v30; // rcx
  unsigned int v31; // eax
  char *v33; // [rsp+30h] [rbp-D0h]
  int v34; // [rsp+40h] [rbp-C0h] BYREF
  const struct _GUID *v35; // [rsp+48h] [rbp-B8h]
  PublicNetworkListManager *v36; // [rsp+50h] [rbp-B0h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+58h] [rbp-A8h]
  DWORD pdwBestIfIndex; // [rsp+60h] [rbp-A0h] BYREF
  NET_LUID InterfaceLuid; // [rsp+68h] [rbp-98h] BYREF
  GUID InterfaceGuid; // [rsp+70h] [rbp-90h] BYREF
  union _NET_LUID_LH v41; // [rsp+80h] [rbp-80h] BYREF
  DWORD v42; // [rsp+88h] [rbp-78h]
  _OWORD v43[69]; // [rsp+8Ch] [rbp-74h] BYREF
  int v44; // [rsp+4E8h] [rbp+3E8h]
  int v45; // [rsp+4ECh] [rbp+3ECh]
  int v46; // [rsp+50Ch] [rbp+40Ch]
  _QWORD v47[141]; // [rsp+5D0h] [rbp+4D0h] BYREF
  int v48; // [rsp+A38h] [rbp+938h]
  int v49; // [rsp+A40h] [rbp+940h]
  int v50; // [rsp+A44h] [rbp+944h]
  char v51; // [rsp+A50h] [rbp+950h]

  v35 = a3;
  InterfaceLuid.Value = (ULONG64)a2;
  v36 = this;
  memset_0(&v41, 0, 0x548u);
  pdwBestIfIndex = 0;
  InterfaceGuid = 0;
  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 124, &WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids);
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !a6 )
  {
    v10 = -2147467261;
    if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 1) != 0 )
    {
      v11 = 125;
LABEL_128:
      WPP_SF_d(v9[2], v11, &WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids, v10);
      return v10;
    }
    return v10;
  }
  lpCriticalSection = (LPCRITICAL_SECTION)((char *)this + 560);
  EnterCriticalSection((LPCRITICAL_SECTION)this + 14);
  if ( a4 )
    goto LABEL_11;
  AddressInListNoLock = PublicNetworkListManager::FindAddressInListNoLock(this, &v34, a2);
  if ( *(_QWORD *)AddressInListNoLock != *((_QWORD *)this + 75) )
  {
    a4 = *(struct ADDRESS_INTERFACE_DATA **)(*(_QWORD *)AddressInListNoLock + 16LL);
LABEL_11:
    v34 = 1;
    goto LABEL_17;
  }
  v34 = 0;
  v13 = (struct ADDRESS_INTERFACE_DATA *)CoTaskMemAlloc(0x150u);
  a4 = v13;
  if ( !v13 )
  {
    v10 = -2147024882;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 126, &WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids);
    goto LABEL_113;
  }
  memset_0(v13, 0, 0x150u);
LABEL_17:
  v10 = 0;
  if ( *((_QWORD *)a4 + 41) )
  {
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_NLM_Fix_DestinationCallbackDrainRace>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_NLM_Fix_DestinationCallbackDrainRace>::GetImpl'::`2'::impl);
    v15 = (char *)a4 + 328;
    if ( IsEnabled )
      IPPhysicalInterfaceForDestination = ((__int64 (__fastcall *)(char *))qword_180060590)(v15);
    else
      IPPhysicalInterfaceForDestination = CloseGetIPPhysicalInterfaceForDestination(v15);
    if ( IPPhysicalInterfaceForDestination
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        127,
        &WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids,
        IPPhysicalInterfaceForDestination);
    }
    *((_QWORD *)a4 + 41) = 0;
    *(GUID *)((char *)a4 + 248) = GUID_NULL;
  }
  if ( !a5 && v34 && *((_DWORD *)a4 + 45) && _InterlockedCompareExchange((volatile signed __int32 *)this + 165, 1, 1) )
  {
    *(_OWORD *)a6 = *((_OWORD *)a4 + 9);
    *((_OWORD *)a6 + 1) = *((_OWORD *)a4 + 10);
    *((_QWORD *)a6 + 4) = *((_QWORD *)a4 + 22);
    goto LABEL_113;
  }
  *(_DWORD *)a6 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_NLM_Fix_DestinationCallbackDrainRace>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_NLM_Fix_DestinationCallbackDrainRace>::GetImpl'::`2'::impl) )
    BestInterface = g_publicNetworkListManagerShim(a2, &pdwBestIfIndex);
  else
    BestInterface = GetBestInterfaceEx(a2, &pdwBestIfIndex);
  if ( BestInterface )
  {
    if ( BestInterface > 0 )
      v10 = (unsigned __int16)BestInterface | 0x80070000;
    else
      v10 = BestInterface;
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v19 = 128;
LABEL_41:
      v20 = v10;
LABEL_42:
      WPP_SF_d(v18[2], v19, &WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids, v20);
      goto LABEL_113;
    }
    goto LABEL_113;
  }
  v42 = pdwBestIfIndex;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_NLM_Fix_DestinationCallbackDrainRace>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_NLM_Fix_DestinationCallbackDrainRace>::GetImpl'::`2'::impl) )
    IfEntry2 = ((__int64 (__fastcall *)(__int64, union _NET_LUID_LH *))qword_180060580)(2, &v41);
  else
    IfEntry2 = GetIfEntry2Ex(2, &v41);
  if ( !IfEntry2 )
  {
    if ( v46 != 1 )
    {
      v10 = -2147019873;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF__guid_D(*((_QWORD *)WPP_GLOBAL_Control + 2), v22, v23, v43);
      goto LABEL_113;
    }
    v24 = 0;
    *(_OWORD *)((char *)a6 + 4) = v43[0];
    ++*(_DWORD *)a6;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF__guid_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v22, v23, v43, v44, v45);
    if ( v34 )
    {
      v24 = (char *)a4 + 248;
      v25 = v36;
      *(struct _GUID *)((char *)a4 + 248) = *v35;
      *(_OWORD *)((char *)a4 + 264) = *(_OWORD *)a4;
      *(_OWORD *)((char *)a4 + 280) = *(_OWORD *)a6;
      *(_OWORD *)((char *)a4 + 296) = *((_OWORD *)a6 + 1);
      *((_QWORD *)a4 + 39) = *((_QWORD *)a6 + 4);
      *((_QWORD *)a4 + 40) = v25;
    }
    v33 = (char *)a4 + 328;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_NLM_Fix_DestinationCallbackDrainRace>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_NLM_Fix_DestinationCallbackDrainRace>::GetImpl'::`2'::impl) )
      NdisPhysicalInterface = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))qword_180060588)(
                                (NET_LUID)InterfaceLuid.Value,
                                0,
                                0,
                                &InterfaceGuid,
                                v24,
                                GetDestIPPhysicalInterfaceCallback,
                                v33);
    else
      NdisPhysicalInterface = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))InternalGetIPPhysicalInterfaceForDestination)(
                                (NET_LUID)InterfaceLuid.Value,
                                0,
                                0,
                                &InterfaceGuid,
                                v24,
                                GetDestIPPhysicalInterfaceCallback,
                                v33);
    if ( NdisPhysicalInterface )
    {
      if ( NdisPhysicalInterface == 997 )
      {
        v27 = 0;
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            132,
            &WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids,
            NdisPhysicalInterface);
        NdisPhysicalInterface = GetNdisPhysicalInterface(&v41, &InterfaceGuid);
        v27 = (int)NdisPhysicalInterface <= 0;
        if ( !NdisPhysicalInterface )
          goto LABEL_107;
      }
      if ( v27 )
        v10 = NdisPhysicalInterface;
      else
        v10 = (unsigned __int16)NdisPhysicalInterface | 0x80070000;
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v19 = 134;
        v20 = NdisPhysicalInterface;
        goto LABEL_42;
      }
      goto LABEL_113;
    }
    InterfaceLuid.Value = 0;
    memset_0(v47, 0, 0x548u);
    if ( !ConvertInterfaceGuidToLuid(&InterfaceGuid, &InterfaceLuid) )
    {
      v47[0] = InterfaceLuid.Value;
      if ( !((unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_NLM_Fix_DestinationCallbackDrainRace>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_NLM_Fix_DestinationCallbackDrainRace>::GetImpl'::`2'::impl)
           ? ((__int64 (__fastcall *)(__int64, _QWORD *))qword_180060580)(2, v47)
           : (unsigned int)GetIfEntry2Ex(2, v47)) )
      {
        if ( (v51 & 2) != 0 )
        {
LABEL_103:
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF__guid_(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              133,
              &WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids,
              &InterfaceGuid);
          v10 = -2147024894;
          goto LABEL_113;
        }
        if ( v48 == 6 || v48 == 23 || v48 != 71 && (v48 == 131 || v48 != 237 && (unsigned int)(v48 - 243) >= 2) )
        {
          if ( v50 )
          {
            if ( v50 != 9 )
            {
              if ( v50 == 10 || v50 == 12 )
                goto LABEL_107;
              if ( v50 != 14 && (v50 != 19 || v49) )
                goto LABEL_103;
            }
          }
          else if ( v49 && v49 != 15 )
          {
            goto LABEL_103;
          }
          if ( (v51 & 1) == 0 || (v51 & 4) == 0 )
            goto LABEL_103;
        }
      }
    }
LABEL_107:
    if ( *(_QWORD *)((char *)a6 + 4) != *(_QWORD *)&InterfaceGuid.Data1
      || *(_QWORD *)((char *)a6 + 12) != *(_QWORD *)InterfaceGuid.Data4 )
    {
      *(GUID *)((char *)a6 + 20) = InterfaceGuid;
      ++*(_DWORD *)a6;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF__guid_(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          135,
          &WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids,
          &InterfaceGuid);
    }
    *((_DWORD *)a6 + 9) = 1;
    goto LABEL_113;
  }
  if ( IfEntry2 > 0 )
    v10 = (unsigned __int16)IfEntry2 | 0x80070000;
  else
    v10 = IfEntry2;
  v18 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v19 = 129;
    goto LABEL_41;
  }
LABEL_113:
  LeaveCriticalSection(lpCriticalSection);
  if ( !v34 && a4 )
  {
    if ( *((_QWORD *)a4 + 41) )
    {
      v29 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_NLM_Fix_DestinationCallbackDrainRace>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_NLM_Fix_DestinationCallbackDrainRace>::GetImpl'::`2'::impl);
      v30 = (char *)a4 + 328;
      if ( v29 )
        v31 = ((__int64 (__fastcall *)(char *))qword_180060590)(v30);
      else
        v31 = CloseGetIPPhysicalInterfaceForDestination(v30);
      if ( v31 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 136, &WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids, v31);
      *((_QWORD *)a4 + 41) = 0;
    }
    CoTaskMemFree(a4);
  }
  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    v11 = 137;
    goto LABEL_128;
  }
  return v10;
}

```

## disassembly

```asm
0x180025b74  mov     [rsp-8+arg_10], rbx
0x180025b79  push    rbp
0x180025b7a  push    rsi
0x180025b7b  push    rdi
0x180025b7c  push    r12
0x180025b7e  push    r13
0x180025b80  push    r14
0x180025b82  push    r15
0x180025b84  lea     rbp, [rsp-0A30h]
0x180025b8c  sub     rsp, 0B30h
0x180025b93  mov     rax, cs:__security_cookie
0x180025b9a  xor     rax, rsp
0x180025b9d  mov     [rbp+0A60h+var_40], rax
0x180025ba4  mov     rsi, [rbp+0A60h+arg_28]
0x180025bab  mov     r13, rdx
0x180025bae  mov     [rsp+0B60h+var_B18], r8
0x180025bb3  mov     r15, rcx
0x180025bb6  mov     qword ptr [rsp+0B60h+InterfaceLuid], rdx
0x180025bbb  mov     r8d, 548h; Size
0x180025bc1  mov     [rsp+0B60h+var_B10], rcx
0x180025bc6  xor     edx, edx; Val
0x180025bc8  lea     rcx, [rbp+0A60h+var_AE0]; void *
0x180025bcc  mov     r14, r9
0x180025bcf  call    memset_0
0x180025bd4  xorps   xmm0, xmm0
0x180025bd7  mov     [rsp+0B60h+pdwBestIfIndex], 0
0x180025bdf  movups  xmmword ptr [rsp+0B60h+InterfaceGuid.Data1], xmm0
0x180025be4  mov     rcx, cs:WPP_GLOBAL_Control
0x180025beb  lea     r12, WPP_GLOBAL_Control
0x180025bf2  cmp     rcx, r12
0x180025bf5  jz      short loc_180025C19
0x180025bf7  test    byte ptr [rcx+1Ch], 8
0x180025bfb  jz      short loc_180025C19
0x180025bfd  mov     rcx, [rcx+10h]
0x180025c01  lea     r8, WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids
0x180025c08  mov     edx, 7Ch ; '|'
0x180025c0d  call    WPP_SF_
0x180025c12  mov     rcx, cs:WPP_GLOBAL_Control
0x180025c19  test    rsi, rsi
0x180025c1c  jnz     short loc_180025C41
0x180025c1e  mov     ebx, 80004003h
0x180025c23  cmp     rcx, r12
0x180025c26  jz      loc_18002629D
0x180025c2c  lea     edi, [rsi+1]
0x180025c2f  test    [rcx+1Ch], dil
0x180025c33  jz      loc_18002629D
0x180025c39  lea     edx, [rsi+7Dh]
0x180025c3c  jmp     loc_18002628A
0x180025c41  lea     rax, [r15+230h]
0x180025c48  mov     rcx, rax; lpCriticalSection
0x180025c4b  mov     [rsp+0B60h+lpCriticalSection], rax
0x180025c50  call    cs:__imp_EnterCriticalSection
0x180025c56  mov     edi, 1
0x180025c5b  test    r14, r14
0x180025c5e  jnz     short loc_180025C80
0x180025c60  mov     r8, r13
0x180025c63  lea     rdx, [rsp+0B60h+var_B20]
0x180025c68  mov     rcx, r15
0x180025c6b  call    ?FindAddressInListNoLock@PublicNetworkListManager@@AEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@PEAUADDRESS_INTERFACE_DATA@@@std@@@std@@@std@@PEAUsockaddr_storage@@@Z; PublicNetworkListManager::FindAddressInListNoLock(sockaddr_storage *)
0x180025c70  mov     r14, [rax]
0x180025c73  cmp     r14, [r15+258h]
0x180025c7a  jz      short loc_180025C86
0x180025c7c  mov     r14, [r14+10h]
0x180025c80  mov     [rsp+0B60h+var_B20], edi
0x180025c84  jmp     short loc_180025CE7
0x180025c86  mov     ebx, 150h
0x180025c8b  mov     [rsp+0B60h+var_B20], 0
0x180025c93  mov     ecx, ebx; cb
0x180025c95  call    cs:__imp_CoTaskMemAlloc
0x180025c9b  mov     r14, rax
0x180025c9e  test    rax, rax
0x180025ca1  jnz     short loc_180025CDA
0x180025ca3  mov     ebx, 8007000Eh
0x180025ca8  mov     rcx, cs:WPP_GLOBAL_Control
0x180025caf  cmp     rcx, r12
0x180025cb2  jz      loc_1800261EA
0x180025cb8  test    [rcx+1Ch], dil
0x180025cbc  jz      loc_1800261EA
0x180025cc2  mov     rcx, [rcx+10h]
0x180025cc6  lea     edx, [rax+7Eh]
0x180025cc9  lea     r8, WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids
0x180025cd0  call    WPP_SF_
0x180025cd5  jmp     loc_1800261EA
0x180025cda  mov     r8, rbx; Size
0x180025cdd  xor     edx, edx; Val
0x180025cdf  mov     rcx, rax; void *
0x180025ce2  call    memset_0
0x180025ce7  xor     ebx, ebx
0x180025ce9  lea     r12, [r14+148h]
0x180025cf0  cmp     [r12], rbx
0x180025cf4  jz      short loc_180025D66
0x180025cf6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_NLM_Fix_DestinationCallbackDrainRace@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_NLM_Fix_DestinationCallbackDrainRace@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NLM_Fix_DestinationCallbackDrainRace> `wil::Feature<__WilFeatureTraits_Feature_NLM_Fix_DestinationCallbackDrainRace>::GetImpl(void)'::`2'::impl
0x180025cfd  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_NLM_Fix_DestinationCallbackDrainRace@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NLM_Fix_DestinationCallbackDrainRace>::__private_IsEnabled(void)
0x180025d02  mov     rcx, r12
0x180025d05  test    al, al
0x180025d07  jz      short loc_180025D17
0x180025d09  mov     rax, cs:qword_180060590
0x180025d10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025d15  jmp     short loc_180025D1D
0x180025d17  call    cs:__imp_CloseGetIPPhysicalInterfaceForDestination
0x180025d1d  test    eax, eax
0x180025d1f  jz      short loc_180025D52
0x180025d21  mov     rcx, cs:WPP_GLOBAL_Control
0x180025d28  lea     rdx, WPP_GLOBAL_Control
0x180025d2f  cmp     rcx, rdx
0x180025d32  jz      short loc_180025D52
0x180025d34  test    [rcx+1Ch], dil
0x180025d38  jz      short loc_180025D52
0x180025d3a  mov     rcx, [rcx+10h]
0x180025d3e  lea     r8, WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids
0x180025d45  mov     edx, 7Fh
0x180025d4a  mov     r9d, eax
0x180025d4d  call    WPP_SF_d
0x180025d52  mov     [r12], rbx
0x180025d56  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180025d5d  movdqu  xmmword ptr [r14+0F8h], xmm0
0x180025d66  cmp     [rbp+0A60h+arg_20], ebx
0x180025d6c  jnz     short loc_180025DBD
0x180025d6e  cmp     [rsp+0B60h+var_B20], ebx
0x180025d72  jz      short loc_180025DBD
0x180025d74  cmp     [r14+0B4h], ebx
0x180025d7b  jz      short loc_180025DBD
0x180025d7d  mov     eax, edi
0x180025d7f  lock cmpxchg [r15+294h], edi
0x180025d88  test    eax, eax
0x180025d8a  jz      short loc_180025DBD
0x180025d8c  movups  xmm0, xmmword ptr [r14+90h]
0x180025d94  lea     r12, WPP_GLOBAL_Control
0x180025d9b  movups  xmmword ptr [rsi], xmm0
0x180025d9e  movups  xmm1, xmmword ptr [r14+0A0h]
0x180025da6  movups  xmmword ptr [rsi+10h], xmm1
0x180025daa  movsd   xmm0, qword ptr [r14+0B0h]
0x180025db3  movsd   qword ptr [rsi+20h], xmm0
0x180025db8  jmp     loc_1800261EA
0x180025dbd  mov     [rsi], ebx
0x180025dbf  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_NLM_Fix_DestinationCallbackDrainRace@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_NLM_Fix_DestinationCallbackDrainRace@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NLM_Fix_DestinationCallbackDrainRace> `wil::Feature<__WilFeatureTraits_Feature_NLM_Fix_DestinationCallbackDrainRace>::GetImpl(void)'::`2'::impl
0x180025dc6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_NLM_Fix_DestinationCallbackDrainRace@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NLM_Fix_DestinationCallbackDrainRace>::__private_IsEnabled(void)
0x180025dcb  lea     rdx, [rsp+0B60h+pdwBestIfIndex]; pdwBestIfIndex
0x180025dd0  mov     rcx, r13; pDestAddr
0x180025dd3  test    al, al
0x180025dd5  jz      short loc_180025DE5
0x180025dd7  mov     rax, cs:?g_publicNetworkListManagerShim@@3UPublicNetworkListManagerShim@@A; PublicNetworkListManagerShim g_publicNetworkListManagerShim
0x180025dde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025de3  jmp     short loc_180025DEB
0x180025de5  call    cs:__imp_GetBestInterfaceEx
0x180025deb  test    eax, eax
0x180025ded  jz      short loc_180025E3C
0x180025def  jg      short loc_180025DF5
0x180025df1  mov     ebx, eax
0x180025df3  jmp     short loc_180025DFE
0x180025df5  movzx   ebx, ax
0x180025df8  or      ebx, 80070000h
0x180025dfe  mov     rcx, cs:WPP_GLOBAL_Control
0x180025e05  lea     r12, WPP_GLOBAL_Control
0x180025e0c  cmp     rcx, r12
0x180025e0f  jz      loc_1800261EA
0x180025e15  test    [rcx+1Ch], dil
0x180025e19  jz      loc_1800261EA
0x180025e1f  mov     edx, 80h
0x180025e24  mov     r9d, ebx
0x180025e27  mov     rcx, [rcx+10h]
0x180025e2b  lea     r8, WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids
0x180025e32  call    WPP_SF_d
0x180025e37  jmp     loc_1800261EA
0x180025e3c  mov     eax, [rsp+0B60h+pdwBestIfIndex]
0x180025e40  mov     [rbp+0A60h+var_AD8], eax
0x180025e43  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_NLM_Fix_DestinationCallbackDrainRace@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_NLM_Fix_DestinationCallbackDrainRace@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NLM_Fix_DestinationCallbackDrainRace> `wil::Feature<__WilFeatureTraits_Feature_NLM_Fix_DestinationCallbackDrainRace>::GetImpl(void)'::`2'::impl
0x180025e4a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_NLM_Fix_DestinationCallbackDrainRace@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NLM_Fix_DestinationCallbackDrainRace>::__private_IsEnabled(void)
0x180025e4f  lea     rdx, [rbp+0A60h+var_AE0]
0x180025e53  mov     r15d, 2
0x180025e59  mov     ecx, r15d
0x180025e5c  test    al, al
0x180025e5e  jz      short loc_180025E6E
0x180025e60  mov     rax, cs:qword_180060580
0x180025e67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025e6c  jmp     short loc_180025E74
0x180025e6e  call    cs:__imp_GetIfEntry2Ex
0x180025e74  test    eax, eax
0x180025e76  jz      short loc_180025EB2
0x180025e78  jg      short loc_180025E7E
0x180025e7a  mov     ebx, eax
0x180025e7c  jmp     short loc_180025E87
0x180025e7e  movzx   ebx, ax
0x180025e81  or      ebx, 80070000h
0x180025e87  mov     rcx, cs:WPP_GLOBAL_Control
0x180025e8e  lea     r12, WPP_GLOBAL_Control
0x180025e95  cmp     rcx, r12
0x180025e98  jz      loc_1800261EA
0x180025e9e  test    [rcx+1Ch], dil
0x180025ea2  jz      loc_1800261EA
0x180025ea8  mov     edx, 81h
0x180025ead  jmp     loc_180025E24
0x180025eb2  cmp     [rbp+0A60h+var_654], edi
0x180025eb8  jz      short loc_180025EF2
0x180025eba  mov     ebx, 8007139Fh
0x180025ebf  mov     rcx, cs:WPP_GLOBAL_Control
0x180025ec6  lea     r12, WPP_GLOBAL_Control
0x180025ecd  cmp     rcx, r12
0x180025ed0  jz      loc_1800261EA
0x180025ed6  test    [rcx+1Ch], r15b
0x180025eda  jz      loc_1800261EA
0x180025ee0  mov     rcx, [rcx+10h]
0x180025ee4  lea     r9, [rbp+0A60h+var_AD4]
0x180025ee8  call    WPP_SF__guid_D
0x180025eed  jmp     loc_1800261EA
0x180025ef2  movups  xmm0, [rbp+0A60h+var_AD4]
0x180025ef6  xor     r13d, r13d
0x180025ef9  movdqu  xmmword ptr [rsi+4], xmm0
0x180025efe  add     [rsi], edi
0x180025f00  mov     rcx, cs:WPP_GLOBAL_Control
0x180025f07  lea     rax, WPP_GLOBAL_Control
0x180025f0e  cmp     rcx, rax
0x180025f11  jz      short loc_180025F3A
0x180025f13  test    byte ptr [rcx+1Ch], 4
0x180025f17  jz      short loc_180025F3A
0x180025f19  mov     eax, [rbp+0A60h+var_674]
0x180025f1f  lea     r9, [rbp+0A60h+var_AD4]
0x180025f23  mov     rcx, [rcx+10h]
0x180025f27  mov     dword ptr [rsp+0B60h+var_B38], eax
0x180025f2b  mov     eax, [rbp+0A60h+var_678]
0x180025f31  mov     dword ptr [rsp+0B60h+var_B40], eax
0x180025f35  call    WPP_SF__guid_dd
0x180025f3a  cmp     [rsp+0B60h+var_B20], ebx
0x180025f3e  jz      short loc_180025F84
0x180025f40  mov     rax, [rsp+0B60h+var_B18]
0x180025f45  lea     r13, [r14+0F8h]
0x180025f4c  movups  xmm0, xmmword ptr [rax]
0x180025f4f  mov     rax, [rsp+0B60h+var_B10]
0x180025f54  movdqu  xmmword ptr [r13+0], xmm0
0x180025f5a  movups  xmm1, xmmword ptr [r14]
0x180025f5e  movdqu  xmmword ptr [r13+10h], xmm1
0x180025f64  movups  xmm0, xmmword ptr [rsi]
0x180025f67  movups  xmmword ptr [r13+20h], xmm0
0x180025f6c  movups  xmm1, xmmword ptr [rsi+10h]
0x180025f70  movups  xmmword ptr [r13+30h], xmm1
0x180025f75  movsd   xmm0, qword ptr [rsi+20h]
0x180025f7a  movsd   qword ptr [r13+40h], xmm0
0x180025f80  mov     [r13+48h], rax
0x180025f84  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_NLM_Fix_DestinationCallbackDrainRace@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_NLM_Fix_DestinationCallbackDrainRace@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NLM_Fix_DestinationCallbackDrainRace> `wil::Feature<__WilFeatureTraits_Feature_NLM_Fix_DestinationCallbackDrainRace>::GetImpl(void)'::`2'::impl
0x180025f8b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_NLM_Fix_DestinationCallbackDrainRace@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NLM_Fix_DestinationCallbackDrainRace>::__private_IsEnabled(void)
0x180025f90  mov     rcx, qword ptr [rsp+0B60h+InterfaceLuid]
0x180025f95  lea     r9, [rsp+0B60h+InterfaceGuid]
0x180025f9a  mov     [rsp+0B60h+var_B30], r12
0x180025f9f  xor     r8d, r8d
0x180025fa2  xor     edx, edx
0x180025fa4  test    al, al
0x180025fa6  lea     rax, ?GetDestIPPhysicalInterfaceCallback@@YAXPEAXPEAU_GUID@@K@Z; GetDestIPPhysicalInterfaceCallback(void *,_GUID *,ulong)
0x180025fad  mov     [rsp+0B60h+var_B38], rax
0x180025fb2  mov     [rsp+0B60h+var_B40], r13
0x180025fb7  jz      short loc_180025FC7
0x180025fb9  mov     rax, cs:qword_180060588
0x180025fc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025fc5  jmp     short loc_180025FCD
0x180025fc7  call    cs:__imp_InternalGetIPPhysicalInterfaceForDestination
0x180025fcd  test    eax, eax
0x180025fcf  jz      loc_180026063
0x180025fd5  cmp     eax, 3E5h
0x180025fda  jz      short loc_180026024
0x180025fdc  mov     rcx, cs:WPP_GLOBAL_Control
0x180025fe3  lea     r12, WPP_GLOBAL_Control
0x180025fea  cmp     rcx, r12
0x180025fed  jz      short loc_18002600D
0x180025fef  test    byte ptr [rcx+1Ch], 8
0x180025ff3  jz      short loc_18002600D
0x180025ff5  mov     rcx, [rcx+10h]
0x180025ff9  lea     r8, WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids
0x180026000  mov     edx, 84h
0x180026005  mov     r9d, eax
0x180026008  call    WPP_SF_d
0x18002600d  lea     rdx, [rsp+0B60h+InterfaceGuid]; struct _GUID *
0x180026012  lea     rcx, [rbp+0A60h+var_AE0]; union _NET_LUID_LH *
0x180026016  call    ?GetNdisPhysicalInterface@@YAKAEBT_NET_LUID_LH@@PEAU_GUID@@@Z; GetNdisPhysicalInterface(_NET_LUID_LH const &,_GUID *)
0x18002601b  test    eax, eax
0x18002601d  jnz     short loc_18002602D
0x18002601f  jmp     loc_180026199
0x180026024  lea     r12, WPP_GLOBAL_Control
0x18002602b  test    eax, eax
0x18002602d  jg      short loc_180026033
0x18002602f  mov     ebx, eax
0x180026031  jmp     short loc_18002603C
0x180026033  movzx   ebx, ax
0x180026036  or      ebx, 80070000h
0x18002603c  mov     rcx, cs:WPP_GLOBAL_Control
0x180026043  cmp     rcx, r12
0x180026046  jz      loc_1800261EA
0x18002604c  test    [rcx+1Ch], dil
0x180026050  jz      loc_1800261EA
0x180026056  mov     edx, 86h
0x18002605b  mov     r9d, eax
0x18002605e  jmp     loc_180025E27
0x180026063  xor     edx, edx; Val
0x180026065  mov     qword ptr [rsp+0B60h+InterfaceLuid], rbx
0x18002606a  mov     r8d, 548h; Size
0x180026070  lea     rcx, [rbp+0A60h+var_590]; void *
0x180026077  call    memset_0
0x18002607c  lea     rdx, [rsp+0B60h+InterfaceLuid]; InterfaceLuid
0x180026081  lea     rcx, [rsp+0B60h+InterfaceGuid]; InterfaceGuid
0x180026086  call    cs:__imp_ConvertInterfaceGuidToLuid
0x18002608c  test    eax, eax
0x18002608e  jnz     loc_180026192
  ... truncated ...
```
