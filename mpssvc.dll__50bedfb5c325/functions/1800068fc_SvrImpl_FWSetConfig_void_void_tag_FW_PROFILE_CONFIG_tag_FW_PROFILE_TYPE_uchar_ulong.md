# SvrImpl_FWSetConfig(void *,void *,_tag_FW_PROFILE_CONFIG,_tag_FW_PROFILE_TYPE,uchar *,ulong)

- ea: `0x1800068fc`
- end: `0x1800073a8`
- name: `?SvrImpl_FWSetConfig@@YAKPEAX0W4_tag_FW_PROFILE_CONFIG@@W4_tag_FW_PROFILE_TYPE@@PEAEK@Z`
- size: `2732`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x1800cb1f0`

## callees

- `0x180005508`
- `0x180005ab4`
- `0x180005b70`
- `0x180005c4c`
- `0x18000615c`
- `0x180006780`
- `0x1800068fc`
- `0x180007b58`
- `0x180008a80`
- `0x180008d60`
- `0x1800097b0`
- `0x18000a710`
- `0x1800192e0`
- `0x18006bcfc`
- `0x18006cb24`
- `0x1800729c0`
- `0x1800a7b68`
- `0x1800b2270`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcspbrk` at `0x180006cbd`
- `api-ms-win-crt-string-l1-1-0!wcspbrk` at `0x180006cbd`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180006980`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180006980`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800069c1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800069c1`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800069da`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800069da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007209`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007209`
- `RPCRT4!RpcImpersonateClient` at `0x1800069a9`
- `RPCRT4!RpcImpersonateClient` at `0x1800069a9`
- `RPCRT4!RpcRevertToSelf` at `0x180006eb1`
- `RPCRT4!RpcRevertToSelf` at `0x180006eb1`
- `fwbase!FwHResultToWindowsError` at `0x180006d4a`
- `fwbase!FwHResultToWindowsError` at `0x180006dfa`
- `fwbase!FwHResultToWindowsError` at `0x180006e7a`
- `fwbase!FwHResultToWindowsError` at `0x180006d4a`
- `fwbase!FwHResultToWindowsError` at `0x180006dfa`
- `fwbase!FwHResultToWindowsError` at `0x180006e7a`
- `fwbase!FwGetRpcCallersProcessImageName` at `0x180006a39`
- `fwbase!FwGetRpcCallersProcessImageName` at `0x180006a39`
- `fwbase!FwLicensingIsXbox` at `0x180007286`
- `fwbase!FwLicensingIsXbox` at `0x180007286`
- `fwbase!FwChangeSourceSignal` at `0x180006d3c`
- `fwbase!FwChangeSourceSignal` at `0x180006d3c`
- `fwbase!FwGetTokenInformation` at `0x1800069fb`
- `fwbase!FwGetTokenInformation` at `0x1800069fb`
- `fwbase!FwCloseHandle` at `0x180006a15`
- `fwbase!FwCloseHandle` at `0x180006a15`
- `fwbase!FwAlloc` at `0x180006b8e`
- `fwbase!FwAlloc` at `0x180006b8e`
- `fwbase!FwFree` at `0x180006dcc`
- `fwbase!FwFree` at `0x180006ddc`
- `fwbase!FwFree` at `0x180006dec`
- `fwbase!FwFree` at `0x180006dcc`
- `fwbase!FwFree` at `0x180006ddc`
- `fwbase!FwFree` at `0x180006dec`
- `FWPolicyIOMgr!FwSetConfig` at `0x180006b0c`
- `FWPolicyIOMgr!FwSetConfig` at `0x180006b0c`

## string_xrefs

- `0x180006959`: `SvrImpl_FWSetConfig`
- `0x180006d20`: `SvrImpl_FWSetConfig`
- `0x180006d2c`: `SvrImpl_FWSetConfig`
- `0x180007273`: `SvrImpl_FWSetConfig`

## pseudocode

