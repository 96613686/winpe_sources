# SvrImpl_FWSetConfig(void *,void *,_tag_FW_PROFILE_CONFIG,_tag_FW_PROFILE_TYPE,uchar *,ulong)

- ea: `0x180007484`
- end: `0x180007eb7`
- name: `?SvrImpl_FWSetConfig@@YAKPEAX0W4_tag_FW_PROFILE_CONFIG@@W4_tag_FW_PROFILE_TYPE@@PEAEK@Z`
- size: `2611`
- prototype: `__int64 __fastcall(void *, __int64, unsigned int, unsigned int, wchar_t *String, int)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x1800c4010`

## callees

- `0x1800059f4`
- `0x180005bc8`
- `0x180005ca0`
- `0x180006d20`
- `0x180007314`
- `0x180007484`
- `0x180008618`
- `0x180009460`
- `0x180009720`
- `0x18000a0c0`
- `0x18000af3c`
- `0x180017110`
- `0x18005b220`
- `0x180068344`
- `0x180069da4`
- `0x18006f520`
- `0x1800a2378`
- `0x1800abd54`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcspbrk` at `0x18000780f`
- `api-ms-win-crt-string-l1-1-0!wcspbrk` at `0x18000780f`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180007508`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180007508`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180007550`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180007550`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000753d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000753d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007d24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007d24`
- `RPCRT4!RpcRevertToSelf` at `0x1800079d2`
- `RPCRT4!RpcRevertToSelf` at `0x1800079d2`
- `RPCRT4!RpcImpersonateClient` at `0x18000752b`
- `RPCRT4!RpcImpersonateClient` at `0x18000752b`
- `fwbase!FwGetRpcCallersProcessImageName` at `0x18000759d`
- `fwbase!FwGetRpcCallersProcessImageName` at `0x18000759d`
- `fwbase!FwLicensingIsXbox` at `0x180007d9b`
- `fwbase!FwLicensingIsXbox` at `0x180007d9b`
- `fwbase!FwChangeSourceSignal` at `0x180007888`
- `fwbase!FwChangeSourceSignal` at `0x180007888`
- `fwbase!FwHResultToWindowsError` at `0x180007890`
- `fwbase!FwHResultToWindowsError` at `0x180007928`
- `fwbase!FwHResultToWindowsError` at `0x1800079a1`
- `fwbase!FwHResultToWindowsError` at `0x180007890`
- `fwbase!FwHResultToWindowsError` at `0x180007928`
- `fwbase!FwHResultToWindowsError` at `0x1800079a1`
- `fwbase!FwGetTokenInformation` at `0x18000756b`
- `fwbase!FwGetTokenInformation` at `0x18000756b`
- `fwbase!FwCloseHandle` at `0x18000757f`
- `fwbase!FwCloseHandle` at `0x18000757f`
- `fwbase!FwAlloc` at `0x1800076e6`
- `fwbase!FwAlloc` at `0x1800076e6`
- `fwbase!FwFree` at `0x18000790c`
- `fwbase!FwFree` at `0x180007916`
- `fwbase!FwFree` at `0x180007920`
- `fwbase!FwFree` at `0x18000790c`
- `fwbase!FwFree` at `0x180007916`
- `fwbase!FwFree` at `0x180007920`
- `FWPolicyIOMgr!FwSetConfig` at `0x18000766a`
- `FWPolicyIOMgr!FwSetConfig` at `0x18000766a`

## string_xrefs

- `0x1800074e1`: `SvrImpl_FWSetConfig`
- `0x18000786c`: `SvrImpl_FWSetConfig`
- `0x180007878`: `SvrImpl_FWSetConfig`
- `0x180007d88`: `SvrImpl_FWSetConfig`

## pseudocode

