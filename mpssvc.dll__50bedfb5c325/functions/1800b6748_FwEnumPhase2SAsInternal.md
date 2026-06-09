# FwEnumPhase2SAsInternal

- ea: `0x1800b6748`
- end: `0x1800b6bcc`
- name: `FwEnumPhase2SAsInternal`
- size: `1156`
- prototype: `__int64 __fastcall(struct _tag_FW_ENDPOINTS *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x1800a1688`

## callees

- `0x18000a710`
- `0x1800729c0`
- `0x18008b9f8`
- `0x1800b43d8`
- `0x1800b4bc4`
- `0x1800b6748`

## import_xrefs

- `fwbase!FwHResultToWindowsError` at `0x1800b69b2`
- `fwbase!FwHResultToWindowsError` at `0x1800b69b2`
- `fwbase!FwSizeTMultiply` at `0x1800b69a4`
- `fwbase!FwSizeTMultiply` at `0x1800b69a4`
- `fwbase!FwAlloc` at `0x1800b69f3`
- `fwbase!FwAlloc` at `0x1800b69f3`
- `fwbase!FwFree` at `0x1800b6b52`
- `fwbase!FwFree` at `0x1800b6b52`
- `fwpuclnt!FwpmEngineOpen0` at `0x1800b67ff`
- `fwpuclnt!FwpmEngineOpen0` at `0x1800b684a`
- `fwpuclnt!FwpmEngineOpen0` at `0x1800b67ff`
- `fwpuclnt!FwpmEngineOpen0` at `0x1800b684a`
- `fwpuclnt!FwpmEngineClose0` at `0x1800b6b96`
- `fwpuclnt!FwpmEngineClose0` at `0x1800b6b96`
- `fwpuclnt!IPsecSaContextCreateEnumHandle0` at `0x1800b688e`
- `fwpuclnt!IPsecSaContextCreateEnumHandle0` at `0x1800b688e`
- `fwpuclnt!IPsecSaContextEnum0` at `0x1800b68e4`
- `fwpuclnt!IPsecSaContextEnum0` at `0x1800b68e4`
- `fwpuclnt!FwpmFreeMemory0` at `0x1800b6b68`
- `fwpuclnt!FwpmFreeMemory0` at `0x1800b6b68`
- `fwpuclnt!IPsecSaContextDestroyEnumHandle0` at `0x1800b6b81`
- `fwpuclnt!IPsecSaContextDestroyEnumHandle0` at `0x1800b6b81`

## pseudocode

