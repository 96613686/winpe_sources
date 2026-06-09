# GetBestInterfaceStack(INTERFACE_STACK_DATA *)

- ea: `0x18004a944`
- end: `0x18004b2a5`
- name: `?GetBestInterfaceStack@@YAKPEAUINTERFACE_STACK_DATA@@@Z`
- size: `2401`
- prototype: `unsigned int __fastcall(struct INTERFACE_STACK_DATA *)`
- caller_count: `1`
- callee_count: `26`
- tags: `service_task, broker_com_uri`

## callers

- `0x18004a894`

## callees

- `0x180009990`
- `0x18000ee14`
- `0x18000fab0`
- `0x180010340`
- `0x1800111b4`
- `0x1800120a0`
- `0x180012210`
- `0x180013470`
- `0x18001662c`
- `0x180016b80`
- `0x180016f1c`
- `0x180035270`
- `0x1800459ac`
- `0x180045a14`
- `0x18004a944`
- `0x18004b2ac`
- `0x18004e92c`
- `0x180051238`
- `0x180051afc`
- `0x18005f618`
- `0x1800a88a0`
- `0x1800a9738`
- `0x1800aba19`
- `0x1800ca330`
- `0x1800ca664`
- `0x1800cce0c`

## import_xrefs

- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18004adc7`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18004adc7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004aa90`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004b037`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004aa90`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004b037`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004aa50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004aa50`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18004aa46`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18004aa46`
- `IPHLPAPI!InternalGetIPPhysicalInterfaceForDestination` at `0x18004b07d`
- `IPHLPAPI!InternalGetIPPhysicalInterfaceForDestination` at `0x18004b07d`
- `IPHLPAPI!GetIfEntry2Ex` at `0x18004ac28`
- `IPHLPAPI!GetIfEntry2Ex` at `0x18004ac28`
- `IPHLPAPI!CloseGetIPPhysicalInterfaceForDestination` at `0x18004a9d6`
- `IPHLPAPI!CloseGetIPPhysicalInterfaceForDestination` at `0x18004a9d6`
- `IPHLPAPI!GetBestInterfaceEx` at `0x18004abba`
- `IPHLPAPI!GetBestInterfaceEx` at `0x18004abba`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetBestInterfaceStack(struct INTERFACE_STACK_DATA *a1)
{
  unsigned int IPPhysicalInterfaceForDestination; // eax
  DWORD LastError; // eax
  unsigned int InternetAddrList; // eax
  const char *v6; // r9
  unsigned int NdisPhysicalInterface; // ebx
  PVOID *v8; // r10
  __int64 v9; // rdx
  char v10; // r13
  unsigned int v11; // r12d
  DWORD BestInterface; // eax
  __int64 v13; // rdx
  int v14; // edx
  int v15; // r8d
  __int64 v16; // r8
  __int64 v17; // rbx
  __int64 v18; // r15
  __int64 v19; // r14
  __int64 v20; // rcx
  __int64 v21; // r8
  __int64 v22; // rbx
  char v23; // r14
  unsigned int v24; // eax
  int v25; // edx
  int v26; // r8d
  __int64 v27; // rax
  __int64 result; // rax
  int v29; // [rsp+28h] [rbp-760h]
  char v30; // [rsp+40h] [rbp-748h]
  union _NET_LUID_LH v31; // [rsp+48h] [rbp-740h] BYREF
  __int128 v32; // [rsp+50h] [rbp-738h] BYREF
  __int64 v33; // [rsp+60h] [rbp-728h]
  _BYTE v34[16]; // [rsp+68h] [rbp-720h] BYREF
  __int64 v35; // [rsp+78h] [rbp-710h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+80h] [rbp-708h] BYREF
  struct _GUID v37; // [rsp+88h] [rbp-700h] BYREF
  GUID Buf1; // [rsp+98h] [rbp-6F0h] BYREF
  _QWORD v39[3]; // [rsp+A8h] [rbp-6E0h] BYREF
  _BYTE v40[32]; // [rsp+C0h] [rbp-6C8h] BYREF
  _QWORD v41[3]; // [rsp+E0h] [rbp-6A8h] BYREF
  char v42; // [rsp+F8h] [rbp-690h]
  union _NET_LUID_LH v43; // [rsp+100h] [rbp-688h] BYREF
  int v44; // [rsp+108h] [rbp-680h]
  struct _GUID v45; // [rsp+10Ch] [rbp-67Ch] BYREF
  int v46; // [rsp+568h] [rbp-220h]
  unsigned int v47; // [rsp+56Ch] [rbp-21Ch]
  int v48; // [rsp+58Ch] [rbp-1FCh]
  _WORD v49[128]; // [rsp+650h] [rbp-138h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+788h] [rbp+0h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 95, &WPP_bec8c779ead031fcc66297531c43b631_Traceguids);
  *(_DWORD *)a1 = 0;
  *(GUID *)((char *)a1 + 4) = GUID_NULL;
  *(GUID *)((char *)a1 + 20) = GUID_NULL;
  if ( g_PhysicalInterfaceCallBackHandle )
  {
    IPPhysicalInterfaceForDestination = CloseGetIPPhysicalInterfaceForDestination(&g_PhysicalInterfaceCallBackHandle);
    if ( IPPhysicalInterfaceForDestination
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        96,
        &WPP_bec8c779ead031fcc66297531c43b631_Traceguids,
        IPPhysicalInterfaceForDestination);
    }
    g_PhysicalInterfaceCallBackHandle = 0;
    lpCriticalSection = 0;
    wil::EnterCriticalSection(&lpCriticalSection, &g_csInterfaceContext);
    g_physicalInterfaceResolutionContext = -1;
    if ( g_hPhysicalInterfaceCallbackTimeoutTimer )
    {
      if ( !DeleteTimerQueueTimer(g_hTimerQueue, g_hPhysicalInterfaceCallbackTimeoutTimer, (HANDLE)0xFFFFFFFFFFFFFFFFLL) )
      {
        LastError = GetLastError();
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 97, &WPP_bec8c779ead031fcc66297531c43b631_Traceguids, LastError);
      }
      g_hPhysicalInterfaceCallbackTimeoutTimer = 0;
    }
    if ( lpCriticalSection )
      LeaveCriticalSection(lpCriticalSection);
  }
  try
  {
    InternetAddrList = GetInternetAddrList();
    NdisPhysicalInterface = InternetAddrList;
    if ( InternetAddrList )
    {
      v8 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_118;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_115;
      v9 = 98;
      goto LABEL_21;
    }
    memset_0(v49, 0, sizeof(v49));
    InternetAddrList = GetPreferredAddress(2, &g_InternetAddrList, v49);
    NdisPhysicalInterface = InternetAddrList;
    if ( InternetAddrList )
    {
      v8 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_118;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_115;
      v9 = 99;
LABEL_21:
      WPP_SF_d(v8[2], v9, &WPP_bec8c779ead031fcc66297531c43b631_Traceguids, InternetAddrList);
      goto LABEL_114;
    }
    Buf1 = GUID_NULL;
    v31.Value = 0;
    v10 = 0;
    v30 = 1;
    v11 = 0;
    v8 = (PVOID *)WPP_GLOBAL_Control;
    while ( v11 < 2 )
    {
      if ( v10 )
        goto LABEL_81;
      if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 4) != 0 )
        WPP_SF_dd(
          v8[2],
          100,
          &WPP_bec8c779ead031fcc66297531c43b631_Traceguids,
          v11,
          (unsigned __int16)v49[64 * (unsigned __int64)v11]);
      LODWORD(lpCriticalSection) = 0;
      BestInterface = GetBestInterfaceEx(
                        (struct sockaddr *)&v49[64 * (unsigned __int64)v11],
                        (PDWORD)&lpCriticalSection);
      if ( BestInterface )
      {
        v8 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v13 = 101;
LABEL_36:
          WPP_SF_d(v8[2], v13, &WPP_bec8c779ead031fcc66297531c43b631_Traceguids, BestInterface);
LABEL_73:
          v8 = (PVOID *)WPP_GLOBAL_Control;
        }
      }
      else
      {
        memset_0(&v43, 0, 0x548u);
        v44 = (int)lpCriticalSection;
        BestInterface = GetIfEntry2Ex(2, &v43);
        if ( BestInterface )
        {
          v8 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v13 = 102;
            goto LABEL_36;
          }
        }
        else
        {
          if ( !memcmp_0(&Buf1, &GUID_NULL, 0x10u) )
          {
            Buf1 = v45;
            v31.Value = v43.Value;
          }
          v8 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            v29 = (int)lpCriticalSection;
            WPP_SF_d_guid_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, v15, v11, (__int64)&v45);
            v8 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( v48 == 1 )
          {
            if ( !NetworkPropertyMaps::IsInterfaceHidden(&v45) )
            {
              LOBYTE(v16) = 1;
              NetworkPropertyMaps::FindConnectedNetworksByInterface(v39, &v45, v16, 0);
              v17 = v39[0];
              v18 = v39[1];
              while ( v17 != v18 )
              {
                std::_Tree<std::_Tmap_traits<_GUID,INTERFACE_DATA,std::less<_GUID>,std::allocator<std::pair<_GUID const,INTERFACE_DATA>>,0>>::_Find_lower_bound<_GUID>(
                  v17 + 112,
                  v34);
                v19 = v35;
                if ( !(unsigned __int8)std::_Tree<std::_Tmap_traits<_GUID,NlmDomain::InterfaceInfo,std::less<_GUID>,std::allocator<std::pair<_GUID const,NlmDomain::InterfaceInfo>>,0>>::_Lower_bound_duplicate<_GUID>(
                                         v20,
                                         v35,
                                         &v45) )
                  std::_Xout_of_range("invalid map<K, T> key");
                v32 = *(_OWORD *)(v19 + 560);
                v33 = *(_QWORD *)(v19 + 576);
                if ( HasInternetCapability((const struct _NLA_INTERNET_CAPABILITY *)&v32) )
                {
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                    WPP_SF__guid_(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      106,
                      &WPP_bec8c779ead031fcc66297531c43b631_Traceguids,
                      &v45);
                  *(struct _GUID *)((char *)a1 + 4) = v45;
                  ++*(_DWORD *)a1;
                  v21 = (unsigned int)ConnectivityFlagsFromInternetCapability(&v32) | 1;
                  *((_DWORD *)a1 + 9) = v21;
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                    WPP_SF__guid_Ddd(*((_QWORD *)WPP_GLOBAL_Control + 2), v47, v21, &v45, v21, v46, v47);
                  NetworkPropertyMaps::GetInterfaceInfo(v40, &v45, 0);
                  if ( v42 )
                  {
                    if ( memcmp_0(v41, &GUID_NULL, 0x10u) )
                    {
                      *(_QWORD *)((char *)a1 + 20) = v41[0];
                      *(_QWORD *)((char *)a1 + 28) = v41[1];
                      ++*(_DWORD *)a1;
                      v30 = 0;
                      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                        WPP_SF__guid_(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          108,
                          &WPP_bec8c779ead031fcc66297531c43b631_Traceguids,
                          v41);
                    }
                  }
                  v10 = 1;
                  break;
                }
                v17 += 696;
              }
              std::vector<ACTIVE_NETWORK>::_Tidy(v39);
              goto LABEL_73;
            }
            v8 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            {
              WPP_SF__guid_(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                105,
                &WPP_bec8c779ead031fcc66297531c43b631_Traceguids,
                &v45);
              goto LABEL_73;
            }
          }
          else if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 2) != 0 )
          {
            WPP_SF__guid_D(v8[2], 104, &WPP_bec8c779ead031fcc66297531c43b631_Traceguids, &v45, 5023, v29);
            goto LABEL_73;
          }
        }
      }
      ++v11;
    }
    if ( !v10 )
    {
      if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 1) != 0 )
      {
        WPP_SF_(v8[2], 109, &WPP_bec8c779ead031fcc66297531c43b631_Traceguids);
        goto LABEL_79;
      }
      goto LABEL_80;
    }
