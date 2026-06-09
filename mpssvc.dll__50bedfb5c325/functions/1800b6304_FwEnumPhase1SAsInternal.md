# FwEnumPhase1SAsInternal

- ea: `0x1800b6304`
- end: `0x1800b6742`
- name: `FwEnumPhase1SAsInternal`
- size: `1086`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x1800a1584`

## callees

- `0x18000a710`
- `0x1800729c0`
- `0x18008b9f8`
- `0x1800b409c`
- `0x1800b4b5c`
- `0x1800b4bc4`
- `0x1800b5c50`
- `0x1800b6304`

## import_xrefs

- `fwbase!FwHResultToWindowsError` at `0x1800b656c`
- `fwbase!FwHResultToWindowsError` at `0x1800b656c`
- `fwbase!FwSizeTMultiply` at `0x1800b655e`
- `fwbase!FwSizeTMultiply` at `0x1800b655e`
- `fwbase!FwAlloc` at `0x1800b65ad`
- `fwbase!FwAlloc` at `0x1800b65ad`
- `fwbase!FwFree` at `0x1800b66af`
- `fwbase!FwFree` at `0x1800b66af`
- `fwpuclnt!FwpmEngineOpen0` at `0x1800b63b0`
- `fwpuclnt!FwpmEngineOpen0` at `0x1800b63f8`
- `fwpuclnt!FwpmEngineOpen0` at `0x1800b63b0`
- `fwpuclnt!FwpmEngineOpen0` at `0x1800b63f8`
- `fwpuclnt!FwpmEngineClose0` at `0x1800b670c`
- `fwpuclnt!FwpmEngineClose0` at `0x1800b670c`
- `fwpuclnt!IkeextSaEnum2` at `0x1800b64ab`
- `fwpuclnt!IkeextSaEnum2` at `0x1800b64ab`
- `fwpuclnt!FwpmFreeMemory0` at `0x1800b66de`
- `fwpuclnt!FwpmFreeMemory0` at `0x1800b66de`
- `fwpuclnt!IkeextSaCreateEnumHandle0` at `0x1800b643f`
- `fwpuclnt!IkeextSaCreateEnumHandle0` at `0x1800b643f`
- `fwpuclnt!IkeextSaDestroyEnumHandle0` at `0x1800b66f7`
- `fwpuclnt!IkeextSaDestroyEnumHandle0` at `0x1800b66f7`

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
0x1800b6304  mov     [rsp-8+arg_0], rbx
0x1800b6309  push    rbp
0x1800b630a  push    rsi
0x1800b630b  push    rdi
0x1800b630c  push    r12
0x1800b630e  push    r13
0x1800b6310  push    r14
0x1800b6312  push    r15
0x1800b6314  lea     rbp, [rsp-27h]
0x1800b6319  sub     rsp, 0C0h
0x1800b6320  mov     rax, cs:__security_cookie
0x1800b6327  xor     rax, rsp
0x1800b632a  mov     [rbp+57h+var_38], rax
0x1800b632e  xor     r15d, r15d
0x1800b6331  mov     [rbp+57h+var_B8], r9
0x1800b6335  mov     [r8], r15d
0x1800b6338  mov     r12, r8
0x1800b633b  mov     [r9], r15
0x1800b633e  mov     [rbp+57h+var_C0], rdx
0x1800b6342  mov     [rbp+57h+var_A8], r15
0x1800b6346  mov     [rbp+57h+enumHandle], r15
0x1800b634a  mov     [rbp+57h+p], r15
0x1800b634e  mov     [rbp+57h+var_40], r15d
0x1800b6352  mov     [rbp+57h+var_98], r15
0x1800b6356  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BugFix_FwBfeSessions@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_FwBfeSessions@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_FwBfeSessions> `wil::Feature<__WilFeatureTraits_Feature_BugFix_FwBfeSessions>::GetImpl(void)'::`2'::impl
0x1800b635d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_FwBfeSessions@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_FwBfeSessions>::__private_IsEnabled(void)
0x1800b6362  xor     r8d, r8d; authIdentity
0x1800b6365  lea     edx, [r15+0Ah]; authnService
0x1800b6369  xor     ecx, ecx; serverName
0x1800b636b  test    al, al
0x1800b636d  jz      short loc_1800B63EC
0x1800b636f  lea     rax, aFirewallEnumPh_0; "Firewall Enum Phase1 SAs"
0x1800b6376  mov     qword ptr [rbp+57h+session.sessionKey.Data1], r15
0x1800b637a  mov     [rbp+57h+session.displayData.name], rax
0x1800b637e  lea     r9, [rbp+57h+session]; session
0x1800b6382  xor     eax, eax
0x1800b6384  mov     qword ptr [rbp+57h+session.sessionKey.Data4], r15
0x1800b6388  mov     dword ptr [rbp+57h+session+2Ch], eax
0x1800b638b  xorps   xmm0, xmm0
0x1800b638e  lea     rax, [rbp+57h+var_A8]
0x1800b6392  mov     [rbp+57h+session.displayData.description], r15
0x1800b6396  mov     [rsp+0F0h+engineHandle], rax; engineHandle
0x1800b639b  mov     [rbp+57h+session.flags], r15d
0x1800b639f  mov     qword ptr [rbp+57h+session.txnWaitTimeoutInMSec], 112A880h
0x1800b63a7  movdqa  xmmword ptr [rbp+57h+session.sid], xmm0
0x1800b63ac  mov     qword ptr [rbp+57h+session.kernelMode], r15
0x1800b63b0  call    cs:__imp_FwpmEngineOpen0
0x1800b63b7  nop     dword ptr [rax+rax+00h]
0x1800b63bc  mov     ebx, eax
0x1800b63be  test    eax, eax
0x1800b63c0  jz      short loc_1800B6435
0x1800b63c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b63c9  lea     rax, WPP_GLOBAL_Control
0x1800b63d0  cmp     rcx, rax
0x1800b63d3  jz      loc_1800B66D4
0x1800b63d9  test    byte ptr [rcx+1Ch], 1
0x1800b63dd  jz      loc_1800B66D4
0x1800b63e3  lea     edx, [r15+0Ah]
0x1800b63e7  jmp     loc_1800B65A4
0x1800b63ec  lea     rax, [rbp+57h+var_A8]
0x1800b63f0  xor     r9d, r9d; session
0x1800b63f3  mov     [rsp+0F0h+engineHandle], rax; engineHandle
0x1800b63f8  call    cs:__imp_FwpmEngineOpen0
0x1800b63ff  nop     dword ptr [rax+rax+00h]
0x1800b6404  mov     ebx, eax
0x1800b6406  test    eax, eax
0x1800b6408  jz      short loc_1800B6435
0x1800b640a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b6411  lea     rax, WPP_GLOBAL_Control
0x1800b6418  cmp     rcx, rax
0x1800b641b  jz      loc_1800B66D4
0x1800b6421  test    byte ptr [rcx+1Ch], 1
0x1800b6425  jz      loc_1800B66D4
0x1800b642b  mov     edx, 0Bh
0x1800b6430  jmp     loc_1800B65A4
0x1800b6435  mov     rcx, [rbp+57h+var_A8]; engineHandle
0x1800b6439  lea     r8, [rbp+57h+enumHandle]; enumHandle
0x1800b643d  xor     edx, edx; enumTemplate
0x1800b643f  call    cs:__imp_IkeextSaCreateEnumHandle0
0x1800b6446  nop     dword ptr [rax+rax+00h]
0x1800b644b  mov     ebx, eax
0x1800b644d  cmp     eax, 6D9h
0x1800b6452  jz      loc_1800B66D1
0x1800b6458  cmp     eax, 80320044h
0x1800b645d  jz      loc_1800B66D1
0x1800b6463  test    eax, eax
0x1800b6465  jz      short loc_1800B6492
0x1800b6467  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b646e  lea     rax, WPP_GLOBAL_Control
0x1800b6475  cmp     rcx, rax
0x1800b6478  jz      loc_1800B66D4
0x1800b647e  test    byte ptr [rcx+1Ch], 1
0x1800b6482  jz      loc_1800B66D4
0x1800b6488  mov     edx, 0Ch
0x1800b648d  jmp     loc_1800B65A4
0x1800b6492  mov     rdx, [rbp+57h+enumHandle]
0x1800b6496  lea     rax, [rbp+57h+var_40]
0x1800b649a  mov     rcx, [rbp+57h+var_A8]
0x1800b649e  lea     r9, [rbp+57h+p]
0x1800b64a2  or      r8d, 0FFFFFFFFh
0x1800b64a6  mov     [rsp+0F0h+engineHandle], rax
0x1800b64ab  call    cs:__imp_IkeextSaEnum2
0x1800b64b2  nop     dword ptr [rax+rax+00h]
0x1800b64b7  mov     ebx, eax
0x1800b64b9  test    eax, eax
0x1800b64bb  jz      short loc_1800B64E8
0x1800b64bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b64c4  lea     rax, WPP_GLOBAL_Control
0x1800b64cb  cmp     rcx, rax
0x1800b64ce  jz      loc_1800B66D4
0x1800b64d4  test    byte ptr [rcx+1Ch], 1
0x1800b64d8  jz      loc_1800B66D4
0x1800b64de  mov     edx, 0Dh
0x1800b64e3  jmp     loc_1800B65A4
0x1800b64e8  mov     esi, [rbp+57h+var_40]
0x1800b64eb  test    esi, esi
0x1800b64ed  jz      loc_1800B66D4
0x1800b64f3  cmp     [rbp+57h+p], r15
0x1800b64f7  jz      loc_1800B66EA
0x1800b64fd  mov     edi, r15d
0x1800b6500  mov     r14d, r15d
0x1800b6503  test    esi, esi
0x1800b6505  jz      loc_1800B66D4
0x1800b650b  mov     r13, [rbp+57h+var_C0]
0x1800b650f  mov     rax, [rbp+57h+p]
0x1800b6513  mov     ecx, r14d
0x1800b6516  mov     r15, [rax+rcx*8]
0x1800b651a  mov     rcx, r13; struct _tag_FW_ENDPOINTS *
0x1800b651d  lea     rdx, [r15+18h]; struct IKEEXT_TRAFFIC0_ *
0x1800b6521  call    ?FwMatchEndpointsWithIkeTraffic@@YAHPEAU_tag_FW_ENDPOINTS@@PEAUIKEEXT_TRAFFIC0_@@@Z; FwMatchEndpointsWithIkeTraffic(_tag_FW_ENDPOINTS *,IKEEXT_TRAFFIC0_ *)
0x1800b6526  test    eax, eax
0x1800b6528  jz      short loc_1800B6540
0x1800b652a  mov     rdx, r15; struct IKEEXT_SA_DETAILS2_ *
0x1800b652d  call    ?FwIsHandledSAType@@YAHGPEAUIKEEXT_SA_DETAILS2_@@@Z; FwIsHandledSAType(ushort,IKEEXT_SA_DETAILS2_ *)
0x1800b6532  mov     esi, [rbp+57h+var_40]
0x1800b6535  xor     r15d, r15d
0x1800b6538  test    eax, eax
0x1800b653a  jz      short loc_1800B6543
0x1800b653c  inc     edi
0x1800b653e  jmp     short loc_1800B6543
0x1800b6540  xor     r15d, r15d
0x1800b6543  inc     r14d
0x1800b6546  cmp     r14d, esi
0x1800b6549  jb      short loc_1800B650F
0x1800b654b  test    edi, edi
0x1800b654d  jz      loc_1800B66D4
0x1800b6553  mov     ecx, edi
0x1800b6555  lea     r8, [rbp+57h+var_98]
0x1800b6559  mov     edx, 80h
0x1800b655e  call    cs:__imp_FwSizeTMultiply
0x1800b6565  nop     dword ptr [rax+rax+00h]
0x1800b656a  mov     ecx, eax
0x1800b656c  call    cs:__imp_FwHResultToWindowsError
0x1800b6573  nop     dword ptr [rax+rax+00h]
0x1800b6578  mov     ebx, eax
0x1800b657a  test    eax, eax
0x1800b657c  jz      short loc_1800B65A9
0x1800b657e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b6585  lea     rax, WPP_GLOBAL_Control
0x1800b658c  cmp     rcx, rax
0x1800b658f  jz      loc_1800B66D4
0x1800b6595  test    byte ptr [rcx+1Ch], 1
0x1800b6599  jz      loc_1800B66D4
0x1800b659f  mov     edx, 0Eh
0x1800b65a4  mov     r9d, ebx
0x1800b65a7  jmp     short loc_1800B65ED
0x1800b65a9  mov     rcx, [rbp+57h+var_98]
0x1800b65ad  call    cs:__imp_FwAlloc
0x1800b65b4  nop     dword ptr [rax+rax+00h]
0x1800b65b9  mov     r14, rax
0x1800b65bc  test    rax, rax
0x1800b65bf  jnz     short loc_1800B6602
0x1800b65c1  lea     r9d, [rax+0Eh]
0x1800b65c5  mov     ebx, r9d
0x1800b65c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b65cf  lea     rax, WPP_GLOBAL_Control
0x1800b65d6  cmp     rcx, rax
0x1800b65d9  jz      loc_1800B66D4
0x1800b65df  test    byte ptr [rcx+1Ch], 1
0x1800b65e3  jz      loc_1800B66D4
0x1800b65e9  lea     edx, [r14+0Fh]
0x1800b65ed  mov     rcx, [rcx+10h]
0x1800b65f1  lea     r8, WPP_79bb214f8d013c8d3517fa004f1c3caf_Traceguids
0x1800b65f8  call    WPP_SF_d
0x1800b65fd  jmp     loc_1800B66D4
0x1800b6602  mov     esi, r15d
0x1800b6605  cmp     r15d, [rbp+57h+var_40]
0x1800b6609  jnb     loc_1800B66BD
0x1800b660f  cmp     esi, edi
0x1800b6611  jnb     loc_1800B66BD
0x1800b6617  mov     rax, [rbp+57h+p]
0x1800b661b  mov     ecx, r15d
0x1800b661e  mov     r13, [rax+rcx*8]
0x1800b6622  mov     rcx, [rbp+57h+var_C0]; struct _tag_FW_ENDPOINTS *
0x1800b6626  lea     rdx, [r13+18h]; struct IKEEXT_TRAFFIC0_ *
0x1800b662a  call    ?FwMatchEndpointsWithIkeTraffic@@YAHPEAU_tag_FW_ENDPOINTS@@PEAUIKEEXT_TRAFFIC0_@@@Z; FwMatchEndpointsWithIkeTraffic(_tag_FW_ENDPOINTS *,IKEEXT_TRAFFIC0_ *)
0x1800b662f  test    eax, eax
0x1800b6631  jz      short loc_1800B6658
0x1800b6633  mov     rdx, r13; struct IKEEXT_SA_DETAILS2_ *
0x1800b6636  call    ?FwIsHandledSAType@@YAHGPEAUIKEEXT_SA_DETAILS2_@@@Z; FwIsHandledSAType(ushort,IKEEXT_SA_DETAILS2_ *)
0x1800b663b  test    eax, eax
0x1800b663d  jz      short loc_1800B6658
0x1800b663f  mov     edx, esi
0x1800b6641  mov     rcx, r13; struct IKEEXT_SA_DETAILS2_ *
0x1800b6644  shl     rdx, 7
0x1800b6648  add     rdx, r14; struct _tag_FW_PHASE1_SA_DETAILS *
0x1800b664b  call    ?FwCopyIkeSa@@YAKPEAUIKEEXT_SA_DETAILS2_@@PEAU_tag_FW_PHASE1_SA_DETAILS@@@Z; FwCopyIkeSa(IKEEXT_SA_DETAILS2_ *,_tag_FW_PHASE1_SA_DETAILS *)
0x1800b6650  mov     ebx, eax
0x1800b6652  test    eax, eax
0x1800b6654  jnz     short loc_1800B665D
0x1800b6656  inc     esi
0x1800b6658  inc     r15d
0x1800b665b  jmp     short loc_1800B6605
0x1800b665d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b6664  lea     rax, WPP_GLOBAL_Control
0x1800b666b  cmp     rcx, rax
0x1800b666e  jz      short loc_1800B668E
0x1800b6670  test    byte ptr [rcx+1Ch], 1
0x1800b6674  jz      short loc_1800B668E
0x1800b6676  mov     rcx, [rcx+10h]
0x1800b667a  lea     r8, WPP_79bb214f8d013c8d3517fa004f1c3caf_Traceguids
0x1800b6681  mov     edx, 10h
0x1800b6686  mov     r9d, ebx
0x1800b6689  call    WPP_SF_d
0x1800b668e  xor     r15d, r15d
0x1800b6691  mov     esi, r15d
0x1800b6694  test    edi, edi
0x1800b6696  jz      short loc_1800B66AC
0x1800b6698  mov     ecx, esi
0x1800b669a  shl     rcx, 7
0x1800b669e  add     rcx, r14
0x1800b66a1  call    FwCleanupPhase1Sa
0x1800b66a6  inc     esi
0x1800b66a8  cmp     esi, edi
0x1800b66aa  jb      short loc_1800B6698
0x1800b66ac  mov     rcx, r14
0x1800b66af  call    cs:__imp_FwFree
0x1800b66b6  nop     dword ptr [rax+rax+00h]
0x1800b66bb  jmp     short loc_1800B66D4
0x1800b66bd  mov     rax, [rbp+57h+var_B8]
0x1800b66c1  mov     [rax], r14
0x1800b66c4  mov     [r12], edi
0x1800b66c8  xor     r15d, r15d
0x1800b66cb  test    ebx, ebx
0x1800b66cd  jz      short loc_1800B66D4
0x1800b66cf  jmp     short loc_1800B6691
0x1800b66d1  mov     ebx, r15d
0x1800b66d4  cmp     [rbp+57h+p], r15
0x1800b66d8  jz      short loc_1800B66EA
0x1800b66da  lea     rcx, [rbp+57h+p]; p
0x1800b66de  call    cs:__imp_FwpmFreeMemory0
0x1800b66e5  nop     dword ptr [rax+rax+00h]
0x1800b66ea  mov     rdx, [rbp+57h+enumHandle]; enumHandle
0x1800b66ee  test    rdx, rdx
0x1800b66f1  jz      short loc_1800B6703
0x1800b66f3  mov     rcx, [rbp+57h+var_A8]; engineHandle
0x1800b66f7  call    cs:__imp_IkeextSaDestroyEnumHandle0
0x1800b66fe  nop     dword ptr [rax+rax+00h]
0x1800b6703  mov     rcx, [rbp+57h+var_A8]; engineHandle
0x1800b6707  test    rcx, rcx
0x1800b670a  jz      short loc_1800B6718
0x1800b670c  call    cs:__imp_FwpmEngineClose0
0x1800b6713  nop     dword ptr [rax+rax+00h]
0x1800b6718  mov     eax, ebx
0x1800b671a  mov     rcx, [rbp+57h+var_38]
0x1800b671e  xor     rcx, rsp; StackCookie
0x1800b6721  call    __security_check_cookie
0x1800b6726  mov     rbx, [rsp+0F0h+arg_0]
0x1800b672e  add     rsp, 0C0h
0x1800b6735  pop     r15
0x1800b6737  pop     r14
0x1800b6739  pop     r13
0x1800b673b  pop     r12
0x1800b673d  pop     rdi
0x1800b673e  pop     rsi
0x1800b673f  pop     rbp
0x1800b6740  retn
```