```c
__int64 __fastcall SvrImpl_FWSetConfig(void *a1, __int64 a2, unsigned int a3, unsigned int a4, wchar_t *String, int a6)
{
  unsigned int v6; // esi
  __int64 result; // rax
  int v10; // ebx
  int v11; // edi
  RPC_STATUS v12; // eax
  signed int TokenInformation; // ebx
  int v14; // esi
  HANDLE CurrentThread; // rax
  __int64 v16; // rdx
  __int64 v17; // rcx
  unsigned int v18; // esi
  int v19; // eax
  __int64 v20; // rax
  const unsigned __int16 *v21; // r14
  int v22; // eax
  __int64 v23; // r9
  __int64 v24; // rdx
  const unsigned __int16 *v25; // rdi
  const unsigned __int16 *v26; // rdx
  const unsigned __int16 *v27; // r10
  const wchar_t *v28; // rcx
  int v29; // eax
  int v30; // r8d
  __int64 v31; // r9
  __int64 v32; // rcx
  __int64 v33; // rdx
  __int64 v34; // rcx
  __int64 v35; // rdx
  signed int LastError; // eax
  const unsigned __int16 *v39; // [rsp+68h] [rbp-21h] BYREF
  void **v40; // [rsp+70h] [rbp-19h] BYREF
  void *TokenHandle; // [rsp+78h] [rbp-11h] BYREF

  v40 = 0;
  v6 = a4;
  v39 = 0;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 142, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids);
  result = FwAcquireRPCSharedLock("SvrImpl_FWSetConfig");
  if ( (int)result >= 0 )
  {
    v10 = FwLock();
    if ( v10 < 0 )
    {
      FwReleaseRPCSharedLock("SvrImpl_FWSetConfig");
      return (unsigned int)v10;
    }
    v11 = 1;
    if ( (unsigned __int8)RtlIsStateSeparationEnabled()
      && !(unsigned int)FwLicensingIsXbox()
      && a3 == 1
      && a6 == 4
      && String
      && !*(_DWORD *)String )
    {
      v32 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 143, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids);
        v32 = WPP_GLOBAL_Control;
      }
      v31 = 2147942405LL;
      TokenInformation = -2147024891;
      if ( (_UNKNOWN *)v32 == &WPP_GLOBAL_Control || (*(_BYTE *)(v32 + 28) & 1) == 0 )
        goto LABEL_68;
      v33 = 144;
LABEL_92:
      WPP_SF_d(*(_QWORD *)(v32 + 16), v33, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids, v31);
      goto LABEL_68;
    }
    TokenHandle = 0;
    v12 = RpcImpersonateClient(a1);
    TokenInformation = v12;
    if ( v12 )
    {
      v14 = 0;
      if ( v12 > 0 )
        TokenInformation = (unsigned __int16)v12 | 0x80070000;
      v34 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_8;
      v35 = 29;
    }
    else
    {
      v14 = 1;
      CurrentThread = GetCurrentThread();
      if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
      {
        TokenInformation = FwGetTokenInformation(TokenHandle, 1, &v40, 0);
        if ( TokenInformation < 0 )
        {
          v34 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          {
            v35 = 31;
            goto LABEL_167;
          }
        }
LABEL_8:
        FwCloseHandle(TokenHandle);
        if ( v14 )
          RpcRevertToSelf();
        if ( TokenInformation < 0 )
        {
          v17 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
            goto LABEL_67;
          v24 = 145;
          goto LABEL_65;
        }
        FwGetRpcCallersProcessImageName(a1, &v39);
        if ( *(_DWORD *)(a2 + 24) != 2 )
        {
          v17 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          {
            WPP_SF_l(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 146);
            v17 = WPP_GLOBAL_Control;
          }
          v23 = 2147942405LL;
          TokenInformation = -2147024891;
          if ( (_UNKNOWN *)v17 == &WPP_GLOBAL_Control || (*(_BYTE *)(v17 + 28) & 1) == 0 )
            goto LABEL_67;
          v24 = 147;
          goto LABEL_66;
        }
        v6 = a4;
        if ( ((a4 - 1) & 0xFFFFFFFC) != 0 || a4 == 3 )
        {
          v31 = 2147942450LL;
          TokenInformation = -2147024846;
          v32 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
            goto LABEL_68;
          v33 = 148;
          goto LABEL_92;
        }
        v17 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
        {
          WPP_SF_lll(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            v16,
            &WPP_GLOBAL_Control,
            *(unsigned int *)(a2 + 16),
            a3,
            a6);
          v17 = WPP_GLOBAL_Control;
        }
        v18 = *(_DWORD *)(a2 + 16);
        if ( v18 != 2 && v18 != 11 )
        {
          v23 = 2147942450LL;
          TokenInformation = -2147024846;
          if ( (_UNKNOWN *)v17 == &WPP_GLOBAL_Control || (*(_BYTE *)(v17 + 28) & 1) == 0 )
            goto LABEL_67;
          v24 = 150;
          goto LABEL_66;
        }
        if ( a3 - 1 > 0x11 )
        {
          v23 = 2147942487LL;
          TokenInformation = -2147024809;
          if ( (_UNKNOWN *)v17 == &WPP_GLOBAL_Control || (*(_BYTE *)(v17 + 28) & 1) == 0 )
            goto LABEL_67;
          v24 = 151;
          goto LABEL_66;
        }
        if ( String )
        {
          if ( (int)a3 <= 9 )
          {
            if ( a3 == 9 )
            {
              if ( wcspbrk(String, L"/*?\"<>|") )
              {
                v23 = 2147942487LL;
                TokenInformation = -2147024809;
                v17 = WPP_GLOBAL_Control;
                if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                  || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
                {
                  goto LABEL_67;
                }
                v24 = 159;
                goto LABEL_66;
              }
              TokenInformation = FwLoggerCreateLogFilesAsCaller(String);
              if ( TokenInformation < 0 )
              {
                v17 = WPP_GLOBAL_Control;
                if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                  || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
                {
                  goto LABEL_67;
                }
                v24 = 160;
                goto LABEL_65;
              }
              goto LABEL_28;
            }
            if ( a3 != 1 && a3 != 2 && a3 != 3 && a3 != 4 && a3 != 5 && a3 != 6 && a3 != 7 )
            {
              if ( a3 == 8 )
              {
                if ( a6 != 4 )
                {
                  v23 = 2147942487LL;
                  TokenInformation = -2147024809;
                  if ( (_UNKNOWN *)v17 == &WPP_GLOBAL_Control || (*(_BYTE *)(v17 + 28) & 1) == 0 )
                    goto LABEL_67;
                  v24 = 155;
                  goto LABEL_66;
                }
                if ( (unsigned int)(*(_DWORD *)String - 1) > 0x7FFE )
                {
                  v23 = 2147942487LL;
                  TokenInformation = -2147024809;
                  if ( (_UNKNOWN *)v17 == &WPP_GLOBAL_Control || (*(_BYTE *)(v17 + 28) & 1) == 0 )
                    goto LABEL_67;
                  v24 = 156;
                  goto LABEL_66;
                }
              }
              goto LABEL_28;
            }
            goto LABEL_51;
          }
          if ( a3 == 10 || a3 == 11 || a3 == 12 || a3 == 13 || a3 == 14 )
          {
LABEL_51:
            if ( a6 != 4 )
            {
              v23 = 2147942487LL;
              TokenInformation = -2147024809;
              if ( (_UNKNOWN *)v17 == &WPP_GLOBAL_Control || (*(_BYTE *)(v17 + 28) & 1) == 0 )
                goto LABEL_67;
              v24 = 154;
              goto LABEL_66;
            }
            goto LABEL_28;
          }
          if ( a3 != 16 && a3 != 17 )
          {
            if ( a3 != 18 )
              goto LABEL_28;
            goto LABEL_51;
          }
          if ( a6 != 4 )
          {
            v23 = 2147942487LL;
            TokenInformation = -2147024809;
            if ( (_UNKNOWN *)v17 == &WPP_GLOBAL_Control || (*(_BYTE *)(v17 + 28) & 1) == 0 )
              goto LABEL_67;
            v24 = 157;
            goto LABEL_66;
          }
          if ( *(_DWORD *)String > 1u )
          {
            v23 = 2147942487LL;
            TokenInformation = -2147024809;
            if ( (_UNKNOWN *)v17 == &WPP_GLOBAL_Control || (*(_BYTE *)(v17 + 28) & 1) == 0 )
              goto LABEL_67;
            v24 = 158;
            goto LABEL_66;
          }
        }
        else
        {
          if ( (_UNKNOWN *)v17 != &WPP_GLOBAL_Control && (*(_BYTE *)(v17 + 28) & 4) != 0 )
          {
            WPP_SF_(*(_QWORD *)(v17 + 16), 152, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids);
            v17 = WPP_GLOBAL_Control;
          }
          if ( a6 )
          {
            v23 = 2147942487LL;
            TokenInformation = -2147024809;
            if ( (_UNKNOWN *)v17 == &WPP_GLOBAL_Control || (*(_BYTE *)(v17 + 28) & 1) == 0 )
              goto LABEL_67;
            v24 = 153;
            goto LABEL_66;
          }
        }
LABEL_28:
        TokenInformation = FwSetConfig(*(_QWORD *)a2, a3, a4, String, a6);
        if ( TokenInformation < 0 )
        {
          v17 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
            goto LABEL_67;
          v24 = 161;
        }
        else
        {
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
            WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 162, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids);
          TokenInformation = FwIncrmSetConfig(*(_QWORD *)(a2 + 8), a3, a4, String, a6);
          if ( TokenInformation >= 0 )
          {
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
            {
              WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 164, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids);
            }
            v19 = FwHyperVMgrApplyHostProfileConfigChange(v18, a4, a3);
            TokenInformation = v19;
            if ( v19 >= 0 )
            {
              v20 = FwAlloc(2048);
              v21 = (const unsigned __int16 *)v20;
              if ( v20 )
              {
                v22 = FwConfig2Str(a3, String, 0, v20);
                if ( v22 >= 0 )
                {
                  v6 = a4;
                  FwAuditLogProfileConfigChange(*v40);
LABEL_39:
                  if ( a3 == 1 )
                  {
                    if ( String )
                      v11 = *(_DWORD *)String;
                    FwSvcTelemeterFwStateChange(v11 != 0, v6, v39);
                  }
                  goto LABEL_69;
                }
                if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
                {
                  WPP_SF_d(
                    *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                    166,
                    WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids,
                    (unsigned int)v22);
                }
              }
              else if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                     && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
              {
                WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 167, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids);
              }
              v6 = a4;
              goto LABEL_39;
            }
            v17 = WPP_GLOBAL_Control;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
            {
              goto LABEL_67;
            }
            v24 = 165;
            v23 = (unsigned int)v19;
LABEL_66:
            WPP_SF_d(*(_QWORD *)(v17 + 16), v24, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids, v23);
LABEL_67:
            v6 = a4;
LABEL_68:
            v21 = 0;
LABEL_69:
            FwUnlockInternal(a1, "SvrImpl_FWSetConfig");
            FwReleaseRPCSharedLock("SvrImpl_FWSetConfig");
            if ( TokenInformation >= 0 )
              FwChangeSourceSignal();
            FwHResultToWindowsError((unsigned int)TokenInformation);
            v25 = &qword_1800F5F90;
            v26 = &qword_1800F5F90;
            if ( v21 )
              v26 = v21;
            v27 = &qword_1800F5F90;
            if ( v39 )
              v27 = v39;
            if ( v40 )
              v28 = (const wchar_t *)*v40;
            else
              v28 = L"S-1-0-0";
            FwEventProfileConfigurationChanged(v28, v27, v6, a3, String != 0 ? a6 : 0, String, v26);
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
            {
              if ( v39 )
                v25 = v39;
              v29 = FwHResultToWindowsError((unsigned int)TokenInformation);
              WPP_SF_DSDD(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 168, v30, v29, (__int64)v25, v6, a3);
            }
            FwFree(v21);
            FwFree(v39);
            FwFree(v40);
            return FwHResultToWindowsError((unsigned int)TokenInformation);
          }
          v17 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
            goto LABEL_67;
          v24 = 163;
        }
LABEL_65:
        v23 = (unsigned int)TokenInformation;
        goto LABEL_66;
      }
      LastError = GetLastError();
      TokenInformation = LastError;
      if ( LastError > 0 )
        TokenInformation = (unsigned __int16)LastError | 0x80070000;
      v34 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_8;
      v35 = 30;
    }
LABEL_167:
    WPP_SF_d(
      *(_QWORD *)(v34 + 16),
      v35,
      WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids,
      (unsigned int)TokenInformation);
    goto LABEL_8;
  }
  return result;
}

```

