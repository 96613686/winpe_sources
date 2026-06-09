# CSpCluster::_InitializeClusterState(ushort * *)

- ea: `0x18004ff18`
- end: `0x1800506ac`
- name: `?_InitializeClusterState@CSpCluster@@AEAA?AV_status_t@@PEAPEAG@Z`
- size: `1940`
- prototype: ``
- caller_count: `2`
- callee_count: `29`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800488fc`
- `0x18004d66c`

## callees

- `0x180001180`
- `0x1800011c4`
- `0x180001504`
- `0x1800015d8`
- `0x18000cc78`
- `0x18000e3ac`
- `0x18000f100`
- `0x18000f484`
- `0x18001e1e0`
- `0x18001fa04`
- `0x180023e3c`
- `0x180028c40`
- `0x180029568`
- `0x180029b04`
- `0x18002b770`
- `0x1800473d8`
- `0x18004ff18`
- `0x180050dbc`
- `0x180050ea0`
- `0x1800515a8`
- `0x180051d7c`
- `0x180052074`
- `0x180052248`
- `0x1800522d0`
- `0x1801b274c`
- `0x1801b2d58`
- `0x1801b5b88`
- `0x1801b5d80`
- `0x1801b5e7c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18005022d`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180050240`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18005022d`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180050240`
- `ext-ms-win-cluster-clusapi-l1-1-0!OpenClusterNode` at `0x18005018f`
- `ext-ms-win-cluster-clusapi-l1-1-0!OpenClusterNode` at `0x18005018f`
- `ext-ms-win-cluster-clusapi-l1-1-0!OpenCluster` at `0x18004ffc3`
- `ext-ms-win-cluster-clusapi-l1-1-0!OpenCluster` at `0x18004ffc3`
- `ext-ms-win-cluster-clusapi-l1-1-1!GetClusterNodeId` at `0x1800501df`
- `ext-ms-win-cluster-clusapi-l1-1-1!GetClusterNodeId` at `0x1800501df`

## string_xrefs

