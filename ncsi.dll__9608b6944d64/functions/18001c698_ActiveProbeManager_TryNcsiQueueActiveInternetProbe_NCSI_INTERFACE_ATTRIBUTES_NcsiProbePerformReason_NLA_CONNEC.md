# ActiveProbeManager::TryNcsiQueueActiveInternetProbe(NCSI_INTERFACE_ATTRIBUTES *,NcsiProbePerformReason,_NLA_CONNECTIVITY_FAMILY)

- ea: `0x18001c698`
- end: `0x18001d0c5`
- name: `?TryNcsiQueueActiveInternetProbe@ActiveProbeManager@@SA?AW4ActiveProbeQueueResult@@PEAVNCSI_INTERFACE_ATTRIBUTES@@W4NcsiProbePerformReason@@W4_NLA_CONNECTIVITY_FAMILY@@@Z`
- size: `2605`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `12`
- callee_count: `27`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000de6c`
- `0x18001be94`
- `0x18001d1d4`
- `0x18002eb80`
- `0x18002ff00`
- `0x18003d948`
- `0x18004ff90`
- `0x18005735c`
- `0x180058ff0`
- `0x18005a838`
- `0x18005bf10`
- `0x18005cac0`

## callees

- `0x180006d6c`
- `0x180006e74`
- `0x18000d188`
- `0x18000d208`
- `0x18001c698`
- `0x18001d71c`
- `0x18001e180`
- `0x18001f904`
- `0x1800208a0`
- `0x180021144`
- `0x1800216f0`
- `0x180025b70`
- `0x18002c860`
- `0x18002cd80`
- `0x18002d09c`
- `0x1800301e8`
- `0x18003f2b8`
- `0x180042220`
- `0x1800435b4`
- `0x180047240`
- `0x180047f60`
- `0x180047f78`
- `0x18004f664`
- `0x18006082c`
- `0x1800694e8`
- `0x18006a83c`
- `0x180077ad0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001cfe5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d058`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001cfe5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d058`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ce36`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ce36`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001cedd`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001cedd`
- `NSI!NsiFreeTable` at `0x18001cad7`
- `NSI!NsiFreeTable` at `0x18001cbdc`
- `NSI!NsiFreeTable` at `0x18001cd25`
- `NSI!NsiFreeTable` at `0x18001ce23`
- `NSI!NsiFreeTable` at `0x18001d01f`
- `NSI!NsiFreeTable` at `0x18001d092`
- `NSI!NsiFreeTable` at `0x18001cad7`
- `NSI!NsiFreeTable` at `0x18001cbdc`
- `NSI!NsiFreeTable` at `0x18001cd25`
- `NSI!NsiFreeTable` at `0x18001ce23`
- `NSI!NsiFreeTable` at `0x18001d01f`
- `NSI!NsiFreeTable` at `0x18001d092`

## string_xrefs

