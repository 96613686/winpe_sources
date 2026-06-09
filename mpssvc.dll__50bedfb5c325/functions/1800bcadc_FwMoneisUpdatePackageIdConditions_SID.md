# FwMoneisUpdatePackageIdConditions(_SID *)

- ea: `0x1800bcadc`
- end: `0x1800bd0a7`
- name: `?FwMoneisUpdatePackageIdConditions@@YAKPEAU_SID@@@Z`
- size: `1483`
- prototype: `unsigned int __fastcall(PSID pSid2)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180037aa0`

## callees

- `0x18000a710`
- `0x1800192e0`
- `0x1800729c0`
- `0x180073488`
- `0x18008b9f8`
- `0x1800bb710`
- `0x1800bcadc`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800bceae`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800bceae`
- `fwpuclnt!FwpmEngineOpen0` at `0x1800bcced`
- `fwpuclnt!FwpmEngineOpen0` at `0x1800bcd3f`
- `fwpuclnt!FwpmEngineOpen0` at `0x1800bcced`
- `fwpuclnt!FwpmEngineOpen0` at `0x1800bcd3f`
- `fwpuclnt!FwpmEngineClose0` at `0x1800bd051`
- `fwpuclnt!FwpmEngineClose0` at `0x1800bd051`
- `fwpuclnt!FwpmFreeMemory0` at `0x1800bcf2d`
- `fwpuclnt!FwpmFreeMemory0` at `0x1800bd00f`
- `fwpuclnt!FwpmFreeMemory0` at `0x1800bcf2d`
- `fwpuclnt!FwpmFreeMemory0` at `0x1800bd00f`
- `fwpuclnt!FwpmFilterDestroyEnumHandle0` at `0x1800bcf4d`
- `fwpuclnt!FwpmFilterDestroyEnumHandle0` at `0x1800bd031`
- `fwpuclnt!FwpmFilterDestroyEnumHandle0` at `0x1800bcf4d`
- `fwpuclnt!FwpmFilterDestroyEnumHandle0` at `0x1800bd031`
- `fwpuclnt!FwpmFilterEnum0` at `0x1800bce31`
- `fwpuclnt!FwpmFilterEnum0` at `0x1800bce31`
- `fwpuclnt!FwpmFilterDeleteByKey0` at `0x1800bcec6`
- `fwpuclnt!FwpmFilterDeleteByKey0` at `0x1800bcec6`
- `fwpuclnt!FwpmFilterAdd0` at `0x1800bceee`
- `fwpuclnt!FwpmFilterAdd0` at `0x1800bceee`

## pseudocode

