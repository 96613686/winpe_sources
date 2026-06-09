# FwMoneisUpdatePackageIdConditions(_SID *)

- ea: `0x1800b5e34`
- end: `0x1800b63b8`
- name: `?FwMoneisUpdatePackageIdConditions@@YAKPEAU_SID@@@Z`
- size: `1412`
- prototype: `unsigned int __fastcall(PSID pSid2)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18002f7d4`

## callees

- `0x18000af3c`
- `0x180017110`
- `0x18006f520`
- `0x18006ffc8`
- `0x1800873a0`
- `0x1800b5000`
- `0x1800b5e34`
- `0x1800e6010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800b61f0`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800b61f0`
- `fwpuclnt!FwpmEngineOpen0` at `0x1800b6045`
- `fwpuclnt!FwpmEngineOpen0` at `0x1800b6091`
- `fwpuclnt!FwpmEngineOpen0` at `0x1800b6045`
- `fwpuclnt!FwpmEngineOpen0` at `0x1800b6091`
- `fwpuclnt!FwpmEngineClose0` at `0x1800b6369`
- `fwpuclnt!FwpmEngineClose0` at `0x1800b6369`
- `fwpuclnt!FwpmFreeMemory0` at `0x1800b625d`
- `fwpuclnt!FwpmFreeMemory0` at `0x1800b6333`
- `fwpuclnt!FwpmFreeMemory0` at `0x1800b625d`
- `fwpuclnt!FwpmFreeMemory0` at `0x1800b6333`
- `fwpuclnt!FwpmFilterDestroyEnumHandle0` at `0x1800b6277`
- `fwpuclnt!FwpmFilterDestroyEnumHandle0` at `0x1800b634f`
- `fwpuclnt!FwpmFilterDestroyEnumHandle0` at `0x1800b6277`
- `fwpuclnt!FwpmFilterDestroyEnumHandle0` at `0x1800b634f`
- `fwpuclnt!FwpmFilterEnum0` at `0x1800b617d`
- `fwpuclnt!FwpmFilterEnum0` at `0x1800b617d`
- `fwpuclnt!FwpmFilterDeleteByKey0` at `0x1800b6202`
- `fwpuclnt!FwpmFilterDeleteByKey0` at `0x1800b6202`
- `fwpuclnt!FwpmFilterAdd0` at `0x1800b6224`
- `fwpuclnt!FwpmFilterAdd0` at `0x1800b6224`

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
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 38, WPP_f2b9ef332e653b3ba80d2c59b36f5ad8_Traceguids);
  v5 = lambda_3ef812906e7d198e2ba7d0b595975e34_::operator()(v4, 2, pSid2);
  if ( v5 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_71;
    v8 = 39;
LABEL_8:
    WPP_SF_d(*(_QWORD *)(v7 + 16), v8, WPP_f2b9ef332e653b3ba80d2c59b36f5ad8_Traceguids, (unsigned int)v5);
LABEL_70:
    v7 = WPP_GLOBAL_Control;
    goto LABEL_71;
  }
  v5 = lambda_3ef812906e7d198e2ba7d0b595975e34_::operator()(v6, 8, pSid2);
  if ( v5 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_71;
    v8 = 40;
    goto LABEL_8;
  }
  v5 = lambda_3ef812906e7d198e2ba7d0b595975e34_::operator()(v9, 10, pSid2);
  if ( v5 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_71;
    v8 = 41;
    goto LABEL_8;
  }
  v5 = lambda_3ef812906e7d198e2ba7d0b595975e34_::operator()(v10, 11, pSid2);
  if ( v5 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_71;
    v8 = 42;
    goto LABEL_8;
  }
  v5 = lambda_3ef812906e7d198e2ba7d0b595975e34_::operator()(v11, 6, pSid2);
  if ( v5 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_71;
    v8 = 43;
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
      v13 = 44;
LABEL_30:
      WPP_SF_d(*(_QWORD *)(v7 + 16), v13, WPP_f2b9ef332e653b3ba80d2c59b36f5ad8_Traceguids, v12);
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
      v13 = 45;
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
  v16 = *(_OWORD *)&qword_18012B9B0[2 * v14];
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
    v13 = 46;
    goto LABEL_30;
  }
  v12 = FwpmFilterEnum0(engineHandle, enumHandle[0], 0xFFFFFFFF, &entries, &numEntriesReturned);
  v3 = v12;
  if ( v12 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_71;
    v13 = 47;
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
        v13 = 49;
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
    v13 = 48;
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
    WPP_SF_(*(_QWORD *)(v7 + 16), 50, WPP_f2b9ef332e653b3ba80d2c59b36f5ad8_Traceguids);
  return v3;
}

```