```c
__int64 __fastcall SvrImpl_FWSetConfig(void *a1, __int64 a2, unsigned int a3, unsigned int a4, wchar_t *String, int a6)
{
  unsigned int v6; // esi
  __int64 result; // rax
  int v10; // ebx
  int v11; // edi
  RPC_STATUS v12; // eax
  int TokenInformation; // ebx
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
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 142, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids);
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
        WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 143, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids);
        v32 = WPP_GLOBAL_Control;
      }
      v31 = 2147942405LL;
      TokenInformation = -2147024891;
      if ( (_UNKNOWN *)v32 == &WPP_GLOBAL_Control || (*(_BYTE *)(v32 + 28) & 1) == 0 )
        goto LABEL_68;
      v33 = 144;
LABEL_92:
      WPP_SF_d(*(_QWORD *)(v32 + 16), v33, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids, v31);
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
              TokenInformation = FwLoggerCreateLogFilesAsCaller((__int64)String);
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
            WPP_SF_(*(_QWORD *)(v17 + 16), 152, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids);
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
            WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 162, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids);
          TokenInformation = FwIncrmSetConfig(*(_QWORD *)(a2 + 8), a3, a4, String, a6);
          if ( TokenInformation >= 0 )
          {
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
            {
              WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 164, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids);
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
                    WPP_681457f4cdf23248f51377d70d9ff610_Traceguids,
                    (unsigned int)v22);
                }
              }
              else if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                     && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
              {
                WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 167, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids);
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
            WPP_SF_d(*(_QWORD *)(v17 + 16), v24, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids, v23);
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
            v25 = &qword_1800FBFF0;
            v26 = &qword_1800FBFF0;
            if ( v21 )
              v26 = v21;
            v27 = &qword_1800FBFF0;
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
      WPP_681457f4cdf23248f51377d70d9ff610_Traceguids,
      (unsigned int)TokenInformation);
    goto LABEL_8;
  }
  return result;
}

```

## disassembly

