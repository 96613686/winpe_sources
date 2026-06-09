# SvrImpl_FWUpdateDynamicKeywordAddress0(void *,void *,_GUID,ushort const *,int)

- ea: `0x1800a0db4`
- end: `0x1800a13f4`
- name: `?SvrImpl_FWUpdateDynamicKeywordAddress0@@YAKPEAX0U_GUID@@PEBGH@Z`
- size: `1600`
- prototype: `unsigned int __fastcall(void *, void *, struct _GUID *, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800c53d0`

## callees

- `0x180008618`
- `0x1800093b0`
- `0x180009720`
- `0x18000ae9c`
- `0x18000af3c`
- `0x180069e20`
- `0x18006c3f8`
- `0x18006f520`
- `0x18006ffc8`
- `0x18008c7e0`
- `0x180092368`
- `0x180092998`
- `0x180093070`
- `0x1800a0db4`
- `0x1800a1c9c`
- `0x1800a2214`
- `0x1800a2378`

## import_xrefs

- `fwbase!IsAddressesEmpty` at `0x1800a10c2`
- `fwbase!IsAddressesEmpty` at `0x1800a10c2`
- `fwbase!FwHResultToWindowsError` at `0x1800a13c7`
- `fwbase!FwHResultToWindowsError` at `0x1800a13c7`
- `fwbase!FwStringBuild` at `0x1800a1145`
- `fwbase!FwStringBuild` at `0x1800a1145`
- `fwbase!FwStringCopy` at `0x1800a1180`
- `fwbase!FwStringCopy` at `0x1800a1180`
- `fwbase!FwFree` at `0x1800a139a`
- `fwbase!FwFree` at `0x1800a13a9`
- `fwbase!FwFree` at `0x1800a139a`
- `fwbase!FwFree` at `0x1800a13a9`
- `FWPolicyIOMgr!FwUpdateDynamicKeywordAddressInRegistry` at `0x1800a1253`
- `FWPolicyIOMgr!FwUpdateDynamicKeywordAddressInRegistry` at `0x1800a1253`
- `FWPolicyIOMgr!IsEqualAddresses` at `0x1800a1238`
- `FWPolicyIOMgr!IsEqualAddresses` at `0x1800a1238`
- `FWPolicyIOMgr!ValidatePortOrAppAddressString` at `0x1800a0ed3`
- `FWPolicyIOMgr!ValidatePortOrAppAddressString` at `0x1800a0ed3`
- `FWPolicyIOMgr!FwGetStoreTypeFromDynamicKeywordOriginType` at `0x1800a1037`
- `FWPolicyIOMgr!FwGetStoreTypeFromDynamicKeywordOriginType` at `0x1800a1037`
- `FWPolicyIOMgr!FwDynamicKeywordAddressIsStringValid` at `0x1800a0ebe`
- `FWPolicyIOMgr!FwDynamicKeywordAddressIsStringValid` at `0x1800a0ebe`
- `FWPolicyIOMgr!GetOpenPortorAuthAppAddrAsString` at `0x1800a10db`
- `FWPolicyIOMgr!GetOpenPortorAuthAppAddrAsString` at `0x1800a10db`
- `FWPolicyIOMgr!StringToOpenPortOrAuthAppAddress` at `0x1800a11bf`
- `FWPolicyIOMgr!StringToOpenPortOrAuthAppAddress` at `0x1800a11bf`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x1800a129b`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x1800a13b3`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x1800a129b`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x1800a13b3`

## string_xrefs

- `0x1800a1106`: `GetOpenPortOrAuthAppAddrAsString`
- `0x1800a0e0a`: `SvrImpl_FWUpdateDynamicKeywordAddress0`
- `0x1800a13b9`: `SvrImpl_FWUpdateDynamicKeywordAddress0`
- `0x1800a11ab`: `FwStringCopy`
- `0x1800a11ea`: `StringToOpenPortOrAuthAppAddress`
- `0x1800a127e`: `FwUpdateDynamicKeywordAddressInRegistry`

## pseudocode