```c
__int64 __fastcall FwEnumPhase2SAsInternal(struct _tag_FW_ENDPOINTS *a1, unsigned int *a2, __int64 *a3)
{
  __int64 v4; // r13
  DWORD v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r9
  UINT32 v10; // r14d
  unsigned int v11; // edi
  UINT32 v12; // esi
  IPSEC_SA_CONTEXT0 *v13; // r15
  IPSEC_SA_DETAILS0 *inboundSa; // rdx
  IPSEC_SA_DETAILS0 *outboundSa; // rdx
  unsigned int v16; // eax
  unsigned int v17; // esi
  UINT32 i; // r14d
  IPSEC_SA_CONTEXT0 *v19; // r12
  IPSEC_SA_DETAILS0 *v20; // r15
  IPSEC_SA_DETAILS0 *v21; // r15
  IPSEC_SA_CONTEXT0 **entries; // [rsp+48h] [rbp-61h] BYREF
  HANDLE engineHandle; // [rsp+50h] [rbp-59h] BYREF
  HANDLE enumHandle; // [rsp+58h] [rbp-51h] BYREF
  __int64 v29; // [rsp+60h] [rbp-49h] BYREF
  FWPM_SESSION0 session; // [rsp+70h] [rbp-39h] BYREF
  UINT32 numEntriesReturned; // [rsp+C0h] [rbp+17h] BYREF

  *a2 = 0;
  *a3 = 0;
  v4 = 0;
  engineHandle = 0;
  enumHandle = 0;
  entries = 0;
  numEntriesReturned = 0;
  v29 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_FwBfeSessions>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BugFix_FwBfeSessions>::GetImpl'::`2'::impl) )
  {
    *(_QWORD *)&session.sessionKey.Data1 = 0;
    session.displayData.name = L"Firewall Enum Phase2 SAs";
    *(_QWORD *)session.sessionKey.Data4 = 0;
    memset(&session.processId + 1, 0, 28);
    session.displayData.description = 0;
    session.flags = 0;
    *(_QWORD *)&session.txnWaitTimeoutInMSec = 18000000;
    v5 = FwpmEngineOpen0(0, 0xAu, 0, &session, &engineHandle);
    v6 = v5;
    if ( v5 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_58;
      v8 = 17;
LABEL_6:
      v9 = v5;
      goto LABEL_38;
    }
  }
  else
  {
    v5 = FwpmEngineOpen0(0, 0xAu, 0, 0, &engineHandle);
    v6 = v5;
    if ( v5 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_58;
      v8 = 18;
      goto LABEL_6;
    }
  }
  v5 = IPsecSaContextCreateEnumHandle0(engineHandle, 0, &enumHandle);
  v6 = v5;
  if ( v5 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_58;
    v8 = 19;
    goto LABEL_6;
  }
  v5 = IPsecSaContextEnum0(engineHandle, enumHandle, 0xFFFFFFFF, &entries, &numEntriesReturned);
  v6 = v5;
  if ( v5 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_58;
    v8 = 20;
    goto LABEL_6;
  }
  v10 = numEntriesReturned;
  if ( !numEntriesReturned )
    goto LABEL_59;
  if ( !entries )
    goto LABEL_61;
  v11 = 0;
  v12 = 0;
  do
  {
    v13 = entries[v12];
    inboundSa = v13->inboundSa;
    if ( inboundSa && (unsigned int)FwMatchEndpointsWithIkeTraffic(a1, (struct IKEEXT_TRAFFIC0_ *)&inboundSa->traffic) )
      ++v11;
    outboundSa = v13->outboundSa;
    if ( outboundSa && (unsigned int)FwMatchEndpointsWithIkeTraffic(a1, (struct IKEEXT_TRAFFIC0_ *)&outboundSa->traffic) )
      ++v11;
    ++v12;
  }
  while ( v12 < v10 );
  if ( !v11 )
    goto LABEL_59;
  v16 = FwSizeTMultiply(v11, 120, &v29);
  v5 = FwHResultToWindowsError(v16);
  v6 = v5;
  if ( v5 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_58;
    v8 = 21;
    goto LABEL_6;
  }
  v4 = FwAlloc(v29);
  if ( !v4 )
  {
    v6 = 14;
    v7 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_58;
    v8 = 22;
    v9 = 14;
LABEL_38:
    WPP_SF_d(*(_QWORD *)(v7 + 16), v8, WPP_79bb214f8d013c8d3517fa004f1c3caf_Traceguids, v9);
    goto LABEL_58;
  }
  v17 = 0;
  for ( i = 0; ; ++i )
  {
    if ( i >= numEntriesReturned || v17 >= v11 )
    {
      *a3 = v4;
      *a2 = v11;
      goto LABEL_59;
    }
    v19 = entries[i];
    v20 = v19->inboundSa;
    if ( v20 && (unsigned int)FwMatchEndpointsWithIkeTraffic(a1, (struct IKEEXT_TRAFFIC0_ *)&v20->traffic) )
    {
      v5 = FwCopyIpsecSa(1, v19->saContextId, v20, v4 + 120LL * v17);
      v6 = v5;
      if ( v5 )
      {
        v7 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        {
          v8 = 23;
          goto LABEL_6;
        }
        goto LABEL_58;
      }
      ++v17;
    }
    v21 = v19->outboundSa;
    if ( v21 )
    {
      if ( (unsigned int)FwMatchEndpointsWithIkeTraffic(a1, (struct IKEEXT_TRAFFIC0_ *)&v21->traffic) )
        break;
    }
LABEL_50:
    ;
  }
  v5 = FwCopyIpsecSa(2, v19->saContextId, v21, v4 + 120LL * v17);
  v6 = v5;
  if ( !v5 )
  {
    ++v17;
    goto LABEL_50;
  }
  v7 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    v8 = 24;
    goto LABEL_6;
  }