- `0x1800502b5`: `RepairQueueDepth`
- `0x180050436`: `StorageSubsystemPolicies`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_status_t *__fastcall CSpCluster::_InitializeClusterState(__int64 a1, _status_t *a2, unsigned __int16 **a3, int a4)
{
  int v7; // edi
  int v8; // edx
  void **v9; // rcx
  HCLUSTER v10; // rax
  int LastError; // eax
  int v12; // r8d
  int v13; // r9d
  __int16 *v14; // rdx
  int v15; // ecx
  int v16; // r8d
  int v17; // r9d
  struct _HNODE *v19; // rax
  signed int ClusterNodeId; // eax
  __int64 v21; // rdx
  __int64 v22; // rax
  __int64 v23; // rax
  int v24; // r8d
  int v25; // r9d
  int v26; // eax
  __int16 *v27; // rdx
  int Control; // eax
  int v29; // r8d
  int v30; // r9d
  int v31; // ecx
  __int64 v32; // rax
  __int64 v33; // rax
  int v34; // eax
  enum _MI_Result MessagePipe; // eax
  enum _MI_Result ClusterApi; // ecx
  int v37; // eax
  __int64 v38; // rax
  __int64 v39; // rcx
  __int64 SpNodeState; // r9
  __int64 v41; // r8
  const char *v42; // [rsp+40h] [rbp-39h] BYREF
  struct _SP_CONTROL_INFO *v43; // [rsp+48h] [rbp-31h] BYREF
  char v44; // [rsp+50h] [rbp-29h]
  unsigned __int16 *v45; // [rsp+58h] [rbp-21h] BYREF
  DWORD cchName; // [rsp+60h] [rbp-19h] BYREF
  LPCWSTR lpszNodeName; // [rsp+68h] [rbp-11h] BYREF
  __int64 v48; // [rsp+70h] [rbp-9h] BYREF
  char v49[8]; // [rsp+78h] [rbp-1h] BYREF
  PVOID RestartKey[2]; // [rsp+80h] [rbp+7h] BYREF
  __int64 v51; // [rsp+90h] [rbp+17h]
  int v52; // [rsp+E0h] [rbp+67h] BYREF
  int v53; // [rsp+E8h] [rbp+6Fh] BYREF
  const char *v54; // [rsp+F8h] [rbp+7Fh] BYREF

  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    v53 = 458;
    v54 = "CSpCluster::_InitializeClusterState";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      a1,
      (unsigned int)word_18030A67A,
      (_DWORD)a3,
      a4,
      (__int64)&v54,
      (__int64)&v53);
  }
  v45 = 0;
  lpszNodeName = 0;
  v48 = 0;
  cchName = 16;
  v51 = 0;
  *(_OWORD *)RestartKey = 0;
  v7 = 0;
  v52 = 0;
  *(_QWORD *)a2 = 0;
  *((_BYTE *)a2 + 8) = 0;
  wil::EnterCriticalSection(v49, a1 + 8);
  if ( *(_QWORD *)(a1 + 72) )
    goto LABEL_9;
  v10 = OpenCluster(0);
  *(_QWORD *)(a1 + 72) = v10;
  if ( !v10 )
  {
    v7 = 1;
    LastError = _status_t::GetLastError(a2);
    LODWORD(v9) = dword_18039EB68;
    if ( (unsigned int)dword_18039EB68 <= 2 )
      goto LABEL_9;
    LODWORD(v54) = 485;
    v14 = &word_180309306;
    goto LABEL_7;
  }
  LastError = SmGetClusterFQDN(0, &v45);
  *(_DWORD *)a2 = LastError;
  if ( LastError < 0 )
  {
    v7 = 2;
    LODWORD(v9) = dword_18039EB68;
    if ( (unsigned int)dword_18039EB68 > 2 )
    {
      LODWORD(v54) = 495;
      v14 = (__int16 *)byte_18030A01B;
LABEL_7:
      v53 = LastError;
LABEL_8:
      v42 = "CSpCluster::_InitializeClusterState";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v9,
        (_DWORD)v14,
        v12,
        v13,
        (__int64)&v42,
        (__int64)&v54,
        (__int64)&v53);
      goto LABEL_9;
    }
    goto LABEL_9;
  }
  LastError = SmGetComputerNameByFormat(ComputerNameDnsHostname, (unsigned __int16 **)&lpszNodeName);
  *(_DWORD *)a2 = LastError;
  if ( LastError >= 0 )
  {
    v19 = OpenClusterNode(*(HCLUSTER *)(a1 + 72), lpszNodeName);
    *(_QWORD *)(a1 + 80) = v19;
    if ( !v19 )
    {
      v7 = 4;
      LastError = _status_t::GetLastError(a2);
      LODWORD(v9) = dword_18039EB68;
      if ( (unsigned int)dword_18039EB68 > 2 )
      {
        LODWORD(v54) = 515;
        v14 = (__int16 *)byte_18030ADC3;
        goto LABEL_7;
      }
      goto LABEL_9;
    }
    ClusterNodeId = GetClusterNodeId(v19, (LPWSTR)(a1 + 88), &cchName);
    LODWORD(v9) = ClusterNodeId;
    if ( ClusterNodeId > 0 )
      LODWORD(v9) = (unsigned __int16)ClusterNodeId | 0x80070000;
    *(_DWORD *)a2 = (_DWORD)v9;
    if ( (int)v9 < 0 )
    {
      v7 = 5;
      if ( (unsigned int)dword_18039EB68 > 2 )
      {
        v53 = (int)v9;
        LODWORD(v54) = 525;
        v14 = (__int16 *)&unk_180308B30;
        goto LABEL_8;
      }
      goto LABEL_9;
    }
    if ( (int)_o__wtoi(a1 + 88) <= 0 )
      v21 = 0;
    else
      v21 = 1LL << ((unsigned __int8)_o__wtoi(a1 + 88) - 1);
    *(_QWORD *)(a1 + 120) = v21;
    v22 = CSpCluster::_ReadClusterRegistry(a1, &v42, 0, L"SpacesSubSystemAutomaticClusteringEnabled", a1 + 152);
    *(_QWORD *)a2 = *(_QWORD *)v22;
    *((_DWORD *)a2 + 2) = *(_DWORD *)(v22 + 8);
    LODWORD(v9) = *(_DWORD *)a2;
    if ( *(_DWORD *)a2 == -2147024894 )
    {
      *(_DWORD *)(a1 + 152) = 1;
    }
    else if ( (int)v9 < 0 )
    {
      v7 = 6;
      if ( (unsigned int)dword_18039EB68 > 2 )
      {
        v53 = *(_DWORD *)a2;
        LODWORD(v54) = 547;
        v14 = word_18030A95A;
        goto LABEL_8;
      }
      goto LABEL_9;
    }
    v7 = 7;
    v23 = CSpCluster::_ReadClusterRegistry(a1, &v42, L"Spaceport\\Parameters", L"RepairQueueDepth", a1 + 156);
    *(_QWORD *)a2 = *(_QWORD *)v23;
    *((_DWORD *)a2 + 2) = *(_DWORD *)(v23 + 8);
    v9 = (void **)*(unsigned int *)a2;
    if ( (_DWORD)v9 == -2147024894 )
    {
      v26 = SuInitialize(v9);
      _status_t::SetBoolGle(a2, v26);
      LODWORD(v9) = *(_DWORD *)a2;
      if ( *(int *)a2 < 0 )
      {
        if ( (unsigned int)dword_18039EB68 <= 2 )
          goto LABEL_9;
        LODWORD(v54) = 571;
        v27 = word_18030BAA2;
        goto LABEL_42;
      }
      v42 = (const char *)&v48;
      v43 = 0;
      v44 = 1;
      Control = SuGetControl(&v43);
      _status_t::SetBoolGle(a2, Control);
      wil::details::out_param_t<wistd::unique_ptr<_SP_CONVERT_PARAMS,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_SP_CONVERT_PARAMS,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&v42);
      v31 = *(_DWORD *)a2;
      if ( *(int *)a2 < 0 )
      {
        if ( (unsigned int)dword_18039EB68 > 2 )
        {
          v53 = *(_DWORD *)a2;
          LODWORD(v54) = 583;
          v42 = "CSpCluster::_InitializeClusterState";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v31,
            (unsigned int)&unk_18030C710,
            v29,
            v30,
            (__int64)&v42,
            (__int64)&v54,
            (__int64)&v53);
        }
        SuCleanup();
        goto LABEL_9;
      }
      *(_DWORD *)(a1 + 156) = *(_DWORD *)(v48 + 76);
      SuCleanup();
    }
    else if ( (int)v9 < 0 )
    {
      if ( (unsigned int)dword_18039EB68 <= 2 )
        goto LABEL_9;
      LODWORD(v54) = 591;
      v27 = (__int16 *)&dword_18030C98C;
      goto LABEL_42;
    }
    v32 = CSpCluster::_ReadClusterRegistry(a1, &v42, L"StorageSubsystemPolicies", L"FDAwarenessDefault", a1 + 160);
    *(_QWORD *)a2 = *(_QWORD *)v32;
    *((_DWORD *)a2 + 2) = *(_DWORD *)(v32 + 8);
    LODWORD(v9) = *(_DWORD *)a2;
    if ( *(_DWORD *)a2 == -2147024894 )
    {
      *(_DWORD *)(a1 + 160) = 1;
    }
    else if ( (int)v9 < 0 )
    {
      v7 = 8;
      if ( (unsigned int)dword_18039EB68 <= 2 )
        goto LABEL_9;
      LODWORD(v54) = 607;
      v27 = (__int16 *)byte_180309F51;
      goto LABEL_42;
    }
    v33 = CSpCluster::_ReadClusterRegistry(a1, &v42, 0, L"S2DEnabled", &v52);
    *(_QWORD *)a2 = *(_QWORD *)v33;
    *((_DWORD *)a2 + 2) = *(_DWORD *)(v33 + 8);
    LODWORD(v9) = *(_DWORD *)a2;
    if ( *(int *)a2 < 0 )
    {
      if ( (_DWORD)v9 != -2147024894 )
      {
        v7 = 9;
        if ( (unsigned int)dword_18039EB68 <= 2 )
          goto LABEL_9;
        LODWORD(v54) = 627;
        v27 = (__int16 *)&byte_18030816F;
        goto LABEL_42;
      }
      v34 = 1;
    }
    else
    {
      v34 = (v52 == 1) + 1;
    }
    *(_DWORD *)(a1 + 164) = v34;
    MessagePipe = CSpCluster::_LoadMessagePipe((CSpCluster *)a1);
    if ( MessagePipe )
    {
      LODWORD(v9) = MessagePipe | 0x85200000;
      *(_DWORD *)a2 = MessagePipe | 0x85200000;
      v7 = 10;
      if ( (unsigned int)dword_18039EB68 <= 2 )
        goto LABEL_9;
      LODWORD(v54) = 642;
      v27 = word_18030C8FA;
    }
    else
    {
      *(_DWORD *)a2 = 85983232;
      ClusterApi = CSpCluster::_LoadClusterApi(0);
      if ( ClusterApi )
      {
        LODWORD(v9) = ClusterApi | 0x85200000;
        *(_DWORD *)a2 = (_DWORD)v9;
        v7 = 11;
        if ( (unsigned int)dword_18039EB68 <= 2 )
          goto LABEL_9;
        LODWORD(v54) = 652;
        v27 = (__int16 *)byte_18030C3C3;
      }
      else
      {
        *(_DWORD *)a2 = 85983232;
        v7 = 12;
        v37 = SuEnumerateClusterNodes((PVOID)(a1 + 184));
        _status_t::SetBoolGle(a2, v37);
        LODWORD(v9) = *(_DWORD *)a2;
        if ( *(int *)a2 >= 0 )
        {
          v38 = CMapBase<_SP_ID,_SU_DRIVE_OBJECT *>::Begin(a1 + 184, &v42);
          *(_OWORD *)RestartKey = *(_OWORD *)v38;
          v51 = *(_QWORD *)(v38 + 16);
          while ( RestartKey[0] )
          {
            v9 = (void **)RestartKey[1];
            if ( !RestartKey[1] )
              break;
            if ( (Microsoft_Windows_StorageManagement_WSP_SpacesEnableBits & 4) != 0 )
            {
              SpNodeState = GetSpNodeState(*((const unsigned __int16 **)RestartKey[1] + 1));
              if ( RestartKey[1] )
                v41 = *((_QWORD *)RestartKey[1] + 1);
              else
                v41 = 0;
              McTemplateU0zq_EventWriteTransfer(v39, ClusterNodeArrived, v41, SpNodeState);
            }
            CMapIter<unsigned short const *,_SUEX_SPACE_OBJECT *>::Next(RestartKey);
          }
          if ( (Microsoft_Windows_StorageManagement_WSP_SpacesEnableBits & 4) != 0 )
            McTemplateU0z_EventWriteTransfer(v9, ClusterStateInitializationSucceeded, v45);
          if ( a3 )
          {
            *a3 = v45;
            v45 = 0;
          }
          goto LABEL_9;
        }
        if ( (unsigned int)dword_18039EB68 <= 2 )
          goto LABEL_9;
        LODWORD(v54) = 670;
        v27 = word_18030939A;
      }
    }
