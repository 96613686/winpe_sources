# ActiveProbeManager::PerFamilyInterfaceProbeInfo::NcsiQueueActiveInternetProbe(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *)

- ea: `0x18003a500`
- end: `0x18003ac88`
- name: `?NcsiQueueActiveInternetProbe@PerFamilyInterfaceProbeInfo@ActiveProbeManager@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z`
- size: `1928`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_TIMER Timer)`
- caller_count: `0`
- callee_count: `26`
- tags: `registry_config, installer_update`

## callees

- `0x180006f98`
- `0x1800070e4`
- `0x18000bf68`
- `0x18000ce20`
- `0x18000ce78`
- `0x18000cea4`
- `0x18000d188`
- `0x18000e350`
- `0x18000e824`
- `0x18001d5c8`
- `0x18001de84`
- `0x1800213cc`
- `0x18002141c`
- `0x1800216f0`
- `0x180026ca0`
- `0x18002a790`
- `0x18002b84c`
- `0x18003a500`
- `0x18003b478`
- `0x18003ea30`
- `0x180042a38`
- `0x18004354c`
- `0x180047240`
- `0x1800472d8`
- `0x18006082c`
- `0x180069f3c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003a61f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003a633`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003a732`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003aae2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003ac38`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003a61f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003a633`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003a732`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003aae2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003ac38`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003a5db`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003a60f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003a74f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003a5db`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003a60f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003a74f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a9e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a9e0`

## string_xrefs

- `0x18003ab93`: `NcsiThreadPoolTrySubmit succeeded`
- `0x18003aa4b`: `NcsiThreadPoolTrySubmit failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall ActiveProbeManager::PerFamilyInterfaceProbeInfo::NcsiQueueActiveInternetProbe(
        PTP_CALLBACK_INSTANCE Instance,
        char *Context,
        PTP_TIMER Timer)
{
  int v4; // r13d
  struct NCSI_INTERFACE_ATTRIBUTES *InterfaceAttributes; // rax
  NCSI_INTERFACE_ATTRIBUTES *v6; // rcx
  unsigned int v7; // r10d
  __int64 v8; // rcx
  _OWORD *HttpProbeServerCache; // rax
  __int64 v10; // r10
  __int64 v11; // rcx
  __int64 DnsServerAddresses; // rax
  Ncsi::Power *v13; // rcx
  char v14; // r14
  Ncsi::Power *v15; // rcx
  char IsSystemInStandby; // r15
  __int64 updated; // rsi
  _DWORD *v18; // rdi
  _DWORD *v19; // r12
  int v20; // ecx
  int v21; // ecx
  int v22; // ecx
  int v23; // ecx
  int v24; // ecx
  int v25; // ecx
  bool v26; // al
  __int64 v27; // rcx
  __int64 v28; // r8
  __int64 v29; // r9
  NcsiActiveProbeDataIn *v30; // rax
  int v31; // r8d
  __int64 v32; // rcx
  __int64 v33; // r8
  __int64 v34; // r9
  const char *v35; // r9
  __int64 v36; // rcx
  __int64 v37; // r8
  __int64 v38; // r9
  LPCRITICAL_SECTION v39; // rbx
  char v40; // [rsp+70h] [rbp-1D8h] BYREF
  _BYTE v41[7]; // [rsp+71h] [rbp-1D7h] BYREF
  const size_t *v42; // [rsp+78h] [rbp-1D0h] BYREF
  const unsigned __int16 *v43; // [rsp+80h] [rbp-1C8h] BYREF
  const size_t *v44; // [rsp+88h] [rbp-1C0h] BYREF
  const char *active; // [rsp+90h] [rbp-1B8h] BYREF
  const size_t *v46; // [rsp+98h] [rbp-1B0h] BYREF
  const char *v47; // [rsp+A0h] [rbp-1A8h] BYREF
  NcsiActiveProbeDataIn *v48; // [rsp+A8h] [rbp-1A0h] BYREF
  LPCRITICAL_SECTION v49; // [rsp+B0h] [rbp-198h]
  _BYTE v50[40]; // [rsp+B8h] [rbp-190h] BYREF
  _OWORD v51[2]; // [rsp+E0h] [rbp-168h] BYREF
  __int16 v52; // [rsp+100h] [rbp-148h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+110h] [rbp-138h] BYREF
  __int128 v54; // [rsp+118h] [rbp-130h] BYREF
  __int64 v55; // [rsp+128h] [rbp-120h]
  __int64 v56; // [rsp+130h] [rbp-118h] BYREF
  __int128 v57; // [rsp+138h] [rbp-110h]
  __int64 v58; // [rsp+148h] [rbp-100h]
  __int64 v59; // [rsp+150h] [rbp-F8h] BYREF
  __int64 v60; // [rsp+188h] [rbp-C0h]
  const size_t *v61; // [rsp+190h] [rbp-B8h]
  _OWORD v62[2]; // [rsp+198h] [rbp-B0h] BYREF
  __int64 v63; // [rsp+1B8h] [rbp-90h] BYREF
  __int128 v64; // [rsp+1C0h] [rbp-88h]
  __int64 v65; // [rsp+1D0h] [rbp-78h]
  __int64 v66; // [rsp+1D8h] [rbp-70h]
  int v67; // [rsp+1E0h] [rbp-68h]
  __int128 v68; // [rsp+1E4h] [rbp-64h]
  __int128 v69; // [rsp+1F4h] [rbp-54h]
  int v70; // [rsp+204h] [rbp-44h]
  char *v71; // [rsp+210h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+248h] [rbp+0h]

  v49 = (LPCRITICAL_SECTION)Context;
  v4 = 0;
  LODWORD(v42) = 0;
  v56 = 0;
  v57 = 0;
  v58 = 15;
  Ncsi::Proxy::Info::Info((Ncsi::Proxy::Info *)&v59);
  v60 = 2;
  v61 = 0;
  memset(v62, 0, sizeof(v62));
  v63 = 0;
  v64 = 0;
  v65 = 0;
  v66 = 0;
  v67 = 0;
  v68 = 0;
  v69 = 0;
  v70 = 0;
  EnterCriticalSection(&g_ncsiLock);
  lpCriticalSection = &g_ncsiLock;
  InterfaceAttributes = FindInterfaceAttributes(*(union _NET_LUID_LH *)(Context + 3224));
  if ( InterfaceAttributes )
  {
    v56 = *(_QWORD *)InterfaceAttributes;
    v57 = *(_OWORD *)((char *)InterfaceAttributes + 8);
    LODWORD(v60) = *((_DWORD *)Context + 808);
    BYTE6(v58) = NCSI_INTERFACE_ATTRIBUTES::IsBehindHotspot(InterfaceAttributes, (unsigned int)v60);
    v61 = (const size_t *)*((_QWORD *)v6 + 1460);
    HIBYTE(v58) = NCSI_INTERFACE_ATTRIBUTES::CanPerformGatewayArpProbe(v6);
    HttpProbeServerCache = (_OWORD *)NCSI_INTERFACE_ATTRIBUTES::GetHttpProbeServerCache(v8, v50, v7);
    v62[0] = *HttpProbeServerCache;
    *(_OWORD *)((char *)v62 + 12) = *(_OWORD *)((char *)HttpProbeServerCache + 12);
    v68 = *(_OWORD *)(3944 * v10 + v11 + 4388);
    v69 = *(_OWORD *)(3944 * v10 + v11 + 4404);
    LOWORD(v70) = *(_WORD *)(3944 * v10 + v11 + 4420);
    try
    {
      DnsServerAddresses = GetDnsServerAddresses();
      std::vector<_SOCKADDR_INET>::operator=(&v63, DnsServerAddresses);
      std::vector<_SOCKADDR_INET>::_Tidy(v50);
      LeaveCriticalSection(&g_ncsiLock);
      v54 = 0;
      v55 = 0;
      EnterCriticalSection((LPCRITICAL_SECTION)Context);
      v71 = Context;
      v14 = Context[3217];
      if ( v14 )
      {
        IsSystemInStandby = Context[3216];
      }
      else
      {
        IsSystemInStandby = Ncsi::Power::IsSystemInStandby(v13);
        v14 = IsSystemInStandby && Ncsi::Power::ShouldDisconnectInStandby(v15);
      }
      v51[0] = v68;
      v51[1] = v69;
      v52 = v70;
      updated = ActiveProbeManager::PerFamilyInterfaceProbeInfo::UpdateProbeStageTypeAndPopulateProbeTypeList(
                  (_DWORD)Context,
                  (unsigned int)v50,
                  (int)Context + 3160,
                  (unsigned int)v51,
                  v14);
      if ( &v54 == (__int128 *)updated )
      {
        v19 = (_DWORD *)*((_QWORD *)&v54 + 1);
        v18 = (_DWORD *)v54;
      }
      else
      {
        std::vector<enum _ActiveProbeType>::_Tidy(&v54);
        v18 = *(_DWORD **)updated;
        *(_QWORD *)&v54 = *(_QWORD *)updated;
        v19 = *(_DWORD **)(updated + 8);
        *((_QWORD *)&v54 + 1) = v19;
        v55 = *(_QWORD *)(updated + 16);
        *(_QWORD *)updated = 0;
        *(_QWORD *)(updated + 8) = 0;
        *(_QWORD *)(updated + 16) = 0;
      }
      std::vector<enum _ActiveProbeType>::_Tidy(v50);
      v20 = *((_DWORD *)Context + 774);
      LODWORD(v58) = v20;
      v65 = *((_QWORD *)Context + 390);
      HIDWORD(v66) = *((_DWORD *)Context + 775);
      LOBYTE(v67) = Context[3129];
      v26 = 1;
      if ( v20 )
      {
        v21 = v20 - 1;
        if ( v21 )
        {
          v22 = v21 - 1;
          if ( v22 )
          {
            v23 = v22 - 2;
            if ( v23 )
            {
              v24 = v23 - 2;
              if ( v24 )
              {
                v25 = v24 - 1;
                if ( v25 )
                {
                  if ( (unsigned int)(v25 - 1) >= 2 )
                    v26 = 0;
                }
              }
            }
          }
        }
      }
      BYTE5(v58) = v26;
      while ( v18 != v19 )
      {
        if ( !v14 || ((*v18 - 1) & 0xFFFFFFFB) != 0 )
        {
          v48 = (NcsiActiveProbeDataIn *)operator new(0xD8u);
          v30 = NcsiActiveProbeDataIn::NcsiActiveProbeDataIn(v48, (const struct NcsiActiveProbeDataIn *)&v56);
          lpCriticalSection = (LPCRITICAL_SECTION)v30;
          *((_DWORD *)v30 + 42) = *v18;
          *((_BYTE *)v30 + 177) = IsSystemInStandby;
          *((_BYTE *)v30 + 178) = v14;
          if ( !(unsigned int)NcsiThreadPoolTrySubmit(NcsiActiveProbeCallback, v30) )
          {
            GetLastError();
            if ( (unsigned int)dword_18009A080 > 5 )
            {
              v40 = v14;
              v41[0] = IsSystemInStandby;
              active = (const char *)ActiveProbeStageToString(*((unsigned int *)Context + 775));
              v44 = (const size_t *)ActiveProbeTypeToString((unsigned int)*v18);
              LODWORD(v42) = v31;
              v43 = (const unsigned __int16 *)ToString(*((unsigned int *)Context + 808));
              v46 = (const size_t *)*((_QWORD *)Context + 403);
              v47 = "NcsiThreadPoolTrySubmit failed";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>>(
                v32,
                (int)byte_18008C3CB,
                v33,
                v34,
                (const unsigned __int16 **)&v47,
                (__int64)&v46,
                &v43,
                (__int64)&v42,
                &v44,
                (const size_t **)&active,
                (__int64)v41,
                (__int64)&v40);
            }
            Context[3130] = 0;
            std::unique_ptr<NcsiActiveProbeDataIn>::~unique_ptr<NcsiActiveProbeDataIn>(&lpCriticalSection);
            if ( Context )
              LeaveCriticalSection((LPCRITICAL_SECTION)Context);
            goto LABEL_35;
          }
          v4 |= 1u;
          lpCriticalSection = 0;
          if ( (unsigned int)dword_18009A080 > 5 )
          {
            v41[0] = v14;
            v40 = IsSystemInStandby;
            v47 = (const char *)ActiveProbeStageToString(*((unsigned int *)Context + 775));
            v46 = (const size_t *)ActiveProbeTypeToString((unsigned int)*v18);
            active = (const char *)*((_QWORD *)Context + 390);
            v44 = v61;
            v43 = (const unsigned __int16 *)ToString(*((unsigned int *)Context + 808));
            v42 = (const size_t *)*((_QWORD *)Context + 403);
            v48 = (NcsiActiveProbeDataIn *)"NcsiThreadPoolTrySubmit succeeded";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>>(
              v36,
              (unsigned __int8 *)&dword_18008C6A4,
              v37,
              v38,
              (const unsigned __int16 **)&v48,
              (__int64)&v42,
              &v43,
              (__int64)&v44,
              (__int64)&active,
              &v46,
              (const size_t **)&v47,
              (__int64)&v40,
              (__int64)v41);
          }
          std::unique_ptr<NcsiActiveProbeDataIn>::~unique_ptr<NcsiActiveProbeDataIn>(&lpCriticalSection);
        }
        else if ( (unsigned int)dword_18009A080 > 5 )
        {
          lpCriticalSection = (LPCRITICAL_SECTION)ActiveProbeStageToString(*((unsigned int *)Context + 775));
          v42 = (const size_t *)ActiveProbeTypeToString((unsigned int)*v18);
          v43 = (const unsigned __int16 *)ToString(*((unsigned int *)Context + 808));
          v44 = (const size_t *)*((_QWORD *)Context + 403);
          active = "Skip global request in DS";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
            v27,
            (int)&byte_18008C867,
            v28,
            v29,
            (const unsigned __int16 **)&active,
            (__int64)&v44,
            &v43,
            &v42,
            (const size_t **)&lpCriticalSection);
        }
        ++v18;
      }
      if ( Context )
        LeaveCriticalSection((LPCRITICAL_SECTION)Context);
LABEL_35:
      std::vector<enum _ActiveProbeType>::_Tidy(&v54);
      NcsiActiveProbeDataIn::~NcsiActiveProbeDataIn((NcsiActiveProbeDataIn *)&v56);
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x1D0,
        (unsigned int)"onecore\\net\\diagnostics\\ncsi\\activeprobemanager\\lib\\activeprobemanager.cpp",
        v35);
      v39 = v49;
      EnterCriticalSection(v49);
      BYTE2(v39[78].LockCount) = 0;
      LeaveCriticalSection(v39);
    }
  }
  else
  {
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::reset(
      &lpCriticalSection,
      0);
    EnterCriticalSection((LPCRITICAL_SECTION)Context);
    Context[3130] = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)Context);
    if ( lpCriticalSection )
      LeaveCriticalSection(lpCriticalSection);
    NcsiActiveProbeDataIn::~NcsiActiveProbeDataIn((NcsiActiveProbeDataIn *)&v56);
  }
}

