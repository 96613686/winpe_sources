# FwTenantRestrictionsPolicyUpdate

- ea: `0x1800aa54c`
- end: `0x1800aaadb`
- name: `FwTenantRestrictionsPolicyUpdate`
- size: `1423`
- prototype: ``
- caller_count: `3`
- callee_count: `17`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800981a0`
- `0x1800a9b60`
- `0x1800aada0`

## callees

- `0x180007b58`
- `0x1800089bc`
- `0x180008d60`
- `0x18000a66c`
- `0x18000a710`
- `0x18000b030`
- `0x1800192e0`
- `0x180071b28`
- `0x1800729c0`
- `0x180073488`
- `0x180092198`
- `0x1800a82a0`
- `0x1800a9a0c`
- `0x1800a9e14`
- `0x1800aa48c`
- `0x1800aa54c`
- `0x1800aac0c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800aa69e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800aa746`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800aa69e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800aa746`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800aa9d5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800aa9d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800aaa29`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800aaa3f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800aaa5b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800aaa71`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800aaa29`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800aaa3f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800aaa5b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800aaa71`
- `fwbase!FwHResultToWindowsError` at `0x1800aa5ea`
- `fwbase!FwHResultToWindowsError` at `0x1800aa827`
- `fwbase!FwHResultToWindowsError` at `0x1800aa5ea`
- `fwbase!FwHResultToWindowsError` at `0x1800aa827`
- `FWPolicyIOMgr!StringArrayToOpenPortOrAuthAppAddress` at `0x1800aa7dd`
- `FWPolicyIOMgr!StringArrayToOpenPortOrAuthAppAddress` at `0x1800aa7dd`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x1800aa9ee`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x1800aa9ff`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x1800aa9ee`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x1800aa9ff`

## string_xrefs

- `0x1800aa5d8`: `FwTenantRestrictionsPolicyUpdate`
- `0x1800aaa7d`: `FwTenantRestrictionsPolicyUpdate`

## pseudocode

