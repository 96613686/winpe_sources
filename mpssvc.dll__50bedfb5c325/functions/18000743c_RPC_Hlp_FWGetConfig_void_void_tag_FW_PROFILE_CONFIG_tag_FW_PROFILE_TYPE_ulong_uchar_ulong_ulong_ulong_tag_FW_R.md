# RPC_Hlp_FWGetConfig(void *,void *,_tag_FW_PROFILE_CONFIG,_tag_FW_PROFILE_TYPE,ulong,uchar *,ulong,ulong *,ulong *,_tag_FW_RULE_ORIGIN_TYPE *)

- ea: `0x18000743c`
- end: `0x1800078fa`
- name: `?RPC_Hlp_FWGetConfig@@YAKPEAX0W4_tag_FW_PROFILE_CONFIG@@W4_tag_FW_PROFILE_TYPE@@KPEAEKPEAK4PEAW4_tag_FW_RULE_ORIGIN_TYPE@@@Z`
- size: `1214`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800c9c20`

## callees

- `0x18000743c`
- `0x180008170`
- `0x1800089bc`
- `0x18000a710`
- `0x18006a710`
- `0x1800729c0`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x1800074b3`
- `ntdll!EtwEventWrite` at `0x180007681`
- `ntdll!EtwEventWrite` at `0x1800074b3`
- `ntdll!EtwEventWrite` at `0x180007681`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180007511`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180007511`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000752b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000752b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800077c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007812`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800077c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007812`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x1800075ca`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x1800075ca`
- `RPCRT4!RpcImpersonateClient` at `0x1800074fb`
- `RPCRT4!RpcImpersonateClient` at `0x1800074fb`
- `RPCRT4!RpcRevertToSelf` at `0x180007553`
- `RPCRT4!RpcRevertToSelf` at `0x180007553`
- `bcrypt!BCryptGetFipsAlgorithmMode` at `0x1800074cd`
- `bcrypt!BCryptGetFipsAlgorithmMode` at `0x1800074cd`
- `fwbase!FwHResultToWindowsError` at `0x18000765a`
- `fwbase!FwHResultToWindowsError` at `0x18000765a`
- `fwbase!FwCloseHandle` at `0x1800075e6`
- `fwbase!FwCloseHandle` at `0x1800075e6`

## string_xrefs