LABEL_42:
    v42 = "CSpCluster::_InitializeClusterState";
    v53 = (int)v9;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (_DWORD)v9,
      (_DWORD)v27,
      v24,
      v25,
      (__int64)&v42,
      (__int64)&v54,
      (__int64)&v53);
    goto LABEL_9;
  }
  v7 = 3;
  LODWORD(v9) = dword_18039EB68;
  if ( (unsigned int)dword_18039EB68 > 2 )
  {
    LODWORD(v54) = 505;
    v14 = &word_18030AAA6;
    goto LABEL_7;
  }
LABEL_9:
  if ( *(int *)a2 < 0 )
  {
    if ( (Microsoft_Windows_StorageManagement_WSP_SpacesEnableBits & 1) != 0 )
      McTemplateU0zqd_EventWriteTransfer((_DWORD)v9, v8, (_DWORD)v45, v7, *(_DWORD *)a2);
    if ( (unsigned int)dword_18039EB68 > 2 && (unsigned __int8)tlgKeywordOn(&dword_18039EB68, 1024) )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        &dword_18039EB68,
        &byte_1803081A7,
        0,
        0);
    CSpCluster::_UninitializeClusterState((CSpCluster *)a1, 0);
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::reset(
    v49,
    0);
  SmFreeString((unsigned __int16 **)&lpszNodeName);
  SmFreeString(&v45);
  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    v53 = 709;
    v54 = "CSpCluster::_InitializeClusterState";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v15,
      (unsigned int)word_18030C932,
      v16,
      v17,
      (__int64)&v54,
      (__int64)&v53);
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(v49);
  wistd::unique_ptr<_SUEX_EXTENDEDSTATUS_OBJECT,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(
    &v48,
    0);
  return a2;
}

