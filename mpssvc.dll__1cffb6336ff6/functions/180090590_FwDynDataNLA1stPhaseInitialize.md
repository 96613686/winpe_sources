# FwDynDataNLA1stPhaseInitialize

- ea: `0x180090590`
- end: `0x180090ad9`
- name: `FwDynDataNLA1stPhaseInitialize`
- size: `1353`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000177c`
- `0x18000af3c`
- `0x180017110`
- `0x18005cf9c`
- `0x18006ffc8`
- `0x1800733bc`
- `0x18008fc50`
- `0x180090590`
- `0x180090ae0`
- `0x180090db4`
- `0x180091750`
- `0x1800c83a0`
- `0x1800cc200`
- `0x1800cc520`
- `0x1800db564`
- `0x1800dc408`
- `0x1800dc6c4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009079f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180090866`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009092c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180090996`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009079f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180090866`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009092c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180090996`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180090782`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180090913`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180090782`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180090913`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x18009084d`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x18009097d`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x18009084d`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x18009097d`
- `fwbase!FwAddrChangeSourceInitialize` at `0x180090a9b`
- `fwbase!FwAddrChangeSourceInitialize` at `0x180090a9b`

## string_xrefs

- `0x180090798`: `CreateEvent`
- `0x180090925`: `CreateEvent`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 FwDynDataNLA1stPhaseInitialize()
{
  void *v0; // rbx
  __int64 v1; // r8
  __int64 v2; // r9
  HANDLE EventW; // rax
  const char *v5; // rdi
  signed int LastError; // eax
  unsigned int v7; // ebx
  __int64 v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // r9
  void *v11; // rbx
  signed int v12; // eax
  int v13; // eax
  HANDLE v14; // rax
  signed int v15; // eax
  signed int v16; // eax
  __int64 v17; // r9
  const mpssvc_exception *v18; // [rsp+30h] [rbp-28h] BYREF
  __int64 v19; // [rsp+60h] [rbp+8h] BYREF
  __int64 v20; // [rsp+68h] [rbp+10h] BYREF

  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 17, WPP_c17a8bb60d3a3c8fffd8e1287cd6d1ad_Traceguids);
  dword_18012F89C = 4;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall>::GetImpl'::`2'::impl) )
  {
    v20 = (__int64)"new CNlmManager";
    v0 = operator new(0x58u);
    v19 = (__int64)v0;
    memset_0(v0, 0, 0x58u);
    qword_18012D138 = (Nlm::CNlmManager *)Nlm::CNlmManager::CNlmManager((Nlm::CNlmManager *)v0);
  }
  else
  {
    try
    {
      v20 = (__int64)"new CNlaManager";
      v11 = operator new(0x60u);
      v19 = (__int64)v11;
      memset_0(v11, 0, 0x60u);
      gFwDynDataNLAComp = (Nla::CNlaManager *)Nla::CNlaManager::CNlaManager((Nla::CNlaManager *)v11);
    }
    catch ( const mpssvc_exception *v18 )
    {
      v17 = *((unsigned int *)v18 + 6);
      LODWORD(v19) = v17;
      if ( (int)v17 < 0 )
      {
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 19, WPP_c17a8bb60d3a3c8fffd8e1287cd6d1ad_Traceguids, v17);
        v7 = v19;
        v5 = (const char *)v20;
        goto LABEL_6;
      }
    }
    catch ( ... )
    {
      LODWORD(v19) = -2147024809;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          20,
          WPP_c17a8bb60d3a3c8fffd8e1287cd6d1ad_Traceguids,
          2147942487LL);
      v7 = v19;
      v5 = (const char *)v20;
      goto LABEL_6;
    }
  }
  memset_0(qword_18012D170, 0, sizeof(qword_18012D170));
  memset_0(qword_18012D880, 0, sizeof(qword_18012D880));
  memset_0(qword_18012D928, 0, sizeof(qword_18012D928));
  xmmword_18012D9A0 = 0;
  xmmword_18012D9B0 = 0;
  xmmword_18012D9C0 = 0;
  qword_18012DA40 = 0;
  qword_18012DA58 = 0;
  qword_18012DA88 = 0;
  dword_18012DA90 = 0;
  qword_18012DAA0 = 0;
  qword_18012DAD0 = 0;
  dword_18012DA48 = 1;
  EventW = CreateEventW(0, 0, 0, 0);
  qword_18012DA58 = EventW;
  if ( !EventW )
  {
    v5 = "CreateEvent";
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    v8 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v9 = 21;
LABEL_21:
      v10 = v7;
LABEL_22:
      WPP_SF_d(*(_QWORD *)(v8 + 16), v9, WPP_c17a8bb60d3a3c8fffd8e1287cd6d1ad_Traceguids, v10);
      goto LABEL_6;
    }
    goto LABEL_6;
  }
  qword_18012DA88 = (HANDLE)RegisterWaitForSingleObjectEx(EventW, FwDynDataAddressUpdate, 0, 0xFFFFFFFFLL, 0);
  if ( qword_18012DA88 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall>::GetImpl'::`2'::impl) )
    {
      v13 = Nlm::CNlmManager::RegisterAddressChangeListener(
              qword_18012D138,
              (struct Nla::_MPSSVC_NLA_COMPLETION *)&dword_18012DA48);
      v7 = v13;
      if ( v13 < 0 )
      {
        v5 = "RegisterAddressChangeListener";
        v8 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_6;
        v9 = 23;
        goto LABEL_34;
      }
    }
    else
    {
      Nla::CNlaManager::RegisterAddressChangeListener(
        gFwDynDataNLAComp,
        (struct Nla::_MPSSVC_NLA_COMPLETION *)&dword_18012DA48);
    }
    dword_18012DA90 = 1;
    v14 = CreateEventW(0, 0, 0, 0);
    qword_18012DAA0 = v14;
    if ( !v14 )
    {
      v5 = "CreateEvent";
      v15 = GetLastError();
      v7 = v15;
      if ( v15 > 0 )
        v7 = (unsigned __int16)v15 | 0x80070000;
      v8 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v9 = 24;
        goto LABEL_21;
      }
      goto LABEL_6;
    }
    qword_18012DAD0 = (HANDLE)RegisterWaitForSingleObjectEx(
                                v14,
                                FwDynDataNetworkStateChangeCallback,
                                0,
                                0xFFFFFFFFLL,
                                0);
    if ( !qword_18012DAD0 )
    {
      v5 = "RegisterWaitForSingleObjectEx";
      v16 = GetLastError();
      v7 = v16;
      if ( v16 > 0 )
        v7 = (unsigned __int16)v16 | 0x80070000;
      v8 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v9 = 25;
        goto LABEL_21;
      }
      goto LABEL_6;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall>::GetImpl'::`2'::impl) )
    {
      v13 = Nlm::CNlmManager::RegisterNetworkStateChangeListener(
              qword_18012D138,
              (struct Nla::_MPSSVC_NLA_COMPLETION *)&dword_18012DA90);
      v7 = v13;
      if ( v13 < 0 )
      {
        v5 = "RegisterNetworkStateChangeListener";
        v8 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_6;
        v9 = 26;
        goto LABEL_34;
      }
    }
    else
    {
      Nla::CNlaManager::RegisterNetworkStateChangeListener(
        gFwDynDataNLAComp,
        (struct Nla::_MPSSVC_NLA_COMPLETION *)&dword_18012DA90);
    }
    v13 = FwDynDataNLSConnectionPointInitialize();
    v7 = v13;
    if ( v13 >= 0 )
    {
      v13 = FwQuarantineMonitorInitialize();
      v7 = v13;
      if ( v13 >= 0 )
      {
        v13 = FwAddrChangeSourceInitialize();
        v7 = v13;
        if ( v13 >= 0 )
        {
          v5 = 0;
          goto LABEL_6;
        }
        v5 = "FwAddrChangeSourceInitialize";
        v8 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_6;
        v9 = 29;
      }
      else
      {
        v5 = "FwQuarantineMonitorInitialize";
        v8 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_6;
        v9 = 28;
      }
    }
    else
    {
      v5 = "FwDynDataNLSConnectionPointInitialize";
      v8 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_6;
      v9 = 27;
    }
