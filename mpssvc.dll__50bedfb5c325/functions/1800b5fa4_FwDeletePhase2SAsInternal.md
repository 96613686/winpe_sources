# FwDeletePhase2SAsInternal

- ea: `0x1800b5fa4`
- end: `0x1800b62fc`
- name: `FwDeletePhase2SAsInternal`
- size: `856`
- prototype: `__int64 __fastcall(struct _tag_FW_ENDPOINTS *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation`

## callers

- `0x18009ff70`

## callees

- `0x18000a710`
- `0x1800729c0`
- `0x18008b9f8`
- `0x1800b37e8`
- `0x1800b4bc4`
- `0x1800b5fa4`

## import_xrefs

- `fwpuclnt!FwpmEngineOpen0` at `0x1800b6046`
- `fwpuclnt!FwpmEngineOpen0` at `0x1800b6095`
- `fwpuclnt!FwpmEngineOpen0` at `0x1800b6046`
- `fwpuclnt!FwpmEngineOpen0` at `0x1800b6095`
- `fwpuclnt!FwpmEngineClose0` at `0x1800b62c6`
- `fwpuclnt!FwpmEngineClose0` at `0x1800b62c6`
- `fwpuclnt!IPsecSaContextCreateEnumHandle0` at `0x1800b60d9`
- `fwpuclnt!IPsecSaContextCreateEnumHandle0` at `0x1800b60d9`
- `fwpuclnt!IPsecSaContextDeleteById0` at `0x1800b61e5`
- `fwpuclnt!IPsecSaContextDeleteById0` at `0x1800b61e5`
- `fwpuclnt!IPsecSaContextEnum0` at `0x1800b612f`
- `fwpuclnt!IPsecSaContextEnum0` at `0x1800b612f`
- `fwpuclnt!FwpmFreeMemory0` at `0x1800b6298`
- `fwpuclnt!FwpmFreeMemory0` at `0x1800b6298`
- `fwpuclnt!IPsecSaContextDestroyEnumHandle0` at `0x1800b62b1`
- `fwpuclnt!IPsecSaContextDestroyEnumHandle0` at `0x1800b62b1`

## string_xrefs