```asm
0x1800068fc  push    rbp
0x1800068fe  push    rbx
0x1800068ff  push    rsi
0x180006900  push    rdi
0x180006901  push    r12
0x180006903  push    r13
0x180006905  push    r14
0x180006907  push    r15
0x180006909  lea     rbp, [rsp-0Fh]
0x18000690e  sub     rsp, 98h
0x180006915  mov     rax, cs:__security_cookie
0x18000691c  xor     rax, rsp
0x18000691f  mov     [rbp+47h+var_50], rax
0x180006923  mov     r12, [rbp+47h+String]
0x180006927  xor     edi, edi
0x180006929  mov     [rbp+47h+var_60], rdi
0x18000692d  mov     esi, r9d
0x180006930  mov     [rbp+47h+var_68], rdi
0x180006934  mov     r15d, r8d
0x180006937  mov     [rbp+47h+var_80], r9d
0x18000693b  mov     r14, rdx
0x18000693e  mov     [rbp+47h+BindingHandle], rcx
0x180006942  mov     rcx, cs:WPP_GLOBAL_Control
0x180006949  lea     rax, WPP_GLOBAL_Control
0x180006950  cmp     rcx, rax
0x180006953  jnz     loc_18000724F
0x180006959  lea     rcx, aSvrimplFwsetco; "SvrImpl_FWSetConfig"
0x180006960  call    FwAcquireRPCSharedLock
0x180006965  test    eax, eax
0x180006967  js      loc_180006E06
0x18000696d  call    FwLock
0x180006972  mov     ebx, eax
0x180006974  test    eax, eax
0x180006976  js      loc_180007273
0x18000697c  mov     [rbp+47h+var_78], rdi
0x180006980  call    cs:__imp_RtlIsStateSeparationEnabled
0x180006987  nop     dword ptr [rax+rax+00h]
0x18000698c  mov     r13d, [rbp+47h+arg_28]
0x180006990  mov     edi, 1
0x180006995  test    al, al
0x180006997  jnz     loc_180007286
0x18000699d  mov     rcx, [rbp+47h+BindingHandle]; BindingHandle
0x1800069a1  mov     [rbp+47h+TokenHandle], 0
0x1800069a9  call    cs:__imp_RpcImpersonateClient
0x1800069b0  nop     dword ptr [rax+rax+00h]
0x1800069b5  mov     ebx, eax
0x1800069b7  test    eax, eax
0x1800069b9  jnz     loc_1800071CF
0x1800069bf  mov     esi, edi
0x1800069c1  call    cs:__imp_GetCurrentThread
0x1800069c8  nop     dword ptr [rax+rax+00h]
0x1800069cd  lea     r9, [rbp+47h+TokenHandle]; TokenHandle
0x1800069d1  mov     r8d, edi; OpenAsSelf
0x1800069d4  mov     rcx, rax; ThreadHandle
0x1800069d7  lea     edx, [rbx+8]; DesiredAccess
0x1800069da  call    cs:__imp_OpenThreadToken
0x1800069e1  nop     dword ptr [rax+rax+00h]
0x1800069e6  test    eax, eax
0x1800069e8  jz      loc_180007209
0x1800069ee  mov     rcx, [rbp+47h+TokenHandle]
0x1800069f2  lea     r8, [rbp+47h+var_60]
0x1800069f6  xor     r9d, r9d
0x1800069f9  mov     edx, edi
0x1800069fb  call    cs:__imp_FwGetTokenInformation
0x180006a02  nop     dword ptr [rax+rax+00h]
0x180006a07  mov     ebx, eax
0x180006a09  test    eax, eax
0x180006a0b  js      loc_18000731B
0x180006a11  mov     rcx, [rbp+47h+TokenHandle]
0x180006a15  call    cs:__imp_FwCloseHandle
0x180006a1c  nop     dword ptr [rax+rax+00h]
0x180006a21  test    esi, esi
0x180006a23  jnz     loc_180006EB1
0x180006a29  test    ebx, ebx
0x180006a2b  js      loc_180007359
0x180006a31  mov     rcx, [rbp+47h+BindingHandle]
0x180006a35  lea     rdx, [rbp+47h+var_68]
0x180006a39  call    cs:__imp_FwGetRpcCallersProcessImageName
0x180006a40  nop     dword ptr [rax+rax+00h]
0x180006a45  mov     r9d, [r14+18h]
0x180006a49  cmp     r9d, 2
0x180006a4d  jnz     loc_180006F06
0x180006a53  mov     esi, [rbp+47h+var_80]
0x180006a56  lea     eax, [rsi-1]
0x180006a59  test    eax, 0FFFFFFFCh
0x180006a5e  jnz     loc_180006EC2
0x180006a64  cmp     esi, 3
0x180006a67  jz      loc_180006EC2
0x180006a6d  mov     rcx, cs:WPP_GLOBAL_Control
0x180006a74  lea     r8, WPP_GLOBAL_Control
0x180006a7b  cmp     rcx, r8
0x180006a7e  jnz     loc_180006F43
0x180006a84  mov     esi, [r14+10h]
0x180006a88  cmp     esi, 2
0x180006a8b  jnz     loc_180006F77
0x180006a91  lea     eax, [r15-1]
0x180006a95  cmp     eax, 11h
0x180006a98  ja      loc_1800071A9
0x180006a9e  test    r12, r12
0x180006aa1  jz      loc_180006FA6
0x180006aa7  cmp     r15d, 9
0x180006aab  jg      loc_180006C1C
0x180006ab1  jz      loc_180006CB3
0x180006ab7  mov     edx, r15d
0x180006aba  sub     edx, edi
0x180006abc  jz      loc_180006C4D
0x180006ac2  sub     edx, edi
0x180006ac4  jz      loc_180006C4D
0x180006aca  sub     edx, edi
0x180006acc  jz      loc_180006C4D
0x180006ad2  sub     edx, edi
0x180006ad4  jz      loc_180006C4D
0x180006ada  sub     edx, edi
0x180006adc  jz      loc_180006C4D
0x180006ae2  sub     edx, edi
0x180006ae4  jz      loc_180006C4D
0x180006aea  sub     edx, edi
0x180006aec  jz      loc_180006C4D
0x180006af2  cmp     edx, edi
0x180006af4  jz      loc_180006C7D
0x180006afa  mov     r8d, [rbp+47h+var_80]
0x180006afe  mov     r9, r12
0x180006b01  mov     rcx, [r14]
0x180006b04  mov     edx, r15d
0x180006b07  mov     dword ptr [rsp+0D0h+var_B0], r13d
0x180006b0c  call    cs:__imp_FwSetConfig
0x180006b13  nop     dword ptr [rax+rax+00h]
0x180006b18  mov     ebx, eax
0x180006b1a  test    eax, eax
0x180006b1c  js      loc_18000708D
0x180006b22  mov     rcx, cs:WPP_GLOBAL_Control
0x180006b29  lea     rax, WPP_GLOBAL_Control
0x180006b30  cmp     rcx, rax
0x180006b33  jnz     loc_1800070B8
0x180006b39  mov     r8d, [rbp+47h+var_80]
0x180006b3d  mov     r9, r12
0x180006b40  mov     rcx, [r14+8]
0x180006b44  mov     edx, r15d
0x180006b47  mov     dword ptr [rsp+0D0h+var_B0], r13d
0x180006b4c  call    FwIncrmSetConfig
0x180006b51  mov     ebx, eax
0x180006b53  test    eax, eax
0x180006b55  js      loc_1800070DC
0x180006b5b  mov     rcx, cs:WPP_GLOBAL_Control
0x180006b62  lea     r14, WPP_GLOBAL_Control
0x180006b69  cmp     rcx, r14
0x180006b6c  jnz     loc_180007107
0x180006b72  mov     edx, [rbp+47h+var_80]
0x180006b75  mov     r8d, r15d
0x180006b78  mov     ecx, esi
0x180006b7a  call    FwHyperVMgrApplyHostProfileConfigChange
0x180006b7f  mov     ebx, eax
0x180006b81  test    eax, eax
0x180006b83  js      loc_18000712B
0x180006b89  mov     ecx, 800h
0x180006b8e  call    cs:__imp_FwAlloc
0x180006b95  nop     dword ptr [rax+rax+00h]
0x180006b9a  mov     r14, rax
0x180006b9d  test    rax, rax
0x180006ba0  jz      loc_18000716E
0x180006ba6  mov     r9, rax
0x180006ba9  xor     r8d, r8d
0x180006bac  mov     rdx, r12
0x180006baf  mov     ecx, r15d
0x180006bb2  call    FwConfig2Str
0x180006bb7  test    eax, eax
0x180006bb9  jns     loc_180007152
0x180006bbf  mov     rcx, cs:WPP_GLOBAL_Control
0x180006bc6  lea     rdx, WPP_GLOBAL_Control
0x180006bcd  cmp     rcx, rdx
0x180006bd0  jz      short loc_180006BF0
0x180006bd2  test    [rcx+1Ch], dil
0x180006bd6  jz      short loc_180006BF0
0x180006bd8  mov     rcx, [rcx+10h]
0x180006bdc  lea     r8, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids
0x180006be3  mov     edx, 0A6h
0x180006be8  mov     r9d, eax
0x180006beb  call    WPP_SF_d
0x180006bf0  mov     esi, [rbp+47h+var_80]
0x180006bf3  cmp     r15d, edi
0x180006bf6  jnz     loc_180006D1C
0x180006bfc  test    r12, r12
0x180006bff  jz      short loc_180006C05
0x180006c01  mov     edi, [r12]
0x180006c05  mov     r8, [rbp+47h+var_68]
0x180006c09  xor     ecx, ecx
0x180006c0b  test    edi, edi
0x180006c0d  mov     edx, esi
0x180006c0f  setnz   cl
0x180006c12  call    FwSvcTelemeterFwStateChange
0x180006c17  jmp     loc_180006D1C
0x180006c1c  mov     edx, r15d
0x180006c1f  sub     edx, 0Ah
0x180006c22  jz      short loc_180006C4D
0x180006c24  sub     edx, edi
0x180006c26  jz      short loc_180006C4D
0x180006c28  sub     edx, edi
0x180006c2a  jz      short loc_180006C4D
0x180006c2c  sub     edx, edi
0x180006c2e  jz      short loc_180006C4D
0x180006c30  sub     edx, edi
0x180006c32  jz      short loc_180006C4D
0x180006c34  sub     edx, 2
0x180006c37  jz      loc_180006E33
0x180006c3d  sub     edx, edi
0x180006c3f  jz      loc_180006E33
0x180006c45  cmp     edx, edi
0x180006c47  jnz     loc_180006AFA
0x180006c4d  cmp     r13d, 4
0x180006c51  jz      loc_180006AFA
0x180006c57  mov     r9d, 80070057h
0x180006c5d  mov     ebx, r9d
0x180006c60  cmp     rcx, r8
0x180006c63  jz      loc_180006D15
0x180006c69  test    [rcx+1Ch], dil
0x180006c6d  jz      loc_180006D15
0x180006c73  mov     edx, 9Ah
0x180006c78  jmp     loc_180006D05
0x180006c7d  cmp     r13d, 4
0x180006c81  jnz     loc_180007003
0x180006c87  mov     eax, [r12]
0x180006c8b  sub     eax, edi
0x180006c8d  cmp     eax, 7FFEh
0x180006c92  jbe     loc_180006AFA
0x180006c98  mov     r9d, 80070057h
0x180006c9e  mov     ebx, r9d
0x180006ca1  cmp     rcx, r8
0x180006ca4  jz      short loc_180006D15
0x180006ca6  test    [rcx+1Ch], dil
0x180006caa  jz      short loc_180006D15
0x180006cac  mov     edx, 9Ch
0x180006cb1  jmp     short loc_180006D05
0x180006cb3  lea     rdx, Control; "/*?\"<>|"
0x180006cba  mov     rcx, r12; String
0x180006cbd  call    cs:__imp_wcspbrk
0x180006cc4  nop     dword ptr [rax+rax+00h]
0x180006cc9  test    rax, rax
0x180006ccc  jnz     loc_180007029
0x180006cd2  mov     rcx, r12
0x180006cd5  call    FwLoggerCreateLogFilesAsCaller
0x180006cda  mov     ebx, eax
0x180006cdc  test    eax, eax
0x180006cde  jns     loc_180006AFA
0x180006ce4  mov     rcx, cs:WPP_GLOBAL_Control
0x180006ceb  lea     rax, WPP_GLOBAL_Control
0x180006cf2  cmp     rcx, rax
0x180006cf5  jz      short loc_180006D15
0x180006cf7  test    [rcx+1Ch], dil
0x180006cfb  jz      short loc_180006D15
0x180006cfd  mov     edx, 0A0h
0x180006d02  mov     r9d, ebx
0x180006d05  mov     rcx, [rcx+10h]
0x180006d09  lea     r8, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids
0x180006d10  call    WPP_SF_d
0x180006d15  mov     esi, [rbp+47h+var_80]
0x180006d18  mov     r14, [rbp+47h+var_78]
0x180006d1c  mov     rcx, [rbp+47h+BindingHandle]; void *
0x180006d20  lea     rdx, aSvrimplFwsetco; "SvrImpl_FWSetConfig"
0x180006d27  call    FwUnlockInternal
0x180006d2c  lea     rcx, aSvrimplFwsetco; "SvrImpl_FWSetConfig"
0x180006d33  call    FwReleaseRPCSharedLock
0x180006d38  test    ebx, ebx
0x180006d3a  js      short loc_180006D48
0x180006d3c  call    cs:__imp_FwChangeSourceSignal
0x180006d43  nop     dword ptr [rax+rax+00h]
0x180006d48  mov     ecx, ebx
0x180006d4a  call    cs:__imp_FwHResultToWindowsError
0x180006d51  nop     dword ptr [rax+rax+00h]
0x180006d56  test    r14, r14
0x180006d59  lea     rdi, qword_1800FBFF0
0x180006d60  mov     rdx, rdi
0x180006d63  mov     rcx, r12
0x180006d66  cmovnz  rdx, r14
0x180006d6a  mov     r10, rdi
0x180006d6d  neg     rcx
0x180006d70  mov     rcx, [rbp+47h+var_68]
0x180006d74  sbb     r8d, r8d
0x180006d77  and     r8d, r13d
0x180006d7a  test    rcx, rcx
0x180006d7d  cmovnz  r10, rcx
0x180006d81  mov     rcx, [rbp+47h+var_60]
0x180006d85  test    rcx, rcx
0x180006d88  jz      loc_180006E27
0x180006d8e  mov     rcx, [rcx]
0x180006d91  mov     [rsp+0D0h+var_90], eax
0x180006d95  mov     r9d, r15d
0x180006d98  mov     [rsp+0D0h+var_A0], rdx
0x180006d9d  mov     rdx, r10
0x180006da0  mov     [rsp+0D0h+var_A8], r12
0x180006da5  mov     dword ptr [rsp+0D0h+var_B0], r8d
0x180006daa  mov     r8d, esi
0x180006dad  call    FwEventProfileConfigurationChanged
0x180006db2  mov     rax, cs:WPP_GLOBAL_Control
0x180006db9  lea     rcx, WPP_GLOBAL_Control
0x180006dc0  cmp     rax, rcx
0x180006dc3  jnz     loc_180006E63
0x180006dc9  mov     rcx, r14
0x180006dcc  call    cs:__imp_FwFree
0x180006dd3  nop     dword ptr [rax+rax+00h]
0x180006dd8  mov     rcx, [rbp+47h+var_68]
  ... truncated ...
```
