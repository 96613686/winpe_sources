# FwDeletePhase1SAsInternal

- ea: `0x1800af50c`
- end: `0x1800af7f7`
- name: `FwDeletePhase1SAsInternal`
- size: `747`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation`

## callers

- `0x18009aa54`

## callees

- `0x18000af3c`
- `0x18006f520`
- `0x1800873a0`
- `0x1800ad000`
- `0x1800ae4f8`
- `0x1800af50c`

## import_xrefs

- `fwpuclnt!FwpmEngineOpen0` at `0x1800af5aa`
- `fwpuclnt!FwpmEngineOpen0` at `0x1800af5f3`
- `fwpuclnt!FwpmEngineOpen0` at `0x1800af5aa`
- `fwpuclnt!FwpmEngineOpen0` at `0x1800af5f3`
- `fwpuclnt!FwpmEngineClose0` at `0x1800af7c8`
- `fwpuclnt!FwpmEngineClose0` at `0x1800af7c8`
- `fwpuclnt!IkeextSaDeleteById0` at `0x1800af70e`
- `fwpuclnt!IkeextSaDeleteById0` at `0x1800af70e`
- `fwpuclnt!IkeextSaEnum2` at `0x1800af681`
- `fwpuclnt!IkeextSaEnum2` at `0x1800af681`
- `fwpuclnt!FwpmFreeMemory0` at `0x1800af7a6`
- `fwpuclnt!FwpmFreeMemory0` at `0x1800af7a6`
- `fwpuclnt!IkeextSaCreateEnumHandle0` at `0x1800af631`
- `fwpuclnt!IkeextSaCreateEnumHandle0` at `0x1800af631`
- `fwpuclnt!IkeextSaDestroyEnumHandle0` at `0x1800af7b9`
- `fwpuclnt!IkeextSaDestroyEnumHandle0` at `0x1800af7b9`

## string_xrefs

- `0x1800af569`: `Firewall Delete Phase1 SAs`

## pseudocode

```c
__int64 __fastcall FwDeletePhase1SAsInternal(struct _tag_FW_ENDPOINTS *a1, void *a2)
{
  DWORD v3; // eax
  DWORD v4; // ebx
  __int64 v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // r9
  __int64 v9; // rsi
  unsigned int v10; // r14d
  __int64 v11; // r12
  DWORD v12; // eax
  void *p; // [rsp+38h] [rbp-51h] BYREF
  HANDLE engineHandle; // [rsp+40h] [rbp-49h] BYREF
  HANDLE enumHandle; // [rsp+48h] [rbp-41h] BYREF
  FWPM_SESSION0 session; // [rsp+50h] [rbp-39h] BYREF
  unsigned int v19; // [rsp+A0h] [rbp+17h] BYREF

  engineHandle = 0;
  enumHandle = 0;
  p = 0;
  v19 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_FwBfeSessions>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BugFix_FwBfeSessions>::GetImpl'::`2'::impl) )
  {
    *(_QWORD *)&session.sessionKey.Data1 = 0;
    session.displayData.name = L"Firewall Delete Phase1 SAs";
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
        goto LABEL_35;
      v6 = 60;
LABEL_6:
      v7 = *(_QWORD *)(v5 + 16);
      v8 = v3;
      goto LABEL_34;
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
        goto LABEL_35;
      v6 = 61;
      goto LABEL_6;
    }
  }
  v3 = IkeextSaCreateEnumHandle0(engineHandle, 0, &enumHandle);
  v4 = v3;
  if ( v3 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_35;
    v6 = 62;
    goto LABEL_6;
  }
  v3 = IkeextSaEnum2(engineHandle, enumHandle, 0xFFFFFFFFLL, &p, &v19);
  v4 = v3;
  if ( v3 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_35;
    v6 = 63;
    goto LABEL_6;
  }
  if ( !v19 )
    goto LABEL_35;
  if ( p )
  {
    v9 = WPP_GLOBAL_Control;
    v4 = 0;
    v10 = 0;
    while ( 1 )
    {
      v11 = *((_QWORD *)p + v10);
      if ( (unsigned int)FwMatchEndpointsWithIkeTraffic(a1, (struct IKEEXT_TRAFFIC0_ *)(v11 + 24)) )
      {
        v12 = IkeextSaDeleteById0(engineHandle, *(_QWORD *)v11);
        if ( v12 )
        {
          v4 = v12;
          v9 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
            goto LABEL_29;
          WPP_SF_d(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            64,
            WPP_79bb214f8d013c8d3517fa004f1c3caf_Traceguids,
            **((unsigned int **)p + v10));
        }
        else
        {
          FwAuditDeletePhase1SAs(a2, *((struct IKEEXT_SA_DETAILS2_ **)p + v10));
        }
        v9 = WPP_GLOBAL_Control;
      }
LABEL_29:
      if ( ++v10 >= v19 )
      {
        if ( v4 && (_UNKNOWN *)v9 != &WPP_GLOBAL_Control && (*(_BYTE *)(v9 + 28) & 1) != 0 )
        {
          v7 = *(_QWORD *)(v9 + 16);
          v6 = 65;
          v8 = v4;
LABEL_34:
          WPP_SF_d(v7, v6, WPP_79bb214f8d013c8d3517fa004f1c3caf_Traceguids, v8);
        }
LABEL_35:
        if ( p )
          FwpmFreeMemory0(&p);
        break;
      }
    }
  }
  if ( enumHandle )
    IkeextSaDestroyEnumHandle0(engineHandle, enumHandle);
  if ( engineHandle )
    FwpmEngineClose0(engineHandle);
  return v4;
}