```

## disassembly

```asm
0x18003a500  mov     r11, rsp
0x18003a503  mov     [r11+8], rbx
0x18003a507  mov     [r11+18h], rsi
0x18003a50b  push    rdi
0x18003a50c  push    r12
0x18003a50e  push    r13
0x18003a510  push    r14
0x18003a512  push    r15
0x18003a514  sub     rsp, 220h
0x18003a51b  mov     rax, cs:__security_cookie
0x18003a522  xor     rax, rsp
0x18003a525  mov     [rsp+248h+var_30], rax
0x18003a52d  mov     rbx, rdx
0x18003a530  mov     [rsp+248h+var_198], rdx
0x18003a538  xor     edi, edi
0x18003a53a  mov     r13d, edi
0x18003a53d  mov     dword ptr [rsp+248h+var_1D0], edi
0x18003a541  xor     eax, eax
0x18003a543  mov     [r11-118h], rax
0x18003a54a  xorps   xmm0, xmm0
0x18003a54d  movups  [rsp+248h+var_110], xmm0
0x18003a555  mov     qword ptr [r11-100h], 0Fh
0x18003a560  lea     rcx, [r11-0F8h]; this
0x18003a567  call    ??0Info@Proxy@Ncsi@@QEAA@XZ; Ncsi::Proxy::Info::Info(void)
0x18003a56c  mov     [rsp+248h+var_C0], 2
0x18003a578  mov     [rsp+248h+var_B8], rdi
0x18003a580  movups  [rsp+248h+var_B0], xmm0
0x18003a588  movups  [rsp+248h+var_A0], xmm0
0x18003a590  mov     [rsp+248h+var_90], rdi
0x18003a598  movdqa  [rsp+248h+var_88], xmm0
0x18003a5a1  mov     [rsp+248h+var_78], rdi
0x18003a5a9  mov     [rsp+248h+var_70], rdi
0x18003a5b1  mov     [rsp+248h+var_68], edi
0x18003a5b8  xor     eax, eax
0x18003a5ba  movups  [rsp+248h+var_64], xmm0
0x18003a5c2  movups  [rsp+248h+var_54], xmm0
0x18003a5ca  mov     [rsp+248h+var_44], eax
0x18003a5d1  lea     rsi, ?g_ncsiLock@@3Vcritical_section@wil@@A; wil::critical_section g_ncsiLock
0x18003a5d8  mov     rcx, rsi; lpCriticalSection
0x18003a5db  call    cs:__imp_EnterCriticalSection
0x18003a5e1  mov     [rsp+248h+lpCriticalSection], rsi
0x18003a5e9  mov     rcx, [rbx+0C98h]; union _NET_LUID_LH
0x18003a5f0  call    ?FindInterfaceAttributes@@YAPEAVNCSI_INTERFACE_ATTRIBUTES@@T_NET_LUID_LH@@@Z; FindInterfaceAttributes(_NET_LUID_LH)
0x18003a5f5  mov     rcx, rax
0x18003a5f8  test    rax, rax
0x18003a5fb  jnz     short loc_18003A64D
0x18003a5fd  xor     edx, edx
0x18003a5ff  lea     rcx, [rsp+248h+lpCriticalSection]
0x18003a607  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_RTL_CRITICAL_SECTION@@@Z; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::reset(_RTL_CRITICAL_SECTION *)
0x18003a60c  mov     rcx, rbx; lpCriticalSection
0x18003a60f  call    cs:__imp_EnterCriticalSection
0x18003a615  mov     [rbx+0C3Ah], dil
0x18003a61c  mov     rcx, rbx; lpCriticalSection
0x18003a61f  call    cs:__imp_LeaveCriticalSection
0x18003a625  nop
0x18003a626  mov     rcx, [rsp+248h+lpCriticalSection]; lpCriticalSection
0x18003a62e  test    rcx, rcx
0x18003a631  jz      short loc_18003A63A
0x18003a633  call    cs:__imp_LeaveCriticalSection
0x18003a639  nop
0x18003a63a  lea     rcx, [rsp+248h+var_118]; this
0x18003a642  call    ??1NcsiActiveProbeDataIn@@QEAA@XZ; NcsiActiveProbeDataIn::~NcsiActiveProbeDataIn(void)
0x18003a647  nop
0x18003a648  jmp     loc_18003AC5B
0x18003a64d  mov     rax, [rax]
0x18003a650  mov     [rsp+248h+var_118], rax
0x18003a658  movups  xmm0, xmmword ptr [rcx+8]
0x18003a65c  movdqu  [rsp+248h+var_110], xmm0
0x18003a665  movsxd  r10, dword ptr [rbx+0CA0h]
0x18003a66c  mov     dword ptr [rsp+248h+var_C0], r10d
0x18003a674  mov     edx, r10d
0x18003a677  call    ?IsBehindHotspot@NCSI_INTERFACE_ATTRIBUTES@@QEBA_NW4_NLA_CONNECTIVITY_FAMILY@@@Z; NCSI_INTERFACE_ATTRIBUTES::IsBehindHotspot(_NLA_CONNECTIVITY_FAMILY)
0x18003a67c  mov     [rsp+248h+var_FA], al
0x18003a683  mov     rax, [rcx+2DA0h]
0x18003a68a  mov     [rsp+248h+var_B8], rax
0x18003a692  call    ?CanPerformGatewayArpProbe@NCSI_INTERFACE_ATTRIBUTES@@QEBA_NXZ; NCSI_INTERFACE_ATTRIBUTES::CanPerformGatewayArpProbe(void)
0x18003a697  mov     [rsp+248h+var_F9], al
0x18003a69e  mov     r8d, r10d
0x18003a6a1  lea     rdx, [rsp+248h+var_190]
0x18003a6a9  call    ?GetHttpProbeServerCache@NCSI_INTERFACE_ATTRIBUTES@@QEBA?BT_SOCKADDR_INET@@W4_NLA_CONNECTIVITY_FAMILY@@@Z; NCSI_INTERFACE_ATTRIBUTES::GetHttpProbeServerCache(_NLA_CONNECTIVITY_FAMILY)
0x18003a6ae  movups  xmm2, xmmword ptr [rax]
0x18003a6b1  movups  [rsp+248h+var_B0], xmm2
0x18003a6b9  movups  xmm0, xmmword ptr [rax+0Ch]
0x18003a6bd  movups  [rsp+248h+var_B0+0Ch], xmm0
0x18003a6c5  imul    rax, r10, 0F68h
0x18003a6cc  movups  xmm0, xmmword ptr [rax+rcx+1124h]
0x18003a6d4  movups  [rsp+248h+var_64], xmm0
0x18003a6dc  movups  xmm1, xmmword ptr [rax+rcx+1134h]
0x18003a6e4  movups  [rsp+248h+var_54], xmm1
0x18003a6ec  movzx   eax, word ptr [rax+rcx+1144h]
0x18003a6f4  mov     word ptr [rsp+248h+var_44], ax
0x18003a6fc  lea     r8, [rsp+248h+var_118]
0x18003a704  lea     rcx, [rsp+248h+var_190]
0x18003a70c  call    GetDnsServerAddresses
0x18003a711  mov     rdx, rax
0x18003a714  lea     rcx, [rsp+248h+var_90]
0x18003a71c  call    ??4?$vector@T_SOCKADDR_INET@@V?$allocator@T_SOCKADDR_INET@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<_SOCKADDR_INET>::operator=(std::vector<_SOCKADDR_INET> &&)
0x18003a721  lea     rcx, [rsp+248h+var_190]
0x18003a729  call    ?_Tidy@?$vector@T_SOCKADDR_INET@@V?$allocator@T_SOCKADDR_INET@@@std@@@std@@AEAAXXZ; std::vector<_SOCKADDR_INET>::_Tidy(void)
0x18003a72e  nop
0x18003a72f  mov     rcx, rsi; lpCriticalSection
0x18003a732  call    cs:__imp_LeaveCriticalSection
0x18003a738  xorps   xmm1, xmm1
0x18003a73b  movdqu  [rsp+248h+var_130], xmm1
0x18003a744  mov     [rsp+248h+var_120], rdi
0x18003a74c  mov     rcx, rbx; lpCriticalSection
0x18003a74f  call    cs:__imp_EnterCriticalSection
0x18003a755  mov     [rsp+248h+var_38], rbx
0x18003a75d  mov     r14b, [rbx+0C91h]
0x18003a764  test    r14b, r14b
0x18003a767  jnz     short loc_18003A788
0x18003a769  call    ?IsSystemInStandby@Power@Ncsi@@YA_NXZ; Ncsi::Power::IsSystemInStandby(void)
0x18003a76e  mov     r15b, al
0x18003a771  test    al, al
0x18003a773  jz      short loc_18003A783
0x18003a775  call    ?ShouldDisconnectInStandby@Power@Ncsi@@YA_NXZ; Ncsi::Power::ShouldDisconnectInStandby(void)
0x18003a77a  test    al, al
0x18003a77c  jz      short loc_18003A783
0x18003a77e  mov     r14b, 1
0x18003a781  jmp     short loc_18003A78F
0x18003a783  mov     r14b, dil
0x18003a786  jmp     short loc_18003A78F
0x18003a788  mov     r15b, [rbx+0C90h]
0x18003a78f  movups  xmm0, [rsp+248h+var_64]
0x18003a797  movaps  [rsp+248h+var_168], xmm0
0x18003a79f  movups  xmm1, [rsp+248h+var_54]
0x18003a7a7  movaps  [rsp+248h+var_158], xmm1
0x18003a7af  movzx   eax, word ptr [rsp+248h+var_44]
0x18003a7b7  mov     [rsp+248h+var_148], ax
0x18003a7bf  lea     r8, [rbx+0C58h]
0x18003a7c6  mov     byte ptr [rsp+248h+var_228], r14b
0x18003a7cb  lea     r9, [rsp+248h+var_168]
0x18003a7d3  lea     rdx, [rsp+248h+var_190]
0x18003a7db  mov     rcx, rbx
0x18003a7de  call    ?UpdateProbeStageTypeAndPopulateProbeTypeList@PerFamilyInterfaceProbeInfo@ActiveProbeManager@@AEAA?AV?$vector@W4_ActiveProbeType@@V?$allocator@W4_ActiveProbeType@@@std@@@std@@AEAULatestProbeInfo@@U_IF_PHYSICAL_ADDRESS_LH@@_N@Z; ActiveProbeManager::PerFamilyInterfaceProbeInfo::UpdateProbeStageTypeAndPopulateProbeTypeList(LatestProbeInfo &,_IF_PHYSICAL_ADDRESS_LH,bool)
0x18003a7e3  mov     rsi, rax
0x18003a7e6  lea     rax, [rsp+248h+var_130]
0x18003a7ee  cmp     rax, rsi
0x18003a7f1  jz      short loc_18003A832
0x18003a7f3  lea     rcx, [rsp+248h+var_130]
0x18003a7fb  call    ?_Tidy@?$vector@W4_ActiveProbeType@@V?$allocator@W4_ActiveProbeType@@@std@@@std@@AEAAXXZ; std::vector<_ActiveProbeType>::_Tidy(void)
0x18003a800  mov     rdi, [rsi]
0x18003a803  mov     qword ptr [rsp+248h+var_130], rdi
0x18003a80b  mov     r12, [rsi+8]
0x18003a80f  mov     qword ptr [rsp+248h+var_130+8], r12
0x18003a817  mov     rcx, [rsi+10h]
0x18003a81b  mov     [rsp+248h+var_120], rcx
0x18003a823  xor     eax, eax
0x18003a825  mov     [rsi], rax
0x18003a828  mov     [rsi+8], rax
0x18003a82c  mov     [rsi+10h], rax
0x18003a830  jmp     short loc_18003A842
0x18003a832  mov     r12, qword ptr [rsp+248h+var_130+8]
0x18003a83a  mov     rdi, qword ptr [rsp+248h+var_130]
0x18003a842  lea     rcx, [rsp+248h+var_190]
0x18003a84a  call    ?_Tidy@?$vector@W4_ActiveProbeType@@V?$allocator@W4_ActiveProbeType@@@std@@@std@@AEAAXXZ; std::vector<_ActiveProbeType>::_Tidy(void)
0x18003a84f  mov     ecx, [rbx+0C18h]
0x18003a855  mov     [rsp+248h+var_100], ecx
0x18003a85c  mov     rax, [rbx+0C30h]
0x18003a863  mov     [rsp+248h+var_78], rax
0x18003a86b  mov     eax, [rbx+0C1Ch]
0x18003a871  mov     dword ptr [rsp+248h+var_70+4], eax
0x18003a878  mov     al, [rbx+0C39h]
0x18003a87e  mov     byte ptr [rsp+248h+var_68], al
0x18003a885  test    ecx, ecx
0x18003a887  jz      short loc_18003A8B0
0x18003a889  sub     ecx, 1
0x18003a88c  jz      short loc_18003A8B0
0x18003a88e  sub     ecx, 1
0x18003a891  jz      short loc_18003A8B0
0x18003a893  sub     ecx, 2
0x18003a896  jz      short loc_18003A8B0
0x18003a898  sub     ecx, 2
0x18003a89b  jz      short loc_18003A8B0
0x18003a89d  sub     ecx, 1
0x18003a8a0  jz      short loc_18003A8B0
0x18003a8a2  sub     ecx, 1
0x18003a8a5  jz      short loc_18003A8B0
0x18003a8a7  cmp     ecx, 1
0x18003a8aa  jz      short loc_18003A8B0
0x18003a8ac  xor     al, al
0x18003a8ae  jmp     short loc_18003A8B2
0x18003a8b0  mov     al, 1
0x18003a8b2  mov     [rsp+248h+var_FB], al
0x18003a8b9  cmp     rdi, r12
0x18003a8bc  jz      loc_18003AC30
0x18003a8c2  test    r14b, r14b
0x18003a8c5  jz      loc_18003A988
0x18003a8cb  mov     eax, [rdi]
0x18003a8cd  dec     eax
0x18003a8cf  test    eax, 0FFFFFFFBh
0x18003a8d4  jnz     loc_18003A988
0x18003a8da  mov     eax, cs:dword_18009A080
0x18003a8e0  cmp     eax, 5
0x18003a8e3  jbe     loc_18003AC27
0x18003a8e9  mov     ecx, [rbx+0C1Ch]
0x18003a8ef  call    ?ActiveProbeStageToString@@YAPEBGW4_ActiveProbeStageType@@@Z; ActiveProbeStageToString(_ActiveProbeStageType)
0x18003a8f4  mov     [rsp+248h+lpCriticalSection], rax
0x18003a8fc  mov     ecx, [rdi]
0x18003a8fe  call    ?ActiveProbeTypeToString@@YAPEBGW4_ActiveProbeType@@@Z; ActiveProbeTypeToString(_ActiveProbeType)
0x18003a903  mov     [rsp+248h+var_1D0], rax
0x18003a908  mov     ecx, [rbx+0CA0h]
0x18003a90e  call    ?ToString@@YAPEBDW4_NLA_CONNECTIVITY_FAMILY@@@Z; ToString(_NLA_CONNECTIVITY_FAMILY)
0x18003a913  mov     [rsp+248h+var_1C8], rax
0x18003a91b  mov     rax, [rbx+0C98h]
0x18003a922  mov     [rsp+248h+var_1C0], rax
0x18003a92a  lea     rax, aSkipGlobalRequ; "Skip global request in DS"
0x18003a931  mov     [rsp+248h+var_1B8], rax
0x18003a939  lea     rax, [rsp+248h+lpCriticalSection]
0x18003a941  mov     [rsp+248h+var_208], rax
0x18003a946  lea     rax, [rsp+248h+var_1D0]
0x18003a94b  mov     [rsp+248h+var_210], rax
0x18003a950  lea     rax, [rsp+248h+var_1C8]
0x18003a958  mov     [rsp+248h+var_218], rax
0x18003a95d  lea     rax, [rsp+248h+var_1C0]
0x18003a965  mov     [rsp+248h+var_220], rax
0x18003a96a  lea     rax, [rsp+248h+var_1B8]
0x18003a972  mov     [rsp+248h+var_228], rax
0x18003a977  lea     rdx, byte_18008C867
0x18003a97e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18003a983  jmp     loc_18003AC27
0x18003a988  mov     ecx, 0D8h; Size
0x18003a98d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003a992  mov     [rsp+248h+var_1A0], rax
0x18003a99a  lea     rdx, [rsp+248h+var_118]; struct NcsiActiveProbeDataIn *
0x18003a9a2  mov     rcx, rax; this
0x18003a9a5  call    ??0NcsiActiveProbeDataIn@@QEAA@AEBU0@@Z; NcsiActiveProbeDataIn::NcsiActiveProbeDataIn(NcsiActiveProbeDataIn const &)
0x18003a9aa  nop
0x18003a9ab  mov     [rsp+248h+lpCriticalSection], rax
0x18003a9b3  mov     ecx, [rdi]
0x18003a9b5  mov     [rax+0A8h], ecx
0x18003a9bb  mov     [rax+0B1h], r15b
0x18003a9c2  mov     [rax+0B2h], r14b
0x18003a9c9  mov     rdx, rax; pv
0x18003a9cc  lea     rcx, ?NcsiActiveProbeCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z; pfns
0x18003a9d3  call    ?NcsiThreadPoolTrySubmit@@YAHP6AXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z1@Z; NcsiThreadPoolTrySubmit(void (*)(_TP_CALLBACK_INSTANCE *,void *),void *)
0x18003a9d8  test    eax, eax
0x18003a9da  jnz     loc_18003AB0A
0x18003a9e0  call    cs:__imp_GetLastError
0x18003a9e6  mov     r8d, eax
0x18003a9e9  mov     edx, cs:dword_18009A080
0x18003a9ef  cmp     edx, 5
0x18003a9f2  jbe     loc_18003AAC5
0x18003a9f8  mov     [rsp+248h+var_1D8], r14b
0x18003a9fd  mov     [rsp+248h+var_1D7], r15b
0x18003aa02  mov     ecx, [rbx+0C1Ch]
0x18003aa08  call    ?ActiveProbeStageToString@@YAPEBGW4_ActiveProbeStageType@@@Z; ActiveProbeStageToString(_ActiveProbeStageType)
0x18003aa0d  mov     [rsp+248h+var_1B8], rax
0x18003aa15  mov     ecx, [rdi]
0x18003aa17  call    ?ActiveProbeTypeToString@@YAPEBGW4_ActiveProbeType@@@Z; ActiveProbeTypeToString(_ActiveProbeType)
0x18003aa1c  mov     [rsp+248h+var_1C0], rax
0x18003aa24  mov     dword ptr [rsp+248h+var_1D0], r8d
0x18003aa29  mov     ecx, [rbx+0CA0h]
0x18003aa2f  call    ?ToString@@YAPEBDW4_NLA_CONNECTIVITY_FAMILY@@@Z; ToString(_NLA_CONNECTIVITY_FAMILY)
0x18003aa34  mov     [rsp+248h+var_1C8], rax
0x18003aa3c  mov     rax, [rbx+0C98h]
0x18003aa43  mov     [rsp+248h+var_1B0], rax
0x18003aa4b  lea     rax, aNcsithreadpool; "NcsiThreadPoolTrySubmit failed"
0x18003aa52  mov     [rsp+248h+var_1A8], rax
0x18003aa5a  lea     rax, [rsp+248h+var_1D8]
0x18003aa5f  mov     [rsp+248h+var_1F0], rax
0x18003aa64  lea     rax, [rsp+248h+var_1D7]
0x18003aa69  mov     [rsp+248h+var_1F8], rax
0x18003aa6e  lea     rax, [rsp+248h+var_1B8]
0x18003aa76  mov     [rsp+248h+var_200], rax
0x18003aa7b  lea     rax, [rsp+248h+var_1C0]
0x18003aa83  mov     [rsp+248h+var_208], rax
0x18003aa88  lea     rax, [rsp+248h+var_1D0]
0x18003aa8d  mov     [rsp+248h+var_210], rax
0x18003aa92  lea     rax, [rsp+248h+var_1C8]
0x18003aa9a  mov     [rsp+248h+var_218], rax
0x18003aa9f  lea     rax, [rsp+248h+var_1B0]
0x18003aaa7  mov     [rsp+248h+var_220], rax
0x18003aaac  lea     rax, [rsp+248h+var_1A8]
0x18003aab4  mov     [rsp+248h+var_228], rax
0x18003aab9  lea     rdx, byte_18008C3CB
0x18003aac0  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U4@U?$_tlgWrapperByVal@$00@@U5@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@6AEBU?$_tlgWrapperByVal@$00@@7@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &)
0x18003aac5  mov     byte ptr [rbx+0C3Ah], 0
0x18003aacc  lea     rcx, [rsp+248h+lpCriticalSection]
0x18003aad4  call    ??1?$unique_ptr@UNcsiActiveProbeDataIn@@U?$default_delete@UNcsiActiveProbeDataIn@@@std@@@std@@QEAA@XZ; std::unique_ptr<NcsiActiveProbeDataIn>::~unique_ptr<NcsiActiveProbeDataIn>(void)
0x18003aad9  nop
0x18003aada  test    rbx, rbx
0x18003aadd  jz      short loc_18003AAE9
0x18003aadf  mov     rcx, rbx; lpCriticalSection
0x18003aae2  call    cs:__imp_LeaveCriticalSection
0x18003aae8  nop
0x18003aae9  lea     rcx, [rsp+248h+var_130]
0x18003aaf1  call    ?_Tidy@?$vector@W4_ActiveProbeType@@V?$allocator@W4_ActiveProbeType@@@std@@@std@@AEAAXXZ; std::vector<_ActiveProbeType>::_Tidy(void)
0x18003aaf6  nop
0x18003aaf7  lea     rcx, [rsp+248h+var_118]; this
0x18003aaff  call    ??1NcsiActiveProbeDataIn@@QEAA@XZ; NcsiActiveProbeDataIn::~NcsiActiveProbeDataIn(void)
0x18003ab04  nop
0x18003ab05  jmp     loc_18003AC5B
0x18003ab0a  or      r13d, 1
0x18003ab0e  mov     [rsp+248h+lpCriticalSection], 0
0x18003ab1a  mov     eax, cs:dword_18009A080
0x18003ab20  cmp     eax, 5
0x18003ab23  jbe     loc_18003AC1A
0x18003ab29  mov     [rsp+248h+var_1D7], r14b
0x18003ab2e  mov     [rsp+248h+var_1D8], r15b
  ... truncated ...
```
