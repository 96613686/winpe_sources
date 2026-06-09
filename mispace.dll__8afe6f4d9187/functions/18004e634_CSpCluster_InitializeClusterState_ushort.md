# CSpCluster::_InitializeClusterState(ushort * *)

- ea: `0x18004e634`
- end: `0x18004edb1`
- name: `?_InitializeClusterState@CSpCluster@@AEAA?AV_status_t@@PEAPEAG@Z`
- size: `1917`
- prototype: ``
- caller_count: `2`
- callee_count: `28`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800473fc`
- `0x18004bef8`

## callees

- `0x18000116c`
- `0x1800011b0`
- `0x1800014ec`
- `0x1800015b8`
- `0x18000cd18`
- `0x18000e43c`
- `0x18000f050`
- `0x18000f3bc`
- `0x18001dae4`
- `0x18001f294`
- `0x180023508`
- `0x180028124`
- `0x180028a4c`
- `0x180028f84`
- `0x18002aac4`
- `0x18004e634`
- `0x18004f460`
- `0x18004f544`
- `0x18004fbf8`
- `0x180050380`
- `0x18005064c`
- `0x180050818`
- `0x1800508a0`
- `0x1801acce0`
- `0x1801ad258`
- `0x1801afe04`
- `0x1801affcc`
- `0x1801b0094`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18004e93e`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18004e94b`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18004e93e`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18004e94b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004e80f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004e80f`
- `ext-ms-win-cluster-clusapi-l1-1-0!OpenClusterNode` at `0x18004e8ac`
- `ext-ms-win-cluster-clusapi-l1-1-0!OpenClusterNode` at `0x18004e8ac`
- `ext-ms-win-cluster-clusapi-l1-1-0!OpenCluster` at `0x18004e6df`
- `ext-ms-win-cluster-clusapi-l1-1-0!OpenCluster` at `0x18004e6df`
- `ext-ms-win-cluster-clusapi-l1-1-1!GetClusterNodeId` at `0x18004e8f6`
- `ext-ms-win-cluster-clusapi-l1-1-1!GetClusterNodeId` at `0x18004e8f6`

## string_xrefs

- `0x18004e9ba`: `RepairQueueDepth`
- `0x18004eb3b`: `StorageSubsystemPolicies`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_status_t *__fastcall CSpCluster::_InitializeClusterState(__int64 a1, _status_t *a2, unsigned __int16 **a3, __int64 a4)
{
  int v7; // edi
  int v8; // edx
  __int64 v9; // rcx
  HCLUSTER v10; // rax
  int LastError; // eax
  __int64 v12; // r8
  __int64 v13; // r9
  __int16 *v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 v17; // r9
  HLOCAL v18; // rcx
  struct _HNODE *v20; // rax
  signed int ClusterNodeId; // eax
  __int64 v22; // rdx
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // r8
  __int64 v26; // r9
  int v27; // eax
  __int16 *v28; // rdx
  int Control; // eax
  __int64 v30; // r8
  __int64 v31; // r9
  __int64 v32; // rcx
  __int64 v33; // rax
  __int64 v34; // rax
  int v35; // eax
  enum _MI_Result MessagePipe; // eax
  enum _MI_Result ClusterApi; // ecx
  int v38; // eax
  __int64 v39; // rax
  __int64 v40; // rcx
  __int64 SpNodeState; // r9
  __int64 v42; // r8
  int *v43; // [rsp+28h] [rbp-51h]
  __int64 v44; // [rsp+28h] [rbp-51h]
  __int64 v45; // [rsp+28h] [rbp-51h]
  __int64 v46; // [rsp+28h] [rbp-51h]
  HLOCAL *p_hMem; // [rsp+40h] [rbp-39h] BYREF
  struct _SP_CONTROL_INFO *v48; // [rsp+48h] [rbp-31h] BYREF
  char v49; // [rsp+50h] [rbp-29h]
  unsigned __int16 *v50; // [rsp+58h] [rbp-21h] BYREF
  HLOCAL hMem; // [rsp+60h] [rbp-19h] BYREF
  DWORD cchName; // [rsp+68h] [rbp-11h] BYREF
  LPCWSTR lpszNodeName; // [rsp+70h] [rbp-9h] BYREF
  _BYTE v54[8]; // [rsp+78h] [rbp-1h] BYREF
  PVOID RestartKey[2]; // [rsp+80h] [rbp+7h] BYREF
  __int64 v56; // [rsp+90h] [rbp+17h]
  int v57; // [rsp+E0h] [rbp+67h] BYREF
  int v58; // [rsp+E8h] [rbp+6Fh] BYREF
  const char *v59; // [rsp+F8h] [rbp+7Fh] BYREF

  if ( (unsigned int)dword_180397B68 > 5 )
  {
    v58 = 458;
    v59 = "CSpCluster::_InitializeClusterState";
    v43 = &v58;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      a1,
      (__int64)word_1803036F2,
      (__int64)a3,
      a4,
      &v59);
  }
  v50 = 0;
  lpszNodeName = 0;
  hMem = 0;
  cchName = 16;
  v56 = 0;
  *(_OWORD *)RestartKey = 0;
  v7 = 0;
  v57 = 0;
  *(_QWORD *)a2 = 0;
  *((_BYTE *)a2 + 8) = 0;
  wil::EnterCriticalSection(v54, a1 + 8);
  if ( *(_QWORD *)(a1 + 72) )
    goto LABEL_9;
  v10 = OpenCluster(0);
  *(_QWORD *)(a1 + 72) = v10;
  if ( !v10 )
  {
    v7 = 1;
    LastError = _status_t::GetLastError(a2);
    v9 = (unsigned int)dword_180397B68;
    if ( (unsigned int)dword_180397B68 <= 2 )
      goto LABEL_9;
    LODWORD(v59) = 485;
    v14 = &word_18030237E;
    goto LABEL_7;
  }
  LastError = SmGetClusterFQDN(0, &v50);
  *(_DWORD *)a2 = LastError;
  if ( LastError < 0 )
  {
    v7 = 2;
    v9 = (unsigned int)dword_180397B68;
    if ( (unsigned int)dword_180397B68 > 2 )
    {
      LODWORD(v59) = 495;
      v14 = (__int16 *)byte_180303093;
LABEL_7:
      v58 = LastError;
LABEL_8:
      p_hMem = (HLOCAL *)"CSpCluster::_InitializeClusterState";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v9,
        (__int64)v14,
        v12,
        v13,
        &p_hMem);
      goto LABEL_9;
    }
    goto LABEL_9;
  }
  LastError = SmGetComputerNameByFormat(ComputerNameDnsHostname, (unsigned __int16 **)&lpszNodeName);
  *(_DWORD *)a2 = LastError;
  if ( LastError >= 0 )
  {
    v20 = OpenClusterNode(*(HCLUSTER *)(a1 + 72), lpszNodeName);
    *(_QWORD *)(a1 + 80) = v20;
    if ( !v20 )
    {
      v7 = 4;
      LastError = _status_t::GetLastError(a2);
      v9 = (unsigned int)dword_180397B68;
      if ( (unsigned int)dword_180397B68 > 2 )
      {
        LODWORD(v59) = 515;
        v14 = (__int16 *)byte_180303E3B;
        goto LABEL_7;
      }
      goto LABEL_9;
    }
    ClusterNodeId = GetClusterNodeId(v20, (LPWSTR)(a1 + 88), &cchName);
    v9 = (unsigned int)ClusterNodeId;
    if ( ClusterNodeId > 0 )
      v9 = (unsigned __int16)ClusterNodeId | 0x80070000;
    *(_DWORD *)a2 = v9;
    if ( (int)v9 < 0 )
    {
      v7 = 5;
      if ( (unsigned int)dword_180397B68 > 2 )
      {
        v58 = v9;
        LODWORD(v59) = 525;
        v14 = (__int16 *)&unk_180301BA8;
        goto LABEL_8;
      }
      goto LABEL_9;
    }
    if ( (int)_o__wtoi(a1 + 88) <= 0 )
      v22 = 0;
    else
      v22 = 1LL << ((unsigned __int8)_o__wtoi(a1 + 88) - 1);
    *(_QWORD *)(a1 + 120) = v22;
    v23 = CSpCluster::_ReadClusterRegistry(a1, &p_hMem, 0, L"SpacesSubSystemAutomaticClusteringEnabled", a1 + 152, v43);
    *(_QWORD *)a2 = *(_QWORD *)v23;
    *((_DWORD *)a2 + 2) = *(_DWORD *)(v23 + 8);
    v9 = *(unsigned int *)a2;
    if ( (_DWORD)v9 == -2147024894 )
    {
      *(_DWORD *)(a1 + 152) = 1;
    }
    else if ( (int)v9 < 0 )
    {
      v7 = 6;
      if ( (unsigned int)dword_180397B68 > 2 )
      {
        v58 = *(_DWORD *)a2;
        LODWORD(v59) = 547;
        v14 = word_1803039D2;
        goto LABEL_8;
      }
      goto LABEL_9;
    }
    v7 = 7;
    v24 = CSpCluster::_ReadClusterRegistry(a1, &p_hMem, L"Spaceport\\Parameters", L"RepairQueueDepth", a1 + 156, v44);
    *(_QWORD *)a2 = *(_QWORD *)v24;
    *((_DWORD *)a2 + 2) = *(_DWORD *)(v24 + 8);
    v9 = *(unsigned int *)a2;
    if ( (_DWORD)v9 == -2147024894 )
    {
      v27 = SuInitialize((void **)v9);
      _status_t::SetBoolGle(a2, v27);
      v9 = *(unsigned int *)a2;
      if ( (int)v9 < 0 )
      {
        if ( (unsigned int)dword_180397B68 <= 2 )
          goto LABEL_9;
        LODWORD(v59) = 571;
        v28 = word_180304B1A;
        goto LABEL_44;
      }
      p_hMem = &hMem;
      v48 = 0;
      v49 = 1;
      Control = SuGetControl(&v48);
      _status_t::SetBoolGle(a2, Control);
      wil::details::out_param_t<wistd::unique_ptr<_SP_CONVERT_PARAMS,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_SP_CONVERT_PARAMS,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_hMem);
      v32 = *(unsigned int *)a2;
      if ( (int)v32 < 0 )
      {
        if ( (unsigned int)dword_180397B68 > 2 )
        {
          v58 = *(_DWORD *)a2;
          LODWORD(v59) = 583;
          p_hMem = (HLOCAL *)"CSpCluster::_InitializeClusterState";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v32,
            (__int64)&unk_180305788,
            v30,
            v31,
            &p_hMem);
        }
        SuCleanup();
        goto LABEL_9;
      }
      *(_DWORD *)(a1 + 156) = *((_DWORD *)hMem + 19);
      SuCleanup();
    }
    else if ( (int)v9 < 0 )
    {
      if ( (unsigned int)dword_180397B68 <= 2 )
        goto LABEL_9;
      LODWORD(v59) = 591;
      v28 = (__int16 *)&dword_180305A04;
      goto LABEL_44;
    }
    v33 = CSpCluster::_ReadClusterRegistry(
            a1,
            &p_hMem,
            L"StorageSubsystemPolicies",
            L"FDAwarenessDefault",
            a1 + 160,
            v45);
    *(_QWORD *)a2 = *(_QWORD *)v33;
    *((_DWORD *)a2 + 2) = *(_DWORD *)(v33 + 8);
    v9 = *(unsigned int *)a2;
    if ( (_DWORD)v9 == -2147024894 )
    {
      *(_DWORD *)(a1 + 160) = 1;
    }
    else if ( (int)v9 < 0 )
    {
      v7 = 8;
      if ( (unsigned int)dword_180397B68 <= 2 )
        goto LABEL_9;
      LODWORD(v59) = 607;
      v28 = (__int16 *)byte_180302FC9;
      goto LABEL_44;
    }
    v34 = CSpCluster::_ReadClusterRegistry(a1, &p_hMem, 0, L"S2DEnabled", &v57, v46);
    *(_QWORD *)a2 = *(_QWORD *)v34;
    *((_DWORD *)a2 + 2) = *(_DWORD *)(v34 + 8);
    v9 = *(unsigned int *)a2;
    if ( (int)v9 < 0 )
    {
      if ( (_DWORD)v9 != -2147024894 )
      {
        v7 = 9;
        if ( (unsigned int)dword_180397B68 <= 2 )
          goto LABEL_9;
        LODWORD(v59) = 627;
        v28 = (__int16 *)&byte_1803011E7;
        goto LABEL_44;
      }
      v35 = 1;
    }
    else
    {
      v35 = (v57 == 1) + 1;
    }
    *(_DWORD *)(a1 + 164) = v35;
    MessagePipe = CSpCluster::_LoadMessagePipe((CSpCluster *)a1);
    if ( MessagePipe )
    {
      v9 = MessagePipe | 0x85200000;
      *(_DWORD *)a2 = v9;
      v7 = 10;
      if ( (unsigned int)dword_180397B68 <= 2 )
        goto LABEL_9;
      LODWORD(v59) = 642;
      v28 = word_180305972;
    }
    else
    {
      *(_DWORD *)a2 = 85983232;
      ClusterApi = CSpCluster::_LoadClusterApi(0);
      if ( ClusterApi )
      {
        v9 = ClusterApi | 0x85200000;
        *(_DWORD *)a2 = v9;
        v7 = 11;
        if ( (unsigned int)dword_180397B68 <= 2 )
          goto LABEL_9;
        LODWORD(v59) = 652;
        v28 = (__int16 *)byte_18030543B;
      }
      else
      {
        *(_DWORD *)a2 = 85983232;
        v7 = 12;
        v38 = SuEnumerateClusterNodes((PVOID)(a1 + 184));
        _status_t::SetBoolGle(a2, v38);
        v9 = *(unsigned int *)a2;
        if ( (int)v9 >= 0 )
        {
          v39 = CMapBase<_SP_ID,_SU_DRIVE_OBJECT *>::Begin(a1 + 184, &p_hMem);
          *(_OWORD *)RestartKey = *(_OWORD *)v39;
          v56 = *(_QWORD *)(v39 + 16);
          while ( RestartKey[0] )
          {
            v9 = (__int64)RestartKey[1];
            if ( !RestartKey[1] )
              break;
            if ( (Microsoft_Windows_StorageManagement_WSP_SpacesEnableBits & 4) != 0 )
            {
              SpNodeState = GetSpNodeState(*((LPCWSTR *)RestartKey[1] + 1));
              if ( RestartKey[1] )
                v42 = *((_QWORD *)RestartKey[1] + 1);
              else
                v42 = 0;
              McTemplateU0zq_EventWriteTransfer(v40, ClusterNodeArrived, v42, SpNodeState);
            }
            CMapIter<unsigned short const *,_SUEX_SPACE_OBJECT *>::Next(RestartKey);
          }
          if ( (Microsoft_Windows_StorageManagement_WSP_SpacesEnableBits & 4) != 0 )
            McTemplateU0z_EventWriteTransfer(v9, ClusterStateInitializationSucceeded, v50);
          if ( a3 )
          {
            *a3 = v50;
            v50 = 0;
          }
          goto LABEL_9;
        }
        if ( (unsigned int)dword_180397B68 <= 2 )
          goto LABEL_9;
        LODWORD(v59) = 670;
        v28 = word_180302412;
      }
    }
LABEL_44:
    p_hMem = (HLOCAL *)"CSpCluster::_InitializeClusterState";
    v58 = v9;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v9,
      (__int64)v28,
      v25,
      v26,
      &p_hMem);
    goto LABEL_9;
  }
  v7 = 3;
  v9 = (unsigned int)dword_180397B68;
  if ( (unsigned int)dword_180397B68 > 2 )
  {
    LODWORD(v59) = 505;
    v14 = &word_180303B1E;
    goto LABEL_7;
  }
LABEL_9:
  if ( *(int *)a2 < 0 )
  {
    if ( (Microsoft_Windows_StorageManagement_WSP_SpacesEnableBits & 1) != 0 )
      McTemplateU0zqd_EventWriteTransfer(v9, v8, (_DWORD)v50, v7, *(_DWORD *)a2);
    if ( (unsigned int)dword_180397B68 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180397B68, 1024) )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        (__int64)&dword_180397B68,
        (__int64)&byte_18030121F);
    CSpCluster::_UninitializeClusterState((CSpCluster *)a1, 0);
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::reset(
    v54,
    0);
  SmFreeString((unsigned __int16 **)&lpszNodeName);
  SmFreeString(&v50);
  if ( (unsigned int)dword_180397B68 > 5 )
  {
    v58 = 709;
    v59 = "CSpCluster::_InitializeClusterState";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v15,
      (__int64)word_1803059AA,
      v16,
      v17,
      &v59);
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(v54);
  v18 = hMem;
  hMem = 0;
  if ( v18 )
    LocalFree(v18);
  return a2;
}

```