- `0x18001c725`: `Disabled by registry`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 __fastcall ActiveProbeManager::TryNcsiQueueActiveInternetProbe(__int64 *a1, unsigned int a2, int a3)
{
  unsigned int v4; // edx
  __int64 v5; // r8
  __int64 v6; // r9
  NcsiConfigData *v8; // rcx
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 v11; // r8
  __int64 v12; // r9
  Ncsi::Power *v13; // rcx
  __int64 v14; // r8
  __int64 v15; // r9
  Ncsi::Power *v16; // rcx
  bool ShouldDisconnectInStandby; // al
  bool v18; // r12
  __int64 v19; // r8
  __int64 v20; // r9
  __int64 v21; // rcx
  const unsigned __int16 **v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // r8
  __int64 v25; // r9
  unsigned int v26; // r8d
  LPCRITICAL_SECTION v27; // rbx
  __int64 v28; // r8
  __int64 v29; // r9
  __int64 v30; // r8
  __int64 v31; // r9
  _QWORD *i; // r14
  const unsigned __int16 *TickCount64; // r13
  bool v34; // r15
  const char **v35; // rdx
  const char *v36; // rax
  unsigned int v37; // edi
  unsigned int v38; // edi
  int v39; // [rsp+20h] [rbp-17F8h]
  int v40; // [rsp+20h] [rbp-17F8h]
  int v41; // [rsp+28h] [rbp-17F0h]
  int v42; // [rsp+28h] [rbp-17F0h]
  int v43; // [rsp+30h] [rbp-17E8h]
  bool IsSystemInStandby; // [rsp+50h] [rbp-17C8h]
  char v45[7]; // [rsp+51h] [rbp-17C7h] BYREF
  __int64 v46; // [rsp+58h] [rbp-17C0h] BYREF
  int v47[2]; // [rsp+60h] [rbp-17B8h] BYREF
  const char *v48; // [rsp+68h] [rbp-17B0h] BYREF
  const unsigned __int16 *v49[2]; // [rsp+70h] [rbp-17A8h] BYREF
  _OWORD v50[2]; // [rsp+80h] [rbp-1798h] BYREF
  __int64 v51; // [rsp+A0h] [rbp-1778h] BYREF
  _BYTE v52[1096]; // [rsp+A8h] [rbp-1770h] BYREF
  char v53[216]; // [rsp+4F0h] [rbp-1328h] BYREF
  char v54[600]; // [rsp+5C8h] [rbp-1250h] BYREF
  int v55; // [rsp+820h] [rbp-FF8h]
  int v56; // [rsp+824h] [rbp-FF4h]
  _BYTE Src[1968]; // [rsp+830h] [rbp-FE8h] BYREF
  _BYTE v58[1960]; // [rsp+FE0h] [rbp-838h] BYREF
  __int64 *v59; // [rsp+1788h] [rbp-90h]
  int v60; // [rsp+1790h] [rbp-88h] BYREF
  const char *v61; // [rsp+1798h] [rbp-80h] BYREF
  LPCRITICAL_SECTION lpCriticalSection[2]; // [rsp+17A0h] [rbp-78h] BYREF
  __int128 v63; // [rsp+17B0h] [rbp-68h] BYREF
  __int128 v64; // [rsp+17C0h] [rbp-58h]
  __int64 v65; // [rsp+17D0h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+1818h] [rbp+0h]
  unsigned int v67; // [rsp+1828h] [rbp+10h] BYREF

  v67 = a2;
  v59 = a1;
  v60 = a3;
  if ( !g_ncsiConfigData )
  {
    if ( (unsigned int)dword_18009A080 > 5 )
    {
      v61 = (const char *)ToString((unsigned int)v60);
      lpCriticalSection[0] = (LPCRITICAL_SECTION)NcsiProbePerformReasonToString(v4);
      *(_QWORD *)v47 = *v59;
      v46 = (__int64)"Disabled by registry";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        *(__int64 *)v47,
        (int)&word_18008C13E,
        v5,
        v6,
        (const unsigned __int16 **)&v46,
        (__int64)v47,
        (const unsigned __int16 **)lpCriticalSection,
        (const unsigned __int16 **)&v61);
    }
    return 2;
  }
  if ( NcsiConfigData::ActiveProbesGPDisabled((NcsiConfigData *)a1) )
  {
    if ( (unsigned int)dword_18009A080 > 5 )
    {
      v46 = ToString((unsigned int)v60);
      *(_QWORD *)v47 = NcsiProbePerformReasonToString(a2);
      lpCriticalSection[0] = (LPCRITICAL_SECTION)*v59;
      v61 = "Disabled by Group Policy";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        (__int64)lpCriticalSection[0],
        (int)word_18008BFA2,
        v9,
        v10,
        (const unsigned __int16 **)&v61,
        (__int64)lpCriticalSection,
        (const unsigned __int16 **)v47,
        (const unsigned __int16 **)&v46);
    }
    return 2;
  }
  if ( NcsiConfigData::IsDisableNCSIConnectivityEvaluationSet(v8) )
  {
    if ( (unsigned int)dword_18009A080 > 5 )
    {
      v46 = ToString((unsigned int)v60);
      *(_QWORD *)v47 = NcsiProbePerformReasonToString(a2);
      lpCriticalSection[0] = (LPCRITICAL_SECTION)*v59;
      v61 = "DisableNCSIConnectivityEvaluation is set";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        (__int64)lpCriticalSection[0],
        (int)byte_18008C783,
        v11,
        v12,
        (const unsigned __int16 **)&v61,
        (__int64)lpCriticalSection,
        (const unsigned __int16 **)v47,
        (const unsigned __int16 **)&v46);
    }
    return 2;
  }
  v63 = 0;
  v64 = 0;
  v65 = 0;
  NsiNotifications::GetNsiInformation<0,0>::Refresh(&v63);
  memset_0(&v51, 0, 0x780u);
  memset(v50, 0, sizeof(v50));
  memset_0(v52, 0, 0x778u);
  v51 = 0;
  memset_0(v52, 0, 0x444u);
  memset_0(v53, 0, sizeof(v53));
  memset_0(v54, 0, sizeof(v54));
  v55 = 0;
  v56 = -1;
  NsiNotifications::GetNsiInformation<0,0>::iterator::iterator(
    (unsigned int)Src,
    v63,
    DWORD2(v63),
    v64,
    *((__int64 *)&v64 + 1),
    v65);
  memcpy_0(v58, Src, sizeof(v58));
  memcpy_0(Src, v50, 0x7A8u);
  memcpy_0(v50, v58, 0x7A8u);
  if ( (unsigned __int8)std::any_of_NsiNotifications::GetNsiInformation_0_0_::iterator__ActiveProbeManager::TryNcsiQueueActiveInternetProbe_::_3_::_lambda_1___(
                          v50,
                          Src) )
  {
    if ( (unsigned int)dword_18009A080 > 5 )
    {
      v46 = ToString((unsigned int)v60);
      *(_QWORD *)v47 = NcsiProbePerformReasonToString(a2);
      lpCriticalSection[0] = (LPCRITICAL_SECTION)*v59;
      v61 = "Disabled because Hidden interface";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        (__int64)lpCriticalSection[0],
        (int)byte_18008BE63,
        v14,
        v15,
        (const unsigned __int16 **)&v61,
        (__int64)lpCriticalSection,
        (const unsigned __int16 **)v47,
        (const unsigned __int16 **)&v46);
    }