LABEL_34:
    v10 = (unsigned int)v13;
    goto LABEL_22;
  }
  v5 = "RegisterWaitForSingleObjectEx";
  v12 = GetLastError();
  v7 = v12;
  if ( v12 > 0 )
    v7 = (unsigned __int16)v12 | 0x80070000;
  v8 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    v9 = 22;
    goto LABEL_21;
  }
LABEL_6:
  if ( (unsigned int)dword_1801263B0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1801263B0, 0x4000000000000LL) )
  {
    LODWORD(v19) = v7;
    v20 = (__int64)v5;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (int)&dword_1801263B0,
      (int)&byte_18010F8C7,
      v1,
      v2,
      (const char **)&v20,
      (__int64)&v19);
  }
  if ( (v7 & 0x80000000) != 0 )
    FwDynDataNLA1stPhaseShutdown();
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 30, WPP_c17a8bb60d3a3c8fffd8e1287cd6d1ad_Traceguids, v7);
  return v7;
}

```

## disassembly

```asm
0x180090590  mov     [rsp+arg_10], rbx
0x180090595  push    rsi
0x180090596  push    rdi
0x180090597  push    r14
0x180090599  sub     rsp, 40h
0x18009059d  lea     rsi, WPP_GLOBAL_Control
0x1800905a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800905ab  cmp     rcx, rsi
0x1800905ae  jz      short loc_1800905CB
0x1800905b0  test    byte ptr [rcx+1Ch], 8
0x1800905b4  jz      short loc_1800905CB
0x1800905b6  mov     edx, 11h
0x1800905bb  lea     r8, WPP_c17a8bb60d3a3c8fffd8e1287cd6d1ad_Traceguids
0x1800905c2  mov     rcx, [rcx+10h]
0x1800905c6  call    WPP_SF_
0x1800905cb  mov     cs:dword_18012F89C, 4
0x1800905d5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall> `wil::Feature<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall>::GetImpl(void)'::`2'::impl
0x1800905dc  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall>::__private_IsEnabled(void)
0x1800905e1  test    al, al
0x1800905e3  jz      loc_1800907EB
0x1800905e9  lea     rax, aNewCnlmmanager; "new CNlmManager"
0x1800905f0  mov     [rsp+58h+arg_8], rax
0x1800905f5  mov     edi, 58h ; 'X'
0x1800905fa  mov     ecx, edi; Size
0x1800905fc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180090601  mov     rbx, rax
0x180090604  mov     [rsp+58h+arg_0], rax
0x180090609  mov     r8d, edi; Size
0x18009060c  xor     edx, edx; Val
0x18009060e  mov     rcx, rax; void *
0x180090611  call    memset_0
0x180090616  mov     rcx, rbx; this
0x180090619  call    ??0CNlmManager@Nlm@@QEAA@XZ; Nlm::CNlmManager::CNlmManager(void)
0x18009061e  nop
0x18009061f  mov     cs:qword_18012D138, rax
0x180090626  jmp     loc_180090828
0x18009062b  lea     rsi, WPP_GLOBAL_Control
0x180090632  mov     ebx, dword ptr [rsp+58h+arg_0]
0x180090636  mov     rdi, [rsp+58h+arg_8]
0x18009063b  mov     eax, cs:dword_1801263B0
0x180090641  cmp     eax, 4
0x180090644  jbe     short loc_180090690
0x180090646  mov     rdx, 4000000000000h
0x180090650  lea     rcx, dword_1801263B0
0x180090657  call    _tlgKeywordOn
0x18009065c  test    al, al
0x18009065e  jz      short loc_180090690
0x180090660  mov     dword ptr [rsp+58h+arg_0], ebx
0x180090664  mov     [rsp+58h+arg_8], rdi
0x180090669  lea     rax, [rsp+58h+arg_0]
0x18009066e  mov     [rsp+58h+var_30], rax; __int64
0x180090673  lea     rax, [rsp+58h+arg_8]
0x180090678  mov     [rsp+58h+var_38], rax; __int64
0x18009067d  lea     rdx, byte_18010F8C7
0x180090684  lea     rcx, dword_1801263B0; int
0x18009068b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180090690  test    ebx, ebx
0x180090692  jns     short loc_180090699
0x180090694  call    FwDynDataNLA1stPhaseShutdown
0x180090699  mov     rcx, cs:WPP_GLOBAL_Control
0x1800906a0  cmp     rcx, rsi
0x1800906a3  jz      short loc_1800906C3
0x1800906a5  test    byte ptr [rcx+1Ch], 8
0x1800906a9  jz      short loc_1800906C3
0x1800906ab  mov     edx, 1Eh
0x1800906b0  mov     r9d, ebx
0x1800906b3  lea     r8, WPP_c17a8bb60d3a3c8fffd8e1287cd6d1ad_Traceguids
0x1800906ba  mov     rcx, [rcx+10h]
0x1800906be  call    WPP_SF_d
0x1800906c3  mov     eax, ebx
0x1800906c5  mov     rbx, [rsp+58h+arg_10]
0x1800906ca  add     rsp, 40h
0x1800906ce  pop     r14
0x1800906d0  pop     rdi
0x1800906d1  pop     rsi
0x1800906d2  retn
0x1800906d3  lea     rsi, WPP_GLOBAL_Control
0x1800906da  xor     edx, edx; Val
0x1800906dc  mov     r8d, 6E0h; Size
0x1800906e2  lea     rcx, qword_18012D170; void *
0x1800906e9  call    memset_0
0x1800906ee  xor     edx, edx; Val
0x1800906f0  lea     r8d, [rdx+78h]; Size
0x1800906f4  lea     rcx, qword_18012D880; void *
0x1800906fb  call    memset_0
0x180090700  xor     edx, edx; Val
0x180090702  lea     r8d, [rdx+48h]; Size
0x180090706  lea     rcx, qword_18012D928; void *
0x18009070d  call    memset_0
0x180090712  xorps   xmm0, xmm0
0x180090715  movups  cs:xmmword_18012D9A0, xmm0
0x18009071c  movups  cs:xmmword_18012D9B0, xmm0
0x180090723  movups  cs:xmmword_18012D9C0, xmm0
0x18009072a  mov     cs:qword_18012DA40, 0
0x180090735  mov     cs:qword_18012DA58, 0
0x180090740  mov     cs:qword_18012DA88, 0
0x18009074b  mov     cs:dword_18012DA90, 0
0x180090755  mov     cs:qword_18012DAA0, 0
0x180090760  mov     cs:qword_18012DAD0, 0
0x18009076b  mov     r14d, 1
0x180090771  mov     cs:dword_18012DA48, r14d
0x180090778  xor     r9d, r9d; lpName
0x18009077b  xor     r8d, r8d; bInitialState
0x18009077e  xor     edx, edx; bManualReset
0x180090780  xor     ecx, ecx; lpEventAttributes
0x180090782  call    cs:__imp_CreateEventW
0x180090788  mov     cs:qword_18012DA58, rax
0x18009078f  test    rax, rax
0x180090792  jnz     loc_180090832
0x180090798  lea     rdi, aCreateevent; "CreateEvent"
0x18009079f  call    cs:__imp_GetLastError
0x1800907a5  mov     ebx, eax
0x1800907a7  test    eax, eax
0x1800907a9  jle     short loc_1800907B4
0x1800907ab  movzx   ebx, ax
0x1800907ae  or      ebx, 80070000h
0x1800907b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800907bb  cmp     rcx, rsi
0x1800907be  jz      loc_18009063B
0x1800907c4  test    [rcx+1Ch], r14b
0x1800907c8  jz      loc_18009063B
0x1800907ce  mov     edx, 15h
0x1800907d3  mov     r9d, ebx
0x1800907d6  lea     r8, WPP_c17a8bb60d3a3c8fffd8e1287cd6d1ad_Traceguids
0x1800907dd  mov     rcx, [rcx+10h]
0x1800907e1  call    WPP_SF_d
0x1800907e6  jmp     loc_18009063B
0x1800907eb  lea     rax, aNewCnlamanager; "new CNlaManager"
0x1800907f2  mov     [rsp+58h+arg_8], rax
0x1800907f7  mov     edi, 60h ; '`'
0x1800907fc  mov     ecx, edi; Size
0x1800907fe  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180090803  mov     rbx, rax
0x180090806  mov     [rsp+58h+arg_0], rax
0x18009080b  mov     r8d, edi; Size
0x18009080e  xor     edx, edx; Val
0x180090810  mov     rcx, rax; void *
0x180090813  call    memset_0
0x180090818  mov     rcx, rbx; this
0x18009081b  call    ??0CNlaManager@Nla@@QEAA@XZ; Nla::CNlaManager::CNlaManager(void)
0x180090820  nop
0x180090821  mov     cs:?gFwDynDataNLAComp@@3U_tagFWDYNDATANLACOMP@@A, rax; _tagFWDYNDATANLACOMP gFwDynDataNLAComp
0x180090828  jmp     loc_1800906DA
0x18009082d  jmp     loc_18009062B
0x180090832  mov     dword ptr [rsp+58h+var_38], 0
0x18009083a  or      edi, 0FFFFFFFFh
0x18009083d  mov     r9d, edi
0x180090840  xor     r8d, r8d
0x180090843  lea     rdx, FwDynDataAddressUpdate
0x18009084a  mov     rcx, rax
0x18009084d  call    cs:__imp_RegisterWaitForSingleObjectEx
0x180090853  mov     cs:qword_18012DA88, rax
0x18009085a  test    rax, rax
0x18009085d  jnz     short loc_18009089F
0x18009085f  lea     rdi, aRegisterwaitfo; "RegisterWaitForSingleObjectEx"
0x180090866  call    cs:__imp_GetLastError
0x18009086c  mov     ebx, eax
0x18009086e  test    eax, eax
0x180090870  jle     short loc_18009087B
0x180090872  movzx   ebx, ax
0x180090875  or      ebx, 80070000h
0x18009087b  mov     rcx, cs:WPP_GLOBAL_Control
0x180090882  cmp     rcx, rsi
0x180090885  jz      loc_18009063B
0x18009088b  test    [rcx+1Ch], r14b
0x18009088f  jz      loc_18009063B
0x180090895  mov     edx, 16h
0x18009089a  jmp     loc_1800907D3
0x18009089f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall> `wil::Feature<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall>::GetImpl(void)'::`2'::impl
0x1800908a6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall>::__private_IsEnabled(void)
0x1800908ab  lea     rdx, dword_18012DA48; struct Nla::_MPSSVC_NLA_COMPLETION *
0x1800908b2  test    al, al
0x1800908b4  jz      short loc_1800908F6
0x1800908b6  mov     rcx, cs:qword_18012D138; this
0x1800908bd  call    ?RegisterAddressChangeListener@CNlmManager@Nlm@@QEAAJPEAU_MPSSVC_NLA_COMPLETION@Nla@@@Z; Nlm::CNlmManager::RegisterAddressChangeListener(Nla::_MPSSVC_NLA_COMPLETION *)
0x1800908c2  mov     ebx, eax
0x1800908c4  test    eax, eax
0x1800908c6  jns     short loc_180090902
0x1800908c8  lea     rdi, aRegisteraddres; "RegisterAddressChangeListener"
0x1800908cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800908d6  cmp     rcx, rsi
0x1800908d9  jz      loc_18009063B
0x1800908df  test    [rcx+1Ch], r14b
0x1800908e3  jz      loc_18009063B
0x1800908e9  mov     edx, 17h
0x1800908ee  mov     r9d, eax
0x1800908f1  jmp     loc_1800907D6
0x1800908f6  mov     rcx, cs:?gFwDynDataNLAComp@@3U_tagFWDYNDATANLACOMP@@A; this
0x1800908fd  call    ?RegisterAddressChangeListener@CNlaManager@Nla@@QEAAXPEAU_MPSSVC_NLA_COMPLETION@2@@Z; Nla::CNlaManager::RegisterAddressChangeListener(Nla::_MPSSVC_NLA_COMPLETION *)
0x180090902  mov     cs:dword_18012DA90, r14d
0x180090909  xor     r9d, r9d; lpName
0x18009090c  xor     r8d, r8d; bInitialState
0x18009090f  xor     edx, edx; bManualReset
0x180090911  xor     ecx, ecx; lpEventAttributes
0x180090913  call    cs:__imp_CreateEventW
0x180090919  mov     cs:qword_18012DAA0, rax
0x180090920  test    rax, rax
0x180090923  jnz     short loc_180090965
0x180090925  lea     rdi, aCreateevent; "CreateEvent"
0x18009092c  call    cs:__imp_GetLastError
0x180090932  mov     ebx, eax
0x180090934  test    eax, eax
0x180090936  jle     short loc_180090941
0x180090938  movzx   ebx, ax
0x18009093b  or      ebx, 80070000h
0x180090941  mov     rcx, cs:WPP_GLOBAL_Control
0x180090948  cmp     rcx, rsi
0x18009094b  jz      loc_18009063B
0x180090951  test    [rcx+1Ch], r14b
0x180090955  jz      loc_18009063B
0x18009095b  mov     edx, 18h
0x180090960  jmp     loc_1800907D3
0x180090965  mov     dword ptr [rsp+58h+var_38], 0
0x18009096d  mov     r9d, edi
0x180090970  xor     r8d, r8d
0x180090973  lea     rdx, FwDynDataNetworkStateChangeCallback
0x18009097a  mov     rcx, rax
0x18009097d  call    cs:__imp_RegisterWaitForSingleObjectEx
0x180090983  mov     cs:qword_18012DAD0, rax
0x18009098a  test    rax, rax
0x18009098d  jnz     short loc_1800909CF
0x18009098f  lea     rdi, aRegisterwaitfo; "RegisterWaitForSingleObjectEx"
0x180090996  call    cs:__imp_GetLastError
0x18009099c  mov     ebx, eax
0x18009099e  test    eax, eax
0x1800909a0  jle     short loc_1800909AB
0x1800909a2  movzx   ebx, ax
0x1800909a5  or      ebx, 80070000h
0x1800909ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800909b2  cmp     rcx, rsi
0x1800909b5  jz      loc_18009063B
0x1800909bb  test    [rcx+1Ch], r14b
0x1800909bf  jz      loc_18009063B
0x1800909c5  mov     edx, 19h
0x1800909ca  jmp     loc_1800907D3
0x1800909cf  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall> `wil::Feature<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall>::GetImpl(void)'::`2'::impl
0x1800909d6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall>::__private_IsEnabled(void)
0x1800909db  lea     rdx, dword_18012DA90; struct Nla::_MPSSVC_NLA_COMPLETION *
0x1800909e2  test    al, al
0x1800909e4  jz      short loc_180090A23
0x1800909e6  mov     rcx, cs:qword_18012D138; this
0x1800909ed  call    ?RegisterNetworkStateChangeListener@CNlmManager@Nlm@@QEAAJPEAU_MPSSVC_NLA_COMPLETION@Nla@@@Z; Nlm::CNlmManager::RegisterNetworkStateChangeListener(Nla::_MPSSVC_NLA_COMPLETION *)
0x1800909f2  mov     ebx, eax
0x1800909f4  test    eax, eax
0x1800909f6  jns     short loc_180090A2F
0x1800909f8  lea     rdi, aRegisternetwor; "RegisterNetworkStateChangeListener"
0x1800909ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180090a06  cmp     rcx, rsi
0x180090a09  jz      loc_18009063B
0x180090a0f  test    [rcx+1Ch], r14b
0x180090a13  jz      loc_18009063B
0x180090a19  mov     edx, 1Ah
0x180090a1e  jmp     loc_1800908EE
0x180090a23  mov     rcx, cs:?gFwDynDataNLAComp@@3U_tagFWDYNDATANLACOMP@@A; this
0x180090a2a  call    ?RegisterNetworkStateChangeListener@CNlaManager@Nla@@QEAAXPEAU_MPSSVC_NLA_COMPLETION@2@@Z; Nla::CNlaManager::RegisterNetworkStateChangeListener(Nla::_MPSSVC_NLA_COMPLETION *)
0x180090a2f  call    FwDynDataNLSConnectionPointInitialize
0x180090a34  mov     ebx, eax
0x180090a36  test    eax, eax
0x180090a38  jns     short loc_180090A65
0x180090a3a  lea     rdi, aFwdyndatanlsco_0; "FwDynDataNLSConnectionPointInitialize"
0x180090a41  mov     rcx, cs:WPP_GLOBAL_Control
0x180090a48  cmp     rcx, rsi
0x180090a4b  jz      loc_18009063B
0x180090a51  test    [rcx+1Ch], r14b
0x180090a55  jz      loc_18009063B
0x180090a5b  mov     edx, 1Bh
0x180090a60  jmp     loc_1800908EE
0x180090a65  call    FwQuarantineMonitorInitialize
0x180090a6a  mov     ebx, eax
0x180090a6c  test    eax, eax
0x180090a6e  jns     short loc_180090A9B
0x180090a70  lea     rdi, aFwquarantinemo; "FwQuarantineMonitorInitialize"
0x180090a77  mov     rcx, cs:WPP_GLOBAL_Control
0x180090a7e  cmp     rcx, rsi
0x180090a81  jz      loc_18009063B
0x180090a87  test    [rcx+1Ch], r14b
0x180090a8b  jz      loc_18009063B
0x180090a91  mov     edx, 1Ch
0x180090a96  jmp     loc_1800908EE
0x180090a9b  call    cs:__imp_FwAddrChangeSourceInitialize
0x180090aa1  mov     ebx, eax
0x180090aa3  test    eax, eax
0x180090aa5  jns     short loc_180090AD2
0x180090aa7  lea     rdi, aFwaddrchangeso_2; "FwAddrChangeSourceInitialize"
0x180090aae  mov     rcx, cs:WPP_GLOBAL_Control
0x180090ab5  cmp     rcx, rsi
0x180090ab8  jz      loc_18009063B
0x180090abe  test    [rcx+1Ch], r14b
0x180090ac2  jz      loc_18009063B
0x180090ac8  mov     edx, 1Dh
0x180090acd  jmp     loc_1800908EE
0x180090ad2  xor     edi, edi
0x180090ad4  jmp     loc_18009063B
```