```

## disassembly

```asm
0x1800af50c  mov     [rsp-8+arg_10], rbx
0x1800af511  push    rbp
0x1800af512  push    rsi
0x1800af513  push    rdi
0x1800af514  push    r12
0x1800af516  push    r13
0x1800af518  push    r14
0x1800af51a  push    r15
0x1800af51c  lea     rbp, [rsp-27h]
0x1800af521  sub     rsp, 0B0h
0x1800af528  mov     rax, cs:__security_cookie
0x1800af52f  xor     rax, rsp
0x1800af532  mov     [rbp+57h+var_38], rax
0x1800af536  xor     r15d, r15d
0x1800af539  mov     [rbp+57h+var_B0], rcx
0x1800af53d  mov     [rbp+57h+var_A0], r15
0x1800af541  mov     r13, rdx
0x1800af544  mov     [rbp+57h+enumHandle], r15
0x1800af548  mov     [rbp+57h+p], r15
0x1800af54c  mov     [rbp+57h+var_40], r15d
0x1800af550  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BugFix_FwBfeSessions@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_FwBfeSessions@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_FwBfeSessions> `wil::Feature<__WilFeatureTraits_Feature_BugFix_FwBfeSessions>::GetImpl(void)'::`2'::impl
0x1800af557  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_FwBfeSessions@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_FwBfeSessions>::__private_IsEnabled(void)
0x1800af55c  xor     r8d, r8d; authIdentity
0x1800af55f  lea     edx, [r15+0Ah]; authnService
0x1800af563  xor     ecx, ecx; serverName
0x1800af565  test    al, al
0x1800af567  jz      short loc_1800AF5E7
0x1800af569  lea     rax, aFirewallDelete_0; "Firewall Delete Phase1 SAs"
0x1800af570  mov     qword ptr [rbp+57h+session.sessionKey.Data1], r15
0x1800af574  mov     [rbp+57h+session.displayData.name], rax
0x1800af578  lea     r9, [rbp+57h+session]; session
0x1800af57c  xor     eax, eax
0x1800af57e  mov     qword ptr [rbp+57h+session.sessionKey.Data4], r15
0x1800af582  mov     dword ptr [rbp+57h+session+2Ch], eax
0x1800af585  xorps   xmm0, xmm0
0x1800af588  lea     rax, [rbp+57h+var_A0]
0x1800af58c  mov     [rbp+57h+session.displayData.description], r15
0x1800af590  mov     [rsp+0E0h+engineHandle], rax; engineHandle
0x1800af595  mov     [rbp+57h+session.flags], r15d
0x1800af599  mov     qword ptr [rbp+57h+session.txnWaitTimeoutInMSec], 112A880h
0x1800af5a1  movdqa  xmmword ptr [rbp+57h+session.sid], xmm0
0x1800af5a6  mov     qword ptr [rbp+57h+session.kernelMode], r15
0x1800af5aa  call    cs:__imp_FwpmEngineOpen0
0x1800af5b0  mov     ebx, eax
0x1800af5b2  test    eax, eax
0x1800af5b4  jz      short loc_1800AF627
0x1800af5b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800af5bd  lea     rdi, WPP_GLOBAL_Control
0x1800af5c4  cmp     rcx, rdi
0x1800af5c7  jz      loc_1800AF79C
0x1800af5cd  test    byte ptr [rcx+1Ch], 1
0x1800af5d1  jz      loc_1800AF79C
0x1800af5d7  lea     edx, [r15+3Ch]
0x1800af5db  mov     rcx, [rcx+10h]
0x1800af5df  mov     r9d, eax
0x1800af5e2  jmp     loc_1800AF790
0x1800af5e7  lea     rax, [rbp+57h+var_A0]
0x1800af5eb  xor     r9d, r9d; session
0x1800af5ee  mov     [rsp+0E0h+engineHandle], rax; engineHandle
0x1800af5f3  call    cs:__imp_FwpmEngineOpen0
0x1800af5f9  mov     ebx, eax
0x1800af5fb  test    eax, eax
0x1800af5fd  jz      short loc_1800AF627
0x1800af5ff  mov     rcx, cs:WPP_GLOBAL_Control
0x1800af606  lea     rdi, WPP_GLOBAL_Control
0x1800af60d  cmp     rcx, rdi
0x1800af610  jz      loc_1800AF79C
0x1800af616  test    byte ptr [rcx+1Ch], 1
0x1800af61a  jz      loc_1800AF79C
0x1800af620  mov     edx, 3Dh ; '='
0x1800af625  jmp     short loc_1800AF5DB
0x1800af627  mov     rcx, [rbp+57h+var_A0]; engineHandle
0x1800af62b  lea     r8, [rbp+57h+enumHandle]; enumHandle
0x1800af62f  xor     edx, edx; enumTemplate
0x1800af631  call    cs:__imp_IkeextSaCreateEnumHandle0
0x1800af637  mov     ebx, eax
0x1800af639  test    eax, eax
0x1800af63b  jz      short loc_1800AF668
0x1800af63d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800af644  lea     rdi, WPP_GLOBAL_Control
0x1800af64b  cmp     rcx, rdi
0x1800af64e  jz      loc_1800AF79C
0x1800af654  test    byte ptr [rcx+1Ch], 1
0x1800af658  jz      loc_1800AF79C
0x1800af65e  mov     edx, 3Eh ; '>'
0x1800af663  jmp     loc_1800AF5DB
0x1800af668  mov     rdx, [rbp+57h+enumHandle]
0x1800af66c  lea     rax, [rbp+57h+var_40]
0x1800af670  mov     rcx, [rbp+57h+var_A0]
0x1800af674  lea     r9, [rbp+57h+p]
0x1800af678  or      r8d, 0FFFFFFFFh
0x1800af67c  mov     [rsp+0E0h+engineHandle], rax
0x1800af681  call    cs:__imp_IkeextSaEnum2
0x1800af687  mov     ebx, eax
0x1800af689  test    eax, eax
0x1800af68b  jz      short loc_1800AF6B8
0x1800af68d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800af694  lea     rdi, WPP_GLOBAL_Control
0x1800af69b  cmp     rcx, rdi
0x1800af69e  jz      loc_1800AF79C
0x1800af6a4  test    byte ptr [rcx+1Ch], 1
0x1800af6a8  jz      loc_1800AF79C
0x1800af6ae  mov     edx, 3Fh ; '?'
0x1800af6b3  jmp     loc_1800AF5DB
0x1800af6b8  mov     eax, [rbp+57h+var_40]
0x1800af6bb  test    eax, eax
0x1800af6bd  jz      loc_1800AF79C
0x1800af6c3  cmp     [rbp+57h+p], r15
0x1800af6c7  jz      loc_1800AF7AC
0x1800af6cd  mov     rsi, cs:WPP_GLOBAL_Control
0x1800af6d4  mov     ebx, r15d
0x1800af6d7  lea     rdi, WPP_GLOBAL_Control
0x1800af6de  mov     r14d, r15d
0x1800af6e1  test    eax, eax
0x1800af6e3  jz      loc_1800AF775
0x1800af6e9  mov     rax, [rbp+57h+p]
0x1800af6ed  mov     rcx, [rbp+57h+var_B0]; struct _tag_FW_ENDPOINTS *
0x1800af6f1  mov     r15d, r14d
0x1800af6f4  mov     r12, [rax+r15*8]
0x1800af6f8  lea     rdx, [r12+18h]; struct IKEEXT_TRAFFIC0_ *
0x1800af6fd  call    ?FwMatchEndpointsWithIkeTraffic@@YAHPEAU_tag_FW_ENDPOINTS@@PEAUIKEEXT_TRAFFIC0_@@@Z; FwMatchEndpointsWithIkeTraffic(_tag_FW_ENDPOINTS *,IKEEXT_TRAFFIC0_ *)
0x1800af702  test    eax, eax
0x1800af704  jz      short loc_1800AF765
0x1800af706  mov     rdx, [r12]; id
0x1800af70a  mov     rcx, [rbp+57h+var_A0]; engineHandle
0x1800af70e  call    cs:__imp_IkeextSaDeleteById0
0x1800af714  test    eax, eax
0x1800af716  jz      short loc_1800AF74E
0x1800af718  mov     ebx, eax
0x1800af71a  mov     rsi, cs:WPP_GLOBAL_Control
0x1800af721  cmp     rsi, rdi
0x1800af724  jz      short loc_1800AF765
0x1800af726  test    byte ptr [rsi+1Ch], 1
0x1800af72a  jz      short loc_1800AF765
0x1800af72c  mov     rax, [rbp+57h+p]
0x1800af730  lea     r8, WPP_79bb214f8d013c8d3517fa004f1c3caf_Traceguids
0x1800af737  mov     rcx, [rsi+10h]
0x1800af73b  mov     edx, 40h ; '@'
0x1800af740  mov     r9, [rax+r15*8]
0x1800af744  mov     r9d, [r9]
0x1800af747  call    WPP_SF_d
0x1800af74c  jmp     short loc_1800AF75E
0x1800af74e  mov     rdx, [rbp+57h+p]
0x1800af752  mov     rcx, r13; void *
0x1800af755  mov     rdx, [rdx+r15*8]; struct IKEEXT_SA_DETAILS2_ *
0x1800af759  call    ?FwAuditDeletePhase1SAs@@YAKPEAXPEAUIKEEXT_SA_DETAILS2_@@@Z; FwAuditDeletePhase1SAs(void *,IKEEXT_SA_DETAILS2_ *)
0x1800af75e  mov     rsi, cs:WPP_GLOBAL_Control
0x1800af765  inc     r14d
0x1800af768  cmp     r14d, [rbp+57h+var_40]
0x1800af76c  jb      loc_1800AF6E9
0x1800af772  xor     r15d, r15d
0x1800af775  test    ebx, ebx
0x1800af777  jz      short loc_1800AF79C
0x1800af779  cmp     rsi, rdi
0x1800af77c  jz      short loc_1800AF79C
0x1800af77e  test    byte ptr [rsi+1Ch], 1
0x1800af782  jz      short loc_1800AF79C
0x1800af784  mov     rcx, [rsi+10h]
0x1800af788  mov     edx, 41h ; 'A'
0x1800af78d  mov     r9d, ebx
0x1800af790  lea     r8, WPP_79bb214f8d013c8d3517fa004f1c3caf_Traceguids
0x1800af797  call    WPP_SF_d
0x1800af79c  cmp     [rbp+57h+p], r15
0x1800af7a0  jz      short loc_1800AF7AC
0x1800af7a2  lea     rcx, [rbp+57h+p]; p
0x1800af7a6  call    cs:__imp_FwpmFreeMemory0
0x1800af7ac  mov     rdx, [rbp+57h+enumHandle]; enumHandle
0x1800af7b0  test    rdx, rdx
0x1800af7b3  jz      short loc_1800AF7BF
0x1800af7b5  mov     rcx, [rbp+57h+var_A0]; engineHandle
0x1800af7b9  call    cs:__imp_IkeextSaDestroyEnumHandle0
0x1800af7bf  mov     rcx, [rbp+57h+var_A0]; engineHandle
0x1800af7c3  test    rcx, rcx
0x1800af7c6  jz      short loc_1800AF7CE
0x1800af7c8  call    cs:__imp_FwpmEngineClose0
0x1800af7ce  mov     eax, ebx
0x1800af7d0  mov     rcx, [rbp+57h+var_38]
0x1800af7d4  xor     rcx, rsp; StackCookie
0x1800af7d7  call    __security_check_cookie
0x1800af7dc  mov     rbx, [rsp+0E0h+arg_10]
0x1800af7e4  add     rsp, 0B0h
0x1800af7eb  pop     r15
0x1800af7ed  pop     r14
0x1800af7ef  pop     r13
0x1800af7f1  pop     r12
0x1800af7f3  pop     rdi
0x1800af7f4  pop     rsi
0x1800af7f5  pop     rbp
0x1800af7f6  retn
```