- `0x18000787c`: `mpssvc.dll`

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
  void *TokenHandle; // [rsp+68h] [rbp-51h] BYREF
  BOOLEAN pfEnabled[4]; // [rsp+70h] [rbp-49h] BYREF
  unsigned int v33; // [rsp+74h] [rbp-45h] BYREF
  WINBOOL AccessStatus; // [rsp+78h] [rbp-41h] BYREF
  DWORD GrantedAccess; // [rsp+7Ch] [rbp-3Dh] BYREF
  DWORD PrivilegeSetLength; // [rsp+80h] [rbp-39h] BYREF
  struct _PRIVILEGE_SET PrivilegeSet; // [rsp+88h] [rbp-31h] BYREF
  _GENERIC_MAPPING GenericMapping; // [rsp+A0h] [rbp-19h] BYREF

  v33 = a7;
  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_SVC_API_Enter_GetConfig, 0, 0);
  *a8 = 0;
  *a9 = 0;
  pfEnabled[0] = 0;
  if ( BCryptGetFipsAlgorithmMode(pfEnabled) < 0 || (v10 = pSecurityDescriptor, !pfEnabled[0]) )
    v10 = (PSECURITY_DESCRIPTOR)qword_180132A18;
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
    v13 = SvrImpl_FWGetConfig2_10(a1, a2, a3, a4, a5, a6, &v33);
    if ( v13 )
    {
      *a8 = 0;
      if ( v13 == 234 )
      {
        *a9 = v33;
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
      v18 = v33;
      if ( v33 > a7 )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs();
        v18 = v33;
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
0x18000743c  push    rbp
0x18000743e  push    rbx
0x18000743f  push    rsi
0x180007440  push    rdi
0x180007441  push    r12
0x180007443  push    r13
0x180007445  push    r14
0x180007447  lea     rbp, [rsp-7]
0x18000744c  sub     rsp, 0C0h
0x180007453  mov     rax, cs:__security_cookie
0x18000745a  xor     rax, rsp
0x18000745d  mov     [rbp+37h+var_40], rax
0x180007461  mov     rax, [rbp+37h+arg_28]
0x180007465  mov     r13, rcx
0x180007468  mov     rcx, cs:g_Provider
0x18000746f  xor     edi, edi
0x180007471  mov     rbx, [rbp+37h+arg_40]
0x180007478  mov     r12, [rbp+37h+arg_38]
0x18000747c  mov     [rbp+37h+var_A8], rax
0x180007480  mov     rax, [rbp+37h+arg_48]
0x180007487  mov     [rbp+37h+var_98], rax
0x18000748b  mov     eax, [rbp+37h+arg_30]
0x18000748e  mov     [rbp+37h+var_7C], eax
0x180007491  mov     [rbp+37h+var_B0], r9d
0x180007495  mov     [rbp+37h+var_AC], r8d
0x180007499  mov     [rbp+37h+var_A0], rdx
0x18000749d  mov     [rbp+37h+var_90], rbx
0x1800074a1  test    rcx, rcx
0x1800074a4  jz      short loc_1800074BF
0x1800074a6  xor     r9d, r9d
0x1800074a9  lea     rdx, MPS_SVC_API_Enter_GetConfig
0x1800074b0  xor     r8d, r8d
0x1800074b3  call    cs:__imp_EtwEventWrite
0x1800074ba  nop     dword ptr [rax+rax+00h]
0x1800074bf  mov     [r12], edi
0x1800074c3  lea     rcx, [rbp+37h+pfEnabled]; pfEnabled
0x1800074c7  mov     [rbx], edi
0x1800074c9  mov     [rbp+37h+pfEnabled], dil
0x1800074cd  call    cs:__imp_BCryptGetFipsAlgorithmMode
0x1800074d4  nop     dword ptr [rax+rax+00h]
0x1800074d9  test    eax, eax
0x1800074db  js      short loc_1800074EA
0x1800074dd  mov     rsi, cs:pSecurityDescriptor
0x1800074e4  cmp     [rbp+37h+pfEnabled], dil
0x1800074e8  jnz     short loc_1800074F1
0x1800074ea  mov     rsi, cs:qword_180132A18
0x1800074f1  mov     rcx, r13; BindingHandle
0x1800074f4  mov     [rbp+37h+TokenHandle], rdi
0x1800074f8  mov     r14, rdi
0x1800074fb  call    cs:__imp_RpcImpersonateClient
0x180007502  nop     dword ptr [rax+rax+00h]
0x180007507  mov     ebx, eax
0x180007509  test    eax, eax
0x18000750b  jnz     loc_180007777
0x180007511  call    cs:__imp_GetCurrentThread
0x180007518  nop     dword ptr [rax+rax+00h]
0x18000751d  mov     rcx, rax; ThreadHandle
0x180007520  lea     r9, [rbp+37h+TokenHandle]; TokenHandle
0x180007524  lea     edx, [rbx+8]; DesiredAccess
0x180007527  lea     r8d, [rbx+1]; OpenAsSelf
0x18000752b  call    cs:__imp_OpenThreadToken
0x180007532  nop     dword ptr [rax+rax+00h]
0x180007537  lea     rdi, WPP_GLOBAL_Control
0x18000753e  test    eax, eax
0x180007540  jz      loc_1800077C0
0x180007546  mov     r14, [rbp+37h+TokenHandle]
0x18000754a  test    r14, r14
0x18000754d  jz      loc_18000786B
0x180007553  call    cs:__imp_RpcRevertToSelf
0x18000755a  nop     dword ptr [rax+rax+00h]
0x18000755f  test    eax, eax
0x180007561  jnz     loc_180007879
0x180007567  mov     rcx, cs:WPP_GLOBAL_Control
0x18000756e  test    ebx, ebx
0x180007570  js      loc_18000788F
0x180007576  xor     eax, eax
0x180007578  mov     [rbp+37h+var_70], 14h
0x18000757f  mov     [rbp+37h+var_68.Privilege.Attributes], eax
0x180007582  lea     r9, [rbp+37h+GenericMapping]; GenericMapping
0x180007586  mov     [rbp+37h+var_74], eax
0x180007589  xorps   xmm0, xmm0
0x18000758c  mov     [rbp+37h+var_78], eax
0x18000758f  xorps   xmm1, xmm1
0x180007592  lea     rax, [rbp+37h+var_78]
0x180007596  mov     r8d, 20000h; DesiredAccess
0x18000759c  mov     [rsp+0F0h+AccessStatus], rax; AccessStatus
0x1800075a1  mov     rdx, r14; ClientToken
0x1800075a4  lea     rax, [rbp+37h+var_74]
0x1800075a8  mov     rcx, rsi; pSecurityDescriptor
0x1800075ab  mov     [rsp+0F0h+GrantedAccess], rax; GrantedAccess
0x1800075b0  lea     rax, [rbp+37h+var_70]
0x1800075b4  mov     [rsp+0F0h+PrivilegeSetLength], rax; PrivilegeSetLength
0x1800075b9  lea     rax, [rbp+37h+var_68]
0x1800075bd  mov     [rsp+0F0h+PrivilegeSet], rax; PrivilegeSet
0x1800075c2  movups  xmmword ptr [rbp+37h+GenericMapping.GenericRead], xmm0
0x1800075c6  movups  xmmword ptr [rbp+37h+var_68.PrivilegeCount], xmm1
0x1800075ca  call    cs:__imp_AccessCheck
0x1800075d1  nop     dword ptr [rax+rax+00h]
0x1800075d6  test    eax, eax
0x1800075d8  jz      loc_180007812
0x1800075de  mov     esi, [rbp+37h+var_78]
0x1800075e1  xor     ebx, ebx
0x1800075e3  mov     rcx, r14
0x1800075e6  call    cs:__imp_FwCloseHandle
0x1800075ed  nop     dword ptr [rax+rax+00h]
0x1800075f2  lea     r14, WPP_bc95a2d00ecc337a62d9dd8dc7f02b78_Traceguids
0x1800075f9  test    ebx, ebx
0x1800075fb  js      loc_1800078AC
0x180007601  test    esi, esi
0x180007603  jz      loc_1800076AE
0x180007609  mov     r9d, [rbp+37h+var_B0]
0x18000760d  lea     rax, [rbp+37h+var_7C]
0x180007611  mov     r8d, [rbp+37h+var_AC]
0x180007615  mov     rcx, r13
0x180007618  mov     rdx, [rbp+37h+var_A0]
0x18000761c  mov     [rsp+0F0h+GrantedAccess], rax
0x180007621  mov     rax, [rbp+37h+var_A8]
0x180007625  mov     [rsp+0F0h+PrivilegeSetLength], rax
0x18000762a  mov     eax, [rbp+37h+arg_20]
0x18000762d  mov     dword ptr [rsp+0F0h+PrivilegeSet], eax
0x180007631  call    ?SvrImpl_FWGetConfig2_10@@YAKPEAX0W4_tag_FW_PROFILE_CONFIG@@W4_tag_FW_PROFILE_TYPE@@KPEAEPEAKPEAW4_tag_FW_RULE_ORIGIN_TYPE@@@Z; SvrImpl_FWGetConfig2_10(void *,void *,_tag_FW_PROFILE_CONFIG,_tag_FW_PROFILE_TYPE,ulong,uchar *,ulong *,_tag_FW_RULE_ORIGIN_TYPE *)
0x180007636  mov     ebx, eax
0x180007638  test    eax, eax
0x18000763a  jnz     loc_18000770E
0x180007640  mov     eax, [rbp+37h+var_7C]
0x180007643  cmp     eax, [rbp+37h+arg_30]
0x180007646  ja      loc_1800078ED
0x18000764c  mov     [r12], eax
0x180007650  test    ebx, ebx
0x180007652  js      loc_1800076DB
0x180007658  mov     ecx, ebx
0x18000765a  call    cs:__imp_FwHResultToWindowsError
0x180007661  nop     dword ptr [rax+rax+00h]
0x180007666  mov     rcx, cs:g_Provider
0x18000766d  mov     ebx, eax
0x18000766f  test    rcx, rcx
0x180007672  jz      short loc_18000768D
0x180007674  xor     r9d, r9d
0x180007677  lea     rdx, MPS_SVC_API_Exit_GetConfig
0x18000767e  xor     r8d, r8d
0x180007681  call    cs:__imp_EtwEventWrite
0x180007688  nop     dword ptr [rax+rax+00h]
0x18000768d  mov     eax, ebx
0x18000768f  mov     rcx, [rbp+37h+var_40]
0x180007693  xor     rcx, rsp; StackCookie
0x180007696  call    __security_check_cookie
0x18000769b  add     rsp, 0C0h
0x1800076a2  pop     r14
0x1800076a4  pop     r13
0x1800076a6  pop     r12
0x1800076a8  pop     rdi
0x1800076a9  pop     rsi
0x1800076aa  pop     rbx
0x1800076ab  pop     rbp
0x1800076ac  retn
0x1800076ae  mov     ebx, 80070005h
0x1800076b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800076ba  cmp     rcx, rdi
0x1800076bd  jz      short loc_180007658
0x1800076bf  test    byte ptr [rcx+1Ch], 1
0x1800076c3  jnz     loc_1800078CD
0x1800076c9  cmp     rcx, rdi
0x1800076cc  jz      short loc_180007658
0x1800076ce  test    byte ptr [rcx+1Ch], 1
0x1800076d2  jz      short loc_180007658
0x1800076d4  mov     edx, 31h ; '1'
0x1800076d9  jmp     short loc_1800076FA
0x1800076db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800076e2  cmp     rcx, rdi
0x1800076e5  jz      loc_180007658
0x1800076eb  test    byte ptr [rcx+1Ch], 1
0x1800076ef  jz      loc_180007658
0x1800076f5  mov     edx, 32h ; '2'
0x1800076fa  mov     rcx, [rcx+10h]
0x1800076fe  mov     r9d, ebx
0x180007701  mov     r8, r14
0x180007704  call    WPP_SF_d
0x180007709  jmp     loc_180007658
0x18000770e  mov     dword ptr [r12], 0
0x180007716  cmp     ebx, 0EAh
0x18000771c  jnz     short loc_180007729
0x18000771e  mov     rcx, [rbp+37h+var_90]
0x180007722  mov     eax, [rbp+37h+var_7C]
0x180007725  mov     [rcx], eax
0x180007727  jmp     short loc_180007731
0x180007729  test    ebx, ebx
0x18000772b  jle     loc_180007652
0x180007731  movzx   ebx, bx
0x180007734  or      ebx, 80070000h
0x18000773a  jmp     loc_180007650
0x18000773f  xor     esi, esi
0x180007741  test    ebx, ebx
0x180007743  jns     loc_1800075E3
0x180007749  cmp     rcx, rdi
0x18000774c  jz      loc_1800075E3
0x180007752  test    byte ptr [rcx+1Ch], 1
0x180007756  jz      loc_1800075E3
0x18000775c  lea     edx, [rsi+25h]
0x18000775f  mov     rcx, [rcx+10h]
0x180007763  lea     r8, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids
0x18000776a  mov     r9d, ebx
0x18000776d  call    WPP_SF_d
0x180007772  jmp     loc_1800075E3
0x180007777  jle     short loc_180007782
0x180007779  movzx   ebx, ax
0x18000777c  or      ebx, 80070000h
0x180007782  mov     rcx, cs:WPP_GLOBAL_Control
0x180007789  lea     rdi, WPP_GLOBAL_Control
0x180007790  cmp     rcx, rdi
0x180007793  jz      loc_18000756E
0x180007799  test    byte ptr [rcx+1Ch], 1
0x18000779d  jz      loc_18000756E
0x1800077a3  mov     rcx, [rcx+10h]
0x1800077a7  lea     r8, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids
0x1800077ae  mov     edx, 22h ; '"'
0x1800077b3  mov     r9d, ebx
0x1800077b6  call    WPP_SF_d
0x1800077bb  jmp     loc_180007567
0x1800077c0  call    cs:__imp_GetLastError
0x1800077c7  nop     dword ptr [rax+rax+00h]
0x1800077cc  mov     ebx, eax
0x1800077ce  test    eax, eax
0x1800077d0  jle     short loc_1800077DB
0x1800077d2  movzx   ebx, ax
0x1800077d5  or      ebx, 80070000h
0x1800077db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800077e2  cmp     rcx, rdi
0x1800077e5  jz      loc_180007553
0x1800077eb  test    byte ptr [rcx+1Ch], 1
0x1800077ef  jz      loc_180007553
0x1800077f5  mov     rcx, [rcx+10h]
0x1800077f9  lea     r8, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids
0x180007800  mov     edx, 23h ; '#'
0x180007805  mov     r9d, ebx
0x180007808  call    WPP_SF_d
0x18000780d  jmp     loc_180007553
0x180007812  call    cs:__imp_GetLastError
0x180007819  nop     dword ptr [rax+rax+00h]
0x18000781e  mov     ebx, eax
0x180007820  test    eax, eax
0x180007822  jle     short loc_18000782D
0x180007824  movzx   ebx, ax
0x180007827  or      ebx, 80070000h
0x18000782d  mov     rcx, cs:WPP_GLOBAL_Control
0x180007834  cmp     rcx, rdi
0x180007837  jz      loc_18000773F
0x18000783d  test    byte ptr [rcx+1Ch], 1
0x180007841  jz      loc_18000773F
0x180007847  mov     rcx, [rcx+10h]
0x18000784b  lea     r8, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids
0x180007852  mov     edx, 26h ; '&'
0x180007857  mov     r9d, ebx
0x18000785a  call    WPP_SF_d
0x18000785f  mov     rcx, cs:WPP_GLOBAL_Control
0x180007866  jmp     loc_18000773F
0x18000786b  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "localToken != NULL")
0x180007870  mov     r14, [rbp+37h+TokenHandle]
0x180007874  jmp     loc_180007553
0x180007879  xor     r8d, r8d; __annotation("Debug", "TelemetryAssert", "status == RPC_S_OK", "RpcRevertToSelf")
0x18000787c  lea     rcx, aMpssvcDll_1; "mpssvc.dll"
0x180007883  mov     edx, eax
0x180007885  call    MicrosoftTelemetryAssertTriggeredArgs
0x18000788a  jmp     loc_180007567
0x18000788f  xor     esi, esi
0x180007891  cmp     rcx, rdi
0x180007894  jz      loc_1800075E3
0x18000789a  test    byte ptr [rcx+1Ch], 1
0x18000789e  jz      loc_1800075E3
0x1800078a4  lea     edx, [rsi+24h]
0x1800078a7  jmp     loc_18000775F
0x1800078ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800078b3  cmp     rcx, rdi
0x1800078b6  jz      loc_180007658
0x1800078bc  test    byte ptr [rcx+1Ch], 1
0x1800078c0  jz      loc_1800076C9
0x1800078c6  mov     edx, 10h
0x1800078cb  jmp     short loc_1800078D2
0x1800078cd  mov     edx, 11h
0x1800078d2  mov     rcx, [rcx+10h]
0x1800078d6  mov     r9d, ebx
0x1800078d9  mov     r8, r14
0x1800078dc  call    WPP_SF_d
0x1800078e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800078e8  jmp     loc_1800076C9
0x1800078ed  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "dwBufSize <= cbData")
0x1800078f2  mov     eax, [rbp+37h+var_7C]
0x1800078f5  jmp     loc_18000764C
```
