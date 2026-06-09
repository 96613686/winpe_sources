# FwDeletePhase2SAsInternal

- ea: `0x1800af800`
- end: `0x1800afb23`
- name: `FwDeletePhase2SAsInternal`
- size: `803`
- prototype: `__int64 __fastcall(struct _tag_FW_ENDPOINTS *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation`

## callers

- `0x18009ac38`

## callees

- `0x18000af3c`
- `0x18006f520`
- `0x1800873a0`
- `0x1800ad1e4`
- `0x1800ae4f8`
- `0x1800af800`

## import_xrefs

- `fwpuclnt!FwpmEngineOpen0` at `0x1800af89e`
- `fwpuclnt!FwpmEngineOpen0` at `0x1800af8e7`
- `fwpuclnt!FwpmEngineOpen0` at `0x1800af89e`
- `fwpuclnt!FwpmEngineOpen0` at `0x1800af8e7`
- `fwpuclnt!FwpmEngineClose0` at `0x1800afaf4`
- `fwpuclnt!FwpmEngineClose0` at `0x1800afaf4`
- `fwpuclnt!IPsecSaContextCreateEnumHandle0` at `0x1800af925`
- `fwpuclnt!IPsecSaContextCreateEnumHandle0` at `0x1800af925`
- `fwpuclnt!IPsecSaContextDeleteById0` at `0x1800afa25`
- `fwpuclnt!IPsecSaContextDeleteById0` at `0x1800afa25`
- `fwpuclnt!IPsecSaContextEnum0` at `0x1800af975`
- `fwpuclnt!IPsecSaContextEnum0` at `0x1800af975`
- `fwpuclnt!FwpmFreeMemory0` at `0x1800afad2`
- `fwpuclnt!FwpmFreeMemory0` at `0x1800afad2`
- `fwpuclnt!IPsecSaContextDestroyEnumHandle0` at `0x1800afae5`
- `fwpuclnt!IPsecSaContextDestroyEnumHandle0` at `0x1800afae5`

## string_xrefs

- `0x1800af85d`: `Firewall Delete Phase2 SAs`

## pseudocode

