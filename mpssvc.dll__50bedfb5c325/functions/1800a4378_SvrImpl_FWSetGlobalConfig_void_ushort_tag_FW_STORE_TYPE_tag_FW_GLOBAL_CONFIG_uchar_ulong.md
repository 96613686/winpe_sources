# SvrImpl_FWSetGlobalConfig(void *,ushort,_tag_FW_STORE_TYPE,_tag_FW_GLOBAL_CONFIG,uchar *,ulong)

- ea: `0x1800a4378`
- end: `0x1800a4e3c`
- name: `?SvrImpl_FWSetGlobalConfig@@YAKPEAXGW4_tag_FW_STORE_TYPE@@W4_tag_FW_GLOBAL_CONFIG@@PEAEK@Z`
- size: `2756`
- prototype: `unsigned int __high(void *, unsigned __int16, enum _tag_FW_STORE_TYPE, enum _tag_FW_GLOBAL_CONFIG, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800cbed0`

## callees

- `0x180005c4c`
- `0x180007b58`
- `0x180008a80`
- `0x180008d60`
- `0x1800097b0`
- `0x18000a710`
- `0x1800192e0`
- `0x180059714`
- `0x18006ad98`
- `0x1800729c0`
- `0x18007d5dc`
- `0x18008ce78`
- `0x1800a4378`
- `0x1800a6d90`
- `0x1800a700c`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800a4b10`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800a4b10`
- `fwbase!FwHResultToWindowsError` at `0x1800a44a7`
- `fwbase!FwHResultToWindowsError` at `0x1800a4db0`
- `fwbase!FwHResultToWindowsError` at `0x1800a4e11`
- `fwbase!FwHResultToWindowsError` at `0x1800a44a7`
- `fwbase!FwHResultToWindowsError` at `0x1800a4db0`
- `fwbase!FwHResultToWindowsError` at `0x1800a4e11`
- `fwbase!FwGetRpcCallersProcessImageName` at `0x1800a4cf9`
- `fwbase!FwGetRpcCallersProcessImageName` at `0x1800a4cf9`
- `fwbase!FwChangeSourceSignal` at `0x1800a4499`
- `fwbase!FwChangeSourceSignal` at `0x1800a4499`
- `fwbase!FwReportReturnError` at `0x1800a4ce3`
- `fwbase!FwReportReturnError` at `0x1800a4ce3`
- `fwbase!FwAlloc` at `0x1800a4c82`
- `fwbase!FwAlloc` at `0x1800a4c82`
- `fwbase!FwFree` at `0x1800a4de1`
- `fwbase!FwFree` at `0x1800a4df2`
- `fwbase!FwFree` at `0x1800a4e03`
- `fwbase!FwFree` at `0x1800a4de1`
- `fwbase!FwFree` at `0x1800a4df2`
- `fwbase!FwFree` at `0x1800a4e03`
- `FWPolicyIOMgr!FwSetGlobalConfig` at `0x1800a4bfb`
- `FWPolicyIOMgr!FwSetGlobalConfig` at `0x1800a4bfb`
- `FWPolicyIOMgr!FwSddlStringVerify` at `0x1800a4b28`
- `FWPolicyIOMgr!FwSddlStringVerify` at `0x1800a4b28`

## string_xrefs

- `0x1800a4cdc`: `FwAuditLogGlobalConfigChange`
- `0x1800a43f1`: `SvrImpl_FWSetGlobalConfig`
- `0x1800a4410`: `SvrImpl_FWSetGlobalConfig`
- `0x1800a447d`: `SvrImpl_FWSetGlobalConfig`
- `0x1800a4489`: `SvrImpl_FWSetGlobalConfig`

## pseudocode