## disassembly

```asm
0x180007484  push    rbp
0x180007486  push    rbx
0x180007487  push    rsi
0x180007488  push    rdi
0x180007489  push    r12
0x18000748b  push    r13
0x18000748d  push    r14
0x18000748f  push    r15
0x180007491  lea     rbp, [rsp-0Fh]
0x180007496  sub     rsp, 98h
0x18000749d  mov     rax, cs:__security_cookie
0x1800074a4  xor     rax, rsp
0x1800074a7  mov     [rbp+47h+var_50], rax
0x1800074ab  mov     r12, [rbp+47h+String]
0x1800074af  xor     edi, edi
0x1800074b1  mov     [rbp+47h+var_60], rdi
0x1800074b5  mov     esi, r9d
0x1800074b8  mov     [rbp+47h+var_68], rdi
0x1800074bc  mov     r15d, r8d
0x1800074bf  mov     [rbp+47h+var_80], r9d
0x1800074c3  mov     r14, rdx
0x1800074c6  mov     [rbp+47h+BindingHandle], rcx
0x1800074ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800074d1  lea     rax, WPP_GLOBAL_Control
0x1800074d8  cmp     rcx, rax
0x1800074db  jnz     loc_180007D64
0x1800074e1  lea     rcx, aSvrimplFwsetco; "SvrImpl_FWSetConfig"
0x1800074e8  call    FwAcquireRPCSharedLock
0x1800074ed  test    eax, eax
0x1800074ef  js      loc_18000792E
0x1800074f5  call    FwLock
0x1800074fa  mov     ebx, eax
0x1800074fc  test    eax, eax
0x1800074fe  js      loc_180007D88
0x180007504  mov     [rbp+47h+var_78], rdi
0x180007508  call    cs:__imp_RtlIsStateSeparationEnabled
0x18000750e  mov     r13d, [rbp+47h+arg_28]
0x180007512  mov     edi, 1
0x180007517  test    al, al
0x180007519  jnz     loc_180007D9B
0x18000751f  mov     rcx, [rbp+47h+BindingHandle]; BindingHandle
0x180007523  mov     [rbp+47h+TokenHandle], 0
0x18000752b  call    cs:__imp_RpcImpersonateClient
0x180007531  mov     ebx, eax
0x180007533  test    eax, eax
0x180007535  jnz     loc_180007CEA
0x18000753b  mov     esi, edi
0x18000753d  call    cs:__imp_GetCurrentThread
0x180007543  lea     r9, [rbp+47h+TokenHandle]; TokenHandle
0x180007547  mov     r8d, edi; OpenAsSelf
0x18000754a  mov     rcx, rax; ThreadHandle
0x18000754d  lea     edx, [rbx+8]; DesiredAccess
0x180007550  call    cs:__imp_OpenThreadToken
0x180007556  test    eax, eax
0x180007558  jz      loc_180007D24
0x18000755e  mov     rcx, [rbp+47h+TokenHandle]
0x180007562  lea     r8, [rbp+47h+var_60]
0x180007566  xor     r9d, r9d
0x180007569  mov     edx, edi
0x18000756b  call    cs:__imp_FwGetTokenInformation
0x180007571  mov     ebx, eax
0x180007573  test    eax, eax
0x180007575  js      loc_180007E2A
0x18000757b  mov     rcx, [rbp+47h+TokenHandle]
0x18000757f  call    cs:__imp_FwCloseHandle
0x180007585  test    esi, esi
0x180007587  jnz     loc_1800079D2
0x18000758d  test    ebx, ebx
0x18000758f  js      loc_180007E68
0x180007595  mov     rcx, [rbp+47h+BindingHandle]
0x180007599  lea     rdx, [rbp+47h+var_68]
0x18000759d  call    cs:__imp_FwGetRpcCallersProcessImageName
0x1800075a3  mov     r9d, [r14+18h]
0x1800075a7  cmp     r9d, 2
0x1800075ab  jnz     loc_180007A21
0x1800075b1  mov     esi, [rbp+47h+var_80]
0x1800075b4  lea     eax, [rsi-1]
0x1800075b7  test    eax, 0FFFFFFFCh
0x1800075bc  jnz     loc_1800079DD
0x1800075c2  cmp     esi, 3
0x1800075c5  jz      loc_1800079DD
0x1800075cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800075d2  lea     r8, WPP_GLOBAL_Control
0x1800075d9  cmp     rcx, r8
0x1800075dc  jnz     loc_180007A5E
0x1800075e2  mov     esi, [r14+10h]
0x1800075e6  cmp     esi, 2
0x1800075e9  jnz     loc_180007A92
0x1800075ef  lea     eax, [r15-1]
0x1800075f3  cmp     eax, 11h
0x1800075f6  ja      loc_180007CC4
0x1800075fc  test    r12, r12
0x1800075ff  jz      loc_180007AC1
0x180007605  cmp     r15d, 9
0x180007609  jg      loc_18000776E
0x18000760f  jz      loc_180007805
0x180007615  mov     edx, r15d
0x180007618  sub     edx, edi
0x18000761a  jz      loc_18000779F
0x180007620  sub     edx, edi
0x180007622  jz      loc_18000779F
0x180007628  sub     edx, edi
0x18000762a  jz      loc_18000779F
0x180007630  sub     edx, edi
0x180007632  jz      loc_18000779F
0x180007638  sub     edx, edi
0x18000763a  jz      loc_18000779F
0x180007640  sub     edx, edi
0x180007642  jz      loc_18000779F
0x180007648  sub     edx, edi
0x18000764a  jz      loc_18000779F
0x180007650  cmp     edx, edi
0x180007652  jz      loc_1800077CF
0x180007658  mov     r8d, [rbp+47h+var_80]
0x18000765c  mov     r9, r12
0x18000765f  mov     rcx, [r14]
0x180007662  mov     edx, r15d
0x180007665  mov     dword ptr [rsp+0D0h+var_B0], r13d
0x18000766a  call    cs:__imp_FwSetConfig
0x180007670  mov     ebx, eax
0x180007672  test    eax, eax
0x180007674  js      loc_180007BA8
0x18000767a  mov     rcx, cs:WPP_GLOBAL_Control
0x180007681  lea     rax, WPP_GLOBAL_Control
0x180007688  cmp     rcx, rax
0x18000768b  jnz     loc_180007BD3
0x180007691  mov     r8d, [rbp+47h+var_80]
0x180007695  mov     r9, r12
0x180007698  mov     rcx, [r14+8]
0x18000769c  mov     edx, r15d
0x18000769f  mov     dword ptr [rsp+0D0h+var_B0], r13d
0x1800076a4  call    FwIncrmSetConfig
0x1800076a9  mov     ebx, eax
0x1800076ab  test    eax, eax
0x1800076ad  js      loc_180007BF7
0x1800076b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800076ba  lea     r14, WPP_GLOBAL_Control
0x1800076c1  cmp     rcx, r14
0x1800076c4  jnz     loc_180007C22
0x1800076ca  mov     edx, [rbp+47h+var_80]
0x1800076cd  mov     r8d, r15d
0x1800076d0  mov     ecx, esi
0x1800076d2  call    FwHyperVMgrApplyHostProfileConfigChange
0x1800076d7  mov     ebx, eax
0x1800076d9  test    eax, eax
0x1800076db  js      loc_180007C46
0x1800076e1  mov     ecx, 800h
0x1800076e6  call    cs:__imp_FwAlloc
0x1800076ec  mov     r14, rax
0x1800076ef  test    rax, rax
0x1800076f2  jz      loc_180007C89
0x1800076f8  mov     r9, rax
0x1800076fb  xor     r8d, r8d
0x1800076fe  mov     rdx, r12
0x180007701  mov     ecx, r15d
0x180007704  call    FwConfig2Str
0x180007709  test    eax, eax
0x18000770b  jns     loc_180007C6D
0x180007711  mov     rcx, cs:WPP_GLOBAL_Control
0x180007718  lea     rdx, WPP_GLOBAL_Control
0x18000771f  cmp     rcx, rdx
0x180007722  jz      short loc_180007742
0x180007724  test    [rcx+1Ch], dil
0x180007728  jz      short loc_180007742
0x18000772a  mov     rcx, [rcx+10h]
0x18000772e  lea     r8, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids
0x180007735  mov     edx, 0A6h
0x18000773a  mov     r9d, eax
0x18000773d  call    WPP_SF_d
0x180007742  mov     esi, [rbp+47h+var_80]
0x180007745  cmp     r15d, edi
0x180007748  jnz     loc_180007868
0x18000774e  test    r12, r12
0x180007751  jz      short loc_180007757
0x180007753  mov     edi, [r12]
0x180007757  mov     r8, [rbp+47h+var_68]
0x18000775b  xor     ecx, ecx
0x18000775d  test    edi, edi
0x18000775f  mov     edx, esi
0x180007761  setnz   cl
0x180007764  call    FwSvcTelemeterFwStateChange
0x180007769  jmp     loc_180007868
0x18000776e  mov     edx, r15d
0x180007771  sub     edx, 0Ah
0x180007774  jz      short loc_18000779F
0x180007776  sub     edx, edi
0x180007778  jz      short loc_18000779F
0x18000777a  sub     edx, edi
0x18000777c  jz      short loc_18000779F
0x18000777e  sub     edx, edi
0x180007780  jz      short loc_18000779F
0x180007782  sub     edx, edi
0x180007784  jz      short loc_18000779F
0x180007786  sub     edx, 2
0x180007789  jz      loc_18000795A
0x18000778f  sub     edx, edi
0x180007791  jz      loc_18000795A
0x180007797  cmp     edx, edi
0x180007799  jnz     loc_180007658
0x18000779f  cmp     r13d, 4
0x1800077a3  jz      loc_180007658
0x1800077a9  mov     r9d, 80070057h
0x1800077af  mov     ebx, r9d
0x1800077b2  cmp     rcx, r8
0x1800077b5  jz      loc_180007861
0x1800077bb  test    [rcx+1Ch], dil
0x1800077bf  jz      loc_180007861
0x1800077c5  mov     edx, 9Ah
0x1800077ca  jmp     loc_180007851
0x1800077cf  cmp     r13d, 4
0x1800077d3  jnz     loc_180007B1E
0x1800077d9  mov     eax, [r12]
0x1800077dd  sub     eax, edi
0x1800077df  cmp     eax, 7FFEh
0x1800077e4  jbe     loc_180007658
0x1800077ea  mov     r9d, 80070057h
0x1800077f0  mov     ebx, r9d
0x1800077f3  cmp     rcx, r8
0x1800077f6  jz      short loc_180007861
0x1800077f8  test    [rcx+1Ch], dil
0x1800077fc  jz      short loc_180007861
0x1800077fe  mov     edx, 9Ch
0x180007803  jmp     short loc_180007851
0x180007805  lea     rdx, Control; "/*?\"<>|"
0x18000780c  mov     rcx, r12; String
0x18000780f  call    cs:__imp_wcspbrk
0x180007815  test    rax, rax
0x180007818  jnz     loc_180007B44
0x18000781e  mov     rcx, r12
0x180007821  call    FwLoggerCreateLogFilesAsCaller
0x180007826  mov     ebx, eax
0x180007828  test    eax, eax
0x18000782a  jns     loc_180007658
0x180007830  mov     rcx, cs:WPP_GLOBAL_Control
0x180007837  lea     rax, WPP_GLOBAL_Control
0x18000783e  cmp     rcx, rax
0x180007841  jz      short loc_180007861
0x180007843  test    [rcx+1Ch], dil
0x180007847  jz      short loc_180007861
0x180007849  mov     edx, 0A0h
0x18000784e  mov     r9d, ebx
0x180007851  mov     rcx, [rcx+10h]
0x180007855  lea     r8, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids
0x18000785c  call    WPP_SF_d
0x180007861  mov     esi, [rbp+47h+var_80]
0x180007864  mov     r14, [rbp+47h+var_78]
0x180007868  mov     rcx, [rbp+47h+BindingHandle]; void *
0x18000786c  lea     rdx, aSvrimplFwsetco; "SvrImpl_FWSetConfig"
0x180007873  call    FwUnlockInternal
0x180007878  lea     rcx, aSvrimplFwsetco; "SvrImpl_FWSetConfig"
0x18000787f  call    FwReleaseRPCSharedLock
0x180007884  test    ebx, ebx
0x180007886  js      short loc_18000788E
0x180007888  call    cs:__imp_FwChangeSourceSignal
0x18000788e  mov     ecx, ebx
0x180007890  call    cs:__imp_FwHResultToWindowsError
0x180007896  test    r14, r14
0x180007899  lea     rdi, qword_1800F5F90
0x1800078a0  mov     rdx, rdi
0x1800078a3  mov     rcx, r12
0x1800078a6  cmovnz  rdx, r14
0x1800078aa  mov     r10, rdi
0x1800078ad  neg     rcx
0x1800078b0  mov     rcx, [rbp+47h+var_68]
0x1800078b4  sbb     r8d, r8d
0x1800078b7  and     r8d, r13d
0x1800078ba  test    rcx, rcx
0x1800078bd  cmovnz  r10, rcx
0x1800078c1  mov     rcx, [rbp+47h+var_60]
0x1800078c5  test    rcx, rcx
0x1800078c8  jz      loc_18000794E
0x1800078ce  mov     rcx, [rcx]
0x1800078d1  mov     [rsp+0D0h+var_90], eax
0x1800078d5  mov     r9d, r15d
0x1800078d8  mov     [rsp+0D0h+var_A0], rdx
0x1800078dd  mov     rdx, r10
0x1800078e0  mov     [rsp+0D0h+var_A8], r12
0x1800078e5  mov     dword ptr [rsp+0D0h+var_B0], r8d
0x1800078ea  mov     r8d, esi
0x1800078ed  call    FwEventProfileConfigurationChanged
0x1800078f2  mov     rax, cs:WPP_GLOBAL_Control
0x1800078f9  lea     rcx, WPP_GLOBAL_Control
0x180007900  cmp     rax, rcx
0x180007903  jnz     loc_18000798A
0x180007909  mov     rcx, r14
0x18000790c  call    cs:__imp_FwFree
0x180007912  mov     rcx, [rbp+47h+var_68]
0x180007916  call    cs:__imp_FwFree
0x18000791c  mov     rcx, [rbp+47h+var_60]
0x180007920  call    cs:__imp_FwFree
0x180007926  mov     ecx, ebx
0x180007928  call    cs:__imp_FwHResultToWindowsError
0x18000792e  mov     rcx, [rbp+47h+var_50]
0x180007932  xor     rcx, rsp; StackCookie
0x180007935  call    __security_check_cookie
0x18000793a  add     rsp, 98h
0x180007941  pop     r15
0x180007943  pop     r14
0x180007945  pop     r13
0x180007947  pop     r12
  ... truncated ...
```
