# FwMoneisDiagInitialize

- ea: `0x1800bff64`
- end: `0x1800c03cd`
- name: `FwMoneisDiagInitialize`
- size: `1129`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x1800beee0`

## callees

- `0x180001784`
- `0x18000a710`
- `0x1800192e0`
- `0x180061c90`
- `0x1800729c0`
- `0x180073488`
- `0x180076abc`
- `0x180076b24`
- `0x18008b9f8`
- `0x1800bfcf4`
- `0x1800bff64`
- `0x1800c0564`

## import_xrefs

- `fwbase!FwCriticalSectionCreate` at `0x1800c0083`
- `fwbase!FwCriticalSectionCreate` at `0x1800c0083`
- `fwpuclnt!FwpmEngineOpen0` at `0x1800c0107`
- `fwpuclnt!FwpmEngineOpen0` at `0x1800c018b`
- `fwpuclnt!FwpmEngineOpen0` at `0x1800c0107`
- `fwpuclnt!FwpmEngineOpen0` at `0x1800c018b`
- `fwpuclnt!FwpmEventProviderCreate0` at `0x1800c01cd`
- `fwpuclnt!FwpmEventProviderCreate0` at `0x1800c01cd`
- `fwpuclnt!FwpmNetEventSubscribe4` at `0x1800c026b`
- `fwpuclnt!FwpmNetEventSubscribe4` at `0x1800c029f`
- `fwpuclnt!FwpmNetEventSubscribe4` at `0x1800c026b`
- `fwpuclnt!FwpmNetEventSubscribe4` at `0x1800c029f`

## string_xrefs

- `0x1800c00d4`: `FwpmEngineOpen`
- `0x1800c01df`: `FwpmEventProviderCreate0`

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
  __int64 v9; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v10; // [rsp+38h] [rbp-C8h] BYREF
  FWPM_SESSION0 session; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v12[4]; // [rsp+90h] [rbp-70h] BYREF
  _OWORD v13[2]; // [rsp+B0h] [rbp-50h] BYREF
  int v14; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v15; // [rsp+D4h] [rbp-2Ch]
  __int128 v16; // [rsp+E4h] [rbp-1Ch]
  int v17; // [rsp+F4h] [rbp-Ch]
  _OWORD v18[6]; // [rsp+100h] [rbp+0h] BYREF
  wchar_t v19; // [rsp+160h] [rbp+60h]

  v17 = 0;
  v19 = aModernNetworkI[48];
  v0 = 0;
  ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
  memset(v13, 0, sizeof(v13));
  memset(v12, 0, sizeof(v12));
  v2 = ThreadLocalStoragePointer[tls_index];
  v14 = 0;
  LODWORD(v2) = *(_DWORD *)(v2 + 4);
  v15 = 0;
  v16 = 0;
  v18[0] = *(_OWORD *)L"Modern Network Isolation Diagnostics Bfe Session";
  v18[1] = *(_OWORD *)L"etwork Isolation Diagnostics Bfe Session";
  v18[2] = *(_OWORD *)L"solation Diagnostics Bfe Session";
  v18[3] = *(_OWORD *)L" Diagnostics Bfe Session";
  v18[4] = *(_OWORD *)L"tics Bfe Session";
  v18[5] = *(_OWORD *)L" Session";
  if ( dword_1801383F0 > (int)v2 )
  {
    Init_thread_header(&dword_1801383F0);
    if ( dword_1801383F0 == -1 )
    {
      ::session.displayData.description = 0;
      ::session.displayData.name = (wchar_t *)v18;
      *(_OWORD *)&::session.sid = 0;
      ::session.flags = 1;
      *(_QWORD *)&::session.txnWaitTimeoutInMSec = 18000000;
      ::session.kernelMode = 0;
      Init_thread_footer(&dword_1801383F0);
    }
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 23, WPP_c82a0d1b11b03f6aea8fb1592911dce6_Traceguids);
  memset_0(&gFwMoneisDiag, 0, 0x118u);
  FwCriticalSectionCreate(qword_180132910);
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
      WPP_SF_d(*(_QWORD *)(v6 + 16), v7, WPP_c82a0d1b11b03f6aea8fb1592911dce6_Traceguids, v3);
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
    v3 = FwpmEventProviderCreate0(4, &qword_1801328D8);
    v4 = v3;
    if ( !v3 )
    {
      *(_QWORD *)&v13[0] = v12;
      LODWORD(v12[2]) = 1;
      v12[3] = &v14;
      *((_QWORD *)&v15 + 1) = *(unsigned int *)&FWPM_CONDITION_NET_EVENT_TYPE.Data4[4];
      DWORD1(v16) = 3;
      HIDWORD(v16) = 3;
      v14 = 544119190;
      *(_QWORD *)&v15 = *(_QWORD *)&FWPM_CONDITION_NET_EVENT_TYPE.Data2;
      FwpmNetEventSubscribe4(gFwMoneisDiag, v13, FwMoneisDiagNetEventCallback, 0, &qword_1801328D0);
      HIDWORD(v16) = 6;
      FwpmNetEventSubscribe4(gFwMoneisDiag, v13, FwMoneisDiagNetEventCallback, 0, &eventsHandle);
      dword_1801328E0 = 1;
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
  v3 = FwpmEngineOpen0(0, 0xAu, 0, &::session, &gFwMoneisDiag);
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
  if ( (unsigned int)dword_18012C3B0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18012C3B0, 0x4000000000000LL) )
  {
    LODWORD(v9) = v4;
    v10 = (__int64)v5;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (int)&dword_18012C3B0,
      (__int64)&v10,
      (__int64)&v9);
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
    WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 28, WPP_c82a0d1b11b03f6aea8fb1592911dce6_Traceguids, v0);
  return v0;
}

```