```c
__int64 __fastcall FwMoneisUpdatePackageIdConditions(PSID pSid2)
{
  UINT32 v1; // r15d
  DWORD v3; // ebx
  __int64 v4; // rcx
  int v5; // eax
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rcx
  DWORD v12; // eax
  __int64 v13; // rdx
  unsigned int v14; // r12d
  unsigned int (*v15)(void *, struct FWPM_FILTER_ENUM_TEMPLATE0_ *, void **); // r13
  __int128 v16; // xmm0
  __int64 v17; // rdx
  UINT32 v18; // r14d
  __int64 v19; // r9
  FWPM_FILTER0 *v20; // rsi
  FWPM_FILTER_CONDITION0 *filterCondition; // r8
  __int64 v22; // rax
  HANDLE engineHandle; // [rsp+30h] [rbp-D0h] BYREF
  FWPM_FILTER0 **entries; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE enumHandle[2]; // [rsp+40h] [rbp-C0h] BYREF
  FWPM_SESSION0 session; // [rsp+50h] [rbp-B0h] BYREF
  int v28; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v29; // [rsp+A4h] [rbp-5Ch]
  _BYTE v30[20]; // [rsp+B4h] [rbp-4Ch] BYREF
  __int64 v31; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v32; // [rsp+D8h] [rbp-28h]
  int v33; // [rsp+E8h] [rbp-18h]
  int v34; // [rsp+ECh] [rbp-14h]
  __int64 v35; // [rsp+F0h] [rbp-10h]
  int v36; // [rsp+F8h] [rbp-8h]
  int *v37; // [rsp+100h] [rbp+0h]
  int v38; // [rsp+108h] [rbp+8h]
  __int64 v39; // [rsp+110h] [rbp+10h]
  UINT32 numEntriesReturned; // [rsp+120h] [rbp+20h] BYREF

  v1 = 0;
  engineHandle = 0;
  enumHandle[0] = 0;
  v3 = 0;
  memset_0(&v31, 0, 0x48u);
  v28 = 0;
  entries = 0;
  v29 = 0;
  memset(v30, 0, sizeof(v30));
  numEntriesReturned = 0;
  v4 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 43, WPP_63b07f154e59352ff1fc5e97167f3127_Traceguids);
  v5 = lambda_686ee172e884bb71eaeae249b5a6c9df_::operator()(v4, 2, pSid2);
  if ( v5 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_71;
    v8 = 44;
LABEL_8:
    WPP_SF_d(*(_QWORD *)(v7 + 16), v8, WPP_63b07f154e59352ff1fc5e97167f3127_Traceguids, (unsigned int)v5);
LABEL_70:
    v7 = WPP_GLOBAL_Control;
    goto LABEL_71;
  }
  v5 = lambda_686ee172e884bb71eaeae249b5a6c9df_::operator()(v6, 8, pSid2);
  if ( v5 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_71;
    v8 = 45;
    goto LABEL_8;
  }
  v5 = lambda_686ee172e884bb71eaeae249b5a6c9df_::operator()(v9, 10, pSid2);
  if ( v5 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_71;
    v8 = 46;
    goto LABEL_8;
  }
  v5 = lambda_686ee172e884bb71eaeae249b5a6c9df_::operator()(v10, 11, pSid2);
  if ( v5 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_71;
    v8 = 47;
    goto LABEL_8;
  }
  v5 = lambda_686ee172e884bb71eaeae249b5a6c9df_::operator()(v11, 6, pSid2);
  if ( v5 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_71;
    v8 = 48;
    goto LABEL_8;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_FwBfeSessions>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BugFix_FwBfeSessions>::GetImpl'::`2'::impl) )
  {
    *(_QWORD *)&session.sessionKey.Data1 = 0;
    session.displayData.name = L"Firewall App Isolation Enumeration";
    *(_QWORD *)session.sessionKey.Data4 = 0;
    memset(&session.processId + 1, 0, 28);
    session.displayData.description = 0;
    session.flags = 0;
    *(_QWORD *)&session.txnWaitTimeoutInMSec = 18000000;
    v12 = FwpmEngineOpen0(0, 0xAu, 0, &session, &engineHandle);
    v3 = v12;
    if ( v12 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_71;
      v13 = 49;
LABEL_30:
      WPP_SF_d(*(_QWORD *)(v7 + 16), v13, WPP_63b07f154e59352ff1fc5e97167f3127_Traceguids, v12);
      goto LABEL_70;
    }
  }
  else
  {
    v12 = FwpmEngineOpen0(0, 0xAu, 0, 0, &engineHandle);
    v3 = v12;
    if ( v12 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_71;
      v13 = 50;
      goto LABEL_30;
    }
  }
  v14 = 0;
  v15 = pFuncFwpmFilterCreateEnumHandle;
  *(_QWORD *)&v29 = *(_QWORD *)((char *)&FWPM_CONDITION_ALE_PACKAGE_ID + 4);
  v28 = 1908177146;
  *((_QWORD *)&v29 + 1) = HIDWORD(FWPM_CONDITION_ALE_PACKAGE_ID);
  *(_DWORD *)&v30[4] = 13;
  *(_QWORD *)&v30[12] = pSid2;
