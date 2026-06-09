# LsaISetSupplementalTokenInfo

- ea: `0x1800d13d0`
- end: `0x1800d1b9d`
- name: `LsaISetSupplementalTokenInfo`
- size: `1997`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `0`
- callee_count: `23`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180001098`
- `0x180001318`
- `0x18000c300`
- `0x180011278`
- `0x180016f70`
- `0x1800284d4`
- `0x1800293c0`
- `0x180074b70`
- `0x180086c2c`
- `0x18008d548`
- `0x18008e61c`
- `0x18009a064`
- `0x1800ada18`
- `0x1800b86d0`
- `0x1800b9304`
- `0x1800bd6d4`
- `0x1800bd6e0`
- `0x1800d0d04`
- `0x1800d13d0`
- `0x1800d77e4`
- `0x1800d8188`
- `0x1800de77c`
- `0x1800f5644`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800d1568`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800d1568`
- `ntdll!RtlSubAuthoritySid` at `0x1800d1b02`
- `ntdll!RtlSubAuthoritySid` at `0x1800d1b02`
- `ntdll!NtClose` at `0x1800d19dd`
- `ntdll!NtClose` at `0x1800d19dd`
- `ntdll!RtlInitializeSid` at `0x1800d1af1`
- `ntdll!RtlInitializeSid` at `0x1800d1af1`
- `ntdll!RtlLengthRequiredSid` at `0x1800d1ab7`
- `ntdll!RtlLengthRequiredSid` at `0x1800d1ab7`
- `ntdll!RtlEqualPrefixSid` at `0x1800d17b0`
- `ntdll!RtlEqualPrefixSid` at `0x1800d17b0`
- `ntdll!NtSetInformationToken` at `0x1800d199d`
- `ntdll!NtSetInformationToken` at `0x1800d1b28`
- `ntdll!NtSetInformationToken` at `0x1800d199d`
- `ntdll!NtSetInformationToken` at `0x1800d1b28`
- `ntdll!NtQueryInformationToken` at `0x1800d165a`
- `ntdll!NtQueryInformationToken` at `0x1800d178f`
- `ntdll!NtQueryInformationToken` at `0x1800d165a`
- `ntdll!NtQueryInformationToken` at `0x1800d178f`

## pseudocode

```c
__int64 __fastcall LsaISetSupplementalTokenInfo(void **a1, __int64 a2, _DWORD *a3)
{
  int v3; // edi
  unsigned int v6; // ebx
  size_t v7; // r12
  int v8; // esi
  int v9; // r13d
  __int64 v10; // rtt
  __int64 v11; // rcx
  __int64 v12; // r8
  int *v13; // rdi
  __int64 v14; // rcx
  __int64 v15; // r8
  int v16; // r15d
  int ShouldSplitToken; // eax
  LsaHandleCache *v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // r9
  unsigned __int8 v21; // r12
  bool v22; // zf
  HANDLE v23; // r12
  HANDLE v24; // rcx
  ULONG v25; // r15d
  _QWORD *v26; // rax
  _QWORD *v27; // rdi
  NTSTATUS v28; // eax
  void *v29; // rdx
  unsigned __int8 v31; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int8 v32[3]; // [rsp+41h] [rbp-BFh] BYREF
  ULONG TokenInformationLength; // [rsp+44h] [rbp-BCh] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v35; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v36; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v37[2]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v38[4]; // [rsp+70h] [rbp-90h] BYREF
  ULONG v39; // [rsp+74h] [rbp-8Ch]
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+C0h] [rbp-40h] BYREF
  int v41; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v42; // [rsp+CCh] [rbp-34h]
  _BYTE v43[4]; // [rsp+E0h] [rbp-20h] BYREF
  ULONG v44; // [rsp+E4h] [rbp-1Ch]
  char v45[32]; // [rsp+E8h] [rbp-18h] BYREF
  char Buf2[40]; // [rsp+108h] [rbp+8h] BYREF
  PSID TokenInformation[12]; // [rsp+130h] [rbp+30h] BYREF

  v3 = 0;
  v35 = a2;
  v6 = 0;
  v7 = 72;
  memset_0(v43, 0, 0x48u);
  memset_0(TokenInformation, 0, 0x58u);
  TokenInformationLength = 0;
  v31 = 0;
  v32[0] = 0;
  memset_0(v38, 0, 0x48u);
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 4096;
  if ( a3 )
    *a3 = 0;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl'::`2'::impl)
    || !LsapShadowAdminEnabled
    || LsapFullTokenRemoteAuthInShadowAdminEnabled
    || (v8 = 1, a1) && LsapIsInRemoteAdminAllowList(*a1) )
  {
    v8 = 0;
    if ( LsapGlobalDisableRestrictionTraversal )
      return v6;
  }
  v9 = 0;
  if ( v35 )
  {
    if ( *(_DWORD *)v35 < 8u )
      return (unsigned int)-1073741811;
    if ( *(_DWORD *)(v35 + 4) )
      return (unsigned int)-1073741637;
    if ( (unsigned __int64)*(unsigned int *)v35 - 8 < 0x48 )
      v7 = *(unsigned int *)v35 - 8LL;
    memcpy_0(v43, (const void *)(v35 + 8), v7);
    if ( !memcmp_0(&LsapGlobalCrossBootMachineID, Buf2, 0x20u) )
    {
      if ( !memcmp_0(&LsapGlobalPerBootMachineID, v45, 0x20u) )
      {
        v9 = 1;
        if ( a3 )
          *a3 = 1;
        LsapNotifyLoopbackPackage();
      }
      else
      {
        if ( !(unsigned int)IsUacBypassAllowed() )
        {
          v41 = 257;
          v13 = &v41;
          v42 = 0;
          if ( a1
            && *a1
            && NtQueryInformationToken(*a1, TokenUser, TokenInformation, 0x58u, &TokenInformationLength) >= 0 )
          {
            v13 = (int *)TokenInformation[0];
          }
          if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_e3883d735ea132313a4b2164525664f9_Traceguids);
          }
          SpmpEventWrite(&LSA_MACHINE_ID_PARTIAL_MISMATCH, L"s", v13);
          v6 = -1073741715;
          if ( dword_18019A2B0
            && (unsigned __int8)tlgKeywordOn(&dword_18019A2B0, 0x200000000000LL)
            && (unsigned int)dword_18019A2B0 > 5
            && (unsigned __int8)tlgKeywordOn(&dword_18019A2B0, 0x400000000000LL) )
          {
            v37[0] = 0x1000000;
            v36 = (__int64)v13;
            SystemTimeAsFileTime.dwLowDateTime = -1073741715;
            v35 = 1;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSid<_SID>,_tlgWrapperByVal<8>>(
              v14,
              (int)byte_18017F16D,
              v15,
              (__int64)&v35,
              (__int64)&SystemTimeAsFileTime,
              &v36,
              (__int64)v37);
          }
          return v6;
        }
        SystemTimeAsFileTime = 0;
        GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
        if ( *(_QWORD *)&SystemTimeAsFileTime > g_uacBypassIsAllowedWarningEventTime + 600000000 )
        {
          v10 = g_uacBypassIsAllowedWarningEventTime;
          if ( v10 == _InterlockedCompareExchange64(
                        &g_uacBypassIsAllowedWarningEventTime,
                        *(_QWORD *)&SystemTimeAsFileTime,
                        g_uacBypassIsAllowedWarningEventTime) )
            SpmpEventWrite(&LSA_ALLOW_UAC_BYPASS, 0);
        }
        if ( dword_18019A2B0
          && (unsigned __int8)tlgKeywordOn(&dword_18019A2B0, 0x200000000000LL)
          && (unsigned int)dword_18019A2B0 > 5
          && (unsigned __int8)tlgKeywordOn(&dword_18019A2B0, 0x400000000000LL) )
        {
          v36 = 0x1000000;
          v37[0] = 1;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
            v11,
            (int)byte_18017F1CD,
            v12,
            (__int64)v37,
            (__int64)&v36);
        }
      }
    }
    if ( LsapGlobalFilterNetworkAuthenticationTokens && (v43[0] & 1) != 0 )
      v3 = 1;
  }
  if ( !a1 )
    return 0;
  v6 = NtQueryInformationToken(*a1, TokenUser, TokenInformation, 0x58u, &TokenInformationLength);
  if ( (v6 & 0x80000000) != 0 )
    return v6;
  if ( !RtlEqualPrefixSid(LsapAccountDomainMemberSid, TokenInformation[0])
    || LsapGlobalLocalAccountTokenFilterPolicy
    || (v16 = 1, NegProductType == NtProductLanManNt) )
  {
    v16 = 0;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl'::`2'::impl) )
  {
    if ( !v16 && !v9 && !v3 && !v8 )
      return v6;
    ShouldSplitToken = LsapShouldSplitToken(TokenInformation[0], *a1, &v31, v32);
    v6 = ShouldSplitToken;
    if ( ShouldSplitToken < 0 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v19 = 11;
LABEL_62:
        v20 = (unsigned int)ShouldSplitToken;
LABEL_63:
        WPP_SF_d(*((_QWORD *)v18 + 2), v19, WPP_e3883d735ea132313a4b2164525664f9_Traceguids, v20);
        return v6;
      }
      return v6;
    }
    v21 = v31;
    if ( !v31 )
    {
      v3 = 0;
      v8 = 0;
LABEL_70:
      if ( v16 || v9 || v3 )
        goto LABEL_87;
      v22 = v8 == 0;
      goto LABEL_86;
    }
    if ( LsapShadowAdminEnabled && v8 )
      v8 = LsapShouldApplyProfileSeparation(*a1) != 0 ? v8 : 0;
    if ( !v9 )
      goto LABEL_70;