```c
__int64 __fastcall SvrImpl_FWUpdateDynamicKeywordAddress0(
        void *a1,
        _DWORD *a2,
        struct _GUID *a3,
        const unsigned __int16 *a4,
        int a5)
{
  struct _GUID *v6; // r14
  int v8; // eax
  int v9; // edx
  int v10; // r8d
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // r9
  int OpenPortorAuthAppAddrAsString; // ebx
  __int64 v15; // rdx
  int IsStringValid; // r12d
  unsigned int v17; // eax
  int v18; // ecx
  __int64 v19; // rax
  __int64 v20; // r14
  __int64 v21; // r9
  __int64 v22; // rcx
  __int64 v23; // rdx
  unsigned int v24; // r12d
  bool v25; // zf
  int v26; // edx
  const char *v27; // rax
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 v30; // r9
  struct _GUID v33; // [rsp+50h] [rbp-61h] BYREF
  __int64 v34; // [rsp+60h] [rbp-51h] BYREF
  __int64 v35; // [rsp+68h] [rbp-49h] BYREF
  _BYTE v36[24]; // [rsp+70h] [rbp-41h] BYREF
  int v37; // [rsp+88h] [rbp-29h]
  __int64 v38; // [rsp+90h] [rbp-21h]
  int v39; // [rsp+A8h] [rbp-9h]
  __int64 v40; // [rsp+B0h] [rbp-1h]

  v35 = 0;
  v6 = a3;
  v34 = 0;
  memset_0(v36, 0, 0x48u);
  v8 = FwAcquireRPCSharedLock("SvrImpl_FWUpdateDynamicKeywordAddress0");
  if ( v8 < 0 )
  {
    v11 = (unsigned int)v8;
    return FwHResultToWindowsError(v11);
  }
  if ( a2[6] != 2 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      WPP_SF_l(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 476);
      v12 = WPP_GLOBAL_Control;
    }
    v13 = 2147942405LL;
    OpenPortorAuthAppAddrAsString = -2147024891;
    if ( (_UNKNOWN *)v12 == &WPP_GLOBAL_Control || (*(_BYTE *)(v12 + 28) & 1) == 0 )
      goto LABEL_89;
    v15 = 477;
    goto LABEL_88;
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF_d_guid_Sd(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), v9, v10, a2[4], (__int64)v6, (__int64)a4, a5);
  IsStringValid = FwDynamicKeywordAddressIsStringValid(a4);
  if ( IsStringValid != 1 )
  {
    if ( !IsStringValid && a5 == 1 )
    {
      OpenPortorAuthAppAddrAsString = 0;
      v12 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_89;
      v15 = 480;
      v13 = 0;
      goto LABEL_88;
    }
LABEL_23:
    v17 = a2[4];
    if ( v17 > 0xB || (v18 = 2084, !_bittest(&v18, v17)) )
    {
      v13 = 2147942487LL;
      OpenPortorAuthAppAddrAsString = -2147024809;
      v12 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_89;
      v15 = 481;
      goto LABEL_88;
    }
    OpenPortorAuthAppAddrAsString = FwDynamicKeywordMgrLock();
    if ( OpenPortorAuthAppAddrAsString < 0 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_Ds(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          482,
          (unsigned int)WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids,
          OpenPortorAuthAppAddrAsString,
          (__int64)"FwDynamicKeywordMgrLock");
      goto LABEL_89;
    }
    v33 = *v6;
    v19 = FwDynamicKeywordMgrAddressFind(&v33);
    v20 = v19;
    if ( !v19 )
    {
      v21 = 2147942487LL;
      OpenPortorAuthAppAddrAsString = -2147024809;
      v22 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_34;
      v23 = 483;
LABEL_33:
      WPP_SF_d(*(_QWORD *)(v22 + 16), v23, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids, v21);
LABEL_34:
      v24 = a5;
      goto LABEL_35;
    }
    if ( (*(_BYTE *)(v19 + 40) & 1) != 0 )
    {
      if ( a2[4] != 5 )
      {
        v21 = 2147942405LL;
        OpenPortorAuthAppAddrAsString = -2147024891;
        v22 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_34;
        v23 = 484;
        goto LABEL_33;
      }
    }
    else if ( (unsigned int)FwGetStoreTypeFromDynamicKeywordOriginType(*(unsigned int *)(v19 + 120)) == 11 )
    {
      if ( a2[4] != 11 )
      {
        v21 = 2147942405LL;
        OpenPortorAuthAppAddrAsString = -2147024891;
        v22 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_34;
        v23 = 485;
        goto LABEL_33;
      }
    }
    else if ( a2[4] != 2 && a2[4] != 5 )
    {
      v21 = 2147942405LL;
      OpenPortorAuthAppAddrAsString = -2147024891;
      v22 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_34;
      v23 = 486;
      goto LABEL_33;
    }
    v25 = IsStringValid == 1;
    v24 = a5;
    if ( v25 )
    {
      if ( a5 != 1 || (unsigned int)IsAddressesEmpty(v20 + 48) )
      {
        OpenPortorAuthAppAddrAsString = FwStringCopy(a4, &v34);
        if ( OpenPortorAuthAppAddrAsString < 0 )
        {
          v22 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
            goto LABEL_35;
          v26 = 489;
          v27 = "FwStringCopy";
          goto LABEL_59;
        }
      }
      else
      {
        OpenPortorAuthAppAddrAsString = GetOpenPortorAuthAppAddrAsString(v20 + 48, &v35, 0);
        if ( OpenPortorAuthAppAddrAsString < 0 )
        {
          v22 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
            goto LABEL_35;
          v26 = 487;
          v27 = "GetOpenPortOrAuthAppAddrAsString";
          goto LABEL_59;
        }
        OpenPortorAuthAppAddrAsString = FwStringBuild(&v34, v35, L",", a4);
        if ( OpenPortorAuthAppAddrAsString < 0 )
        {
          v22 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
            goto LABEL_35;
          v26 = 488;
          v27 = "FwStringBuild";
          goto LABEL_59;
        }
      }
      OpenPortorAuthAppAddrAsString = StringToOpenPortOrAuthAppAddress(v34, v36);
      if ( OpenPortorAuthAppAddrAsString < 0 )
      {
        v22 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_35;
        v26 = 490;
        v27 = "StringToOpenPortOrAuthAppAddress";
        goto LABEL_59;
      }
    }
    OpenPortorAuthAppAddrAsString = FwDynamicKeywordMgrFormatAddresses(v36);
    if ( OpenPortorAuthAppAddrAsString >= 0 )
    {
      if ( (unsigned int)IsEqualAddresses(v36, v20 + 48) )
        goto LABEL_35;
      if ( (*(_BYTE *)(v20 + 40) & 1) != 0
        || (OpenPortorAuthAppAddrAsString = FwUpdateDynamicKeywordAddressInRegistry(v20, v36),
            OpenPortorAuthAppAddrAsString >= 0) )
      {
        if ( (_DWORD)gFwDynamicKeywordMgr != 1 )
          MicrosoftTelemetryAssertTriggeredNoArgs(v22, v28, v29, v30);
        FwPolioEmptyWFAddresses(v20 + 48);
        *(_DWORD *)(v20 + 72) = v37;
        *(_QWORD *)(v20 + 80) = v38;
        *(_DWORD *)(v20 + 104) = v39;
        *(_QWORD *)(v20 + 112) = v40;
        v6 = a3;
        v37 = 0;
        v38 = 0;
        v39 = 0;
        v33 = *a3;
        v40 = 0;
        FwQueueUpdateForRulesWithDynamicKeywordAddress(&v33);
        goto LABEL_36;
      }
      v22 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      {
LABEL_35:
        v6 = a3;
LABEL_36:
        FwDynamicKeywordMgrUnlock(v22);
        goto LABEL_90;
      }
      v26 = 492;
      v27 = "FwUpdateDynamicKeywordAddressInRegistry";
    }
    else
    {
      v22 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_35;
      v26 = 491;
      v27 = "FwDynamicKeywordMgrFormatAddresses";
    }
LABEL_59:
    WPP_SF_Ds(
      *(_QWORD *)(v22 + 16),
      v26,
      (unsigned int)WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids,
      OpenPortorAuthAppAddrAsString,
      (__int64)v27);
    goto LABEL_35;
  }
  if ( !(unsigned int)ValidatePortOrAppAddressString(a4) )
    goto LABEL_23;
  v13 = 2147942487LL;
  OpenPortorAuthAppAddrAsString = -2147024809;
  v12 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
    goto LABEL_89;
  v15 = 479;
LABEL_88:
  WPP_SF_d(*(_QWORD *)(v12 + 16), v15, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids, v13);
LABEL_89:
  v24 = a5;
LABEL_90:
  v33 = *v6;
  FwEventDynamicKeywordAddressUpdate((unsigned int)OpenPortorAuthAppAddrAsString, &v33, v24, v35, a4, v34);
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF_dSS(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      493,
      (unsigned int)WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids,
      OpenPortorAuthAppAddrAsString,
      v35,
      v34);
  if ( v35 )
    FwFree(v35);
  if ( v34 )
    FwFree(v34);
  FwPolioEmptyWFAddresses(v36);
  FwReleaseRPCSharedLock("SvrImpl_FWUpdateDynamicKeywordAddress0");
  v11 = (unsigned int)OpenPortorAuthAppAddrAsString;
  return FwHResultToWindowsError(v11);
}

```