LABEL_58:
  FwFree(v4);
LABEL_59:
  if ( entries )
    FwpmFreeMemory0((void **)&entries);
LABEL_61:
  if ( enumHandle )
    IPsecSaContextDestroyEnumHandle0(engineHandle, enumHandle);
  if ( engineHandle )
    FwpmEngineClose0(engineHandle);
  return v6;
}

```

## disassembly

```asm
0x1800b6748  mov     [rsp-8+arg_18], rbx
0x1800b674d  push    rbp
0x1800b674e  push    rsi
0x1800b674f  push    rdi
0x1800b6750  push    r12
0x1800b6752  push    r13
0x1800b6754  push    r14
0x1800b6756  push    r15
0x1800b6758  lea     rbp, [rsp-27h]
0x1800b675d  sub     rsp, 0D0h
0x1800b6764  mov     rax, cs:__security_cookie
0x1800b676b  xor     rax, rsp
0x1800b676e  mov     [rbp+57h+var_38], rax
0x1800b6772  xor     r15d, r15d
0x1800b6775  mov     [rbp+57h+var_C8], r8
0x1800b6779  mov     [rdx], r15d
0x1800b677c  mov     r12, rcx
0x1800b677f  mov     [r8], r15
0x1800b6782  mov     r13d, r15d
0x1800b6785  mov     [rbp+57h+var_C0], rdx
0x1800b6789  mov     [rbp+57h+var_D0], rcx
0x1800b678d  mov     [rbp+57h+var_B0], r15
0x1800b6791  mov     [rbp+57h+enumHandle], r15
0x1800b6795  mov     [rbp+57h+entries], r15
0x1800b6799  mov     [rbp+57h+numEntriesReturned], r15d
0x1800b679d  mov     [rbp+57h+var_A0], r15
0x1800b67a1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BugFix_FwBfeSessions@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_FwBfeSessions@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_FwBfeSessions> `wil::Feature<__WilFeatureTraits_Feature_BugFix_FwBfeSessions>::GetImpl(void)'::`2'::impl
0x1800b67a8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_FwBfeSessions@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_FwBfeSessions>::__private_IsEnabled(void)
0x1800b67ad  xor     r8d, r8d; authIdentity
0x1800b67b0  lea     edx, [r15+0Ah]; authnService
0x1800b67b4  xor     ecx, ecx; serverName
0x1800b67b6  test    al, al
0x1800b67b8  jz      loc_1800B683E
0x1800b67be  lea     rax, aFirewallEnumPh; "Firewall Enum Phase2 SAs"
0x1800b67c5  mov     qword ptr [rbp+57h+session.sessionKey.Data1], r15
0x1800b67c9  mov     [rbp+57h+session.displayData.name], rax
0x1800b67cd  lea     r9, [rbp+57h+session]; session
0x1800b67d1  xor     eax, eax
0x1800b67d3  mov     qword ptr [rbp+57h+session.sessionKey.Data4], r15
0x1800b67d7  mov     dword ptr [rbp+57h+session+2Ch], eax
0x1800b67da  xorps   xmm0, xmm0
0x1800b67dd  lea     rax, [rbp+57h+var_B0]
0x1800b67e1  mov     [rbp+57h+session.displayData.description], r15
0x1800b67e5  mov     [rsp+100h+engineHandle], rax; engineHandle
0x1800b67ea  mov     [rbp+57h+session.flags], r15d
0x1800b67ee  mov     qword ptr [rbp+57h+session.txnWaitTimeoutInMSec], 112A880h
0x1800b67f6  movdqa  xmmword ptr [rbp+57h+session.sid], xmm0
0x1800b67fb  mov     qword ptr [rbp+57h+session.kernelMode], r15
0x1800b67ff  call    cs:__imp_FwpmEngineOpen0
0x1800b6806  nop     dword ptr [rax+rax+00h]
0x1800b680b  mov     ebx, eax
0x1800b680d  test    eax, eax
0x1800b680f  jz      short loc_1800B6884
0x1800b6811  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b6818  lea     rdx, WPP_GLOBAL_Control
0x1800b681f  cmp     rcx, rdx
0x1800b6822  jz      loc_1800B6B4F
0x1800b6828  test    byte ptr [rcx+1Ch], 1
0x1800b682c  jz      loc_1800B6B4F
0x1800b6832  lea     edx, [r15+11h]
0x1800b6836  mov     r9d, eax
0x1800b6839  jmp     loc_1800B6A31
0x1800b683e  lea     rax, [rbp+57h+var_B0]
0x1800b6842  xor     r9d, r9d; session
0x1800b6845  mov     [rsp+100h+engineHandle], rax; engineHandle
0x1800b684a  call    cs:__imp_FwpmEngineOpen0
0x1800b6851  nop     dword ptr [rax+rax+00h]
0x1800b6856  mov     ebx, eax
0x1800b6858  test    eax, eax
0x1800b685a  jz      short loc_1800B6884
0x1800b685c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b6863  lea     rdx, WPP_GLOBAL_Control
0x1800b686a  cmp     rcx, rdx
0x1800b686d  jz      loc_1800B6B4F
0x1800b6873  test    byte ptr [rcx+1Ch], 1
0x1800b6877  jz      loc_1800B6B4F
0x1800b687d  mov     edx, 12h
0x1800b6882  jmp     short loc_1800B6836
0x1800b6884  mov     rcx, [rbp+57h+var_B0]; engineHandle
0x1800b6888  lea     r8, [rbp+57h+enumHandle]; enumHandle
0x1800b688c  xor     edx, edx; enumTemplate
0x1800b688e  call    cs:__imp_IPsecSaContextCreateEnumHandle0
0x1800b6895  nop     dword ptr [rax+rax+00h]
0x1800b689a  mov     ebx, eax
0x1800b689c  test    eax, eax
0x1800b689e  jz      short loc_1800B68CB
0x1800b68a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b68a7  lea     rdx, WPP_GLOBAL_Control
0x1800b68ae  cmp     rcx, rdx
0x1800b68b1  jz      loc_1800B6B4F
0x1800b68b7  test    byte ptr [rcx+1Ch], 1
0x1800b68bb  jz      loc_1800B6B4F
0x1800b68c1  mov     edx, 13h
0x1800b68c6  jmp     loc_1800B6836
0x1800b68cb  mov     rdx, [rbp+57h+enumHandle]; enumHandle
0x1800b68cf  lea     rax, [rbp+57h+numEntriesReturned]
0x1800b68d3  mov     rcx, [rbp+57h+var_B0]; engineHandle
0x1800b68d7  lea     r9, [rbp+57h+entries]; entries
0x1800b68db  or      r8d, 0FFFFFFFFh; numEntriesRequested
0x1800b68df  mov     [rsp+100h+engineHandle], rax; numEntriesReturned
0x1800b68e4  call    cs:__imp_IPsecSaContextEnum0
0x1800b68eb  nop     dword ptr [rax+rax+00h]
0x1800b68f0  mov     ebx, eax
0x1800b68f2  test    eax, eax
0x1800b68f4  jz      short loc_1800B6921
0x1800b68f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b68fd  lea     rdx, WPP_GLOBAL_Control
0x1800b6904  cmp     rcx, rdx
0x1800b6907  jz      loc_1800B6B4F
0x1800b690d  test    byte ptr [rcx+1Ch], 1
0x1800b6911  jz      loc_1800B6B4F
0x1800b6917  mov     edx, 14h
0x1800b691c  jmp     loc_1800B6836
0x1800b6921  mov     r14d, [rbp+57h+numEntriesReturned]
0x1800b6925  test    r14d, r14d
0x1800b6928  jz      loc_1800B6B5E
0x1800b692e  cmp     [rbp+57h+entries], r15
0x1800b6932  jz      loc_1800B6B74
0x1800b6938  mov     edi, r15d
0x1800b693b  mov     esi, r15d
0x1800b693e  test    r14d, r14d
0x1800b6941  jz      loc_1800B6B5E
0x1800b6947  mov     rax, [rbp+57h+entries]
0x1800b694b  mov     ecx, esi
0x1800b694d  mov     r15, [rax+rcx*8]
0x1800b6951  mov     rdx, [r15+8]
0x1800b6955  test    rdx, rdx
0x1800b6958  jz      short loc_1800B696C
0x1800b695a  add     rdx, 8; struct IKEEXT_TRAFFIC0_ *
0x1800b695e  mov     rcx, r12; struct _tag_FW_ENDPOINTS *
0x1800b6961  call    ?FwMatchEndpointsWithIkeTraffic@@YAHPEAU_tag_FW_ENDPOINTS@@PEAUIKEEXT_TRAFFIC0_@@@Z; FwMatchEndpointsWithIkeTraffic(_tag_FW_ENDPOINTS *,IKEEXT_TRAFFIC0_ *)
0x1800b6966  test    eax, eax
0x1800b6968  jz      short loc_1800B696C
0x1800b696a  inc     edi
0x1800b696c  mov     rdx, [r15+10h]
0x1800b6970  xor     r15d, r15d
0x1800b6973  test    rdx, rdx
0x1800b6976  jz      short loc_1800B698A
0x1800b6978  add     rdx, 8; struct IKEEXT_TRAFFIC0_ *
0x1800b697c  mov     rcx, r12; struct _tag_FW_ENDPOINTS *
0x1800b697f  call    ?FwMatchEndpointsWithIkeTraffic@@YAHPEAU_tag_FW_ENDPOINTS@@PEAUIKEEXT_TRAFFIC0_@@@Z; FwMatchEndpointsWithIkeTraffic(_tag_FW_ENDPOINTS *,IKEEXT_TRAFFIC0_ *)
0x1800b6984  test    eax, eax
0x1800b6986  jz      short loc_1800B698A
0x1800b6988  inc     edi
0x1800b698a  inc     esi
0x1800b698c  cmp     esi, r14d
0x1800b698f  jb      short loc_1800B6947
0x1800b6991  test    edi, edi
0x1800b6993  jz      loc_1800B6B5E
0x1800b6999  mov     ecx, edi
0x1800b699b  lea     r8, [rbp+57h+var_A0]
0x1800b699f  mov     edx, 78h ; 'x'
0x1800b69a4  call    cs:__imp_FwSizeTMultiply
0x1800b69ab  nop     dword ptr [rax+rax+00h]
0x1800b69b0  mov     ecx, eax
0x1800b69b2  call    cs:__imp_FwHResultToWindowsError
0x1800b69b9  nop     dword ptr [rax+rax+00h]
0x1800b69be  mov     ebx, eax
0x1800b69c0  test    eax, eax
0x1800b69c2  jz      short loc_1800B69EF
0x1800b69c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b69cb  lea     rdx, WPP_GLOBAL_Control
0x1800b69d2  cmp     rcx, rdx
0x1800b69d5  jz      loc_1800B6B4F
0x1800b69db  test    byte ptr [rcx+1Ch], 1
0x1800b69df  jz      loc_1800B6B4F
0x1800b69e5  mov     edx, 15h
0x1800b69ea  jmp     loc_1800B6836
0x1800b69ef  mov     rcx, [rbp+57h+var_A0]
0x1800b69f3  call    cs:__imp_FwAlloc
0x1800b69fa  nop     dword ptr [rax+rax+00h]
0x1800b69ff  mov     r13, rax
0x1800b6a02  test    rax, rax
0x1800b6a05  jnz     short loc_1800B6A46
0x1800b6a07  lea     ebx, [rax+0Eh]
0x1800b6a0a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b6a11  lea     rdx, WPP_GLOBAL_Control
0x1800b6a18  cmp     rcx, rdx
0x1800b6a1b  jz      loc_1800B6B4F
0x1800b6a21  test    byte ptr [rcx+1Ch], 1
0x1800b6a25  jz      loc_1800B6B4F
0x1800b6a2b  lea     edx, [rax+16h]
0x1800b6a2e  mov     r9d, ebx
0x1800b6a31  mov     rcx, [rcx+10h]
0x1800b6a35  lea     r8, WPP_79bb214f8d013c8d3517fa004f1c3caf_Traceguids
0x1800b6a3c  call    WPP_SF_d
0x1800b6a41  jmp     loc_1800B6B4F
0x1800b6a46  mov     esi, r15d
0x1800b6a49  mov     r14d, r15d
0x1800b6a4c  mov     eax, ebx
0x1800b6a4e  cmp     r14d, [rbp+57h+numEntriesReturned]
0x1800b6a52  jnb     loc_1800B6B3E
0x1800b6a58  cmp     esi, edi
0x1800b6a5a  jnb     loc_1800B6B3E
0x1800b6a60  mov     rax, [rbp+57h+entries]
0x1800b6a64  mov     ecx, r14d
0x1800b6a67  mov     r12, [rax+rcx*8]
0x1800b6a6b  mov     r15, [r12+8]
0x1800b6a70  test    r15, r15
0x1800b6a73  jz      short loc_1800B6AAB
0x1800b6a75  mov     rcx, [rbp+57h+var_D0]; struct _tag_FW_ENDPOINTS *
0x1800b6a79  lea     rdx, [r15+8]; struct IKEEXT_TRAFFIC0_ *
0x1800b6a7d  call    ?FwMatchEndpointsWithIkeTraffic@@YAHPEAU_tag_FW_ENDPOINTS@@PEAUIKEEXT_TRAFFIC0_@@@Z; FwMatchEndpointsWithIkeTraffic(_tag_FW_ENDPOINTS *,IKEEXT_TRAFFIC0_ *)
0x1800b6a82  test    eax, eax
0x1800b6a84  jz      short loc_1800B6AAB
0x1800b6a86  mov     rdx, [r12]
0x1800b6a8a  mov     r8, r15
0x1800b6a8d  mov     eax, esi
0x1800b6a8f  mov     ecx, 1
0x1800b6a94  imul    r9, rax, 78h ; 'x'
0x1800b6a98  add     r9, r13
0x1800b6a9b  call    ?FwCopyIpsecSa@@YAKW4_tag_FW_DIRECTION@@_KPEAUIPSEC_SA_DETAILS0_@@PEAU_tag_FW_PHASE2_SA_DETAILS@@@Z; FwCopyIpsecSa(_tag_FW_DIRECTION,unsigned __int64,IPSEC_SA_DETAILS0_ *,_tag_FW_PHASE2_SA_DETAILS *)
0x1800b6aa0  xor     r15d, r15d
0x1800b6aa3  mov     ebx, eax
0x1800b6aa5  test    eax, eax
0x1800b6aa7  jnz     short loc_1800B6AF8
0x1800b6aa9  inc     esi
0x1800b6aab  mov     r15, [r12+10h]
0x1800b6ab0  test    r15, r15
0x1800b6ab3  jz      short loc_1800B6AED
0x1800b6ab5  mov     rcx, [rbp+57h+var_D0]; struct _tag_FW_ENDPOINTS *
0x1800b6ab9  lea     rdx, [r15+8]; struct IKEEXT_TRAFFIC0_ *
0x1800b6abd  call    ?FwMatchEndpointsWithIkeTraffic@@YAHPEAU_tag_FW_ENDPOINTS@@PEAUIKEEXT_TRAFFIC0_@@@Z; FwMatchEndpointsWithIkeTraffic(_tag_FW_ENDPOINTS *,IKEEXT_TRAFFIC0_ *)
0x1800b6ac2  test    eax, eax
0x1800b6ac4  jz      short loc_1800B6AED
0x1800b6ac6  mov     rdx, [r12]
0x1800b6aca  mov     r8, r15
0x1800b6acd  mov     eax, esi
0x1800b6acf  mov     ecx, 2
0x1800b6ad4  imul    r9, rax, 78h ; 'x'
0x1800b6ad8  add     r9, r13
0x1800b6adb  call    ?FwCopyIpsecSa@@YAKW4_tag_FW_DIRECTION@@_KPEAUIPSEC_SA_DETAILS0_@@PEAU_tag_FW_PHASE2_SA_DETAILS@@@Z; FwCopyIpsecSa(_tag_FW_DIRECTION,unsigned __int64,IPSEC_SA_DETAILS0_ *,_tag_FW_PHASE2_SA_DETAILS *)
0x1800b6ae0  xor     r15d, r15d
0x1800b6ae3  mov     ebx, eax
0x1800b6ae5  test    eax, eax
0x1800b6ae7  jnz     short loc_1800B6B1B
0x1800b6ae9  inc     esi
0x1800b6aeb  jmp     short loc_1800B6AF0
0x1800b6aed  xor     r15d, r15d
0x1800b6af0  inc     r14d
0x1800b6af3  jmp     loc_1800B6A4C
0x1800b6af8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b6aff  lea     rdx, WPP_GLOBAL_Control
0x1800b6b06  cmp     rcx, rdx
0x1800b6b09  jz      short loc_1800B6B4F
0x1800b6b0b  test    byte ptr [rcx+1Ch], 1
0x1800b6b0f  jz      short loc_1800B6B4F
0x1800b6b11  mov     edx, 17h
0x1800b6b16  jmp     loc_1800B6836
0x1800b6b1b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b6b22  lea     rdx, WPP_GLOBAL_Control
0x1800b6b29  cmp     rcx, rdx
0x1800b6b2c  jz      short loc_1800B6B4F
0x1800b6b2e  test    byte ptr [rcx+1Ch], 1
0x1800b6b32  jz      short loc_1800B6B4F
0x1800b6b34  mov     edx, 18h
0x1800b6b39  jmp     loc_1800B6836
0x1800b6b3e  mov     rcx, [rbp+57h+var_C8]
0x1800b6b42  mov     [rcx], r13
0x1800b6b45  mov     rcx, [rbp+57h+var_C0]
0x1800b6b49  mov     [rcx], edi
0x1800b6b4b  test    eax, eax
0x1800b6b4d  jz      short loc_1800B6B5E
0x1800b6b4f  mov     rcx, r13
0x1800b6b52  call    cs:__imp_FwFree
0x1800b6b59  nop     dword ptr [rax+rax+00h]
0x1800b6b5e  cmp     [rbp+57h+entries], r15
0x1800b6b62  jz      short loc_1800B6B74
0x1800b6b64  lea     rcx, [rbp+57h+entries]; p
0x1800b6b68  call    cs:__imp_FwpmFreeMemory0
0x1800b6b6f  nop     dword ptr [rax+rax+00h]
0x1800b6b74  mov     rdx, [rbp+57h+enumHandle]; enumHandle
0x1800b6b78  test    rdx, rdx
0x1800b6b7b  jz      short loc_1800B6B8D
0x1800b6b7d  mov     rcx, [rbp+57h+var_B0]; engineHandle
0x1800b6b81  call    cs:__imp_IPsecSaContextDestroyEnumHandle0
0x1800b6b88  nop     dword ptr [rax+rax+00h]
0x1800b6b8d  mov     rcx, [rbp+57h+var_B0]; engineHandle
0x1800b6b91  test    rcx, rcx
0x1800b6b94  jz      short loc_1800B6BA2
0x1800b6b96  call    cs:__imp_FwpmEngineClose0
0x1800b6b9d  nop     dword ptr [rax+rax+00h]
0x1800b6ba2  mov     eax, ebx
0x1800b6ba4  mov     rcx, [rbp+57h+var_38]
0x1800b6ba8  xor     rcx, rsp; StackCookie
0x1800b6bab  call    __security_check_cookie
0x1800b6bb0  mov     rbx, [rsp+100h+arg_18]
0x1800b6bb8  add     rsp, 0D0h
0x1800b6bbf  pop     r15
0x1800b6bc1  pop     r14
0x1800b6bc3  pop     r13
0x1800b6bc5  pop     r12
0x1800b6bc7  pop     rdi
0x1800b6bc8  pop     rsi
0x1800b6bc9  pop     rbp
0x1800b6bca  retn
```