```c
__int64 FwTenantRestrictionsPolicyUpdate()
{
  unsigned __int16 **v0; // rdi
  unsigned int v1; // r14d
  int v2; // eax
  int v4; // ebx
  LPVOID *v5; // r15
  unsigned int v6; // r12d
  unsigned int v7; // esi
  int v8; // eax
  int TenantRestrictionsIpRanges; // eax
  unsigned int v10; // eax
  __int64 v11; // rcx
  int v12; // edx
  const char *v13; // rax
  __int64 i; // rsi
  __int64 j; // rsi
  unsigned int v16; // [rsp+40h] [rbp-C0h] BYREF
  int v17; // [rsp+44h] [rbp-BCh] BYREF
  unsigned __int16 **v18; // [rsp+48h] [rbp-B8h] BYREF
  _DWORD v19[4]; // [rsp+50h] [rbp-B0h] BYREF
  _OWORD v20[4]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v21; // [rsp+A0h] [rbp-60h]
  _OWORD v22[4]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v23; // [rsp+F0h] [rbp-10h]

  v0 = 0;
  v1 = 0;
  v18 = 0;
  v16 = 0;
  v19[0] = 0;
  memset_0(v20, 0, 0x48u);
  memset_0(v22, 0, 0x48u);
  v19[1] = 0;
  v17 = 0;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 19, WPP_8d116e4572a231222e7bf36008d166e3_Traceguids);
  v2 = FwAcquireRPCSharedLock("FwTenantRestrictionsPolicyUpdate");
  if ( v2 < 0 )
    return FwHResultToWindowsError((unsigned int)v2);
  v4 = 0;
  v5 = 0;
  v6 = 0;
  v7 = 0;
  if ( (_DWORD)qword_1801325D4 )
  {
    v8 = IsTrFwEnforcementConfigured(&v17);
    v4 = v8;
    if ( v8 < 0 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          20,
          WPP_8d116e4572a231222e7bf36008d166e3_Traceguids,
          (unsigned int)v8);
      goto LABEL_54;
    }
    gFwTenantRestrictions = v17;
    if ( !v17 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
        WPP_SF_(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          (unsigned int)(v17 + 21),
          WPP_8d116e4572a231222e7bf36008d166e3_Traceguids);
      AcquireSRWLockExclusive(&stru_1801325E0);
      FwTenantRestrictionsPolicyRemove();
      goto LABEL_53;
    }
    TenantRestrictionsIpRanges = GetTenantRestrictionsIpRanges(&v18, &v16);
    v4 = TenantRestrictionsIpRanges;
    if ( TenantRestrictionsIpRanges < 0 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          22,
          WPP_8d116e4572a231222e7bf36008d166e3_Traceguids,
          (unsigned int)TenantRestrictionsIpRanges);
      v0 = v18;
      v1 = v16;
      goto LABEL_54;
    }
    v1 = v16;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 23, WPP_8d116e4572a231222e7bf36008d166e3_Traceguids, v16);
    AcquireSRWLockExclusive(&stru_1801325E0);
    v0 = v18;
    if ( dword_180132648 )
    {
      if ( v18 )
      {
        if ( pv && (unsigned int)FwTenantRestrictionsCompareSubnetHlpr(v18, v1) )
          goto LABEL_53;
      }
      else if ( !pv )
      {
        goto LABEL_53;
      }
    }
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 24, WPP_8d116e4572a231222e7bf36008d166e3_Traceguids);
    FwTenantRestrictionsTraceEndpointHelper(v0, v1, 1);
    v4 = StringArrayToOpenPortOrAuthAppAddress(v0, v1, v20, v19);
    if ( v19[0] != v1 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 25, WPP_8d116e4572a231222e7bf36008d166e3_Traceguids);
      MicrosoftTelemetryAssertTriggeredNoArgs();
    }
    v10 = FwHResultToWindowsError((unsigned int)v4);
    if ( v10 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 26, WPP_8d116e4572a231222e7bf36008d166e3_Traceguids, v10);
      goto LABEL_53;
    }
    v4 = ResolveAddresses((struct _tag_FW_ADDRESSES *)v20, 0, 0, 0);
    if ( v4 >= 0 )
    {
      v22[0] = xmmword_180132600;
      v22[1] = xmmword_180132610;
      v22[2] = xmmword_180132620;
      v22[3] = xmmword_180132630;
      v23 = qword_180132640;
      xmmword_180132600 = v20[0];
      xmmword_180132610 = v20[1];
      xmmword_180132620 = v20[2];
      xmmword_180132630 = v20[3];
      qword_180132640 = v21;
      memset_0(v20, 0, 0x48u);
      if ( v1 )
      {
        v5 = (LPVOID *)pv;
        v6 = qword_1801325F8;
        pv = v0;
        v0 = 0;
        LODWORD(qword_1801325F8) = v1;
        HIDWORD(qword_1801325F8) = v19[0];
      }
      v7 = 1;
      v4 = FwTenantRestrictionsPolicyRefresh();
      if ( v4 >= 0 )
        goto LABEL_53;
      v11 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_53;
      v12 = 28;
      v13 = "FwTenantRestrictionsPolicyRefresh";
    }
    else
    {
      v11 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_53;
      v12 = 27;
      v13 = "ResolveAddresses";
    }
    WPP_SF_Ds(
      *(_QWORD *)(v11 + 16),
      v12,
      (unsigned int)WPP_8d116e4572a231222e7bf36008d166e3_Traceguids,
      v4,
      (__int64)v13);
LABEL_53:
    ReleaseSRWLockExclusive(&stru_1801325E0);
  }
LABEL_54:
  FwEventTenantRestrictionsPolicyUpdate((unsigned int)v4, v7);
  FwPolioEmptyWFAddresses(v22);
  FwPolioEmptyWFAddresses(v20);
  if ( v5 )
  {
    FwTenantRestrictionsTraceEndpointHelper(v5, v6, 0);
    for ( i = 0; (unsigned int)i < v6; i = (unsigned int)(i + 1) )
      CoTaskMemFree(v5[i]);
    CoTaskMemFree(v5);
  }
  if ( v0 )
  {
    for ( j = 0; (unsigned int)j < v1; j = (unsigned int)(j + 1) )
      CoTaskMemFree(v0[j]);
    CoTaskMemFree(v0);
  }
  FwReleaseRPCSharedLock("FwTenantRestrictionsPolicyUpdate");
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    WPP_SF_d(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      29,
      WPP_8d116e4572a231222e7bf36008d166e3_Traceguids,
      (unsigned int)v4);
  return 0;
}

```

