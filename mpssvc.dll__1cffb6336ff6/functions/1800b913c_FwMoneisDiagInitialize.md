# FwMoneisDiagInitialize

- ea: `0x1800b913c`
- end: `0x1800b9580`
- name: `FwMoneisDiagInitialize`
- size: `1092`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x1800b80c0`

## callees

- `0x18000177c`
- `0x18000af3c`
- `0x180017110`
- `0x18005cf9c`
- `0x18006f520`
- `0x18006ffc8`
- `0x1800735fc`
- `0x180073664`
- `0x1800873a0`
- `0x1800b8f1c`
- `0x1800b913c`
- `0x1800b9700`

## import_xrefs

- `fwbase!FwCriticalSectionCreate` at `0x1800b925b`
- `fwbase!FwCriticalSectionCreate` at `0x1800b925b`
- `fwpuclnt!FwpmEngineOpen0` at `0x1800b92d9`
- `fwpuclnt!FwpmEngineOpen0` at `0x1800b9357`
- `fwpuclnt!FwpmEngineOpen0` at `0x1800b92d9`
- `fwpuclnt!FwpmEngineOpen0` at `0x1800b9357`
- `fwpuclnt!FwpmEventProviderCreate0` at `0x1800b9393`
- `fwpuclnt!FwpmEventProviderCreate0` at `0x1800b9393`
- `fwpuclnt!FwpmNetEventSubscribe4` at `0x1800b942b`
- `fwpuclnt!FwpmNetEventSubscribe4` at `0x1800b9459`
- `fwpuclnt!FwpmNetEventSubscribe4` at `0x1800b942b`
- `fwpuclnt!FwpmNetEventSubscribe4` at `0x1800b9459`

## string_xrefs

- `0x1800b92a6`: `FwpmEngineOpen`
- `0x1800b939f`: `FwpmEventProviderCreate0`

## pseudocode

```c
__int64 FwMoneisDiagInitialize()
{
  unsigned int v0; // edi
  _QWORD *ThreadLocalStoragePointer; // rax
  __int64 v2; // rax
  DWORD v3; // eax
  int v4; // ebx
  const char *v5; // rsi
  __int64 v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // r9
  __int64 v11; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v12; // [rsp+38h] [rbp-C8h] BYREF
  FWPM_SESSION0 session; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v14[4]; // [rsp+90h] [rbp-70h] BYREF
  _OWORD v15[2]; // [rsp+B0h] [rbp-50h] BYREF
  int v16; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v17; // [rsp+D4h] [rbp-2Ch]
  __int128 v18; // [rsp+E4h] [rbp-1Ch]
  int v19; // [rsp+F4h] [rbp-Ch]
  _OWORD v20[6]; // [rsp+100h] [rbp+0h] BYREF
  wchar_t v21; // [rsp+160h] [rbp+60h]

  v19 = 0;
  v21 = aModernNetworkI[48];
  v0 = 0;
  ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
  memset(v15, 0, sizeof(v15));
  memset(v14, 0, sizeof(v14));
  v2 = ThreadLocalStoragePointer[tls_index];
  v16 = 0;
  LODWORD(v2) = *(_DWORD *)(v2 + 4);
  v17 = 0;
  v18 = 0;
  v20[0] = *(_OWORD *)L"Modern Network Isolation Diagnostics Bfe Session";
  v20[1] = *(_OWORD *)L"etwork Isolation Diagnostics Bfe Session";
  v20[2] = *(_OWORD *)L"solation Diagnostics Bfe Session";
  v20[3] = *(_OWORD *)L" Diagnostics Bfe Session";
  v20[4] = *(_OWORD *)L"tics Bfe Session";
  v20[5] = *(_OWORD *)L" Session";
  if ( dword_180132348 > (int)v2 )
  {
    Init_thread_header(&dword_180132348);
    if ( dword_180132348 == -1 )
    {
      stru_180131680.displayData.description = 0;
      stru_180131680.displayData.name = (wchar_t *)v20;
      *(_OWORD *)&stru_180131680.sid = 0;
      stru_180131680.flags = 1;
      *(_QWORD *)&stru_180131680.txnWaitTimeoutInMSec = 18000000;
      stru_180131680.kernelMode = 0;
      Init_thread_footer(&dword_180132348);
    }
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 23, WPP_0da5eba620563d62cce5b7087a7b5f88_Traceguids);
  memset_0(&gFwMoneisDiag, 0, 0x118u);
  FwCriticalSectionCreate(qword_18012C740);
  v3 = FwMoneisDiagEdpInitialize();
  v4 = v3;
  if ( v3 )
  {
    v5 = "FwMoneisDiagEdpInitialize";
    v6 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v7 = 24;
LABEL_9:
      WPP_SF_d(*(_QWORD *)(v6 + 16), v7, WPP_0da5eba620563d62cce5b7087a7b5f88_Traceguids, v3);
      goto LABEL_24;
    }
    goto LABEL_24;
  }
  v5 = "FwpmEngineOpen";
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_FwBfeSessions>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BugFix_FwBfeSessions>::GetImpl'::`2'::impl) )
  {
    *(_QWORD *)&session.sessionKey.Data1 = 0;
    session.displayData.name = L"Modern Network Isolation Diagnostics Bfe Session";
    *(_QWORD *)session.sessionKey.Data4 = 0;
    memset(&session.processId + 1, 0, 28);
    session.displayData.description = 0;
    session.flags = 1;
    *(_QWORD *)&session.txnWaitTimeoutInMSec = 18000000;
    v3 = FwpmEngineOpen0(0, 0xAu, 0, &session, &gFwMoneisDiag);
    v4 = v3;
    if ( v3 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v7 = 25;
        goto LABEL_9;
      }
      goto LABEL_24;
    }