LABEL_81:
    if ( !v30 )
    {
      NdisPhysicalInterface = 0;
      goto LABEL_115;
    }
    if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 4) != 0 )
      WPP_SF_(v8[2], 110, &WPP_bec8c779ead031fcc66297531c43b631_Traceguids);
    lpCriticalSection = 0;
    wil::EnterCriticalSection(&lpCriticalSection, &g_csInterfaceContext);
    v22 = ++g_physicalInterfaceResolutionContext;
    xmmword_1801C6DE8 = *(_OWORD *)a1;
    xmmword_1801C6DF8 = *((_OWORD *)a1 + 1);
    xmmword_1801C6E08 = *((_OWORD *)a1 + 2);
    xmmword_1801C6E18 = *((_OWORD *)a1 + 3);
    xmmword_1801C6E28 = *((_OWORD *)a1 + 4);
    xmmword_1801C6E38 = *((_OWORD *)a1 + 5);
    qword_1801C6E48 = *((_QWORD *)a1 + 12);
    if ( lpCriticalSection )
      LeaveCriticalSection(lpCriticalSection);
    v23 = 0;
    v37 = 0;
    v24 = InternalGetIPPhysicalInterfaceForDestination(
            v49,
            0,
            0,
            &v37,
            v22,
            NetworkListManager::GetIPPhysicalInterfaceCallback,
            &g_PhysicalInterfaceCallBackHandle);
    NdisPhysicalInterface = v24;
    if ( !v24 )
      goto LABEL_99;
    if ( v24 != 997 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_D_guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), v25, v26, v24, (__int64)&Buf1);
      NdisPhysicalInterface = GetNdisPhysicalInterface(&v31, &v37);
      v23 = 1;
      if ( !NdisPhysicalInterface )
      {
LABEL_99:
        v27 = *(_QWORD *)((char *)a1 + 4) - *(_QWORD *)&v37.Data1;
        if ( !v27 )
          v27 = *(_QWORD *)((char *)a1 + 12) - *(_QWORD *)v37.Data4;
        if ( v27 )
        {
          if ( !v23 )
          {
            LODWORD(lpCriticalSection) = 0;
            if ( (int)IsInterfaceConnectedOrPhysical(&v37, 0, (int *)&lpCriticalSection) >= 0 )
            {
              if ( !(_DWORD)lpCriticalSection )
              {
                v8 = (PVOID *)WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                {
                  WPP_SF__guid_(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    113,
                    &WPP_bec8c779ead031fcc66297531c43b631_Traceguids,
                    &v37);
LABEL_79:
                  v8 = (PVOID *)WPP_GLOBAL_Control;
                }
LABEL_80:
                NdisPhysicalInterface = 2;
                goto LABEL_115;
              }
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                WPP_SF__guid_(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  114,
                  &WPP_bec8c779ead031fcc66297531c43b631_Traceguids,
                  &v37);
            }
          }
          *(struct _GUID *)((char *)a1 + 20) = v37;
          ++*(_DWORD *)a1;
          v8 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
            goto LABEL_118;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
            goto LABEL_115;
          WPP_SF__guid_(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            115,
            &WPP_bec8c779ead031fcc66297531c43b631_Traceguids,
            &v37);
        }
LABEL_114:
        v8 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_115;
      }
    }
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        112,
        &WPP_bec8c779ead031fcc66297531c43b631_Traceguids,
        NdisPhysicalInterface);
      v8 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( NdisPhysicalInterface == 997 )
    {
      CreatePhysicalInterfaceTimer();
      goto LABEL_114;
    }
