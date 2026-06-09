# FwTenantRestrictionsPolicyUpdate

- ea: `0x1800a4ba8`
- end: `0x1800a50ee`
- name: `FwTenantRestrictionsPolicyUpdate`
- size: `1350`
- prototype: ``
- caller_count: `3`
- callee_count: `17`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180093470`
- `0x1800a41f0`
- `0x1800a5390`

## callees

- `0x180008618`
- `0x1800093b0`
- `0x180009720`
- `0x18000ae9c`
- `0x18000af3c`
- `0x18000b800`
- `0x180017110`
- `0x18006e6e4`
- `0x18006f520`
- `0x18006ffc8`
- `0x18008d8b0`
- `0x1800a2a9c`
- `0x1800a40ac`
- `0x1800a4490`
- `0x1800a4aec`
- `0x1800a4ba8`
- `0x1800a5200`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800a4cf4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800a4d96`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800a4cf4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800a4d96`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a5013`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a5013`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a5055`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a5065`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a507b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a508b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a5055`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a5065`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a507b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a508b`
- `fwbase!FwHResultToWindowsError` at `0x1800a4c46`
- `fwbase!FwHResultToWindowsError` at `0x1800a4e6b`
- `fwbase!FwHResultToWindowsError` at `0x1800a4c46`
- `fwbase!FwHResultToWindowsError` at `0x1800a4e6b`
- `FWPolicyIOMgr!StringArrayToOpenPortOrAuthAppAddress` at `0x1800a4e27`
- `FWPolicyIOMgr!StringArrayToOpenPortOrAuthAppAddress` at `0x1800a4e27`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x1800a5026`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x1800a5031`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x1800a5026`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x1800a5031`

## string_xrefs

- `0x1800a4c34`: `FwTenantRestrictionsPolicyUpdate`
- `0x1800a5091`: `FwTenantRestrictionsPolicyUpdate`

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
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 v13; // rcx
  unsigned int v14; // eax
  __int64 v15; // rcx
  int v16; // edx
  const char *v17; // rax
  __int64 i; // rsi
  __int64 j; // rsi
  unsigned int v20; // [rsp+40h] [rbp-C0h] BYREF
  int v21; // [rsp+44h] [rbp-BCh] BYREF
  unsigned __int16 **v22; // [rsp+48h] [rbp-B8h] BYREF
  _DWORD v23[4]; // [rsp+50h] [rbp-B0h] BYREF
  _OWORD v24[4]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v25; // [rsp+A0h] [rbp-60h]
  _OWORD v26[4]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v27; // [rsp+F0h] [rbp-10h]

  v0 = 0;
  v1 = 0;
  v22 = 0;
  v20 = 0;
  v23[0] = 0;
  memset_0(v24, 0, 0x48u);
  memset_0(v26, 0, 0x48u);
  v23[1] = 0;
  v21 = 0;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 19, WPP_399948166deb306656bccb872248c4f3_Traceguids);
  v2 = FwAcquireRPCSharedLock("FwTenantRestrictionsPolicyUpdate");
  if ( v2 < 0 )
    return FwHResultToWindowsError((unsigned int)v2);
  v4 = 0;
  v5 = 0;
  v6 = 0;
  v7 = 0;
  if ( (_DWORD)qword_18012C404 )
  {
    v8 = IsTrFwEnforcementConfigured(&v21);
    v4 = v8;
    if ( v8 < 0 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          20,
          WPP_399948166deb306656bccb872248c4f3_Traceguids,
          (unsigned int)v8);
      goto LABEL_54;
    }
    gFwTenantRestrictions = v21;
    if ( !v21 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
        WPP_SF_(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          (unsigned int)(v21 + 21),
          WPP_399948166deb306656bccb872248c4f3_Traceguids);
      AcquireSRWLockExclusive(&stru_18012C410);
      FwTenantRestrictionsPolicyRemove();
      goto LABEL_53;
    }
    TenantRestrictionsIpRanges = GetTenantRestrictionsIpRanges(&v22, &v20);
    v4 = TenantRestrictionsIpRanges;
    if ( TenantRestrictionsIpRanges < 0 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          22,
          WPP_399948166deb306656bccb872248c4f3_Traceguids,
          (unsigned int)TenantRestrictionsIpRanges);
      v0 = v22;
      v1 = v20;
      goto LABEL_54;
    }
    v1 = v20;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 23, WPP_399948166deb306656bccb872248c4f3_Traceguids, v20);
    AcquireSRWLockExclusive(&stru_18012C410);
    v0 = v22;
    if ( dword_18012C478 )
    {
      if ( v22 )
      {
        if ( pv && (unsigned int)FwTenantRestrictionsCompareSubnetHlpr(v22, v1) )
          goto LABEL_53;
      }
      else if ( !pv )
      {
        goto LABEL_53;
      }
    }
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 24, WPP_399948166deb306656bccb872248c4f3_Traceguids);
    FwTenantRestrictionsTraceEndpointHelper(v0, v1, 1);
    v4 = StringArrayToOpenPortOrAuthAppAddress(v0, v1, v24, v23);
    if ( v23[0] != v1 )
    {
      v13 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 25, WPP_399948166deb306656bccb872248c4f3_Traceguids);
      MicrosoftTelemetryAssertTriggeredNoArgs(v13, v10, v11, v12);
    }
    v14 = FwHResultToWindowsError((unsigned int)v4);
    if ( v14 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 26, WPP_399948166deb306656bccb872248c4f3_Traceguids, v14);
      goto LABEL_53;
    }
    v4 = ResolveAddresses((struct _tag_FW_ADDRESSES *)v24, 0, 0, 0);
    if ( v4 >= 0 )
    {
      v26[0] = xmmword_18012C430;
      v26[1] = xmmword_18012C440;
      v26[2] = xmmword_18012C450;
      v26[3] = xmmword_18012C460;
      v27 = qword_18012C470;
      xmmword_18012C430 = v24[0];
      xmmword_18012C440 = v24[1];
      xmmword_18012C450 = v24[2];
      xmmword_18012C460 = v24[3];
      qword_18012C470 = v25;
      memset_0(v24, 0, 0x48u);
      if ( v1 )
      {
        v5 = (LPVOID *)pv;
        v6 = qword_18012C428;
        pv = v0;
        v0 = 0;
        LODWORD(qword_18012C428) = v1;
        HIDWORD(qword_18012C428) = v23[0];
      }
      v7 = 1;
      v4 = FwTenantRestrictionsPolicyRefresh();
      if ( v4 >= 0 )
        goto LABEL_53;
      v15 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_53;
      v16 = 28;
      v17 = "FwTenantRestrictionsPolicyRefresh";
    }
    else
    {
      v15 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_53;
      v16 = 27;
      v17 = "ResolveAddresses";
    }
    WPP_SF_Ds(
      *(_QWORD *)(v15 + 16),
      v16,
      (unsigned int)WPP_399948166deb306656bccb872248c4f3_Traceguids,
      v4,
      (__int64)v17);