- `0x1800b6005`: `Firewall Delete Phase2 SAs`

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
0x1800b5fa4  mov     [rsp-8+arg_10], rbx
0x1800b5fa9  push    rbp
0x1800b5faa  push    rsi
0x1800b5fab  push    rdi
0x1800b5fac  push    r12
0x1800b5fae  push    r13
0x1800b5fb0  push    r14
0x1800b5fb2  push    r15
0x1800b5fb4  lea     rbp, [rsp-27h]
0x1800b5fb9  sub     rsp, 0B0h
0x1800b5fc0  mov     rax, cs:__security_cookie
0x1800b5fc7  xor     rax, rsp
0x1800b5fca  mov     [rbp+57h+var_38], rax
0x1800b5fce  xor     r15d, r15d
0x1800b5fd1  mov     [rbp+57h+var_B0], rdx
0x1800b5fd5  mov     [rbp+57h+var_A0], r15
0x1800b5fd9  mov     r13, rcx
0x1800b5fdc  mov     [rbp+57h+enumHandle], r15
0x1800b5fe0  mov     [rbp+57h+entries], r15
0x1800b5fe4  mov     [rbp+57h+numEntriesReturned], r15d
0x1800b5fe8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BugFix_FwBfeSessions@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_FwBfeSessions@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_FwBfeSessions> `wil::Feature<__WilFeatureTraits_Feature_BugFix_FwBfeSessions>::GetImpl(void)'::`2'::impl
0x1800b5fef  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_FwBfeSessions@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_FwBfeSessions>::__private_IsEnabled(void)
0x1800b5ff4  xor     r8d, r8d; authIdentity
0x1800b5ff7  lea     edx, [r15+0Ah]; authnService
0x1800b5ffb  xor     ecx, ecx; serverName
0x1800b5ffd  test    al, al
0x1800b5fff  jz      loc_1800B6089
0x1800b6005  lea     rax, aFirewallDelete; "Firewall Delete Phase2 SAs"
0x1800b600c  mov     qword ptr [rbp+57h+session.sessionKey.Data1], r15
0x1800b6010  mov     [rbp+57h+session.displayData.name], rax
0x1800b6014  lea     r9, [rbp+57h+session]; session
0x1800b6018  xor     eax, eax
0x1800b601a  mov     qword ptr [rbp+57h+session.sessionKey.Data4], r15
0x1800b601e  mov     dword ptr [rbp+57h+session+2Ch], eax
0x1800b6021  xorps   xmm0, xmm0
0x1800b6024  lea     rax, [rbp+57h+var_A0]
0x1800b6028  mov     [rbp+57h+session.displayData.description], r15
0x1800b602c  mov     [rsp+0E0h+engineHandle], rax; engineHandle
0x1800b6031  mov     [rbp+57h+session.flags], r15d
0x1800b6035  mov     qword ptr [rbp+57h+session.txnWaitTimeoutInMSec], 112A880h
0x1800b603d  movdqa  xmmword ptr [rbp+57h+session.sid], xmm0
0x1800b6042  mov     qword ptr [rbp+57h+session.kernelMode], r15
0x1800b6046  call    cs:__imp_FwpmEngineOpen0
0x1800b604d  nop     dword ptr [rax+rax+00h]
0x1800b6052  mov     ebx, eax
0x1800b6054  test    eax, eax
0x1800b6056  jz      short loc_1800B60CF
0x1800b6058  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b605f  lea     rdi, WPP_GLOBAL_Control
0x1800b6066  cmp     rcx, rdi
0x1800b6069  jz      loc_1800B628E
0x1800b606f  test    byte ptr [rcx+1Ch], 1
0x1800b6073  jz      loc_1800B628E
0x1800b6079  lea     edx, [r15+42h]
0x1800b607d  mov     rcx, [rcx+10h]
0x1800b6081  mov     r9d, eax
0x1800b6084  jmp     loc_1800B6282
0x1800b6089  lea     rax, [rbp+57h+var_A0]
0x1800b608d  xor     r9d, r9d; session
0x1800b6090  mov     [rsp+0E0h+engineHandle], rax; engineHandle
0x1800b6095  call    cs:__imp_FwpmEngineOpen0
0x1800b609c  nop     dword ptr [rax+rax+00h]
0x1800b60a1  mov     ebx, eax
0x1800b60a3  test    eax, eax
0x1800b60a5  jz      short loc_1800B60CF
0x1800b60a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b60ae  lea     rdi, WPP_GLOBAL_Control
0x1800b60b5  cmp     rcx, rdi
0x1800b60b8  jz      loc_1800B628E
0x1800b60be  test    byte ptr [rcx+1Ch], 1
0x1800b60c2  jz      loc_1800B628E
0x1800b60c8  mov     edx, 43h ; 'C'
0x1800b60cd  jmp     short loc_1800B607D
0x1800b60cf  mov     rcx, [rbp+57h+var_A0]; engineHandle
0x1800b60d3  lea     r8, [rbp+57h+enumHandle]; enumHandle
0x1800b60d7  xor     edx, edx; enumTemplate
0x1800b60d9  call    cs:__imp_IPsecSaContextCreateEnumHandle0
0x1800b60e0  nop     dword ptr [rax+rax+00h]
0x1800b60e5  mov     ebx, eax
0x1800b60e7  test    eax, eax
0x1800b60e9  jz      short loc_1800B6116
0x1800b60eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b60f2  lea     rdi, WPP_GLOBAL_Control
0x1800b60f9  cmp     rcx, rdi
0x1800b60fc  jz      loc_1800B628E
0x1800b6102  test    byte ptr [rcx+1Ch], 1
0x1800b6106  jz      loc_1800B628E
0x1800b610c  mov     edx, 44h ; 'D'
0x1800b6111  jmp     loc_1800B607D
0x1800b6116  mov     rdx, [rbp+57h+enumHandle]; enumHandle
0x1800b611a  lea     rax, [rbp+57h+numEntriesReturned]
0x1800b611e  mov     rcx, [rbp+57h+var_A0]; engineHandle
0x1800b6122  lea     r9, [rbp+57h+entries]; entries
0x1800b6126  or      r8d, 0FFFFFFFFh; numEntriesRequested
0x1800b612a  mov     [rsp+0E0h+engineHandle], rax; numEntriesReturned
0x1800b612f  call    cs:__imp_IPsecSaContextEnum0
0x1800b6136  nop     dword ptr [rax+rax+00h]
0x1800b613b  mov     ebx, eax
0x1800b613d  test    eax, eax
0x1800b613f  jz      short loc_1800B616C
0x1800b6141  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b6148  lea     rdi, WPP_GLOBAL_Control
0x1800b614f  cmp     rcx, rdi
0x1800b6152  jz      loc_1800B628E
0x1800b6158  test    byte ptr [rcx+1Ch], 1
0x1800b615c  jz      loc_1800B628E
0x1800b6162  mov     edx, 45h ; 'E'
0x1800b6167  jmp     loc_1800B607D
0x1800b616c  mov     eax, [rbp+57h+numEntriesReturned]
0x1800b616f  test    eax, eax
0x1800b6171  jz      loc_1800B628E
0x1800b6177  cmp     [rbp+57h+entries], r15
0x1800b617b  jz      loc_1800B62A4
0x1800b6181  mov     rsi, cs:WPP_GLOBAL_Control
0x1800b6188  mov     ebx, r15d
0x1800b618b  lea     rdi, WPP_GLOBAL_Control
0x1800b6192  mov     r14d, r15d
0x1800b6195  test    eax, eax
0x1800b6197  jz      loc_1800B6267
0x1800b619d  mov     rax, [rbp+57h+entries]
0x1800b61a1  mov     r12d, r14d
0x1800b61a4  mov     r15, [rax+r12*8]
0x1800b61a8  mov     rdx, [r15+8]
0x1800b61ac  test    rdx, rdx
0x1800b61af  jz      short loc_1800B61C1
0x1800b61b1  add     rdx, 8; struct IKEEXT_TRAFFIC0_ *
0x1800b61b5  mov     rcx, r13; struct _tag_FW_ENDPOINTS *
0x1800b61b8  call    ?FwMatchEndpointsWithIkeTraffic@@YAHPEAU_tag_FW_ENDPOINTS@@PEAUIKEEXT_TRAFFIC0_@@@Z; FwMatchEndpointsWithIkeTraffic(_tag_FW_ENDPOINTS *,IKEEXT_TRAFFIC0_ *)
0x1800b61bd  test    eax, eax
0x1800b61bf  jnz     short loc_1800B61DE
0x1800b61c1  mov     rdx, [r15+10h]
0x1800b61c5  test    rdx, rdx
0x1800b61c8  jz      loc_1800B6257
0x1800b61ce  add     rdx, 8; struct IKEEXT_TRAFFIC0_ *
0x1800b61d2  mov     rcx, r13; struct _tag_FW_ENDPOINTS *
0x1800b61d5  call    ?FwMatchEndpointsWithIkeTraffic@@YAHPEAU_tag_FW_ENDPOINTS@@PEAUIKEEXT_TRAFFIC0_@@@Z; FwMatchEndpointsWithIkeTraffic(_tag_FW_ENDPOINTS *,IKEEXT_TRAFFIC0_ *)
0x1800b61da  test    eax, eax
0x1800b61dc  jz      short loc_1800B6257
0x1800b61de  mov     rdx, [r15]; id
0x1800b61e1  mov     rcx, [rbp+57h+var_A0]; engineHandle
0x1800b61e5  call    cs:__imp_IPsecSaContextDeleteById0
0x1800b61ec  nop     dword ptr [rax+rax+00h]
0x1800b61f1  xor     r15d, r15d
0x1800b61f4  test    eax, eax
0x1800b61f6  jz      short loc_1800B6234
0x1800b61f8  mov     ebx, eax
0x1800b61fa  mov     rsi, cs:WPP_GLOBAL_Control
0x1800b6201  cmp     rsi, rdi
0x1800b6204  jz      short loc_1800B625A
0x1800b6206  test    byte ptr [rsi+1Ch], 2
0x1800b620a  jz      short loc_1800B625A
0x1800b620c  mov     rax, [rbp+57h+entries]
0x1800b6210  lea     edx, [r15+46h]
0x1800b6214  mov     rcx, [rsi+10h]
0x1800b6218  lea     r8, WPP_79bb214f8d013c8d3517fa004f1c3caf_Traceguids
0x1800b621f  mov     r9, [rax+r12*8]
0x1800b6223  mov     r9d, [r9]
0x1800b6226  call    WPP_SF_d
0x1800b622b  mov     rsi, cs:WPP_GLOBAL_Control
0x1800b6232  jmp     short loc_1800B625A
0x1800b6234  mov     rax, [rbp+57h+entries]
0x1800b6238  mov     rdx, [rax+r12*8]
0x1800b623c  mov     r8, [rdx+8]
0x1800b6240  test    r8, r8
0x1800b6243  jnz     short loc_1800B6249
0x1800b6245  mov     r8, [rdx+10h]; struct IPSEC_SA_DETAILS0_ *
0x1800b6249  mov     rdx, [rdx]; unsigned __int64
0x1800b624c  mov     rcx, [rbp+57h+var_B0]; void *
0x1800b6250  call    ?FwAuditDeletePhase2SAs@@YAKPEAX_KPEAUIPSEC_SA_DETAILS0_@@@Z; FwAuditDeletePhase2SAs(void *,unsigned __int64,IPSEC_SA_DETAILS0_ *)
0x1800b6255  jmp     short loc_1800B622B
0x1800b6257  xor     r15d, r15d
0x1800b625a  inc     r14d
0x1800b625d  cmp     r14d, [rbp+57h+numEntriesReturned]
0x1800b6261  jb      loc_1800B619D
0x1800b6267  test    ebx, ebx
0x1800b6269  jz      short loc_1800B628E
0x1800b626b  cmp     rsi, rdi
0x1800b626e  jz      short loc_1800B628E
0x1800b6270  test    byte ptr [rsi+1Ch], 1
0x1800b6274  jz      short loc_1800B628E
0x1800b6276  mov     rcx, [rsi+10h]
0x1800b627a  mov     edx, 47h ; 'G'
0x1800b627f  mov     r9d, ebx
0x1800b6282  lea     r8, WPP_79bb214f8d013c8d3517fa004f1c3caf_Traceguids
0x1800b6289  call    WPP_SF_d
0x1800b628e  cmp     [rbp+57h+entries], r15
0x1800b6292  jz      short loc_1800B62A4
0x1800b6294  lea     rcx, [rbp+57h+entries]; p
0x1800b6298  call    cs:__imp_FwpmFreeMemory0
0x1800b629f  nop     dword ptr [rax+rax+00h]
0x1800b62a4  mov     rdx, [rbp+57h+enumHandle]; enumHandle
0x1800b62a8  test    rdx, rdx
0x1800b62ab  jz      short loc_1800B62BD
0x1800b62ad  mov     rcx, [rbp+57h+var_A0]; engineHandle
0x1800b62b1  call    cs:__imp_IPsecSaContextDestroyEnumHandle0
0x1800b62b8  nop     dword ptr [rax+rax+00h]
0x1800b62bd  mov     rcx, [rbp+57h+var_A0]; engineHandle
0x1800b62c1  test    rcx, rcx
0x1800b62c4  jz      short loc_1800B62D2
0x1800b62c6  call    cs:__imp_FwpmEngineClose0
0x1800b62cd  nop     dword ptr [rax+rax+00h]
0x1800b62d2  mov     eax, ebx
0x1800b62d4  mov     rcx, [rbp+57h+var_38]
0x1800b62d8  xor     rcx, rsp; StackCookie
0x1800b62db  call    __security_check_cookie
0x1800b62e0  mov     rbx, [rsp+0E0h+arg_10]
0x1800b62e8  add     rsp, 0B0h
0x1800b62ef  pop     r15
0x1800b62f1  pop     r14
0x1800b62f3  pop     r13
0x1800b62f5  pop     r12
0x1800b62f7  pop     rdi
0x1800b62f8  pop     rsi
0x1800b62f9  pop     rbp
0x1800b62fa  retn
```
