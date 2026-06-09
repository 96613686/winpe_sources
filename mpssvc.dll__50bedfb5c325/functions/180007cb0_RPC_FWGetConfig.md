# RPC_FWGetConfig

- ea: `0x180007cb0`
- end: `0x180008164`
- name: `RPC_FWGetConfig`
- size: `1204`
- prototype: `__int64 __usercall@<rax>(RPC_BINDING_HANDLE BindingHandle@<rcx>, int, __int64, int, __int64, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180007cb0`
- `0x180008170`
- `0x1800089bc`
- `0x18000a710`
- `0x18006a710`
- `0x1800729c0`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180007d1c`
- `ntdll!EtwEventWrite` at `0x180007eed`
- `ntdll!EtwEventWrite` at `0x180007d1c`
- `ntdll!EtwEventWrite` at `0x180007eed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180007d7c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180007d7c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180007d96`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180007d96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000802a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000807c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000802a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000807c`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180007e35`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180007e35`
- `RPCRT4!RpcImpersonateClient` at `0x180007d66`
- `RPCRT4!RpcImpersonateClient` at `0x180007d66`
- `RPCRT4!RpcRevertToSelf` at `0x180007dbe`
- `RPCRT4!RpcRevertToSelf` at `0x180007dbe`
- `bcrypt!BCryptGetFipsAlgorithmMode` at `0x180007d38`
- `bcrypt!BCryptGetFipsAlgorithmMode` at `0x180007d38`
- `fwbase!FwHResultToWindowsError` at `0x180007ec6`
- `fwbase!FwHResultToWindowsError` at `0x180007ec6`
- `fwbase!FwCloseHandle` at `0x180007e51`
- `fwbase!FwCloseHandle` at `0x180007e51`

## string_xrefs

- `0x1800080e6`: `mpssvc.dll`

## pseudocode

