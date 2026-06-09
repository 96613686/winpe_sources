# RPC_Hlp_FWGetConfig(void *,void *,_tag_FW_PROFILE_CONFIG,_tag_FW_PROFILE_TYPE,ulong,uchar *,ulong,ulong *,ulong *,_tag_FW_RULE_ORIGIN_TYPE *)

- ea: `0x180007f4c`
- end: `0x1800083bd`
- name: `?RPC_Hlp_FWGetConfig@@YAKPEAX0W4_tag_FW_PROFILE_CONFIG@@W4_tag_FW_PROFILE_TYPE@@KPEAEKPEAK4PEAW4_tag_FW_RULE_ORIGIN_TYPE@@@Z`
- size: `1137`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800c2b70`

## callees

- `0x180007f4c`
- `0x180008bc0`
- `0x1800093b0`
- `0x18000af3c`
- `0x1800670c0`
- `0x18006f520`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180007fc3`
- `ntdll!EtwEventWrite` at `0x180008157`
- `ntdll!EtwEventWrite` at `0x180007fc3`
- `ntdll!EtwEventWrite` at `0x180008157`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180008023`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180008023`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000800f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000800f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000828f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800082db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000828f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800082db`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x1800080b6`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x1800080b6`
- `RPCRT4!RpcRevertToSelf` at `0x180008045`
- `RPCRT4!RpcRevertToSelf` at `0x180008045`
- `RPCRT4!RpcImpersonateClient` at `0x180007fff`
- `RPCRT4!RpcImpersonateClient` at `0x180007fff`
- `bcrypt!BCryptGetFipsAlgorithmMode` at `0x180007fd7`
- `bcrypt!BCryptGetFipsAlgorithmMode` at `0x180007fd7`
- `fwbase!FwHResultToWindowsError` at `0x180008136`
- `fwbase!FwHResultToWindowsError` at `0x180008136`
- `fwbase!FwCloseHandle` at `0x1800080cc`
- `fwbase!FwCloseHandle` at `0x1800080cc`

## string_xrefs

- `0x18000833f`: `mpssvc.dll`

## pseudocode

```c
__int64 __fastcall RPC_Hlp_FWGetConfig(
        void *a1,
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
  void *v11; // r14
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
  void *TokenHandle; // [rsp+68h] [rbp-51h] BYREF
  BOOLEAN pfEnabled[4]; // [rsp+70h] [rbp-49h] BYREF
  unsigned int v41; // [rsp+74h] [rbp-45h] BYREF
  WINBOOL AccessStatus; // [rsp+78h] [rbp-41h] BYREF
  DWORD GrantedAccess; // [rsp+7Ch] [rbp-3Dh] BYREF
  DWORD PrivilegeSetLength; // [rsp+80h] [rbp-39h] BYREF
  struct _PRIVILEGE_SET PrivilegeSet; // [rsp+88h] [rbp-31h] BYREF
  _GENERIC_MAPPING GenericMapping; // [rsp+A0h] [rbp-19h] BYREF

  v41 = a7;
  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_SVC_API_Enter_GetConfig, 0, 0);
  *a8 = 0;
  *a9 = 0;
  pfEnabled[0] = 0;
  if ( BCryptGetFipsAlgorithmMode(pfEnabled) < 0 || (v10 = pSecurityDescriptor, !pfEnabled[0]) )
    v10 = (PSECURITY_DESCRIPTOR)qword_18012C848[0];
  TokenHandle = 0;
  v11 = 0;
  v12 = RpcImpersonateClient(a1);
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
    v13 = SvrImpl_FWGetConfig2_10(a1, a2, a3, a4, a5, a6, &v41);
    if ( v13 )
    {
      *a8 = 0;
      if ( v13 == 234 )
      {
        *a9 = v41;
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
      v26 = v41;
      if ( v41 > a7 )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs(v23, v22, v24, v25);
        v26 = v41;
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
0x180007f4c  push    rbp
0x180007f4e  push    rbx
0x180007f4f  push    rsi
0x180007f50  push    rdi
0x180007f51  push    r12
0x180007f53  push    r13
0x180007f55  push    r14
0x180007f57  lea     rbp, [rsp-7]
0x180007f5c  sub     rsp, 0C0h
0x180007f63  mov     rax, cs:__security_cookie
0x180007f6a  xor     rax, rsp
0x180007f6d  mov     [rbp+37h+var_40], rax
0x180007f71  mov     rax, [rbp+37h+arg_28]
0x180007f75  mov     r13, rcx
0x180007f78  mov     rcx, cs:g_Provider
0x180007f7f  xor     edi, edi
0x180007f81  mov     rbx, [rbp+37h+arg_40]
0x180007f88  mov     r12, [rbp+37h+arg_38]
0x180007f8c  mov     [rbp+37h+var_A8], rax
0x180007f90  mov     rax, [rbp+37h+arg_48]
0x180007f97  mov     [rbp+37h+var_98], rax
0x180007f9b  mov     eax, [rbp+37h+arg_30]
0x180007f9e  mov     [rbp+37h+var_7C], eax
0x180007fa1  mov     [rbp+37h+var_B0], r9d
0x180007fa5  mov     [rbp+37h+var_AC], r8d
0x180007fa9  mov     [rbp+37h+var_A0], rdx
0x180007fad  mov     [rbp+37h+var_90], rbx
0x180007fb1  test    rcx, rcx
0x180007fb4  jz      short loc_180007FC9
0x180007fb6  xor     r9d, r9d
0x180007fb9  lea     rdx, MPS_SVC_API_Enter_GetConfig
0x180007fc0  xor     r8d, r8d
0x180007fc3  call    cs:__imp_EtwEventWrite
0x180007fc9  mov     [r12], edi
0x180007fcd  lea     rcx, [rbp+37h+pfEnabled]; pfEnabled
0x180007fd1  mov     [rbx], edi
0x180007fd3  mov     [rbp+37h+pfEnabled], dil
0x180007fd7  call    cs:__imp_BCryptGetFipsAlgorithmMode
0x180007fdd  test    eax, eax
0x180007fdf  js      short loc_180007FEE
0x180007fe1  mov     rsi, cs:pSecurityDescriptor
0x180007fe8  cmp     [rbp+37h+pfEnabled], dil
0x180007fec  jnz     short loc_180007FF5
0x180007fee  mov     rsi, cs:qword_18012C848
0x180007ff5  mov     rcx, r13; BindingHandle
0x180007ff8  mov     [rbp+37h+TokenHandle], rdi
0x180007ffc  mov     r14, rdi
0x180007fff  call    cs:__imp_RpcImpersonateClient
0x180008005  mov     ebx, eax
0x180008007  test    eax, eax
0x180008009  jnz     loc_180008246
0x18000800f  call    cs:__imp_GetCurrentThread
0x180008015  mov     rcx, rax; ThreadHandle
0x180008018  lea     r9, [rbp+37h+TokenHandle]; TokenHandle
0x18000801c  lea     edx, [rbx+8]; DesiredAccess
0x18000801f  lea     r8d, [rbx+1]; OpenAsSelf
0x180008023  call    cs:__imp_OpenThreadToken
0x180008029  lea     rdi, WPP_GLOBAL_Control
0x180008030  test    eax, eax
0x180008032  jz      loc_18000828F
0x180008038  mov     r14, [rbp+37h+TokenHandle]
0x18000803c  test    r14, r14
0x18000803f  jz      loc_18000832E
0x180008045  call    cs:__imp_RpcRevertToSelf
0x18000804b  test    eax, eax
0x18000804d  jnz     loc_18000833C
0x180008053  mov     rcx, cs:WPP_GLOBAL_Control
0x18000805a  test    ebx, ebx
0x18000805c  js      loc_180008352
0x180008062  xor     eax, eax
0x180008064  mov     [rbp+37h+var_70], 14h
0x18000806b  mov     [rbp+37h+var_68.Privilege.Attributes], eax
0x18000806e  lea     r9, [rbp+37h+GenericMapping]; GenericMapping
0x180008072  mov     [rbp+37h+var_74], eax
0x180008075  xorps   xmm0, xmm0
0x180008078  mov     [rbp+37h+var_78], eax
0x18000807b  xorps   xmm1, xmm1
0x18000807e  lea     rax, [rbp+37h+var_78]
0x180008082  mov     r8d, 20000h; DesiredAccess
0x180008088  mov     [rsp+0F0h+AccessStatus], rax; AccessStatus
0x18000808d  mov     rdx, r14; ClientToken
0x180008090  lea     rax, [rbp+37h+var_74]
0x180008094  mov     rcx, rsi; pSecurityDescriptor
0x180008097  mov     [rsp+0F0h+GrantedAccess], rax; GrantedAccess
0x18000809c  lea     rax, [rbp+37h+var_70]
0x1800080a0  mov     [rsp+0F0h+PrivilegeSetLength], rax; PrivilegeSetLength
0x1800080a5  lea     rax, [rbp+37h+var_68]
0x1800080a9  mov     [rsp+0F0h+PrivilegeSet], rax; PrivilegeSet
0x1800080ae  movups  xmmword ptr [rbp+37h+GenericMapping.GenericRead], xmm0
0x1800080b2  movups  xmmword ptr [rbp+37h+var_68.PrivilegeCount], xmm1
0x1800080b6  call    cs:__imp_AccessCheck
0x1800080bc  test    eax, eax
0x1800080be  jz      loc_1800082DB
0x1800080c4  mov     esi, [rbp+37h+var_78]
0x1800080c7  xor     ebx, ebx
0x1800080c9  mov     rcx, r14
0x1800080cc  call    cs:__imp_FwCloseHandle
0x1800080d2  lea     r14, WPP_bc95a2d00ecc337a62d9dd8dc7f02b78_Traceguids
0x1800080d9  test    ebx, ebx
0x1800080db  js      loc_18000836F
0x1800080e1  test    esi, esi
0x1800080e3  jz      loc_18000817D
0x1800080e9  mov     r9d, [rbp+37h+var_B0]
0x1800080ed  lea     rax, [rbp+37h+var_7C]
0x1800080f1  mov     r8d, [rbp+37h+var_AC]
0x1800080f5  mov     rcx, r13
0x1800080f8  mov     rdx, [rbp+37h+var_A0]
0x1800080fc  mov     [rsp+0F0h+GrantedAccess], rax
0x180008101  mov     rax, [rbp+37h+var_A8]
0x180008105  mov     [rsp+0F0h+PrivilegeSetLength], rax
0x18000810a  mov     eax, [rbp+37h+arg_20]
0x18000810d  mov     dword ptr [rsp+0F0h+PrivilegeSet], eax
0x180008111  call    ?SvrImpl_FWGetConfig2_10@@YAKPEAX0W4_tag_FW_PROFILE_CONFIG@@W4_tag_FW_PROFILE_TYPE@@KPEAEPEAKPEAW4_tag_FW_RULE_ORIGIN_TYPE@@@Z; SvrImpl_FWGetConfig2_10(void *,void *,_tag_FW_PROFILE_CONFIG,_tag_FW_PROFILE_TYPE,ulong,uchar *,ulong *,_tag_FW_RULE_ORIGIN_TYPE *)
0x180008116  mov     ebx, eax
0x180008118  test    eax, eax
0x18000811a  jnz     loc_1800081DD
0x180008120  mov     eax, [rbp+37h+var_7C]
0x180008123  cmp     eax, [rbp+37h+arg_30]
0x180008126  ja      loc_1800083B0
0x18000812c  mov     [r12], eax
0x180008130  test    ebx, ebx
0x180008132  js      short loc_1800081AA
0x180008134  mov     ecx, ebx
0x180008136  call    cs:__imp_FwHResultToWindowsError
0x18000813c  mov     rcx, cs:g_Provider
0x180008143  mov     ebx, eax
0x180008145  test    rcx, rcx
0x180008148  jz      short loc_18000815D
0x18000814a  xor     r9d, r9d
0x18000814d  lea     rdx, MPS_SVC_API_Exit_GetConfig
0x180008154  xor     r8d, r8d
0x180008157  call    cs:__imp_EtwEventWrite
0x18000815d  mov     eax, ebx
0x18000815f  mov     rcx, [rbp+37h+var_40]
0x180008163  xor     rcx, rsp; StackCookie
0x180008166  call    __security_check_cookie
0x18000816b  add     rsp, 0C0h
0x180008172  pop     r14
0x180008174  pop     r13
0x180008176  pop     r12
0x180008178  pop     rdi
0x180008179  pop     rsi
0x18000817a  pop     rbx
0x18000817b  pop     rbp
0x18000817c  retn
0x18000817d  mov     ebx, 80070005h
0x180008182  mov     rcx, cs:WPP_GLOBAL_Control
0x180008189  cmp     rcx, rdi
0x18000818c  jz      short loc_180008134
0x18000818e  test    byte ptr [rcx+1Ch], 1
0x180008192  jnz     loc_180008390
0x180008198  cmp     rcx, rdi
0x18000819b  jz      short loc_180008134
0x18000819d  test    byte ptr [rcx+1Ch], 1
0x1800081a1  jz      short loc_180008134
0x1800081a3  mov     edx, 31h ; '1'
0x1800081a8  jmp     short loc_1800081C9
0x1800081aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800081b1  cmp     rcx, rdi
0x1800081b4  jz      loc_180008134
0x1800081ba  test    byte ptr [rcx+1Ch], 1
0x1800081be  jz      loc_180008134
0x1800081c4  mov     edx, 32h ; '2'
0x1800081c9  mov     rcx, [rcx+10h]
0x1800081cd  mov     r9d, ebx
0x1800081d0  mov     r8, r14
0x1800081d3  call    WPP_SF_d
0x1800081d8  jmp     loc_180008134
0x1800081dd  mov     dword ptr [r12], 0
0x1800081e5  cmp     ebx, 0EAh
0x1800081eb  jnz     short loc_1800081F8
0x1800081ed  mov     rcx, [rbp+37h+var_90]
0x1800081f1  mov     eax, [rbp+37h+var_7C]
0x1800081f4  mov     [rcx], eax
0x1800081f6  jmp     short loc_180008200
0x1800081f8  test    ebx, ebx
0x1800081fa  jle     loc_180008132
0x180008200  movzx   ebx, bx
0x180008203  or      ebx, 80070000h
0x180008209  jmp     loc_180008130
0x18000820e  xor     esi, esi
0x180008210  test    ebx, ebx
0x180008212  jns     loc_1800080C9
0x180008218  cmp     rcx, rdi
0x18000821b  jz      loc_1800080C9
0x180008221  test    byte ptr [rcx+1Ch], 1
0x180008225  jz      loc_1800080C9
0x18000822b  lea     edx, [rsi+25h]
0x18000822e  mov     rcx, [rcx+10h]
0x180008232  lea     r8, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids
0x180008239  mov     r9d, ebx
0x18000823c  call    WPP_SF_d
0x180008241  jmp     loc_1800080C9
0x180008246  jle     short loc_180008251
0x180008248  movzx   ebx, ax
0x18000824b  or      ebx, 80070000h
0x180008251  mov     rcx, cs:WPP_GLOBAL_Control
0x180008258  lea     rdi, WPP_GLOBAL_Control
0x18000825f  cmp     rcx, rdi
0x180008262  jz      loc_18000805A
0x180008268  test    byte ptr [rcx+1Ch], 1
0x18000826c  jz      loc_18000805A
0x180008272  mov     rcx, [rcx+10h]
0x180008276  lea     r8, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids
0x18000827d  mov     edx, 22h ; '"'
0x180008282  mov     r9d, ebx
0x180008285  call    WPP_SF_d
0x18000828a  jmp     loc_180008053
0x18000828f  call    cs:__imp_GetLastError
0x180008295  mov     ebx, eax
0x180008297  test    eax, eax
0x180008299  jle     short loc_1800082A4
0x18000829b  movzx   ebx, ax
0x18000829e  or      ebx, 80070000h
0x1800082a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800082ab  cmp     rcx, rdi
0x1800082ae  jz      loc_180008045
0x1800082b4  test    byte ptr [rcx+1Ch], 1
0x1800082b8  jz      loc_180008045
0x1800082be  mov     rcx, [rcx+10h]
0x1800082c2  lea     r8, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids
0x1800082c9  mov     edx, 23h ; '#'
0x1800082ce  mov     r9d, ebx
0x1800082d1  call    WPP_SF_d
0x1800082d6  jmp     loc_180008045
0x1800082db  call    cs:__imp_GetLastError
0x1800082e1  mov     ebx, eax
0x1800082e3  test    eax, eax
0x1800082e5  jle     short loc_1800082F0
0x1800082e7  movzx   ebx, ax
0x1800082ea  or      ebx, 80070000h
0x1800082f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800082f7  cmp     rcx, rdi
0x1800082fa  jz      loc_18000820E
0x180008300  test    byte ptr [rcx+1Ch], 1
0x180008304  jz      loc_18000820E
0x18000830a  mov     rcx, [rcx+10h]
0x18000830e  lea     r8, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids
0x180008315  mov     edx, 26h ; '&'
0x18000831a  mov     r9d, ebx
0x18000831d  call    WPP_SF_d
0x180008322  mov     rcx, cs:WPP_GLOBAL_Control
0x180008329  jmp     loc_18000820E
0x18000832e  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180008333  mov     r14, [rbp+37h+TokenHandle]
0x180008337  jmp     loc_180008045
0x18000833c  xor     r8d, r8d
0x18000833f  lea     rcx, aMpssvcDll_1; "mpssvc.dll"
0x180008346  mov     edx, eax
0x180008348  call    MicrosoftTelemetryAssertTriggeredArgs
0x18000834d  jmp     loc_180008053
0x180008352  xor     esi, esi
0x180008354  cmp     rcx, rdi
0x180008357  jz      loc_1800080C9
0x18000835d  test    byte ptr [rcx+1Ch], 1
0x180008361  jz      loc_1800080C9
0x180008367  lea     edx, [rsi+24h]
0x18000836a  jmp     loc_18000822E
0x18000836f  mov     rcx, cs:WPP_GLOBAL_Control
0x180008376  cmp     rcx, rdi
0x180008379  jz      loc_180008134
0x18000837f  test    byte ptr [rcx+1Ch], 1
0x180008383  jz      loc_180008198
0x180008389  mov     edx, 10h
0x18000838e  jmp     short loc_180008395
0x180008390  mov     edx, 11h
0x180008395  mov     rcx, [rcx+10h]
0x180008399  mov     r9d, ebx
0x18000839c  mov     r8, r14
0x18000839f  call    WPP_SF_d
0x1800083a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800083ab  jmp     loc_180008198
0x1800083b0  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800083b5  mov     eax, [rbp+37h+var_7C]
0x1800083b8  jmp     loc_18000812C
```