```c
__int64 __fastcall SvrImpl_FWSetGlobalConfig(
        void *a1,
        unsigned __int16 a2,
        unsigned int a3,
        unsigned int a4,
        LPCWCH lpString1,
        unsigned int a6)
{
  const unsigned __int16 *v6; // r13
  __int64 result; // rax
  int v11; // ebx
  int RPCClientSID; // eax
  signed int v13; // ebx
  __int64 v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // r9
  const unsigned __int16 *v17; // rdi
  const unsigned __int16 *v18; // rdx
  const unsigned __int16 *v19; // r10
  const wchar_t *v20; // rcx
  __int64 v21; // rax
  bool v22; // sf
  int v23; // eax
  __int64 v24; // rcx
  __int64 v25; // rax
  int v26; // eax
  int v27; // eax
  int v28; // r8d
  const unsigned __int16 *v30; // [rsp+48h] [rbp-60h] BYREF
  void **v31; // [rsp+50h] [rbp-58h] BYREF

  v6 = 0;
  v31 = 0;
  v30 = 0;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 193, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids);
  result = FwAcquireRPCSharedLock("SvrImpl_FWSetGlobalConfig");
  if ( (int)result >= 0 )
  {
    v11 = FwLock();
    if ( v11 < 0 )
    {
      FwReleaseRPCSharedLock("SvrImpl_FWSetGlobalConfig");
      return (unsigned int)v11;
    }
    RPCClientSID = ExtractRPCClientSID(a1, (__int64)&v31);
    v13 = RPCClientSID;
    if ( RPCClientSID < 0 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_12;
      v15 = 194;
      v16 = (unsigned int)RPCClientSID;
      goto LABEL_11;
    }
    if ( a3 != 2 && a3 != 11 )
    {
      v16 = 2147942450LL;
      v13 = -2147024846;
      v14 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_12;
      v15 = 195;
      goto LABEL_11;
    }
    if ( !lpString1 )
    {
      if ( a6 )
      {
        v16 = 2147942487LL;
        v13 = -2147024809;
        v14 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_12;
        v15 = 196;
        goto LABEL_11;
      }
      goto LABEL_145;
    }
    if ( (int)a4 <= 9 )
    {
      if ( a4 == 9 )
      {
        if ( a6 != 4 )
        {
          v16 = 2147942487LL;
          v13 = -2147024809;
          v14 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
            goto LABEL_12;
          v15 = 207;
          goto LABEL_11;
        }
        if ( *(_DWORD *)lpString1 > 2u )
        {
          v16 = 2147942487LL;
          v13 = -2147024809;
          v14 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
            goto LABEL_12;
          v15 = 208;
          goto LABEL_11;
        }
        goto LABEL_145;
      }
      if ( a4 <= 2 )
        goto LABEL_138;
      if ( a4 != 3 && a4 != 4 )
      {
        switch ( a4 )
        {
          case 5u:
            if ( a6 != 4 )
            {
              v16 = 2147942487LL;
              v13 = -2147024809;
              v14 = WPP_GLOBAL_Control;
              if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
              {
                goto LABEL_12;
              }
              v15 = 198;
              goto LABEL_11;
            }
            if ( *(_DWORD *)lpString1 > 0xE10u )
            {
              v16 = 2147942487LL;
              v13 = -2147024809;
              v14 = WPP_GLOBAL_Control;
              if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
              {
                goto LABEL_12;
              }
              v15 = 199;
              goto LABEL_11;
            }
            if ( *(_DWORD *)lpString1 < 0x12Cu )
            {
              v16 = 2147942487LL;
              v13 = -2147024809;
              v14 = WPP_GLOBAL_Control;
              if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
              {
                goto LABEL_12;
              }
              v15 = 200;
              goto LABEL_11;
            }
            goto LABEL_145;
          case 6u:
            if ( a6 != 4 )
            {
              v16 = 2147942487LL;
              v13 = -2147024809;
              v14 = WPP_GLOBAL_Control;
              if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
              {
                goto LABEL_12;
              }
              v15 = 201;
              goto LABEL_11;
            }
            if ( *(_DWORD *)lpString1 > 1u )
            {
              v16 = 2147942487LL;
              v13 = -2147024809;
              v14 = WPP_GLOBAL_Control;
              if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
              {
                goto LABEL_12;
              }
              v15 = 202;
              goto LABEL_11;
            }
            goto LABEL_145;
          case 7u:
            if ( a6 != 4 )
            {
              v16 = 2147942487LL;
              v13 = -2147024809;
              v14 = WPP_GLOBAL_Control;
              if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
              {
                goto LABEL_12;
              }
              v15 = 203;
              goto LABEL_11;
            }
            if ( *(_DWORD *)lpString1 > 0xFu )
            {
              v16 = 2147942487LL;
              v13 = -2147024809;
              v14 = WPP_GLOBAL_Control;
              if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
              {
                goto LABEL_12;
              }
              v15 = 204;
              goto LABEL_11;
            }
            goto LABEL_145;
          case 8u:
            if ( a6 != 4 )
            {
              v16 = 2147942487LL;
              v13 = -2147024809;
              v14 = WPP_GLOBAL_Control;
              if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
              {
                goto LABEL_12;
              }
              v15 = 205;
              goto LABEL_11;
            }
            if ( *(_DWORD *)lpString1 > 2u )
            {
              v16 = 2147942487LL;
              v13 = -2147024809;
              v14 = WPP_GLOBAL_Control;
              if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
              {
                goto LABEL_12;
              }
              v15 = 206;
              goto LABEL_11;
            }
            goto LABEL_145;
        }
LABEL_138:
        v16 = 2147942487LL;
        v13 = -2147024809;
        v14 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_12;
        v15 = 219;
        goto LABEL_11;
      }
LABEL_141:
      if ( a6 != 4 )
      {
        v16 = 2147942487LL;
        v13 = -2147024809;
        v14 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_12;
        v15 = 197;
        goto LABEL_11;
      }
      goto LABEL_145;
    }
    if ( a4 == 10 )
      goto LABEL_141;
    if ( a4 == 11 )
      goto LABEL_138;
    if ( a4 != 12 && a4 != 13 )
    {
      if ( a4 == 14 )
        goto LABEL_141;
      if ( a4 != 15 && a4 != 16 )
      {
        if ( a4 == 17 )
        {
          if ( a6 != 4 )
          {
            v16 = 2147942487LL;
            v13 = -2147024809;
            v14 = WPP_GLOBAL_Control;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
            {
              goto LABEL_12;
            }
            v15 = 209;
            goto LABEL_11;
          }
          if ( (*(_DWORD *)lpString1 & 0xFFFFFFFC) != 0 )
          {
            v16 = 2147942487LL;
            v13 = -2147024809;
            v14 = WPP_GLOBAL_Control;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
            {
              goto LABEL_12;
            }
            v15 = 210;
            goto LABEL_11;
          }
          goto LABEL_145;
        }
        if ( a4 == 18 )
        {
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Netsec_AuditMode_Hardening>::__private_IsEnabled(
                                  `wil::Feature<__WilFeatureTraits_Feature_Netsec_AuditMode_Hardening>::GetImpl'::`2'::impl,
                                  4,
                                  0)
            && a3 != 11 )
          {
            v16 = 2147942450LL;
            v13 = -2147024846;
            v14 = WPP_GLOBAL_Control;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
            {
              goto LABEL_12;
            }
            v15 = 216;
            goto LABEL_11;
          }
          if ( a6 != 4 )
          {
            v16 = 2147942487LL;
            v13 = -2147024809;
            v14 = WPP_GLOBAL_Control;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
            {
              goto LABEL_12;
            }
            v15 = 217;
            goto LABEL_11;
          }
          if ( *(_DWORD *)lpString1 > 1u )
          {
            v16 = 2147942487LL;
            v13 = -2147024809;
            v14 = WPP_GLOBAL_Control;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
            {
              goto LABEL_12;
            }
            v15 = 218;
            goto LABEL_11;
          }
          goto LABEL_145;
        }
        goto LABEL_138;
      }
    }
    if ( (a6 & 1) != 0 )
    {
      v16 = 2147942487LL;
      v13 = -2147024809;
      v14 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_12;
      v15 = 211;
      goto LABEL_11;
    }
    if ( a6 < 2 )
    {
      v16 = 2147942487LL;
      v13 = -2147024809;
      v14 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_12;
      v15 = 212;
      goto LABEL_11;
    }
    if ( lpString1[((unsigned __int64)a6 >> 1) - 1] )
    {
      v16 = 2147942487LL;
      v13 = -2147024809;
      v14 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_12;
      v15 = 213;
      goto LABEL_11;
    }
    v21 = -1;
    do
      ++v21;
    while ( lpString1[v21] );
    if ( 2 * v21 + 2 != a6 )
    {
      v16 = 2147942487LL;
      v13 = -2147024809;
      v14 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_12;
      v15 = 214;
      goto LABEL_11;
    }
    if ( CompareStringOrdinal(lpString1, -1, L"None", -1, 1) != 2 )
    {
      v13 = FwSddlStringVerify(lpString1);
      v22 = v13 < 0;
      if ( v13 > 0 )
      {
        v13 = (unsigned __int16)v13 | 0x80070000;
        v22 = v13 < 0;
      }
      if ( v22 )
      {
        v14 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_12;
        v15 = 215;
        v16 = (unsigned int)v13;
        goto LABEL_11;
      }
    }
