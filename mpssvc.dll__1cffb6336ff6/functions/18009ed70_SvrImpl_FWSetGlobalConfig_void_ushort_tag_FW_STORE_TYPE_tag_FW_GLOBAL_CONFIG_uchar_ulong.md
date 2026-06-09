# SvrImpl_FWSetGlobalConfig(void *,ushort,_tag_FW_STORE_TYPE,_tag_FW_GLOBAL_CONFIG,uchar *,ulong)

- ea: `0x18009ed70`
- end: `0x18009f7e5`
- name: `?SvrImpl_FWSetGlobalConfig@@YAKPEAXGW4_tag_FW_STORE_TYPE@@W4_tag_FW_GLOBAL_CONFIG@@PEAEK@Z`
- size: `2677`
- prototype: `__int64 __fastcall(void *, unsigned __int16, unsigned int, unsigned int, LPCWCH lpString1, unsigned int)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800c4c10`

## callees

- `0x180005ca0`
- `0x180008618`
- `0x180009460`
- `0x180009720`
- `0x18000a0c0`
- `0x18000af3c`
- `0x180017110`
- `0x18005441c`
- `0x1800674d4`
- `0x18006f520`
- `0x180079940`
- `0x180088728`
- `0x18009ed70`
- `0x1800a1600`
- `0x1800a1868`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18009f4fc`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18009f4fc`
- `fwbase!FwGetRpcCallersProcessImageName` at `0x18009f6c7`
- `fwbase!FwGetRpcCallersProcessImageName` at `0x18009f6c7`
- `fwbase!FwChangeSourceSignal` at `0x18009ee91`
- `fwbase!FwChangeSourceSignal` at `0x18009ee91`
- `fwbase!FwHResultToWindowsError` at `0x18009ee99`
- `fwbase!FwHResultToWindowsError` at `0x18009f778`
- `fwbase!FwHResultToWindowsError` at `0x18009f7c1`
- `fwbase!FwHResultToWindowsError` at `0x18009ee99`
- `fwbase!FwHResultToWindowsError` at `0x18009f778`
- `fwbase!FwHResultToWindowsError` at `0x18009f7c1`
- `fwbase!FwReportReturnError` at `0x18009f6b7`
- `fwbase!FwReportReturnError` at `0x18009f6b7`
- `fwbase!FwAlloc` at `0x18009f65c`
- `fwbase!FwAlloc` at `0x18009f65c`
- `fwbase!FwFree` at `0x18009f7a3`
- `fwbase!FwFree` at `0x18009f7ae`
- `fwbase!FwFree` at `0x18009f7b9`
- `fwbase!FwFree` at `0x18009f7a3`
- `fwbase!FwFree` at `0x18009f7ae`
- `fwbase!FwFree` at `0x18009f7b9`
- `FWPolicyIOMgr!FwSetGlobalConfig` at `0x18009f5db`
- `FWPolicyIOMgr!FwSetGlobalConfig` at `0x18009f5db`
- `FWPolicyIOMgr!FwSddlStringVerify` at `0x18009f50e`
- `FWPolicyIOMgr!FwSddlStringVerify` at `0x18009f50e`

## string_xrefs

- `0x18009f6b0`: `FwAuditLogGlobalConfigChange`
- `0x18009ede9`: `SvrImpl_FWSetGlobalConfig`
- `0x18009ee08`: `SvrImpl_FWSetGlobalConfig`
- `0x18009ee75`: `SvrImpl_FWSetGlobalConfig`
- `0x18009ee81`: `SvrImpl_FWSetGlobalConfig`

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
  __int64 v27; // r8
  int v28; // eax
  int v29; // r8d
  const unsigned __int16 *v31; // [rsp+48h] [rbp-60h] BYREF
  void **v32; // [rsp+50h] [rbp-58h] BYREF

  v6 = 0;
  v32 = 0;
  v31 = 0;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 193, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids);
  result = FwAcquireRPCSharedLock("SvrImpl_FWSetGlobalConfig");
  if ( (int)result >= 0 )
  {
    v11 = FwLock();
    if ( v11 < 0 )
    {
      FwReleaseRPCSharedLock("SvrImpl_FWSetGlobalConfig");
      return (unsigned int)v11;
    }
    RPCClientSID = ExtractRPCClientSID(a1, (__int64)&v32);
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
            WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 223, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids);
          goto LABEL_12;
        }
        v23 = FwConfig2Str(a4, lpString1, 1, v25);
        if ( v23 >= 0 )
        {
          if ( dword_18012E0BC )
          {
            v26 = FwAuditLogSettingChangeImpl(*v32, qword_18012DF28, a4, 1, v6);
            if ( v26 < 0 )
              FwReportReturnError("FwAuditLogGlobalConfigChange", (unsigned int)v26, v27);
          }
          FwGetRpcCallersProcessImageName(a1, &v31);
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
          v17 = &qword_1800F5F90;
          v18 = &qword_1800F5F90;
          if ( v6 )
            v18 = v6;
          v19 = &qword_1800F5F90;
          if ( v31 )
            v19 = v31;
          if ( v32 )
            v20 = (const wchar_t *)*v32;
          else
            v20 = L"S-1-0-0";
          FwEventGlobalConfigurationChanged(v20, v19, a4, lpString1 != 0 ? a6 : 0, lpString1, v18);
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
          {
            if ( v31 )
              v17 = v31;
            v28 = FwHResultToWindowsError((unsigned int)v13);
            WPP_SF_DSD(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 224, v29, v28, (__int64)v17, a4);
          }
          FwFree(v6);
          FwFree(v31);
          FwFree(v32);
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
    WPP_SF_d(*(_QWORD *)(v14 + 16), v15, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids, v16);
    goto LABEL_12;
  }
  return result;
}

