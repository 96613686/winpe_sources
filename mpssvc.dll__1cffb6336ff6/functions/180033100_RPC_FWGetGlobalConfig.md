# RPC_FWGetGlobalConfig

- ea: `0x180033100`
- end: `0x180033578`
- name: `RPC_FWGetGlobalConfig`
- size: `1144`
- prototype: `__int64 __usercall@<rax>(RPC_BINDING_HANDLE BindingHandle@<rcx>, int, __int64, int, __int64, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800093b0`
- `0x18000af3c`
- `0x180033100`
- `0x180033580`
- `0x1800670c0`
- `0x18006f520`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18003316c`
- `ntdll!EtwEventWrite` at `0x180033313`
- `ntdll!EtwEventWrite` at `0x18003316c`
- `ntdll!EtwEventWrite` at `0x180033313`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800331ce`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800331ce`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800331ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800331ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800333dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033428`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800333dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033428`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180033261`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180033261`
- `RPCRT4!RpcRevertToSelf` at `0x1800331f0`
- `RPCRT4!RpcRevertToSelf` at `0x1800331f0`
- `RPCRT4!RpcImpersonateClient` at `0x1800331aa`
- `RPCRT4!RpcImpersonateClient` at `0x1800331aa`
- `bcrypt!BCryptGetFipsAlgorithmMode` at `0x180033182`
- `bcrypt!BCryptGetFipsAlgorithmMode` at `0x180033182`
- `fwbase!FwHResultToWindowsError` at `0x1800332f2`
- `fwbase!FwHResultToWindowsError` at `0x1800332f2`
- `fwbase!FwCloseHandle` at `0x180033283`
- `fwbase!FwCloseHandle` at `0x180033283`

## string_xrefs

- `0x18003348c`: `mpssvc.dll`

## pseudocode

```c
__int64 __fastcall RPC_FWGetGlobalConfig(
        RPC_BINDING_HANDLE BindingHandle,
        unsigned __int16 a2,
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
  signed int LastError; // eax
  signed int v33; // eax
  __int64 v34; // rdx
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
    EtwEventWrite(g_Provider, MPS_SVC_API_Enter_GetGlobalConfig, 0, 0);
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
      v34 = 36;
LABEL_54:
      WPP_SF_d(*(_QWORD *)(v20 + 16), v34, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids, (unsigned int)v13);
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
      goto LABEL_17;
    }
    v33 = GetLastError();
    v13 = v33;
    if ( v33 > 0 )
      v13 = (unsigned __int16)v33 | 0x80070000;
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
      v34 = 37;
      goto LABEL_54;
    }
  }
LABEL_17:
  FwCloseHandle(v11);
  if ( v13 < 0 )
  {
    v30 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_25;
    if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_30;
    v35 = 16;
LABEL_62:
    WPP_SF_d(*(_QWORD *)(v30 + 16), v35, WPP_bc95a2d00ecc337a62d9dd8dc7f02b78_Traceguids, (unsigned int)v13);
    v30 = WPP_GLOBAL_Control;
    goto LABEL_30;
  }
  if ( v21 )
  {
    v13 = SvrImpl_FWGetGlobalConfig2_10(BindingHandle, a2, a3, a4, a5, a6, &v42);
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
          goto LABEL_24;
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
LABEL_24:
    if ( v27 )
    {
      v30 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v31 = 58;
        goto LABEL_67;
      }
    }
    goto LABEL_25;
  }
  v13 = -2147024891;
  v30 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    goto LABEL_25;
  if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    v35 = 17;
    goto LABEL_62;
  }
LABEL_30:
  if ( (_UNKNOWN *)v30 != &WPP_GLOBAL_Control && (*(_BYTE *)(v30 + 28) & 1) != 0 )
  {
    v31 = 57;
LABEL_67:
    WPP_SF_d(*(_QWORD *)(v30 + 16), v31, WPP_bc95a2d00ecc337a62d9dd8dc7f02b78_Traceguids, (unsigned int)v13);
  }