LABEL_145:
    v23 = FwSetGlobalConfig(a2, a3, 0, a4, lpString1, a6);
    v13 = v23;
    if ( v23 >= 0 )
    {
      v23 = FwIncrmSetGlobalConfig(v24, a3, a4, lpString1, a6);
      v13 = v23;
      if ( v23 >= 0 )
      {
        v25 = FwAlloc(2048);
        v6 = (const unsigned __int16 *)v25;
        if ( !v25 )
        {
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
            WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 223, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids);
          goto LABEL_12;
        }
        v23 = FwConfig2Str(a4, lpString1, 1, v25);
        if ( v23 >= 0 )
        {
          if ( dword_18013426C )
          {
            v26 = FwAuditLogSettingChangeImpl(*v31, qword_1801340E8, a4, 1, v6);
            if ( v26 < 0 )
              FwReportReturnError("FwAuditLogGlobalConfigChange", (unsigned int)v26);
          }
          FwGetRpcCallersProcessImageName(a1, &v30);
          goto LABEL_12;
        }
        v14 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        {
LABEL_12:
          FwUnlockInternal(a1, "SvrImpl_FWSetGlobalConfig");
          FwReleaseRPCSharedLock("SvrImpl_FWSetGlobalConfig");
          if ( v13 >= 0 )
            FwChangeSourceSignal();
          FwHResultToWindowsError((unsigned int)v13);
          v17 = &qword_1800FBFF0;
          v18 = &qword_1800FBFF0;
          if ( v6 )
            v18 = v6;
          v19 = &qword_1800FBFF0;
          if ( v30 )
            v19 = v30;
          if ( v31 )
            v20 = (const wchar_t *)*v31;
          else
            v20 = L"S-1-0-0";
          FwEventGlobalConfigurationChanged(v20, v19, a4, lpString1 != 0 ? a6 : 0, lpString1, v18);
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
          {
            if ( v30 )
              v17 = v30;
            v27 = FwHResultToWindowsError((unsigned int)v13);
            WPP_SF_DSD(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 224, v28, v27, (__int64)v17, a4);
          }
          FwFree(v6);
          FwFree(v30);
          FwFree(v31);
          return FwHResultToWindowsError((unsigned int)v13);
        }
        v15 = 222;
      }
      else
      {
        v14 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_12;
        v15 = 221;
      }
    }
    else
    {
      v14 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_12;
      v15 = 220;
    }
    v16 = (unsigned int)v23;
