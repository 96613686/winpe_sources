# SvrImpl_FWUpdateDynamicKeywordAddress0(void *,void *,_GUID,ushort const *,int)

- ea: `0x1800a64e4`
- end: `0x1800a6b7f`
- name: `?SvrImpl_FWUpdateDynamicKeywordAddress0@@YAKPEAX0U_GUID@@PEBGH@Z`
- size: `1691`
- prototype: `unsigned int __fastcall(void *, void *, struct _GUID *, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800cc740`

## callees

- `0x180007b58`
- `0x1800089bc`
- `0x180008d60`
- `0x18000a66c`
- `0x18000a710`
- `0x18006cba8`
- `0x18006f5d4`
- `0x1800729c0`
- `0x180073488`
- `0x1800910bc`
- `0x180096fd0`
- `0x180097680`
- `0x180097d80`
- `0x1800a64e4`
- `0x1800a7458`
- `0x1800a79f4`
- `0x1800a7b68`

## import_xrefs

- `fwbase!FwHResultToWindowsError` at `0x1800a6b4b`
- `fwbase!FwHResultToWindowsError` at `0x1800a6b4b`
- `fwbase!IsAddressesEmpty` at `0x1800a6804`
- `fwbase!IsAddressesEmpty` at `0x1800a6804`
- `fwbase!FwStringBuild` at `0x1800a6893`
- `fwbase!FwStringBuild` at `0x1800a6893`
- `fwbase!FwStringCopy` at `0x1800a68d4`
- `fwbase!FwStringCopy` at `0x1800a68d4`
- `fwbase!FwFree` at `0x1800a6b0c`
- `fwbase!FwFree` at `0x1800a6b21`
- `fwbase!FwFree` at `0x1800a6b0c`
- `fwbase!FwFree` at `0x1800a6b21`
- `FWPolicyIOMgr!FwUpdateDynamicKeywordAddressInRegistry` at `0x1800a69b9`
- `FWPolicyIOMgr!FwUpdateDynamicKeywordAddressInRegistry` at `0x1800a69b9`
- `FWPolicyIOMgr!IsEqualAddresses` at `0x1800a6998`
- `FWPolicyIOMgr!IsEqualAddresses` at `0x1800a6998`
- `FWPolicyIOMgr!ValidatePortOrAppAddressString` at `0x1800a6609`
- `FWPolicyIOMgr!ValidatePortOrAppAddressString` at `0x1800a6609`
- `FWPolicyIOMgr!FwGetStoreTypeFromDynamicKeywordOriginType` at `0x1800a6773`
- `FWPolicyIOMgr!FwGetStoreTypeFromDynamicKeywordOriginType` at `0x1800a6773`
- `FWPolicyIOMgr!FwDynamicKeywordAddressIsStringValid` at `0x1800a65ee`
- `FWPolicyIOMgr!FwDynamicKeywordAddressIsStringValid` at `0x1800a65ee`
- `FWPolicyIOMgr!GetOpenPortorAuthAppAddrAsString` at `0x1800a6823`
- `FWPolicyIOMgr!GetOpenPortorAuthAppAddrAsString` at `0x1800a6823`
- `FWPolicyIOMgr!StringToOpenPortOrAuthAppAddress` at `0x1800a6919`
- `FWPolicyIOMgr!StringToOpenPortOrAuthAppAddress` at `0x1800a6919`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x1800a6a07`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x1800a6b31`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x1800a6a07`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x1800a6b31`

## string_xrefs

