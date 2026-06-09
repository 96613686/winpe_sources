# RPC_FWGetConfig

- ea: `0x180008750`
- end: `0x180008bb7`
- name: `RPC_FWGetConfig`
- size: `1127`
- prototype: `__int64 __usercall@<rax>(RPC_BINDING_HANDLE BindingHandle@<rcx>, int, __int64, int, __int64, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180008750`
- `0x180008bc0`
- `0x1800093b0`
- `0x18000af3c`
- `0x1800670c0`
- `0x18006f520`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x1800087bc`
- `ntdll!EtwEventWrite` at `0x180008953`
- `ntdll!EtwEventWrite` at `0x1800087bc`
- `ntdll!EtwEventWrite` at `0x180008953`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000881e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000881e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000880a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000880a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008a89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008ad5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008a89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008ad5`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x1800088b1`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x1800088b1`
- `RPCRT4!RpcRevertToSelf` at `0x180008840`
- `RPCRT4!RpcRevertToSelf` at `0x180008840`
- `RPCRT4!RpcImpersonateClient` at `0x1800087fa`
- `RPCRT4!RpcImpersonateClient` at `0x1800087fa`
- `bcrypt!BCryptGetFipsAlgorithmMode` at `0x1800087d2`
- `bcrypt!BCryptGetFipsAlgorithmMode` at `0x1800087d2`
- `fwbase!FwHResultToWindowsError` at `0x180008932`
- `fwbase!FwHResultToWindowsError` at `0x180008932`
- `fwbase!FwCloseHandle` at `0x1800088c7`
- `fwbase!FwCloseHandle` at `0x1800088c7`

## string_xrefs

- `0x180008b39`: `mpssvc.dll`

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
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // r8
  __int64 v18; // r9
  unsigned int v19; // eax
  __int64 v20; // rcx
  WINBOOL v21; // esi
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // r8
  __int64 v25; // r9
  unsigned int v26; // eax
  bool v27; // sf
  unsigned int v28; // ebx
  __int64 v30; // rcx
  __int64 v31; // rdx
  __int64 v32; // rdx
  signed int LastError; // eax
  signed int v34; // eax
  __int64 v35; // rdx
  void *TokenHandle; // [rsp+60h] [rbp-49h] BYREF
  BOOLEAN pfEnabled[4]; // [rsp+68h] [rbp-41h] BYREF
  unsigned int v42; // [rsp+6Ch] [rbp-3Dh] BYREF
  WINBOOL AccessStatus; // [rsp+70h] [rbp-39h] BYREF
  DWORD GrantedAccess; // [rsp+74h] [rbp-35h] BYREF
  DWORD PrivilegeSetLength; // [rsp+78h] [rbp-31h] BYREF
  struct _PRIVILEGE_SET PrivilegeSet; // [rsp+80h] [rbp-29h] BYREF
  struct _GENERIC_MAPPING GenericMapping; // [rsp+98h] [rbp-11h] BYREF

  v42 = a7;
  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_SVC_API_Enter_GetConfig, 0, 0);
  *a8 = 0;
  *a9 = 0;
  pfEnabled[0] = 0;
  if ( BCryptGetFipsAlgorithmMode(pfEnabled) < 0 || (v10 = pSecurityDescriptor, !pfEnabled[0]) )
    v10 = (PSECURITY_DESCRIPTOR)qword_18012C848[0];
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
        MicrosoftTelemetryAssertTriggeredNoArgs(v16, v15, v17, v18);
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
    v19 = RpcRevertToSelf();
    if ( v19 )
      MicrosoftTelemetryAssertTriggeredArgs("mpssvc.dll", v19, 0);
    goto LABEL_12;
  }
  if ( v12 > 0 )
    v13 = (unsigned __int16)v12 | 0x80070000;
  v20 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    WPP_SF_d(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      34,
      WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids,
      (unsigned int)v13);
LABEL_12:
    v20 = WPP_GLOBAL_Control;
  }
  if ( v13 < 0 )
  {
    v21 = 0;
    if ( (_UNKNOWN *)v20 != &WPP_GLOBAL_Control && (*(_BYTE *)(v20 + 28) & 1) != 0 )
    {
      v32 = 36;
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
      v21 = AccessStatus;
      v13 = 0;
      goto LABEL_16;
    }
    v34 = GetLastError();
    v13 = v34;
    if ( v34 > 0 )
      v13 = (unsigned __int16)v34 | 0x80070000;
    v20 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        38,
        WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids,
        (unsigned int)v13);
      v20 = WPP_GLOBAL_Control;
    }
    v21 = 0;
    if ( v13 < 0 && (_UNKNOWN *)v20 != &WPP_GLOBAL_Control && (*(_BYTE *)(v20 + 28) & 1) != 0 )
    {
      v32 = 37;
LABEL_44:
      WPP_SF_d(*(_QWORD *)(v20 + 16), v32, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids, (unsigned int)v13);
    }
  }