```

## disassembly

```asm
0x18004ff18  mov     [rsp-8+arg_10], rbx
0x18004ff1d  push    rbp
0x18004ff1e  push    rsi
0x18004ff1f  push    rdi
0x18004ff20  push    r12
0x18004ff22  push    r13
0x18004ff24  push    r14
0x18004ff26  push    r15
0x18004ff28  lea     rbp, [rsp-27h]
0x18004ff2d  sub     rsp, 0A0h
0x18004ff34  mov     r15, r8
0x18004ff37  mov     rbx, rdx
0x18004ff3a  mov     rsi, rcx
0x18004ff3d  mov     eax, cs:dword_18039EB68
0x18004ff43  lea     r14, aCspclusterInit; "CSpCluster::_InitializeClusterState"
0x18004ff4a  cmp     eax, 5
0x18004ff4d  jbe     short loc_18004FF78
0x18004ff4f  mov     [rbp+57h+arg_8], 1CAh
0x18004ff56  mov     [rbp+57h+arg_18], r14
0x18004ff5a  lea     rax, [rbp+57h+arg_8]
0x18004ff5e  mov     [rsp+0D0h+var_A8], rax
0x18004ff63  lea     rax, [rbp+57h+arg_18]
0x18004ff67  mov     [rsp+0D0h+var_B0], rax
0x18004ff6c  lea     rdx, word_18030A67A
0x18004ff73  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18004ff78  xor     r12d, r12d
0x18004ff7b  mov     [rbp+57h+var_78], r12
0x18004ff7f  mov     [rbp+57h+lpszNodeName], r12
0x18004ff83  mov     [rbp+57h+var_60], r12
0x18004ff87  mov     [rbp+57h+cchName], 10h
0x18004ff8e  mov     [rbp+57h+var_40], r12
0x18004ff92  xorps   xmm0, xmm0
0x18004ff95  movdqu  xmmword ptr [rbp+57h+RestartKey], xmm0
0x18004ff9a  mov     edi, r12d
0x18004ff9d  mov     [rbp+57h+arg_0], r12d
0x18004ffa1  mov     [rbx], r12
0x18004ffa4  mov     [rbx+8], r12b
0x18004ffa8  lea     rdx, [rsi+8]
0x18004ffac  lea     rcx, [rbp+57h+var_58]
0x18004ffb0  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x18004ffb5  nop
0x18004ffb6  lea     r13d, [r12+2]
0x18004ffbb  cmp     [rsi+48h], r12
0x18004ffbf  jnz     short loc_180050027
0x18004ffc1  xor     ecx, ecx; lpszClusterName
0x18004ffc3  call    cs:__imp_OpenCluster
0x18004ffca  nop     dword ptr [rax+rax+00h]
0x18004ffcf  mov     [rsi+48h], rax
0x18004ffd3  test    rax, rax
0x18004ffd6  jnz     loc_180050116
0x18004ffdc  lea     edi, [rax+1]
0x18004ffdf  mov     rcx, rbx; this
0x18004ffe2  call    ?GetLastError@_status_t@@QEAAJXZ; _status_t::GetLastError(void)
0x18004ffe7  mov     ecx, cs:dword_18039EB68
0x18004ffed  cmp     ecx, r13d
0x18004fff0  jbe     short loc_180050027
0x18004fff2  mov     dword ptr [rbp+57h+arg_18], 1E5h
0x18004fff9  lea     rdx, word_180309306
0x180050000  mov     [rbp+57h+arg_8], eax
0x180050003  lea     rax, [rbp+57h+arg_8]
0x180050007  mov     [rsp+0D0h+var_A0], rax
0x18005000c  lea     rax, [rbp+57h+arg_18]
0x180050010  mov     [rsp+0D0h+var_A8], rax
0x180050015  lea     rax, [rbp+57h+var_90]
0x180050019  mov     [rsp+0D0h+var_B0], rax
0x18005001e  mov     [rbp+57h+var_90], r14
0x180050022  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180050027  lea     r14, aCspclusterInit; "CSpCluster::_InitializeClusterState"
0x18005002e  mov     eax, [rbx]
0x180050030  test    eax, eax
0x180050032  jns     short loc_180050090
0x180050034  test    cs:Microsoft_Windows_StorageManagement_WSP_SpacesEnableBits, 1
0x18005003b  jz      short loc_18005004D
0x18005003d  mov     dword ptr [rsp+0D0h+var_B0], eax
0x180050041  mov     r9d, edi
0x180050044  mov     r8, [rbp+57h+var_78]
0x180050048  call    McTemplateU0zqd_EventWriteTransfer
0x18005004d  mov     eax, cs:dword_18039EB68
0x180050053  cmp     eax, r13d
0x180050056  jbe     short loc_180050086
0x180050058  mov     edx, 400h
0x18005005d  lea     rcx, dword_18039EB68
0x180050064  call    _tlgKeywordOn
0x180050069  test    al, al
0x18005006b  jz      short loc_180050086
0x18005006d  xor     r9d, r9d
0x180050070  xor     r8d, r8d
0x180050073  lea     rdx, byte_1803081A7
0x18005007a  lea     rcx, dword_18039EB68
0x180050081  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180050086  xor     edx, edx; int
0x180050088  mov     rcx, rsi; this
0x18005008b  call    ?_UninitializeClusterState@CSpCluster@@AEAAXH@Z; CSpCluster::_UninitializeClusterState(int)
0x180050090  xor     edx, edx
0x180050092  lea     rcx, [rbp+57h+var_58]
0x180050096  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_RTL_CRITICAL_SECTION@@@Z; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::reset(_RTL_CRITICAL_SECTION *)
0x18005009b  lea     rcx, [rbp+57h+lpszNodeName]; unsigned __int16 **
0x18005009f  call    ?SmFreeString@@YAXAEAPEAG@Z; SmFreeString(ushort * &)
0x1800500a4  lea     rcx, [rbp+57h+var_78]; unsigned __int16 **
0x1800500a8  call    ?SmFreeString@@YAXAEAPEAG@Z; SmFreeString(ushort * &)
0x1800500ad  mov     eax, cs:dword_18039EB68
0x1800500b3  cmp     eax, 5
0x1800500b6  jbe     short loc_1800500E2
0x1800500b8  mov     [rbp+57h+arg_8], 2C5h
0x1800500bf  mov     [rbp+57h+arg_18], r14
0x1800500c3  lea     rax, [rbp+57h+arg_8]
0x1800500c7  mov     [rsp+0D0h+var_A8], rax
0x1800500cc  lea     rax, [rbp+57h+arg_18]
0x1800500d0  mov     [rsp+0D0h+var_B0], rax
0x1800500d5  lea     rdx, word_18030C932
0x1800500dc  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800500e1  nop
0x1800500e2  lea     rcx, [rbp+57h+var_58]
0x1800500e6  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x1800500eb  nop
0x1800500ec  xor     edx, edx
0x1800500ee  lea     rcx, [rbp+57h+var_60]
0x1800500f2  call    ?reset@?$unique_ptr@U_SUEX_EXTENDEDSTATUS_OBJECT@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAU_SUEX_EXTENDEDSTATUS_OBJECT@@@Z; wistd::unique_ptr<_SUEX_EXTENDEDSTATUS_OBJECT,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(_SUEX_EXTENDEDSTATUS_OBJECT *)
0x1800500f7  mov     rax, rbx
0x1800500fa  mov     rbx, [rsp+0D0h+arg_10]
0x180050102  add     rsp, 0A0h
0x180050109  pop     r15
0x18005010b  pop     r14
0x18005010d  pop     r13
0x18005010f  pop     r12
0x180050111  pop     rdi
0x180050112  pop     rsi
0x180050113  pop     rbp
0x180050114  retn
0x180050116  lea     rdx, [rbp+57h+var_78]; unsigned __int16 **
0x18005011a  xor     ecx, ecx; unsigned __int16 *
0x18005011c  call    ?SmGetClusterFQDN@@YAJPEBGPEAPEAG@Z; SmGetClusterFQDN(ushort const *,ushort * *)
0x180050121  mov     [rbx], eax
0x180050123  test    eax, eax
0x180050125  jns     short loc_18005014C
0x180050127  mov     edi, r13d
0x18005012a  mov     ecx, cs:dword_18039EB68
0x180050130  cmp     ecx, r13d
0x180050133  jbe     loc_180050027
0x180050139  mov     dword ptr [rbp+57h+arg_18], 1EFh
0x180050140  lea     rdx, byte_18030A01B
0x180050147  jmp     loc_180050000
0x18005014c  lea     rdx, [rbp+57h+lpszNodeName]; unsigned __int16 **
0x180050150  mov     ecx, 1; NameType
0x180050155  call    ?SmGetComputerNameByFormat@@YAJW4_COMPUTER_NAME_FORMAT@@PEAPEAG@Z; SmGetComputerNameByFormat(_COMPUTER_NAME_FORMAT,ushort * *)
0x18005015a  mov     [rbx], eax
0x18005015c  test    eax, eax
0x18005015e  jns     short loc_180050187
0x180050160  mov     edi, 3
0x180050165  mov     ecx, cs:dword_18039EB68
0x18005016b  cmp     ecx, r13d
0x18005016e  jbe     loc_180050027
0x180050174  mov     dword ptr [rbp+57h+arg_18], 1F9h
0x18005017b  lea     rdx, word_18030AAA6
0x180050182  jmp     loc_180050000
0x180050187  mov     rdx, [rbp+57h+lpszNodeName]; lpszNodeName
0x18005018b  mov     rcx, [rsi+48h]; hCluster
0x18005018f  call    cs:__imp_OpenClusterNode
0x180050196  nop     dword ptr [rax+rax+00h]
0x18005019b  mov     [rsi+50h], rax
0x18005019f  test    rax, rax
0x1800501a2  jnz     short loc_1800501D1
0x1800501a4  lea     edi, [rax+4]
0x1800501a7  mov     rcx, rbx; this
0x1800501aa  call    ?GetLastError@_status_t@@QEAAJXZ; _status_t::GetLastError(void)
0x1800501af  mov     ecx, cs:dword_18039EB68
0x1800501b5  cmp     ecx, r13d
0x1800501b8  jbe     loc_180050027
0x1800501be  mov     dword ptr [rbp+57h+arg_18], 203h
0x1800501c5  lea     rdx, byte_18030ADC3
0x1800501cc  jmp     loc_180050000
0x1800501d1  lea     rdi, [rsi+58h]
0x1800501d5  lea     r8, [rbp+57h+cchName]; lpcchName
0x1800501d9  mov     rdx, rdi; lpszNodeId
0x1800501dc  mov     rcx, rax; hNode
0x1800501df  call    cs:__imp_GetClusterNodeId
0x1800501e6  nop     dword ptr [rax+rax+00h]
0x1800501eb  mov     ecx, eax
0x1800501ed  test    eax, eax
0x1800501ef  jle     short loc_1800501FA
0x1800501f1  movzx   ecx, ax
0x1800501f4  or      ecx, 80070000h
0x1800501fa  mov     [rbx], ecx
0x1800501fc  test    ecx, ecx
0x1800501fe  jns     short loc_18005022A
0x180050200  mov     edi, 5
0x180050205  mov     eax, cs:dword_18039EB68
0x18005020b  cmp     eax, r13d
0x18005020e  jbe     loc_180050027
0x180050214  mov     [rbp+57h+arg_8], ecx
0x180050217  mov     dword ptr [rbp+57h+arg_18], 20Dh
0x18005021e  lea     rdx, unk_180308B30
0x180050225  jmp     loc_180050003
0x18005022a  mov     rcx, rdi
0x18005022d  call    cs:__imp__o__wtoi
0x180050234  nop     dword ptr [rax+rax+00h]
0x180050239  test    eax, eax
0x18005023b  jle     short loc_180050259
0x18005023d  mov     rcx, rdi
0x180050240  call    cs:__imp__o__wtoi
0x180050247  nop     dword ptr [rax+rax+00h]
0x18005024c  lea     ecx, [rax-1]
0x18005024f  mov     edx, 1
0x180050254  shl     rdx, cl
0x180050257  jmp     short loc_18005025C
0x180050259  mov     rdx, r12
0x18005025c  mov     [rsi+78h], rdx
0x180050260  lea     rdi, [rsi+98h]
0x180050267  mov     [rsp+0D0h+var_B0], rdi
0x18005026c  lea     r9, aSpacessubsyste; "SpacesSubSystemAutomaticClusteringEnabl"...
0x180050273  xor     r8d, r8d
0x180050276  lea     rdx, [rbp+57h+var_90]
0x18005027a  mov     rcx, rsi
0x18005027d  call    ?_ReadClusterRegistry@CSpCluster@@AEAA?AV_status_t@@PEBG0PEAEK@Z; CSpCluster::_ReadClusterRegistry(ushort const *,ushort const *,uchar *,ulong)
0x180050282  movsd   xmm0, qword ptr [rax]
0x180050286  movsd   qword ptr [rbx], xmm0
0x18005028a  mov     eax, [rax+8]
0x18005028d  mov     [rbx+8], eax
0x180050290  mov     ecx, [rbx]
0x180050292  cmp     ecx, 80070002h
0x180050298  jnz     loc_180050354
0x18005029e  mov     dword ptr [rdi], 1
0x1800502a4  mov     edi, 7
0x1800502a9  lea     r14, [rsi+9Ch]
0x1800502b0  mov     [rsp+0D0h+var_B0], r14
0x1800502b5  lea     r9, aRepairqueuedep; "RepairQueueDepth"
0x1800502bc  lea     r8, szSubKey; "Spaceport\\Parameters"
0x1800502c3  lea     rdx, [rbp+57h+var_90]
0x1800502c7  mov     rcx, rsi
0x1800502ca  call    ?_ReadClusterRegistry@CSpCluster@@AEAA?AV_status_t@@PEBG0PEAEK@Z; CSpCluster::_ReadClusterRegistry(ushort const *,ushort const *,uchar *,ulong)
0x1800502cf  movsd   xmm0, qword ptr [rax]
0x1800502d3  movsd   qword ptr [rbx], xmm0
0x1800502d7  mov     eax, [rax+8]
0x1800502da  mov     [rbx+8], eax
0x1800502dd  mov     ecx, [rbx]
0x1800502df  cmp     ecx, 80070002h
0x1800502e5  jnz     loc_1800504AB
0x1800502eb  call    ?SuInitialize@@YAHXZ; SuInitialize(void)
0x1800502f0  mov     edx, eax; int
0x1800502f2  mov     rcx, rbx; this
0x1800502f5  call    ?SetBoolGle@_status_t@@QEAAJH@Z; _status_t::SetBoolGle(int)
0x1800502fa  mov     ecx, [rbx]
0x1800502fc  test    ecx, ecx
0x1800502fe  jns     loc_180050386
0x180050304  mov     eax, cs:dword_18039EB68
0x18005030a  cmp     eax, r13d
0x18005030d  jbe     loc_180050027
0x180050313  mov     dword ptr [rbp+57h+arg_18], 23Bh
0x18005031a  lea     rdx, word_18030BAA2
0x180050321  lea     rax, [rbp+57h+arg_8]
0x180050325  mov     [rsp+0D0h+var_A0], rax
0x18005032a  lea     rax, [rbp+57h+arg_18]
0x18005032e  mov     [rsp+0D0h+var_A8], rax
0x180050333  lea     r14, aCspclusterInit; "CSpCluster::_InitializeClusterState"
0x18005033a  lea     rax, [rbp+57h+var_90]
0x18005033e  mov     [rbp+57h+var_90], r14
0x180050342  mov     [rsp+0D0h+var_B0], rax
0x180050347  mov     [rbp+57h+arg_8], ecx
0x18005034a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18005034f  jmp     loc_18005002E
0x180050354  test    ecx, ecx
0x180050356  jns     loc_1800502A4
0x18005035c  mov     edi, 6
0x180050361  mov     eax, cs:dword_18039EB68
0x180050367  cmp     eax, r13d
0x18005036a  jbe     loc_180050027
0x180050370  mov     [rbp+57h+arg_8], ecx
0x180050373  mov     dword ptr [rbp+57h+arg_18], 223h
0x18005037a  lea     rdx, word_18030A95A
0x180050381  jmp     loc_180050003
0x180050386  lea     rax, [rbp+57h+var_60]
0x18005038a  mov     [rbp+57h+var_90], rax
0x18005038e  mov     [rbp+57h+var_88], r12
0x180050392  mov     [rbp+57h+var_80], 1
0x180050396  lea     rcx, [rbp+57h+var_88]; struct _SP_CONTROL_INFO **
0x18005039a  call    ?SuGetControl@@YAHPEAPEAU_SP_CONTROL_INFO@@@Z; SuGetControl(_SP_CONTROL_INFO * *)
0x18005039f  mov     edx, eax; int
0x1800503a1  mov     rcx, rbx; this
0x1800503a4  call    ?SetBoolGle@_status_t@@QEAAJH@Z; _status_t::SetBoolGle(int)
0x1800503a9  lea     rcx, [rbp+57h+var_90]
0x1800503ad  call    ??1?$out_param_t@V?$unique_ptr@U_SP_CONVERT_PARAMS@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_SP_CONVERT_PARAMS,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_SP_CONVERT_PARAMS,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x1800503b2  mov     ecx, [rbx]
0x1800503b4  test    ecx, ecx
0x1800503b6  jns     short loc_180050413
0x1800503b8  mov     eax, cs:dword_18039EB68
0x1800503be  cmp     eax, r13d
0x1800503c1  jbe     short loc_180050401
0x1800503c3  mov     [rbp+57h+arg_8], ecx
0x1800503c6  mov     dword ptr [rbp+57h+arg_18], 247h
0x1800503cd  lea     r14, aCspclusterInit; "CSpCluster::_InitializeClusterState"
0x1800503d4  mov     [rbp+57h+var_90], r14
0x1800503d8  lea     rax, [rbp+57h+arg_8]
0x1800503dc  mov     [rsp+0D0h+var_A0], rax
0x1800503e1  lea     rax, [rbp+57h+arg_18]
0x1800503e5  mov     [rsp+0D0h+var_A8], rax
0x1800503ea  lea     rax, [rbp+57h+var_90]
0x1800503ee  mov     [rsp+0D0h+var_B0], rax
0x1800503f3  lea     rdx, unk_18030C710
0x1800503fa  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800503ff  jmp     short loc_180050408
  ... truncated ...
```