- `0x1800a653a`: `SvrImpl_FWUpdateDynamicKeywordAddress0`
- `0x1800a6b3d`: `SvrImpl_FWUpdateDynamicKeywordAddress0`
- `0x1800a6854`: `GetOpenPortOrAuthAppAddrAsString`
- `0x1800a694a`: `StringToOpenPortOrAuthAppAddress`
- `0x1800a6905`: `FwStringCopy`
- `0x1800a69ea`: `FwUpdateDynamicKeywordAddressInRegistry`

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
  struct _GUID v30; // [rsp+50h] [rbp-61h] BYREF
  __int64 v31; // [rsp+60h] [rbp-51h] BYREF
  __int64 v32; // [rsp+68h] [rbp-49h] BYREF
  _BYTE v33[24]; // [rsp+70h] [rbp-41h] BYREF
  int v34; // [rsp+88h] [rbp-29h]
  __int64 v35; // [rsp+90h] [rbp-21h]
  int v36; // [rsp+A8h] [rbp-9h]
  __int64 v37; // [rsp+B0h] [rbp-1h]

  v32 = 0;
  v6 = a3;
  v31 = 0;
  memset_0(v33, 0, 0x48u);
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
          (unsigned int)WPP_681457f4cdf23248f51377d70d9ff610_Traceguids,
          OpenPortorAuthAppAddrAsString,
          (__int64)"FwDynamicKeywordMgrLock");
      goto LABEL_89;
    }
    v30 = *v6;
    v19 = FwDynamicKeywordMgrAddressFind(&v30);
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
      WPP_SF_d(*(_QWORD *)(v22 + 16), v23, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids, v21);
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
        OpenPortorAuthAppAddrAsString = FwStringCopy(a4, &v31);
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
        OpenPortorAuthAppAddrAsString = GetOpenPortorAuthAppAddrAsString(v20 + 48, &v32, 0);
        if ( OpenPortorAuthAppAddrAsString < 0 )
        {
          v22 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
            goto LABEL_35;
          v26 = 487;
          v27 = "GetOpenPortOrAuthAppAddrAsString";
          goto LABEL_59;
        }
        OpenPortorAuthAppAddrAsString = FwStringBuild(&v31, v32, L",", a4);
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
      OpenPortorAuthAppAddrAsString = StringToOpenPortOrAuthAppAddress(v31, v33);
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
    OpenPortorAuthAppAddrAsString = FwDynamicKeywordMgrFormatAddresses(v33);
    if ( OpenPortorAuthAppAddrAsString >= 0 )
    {
      if ( (unsigned int)IsEqualAddresses(v33, v20 + 48) )
        goto LABEL_35;
      if ( (*(_BYTE *)(v20 + 40) & 1) != 0
        || (OpenPortorAuthAppAddrAsString = FwUpdateDynamicKeywordAddressInRegistry(v20, v33),
            OpenPortorAuthAppAddrAsString >= 0) )
      {
        if ( (_DWORD)gFwDynamicKeywordMgr != 1 )
          MicrosoftTelemetryAssertTriggeredNoArgs(v22);
        FwPolioEmptyWFAddresses(v20 + 48);
        *(_DWORD *)(v20 + 72) = v34;
        *(_QWORD *)(v20 + 80) = v35;
        *(_DWORD *)(v20 + 104) = v36;
        *(_QWORD *)(v20 + 112) = v37;
        v6 = a3;
        v34 = 0;
        v35 = 0;
        v36 = 0;
        v30 = *a3;
        v37 = 0;
        FwQueueUpdateForRulesWithDynamicKeywordAddress(&v30);
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
      (unsigned int)WPP_681457f4cdf23248f51377d70d9ff610_Traceguids,
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
  WPP_SF_d(*(_QWORD *)(v12 + 16), v15, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids, v13);
LABEL_89:
  v24 = a5;
LABEL_90:
  v30 = *v6;
  FwEventDynamicKeywordAddressUpdate((unsigned int)OpenPortorAuthAppAddrAsString, &v30, v24, v32, a4, v31);
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF_dSS(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      493,
      (unsigned int)WPP_681457f4cdf23248f51377d70d9ff610_Traceguids,
      OpenPortorAuthAppAddrAsString,
      v32,
      v31);
  if ( v32 )
    FwFree(v32);
  if ( v31 )
    FwFree(v31);
  FwPolioEmptyWFAddresses(v33);
  FwReleaseRPCSharedLock("SvrImpl_FWUpdateDynamicKeywordAddress0");
  v11 = (unsigned int)OpenPortorAuthAppAddrAsString;
  return FwHResultToWindowsError(v11);
}

```

## disassembly

```asm
0x1800a64e4  mov     [rsp-8+arg_0], rbx
0x1800a64e9  push    rbp
0x1800a64ea  push    rsi
0x1800a64eb  push    rdi
0x1800a64ec  push    r12
0x1800a64ee  push    r13
0x1800a64f0  push    r14
0x1800a64f2  push    r15
0x1800a64f4  lea     rbp, [rsp-1Fh]
0x1800a64f9  sub     rsp, 0D0h
0x1800a6500  mov     rax, cs:__security_cookie
0x1800a6507  xor     rax, rsp
0x1800a650a  mov     [rbp+4Fh+var_40], rax
0x1800a650e  mov     r15, rdx
0x1800a6511  mov     [rbp+4Fh+var_C0], r8
0x1800a6515  xor     edx, edx; Val
0x1800a6517  mov     [rbp+4Fh+var_98], 0
0x1800a651f  mov     r14, r8
0x1800a6522  mov     [rbp+4Fh+var_A0], 0
0x1800a652a  lea     rcx, [rbp+4Fh+var_90]; void *
0x1800a652e  mov     r13, r9
0x1800a6531  lea     r8d, [rdx+48h]; Size
0x1800a6535  call    memset_0
0x1800a653a  lea     rcx, aSvrimplFwupdat; "SvrImpl_FWUpdateDynamicKeywordAddress0"
0x1800a6541  call    FwAcquireRPCSharedLock
0x1800a6546  test    eax, eax
0x1800a6548  jns     short loc_1800A6551
0x1800a654a  mov     ecx, eax
0x1800a654c  jmp     loc_1800A6B4B
0x1800a6551  mov     r9d, [r15+18h]
0x1800a6555  cmp     r9d, 2
0x1800a6559  jz      short loc_1800A65B4
0x1800a655b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a6562  lea     rsi, WPP_GLOBAL_Control
0x1800a6569  mov     edi, 1
0x1800a656e  cmp     rcx, rsi
0x1800a6571  jz      short loc_1800A658E
0x1800a6573  test    [rcx+1Ch], dil
0x1800a6577  jz      short loc_1800A658E
0x1800a6579  mov     rcx, [rcx+10h]
0x1800a657d  mov     edx, 1DCh
0x1800a6582  call    WPP_SF_l
0x1800a6587  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a658e  mov     r9d, 80070005h
0x1800a6594  mov     ebx, r9d
0x1800a6597  cmp     rcx, rsi
0x1800a659a  jz      loc_1800A6A9A
0x1800a65a0  test    [rcx+1Ch], dil
0x1800a65a4  jz      loc_1800A6A9A
0x1800a65aa  mov     edx, 1DDh
0x1800a65af  jmp     loc_1800A6A8A
0x1800a65b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a65bb  lea     rsi, WPP_GLOBAL_Control
0x1800a65c2  mov     ebx, [rbp+4Fh+arg_20]
0x1800a65c5  cmp     rcx, rsi
0x1800a65c8  jz      short loc_1800A65EB
0x1800a65ca  test    byte ptr [rcx+1Ch], 4
0x1800a65ce  jz      short loc_1800A65EB
0x1800a65d0  mov     r9d, [r15+10h]
0x1800a65d4  mov     rcx, [rcx+10h]
0x1800a65d8  mov     [rsp+100h+var_D0], ebx
0x1800a65dc  mov     [rsp+100h+var_D8], r13
0x1800a65e1  mov     [rsp+100h+var_E0], r14
0x1800a65e6  call    WPP_SF_d_guid_Sd
0x1800a65eb  mov     rcx, r13
0x1800a65ee  call    cs:__imp_FwDynamicKeywordAddressIsStringValid
0x1800a65f5  nop     dword ptr [rax+rax+00h]
0x1800a65fa  mov     edi, 1
0x1800a65ff  mov     r12d, eax
0x1800a6602  cmp     eax, edi
0x1800a6604  jnz     short loc_1800A6646
0x1800a6606  mov     rcx, r13
0x1800a6609  call    cs:__imp_ValidatePortOrAppAddressString
0x1800a6610  nop     dword ptr [rax+rax+00h]
0x1800a6615  test    eax, eax
0x1800a6617  jz      short loc_1800A6678
0x1800a6619  mov     r9d, 80070057h
0x1800a661f  mov     ebx, r9d
0x1800a6622  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a6629  cmp     rcx, rsi
0x1800a662c  jz      loc_1800A6A9A
0x1800a6632  test    [rcx+1Ch], dil
0x1800a6636  jz      loc_1800A6A9A
0x1800a663c  mov     edx, 1DFh
0x1800a6641  jmp     loc_1800A6A8A
0x1800a6646  test    r12d, r12d
0x1800a6649  jnz     short loc_1800A6678
0x1800a664b  cmp     ebx, edi
0x1800a664d  jnz     short loc_1800A6678
0x1800a664f  xor     ebx, ebx
0x1800a6651  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a6658  cmp     rcx, rsi
0x1800a665b  jz      loc_1800A6A9A
0x1800a6661  test    [rcx+1Ch], dil
0x1800a6665  jz      loc_1800A6A9A
0x1800a666b  mov     edx, 1E0h
0x1800a6670  xor     r9d, r9d
0x1800a6673  jmp     loc_1800A6A8A
0x1800a6678  mov     eax, [r15+10h]
0x1800a667c  cmp     eax, 0Bh
0x1800a667f  ja      loc_1800A6A6A
0x1800a6685  mov     ecx, 824h
0x1800a668a  bt      ecx, eax
0x1800a668d  jnb     loc_1800A6A6A
0x1800a6693  call    FwDynamicKeywordMgrLock
0x1800a6698  mov     ebx, eax
0x1800a669a  test    eax, eax
0x1800a669c  jns     short loc_1800A66E1
0x1800a669e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a66a5  cmp     rcx, rsi
0x1800a66a8  jz      loc_1800A6A9A
0x1800a66ae  test    [rcx+1Ch], dil
0x1800a66b2  jz      loc_1800A6A9A
0x1800a66b8  mov     rcx, [rcx+10h]
0x1800a66bc  lea     rax, aFwdynamickeywo_4; "FwDynamicKeywordMgrLock"
0x1800a66c3  mov     edx, 1E2h
0x1800a66c8  mov     [rsp+100h+var_E0], rax
0x1800a66cd  mov     r9d, ebx
0x1800a66d0  lea     r8, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids
0x1800a66d7  call    WPP_SF_Ds
0x1800a66dc  jmp     loc_1800A6A9A
0x1800a66e1  movaps  xmm0, xmmword ptr [r14]
0x1800a66e5  lea     rcx, [rbp+4Fh+var_B0]
0x1800a66e9  movdqa  [rbp+4Fh+var_B0], xmm0
0x1800a66ee  call    FwDynamicKeywordMgrAddressFind
0x1800a66f3  mov     r14, rax
0x1800a66f6  test    rax, rax
0x1800a66f9  jnz     short loc_1800A673D
0x1800a66fb  mov     r9d, 80070057h
0x1800a6701  mov     ebx, r9d
0x1800a6704  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a670b  cmp     rcx, rsi
0x1800a670e  jz      short loc_1800A672B
0x1800a6710  test    [rcx+1Ch], dil
0x1800a6714  jz      short loc_1800A672B
0x1800a6716  mov     edx, 1E3h
0x1800a671b  mov     rcx, [rcx+10h]
0x1800a671f  lea     r8, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids
0x1800a6726  call    WPP_SF_d
0x1800a672b  mov     r12d, [rbp+4Fh+arg_20]
0x1800a672f  mov     r14, [rbp+4Fh+var_C0]
0x1800a6733  call    FwDynamicKeywordMgrUnlock
0x1800a6738  jmp     loc_1800A6A9E
0x1800a673d  test    [rax+28h], dil
0x1800a6741  jz      short loc_1800A6770
0x1800a6743  cmp     dword ptr [r15+10h], 5
0x1800a6748  jz      loc_1800A67EA
0x1800a674e  mov     r9d, 80070005h
0x1800a6754  mov     ebx, r9d
0x1800a6757  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a675e  cmp     rcx, rsi
0x1800a6761  jz      short loc_1800A672B
0x1800a6763  test    [rcx+1Ch], dil
0x1800a6767  jz      short loc_1800A672B
0x1800a6769  mov     edx, 1E4h
0x1800a676e  jmp     short loc_1800A671B
0x1800a6770  mov     ecx, [rax+78h]
0x1800a6773  call    cs:__imp_FwGetStoreTypeFromDynamicKeywordOriginType
0x1800a677a  nop     dword ptr [rax+rax+00h]
0x1800a677f  cmp     eax, 0Bh
0x1800a6782  jnz     short loc_1800A67AF
0x1800a6784  cmp     [r15+10h], eax
0x1800a6788  jz      short loc_1800A67EA
0x1800a678a  mov     r9d, 80070005h
0x1800a6790  mov     ebx, r9d
0x1800a6793  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a679a  cmp     rcx, rsi
0x1800a679d  jz      short loc_1800A672B
0x1800a679f  test    [rcx+1Ch], dil
0x1800a67a3  jz      short loc_1800A672B
0x1800a67a5  mov     edx, 1E5h
0x1800a67aa  jmp     loc_1800A671B
0x1800a67af  cmp     dword ptr [r15+10h], 2
0x1800a67b4  jz      short loc_1800A67EA
0x1800a67b6  cmp     dword ptr [r15+10h], 5
0x1800a67bb  jz      short loc_1800A67EA
0x1800a67bd  mov     r9d, 80070005h
0x1800a67c3  mov     ebx, r9d
0x1800a67c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a67cd  cmp     rcx, rsi
0x1800a67d0  jz      loc_1800A672B
0x1800a67d6  test    [rcx+1Ch], dil
0x1800a67da  jz      loc_1800A672B
0x1800a67e0  mov     edx, 1E6h
0x1800a67e5  jmp     loc_1800A671B
0x1800a67ea  cmp     r12d, edi
0x1800a67ed  mov     r12d, [rbp+4Fh+arg_20]
0x1800a67f1  jnz     loc_1800A6956
0x1800a67f7  cmp     r12d, edi
0x1800a67fa  jnz     loc_1800A68CD
0x1800a6800  lea     rcx, [r14+30h]
0x1800a6804  call    cs:__imp_IsAddressesEmpty
0x1800a680b  nop     dword ptr [rax+rax+00h]
0x1800a6810  test    eax, eax
0x1800a6812  jnz     loc_1800A68CD
0x1800a6818  xor     r8d, r8d
0x1800a681b  lea     rdx, [rbp+4Fh+var_98]
0x1800a681f  lea     rcx, [r14+30h]
0x1800a6823  call    cs:__imp_GetOpenPortorAuthAppAddrAsString
0x1800a682a  nop     dword ptr [rax+rax+00h]
0x1800a682f  mov     ebx, eax
0x1800a6831  test    eax, eax
0x1800a6833  jns     short loc_1800A6878
0x1800a6835  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a683c  cmp     rcx, rsi
0x1800a683f  jz      loc_1800A672F
0x1800a6845  test    [rcx+1Ch], dil
0x1800a6849  jz      loc_1800A672F
0x1800a684f  mov     edx, 1E7h
0x1800a6854  lea     rax, aGetopenportora_0; "GetOpenPortOrAuthAppAddrAsString"
0x1800a685b  mov     rcx, [rcx+10h]
0x1800a685f  lea     r8, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids
0x1800a6866  mov     r9d, ebx
0x1800a6869  mov     [rsp+100h+var_E0], rax
0x1800a686e  call    WPP_SF_Ds
0x1800a6873  jmp     loc_1800A672F
0x1800a6878  mov     rdx, [rbp+4Fh+var_98]
0x1800a687c  lea     r8, asc_1800FDD80; ","
0x1800a6883  mov     r9, r13
0x1800a6886  mov     [rsp+100h+var_E0], 0
0x1800a688f  lea     rcx, [rbp+4Fh+var_A0]
0x1800a6893  call    cs:__imp_FwStringBuild
0x1800a689a  nop     dword ptr [rax+rax+00h]
0x1800a689f  mov     ebx, eax
0x1800a68a1  test    eax, eax
0x1800a68a3  jns     short loc_1800A6911
0x1800a68a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a68ac  cmp     rcx, rsi
0x1800a68af  jz      loc_1800A672F
0x1800a68b5  test    [rcx+1Ch], dil
0x1800a68b9  jz      loc_1800A672F
0x1800a68bf  mov     edx, 1E8h
0x1800a68c4  lea     rax, aFwstringbuild_0; "FwStringBuild"
0x1800a68cb  jmp     short loc_1800A685B
0x1800a68cd  lea     rdx, [rbp+4Fh+var_A0]
0x1800a68d1  mov     rcx, r13
0x1800a68d4  call    cs:__imp_FwStringCopy
0x1800a68db  nop     dword ptr [rax+rax+00h]
0x1800a68e0  mov     ebx, eax
0x1800a68e2  test    eax, eax
0x1800a68e4  jns     short loc_1800A6911
0x1800a68e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a68ed  cmp     rcx, rsi
0x1800a68f0  jz      loc_1800A672F
0x1800a68f6  test    [rcx+1Ch], dil
0x1800a68fa  jz      loc_1800A672F
0x1800a6900  mov     edx, 1E9h
0x1800a6905  lea     rax, aFwstringcopy_0; "FwStringCopy"
0x1800a690c  jmp     loc_1800A685B
0x1800a6911  mov     rcx, [rbp+4Fh+var_A0]
0x1800a6915  lea     rdx, [rbp+4Fh+var_90]
0x1800a6919  call    cs:__imp_StringToOpenPortOrAuthAppAddress
0x1800a6920  nop     dword ptr [rax+rax+00h]
0x1800a6925  mov     ebx, eax
0x1800a6927  test    eax, eax
0x1800a6929  jns     short loc_1800A6956
0x1800a692b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a6932  cmp     rcx, rsi
0x1800a6935  jz      loc_1800A672F
0x1800a693b  test    [rcx+1Ch], dil
0x1800a693f  jz      loc_1800A672F
0x1800a6945  mov     edx, 1EAh
0x1800a694a  lea     rax, aStringtoopenpo_0; "StringToOpenPortOrAuthAppAddress"
0x1800a6951  jmp     loc_1800A685B
0x1800a6956  lea     rcx, [rbp+4Fh+var_90]
0x1800a695a  call    FwDynamicKeywordMgrFormatAddresses
0x1800a695f  mov     ebx, eax
0x1800a6961  test    eax, eax
0x1800a6963  jns     short loc_1800A6990
0x1800a6965  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a696c  cmp     rcx, rsi
0x1800a696f  jz      loc_1800A672F
0x1800a6975  test    [rcx+1Ch], dil
0x1800a6979  jz      loc_1800A672F
0x1800a697f  mov     edx, 1EBh
0x1800a6984  lea     rax, aFwdynamickeywo_2; "FwDynamicKeywordMgrFormatAddresses"
0x1800a698b  jmp     loc_1800A685B
0x1800a6990  lea     rdx, [r14+30h]
0x1800a6994  lea     rcx, [rbp+4Fh+var_90]
0x1800a6998  call    cs:__imp_IsEqualAddresses
0x1800a699f  nop     dword ptr [rax+rax+00h]
0x1800a69a4  test    eax, eax
0x1800a69a6  jnz     loc_1800A672F
0x1800a69ac  test    [r14+28h], dil
0x1800a69b0  jnz     short loc_1800A69F6
0x1800a69b2  lea     rdx, [rbp+4Fh+var_90]
0x1800a69b6  mov     rcx, r14
0x1800a69b9  call    cs:__imp_FwUpdateDynamicKeywordAddressInRegistry
0x1800a69c0  nop     dword ptr [rax+rax+00h]
0x1800a69c5  mov     ebx, eax
0x1800a69c7  test    eax, eax
0x1800a69c9  jns     short loc_1800A69F6
0x1800a69cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a69d2  cmp     rcx, rsi
0x1800a69d5  jz      loc_1800A672F
0x1800a69db  test    [rcx+1Ch], dil
0x1800a69df  jz      loc_1800A672F
0x1800a69e5  mov     edx, 1ECh
0x1800a69ea  lea     rax, aFwupdatedynami_0; "FwUpdateDynamicKeywordAddressInRegistry"
0x1800a69f1  jmp     loc_1800A685B
  ... truncated ...
```