```c
__int64 __fastcall RPC_FWGetConfig(
        RPC_BINDING_HANDLE BindingHandle,
        __int64 a2,
        unsigned int a3,
        unsigned int a4,
        int a5,
        __int64 a6,
        unsigned int a7,
        unsigned int *a8,
        unsigned int *a9)
{
  PSECURITY_DESCRIPTOR v10; // rsi
  void *v11; // r15
  RPC_STATUS v12; // eax
  signed int v13; // ebx
  HANDLE CurrentThread; // rax
  unsigned int v15; // eax
  __int64 v16; // rcx
  WINBOOL v17; // esi
  unsigned int v18; // eax
  bool v19; // sf
  unsigned int v20; // ebx
  __int64 v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // rdx
  signed int LastError; // eax
  signed int v26; // eax
  __int64 v27; // rdx
  void *TokenHandle; // [rsp+60h] [rbp-49h] BYREF
  BOOLEAN pfEnabled[4]; // [rsp+68h] [rbp-41h] BYREF
  unsigned int v34; // [rsp+6Ch] [rbp-3Dh] BYREF
  WINBOOL AccessStatus; // [rsp+70h] [rbp-39h] BYREF
  DWORD GrantedAccess; // [rsp+74h] [rbp-35h] BYREF
  DWORD PrivilegeSetLength; // [rsp+78h] [rbp-31h] BYREF
  struct _PRIVILEGE_SET PrivilegeSet; // [rsp+80h] [rbp-29h] BYREF
  struct _GENERIC_MAPPING GenericMapping; // [rsp+98h] [rbp-11h] BYREF

  v34 = a7;
  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_SVC_API_Enter_GetConfig, 0, 0);
  *a8 = 0;
  *a9 = 0;
  pfEnabled[0] = 0;
  if ( BCryptGetFipsAlgorithmMode(pfEnabled) < 0 || (v10 = pSecurityDescriptor, !pfEnabled[0]) )
    v10 = (PSECURITY_DESCRIPTOR)qword_180132A18;
  TokenHandle = 0;
  v11 = 0;
  v12 = RpcImpersonateClient(BindingHandle);
  v13 = v12;
  if ( !v12 )
  {
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    {
      v11 = TokenHandle;
      if ( !TokenHandle )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs();
        v11 = TokenHandle;
      }
    }
    else
    {
      LastError = GetLastError();
      v13 = LastError;
      if ( LastError > 0 )
        v13 = (unsigned __int16)LastError | 0x80070000;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          35,
          WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids,
          (unsigned int)v13);
    }
    v15 = RpcRevertToSelf();
    if ( v15 )
      MicrosoftTelemetryAssertTriggeredArgs("mpssvc.dll", v15, 0);
    goto LABEL_12;
  }
  if ( v12 > 0 )
    v13 = (unsigned __int16)v12 | 0x80070000;
  v16 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    WPP_SF_d(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      34,
      WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids,
      (unsigned int)v13);
LABEL_12:
    v16 = WPP_GLOBAL_Control;
  }
  if ( v13 < 0 )
  {
    v17 = 0;
    if ( (_UNKNOWN *)v16 != &WPP_GLOBAL_Control && (*(_BYTE *)(v16 + 28) & 1) != 0 )
    {
      v24 = 36;
      goto LABEL_44;
    }
  }
  else
  {
    PrivilegeSetLength = 20;
    GrantedAccess = 0;
    AccessStatus = 0;
    GenericMapping = 0;
    memset(&PrivilegeSet, 0, sizeof(PrivilegeSet));
    if ( AccessCheck(
           v10,
           v11,
           0x20000u,
           &GenericMapping,
           &PrivilegeSet,
           &PrivilegeSetLength,
           &GrantedAccess,
           &AccessStatus) )
    {
      v17 = AccessStatus;
      v13 = 0;
      goto LABEL_16;
    }
    v26 = GetLastError();
    v13 = v26;
    if ( v26 > 0 )
      v13 = (unsigned __int16)v26 | 0x80070000;
    v16 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        38,
        WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids,
        (unsigned int)v13);
      v16 = WPP_GLOBAL_Control;
    }
    v17 = 0;
    if ( v13 < 0 && (_UNKNOWN *)v16 != &WPP_GLOBAL_Control && (*(_BYTE *)(v16 + 28) & 1) != 0 )
    {
      v24 = 37;
LABEL_44:
      WPP_SF_d(*(_QWORD *)(v16 + 16), v24, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids, (unsigned int)v13);
    }
  }
LABEL_16:
  FwCloseHandle(v11);
  if ( v13 < 0 )
  {
    v22 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_24;
    if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_29;
    v27 = 16;
    goto LABEL_67;
  }
  if ( v17 )
  {
    v13 = SvrImpl_FWGetConfig2_10(BindingHandle, a2, a3, a4, a5, a6, &v34);
    if ( v13 )
    {
      *a8 = 0;
      if ( v13 == 234 )
      {
        *a9 = v34;
      }
      else
      {
        v19 = v13 < 0;
        if ( v13 <= 0 )
          goto LABEL_23;
      }
      v13 = (unsigned __int16)v13 | 0x80070000;
    }
    else
    {
      v18 = v34;
      if ( v34 > a7 )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs();
        v18 = v34;
      }
      *a8 = v18;
    }
    v19 = v13 < 0;
LABEL_23:
    if ( v19 )
    {
      v22 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v23 = 50;
        goto LABEL_35;
      }
    }
    goto LABEL_24;
  }
  v13 = -2147024891;
  v22 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    goto LABEL_24;
  if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    v27 = 17;
LABEL_67:
    WPP_SF_d(*(_QWORD *)(v22 + 16), v27, WPP_bc95a2d00ecc337a62d9dd8dc7f02b78_Traceguids, (unsigned int)v13);
    v22 = WPP_GLOBAL_Control;
  }
LABEL_29:
  if ( (_UNKNOWN *)v22 != &WPP_GLOBAL_Control && (*(_BYTE *)(v22 + 28) & 1) != 0 )
  {
    v23 = 49;
LABEL_35:
    WPP_SF_d(*(_QWORD *)(v22 + 16), v23, WPP_bc95a2d00ecc337a62d9dd8dc7f02b78_Traceguids, (unsigned int)v13);
  }
LABEL_24:
  v20 = FwHResultToWindowsError((unsigned int)v13);
  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_SVC_API_Exit_GetConfig, 0, 0);
  return v20;
}

```