LABEL_19:
    v3 = FwpmEventProviderCreate0(4, &qword_18012C708);
    v4 = v3;
    if ( !v3 )
    {
      *(_QWORD *)&v15[0] = v14;
      LODWORD(v14[2]) = 1;
      v14[3] = &v16;
      *((_QWORD *)&v17 + 1) = *(unsigned int *)&FWPM_CONDITION_NET_EVENT_TYPE.Data4[4];
      DWORD1(v18) = 3;
      HIDWORD(v18) = 3;
      v16 = 544119190;
      *(_QWORD *)&v17 = *(_QWORD *)&FWPM_CONDITION_NET_EVENT_TYPE.Data2;
      FwpmNetEventSubscribe4(gFwMoneisDiag, v15, FwMoneisDiagNetEventCallback, 0, &qword_18012C700);
      HIDWORD(v18) = 6;
      FwpmNetEventSubscribe4(gFwMoneisDiag, v15, FwMoneisDiagNetEventCallback, 0, &eventsHandle);
      dword_18012C710 = 1;
      v5 = 0;
      goto LABEL_24;
    }
    v5 = "FwpmEventProviderCreate0";
    v6 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v7 = 27;
      goto LABEL_9;
    }
    goto LABEL_24;
  }
  v3 = FwpmEngineOpen0(0, 0xAu, 0, &stru_180131680, &gFwMoneisDiag);
  v4 = v3;
  if ( !v3 )
    goto LABEL_19;
  v6 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    v7 = 26;
    goto LABEL_9;
  }
LABEL_24:
  if ( (unsigned int)dword_1801263B0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1801263B0, 0x4000000000000LL) )
  {
    LODWORD(v11) = v4;
    v12 = (__int64)v5;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (int)&dword_1801263B0,
      (int)&byte_180110C57,
      v8,
      v9,
      (const char **)&v12,
      (__int64)&v11);
  }
  if ( v4 )
  {
    FwMoneisDiagShutdown();
    if ( v4 > 0 )
      v0 = (unsigned __int16)v4 | 0x80070000;
    else
      v0 = v4;
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 28, WPP_0da5eba620563d62cce5b7087a7b5f88_Traceguids, v0);
  return v0;
}