LABEL_16:
  FwCloseHandle(v11);
  if ( v13 < 0 )
  {
    v30 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_24;
    if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_29;
    v35 = 16;
    goto LABEL_67;
  }
  if ( v21 )
  {
    v13 = SvrImpl_FWGetConfig2_10(BindingHandle, a2, a3, a4, a5, a6, &v42);
    if ( v13 )
    {
      *a8 = 0;
      if ( v13 == 234 )
      {
        *a9 = v42;
      }
      else
      {
        v27 = v13 < 0;
        if ( v13 <= 0 )
          goto LABEL_23;
      }
      v13 = (unsigned __int16)v13 | 0x80070000;
    }
    else
    {
      v26 = v42;
      if ( v42 > a7 )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs(v23, v22, v24, v25);
        v26 = v42;
      }
      *a8 = v26;
    }
    v27 = v13 < 0;
LABEL_23:
    if ( v27 )
    {
      v30 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v31 = 50;
        goto LABEL_35;
      }
    }
    goto LABEL_24;
  }
  v13 = -2147024891;
  v30 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    goto LABEL_24;
  if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    v35 = 17;
LABEL_67:
    WPP_SF_d(*(_QWORD *)(v30 + 16), v35, WPP_bc95a2d00ecc337a62d9dd8dc7f02b78_Traceguids, (unsigned int)v13);
    v30 = WPP_GLOBAL_Control;
  }
LABEL_29:
  if ( (_UNKNOWN *)v30 != &WPP_GLOBAL_Control && (*(_BYTE *)(v30 + 28) & 1) != 0 )
  {
    v31 = 49;
LABEL_35:
    WPP_SF_d(*(_QWORD *)(v30 + 16), v31, WPP_bc95a2d00ecc337a62d9dd8dc7f02b78_Traceguids, (unsigned int)v13);
  }
LABEL_24:
  v28 = FwHResultToWindowsError((unsigned int)v13);
  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_SVC_API_Exit_GetConfig, 0, 0);
  return v28;
}

