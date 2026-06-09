# FwEnumPhase1SAsInternal

- ea: `0x1800afb2c`
- end: `0x1800aff27`
- name: `FwEnumPhase1SAsInternal`
- size: `1019`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x18009c164`

## callees

- `0x18000af3c`
- `0x18006f520`
- `0x1800873a0`
- `0x1800ada04`
- `0x1800ae494`
- `0x1800ae4f8`
- `0x1800af4e0`
- `0x1800afb2c`

## import_xrefs

- `fwbase!FwHResultToWindowsError` at `0x1800afd76`
- `fwbase!FwHResultToWindowsError` at `0x1800afd76`
- `fwbase!FwSizeTMultiply` at `0x1800afd6e`
- `fwbase!FwSizeTMultiply` at `0x1800afd6e`
- `fwbase!FwAlloc` at `0x1800afdb1`
- `fwbase!FwAlloc` at `0x1800afdb1`
- `fwbase!FwFree` at `0x1800afead`
- `fwbase!FwFree` at `0x1800afead`
- `fwpuclnt!FwpmEngineOpen0` at `0x1800afbd8`
- `fwpuclnt!FwpmEngineOpen0` at `0x1800afc1a`
- `fwpuclnt!FwpmEngineOpen0` at `0x1800afbd8`
- `fwpuclnt!FwpmEngineOpen0` at `0x1800afc1a`
- `fwpuclnt!FwpmEngineClose0` at `0x1800afef8`
- `fwpuclnt!FwpmEngineClose0` at `0x1800afef8`
- `fwpuclnt!IkeextSaEnum2` at `0x1800afcc1`
- `fwpuclnt!IkeextSaEnum2` at `0x1800afcc1`
- `fwpuclnt!FwpmFreeMemory0` at `0x1800afed6`
- `fwpuclnt!FwpmFreeMemory0` at `0x1800afed6`
- `fwpuclnt!IkeextSaCreateEnumHandle0` at `0x1800afc5b`
- `fwpuclnt!IkeextSaCreateEnumHandle0` at `0x1800afc5b`
- `fwpuclnt!IkeextSaDestroyEnumHandle0` at `0x1800afee9`
- `fwpuclnt!IkeextSaDestroyEnumHandle0` at `0x1800afee9`

## pseudocode

```c
__int64 __fastcall FwEnumPhase1SAsInternal(__int64 a1, struct _tag_FW_ENDPOINTS *a2, unsigned int *a3, __int64 *a4)
{
  DWORD v5; // ebx
  __int64 v6; // rcx
  __int64 v7; // rdx
  DWORD v8; // eax
  unsigned int v9; // esi
  unsigned int v10; // edi
  unsigned int v11; // r14d
  __int64 v12; // r15
  unsigned __int16 v13; // cx
  int IsHandledSAType; // eax
  unsigned int v15; // r15d
  unsigned int v16; // eax
  __int64 v17; // r9
  __int64 v18; // r14
  unsigned int v19; // esi
  __int64 v20; // r13
  unsigned __int16 v21; // cx
  unsigned int i; // esi
  void *p; // [rsp+40h] [rbp-59h] BYREF
  HANDLE engineHandle; // [rsp+48h] [rbp-51h] BYREF
  HANDLE enumHandle; // [rsp+50h] [rbp-49h] BYREF
  __int64 v29; // [rsp+58h] [rbp-41h] BYREF
  FWPM_SESSION0 session; // [rsp+60h] [rbp-39h] BYREF
  unsigned int v31; // [rsp+B0h] [rbp+17h] BYREF

  *a3 = 0;
  *a4 = 0;
  engineHandle = 0;
  enumHandle = 0;
  p = 0;
  v31 = 0;
  v29 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_FwBfeSessions>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BugFix_FwBfeSessions>::GetImpl'::`2'::impl) )
  {
    *(_QWORD *)&session.sessionKey.Data1 = 0;
    session.displayData.name = L"Firewall Enum Phase1 SAs";
    *(_QWORD *)session.sessionKey.Data4 = 0;
    memset(&session.processId + 1, 0, 28);
    session.displayData.description = 0;
    session.flags = 0;
    *(_QWORD *)&session.txnWaitTimeoutInMSec = 18000000;
    v5 = FwpmEngineOpen0(0, 0xAu, 0, &session, &engineHandle);
    if ( v5 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_55;
      v7 = 10;
      goto LABEL_33;
    }
  }
  else
  {
    v5 = FwpmEngineOpen0(0, 0xAu, 0, 0, &engineHandle);
    if ( v5 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_55;
      v7 = 11;
      goto LABEL_33;
    }
  }
  v8 = IkeextSaCreateEnumHandle0(engineHandle, 0, &enumHandle);
  v5 = v8;
  if ( v8 == 1753 || v8 == -2144206780 )
  {
    v5 = 0;
    goto LABEL_55;
  }
  if ( v8 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_55;
    v7 = 12;
    goto LABEL_33;
  }
  v5 = IkeextSaEnum2(engineHandle, enumHandle, 0xFFFFFFFFLL, &p, &v31);
  if ( v5 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_55;
    v7 = 13;
    goto LABEL_33;
  }
  v9 = v31;
  if ( !v31 )
    goto LABEL_55;
  if ( p )
  {
    v10 = 0;
    v11 = 0;
    do
    {
      v12 = *((_QWORD *)p + v11);
      if ( (unsigned int)FwMatchEndpointsWithIkeTraffic(a2, (struct IKEEXT_TRAFFIC0_ *)(v12 + 24)) )
      {
        IsHandledSAType = FwIsHandledSAType(v13, (struct IKEEXT_SA_DETAILS2_ *)v12);
        v9 = v31;
        v15 = 0;
        if ( IsHandledSAType )
          ++v10;
      }
      else
      {
        v15 = 0;
      }
      ++v11;
    }
    while ( v11 < v9 );
    if ( v10 )
    {
      v16 = FwSizeTMultiply(v10, 128, &v29);
      v5 = FwHResultToWindowsError(v16);
      if ( !v5 )
      {
        v18 = FwAlloc(v29);
        if ( v18 )
        {
          v19 = 0;
          while ( 1 )
          {
            if ( v15 >= v31 || v19 >= v10 )
            {
              *a4 = v18;
              *a3 = v10;
              goto LABEL_55;
            }
            v20 = *((_QWORD *)p + v15);
            if ( (unsigned int)FwMatchEndpointsWithIkeTraffic(a2, (struct IKEEXT_TRAFFIC0_ *)(v20 + 24))
              && (unsigned int)FwIsHandledSAType(v21, (struct IKEEXT_SA_DETAILS2_ *)v20) )
            {
              v5 = FwCopyIkeSa(
                     (struct IKEEXT_SA_DETAILS2_ *)v20,
                     (struct _tag_FW_PHASE1_SA_DETAILS *)(v18 + ((unsigned __int64)v19 << 7)));
              if ( v5 )
              {
                if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
                {
                  WPP_SF_d(
                    *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                    16,
                    WPP_79bb214f8d013c8d3517fa004f1c3caf_Traceguids,
                    v5);
                }
                for ( i = 0; i < v10; ++i )
                  FwCleanupPhase1Sa(v18 + ((unsigned __int64)i << 7));
                FwFree(v18);
                goto LABEL_55;
              }
              ++v19;
            }
            ++v15;
          }
        }
        v17 = 14;
        v5 = 14;
        v6 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_55;
        v7 = 15;
LABEL_38:
        WPP_SF_d(*(_QWORD *)(v6 + 16), v7, WPP_79bb214f8d013c8d3517fa004f1c3caf_Traceguids, v17);
        goto LABEL_55;
      }
      v6 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_55;
      v7 = 14;
LABEL_33:
      v17 = v5;
      goto LABEL_38;
    }
LABEL_55:
    if ( p )
      FwpmFreeMemory0(&p);
  }
  if ( enumHandle )
    IkeextSaDestroyEnumHandle0(engineHandle, enumHandle);
  if ( engineHandle )
    FwpmEngineClose0(engineHandle);
  return v5;
}