```

## disassembly

```asm
0x1800b913c  push    rbp
0x1800b913e  push    rbx
0x1800b913f  push    rsi
0x1800b9140  push    rdi
0x1800b9141  push    r12
0x1800b9143  push    r13
0x1800b9145  push    r14
0x1800b9147  push    r15
0x1800b9149  lea     rbp, [rsp-88h]
0x1800b9151  sub     rsp, 188h
0x1800b9158  mov     rax, cs:__security_cookie
0x1800b915f  xor     rax, rsp
0x1800b9162  mov     [rbp+0C0h+var_50], rax
0x1800b9166  mov     ecx, cs:_tls_index
0x1800b916c  xorps   xmm0, xmm0
0x1800b916f  xor     eax, eax
0x1800b9171  mov     edx, 4
0x1800b9176  xorps   xmm1, xmm1
0x1800b9179  mov     [rbp+0C0h+var_CC], eax
0x1800b917c  movzx   eax, word ptr cs:aModernNetworkI+60h; ""
0x1800b9183  xor     r14d, r14d
0x1800b9186  movups  [rbp+0C0h+var_12C], xmm1
0x1800b918a  mov     [rbp+0C0h+var_60], ax
0x1800b918e  mov     edi, r14d
0x1800b9191  mov     rax, gs:58h
0x1800b919a  movups  [rbp+0C0h+var_110], xmm0
0x1800b919e  mov     [rbp+0C0h+var_130], r14d
0x1800b91a2  lea     r12d, [r14+1]
0x1800b91a6  movups  [rbp+0C0h+var_100], xmm0
0x1800b91aa  mov     rax, [rax+rcx*8]
0x1800b91ae  movups  [rbp+0C0h+var_12C+0Ch], xmm1
0x1800b91b2  mov     [rbp+0C0h+var_F0], r14d
0x1800b91b6  movaps  xmm1, xmmword ptr cs:aModernNetworkI+10h; "etwork Isolation Diagnostics Bfe Sessio"...
0x1800b91bd  mov     eax, [rdx+rax]
0x1800b91c0  cmp     cs:dword_180132348, eax
0x1800b91c6  movups  [rbp+0C0h+var_EC], xmm0
0x1800b91ca  movups  [rbp+0C0h+var_DC], xmm0
0x1800b91ce  movaps  xmm0, xmmword ptr cs:aModernNetworkI; "Modern Network Isolation Diagnostics Bf"...
0x1800b91d5  movaps  [rbp+0C0h+var_C0], xmm0
0x1800b91d9  movaps  xmm0, xmmword ptr cs:aModernNetworkI+20h; "solation Diagnostics Bfe Session"
0x1800b91e0  movaps  [rbp+0C0h+var_B0], xmm1
0x1800b91e4  movaps  xmm1, xmmword ptr cs:aModernNetworkI+30h; " Diagnostics Bfe Session"
0x1800b91eb  movaps  [rbp+0C0h+var_A0], xmm0
0x1800b91ef  movaps  xmm0, xmmword ptr cs:aModernNetworkI+40h; "tics Bfe Session"
0x1800b91f6  movaps  [rbp+0C0h+var_90], xmm1
0x1800b91fa  movaps  xmm1, xmmword ptr cs:aModernNetworkI+50h; " Session"
0x1800b9201  movaps  [rbp+0C0h+var_80], xmm0
0x1800b9205  movaps  [rbp+0C0h+var_70], xmm1
0x1800b9209  jg      loc_1800B9520
0x1800b920f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b9216  lea     r15, WPP_GLOBAL_Control
0x1800b921d  lea     r13, WPP_0da5eba620563d62cce5b7087a7b5f88_Traceguids
0x1800b9224  cmp     rcx, r15
0x1800b9227  jz      short loc_1800B9240
0x1800b9229  test    byte ptr [rcx+1Ch], 8
0x1800b922d  jz      short loc_1800B9240
0x1800b922f  mov     rcx, [rcx+10h]
0x1800b9233  mov     edx, 17h
0x1800b9238  mov     r8, r13
0x1800b923b  call    WPP_SF_
0x1800b9240  xor     edx, edx; Val
0x1800b9242  lea     rcx, gFwMoneisDiag; void *
0x1800b9249  mov     r8d, 118h; Size
0x1800b924f  call    memset_0
0x1800b9254  lea     rcx, qword_18012C740
0x1800b925b  call    cs:__imp_FwCriticalSectionCreate
0x1800b9261  call    FwMoneisDiagEdpInitialize
0x1800b9266  mov     ebx, eax
0x1800b9268  test    eax, eax
0x1800b926a  jz      short loc_1800B92A6
0x1800b926c  lea     rsi, aFwmoneisdiaged; "FwMoneisDiagEdpInitialize"
0x1800b9273  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b927a  cmp     rcx, r15
0x1800b927d  jz      loc_1800B9469
0x1800b9283  test    [rcx+1Ch], r12b
0x1800b9287  jz      loc_1800B9469
0x1800b928d  mov     edx, 18h
0x1800b9292  mov     rcx, [rcx+10h]
0x1800b9296  mov     r9d, eax
0x1800b9299  mov     r8, r13
0x1800b929c  call    WPP_SF_d
0x1800b92a1  jmp     loc_1800B9469
0x1800b92a6  lea     rsi, aFwpmengineopen_0; "FwpmEngineOpen"
0x1800b92ad  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BugFix_FwBfeSessions@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_FwBfeSessions@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_FwBfeSessions> `wil::Feature<__WilFeatureTraits_Feature_BugFix_FwBfeSessions>::GetImpl(void)'::`2'::impl
0x1800b92b4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_FwBfeSessions@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_FwBfeSessions>::__private_IsEnabled(void)
0x1800b92b9  xor     r8d, r8d; authIdentity
0x1800b92bc  xor     ecx, ecx; serverName
0x1800b92be  lea     edx, [r8+0Ah]; authnService
0x1800b92c2  test    al, al
0x1800b92c4  jnz     short loc_1800B930A
0x1800b92c6  lea     rax, gFwMoneisDiag
0x1800b92cd  lea     r9, stru_180131680; session
0x1800b92d4  mov     [rsp+1C0h+engineHandle], rax; engineHandle
0x1800b92d9  call    cs:__imp_FwpmEngineOpen0
0x1800b92df  mov     ebx, eax
0x1800b92e1  test    eax, eax
0x1800b92e3  jz      loc_1800B9387
0x1800b92e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b92f0  cmp     rcx, r15
0x1800b92f3  jz      loc_1800B9469
0x1800b92f9  test    [rcx+1Ch], r12b
0x1800b92fd  jz      loc_1800B9469
0x1800b9303  mov     edx, 1Ah
0x1800b9308  jmp     short loc_1800B9292
0x1800b930a  lea     rax, aModernNetworkI; "Modern Network Isolation Diagnostics Bf"...
0x1800b9311  mov     qword ptr [rsp+1C0h+session.sessionKey.Data1], r14
0x1800b9316  mov     [rsp+1C0h+session.displayData.name], rax
0x1800b931b  lea     r9, [rsp+1C0h+session]; session
0x1800b9320  xor     eax, eax
0x1800b9322  mov     qword ptr [rsp+1C0h+session.sessionKey.Data4], r14
0x1800b9327  mov     dword ptr [rsp+1C0h+session+2Ch], eax
0x1800b932b  xorps   xmm0, xmm0
0x1800b932e  lea     rax, gFwMoneisDiag
0x1800b9335  mov     [rsp+1C0h+session.displayData.description], r14
0x1800b933a  mov     [rsp+1C0h+engineHandle], rax; engineHandle
0x1800b933f  mov     [rsp+1C0h+session.flags], r12d
0x1800b9344  mov     qword ptr [rsp+1C0h+session.txnWaitTimeoutInMSec], 112A880h
0x1800b934d  movdqa  xmmword ptr [rsp+1C0h+session.sid], xmm0
0x1800b9353  mov     qword ptr [rbp+0C0h+session.kernelMode], r14
0x1800b9357  call    cs:__imp_FwpmEngineOpen0
0x1800b935d  mov     ebx, eax
0x1800b935f  test    eax, eax
0x1800b9361  jz      short loc_1800B9387
0x1800b9363  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b936a  cmp     rcx, r15
0x1800b936d  jz      loc_1800B9469
0x1800b9373  test    [rcx+1Ch], r12b
0x1800b9377  jz      loc_1800B9469
0x1800b937d  mov     edx, 19h
0x1800b9382  jmp     loc_1800B9292
0x1800b9387  lea     rdx, qword_18012C708
0x1800b938e  mov     ecx, 4
0x1800b9393  call    cs:__imp_FwpmEventProviderCreate0
0x1800b9399  mov     ebx, eax
0x1800b939b  test    eax, eax
0x1800b939d  jz      short loc_1800B93CA
0x1800b939f  lea     rsi, aFwpmeventprovi_3; "FwpmEventProviderCreate0"
0x1800b93a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b93ad  cmp     rcx, r15
0x1800b93b0  jz      loc_1800B9469
0x1800b93b6  test    [rcx+1Ch], r12b
0x1800b93ba  jz      loc_1800B9469
0x1800b93c0  mov     edx, 1Bh
0x1800b93c5  jmp     loc_1800B9292
0x1800b93ca  movsd   xmm0, qword ptr cs:FWPM_CONDITION_NET_EVENT_TYPE.Data2
0x1800b93d2  lea     rax, [rbp+0C0h+var_130]
0x1800b93d6  mov     rcx, cs:gFwMoneisDiag
0x1800b93dd  lea     r8, FwMoneisDiagNetEventCallback
0x1800b93e4  mov     qword ptr [rbp+0C0h+var_110], rax
0x1800b93e8  lea     rdx, [rbp+0C0h+var_110]
0x1800b93ec  lea     rax, [rbp+0C0h+var_F0]
0x1800b93f0  mov     dword ptr [rbp+0C0h+var_12C+0Ch], r12d
0x1800b93f4  mov     [rbp+0C0h+var_118], rax
0x1800b93f8  xor     r9d, r9d
0x1800b93fb  mov     eax, dword ptr cs:FWPM_CONDITION_NET_EVENT_TYPE.Data4+4
0x1800b9401  mov     dword ptr [rbp+0C0h+var_EC+8], eax
0x1800b9404  mov     eax, 3
0x1800b9409  mov     dword ptr [rbp+0C0h+var_DC+4], eax
0x1800b940c  mov     dword ptr [rbp+0C0h+var_DC+0Ch], eax
0x1800b940f  lea     rax, qword_18012C700
0x1800b9416  mov     [rsp+1C0h+engineHandle], rax
0x1800b941b  mov     [rbp+0C0h+var_F0], 206E9996h
0x1800b9422  movsd   qword ptr [rbp+0C0h+var_EC], xmm0
0x1800b9427  mov     dword ptr [rbp+0C0h+var_EC+0Ch], r14d
0x1800b942b  call    cs:__imp_FwpmNetEventSubscribe4
0x1800b9431  mov     rcx, cs:gFwMoneisDiag
0x1800b9438  lea     rax, eventsHandle
0x1800b943f  xor     r9d, r9d
0x1800b9442  mov     [rsp+1C0h+engineHandle], rax
0x1800b9447  lea     r8, FwMoneisDiagNetEventCallback
0x1800b944e  mov     dword ptr [rbp+0C0h+var_DC+0Ch], 6
0x1800b9455  lea     rdx, [rbp+0C0h+var_110]
0x1800b9459  call    cs:__imp_FwpmNetEventSubscribe4
0x1800b945f  mov     cs:dword_18012C710, r12d
0x1800b9466  mov     rsi, r14
0x1800b9469  mov     eax, cs:dword_1801263B0
0x1800b946f  cmp     eax, 4
0x1800b9472  jbe     short loc_1800B94BE
0x1800b9474  mov     rdx, 4000000000000h
0x1800b947e  lea     rcx, dword_1801263B0
0x1800b9485  call    _tlgKeywordOn
0x1800b948a  test    al, al
0x1800b948c  jz      short loc_1800B94BE
0x1800b948e  lea     rax, [rsp+1C0h+var_190]
0x1800b9493  mov     dword ptr [rsp+1C0h+var_190], ebx
0x1800b9497  mov     [rsp+1C0h+var_198], rax; __int64
0x1800b949c  lea     rdx, byte_180110C57
0x1800b94a3  lea     rax, [rsp+1C0h+var_188]
0x1800b94a8  mov     [rsp+1C0h+var_188], rsi
0x1800b94ad  lea     rcx, dword_1801263B0; int
0x1800b94b4  mov     [rsp+1C0h+engineHandle], rax; __int64
0x1800b94b9  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800b94be  test    ebx, ebx
0x1800b94c0  jz      short loc_1800B94D8
0x1800b94c2  call    FwMoneisDiagShutdown
0x1800b94c7  test    ebx, ebx
0x1800b94c9  jg      short loc_1800B94CF
0x1800b94cb  mov     edi, ebx
0x1800b94cd  jmp     short loc_1800B94D8
0x1800b94cf  movzx   edi, bx
0x1800b94d2  or      edi, 80070000h
0x1800b94d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b94df  cmp     rcx, r15
0x1800b94e2  jz      short loc_1800B94FE
0x1800b94e4  test    byte ptr [rcx+1Ch], 8
0x1800b94e8  jz      short loc_1800B94FE
0x1800b94ea  mov     rcx, [rcx+10h]
0x1800b94ee  mov     edx, 1Ch
0x1800b94f3  mov     r9d, edi
0x1800b94f6  mov     r8, r13
0x1800b94f9  call    WPP_SF_d
0x1800b94fe  mov     eax, edi
0x1800b9500  mov     rcx, [rbp+0C0h+var_50]
0x1800b9504  xor     rcx, rsp; StackCookie
0x1800b9507  call    __security_check_cookie
0x1800b950c  add     rsp, 188h
0x1800b9513  pop     r15
0x1800b9515  pop     r14
0x1800b9517  pop     r13
0x1800b9519  pop     r12
0x1800b951b  pop     rdi
0x1800b951c  pop     rsi
0x1800b951d  pop     rbx
0x1800b951e  pop     rbp
0x1800b951f  retn
0x1800b9520  lea     rcx, dword_180132348
0x1800b9527  call    _Init_thread_header
0x1800b952c  cmp     cs:dword_180132348, 0FFFFFFFFh
0x1800b9533  jnz     loc_1800B920F
0x1800b9539  lea     rax, [rbp+0C0h+var_C0]
0x1800b953d  mov     cs:stru_180131680.displayData.description, r14
0x1800b9544  xorps   xmm0, xmm0
0x1800b9547  mov     cs:stru_180131680.displayData.name, rax
0x1800b954e  lea     rcx, dword_180132348
0x1800b9555  movdqa  xmmword ptr cs:stru_180131680.sid, xmm0
0x1800b955d  mov     cs:stru_180131680.flags, r12d
0x1800b9564  mov     qword ptr cs:stru_180131680.txnWaitTimeoutInMSec, 112A880h
0x1800b956f  mov     cs:stru_180131680.kernelMode, r14d
0x1800b9576  call    _Init_thread_footer
0x1800b957b  jmp     loc_1800B920F
```