LABEL_11:
    WPP_SF_d(*(_QWORD *)(v14 + 16), v15, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids, v16);
    goto LABEL_12;
  }
  return result;
}

```

## disassembly

```asm
0x1800a4378  push    rbx
0x1800a437a  push    rbp
0x1800a437b  push    rsi
0x1800a437c  push    rdi
0x1800a437d  push    r12
0x1800a437f  push    r13
0x1800a4381  push    r14
0x1800a4383  push    r15
0x1800a4385  sub     rsp, 68h
0x1800a4389  mov     rax, cs:__security_cookie
0x1800a4390  xor     rax, rsp
0x1800a4393  mov     [rsp+0A8h+var_50], rax
0x1800a4398  mov     r14d, [rsp+0A8h+arg_28]
0x1800a43a0  xor     r13d, r13d
0x1800a43a3  mov     r15, [rsp+0A8h+lpString1]
0x1800a43ab  mov     r12d, r9d
0x1800a43ae  mov     [rsp+0A8h+var_58], r13
0x1800a43b3  mov     esi, r8d
0x1800a43b6  mov     [rsp+0A8h+var_60], r13
0x1800a43bb  movzx   ebp, dx
0x1800a43be  mov     [rsp+0A8h+var_68], rcx
0x1800a43c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a43ca  lea     rdi, WPP_GLOBAL_Control
0x1800a43d1  cmp     rcx, rdi
0x1800a43d4  jz      short loc_1800A43F1
0x1800a43d6  test    byte ptr [rcx+1Ch], 8
0x1800a43da  jz      short loc_1800A43F1
0x1800a43dc  mov     rcx, [rcx+10h]
0x1800a43e0  lea     r8, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids
0x1800a43e7  mov     edx, 0C1h
0x1800a43ec  call    WPP_SF_
0x1800a43f1  lea     rcx, aSvrimplFwsetgl; "SvrImpl_FWSetGlobalConfig"
0x1800a43f8  call    FwAcquireRPCSharedLock
0x1800a43fd  test    eax, eax
0x1800a43ff  js      loc_1800A4E1D
0x1800a4405  call    FwLock
0x1800a440a  mov     ebx, eax
0x1800a440c  test    eax, eax
0x1800a440e  jns     short loc_1800A4423
0x1800a4410  lea     rcx, aSvrimplFwsetgl; "SvrImpl_FWSetGlobalConfig"
0x1800a4417  call    FwReleaseRPCSharedLock
0x1800a441c  mov     eax, ebx
0x1800a441e  jmp     loc_1800A4E1D
0x1800a4423  mov     rcx, [rsp+0A8h+var_68]
0x1800a4428  lea     rdx, [rsp+0A8h+var_58]
0x1800a442d  call    ExtractRPCClientSID
0x1800a4432  xor     r8d, r8d
0x1800a4435  mov     ebx, eax
0x1800a4437  mov     edx, 4
0x1800a443c  test    eax, eax
0x1800a443e  jns     loc_1800A44F5
0x1800a4444  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a444b  cmp     rcx, rdi
0x1800a444e  jz      short loc_1800A4471
0x1800a4450  lea     edi, [rdx-3]
0x1800a4453  test    [rcx+1Ch], dil
0x1800a4457  jz      short loc_1800A4471
0x1800a4459  mov     edx, 0C2h
0x1800a445e  mov     r9d, eax
0x1800a4461  mov     rcx, [rcx+10h]
0x1800a4465  lea     r8, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids
0x1800a446c  call    WPP_SF_d
0x1800a4471  lea     rsi, WPP_GLOBAL_Control
0x1800a4478  mov     rcx, [rsp+0A8h+var_68]; void *
0x1800a447d  lea     rdx, aSvrimplFwsetgl; "SvrImpl_FWSetGlobalConfig"
0x1800a4484  call    FwUnlockInternal
0x1800a4489  lea     rcx, aSvrimplFwsetgl; "SvrImpl_FWSetGlobalConfig"
0x1800a4490  call    FwReleaseRPCSharedLock
0x1800a4495  test    ebx, ebx
0x1800a4497  js      short loc_1800A44A5
0x1800a4499  call    cs:__imp_FwChangeSourceSignal
0x1800a44a0  nop     dword ptr [rax+rax+00h]
0x1800a44a5  mov     ecx, ebx
0x1800a44a7  call    cs:__imp_FwHResultToWindowsError
0x1800a44ae  nop     dword ptr [rax+rax+00h]
0x1800a44b3  test    r13, r13
0x1800a44b6  lea     rdi, qword_1800FBFF0
0x1800a44bd  mov     rdx, rdi
0x1800a44c0  mov     rcx, r15
0x1800a44c3  cmovnz  rdx, r13
0x1800a44c7  mov     r10, rdi
0x1800a44ca  neg     rcx
0x1800a44cd  mov     rcx, [rsp+0A8h+var_60]
0x1800a44d2  sbb     r9d, r9d
0x1800a44d5  and     r9d, r14d
0x1800a44d8  test    rcx, rcx
0x1800a44db  cmovnz  r10, rcx
0x1800a44df  mov     rcx, [rsp+0A8h+var_58]
0x1800a44e4  test    rcx, rcx
0x1800a44e7  jz      loc_1800A4D70
0x1800a44ed  mov     rcx, [rcx]
0x1800a44f0  jmp     loc_1800A4D77
0x1800a44f5  cmp     esi, 2
0x1800a44f8  jz      short loc_1800A4531
0x1800a44fa  cmp     esi, 0Bh
0x1800a44fd  jz      short loc_1800A4531
0x1800a44ff  mov     r9d, 80070032h
0x1800a4505  mov     ebx, r9d
0x1800a4508  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a450f  cmp     rcx, rdi
0x1800a4512  jz      loc_1800A4471
0x1800a4518  mov     edi, 1
0x1800a451d  test    [rcx+1Ch], dil
0x1800a4521  jz      loc_1800A4471
0x1800a4527  mov     edx, 0C3h
0x1800a452c  jmp     loc_1800A4461
0x1800a4531  mov     edi, 1
0x1800a4536  test    r15, r15
0x1800a4539  jnz     short loc_1800A4588
0x1800a453b  test    r14d, r14d
0x1800a453e  jz      loc_1800A4BE6
0x1800a4544  mov     r9d, 80070057h
0x1800a454a  mov     ebx, r9d
0x1800a454d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a4554  lea     rsi, WPP_GLOBAL_Control
0x1800a455b  cmp     rcx, rsi
0x1800a455e  jz      loc_1800A4478
0x1800a4564  test    [rcx+1Ch], dil
0x1800a4568  jz      loc_1800A4478
0x1800a456e  mov     edx, 0C4h
0x1800a4573  mov     rcx, [rcx+10h]
0x1800a4577  lea     r8, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids
0x1800a457e  call    WPP_SF_d
0x1800a4583  jmp     loc_1800A4478
0x1800a4588  cmp     r12d, 9
0x1800a458c  jg      loc_1800A4872
0x1800a4592  jz      loc_1800A47FB
0x1800a4598  mov     ecx, r12d
0x1800a459b  test    r12d, r12d
0x1800a459e  jz      loc_1800A4B79
0x1800a45a4  sub     ecx, edi
0x1800a45a6  jz      loc_1800A4B79
0x1800a45ac  sub     ecx, edi
0x1800a45ae  jz      loc_1800A4B79
0x1800a45b4  sub     ecx, edi
0x1800a45b6  jz      loc_1800A4BAD
0x1800a45bc  sub     ecx, edi
0x1800a45be  jz      loc_1800A4BAD
0x1800a45c4  sub     ecx, edi
0x1800a45c6  jz      loc_1800A4744
0x1800a45cc  sub     ecx, edi
0x1800a45ce  jz      loc_1800A46CE
0x1800a45d4  sub     ecx, edi
0x1800a45d6  jz      short loc_1800A4657
0x1800a45d8  cmp     ecx, edi
0x1800a45da  jnz     loc_1800A4B79
0x1800a45e0  cmp     r14d, edx
0x1800a45e3  jz      short loc_1800A4619
0x1800a45e5  mov     r9d, 80070057h
0x1800a45eb  mov     ebx, r9d
0x1800a45ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a45f5  lea     rsi, WPP_GLOBAL_Control
0x1800a45fc  cmp     rcx, rsi
0x1800a45ff  jz      loc_1800A4478
0x1800a4605  test    [rcx+1Ch], dil
0x1800a4609  jz      loc_1800A4478
0x1800a460f  mov     edx, 0CDh
0x1800a4614  jmp     loc_1800A4573
0x1800a4619  cmp     dword ptr [r15], 2
0x1800a461d  jbe     loc_1800A4BE6
0x1800a4623  mov     r9d, 80070057h
0x1800a4629  mov     ebx, r9d
0x1800a462c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a4633  lea     rsi, WPP_GLOBAL_Control
0x1800a463a  cmp     rcx, rsi
0x1800a463d  jz      loc_1800A4478
0x1800a4643  test    [rcx+1Ch], dil
0x1800a4647  jz      loc_1800A4478
0x1800a464d  mov     edx, 0CEh
0x1800a4652  jmp     loc_1800A4573
0x1800a4657  cmp     r14d, edx
0x1800a465a  jz      short loc_1800A4690
0x1800a465c  mov     r9d, 80070057h
0x1800a4662  mov     ebx, r9d
0x1800a4665  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a466c  lea     rsi, WPP_GLOBAL_Control
0x1800a4673  cmp     rcx, rsi
0x1800a4676  jz      loc_1800A4478
0x1800a467c  test    [rcx+1Ch], dil
0x1800a4680  jz      loc_1800A4478
0x1800a4686  mov     edx, 0CBh
0x1800a468b  jmp     loc_1800A4573
0x1800a4690  cmp     dword ptr [r15], 0Fh
0x1800a4694  jbe     loc_1800A4BE6
0x1800a469a  mov     r9d, 80070057h
0x1800a46a0  mov     ebx, r9d
0x1800a46a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a46aa  lea     rsi, WPP_GLOBAL_Control
0x1800a46b1  cmp     rcx, rsi
0x1800a46b4  jz      loc_1800A4478
0x1800a46ba  test    [rcx+1Ch], dil
0x1800a46be  jz      loc_1800A4478
0x1800a46c4  mov     edx, 0CCh
0x1800a46c9  jmp     loc_1800A4573
0x1800a46ce  cmp     r14d, edx
0x1800a46d1  jz      short loc_1800A4707
0x1800a46d3  mov     r9d, 80070057h
0x1800a46d9  mov     ebx, r9d
0x1800a46dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a46e3  lea     rsi, WPP_GLOBAL_Control
0x1800a46ea  cmp     rcx, rsi
0x1800a46ed  jz      loc_1800A4478
0x1800a46f3  test    [rcx+1Ch], dil
0x1800a46f7  jz      loc_1800A4478
0x1800a46fd  mov     edx, 0C9h
0x1800a4702  jmp     loc_1800A4573
0x1800a4707  cmp     [r15], edi
0x1800a470a  jbe     loc_1800A4BE6
0x1800a4710  mov     r9d, 80070057h
0x1800a4716  mov     ebx, r9d
0x1800a4719  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a4720  lea     rsi, WPP_GLOBAL_Control
0x1800a4727  cmp     rcx, rsi
0x1800a472a  jz      loc_1800A4478
0x1800a4730  test    [rcx+1Ch], dil
0x1800a4734  jz      loc_1800A4478
0x1800a473a  mov     edx, 0CAh
0x1800a473f  jmp     loc_1800A4573
0x1800a4744  cmp     r14d, edx
0x1800a4747  jz      short loc_1800A477D
0x1800a4749  mov     r9d, 80070057h
0x1800a474f  mov     ebx, r9d
0x1800a4752  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a4759  lea     rsi, WPP_GLOBAL_Control
0x1800a4760  cmp     rcx, rsi
0x1800a4763  jz      loc_1800A4478
0x1800a4769  test    [rcx+1Ch], dil
0x1800a476d  jz      loc_1800A4478
0x1800a4773  mov     edx, 0C6h
0x1800a4778  jmp     loc_1800A4573
0x1800a477d  cmp     dword ptr [r15], 0E10h
0x1800a4784  jbe     short loc_1800A47BA
0x1800a4786  mov     r9d, 80070057h
0x1800a478c  mov     ebx, r9d
0x1800a478f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a4796  lea     rsi, WPP_GLOBAL_Control
0x1800a479d  cmp     rcx, rsi
0x1800a47a0  jz      loc_1800A4478
0x1800a47a6  test    [rcx+1Ch], dil
0x1800a47aa  jz      loc_1800A4478
0x1800a47b0  mov     edx, 0C7h
0x1800a47b5  jmp     loc_1800A4573
0x1800a47ba  cmp     dword ptr [r15], 12Ch
0x1800a47c1  jnb     loc_1800A4BE6
0x1800a47c7  mov     r9d, 80070057h
0x1800a47cd  mov     ebx, r9d
0x1800a47d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a47d7  lea     rsi, WPP_GLOBAL_Control
0x1800a47de  cmp     rcx, rsi
0x1800a47e1  jz      loc_1800A4478
0x1800a47e7  test    [rcx+1Ch], dil
0x1800a47eb  jz      loc_1800A4478
0x1800a47f1  mov     edx, 0C8h
0x1800a47f6  jmp     loc_1800A4573
0x1800a47fb  cmp     r14d, edx
0x1800a47fe  jz      short loc_1800A4834
0x1800a4800  mov     r9d, 80070057h
0x1800a4806  mov     ebx, r9d
0x1800a4809  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a4810  lea     rsi, WPP_GLOBAL_Control
0x1800a4817  cmp     rcx, rsi
0x1800a481a  jz      loc_1800A4478
0x1800a4820  test    [rcx+1Ch], dil
0x1800a4824  jz      loc_1800A4478
0x1800a482a  mov     edx, 0CFh
0x1800a482f  jmp     loc_1800A4573
0x1800a4834  cmp     dword ptr [r15], 2
0x1800a4838  jbe     loc_1800A4BE6
0x1800a483e  mov     r9d, 80070057h
0x1800a4844  mov     ebx, r9d
0x1800a4847  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a484e  lea     rsi, WPP_GLOBAL_Control
0x1800a4855  cmp     rcx, rsi
0x1800a4858  jz      loc_1800A4478
0x1800a485e  test    [rcx+1Ch], dil
0x1800a4862  jz      loc_1800A4478
0x1800a4868  mov     edx, 0D0h
0x1800a486d  jmp     loc_1800A4573
0x1800a4872  mov     ecx, r12d
0x1800a4875  sub     ecx, 0Ah
0x1800a4878  jz      loc_1800A4BAD
0x1800a487e  sub     ecx, edi
0x1800a4880  jz      loc_1800A4B79
0x1800a4886  sub     ecx, edi
0x1800a4888  jz      loc_1800A49F8
0x1800a488e  sub     ecx, edi
0x1800a4890  jz      loc_1800A49F8
0x1800a4896  sub     ecx, edi
0x1800a4898  jz      loc_1800A4BAD
0x1800a489e  sub     ecx, edi
0x1800a48a0  jz      loc_1800A49F8
0x1800a48a6  sub     ecx, edi
0x1800a48a8  jz      loc_1800A49F8
0x1800a48ae  sub     ecx, edi
0x1800a48b0  jz      loc_1800A497E
0x1800a48b6  cmp     ecx, edi
0x1800a48b8  jnz     loc_1800A4B79
0x1800a48be  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Netsec_AuditMode_Hardening@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Netsec_AuditMode_Hardening@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Netsec_AuditMode_Hardening> `wil::Feature<__WilFeatureTraits_Feature_Netsec_AuditMode_Hardening>::GetImpl(void)'::`2'::impl
0x1800a48c5  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Netsec_AuditMode_Hardening@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Netsec_AuditMode_Hardening>::__private_IsEnabled(void)
0x1800a48ca  test    al, al
  ... truncated ...
```
