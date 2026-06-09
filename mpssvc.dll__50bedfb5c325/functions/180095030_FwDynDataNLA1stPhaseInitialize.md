# FwDynDataNLA1stPhaseInitialize

- ea: `0x180095030`
- end: `0x1800955b0`
- name: `FwDynDataNLA1stPhaseInitialize`
- size: `1408`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180001784`
- `0x18000a710`
- `0x1800192e0`
- `0x180061c90`
- `0x180073488`
- `0x18007687c`
- `0x180094610`
- `0x180095030`
- `0x1800955c0`
- `0x1800958b8`
- `0x180096338`
- `0x1800cf990`
- `0x1800d3910`
- `0x1800d3c70`
- `0x1800e1510`
- `0x1800e2414`
- `0x1800e271c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095246`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095319`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800953eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095461`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095246`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095319`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800953eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095461`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180095223`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800953cc`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180095223`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800953cc`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x1800952fa`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x180095442`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x1800952fa`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x180095442`
- `fwbase!FwAddrChangeSourceInitialize` at `0x18009556c`
- `fwbase!FwAddrChangeSourceInitialize` at `0x18009556c`

## string_xrefs

- `0x18009523f`: `CreateEvent`
- `0x1800953e4`: `CreateEvent`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 FwDynDataNLA1stPhaseInitialize()
{
  void *v0; // rbx
  HANDLE EventW; // rax
  const char *v3; // rdi
  signed int LastError; // eax
  unsigned int v5; // ebx
  __int64 v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r9
  void *v9; // rbx
  signed int v10; // eax
  int v11; // eax
  HANDLE v12; // rax
  signed int v13; // eax
  signed int v14; // eax
  __int64 v15; // r9
  const mpssvc_exception *v16; // [rsp+30h] [rbp-28h] BYREF
  __int64 v17; // [rsp+60h] [rbp+8h] BYREF
  __int64 v18; // [rsp+68h] [rbp+10h] BYREF

  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 17, WPP_0043c1167b9d39bdb1a15ac1c4aee9c9_Traceguids);
  dword_180135A5C = 4;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall>::GetImpl'::`2'::impl) )
  {
    v18 = (__int64)"new CNlmManager";
    v0 = operator new(0x58u);
    v17 = (__int64)v0;
    memset_0(v0, 0, 0x58u);
    qword_180133308 = (Nlm::CNlmManager *)Nlm::CNlmManager::CNlmManager((Nlm::CNlmManager *)v0);
  }
  else
  {
    try
    {
      v18 = (__int64)"new CNlaManager";
      v9 = operator new(0x60u);
      v17 = (__int64)v9;
      memset_0(v9, 0, 0x60u);
      gFwDynDataNLAComp = (Nla::CNlaManager *)Nla::CNlaManager::CNlaManager((Nla::CNlaManager *)v9);
    }
    catch ( const mpssvc_exception *v16 )
    {
      v15 = *((unsigned int *)v16 + 6);
      LODWORD(v17) = v15;
      if ( (int)v15 < 0 )
      {
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 19, WPP_0043c1167b9d39bdb1a15ac1c4aee9c9_Traceguids, v15);
        v5 = v17;
        v3 = (const char *)v18;
        goto LABEL_6;
      }
    }
    catch ( ... )
    {
      LODWORD(v17) = -2147024809;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          20,
          WPP_0043c1167b9d39bdb1a15ac1c4aee9c9_Traceguids,
          2147942487LL);
      v5 = v17;
      v3 = (const char *)v18;
      goto LABEL_6;
    }
  }
  memset_0(qword_180133340, 0, sizeof(qword_180133340));
  memset_0(qword_180133A50, 0, sizeof(qword_180133A50));
  memset_0(qword_180133AF8, 0, sizeof(qword_180133AF8));
  xmmword_180133B70 = 0;
  xmmword_180133B80 = 0;
  xmmword_180133B90 = 0;
  qword_180133C10 = 0;
  qword_180133C28 = 0;
  qword_180133C58 = 0;
  dword_180133C60 = 0;
  qword_180133C70 = 0;
  qword_180133CA0 = 0;
  dword_180133C18 = 1;
  EventW = CreateEventW(0, 0, 0, 0);
  qword_180133C28 = EventW;
  if ( !EventW )
  {
    v3 = "CreateEvent";
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    v6 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v7 = 21;
LABEL_21:
      v8 = v5;
LABEL_22:
      WPP_SF_d(*(_QWORD *)(v6 + 16), v7, WPP_0043c1167b9d39bdb1a15ac1c4aee9c9_Traceguids, v8);
      goto LABEL_6;
    }
    goto LABEL_6;
  }
  qword_180133C58 = (HANDLE)RegisterWaitForSingleObjectEx(EventW, FwDynDataAddressUpdate, 0, 0xFFFFFFFFLL, 0);
  if ( qword_180133C58 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall>::GetImpl'::`2'::impl) )
    {
      v11 = Nlm::CNlmManager::RegisterAddressChangeListener(
              qword_180133308,
              (struct Nla::_MPSSVC_NLA_COMPLETION *)&dword_180133C18);
      v5 = v11;
      if ( v11 < 0 )
      {
        v3 = "RegisterAddressChangeListener";
        v6 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_6;
        v7 = 23;
        goto LABEL_34;
      }
    }
    else
    {
      Nla::CNlaManager::RegisterAddressChangeListener(
        gFwDynDataNLAComp,
        (struct Nla::_MPSSVC_NLA_COMPLETION *)&dword_180133C18);
    }
    dword_180133C60 = 1;
    v12 = CreateEventW(0, 0, 0, 0);
    qword_180133C70 = v12;
    if ( !v12 )
    {
      v3 = "CreateEvent";
      v13 = GetLastError();
      v5 = v13;
      if ( v13 > 0 )
        v5 = (unsigned __int16)v13 | 0x80070000;
      v6 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v7 = 24;
        goto LABEL_21;
      }
      goto LABEL_6;
    }
    qword_180133CA0 = (HANDLE)RegisterWaitForSingleObjectEx(
                                v12,
                                FwDynDataNetworkStateChangeCallback,
                                0,
                                0xFFFFFFFFLL,
                                0);
    if ( !qword_180133CA0 )
    {
      v3 = "RegisterWaitForSingleObjectEx";
      v14 = GetLastError();
      v5 = v14;
      if ( v14 > 0 )
        v5 = (unsigned __int16)v14 | 0x80070000;
      v6 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v7 = 25;
        goto LABEL_21;
      }
      goto LABEL_6;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall>::GetImpl'::`2'::impl) )
    {
      v11 = Nlm::CNlmManager::RegisterNetworkStateChangeListener(
              qword_180133308,
              (struct Nla::_MPSSVC_NLA_COMPLETION *)&dword_180133C60);
      v5 = v11;
      if ( v11 < 0 )
      {
        v3 = "RegisterNetworkStateChangeListener";
        v6 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_6;
        v7 = 26;
        goto LABEL_34;
      }
    }
    else
    {
      Nla::CNlaManager::RegisterNetworkStateChangeListener(
        gFwDynDataNLAComp,
        (struct Nla::_MPSSVC_NLA_COMPLETION *)&dword_180133C60);
    }
    v11 = FwDynDataNLSConnectionPointInitialize();
    v5 = v11;
    if ( v11 >= 0 )
    {
      v11 = FwQuarantineMonitorInitialize();
      v5 = v11;
      if ( v11 >= 0 )
      {
        v11 = FwAddrChangeSourceInitialize();
        v5 = v11;
        if ( v11 >= 0 )
        {
          v3 = 0;
          goto LABEL_6;
        }
        v3 = "FwAddrChangeSourceInitialize";
        v6 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_6;
        v7 = 29;
      }
      else
      {
        v3 = "FwQuarantineMonitorInitialize";
        v6 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_6;
        v7 = 28;
      }
    }
    else
    {
      v3 = "FwDynDataNLSConnectionPointInitialize";
      v6 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_6;
      v7 = 27;
    }
