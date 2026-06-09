# ActiveProbeManager::PerFamilyInterfaceProbeInfo::ShouldUpdateInterface(NcsiActiveProbeDataIn const &,NcsiActiveProbeDataOut const &,ulong)

- ea: `0x18003ae54`
- end: `0x18003b46f`
- name: `?ShouldUpdateInterface@PerFamilyInterfaceProbeInfo@ActiveProbeManager@@QEAA?AV?$optional@UNcsiActiveProbeDataOut@@@std@@AEBUNcsiActiveProbeDataIn@@AEBUNcsiActiveProbeDataOut@@K@Z`
- size: `1563`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18003ac90`

## callees

- `0x180002a84`
- `0x18000725c`
- `0x18000be24`
- `0x18000e350`
- `0x18001dba8`
- `0x180020c04`
- `0x180021144`
- `0x18002a790`
- `0x18002b82c`
- `0x18002d618`
- `0x18003a2e8`
- `0x18003ae54`
- `0x180041168`
- `0x180047240`
- `0x18006a048`
- `0x18006a280`
- `0x18006a4b4`
- `0x18006a87c`
- `0x18006aa54`
- `0x180077ad0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003aecf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003af75`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003b414`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003b43b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003aecf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003af75`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003b414`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003b43b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003aeac`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003aed8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003aeac`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003aed8`

## pseudocode

```c
__int64 __fastcall ActiveProbeManager::PerFamilyInterfaceProbeInfo::ShouldUpdateInterface(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5)
{
  bool v9; // r12
  bool IsDefaultURLChanged; // r13
  struct NCSI_INTERFACE_ATTRIBUTES *InterfaceAttributes; // rax
  char IsBehindHotspot; // r15
  __int64 v13; // r8
  const char *v14; // r9
  const char *v15; // rax
  __int64 result; // rax
  __int64 v17; // r8
  __int64 v18; // r9
  char v19; // r15
  const char *v20; // rax
  int v21; // eax
  __int64 ShouldUpdateInterfaceTwoRequestsInDisconnectedStandby; // rax
  __int64 ShouldUpdateInterfaceTwoRequests; // rax
  __int64 ShouldUpdateInterfaceThreeRequests; // rax
  bool v25; // zf
  char v26; // al
  const char *v27; // [rsp+40h] [rbp-16B8h] BYREF
  const char *v28; // [rsp+48h] [rbp-16B0h] BYREF
  union _NET_LUID_LH v29; // [rsp+50h] [rbp-16A8h] BYREF
  const char *v30; // [rsp+58h] [rbp-16A0h] BYREF
  __int64 v31; // [rsp+60h] [rbp-1698h]
  _BYTE v32[2840]; // [rsp+70h] [rbp-1688h] BYREF
  char v33; // [rsp+B88h] [rbp-B70h]
  _BYTE v34[2840]; // [rsp+B90h] [rbp-B68h] BYREF
  char v35; // [rsp+16A8h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+16F8h] [rbp+0h]

  v31 = a2;
  v9 = (_DWORD)dword_18009B418 != 0;
  IsDefaultURLChanged = NcsiConfigData::IsDefaultURLChanged((NcsiConfigData *)a1);
  EnterCriticalSection(&g_ncsiLock);
  InterfaceAttributes = FindInterfaceAttributes(*(union _NET_LUID_LH *)a3);
  IsBehindHotspot = NCSI_INTERFACE_ATTRIBUTES::IsBehindHotspot(InterfaceAttributes, *(unsigned int *)(a3 + 88));
  LeaveCriticalSection(&g_ncsiLock);
  EnterCriticalSection((LPCRITICAL_SECTION)a1);
  if ( *(_QWORD *)(a1 + 3120) > *(_QWORD *)(a3 + 160) && !IsBehindHotspot )
  {
    if ( (unsigned int)dword_18009A048 > 5 )
    {
      v28 = "A new probe has started on the same interface with same address family";
      v29.Value = *(ULONG64 *)a3;
      v15 = "IPv4";
      if ( *(_DWORD *)(a3 + 88) )
        v15 = "IPv6";
      v30 = v15;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(
        (int)&dword_18009A048,
        (int)byte_18008BFFD,
        v13,
        (__int64)v14,
        (const unsigned __int16 **)&v30,
        (__int64)&v29,
        (const unsigned __int16 **)&v28);
    }
    *(_BYTE *)(a2 + 2840) = 0;
    if ( a1 )
      LeaveCriticalSection((LPCRITICAL_SECTION)a1);
    result = a2;
    goto LABEL_72;
  }
  ++*(_DWORD *)(a1 + 3112);
  CacheNcsiHttpRequestTelemetryDetail(
    (const struct NcsiActiveProbeDataIn *)a3,
    (const struct NcsiActiveProbeDataOut *)a4,
    a5,
    v9,
    IsDefaultURLChanged,
    *(_BYTE *)(a3 + 177),
    *(_BYTE *)(a3 + 178));
  if ( ((*(_DWORD *)(a3 + 168) - 1) & 0xFFFFFFFB) != 0 || *(_QWORD *)a3 == *(_QWORD *)(a4 + 2816) )
  {
    v19 = 0;
  }
  else
  {
    v19 = 1;
    if ( (unsigned int)dword_18009A048 > 5 )
    {
      v30 = "Default interface is not the current interface";
      v29.Value = *(ULONG64 *)(a4 + 2816);
      v28 = *(const char **)a3;
      v20 = "IPv4";
      if ( *(_DWORD *)(a3 + 88) )
        v20 = "IPv6";
      v27 = v20;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(
        (__int64)"IPv6",
        (int)&word_18008C466,
        v17,
        v18,
        (const unsigned __int16 **)&v27,
        (__int64)&v28,
        (__int64)&v29,
        (const unsigned __int16 **)&v30);
    }
  }
  v35 = 0;
  v21 = *(_DWORD *)(a3 + 172);
  if ( *(_BYTE *)(a3 + 178) )
  {
    if ( (v21 & 0xFFFFFFFC) == 0 && v21 != 2 )
    {
      ActiveProbeManager::PerFamilyInterfaceProbeInfo::NewInternalShouldUpdateInterfaceOneRequestInDisconnectedStandbyImpl((ActiveProbeManager::PerFamilyInterfaceProbeInfo *)a1);
      if ( v33 )
      {
        if ( v35 )
        {
          NcsiActiveProbeDataOut::operator=(v34, v32);
        }
        else
        {
          NcsiActiveProbeDataOut::NcsiActiveProbeDataOut(v34, v32);
          v35 = 1;
        }
      }
      else if ( v35 )
      {
        NcsiActiveProbeDataOut::~NcsiActiveProbeDataOut((NcsiActiveProbeDataOut *)v34);
        v35 = 0;
      }
      std::_Non_trivial_move<std::_Optional_construct_base<NcsiActiveProbeDataOut>,NcsiActiveProbeDataOut>::~_Non_trivial_move<std::_Optional_construct_base<NcsiActiveProbeDataOut>,NcsiActiveProbeDataOut>(v32);
    }
    if ( *(_DWORD *)(a3 + 172) != 2 )
      goto LABEL_62;
    ShouldUpdateInterfaceTwoRequestsInDisconnectedStandby = ActiveProbeManager::PerFamilyInterfaceProbeInfo::InternalShouldUpdateInterfaceTwoRequestsInDisconnectedStandby((ActiveProbeManager::PerFamilyInterfaceProbeInfo *)a1);
  }
  else
  {
    if ( !v21 )
    {
      ActiveProbeManager::PerFamilyInterfaceProbeInfo::NewInternalShouldUpdateInterfaceOneRequestImpl(
        (ActiveProbeManager::PerFamilyInterfaceProbeInfo *)a1,
        v19);
      if ( v33 )
      {
        if ( v35 )
        {
          NcsiActiveProbeDataOut::operator=(v34, v32);
        }
        else
        {
          NcsiActiveProbeDataOut::NcsiActiveProbeDataOut(v34, v32);
          v35 = 1;
        }
      }
      else if ( v35 )
      {
        NcsiActiveProbeDataOut::~NcsiActiveProbeDataOut((NcsiActiveProbeDataOut *)v34);
        v35 = 0;
      }
      std::_Non_trivial_move<std::_Optional_construct_base<NcsiActiveProbeDataOut>,NcsiActiveProbeDataOut>::~_Non_trivial_move<std::_Optional_construct_base<NcsiActiveProbeDataOut>,NcsiActiveProbeDataOut>(v32);
    }
    if ( *(_DWORD *)(a3 + 172) == 1 )
    {
      ShouldUpdateInterfaceTwoRequests = ActiveProbeManager::PerFamilyInterfaceProbeInfo::InternalShouldUpdateInterfaceTwoRequests(
                                           (ActiveProbeManager::PerFamilyInterfaceProbeInfo *)a1,
                                           v19);
      if ( *(_BYTE *)(ShouldUpdateInterfaceTwoRequests + 2840) )
      {
        if ( v35 )
        {
          NcsiActiveProbeDataOut::operator=(v34, ShouldUpdateInterfaceTwoRequests);
        }
        else
        {
          NcsiActiveProbeDataOut::NcsiActiveProbeDataOut(v34, ShouldUpdateInterfaceTwoRequests);
          v35 = 1;
        }
      }
      else if ( v35 )
      {
        NcsiActiveProbeDataOut::~NcsiActiveProbeDataOut((NcsiActiveProbeDataOut *)v34);
        v35 = 0;
      }
      std::_Non_trivial_move<std::_Optional_construct_base<NcsiActiveProbeDataOut>,NcsiActiveProbeDataOut>::~_Non_trivial_move<std::_Optional_construct_base<NcsiActiveProbeDataOut>,NcsiActiveProbeDataOut>(v32);
    }
    if ( *(_DWORD *)(a3 + 172) == 2 )
    {
      ShouldUpdateInterfaceThreeRequests = ActiveProbeManager::PerFamilyInterfaceProbeInfo::InternalShouldUpdateInterfaceThreeRequests(
                                             (ActiveProbeManager::PerFamilyInterfaceProbeInfo *)a1,
                                             v19);
      if ( *(_BYTE *)(ShouldUpdateInterfaceThreeRequests + 2840) )
      {
        if ( v35 )
        {
          NcsiActiveProbeDataOut::operator=(v34, ShouldUpdateInterfaceThreeRequests);
        }
        else
        {
          NcsiActiveProbeDataOut::NcsiActiveProbeDataOut(v34, ShouldUpdateInterfaceThreeRequests);
          v35 = 1;
        }
      }
      else if ( v35 )
      {
        NcsiActiveProbeDataOut::~NcsiActiveProbeDataOut((NcsiActiveProbeDataOut *)v34);
        v35 = 0;
      }
      std::_Non_trivial_move<std::_Optional_construct_base<NcsiActiveProbeDataOut>,NcsiActiveProbeDataOut>::~_Non_trivial_move<std::_Optional_construct_base<NcsiActiveProbeDataOut>,NcsiActiveProbeDataOut>(v32);
    }
    if ( *(_DWORD *)(a3 + 172) != 3 )
      goto LABEL_62;
    ShouldUpdateInterfaceTwoRequestsInDisconnectedStandby = ActiveProbeManager::PerFamilyInterfaceProbeInfo::InternalShouldUpdateInterfaceUserProxyRequests(
                                                              (LPCRITICAL_SECTION)a1,
                                                              v19);
  }
  if ( *(_BYTE *)(ShouldUpdateInterfaceTwoRequestsInDisconnectedStandby + 2840) )
  {
    if ( v35 )
    {
      NcsiActiveProbeDataOut::operator=(v34, ShouldUpdateInterfaceTwoRequestsInDisconnectedStandby);
    }
    else
    {
      NcsiActiveProbeDataOut::NcsiActiveProbeDataOut(v34, ShouldUpdateInterfaceTwoRequestsInDisconnectedStandby);
      v35 = 1;
    }
  }
  else if ( v35 )
  {
    NcsiActiveProbeDataOut::~NcsiActiveProbeDataOut((NcsiActiveProbeDataOut *)v34);
    v35 = 0;
  }
  std::_Non_trivial_move<std::_Optional_construct_base<NcsiActiveProbeDataOut>,NcsiActiveProbeDataOut>::~_Non_trivial_move<std::_Optional_construct_base<NcsiActiveProbeDataOut>,NcsiActiveProbeDataOut>(v32);
LABEL_62:
  if ( v35 )
  {
    *(_DWORD *)(a1 + 3160) = *(_DWORD *)(a3 + 172);
    *(_BYTE *)(a1 + 3164) = 1;
    *(_WORD *)(a1 + 3165) = *(_WORD *)((char *)&v27 + 5);
    *(_BYTE *)(a1 + 3167) = HIBYTE(v27);
    *(_DWORD *)(a1 + 3168) = *(_DWORD *)(a3 + 168);
    *(_BYTE *)(a1 + 3172) = 1;
    *(_WORD *)(a1 + 3173) = *(_WORD *)((char *)&v27 + 5);
    *(_BYTE *)(a1 + 3175) = HIBYTE(v27);
    if ( *(_BYTE *)(a4 + 2652)
      || (v25 = !NcsiActiveProbeDataOut::RequestCompleteOverCaptivePortal((NcsiActiveProbeDataOut *)a4), v26 = 0, !v25) )
    {
      v26 = 1;
    }
    *(_BYTE *)(a1 + 3176) = v26;
    *(_BYTE *)(a1 + 3177) = 1;
    *(_BYTE *)(a1 + 3178) = *(_BYTE *)(a3 + 178);
    *(_BYTE *)(a1 + 3179) = 1;
    *(_OWORD *)(a1 + 3180) = *(_OWORD *)(a3 + 180);
    *(_OWORD *)(a1 + 3196) = *(_OWORD *)(a3 + 196);
    *(_WORD *)(a1 + 3212) = *(_WORD *)(a3 + 212);
    *(_BYTE *)(a2 + 2840) = 0;
    NcsiActiveProbeDataOut::NcsiActiveProbeDataOut(a2, v34);
    *(_BYTE *)(a2 + 2840) = 1;
    std::_Non_trivial_move<std::_Optional_construct_base<NcsiActiveProbeDataOut>,NcsiActiveProbeDataOut>::~_Non_trivial_move<std::_Optional_construct_base<NcsiActiveProbeDataOut>,NcsiActiveProbeDataOut>(v34);
    if ( a1 )
      LeaveCriticalSection((LPCRITICAL_SECTION)a1);
    result = a2;
  }
  else
  {
    *(_BYTE *)(a2 + 2840) = 0;
    std::_Non_trivial_move<std::_Optional_construct_base<NcsiActiveProbeDataOut>,NcsiActiveProbeDataOut>::~_Non_trivial_move<std::_Optional_construct_base<NcsiActiveProbeDataOut>,NcsiActiveProbeDataOut>(v34);
    if ( a1 )
      LeaveCriticalSection((LPCRITICAL_SECTION)a1);
    result = a2;
  }
LABEL_72:
  while ( 2 )
  {
    try
    {
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x4A1,
        (unsigned int)"onecore\\net\\diagnostics\\ncsi\\activeprobemanager\\lib\\activeprobemanager.cpp",
        v14);
      *(_BYTE *)(v31 + 2840) = 0;
      result = v31;
      continue;
    }
    break;
  }
  return result;
}