```

## disassembly

```asm
0x1800afb2c  mov     [rsp-8+arg_0], rbx
0x1800afb31  push    rbp
0x1800afb32  push    rsi
0x1800afb33  push    rdi
0x1800afb34  push    r12
0x1800afb36  push    r13
0x1800afb38  push    r14
0x1800afb3a  push    r15
0x1800afb3c  lea     rbp, [rsp-27h]
0x1800afb41  sub     rsp, 0C0h
0x1800afb48  mov     rax, cs:__security_cookie
0x1800afb4f  xor     rax, rsp
0x1800afb52  mov     [rbp+57h+var_38], rax
0x1800afb56  xor     r15d, r15d
0x1800afb59  mov     [rbp+57h+var_B8], r9
0x1800afb5d  mov     [r8], r15d
0x1800afb60  mov     r12, r8
0x1800afb63  mov     [r9], r15
0x1800afb66  mov     [rbp+57h+var_C0], rdx
0x1800afb6a  mov     [rbp+57h+var_A8], r15
0x1800afb6e  mov     [rbp+57h+enumHandle], r15
0x1800afb72  mov     [rbp+57h+p], r15
0x1800afb76  mov     [rbp+57h+var_40], r15d
0x1800afb7a  mov     [rbp+57h+var_98], r15
0x1800afb7e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BugFix_FwBfeSessions@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_FwBfeSessions@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_FwBfeSessions> `wil::Feature<__WilFeatureTraits_Feature_BugFix_FwBfeSessions>::GetImpl(void)'::`2'::impl
0x1800afb85  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_FwBfeSessions@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_FwBfeSessions>::__private_IsEnabled(void)
0x1800afb8a  xor     r8d, r8d; authIdentity
0x1800afb8d  lea     edx, [r15+0Ah]; authnService
0x1800afb91  xor     ecx, ecx; serverName
0x1800afb93  test    al, al
0x1800afb95  jz      short loc_1800AFC0E
0x1800afb97  lea     rax, aFirewallEnumPh_0; "Firewall Enum Phase1 SAs"
0x1800afb9e  mov     qword ptr [rbp+57h+session.sessionKey.Data1], r15
0x1800afba2  mov     [rbp+57h+session.displayData.name], rax
0x1800afba6  lea     r9, [rbp+57h+session]; session
0x1800afbaa  xor     eax, eax
0x1800afbac  mov     qword ptr [rbp+57h+session.sessionKey.Data4], r15
0x1800afbb0  mov     dword ptr [rbp+57h+session+2Ch], eax
0x1800afbb3  xorps   xmm0, xmm0
0x1800afbb6  lea     rax, [rbp+57h+var_A8]
0x1800afbba  mov     [rbp+57h+session.displayData.description], r15
0x1800afbbe  mov     [rsp+0F0h+engineHandle], rax; engineHandle
0x1800afbc3  mov     [rbp+57h+session.flags], r15d
0x1800afbc7  mov     qword ptr [rbp+57h+session.txnWaitTimeoutInMSec], 112A880h
0x1800afbcf  movdqa  xmmword ptr [rbp+57h+session.sid], xmm0
0x1800afbd4  mov     qword ptr [rbp+57h+session.kernelMode], r15
0x1800afbd8  call    cs:__imp_FwpmEngineOpen0
0x1800afbde  mov     ebx, eax
0x1800afbe0  test    eax, eax
0x1800afbe2  jz      short loc_1800AFC51
0x1800afbe4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800afbeb  lea     rax, WPP_GLOBAL_Control
0x1800afbf2  cmp     rcx, rax
0x1800afbf5  jz      loc_1800AFECC
0x1800afbfb  test    byte ptr [rcx+1Ch], 1
0x1800afbff  jz      loc_1800AFECC
0x1800afc05  lea     edx, [r15+0Ah]
0x1800afc09  jmp     loc_1800AFDA8
0x1800afc0e  lea     rax, [rbp+57h+var_A8]
0x1800afc12  xor     r9d, r9d; session
0x1800afc15  mov     [rsp+0F0h+engineHandle], rax; engineHandle
0x1800afc1a  call    cs:__imp_FwpmEngineOpen0
0x1800afc20  mov     ebx, eax
0x1800afc22  test    eax, eax
0x1800afc24  jz      short loc_1800AFC51
0x1800afc26  mov     rcx, cs:WPP_GLOBAL_Control
0x1800afc2d  lea     rax, WPP_GLOBAL_Control
0x1800afc34  cmp     rcx, rax
0x1800afc37  jz      loc_1800AFECC
0x1800afc3d  test    byte ptr [rcx+1Ch], 1
0x1800afc41  jz      loc_1800AFECC
0x1800afc47  mov     edx, 0Bh
0x1800afc4c  jmp     loc_1800AFDA8
0x1800afc51  mov     rcx, [rbp+57h+var_A8]; engineHandle
0x1800afc55  lea     r8, [rbp+57h+enumHandle]; enumHandle
0x1800afc59  xor     edx, edx; enumTemplate
0x1800afc5b  call    cs:__imp_IkeextSaCreateEnumHandle0
0x1800afc61  mov     ebx, eax
0x1800afc63  cmp     eax, 6D9h
0x1800afc68  jz      loc_1800AFEC9
0x1800afc6e  cmp     eax, 80320044h
0x1800afc73  jz      loc_1800AFEC9
0x1800afc79  test    eax, eax
0x1800afc7b  jz      short loc_1800AFCA8
0x1800afc7d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800afc84  lea     rax, WPP_GLOBAL_Control
0x1800afc8b  cmp     rcx, rax
0x1800afc8e  jz      loc_1800AFECC
0x1800afc94  test    byte ptr [rcx+1Ch], 1
0x1800afc98  jz      loc_1800AFECC
0x1800afc9e  mov     edx, 0Ch
0x1800afca3  jmp     loc_1800AFDA8
0x1800afca8  mov     rdx, [rbp+57h+enumHandle]
0x1800afcac  lea     rax, [rbp+57h+var_40]
0x1800afcb0  mov     rcx, [rbp+57h+var_A8]
0x1800afcb4  lea     r9, [rbp+57h+p]
0x1800afcb8  or      r8d, 0FFFFFFFFh
0x1800afcbc  mov     [rsp+0F0h+engineHandle], rax
0x1800afcc1  call    cs:__imp_IkeextSaEnum2
0x1800afcc7  mov     ebx, eax
0x1800afcc9  test    eax, eax
0x1800afccb  jz      short loc_1800AFCF8
0x1800afccd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800afcd4  lea     rax, WPP_GLOBAL_Control
0x1800afcdb  cmp     rcx, rax
0x1800afcde  jz      loc_1800AFECC
0x1800afce4  test    byte ptr [rcx+1Ch], 1
0x1800afce8  jz      loc_1800AFECC
0x1800afcee  mov     edx, 0Dh
0x1800afcf3  jmp     loc_1800AFDA8
0x1800afcf8  mov     esi, [rbp+57h+var_40]
0x1800afcfb  test    esi, esi
0x1800afcfd  jz      loc_1800AFECC
0x1800afd03  cmp     [rbp+57h+p], r15
0x1800afd07  jz      loc_1800AFEDC
0x1800afd0d  mov     edi, r15d
0x1800afd10  mov     r14d, r15d
0x1800afd13  test    esi, esi
0x1800afd15  jz      loc_1800AFECC
0x1800afd1b  mov     r13, [rbp+57h+var_C0]
0x1800afd1f  mov     rax, [rbp+57h+p]
0x1800afd23  mov     ecx, r14d
0x1800afd26  mov     r15, [rax+rcx*8]
0x1800afd2a  mov     rcx, r13; struct _tag_FW_ENDPOINTS *
0x1800afd2d  lea     rdx, [r15+18h]; struct IKEEXT_TRAFFIC0_ *
0x1800afd31  call    ?FwMatchEndpointsWithIkeTraffic@@YAHPEAU_tag_FW_ENDPOINTS@@PEAUIKEEXT_TRAFFIC0_@@@Z; FwMatchEndpointsWithIkeTraffic(_tag_FW_ENDPOINTS *,IKEEXT_TRAFFIC0_ *)
0x1800afd36  test    eax, eax
0x1800afd38  jz      short loc_1800AFD50
0x1800afd3a  mov     rdx, r15; struct IKEEXT_SA_DETAILS2_ *
0x1800afd3d  call    ?FwIsHandledSAType@@YAHGPEAUIKEEXT_SA_DETAILS2_@@@Z; FwIsHandledSAType(ushort,IKEEXT_SA_DETAILS2_ *)
0x1800afd42  mov     esi, [rbp+57h+var_40]
0x1800afd45  xor     r15d, r15d
0x1800afd48  test    eax, eax
0x1800afd4a  jz      short loc_1800AFD53
0x1800afd4c  inc     edi
0x1800afd4e  jmp     short loc_1800AFD53
0x1800afd50  xor     r15d, r15d
0x1800afd53  inc     r14d
0x1800afd56  cmp     r14d, esi
0x1800afd59  jb      short loc_1800AFD1F
0x1800afd5b  test    edi, edi
0x1800afd5d  jz      loc_1800AFECC
0x1800afd63  mov     ecx, edi
0x1800afd65  lea     r8, [rbp+57h+var_98]
0x1800afd69  mov     edx, 80h
0x1800afd6e  call    cs:__imp_FwSizeTMultiply
0x1800afd74  mov     ecx, eax
0x1800afd76  call    cs:__imp_FwHResultToWindowsError
0x1800afd7c  mov     ebx, eax
0x1800afd7e  test    eax, eax
0x1800afd80  jz      short loc_1800AFDAD
0x1800afd82  mov     rcx, cs:WPP_GLOBAL_Control
0x1800afd89  lea     rax, WPP_GLOBAL_Control
0x1800afd90  cmp     rcx, rax
0x1800afd93  jz      loc_1800AFECC
0x1800afd99  test    byte ptr [rcx+1Ch], 1
0x1800afd9d  jz      loc_1800AFECC
0x1800afda3  mov     edx, 0Eh
0x1800afda8  mov     r9d, ebx
0x1800afdab  jmp     short loc_1800AFDEB
0x1800afdad  mov     rcx, [rbp+57h+var_98]
0x1800afdb1  call    cs:__imp_FwAlloc
0x1800afdb7  mov     r14, rax
0x1800afdba  test    rax, rax
0x1800afdbd  jnz     short loc_1800AFE00
0x1800afdbf  lea     r9d, [rax+0Eh]
0x1800afdc3  mov     ebx, r9d
0x1800afdc6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800afdcd  lea     rax, WPP_GLOBAL_Control
0x1800afdd4  cmp     rcx, rax
0x1800afdd7  jz      loc_1800AFECC
0x1800afddd  test    byte ptr [rcx+1Ch], 1
0x1800afde1  jz      loc_1800AFECC
0x1800afde7  lea     edx, [r14+0Fh]
0x1800afdeb  mov     rcx, [rcx+10h]
0x1800afdef  lea     r8, WPP_79bb214f8d013c8d3517fa004f1c3caf_Traceguids
0x1800afdf6  call    WPP_SF_d
0x1800afdfb  jmp     loc_1800AFECC
0x1800afe00  mov     esi, r15d
0x1800afe03  cmp     r15d, [rbp+57h+var_40]
0x1800afe07  jnb     loc_1800AFEB5
0x1800afe0d  cmp     esi, edi
0x1800afe0f  jnb     loc_1800AFEB5
0x1800afe15  mov     rax, [rbp+57h+p]
0x1800afe19  mov     ecx, r15d
0x1800afe1c  mov     r13, [rax+rcx*8]
0x1800afe20  mov     rcx, [rbp+57h+var_C0]; struct _tag_FW_ENDPOINTS *
0x1800afe24  lea     rdx, [r13+18h]; struct IKEEXT_TRAFFIC0_ *
0x1800afe28  call    ?FwMatchEndpointsWithIkeTraffic@@YAHPEAU_tag_FW_ENDPOINTS@@PEAUIKEEXT_TRAFFIC0_@@@Z; FwMatchEndpointsWithIkeTraffic(_tag_FW_ENDPOINTS *,IKEEXT_TRAFFIC0_ *)
0x1800afe2d  test    eax, eax
0x1800afe2f  jz      short loc_1800AFE56
0x1800afe31  mov     rdx, r13; struct IKEEXT_SA_DETAILS2_ *
0x1800afe34  call    ?FwIsHandledSAType@@YAHGPEAUIKEEXT_SA_DETAILS2_@@@Z; FwIsHandledSAType(ushort,IKEEXT_SA_DETAILS2_ *)
0x1800afe39  test    eax, eax
0x1800afe3b  jz      short loc_1800AFE56
0x1800afe3d  mov     edx, esi
0x1800afe3f  mov     rcx, r13; struct IKEEXT_SA_DETAILS2_ *
0x1800afe42  shl     rdx, 7
0x1800afe46  add     rdx, r14; struct _tag_FW_PHASE1_SA_DETAILS *
0x1800afe49  call    ?FwCopyIkeSa@@YAKPEAUIKEEXT_SA_DETAILS2_@@PEAU_tag_FW_PHASE1_SA_DETAILS@@@Z; FwCopyIkeSa(IKEEXT_SA_DETAILS2_ *,_tag_FW_PHASE1_SA_DETAILS *)
0x1800afe4e  mov     ebx, eax
0x1800afe50  test    eax, eax
0x1800afe52  jnz     short loc_1800AFE5B
0x1800afe54  inc     esi
0x1800afe56  inc     r15d
0x1800afe59  jmp     short loc_1800AFE03
0x1800afe5b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800afe62  lea     rax, WPP_GLOBAL_Control
0x1800afe69  cmp     rcx, rax
0x1800afe6c  jz      short loc_1800AFE8C
0x1800afe6e  test    byte ptr [rcx+1Ch], 1
0x1800afe72  jz      short loc_1800AFE8C
0x1800afe74  mov     rcx, [rcx+10h]
0x1800afe78  lea     r8, WPP_79bb214f8d013c8d3517fa004f1c3caf_Traceguids
0x1800afe7f  mov     edx, 10h
0x1800afe84  mov     r9d, ebx
0x1800afe87  call    WPP_SF_d
0x1800afe8c  xor     r15d, r15d
0x1800afe8f  mov     esi, r15d
0x1800afe92  test    edi, edi
0x1800afe94  jz      short loc_1800AFEAA
0x1800afe96  mov     ecx, esi
0x1800afe98  shl     rcx, 7
0x1800afe9c  add     rcx, r14
0x1800afe9f  call    FwCleanupPhase1Sa
0x1800afea4  inc     esi
0x1800afea6  cmp     esi, edi
0x1800afea8  jb      short loc_1800AFE96
0x1800afeaa  mov     rcx, r14
0x1800afead  call    cs:__imp_FwFree
0x1800afeb3  jmp     short loc_1800AFECC
0x1800afeb5  mov     rax, [rbp+57h+var_B8]
0x1800afeb9  mov     [rax], r14
0x1800afebc  mov     [r12], edi
0x1800afec0  xor     r15d, r15d
0x1800afec3  test    ebx, ebx
0x1800afec5  jz      short loc_1800AFECC
0x1800afec7  jmp     short loc_1800AFE8F
0x1800afec9  mov     ebx, r15d
0x1800afecc  cmp     [rbp+57h+p], r15
0x1800afed0  jz      short loc_1800AFEDC
0x1800afed2  lea     rcx, [rbp+57h+p]; p
0x1800afed6  call    cs:__imp_FwpmFreeMemory0
0x1800afedc  mov     rdx, [rbp+57h+enumHandle]; enumHandle
0x1800afee0  test    rdx, rdx
0x1800afee3  jz      short loc_1800AFEEF
0x1800afee5  mov     rcx, [rbp+57h+var_A8]; engineHandle
0x1800afee9  call    cs:__imp_IkeextSaDestroyEnumHandle0
0x1800afeef  mov     rcx, [rbp+57h+var_A8]; engineHandle
0x1800afef3  test    rcx, rcx
0x1800afef6  jz      short loc_1800AFEFE
0x1800afef8  call    cs:__imp_FwpmEngineClose0
0x1800afefe  mov     eax, ebx
0x1800aff00  mov     rcx, [rbp+57h+var_38]
0x1800aff04  xor     rcx, rsp; StackCookie
0x1800aff07  call    __security_check_cookie
0x1800aff0c  mov     rbx, [rsp+0F0h+arg_0]
0x1800aff14  add     rsp, 0C0h
0x1800aff1b  pop     r15
0x1800aff1d  pop     r14
0x1800aff1f  pop     r13
0x1800aff21  pop     r12
0x1800aff23  pop     rdi
0x1800aff24  pop     rsi
0x1800aff25  pop     rbp
0x1800aff26  retn
```