LABEL_25:
  v28 = FwHResultToWindowsError((unsigned int)v13);
  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_SVC_API_Exit_GetGlobalConfig, 0, 0);
  return v28;
}

```

## disassembly

```asm
0x180033100  push    rbp
0x180033102  push    rbx
0x180033103  push    rsi
0x180033104  push    rdi
0x180033105  push    r12
0x180033107  push    r13
0x180033109  push    r15
0x18003310b  lea     rbp, [rsp-7]
0x180033110  sub     rsp, 0B0h
0x180033117  mov     rax, cs:__security_cookie
0x18003311e  xor     rax, rsp
0x180033121  mov     [rbp+37h+var_38], rax
0x180033125  mov     rax, [rbp+37h+arg_28]
0x180033129  mov     rbx, rcx
0x18003312c  mov     r12, [rbp+37h+arg_38]
0x180033130  xor     edi, edi
0x180033132  mov     r13, [rbp+37h+arg_40]
0x180033139  mov     [rbp+37h+var_88], rcx
0x18003313d  mov     rcx, cs:g_Provider
0x180033144  mov     [rbp+37h+var_90], rax
0x180033148  mov     eax, [rbp+37h+arg_30]
0x18003314b  mov     [rbp+37h+var_74], eax
0x18003314e  mov     [rbp+37h+var_9C], r9d
0x180033152  mov     [rbp+37h+var_98], r8d
0x180033156  mov     [rbp+37h+var_A0], dx
0x18003315a  test    rcx, rcx
0x18003315d  jz      short loc_180033172
0x18003315f  xor     r9d, r9d
0x180033162  lea     rdx, MPS_SVC_API_Enter_GetGlobalConfig
0x180033169  xor     r8d, r8d
0x18003316c  call    cs:__imp_EtwEventWrite
0x180033172  mov     [r12], edi
0x180033176  lea     rcx, [rbp+37h+pfEnabled]; pfEnabled
0x18003317a  mov     [r13+0], edi
0x18003317e  mov     [rbp+37h+pfEnabled], dil
0x180033182  call    cs:__imp_BCryptGetFipsAlgorithmMode
0x180033188  test    eax, eax
0x18003318a  js      short loc_180033199
0x18003318c  mov     rsi, cs:pSecurityDescriptor
0x180033193  cmp     [rbp+37h+pfEnabled], dil
0x180033197  jnz     short loc_1800331A0
0x180033199  mov     rsi, cs:qword_18012C848
0x1800331a0  mov     rcx, rbx; BindingHandle
0x1800331a3  mov     [rbp+37h+TokenHandle], rdi
0x1800331a7  mov     r15, rdi
0x1800331aa  call    cs:__imp_RpcImpersonateClient
0x1800331b0  mov     ebx, eax
0x1800331b2  test    eax, eax
0x1800331b4  jnz     loc_180033393
0x1800331ba  call    cs:__imp_GetCurrentThread
0x1800331c0  mov     rcx, rax; ThreadHandle
0x1800331c3  lea     r9, [rbp+37h+TokenHandle]; TokenHandle
0x1800331c7  lea     edx, [rbx+8]; DesiredAccess
0x1800331ca  lea     r8d, [rbx+1]; OpenAsSelf
0x1800331ce  call    cs:__imp_OpenThreadToken
0x1800331d4  lea     rdi, WPP_GLOBAL_Control
0x1800331db  test    eax, eax
0x1800331dd  jz      loc_1800333DC
0x1800331e3  mov     r15, [rbp+37h+TokenHandle]
0x1800331e7  test    r15, r15
0x1800331ea  jz      loc_18003347B
0x1800331f0  call    cs:__imp_RpcRevertToSelf
0x1800331f6  test    eax, eax
0x1800331f8  jnz     loc_180033489
0x1800331fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180033205  test    ebx, ebx
0x180033207  js      loc_18003349F
0x18003320d  xor     eax, eax
0x18003320f  mov     [rbp+37h+var_68], 14h
0x180033216  mov     [rbp+37h+var_60.Privilege.Attributes], eax
0x180033219  lea     r9, [rbp+37h+GenericMapping]; GenericMapping
0x18003321d  mov     [rbp+37h+var_6C], eax
0x180033220  xorps   xmm0, xmm0
0x180033223  mov     [rbp+37h+var_70], eax
0x180033226  xorps   xmm1, xmm1
0x180033229  lea     rax, [rbp+37h+var_70]
0x18003322d  mov     r8d, 20000h; DesiredAccess
0x180033233  mov     [rsp+0E0h+AccessStatus], rax; AccessStatus
0x180033238  mov     rdx, r15; ClientToken
0x18003323b  lea     rax, [rbp+37h+var_6C]
0x18003323f  mov     rcx, rsi; pSecurityDescriptor
0x180033242  mov     [rsp+0E0h+GrantedAccess], rax; GrantedAccess
0x180033247  lea     rax, [rbp+37h+var_68]
0x18003324b  mov     [rsp+0E0h+PrivilegeSetLength], rax; PrivilegeSetLength
0x180033250  lea     rax, [rbp+37h+var_60]
0x180033254  mov     [rsp+0E0h+PrivilegeSet], rax; PrivilegeSet
0x180033259  movups  xmmword ptr [rbp+37h+GenericMapping.GenericRead], xmm0
0x18003325d  movups  xmmword ptr [rbp+37h+var_60.PrivilegeCount], xmm1
0x180033261  call    cs:__imp_AccessCheck
0x180033267  test    eax, eax
0x180033269  jz      loc_180033428
0x18003326f  mov     esi, [rbp+37h+var_70]
0x180033272  xor     ebx, ebx
0x180033274  jmp     short loc_180033280
0x180033276  xor     esi, esi
0x180033278  test    ebx, ebx
0x18003327a  js      loc_1800334D6
0x180033280  mov     rcx, r15
0x180033283  call    cs:__imp_FwCloseHandle
0x180033289  lea     r15, WPP_bc95a2d00ecc337a62d9dd8dc7f02b78_Traceguids
0x180033290  test    ebx, ebx
0x180033292  js      loc_1800334EB
0x180033298  test    esi, esi
0x18003329a  jz      loc_180033339
0x1800332a0  mov     r9d, [rbp+37h+var_9C]
0x1800332a4  lea     rax, [rbp+37h+var_74]
0x1800332a8  mov     r8d, [rbp+37h+var_98]
0x1800332ac  movzx   edx, [rbp+37h+var_A0]
0x1800332b0  mov     rcx, [rbp+37h+var_88]
0x1800332b4  mov     [rsp+0E0h+GrantedAccess], rax
0x1800332b9  mov     rax, [rbp+37h+var_90]
0x1800332bd  mov     [rsp+0E0h+PrivilegeSetLength], rax
0x1800332c2  mov     eax, [rbp+37h+arg_20]
0x1800332c5  mov     dword ptr [rsp+0E0h+PrivilegeSet], eax
0x1800332c9  call    ?SvrImpl_FWGetGlobalConfig2_10@@YAKPEAXGW4_tag_FW_STORE_TYPE@@W4_tag_FW_GLOBAL_CONFIG@@KPEAEPEAKPEAW4_tag_FW_RULE_ORIGIN_TYPE@@@Z; SvrImpl_FWGetGlobalConfig2_10(void *,ushort,_tag_FW_STORE_TYPE,_tag_FW_GLOBAL_CONFIG,ulong,uchar *,ulong *,_tag_FW_RULE_ORIGIN_TYPE *)
0x1800332ce  mov     ebx, eax
0x1800332d0  test    eax, eax
0x1800332d2  jnz     loc_180033369
0x1800332d8  mov     eax, [rbp+37h+var_74]
0x1800332db  cmp     eax, [rbp+37h+arg_30]
0x1800332de  ja      loc_18003352C
0x1800332e4  mov     [r12], eax
0x1800332e8  test    ebx, ebx
0x1800332ea  js      loc_180033545
0x1800332f0  mov     ecx, ebx
0x1800332f2  call    cs:__imp_FwHResultToWindowsError
0x1800332f8  mov     rcx, cs:g_Provider
0x1800332ff  mov     ebx, eax
0x180033301  test    rcx, rcx
0x180033304  jz      short loc_180033319
0x180033306  xor     r9d, r9d
0x180033309  lea     rdx, MPS_SVC_API_Exit_GetGlobalConfig
0x180033310  xor     r8d, r8d
0x180033313  call    cs:__imp_EtwEventWrite
0x180033319  mov     eax, ebx
0x18003331b  mov     rcx, [rbp+37h+var_38]
0x18003331f  xor     rcx, rsp; StackCookie
0x180033322  call    __security_check_cookie
0x180033327  add     rsp, 0B0h
0x18003332e  pop     r15
0x180033330  pop     r13
0x180033332  pop     r12
0x180033334  pop     rdi
0x180033335  pop     rsi
0x180033336  pop     rbx
0x180033337  pop     rbp
0x180033338  retn
0x180033339  mov     ebx, 80070005h
0x18003333e  mov     rcx, cs:WPP_GLOBAL_Control
0x180033345  cmp     rcx, rdi
0x180033348  jz      short loc_1800332F0
0x18003334a  test    byte ptr [rcx+1Ch], 1
0x18003334e  jnz     loc_18003350C
0x180033354  cmp     rcx, rdi
0x180033357  jz      short loc_1800332F0
0x180033359  test    byte ptr [rcx+1Ch], 1
0x18003335d  jz      short loc_1800332F0
0x18003335f  mov     edx, 39h ; '9'
0x180033364  jmp     loc_180033564
0x180033369  mov     dword ptr [r12], 0
0x180033371  cmp     ebx, 0EAh
0x180033377  jz      loc_180033539
0x18003337d  test    ebx, ebx
0x18003337f  jle     loc_1800332EA
0x180033385  movzx   ebx, bx
0x180033388  or      ebx, 80070000h
0x18003338e  jmp     loc_1800332E8
0x180033393  jle     short loc_18003339E
0x180033395  movzx   ebx, ax
0x180033398  or      ebx, 80070000h
0x18003339e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800333a5  lea     rdi, WPP_GLOBAL_Control
0x1800333ac  cmp     rcx, rdi
0x1800333af  jz      loc_180033205
0x1800333b5  test    byte ptr [rcx+1Ch], 1
0x1800333b9  jz      loc_180033205
0x1800333bf  mov     rcx, [rcx+10h]
0x1800333c3  lea     r8, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids
0x1800333ca  mov     edx, 22h ; '"'
0x1800333cf  mov     r9d, ebx
0x1800333d2  call    WPP_SF_d
0x1800333d7  jmp     loc_1800331FE
0x1800333dc  call    cs:__imp_GetLastError
0x1800333e2  mov     ebx, eax
0x1800333e4  test    eax, eax
0x1800333e6  jle     short loc_1800333F1
0x1800333e8  movzx   ebx, ax
0x1800333eb  or      ebx, 80070000h
0x1800333f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800333f8  cmp     rcx, rdi
0x1800333fb  jz      loc_1800331F0
0x180033401  test    byte ptr [rcx+1Ch], 1
0x180033405  jz      loc_1800331F0
0x18003340b  mov     rcx, [rcx+10h]
0x18003340f  lea     r8, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids
0x180033416  mov     edx, 23h ; '#'
0x18003341b  mov     r9d, ebx
0x18003341e  call    WPP_SF_d
0x180033423  jmp     loc_1800331F0
0x180033428  call    cs:__imp_GetLastError
0x18003342e  mov     ebx, eax
0x180033430  test    eax, eax
0x180033432  jle     short loc_18003343D
0x180033434  movzx   ebx, ax
0x180033437  or      ebx, 80070000h
0x18003343d  mov     rcx, cs:WPP_GLOBAL_Control
0x180033444  cmp     rcx, rdi
0x180033447  jz      loc_180033276
0x18003344d  test    byte ptr [rcx+1Ch], 1
0x180033451  jz      loc_180033276
0x180033457  mov     rcx, [rcx+10h]
0x18003345b  lea     r8, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids
0x180033462  mov     edx, 26h ; '&'
0x180033467  mov     r9d, ebx
0x18003346a  call    WPP_SF_d
0x18003346f  mov     rcx, cs:WPP_GLOBAL_Control
0x180033476  jmp     loc_180033276
0x18003347b  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180033480  mov     r15, [rbp+37h+TokenHandle]
0x180033484  jmp     loc_1800331F0
0x180033489  xor     r8d, r8d
0x18003348c  lea     rcx, aMpssvcDll_1; "mpssvc.dll"
0x180033493  mov     edx, eax
0x180033495  call    MicrosoftTelemetryAssertTriggeredArgs
0x18003349a  jmp     loc_1800331FE
0x18003349f  xor     esi, esi
0x1800334a1  cmp     rcx, rdi
0x1800334a4  jz      loc_180033280
0x1800334aa  test    byte ptr [rcx+1Ch], 1
0x1800334ae  jz      loc_180033280
0x1800334b4  lea     edx, [rsi+24h]
0x1800334b7  jmp     short loc_1800334BE
0x1800334b9  mov     edx, 25h ; '%'
0x1800334be  mov     rcx, [rcx+10h]
0x1800334c2  lea     r8, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids
0x1800334c9  mov     r9d, ebx
0x1800334cc  call    WPP_SF_d
0x1800334d1  jmp     loc_180033280
0x1800334d6  cmp     rcx, rdi
0x1800334d9  jz      loc_180033280
0x1800334df  test    byte ptr [rcx+1Ch], 1
0x1800334e3  jz      loc_180033280
0x1800334e9  jmp     short loc_1800334B9
0x1800334eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800334f2  cmp     rcx, rdi
0x1800334f5  jz      loc_1800332F0
0x1800334fb  test    byte ptr [rcx+1Ch], 1
0x1800334ff  jz      loc_180033354
0x180033505  mov     edx, 10h
0x18003350a  jmp     short loc_180033511
0x18003350c  mov     edx, 11h
0x180033511  mov     rcx, [rcx+10h]
0x180033515  mov     r9d, ebx
0x180033518  mov     r8, r15
0x18003351b  call    WPP_SF_d
0x180033520  mov     rcx, cs:WPP_GLOBAL_Control
0x180033527  jmp     loc_180033354
0x18003352c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180033531  mov     eax, [rbp+37h+var_74]
0x180033534  jmp     loc_1800332E4
0x180033539  mov     eax, [rbp+37h+var_74]
0x18003353c  mov     [r13+0], eax
0x180033540  jmp     loc_180033385
0x180033545  mov     rcx, cs:WPP_GLOBAL_Control
0x18003354c  cmp     rcx, rdi
0x18003354f  jz      loc_1800332F0
0x180033555  test    byte ptr [rcx+1Ch], 1
0x180033559  jz      loc_1800332F0
0x18003355f  mov     edx, 3Ah ; ':'
0x180033564  mov     rcx, [rcx+10h]
0x180033568  mov     r9d, ebx
0x18003356b  mov     r8, r15
0x18003356e  call    WPP_SF_d
0x180033573  jmp     loc_1800332F0
```