```

## disassembly

```asm
0x18003ae54  push    rbx
0x18003ae56  push    rsi
0x18003ae57  push    rdi
0x18003ae58  push    r12
0x18003ae5a  push    r13
0x18003ae5c  push    r14
0x18003ae5e  push    r15
0x18003ae60  mov     eax, 16C0h
0x18003ae65  call    _alloca_probe
0x18003ae6a  sub     rsp, rax
0x18003ae6d  mov     rax, cs:__security_cookie
0x18003ae74  xor     rax, rsp
0x18003ae77  mov     [rsp+16F8h+var_48], rax
0x18003ae7f  mov     r14, r9
0x18003ae82  mov     rdi, r8
0x18003ae85  mov     rsi, rdx
0x18003ae88  mov     rbx, rcx
0x18003ae8b  mov     [rsp+16F8h+var_1698], rdx
0x18003ae90  mov     eax, cs:dword_18009B418
0x18003ae96  nop
0x18003ae97  test    eax, eax
0x18003ae99  setnz   r12b
0x18003ae9d  call    ?IsDefaultURLChanged@NcsiConfigData@@QEAA_NXZ; NcsiConfigData::IsDefaultURLChanged(void)
0x18003aea2  mov     r13b, al
0x18003aea5  lea     rcx, ?g_ncsiLock@@3Vcritical_section@wil@@A; lpCriticalSection
0x18003aeac  call    cs:__imp_EnterCriticalSection
0x18003aeb2  mov     rcx, [rdi]; union _NET_LUID_LH
0x18003aeb5  call    ?FindInterfaceAttributes@@YAPEAVNCSI_INTERFACE_ATTRIBUTES@@T_NET_LUID_LH@@@Z; FindInterfaceAttributes(_NET_LUID_LH)
0x18003aeba  mov     edx, [rdi+58h]
0x18003aebd  mov     rcx, rax
0x18003aec0  call    ?IsBehindHotspot@NCSI_INTERFACE_ATTRIBUTES@@QEBA_NW4_NLA_CONNECTIVITY_FAMILY@@@Z; NCSI_INTERFACE_ATTRIBUTES::IsBehindHotspot(_NLA_CONNECTIVITY_FAMILY)
0x18003aec5  mov     r15b, al
0x18003aec8  lea     rcx, ?g_ncsiLock@@3Vcritical_section@wil@@A; lpCriticalSection
0x18003aecf  call    cs:__imp_LeaveCriticalSection
0x18003aed5  mov     rcx, rbx; lpCriticalSection
0x18003aed8  call    cs:__imp_EnterCriticalSection
0x18003aede  mov     rax, [rdi+0A0h]
0x18003aee5  cmp     [rbx+0C30h], rax
0x18003aeec  jbe     loc_18003AF83
0x18003aef2  test    r15b, r15b
0x18003aef5  jnz     loc_18003AF83
0x18003aefb  mov     eax, cs:dword_18009A048
0x18003af01  cmp     eax, 5
0x18003af04  jbe     short loc_18003AF66
0x18003af06  lea     rax, aANewProbeHasSt; "A new probe has started on the same int"...
0x18003af0d  mov     [rsp+16F8h+var_16B0], rax
0x18003af12  mov     rax, [rdi]
0x18003af15  mov     [rsp+16F8h+var_16A8], rax
0x18003af1a  lea     rcx, aIpv6; "IPv6"
0x18003af21  lea     rax, aIpv4; "IPv4"
0x18003af28  cmp     dword ptr [rdi+58h], 0
0x18003af2c  cmovnz  rax, rcx
0x18003af30  mov     [rsp+16F8h+var_16A0], rax
0x18003af35  lea     rax, [rsp+16F8h+var_16B0]
0x18003af3a  mov     qword ptr [rsp+16F8h+var_16C8], rax
0x18003af3f  lea     rax, [rsp+16F8h+var_16A8]
0x18003af44  mov     qword ptr [rsp+16F8h+var_16D0], rax
0x18003af49  lea     rax, [rsp+16F8h+var_16A0]
0x18003af4e  mov     qword ptr [rsp+16F8h+var_16D8], rax
0x18003af53  lea     rdx, byte_18008BFFD
0x18003af5a  lea     rcx, dword_18009A048
0x18003af61  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &)
0x18003af66  mov     byte ptr [rsi+0B18h], 0
0x18003af6d  test    rbx, rbx
0x18003af70  jz      short loc_18003AF7B
0x18003af72  mov     rcx, rbx; lpCriticalSection
0x18003af75  call    cs:__imp_LeaveCriticalSection
0x18003af7b  mov     rax, rsi
0x18003af7e  jmp     loc_18003B44B
0x18003af83  inc     dword ptr [rbx+0C28h]
0x18003af89  mov     al, [rdi+0B2h]
0x18003af8f  mov     [rsp+16F8h+var_16C8], al; bool
0x18003af93  mov     al, [rdi+0B1h]
0x18003af99  mov     [rsp+16F8h+var_16D0], al; bool
0x18003af9d  mov     [rsp+16F8h+var_16D8], r13b; bool
0x18003afa2  mov     r9b, r12b; bool
0x18003afa5  mov     r8d, [rsp+16F8h+arg_20]; unsigned int
0x18003afad  mov     rdx, r14; struct NcsiActiveProbeDataOut *
0x18003afb0  mov     rcx, rdi; struct NcsiActiveProbeDataIn *
0x18003afb3  call    ?CacheNcsiHttpRequestTelemetryDetail@@YAXAEBUNcsiActiveProbeDataIn@@AEBUNcsiActiveProbeDataOut@@K_N222@Z; CacheNcsiHttpRequestTelemetryDetail(NcsiActiveProbeDataIn const &,NcsiActiveProbeDataOut const &,ulong,bool,bool,bool,bool)
0x18003afb8  mov     eax, [rdi+0A8h]
0x18003afbe  dec     eax
0x18003afc0  test    eax, 0FFFFFFFBh
0x18003afc5  jnz     loc_18003B062
0x18003afcb  mov     rax, [r14+0B00h]
0x18003afd2  cmp     [rdi], rax
0x18003afd5  jz      loc_18003B062
0x18003afdb  mov     r15b, 1
0x18003afde  mov     eax, cs:dword_18009A048
0x18003afe4  cmp     eax, 5
0x18003afe7  jbe     short loc_18003B05D
0x18003afe9  lea     rax, aDefaultInterfa; "Default interface is not the current in"...
0x18003aff0  mov     [rsp+16F8h+var_16A0], rax
0x18003aff5  mov     rax, [r14+0B00h]
0x18003affc  mov     [rsp+16F8h+var_16A8], rax
0x18003b001  mov     rax, [rdi]
0x18003b004  mov     [rsp+16F8h+var_16B0], rax
0x18003b009  lea     rcx, aIpv6; "IPv6"
0x18003b010  lea     rax, aIpv4; "IPv4"
0x18003b017  xor     r12d, r12d
0x18003b01a  cmp     [rdi+58h], r12d
0x18003b01e  cmovnz  rax, rcx
0x18003b022  mov     [rsp+16F8h+var_16B8], rax
0x18003b027  lea     rax, [rsp+16F8h+var_16A0]
0x18003b02c  mov     [rsp+16F8h+var_16C0], rax
0x18003b031  lea     rax, [rsp+16F8h+var_16A8]
0x18003b036  mov     qword ptr [rsp+16F8h+var_16C8], rax
0x18003b03b  lea     rax, [rsp+16F8h+var_16B0]
0x18003b040  mov     qword ptr [rsp+16F8h+var_16D0], rax
0x18003b045  lea     rax, [rsp+16F8h+var_16B8]
0x18003b04a  mov     qword ptr [rsp+16F8h+var_16D8], rax
0x18003b04f  lea     rdx, word_18008C466
0x18003b056  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@43@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &)
0x18003b05b  jmp     short loc_18003B068
0x18003b05d  xor     r12d, r12d
0x18003b060  jmp     short loc_18003B068
0x18003b062  xor     r12d, r12d
0x18003b065  mov     r15b, r12b
0x18003b068  mov     [rsp+16F8h+var_50], r12b
0x18003b070  mov     eax, [rdi+0ACh]
0x18003b076  cmp     [rdi+0B2h], r12b
0x18003b07d  jz      loc_18003B127
0x18003b083  test    eax, 0FFFFFFFCh
0x18003b088  jnz     short loc_18003B102
0x18003b08a  cmp     eax, 2
0x18003b08d  jz      short loc_18003B102
0x18003b08f  mov     r9, r14
0x18003b092  mov     r8, rdi
0x18003b095  lea     rdx, [rsp+16F8h+var_1688]
0x18003b09a  mov     rcx, rbx; this
0x18003b09d  call    ?NewInternalShouldUpdateInterfaceOneRequestInDisconnectedStandbyImpl@PerFamilyInterfaceProbeInfo@ActiveProbeManager@@AEAA?AV?$optional@UNcsiActiveProbeDataOut@@@std@@AEBUNcsiActiveProbeDataIn@@AEBUNcsiActiveProbeDataOut@@@Z; ActiveProbeManager::PerFamilyInterfaceProbeInfo::NewInternalShouldUpdateInterfaceOneRequestInDisconnectedStandbyImpl(NcsiActiveProbeDataIn const &,NcsiActiveProbeDataOut const &)
0x18003b0a2  cmp     [rsp+16F8h+var_B70], r12b
0x18003b0aa  jz      short loc_18003B0D9
0x18003b0ac  lea     rdx, [rsp+16F8h+var_1688]
0x18003b0b1  lea     rcx, [rsp+16F8h+var_B68]
0x18003b0b9  cmp     [rsp+16F8h+var_50], r12b
0x18003b0c1  jz      short loc_18003B0CA
0x18003b0c3  call    ??4NcsiActiveProbeDataOut@@QEAAAEAU0@$$QEAU0@@Z; NcsiActiveProbeDataOut::operator=(NcsiActiveProbeDataOut &&)
0x18003b0c8  jmp     short loc_18003B0F8
0x18003b0ca  call    ??0NcsiActiveProbeDataOut@@QEAA@$$QEAU0@@Z; NcsiActiveProbeDataOut::NcsiActiveProbeDataOut(NcsiActiveProbeDataOut &&)
0x18003b0cf  mov     [rsp+16F8h+var_50], 1
0x18003b0d7  jmp     short loc_18003B0F8
0x18003b0d9  cmp     [rsp+16F8h+var_50], r12b
0x18003b0e1  jz      short loc_18003B0F8
0x18003b0e3  lea     rcx, [rsp+16F8h+var_B68]; this
0x18003b0eb  call    ??1NcsiActiveProbeDataOut@@QEAA@XZ; NcsiActiveProbeDataOut::~NcsiActiveProbeDataOut(void)
0x18003b0f0  mov     [rsp+16F8h+var_50], r12b
0x18003b0f8  lea     rcx, [rsp+16F8h+var_1688]
0x18003b0fd  call    ??1?$_Non_trivial_move@U?$_Optional_construct_base@UNcsiActiveProbeDataOut@@@std@@UNcsiActiveProbeDataOut@@@std@@QEAA@XZ; std::_Non_trivial_move<std::_Optional_construct_base<NcsiActiveProbeDataOut>,NcsiActiveProbeDataOut>::~_Non_trivial_move<std::_Optional_construct_base<NcsiActiveProbeDataOut>,NcsiActiveProbeDataOut>(void)
0x18003b102  cmp     dword ptr [rdi+0ACh], 2
0x18003b109  jnz     loc_18003B31D
0x18003b10f  mov     r9, r14
0x18003b112  mov     r8, rdi
0x18003b115  lea     rdx, [rsp+16F8h+var_1688]
0x18003b11a  mov     rcx, rbx; this
0x18003b11d  call    ?InternalShouldUpdateInterfaceTwoRequestsInDisconnectedStandby@PerFamilyInterfaceProbeInfo@ActiveProbeManager@@AEAA?AV?$optional@UNcsiActiveProbeDataOut@@@std@@AEBUNcsiActiveProbeDataIn@@AEBUNcsiActiveProbeDataOut@@@Z; ActiveProbeManager::PerFamilyInterfaceProbeInfo::InternalShouldUpdateInterfaceTwoRequestsInDisconnectedStandby(NcsiActiveProbeDataIn const &,NcsiActiveProbeDataOut const &)
0x18003b122  jmp     loc_18003B2C0
0x18003b127  test    eax, eax
0x18003b129  jnz     short loc_18003B1A3
0x18003b12b  mov     [rsp+16F8h+var_16D8], r15b; char
0x18003b130  mov     r9, r14
0x18003b133  mov     r8, rdi
0x18003b136  lea     rdx, [rsp+16F8h+var_1688]
0x18003b13b  mov     rcx, rbx; this
0x18003b13e  call    ?NewInternalShouldUpdateInterfaceOneRequestImpl@PerFamilyInterfaceProbeInfo@ActiveProbeManager@@AEAA?AV?$optional@UNcsiActiveProbeDataOut@@@std@@AEBUNcsiActiveProbeDataIn@@AEBUNcsiActiveProbeDataOut@@_N@Z; ActiveProbeManager::PerFamilyInterfaceProbeInfo::NewInternalShouldUpdateInterfaceOneRequestImpl(NcsiActiveProbeDataIn const &,NcsiActiveProbeDataOut const &,bool)
0x18003b143  cmp     [rsp+16F8h+var_B70], r12b
0x18003b14b  jz      short loc_18003B17A
0x18003b14d  lea     rdx, [rsp+16F8h+var_1688]
0x18003b152  lea     rcx, [rsp+16F8h+var_B68]
0x18003b15a  cmp     [rsp+16F8h+var_50], r12b
0x18003b162  jz      short loc_18003B16B
0x18003b164  call    ??4NcsiActiveProbeDataOut@@QEAAAEAU0@$$QEAU0@@Z; NcsiActiveProbeDataOut::operator=(NcsiActiveProbeDataOut &&)
0x18003b169  jmp     short loc_18003B199
0x18003b16b  call    ??0NcsiActiveProbeDataOut@@QEAA@$$QEAU0@@Z; NcsiActiveProbeDataOut::NcsiActiveProbeDataOut(NcsiActiveProbeDataOut &&)
0x18003b170  mov     [rsp+16F8h+var_50], 1
0x18003b178  jmp     short loc_18003B199
0x18003b17a  cmp     [rsp+16F8h+var_50], r12b
0x18003b182  jz      short loc_18003B199
0x18003b184  lea     rcx, [rsp+16F8h+var_B68]; this
0x18003b18c  call    ??1NcsiActiveProbeDataOut@@QEAA@XZ; NcsiActiveProbeDataOut::~NcsiActiveProbeDataOut(void)
0x18003b191  mov     [rsp+16F8h+var_50], r12b
0x18003b199  lea     rcx, [rsp+16F8h+var_1688]
0x18003b19e  call    ??1?$_Non_trivial_move@U?$_Optional_construct_base@UNcsiActiveProbeDataOut@@@std@@UNcsiActiveProbeDataOut@@@std@@QEAA@XZ; std::_Non_trivial_move<std::_Optional_construct_base<NcsiActiveProbeDataOut>,NcsiActiveProbeDataOut>::~_Non_trivial_move<std::_Optional_construct_base<NcsiActiveProbeDataOut>,NcsiActiveProbeDataOut>(void)
0x18003b1a3  cmp     dword ptr [rdi+0ACh], 1
0x18003b1aa  jnz     short loc_18003B221
0x18003b1ac  mov     [rsp+16F8h+var_16D8], r15b; char
0x18003b1b1  mov     r9, r14
0x18003b1b4  mov     r8, rdi
0x18003b1b7  lea     rdx, [rsp+16F8h+var_1688]
0x18003b1bc  mov     rcx, rbx; this
0x18003b1bf  call    ?InternalShouldUpdateInterfaceTwoRequests@PerFamilyInterfaceProbeInfo@ActiveProbeManager@@AEAA?AV?$optional@UNcsiActiveProbeDataOut@@@std@@AEBUNcsiActiveProbeDataIn@@AEBUNcsiActiveProbeDataOut@@_N@Z; ActiveProbeManager::PerFamilyInterfaceProbeInfo::InternalShouldUpdateInterfaceTwoRequests(NcsiActiveProbeDataIn const &,NcsiActiveProbeDataOut const &,bool)
0x18003b1c4  cmp     [rax+0B18h], r12b
0x18003b1cb  jz      short loc_18003B1F8
0x18003b1cd  mov     rdx, rax
0x18003b1d0  lea     rcx, [rsp+16F8h+var_B68]
0x18003b1d8  cmp     [rsp+16F8h+var_50], r12b
0x18003b1e0  jz      short loc_18003B1E9
0x18003b1e2  call    ??4NcsiActiveProbeDataOut@@QEAAAEAU0@$$QEAU0@@Z; NcsiActiveProbeDataOut::operator=(NcsiActiveProbeDataOut &&)
0x18003b1e7  jmp     short loc_18003B217
0x18003b1e9  call    ??0NcsiActiveProbeDataOut@@QEAA@$$QEAU0@@Z; NcsiActiveProbeDataOut::NcsiActiveProbeDataOut(NcsiActiveProbeDataOut &&)
0x18003b1ee  mov     [rsp+16F8h+var_50], 1
0x18003b1f6  jmp     short loc_18003B217
0x18003b1f8  cmp     [rsp+16F8h+var_50], r12b
0x18003b200  jz      short loc_18003B217
0x18003b202  lea     rcx, [rsp+16F8h+var_B68]; this
0x18003b20a  call    ??1NcsiActiveProbeDataOut@@QEAA@XZ; NcsiActiveProbeDataOut::~NcsiActiveProbeDataOut(void)
0x18003b20f  mov     [rsp+16F8h+var_50], r12b
0x18003b217  lea     rcx, [rsp+16F8h+var_1688]
0x18003b21c  call    ??1?$_Non_trivial_move@U?$_Optional_construct_base@UNcsiActiveProbeDataOut@@@std@@UNcsiActiveProbeDataOut@@@std@@QEAA@XZ; std::_Non_trivial_move<std::_Optional_construct_base<NcsiActiveProbeDataOut>,NcsiActiveProbeDataOut>::~_Non_trivial_move<std::_Optional_construct_base<NcsiActiveProbeDataOut>,NcsiActiveProbeDataOut>(void)
0x18003b221  cmp     dword ptr [rdi+0ACh], 2
0x18003b228  jnz     short loc_18003B29F
0x18003b22a  mov     [rsp+16F8h+var_16D8], r15b; char
0x18003b22f  mov     r9, r14
0x18003b232  mov     r8, rdi
0x18003b235  lea     rdx, [rsp+16F8h+var_1688]
0x18003b23a  mov     rcx, rbx; this
0x18003b23d  call    ?InternalShouldUpdateInterfaceThreeRequests@PerFamilyInterfaceProbeInfo@ActiveProbeManager@@AEAA?AV?$optional@UNcsiActiveProbeDataOut@@@std@@AEBUNcsiActiveProbeDataIn@@AEBUNcsiActiveProbeDataOut@@_N@Z; ActiveProbeManager::PerFamilyInterfaceProbeInfo::InternalShouldUpdateInterfaceThreeRequests(NcsiActiveProbeDataIn const &,NcsiActiveProbeDataOut const &,bool)
0x18003b242  cmp     [rax+0B18h], r12b
0x18003b249  jz      short loc_18003B276
0x18003b24b  mov     rdx, rax
0x18003b24e  lea     rcx, [rsp+16F8h+var_B68]
0x18003b256  cmp     [rsp+16F8h+var_50], r12b
0x18003b25e  jz      short loc_18003B267
0x18003b260  call    ??4NcsiActiveProbeDataOut@@QEAAAEAU0@$$QEAU0@@Z; NcsiActiveProbeDataOut::operator=(NcsiActiveProbeDataOut &&)
0x18003b265  jmp     short loc_18003B295
0x18003b267  call    ??0NcsiActiveProbeDataOut@@QEAA@$$QEAU0@@Z; NcsiActiveProbeDataOut::NcsiActiveProbeDataOut(NcsiActiveProbeDataOut &&)
0x18003b26c  mov     [rsp+16F8h+var_50], 1
0x18003b274  jmp     short loc_18003B295
0x18003b276  cmp     [rsp+16F8h+var_50], r12b
0x18003b27e  jz      short loc_18003B295
0x18003b280  lea     rcx, [rsp+16F8h+var_B68]; this
0x18003b288  call    ??1NcsiActiveProbeDataOut@@QEAA@XZ; NcsiActiveProbeDataOut::~NcsiActiveProbeDataOut(void)
0x18003b28d  mov     [rsp+16F8h+var_50], r12b
0x18003b295  lea     rcx, [rsp+16F8h+var_1688]
0x18003b29a  call    ??1?$_Non_trivial_move@U?$_Optional_construct_base@UNcsiActiveProbeDataOut@@@std@@UNcsiActiveProbeDataOut@@@std@@QEAA@XZ; std::_Non_trivial_move<std::_Optional_construct_base<NcsiActiveProbeDataOut>,NcsiActiveProbeDataOut>::~_Non_trivial_move<std::_Optional_construct_base<NcsiActiveProbeDataOut>,NcsiActiveProbeDataOut>(void)
0x18003b29f  cmp     dword ptr [rdi+0ACh], 3
0x18003b2a6  jnz     short loc_18003B31D
0x18003b2a8  mov     [rsp+16F8h+var_16D8], r15b; char
0x18003b2ad  mov     r9, r14
0x18003b2b0  mov     r8, rdi
0x18003b2b3  lea     rdx, [rsp+16F8h+var_1688]
0x18003b2b8  mov     rcx, rbx; lpCriticalSection
0x18003b2bb  call    ?InternalShouldUpdateInterfaceUserProxyRequests@PerFamilyInterfaceProbeInfo@ActiveProbeManager@@AEAA?AV?$optional@UNcsiActiveProbeDataOut@@@std@@AEBUNcsiActiveProbeDataIn@@AEBUNcsiActiveProbeDataOut@@_N@Z; ActiveProbeManager::PerFamilyInterfaceProbeInfo::InternalShouldUpdateInterfaceUserProxyRequests(NcsiActiveProbeDataIn const &,NcsiActiveProbeDataOut const &,bool)
0x18003b2c0  cmp     [rax+0B18h], r12b
0x18003b2c7  jz      short loc_18003B2F4
0x18003b2c9  mov     rdx, rax
0x18003b2cc  lea     rcx, [rsp+16F8h+var_B68]
0x18003b2d4  cmp     [rsp+16F8h+var_50], r12b
0x18003b2dc  jz      short loc_18003B2E5
0x18003b2de  call    ??4NcsiActiveProbeDataOut@@QEAAAEAU0@$$QEAU0@@Z; NcsiActiveProbeDataOut::operator=(NcsiActiveProbeDataOut &&)
0x18003b2e3  jmp     short loc_18003B313
0x18003b2e5  call    ??0NcsiActiveProbeDataOut@@QEAA@$$QEAU0@@Z; NcsiActiveProbeDataOut::NcsiActiveProbeDataOut(NcsiActiveProbeDataOut &&)
0x18003b2ea  mov     [rsp+16F8h+var_50], 1
0x18003b2f2  jmp     short loc_18003B313
0x18003b2f4  cmp     [rsp+16F8h+var_50], r12b
0x18003b2fc  jz      short loc_18003B313
0x18003b2fe  lea     rcx, [rsp+16F8h+var_B68]; this
0x18003b306  call    ??1NcsiActiveProbeDataOut@@QEAA@XZ; NcsiActiveProbeDataOut::~NcsiActiveProbeDataOut(void)
0x18003b30b  mov     [rsp+16F8h+var_50], r12b
0x18003b313  lea     rcx, [rsp+16F8h+var_1688]
0x18003b318  call    ??1?$_Non_trivial_move@U?$_Optional_construct_base@UNcsiActiveProbeDataOut@@@std@@UNcsiActiveProbeDataOut@@@std@@QEAA@XZ; std::_Non_trivial_move<std::_Optional_construct_base<NcsiActiveProbeDataOut>,NcsiActiveProbeDataOut>::~_Non_trivial_move<std::_Optional_construct_base<NcsiActiveProbeDataOut>,NcsiActiveProbeDataOut>(void)
0x18003b31d  cmp     [rsp+16F8h+var_50], r12b
0x18003b325  jz      loc_18003B41F
0x18003b32b  mov     eax, [rdi+0ACh]
0x18003b331  mov     [rbx+0C58h], eax
0x18003b337  mov     byte ptr [rbx+0C5Ch], 1
0x18003b33e  movzx   eax, word ptr [rsp+16F8h+var_16B8+5]
0x18003b343  mov     [rbx+0C5Dh], ax
0x18003b34a  mov     al, byte ptr [rsp+16F8h+var_16B8+7]
0x18003b34e  mov     [rbx+0C5Fh], al
0x18003b354  mov     eax, [rdi+0A8h]
0x18003b35a  mov     [rbx+0C60h], eax
0x18003b360  mov     byte ptr [rbx+0C64h], 1
0x18003b367  movzx   eax, word ptr [rsp+16F8h+var_16B8+5]
0x18003b36c  mov     [rbx+0C65h], ax
0x18003b373  mov     al, byte ptr [rsp+16F8h+var_16B8+7]
0x18003b377  mov     [rbx+0C67h], al
0x18003b37d  cmp     [r14+0A5Ch], r12b
0x18003b384  jnz     short loc_18003B395
0x18003b386  mov     rcx, r14; this
0x18003b389  call    ?RequestCompleteOverCaptivePortal@NcsiActiveProbeDataOut@@QEBA_NXZ; NcsiActiveProbeDataOut::RequestCompleteOverCaptivePortal(void)
0x18003b38e  test    al, al
0x18003b390  mov     al, r12b
0x18003b393  jz      short loc_18003B397
0x18003b395  mov     al, 1
0x18003b397  mov     [rbx+0C68h], al
0x18003b39d  mov     byte ptr [rbx+0C69h], 1
0x18003b3a4  mov     al, [rdi+0B2h]
0x18003b3aa  mov     [rbx+0C6Ah], al
0x18003b3b0  mov     byte ptr [rbx+0C6Bh], 1
0x18003b3b7  movups  xmm0, xmmword ptr [rdi+0B4h]
0x18003b3be  movups  xmmword ptr [rbx+0C6Ch], xmm0
0x18003b3c5  movups  xmm1, xmmword ptr [rdi+0C4h]
0x18003b3cc  movups  xmmword ptr [rbx+0C7Ch], xmm1
0x18003b3d3  movzx   eax, word ptr [rdi+0D4h]
0x18003b3da  mov     [rbx+0C8Ch], ax
0x18003b3e1  mov     [rsi+0B18h], r12b
0x18003b3e8  lea     rdx, [rsp+16F8h+var_B68]
0x18003b3f0  mov     rcx, rsi
0x18003b3f3  call    ??0NcsiActiveProbeDataOut@@QEAA@$$QEAU0@@Z; NcsiActiveProbeDataOut::NcsiActiveProbeDataOut(NcsiActiveProbeDataOut &&)
  ... truncated ...
```