LABEL_36:
  if ( v14 >= 0x10 )
    goto LABEL_70;
  v36 = 1;
  v37 = &v28;
  v38 = -1;
  v35 = 0;
  v33 = 0;
  v31 = 0;
  v16 = *(_OWORD *)&qword_180131BA0[2 * v14];
  v34 = 2;
  v32 = v16;
  v39 = 0;
  v12 = ((__int64 (__fastcall *)(HANDLE, __int64 *, HANDLE *))v15)(engineHandle, &v31, enumHandle);
  v3 = v12;
  if ( v12 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_71;
    v13 = 51;
    goto LABEL_30;
  }
  v12 = FwpmFilterEnum0(engineHandle, enumHandle[0], 0xFFFFFFFF, &entries, &numEntriesReturned);
  v3 = v12;
  if ( v12 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_71;
    v13 = 52;
    goto LABEL_30;
  }
  v17 = *((_QWORD *)&FWPM_CONDITION_ALE_PACKAGE_ID + 1);
  v18 = 0;
  v19 = FWPM_CONDITION_ALE_PACKAGE_ID;
  while ( 1 )
  {
    if ( v18 >= numEntriesReturned )
    {
      if ( entries )
      {
        FwpmFreeMemory0((void **)&entries);
        entries = 0;
      }
      if ( enumHandle[0] )
      {
        FwpmFilterDestroyEnumHandle0(engineHandle, enumHandle[0]);
        enumHandle[0] = 0;
      }
      ++v14;
      goto LABEL_36;
    }
    v20 = entries[v18];
    if ( (v20->flags & 0x4000) == 0 )
      break;
LABEL_52:
    ++v18;
  }
  while ( 1 )
  {
    if ( v1 >= v20->numFilterConditions )
    {
      v1 = 0;
      goto LABEL_52;
    }
    filterCondition = v20->filterCondition;
    v22 = *(_QWORD *)&filterCondition[v1].fieldKey.Data1 - v19;
    if ( !v22 )
      v22 = *(_QWORD *)filterCondition[v1].fieldKey.Data4 - v17;
    if ( v22 )
      goto LABEL_50;
    if ( !EqualSid(filterCondition[v1].conditionValue.uint64, pSid2) )
      goto LABEL_49;
    v12 = FwpmFilterDeleteByKey0(engineHandle, &v20->filterKey);
    v3 = v12;
    if ( v12 )
      break;
    v12 = FwpmFilterAdd0(engineHandle, v20, 0, &v20->filterId);
    v3 = v12;
    if ( v12 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v13 = 54;
        goto LABEL_30;
      }
      goto LABEL_71;
    }
LABEL_49:
    v17 = *((_QWORD *)&FWPM_CONDITION_ALE_PACKAGE_ID + 1);
    v19 = FWPM_CONDITION_ALE_PACKAGE_ID;
LABEL_50:
    ++v1;
  }
  v7 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    v13 = 53;
    goto LABEL_30;
  }
LABEL_71:
  if ( entries )
  {
    FwpmFreeMemory0((void **)&entries);
    v7 = WPP_GLOBAL_Control;
  }
  if ( enumHandle[0] )
  {
    FwpmFilterDestroyEnumHandle0(engineHandle, enumHandle[0]);
    v7 = WPP_GLOBAL_Control;
  }
  if ( engineHandle )
  {
    FwpmEngineClose0(engineHandle);
    v7 = WPP_GLOBAL_Control;
  }
  if ( (_UNKNOWN *)v7 != &WPP_GLOBAL_Control && (*(_BYTE *)(v7 + 28) & 8) != 0 )
    WPP_SF_(*(_QWORD *)(v7 + 16), 55, WPP_63b07f154e59352ff1fc5e97167f3127_Traceguids);
  return v3;
}