## disassembly

```asm
0x1800b5e34  push    rbp
0x1800b5e36  push    rbx
0x1800b5e37  push    rsi
0x1800b5e38  push    rdi
0x1800b5e39  push    r12
0x1800b5e3b  push    r13
0x1800b5e3d  push    r14
0x1800b5e3f  push    r15
0x1800b5e41  lea     rbp, [rsp-38h]
0x1800b5e46  sub     rsp, 138h
0x1800b5e4d  mov     rax, cs:__security_cookie
0x1800b5e54  xor     rax, rsp
0x1800b5e57  mov     [rbp+70h+var_48], rax
0x1800b5e5b  xor     r15d, r15d
0x1800b5e5e  mov     rdi, rcx
0x1800b5e61  xor     edx, edx; Val
0x1800b5e63  mov     [rsp+170h+var_140], r15
0x1800b5e68  lea     rcx, [rbp+70h+var_A0]; void *
0x1800b5e6c  mov     [rsp+170h+enumHandle], r15
0x1800b5e71  mov     ebx, r15d
0x1800b5e74  lea     r8d, [r15+48h]; Size
0x1800b5e78  call    memset_0
0x1800b5e7d  xorps   xmm0, xmm0
0x1800b5e80  mov     [rbp+70h+var_D0], r15d
0x1800b5e84  xor     eax, eax
0x1800b5e86  mov     [rsp+170h+entries], r15
0x1800b5e8b  movups  [rbp+70h+var_CC], xmm0
0x1800b5e8f  mov     [rbp+70h+var_AC], eax
0x1800b5e92  movups  [rbp+70h+var_BC], xmm0
0x1800b5e96  mov     [rbp+70h+numEntriesReturned], r15d
0x1800b5e9a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b5ea1  lea     rsi, WPP_GLOBAL_Control
0x1800b5ea8  lea     r14, WPP_f2b9ef332e653b3ba80d2c59b36f5ad8_Traceguids
0x1800b5eaf  cmp     rcx, rsi
0x1800b5eb2  jz      short loc_1800B5EC9
0x1800b5eb4  test    byte ptr [rcx+1Ch], 8
0x1800b5eb8  jz      short loc_1800B5EC9
0x1800b5eba  mov     rcx, [rcx+10h]
0x1800b5ebe  lea     edx, [rax+26h]
0x1800b5ec1  mov     r8, r14
0x1800b5ec4  call    WPP_SF_
0x1800b5ec9  mov     r8, rdi
0x1800b5ecc  mov     edx, 2
0x1800b5ed1  call    _lambda_3ef812906e7d198e2ba7d0b595975e34___operator__
0x1800b5ed6  test    eax, eax
0x1800b5ed8  jns     short loc_1800B5F0D
0x1800b5eda  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b5ee1  cmp     rcx, rsi
0x1800b5ee4  jz      loc_1800B6326
0x1800b5eea  test    byte ptr [rcx+1Ch], 1
0x1800b5eee  jz      loc_1800B6326
0x1800b5ef4  mov     edx, 27h ; '''
0x1800b5ef9  mov     rcx, [rcx+10h]
0x1800b5efd  mov     r9d, eax
0x1800b5f00  mov     r8, r14
0x1800b5f03  call    WPP_SF_d
0x1800b5f08  jmp     loc_1800B631F
0x1800b5f0d  mov     r8, rdi
0x1800b5f10  mov     edx, 8
0x1800b5f15  call    _lambda_3ef812906e7d198e2ba7d0b595975e34___operator__
0x1800b5f1a  test    eax, eax
0x1800b5f1c  jns     short loc_1800B5F3F
0x1800b5f1e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b5f25  cmp     rcx, rsi
0x1800b5f28  jz      loc_1800B6326
0x1800b5f2e  test    byte ptr [rcx+1Ch], 1
0x1800b5f32  jz      loc_1800B6326
0x1800b5f38  mov     edx, 28h ; '('
0x1800b5f3d  jmp     short loc_1800B5EF9
0x1800b5f3f  mov     r12d, 0Ah
0x1800b5f45  mov     r8, rdi
0x1800b5f48  mov     edx, r12d
0x1800b5f4b  call    _lambda_3ef812906e7d198e2ba7d0b595975e34___operator__
0x1800b5f50  test    eax, eax
0x1800b5f52  jns     short loc_1800B5F75
0x1800b5f54  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b5f5b  cmp     rcx, rsi
0x1800b5f5e  jz      loc_1800B6326
0x1800b5f64  test    byte ptr [rcx+1Ch], 1
0x1800b5f68  jz      loc_1800B6326
0x1800b5f6e  lea     edx, [r12+1Fh]
0x1800b5f73  jmp     short loc_1800B5EF9
0x1800b5f75  mov     r8, rdi
0x1800b5f78  mov     edx, 0Bh
0x1800b5f7d  call    _lambda_3ef812906e7d198e2ba7d0b595975e34___operator__
0x1800b5f82  test    eax, eax
0x1800b5f84  jns     short loc_1800B5FAA
0x1800b5f86  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b5f8d  cmp     rcx, rsi
0x1800b5f90  jz      loc_1800B6326
0x1800b5f96  test    byte ptr [rcx+1Ch], 1
0x1800b5f9a  jz      loc_1800B6326
0x1800b5fa0  mov     edx, 2Ah ; '*'
0x1800b5fa5  jmp     loc_1800B5EF9
0x1800b5faa  mov     r8, rdi
0x1800b5fad  mov     edx, 6
0x1800b5fb2  call    _lambda_3ef812906e7d198e2ba7d0b595975e34___operator__
0x1800b5fb7  test    eax, eax
0x1800b5fb9  jns     short loc_1800B5FDF
0x1800b5fbb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b5fc2  cmp     rcx, rsi
0x1800b5fc5  jz      loc_1800B6326
0x1800b5fcb  test    byte ptr [rcx+1Ch], 1
0x1800b5fcf  jz      loc_1800B6326
0x1800b5fd5  mov     edx, 2Bh ; '+'
0x1800b5fda  jmp     loc_1800B5EF9
0x1800b5fdf  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BugFix_FwBfeSessions@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_FwBfeSessions@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_FwBfeSessions> `wil::Feature<__WilFeatureTraits_Feature_BugFix_FwBfeSessions>::GetImpl(void)'::`2'::impl
0x1800b5fe6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_FwBfeSessions@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_FwBfeSessions>::__private_IsEnabled(void)
0x1800b5feb  xor     r8d, r8d; authIdentity
0x1800b5fee  xor     ecx, ecx; serverName
0x1800b5ff0  mov     edx, r12d; authnService
0x1800b5ff3  test    al, al
0x1800b5ff5  jz      loc_1800B6084
0x1800b5ffb  lea     rax, aFirewallAppIso; "Firewall App Isolation Enumeration"
0x1800b6002  mov     qword ptr [rsp+170h+session.sessionKey.Data1], r15
0x1800b6007  mov     [rsp+170h+session.displayData.name], rax
0x1800b600c  lea     r9, [rsp+170h+session]; session
0x1800b6011  xor     eax, eax
0x1800b6013  mov     qword ptr [rsp+170h+session.sessionKey.Data4], r15
0x1800b6018  mov     dword ptr [rsp+170h+session+2Ch], eax
0x1800b601c  xorps   xmm0, xmm0
0x1800b601f  lea     rax, [rsp+170h+var_140]
0x1800b6024  mov     [rsp+170h+session.displayData.description], r15
0x1800b6029  mov     [rsp+170h+engineHandle], rax; engineHandle
0x1800b602e  mov     [rsp+170h+session.flags], r15d
0x1800b6033  mov     qword ptr [rsp+170h+session.txnWaitTimeoutInMSec], 112A880h
0x1800b603c  movdqa  xmmword ptr [rbp+70h+session.sid], xmm0
0x1800b6041  mov     qword ptr [rbp+70h+session.kernelMode], r15
0x1800b6045  call    cs:__imp_FwpmEngineOpen0
0x1800b604b  mov     ebx, eax
0x1800b604d  test    eax, eax
0x1800b604f  jz      short loc_1800B60BE
0x1800b6051  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b6058  cmp     rcx, rsi
0x1800b605b  jz      loc_1800B6326
0x1800b6061  test    byte ptr [rcx+1Ch], 1
0x1800b6065  jz      loc_1800B6326
0x1800b606b  mov     edx, 2Ch ; ','
0x1800b6070  mov     r8, r14
0x1800b6073  mov     rcx, [rcx+10h]
0x1800b6077  mov     r9d, eax
0x1800b607a  call    WPP_SF_d
0x1800b607f  jmp     loc_1800B631F
0x1800b6084  lea     rax, [rsp+170h+var_140]
0x1800b6089  xor     r9d, r9d; session
0x1800b608c  mov     [rsp+170h+engineHandle], rax; engineHandle
0x1800b6091  call    cs:__imp_FwpmEngineOpen0
0x1800b6097  mov     ebx, eax
0x1800b6099  test    eax, eax
0x1800b609b  jz      short loc_1800B60BE
0x1800b609d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b60a4  cmp     rcx, rsi
0x1800b60a7  jz      loc_1800B6326
0x1800b60ad  test    byte ptr [rcx+1Ch], 1
0x1800b60b1  jz      loc_1800B6326
0x1800b60b7  mov     edx, 2Dh ; '-'
0x1800b60bc  jmp     short loc_1800B6070
0x1800b60be  movsd   xmm0, qword ptr cs:FWPM_CONDITION_ALE_PACKAGE_ID+4
0x1800b60c6  mov     r12d, r15d
0x1800b60c9  mov     eax, dword ptr cs:FWPM_CONDITION_ALE_PACKAGE_ID+0Ch
0x1800b60cf  mov     r13, cs:?pFuncFwpmFilterCreateEnumHandle@@3P6AKPEAXPEAUFWPM_FILTER_ENUM_TEMPLATE0_@@PEAPEAX@ZEA; ulong (*pFuncFwpmFilterCreateEnumHandle)(void *,FWPM_FILTER_ENUM_TEMPLATE0_ *,void * *)
0x1800b60d6  movsd   qword ptr [rbp+70h+var_CC], xmm0
0x1800b60db  mov     [rbp+70h+var_D0], 71BC78FAh
0x1800b60e2  mov     dword ptr [rbp+70h+var_CC+8], eax
0x1800b60e5  mov     dword ptr [rbp+70h+var_CC+0Ch], r15d
0x1800b60e9  mov     dword ptr [rbp+70h+var_BC+4], 0Dh
0x1800b60f0  mov     qword ptr [rbp+70h+var_BC+0Ch], rdi
0x1800b60f4  cmp     r12d, 10h
0x1800b60f8  jnb     loc_1800B6318
0x1800b60fe  lea     rax, [rbp+70h+var_D0]
0x1800b6102  mov     [rbp+70h+var_78], 1
0x1800b6109  mov     [rbp+70h+var_70], rax
0x1800b610d  lea     rcx, qword_18012B9B0
0x1800b6114  mov     eax, r12d
0x1800b6117  lea     r8, [rsp+170h+enumHandle]
0x1800b611c  add     rax, rax
0x1800b611f  mov     [rbp+70h+var_68], 0FFFFFFFFh
0x1800b6126  lea     rdx, [rbp+70h+var_A0]
0x1800b612a  mov     [rbp+70h+var_80], r15
0x1800b612e  mov     [rbp+70h+var_88], r15d
0x1800b6132  mov     [rbp+70h+var_A0], r15
0x1800b6136  movups  xmm0, xmmword ptr [rcx+rax*8]
0x1800b613a  mov     rcx, [rsp+170h+var_140]
0x1800b613f  mov     rax, r13
0x1800b6142  mov     [rbp+70h+var_84], 2
0x1800b6149  movdqu  [rbp+70h+var_98], xmm0
0x1800b614e  mov     [rbp+70h+var_60], r15
0x1800b6152  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6157  mov     ebx, eax
0x1800b6159  test    eax, eax
0x1800b615b  jnz     loc_1800B62F8
0x1800b6161  mov     rdx, [rsp+170h+enumHandle]; enumHandle
0x1800b6166  lea     rax, [rbp+70h+numEntriesReturned]
0x1800b616a  mov     rcx, [rsp+170h+var_140]; engineHandle
0x1800b616f  lea     r9, [rsp+170h+entries]; entries
0x1800b6174  or      r8d, 0FFFFFFFFh; numEntriesRequested
0x1800b6178  mov     [rsp+170h+engineHandle], rax; numEntriesReturned
0x1800b617d  call    cs:__imp_FwpmFilterEnum0
0x1800b6183  mov     ebx, eax
0x1800b6185  test    eax, eax
0x1800b6187  jnz     loc_1800B62D8
0x1800b618d  mov     rdx, qword ptr cs:FWPM_CONDITION_ALE_PACKAGE_ID+8
0x1800b6194  mov     r14d, r15d
0x1800b6197  mov     r9, qword ptr cs:FWPM_CONDITION_ALE_PACKAGE_ID
0x1800b619e  cmp     r14d, [rbp+70h+numEntriesReturned]
0x1800b61a2  jnb     loc_1800B6251
0x1800b61a8  mov     rax, [rsp+170h+entries]
0x1800b61ad  mov     ecx, r14d
0x1800b61b0  mov     rsi, [rax+rcx*8]
0x1800b61b4  test    dword ptr [rsi+20h], 4000h
0x1800b61bb  jnz     loc_1800B6249
0x1800b61c1  cmp     r15d, [rsi+70h]
0x1800b61c5  jnb     short loc_1800B6246
0x1800b61c7  mov     r8, [rsi+78h]
0x1800b61cb  mov     eax, r15d
0x1800b61ce  lea     rcx, [rax+rax*4]
0x1800b61d2  mov     rax, [r8+rcx*8]
0x1800b61d6  sub     rax, r9
0x1800b61d9  jnz     short loc_1800B61E3
0x1800b61db  mov     rax, [r8+rcx*8+8]
0x1800b61e0  sub     rax, rdx
0x1800b61e3  test    rax, rax
0x1800b61e6  jnz     short loc_1800B623E
0x1800b61e8  mov     rcx, [r8+rcx*8+20h]; pSid1
0x1800b61ed  mov     rdx, rdi; pSid2
0x1800b61f0  call    cs:__imp_EqualSid
0x1800b61f6  test    eax, eax
0x1800b61f8  jz      short loc_1800B6230
0x1800b61fa  mov     rcx, [rsp+170h+var_140]; engineHandle
0x1800b61ff  mov     rdx, rsi; key
0x1800b6202  call    cs:__imp_FwpmFilterDeleteByKey0
0x1800b6208  mov     ebx, eax
0x1800b620a  test    eax, eax
0x1800b620c  jnz     loc_1800B62B8
0x1800b6212  mov     rcx, [rsp+170h+var_140]; engineHandle
0x1800b6217  lea     r9, [rsi+0B0h]; id
0x1800b621e  xor     r8d, r8d; sd
0x1800b6221  mov     rdx, rsi; filter
0x1800b6224  call    cs:__imp_FwpmFilterAdd0
0x1800b622a  mov     ebx, eax
0x1800b622c  test    eax, eax
0x1800b622e  jnz     short loc_1800B628A
0x1800b6230  mov     rdx, qword ptr cs:FWPM_CONDITION_ALE_PACKAGE_ID+8
0x1800b6237  mov     r9, qword ptr cs:FWPM_CONDITION_ALE_PACKAGE_ID
0x1800b623e  inc     r15d
0x1800b6241  jmp     loc_1800B61C1
0x1800b6246  xor     r15d, r15d
0x1800b6249  inc     r14d
0x1800b624c  jmp     loc_1800B619E
0x1800b6251  cmp     [rsp+170h+entries], r15
0x1800b6256  jz      short loc_1800B6268
0x1800b6258  lea     rcx, [rsp+170h+entries]; p
0x1800b625d  call    cs:__imp_FwpmFreeMemory0
0x1800b6263  mov     [rsp+170h+entries], r15
0x1800b6268  mov     rdx, [rsp+170h+enumHandle]; enumHandle
0x1800b626d  test    rdx, rdx
0x1800b6270  jz      short loc_1800B6282
0x1800b6272  mov     rcx, [rsp+170h+var_140]; engineHandle
0x1800b6277  call    cs:__imp_FwpmFilterDestroyEnumHandle0
0x1800b627d  mov     [rsp+170h+enumHandle], r15
0x1800b6282  inc     r12d
0x1800b6285  jmp     loc_1800B60F4
0x1800b628a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b6291  lea     rsi, WPP_GLOBAL_Control
0x1800b6298  cmp     rcx, rsi
0x1800b629b  jz      loc_1800B6326
0x1800b62a1  test    byte ptr [rcx+1Ch], 1
0x1800b62a5  jz      short loc_1800B6326
0x1800b62a7  mov     edx, 31h ; '1'
0x1800b62ac  lea     r8, WPP_f2b9ef332e653b3ba80d2c59b36f5ad8_Traceguids
0x1800b62b3  jmp     loc_1800B6073
0x1800b62b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b62bf  lea     rsi, WPP_GLOBAL_Control
0x1800b62c6  cmp     rcx, rsi
0x1800b62c9  jz      short loc_1800B6326
0x1800b62cb  test    byte ptr [rcx+1Ch], 1
0x1800b62cf  jz      short loc_1800B6326
0x1800b62d1  mov     edx, 30h ; '0'
0x1800b62d6  jmp     short loc_1800B62AC
0x1800b62d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b62df  lea     rsi, WPP_GLOBAL_Control
0x1800b62e6  cmp     rcx, rsi
0x1800b62e9  jz      short loc_1800B6326
0x1800b62eb  test    byte ptr [rcx+1Ch], 1
0x1800b62ef  jz      short loc_1800B6326
0x1800b62f1  mov     edx, 2Fh ; '/'
0x1800b62f6  jmp     short loc_1800B62AC
0x1800b62f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b62ff  lea     rsi, WPP_GLOBAL_Control
0x1800b6306  cmp     rcx, rsi
0x1800b6309  jz      short loc_1800B6326
0x1800b630b  test    byte ptr [rcx+1Ch], 1
0x1800b630f  jz      short loc_1800B6326
0x1800b6311  mov     edx, 2Eh ; '.'
0x1800b6316  jmp     short loc_1800B62AC
0x1800b6318  lea     rsi, WPP_GLOBAL_Control
0x1800b631f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b6326  cmp     [rsp+170h+entries], 0
0x1800b632c  jz      short loc_1800B6340
0x1800b632e  lea     rcx, [rsp+170h+entries]; p
  ... truncated ...
```