## disassembly

```asm
0x1800a0db4  mov     [rsp-8+arg_0], rbx
0x1800a0db9  push    rbp
0x1800a0dba  push    rsi
0x1800a0dbb  push    rdi
0x1800a0dbc  push    r12
0x1800a0dbe  push    r13
0x1800a0dc0  push    r14
0x1800a0dc2  push    r15
0x1800a0dc4  lea     rbp, [rsp-1Fh]
0x1800a0dc9  sub     rsp, 0D0h
0x1800a0dd0  mov     rax, cs:__security_cookie
0x1800a0dd7  xor     rax, rsp
0x1800a0dda  mov     [rbp+4Fh+var_40], rax
0x1800a0dde  mov     r15, rdx
0x1800a0de1  mov     [rbp+4Fh+var_C0], r8
0x1800a0de5  xor     edx, edx; Val
0x1800a0de7  mov     [rbp+4Fh+var_98], 0
0x1800a0def  mov     r14, r8
0x1800a0df2  mov     [rbp+4Fh+var_A0], 0
0x1800a0dfa  lea     rcx, [rbp+4Fh+var_90]; void *
0x1800a0dfe  mov     r13, r9
0x1800a0e01  lea     r8d, [rdx+48h]; Size
0x1800a0e05  call    memset_0
0x1800a0e0a  lea     rcx, aSvrimplFwupdat; "SvrImpl_FWUpdateDynamicKeywordAddress0"
0x1800a0e11  call    FwAcquireRPCSharedLock
0x1800a0e16  test    eax, eax
0x1800a0e18  jns     short loc_1800A0E21
0x1800a0e1a  mov     ecx, eax
0x1800a0e1c  jmp     loc_1800A13C7
0x1800a0e21  mov     r9d, [r15+18h]
0x1800a0e25  cmp     r9d, 2
0x1800a0e29  jz      short loc_1800A0E84
0x1800a0e2b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a0e32  lea     rsi, WPP_GLOBAL_Control
0x1800a0e39  mov     edi, 1
0x1800a0e3e  cmp     rcx, rsi
0x1800a0e41  jz      short loc_1800A0E5E
0x1800a0e43  test    [rcx+1Ch], dil
0x1800a0e47  jz      short loc_1800A0E5E
0x1800a0e49  mov     rcx, [rcx+10h]
0x1800a0e4d  mov     edx, 1DCh
0x1800a0e52  call    WPP_SF_l
0x1800a0e57  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a0e5e  mov     r9d, 80070005h
0x1800a0e64  mov     ebx, r9d
0x1800a0e67  cmp     rcx, rsi
0x1800a0e6a  jz      loc_1800A1328
0x1800a0e70  test    [rcx+1Ch], dil
0x1800a0e74  jz      loc_1800A1328
0x1800a0e7a  mov     edx, 1DDh
0x1800a0e7f  jmp     loc_1800A1318
0x1800a0e84  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a0e8b  lea     rsi, WPP_GLOBAL_Control
0x1800a0e92  mov     ebx, [rbp+4Fh+arg_20]
0x1800a0e95  cmp     rcx, rsi
0x1800a0e98  jz      short loc_1800A0EBB
0x1800a0e9a  test    byte ptr [rcx+1Ch], 4
0x1800a0e9e  jz      short loc_1800A0EBB
0x1800a0ea0  mov     r9d, [r15+10h]
0x1800a0ea4  mov     rcx, [rcx+10h]
0x1800a0ea8  mov     [rsp+100h+var_D0], ebx
0x1800a0eac  mov     [rsp+100h+var_D8], r13
0x1800a0eb1  mov     [rsp+100h+var_E0], r14
0x1800a0eb6  call    WPP_SF_d_guid_Sd
0x1800a0ebb  mov     rcx, r13
0x1800a0ebe  call    cs:__imp_FwDynamicKeywordAddressIsStringValid
0x1800a0ec4  mov     edi, 1
0x1800a0ec9  mov     r12d, eax
0x1800a0ecc  cmp     eax, edi
0x1800a0ece  jnz     short loc_1800A0F0A
0x1800a0ed0  mov     rcx, r13
0x1800a0ed3  call    cs:__imp_ValidatePortOrAppAddressString
0x1800a0ed9  test    eax, eax
0x1800a0edb  jz      short loc_1800A0F3C
0x1800a0edd  mov     r9d, 80070057h
0x1800a0ee3  mov     ebx, r9d
0x1800a0ee6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a0eed  cmp     rcx, rsi
0x1800a0ef0  jz      loc_1800A1328
0x1800a0ef6  test    [rcx+1Ch], dil
0x1800a0efa  jz      loc_1800A1328
0x1800a0f00  mov     edx, 1DFh
0x1800a0f05  jmp     loc_1800A1318
0x1800a0f0a  test    r12d, r12d
0x1800a0f0d  jnz     short loc_1800A0F3C
0x1800a0f0f  cmp     ebx, edi
0x1800a0f11  jnz     short loc_1800A0F3C
0x1800a0f13  xor     ebx, ebx
0x1800a0f15  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a0f1c  cmp     rcx, rsi
0x1800a0f1f  jz      loc_1800A1328
0x1800a0f25  test    [rcx+1Ch], dil
0x1800a0f29  jz      loc_1800A1328
0x1800a0f2f  mov     edx, 1E0h
0x1800a0f34  xor     r9d, r9d
0x1800a0f37  jmp     loc_1800A1318
0x1800a0f3c  mov     eax, [r15+10h]
0x1800a0f40  cmp     eax, 0Bh
0x1800a0f43  ja      loc_1800A12F8
0x1800a0f49  mov     ecx, 824h
0x1800a0f4e  bt      ecx, eax
0x1800a0f51  jnb     loc_1800A12F8
0x1800a0f57  call    FwDynamicKeywordMgrLock
0x1800a0f5c  mov     ebx, eax
0x1800a0f5e  test    eax, eax
0x1800a0f60  jns     short loc_1800A0FA5
0x1800a0f62  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a0f69  cmp     rcx, rsi
0x1800a0f6c  jz      loc_1800A1328
0x1800a0f72  test    [rcx+1Ch], dil
0x1800a0f76  jz      loc_1800A1328
0x1800a0f7c  mov     rcx, [rcx+10h]
0x1800a0f80  lea     rax, aFwdynamickeywo_4; "FwDynamicKeywordMgrLock"
0x1800a0f87  mov     edx, 1E2h
0x1800a0f8c  mov     [rsp+100h+var_E0], rax
0x1800a0f91  mov     r9d, ebx
0x1800a0f94  lea     r8, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids
0x1800a0f9b  call    WPP_SF_Ds
0x1800a0fa0  jmp     loc_1800A1328
0x1800a0fa5  movaps  xmm0, xmmword ptr [r14]
0x1800a0fa9  lea     rcx, [rbp+4Fh+var_B0]
0x1800a0fad  movdqa  [rbp+4Fh+var_B0], xmm0
0x1800a0fb2  call    FwDynamicKeywordMgrAddressFind
0x1800a0fb7  mov     r14, rax
0x1800a0fba  test    rax, rax
0x1800a0fbd  jnz     short loc_1800A1001
0x1800a0fbf  mov     r9d, 80070057h
0x1800a0fc5  mov     ebx, r9d
0x1800a0fc8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a0fcf  cmp     rcx, rsi
0x1800a0fd2  jz      short loc_1800A0FEF
0x1800a0fd4  test    [rcx+1Ch], dil
0x1800a0fd8  jz      short loc_1800A0FEF
0x1800a0fda  mov     edx, 1E3h
0x1800a0fdf  mov     rcx, [rcx+10h]
0x1800a0fe3  lea     r8, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids
0x1800a0fea  call    WPP_SF_d
0x1800a0fef  mov     r12d, [rbp+4Fh+arg_20]
0x1800a0ff3  mov     r14, [rbp+4Fh+var_C0]
0x1800a0ff7  call    FwDynamicKeywordMgrUnlock
0x1800a0ffc  jmp     loc_1800A132C
0x1800a1001  test    [rax+28h], dil
0x1800a1005  jz      short loc_1800A1034
0x1800a1007  cmp     dword ptr [r15+10h], 5
0x1800a100c  jz      loc_1800A10A8
0x1800a1012  mov     r9d, 80070005h
0x1800a1018  mov     ebx, r9d
0x1800a101b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a1022  cmp     rcx, rsi
0x1800a1025  jz      short loc_1800A0FEF
0x1800a1027  test    [rcx+1Ch], dil
0x1800a102b  jz      short loc_1800A0FEF
0x1800a102d  mov     edx, 1E4h
0x1800a1032  jmp     short loc_1800A0FDF
0x1800a1034  mov     ecx, [rax+78h]
0x1800a1037  call    cs:__imp_FwGetStoreTypeFromDynamicKeywordOriginType
0x1800a103d  cmp     eax, 0Bh
0x1800a1040  jnz     short loc_1800A106D
0x1800a1042  cmp     [r15+10h], eax
0x1800a1046  jz      short loc_1800A10A8
0x1800a1048  mov     r9d, 80070005h
0x1800a104e  mov     ebx, r9d
0x1800a1051  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a1058  cmp     rcx, rsi
0x1800a105b  jz      short loc_1800A0FEF
0x1800a105d  test    [rcx+1Ch], dil
0x1800a1061  jz      short loc_1800A0FEF
0x1800a1063  mov     edx, 1E5h
0x1800a1068  jmp     loc_1800A0FDF
0x1800a106d  cmp     dword ptr [r15+10h], 2
0x1800a1072  jz      short loc_1800A10A8
0x1800a1074  cmp     dword ptr [r15+10h], 5
0x1800a1079  jz      short loc_1800A10A8
0x1800a107b  mov     r9d, 80070005h
0x1800a1081  mov     ebx, r9d
0x1800a1084  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a108b  cmp     rcx, rsi
0x1800a108e  jz      loc_1800A0FEF
0x1800a1094  test    [rcx+1Ch], dil
0x1800a1098  jz      loc_1800A0FEF
0x1800a109e  mov     edx, 1E6h
0x1800a10a3  jmp     loc_1800A0FDF
0x1800a10a8  cmp     r12d, edi
0x1800a10ab  mov     r12d, [rbp+4Fh+arg_20]
0x1800a10af  jnz     loc_1800A11F6
0x1800a10b5  cmp     r12d, edi
0x1800a10b8  jnz     loc_1800A1179
0x1800a10be  lea     rcx, [r14+30h]
0x1800a10c2  call    cs:__imp_IsAddressesEmpty
0x1800a10c8  test    eax, eax
0x1800a10ca  jnz     loc_1800A1179
0x1800a10d0  xor     r8d, r8d
0x1800a10d3  lea     rdx, [rbp+4Fh+var_98]
0x1800a10d7  lea     rcx, [r14+30h]
0x1800a10db  call    cs:__imp_GetOpenPortorAuthAppAddrAsString
0x1800a10e1  mov     ebx, eax
0x1800a10e3  test    eax, eax
0x1800a10e5  jns     short loc_1800A112A
0x1800a10e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a10ee  cmp     rcx, rsi
0x1800a10f1  jz      loc_1800A0FF3
0x1800a10f7  test    [rcx+1Ch], dil
0x1800a10fb  jz      loc_1800A0FF3
0x1800a1101  mov     edx, 1E7h
0x1800a1106  lea     rax, aGetopenportora_0; "GetOpenPortOrAuthAppAddrAsString"
0x1800a110d  mov     rcx, [rcx+10h]
0x1800a1111  lea     r8, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids
0x1800a1118  mov     r9d, ebx
0x1800a111b  mov     [rsp+100h+var_E0], rax
0x1800a1120  call    WPP_SF_Ds
0x1800a1125  jmp     loc_1800A0FF3
0x1800a112a  mov     rdx, [rbp+4Fh+var_98]
0x1800a112e  lea     r8, asc_1800F7CB0; ","
0x1800a1135  mov     r9, r13
0x1800a1138  mov     [rsp+100h+var_E0], 0
0x1800a1141  lea     rcx, [rbp+4Fh+var_A0]
0x1800a1145  call    cs:__imp_FwStringBuild
0x1800a114b  mov     ebx, eax
0x1800a114d  test    eax, eax
0x1800a114f  jns     short loc_1800A11B7
0x1800a1151  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a1158  cmp     rcx, rsi
0x1800a115b  jz      loc_1800A0FF3
0x1800a1161  test    [rcx+1Ch], dil
0x1800a1165  jz      loc_1800A0FF3
0x1800a116b  mov     edx, 1E8h
0x1800a1170  lea     rax, aFwstringbuild_0; "FwStringBuild"
0x1800a1177  jmp     short loc_1800A110D
0x1800a1179  lea     rdx, [rbp+4Fh+var_A0]
0x1800a117d  mov     rcx, r13
0x1800a1180  call    cs:__imp_FwStringCopy
0x1800a1186  mov     ebx, eax
0x1800a1188  test    eax, eax
0x1800a118a  jns     short loc_1800A11B7
0x1800a118c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a1193  cmp     rcx, rsi
0x1800a1196  jz      loc_1800A0FF3
0x1800a119c  test    [rcx+1Ch], dil
0x1800a11a0  jz      loc_1800A0FF3
0x1800a11a6  mov     edx, 1E9h
0x1800a11ab  lea     rax, aFwstringcopy_0; "FwStringCopy"
0x1800a11b2  jmp     loc_1800A110D
0x1800a11b7  mov     rcx, [rbp+4Fh+var_A0]
0x1800a11bb  lea     rdx, [rbp+4Fh+var_90]
0x1800a11bf  call    cs:__imp_StringToOpenPortOrAuthAppAddress
0x1800a11c5  mov     ebx, eax
0x1800a11c7  test    eax, eax
0x1800a11c9  jns     short loc_1800A11F6
0x1800a11cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a11d2  cmp     rcx, rsi
0x1800a11d5  jz      loc_1800A0FF3
0x1800a11db  test    [rcx+1Ch], dil
0x1800a11df  jz      loc_1800A0FF3
0x1800a11e5  mov     edx, 1EAh
0x1800a11ea  lea     rax, aStringtoopenpo_0; "StringToOpenPortOrAuthAppAddress"
0x1800a11f1  jmp     loc_1800A110D
0x1800a11f6  lea     rcx, [rbp+4Fh+var_90]
0x1800a11fa  call    FwDynamicKeywordMgrFormatAddresses
0x1800a11ff  mov     ebx, eax
0x1800a1201  test    eax, eax
0x1800a1203  jns     short loc_1800A1230
0x1800a1205  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a120c  cmp     rcx, rsi
0x1800a120f  jz      loc_1800A0FF3
0x1800a1215  test    [rcx+1Ch], dil
0x1800a1219  jz      loc_1800A0FF3
0x1800a121f  mov     edx, 1EBh
0x1800a1224  lea     rax, aFwdynamickeywo_2; "FwDynamicKeywordMgrFormatAddresses"
0x1800a122b  jmp     loc_1800A110D
0x1800a1230  lea     rdx, [r14+30h]
0x1800a1234  lea     rcx, [rbp+4Fh+var_90]
0x1800a1238  call    cs:__imp_IsEqualAddresses
0x1800a123e  test    eax, eax
0x1800a1240  jnz     loc_1800A0FF3
0x1800a1246  test    [r14+28h], dil
0x1800a124a  jnz     short loc_1800A128A
0x1800a124c  lea     rdx, [rbp+4Fh+var_90]
0x1800a1250  mov     rcx, r14
0x1800a1253  call    cs:__imp_FwUpdateDynamicKeywordAddressInRegistry
0x1800a1259  mov     ebx, eax
0x1800a125b  test    eax, eax
0x1800a125d  jns     short loc_1800A128A
0x1800a125f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a1266  cmp     rcx, rsi
0x1800a1269  jz      loc_1800A0FF3
0x1800a126f  test    [rcx+1Ch], dil
0x1800a1273  jz      loc_1800A0FF3
0x1800a1279  mov     edx, 1ECh
0x1800a127e  lea     rax, aFwupdatedynami_0; "FwUpdateDynamicKeywordAddressInRegistry"
0x1800a1285  jmp     loc_1800A110D
0x1800a128a  cmp     dword ptr cs:gFwDynamicKeywordMgr, edi
0x1800a1290  jz      short loc_1800A1297
0x1800a1292  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800a1297  lea     rcx, [r14+30h]
0x1800a129b  call    cs:__imp_FwPolioEmptyWFAddresses
0x1800a12a1  mov     eax, [rbp+4Fh+var_78]
0x1800a12a4  lea     rcx, [rbp+4Fh+var_B0]
0x1800a12a8  mov     [r14+48h], eax
0x1800a12ac  mov     rax, [rbp+4Fh+var_70]
0x1800a12b0  mov     [r14+50h], rax
  ... truncated ...
```