```c
__int64 __fastcall FwDeletePhase2SAsInternal(struct _tag_FW_ENDPOINTS *a1, void *a2)
{
  DWORD v3; // eax
  DWORD v4; // ebx
  __int64 v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // r9
  __int64 v9; // rsi
  int v10; // r14d
  IPSEC_SA_CONTEXT0 *v11; // r15
  IPSEC_SA_DETAILS0 *inboundSa; // rdx
  IPSEC_SA_DETAILS0 *outboundSa; // rdx
  DWORD v14; // eax
  IPSEC_SA_CONTEXT0 *v15; // rdx
  struct IPSEC_SA_DETAILS0_ *v16; // r8
  IPSEC_SA_CONTEXT0 **entries; // [rsp+38h] [rbp-51h] BYREF
  HANDLE engineHandle; // [rsp+40h] [rbp-49h] BYREF
  HANDLE enumHandle; // [rsp+48h] [rbp-41h] BYREF
  FWPM_SESSION0 session; // [rsp+50h] [rbp-39h] BYREF
  UINT32 numEntriesReturned; // [rsp+A0h] [rbp+17h] BYREF

  engineHandle = 0;
  enumHandle = 0;
  entries = 0;
  numEntriesReturned = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_FwBfeSessions>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BugFix_FwBfeSessions>::GetImpl'::`2'::impl) )
  {
    *(_QWORD *)&session.sessionKey.Data1 = 0;
    session.displayData.name = L"Firewall Delete Phase2 SAs";
    *(_QWORD *)session.sessionKey.Data4 = 0;
    memset(&session.processId + 1, 0, 28);
    session.displayData.description = 0;
    session.flags = 0;
    *(_QWORD *)&session.txnWaitTimeoutInMSec = 18000000;
    v3 = FwpmEngineOpen0(0, 0xAu, 0, &session, &engineHandle);
    v4 = v3;
    if ( v3 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_40;
      v6 = 66;
LABEL_6:
      v7 = *(_QWORD *)(v5 + 16);
      v8 = v3;
      goto LABEL_39;
    }
  }
  else
  {
    v3 = FwpmEngineOpen0(0, 0xAu, 0, 0, &engineHandle);
    v4 = v3;
    if ( v3 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_40;
      v6 = 67;
      goto LABEL_6;
    }
  }
  v3 = IPsecSaContextCreateEnumHandle0(engineHandle, 0, &enumHandle);
  v4 = v3;
  if ( v3 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_40;
    v6 = 68;
    goto LABEL_6;
  }
  v3 = IPsecSaContextEnum0(engineHandle, enumHandle, 0xFFFFFFFF, &entries, &numEntriesReturned);
  v4 = v3;
  if ( v3 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_40;
    v6 = 69;
    goto LABEL_6;
  }
  if ( !numEntriesReturned )
    goto LABEL_40;
  if ( entries )
  {
    v9 = WPP_GLOBAL_Control;
    v4 = 0;
    v10 = 0;
    while ( 1 )
    {
      v11 = entries[v10];
      inboundSa = v11->inboundSa;
      if ( !inboundSa
        || !(unsigned int)FwMatchEndpointsWithIkeTraffic(a1, (struct IKEEXT_TRAFFIC0_ *)&inboundSa->traffic) )
      {
        outboundSa = v11->outboundSa;
        if ( !outboundSa
          || !(unsigned int)FwMatchEndpointsWithIkeTraffic(a1, (struct IKEEXT_TRAFFIC0_ *)&outboundSa->traffic) )
        {
          goto LABEL_34;
        }
      }
      v14 = IPsecSaContextDeleteById0(engineHandle, v11->saContextId);
      if ( v14 )
      {
        v4 = v14;
        v9 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) == 0 )
          goto LABEL_34;
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          70,
          WPP_79bb214f8d013c8d3517fa004f1c3caf_Traceguids,
          LODWORD(entries[v10]->saContextId));
      }
      else
      {
        v15 = entries[v10];
        v16 = v15->inboundSa;
        if ( !v16 )
          v16 = v15->outboundSa;
        FwAuditDeletePhase2SAs(a2, v15->saContextId, v16);
      }
      v9 = WPP_GLOBAL_Control;
LABEL_34:
      if ( ++v10 >= numEntriesReturned )
      {
        if ( v4 && (_UNKNOWN *)v9 != &WPP_GLOBAL_Control && (*(_BYTE *)(v9 + 28) & 1) != 0 )
        {
          v7 = *(_QWORD *)(v9 + 16);
          v6 = 71;
          v8 = v4;
LABEL_39:
          WPP_SF_d(v7, v6, WPP_79bb214f8d013c8d3517fa004f1c3caf_Traceguids, v8);
        }
LABEL_40:
        if ( entries )
          FwpmFreeMemory0((void **)&entries);
        break;
      }
    }
  }
  if ( enumHandle )
    IPsecSaContextDestroyEnumHandle0(engineHandle, enumHandle);
  if ( engineHandle )
    FwpmEngineClose0(engineHandle);
  return v4;
}