LABEL_16:
    NsiFreeTable(v63, *((_QWORD *)&v63 + 1), v64, *((_QWORD *)&v64 + 1));
    return 2;
  }
  IsSystemInStandby = Ncsi::Power::IsSystemInStandby(v13);
  ShouldDisconnectInStandby = Ncsi::Power::ShouldDisconnectInStandby(v16);
  v18 = IsSystemInStandby && ShouldDisconnectInStandby;
  if ( a2 == 14 || !v18 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_NCSI_Fix_PreventingProbeLoopInNonDS>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_NCSI_Fix_PreventingProbeLoopInNonDS>::GetImpl'::`2'::impl) )
    {
      if ( a2 == 6 )
      {
        v21 = 493LL * v60;
        if ( HIDWORD(v59[v21 + 962]) >= 3 )
        {
          if ( (unsigned int)dword_18009A048 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18009A048, 0x400000000000LL) )
          {
            v46 = 2048;
            LODWORD(v61) = HIDWORD(v59[493 * v60 + 962]);
            *(_QWORD *)v47 = ToString(v60);
            lpCriticalSection[0] = (LPCRITICAL_SECTION)NcsiProbePerformReasonToString(6);
            v49[0] = *v22;
            v48 = "Suppressed proxy-changed probe after persistent failures";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
              v23,
              (int)byte_18008C529,
              v24,
              v25,
              (const unsigned __int16 **)&v48,
              (__int64)v49,
              (const unsigned __int16 **)lpCriticalSection,
              (const unsigned __int16 **)v47,
              (__int64)&v61,
              (__int64)&v46);
          }
          goto LABEL_16;
        }
      }
    }
    *(_OWORD *)lpCriticalSection = 0;
    std::weak_ptr<ActiveProbeManager>::lock(v21 * 8, lpCriticalSection);
    v27 = lpCriticalSection[0];
    if ( lpCriticalSection[0] )
    {
      EnterCriticalSection(lpCriticalSection[0]);
      *(_QWORD *)v47 = v27;
      if ( (unsigned int)dword_18009A048 > 5 )
      {
        v48 = (const char *)ToString((unsigned int)v60);
        v49[0] = (const unsigned __int16 *)NcsiProbePerformReasonToString(a2);
        v46 = *v59;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v46,
          (int)byte_18008C5F3,
          v30,
          v31,
          (__int64)&v46,
          v49,
          (const unsigned __int16 **)&v48);
      }
      for ( i = &v27[1].DebugInfo->Type; i != *(_QWORD **)&v27[1].LockCount; ++i )
      {
        if ( *(_QWORD *)(*i + 3224LL) == *v59 && *(_DWORD *)(*i + 3232LL) == v60 )
          break;
      }
      TickCount64 = (const unsigned __int16 *)GetTickCount64();
      v48 = (const char *)TickCount64;
      v34 = (LODWORD(v27[1].LockSemaphore) >= 3 || HIDWORD(v27[1].LockSemaphore) >= 3 || a2 == 11)
         && !(_DWORD)dword_18009B418
         && !NcsiConfigData::IsDefaultURLChanged(0);
      v45[0] = v34;
      if ( i == *(_QWORD **)&v27[1].LockCount )
      {
        v61 = 0;
        std::make_unique<ActiveProbeManager::PerFamilyInterfaceProbeInfo,_NET_LUID_LH &,enum NcsiProbePerformReason &,enum _NLA_CONNECTIVITY_FAMILY &,unsigned __int64 const &,bool const &,0>(
          &v61,
          v59,
          &v67,
          (unsigned int *)&v60,
          &v48,
          v45);
        v35 = *(const char ***)&v27[1].LockCount;
        if ( v35 == v27[1].OwningThread )
        {
          std::vector<std::unique_ptr<ActiveProbeManager::PerFamilyInterfaceProbeInfo>>::_Emplace_reallocate<std::unique_ptr<ActiveProbeManager::PerFamilyInterfaceProbeInfo>>(
            (__int64 *)&v27[1],
            (__int64)v35,
            (__int64 *)&v61);
        }
        else
        {
          v36 = v61;
          v61 = 0;
          *v35 = v36;
          *(_QWORD *)&v27[1].LockCount += 8LL;
        }
        LOBYTE(v43) = v18;
        LOBYTE(v42) = IsSystemInStandby;
        LOBYTE(v40) = v34;
        v37 = ActiveProbeManager::PerFamilyInterfaceProbeInfo::ProcessProbeQueueRequest(
                *(_QWORD *)(*(_QWORD *)&v27[1].LockCount - 8LL),
                0,
                TickCount64,
                a2,
                v40,
                v42,
                v43);
        std::unique_ptr<ActiveProbeManager::PerFamilyInterfaceProbeInfo>::~unique_ptr<ActiveProbeManager::PerFamilyInterfaceProbeInfo>(&v61);
        if ( v27 )
          LeaveCriticalSection(v27);
        if ( lpCriticalSection[1] )
          std::_Ref_count_base::_Decref((std::_Ref_count_base *)lpCriticalSection[1]);
        NsiFreeTable(v63, *((_QWORD *)&v63 + 1), v64, *((_QWORD *)&v64 + 1));
        return v37;
      }
      else
      {
        LOBYTE(v43) = v18;
        LOBYTE(v41) = IsSystemInStandby;
        LOBYTE(v39) = v34;
        v38 = ActiveProbeManager::PerFamilyInterfaceProbeInfo::ProcessProbeQueueRequest(
                *i,
                1,
                TickCount64,
                a2,
                v39,
                v41,
                v43);
        if ( v27 )
          LeaveCriticalSection(v27);
        if ( lpCriticalSection[1] )
          std::_Ref_count_base::_Decref((std::_Ref_count_base *)lpCriticalSection[1]);
        NsiFreeTable(v63, *((_QWORD *)&v63 + 1), v64, *((_QWORD *)&v64 + 1));
        return v38;
      }
    }
    else
    {
      if ( (unsigned int)dword_18009A080 > 5 )
      {
        v48 = (const char *)ToString((unsigned int)v60);
        v49[0] = (const unsigned __int16 *)NcsiProbePerformReasonToString(a2);
        v46 = *v59;
        *(_QWORD *)v47 = "ActiveProbeManager doesn't exist";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v46,
          (int)byte_18008C199,
          v28,
          v29,
          (const unsigned __int16 **)v47,
          (__int64)&v46,
          v49,
          (const unsigned __int16 **)&v48);
      }
      wil::details::in1diag3::Log_Hr(retaddr, (void *)0x593, v26, (const char *)0x80070015LL, v39);
      if ( lpCriticalSection[1] )
        std::_Ref_count_base::_Decref((std::_Ref_count_base *)lpCriticalSection[1]);
      NsiFreeTable(v63, *((_QWORD *)&v63 + 1), v64, *((_QWORD *)&v64 + 1));
      return 1;
    }
  }
  else
  {
    if ( (unsigned int)dword_18009A080 > 5 )
    {
      v46 = ToString((unsigned int)v60);
      *(_QWORD *)v47 = NcsiProbePerformReasonToString(a2);
      lpCriticalSection[0] = (LPCRITICAL_SECTION)*v59;
      v61 = "Disallow non operStatus up probes in DS";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        (__int64)lpCriticalSection[0],
        (int)&byte_18008BF47,
        v19,
        v20,
        (const unsigned __int16 **)&v61,
        (__int64)lpCriticalSection,
        (const unsigned __int16 **)v47,
        (const unsigned __int16 **)&v46);
    }
    BYTE1(v59[493 * v60 + 962]) = 1;
    NsiFreeTable(v63, *((_QWORD *)&v63 + 1), v64, *((_QWORD *)&v64 + 1));
    return 2;
  }
}