## disassembly

```asm
0x1800aa54c  push    rbp
0x1800aa54e  push    rbx
0x1800aa54f  push    rsi
0x1800aa550  push    rdi
0x1800aa551  push    r12
0x1800aa553  push    r14
0x1800aa555  push    r15
0x1800aa557  lea     rbp, [rsp-10h]
0x1800aa55c  sub     rsp, 110h
0x1800aa563  mov     rax, cs:__security_cookie
0x1800aa56a  xor     rax, rsp
0x1800aa56d  mov     [rbp+40h+var_40], rax
0x1800aa571  xor     edi, edi
0x1800aa573  lea     rcx, [rsp+140h+var_E0]; void *
0x1800aa578  xor     r14d, r14d
0x1800aa57b  mov     [rsp+140h+var_F8], rdi
0x1800aa580  xor     edx, edx; Val
0x1800aa582  mov     [rsp+140h+var_100], r14d
0x1800aa587  mov     [rsp+140h+var_F0], edi
0x1800aa58b  lea     ebx, [rdi+48h]
0x1800aa58e  mov     r8d, ebx; Size
0x1800aa591  call    memset_0
0x1800aa596  mov     r8d, ebx; Size
0x1800aa599  lea     rcx, [rbp+40h+var_90]; void *
0x1800aa59d  xor     edx, edx; Val
0x1800aa59f  call    memset_0
0x1800aa5a4  mov     [rsp+140h+var_EC], edi
0x1800aa5a8  mov     [rsp+140h+var_FC], edi
0x1800aa5ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aa5b3  lea     rax, WPP_GLOBAL_Control
0x1800aa5ba  cmp     rcx, rax
0x1800aa5bd  jz      short loc_1800AA5D8
0x1800aa5bf  test    byte ptr [rcx+1Ch], 8
0x1800aa5c3  jz      short loc_1800AA5D8
0x1800aa5c5  mov     rcx, [rcx+10h]
0x1800aa5c9  lea     edx, [rdi+13h]
0x1800aa5cc  lea     r8, WPP_8d116e4572a231222e7bf36008d166e3_Traceguids
0x1800aa5d3  call    WPP_SF_
0x1800aa5d8  lea     rcx, aFwtenantrestri_19; "FwTenantRestrictionsPolicyUpdate"
0x1800aa5df  call    FwAcquireRPCSharedLock
0x1800aa5e4  test    eax, eax
0x1800aa5e6  jns     short loc_1800AA5FB
0x1800aa5e8  mov     ecx, eax
0x1800aa5ea  call    cs:__imp_FwHResultToWindowsError
0x1800aa5f1  nop     dword ptr [rax+rax+00h]
0x1800aa5f6  jmp     loc_1800AAABC
0x1800aa5fb  xor     ebx, ebx
0x1800aa5fd  xor     r15d, r15d
0x1800aa600  xor     r12d, r12d
0x1800aa603  xor     esi, esi
0x1800aa605  cmp     dword ptr cs:qword_1801325D4, ebx
0x1800aa60b  jz      loc_1800AA9E1
0x1800aa611  lea     rcx, [rsp+140h+var_FC]; int *
0x1800aa616  call    ?IsTrFwEnforcementConfigured@@YAJPEAH@Z; IsTrFwEnforcementConfigured(int *)
0x1800aa61b  mov     ebx, eax
0x1800aa61d  test    eax, eax
0x1800aa61f  jns     short loc_1800AA65D
0x1800aa621  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aa628  lea     rdx, WPP_GLOBAL_Control
0x1800aa62f  cmp     rcx, rdx
0x1800aa632  jz      loc_1800AA9E1
0x1800aa638  test    byte ptr [rcx+1Ch], 1
0x1800aa63c  jz      loc_1800AA9E1
0x1800aa642  mov     rcx, [rcx+10h]
0x1800aa646  lea     edx, [rsi+14h]
0x1800aa649  mov     r9d, eax
0x1800aa64c  lea     r8, WPP_8d116e4572a231222e7bf36008d166e3_Traceguids
0x1800aa653  call    WPP_SF_d
0x1800aa658  jmp     loc_1800AA9E1
0x1800aa65d  mov     eax, [rsp+140h+var_FC]
0x1800aa661  mov     cs:gFwTenantRestrictions, eax
0x1800aa667  test    eax, eax
0x1800aa669  jnz     short loc_1800AA6B4
0x1800aa66b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aa672  lea     rdx, WPP_GLOBAL_Control
0x1800aa679  cmp     rcx, rdx
0x1800aa67c  jz      short loc_1800AA697
0x1800aa67e  test    byte ptr [rcx+1Ch], 4
0x1800aa682  jz      short loc_1800AA697
0x1800aa684  mov     rcx, [rcx+10h]
0x1800aa688  lea     edx, [rax+15h]
0x1800aa68b  lea     r8, WPP_8d116e4572a231222e7bf36008d166e3_Traceguids
0x1800aa692  call    WPP_SF_
0x1800aa697  lea     rcx, stru_1801325E0; SRWLock
0x1800aa69e  call    cs:__imp_AcquireSRWLockExclusive
0x1800aa6a5  nop     dword ptr [rax+rax+00h]
0x1800aa6aa  call    FwTenantRestrictionsPolicyRemove
0x1800aa6af  jmp     loc_1800AA9CE
0x1800aa6b4  lea     rdx, [rsp+140h+var_100]; unsigned int *
0x1800aa6b9  lea     rcx, [rsp+140h+var_F8]; unsigned __int16 ***
0x1800aa6be  call    ?GetTenantRestrictionsIpRanges@@YAJPEAPEAPEAGPEAI@Z; GetTenantRestrictionsIpRanges(ushort * * *,uint *)
0x1800aa6c3  mov     ebx, eax
0x1800aa6c5  test    eax, eax
0x1800aa6c7  jns     short loc_1800AA709
0x1800aa6c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aa6d0  lea     rdx, WPP_GLOBAL_Control
0x1800aa6d7  cmp     rcx, rdx
0x1800aa6da  jz      short loc_1800AA6FA
0x1800aa6dc  test    byte ptr [rcx+1Ch], 1
0x1800aa6e0  jz      short loc_1800AA6FA
0x1800aa6e2  mov     rcx, [rcx+10h]
0x1800aa6e6  lea     r8, WPP_8d116e4572a231222e7bf36008d166e3_Traceguids
0x1800aa6ed  mov     edx, 16h
0x1800aa6f2  mov     r9d, eax
0x1800aa6f5  call    WPP_SF_d
0x1800aa6fa  mov     rdi, [rsp+140h+var_F8]
0x1800aa6ff  mov     r14d, [rsp+140h+var_100]
0x1800aa704  jmp     loc_1800AA9E1
0x1800aa709  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aa710  lea     rdx, WPP_GLOBAL_Control
0x1800aa717  mov     r14d, [rsp+140h+var_100]
0x1800aa71c  cmp     rcx, rdx
0x1800aa71f  jz      short loc_1800AA73F
0x1800aa721  test    byte ptr [rcx+1Ch], 4
0x1800aa725  jz      short loc_1800AA73F
0x1800aa727  mov     rcx, [rcx+10h]
0x1800aa72b  lea     r8, WPP_8d116e4572a231222e7bf36008d166e3_Traceguids
0x1800aa732  mov     edx, 17h
0x1800aa737  mov     r9d, r14d
0x1800aa73a  call    WPP_SF_d
0x1800aa73f  lea     rcx, stru_1801325E0; SRWLock
0x1800aa746  call    cs:__imp_AcquireSRWLockExclusive
0x1800aa74d  nop     dword ptr [rax+rax+00h]
0x1800aa752  cmp     cs:dword_180132648, esi
0x1800aa758  mov     rdi, [rsp+140h+var_F8]
0x1800aa75d  jz      short loc_1800AA78E
0x1800aa75f  test    rdi, rdi
0x1800aa762  jz      short loc_1800AA781
0x1800aa764  cmp     cs:pv, rsi
0x1800aa76b  jz      short loc_1800AA78E
0x1800aa76d  mov     edx, r14d
0x1800aa770  mov     rcx, rdi
0x1800aa773  call    FwTenantRestrictionsCompareSubnetHlpr
0x1800aa778  test    eax, eax
0x1800aa77a  jz      short loc_1800AA78E
0x1800aa77c  jmp     loc_1800AA9CE
0x1800aa781  cmp     cs:pv, rsi
0x1800aa788  jz      loc_1800AA9CE
0x1800aa78e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aa795  lea     rax, WPP_GLOBAL_Control
0x1800aa79c  cmp     rcx, rax
0x1800aa79f  jz      short loc_1800AA7BC
0x1800aa7a1  test    byte ptr [rcx+1Ch], 4
0x1800aa7a5  jz      short loc_1800AA7BC
0x1800aa7a7  mov     rcx, [rcx+10h]
0x1800aa7ab  lea     r8, WPP_8d116e4572a231222e7bf36008d166e3_Traceguids
0x1800aa7b2  mov     edx, 18h
0x1800aa7b7  call    WPP_SF_
0x1800aa7bc  mov     r8d, 1
0x1800aa7c2  mov     edx, r14d
0x1800aa7c5  mov     rcx, rdi
0x1800aa7c8  call    FwTenantRestrictionsTraceEndpointHelper
0x1800aa7cd  lea     r9, [rsp+140h+var_F0]
0x1800aa7d2  mov     edx, r14d
0x1800aa7d5  lea     r8, [rsp+140h+var_E0]
0x1800aa7da  mov     rcx, rdi
0x1800aa7dd  call    cs:__imp_StringArrayToOpenPortOrAuthAppAddress
0x1800aa7e4  nop     dword ptr [rax+rax+00h]
0x1800aa7e9  mov     ebx, eax
0x1800aa7eb  cmp     [rsp+140h+var_F0], r14d
0x1800aa7f0  jz      short loc_1800AA825
0x1800aa7f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aa7f9  lea     rax, WPP_GLOBAL_Control
0x1800aa800  cmp     rcx, rax
0x1800aa803  jz      short loc_1800AA820
0x1800aa805  test    byte ptr [rcx+1Ch], 1
0x1800aa809  jz      short loc_1800AA820
0x1800aa80b  mov     rcx, [rcx+10h]
0x1800aa80f  lea     r8, WPP_8d116e4572a231222e7bf36008d166e3_Traceguids
0x1800aa816  mov     edx, 19h
0x1800aa81b  call    WPP_SF_
0x1800aa820  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "false", "Failed to parse an Input Address")
0x1800aa825  mov     ecx, ebx
0x1800aa827  call    cs:__imp_FwHResultToWindowsError
0x1800aa82e  nop     dword ptr [rax+rax+00h]
0x1800aa833  test    eax, eax
0x1800aa835  jz      short loc_1800AA875
0x1800aa837  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aa83e  lea     rdx, WPP_GLOBAL_Control
0x1800aa845  cmp     rcx, rdx
0x1800aa848  jz      loc_1800AA9CE
0x1800aa84e  test    byte ptr [rcx+1Ch], 1
0x1800aa852  jz      loc_1800AA9CE
0x1800aa858  mov     rcx, [rcx+10h]
0x1800aa85c  lea     r8, WPP_8d116e4572a231222e7bf36008d166e3_Traceguids
0x1800aa863  mov     edx, 1Ah
0x1800aa868  mov     r9d, eax
0x1800aa86b  call    WPP_SF_d
0x1800aa870  jmp     loc_1800AA9CE
0x1800aa875  mov     [rsp+140h+var_110], rsi; __int64
0x1800aa87a  lea     r8, [rsp+140h+var_EC]
0x1800aa87f  mov     dword ptr [rsp+140h+var_118], esi; char
0x1800aa883  lea     rcx, [rsp+140h+var_E0]; struct _tag_FW_ADDRESSES *
0x1800aa888  xor     r9d, r9d
0x1800aa88b  mov     [rsp+140h+var_120], rsi; __int64
0x1800aa890  mov     edx, 7FFFFFFFh
0x1800aa895  call    ResolveAddresses
0x1800aa89a  mov     ebx, eax
0x1800aa89c  test    eax, eax
0x1800aa89e  jns     short loc_1800AA8D2
0x1800aa8a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aa8a7  lea     rax, WPP_GLOBAL_Control
0x1800aa8ae  cmp     rcx, rax
0x1800aa8b1  jz      loc_1800AA9CE
0x1800aa8b7  test    byte ptr [rcx+1Ch], 1
0x1800aa8bb  jz      loc_1800AA9CE
0x1800aa8c1  mov     edx, 1Bh
0x1800aa8c6  lea     rax, aResolveaddress; "ResolveAddresses"
0x1800aa8cd  jmp     loc_1800AA9B6
0x1800aa8d2  movaps  xmm0, cs:xmmword_180132600
0x1800aa8d9  lea     rcx, [rsp+140h+var_E0]; void *
0x1800aa8de  movaps  xmm1, cs:xmmword_180132610
0x1800aa8e5  xor     edx, edx; Val
0x1800aa8e7  movaps  [rbp+40h+var_90], xmm0
0x1800aa8eb  movaps  xmm0, cs:xmmword_180132620
0x1800aa8f2  movaps  [rbp+40h+var_80], xmm1
0x1800aa8f6  movaps  xmm1, cs:xmmword_180132630
0x1800aa8fd  lea     r8d, [rdx+48h]; Size
0x1800aa901  movaps  [rbp+40h+var_70], xmm0
0x1800aa905  movsd   xmm0, cs:qword_180132640
0x1800aa90d  movaps  [rbp+40h+var_60], xmm1
0x1800aa911  movaps  xmm1, [rsp+140h+var_E0]
0x1800aa916  movsd   [rbp+40h+var_50], xmm0
0x1800aa91b  movaps  xmm0, [rsp+140h+var_D0]
0x1800aa920  movaps  cs:xmmword_180132600, xmm1
0x1800aa927  movaps  xmm1, [rbp+40h+var_C0]
0x1800aa92b  movaps  cs:xmmword_180132610, xmm0
0x1800aa932  movaps  xmm0, [rbp+40h+var_B0]
0x1800aa936  movaps  cs:xmmword_180132620, xmm1
0x1800aa93d  movsd   xmm1, [rbp+40h+var_A0]
0x1800aa942  movaps  cs:xmmword_180132630, xmm0
0x1800aa949  movsd   cs:qword_180132640, xmm1
0x1800aa951  call    memset_0
0x1800aa956  test    r14d, r14d
0x1800aa959  jz      short loc_1800AA983
0x1800aa95b  mov     r15, cs:pv
0x1800aa962  mov     r12d, dword ptr cs:qword_1801325F8
0x1800aa969  mov     eax, [rsp+140h+var_F0]
0x1800aa96d  mov     cs:pv, rdi
0x1800aa974  xor     edi, edi
0x1800aa976  mov     dword ptr cs:qword_1801325F8, r14d
0x1800aa97d  mov     dword ptr cs:qword_1801325F8+4, eax
0x1800aa983  mov     esi, 1
0x1800aa988  call    FwTenantRestrictionsPolicyRefresh
0x1800aa98d  mov     ebx, eax
0x1800aa98f  test    eax, eax
0x1800aa991  jns     short loc_1800AA9CE
0x1800aa993  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aa99a  lea     rax, WPP_GLOBAL_Control
0x1800aa9a1  cmp     rcx, rax
0x1800aa9a4  jz      short loc_1800AA9CE
0x1800aa9a6  test    [rcx+1Ch], sil
0x1800aa9aa  jz      short loc_1800AA9CE
0x1800aa9ac  lea     edx, [rsi+1Bh]
0x1800aa9af  lea     rax, aFwtenantrestri_9; "FwTenantRestrictionsPolicyRefresh"
0x1800aa9b6  mov     rcx, [rcx+10h]
0x1800aa9ba  lea     r8, WPP_8d116e4572a231222e7bf36008d166e3_Traceguids
0x1800aa9c1  mov     r9d, ebx
0x1800aa9c4  mov     [rsp+140h+var_120], rax
0x1800aa9c9  call    WPP_SF_Ds
0x1800aa9ce  lea     rcx, stru_1801325E0; SRWLock
0x1800aa9d5  call    cs:__imp_ReleaseSRWLockExclusive
0x1800aa9dc  nop     dword ptr [rax+rax+00h]
0x1800aa9e1  mov     edx, esi
0x1800aa9e3  mov     ecx, ebx
0x1800aa9e5  call    FwEventTenantRestrictionsPolicyUpdate
0x1800aa9ea  lea     rcx, [rbp+40h+var_90]
0x1800aa9ee  call    cs:__imp_FwPolioEmptyWFAddresses
0x1800aa9f5  nop     dword ptr [rax+rax+00h]
0x1800aa9fa  lea     rcx, [rsp+140h+var_E0]
0x1800aa9ff  call    cs:__imp_FwPolioEmptyWFAddresses
0x1800aaa06  nop     dword ptr [rax+rax+00h]
0x1800aaa0b  test    r15, r15
0x1800aaa0e  jz      short loc_1800AAA4B
0x1800aaa10  xor     r8d, r8d
0x1800aaa13  mov     edx, r12d
0x1800aaa16  mov     rcx, r15
0x1800aaa19  call    FwTenantRestrictionsTraceEndpointHelper
0x1800aaa1e  xor     esi, esi
0x1800aaa20  test    r12d, r12d
0x1800aaa23  jz      short loc_1800AAA3C
0x1800aaa25  mov     rcx, [r15+rsi*8]; pv
0x1800aaa29  call    cs:__imp_CoTaskMemFree
0x1800aaa30  nop     dword ptr [rax+rax+00h]
0x1800aaa35  inc     esi
0x1800aaa37  cmp     esi, r12d
0x1800aaa3a  jb      short loc_1800AAA25
0x1800aaa3c  mov     rcx, r15; pv
0x1800aaa3f  call    cs:__imp_CoTaskMemFree
0x1800aaa46  nop     dword ptr [rax+rax+00h]
0x1800aaa4b  test    rdi, rdi
0x1800aaa4e  jz      short loc_1800AAA7D
0x1800aaa50  xor     esi, esi
0x1800aaa52  test    r14d, r14d
0x1800aaa55  jz      short loc_1800AAA6E
0x1800aaa57  mov     rcx, [rdi+rsi*8]; pv
0x1800aaa5b  call    cs:__imp_CoTaskMemFree
0x1800aaa62  nop     dword ptr [rax+rax+00h]
0x1800aaa67  inc     esi
0x1800aaa69  cmp     esi, r14d
  ... truncated ...
```