LABEL_96:
    if ( !v16 && (v43[0] & 1) == 0 )
      v21 = 0;
    goto LABEL_87;
  }
  if ( !v16 && !v9 && !v3 )
    return v6;
  ShouldSplitToken = LsapShouldSplitToken(TokenInformation[0], *a1, &v31, v32);
  v6 = ShouldSplitToken;
  if ( ShouldSplitToken >= 0 )
  {
    v21 = v31;
    if ( v31 )
    {
      if ( v9 )
        goto LABEL_96;
    }
    else
    {
      v3 = 0;
    }
    if ( v16 || v9 )
      goto LABEL_87;
    v22 = v3 == 0;
LABEL_86:
    if ( v22 )
      return v6;
LABEL_87:
    if ( !v21 )
      goto LABEL_104;
    SystemTimeAsFileTime = 0;
    if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_e3883d735ea132313a4b2164525664f9_Traceguids);
    v23 = *a1;
    v24 = *a1;
    *a1 = 0;
    v6 = LsapFilterElevatedTokenFull(v24, a1);
    if ( (v6 & 0x80000000) == 0 )
    {
      SystemTimeAsFileTime = (struct _FILETIME)*a1;
      v6 = NtSetInformationToken(v23, TokenLinkedToken, &SystemTimeAsFileTime, 8u);
    }
    if ( *a1 )
      NtClose(v23);
    else
      *a1 = v23;
    if ( (v6 & 0x80000000) != 0 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v19 = 14;
        v20 = v6;
        goto LABEL_63;
      }
    }
    else
    {
LABEL_104:
      ShouldSplitToken = LsapVirtualizeToken(*a1, v32[0]);
      v6 = ShouldSplitToken;
      if ( ShouldSplitToken >= 0 )
      {
        if ( (!v16 || v9 || v3) && v35 )
        {
          ShouldSplitToken = LsapGetTokenIntegrityInfo(*a1, (struct _LSAP_TOKEN_INFO_INTEGRITY *)v38);
          v6 = ShouldSplitToken;
          if ( ShouldSplitToken >= 0 )
          {
            v25 = v44;
            if ( v44 < v39 )
            {
              TokenInformationLength = RtlLengthRequiredSid(1u) + 16;
              v26 = (_QWORD *)LsapAllocate(TokenInformationLength);
              v27 = v26;
              if ( v26 )
              {
                *v26 = v26 + 2;
                RtlInitializeSid(v26 + 2, &IdentifierAuthority, 1u);
                *RtlSubAuthoritySid((PSID)*v27, 0) = v25;
                *((_DWORD *)v27 + 2) = 96;
                v28 = NtSetInformationToken(*a1, TokenIntegrityLevel, v27, TokenInformationLength);
                v6 = v28;
                if ( v28 < 0
                  && WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                {
                  WPP_SF_Dd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    17,
                    WPP_e3883d735ea132313a4b2164525664f9_Traceguids,
                    v25,
                    v28);
                }
                LsapSubProv_FreeRoutine((struct _RTL_BALANCED_NODE *)v27, v29);
              }
              else
              {
                return (unsigned int)-1073741801;
              }
            }
          }
          else
          {
            v18 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v19 = 16;
              goto LABEL_62;
            }
          }
        }
      }
      else
      {
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v19 = 15;
          goto LABEL_62;
        }
      }
    }
    return v6;
  }
  v18 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v19 = 12;
    goto LABEL_62;
  }
  return v6;
}