```

## disassembly

```asm
0x1800bcadc  push    rbp
0x1800bcade  push    rbx
0x1800bcadf  push    rsi
0x1800bcae0  push    rdi
0x1800bcae1  push    r12
0x1800bcae3  push    r13
0x1800bcae5  push    r14
0x1800bcae7  push    r15
0x1800bcae9  lea     rbp, [rsp-38h]
0x1800bcaee  sub     rsp, 138h
0x1800bcaf5  mov     rax, cs:__security_cookie
0x1800bcafc  xor     rax, rsp
0x1800bcaff  mov     [rbp+70h+var_48], rax
0x1800bcb03  xor     r15d, r15d
0x1800bcb06  mov     rdi, rcx
0x1800bcb09  xor     edx, edx; Val
0x1800bcb0b  mov     [rsp+170h+var_140], r15
0x1800bcb10  lea     rcx, [rbp+70h+var_A0]; void *
0x1800bcb14  mov     [rsp+170h+enumHandle], r15
0x1800bcb19  mov     ebx, r15d
0x1800bcb1c  lea     r8d, [r15+48h]; Size
0x1800bcb20  call    memset_0
0x1800bcb25  xorps   xmm0, xmm0
0x1800bcb28  mov     [rbp+70h+var_D0], r15d
0x1800bcb2c  xor     eax, eax
0x1800bcb2e  mov     [rsp+170h+entries], r15
0x1800bcb33  movups  [rbp+70h+var_CC], xmm0
0x1800bcb37  mov     [rbp+70h+var_AC], eax
0x1800bcb3a  movups  [rbp+70h+var_BC], xmm0
0x1800bcb3e  mov     [rbp+70h+numEntriesReturned], r15d
0x1800bcb42  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bcb49  lea     rsi, WPP_GLOBAL_Control
0x1800bcb50  lea     r14, WPP_63b07f154e59352ff1fc5e97167f3127_Traceguids
0x1800bcb57  cmp     rcx, rsi
0x1800bcb5a  jz      short loc_1800BCB71
0x1800bcb5c  test    byte ptr [rcx+1Ch], 8
0x1800bcb60  jz      short loc_1800BCB71
0x1800bcb62  mov     rcx, [rcx+10h]
0x1800bcb66  lea     edx, [rax+2Bh]
0x1800bcb69  mov     r8, r14
0x1800bcb6c  call    WPP_SF_
0x1800bcb71  mov     r8, rdi
0x1800bcb74  mov     edx, 2
0x1800bcb79  call    _lambda_686ee172e884bb71eaeae249b5a6c9df___operator__
0x1800bcb7e  test    eax, eax
0x1800bcb80  jns     short loc_1800BCBB5
0x1800bcb82  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bcb89  cmp     rcx, rsi
0x1800bcb8c  jz      loc_1800BD002
0x1800bcb92  test    byte ptr [rcx+1Ch], 1
0x1800bcb96  jz      loc_1800BD002
0x1800bcb9c  mov     edx, 2Ch ; ','
0x1800bcba1  mov     rcx, [rcx+10h]
0x1800bcba5  mov     r9d, eax
0x1800bcba8  mov     r8, r14
0x1800bcbab  call    WPP_SF_d
0x1800bcbb0  jmp     loc_1800BCFFB
0x1800bcbb5  mov     r8, rdi
0x1800bcbb8  mov     edx, 8
0x1800bcbbd  call    _lambda_686ee172e884bb71eaeae249b5a6c9df___operator__
0x1800bcbc2  test    eax, eax
0x1800bcbc4  jns     short loc_1800BCBE7
0x1800bcbc6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bcbcd  cmp     rcx, rsi
0x1800bcbd0  jz      loc_1800BD002
0x1800bcbd6  test    byte ptr [rcx+1Ch], 1
0x1800bcbda  jz      loc_1800BD002
0x1800bcbe0  mov     edx, 2Dh ; '-'
0x1800bcbe5  jmp     short loc_1800BCBA1
0x1800bcbe7  mov     r12d, 0Ah
0x1800bcbed  mov     r8, rdi
0x1800bcbf0  mov     edx, r12d
0x1800bcbf3  call    _lambda_686ee172e884bb71eaeae249b5a6c9df___operator__
0x1800bcbf8  test    eax, eax
0x1800bcbfa  jns     short loc_1800BCC1D
0x1800bcbfc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bcc03  cmp     rcx, rsi
0x1800bcc06  jz      loc_1800BD002
0x1800bcc0c  test    byte ptr [rcx+1Ch], 1
0x1800bcc10  jz      loc_1800BD002
0x1800bcc16  lea     edx, [r12+24h]
0x1800bcc1b  jmp     short loc_1800BCBA1
0x1800bcc1d  mov     r8, rdi
0x1800bcc20  mov     edx, 0Bh
0x1800bcc25  call    _lambda_686ee172e884bb71eaeae249b5a6c9df___operator__
0x1800bcc2a  test    eax, eax
0x1800bcc2c  jns     short loc_1800BCC52
0x1800bcc2e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bcc35  cmp     rcx, rsi
0x1800bcc38  jz      loc_1800BD002
0x1800bcc3e  test    byte ptr [rcx+1Ch], 1
0x1800bcc42  jz      loc_1800BD002
0x1800bcc48  mov     edx, 2Fh ; '/'
0x1800bcc4d  jmp     loc_1800BCBA1
0x1800bcc52  mov     r8, rdi
0x1800bcc55  mov     edx, 6
0x1800bcc5a  call    _lambda_686ee172e884bb71eaeae249b5a6c9df___operator__
0x1800bcc5f  test    eax, eax
0x1800bcc61  jns     short loc_1800BCC87
0x1800bcc63  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bcc6a  cmp     rcx, rsi
0x1800bcc6d  jz      loc_1800BD002
0x1800bcc73  test    byte ptr [rcx+1Ch], 1
0x1800bcc77  jz      loc_1800BD002
0x1800bcc7d  mov     edx, 30h ; '0'
0x1800bcc82  jmp     loc_1800BCBA1
0x1800bcc87  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BugFix_FwBfeSessions@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_FwBfeSessions@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_FwBfeSessions> `wil::Feature<__WilFeatureTraits_Feature_BugFix_FwBfeSessions>::GetImpl(void)'::`2'::impl
0x1800bcc8e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_FwBfeSessions@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_FwBfeSessions>::__private_IsEnabled(void)
0x1800bcc93  xor     r8d, r8d; authIdentity
0x1800bcc96  xor     ecx, ecx; serverName
0x1800bcc98  mov     edx, r12d; authnService
0x1800bcc9b  test    al, al
0x1800bcc9d  jz      loc_1800BCD32
0x1800bcca3  lea     rax, aFirewallAppIso; "Firewall App Isolation Enumeration"
0x1800bccaa  mov     qword ptr [rsp+170h+session.sessionKey.Data1], r15
0x1800bccaf  mov     [rsp+170h+session.displayData.name], rax
0x1800bccb4  lea     r9, [rsp+170h+session]; session
0x1800bccb9  xor     eax, eax
0x1800bccbb  mov     qword ptr [rsp+170h+session.sessionKey.Data4], r15
0x1800bccc0  mov     dword ptr [rsp+170h+session+2Ch], eax
0x1800bccc4  xorps   xmm0, xmm0
0x1800bccc7  lea     rax, [rsp+170h+var_140]
0x1800bcccc  mov     [rsp+170h+session.displayData.description], r15
0x1800bccd1  mov     [rsp+170h+engineHandle], rax; engineHandle
0x1800bccd6  mov     [rsp+170h+session.flags], r15d
0x1800bccdb  mov     qword ptr [rsp+170h+session.txnWaitTimeoutInMSec], 112A880h
0x1800bcce4  movdqa  xmmword ptr [rbp+70h+session.sid], xmm0
0x1800bcce9  mov     qword ptr [rbp+70h+session.kernelMode], r15
0x1800bcced  call    cs:__imp_FwpmEngineOpen0
0x1800bccf4  nop     dword ptr [rax+rax+00h]
0x1800bccf9  mov     ebx, eax
0x1800bccfb  test    eax, eax
0x1800bccfd  jz      short loc_1800BCD72
0x1800bccff  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bcd06  cmp     rcx, rsi
0x1800bcd09  jz      loc_1800BD002
0x1800bcd0f  test    byte ptr [rcx+1Ch], 1
0x1800bcd13  jz      loc_1800BD002
0x1800bcd19  mov     edx, 31h ; '1'
0x1800bcd1e  mov     r8, r14
0x1800bcd21  mov     rcx, [rcx+10h]
0x1800bcd25  mov     r9d, eax
0x1800bcd28  call    WPP_SF_d
0x1800bcd2d  jmp     loc_1800BCFFB
0x1800bcd32  lea     rax, [rsp+170h+var_140]
0x1800bcd37  xor     r9d, r9d; session
0x1800bcd3a  mov     [rsp+170h+engineHandle], rax; engineHandle
0x1800bcd3f  call    cs:__imp_FwpmEngineOpen0
0x1800bcd46  nop     dword ptr [rax+rax+00h]
0x1800bcd4b  mov     ebx, eax
0x1800bcd4d  test    eax, eax
0x1800bcd4f  jz      short loc_1800BCD72
0x1800bcd51  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bcd58  cmp     rcx, rsi
0x1800bcd5b  jz      loc_1800BD002
0x1800bcd61  test    byte ptr [rcx+1Ch], 1
0x1800bcd65  jz      loc_1800BD002
0x1800bcd6b  mov     edx, 32h ; '2'
0x1800bcd70  jmp     short loc_1800BCD1E
0x1800bcd72  movsd   xmm0, qword ptr cs:FWPM_CONDITION_ALE_PACKAGE_ID+4
0x1800bcd7a  mov     r12d, r15d
0x1800bcd7d  mov     eax, dword ptr cs:FWPM_CONDITION_ALE_PACKAGE_ID+0Ch
0x1800bcd83  mov     r13, cs:?pFuncFwpmFilterCreateEnumHandle@@3P6AKPEAXPEAUFWPM_FILTER_ENUM_TEMPLATE0_@@PEAPEAX@ZEA; ulong (*pFuncFwpmFilterCreateEnumHandle)(void *,FWPM_FILTER_ENUM_TEMPLATE0_ *,void * *)
0x1800bcd8a  movsd   qword ptr [rbp+70h+var_CC], xmm0
0x1800bcd8f  mov     [rbp+70h+var_D0], 71BC78FAh
0x1800bcd96  mov     dword ptr [rbp+70h+var_CC+8], eax
0x1800bcd99  mov     dword ptr [rbp+70h+var_CC+0Ch], r15d
0x1800bcd9d  mov     dword ptr [rbp+70h+var_BC+4], 0Dh
0x1800bcda4  mov     qword ptr [rbp+70h+var_BC+0Ch], rdi
0x1800bcda8  cmp     r12d, 10h
0x1800bcdac  jnb     loc_1800BCFF4
0x1800bcdb2  lea     rax, [rbp+70h+var_D0]
0x1800bcdb6  mov     [rbp+70h+var_78], 1
0x1800bcdbd  mov     [rbp+70h+var_70], rax
0x1800bcdc1  lea     rcx, qword_180131BA0
0x1800bcdc8  mov     eax, r12d
0x1800bcdcb  lea     r8, [rsp+170h+enumHandle]
0x1800bcdd0  add     rax, rax
0x1800bcdd3  mov     [rbp+70h+var_68], 0FFFFFFFFh
0x1800bcdda  lea     rdx, [rbp+70h+var_A0]
0x1800bcdde  mov     [rbp+70h+var_80], r15
0x1800bcde2  mov     [rbp+70h+var_88], r15d
0x1800bcde6  mov     [rbp+70h+var_A0], r15
0x1800bcdea  movups  xmm0, xmmword ptr [rcx+rax*8]
0x1800bcdee  mov     rcx, [rsp+170h+var_140]
0x1800bcdf3  mov     rax, r13
0x1800bcdf6  mov     [rbp+70h+var_84], 2
0x1800bcdfd  movdqu  [rbp+70h+var_98], xmm0
0x1800bce02  mov     [rbp+70h+var_60], r15
0x1800bce06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bce0b  mov     ebx, eax
0x1800bce0d  test    eax, eax
0x1800bce0f  jnz     loc_1800BCFD4
0x1800bce15  mov     rdx, [rsp+170h+enumHandle]; enumHandle
0x1800bce1a  lea     rax, [rbp+70h+numEntriesReturned]
0x1800bce1e  mov     rcx, [rsp+170h+var_140]; engineHandle
0x1800bce23  lea     r9, [rsp+170h+entries]; entries
0x1800bce28  or      r8d, 0FFFFFFFFh; numEntriesRequested
0x1800bce2c  mov     [rsp+170h+engineHandle], rax; numEntriesReturned
0x1800bce31  call    cs:__imp_FwpmFilterEnum0
0x1800bce38  nop     dword ptr [rax+rax+00h]
0x1800bce3d  mov     ebx, eax
0x1800bce3f  test    eax, eax
0x1800bce41  jnz     loc_1800BCFB4
0x1800bce47  mov     rdx, qword ptr cs:FWPM_CONDITION_ALE_PACKAGE_ID+8
0x1800bce4e  mov     r14d, r15d
0x1800bce51  mov     r9, qword ptr cs:FWPM_CONDITION_ALE_PACKAGE_ID
0x1800bce58  cmp     r14d, [rbp+70h+numEntriesReturned]
0x1800bce5c  jnb     loc_1800BCF21
0x1800bce62  mov     rax, [rsp+170h+entries]
0x1800bce67  mov     ecx, r14d
0x1800bce6a  mov     rsi, [rax+rcx*8]
0x1800bce6e  test    dword ptr [rsi+20h], 4000h
0x1800bce75  jnz     loc_1800BCF19
0x1800bce7b  cmp     r15d, [rsi+70h]
0x1800bce7f  jnb     loc_1800BCF16
0x1800bce85  mov     r8, [rsi+78h]
0x1800bce89  mov     eax, r15d
0x1800bce8c  lea     rcx, [rax+rax*4]
0x1800bce90  mov     rax, [r8+rcx*8]
0x1800bce94  sub     rax, r9
0x1800bce97  jnz     short loc_1800BCEA1
0x1800bce99  mov     rax, [r8+rcx*8+8]
0x1800bce9e  sub     rax, rdx
0x1800bcea1  test    rax, rax
0x1800bcea4  jnz     short loc_1800BCF0E
0x1800bcea6  mov     rcx, [r8+rcx*8+20h]; pSid1
0x1800bceab  mov     rdx, rdi; pSid2
0x1800bceae  call    cs:__imp_EqualSid
0x1800bceb5  nop     dword ptr [rax+rax+00h]
0x1800bceba  test    eax, eax
0x1800bcebc  jz      short loc_1800BCF00
0x1800bcebe  mov     rcx, [rsp+170h+var_140]; engineHandle
0x1800bcec3  mov     rdx, rsi; key
0x1800bcec6  call    cs:__imp_FwpmFilterDeleteByKey0
0x1800bcecd  nop     dword ptr [rax+rax+00h]
0x1800bced2  mov     ebx, eax
0x1800bced4  test    eax, eax
0x1800bced6  jnz     loc_1800BCF94
0x1800bcedc  mov     rcx, [rsp+170h+var_140]; engineHandle
0x1800bcee1  lea     r9, [rsi+0B0h]; id
0x1800bcee8  xor     r8d, r8d; sd
0x1800bceeb  mov     rdx, rsi; filter
0x1800bceee  call    cs:__imp_FwpmFilterAdd0
0x1800bcef5  nop     dword ptr [rax+rax+00h]
0x1800bcefa  mov     ebx, eax
0x1800bcefc  test    eax, eax
0x1800bcefe  jnz     short loc_1800BCF66
0x1800bcf00  mov     rdx, qword ptr cs:FWPM_CONDITION_ALE_PACKAGE_ID+8
0x1800bcf07  mov     r9, qword ptr cs:FWPM_CONDITION_ALE_PACKAGE_ID
0x1800bcf0e  inc     r15d
0x1800bcf11  jmp     loc_1800BCE7B
0x1800bcf16  xor     r15d, r15d
0x1800bcf19  inc     r14d
0x1800bcf1c  jmp     loc_1800BCE58
0x1800bcf21  cmp     [rsp+170h+entries], r15
0x1800bcf26  jz      short loc_1800BCF3E
0x1800bcf28  lea     rcx, [rsp+170h+entries]; p
0x1800bcf2d  call    cs:__imp_FwpmFreeMemory0
0x1800bcf34  nop     dword ptr [rax+rax+00h]
0x1800bcf39  mov     [rsp+170h+entries], r15
0x1800bcf3e  mov     rdx, [rsp+170h+enumHandle]; enumHandle
0x1800bcf43  test    rdx, rdx
0x1800bcf46  jz      short loc_1800BCF5E
0x1800bcf48  mov     rcx, [rsp+170h+var_140]; engineHandle
0x1800bcf4d  call    cs:__imp_FwpmFilterDestroyEnumHandle0
0x1800bcf54  nop     dword ptr [rax+rax+00h]
0x1800bcf59  mov     [rsp+170h+enumHandle], r15
0x1800bcf5e  inc     r12d
0x1800bcf61  jmp     loc_1800BCDA8
0x1800bcf66  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bcf6d  lea     rsi, WPP_GLOBAL_Control
0x1800bcf74  cmp     rcx, rsi
0x1800bcf77  jz      loc_1800BD002
0x1800bcf7d  test    byte ptr [rcx+1Ch], 1
0x1800bcf81  jz      short loc_1800BD002
0x1800bcf83  mov     edx, 36h ; '6'
0x1800bcf88  lea     r8, WPP_63b07f154e59352ff1fc5e97167f3127_Traceguids
0x1800bcf8f  jmp     loc_1800BCD21
0x1800bcf94  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bcf9b  lea     rsi, WPP_GLOBAL_Control
0x1800bcfa2  cmp     rcx, rsi
0x1800bcfa5  jz      short loc_1800BD002
0x1800bcfa7  test    byte ptr [rcx+1Ch], 1
0x1800bcfab  jz      short loc_1800BD002
0x1800bcfad  mov     edx, 35h ; '5'
0x1800bcfb2  jmp     short loc_1800BCF88
0x1800bcfb4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bcfbb  lea     rsi, WPP_GLOBAL_Control
0x1800bcfc2  cmp     rcx, rsi
0x1800bcfc5  jz      short loc_1800BD002
0x1800bcfc7  test    byte ptr [rcx+1Ch], 1
0x1800bcfcb  jz      short loc_1800BD002
0x1800bcfcd  mov     edx, 34h ; '4'
0x1800bcfd2  jmp     short loc_1800BCF88
0x1800bcfd4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bcfdb  lea     rsi, WPP_GLOBAL_Control
0x1800bcfe2  cmp     rcx, rsi
0x1800bcfe5  jz      short loc_1800BD002
0x1800bcfe7  test    byte ptr [rcx+1Ch], 1
  ... truncated ...
```