LABEL_115:
    if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 8) != 0 )
      WPP_SF_d(v8[2], 116, &WPP_bec8c779ead031fcc66297531c43b631_Traceguids, NdisPhysicalInterface);
LABEL_118:
    result = NdisPhysicalInterface;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x72B,
                           (unsigned int)"onecore\\net\\netprofiles\\service\\src\\host\\lib\\common.cpp",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x18004a944  mov     [rsp+arg_8], rbx
0x18004a949  mov     [rsp+arg_10], rsi
0x18004a94e  push    rdi
0x18004a94f  push    r12
0x18004a951  push    r13
0x18004a953  push    r14
0x18004a955  push    r15
0x18004a957  sub     rsp, 760h
0x18004a95e  mov     rax, cs:__security_cookie
0x18004a965  xor     rax, rsp
0x18004a968  mov     [rsp+788h+var_38], rax
0x18004a970  mov     rsi, rcx
0x18004a973  lea     r14, WPP_GLOBAL_Control
0x18004a97a  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a981  lea     rdi, WPP_bec8c779ead031fcc66297531c43b631_Traceguids
0x18004a988  cmp     rcx, r14
0x18004a98b  jz      short loc_18004A9A4
0x18004a98d  test    byte ptr [rcx+1Ch], 8
0x18004a991  jz      short loc_18004A9A4
0x18004a993  mov     edx, 5Fh ; '_'
0x18004a998  mov     r8, rdi
0x18004a99b  mov     rcx, [rcx+10h]
0x18004a99f  call    WPP_SF_
0x18004a9a4  xor     r15d, r15d
0x18004a9a7  mov     [rsi], r15d
0x18004a9aa  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18004a9b1  movdqu  xmmword ptr [rsi+4], xmm0
0x18004a9b6  movups  xmm1, xmmword ptr cs:GUID_NULL.Data1
0x18004a9bd  movdqu  xmmword ptr [rsi+14h], xmm1
0x18004a9c2  cmp     cs:?g_PhysicalInterfaceCallBackHandle@@3PEAXEA, r15; void * g_PhysicalInterfaceCallBackHandle
0x18004a9c9  jz      loc_18004AA96
0x18004a9cf  lea     rcx, ?g_PhysicalInterfaceCallBackHandle@@3PEAXEA; void * g_PhysicalInterfaceCallBackHandle
0x18004a9d6  call    cs:__imp_CloseGetIPPhysicalInterfaceForDestination
0x18004a9dc  test    eax, eax
0x18004a9de  jz      short loc_18004AA05
0x18004a9e0  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a9e7  cmp     rcx, r14
0x18004a9ea  jz      short loc_18004AA05
0x18004a9ec  test    byte ptr [rcx+1Ch], 1
0x18004a9f0  jz      short loc_18004AA05
0x18004a9f2  lea     edx, [r15+60h]
0x18004a9f6  mov     r9d, eax
0x18004a9f9  mov     r8, rdi
0x18004a9fc  mov     rcx, [rcx+10h]
0x18004aa00  call    WPP_SF_d
0x18004aa05  mov     cs:?g_PhysicalInterfaceCallBackHandle@@3PEAXEA, r15; void * g_PhysicalInterfaceCallBackHandle
0x18004aa0c  mov     [rsp+788h+lpCriticalSection], r15
0x18004aa14  lea     rdx, ?g_csInterfaceContext@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_csInterfaceContext
0x18004aa1b  lea     rcx, [rsp+788h+lpCriticalSection]
0x18004aa23  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x18004aa28  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18004aa2c  mov     cs:?g_physicalInterfaceResolutionContext@@3UPhysicalInterfaceResolutionContext@@A, r8; PhysicalInterfaceResolutionContext g_physicalInterfaceResolutionContext
0x18004aa33  mov     rdx, cs:?g_hPhysicalInterfaceCallbackTimeoutTimer@@3PEAXEA; Timer
0x18004aa3a  test    rdx, rdx
0x18004aa3d  jz      short loc_18004AA83
0x18004aa3f  mov     rcx, cs:?g_hTimerQueue@@3PEAXEA; TimerQueue
0x18004aa46  call    cs:__imp_DeleteTimerQueueTimer
0x18004aa4c  test    eax, eax
0x18004aa4e  jnz     short loc_18004AA7C
0x18004aa50  call    cs:__imp_GetLastError
0x18004aa56  mov     rcx, cs:WPP_GLOBAL_Control
0x18004aa5d  cmp     rcx, r14
0x18004aa60  jz      short loc_18004AA7C
0x18004aa62  test    byte ptr [rcx+1Ch], 1
0x18004aa66  jz      short loc_18004AA7C
0x18004aa68  mov     edx, 61h ; 'a'
0x18004aa6d  mov     r9d, eax
0x18004aa70  mov     r8, rdi
0x18004aa73  mov     rcx, [rcx+10h]
0x18004aa77  call    WPP_SF_d
0x18004aa7c  mov     cs:?g_hPhysicalInterfaceCallbackTimeoutTimer@@3PEAXEA, r15; void * g_hPhysicalInterfaceCallbackTimeoutTimer
0x18004aa83  mov     rcx, [rsp+788h+lpCriticalSection]; lpCriticalSection
0x18004aa8b  test    rcx, rcx
0x18004aa8e  jz      short loc_18004AA96
0x18004aa90  call    cs:__imp_LeaveCriticalSection
0x18004aa96  call    ?GetInternetAddrList@@YAKXZ; GetInternetAddrList(void)
0x18004aa9b  mov     ebx, eax
0x18004aa9d  test    eax, eax
0x18004aa9f  jz      short loc_18004AAD5
0x18004aaa1  mov     r10, cs:WPP_GLOBAL_Control
0x18004aaa8  cmp     r10, r14
0x18004aaab  jz      loc_18004B26C
0x18004aab1  test    byte ptr [r10+1Ch], 1
0x18004aab6  jz      loc_18004B24C
0x18004aabc  mov     edx, 62h ; 'b'
0x18004aac1  mov     r9d, eax
0x18004aac4  mov     r8, rdi
0x18004aac7  mov     rcx, [r10+10h]
0x18004aacb  call    WPP_SF_d
0x18004aad0  jmp     loc_18004B245
0x18004aad5  xor     edx, edx; Val
0x18004aad7  mov     r8d, 100h; Size
0x18004aadd  lea     rcx, [rsp+788h+var_138]; void *
0x18004aae5  call    memset_0
0x18004aaea  lea     r8, [rsp+788h+var_138]
0x18004aaf2  lea     rdx, ?g_InternetAddrList@@3V?$array@Usockaddr_in6@@$01@std@@A; std::array<sockaddr_in6,2> g_InternetAddrList
0x18004aaf9  mov     ecx, 2
0x18004aafe  call    GetPreferredAddress
0x18004ab03  mov     ebx, eax
0x18004ab05  test    eax, eax
0x18004ab07  jz      short loc_18004AB2B
0x18004ab09  mov     r10, cs:WPP_GLOBAL_Control
0x18004ab10  cmp     r10, r14
0x18004ab13  jz      loc_18004B26C
0x18004ab19  test    byte ptr [r10+1Ch], 1
0x18004ab1e  jz      loc_18004B24C
0x18004ab24  mov     edx, 63h ; 'c'
0x18004ab29  jmp     short loc_18004AAC1
0x18004ab2b  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18004ab32  movdqu  [rsp+788h+Buf1], xmm0
0x18004ab3b  mov     qword ptr [rsp+788h+var_740], r15
0x18004ab40  mov     r13b, r15b
0x18004ab43  mov     [rsp+788h+var_748], 1
0x18004ab48  mov     r12d, r15d
0x18004ab4b  mov     r10, cs:WPP_GLOBAL_Control
0x18004ab52  cmp     r12d, 2
0x18004ab56  jnb     loc_18004AF50
0x18004ab5c  test    r13b, r13b
0x18004ab5f  jnz     loc_18004AF83
0x18004ab65  cmp     r10, r14
0x18004ab68  jz      short loc_18004AB98
0x18004ab6a  test    byte ptr [r10+1Ch], 4
0x18004ab6f  jz      short loc_18004AB98
0x18004ab71  mov     eax, r12d
0x18004ab74  shl     rax, 7
0x18004ab78  movzx   ecx, [rsp+rax+788h+var_138]
0x18004ab80  mov     edx, 64h ; 'd'
0x18004ab85  mov     dword ptr [rsp+788h+var_768], ecx
0x18004ab89  mov     r9d, r12d
0x18004ab8c  mov     r8, rdi
0x18004ab8f  mov     rcx, [r10+10h]
0x18004ab93  call    WPP_SF_dd
0x18004ab98  mov     dword ptr [rsp+788h+lpCriticalSection], r15d
0x18004aba0  mov     eax, r12d
0x18004aba3  shl     rax, 7
0x18004aba7  lea     rcx, [rsp+788h+var_138]
0x18004abaf  add     rcx, rax; pDestAddr
0x18004abb2  lea     rdx, [rsp+788h+lpCriticalSection]; pdwBestIfIndex
0x18004abba  call    cs:__imp_GetBestInterfaceEx
0x18004abc0  test    eax, eax
0x18004abc2  jz      short loc_18004ABF8
0x18004abc4  mov     r10, cs:WPP_GLOBAL_Control
0x18004abcb  cmp     r10, r14
0x18004abce  jz      loc_18004AF48
0x18004abd4  test    byte ptr [r10+1Ch], 1
0x18004abd9  jz      loc_18004AF48
0x18004abdf  mov     edx, 65h ; 'e'
0x18004abe4  mov     r9d, eax
0x18004abe7  mov     r8, rdi
0x18004abea  mov     rcx, [r10+10h]
0x18004abee  call    WPP_SF_d
0x18004abf3  jmp     loc_18004AF41
0x18004abf8  xor     edx, edx; Val
0x18004abfa  mov     r8d, 548h; Size
0x18004ac00  lea     rcx, [rsp+788h+var_688]; void *
0x18004ac08  call    memset_0
0x18004ac0d  mov     eax, dword ptr [rsp+788h+lpCriticalSection]
0x18004ac14  mov     [rsp+788h+var_680], eax
0x18004ac1b  lea     rdx, [rsp+788h+var_688]
0x18004ac23  mov     ecx, 2
0x18004ac28  call    cs:__imp_GetIfEntry2Ex
0x18004ac2e  test    eax, eax
0x18004ac30  jz      short loc_18004AC54
0x18004ac32  mov     r10, cs:WPP_GLOBAL_Control
0x18004ac39  cmp     r10, r14
0x18004ac3c  jz      loc_18004AF48
0x18004ac42  test    byte ptr [r10+1Ch], 1
0x18004ac47  jz      loc_18004AF48
0x18004ac4d  mov     edx, 66h ; 'f'
0x18004ac52  jmp     short loc_18004ABE4
0x18004ac54  mov     r8d, 10h; Size
0x18004ac5a  lea     rdx, GUID_NULL; Buf2
0x18004ac61  lea     rcx, [rsp+788h+Buf1]; Buf1
0x18004ac69  call    memcmp_0
0x18004ac6e  test    eax, eax
0x18004ac70  jnz     short loc_18004AC90
0x18004ac72  movups  xmm0, xmmword ptr [rsp+788h+var_67C.Data1]
0x18004ac7a  movdqu  [rsp+788h+Buf1], xmm0
0x18004ac83  mov     rax, [rsp+788h+var_688]
0x18004ac8b  mov     qword ptr [rsp+788h+var_740], rax
0x18004ac90  mov     r10, cs:WPP_GLOBAL_Control
0x18004ac97  cmp     r10, r14
0x18004ac9a  jz      short loc_18004ACCE
0x18004ac9c  test    byte ptr [r10+1Ch], 4
0x18004aca1  jz      short loc_18004ACCE
0x18004aca3  mov     eax, dword ptr [rsp+788h+lpCriticalSection]
0x18004acaa  mov     dword ptr [rsp+788h+var_760], eax
0x18004acae  lea     rax, [rsp+788h+var_67C]
0x18004acb6  mov     [rsp+788h+var_768], rax
0x18004acbb  mov     r9d, r12d
0x18004acbe  mov     rcx, [r10+10h]
0x18004acc2  call    WPP_SF_d_guid_d
0x18004acc7  mov     r10, cs:WPP_GLOBAL_Control
0x18004acce  cmp     [rsp+788h+var_1FC], 1
0x18004acd6  jz      short loc_18004AD12
0x18004acd8  cmp     r10, r14
0x18004acdb  jz      loc_18004AF48
0x18004ace1  test    byte ptr [r10+1Ch], 2
0x18004ace6  jz      loc_18004AF48
0x18004acec  mov     edx, 68h ; 'h'
0x18004acf1  mov     dword ptr [rsp+788h+var_768], 139Fh
0x18004acf9  lea     r9, [rsp+788h+var_67C]
0x18004ad01  mov     r8, rdi
0x18004ad04  mov     rcx, [r10+10h]
0x18004ad08  call    WPP_SF__guid_D
0x18004ad0d  jmp     loc_18004AF41
0x18004ad12  lea     rcx, [rsp+788h+var_67C]; Buf1
0x18004ad1a  call    ?IsInterfaceHidden@NetworkPropertyMaps@@SA_NAEBU_GUID@@@Z; NetworkPropertyMaps::IsInterfaceHidden(_GUID const &)
0x18004ad1f  test    al, al
0x18004ad21  jz      short loc_18004AD5C
0x18004ad23  mov     r10, cs:WPP_GLOBAL_Control
0x18004ad2a  cmp     r10, r14
0x18004ad2d  jz      loc_18004AF48
0x18004ad33  test    byte ptr [r10+1Ch], 4
0x18004ad38  jz      loc_18004AF48
0x18004ad3e  mov     edx, 69h ; 'i'
0x18004ad43  lea     r9, [rsp+788h+var_67C]
0x18004ad4b  mov     r8, rdi
0x18004ad4e  mov     rcx, [r10+10h]
0x18004ad52  call    WPP_SF__guid_
0x18004ad57  jmp     loc_18004AF41
0x18004ad5c  xor     r9d, r9d
0x18004ad5f  mov     r8b, 1
0x18004ad62  lea     rdx, [rsp+788h+var_67C]
0x18004ad6a  lea     rcx, [rsp+788h+var_6E0]
0x18004ad72  call    ?FindConnectedNetworksByInterface@NetworkPropertyMaps@@SA?AV?$vector@UACTIVE_NETWORK@@V?$allocator@UACTIVE_NETWORK@@@std@@@std@@PEBU_GUID@@_NI@Z; NetworkPropertyMaps::FindConnectedNetworksByInterface(_GUID const *,bool,uint)
0x18004ad77  nop
0x18004ad78  mov     rbx, [rsp+788h+var_6E0]
0x18004ad80  mov     r15, [rsp+788h+var_6D8]
0x18004ad88  cmp     rbx, r15
0x18004ad8b  jz      loc_18004AF31
0x18004ad91  lea     rcx, [rbx+70h]
0x18004ad95  lea     r8, [rsp+788h+var_67C]
0x18004ad9d  lea     rdx, [rsp+788h+var_720]
0x18004ada2  call    ??$_Find_lower_bound@U_GUID@@@?$_Tree@V?$_Tmap_traits@U_GUID@@UINTERFACE_DATA@@U?$less@U_GUID@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@UINTERFACE_DATA@@@std@@@4@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@UINTERFACE_DATA@@@std@@PEAX@std@@@1@AEBU_GUID@@@Z; std::_Tree<std::_Tmap_traits<_GUID,INTERFACE_DATA,std::less<_GUID>,std::allocator<std::pair<_GUID const,INTERFACE_DATA>>,0>>::_Find_lower_bound<_GUID>(_GUID const &)
0x18004ada7  lea     r8, [rsp+788h+var_67C]
0x18004adaf  mov     r14, [rsp+788h+var_710]
0x18004adb4  mov     rdx, r14
0x18004adb7  call    ??$_Lower_bound_duplicate@U_GUID@@@?$_Tree@V?$_Tmap_traits@U_GUID@@UInterfaceInfo@NlmDomain@@U?$less@U_GUID@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@UInterfaceInfo@NlmDomain@@@std@@@5@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@U?$pair@$$CBU_GUID@@UInterfaceInfo@NlmDomain@@@std@@PEAX@1@AEBU_GUID@@@Z; std::_Tree<std::_Tmap_traits<_GUID,NlmDomain::InterfaceInfo,std::less<_GUID>,std::allocator<std::pair<_GUID const,NlmDomain::InterfaceInfo>>,0>>::_Lower_bound_duplicate<_GUID>(std::_Tree_node<std::pair<_GUID const,NlmDomain::InterfaceInfo>,void *> * const,_GUID const &)
0x18004adbc  test    al, al
0x18004adbe  jnz     short loc_18004ADCD
0x18004adc0  lea     rcx, aInvalidMapKTKe; "invalid map<K, T> key"
0x18004adc7  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x18004adcd  movups  xmm0, xmmword ptr [r14+230h]
0x18004add5  movups  [rsp+788h+var_738], xmm0
0x18004adda  movsd   xmm1, qword ptr [r14+240h]
0x18004ade3  movsd   [rsp+788h+var_728], xmm1
0x18004ade9  lea     rcx, [rsp+788h+var_738]; struct _NLA_INTERNET_CAPABILITY *
0x18004adee  call    ?HasInternetCapability@@YA_NAEBU_NLA_INTERNET_CAPABILITY@@@Z; HasInternetCapability(_NLA_INTERNET_CAPABILITY const &)
0x18004adf3  test    al, al
0x18004adf5  jz      loc_18004AF1E
0x18004adfb  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ae02  lea     r14, WPP_GLOBAL_Control
0x18004ae09  cmp     rcx, r14
0x18004ae0c  jz      short loc_18004AE2D
0x18004ae0e  test    byte ptr [rcx+1Ch], 4
0x18004ae12  jz      short loc_18004AE2D
0x18004ae14  mov     edx, 6Ah ; 'j'
0x18004ae19  lea     r9, [rsp+788h+var_67C]
0x18004ae21  mov     r8, rdi
0x18004ae24  mov     rcx, [rcx+10h]
0x18004ae28  call    WPP_SF__guid_
0x18004ae2d  movups  xmm0, xmmword ptr [rsp+788h+var_67C.Data1]
0x18004ae35  movdqu  xmmword ptr [rsi+4], xmm0
0x18004ae3a  inc     dword ptr [rsi]
0x18004ae3c  lea     rcx, [rsp+788h+var_738]
0x18004ae41  call    ConnectivityFlagsFromInternetCapability
0x18004ae46  mov     r8d, eax
0x18004ae49  or      r8d, 1
0x18004ae4d  mov     [rsi+24h], r8d
0x18004ae51  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ae58  cmp     rcx, r14
0x18004ae5b  jz      short loc_18004AE8F
0x18004ae5d  test    byte ptr [rcx+1Ch], 4
0x18004ae61  jz      short loc_18004AE8F
0x18004ae63  mov     edx, [rsp+788h+var_21C]
0x18004ae6a  mov     dword ptr [rsp+788h+var_758], edx
0x18004ae6e  mov     eax, [rsp+788h+var_220]
0x18004ae75  mov     dword ptr [rsp+788h+var_760], eax
0x18004ae79  mov     dword ptr [rsp+788h+var_768], r8d
0x18004ae7e  lea     r9, [rsp+788h+var_67C]
0x18004ae86  mov     rcx, [rcx+10h]
0x18004ae8a  call    WPP_SF__guid_Ddd
0x18004ae8f  xor     r8d, r8d
0x18004ae92  lea     rdx, [rsp+788h+var_67C]
0x18004ae9a  lea     rcx, [rsp+788h+var_6C8]
0x18004aea2  call    ?GetInterfaceInfo@NetworkPropertyMaps@@SA?AV?$optional@UtagNP_IP_INTERFACE_INFO@@@std@@PEBU_GUID@@I@Z; NetworkPropertyMaps::GetInterfaceInfo(_GUID const *,uint)
0x18004aea7  xor     r15d, r15d
0x18004aeaa  cmp     [rsp+788h+var_690], r15b
0x18004aeb2  jz      short loc_18004AF19
0x18004aeb4  lea     r8d, [r15+10h]; Size
0x18004aeb8  lea     rdx, GUID_NULL; Buf2
0x18004aebf  lea     rcx, [rsp+788h+var_6A8]; Buf1
0x18004aec7  call    memcmp_0
0x18004aecc  test    eax, eax
0x18004aece  jz      short loc_18004AF19
0x18004aed0  mov     rax, [rsp+788h+var_6A8]
0x18004aed8  mov     [rsi+14h], rax
0x18004aedc  mov     rax, [rsp+788h+var_6A0]
0x18004aee4  mov     [rsi+1Ch], rax
  ... truncated ...
```