LABEL_34:
    v8 = (unsigned int)v11;
    goto LABEL_22;
  }
  v3 = "RegisterWaitForSingleObjectEx";
  v10 = GetLastError();
  v5 = v10;
  if ( v10 > 0 )
    v5 = (unsigned __int16)v10 | 0x80070000;
  v6 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    v7 = 22;
    goto LABEL_21;
  }
LABEL_6:
  if ( (unsigned int)dword_18012C3B0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18012C3B0, 0x4000000000000LL) )
  {
    LODWORD(v17) = v5;
    v18 = (__int64)v3;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (int)&dword_18012C3B0,
      (__int64)&v18,
      (__int64)&v17);
  }
  if ( (v5 & 0x80000000) != 0 )
    FwDynDataNLA1stPhaseShutdown();
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 30, WPP_0043c1167b9d39bdb1a15ac1c4aee9c9_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x180095030  mov     [rsp+arg_10], rbx
0x180095035  push    rsi
0x180095036  push    rdi
0x180095037  push    r14
0x180095039  sub     rsp, 40h
0x18009503d  lea     rsi, WPP_GLOBAL_Control
0x180095044  mov     rcx, cs:WPP_GLOBAL_Control
0x18009504b  cmp     rcx, rsi
0x18009504e  jz      short loc_18009506B
0x180095050  test    byte ptr [rcx+1Ch], 8
0x180095054  jz      short loc_18009506B
0x180095056  mov     edx, 11h
0x18009505b  lea     r8, WPP_0043c1167b9d39bdb1a15ac1c4aee9c9_Traceguids
0x180095062  mov     rcx, [rcx+10h]
0x180095066  call    WPP_SF_
0x18009506b  mov     cs:dword_180135A5C, 4
0x180095075  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall> `wil::Feature<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall>::GetImpl(void)'::`2'::impl
0x18009507c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall>::__private_IsEnabled(void)
0x180095081  test    al, al
0x180095083  jz      loc_180095298
0x180095089  lea     rax, aNewCnlmmanager; "new CNlmManager"
0x180095090  mov     [rsp+58h+arg_8], rax
0x180095095  mov     edi, 58h ; 'X'
0x18009509a  mov     ecx, edi; Size
0x18009509c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800950a1  mov     rbx, rax
0x1800950a4  mov     [rsp+58h+arg_0], rax
0x1800950a9  mov     r8d, edi; Size
0x1800950ac  xor     edx, edx; Val
0x1800950ae  mov     rcx, rax; void *
0x1800950b1  call    memset_0
0x1800950b6  mov     rcx, rbx; this
0x1800950b9  call    ??0CNlmManager@Nlm@@QEAA@XZ; Nlm::CNlmManager::CNlmManager(void)
0x1800950be  nop
0x1800950bf  mov     cs:qword_180133308, rax
0x1800950c6  jmp     loc_1800952D5
0x1800950cb  lea     rsi, WPP_GLOBAL_Control
0x1800950d2  mov     ebx, dword ptr [rsp+58h+arg_0]
0x1800950d6  mov     rdi, [rsp+58h+arg_8]
0x1800950db  mov     eax, cs:dword_18012C3B0
0x1800950e1  cmp     eax, 4
0x1800950e4  jbe     short loc_180095130
0x1800950e6  mov     rdx, 4000000000000h
0x1800950f0  lea     rcx, dword_18012C3B0
0x1800950f7  call    _tlgKeywordOn
0x1800950fc  test    al, al
0x1800950fe  jz      short loc_180095130
0x180095100  mov     dword ptr [rsp+58h+arg_0], ebx
0x180095104  mov     [rsp+58h+arg_8], rdi
0x180095109  lea     rax, [rsp+58h+arg_0]
0x18009510e  mov     [rsp+58h+var_30], rax; __int64
0x180095113  lea     rax, [rsp+58h+arg_8]
0x180095118  mov     [rsp+58h+var_38], rax; __int64
0x18009511d  lea     rdx, word_180115762
0x180095124  lea     rcx, dword_18012C3B0; int
0x18009512b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180095130  test    ebx, ebx
0x180095132  jns     short loc_180095139
0x180095134  call    FwDynDataNLA1stPhaseShutdown
0x180095139  mov     rcx, cs:WPP_GLOBAL_Control
0x180095140  cmp     rcx, rsi
0x180095143  jz      short loc_180095163
0x180095145  test    byte ptr [rcx+1Ch], 8
0x180095149  jz      short loc_180095163
0x18009514b  mov     edx, 1Eh
0x180095150  mov     r9d, ebx
0x180095153  lea     r8, WPP_0043c1167b9d39bdb1a15ac1c4aee9c9_Traceguids
0x18009515a  mov     rcx, [rcx+10h]
0x18009515e  call    WPP_SF_d
0x180095163  mov     eax, ebx
0x180095165  mov     rbx, [rsp+58h+arg_10]
0x18009516a  add     rsp, 40h
0x18009516e  pop     r14
0x180095170  pop     rdi
0x180095171  pop     rsi
0x180095172  retn
0x180095174  lea     rsi, WPP_GLOBAL_Control
0x18009517b  xor     edx, edx; Val
0x18009517d  mov     r8d, 6E0h; Size
0x180095183  lea     rcx, qword_180133340; void *
0x18009518a  call    memset_0
0x18009518f  xor     edx, edx; Val
0x180095191  lea     r8d, [rdx+78h]; Size
0x180095195  lea     rcx, qword_180133A50; void *
0x18009519c  call    memset_0
0x1800951a1  xor     edx, edx; Val
0x1800951a3  lea     r8d, [rdx+48h]; Size
0x1800951a7  lea     rcx, qword_180133AF8; void *
0x1800951ae  call    memset_0
0x1800951b3  xorps   xmm0, xmm0
0x1800951b6  movups  cs:xmmword_180133B70, xmm0
0x1800951bd  movups  cs:xmmword_180133B80, xmm0
0x1800951c4  movups  cs:xmmword_180133B90, xmm0
0x1800951cb  mov     cs:qword_180133C10, 0
0x1800951d6  mov     cs:qword_180133C28, 0
0x1800951e1  mov     cs:qword_180133C58, 0
0x1800951ec  mov     cs:dword_180133C60, 0
0x1800951f6  mov     cs:qword_180133C70, 0
0x180095201  mov     cs:qword_180133CA0, 0
0x18009520c  mov     r14d, 1
0x180095212  mov     cs:dword_180133C18, r14d
0x180095219  xor     r9d, r9d; lpName
0x18009521c  xor     r8d, r8d; bInitialState
0x18009521f  xor     edx, edx; bManualReset
0x180095221  xor     ecx, ecx; lpEventAttributes
0x180095223  call    cs:__imp_CreateEventW
0x18009522a  nop     dword ptr [rax+rax+00h]
0x18009522f  mov     cs:qword_180133C28, rax
0x180095236  test    rax, rax
0x180095239  jnz     loc_1800952DF
0x18009523f  lea     rdi, aCreateevent; "CreateEvent"
0x180095246  call    cs:__imp_GetLastError
0x18009524d  nop     dword ptr [rax+rax+00h]
0x180095252  mov     ebx, eax
0x180095254  test    eax, eax
0x180095256  jle     short loc_180095261
0x180095258  movzx   ebx, ax
0x18009525b  or      ebx, 80070000h
0x180095261  mov     rcx, cs:WPP_GLOBAL_Control
0x180095268  cmp     rcx, rsi
0x18009526b  jz      loc_1800950DB
0x180095271  test    [rcx+1Ch], r14b
0x180095275  jz      loc_1800950DB
0x18009527b  mov     edx, 15h
0x180095280  mov     r9d, ebx
0x180095283  lea     r8, WPP_0043c1167b9d39bdb1a15ac1c4aee9c9_Traceguids
0x18009528a  mov     rcx, [rcx+10h]
0x18009528e  call    WPP_SF_d
0x180095293  jmp     loc_1800950DB
0x180095298  lea     rax, aNewCnlamanager; "new CNlaManager"
0x18009529f  mov     [rsp+58h+arg_8], rax
0x1800952a4  mov     edi, 60h ; '`'
0x1800952a9  mov     ecx, edi; Size
0x1800952ab  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800952b0  mov     rbx, rax
0x1800952b3  mov     [rsp+58h+arg_0], rax
0x1800952b8  mov     r8d, edi; Size
0x1800952bb  xor     edx, edx; Val
0x1800952bd  mov     rcx, rax; void *
0x1800952c0  call    memset_0
0x1800952c5  mov     rcx, rbx; this
0x1800952c8  call    ??0CNlaManager@Nla@@QEAA@XZ; Nla::CNlaManager::CNlaManager(void)
0x1800952cd  nop
0x1800952ce  mov     cs:?gFwDynDataNLAComp@@3U_tagFWDYNDATANLACOMP@@A, rax; _tagFWDYNDATANLACOMP gFwDynDataNLAComp
0x1800952d5  jmp     loc_18009517B
0x1800952da  jmp     loc_1800950CB
0x1800952df  mov     dword ptr [rsp+58h+var_38], 0
0x1800952e7  or      edi, 0FFFFFFFFh
0x1800952ea  mov     r9d, edi
0x1800952ed  xor     r8d, r8d
0x1800952f0  lea     rdx, FwDynDataAddressUpdate
0x1800952f7  mov     rcx, rax
0x1800952fa  call    cs:__imp_RegisterWaitForSingleObjectEx
0x180095301  nop     dword ptr [rax+rax+00h]
0x180095306  mov     cs:qword_180133C58, rax
0x18009530d  test    rax, rax
0x180095310  jnz     short loc_180095358
0x180095312  lea     rdi, aRegisterwaitfo; "RegisterWaitForSingleObjectEx"
0x180095319  call    cs:__imp_GetLastError
0x180095320  nop     dword ptr [rax+rax+00h]
0x180095325  mov     ebx, eax
0x180095327  test    eax, eax
0x180095329  jle     short loc_180095334
0x18009532b  movzx   ebx, ax
0x18009532e  or      ebx, 80070000h
0x180095334  mov     rcx, cs:WPP_GLOBAL_Control
0x18009533b  cmp     rcx, rsi
0x18009533e  jz      loc_1800950DB
0x180095344  test    [rcx+1Ch], r14b
0x180095348  jz      loc_1800950DB
0x18009534e  mov     edx, 16h
0x180095353  jmp     loc_180095280
0x180095358  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall> `wil::Feature<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall>::GetImpl(void)'::`2'::impl
0x18009535f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall>::__private_IsEnabled(void)
0x180095364  lea     rdx, dword_180133C18; struct Nla::_MPSSVC_NLA_COMPLETION *
0x18009536b  test    al, al
0x18009536d  jz      short loc_1800953AF
0x18009536f  mov     rcx, cs:qword_180133308; this
0x180095376  call    ?RegisterAddressChangeListener@CNlmManager@Nlm@@QEAAJPEAU_MPSSVC_NLA_COMPLETION@Nla@@@Z; Nlm::CNlmManager::RegisterAddressChangeListener(Nla::_MPSSVC_NLA_COMPLETION *)
0x18009537b  mov     ebx, eax
0x18009537d  test    eax, eax
0x18009537f  jns     short loc_1800953BB
0x180095381  lea     rdi, aRegisteraddres; "RegisterAddressChangeListener"
0x180095388  mov     rcx, cs:WPP_GLOBAL_Control
0x18009538f  cmp     rcx, rsi
0x180095392  jz      loc_1800950DB
0x180095398  test    [rcx+1Ch], r14b
0x18009539c  jz      loc_1800950DB
0x1800953a2  mov     edx, 17h
0x1800953a7  mov     r9d, eax
0x1800953aa  jmp     loc_180095283
0x1800953af  mov     rcx, cs:?gFwDynDataNLAComp@@3U_tagFWDYNDATANLACOMP@@A; this
0x1800953b6  call    ?RegisterAddressChangeListener@CNlaManager@Nla@@QEAAXPEAU_MPSSVC_NLA_COMPLETION@2@@Z; Nla::CNlaManager::RegisterAddressChangeListener(Nla::_MPSSVC_NLA_COMPLETION *)
0x1800953bb  mov     cs:dword_180133C60, r14d
0x1800953c2  xor     r9d, r9d; lpName
0x1800953c5  xor     r8d, r8d; bInitialState
0x1800953c8  xor     edx, edx; bManualReset
0x1800953ca  xor     ecx, ecx; lpEventAttributes
0x1800953cc  call    cs:__imp_CreateEventW
0x1800953d3  nop     dword ptr [rax+rax+00h]
0x1800953d8  mov     cs:qword_180133C70, rax
0x1800953df  test    rax, rax
0x1800953e2  jnz     short loc_18009542A
0x1800953e4  lea     rdi, aCreateevent; "CreateEvent"
0x1800953eb  call    cs:__imp_GetLastError
0x1800953f2  nop     dword ptr [rax+rax+00h]
0x1800953f7  mov     ebx, eax
0x1800953f9  test    eax, eax
0x1800953fb  jle     short loc_180095406
0x1800953fd  movzx   ebx, ax
0x180095400  or      ebx, 80070000h
0x180095406  mov     rcx, cs:WPP_GLOBAL_Control
0x18009540d  cmp     rcx, rsi
0x180095410  jz      loc_1800950DB
0x180095416  test    [rcx+1Ch], r14b
0x18009541a  jz      loc_1800950DB
0x180095420  mov     edx, 18h
0x180095425  jmp     loc_180095280
0x18009542a  mov     dword ptr [rsp+58h+var_38], 0
0x180095432  mov     r9d, edi
0x180095435  xor     r8d, r8d
0x180095438  lea     rdx, FwDynDataNetworkStateChangeCallback
0x18009543f  mov     rcx, rax
0x180095442  call    cs:__imp_RegisterWaitForSingleObjectEx
0x180095449  nop     dword ptr [rax+rax+00h]
0x18009544e  mov     cs:qword_180133CA0, rax
0x180095455  test    rax, rax
0x180095458  jnz     short loc_1800954A0
0x18009545a  lea     rdi, aRegisterwaitfo; "RegisterWaitForSingleObjectEx"
0x180095461  call    cs:__imp_GetLastError
0x180095468  nop     dword ptr [rax+rax+00h]
0x18009546d  mov     ebx, eax
0x18009546f  test    eax, eax
0x180095471  jle     short loc_18009547C
0x180095473  movzx   ebx, ax
0x180095476  or      ebx, 80070000h
0x18009547c  mov     rcx, cs:WPP_GLOBAL_Control
0x180095483  cmp     rcx, rsi
0x180095486  jz      loc_1800950DB
0x18009548c  test    [rcx+1Ch], r14b
0x180095490  jz      loc_1800950DB
0x180095496  mov     edx, 19h
0x18009549b  jmp     loc_180095280
0x1800954a0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall> `wil::Feature<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall>::GetImpl(void)'::`2'::impl
0x1800954a7  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall>::__private_IsEnabled(void)
0x1800954ac  lea     rdx, dword_180133C60; struct Nla::_MPSSVC_NLA_COMPLETION *
0x1800954b3  test    al, al
0x1800954b5  jz      short loc_1800954F4
0x1800954b7  mov     rcx, cs:qword_180133308; this
0x1800954be  call    ?RegisterNetworkStateChangeListener@CNlmManager@Nlm@@QEAAJPEAU_MPSSVC_NLA_COMPLETION@Nla@@@Z; Nlm::CNlmManager::RegisterNetworkStateChangeListener(Nla::_MPSSVC_NLA_COMPLETION *)
0x1800954c3  mov     ebx, eax
0x1800954c5  test    eax, eax
0x1800954c7  jns     short loc_180095500
0x1800954c9  lea     rdi, aRegisternetwor; "RegisterNetworkStateChangeListener"
0x1800954d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800954d7  cmp     rcx, rsi
0x1800954da  jz      loc_1800950DB
0x1800954e0  test    [rcx+1Ch], r14b
0x1800954e4  jz      loc_1800950DB
0x1800954ea  mov     edx, 1Ah
0x1800954ef  jmp     loc_1800953A7
0x1800954f4  mov     rcx, cs:?gFwDynDataNLAComp@@3U_tagFWDYNDATANLACOMP@@A; this
0x1800954fb  call    ?RegisterNetworkStateChangeListener@CNlaManager@Nla@@QEAAXPEAU_MPSSVC_NLA_COMPLETION@2@@Z; Nla::CNlaManager::RegisterNetworkStateChangeListener(Nla::_MPSSVC_NLA_COMPLETION *)
0x180095500  call    FwDynDataNLSConnectionPointInitialize
0x180095505  mov     ebx, eax
0x180095507  test    eax, eax
0x180095509  jns     short loc_180095536
0x18009550b  lea     rdi, aFwdyndatanlsco_0; "FwDynDataNLSConnectionPointInitialize"
0x180095512  mov     rcx, cs:WPP_GLOBAL_Control
0x180095519  cmp     rcx, rsi
0x18009551c  jz      loc_1800950DB
0x180095522  test    [rcx+1Ch], r14b
0x180095526  jz      loc_1800950DB
0x18009552c  mov     edx, 1Bh
0x180095531  jmp     loc_1800953A7
0x180095536  call    FwQuarantineMonitorInitialize
0x18009553b  mov     ebx, eax
0x18009553d  test    eax, eax
0x18009553f  jns     short loc_18009556C
0x180095541  lea     rdi, aFwquarantinemo; "FwQuarantineMonitorInitialize"
0x180095548  mov     rcx, cs:WPP_GLOBAL_Control
0x18009554f  cmp     rcx, rsi
0x180095552  jz      loc_1800950DB
0x180095558  test    [rcx+1Ch], r14b
0x18009555c  jz      loc_1800950DB
0x180095562  mov     edx, 1Ch
0x180095567  jmp     loc_1800953A7
0x18009556c  call    cs:__imp_FwAddrChangeSourceInitialize
0x180095573  nop     dword ptr [rax+rax+00h]
0x180095578  mov     ebx, eax
0x18009557a  test    eax, eax
0x18009557c  jns     short loc_1800955A9
0x18009557e  lea     rdi, aFwaddrchangeso_2; "FwAddrChangeSourceInitialize"
0x180095585  mov     rcx, cs:WPP_GLOBAL_Control
0x18009558c  cmp     rcx, rsi
0x18009558f  jz      loc_1800950DB
0x180095595  test    [rcx+1Ch], r14b
0x180095599  jz      loc_1800950DB
0x18009559f  mov     edx, 1Dh
0x1800955a4  jmp     loc_1800953A7
  ... truncated ...
```
