# FwEnumPhase2SAsInternal

- ea: `0x1800aff30`
- end: `0x1800b036d`
- name: `FwEnumPhase2SAsInternal`
- size: `1085`
- prototype: `__int64 __fastcall(struct _tag_FW_ENDPOINTS *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x18009c264`

## callees

- `0x18000af3c`
- `0x18006f520`
- `0x1800873a0`
- `0x1800add40`
- `0x1800ae4f8`
- `0x1800aff30`

## import_xrefs

- `fwbase!FwHResultToWindowsError` at `0x1800b0178`
- `fwbase!FwHResultToWindowsError` at `0x1800b0178`
- `fwbase!FwSizeTMultiply` at `0x1800b0170`
- `fwbase!FwSizeTMultiply` at `0x1800b0170`
- `fwbase!FwAlloc` at `0x1800b01b3`
- `fwbase!FwAlloc` at `0x1800b01b3`
- `fwbase!FwFree` at `0x1800b030c`
- `fwbase!FwFree` at `0x1800b030c`
- `fwpuclnt!FwpmEngineOpen0` at `0x1800affe3`
- `fwpuclnt!FwpmEngineOpen0` at `0x1800b0028`
- `fwpuclnt!FwpmEngineOpen0` at `0x1800affe3`
- `fwpuclnt!FwpmEngineOpen0` at `0x1800b0028`
- `fwpuclnt!FwpmEngineClose0` at `0x1800b033e`
- `fwpuclnt!FwpmEngineClose0` at `0x1800b033e`
- `fwpuclnt!IPsecSaContextCreateEnumHandle0` at `0x1800b0066`
- `fwpuclnt!IPsecSaContextCreateEnumHandle0` at `0x1800b0066`
- `fwpuclnt!IPsecSaContextEnum0` at `0x1800b00b6`
- `fwpuclnt!IPsecSaContextEnum0` at `0x1800b00b6`
- `fwpuclnt!FwpmFreeMemory0` at `0x1800b031c`
- `fwpuclnt!FwpmFreeMemory0` at `0x1800b031c`
- `fwpuclnt!IPsecSaContextDestroyEnumHandle0` at `0x1800b032f`
- `fwpuclnt!IPsecSaContextDestroyEnumHandle0` at `0x1800b032f`

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
0x1800aff30  mov     [rsp-8+arg_18], rbx
0x1800aff35  push    rbp
0x1800aff36  push    rsi
0x1800aff37  push    rdi
0x1800aff38  push    r12
0x1800aff3a  push    r13
0x1800aff3c  push    r14
0x1800aff3e  push    r15
0x1800aff40  lea     rbp, [rsp-27h]
0x1800aff45  sub     rsp, 0D0h
0x1800aff4c  mov     rax, cs:__security_cookie
0x1800aff53  xor     rax, rsp
0x1800aff56  mov     [rbp+57h+var_38], rax
0x1800aff5a  xor     r15d, r15d
0x1800aff5d  mov     [rbp+57h+var_C8], r8
0x1800aff61  mov     [rdx], r15d
0x1800aff64  mov     r12, rcx
0x1800aff67  mov     [r8], r15
0x1800aff6a  mov     r13d, r15d
0x1800aff6d  mov     [rbp+57h+var_C0], rdx
0x1800aff71  mov     [rbp+57h+var_D0], rcx
0x1800aff75  mov     [rbp+57h+var_B0], r15
0x1800aff79  mov     [rbp+57h+enumHandle], r15
0x1800aff7d  mov     [rbp+57h+entries], r15
0x1800aff81  mov     [rbp+57h+numEntriesReturned], r15d
0x1800aff85  mov     [rbp+57h+var_A0], r15
0x1800aff89  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BugFix_FwBfeSessions@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_FwBfeSessions@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_FwBfeSessions> `wil::Feature<__WilFeatureTraits_Feature_BugFix_FwBfeSessions>::GetImpl(void)'::`2'::impl
0x1800aff90  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_FwBfeSessions@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_FwBfeSessions>::__private_IsEnabled(void)
0x1800aff95  xor     r8d, r8d; authIdentity
0x1800aff98  lea     edx, [r15+0Ah]; authnService
0x1800aff9c  xor     ecx, ecx; serverName
0x1800aff9e  test    al, al
0x1800affa0  jz      short loc_1800B001C
0x1800affa2  lea     rax, aFirewallEnumPh; "Firewall Enum Phase2 SAs"
0x1800affa9  mov     qword ptr [rbp+57h+session.sessionKey.Data1], r15
0x1800affad  mov     [rbp+57h+session.displayData.name], rax
0x1800affb1  lea     r9, [rbp+57h+session]; session
0x1800affb5  xor     eax, eax
0x1800affb7  mov     qword ptr [rbp+57h+session.sessionKey.Data4], r15
0x1800affbb  mov     dword ptr [rbp+57h+session+2Ch], eax
0x1800affbe  xorps   xmm0, xmm0
0x1800affc1  lea     rax, [rbp+57h+var_B0]
0x1800affc5  mov     [rbp+57h+session.displayData.description], r15
0x1800affc9  mov     [rsp+100h+engineHandle], rax; engineHandle
0x1800affce  mov     [rbp+57h+session.flags], r15d
0x1800affd2  mov     qword ptr [rbp+57h+session.txnWaitTimeoutInMSec], 112A880h
0x1800affda  movdqa  xmmword ptr [rbp+57h+session.sid], xmm0
0x1800affdf  mov     qword ptr [rbp+57h+session.kernelMode], r15
0x1800affe3  call    cs:__imp_FwpmEngineOpen0
0x1800affe9  mov     ebx, eax
0x1800affeb  test    eax, eax
0x1800affed  jz      short loc_1800B005C
0x1800affef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800afff6  lea     rdx, WPP_GLOBAL_Control
0x1800afffd  cmp     rcx, rdx
0x1800b0000  jz      loc_1800B0309
0x1800b0006  test    byte ptr [rcx+1Ch], 1
0x1800b000a  jz      loc_1800B0309
0x1800b0010  lea     edx, [r15+11h]
0x1800b0014  mov     r9d, eax
0x1800b0017  jmp     loc_1800B01EB
0x1800b001c  lea     rax, [rbp+57h+var_B0]
0x1800b0020  xor     r9d, r9d; session
0x1800b0023  mov     [rsp+100h+engineHandle], rax; engineHandle
0x1800b0028  call    cs:__imp_FwpmEngineOpen0
0x1800b002e  mov     ebx, eax
0x1800b0030  test    eax, eax
0x1800b0032  jz      short loc_1800B005C
0x1800b0034  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b003b  lea     rdx, WPP_GLOBAL_Control
0x1800b0042  cmp     rcx, rdx
0x1800b0045  jz      loc_1800B0309
0x1800b004b  test    byte ptr [rcx+1Ch], 1
0x1800b004f  jz      loc_1800B0309
0x1800b0055  mov     edx, 12h
0x1800b005a  jmp     short loc_1800B0014
0x1800b005c  mov     rcx, [rbp+57h+var_B0]; engineHandle
0x1800b0060  lea     r8, [rbp+57h+enumHandle]; enumHandle
0x1800b0064  xor     edx, edx; enumTemplate
0x1800b0066  call    cs:__imp_IPsecSaContextCreateEnumHandle0
0x1800b006c  mov     ebx, eax
0x1800b006e  test    eax, eax
0x1800b0070  jz      short loc_1800B009D
0x1800b0072  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b0079  lea     rdx, WPP_GLOBAL_Control
0x1800b0080  cmp     rcx, rdx
0x1800b0083  jz      loc_1800B0309
0x1800b0089  test    byte ptr [rcx+1Ch], 1
0x1800b008d  jz      loc_1800B0309
0x1800b0093  mov     edx, 13h
0x1800b0098  jmp     loc_1800B0014
0x1800b009d  mov     rdx, [rbp+57h+enumHandle]; enumHandle
0x1800b00a1  lea     rax, [rbp+57h+numEntriesReturned]
0x1800b00a5  mov     rcx, [rbp+57h+var_B0]; engineHandle
0x1800b00a9  lea     r9, [rbp+57h+entries]; entries
0x1800b00ad  or      r8d, 0FFFFFFFFh; numEntriesRequested
0x1800b00b1  mov     [rsp+100h+engineHandle], rax; numEntriesReturned
0x1800b00b6  call    cs:__imp_IPsecSaContextEnum0
0x1800b00bc  mov     ebx, eax
0x1800b00be  test    eax, eax
0x1800b00c0  jz      short loc_1800B00ED
0x1800b00c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b00c9  lea     rdx, WPP_GLOBAL_Control
0x1800b00d0  cmp     rcx, rdx
0x1800b00d3  jz      loc_1800B0309
0x1800b00d9  test    byte ptr [rcx+1Ch], 1
0x1800b00dd  jz      loc_1800B0309
0x1800b00e3  mov     edx, 14h
0x1800b00e8  jmp     loc_1800B0014
0x1800b00ed  mov     r14d, [rbp+57h+numEntriesReturned]
0x1800b00f1  test    r14d, r14d
0x1800b00f4  jz      loc_1800B0312
0x1800b00fa  cmp     [rbp+57h+entries], r15
0x1800b00fe  jz      loc_1800B0322
0x1800b0104  mov     edi, r15d
0x1800b0107  mov     esi, r15d
0x1800b010a  test    r14d, r14d
0x1800b010d  jz      loc_1800B0312
0x1800b0113  mov     rax, [rbp+57h+entries]
0x1800b0117  mov     ecx, esi
0x1800b0119  mov     r15, [rax+rcx*8]
0x1800b011d  mov     rdx, [r15+8]
0x1800b0121  test    rdx, rdx
0x1800b0124  jz      short loc_1800B0138
0x1800b0126  add     rdx, 8; struct IKEEXT_TRAFFIC0_ *
0x1800b012a  mov     rcx, r12; struct _tag_FW_ENDPOINTS *
0x1800b012d  call    ?FwMatchEndpointsWithIkeTraffic@@YAHPEAU_tag_FW_ENDPOINTS@@PEAUIKEEXT_TRAFFIC0_@@@Z; FwMatchEndpointsWithIkeTraffic(_tag_FW_ENDPOINTS *,IKEEXT_TRAFFIC0_ *)
0x1800b0132  test    eax, eax
0x1800b0134  jz      short loc_1800B0138
0x1800b0136  inc     edi
0x1800b0138  mov     rdx, [r15+10h]
0x1800b013c  xor     r15d, r15d
0x1800b013f  test    rdx, rdx
0x1800b0142  jz      short loc_1800B0156
0x1800b0144  add     rdx, 8; struct IKEEXT_TRAFFIC0_ *
0x1800b0148  mov     rcx, r12; struct _tag_FW_ENDPOINTS *
0x1800b014b  call    ?FwMatchEndpointsWithIkeTraffic@@YAHPEAU_tag_FW_ENDPOINTS@@PEAUIKEEXT_TRAFFIC0_@@@Z; FwMatchEndpointsWithIkeTraffic(_tag_FW_ENDPOINTS *,IKEEXT_TRAFFIC0_ *)
0x1800b0150  test    eax, eax
0x1800b0152  jz      short loc_1800B0156
0x1800b0154  inc     edi
0x1800b0156  inc     esi
0x1800b0158  cmp     esi, r14d
0x1800b015b  jb      short loc_1800B0113
0x1800b015d  test    edi, edi
0x1800b015f  jz      loc_1800B0312
0x1800b0165  mov     ecx, edi
0x1800b0167  lea     r8, [rbp+57h+var_A0]
0x1800b016b  mov     edx, 78h ; 'x'
0x1800b0170  call    cs:__imp_FwSizeTMultiply
0x1800b0176  mov     ecx, eax
0x1800b0178  call    cs:__imp_FwHResultToWindowsError
0x1800b017e  mov     ebx, eax
0x1800b0180  test    eax, eax
0x1800b0182  jz      short loc_1800B01AF
0x1800b0184  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b018b  lea     rdx, WPP_GLOBAL_Control
0x1800b0192  cmp     rcx, rdx
0x1800b0195  jz      loc_1800B0309
0x1800b019b  test    byte ptr [rcx+1Ch], 1
0x1800b019f  jz      loc_1800B0309
0x1800b01a5  mov     edx, 15h
0x1800b01aa  jmp     loc_1800B0014
0x1800b01af  mov     rcx, [rbp+57h+var_A0]
0x1800b01b3  call    cs:__imp_FwAlloc
0x1800b01b9  mov     r13, rax
0x1800b01bc  test    rax, rax
0x1800b01bf  jnz     short loc_1800B0200
0x1800b01c1  lea     ebx, [rax+0Eh]
0x1800b01c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b01cb  lea     rdx, WPP_GLOBAL_Control
0x1800b01d2  cmp     rcx, rdx
0x1800b01d5  jz      loc_1800B0309
0x1800b01db  test    byte ptr [rcx+1Ch], 1
0x1800b01df  jz      loc_1800B0309
0x1800b01e5  lea     edx, [rax+16h]
0x1800b01e8  mov     r9d, ebx
0x1800b01eb  mov     rcx, [rcx+10h]
0x1800b01ef  lea     r8, WPP_79bb214f8d013c8d3517fa004f1c3caf_Traceguids
0x1800b01f6  call    WPP_SF_d
0x1800b01fb  jmp     loc_1800B0309
0x1800b0200  mov     esi, r15d
0x1800b0203  mov     r14d, r15d
0x1800b0206  mov     eax, ebx
0x1800b0208  cmp     r14d, [rbp+57h+numEntriesReturned]
0x1800b020c  jnb     loc_1800B02F8
0x1800b0212  cmp     esi, edi
0x1800b0214  jnb     loc_1800B02F8
0x1800b021a  mov     rax, [rbp+57h+entries]
0x1800b021e  mov     ecx, r14d
0x1800b0221  mov     r12, [rax+rcx*8]
0x1800b0225  mov     r15, [r12+8]
0x1800b022a  test    r15, r15
0x1800b022d  jz      short loc_1800B0265
0x1800b022f  mov     rcx, [rbp+57h+var_D0]; struct _tag_FW_ENDPOINTS *
0x1800b0233  lea     rdx, [r15+8]; struct IKEEXT_TRAFFIC0_ *
0x1800b0237  call    ?FwMatchEndpointsWithIkeTraffic@@YAHPEAU_tag_FW_ENDPOINTS@@PEAUIKEEXT_TRAFFIC0_@@@Z; FwMatchEndpointsWithIkeTraffic(_tag_FW_ENDPOINTS *,IKEEXT_TRAFFIC0_ *)
0x1800b023c  test    eax, eax
0x1800b023e  jz      short loc_1800B0265
0x1800b0240  mov     rdx, [r12]
0x1800b0244  mov     r8, r15
0x1800b0247  mov     eax, esi
0x1800b0249  mov     ecx, 1
0x1800b024e  imul    r9, rax, 78h ; 'x'
0x1800b0252  add     r9, r13
0x1800b0255  call    ?FwCopyIpsecSa@@YAKW4_tag_FW_DIRECTION@@_KPEAUIPSEC_SA_DETAILS0_@@PEAU_tag_FW_PHASE2_SA_DETAILS@@@Z; FwCopyIpsecSa(_tag_FW_DIRECTION,unsigned __int64,IPSEC_SA_DETAILS0_ *,_tag_FW_PHASE2_SA_DETAILS *)
0x1800b025a  xor     r15d, r15d
0x1800b025d  mov     ebx, eax
0x1800b025f  test    eax, eax
0x1800b0261  jnz     short loc_1800B02B2
0x1800b0263  inc     esi
0x1800b0265  mov     r15, [r12+10h]
0x1800b026a  test    r15, r15
0x1800b026d  jz      short loc_1800B02A7
0x1800b026f  mov     rcx, [rbp+57h+var_D0]; struct _tag_FW_ENDPOINTS *
0x1800b0273  lea     rdx, [r15+8]; struct IKEEXT_TRAFFIC0_ *
0x1800b0277  call    ?FwMatchEndpointsWithIkeTraffic@@YAHPEAU_tag_FW_ENDPOINTS@@PEAUIKEEXT_TRAFFIC0_@@@Z; FwMatchEndpointsWithIkeTraffic(_tag_FW_ENDPOINTS *,IKEEXT_TRAFFIC0_ *)
0x1800b027c  test    eax, eax
0x1800b027e  jz      short loc_1800B02A7
0x1800b0280  mov     rdx, [r12]
0x1800b0284  mov     r8, r15
0x1800b0287  mov     eax, esi
0x1800b0289  mov     ecx, 2
0x1800b028e  imul    r9, rax, 78h ; 'x'
0x1800b0292  add     r9, r13
0x1800b0295  call    ?FwCopyIpsecSa@@YAKW4_tag_FW_DIRECTION@@_KPEAUIPSEC_SA_DETAILS0_@@PEAU_tag_FW_PHASE2_SA_DETAILS@@@Z; FwCopyIpsecSa(_tag_FW_DIRECTION,unsigned __int64,IPSEC_SA_DETAILS0_ *,_tag_FW_PHASE2_SA_DETAILS *)
0x1800b029a  xor     r15d, r15d
0x1800b029d  mov     ebx, eax
0x1800b029f  test    eax, eax
0x1800b02a1  jnz     short loc_1800B02D5
0x1800b02a3  inc     esi
0x1800b02a5  jmp     short loc_1800B02AA
0x1800b02a7  xor     r15d, r15d
0x1800b02aa  inc     r14d
0x1800b02ad  jmp     loc_1800B0206
0x1800b02b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b02b9  lea     rdx, WPP_GLOBAL_Control
0x1800b02c0  cmp     rcx, rdx
0x1800b02c3  jz      short loc_1800B0309
0x1800b02c5  test    byte ptr [rcx+1Ch], 1
0x1800b02c9  jz      short loc_1800B0309
0x1800b02cb  mov     edx, 17h
0x1800b02d0  jmp     loc_1800B0014
0x1800b02d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b02dc  lea     rdx, WPP_GLOBAL_Control
0x1800b02e3  cmp     rcx, rdx
0x1800b02e6  jz      short loc_1800B0309
0x1800b02e8  test    byte ptr [rcx+1Ch], 1
0x1800b02ec  jz      short loc_1800B0309
0x1800b02ee  mov     edx, 18h
0x1800b02f3  jmp     loc_1800B0014
0x1800b02f8  mov     rcx, [rbp+57h+var_C8]
0x1800b02fc  mov     [rcx], r13
0x1800b02ff  mov     rcx, [rbp+57h+var_C0]
0x1800b0303  mov     [rcx], edi
0x1800b0305  test    eax, eax
0x1800b0307  jz      short loc_1800B0312
0x1800b0309  mov     rcx, r13
0x1800b030c  call    cs:__imp_FwFree
0x1800b0312  cmp     [rbp+57h+entries], r15
0x1800b0316  jz      short loc_1800B0322
0x1800b0318  lea     rcx, [rbp+57h+entries]; p
0x1800b031c  call    cs:__imp_FwpmFreeMemory0
0x1800b0322  mov     rdx, [rbp+57h+enumHandle]; enumHandle
0x1800b0326  test    rdx, rdx
0x1800b0329  jz      short loc_1800B0335
0x1800b032b  mov     rcx, [rbp+57h+var_B0]; engineHandle
0x1800b032f  call    cs:__imp_IPsecSaContextDestroyEnumHandle0
0x1800b0335  mov     rcx, [rbp+57h+var_B0]; engineHandle
0x1800b0339  test    rcx, rcx
0x1800b033c  jz      short loc_1800B0344
0x1800b033e  call    cs:__imp_FwpmEngineClose0
0x1800b0344  mov     eax, ebx
0x1800b0346  mov     rcx, [rbp+57h+var_38]
0x1800b034a  xor     rcx, rsp; StackCookie
0x1800b034d  call    __security_check_cookie
0x1800b0352  mov     rbx, [rsp+100h+arg_18]
0x1800b035a  add     rsp, 0D0h
0x1800b0361  pop     r15
0x1800b0363  pop     r14
0x1800b0365  pop     r13
0x1800b0367  pop     r12
0x1800b0369  pop     rdi
0x1800b036a  pop     rsi
0x1800b036b  pop     rbp
0x1800b036c  retn
```