```

## disassembly

```asm
0x1800d13d0  mov     [rsp-8+arg_18], rbx
0x1800d13d5  push    rbp
0x1800d13d6  push    rsi
0x1800d13d7  push    rdi
0x1800d13d8  push    r12
0x1800d13da  push    r13
0x1800d13dc  push    r14
0x1800d13de  push    r15
0x1800d13e0  lea     rbp, [rsp-0A0h]
0x1800d13e8  sub     rsp, 1A0h
0x1800d13ef  mov     rax, cs:__security_cookie
0x1800d13f6  xor     rax, rsp
0x1800d13f9  mov     [rbp+0D0h+var_40], rax
0x1800d1400  xor     edi, edi
0x1800d1402  mov     [rsp+1D0h+var_180], rdx
0x1800d1407  mov     r15, r8
0x1800d140a  mov     r14, rcx
0x1800d140d  xor     edx, edx; Val
0x1800d140f  lea     rcx, [rbp+0D0h+var_F0]; void *
0x1800d1413  mov     ebx, edi
0x1800d1415  lea     r12d, [rdi+48h]
0x1800d1419  mov     r8d, r12d; Size
0x1800d141c  call    memset_0
0x1800d1421  xor     edx, edx; Val
0x1800d1423  lea     r8d, [rdi+58h]; Size
0x1800d1427  lea     rcx, [rbp+0D0h+TokenInformation]; void *
0x1800d142b  call    memset_0
0x1800d1430  mov     r8d, r12d; Size
0x1800d1433  mov     [rsp+1D0h+TokenInformationLength], edi
0x1800d1437  xor     edx, edx; Val
0x1800d1439  mov     [rsp+1D0h+var_190], dil
0x1800d143e  lea     rcx, [rsp+1D0h+var_160]; void *
0x1800d1443  mov     [rsp+1D0h+var_18F], dil
0x1800d1448  call    memset_0
0x1800d144d  mov     dword ptr [rbp+0D0h+IdentifierAuthority.Value], edi
0x1800d1450  mov     word ptr [rbp+0D0h+IdentifierAuthority.Value+4], 1000h
0x1800d1456  test    r15, r15
0x1800d1459  jz      short loc_1800D145E
0x1800d145b  mov     [r15], edi
0x1800d145e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ShadowAdmin@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin> `wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl(void)'::`2'::impl
0x1800d1465  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(void)
0x1800d146a  test    al, al
0x1800d146c  jz      short loc_1800D1494
0x1800d146e  cmp     cs:?LsapShadowAdminEnabled@@3HA, edi; int LsapShadowAdminEnabled
0x1800d1474  jz      short loc_1800D1494
0x1800d1476  cmp     cs:?LsapFullTokenRemoteAuthInShadowAdminEnabled@@3HA, edi; int LsapFullTokenRemoteAuthInShadowAdminEnabled
0x1800d147c  jnz     short loc_1800D1494
0x1800d147e  mov     esi, 1
0x1800d1483  test    r14, r14
0x1800d1486  jz      short loc_1800D14A2
0x1800d1488  mov     rcx, [r14]; TokenHandle
0x1800d148b  call    ?LsapIsInRemoteAdminAllowList@@YAEPEAX@Z; LsapIsInRemoteAdminAllowList(void *)
0x1800d1490  test    al, al
0x1800d1492  jz      short loc_1800D14A2
0x1800d1494  cmp     cs:?LsapGlobalDisableRestrictionTraversal@@3KA, edi; ulong LsapGlobalDisableRestrictionTraversal
0x1800d149a  mov     esi, edi
0x1800d149c  jnz     loc_1800D1B70
0x1800d14a2  mov     rcx, [rsp+1D0h+var_180]
0x1800d14a7  mov     r13d, edi
0x1800d14aa  test    rcx, rcx
0x1800d14ad  jz      loc_1800D1761
0x1800d14b3  cmp     dword ptr [rcx], 8
0x1800d14b6  jnb     short loc_1800D14C2
0x1800d14b8  mov     ebx, 0C000000Dh
0x1800d14bd  jmp     loc_1800D1B70
0x1800d14c2  mov     ebx, 1
0x1800d14c7  cmp     [rcx+4], ebx
0x1800d14ca  jb      short loc_1800D14D6
0x1800d14cc  mov     ebx, 0C00000BBh
0x1800d14d1  jmp     loc_1800D1B70
0x1800d14d6  mov     eax, [rcx]
0x1800d14d8  lea     rdx, [rcx+8]; Src
0x1800d14dc  add     rax, 0FFFFFFFFFFFFFFF8h
0x1800d14e0  lea     rcx, [rbp+0D0h+var_F0]; void *
0x1800d14e4  cmp     rax, r12
0x1800d14e7  cmovb   r12, rax
0x1800d14eb  mov     r8, r12; Size
0x1800d14ee  call    memcpy_0
0x1800d14f3  mov     r8d, 20h ; ' '; Size
0x1800d14f9  lea     rdx, [rbp+0D0h+Buf2]; Buf2
0x1800d14fd  lea     rcx, ?LsapGlobalCrossBootMachineID@@3PAEA; Buf1
0x1800d1504  call    memcmp_0
0x1800d1509  xor     r12d, r12d
0x1800d150c  test    eax, eax
0x1800d150e  jnz     short loc_1800D1539
0x1800d1510  lea     r8d, [r12+20h]; Size
0x1800d1515  lea     rdx, [rbp+0D0h+var_E8]; Buf2
0x1800d1519  lea     rcx, ?LsapGlobalPerBootMachineID@@3PAEA; Buf1
0x1800d1520  call    memcmp_0
0x1800d1525  test    eax, eax
0x1800d1527  jnz     short loc_1800D1551
0x1800d1529  mov     r13d, ebx
0x1800d152c  test    r15, r15
0x1800d152f  jz      short loc_1800D1534
0x1800d1531  mov     [r15], ebx
0x1800d1534  call    ?LsapNotifyLoopbackPackage@@YAXXZ; LsapNotifyLoopbackPackage(void)
0x1800d1539  cmp     cs:?LsapGlobalFilterNetworkAuthenticationTokens@@3KA, r12d; ulong LsapGlobalFilterNetworkAuthenticationTokens
0x1800d1540  jz      loc_1800D1769
0x1800d1546  test    [rbp+0D0h+var_F0], bl
0x1800d1549  cmovnz  edi, ebx
0x1800d154c  jmp     loc_1800D1769
0x1800d1551  call    ?IsUacBypassAllowed@@YAHXZ; IsUacBypassAllowed(void)
0x1800d1556  test    eax, eax
0x1800d1558  jz      loc_1800D1628
0x1800d155e  lea     rcx, [rsp+1D0h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800d1563  mov     qword ptr [rsp+1D0h+SystemTimeAsFileTime.dwLowDateTime], r12
0x1800d1568  call    cs:__imp_GetSystemTimeAsFileTime
0x1800d156f  nop     dword ptr [rax+rax+00h]
0x1800d1574  mov     rax, cs:?g_uacBypassIsAllowedWarningEventTime@@3_JA; __int64 g_uacBypassIsAllowedWarningEventTime
0x1800d157b  mov     rcx, qword ptr [rsp+1D0h+SystemTimeAsFileTime.dwLowDateTime]
0x1800d1580  lea     rdx, [rax+23C34600h]
0x1800d1587  cmp     rcx, rdx
0x1800d158a  jle     short loc_1800D15A5
0x1800d158c  lock cmpxchg cs:?g_uacBypassIsAllowedWarningEventTime@@3_JA, rcx; __int64 g_uacBypassIsAllowedWarningEventTime
0x1800d1595  jnz     short loc_1800D15A5
0x1800d1597  xor     edx, edx; unsigned __int16 *
0x1800d1599  lea     rcx, LSA_ALLOW_UAC_BYPASS; struct _EVENT_DESCRIPTOR *
0x1800d15a0  call    ?SpmpEventWrite@@YAKPEBU_EVENT_DESCRIPTOR@@PEAGZZ; SpmpEventWrite(_EVENT_DESCRIPTOR const *,ushort *,...)
0x1800d15a5  mov     eax, cs:dword_18019A2B0
0x1800d15ab  test    eax, eax
0x1800d15ad  jz      short loc_1800D1539
0x1800d15af  mov     rdx, 200000000000h
0x1800d15b9  lea     rcx, dword_18019A2B0
0x1800d15c0  call    _tlgKeywordOn
0x1800d15c5  test    al, al
0x1800d15c7  jz      loc_1800D1539
0x1800d15cd  mov     eax, cs:dword_18019A2B0
0x1800d15d3  cmp     eax, 5
0x1800d15d6  jbe     loc_1800D1539
0x1800d15dc  mov     rdx, 400000000000h
0x1800d15e6  lea     rcx, dword_18019A2B0
0x1800d15ed  call    _tlgKeywordOn
0x1800d15f2  test    al, al
0x1800d15f4  jz      loc_1800D1539
0x1800d15fa  lea     rax, [rsp+1D0h+var_178]
0x1800d15ff  mov     [rsp+1D0h+var_178], 1000000h
0x1800d1608  lea     r9, [rsp+1D0h+var_170]
0x1800d160d  mov     [rsp+1D0h+ReturnLength], rax
0x1800d1612  lea     rdx, byte_18017F1CD
0x1800d1619  mov     [rsp+1D0h+var_170], rbx
0x1800d161e  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBX1IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteAgg@@YAJ011I2@ZPEBX@@SAJPEBU_tlgProvider_t@@PEBX1AEBU?$_tlgWrapperByVal@$07@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,void const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x1800d1623  jmp     loc_1800D1539
0x1800d1628  mov     [rbp+0D0h+var_108], 101h
0x1800d162f  lea     rdi, [rbp+0D0h+var_108]
0x1800d1633  mov     [rbp+0D0h+var_104], r12
0x1800d1637  test    r14, r14
0x1800d163a  jz      short loc_1800D166D
0x1800d163c  mov     rcx, [r14]; TokenHandle
0x1800d163f  test    rcx, rcx
0x1800d1642  jz      short loc_1800D166D
0x1800d1644  lea     rax, [rsp+1D0h+TokenInformationLength]
0x1800d1649  mov     r9d, 58h ; 'X'; TokenInformationLength
0x1800d164f  lea     r8, [rbp+0D0h+TokenInformation]; TokenInformation
0x1800d1653  mov     [rsp+1D0h+ReturnLength], rax; ReturnLength
0x1800d1658  mov     edx, ebx; TokenInformationClass
0x1800d165a  call    cs:__imp_NtQueryInformationToken
0x1800d1661  nop     dword ptr [rax+rax+00h]
0x1800d1666  test    eax, eax
0x1800d1668  cmovns  rdi, [rbp+0D0h+TokenInformation]
0x1800d166d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d1674  lea     rsi, WPP_GLOBAL_Control
0x1800d167b  cmp     rcx, rsi
0x1800d167e  jz      short loc_1800D169A
0x1800d1680  test    [rcx+1Ch], bl
0x1800d1683  jz      short loc_1800D169A
0x1800d1685  mov     rcx, [rcx+10h]
0x1800d1689  lea     r8, WPP_e3883d735ea132313a4b2164525664f9_Traceguids
0x1800d1690  mov     edx, 0Ah
0x1800d1695  call    WPP_SF_
0x1800d169a  mov     r8, rdi
0x1800d169d  lea     rdx, aS_1; "s"
0x1800d16a4  lea     rcx, LSA_MACHINE_ID_PARTIAL_MISMATCH; struct _EVENT_DESCRIPTOR *
0x1800d16ab  call    ?SpmpEventWrite@@YAKPEBU_EVENT_DESCRIPTOR@@PEAGZZ; SpmpEventWrite(_EVENT_DESCRIPTOR const *,ushort *,...)
0x1800d16b0  mov     eax, cs:dword_18019A2B0
0x1800d16b6  mov     ebx, 0C000006Dh
0x1800d16bb  test    eax, eax
0x1800d16bd  jz      loc_1800D1B70
0x1800d16c3  mov     rdx, 200000000000h
0x1800d16cd  lea     rcx, dword_18019A2B0
0x1800d16d4  call    _tlgKeywordOn
0x1800d16d9  test    al, al
0x1800d16db  jz      loc_1800D1B70
0x1800d16e1  mov     eax, cs:dword_18019A2B0
0x1800d16e7  cmp     eax, 5
0x1800d16ea  jbe     loc_1800D1B70
0x1800d16f0  mov     rdx, 400000000000h
0x1800d16fa  lea     rcx, dword_18019A2B0
0x1800d1701  call    _tlgKeywordOn
0x1800d1706  test    al, al
0x1800d1708  jz      loc_1800D1B70
0x1800d170e  lea     rax, [rsp+1D0h+var_170]
0x1800d1713  mov     [rsp+1D0h+var_170], 1000000h
0x1800d171c  mov     [rsp+1D0h+var_1A0], rax
0x1800d1721  lea     r9, [rsp+1D0h+var_180]
0x1800d1726  lea     rax, [rsp+1D0h+var_178]
0x1800d172b  mov     [rsp+1D0h+var_178], rdi
0x1800d1730  mov     [rsp+1D0h+var_1A8], rax
0x1800d1735  lea     rdx, byte_18017F16D
0x1800d173c  lea     rax, [rsp+1D0h+SystemTimeAsFileTime]
0x1800d1741  mov     [rsp+1D0h+SystemTimeAsFileTime.dwLowDateTime], 0C000006Dh
0x1800d1749  mov     [rsp+1D0h+ReturnLength], rax
0x1800d174e  mov     [rsp+1D0h+var_180], 1
0x1800d1757  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSid@U_SID@@@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBX1IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteAgg@@YAJ011I2@ZPEBX@@SAJPEBU_tlgProvider_t@@PEBX1AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSid@U_SID@@@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSid<_SID>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,void const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSid<_SID> const &,_tlgWrapperByVal<8> const &)
0x1800d175c  jmp     loc_1800D1B70
0x1800d1761  xor     r12d, r12d
0x1800d1764  lea     ebx, [r12+1]
0x1800d1769  test    r14, r14
0x1800d176c  jnz     short loc_1800D1776
0x1800d176e  mov     ebx, r12d
0x1800d1771  jmp     loc_1800D1B70
0x1800d1776  mov     rcx, [r14]; TokenHandle
0x1800d1779  lea     rax, [rsp+1D0h+TokenInformationLength]
0x1800d177e  mov     r9d, 58h ; 'X'; TokenInformationLength
0x1800d1784  mov     [rsp+1D0h+ReturnLength], rax; ReturnLength
0x1800d1789  lea     r8, [rbp+0D0h+TokenInformation]; TokenInformation
0x1800d178d  mov     edx, ebx; TokenInformationClass
0x1800d178f  call    cs:__imp_NtQueryInformationToken
0x1800d1796  nop     dword ptr [rax+rax+00h]
0x1800d179b  mov     ebx, eax
0x1800d179d  test    eax, eax
0x1800d179f  js      loc_1800D1B70
0x1800d17a5  mov     rdx, [rbp+0D0h+TokenInformation]; Sid2
0x1800d17a9  mov     rcx, cs:?LsapAccountDomainMemberSid@@3PEAXEA; Sid1
0x1800d17b0  call    cs:__imp_RtlEqualPrefixSid
0x1800d17b7  nop     dword ptr [rax+rax+00h]
0x1800d17bc  test    al, al
0x1800d17be  jz      short loc_1800D17D8
0x1800d17c0  cmp     cs:?LsapGlobalLocalAccountTokenFilterPolicy@@3KA, r12d; ulong LsapGlobalLocalAccountTokenFilterPolicy
0x1800d17c7  jnz     short loc_1800D17D8
0x1800d17c9  cmp     cs:?NegProductType@@3W4_NT_PRODUCT_TYPE@@A, 2; _NT_PRODUCT_TYPE NegProductType
0x1800d17d0  mov     r15d, 1
0x1800d17d6  jnz     short loc_1800D17DB
0x1800d17d8  mov     r15d, r12d
0x1800d17db  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ShadowAdmin@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin> `wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl(void)'::`2'::impl
0x1800d17e2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(void)
0x1800d17e7  test    al, al
0x1800d17e9  jz      loc_1800D18AD
0x1800d17ef  test    r15d, r15d
0x1800d17f2  jnz     short loc_1800D1805
0x1800d17f4  test    r13d, r13d
0x1800d17f7  jnz     short loc_1800D1805
0x1800d17f9  test    edi, edi
0x1800d17fb  jnz     short loc_1800D1805
0x1800d17fd  test    esi, esi
0x1800d17ff  jz      loc_1800D1B70
0x1800d1805  mov     rdx, [r14]; TokenHandle
0x1800d1808  lea     r9, [rsp+1D0h+var_18F]; unsigned __int8 *
0x1800d180d  mov     rcx, [rbp+0D0h+TokenInformation]; Sid
0x1800d1811  lea     r8, [rsp+1D0h+var_190]; unsigned __int8 *
0x1800d1816  call    ?LsapShouldSplitToken@@YAJPEAX0PEAE1@Z; LsapShouldSplitToken(void *,void *,uchar *,uchar *)
0x1800d181b  mov     ebx, eax
0x1800d181d  test    eax, eax
0x1800d181f  jns     short loc_1800D185F
0x1800d1821  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d1828  lea     rsi, WPP_GLOBAL_Control
0x1800d182f  cmp     rcx, rsi
0x1800d1832  jz      loc_1800D1B70
0x1800d1838  test    byte ptr [rcx+1Ch], 1
0x1800d183c  jz      loc_1800D1B70
0x1800d1842  mov     edx, 0Bh
0x1800d1847  mov     r9d, eax
0x1800d184a  mov     rcx, [rcx+10h]
0x1800d184e  lea     r8, WPP_e3883d735ea132313a4b2164525664f9_Traceguids
0x1800d1855  call    WPP_SF_d
0x1800d185a  jmp     loc_1800D1B70
0x1800d185f  mov     r12b, [rsp+1D0h+var_190]
0x1800d1864  test    r12b, r12b
0x1800d1867  jnz     short loc_1800D186F
0x1800d1869  xor     edi, edi
0x1800d186b  xor     esi, esi
0x1800d186d  jmp     short loc_1800D1893
0x1800d186f  cmp     cs:?LsapShadowAdminEnabled@@3HA, 0; int LsapShadowAdminEnabled
0x1800d1876  jz      short loc_1800D188A
0x1800d1878  test    esi, esi
0x1800d187a  jz      short loc_1800D188A
0x1800d187c  mov     rcx, [r14]; void *
0x1800d187f  call    ?LsapShouldApplyProfileSeparation@@YAEPEAX@Z; LsapShouldApplyProfileSeparation(void *)
0x1800d1884  neg     al
0x1800d1886  sbb     ecx, ecx
0x1800d1888  and     esi, ecx
0x1800d188a  test    r13d, r13d
0x1800d188d  jnz     loc_1800D19BF
0x1800d1893  test    r15d, r15d
0x1800d1896  jnz     loc_1800D1928
0x1800d189c  test    r13d, r13d
0x1800d189f  jnz     loc_1800D1928
0x1800d18a5  test    edi, edi
0x1800d18a7  jnz     short loc_1800D1928
0x1800d18a9  test    esi, esi
0x1800d18ab  jmp     short loc_1800D1922
0x1800d18ad  test    r15d, r15d
0x1800d18b0  jnz     short loc_1800D18BF
0x1800d18b2  test    r13d, r13d
0x1800d18b5  jnz     short loc_1800D18BF
0x1800d18b7  test    edi, edi
0x1800d18b9  jz      loc_1800D1B70
0x1800d18bf  mov     rdx, [r14]; TokenHandle
0x1800d18c2  lea     r9, [rsp+1D0h+var_18F]; unsigned __int8 *
0x1800d18c7  mov     rcx, [rbp+0D0h+TokenInformation]; Sid
0x1800d18cb  lea     r8, [rsp+1D0h+var_190]; unsigned __int8 *
  ... truncated ...
```