## disassembly

```asm
0x180007cb0  push    rbp
0x180007cb2  push    rbx
0x180007cb3  push    rsi
0x180007cb4  push    rdi
0x180007cb5  push    r12
0x180007cb7  push    r13
0x180007cb9  push    r15
0x180007cbb  lea     rbp, [rsp-7]
0x180007cc0  sub     rsp, 0B0h
0x180007cc7  mov     rax, cs:__security_cookie
0x180007cce  xor     rax, rsp
0x180007cd1  mov     [rbp+37h+var_38], rax
0x180007cd5  mov     rax, [rbp+37h+arg_28]
0x180007cd9  mov     rbx, rcx
0x180007cdc  mov     r12, [rbp+37h+arg_38]
0x180007ce0  xor     edi, edi
0x180007ce2  mov     r13, [rbp+37h+arg_40]
0x180007ce9  mov     [rbp+37h+var_88], rcx
0x180007ced  mov     rcx, cs:g_Provider
0x180007cf4  mov     [rbp+37h+var_98], rax
0x180007cf8  mov     eax, [rbp+37h+arg_30]
0x180007cfb  mov     [rbp+37h+var_74], eax
0x180007cfe  mov     [rbp+37h+var_A0], r9d
0x180007d02  mov     [rbp+37h+var_9C], r8d
0x180007d06  mov     [rbp+37h+var_90], rdx
0x180007d0a  test    rcx, rcx
0x180007d0d  jz      short loc_180007D28
0x180007d0f  xor     r9d, r9d
0x180007d12  lea     rdx, MPS_SVC_API_Enter_GetConfig
0x180007d19  xor     r8d, r8d
0x180007d1c  call    cs:__imp_EtwEventWrite
0x180007d23  nop     dword ptr [rax+rax+00h]
0x180007d28  mov     [r12], edi
0x180007d2c  lea     rcx, [rbp+37h+pfEnabled]; pfEnabled
0x180007d30  mov     [r13+0], edi
0x180007d34  mov     [rbp+37h+pfEnabled], dil
0x180007d38  call    cs:__imp_BCryptGetFipsAlgorithmMode
0x180007d3f  nop     dword ptr [rax+rax+00h]
0x180007d44  test    eax, eax
0x180007d46  js      short loc_180007D55
0x180007d48  mov     rsi, cs:pSecurityDescriptor
0x180007d4f  cmp     [rbp+37h+pfEnabled], dil
0x180007d53  jnz     short loc_180007D5C
0x180007d55  mov     rsi, cs:qword_180132A18
0x180007d5c  mov     rcx, rbx; BindingHandle
0x180007d5f  mov     [rbp+37h+TokenHandle], rdi
0x180007d63  mov     r15, rdi
0x180007d66  call    cs:__imp_RpcImpersonateClient
0x180007d6d  nop     dword ptr [rax+rax+00h]
0x180007d72  mov     ebx, eax
0x180007d74  test    eax, eax
0x180007d76  jnz     loc_180007FE1
0x180007d7c  call    cs:__imp_GetCurrentThread
0x180007d83  nop     dword ptr [rax+rax+00h]
0x180007d88  mov     rcx, rax; ThreadHandle
0x180007d8b  lea     r9, [rbp+37h+TokenHandle]; TokenHandle
0x180007d8f  lea     edx, [rbx+8]; DesiredAccess
0x180007d92  lea     r8d, [rbx+1]; OpenAsSelf
0x180007d96  call    cs:__imp_OpenThreadToken
0x180007d9d  nop     dword ptr [rax+rax+00h]
0x180007da2  lea     rdi, WPP_GLOBAL_Control
0x180007da9  test    eax, eax
0x180007dab  jz      loc_18000802A
0x180007db1  mov     r15, [rbp+37h+TokenHandle]
0x180007db5  test    r15, r15
0x180007db8  jz      loc_1800080D5
0x180007dbe  call    cs:__imp_RpcRevertToSelf
0x180007dc5  nop     dword ptr [rax+rax+00h]
0x180007dca  test    eax, eax
0x180007dcc  jnz     loc_1800080E3
0x180007dd2  mov     rcx, cs:WPP_GLOBAL_Control
0x180007dd9  test    ebx, ebx
0x180007ddb  js      loc_1800080F9
0x180007de1  xor     eax, eax
0x180007de3  mov     [rbp+37h+var_68], 14h
0x180007dea  mov     [rbp+37h+var_60.Privilege.Attributes], eax
0x180007ded  lea     r9, [rbp+37h+GenericMapping]; GenericMapping
0x180007df1  mov     [rbp+37h+var_6C], eax
0x180007df4  xorps   xmm0, xmm0
0x180007df7  mov     [rbp+37h+var_70], eax
0x180007dfa  xorps   xmm1, xmm1
0x180007dfd  lea     rax, [rbp+37h+var_70]
0x180007e01  mov     r8d, 20000h; DesiredAccess
0x180007e07  mov     [rsp+0E0h+AccessStatus], rax; AccessStatus
0x180007e0c  mov     rdx, r15; ClientToken
0x180007e0f  lea     rax, [rbp+37h+var_6C]
0x180007e13  mov     rcx, rsi; pSecurityDescriptor
0x180007e16  mov     [rsp+0E0h+GrantedAccess], rax; GrantedAccess
0x180007e1b  lea     rax, [rbp+37h+var_68]
0x180007e1f  mov     [rsp+0E0h+PrivilegeSetLength], rax; PrivilegeSetLength
0x180007e24  lea     rax, [rbp+37h+var_60]
0x180007e28  mov     [rsp+0E0h+PrivilegeSet], rax; PrivilegeSet
0x180007e2d  movups  xmmword ptr [rbp+37h+GenericMapping.GenericRead], xmm0
0x180007e31  movups  xmmword ptr [rbp+37h+var_60.PrivilegeCount], xmm1
0x180007e35  call    cs:__imp_AccessCheck
0x180007e3c  nop     dword ptr [rax+rax+00h]
0x180007e41  test    eax, eax
0x180007e43  jz      loc_18000807C
0x180007e49  mov     esi, [rbp+37h+var_70]
0x180007e4c  xor     ebx, ebx
0x180007e4e  mov     rcx, r15
0x180007e51  call    cs:__imp_FwCloseHandle
0x180007e58  nop     dword ptr [rax+rax+00h]
0x180007e5d  lea     r15, WPP_bc95a2d00ecc337a62d9dd8dc7f02b78_Traceguids
0x180007e64  test    ebx, ebx
0x180007e66  js      loc_180008116
0x180007e6c  test    esi, esi
0x180007e6e  jz      loc_180007F1A
0x180007e74  mov     r9d, [rbp+37h+var_A0]
0x180007e78  lea     rax, [rbp+37h+var_74]
0x180007e7c  mov     r8d, [rbp+37h+var_9C]
0x180007e80  mov     rdx, [rbp+37h+var_90]
0x180007e84  mov     rcx, [rbp+37h+var_88]
0x180007e88  mov     [rsp+0E0h+GrantedAccess], rax
0x180007e8d  mov     rax, [rbp+37h+var_98]
0x180007e91  mov     [rsp+0E0h+PrivilegeSetLength], rax
0x180007e96  mov     eax, [rbp+37h+arg_20]
0x180007e99  mov     dword ptr [rsp+0E0h+PrivilegeSet], eax
0x180007e9d  call    ?SvrImpl_FWGetConfig2_10@@YAKPEAX0W4_tag_FW_PROFILE_CONFIG@@W4_tag_FW_PROFILE_TYPE@@KPEAEPEAKPEAW4_tag_FW_RULE_ORIGIN_TYPE@@@Z; SvrImpl_FWGetConfig2_10(void *,void *,_tag_FW_PROFILE_CONFIG,_tag_FW_PROFILE_TYPE,ulong,uchar *,ulong *,_tag_FW_RULE_ORIGIN_TYPE *)
0x180007ea2  mov     ebx, eax
0x180007ea4  test    eax, eax
0x180007ea6  jnz     loc_180007F7A
0x180007eac  mov     eax, [rbp+37h+var_74]
0x180007eaf  cmp     eax, [rbp+37h+arg_30]
0x180007eb2  ja      loc_180008157
0x180007eb8  mov     [r12], eax
0x180007ebc  test    ebx, ebx
0x180007ebe  js      loc_180007F47
0x180007ec4  mov     ecx, ebx
0x180007ec6  call    cs:__imp_FwHResultToWindowsError
0x180007ecd  nop     dword ptr [rax+rax+00h]
0x180007ed2  mov     rcx, cs:g_Provider
0x180007ed9  mov     ebx, eax
0x180007edb  test    rcx, rcx
0x180007ede  jz      short loc_180007EF9
0x180007ee0  xor     r9d, r9d
0x180007ee3  lea     rdx, MPS_SVC_API_Exit_GetConfig
0x180007eea  xor     r8d, r8d
0x180007eed  call    cs:__imp_EtwEventWrite
0x180007ef4  nop     dword ptr [rax+rax+00h]
0x180007ef9  mov     eax, ebx
0x180007efb  mov     rcx, [rbp+37h+var_38]
0x180007eff  xor     rcx, rsp; StackCookie
0x180007f02  call    __security_check_cookie
0x180007f07  add     rsp, 0B0h
0x180007f0e  pop     r15
0x180007f10  pop     r13
0x180007f12  pop     r12
0x180007f14  pop     rdi
0x180007f15  pop     rsi
0x180007f16  pop     rbx
0x180007f17  pop     rbp
0x180007f18  retn
0x180007f1a  mov     ebx, 80070005h
0x180007f1f  mov     rcx, cs:WPP_GLOBAL_Control
0x180007f26  cmp     rcx, rdi
0x180007f29  jz      short loc_180007EC4
0x180007f2b  test    byte ptr [rcx+1Ch], 1
0x180007f2f  jnz     loc_180008137
0x180007f35  cmp     rcx, rdi
0x180007f38  jz      short loc_180007EC4
0x180007f3a  test    byte ptr [rcx+1Ch], 1
0x180007f3e  jz      short loc_180007EC4
0x180007f40  mov     edx, 31h ; '1'
0x180007f45  jmp     short loc_180007F66
0x180007f47  mov     rcx, cs:WPP_GLOBAL_Control
0x180007f4e  cmp     rcx, rdi
0x180007f51  jz      loc_180007EC4
0x180007f57  test    byte ptr [rcx+1Ch], 1
0x180007f5b  jz      loc_180007EC4
0x180007f61  mov     edx, 32h ; '2'
0x180007f66  mov     rcx, [rcx+10h]
0x180007f6a  mov     r9d, ebx
0x180007f6d  mov     r8, r15
0x180007f70  call    WPP_SF_d
0x180007f75  jmp     loc_180007EC4
0x180007f7a  mov     dword ptr [r12], 0
0x180007f82  cmp     ebx, 0EAh
0x180007f88  jnz     short loc_180007F93
0x180007f8a  mov     eax, [rbp+37h+var_74]
0x180007f8d  mov     [r13+0], eax
0x180007f91  jmp     short loc_180007F9B
0x180007f93  test    ebx, ebx
0x180007f95  jle     loc_180007EBE
0x180007f9b  movzx   ebx, bx
0x180007f9e  or      ebx, 80070000h
0x180007fa4  jmp     loc_180007EBC
0x180007fa9  xor     esi, esi
0x180007fab  test    ebx, ebx
0x180007fad  jns     loc_180007E4E
0x180007fb3  cmp     rcx, rdi
0x180007fb6  jz      loc_180007E4E
0x180007fbc  test    byte ptr [rcx+1Ch], 1
0x180007fc0  jz      loc_180007E4E
0x180007fc6  lea     edx, [rsi+25h]
0x180007fc9  mov     rcx, [rcx+10h]
0x180007fcd  lea     r8, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids
0x180007fd4  mov     r9d, ebx
0x180007fd7  call    WPP_SF_d
0x180007fdc  jmp     loc_180007E4E
0x180007fe1  jle     short loc_180007FEC
0x180007fe3  movzx   ebx, ax
0x180007fe6  or      ebx, 80070000h
0x180007fec  mov     rcx, cs:WPP_GLOBAL_Control
0x180007ff3  lea     rdi, WPP_GLOBAL_Control
0x180007ffa  cmp     rcx, rdi
0x180007ffd  jz      loc_180007DD9
0x180008003  test    byte ptr [rcx+1Ch], 1
0x180008007  jz      loc_180007DD9
0x18000800d  mov     rcx, [rcx+10h]
0x180008011  lea     r8, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids
0x180008018  mov     edx, 22h ; '"'
0x18000801d  mov     r9d, ebx
0x180008020  call    WPP_SF_d
0x180008025  jmp     loc_180007DD2
0x18000802a  call    cs:__imp_GetLastError
0x180008031  nop     dword ptr [rax+rax+00h]
0x180008036  mov     ebx, eax
0x180008038  test    eax, eax
0x18000803a  jle     short loc_180008045
0x18000803c  movzx   ebx, ax
0x18000803f  or      ebx, 80070000h
0x180008045  mov     rcx, cs:WPP_GLOBAL_Control
0x18000804c  cmp     rcx, rdi
0x18000804f  jz      loc_180007DBE
0x180008055  test    byte ptr [rcx+1Ch], 1
0x180008059  jz      loc_180007DBE
0x18000805f  mov     rcx, [rcx+10h]
0x180008063  lea     r8, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids
0x18000806a  mov     edx, 23h ; '#'
0x18000806f  mov     r9d, ebx
0x180008072  call    WPP_SF_d
0x180008077  jmp     loc_180007DBE
0x18000807c  call    cs:__imp_GetLastError
0x180008083  nop     dword ptr [rax+rax+00h]
0x180008088  mov     ebx, eax
0x18000808a  test    eax, eax
0x18000808c  jle     short loc_180008097
0x18000808e  movzx   ebx, ax
0x180008091  or      ebx, 80070000h
0x180008097  mov     rcx, cs:WPP_GLOBAL_Control
0x18000809e  cmp     rcx, rdi
0x1800080a1  jz      loc_180007FA9
0x1800080a7  test    byte ptr [rcx+1Ch], 1
0x1800080ab  jz      loc_180007FA9
0x1800080b1  mov     rcx, [rcx+10h]
0x1800080b5  lea     r8, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids
0x1800080bc  mov     edx, 26h ; '&'
0x1800080c1  mov     r9d, ebx
0x1800080c4  call    WPP_SF_d
0x1800080c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800080d0  jmp     loc_180007FA9
0x1800080d5  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "localToken != NULL")
0x1800080da  mov     r15, [rbp+37h+TokenHandle]
0x1800080de  jmp     loc_180007DBE
0x1800080e3  xor     r8d, r8d; __annotation("Debug", "TelemetryAssert", "status == RPC_S_OK", "RpcRevertToSelf")
0x1800080e6  lea     rcx, aMpssvcDll_1; "mpssvc.dll"
0x1800080ed  mov     edx, eax
0x1800080ef  call    MicrosoftTelemetryAssertTriggeredArgs
0x1800080f4  jmp     loc_180007DD2
0x1800080f9  xor     esi, esi
0x1800080fb  cmp     rcx, rdi
0x1800080fe  jz      loc_180007E4E
0x180008104  test    byte ptr [rcx+1Ch], 1
0x180008108  jz      loc_180007E4E
0x18000810e  lea     edx, [rsi+24h]
0x180008111  jmp     loc_180007FC9
0x180008116  mov     rcx, cs:WPP_GLOBAL_Control
0x18000811d  cmp     rcx, rdi
0x180008120  jz      loc_180007EC4
0x180008126  test    byte ptr [rcx+1Ch], 1
0x18000812a  jz      loc_180007F35
0x180008130  mov     edx, 10h
0x180008135  jmp     short loc_18000813C
0x180008137  mov     edx, 11h
0x18000813c  mov     rcx, [rcx+10h]
0x180008140  mov     r9d, ebx
0x180008143  mov     r8, r15
0x180008146  call    WPP_SF_d
0x18000814b  mov     rcx, cs:WPP_GLOBAL_Control
0x180008152  jmp     loc_180007F35
0x180008157  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "dwBufSize <= cbData")
0x18000815c  mov     eax, [rbp+37h+var_74]
0x18000815f  jmp     loc_180007EB8
```