## disassembly

```asm
0x1800bff64  push    rbp
0x1800bff66  push    rbx
0x1800bff67  push    rsi
0x1800bff68  push    rdi
0x1800bff69  push    r12
0x1800bff6b  push    r13
0x1800bff6d  push    r14
0x1800bff6f  push    r15
0x1800bff71  lea     rbp, [rsp-88h]
0x1800bff79  sub     rsp, 188h
0x1800bff80  mov     rax, cs:__security_cookie
0x1800bff87  xor     rax, rsp
0x1800bff8a  mov     [rbp+0C0h+var_50], rax
0x1800bff8e  mov     ecx, cs:_tls_index
0x1800bff94  xorps   xmm0, xmm0
0x1800bff97  xor     eax, eax
0x1800bff99  mov     edx, 4
0x1800bff9e  xorps   xmm1, xmm1
0x1800bffa1  mov     [rbp+0C0h+var_CC], eax
0x1800bffa4  movzx   eax, word ptr cs:aModernNetworkI+60h; ""
0x1800bffab  xor     r14d, r14d
0x1800bffae  movups  [rbp+0C0h+var_12C], xmm1
0x1800bffb2  mov     [rbp+0C0h+var_60], ax
0x1800bffb6  mov     edi, r14d
0x1800bffb9  mov     rax, gs:58h
0x1800bffc2  movups  [rbp+0C0h+var_110], xmm0
0x1800bffc6  mov     [rbp+0C0h+var_130], r14d
0x1800bffca  lea     r12d, [r14+1]
0x1800bffce  movups  [rbp+0C0h+var_100], xmm0
0x1800bffd2  mov     rax, [rax+rcx*8]
0x1800bffd6  movups  [rbp+0C0h+var_12C+0Ch], xmm1
0x1800bffda  mov     [rbp+0C0h+var_F0], r14d
0x1800bffde  movaps  xmm1, xmmword ptr cs:aModernNetworkI+10h; "etwork Isolation Diagnostics Bfe Sessio"...
0x1800bffe5  mov     eax, [rdx+rax]
0x1800bffe8  cmp     cs:dword_1801383F0, eax
0x1800bffee  movups  [rbp+0C0h+var_EC], xmm0
0x1800bfff2  movups  [rbp+0C0h+var_DC], xmm0
0x1800bfff6  movaps  xmm0, xmmword ptr cs:aModernNetworkI; "Modern Network Isolation Diagnostics Bf"...
0x1800bfffd  movaps  [rbp+0C0h+var_C0], xmm0
0x1800c0001  movaps  xmm0, xmmword ptr cs:aModernNetworkI+20h; "solation Diagnostics Bfe Session"
0x1800c0008  movaps  [rbp+0C0h+var_B0], xmm1
0x1800c000c  movaps  xmm1, xmmword ptr cs:aModernNetworkI+30h; " Diagnostics Bfe Session"
0x1800c0013  movaps  [rbp+0C0h+var_A0], xmm0
0x1800c0017  movaps  xmm0, xmmword ptr cs:aModernNetworkI+40h; "tics Bfe Session"
0x1800c001e  movaps  [rbp+0C0h+var_90], xmm1
0x1800c0022  movaps  xmm1, xmmword ptr cs:aModernNetworkI+50h; " Session"
0x1800c0029  movaps  [rbp+0C0h+var_80], xmm0
0x1800c002d  movaps  [rbp+0C0h+var_70], xmm1
0x1800c0031  jg      loc_1800C036D
0x1800c0037  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c003e  lea     r15, WPP_GLOBAL_Control
0x1800c0045  lea     r13, WPP_c82a0d1b11b03f6aea8fb1592911dce6_Traceguids
0x1800c004c  cmp     rcx, r15
0x1800c004f  jz      short loc_1800C0068
0x1800c0051  test    byte ptr [rcx+1Ch], 8
0x1800c0055  jz      short loc_1800C0068
0x1800c0057  mov     rcx, [rcx+10h]
0x1800c005b  mov     edx, 17h
0x1800c0060  mov     r8, r13
0x1800c0063  call    WPP_SF_
0x1800c0068  xor     edx, edx; Val
0x1800c006a  lea     rcx, gFwMoneisDiag; void *
0x1800c0071  mov     r8d, 118h; Size
0x1800c0077  call    memset_0
0x1800c007c  lea     rcx, qword_180132910
0x1800c0083  call    cs:__imp_FwCriticalSectionCreate
0x1800c008a  nop     dword ptr [rax+rax+00h]
0x1800c008f  call    FwMoneisDiagEdpInitialize
0x1800c0094  mov     ebx, eax
0x1800c0096  test    eax, eax
0x1800c0098  jz      short loc_1800C00D4
0x1800c009a  lea     rsi, aFwmoneisdiaged; "FwMoneisDiagEdpInitialize"
0x1800c00a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c00a8  cmp     rcx, r15
0x1800c00ab  jz      loc_1800C02B5
0x1800c00b1  test    [rcx+1Ch], r12b
0x1800c00b5  jz      loc_1800C02B5
0x1800c00bb  mov     edx, 18h
0x1800c00c0  mov     rcx, [rcx+10h]
0x1800c00c4  mov     r9d, eax
0x1800c00c7  mov     r8, r13
0x1800c00ca  call    WPP_SF_d
0x1800c00cf  jmp     loc_1800C02B5
0x1800c00d4  lea     rsi, aFwpmengineopen_0; "FwpmEngineOpen"
0x1800c00db  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BugFix_FwBfeSessions@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_FwBfeSessions@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_FwBfeSessions> `wil::Feature<__WilFeatureTraits_Feature_BugFix_FwBfeSessions>::GetImpl(void)'::`2'::impl
0x1800c00e2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_FwBfeSessions@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_FwBfeSessions>::__private_IsEnabled(void)
0x1800c00e7  xor     r8d, r8d; authIdentity
0x1800c00ea  xor     ecx, ecx; serverName
0x1800c00ec  lea     edx, [r8+0Ah]; authnService
0x1800c00f0  test    al, al
0x1800c00f2  jnz     short loc_1800C013E
0x1800c00f4  lea     rax, gFwMoneisDiag
0x1800c00fb  lea     r9, session; session
0x1800c0102  mov     [rsp+1C0h+engineHandle], rax; engineHandle
0x1800c0107  call    cs:__imp_FwpmEngineOpen0
0x1800c010e  nop     dword ptr [rax+rax+00h]
0x1800c0113  mov     ebx, eax
0x1800c0115  test    eax, eax
0x1800c0117  jz      loc_1800C01C1
0x1800c011d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c0124  cmp     rcx, r15
0x1800c0127  jz      loc_1800C02B5
0x1800c012d  test    [rcx+1Ch], r12b
0x1800c0131  jz      loc_1800C02B5
0x1800c0137  mov     edx, 1Ah
0x1800c013c  jmp     short loc_1800C00C0
0x1800c013e  lea     rax, aModernNetworkI; "Modern Network Isolation Diagnostics Bf"...
0x1800c0145  mov     qword ptr [rsp+1C0h+session.sessionKey.Data1], r14
0x1800c014a  mov     [rsp+1C0h+session.displayData.name], rax
0x1800c014f  lea     r9, [rsp+1C0h+session]; session
0x1800c0154  xor     eax, eax
0x1800c0156  mov     qword ptr [rsp+1C0h+session.sessionKey.Data4], r14
0x1800c015b  mov     dword ptr [rsp+1C0h+session+2Ch], eax
0x1800c015f  xorps   xmm0, xmm0
0x1800c0162  lea     rax, gFwMoneisDiag
0x1800c0169  mov     [rsp+1C0h+session.displayData.description], r14
0x1800c016e  mov     [rsp+1C0h+engineHandle], rax; engineHandle
0x1800c0173  mov     [rsp+1C0h+session.flags], r12d
0x1800c0178  mov     qword ptr [rsp+1C0h+session.txnWaitTimeoutInMSec], 112A880h
0x1800c0181  movdqa  xmmword ptr [rsp+1C0h+session.sid], xmm0
0x1800c0187  mov     qword ptr [rbp+0C0h+session.kernelMode], r14
0x1800c018b  call    cs:__imp_FwpmEngineOpen0
0x1800c0192  nop     dword ptr [rax+rax+00h]
0x1800c0197  mov     ebx, eax
0x1800c0199  test    eax, eax
0x1800c019b  jz      short loc_1800C01C1
0x1800c019d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c01a4  cmp     rcx, r15
0x1800c01a7  jz      loc_1800C02B5
0x1800c01ad  test    [rcx+1Ch], r12b
0x1800c01b1  jz      loc_1800C02B5
0x1800c01b7  mov     edx, 19h
0x1800c01bc  jmp     loc_1800C00C0
0x1800c01c1  lea     rdx, qword_1801328D8
0x1800c01c8  mov     ecx, 4
0x1800c01cd  call    cs:__imp_FwpmEventProviderCreate0
0x1800c01d4  nop     dword ptr [rax+rax+00h]
0x1800c01d9  mov     ebx, eax
0x1800c01db  test    eax, eax
0x1800c01dd  jz      short loc_1800C020A
0x1800c01df  lea     rsi, aFwpmeventprovi_3; "FwpmEventProviderCreate0"
0x1800c01e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c01ed  cmp     rcx, r15
0x1800c01f0  jz      loc_1800C02B5
0x1800c01f6  test    [rcx+1Ch], r12b
0x1800c01fa  jz      loc_1800C02B5
0x1800c0200  mov     edx, 1Bh
0x1800c0205  jmp     loc_1800C00C0
0x1800c020a  movsd   xmm0, qword ptr cs:FWPM_CONDITION_NET_EVENT_TYPE.Data2
0x1800c0212  lea     rax, [rbp+0C0h+var_130]
0x1800c0216  mov     rcx, cs:gFwMoneisDiag
0x1800c021d  lea     r8, FwMoneisDiagNetEventCallback
0x1800c0224  mov     qword ptr [rbp+0C0h+var_110], rax
0x1800c0228  lea     rdx, [rbp+0C0h+var_110]
0x1800c022c  lea     rax, [rbp+0C0h+var_F0]
0x1800c0230  mov     dword ptr [rbp+0C0h+var_12C+0Ch], r12d
0x1800c0234  mov     [rbp+0C0h+var_118], rax
0x1800c0238  xor     r9d, r9d
0x1800c023b  mov     eax, dword ptr cs:FWPM_CONDITION_NET_EVENT_TYPE.Data4+4
0x1800c0241  mov     dword ptr [rbp+0C0h+var_EC+8], eax
0x1800c0244  mov     eax, 3
0x1800c0249  mov     dword ptr [rbp+0C0h+var_DC+4], eax
0x1800c024c  mov     dword ptr [rbp+0C0h+var_DC+0Ch], eax
0x1800c024f  lea     rax, qword_1801328D0
0x1800c0256  mov     [rsp+1C0h+engineHandle], rax
0x1800c025b  mov     [rbp+0C0h+var_F0], 206E9996h
0x1800c0262  movsd   qword ptr [rbp+0C0h+var_EC], xmm0
0x1800c0267  mov     dword ptr [rbp+0C0h+var_EC+0Ch], r14d
0x1800c026b  call    cs:__imp_FwpmNetEventSubscribe4
0x1800c0272  nop     dword ptr [rax+rax+00h]
0x1800c0277  mov     rcx, cs:gFwMoneisDiag
0x1800c027e  lea     rax, eventsHandle
0x1800c0285  xor     r9d, r9d
0x1800c0288  mov     [rsp+1C0h+engineHandle], rax
0x1800c028d  lea     r8, FwMoneisDiagNetEventCallback
0x1800c0294  mov     dword ptr [rbp+0C0h+var_DC+0Ch], 6
0x1800c029b  lea     rdx, [rbp+0C0h+var_110]
0x1800c029f  call    cs:__imp_FwpmNetEventSubscribe4
0x1800c02a6  nop     dword ptr [rax+rax+00h]
0x1800c02ab  mov     cs:dword_1801328E0, r12d
0x1800c02b2  mov     rsi, r14
0x1800c02b5  mov     eax, cs:dword_18012C3B0
0x1800c02bb  cmp     eax, 4
0x1800c02be  jbe     short loc_1800C030A
0x1800c02c0  mov     rdx, 4000000000000h
0x1800c02ca  lea     rcx, dword_18012C3B0
0x1800c02d1  call    _tlgKeywordOn
0x1800c02d6  test    al, al
0x1800c02d8  jz      short loc_1800C030A
0x1800c02da  lea     rax, [rsp+1C0h+var_190]
0x1800c02df  mov     dword ptr [rsp+1C0h+var_190], ebx
0x1800c02e3  mov     [rsp+1C0h+var_198], rax; __int64
0x1800c02e8  lea     rdx, byte_180116C2B
0x1800c02ef  lea     rax, [rsp+1C0h+var_188]
0x1800c02f4  mov     [rsp+1C0h+var_188], rsi
0x1800c02f9  lea     rcx, dword_18012C3B0; int
0x1800c0300  mov     [rsp+1C0h+engineHandle], rax; __int64
0x1800c0305  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800c030a  test    ebx, ebx
0x1800c030c  jz      short loc_1800C0324
0x1800c030e  call    FwMoneisDiagShutdown
0x1800c0313  test    ebx, ebx
0x1800c0315  jg      short loc_1800C031B
0x1800c0317  mov     edi, ebx
0x1800c0319  jmp     short loc_1800C0324
0x1800c031b  movzx   edi, bx
0x1800c031e  or      edi, 80070000h
0x1800c0324  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c032b  cmp     rcx, r15
0x1800c032e  jz      short loc_1800C034A
0x1800c0330  test    byte ptr [rcx+1Ch], 8
0x1800c0334  jz      short loc_1800C034A
0x1800c0336  mov     rcx, [rcx+10h]
0x1800c033a  mov     edx, 1Ch
0x1800c033f  mov     r9d, edi
0x1800c0342  mov     r8, r13
0x1800c0345  call    WPP_SF_d
0x1800c034a  mov     eax, edi
0x1800c034c  mov     rcx, [rbp+0C0h+var_50]
0x1800c0350  xor     rcx, rsp; StackCookie
0x1800c0353  call    __security_check_cookie
0x1800c0358  add     rsp, 188h
0x1800c035f  pop     r15
0x1800c0361  pop     r14
0x1800c0363  pop     r13
0x1800c0365  pop     r12
0x1800c0367  pop     rdi
0x1800c0368  pop     rsi
0x1800c0369  pop     rbx
0x1800c036a  pop     rbp
0x1800c036b  retn
0x1800c036d  lea     rcx, dword_1801383F0
0x1800c0374  call    _Init_thread_header
0x1800c0379  cmp     cs:dword_1801383F0, 0FFFFFFFFh
0x1800c0380  jnz     loc_1800C0037
0x1800c0386  lea     rax, [rbp+0C0h+var_C0]
0x1800c038a  mov     cs:session.displayData.description, r14
0x1800c0391  xorps   xmm0, xmm0
0x1800c0394  mov     cs:session.displayData.name, rax
0x1800c039b  lea     rcx, dword_1801383F0
0x1800c03a2  movdqa  xmmword ptr cs:session.sid, xmm0
0x1800c03aa  mov     cs:session.flags, r12d
0x1800c03b1  mov     qword ptr cs:session.txnWaitTimeoutInMSec, 112A880h
0x1800c03bc  mov     cs:session.kernelMode, r14d
0x1800c03c3  call    _Init_thread_footer
0x1800c03c8  jmp     loc_1800C0037
```