```

## disassembly

```asm
0x18009ed70  push    rbx
0x18009ed72  push    rbp
0x18009ed73  push    rsi
0x18009ed74  push    rdi
0x18009ed75  push    r12
0x18009ed77  push    r13
0x18009ed79  push    r14
0x18009ed7b  push    r15
0x18009ed7d  sub     rsp, 68h
0x18009ed81  mov     rax, cs:__security_cookie
0x18009ed88  xor     rax, rsp
0x18009ed8b  mov     [rsp+0A8h+var_50], rax
0x18009ed90  mov     r14d, [rsp+0A8h+arg_28]
0x18009ed98  xor     r13d, r13d
0x18009ed9b  mov     r15, [rsp+0A8h+lpString1]
0x18009eda3  mov     r12d, r9d
0x18009eda6  mov     [rsp+0A8h+var_58], r13
0x18009edab  mov     esi, r8d
0x18009edae  mov     [rsp+0A8h+var_60], r13
0x18009edb3  movzx   ebp, dx
0x18009edb6  mov     [rsp+0A8h+var_68], rcx
0x18009edbb  mov     rcx, cs:WPP_GLOBAL_Control
0x18009edc2  lea     rdi, WPP_GLOBAL_Control
0x18009edc9  cmp     rcx, rdi
0x18009edcc  jz      short loc_18009EDE9
0x18009edce  test    byte ptr [rcx+1Ch], 8
0x18009edd2  jz      short loc_18009EDE9
0x18009edd4  mov     rcx, [rcx+10h]
0x18009edd8  lea     r8, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids
0x18009eddf  mov     edx, 0C1h
0x18009ede4  call    WPP_SF_
0x18009ede9  lea     rcx, aSvrimplFwsetgl; "SvrImpl_FWSetGlobalConfig"
0x18009edf0  call    FwAcquireRPCSharedLock
0x18009edf5  test    eax, eax
0x18009edf7  js      loc_18009F7C7
0x18009edfd  call    FwLock
0x18009ee02  mov     ebx, eax
0x18009ee04  test    eax, eax
0x18009ee06  jns     short loc_18009EE1B
0x18009ee08  lea     rcx, aSvrimplFwsetgl; "SvrImpl_FWSetGlobalConfig"
0x18009ee0f  call    FwReleaseRPCSharedLock
0x18009ee14  mov     eax, ebx
0x18009ee16  jmp     loc_18009F7C7
0x18009ee1b  mov     rcx, [rsp+0A8h+var_68]
0x18009ee20  lea     rdx, [rsp+0A8h+var_58]
0x18009ee25  call    ExtractRPCClientSID
0x18009ee2a  xor     r8d, r8d
0x18009ee2d  mov     ebx, eax
0x18009ee2f  mov     edx, 4
0x18009ee34  test    eax, eax
0x18009ee36  jns     loc_18009EEE1
0x18009ee3c  mov     rcx, cs:WPP_GLOBAL_Control
0x18009ee43  cmp     rcx, rdi
0x18009ee46  jz      short loc_18009EE69
0x18009ee48  lea     edi, [rdx-3]
0x18009ee4b  test    [rcx+1Ch], dil
0x18009ee4f  jz      short loc_18009EE69
0x18009ee51  mov     edx, 0C2h
0x18009ee56  mov     r9d, eax
0x18009ee59  mov     rcx, [rcx+10h]
0x18009ee5d  lea     r8, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids
0x18009ee64  call    WPP_SF_d
0x18009ee69  lea     rsi, WPP_GLOBAL_Control
0x18009ee70  mov     rcx, [rsp+0A8h+var_68]; void *
0x18009ee75  lea     rdx, aSvrimplFwsetgl; "SvrImpl_FWSetGlobalConfig"
0x18009ee7c  call    FwUnlockInternal
0x18009ee81  lea     rcx, aSvrimplFwsetgl; "SvrImpl_FWSetGlobalConfig"
0x18009ee88  call    FwReleaseRPCSharedLock
0x18009ee8d  test    ebx, ebx
0x18009ee8f  js      short loc_18009EE97
0x18009ee91  call    cs:__imp_FwChangeSourceSignal
0x18009ee97  mov     ecx, ebx
0x18009ee99  call    cs:__imp_FwHResultToWindowsError
0x18009ee9f  test    r13, r13
0x18009eea2  lea     rdi, qword_1800F5F90
0x18009eea9  mov     rdx, rdi
0x18009eeac  mov     rcx, r15
0x18009eeaf  cmovnz  rdx, r13
0x18009eeb3  mov     r10, rdi
0x18009eeb6  neg     rcx
0x18009eeb9  mov     rcx, [rsp+0A8h+var_60]
0x18009eebe  sbb     r9d, r9d
0x18009eec1  and     r9d, r14d
0x18009eec4  test    rcx, rcx
0x18009eec7  cmovnz  r10, rcx
0x18009eecb  mov     rcx, [rsp+0A8h+var_58]
0x18009eed0  test    rcx, rcx
0x18009eed3  jz      loc_18009F738
0x18009eed9  mov     rcx, [rcx]
0x18009eedc  jmp     loc_18009F73F
0x18009eee1  cmp     esi, 2
0x18009eee4  jz      short loc_18009EF1D
0x18009eee6  cmp     esi, 0Bh
0x18009eee9  jz      short loc_18009EF1D
0x18009eeeb  mov     r9d, 80070032h
0x18009eef1  mov     ebx, r9d
0x18009eef4  mov     rcx, cs:WPP_GLOBAL_Control
0x18009eefb  cmp     rcx, rdi
0x18009eefe  jz      loc_18009EE69
0x18009ef04  mov     edi, 1
0x18009ef09  test    [rcx+1Ch], dil
0x18009ef0d  jz      loc_18009EE69
0x18009ef13  mov     edx, 0C3h
0x18009ef18  jmp     loc_18009EE59
0x18009ef1d  mov     edi, 1
0x18009ef22  test    r15, r15
0x18009ef25  jnz     short loc_18009EF74
0x18009ef27  test    r14d, r14d
0x18009ef2a  jz      loc_18009F5C6
0x18009ef30  mov     r9d, 80070057h
0x18009ef36  mov     ebx, r9d
0x18009ef39  mov     rcx, cs:WPP_GLOBAL_Control
0x18009ef40  lea     rsi, WPP_GLOBAL_Control
0x18009ef47  cmp     rcx, rsi
0x18009ef4a  jz      loc_18009EE70
0x18009ef50  test    [rcx+1Ch], dil
0x18009ef54  jz      loc_18009EE70
0x18009ef5a  mov     edx, 0C4h
0x18009ef5f  mov     rcx, [rcx+10h]
0x18009ef63  lea     r8, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids
0x18009ef6a  call    WPP_SF_d
0x18009ef6f  jmp     loc_18009EE70
0x18009ef74  cmp     r12d, 9
0x18009ef78  jg      loc_18009F25E
0x18009ef7e  jz      loc_18009F1E7
0x18009ef84  mov     ecx, r12d
0x18009ef87  test    r12d, r12d
0x18009ef8a  jz      loc_18009F559
0x18009ef90  sub     ecx, edi
0x18009ef92  jz      loc_18009F559
0x18009ef98  sub     ecx, edi
0x18009ef9a  jz      loc_18009F559
0x18009efa0  sub     ecx, edi
0x18009efa2  jz      loc_18009F58D
0x18009efa8  sub     ecx, edi
0x18009efaa  jz      loc_18009F58D
0x18009efb0  sub     ecx, edi
0x18009efb2  jz      loc_18009F130
0x18009efb8  sub     ecx, edi
0x18009efba  jz      loc_18009F0BA
0x18009efc0  sub     ecx, edi
0x18009efc2  jz      short loc_18009F043
0x18009efc4  cmp     ecx, edi
0x18009efc6  jnz     loc_18009F559
0x18009efcc  cmp     r14d, edx
0x18009efcf  jz      short loc_18009F005
0x18009efd1  mov     r9d, 80070057h
0x18009efd7  mov     ebx, r9d
0x18009efda  mov     rcx, cs:WPP_GLOBAL_Control
0x18009efe1  lea     rsi, WPP_GLOBAL_Control
0x18009efe8  cmp     rcx, rsi
0x18009efeb  jz      loc_18009EE70
0x18009eff1  test    [rcx+1Ch], dil
0x18009eff5  jz      loc_18009EE70
0x18009effb  mov     edx, 0CDh
0x18009f000  jmp     loc_18009EF5F
0x18009f005  cmp     dword ptr [r15], 2
0x18009f009  jbe     loc_18009F5C6
0x18009f00f  mov     r9d, 80070057h
0x18009f015  mov     ebx, r9d
0x18009f018  mov     rcx, cs:WPP_GLOBAL_Control
0x18009f01f  lea     rsi, WPP_GLOBAL_Control
0x18009f026  cmp     rcx, rsi
0x18009f029  jz      loc_18009EE70
0x18009f02f  test    [rcx+1Ch], dil
0x18009f033  jz      loc_18009EE70
0x18009f039  mov     edx, 0CEh
0x18009f03e  jmp     loc_18009EF5F
0x18009f043  cmp     r14d, edx
0x18009f046  jz      short loc_18009F07C
0x18009f048  mov     r9d, 80070057h
0x18009f04e  mov     ebx, r9d
0x18009f051  mov     rcx, cs:WPP_GLOBAL_Control
0x18009f058  lea     rsi, WPP_GLOBAL_Control
0x18009f05f  cmp     rcx, rsi
0x18009f062  jz      loc_18009EE70
0x18009f068  test    [rcx+1Ch], dil
0x18009f06c  jz      loc_18009EE70
0x18009f072  mov     edx, 0CBh
0x18009f077  jmp     loc_18009EF5F
0x18009f07c  cmp     dword ptr [r15], 0Fh
0x18009f080  jbe     loc_18009F5C6
0x18009f086  mov     r9d, 80070057h
0x18009f08c  mov     ebx, r9d
0x18009f08f  mov     rcx, cs:WPP_GLOBAL_Control
0x18009f096  lea     rsi, WPP_GLOBAL_Control
0x18009f09d  cmp     rcx, rsi
0x18009f0a0  jz      loc_18009EE70
0x18009f0a6  test    [rcx+1Ch], dil
0x18009f0aa  jz      loc_18009EE70
0x18009f0b0  mov     edx, 0CCh
0x18009f0b5  jmp     loc_18009EF5F
0x18009f0ba  cmp     r14d, edx
0x18009f0bd  jz      short loc_18009F0F3
0x18009f0bf  mov     r9d, 80070057h
0x18009f0c5  mov     ebx, r9d
0x18009f0c8  mov     rcx, cs:WPP_GLOBAL_Control
0x18009f0cf  lea     rsi, WPP_GLOBAL_Control
0x18009f0d6  cmp     rcx, rsi
0x18009f0d9  jz      loc_18009EE70
0x18009f0df  test    [rcx+1Ch], dil
0x18009f0e3  jz      loc_18009EE70
0x18009f0e9  mov     edx, 0C9h
0x18009f0ee  jmp     loc_18009EF5F
0x18009f0f3  cmp     [r15], edi
0x18009f0f6  jbe     loc_18009F5C6
0x18009f0fc  mov     r9d, 80070057h
0x18009f102  mov     ebx, r9d
0x18009f105  mov     rcx, cs:WPP_GLOBAL_Control
0x18009f10c  lea     rsi, WPP_GLOBAL_Control
0x18009f113  cmp     rcx, rsi
0x18009f116  jz      loc_18009EE70
0x18009f11c  test    [rcx+1Ch], dil
0x18009f120  jz      loc_18009EE70
0x18009f126  mov     edx, 0CAh
0x18009f12b  jmp     loc_18009EF5F
0x18009f130  cmp     r14d, edx
0x18009f133  jz      short loc_18009F169
0x18009f135  mov     r9d, 80070057h
0x18009f13b  mov     ebx, r9d
0x18009f13e  mov     rcx, cs:WPP_GLOBAL_Control
0x18009f145  lea     rsi, WPP_GLOBAL_Control
0x18009f14c  cmp     rcx, rsi
0x18009f14f  jz      loc_18009EE70
0x18009f155  test    [rcx+1Ch], dil
0x18009f159  jz      loc_18009EE70
0x18009f15f  mov     edx, 0C6h
0x18009f164  jmp     loc_18009EF5F
0x18009f169  cmp     dword ptr [r15], 0E10h
0x18009f170  jbe     short loc_18009F1A6
0x18009f172  mov     r9d, 80070057h
0x18009f178  mov     ebx, r9d
0x18009f17b  mov     rcx, cs:WPP_GLOBAL_Control
0x18009f182  lea     rsi, WPP_GLOBAL_Control
0x18009f189  cmp     rcx, rsi
0x18009f18c  jz      loc_18009EE70
0x18009f192  test    [rcx+1Ch], dil
0x18009f196  jz      loc_18009EE70
0x18009f19c  mov     edx, 0C7h
0x18009f1a1  jmp     loc_18009EF5F
0x18009f1a6  cmp     dword ptr [r15], 12Ch
0x18009f1ad  jnb     loc_18009F5C6
0x18009f1b3  mov     r9d, 80070057h
0x18009f1b9  mov     ebx, r9d
0x18009f1bc  mov     rcx, cs:WPP_GLOBAL_Control
0x18009f1c3  lea     rsi, WPP_GLOBAL_Control
0x18009f1ca  cmp     rcx, rsi
0x18009f1cd  jz      loc_18009EE70
0x18009f1d3  test    [rcx+1Ch], dil
0x18009f1d7  jz      loc_18009EE70
0x18009f1dd  mov     edx, 0C8h
0x18009f1e2  jmp     loc_18009EF5F
0x18009f1e7  cmp     r14d, edx
0x18009f1ea  jz      short loc_18009F220
0x18009f1ec  mov     r9d, 80070057h
0x18009f1f2  mov     ebx, r9d
0x18009f1f5  mov     rcx, cs:WPP_GLOBAL_Control
0x18009f1fc  lea     rsi, WPP_GLOBAL_Control
0x18009f203  cmp     rcx, rsi
0x18009f206  jz      loc_18009EE70
0x18009f20c  test    [rcx+1Ch], dil
0x18009f210  jz      loc_18009EE70
0x18009f216  mov     edx, 0CFh
0x18009f21b  jmp     loc_18009EF5F
0x18009f220  cmp     dword ptr [r15], 2
0x18009f224  jbe     loc_18009F5C6
0x18009f22a  mov     r9d, 80070057h
0x18009f230  mov     ebx, r9d
0x18009f233  mov     rcx, cs:WPP_GLOBAL_Control
0x18009f23a  lea     rsi, WPP_GLOBAL_Control
0x18009f241  cmp     rcx, rsi
0x18009f244  jz      loc_18009EE70
0x18009f24a  test    [rcx+1Ch], dil
0x18009f24e  jz      loc_18009EE70
0x18009f254  mov     edx, 0D0h
0x18009f259  jmp     loc_18009EF5F
0x18009f25e  mov     ecx, r12d
0x18009f261  sub     ecx, 0Ah
0x18009f264  jz      loc_18009F58D
0x18009f26a  sub     ecx, edi
0x18009f26c  jz      loc_18009F559
0x18009f272  sub     ecx, edi
0x18009f274  jz      loc_18009F3E4
0x18009f27a  sub     ecx, edi
0x18009f27c  jz      loc_18009F3E4
0x18009f282  sub     ecx, edi
0x18009f284  jz      loc_18009F58D
0x18009f28a  sub     ecx, edi
0x18009f28c  jz      loc_18009F3E4
0x18009f292  sub     ecx, edi
0x18009f294  jz      loc_18009F3E4
0x18009f29a  sub     ecx, edi
0x18009f29c  jz      loc_18009F36A
0x18009f2a2  cmp     ecx, edi
0x18009f2a4  jnz     loc_18009F559
0x18009f2aa  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Netsec_AuditMode_Hardening@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Netsec_AuditMode_Hardening@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Netsec_AuditMode_Hardening> `wil::Feature<__WilFeatureTraits_Feature_Netsec_AuditMode_Hardening>::GetImpl(void)'::`2'::impl
0x18009f2b1  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Netsec_AuditMode_Hardening@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Netsec_AuditMode_Hardening>::__private_IsEnabled(void)
0x18009f2b6  test    al, al
0x18009f2b8  jz      short loc_18009F2F3
0x18009f2ba  cmp     esi, 0Bh
  ... truncated ...
```