```

## disassembly

```asm
0x180008750  push    rbp
0x180008752  push    rbx
0x180008753  push    rsi
0x180008754  push    rdi
0x180008755  push    r12
0x180008757  push    r13
0x180008759  push    r15
0x18000875b  lea     rbp, [rsp-7]
0x180008760  sub     rsp, 0B0h
0x180008767  mov     rax, cs:__security_cookie
0x18000876e  xor     rax, rsp
0x180008771  mov     [rbp+37h+var_38], rax
0x180008775  mov     rax, [rbp+37h+arg_28]
0x180008779  mov     rbx, rcx
0x18000877c  mov     r12, [rbp+37h+arg_38]
0x180008780  xor     edi, edi
0x180008782  mov     r13, [rbp+37h+arg_40]
0x180008789  mov     [rbp+37h+var_88], rcx
0x18000878d  mov     rcx, cs:g_Provider
0x180008794  mov     [rbp+37h+var_98], rax
0x180008798  mov     eax, [rbp+37h+arg_30]
0x18000879b  mov     [rbp+37h+var_74], eax
0x18000879e  mov     [rbp+37h+var_A0], r9d
0x1800087a2  mov     [rbp+37h+var_9C], r8d
0x1800087a6  mov     [rbp+37h+var_90], rdx
0x1800087aa  test    rcx, rcx
0x1800087ad  jz      short loc_1800087C2
0x1800087af  xor     r9d, r9d
0x1800087b2  lea     rdx, MPS_SVC_API_Enter_GetConfig
0x1800087b9  xor     r8d, r8d
0x1800087bc  call    cs:__imp_EtwEventWrite
0x1800087c2  mov     [r12], edi
0x1800087c6  lea     rcx, [rbp+37h+pfEnabled]; pfEnabled
0x1800087ca  mov     [r13+0], edi
0x1800087ce  mov     [rbp+37h+pfEnabled], dil
0x1800087d2  call    cs:__imp_BCryptGetFipsAlgorithmMode
0x1800087d8  test    eax, eax
0x1800087da  js      short loc_1800087E9
0x1800087dc  mov     rsi, cs:pSecurityDescriptor
0x1800087e3  cmp     [rbp+37h+pfEnabled], dil
0x1800087e7  jnz     short loc_1800087F0
0x1800087e9  mov     rsi, cs:qword_18012C848
0x1800087f0  mov     rcx, rbx; BindingHandle
0x1800087f3  mov     [rbp+37h+TokenHandle], rdi
0x1800087f7  mov     r15, rdi
0x1800087fa  call    cs:__imp_RpcImpersonateClient
0x180008800  mov     ebx, eax
0x180008802  test    eax, eax
0x180008804  jnz     loc_180008A40
0x18000880a  call    cs:__imp_GetCurrentThread
0x180008810  mov     rcx, rax; ThreadHandle
0x180008813  lea     r9, [rbp+37h+TokenHandle]; TokenHandle
0x180008817  lea     edx, [rbx+8]; DesiredAccess
0x18000881a  lea     r8d, [rbx+1]; OpenAsSelf
0x18000881e  call    cs:__imp_OpenThreadToken
0x180008824  lea     rdi, WPP_GLOBAL_Control
0x18000882b  test    eax, eax
0x18000882d  jz      loc_180008A89
0x180008833  mov     r15, [rbp+37h+TokenHandle]
0x180008837  test    r15, r15
0x18000883a  jz      loc_180008B28
0x180008840  call    cs:__imp_RpcRevertToSelf
0x180008846  test    eax, eax
0x180008848  jnz     loc_180008B36
0x18000884e  mov     rcx, cs:WPP_GLOBAL_Control
0x180008855  test    ebx, ebx
0x180008857  js      loc_180008B4C
0x18000885d  xor     eax, eax
0x18000885f  mov     [rbp+37h+var_68], 14h
0x180008866  mov     [rbp+37h+var_60.Privilege.Attributes], eax
0x180008869  lea     r9, [rbp+37h+GenericMapping]; GenericMapping
0x18000886d  mov     [rbp+37h+var_6C], eax
0x180008870  xorps   xmm0, xmm0
0x180008873  mov     [rbp+37h+var_70], eax
0x180008876  xorps   xmm1, xmm1
0x180008879  lea     rax, [rbp+37h+var_70]
0x18000887d  mov     r8d, 20000h; DesiredAccess
0x180008883  mov     [rsp+0E0h+AccessStatus], rax; AccessStatus
0x180008888  mov     rdx, r15; ClientToken
0x18000888b  lea     rax, [rbp+37h+var_6C]
0x18000888f  mov     rcx, rsi; pSecurityDescriptor
0x180008892  mov     [rsp+0E0h+GrantedAccess], rax; GrantedAccess
0x180008897  lea     rax, [rbp+37h+var_68]
0x18000889b  mov     [rsp+0E0h+PrivilegeSetLength], rax; PrivilegeSetLength
0x1800088a0  lea     rax, [rbp+37h+var_60]
0x1800088a4  mov     [rsp+0E0h+PrivilegeSet], rax; PrivilegeSet
0x1800088a9  movups  xmmword ptr [rbp+37h+GenericMapping.GenericRead], xmm0
0x1800088ad  movups  xmmword ptr [rbp+37h+var_60.PrivilegeCount], xmm1
0x1800088b1  call    cs:__imp_AccessCheck
0x1800088b7  test    eax, eax
0x1800088b9  jz      loc_180008AD5
0x1800088bf  mov     esi, [rbp+37h+var_70]
0x1800088c2  xor     ebx, ebx
0x1800088c4  mov     rcx, r15
0x1800088c7  call    cs:__imp_FwCloseHandle
0x1800088cd  lea     r15, WPP_bc95a2d00ecc337a62d9dd8dc7f02b78_Traceguids
0x1800088d4  test    ebx, ebx
0x1800088d6  js      loc_180008B69
0x1800088dc  test    esi, esi
0x1800088de  jz      loc_180008979
0x1800088e4  mov     r9d, [rbp+37h+var_A0]
0x1800088e8  lea     rax, [rbp+37h+var_74]
0x1800088ec  mov     r8d, [rbp+37h+var_9C]
0x1800088f0  mov     rdx, [rbp+37h+var_90]
0x1800088f4  mov     rcx, [rbp+37h+var_88]
0x1800088f8  mov     [rsp+0E0h+GrantedAccess], rax
0x1800088fd  mov     rax, [rbp+37h+var_98]
0x180008901  mov     [rsp+0E0h+PrivilegeSetLength], rax
0x180008906  mov     eax, [rbp+37h+arg_20]
0x180008909  mov     dword ptr [rsp+0E0h+PrivilegeSet], eax
0x18000890d  call    ?SvrImpl_FWGetConfig2_10@@YAKPEAX0W4_tag_FW_PROFILE_CONFIG@@W4_tag_FW_PROFILE_TYPE@@KPEAEPEAKPEAW4_tag_FW_RULE_ORIGIN_TYPE@@@Z; SvrImpl_FWGetConfig2_10(void *,void *,_tag_FW_PROFILE_CONFIG,_tag_FW_PROFILE_TYPE,ulong,uchar *,ulong *,_tag_FW_RULE_ORIGIN_TYPE *)
0x180008912  mov     ebx, eax
0x180008914  test    eax, eax
0x180008916  jnz     loc_1800089D9
0x18000891c  mov     eax, [rbp+37h+var_74]
0x18000891f  cmp     eax, [rbp+37h+arg_30]
0x180008922  ja      loc_180008BAA
0x180008928  mov     [r12], eax
0x18000892c  test    ebx, ebx
0x18000892e  js      short loc_1800089A6
0x180008930  mov     ecx, ebx
0x180008932  call    cs:__imp_FwHResultToWindowsError
0x180008938  mov     rcx, cs:g_Provider
0x18000893f  mov     ebx, eax
0x180008941  test    rcx, rcx
0x180008944  jz      short loc_180008959
0x180008946  xor     r9d, r9d
0x180008949  lea     rdx, MPS_SVC_API_Exit_GetConfig
0x180008950  xor     r8d, r8d
0x180008953  call    cs:__imp_EtwEventWrite
0x180008959  mov     eax, ebx
0x18000895b  mov     rcx, [rbp+37h+var_38]
0x18000895f  xor     rcx, rsp; StackCookie
0x180008962  call    __security_check_cookie
0x180008967  add     rsp, 0B0h
0x18000896e  pop     r15
0x180008970  pop     r13
0x180008972  pop     r12
0x180008974  pop     rdi
0x180008975  pop     rsi
0x180008976  pop     rbx
0x180008977  pop     rbp
0x180008978  retn
0x180008979  mov     ebx, 80070005h
0x18000897e  mov     rcx, cs:WPP_GLOBAL_Control
0x180008985  cmp     rcx, rdi
0x180008988  jz      short loc_180008930
0x18000898a  test    byte ptr [rcx+1Ch], 1
0x18000898e  jnz     loc_180008B8A
0x180008994  cmp     rcx, rdi
0x180008997  jz      short loc_180008930
0x180008999  test    byte ptr [rcx+1Ch], 1
0x18000899d  jz      short loc_180008930
0x18000899f  mov     edx, 31h ; '1'
0x1800089a4  jmp     short loc_1800089C5
0x1800089a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800089ad  cmp     rcx, rdi
0x1800089b0  jz      loc_180008930
0x1800089b6  test    byte ptr [rcx+1Ch], 1
0x1800089ba  jz      loc_180008930
0x1800089c0  mov     edx, 32h ; '2'
0x1800089c5  mov     rcx, [rcx+10h]
0x1800089c9  mov     r9d, ebx
0x1800089cc  mov     r8, r15
0x1800089cf  call    WPP_SF_d
0x1800089d4  jmp     loc_180008930
0x1800089d9  mov     dword ptr [r12], 0
0x1800089e1  cmp     ebx, 0EAh
0x1800089e7  jnz     short loc_1800089F2
0x1800089e9  mov     eax, [rbp+37h+var_74]
0x1800089ec  mov     [r13+0], eax
0x1800089f0  jmp     short loc_1800089FA
0x1800089f2  test    ebx, ebx
0x1800089f4  jle     loc_18000892E
0x1800089fa  movzx   ebx, bx
0x1800089fd  or      ebx, 80070000h
0x180008a03  jmp     loc_18000892C
0x180008a08  xor     esi, esi
0x180008a0a  test    ebx, ebx
0x180008a0c  jns     loc_1800088C4
0x180008a12  cmp     rcx, rdi
0x180008a15  jz      loc_1800088C4
0x180008a1b  test    byte ptr [rcx+1Ch], 1
0x180008a1f  jz      loc_1800088C4
0x180008a25  lea     edx, [rsi+25h]
0x180008a28  mov     rcx, [rcx+10h]
0x180008a2c  lea     r8, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids
0x180008a33  mov     r9d, ebx
0x180008a36  call    WPP_SF_d
0x180008a3b  jmp     loc_1800088C4
0x180008a40  jle     short loc_180008A4B
0x180008a42  movzx   ebx, ax
0x180008a45  or      ebx, 80070000h
0x180008a4b  mov     rcx, cs:WPP_GLOBAL_Control
0x180008a52  lea     rdi, WPP_GLOBAL_Control
0x180008a59  cmp     rcx, rdi
0x180008a5c  jz      loc_180008855
0x180008a62  test    byte ptr [rcx+1Ch], 1
0x180008a66  jz      loc_180008855
0x180008a6c  mov     rcx, [rcx+10h]
0x180008a70  lea     r8, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids
0x180008a77  mov     edx, 22h ; '"'
0x180008a7c  mov     r9d, ebx
0x180008a7f  call    WPP_SF_d
0x180008a84  jmp     loc_18000884E
0x180008a89  call    cs:__imp_GetLastError
0x180008a8f  mov     ebx, eax
0x180008a91  test    eax, eax
0x180008a93  jle     short loc_180008A9E
0x180008a95  movzx   ebx, ax
0x180008a98  or      ebx, 80070000h
0x180008a9e  mov     rcx, cs:WPP_GLOBAL_Control
0x180008aa5  cmp     rcx, rdi
0x180008aa8  jz      loc_180008840
0x180008aae  test    byte ptr [rcx+1Ch], 1
0x180008ab2  jz      loc_180008840
0x180008ab8  mov     rcx, [rcx+10h]
0x180008abc  lea     r8, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids
0x180008ac3  mov     edx, 23h ; '#'
0x180008ac8  mov     r9d, ebx
0x180008acb  call    WPP_SF_d
0x180008ad0  jmp     loc_180008840
0x180008ad5  call    cs:__imp_GetLastError
0x180008adb  mov     ebx, eax
0x180008add  test    eax, eax
0x180008adf  jle     short loc_180008AEA
0x180008ae1  movzx   ebx, ax
0x180008ae4  or      ebx, 80070000h
0x180008aea  mov     rcx, cs:WPP_GLOBAL_Control
0x180008af1  cmp     rcx, rdi
0x180008af4  jz      loc_180008A08
0x180008afa  test    byte ptr [rcx+1Ch], 1
0x180008afe  jz      loc_180008A08
0x180008b04  mov     rcx, [rcx+10h]
0x180008b08  lea     r8, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids
0x180008b0f  mov     edx, 26h ; '&'
0x180008b14  mov     r9d, ebx
0x180008b17  call    WPP_SF_d
0x180008b1c  mov     rcx, cs:WPP_GLOBAL_Control
0x180008b23  jmp     loc_180008A08
0x180008b28  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180008b2d  mov     r15, [rbp+37h+TokenHandle]
0x180008b31  jmp     loc_180008840
0x180008b36  xor     r8d, r8d
0x180008b39  lea     rcx, aMpssvcDll_1; "mpssvc.dll"
0x180008b40  mov     edx, eax
0x180008b42  call    MicrosoftTelemetryAssertTriggeredArgs
0x180008b47  jmp     loc_18000884E
0x180008b4c  xor     esi, esi
0x180008b4e  cmp     rcx, rdi
0x180008b51  jz      loc_1800088C4
0x180008b57  test    byte ptr [rcx+1Ch], 1
0x180008b5b  jz      loc_1800088C4
0x180008b61  lea     edx, [rsi+24h]
0x180008b64  jmp     loc_180008A28
0x180008b69  mov     rcx, cs:WPP_GLOBAL_Control
0x180008b70  cmp     rcx, rdi
0x180008b73  jz      loc_180008930
0x180008b79  test    byte ptr [rcx+1Ch], 1
0x180008b7d  jz      loc_180008994
0x180008b83  mov     edx, 10h
0x180008b88  jmp     short loc_180008B8F
0x180008b8a  mov     edx, 11h
0x180008b8f  mov     rcx, [rcx+10h]
0x180008b93  mov     r9d, ebx
0x180008b96  mov     r8, r15
0x180008b99  call    WPP_SF_d
0x180008b9e  mov     rcx, cs:WPP_GLOBAL_Control
0x180008ba5  jmp     loc_180008994
0x180008baa  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180008baf  mov     eax, [rbp+37h+var_74]
0x180008bb2  jmp     loc_180008928
```