LABEL_53:
    ReleaseSRWLockExclusive(&stru_18012C410);
  }
LABEL_54:
  FwEventTenantRestrictionsPolicyUpdate((unsigned int)v4, v7);
  FwPolioEmptyWFAddresses(v26);
  FwPolioEmptyWFAddresses(v24);
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
      WPP_399948166deb306656bccb872248c4f3_Traceguids,
      (unsigned int)v4);
  return 0;
}

```

## disassembly

```asm
0x1800a4ba8  push    rbp
0x1800a4baa  push    rbx
0x1800a4bab  push    rsi
0x1800a4bac  push    rdi
0x1800a4bad  push    r12
0x1800a4baf  push    r14
0x1800a4bb1  push    r15
0x1800a4bb3  lea     rbp, [rsp-10h]
0x1800a4bb8  sub     rsp, 110h
0x1800a4bbf  mov     rax, cs:__security_cookie
0x1800a4bc6  xor     rax, rsp
0x1800a4bc9  mov     [rbp+40h+var_40], rax
0x1800a4bcd  xor     edi, edi
0x1800a4bcf  lea     rcx, [rsp+140h+var_E0]; void *
0x1800a4bd4  xor     r14d, r14d
0x1800a4bd7  mov     [rsp+140h+var_F8], rdi
0x1800a4bdc  xor     edx, edx; Val
0x1800a4bde  mov     [rsp+140h+var_100], r14d
0x1800a4be3  mov     [rsp+140h+var_F0], edi
0x1800a4be7  lea     ebx, [rdi+48h]
0x1800a4bea  mov     r8d, ebx; Size
0x1800a4bed  call    memset_0
0x1800a4bf2  mov     r8d, ebx; Size
0x1800a4bf5  lea     rcx, [rbp+40h+var_90]; void *
0x1800a4bf9  xor     edx, edx; Val
0x1800a4bfb  call    memset_0
0x1800a4c00  mov     [rsp+140h+var_EC], edi
0x1800a4c04  mov     [rsp+140h+var_FC], edi
0x1800a4c08  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a4c0f  lea     rax, WPP_GLOBAL_Control
0x1800a4c16  cmp     rcx, rax
0x1800a4c19  jz      short loc_1800A4C34
0x1800a4c1b  test    byte ptr [rcx+1Ch], 8
0x1800a4c1f  jz      short loc_1800A4C34
0x1800a4c21  mov     rcx, [rcx+10h]
0x1800a4c25  lea     edx, [rdi+13h]
0x1800a4c28  lea     r8, WPP_399948166deb306656bccb872248c4f3_Traceguids
0x1800a4c2f  call    WPP_SF_
0x1800a4c34  lea     rcx, aFwtenantrestri_19; "FwTenantRestrictionsPolicyUpdate"
0x1800a4c3b  call    FwAcquireRPCSharedLock
0x1800a4c40  test    eax, eax
0x1800a4c42  jns     short loc_1800A4C51
0x1800a4c44  mov     ecx, eax
0x1800a4c46  call    cs:__imp_FwHResultToWindowsError
0x1800a4c4c  jmp     loc_1800A50D0
0x1800a4c51  xor     ebx, ebx
0x1800a4c53  xor     r15d, r15d
0x1800a4c56  xor     r12d, r12d
0x1800a4c59  xor     esi, esi
0x1800a4c5b  cmp     dword ptr cs:qword_18012C404, ebx
0x1800a4c61  jz      loc_1800A5019
0x1800a4c67  lea     rcx, [rsp+140h+var_FC]; int *
0x1800a4c6c  call    ?IsTrFwEnforcementConfigured@@YAJPEAH@Z; IsTrFwEnforcementConfigured(int *)
0x1800a4c71  mov     ebx, eax
0x1800a4c73  test    eax, eax
0x1800a4c75  jns     short loc_1800A4CB3
0x1800a4c77  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a4c7e  lea     rdx, WPP_GLOBAL_Control
0x1800a4c85  cmp     rcx, rdx
0x1800a4c88  jz      loc_1800A5019
0x1800a4c8e  test    byte ptr [rcx+1Ch], 1
0x1800a4c92  jz      loc_1800A5019
0x1800a4c98  mov     rcx, [rcx+10h]
0x1800a4c9c  lea     edx, [rsi+14h]
0x1800a4c9f  mov     r9d, eax
0x1800a4ca2  lea     r8, WPP_399948166deb306656bccb872248c4f3_Traceguids
0x1800a4ca9  call    WPP_SF_d
0x1800a4cae  jmp     loc_1800A5019
0x1800a4cb3  mov     eax, [rsp+140h+var_FC]
0x1800a4cb7  mov     cs:gFwTenantRestrictions, eax
0x1800a4cbd  test    eax, eax
0x1800a4cbf  jnz     short loc_1800A4D04
0x1800a4cc1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a4cc8  lea     rdx, WPP_GLOBAL_Control
0x1800a4ccf  cmp     rcx, rdx
0x1800a4cd2  jz      short loc_1800A4CED
0x1800a4cd4  test    byte ptr [rcx+1Ch], 4
0x1800a4cd8  jz      short loc_1800A4CED
0x1800a4cda  mov     rcx, [rcx+10h]
0x1800a4cde  lea     edx, [rax+15h]
0x1800a4ce1  lea     r8, WPP_399948166deb306656bccb872248c4f3_Traceguids
0x1800a4ce8  call    WPP_SF_
0x1800a4ced  lea     rcx, stru_18012C410; SRWLock
0x1800a4cf4  call    cs:__imp_AcquireSRWLockExclusive
0x1800a4cfa  call    FwTenantRestrictionsPolicyRemove
0x1800a4cff  jmp     loc_1800A500C
0x1800a4d04  lea     rdx, [rsp+140h+var_100]; unsigned int *
0x1800a4d09  lea     rcx, [rsp+140h+var_F8]; unsigned __int16 ***
0x1800a4d0e  call    ?GetTenantRestrictionsIpRanges@@YAJPEAPEAPEAGPEAI@Z; GetTenantRestrictionsIpRanges(ushort * * *,uint *)
0x1800a4d13  mov     ebx, eax
0x1800a4d15  test    eax, eax
0x1800a4d17  jns     short loc_1800A4D59
0x1800a4d19  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a4d20  lea     rdx, WPP_GLOBAL_Control
0x1800a4d27  cmp     rcx, rdx
0x1800a4d2a  jz      short loc_1800A4D4A
0x1800a4d2c  test    byte ptr [rcx+1Ch], 1
0x1800a4d30  jz      short loc_1800A4D4A
0x1800a4d32  mov     rcx, [rcx+10h]
0x1800a4d36  lea     r8, WPP_399948166deb306656bccb872248c4f3_Traceguids
0x1800a4d3d  mov     edx, 16h
0x1800a4d42  mov     r9d, eax
0x1800a4d45  call    WPP_SF_d
0x1800a4d4a  mov     rdi, [rsp+140h+var_F8]
0x1800a4d4f  mov     r14d, [rsp+140h+var_100]
0x1800a4d54  jmp     loc_1800A5019
0x1800a4d59  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a4d60  lea     rdx, WPP_GLOBAL_Control
0x1800a4d67  mov     r14d, [rsp+140h+var_100]
0x1800a4d6c  cmp     rcx, rdx
0x1800a4d6f  jz      short loc_1800A4D8F
0x1800a4d71  test    byte ptr [rcx+1Ch], 4
0x1800a4d75  jz      short loc_1800A4D8F
0x1800a4d77  mov     rcx, [rcx+10h]
0x1800a4d7b  lea     r8, WPP_399948166deb306656bccb872248c4f3_Traceguids
0x1800a4d82  mov     edx, 17h
0x1800a4d87  mov     r9d, r14d
0x1800a4d8a  call    WPP_SF_d
0x1800a4d8f  lea     rcx, stru_18012C410; SRWLock
0x1800a4d96  call    cs:__imp_AcquireSRWLockExclusive
0x1800a4d9c  cmp     cs:dword_18012C478, esi
0x1800a4da2  mov     rdi, [rsp+140h+var_F8]
0x1800a4da7  jz      short loc_1800A4DD8
0x1800a4da9  test    rdi, rdi
0x1800a4dac  jz      short loc_1800A4DCB
0x1800a4dae  cmp     cs:pv, rsi
0x1800a4db5  jz      short loc_1800A4DD8
0x1800a4db7  mov     edx, r14d
0x1800a4dba  mov     rcx, rdi
0x1800a4dbd  call    FwTenantRestrictionsCompareSubnetHlpr
0x1800a4dc2  test    eax, eax
0x1800a4dc4  jz      short loc_1800A4DD8
0x1800a4dc6  jmp     loc_1800A500C
0x1800a4dcb  cmp     cs:pv, rsi
0x1800a4dd2  jz      loc_1800A500C
0x1800a4dd8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a4ddf  lea     rax, WPP_GLOBAL_Control
0x1800a4de6  cmp     rcx, rax
0x1800a4de9  jz      short loc_1800A4E06
0x1800a4deb  test    byte ptr [rcx+1Ch], 4
0x1800a4def  jz      short loc_1800A4E06
0x1800a4df1  mov     rcx, [rcx+10h]
0x1800a4df5  lea     r8, WPP_399948166deb306656bccb872248c4f3_Traceguids
0x1800a4dfc  mov     edx, 18h
0x1800a4e01  call    WPP_SF_
0x1800a4e06  mov     r8d, 1
0x1800a4e0c  mov     edx, r14d
0x1800a4e0f  mov     rcx, rdi
0x1800a4e12  call    FwTenantRestrictionsTraceEndpointHelper
0x1800a4e17  lea     r9, [rsp+140h+var_F0]
0x1800a4e1c  mov     edx, r14d
0x1800a4e1f  lea     r8, [rsp+140h+var_E0]
0x1800a4e24  mov     rcx, rdi
0x1800a4e27  call    cs:__imp_StringArrayToOpenPortOrAuthAppAddress
0x1800a4e2d  mov     ebx, eax
0x1800a4e2f  cmp     [rsp+140h+var_F0], r14d
0x1800a4e34  jz      short loc_1800A4E69
0x1800a4e36  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a4e3d  lea     rax, WPP_GLOBAL_Control
0x1800a4e44  cmp     rcx, rax
0x1800a4e47  jz      short loc_1800A4E64
0x1800a4e49  test    byte ptr [rcx+1Ch], 1
0x1800a4e4d  jz      short loc_1800A4E64
0x1800a4e4f  mov     rcx, [rcx+10h]
0x1800a4e53  lea     r8, WPP_399948166deb306656bccb872248c4f3_Traceguids
0x1800a4e5a  mov     edx, 19h
0x1800a4e5f  call    WPP_SF_
0x1800a4e64  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800a4e69  mov     ecx, ebx
0x1800a4e6b  call    cs:__imp_FwHResultToWindowsError
0x1800a4e71  test    eax, eax
0x1800a4e73  jz      short loc_1800A4EB3
0x1800a4e75  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a4e7c  lea     rdx, WPP_GLOBAL_Control
0x1800a4e83  cmp     rcx, rdx
0x1800a4e86  jz      loc_1800A500C
0x1800a4e8c  test    byte ptr [rcx+1Ch], 1
0x1800a4e90  jz      loc_1800A500C
0x1800a4e96  mov     rcx, [rcx+10h]
0x1800a4e9a  lea     r8, WPP_399948166deb306656bccb872248c4f3_Traceguids
0x1800a4ea1  mov     edx, 1Ah
0x1800a4ea6  mov     r9d, eax
0x1800a4ea9  call    WPP_SF_d
0x1800a4eae  jmp     loc_1800A500C
0x1800a4eb3  mov     [rsp+140h+var_110], rsi; __int64
0x1800a4eb8  lea     r8, [rsp+140h+var_EC]
0x1800a4ebd  mov     dword ptr [rsp+140h+var_118], esi; char
0x1800a4ec1  lea     rcx, [rsp+140h+var_E0]; struct _tag_FW_ADDRESSES *
0x1800a4ec6  xor     r9d, r9d
0x1800a4ec9  mov     [rsp+140h+var_120], rsi; __int64
0x1800a4ece  mov     edx, 7FFFFFFFh
0x1800a4ed3  call    ResolveAddresses
0x1800a4ed8  mov     ebx, eax
0x1800a4eda  test    eax, eax
0x1800a4edc  jns     short loc_1800A4F10
0x1800a4ede  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a4ee5  lea     rax, WPP_GLOBAL_Control
0x1800a4eec  cmp     rcx, rax
0x1800a4eef  jz      loc_1800A500C
0x1800a4ef5  test    byte ptr [rcx+1Ch], 1
0x1800a4ef9  jz      loc_1800A500C
0x1800a4eff  mov     edx, 1Bh
0x1800a4f04  lea     rax, aResolveaddress; "ResolveAddresses"
0x1800a4f0b  jmp     loc_1800A4FF4
0x1800a4f10  movaps  xmm0, cs:xmmword_18012C430
0x1800a4f17  lea     rcx, [rsp+140h+var_E0]; void *
0x1800a4f1c  movaps  xmm1, cs:xmmword_18012C440
0x1800a4f23  xor     edx, edx; Val
0x1800a4f25  movaps  [rbp+40h+var_90], xmm0
0x1800a4f29  movaps  xmm0, cs:xmmword_18012C450
0x1800a4f30  movaps  [rbp+40h+var_80], xmm1
0x1800a4f34  movaps  xmm1, cs:xmmword_18012C460
0x1800a4f3b  lea     r8d, [rdx+48h]; Size
0x1800a4f3f  movaps  [rbp+40h+var_70], xmm0
0x1800a4f43  movsd   xmm0, cs:qword_18012C470
0x1800a4f4b  movaps  [rbp+40h+var_60], xmm1
0x1800a4f4f  movaps  xmm1, [rsp+140h+var_E0]
0x1800a4f54  movsd   [rbp+40h+var_50], xmm0
0x1800a4f59  movaps  xmm0, [rsp+140h+var_D0]
0x1800a4f5e  movaps  cs:xmmword_18012C430, xmm1
0x1800a4f65  movaps  xmm1, [rbp+40h+var_C0]
0x1800a4f69  movaps  cs:xmmword_18012C440, xmm0
0x1800a4f70  movaps  xmm0, [rbp+40h+var_B0]
0x1800a4f74  movaps  cs:xmmword_18012C450, xmm1
0x1800a4f7b  movsd   xmm1, [rbp+40h+var_A0]
0x1800a4f80  movaps  cs:xmmword_18012C460, xmm0
0x1800a4f87  movsd   cs:qword_18012C470, xmm1
0x1800a4f8f  call    memset_0
0x1800a4f94  test    r14d, r14d
0x1800a4f97  jz      short loc_1800A4FC1
0x1800a4f99  mov     r15, cs:pv
0x1800a4fa0  mov     r12d, dword ptr cs:qword_18012C428
0x1800a4fa7  mov     eax, [rsp+140h+var_F0]
0x1800a4fab  mov     cs:pv, rdi
0x1800a4fb2  xor     edi, edi
0x1800a4fb4  mov     dword ptr cs:qword_18012C428, r14d
0x1800a4fbb  mov     dword ptr cs:qword_18012C428+4, eax
0x1800a4fc1  mov     esi, 1
0x1800a4fc6  call    FwTenantRestrictionsPolicyRefresh
0x1800a4fcb  mov     ebx, eax
0x1800a4fcd  test    eax, eax
0x1800a4fcf  jns     short loc_1800A500C
0x1800a4fd1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a4fd8  lea     rax, WPP_GLOBAL_Control
0x1800a4fdf  cmp     rcx, rax
0x1800a4fe2  jz      short loc_1800A500C
0x1800a4fe4  test    [rcx+1Ch], sil
0x1800a4fe8  jz      short loc_1800A500C
0x1800a4fea  lea     edx, [rsi+1Bh]
0x1800a4fed  lea     rax, aFwtenantrestri_9; "FwTenantRestrictionsPolicyRefresh"
0x1800a4ff4  mov     rcx, [rcx+10h]
0x1800a4ff8  lea     r8, WPP_399948166deb306656bccb872248c4f3_Traceguids
0x1800a4fff  mov     r9d, ebx
0x1800a5002  mov     [rsp+140h+var_120], rax
0x1800a5007  call    WPP_SF_Ds
0x1800a500c  lea     rcx, stru_18012C410; SRWLock
0x1800a5013  call    cs:__imp_ReleaseSRWLockExclusive
0x1800a5019  mov     edx, esi
0x1800a501b  mov     ecx, ebx
0x1800a501d  call    FwEventTenantRestrictionsPolicyUpdate
0x1800a5022  lea     rcx, [rbp+40h+var_90]
0x1800a5026  call    cs:__imp_FwPolioEmptyWFAddresses
0x1800a502c  lea     rcx, [rsp+140h+var_E0]
0x1800a5031  call    cs:__imp_FwPolioEmptyWFAddresses
0x1800a5037  test    r15, r15
0x1800a503a  jz      short loc_1800A506B
0x1800a503c  xor     r8d, r8d
0x1800a503f  mov     edx, r12d
0x1800a5042  mov     rcx, r15
0x1800a5045  call    FwTenantRestrictionsTraceEndpointHelper
0x1800a504a  xor     esi, esi
0x1800a504c  test    r12d, r12d
0x1800a504f  jz      short loc_1800A5062
0x1800a5051  mov     rcx, [r15+rsi*8]; pv
0x1800a5055  call    cs:__imp_CoTaskMemFree
0x1800a505b  inc     esi
0x1800a505d  cmp     esi, r12d
0x1800a5060  jb      short loc_1800A5051
0x1800a5062  mov     rcx, r15; pv
0x1800a5065  call    cs:__imp_CoTaskMemFree
0x1800a506b  test    rdi, rdi
0x1800a506e  jz      short loc_1800A5091
0x1800a5070  xor     esi, esi
0x1800a5072  test    r14d, r14d
0x1800a5075  jz      short loc_1800A5088
0x1800a5077  mov     rcx, [rdi+rsi*8]; pv
0x1800a507b  call    cs:__imp_CoTaskMemFree
0x1800a5081  inc     esi
0x1800a5083  cmp     esi, r14d
0x1800a5086  jb      short loc_1800A5077
0x1800a5088  mov     rcx, rdi; pv
0x1800a508b  call    cs:__imp_CoTaskMemFree
0x1800a5091  lea     rcx, aFwtenantrestri_19; "FwTenantRestrictionsPolicyUpdate"
0x1800a5098  call    FwReleaseRPCSharedLock
0x1800a509d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a50a4  lea     rax, WPP_GLOBAL_Control
0x1800a50ab  cmp     rcx, rax
0x1800a50ae  jz      short loc_1800A50CE
0x1800a50b0  test    byte ptr [rcx+1Ch], 8
0x1800a50b4  jz      short loc_1800A50CE
  ... truncated ...
```