```

## disassembly

```asm
0x18001c698  mov     [rsp+arg_8], edx
0x18001c69c  push    rbx
0x18001c69d  push    rsi
0x18001c69e  push    rdi
0x18001c69f  push    r12
0x18001c6a1  push    r13
0x18001c6a3  push    r14
0x18001c6a5  push    r15
0x18001c6a7  mov     eax, 17E0h
0x18001c6ac  call    _alloca_probe
0x18001c6b1  sub     rsp, rax
0x18001c6b4  mov     rax, cs:__security_cookie
0x18001c6bb  xor     rax, rsp
0x18001c6be  mov     [rsp+1818h+var_40], rax
0x18001c6c6  mov     edi, edx
0x18001c6c8  mov     [rsp+1818h+var_90], rcx
0x18001c6d0  mov     [rsp+1818h+var_88], r8d
0x18001c6d8  mov     eax, cs:?g_ncsiConfigData@@3VNcsiConfigData@@A; NcsiConfigData g_ncsiConfigData
0x18001c6de  nop
0x18001c6df  test    eax, eax
0x18001c6e1  jnz     loc_18001C775
0x18001c6e7  mov     eax, cs:dword_18009A080
0x18001c6ed  cmp     eax, 5
0x18001c6f0  jbe     short loc_18001C76B
0x18001c6f2  mov     ecx, [rsp+1818h+var_88]
0x18001c6f9  call    ?ToString@@YAPEBDW4_NLA_CONNECTIVITY_FAMILY@@@Z; ToString(_NLA_CONNECTIVITY_FAMILY)
0x18001c6fe  mov     [rsp+1818h+var_80], rax
0x18001c706  mov     ecx, edx
0x18001c708  call    ?NcsiProbePerformReasonToString@@YAPEBDW4NcsiProbePerformReason@@@Z; NcsiProbePerformReasonToString(NcsiProbePerformReason)
0x18001c70d  mov     [rsp+1818h+lpCriticalSection], rax
0x18001c715  mov     rax, [rsp+1818h+var_90]
0x18001c71d  mov     rcx, [rax]
0x18001c720  mov     qword ptr [rsp+1818h+var_17B8], rcx
0x18001c725  lea     rax, aDisabledByRegi; "Disabled by registry"
0x18001c72c  mov     [rsp+1818h+var_17C0], rax
0x18001c731  lea     rax, [rsp+1818h+var_80]
0x18001c739  mov     [rsp+1818h+var_17E0], rax
0x18001c73e  lea     rax, [rsp+1818h+lpCriticalSection]
0x18001c746  mov     [rsp+1818h+var_17E8], rax
0x18001c74b  lea     rax, [rsp+1818h+var_17B8]
0x18001c750  mov     [rsp+1818h+var_17F0], rax
0x18001c755  lea     rax, [rsp+1818h+var_17C0]
0x18001c75a  mov     qword ptr [rsp+1818h+var_17F8], rax
0x18001c75f  lea     rdx, word_18008C13E
0x18001c766  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18001c76b  mov     eax, 2
0x18001c770  jmp     loc_18001D0A1
0x18001c775  call    ?ActiveProbesGPDisabled@NcsiConfigData@@QEAA_NXZ; NcsiConfigData::ActiveProbesGPDisabled(void)
0x18001c77a  test    al, al
0x18001c77c  jz      loc_18001C810
0x18001c782  mov     eax, cs:dword_18009A080
0x18001c788  cmp     eax, 5
0x18001c78b  jbe     short loc_18001C806
0x18001c78d  mov     ecx, [rsp+1818h+var_88]
0x18001c794  call    ?ToString@@YAPEBDW4_NLA_CONNECTIVITY_FAMILY@@@Z; ToString(_NLA_CONNECTIVITY_FAMILY)
0x18001c799  mov     [rsp+1818h+var_17C0], rax
0x18001c79e  mov     ecx, edi
0x18001c7a0  call    ?NcsiProbePerformReasonToString@@YAPEBDW4NcsiProbePerformReason@@@Z; NcsiProbePerformReasonToString(NcsiProbePerformReason)
0x18001c7a5  mov     qword ptr [rsp+1818h+var_17B8], rax
0x18001c7aa  mov     rax, [rsp+1818h+var_90]
0x18001c7b2  mov     rcx, [rax]
0x18001c7b5  mov     [rsp+1818h+lpCriticalSection], rcx
0x18001c7bd  lea     rax, aDisabledByGrou; "Disabled by Group Policy"
0x18001c7c4  mov     [rsp+1818h+var_80], rax
0x18001c7cc  lea     rax, [rsp+1818h+var_17C0]
0x18001c7d1  mov     [rsp+1818h+var_17E0], rax
0x18001c7d6  lea     rax, [rsp+1818h+var_17B8]
0x18001c7db  mov     [rsp+1818h+var_17E8], rax
0x18001c7e0  lea     rax, [rsp+1818h+lpCriticalSection]
0x18001c7e8  mov     [rsp+1818h+var_17F0], rax
0x18001c7ed  lea     rax, [rsp+1818h+var_80]
0x18001c7f5  mov     qword ptr [rsp+1818h+var_17F8], rax
0x18001c7fa  lea     rdx, word_18008BFA2
0x18001c801  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18001c806  mov     eax, 2
0x18001c80b  jmp     loc_18001D0A1
0x18001c810  call    ?IsDisableNCSIConnectivityEvaluationSet@NcsiConfigData@@QEAA_NXZ; NcsiConfigData::IsDisableNCSIConnectivityEvaluationSet(void)
0x18001c815  test    al, al
0x18001c817  jz      loc_18001C8AB
0x18001c81d  mov     eax, cs:dword_18009A080
0x18001c823  cmp     eax, 5
0x18001c826  jbe     short loc_18001C8A1
0x18001c828  mov     ecx, [rsp+1818h+var_88]
0x18001c82f  call    ?ToString@@YAPEBDW4_NLA_CONNECTIVITY_FAMILY@@@Z; ToString(_NLA_CONNECTIVITY_FAMILY)
0x18001c834  mov     [rsp+1818h+var_17C0], rax
0x18001c839  mov     ecx, edi
0x18001c83b  call    ?NcsiProbePerformReasonToString@@YAPEBDW4NcsiProbePerformReason@@@Z; NcsiProbePerformReasonToString(NcsiProbePerformReason)
0x18001c840  mov     qword ptr [rsp+1818h+var_17B8], rax
0x18001c845  mov     rax, [rsp+1818h+var_90]
0x18001c84d  mov     rcx, [rax]
0x18001c850  mov     [rsp+1818h+lpCriticalSection], rcx
0x18001c858  lea     rax, aDisablencsicon_0; "DisableNCSIConnectivityEvaluation is se"...
0x18001c85f  mov     [rsp+1818h+var_80], rax
0x18001c867  lea     rax, [rsp+1818h+var_17C0]
0x18001c86c  mov     [rsp+1818h+var_17E0], rax
0x18001c871  lea     rax, [rsp+1818h+var_17B8]
0x18001c876  mov     [rsp+1818h+var_17E8], rax
0x18001c87b  lea     rax, [rsp+1818h+lpCriticalSection]
0x18001c883  mov     [rsp+1818h+var_17F0], rax
0x18001c888  lea     rax, [rsp+1818h+var_80]
0x18001c890  mov     qword ptr [rsp+1818h+var_17F8], rax
0x18001c895  lea     rdx, byte_18008C783
0x18001c89c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18001c8a1  mov     eax, 2
0x18001c8a6  jmp     loc_18001D0A1
0x18001c8ab  xorps   xmm0, xmm0
0x18001c8ae  xor     eax, eax
0x18001c8b0  mov     [rsp+1818h+var_48], rax
0x18001c8b8  movdqu  [rsp+1818h+var_68], xmm0
0x18001c8c1  xorps   xmm1, xmm1
0x18001c8c4  movdqu  [rsp+1818h+var_58], xmm1
0x18001c8cd  mov     dword ptr [rsp+1818h+var_48], eax
0x18001c8d4  lea     rcx, [rsp+1818h+var_68]
0x18001c8dc  call    ?Refresh@?$GetNsiInformation@$0A@$0A@@NsiNotifications@@QEAAXXZ; NsiNotifications::GetNsiInformation<0,0>::Refresh(void)
0x18001c8e1  nop
0x18001c8e2  xor     edx, edx; Val
0x18001c8e4  mov     r8d, 780h; Size
0x18001c8ea  lea     rcx, [rsp+1818h+var_1778]; void *
0x18001c8f2  call    memset_0
0x18001c8f7  xorps   xmm0, xmm0
0x18001c8fa  movdqa  [rsp+1818h+var_1798], xmm0
0x18001c903  xorps   xmm1, xmm1
0x18001c906  movdqa  [rsp+1818h+var_1788], xmm1
0x18001c90f  xor     edx, edx; Val
0x18001c911  mov     r8d, 778h; Size
0x18001c917  lea     rcx, [rsp+1818h+var_1770]; void *
0x18001c91f  call    memset_0
0x18001c924  xor     eax, eax
0x18001c926  mov     [rsp+1818h+var_1778], rax
0x18001c92e  xor     edx, edx; Val
0x18001c930  mov     r8d, 444h; Size
0x18001c936  lea     rcx, [rsp+1818h+var_1770]; void *
0x18001c93e  call    memset_0
0x18001c943  xor     edx, edx; Val
0x18001c945  mov     r8d, 0D8h; Size
0x18001c94b  lea     rcx, [rsp+1818h+var_1328]; void *
0x18001c953  call    memset_0
0x18001c958  xor     edx, edx; Val
0x18001c95a  mov     r8d, 258h; Size
0x18001c960  lea     rcx, [rsp+1818h+var_1250]; void *
0x18001c968  call    memset_0
0x18001c96d  mov     [rsp+1818h+var_FF8], 0
0x18001c978  mov     [rsp+1818h+var_FF4], 0FFFFFFFFh
0x18001c983  mov     eax, dword ptr [rsp+1818h+var_48]
0x18001c98a  mov     dword ptr [rsp+1818h+var_17F0], eax
0x18001c98e  mov     rax, qword ptr [rsp+1818h+var_58+8]
0x18001c996  mov     qword ptr [rsp+1818h+var_17F8], rax
0x18001c99b  mov     r9, qword ptr [rsp+1818h+var_58]
0x18001c9a3  mov     r8, qword ptr [rsp+1818h+var_68+8]
0x18001c9ab  mov     rdx, qword ptr [rsp+1818h+var_68]
0x18001c9b3  lea     rcx, [rsp+1818h+Src]
0x18001c9bb  call    ??0iterator@?$GetNsiInformation@$0A@$0A@@NsiNotifications@@QEAA@PEAT_NET_LUID_LH@@PEAU_NDIS_NSI_INTERFACE_INFORMATION_RW@@PEAU_NDIS_INTERFACE_INFORMATION@@PEAU_NDIS_NSI_INTERFACE_INFORMATION_ROS@@K@Z; NsiNotifications::GetNsiInformation<0,0>::iterator::iterator(_NET_LUID_LH *,_NDIS_NSI_INTERFACE_INFORMATION_RW *,_NDIS_INTERFACE_INFORMATION *,_NDIS_NSI_INTERFACE_INFORMATION_ROS *,ulong)
0x18001c9c0  lea     rcx, [rsp+1818h+var_838]; void *
0x18001c9c8  lea     rdx, [rsp+1818h+Src]; Src
0x18001c9d0  mov     ebx, 7A8h
0x18001c9d5  mov     r8d, ebx; Size
0x18001c9d8  call    memcpy_0
0x18001c9dd  lea     rcx, [rsp+1818h+Src]; void *
0x18001c9e5  lea     rdx, [rsp+1818h+var_1798]; Src
0x18001c9ed  mov     r8d, ebx; Size
0x18001c9f0  call    memcpy_0
0x18001c9f5  lea     rcx, [rsp+1818h+var_1798]; void *
0x18001c9fd  lea     rdx, [rsp+1818h+var_838]; Src
0x18001ca05  mov     r8d, ebx; Size
0x18001ca08  call    memcpy_0
0x18001ca0d  lea     r8, [rsp+1818h+var_90]
0x18001ca15  lea     rdx, [rsp+1818h+Src]; void *
0x18001ca1d  lea     rcx, [rsp+1818h+var_1798]; Src
0x18001ca25  call    std__any_of_NsiNotifications__GetNsiInformation_0_0___iterator__ActiveProbeManager__TryNcsiQueueActiveInternetProbe____3____lambda_1___
0x18001ca2a  test    al, al
0x18001ca2c  jz      loc_18001CAE7
0x18001ca32  mov     eax, cs:dword_18009A080
0x18001ca38  cmp     eax, 5
0x18001ca3b  jbe     short loc_18001CAB7
0x18001ca3d  mov     ecx, [rsp+1818h+var_88]
0x18001ca44  call    ?ToString@@YAPEBDW4_NLA_CONNECTIVITY_FAMILY@@@Z; ToString(_NLA_CONNECTIVITY_FAMILY)
0x18001ca49  mov     [rsp+1818h+var_17C0], rax
0x18001ca4e  mov     ecx, edi
0x18001ca50  call    ?NcsiProbePerformReasonToString@@YAPEBDW4NcsiProbePerformReason@@@Z; NcsiProbePerformReasonToString(NcsiProbePerformReason)
0x18001ca55  mov     qword ptr [rsp+1818h+var_17B8], rax
0x18001ca5a  mov     rax, [rsp+1818h+var_90]
0x18001ca62  mov     rcx, [rax]
0x18001ca65  mov     [rsp+1818h+lpCriticalSection], rcx
0x18001ca6d  lea     rax, aDisabledBecaus; "Disabled because Hidden interface"
0x18001ca74  mov     [rsp+1818h+var_80], rax
0x18001ca7c  lea     rax, [rsp+1818h+var_17C0]
0x18001ca81  mov     [rsp+1818h+var_17E0], rax
0x18001ca86  lea     rax, [rsp+1818h+var_17B8]
0x18001ca8b  mov     [rsp+1818h+var_17E8], rax
0x18001ca90  lea     rax, [rsp+1818h+lpCriticalSection]
0x18001ca98  mov     [rsp+1818h+var_17F0], rax
0x18001ca9d  lea     rax, [rsp+1818h+var_80]
0x18001caa5  mov     qword ptr [rsp+1818h+var_17F8], rax
0x18001caaa  lea     rdx, byte_18008BE63
0x18001cab1  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18001cab6  nop
0x18001cab7  mov     r9, qword ptr [rsp+1818h+var_58+8]
0x18001cabf  mov     r8, qword ptr [rsp+1818h+var_58]
0x18001cac7  mov     rdx, qword ptr [rsp+1818h+var_68+8]
0x18001cacf  mov     rcx, qword ptr [rsp+1818h+var_68]
0x18001cad7  call    cs:__imp_NsiFreeTable
0x18001cadd  mov     eax, 2
0x18001cae2  jmp     loc_18001D0A1
0x18001cae7  call    ?IsSystemInStandby@Power@Ncsi@@YA_NXZ; Ncsi::Power::IsSystemInStandby(void)
0x18001caec  mov     bl, al
0x18001caee  mov     [rsp+1818h+var_17C8], al
0x18001caf2  call    ?ShouldDisconnectInStandby@Power@Ncsi@@YA_NXZ; Ncsi::Power::ShouldDisconnectInStandby(void)
0x18001caf7  test    bl, bl
0x18001caf9  jz      short loc_18001CB04
0x18001cafb  test    al, al
0x18001cafd  jz      short loc_18001CB04
0x18001caff  mov     r12b, 1
0x18001cb02  jmp     short loc_18001CB07
0x18001cb04  xor     r12b, r12b
0x18001cb07  cmp     edi, 0Eh
0x18001cb0a  jz      loc_18001CBEC
0x18001cb10  test    r12b, r12b
0x18001cb13  jz      loc_18001CBEC
0x18001cb19  mov     eax, cs:dword_18009A080
0x18001cb1f  cmp     eax, 5
0x18001cb22  jbe     short loc_18001CB9D
0x18001cb24  mov     ecx, [rsp+1818h+var_88]
0x18001cb2b  call    ?ToString@@YAPEBDW4_NLA_CONNECTIVITY_FAMILY@@@Z; ToString(_NLA_CONNECTIVITY_FAMILY)
0x18001cb30  mov     [rsp+1818h+var_17C0], rax
0x18001cb35  mov     ecx, edi
0x18001cb37  call    ?NcsiProbePerformReasonToString@@YAPEBDW4NcsiProbePerformReason@@@Z; NcsiProbePerformReasonToString(NcsiProbePerformReason)
0x18001cb3c  mov     qword ptr [rsp+1818h+var_17B8], rax
0x18001cb41  mov     rax, [rsp+1818h+var_90]
0x18001cb49  mov     rcx, [rax]
0x18001cb4c  mov     [rsp+1818h+lpCriticalSection], rcx
0x18001cb54  lea     rax, aDisallowNonOpe; "Disallow non operStatus up probes in DS"
0x18001cb5b  mov     [rsp+1818h+var_80], rax
0x18001cb63  lea     rax, [rsp+1818h+var_17C0]
0x18001cb68  mov     [rsp+1818h+var_17E0], rax
0x18001cb6d  lea     rax, [rsp+1818h+var_17B8]
0x18001cb72  mov     [rsp+1818h+var_17E8], rax
0x18001cb77  lea     rax, [rsp+1818h+lpCriticalSection]
0x18001cb7f  mov     [rsp+1818h+var_17F0], rax
0x18001cb84  lea     rax, [rsp+1818h+var_80]
0x18001cb8c  mov     qword ptr [rsp+1818h+var_17F8], rax
0x18001cb91  lea     rdx, byte_18008BF47
0x18001cb98  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18001cb9d  movsxd  rax, [rsp+1818h+var_88]
0x18001cba5  imul    rcx, rax, 0F68h
0x18001cbac  mov     rax, [rsp+1818h+var_90]
0x18001cbb4  mov     byte ptr [rcx+rax+1E11h], 1
0x18001cbbc  mov     r9, qword ptr [rsp+1818h+var_58+8]
0x18001cbc4  mov     r8, qword ptr [rsp+1818h+var_58]
0x18001cbcc  mov     rdx, qword ptr [rsp+1818h+var_68+8]
0x18001cbd4  mov     rcx, qword ptr [rsp+1818h+var_68]
0x18001cbdc  call    cs:__imp_NsiFreeTable
0x18001cbe2  mov     eax, 2
0x18001cbe7  jmp     loc_18001D0A1
0x18001cbec  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_NCSI_Fix_PreventingProbeLoopInNonDS@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_NCSI_Fix_PreventingProbeLoopInNonDS@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NCSI_Fix_PreventingProbeLoopInNonDS> `wil::Feature<__WilFeatureTraits_Feature_NCSI_Fix_PreventingProbeLoopInNonDS>::GetImpl(void)'::`2'::impl
0x18001cbf3  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_NCSI_Fix_PreventingProbeLoopInNonDS@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NCSI_Fix_PreventingProbeLoopInNonDS>::__private_IsEnabled(void)
0x18001cbf8  test    al, al
0x18001cbfa  jz      loc_18001CD35
0x18001cc00  cmp     edi, 6
0x18001cc03  jnz     loc_18001CD35
0x18001cc09  movsxd  rax, [rsp+1818h+var_88]
0x18001cc11  imul    rcx, rax, 0F68h
0x18001cc18  mov     rax, [rsp+1818h+var_90]
0x18001cc20  cmp     dword ptr [rcx+rax+1E14h], 3
0x18001cc28  jb      loc_18001CD35
0x18001cc2e  mov     eax, cs:dword_18009A048
0x18001cc34  cmp     eax, 5
0x18001cc37  jbe     loc_18001CD05
0x18001cc3d  mov     rdx, 400000000000h
0x18001cc47  lea     rcx, dword_18009A048
0x18001cc4e  call    _tlgKeywordOn
0x18001cc53  test    al, al
0x18001cc55  jz      loc_18001CD05
0x18001cc5b  mov     [rsp+1818h+var_17C0], 800h
0x18001cc64  movsxd  rcx, [rsp+1818h+var_88]
0x18001cc6c  imul    rax, rcx, 0F68h
0x18001cc73  mov     rdx, [rsp+1818h+var_90]
0x18001cc7b  mov     eax, [rax+rdx+1E14h]
0x18001cc82  mov     dword ptr [rsp+1818h+var_80], eax
0x18001cc89  call    ?ToString@@YAPEBDW4_NLA_CONNECTIVITY_FAMILY@@@Z; ToString(_NLA_CONNECTIVITY_FAMILY)
0x18001cc8e  mov     qword ptr [rsp+1818h+var_17B8], rax
0x18001cc93  mov     ecx, edi
0x18001cc95  call    ?NcsiProbePerformReasonToString@@YAPEBDW4NcsiProbePerformReason@@@Z; NcsiProbePerformReasonToString(NcsiProbePerformReason)
0x18001cc9a  mov     [rsp+1818h+lpCriticalSection], rax
0x18001cca2  mov     rax, [rdx]
0x18001cca5  mov     [rsp+1818h+var_17A8], rax
0x18001ccaa  lea     rax, aSuppressedProx; "Suppressed proxy-changed probe after pe"...
0x18001ccb1  mov     [rsp+1818h+var_17B0], rax
0x18001ccb6  lea     rax, [rsp+1818h+var_17C0]
0x18001ccbb  mov     [rsp+1818h+var_17D0], rax
0x18001ccc0  lea     rax, [rsp+1818h+var_80]
0x18001ccc8  mov     [rsp+1818h+var_17D8], rax
0x18001cccd  lea     rax, [rsp+1818h+var_17B8]
0x18001ccd2  mov     [rsp+1818h+var_17E0], rax
0x18001ccd7  lea     rax, [rsp+1818h+lpCriticalSection]
0x18001ccdf  mov     [rsp+1818h+var_17E8], rax
0x18001cce4  lea     rax, [rsp+1818h+var_17A8]
0x18001cce9  mov     [rsp+1818h+var_17F0], rax
0x18001ccee  lea     rax, [rsp+1818h+var_17B0]
0x18001ccf3  mov     qword ptr [rsp+1818h+var_17F8], rax
0x18001ccf8  lea     rdx, byte_18008C529
  ... truncated ...
```