```

## disassembly

```asm
0x1800af800  mov     [rsp-8+arg_10], rbx
0x1800af805  push    rbp
0x1800af806  push    rsi
0x1800af807  push    rdi
0x1800af808  push    r12
0x1800af80a  push    r13
0x1800af80c  push    r14
0x1800af80e  push    r15
0x1800af810  lea     rbp, [rsp-27h]
0x1800af815  sub     rsp, 0B0h
0x1800af81c  mov     rax, cs:__security_cookie
0x1800af823  xor     rax, rsp
0x1800af826  mov     [rbp+57h+var_38], rax
0x1800af82a  xor     r15d, r15d
0x1800af82d  mov     [rbp+57h+var_B0], rdx
0x1800af831  mov     [rbp+57h+var_A0], r15
0x1800af835  mov     r13, rcx
0x1800af838  mov     [rbp+57h+enumHandle], r15
0x1800af83c  mov     [rbp+57h+entries], r15
0x1800af840  mov     [rbp+57h+numEntriesReturned], r15d
0x1800af844  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BugFix_FwBfeSessions@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_FwBfeSessions@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_FwBfeSessions> `wil::Feature<__WilFeatureTraits_Feature_BugFix_FwBfeSessions>::GetImpl(void)'::`2'::impl
0x1800af84b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_FwBfeSessions@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_FwBfeSessions>::__private_IsEnabled(void)
0x1800af850  xor     r8d, r8d; authIdentity
0x1800af853  lea     edx, [r15+0Ah]; authnService
0x1800af857  xor     ecx, ecx; serverName
0x1800af859  test    al, al
0x1800af85b  jz      short loc_1800AF8DB
0x1800af85d  lea     rax, aFirewallDelete; "Firewall Delete Phase2 SAs"
0x1800af864  mov     qword ptr [rbp+57h+session.sessionKey.Data1], r15
0x1800af868  mov     [rbp+57h+session.displayData.name], rax
0x1800af86c  lea     r9, [rbp+57h+session]; session
0x1800af870  xor     eax, eax
0x1800af872  mov     qword ptr [rbp+57h+session.sessionKey.Data4], r15
0x1800af876  mov     dword ptr [rbp+57h+session+2Ch], eax
0x1800af879  xorps   xmm0, xmm0
0x1800af87c  lea     rax, [rbp+57h+var_A0]
0x1800af880  mov     [rbp+57h+session.displayData.description], r15
0x1800af884  mov     [rsp+0E0h+engineHandle], rax; engineHandle
0x1800af889  mov     [rbp+57h+session.flags], r15d
0x1800af88d  mov     qword ptr [rbp+57h+session.txnWaitTimeoutInMSec], 112A880h
0x1800af895  movdqa  xmmword ptr [rbp+57h+session.sid], xmm0
0x1800af89a  mov     qword ptr [rbp+57h+session.kernelMode], r15
0x1800af89e  call    cs:__imp_FwpmEngineOpen0
0x1800af8a4  mov     ebx, eax
0x1800af8a6  test    eax, eax
0x1800af8a8  jz      short loc_1800AF91B
0x1800af8aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800af8b1  lea     rdi, WPP_GLOBAL_Control
0x1800af8b8  cmp     rcx, rdi
0x1800af8bb  jz      loc_1800AFAC8
0x1800af8c1  test    byte ptr [rcx+1Ch], 1
0x1800af8c5  jz      loc_1800AFAC8
0x1800af8cb  lea     edx, [r15+42h]
0x1800af8cf  mov     rcx, [rcx+10h]
0x1800af8d3  mov     r9d, eax
0x1800af8d6  jmp     loc_1800AFABC
0x1800af8db  lea     rax, [rbp+57h+var_A0]
0x1800af8df  xor     r9d, r9d; session
0x1800af8e2  mov     [rsp+0E0h+engineHandle], rax; engineHandle
0x1800af8e7  call    cs:__imp_FwpmEngineOpen0
0x1800af8ed  mov     ebx, eax
0x1800af8ef  test    eax, eax
0x1800af8f1  jz      short loc_1800AF91B
0x1800af8f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800af8fa  lea     rdi, WPP_GLOBAL_Control
0x1800af901  cmp     rcx, rdi
0x1800af904  jz      loc_1800AFAC8
0x1800af90a  test    byte ptr [rcx+1Ch], 1
0x1800af90e  jz      loc_1800AFAC8
0x1800af914  mov     edx, 43h ; 'C'
0x1800af919  jmp     short loc_1800AF8CF
0x1800af91b  mov     rcx, [rbp+57h+var_A0]; engineHandle
0x1800af91f  lea     r8, [rbp+57h+enumHandle]; enumHandle
0x1800af923  xor     edx, edx; enumTemplate
0x1800af925  call    cs:__imp_IPsecSaContextCreateEnumHandle0
0x1800af92b  mov     ebx, eax
0x1800af92d  test    eax, eax
0x1800af92f  jz      short loc_1800AF95C
0x1800af931  mov     rcx, cs:WPP_GLOBAL_Control
0x1800af938  lea     rdi, WPP_GLOBAL_Control
0x1800af93f  cmp     rcx, rdi
0x1800af942  jz      loc_1800AFAC8
0x1800af948  test    byte ptr [rcx+1Ch], 1
0x1800af94c  jz      loc_1800AFAC8
0x1800af952  mov     edx, 44h ; 'D'
0x1800af957  jmp     loc_1800AF8CF
0x1800af95c  mov     rdx, [rbp+57h+enumHandle]; enumHandle
0x1800af960  lea     rax, [rbp+57h+numEntriesReturned]
0x1800af964  mov     rcx, [rbp+57h+var_A0]; engineHandle
0x1800af968  lea     r9, [rbp+57h+entries]; entries
0x1800af96c  or      r8d, 0FFFFFFFFh; numEntriesRequested
0x1800af970  mov     [rsp+0E0h+engineHandle], rax; numEntriesReturned
0x1800af975  call    cs:__imp_IPsecSaContextEnum0
0x1800af97b  mov     ebx, eax
0x1800af97d  test    eax, eax
0x1800af97f  jz      short loc_1800AF9AC
0x1800af981  mov     rcx, cs:WPP_GLOBAL_Control
0x1800af988  lea     rdi, WPP_GLOBAL_Control
0x1800af98f  cmp     rcx, rdi
0x1800af992  jz      loc_1800AFAC8
0x1800af998  test    byte ptr [rcx+1Ch], 1
0x1800af99c  jz      loc_1800AFAC8
0x1800af9a2  mov     edx, 45h ; 'E'
0x1800af9a7  jmp     loc_1800AF8CF
0x1800af9ac  mov     eax, [rbp+57h+numEntriesReturned]
0x1800af9af  test    eax, eax
0x1800af9b1  jz      loc_1800AFAC8
0x1800af9b7  cmp     [rbp+57h+entries], r15
0x1800af9bb  jz      loc_1800AFAD8
0x1800af9c1  mov     rsi, cs:WPP_GLOBAL_Control
0x1800af9c8  mov     ebx, r15d
0x1800af9cb  lea     rdi, WPP_GLOBAL_Control
0x1800af9d2  mov     r14d, r15d
0x1800af9d5  test    eax, eax
0x1800af9d7  jz      loc_1800AFAA1
0x1800af9dd  mov     rax, [rbp+57h+entries]
0x1800af9e1  mov     r12d, r14d
0x1800af9e4  mov     r15, [rax+r12*8]
0x1800af9e8  mov     rdx, [r15+8]
0x1800af9ec  test    rdx, rdx
0x1800af9ef  jz      short loc_1800AFA01
0x1800af9f1  add     rdx, 8; struct IKEEXT_TRAFFIC0_ *
0x1800af9f5  mov     rcx, r13; struct _tag_FW_ENDPOINTS *
0x1800af9f8  call    ?FwMatchEndpointsWithIkeTraffic@@YAHPEAU_tag_FW_ENDPOINTS@@PEAUIKEEXT_TRAFFIC0_@@@Z; FwMatchEndpointsWithIkeTraffic(_tag_FW_ENDPOINTS *,IKEEXT_TRAFFIC0_ *)
0x1800af9fd  test    eax, eax
0x1800af9ff  jnz     short loc_1800AFA1E
0x1800afa01  mov     rdx, [r15+10h]
0x1800afa05  test    rdx, rdx
0x1800afa08  jz      loc_1800AFA91
0x1800afa0e  add     rdx, 8; struct IKEEXT_TRAFFIC0_ *
0x1800afa12  mov     rcx, r13; struct _tag_FW_ENDPOINTS *
0x1800afa15  call    ?FwMatchEndpointsWithIkeTraffic@@YAHPEAU_tag_FW_ENDPOINTS@@PEAUIKEEXT_TRAFFIC0_@@@Z; FwMatchEndpointsWithIkeTraffic(_tag_FW_ENDPOINTS *,IKEEXT_TRAFFIC0_ *)
0x1800afa1a  test    eax, eax
0x1800afa1c  jz      short loc_1800AFA91
0x1800afa1e  mov     rdx, [r15]; id
0x1800afa21  mov     rcx, [rbp+57h+var_A0]; engineHandle
0x1800afa25  call    cs:__imp_IPsecSaContextDeleteById0
0x1800afa2b  xor     r15d, r15d
0x1800afa2e  test    eax, eax
0x1800afa30  jz      short loc_1800AFA6E
0x1800afa32  mov     ebx, eax
0x1800afa34  mov     rsi, cs:WPP_GLOBAL_Control
0x1800afa3b  cmp     rsi, rdi
0x1800afa3e  jz      short loc_1800AFA94
0x1800afa40  test    byte ptr [rsi+1Ch], 2
0x1800afa44  jz      short loc_1800AFA94
0x1800afa46  mov     rax, [rbp+57h+entries]
0x1800afa4a  lea     edx, [r15+46h]
0x1800afa4e  mov     rcx, [rsi+10h]
0x1800afa52  lea     r8, WPP_79bb214f8d013c8d3517fa004f1c3caf_Traceguids
0x1800afa59  mov     r9, [rax+r12*8]
0x1800afa5d  mov     r9d, [r9]
0x1800afa60  call    WPP_SF_d
0x1800afa65  mov     rsi, cs:WPP_GLOBAL_Control
0x1800afa6c  jmp     short loc_1800AFA94
0x1800afa6e  mov     rax, [rbp+57h+entries]
0x1800afa72  mov     rdx, [rax+r12*8]
0x1800afa76  mov     r8, [rdx+8]
0x1800afa7a  test    r8, r8
0x1800afa7d  jnz     short loc_1800AFA83
0x1800afa7f  mov     r8, [rdx+10h]; struct IPSEC_SA_DETAILS0_ *
0x1800afa83  mov     rdx, [rdx]; unsigned __int64
0x1800afa86  mov     rcx, [rbp+57h+var_B0]; void *
0x1800afa8a  call    ?FwAuditDeletePhase2SAs@@YAKPEAX_KPEAUIPSEC_SA_DETAILS0_@@@Z; FwAuditDeletePhase2SAs(void *,unsigned __int64,IPSEC_SA_DETAILS0_ *)
0x1800afa8f  jmp     short loc_1800AFA65
0x1800afa91  xor     r15d, r15d
0x1800afa94  inc     r14d
0x1800afa97  cmp     r14d, [rbp+57h+numEntriesReturned]
0x1800afa9b  jb      loc_1800AF9DD
0x1800afaa1  test    ebx, ebx
0x1800afaa3  jz      short loc_1800AFAC8
0x1800afaa5  cmp     rsi, rdi
0x1800afaa8  jz      short loc_1800AFAC8
0x1800afaaa  test    byte ptr [rsi+1Ch], 1
0x1800afaae  jz      short loc_1800AFAC8
0x1800afab0  mov     rcx, [rsi+10h]
0x1800afab4  mov     edx, 47h ; 'G'
0x1800afab9  mov     r9d, ebx
0x1800afabc  lea     r8, WPP_79bb214f8d013c8d3517fa004f1c3caf_Traceguids
0x1800afac3  call    WPP_SF_d
0x1800afac8  cmp     [rbp+57h+entries], r15
0x1800afacc  jz      short loc_1800AFAD8
0x1800aface  lea     rcx, [rbp+57h+entries]; p
0x1800afad2  call    cs:__imp_FwpmFreeMemory0
0x1800afad8  mov     rdx, [rbp+57h+enumHandle]; enumHandle
0x1800afadc  test    rdx, rdx
0x1800afadf  jz      short loc_1800AFAEB
0x1800afae1  mov     rcx, [rbp+57h+var_A0]; engineHandle
0x1800afae5  call    cs:__imp_IPsecSaContextDestroyEnumHandle0
0x1800afaeb  mov     rcx, [rbp+57h+var_A0]; engineHandle
0x1800afaef  test    rcx, rcx
0x1800afaf2  jz      short loc_1800AFAFA
0x1800afaf4  call    cs:__imp_FwpmEngineClose0
0x1800afafa  mov     eax, ebx
0x1800afafc  mov     rcx, [rbp+57h+var_38]
0x1800afb00  xor     rcx, rsp; StackCookie
0x1800afb03  call    __security_check_cookie
0x1800afb08  mov     rbx, [rsp+0E0h+arg_10]
0x1800afb10  add     rsp, 0B0h
0x1800afb17  pop     r15
0x1800afb19  pop     r14
0x1800afb1b  pop     r13
0x1800afb1d  pop     r12
0x1800afb1f  pop     rdi
0x1800afb20  pop     rsi
0x1800afb21  pop     rbp
0x1800afb22  retn
```