## disassembly

```asm
0x18004e634  mov     [rsp-8+arg_10], rbx
0x18004e639  push    rbp
0x18004e63a  push    rsi
0x18004e63b  push    rdi
0x18004e63c  push    r12
0x18004e63e  push    r13
0x18004e640  push    r14
0x18004e642  push    r15
0x18004e644  lea     rbp, [rsp-27h]
0x18004e649  sub     rsp, 0A0h
0x18004e650  mov     r15, r8
0x18004e653  mov     rbx, rdx
0x18004e656  mov     rsi, rcx
0x18004e659  mov     eax, cs:dword_180397B68
0x18004e65f  lea     r14, aCspclusterInit; "CSpCluster::_InitializeClusterState"
0x18004e666  cmp     eax, 5
0x18004e669  jbe     short loc_18004E694
0x18004e66b  mov     [rbp+57h+arg_8], 1CAh
0x18004e672  mov     [rbp+57h+arg_18], r14
0x18004e676  lea     rax, [rbp+57h+arg_8]
0x18004e67a  mov     [rsp+0D0h+var_A8], rax
0x18004e67f  lea     rax, [rbp+57h+arg_18]
0x18004e683  mov     [rsp+0D0h+var_B0], rax
0x18004e688  lea     rdx, word_1803036F2
0x18004e68f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18004e694  xor     r12d, r12d
0x18004e697  mov     [rbp+57h+var_78], r12
0x18004e69b  mov     [rbp+57h+lpszNodeName], r12
0x18004e69f  mov     [rbp+57h+hMem], r12
0x18004e6a3  mov     [rbp+57h+cchName], 10h
0x18004e6aa  mov     [rbp+57h+var_40], r12
0x18004e6ae  xorps   xmm0, xmm0
0x18004e6b1  movdqu  xmmword ptr [rbp+57h+RestartKey], xmm0
0x18004e6b6  mov     edi, r12d
0x18004e6b9  mov     [rbp+57h+arg_0], r12d
0x18004e6bd  mov     [rbx], r12
0x18004e6c0  mov     [rbx+8], r12b
0x18004e6c4  lea     rdx, [rsi+8]
0x18004e6c8  lea     rcx, [rbp+57h+var_58]
0x18004e6cc  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x18004e6d1  nop
0x18004e6d2  lea     r13d, [r12+2]
0x18004e6d7  cmp     [rsi+48h], r12
0x18004e6db  jnz     short loc_18004E73D
0x18004e6dd  xor     ecx, ecx; lpszClusterName
0x18004e6df  call    cs:__imp_OpenCluster
0x18004e6e5  mov     [rsi+48h], rax
0x18004e6e9  test    rax, rax
0x18004e6ec  jnz     loc_18004E833
0x18004e6f2  lea     edi, [rax+1]
0x18004e6f5  mov     rcx, rbx; this
0x18004e6f8  call    ?GetLastError@_status_t@@QEAAJXZ; _status_t::GetLastError(void)
0x18004e6fd  mov     ecx, cs:dword_180397B68
0x18004e703  cmp     ecx, r13d
0x18004e706  jbe     short loc_18004E73D
0x18004e708  mov     dword ptr [rbp+57h+arg_18], 1E5h
0x18004e70f  lea     rdx, word_18030237E
0x18004e716  mov     [rbp+57h+arg_8], eax
0x18004e719  lea     rax, [rbp+57h+arg_8]
0x18004e71d  mov     [rsp+0D0h+var_A0], rax
0x18004e722  lea     rax, [rbp+57h+arg_18]
0x18004e726  mov     [rsp+0D0h+var_A8], rax
0x18004e72b  lea     rax, [rbp+57h+var_90]
0x18004e72f  mov     [rsp+0D0h+var_B0], rax
0x18004e734  mov     [rbp+57h+var_90], r14
0x18004e738  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18004e73d  lea     r14, aCspclusterInit; "CSpCluster::_InitializeClusterState"
0x18004e744  mov     eax, [rbx]
0x18004e746  test    eax, eax
0x18004e748  jns     short loc_18004E7A6
0x18004e74a  test    cs:Microsoft_Windows_StorageManagement_WSP_SpacesEnableBits, 1
0x18004e751  jz      short loc_18004E763
0x18004e753  mov     dword ptr [rsp+0D0h+var_B0], eax
0x18004e757  mov     r9d, edi
0x18004e75a  mov     r8, [rbp+57h+var_78]
0x18004e75e  call    McTemplateU0zqd_EventWriteTransfer
0x18004e763  mov     eax, cs:dword_180397B68
0x18004e769  cmp     eax, r13d
0x18004e76c  jbe     short loc_18004E79C
0x18004e76e  mov     edx, 400h
0x18004e773  lea     rcx, dword_180397B68
0x18004e77a  call    _tlgKeywordOn
0x18004e77f  test    al, al
0x18004e781  jz      short loc_18004E79C
0x18004e783  xor     r9d, r9d
0x18004e786  xor     r8d, r8d
0x18004e789  lea     rdx, byte_18030121F
0x18004e790  lea     rcx, dword_180397B68
0x18004e797  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18004e79c  xor     edx, edx; int
0x18004e79e  mov     rcx, rsi; this
0x18004e7a1  call    ?_UninitializeClusterState@CSpCluster@@AEAAXH@Z; CSpCluster::_UninitializeClusterState(int)
0x18004e7a6  xor     edx, edx
0x18004e7a8  lea     rcx, [rbp+57h+var_58]
0x18004e7ac  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_RTL_CRITICAL_SECTION@@@Z; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::reset(_RTL_CRITICAL_SECTION *)
0x18004e7b1  lea     rcx, [rbp+57h+lpszNodeName]; unsigned __int16 **
0x18004e7b5  call    ?SmFreeString@@YAXAEAPEAG@Z; SmFreeString(ushort * &)
0x18004e7ba  lea     rcx, [rbp+57h+var_78]; unsigned __int16 **
0x18004e7be  call    ?SmFreeString@@YAXAEAPEAG@Z; SmFreeString(ushort * &)
0x18004e7c3  mov     eax, cs:dword_180397B68
0x18004e7c9  cmp     eax, 5
0x18004e7cc  jbe     short loc_18004E7F8
0x18004e7ce  mov     [rbp+57h+arg_8], 2C5h
0x18004e7d5  mov     [rbp+57h+arg_18], r14
0x18004e7d9  lea     rax, [rbp+57h+arg_8]
0x18004e7dd  mov     [rsp+0D0h+var_A8], rax
0x18004e7e2  lea     rax, [rbp+57h+arg_18]
0x18004e7e6  mov     [rsp+0D0h+var_B0], rax
0x18004e7eb  lea     rdx, word_1803059AA
0x18004e7f2  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18004e7f7  nop
0x18004e7f8  lea     rcx, [rbp+57h+var_58]
0x18004e7fc  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18004e801  nop
0x18004e802  mov     rcx, [rbp+57h+hMem]; hMem
0x18004e806  mov     [rbp+57h+hMem], r12
0x18004e80a  test    rcx, rcx
0x18004e80d  jz      short loc_18004E815
0x18004e80f  call    cs:__imp_LocalFree
0x18004e815  mov     rax, rbx
0x18004e818  mov     rbx, [rsp+0D0h+arg_10]
0x18004e820  add     rsp, 0A0h
0x18004e827  pop     r15
0x18004e829  pop     r14
0x18004e82b  pop     r13
0x18004e82d  pop     r12
0x18004e82f  pop     rdi
0x18004e830  pop     rsi
0x18004e831  pop     rbp
0x18004e832  retn
0x18004e833  lea     rdx, [rbp+57h+var_78]; unsigned __int16 **
0x18004e837  xor     ecx, ecx; unsigned __int16 *
0x18004e839  call    ?SmGetClusterFQDN@@YAJPEBGPEAPEAG@Z; SmGetClusterFQDN(ushort const *,ushort * *)
0x18004e83e  mov     [rbx], eax
0x18004e840  test    eax, eax
0x18004e842  jns     short loc_18004E869
0x18004e844  mov     edi, r13d
0x18004e847  mov     ecx, cs:dword_180397B68
0x18004e84d  cmp     ecx, r13d
0x18004e850  jbe     loc_18004E73D
0x18004e856  mov     dword ptr [rbp+57h+arg_18], 1EFh
0x18004e85d  lea     rdx, byte_180303093
0x18004e864  jmp     loc_18004E716
0x18004e869  lea     rdx, [rbp+57h+lpszNodeName]; unsigned __int16 **
0x18004e86d  mov     ecx, 1; NameType
0x18004e872  call    ?SmGetComputerNameByFormat@@YAJW4_COMPUTER_NAME_FORMAT@@PEAPEAG@Z; SmGetComputerNameByFormat(_COMPUTER_NAME_FORMAT,ushort * *)
0x18004e877  mov     [rbx], eax
0x18004e879  test    eax, eax
0x18004e87b  jns     short loc_18004E8A4
0x18004e87d  mov     edi, 3
0x18004e882  mov     ecx, cs:dword_180397B68
0x18004e888  cmp     ecx, r13d
0x18004e88b  jbe     loc_18004E73D
0x18004e891  mov     dword ptr [rbp+57h+arg_18], 1F9h
0x18004e898  lea     rdx, word_180303B1E
0x18004e89f  jmp     loc_18004E716
0x18004e8a4  mov     rdx, [rbp+57h+lpszNodeName]; lpszNodeName
0x18004e8a8  mov     rcx, [rsi+48h]; hCluster
0x18004e8ac  call    cs:__imp_OpenClusterNode
0x18004e8b2  mov     [rsi+50h], rax
0x18004e8b6  test    rax, rax
0x18004e8b9  jnz     short loc_18004E8E8
0x18004e8bb  lea     edi, [rax+4]
0x18004e8be  mov     rcx, rbx; this
0x18004e8c1  call    ?GetLastError@_status_t@@QEAAJXZ; _status_t::GetLastError(void)
0x18004e8c6  mov     ecx, cs:dword_180397B68
0x18004e8cc  cmp     ecx, r13d
0x18004e8cf  jbe     loc_18004E73D
0x18004e8d5  mov     dword ptr [rbp+57h+arg_18], 203h
0x18004e8dc  lea     rdx, byte_180303E3B
0x18004e8e3  jmp     loc_18004E716
0x18004e8e8  lea     rdi, [rsi+58h]
0x18004e8ec  lea     r8, [rbp+57h+cchName]; lpcchName
0x18004e8f0  mov     rdx, rdi; lpszNodeId
0x18004e8f3  mov     rcx, rax; hNode
0x18004e8f6  call    cs:__imp_GetClusterNodeId
0x18004e8fc  mov     ecx, eax
0x18004e8fe  test    eax, eax
0x18004e900  jle     short loc_18004E90B
0x18004e902  movzx   ecx, ax
0x18004e905  or      ecx, 80070000h
0x18004e90b  mov     [rbx], ecx
0x18004e90d  test    ecx, ecx
0x18004e90f  jns     short loc_18004E93B
0x18004e911  mov     edi, 5
0x18004e916  mov     eax, cs:dword_180397B68
0x18004e91c  cmp     eax, r13d
0x18004e91f  jbe     loc_18004E73D
0x18004e925  mov     [rbp+57h+arg_8], ecx
0x18004e928  mov     dword ptr [rbp+57h+arg_18], 20Dh
0x18004e92f  lea     rdx, unk_180301BA8
0x18004e936  jmp     loc_18004E719
0x18004e93b  mov     rcx, rdi
0x18004e93e  call    cs:__imp__o__wtoi
0x18004e944  test    eax, eax
0x18004e946  jle     short loc_18004E95E
0x18004e948  mov     rcx, rdi
0x18004e94b  call    cs:__imp__o__wtoi
0x18004e951  lea     ecx, [rax-1]
0x18004e954  mov     edx, 1
0x18004e959  shl     rdx, cl
0x18004e95c  jmp     short loc_18004E961
0x18004e95e  mov     rdx, r12
0x18004e961  mov     [rsi+78h], rdx
0x18004e965  lea     rdi, [rsi+98h]
0x18004e96c  mov     [rsp+0D0h+var_B0], rdi
0x18004e971  lea     r9, aSpacessubsyste; "SpacesSubSystemAutomaticClusteringEnabl"...
0x18004e978  xor     r8d, r8d
0x18004e97b  lea     rdx, [rbp+57h+var_90]
0x18004e97f  mov     rcx, rsi
0x18004e982  call    ?_ReadClusterRegistry@CSpCluster@@AEAA?AV_status_t@@PEBG0PEAEK@Z; CSpCluster::_ReadClusterRegistry(ushort const *,ushort const *,uchar *,ulong)
0x18004e987  movsd   xmm0, qword ptr [rax]
0x18004e98b  movsd   qword ptr [rbx], xmm0
0x18004e98f  mov     eax, [rax+8]
0x18004e992  mov     [rbx+8], eax
0x18004e995  mov     ecx, [rbx]
0x18004e997  cmp     ecx, 80070002h
0x18004e99d  jnz     loc_18004EA59
0x18004e9a3  mov     dword ptr [rdi], 1
0x18004e9a9  mov     edi, 7
0x18004e9ae  lea     r14, [rsi+9Ch]
0x18004e9b5  mov     [rsp+0D0h+var_B0], r14
0x18004e9ba  lea     r9, aRepairqueuedep; "RepairQueueDepth"
0x18004e9c1  lea     r8, szSubKey; "Spaceport\\Parameters"
0x18004e9c8  lea     rdx, [rbp+57h+var_90]
0x18004e9cc  mov     rcx, rsi
0x18004e9cf  call    ?_ReadClusterRegistry@CSpCluster@@AEAA?AV_status_t@@PEBG0PEAEK@Z; CSpCluster::_ReadClusterRegistry(ushort const *,ushort const *,uchar *,ulong)
0x18004e9d4  movsd   xmm0, qword ptr [rax]
0x18004e9d8  movsd   qword ptr [rbx], xmm0
0x18004e9dc  mov     eax, [rax+8]
0x18004e9df  mov     [rbx+8], eax
0x18004e9e2  mov     ecx, [rbx]
0x18004e9e4  cmp     ecx, 80070002h
0x18004e9ea  jnz     loc_18004EBB0
0x18004e9f0  call    ?SuInitialize@@YAHXZ; SuInitialize(void)
0x18004e9f5  mov     edx, eax; int
0x18004e9f7  mov     rcx, rbx; this
0x18004e9fa  call    ?SetBoolGle@_status_t@@QEAAJH@Z; _status_t::SetBoolGle(int)
0x18004e9ff  mov     ecx, [rbx]
0x18004ea01  test    ecx, ecx
0x18004ea03  jns     loc_18004EA8B
0x18004ea09  mov     eax, cs:dword_180397B68
0x18004ea0f  cmp     eax, r13d
0x18004ea12  jbe     loc_18004E73D
0x18004ea18  mov     dword ptr [rbp+57h+arg_18], 23Bh
0x18004ea1f  lea     rdx, word_180304B1A
0x18004ea26  lea     rax, [rbp+57h+arg_8]
0x18004ea2a  mov     [rsp+0D0h+var_A0], rax
0x18004ea2f  lea     rax, [rbp+57h+arg_18]
0x18004ea33  mov     [rsp+0D0h+var_A8], rax
0x18004ea38  lea     r14, aCspclusterInit; "CSpCluster::_InitializeClusterState"
0x18004ea3f  lea     rax, [rbp+57h+var_90]
0x18004ea43  mov     [rbp+57h+var_90], r14
0x18004ea47  mov     [rsp+0D0h+var_B0], rax
0x18004ea4c  mov     [rbp+57h+arg_8], ecx
0x18004ea4f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18004ea54  jmp     loc_18004E744
0x18004ea59  test    ecx, ecx
0x18004ea5b  jns     loc_18004E9A9
0x18004ea61  mov     edi, 6
0x18004ea66  mov     eax, cs:dword_180397B68
0x18004ea6c  cmp     eax, r13d
0x18004ea6f  jbe     loc_18004E73D
0x18004ea75  mov     [rbp+57h+arg_8], ecx
0x18004ea78  mov     dword ptr [rbp+57h+arg_18], 223h
0x18004ea7f  lea     rdx, word_1803039D2
0x18004ea86  jmp     loc_18004E719
0x18004ea8b  lea     rax, [rbp+57h+hMem]
0x18004ea8f  mov     [rbp+57h+var_90], rax
0x18004ea93  mov     [rbp+57h+var_88], r12
0x18004ea97  mov     [rbp+57h+var_80], 1
0x18004ea9b  lea     rcx, [rbp+57h+var_88]; struct _SP_CONTROL_INFO **
0x18004ea9f  call    ?SuGetControl@@YAHPEAPEAU_SP_CONTROL_INFO@@@Z; SuGetControl(_SP_CONTROL_INFO * *)
0x18004eaa4  mov     edx, eax; int
0x18004eaa6  mov     rcx, rbx; this
0x18004eaa9  call    ?SetBoolGle@_status_t@@QEAAJH@Z; _status_t::SetBoolGle(int)
0x18004eaae  lea     rcx, [rbp+57h+var_90]
0x18004eab2  call    ??1?$out_param_t@V?$unique_ptr@U_SP_CONVERT_PARAMS@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_SP_CONVERT_PARAMS,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_SP_CONVERT_PARAMS,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x18004eab7  mov     ecx, [rbx]
0x18004eab9  test    ecx, ecx
0x18004eabb  jns     short loc_18004EB18
0x18004eabd  mov     eax, cs:dword_180397B68
0x18004eac3  cmp     eax, r13d
0x18004eac6  jbe     short loc_18004EB06
0x18004eac8  mov     [rbp+57h+arg_8], ecx
0x18004eacb  mov     dword ptr [rbp+57h+arg_18], 247h
0x18004ead2  lea     r14, aCspclusterInit; "CSpCluster::_InitializeClusterState"
0x18004ead9  mov     [rbp+57h+var_90], r14
0x18004eadd  lea     rax, [rbp+57h+arg_8]
0x18004eae1  mov     [rsp+0D0h+var_A0], rax
0x18004eae6  lea     rax, [rbp+57h+arg_18]
0x18004eaea  mov     [rsp+0D0h+var_A8], rax
0x18004eaef  lea     rax, [rbp+57h+var_90]
0x18004eaf3  mov     [rsp+0D0h+var_B0], rax
0x18004eaf8  lea     rdx, unk_180305788
0x18004eaff  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18004eb04  jmp     short loc_18004EB0D
0x18004eb06  lea     r14, aCspclusterInit; "CSpCluster::_InitializeClusterState"
0x18004eb0d  call    ?SuCleanup@@YAHXZ; SuCleanup(void)
0x18004eb12  nop
  ... truncated ...
```
