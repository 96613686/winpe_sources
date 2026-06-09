# FwRpcAPIsSecModeAccessCheckForClient

- ea: `0x180036b64`
- end: `0x180036ec4`
- name: `FwRpcAPIsSecModeAccessCheckForClient`
- size: `864`
- prototype: ``
- caller_count: `144`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180034fe0`
- `0x180035500`
- `0x180035ab0`
- `0x180035b90`
- `0x180036360`
- `0x180036560`
- `0x1800366d0`
- `0x180036980`
- `0x1800379f0`
- `0x180041240`
- `0x180054c30`
- `0x180057b50`
- `0x180059af0`
- `0x18005a730`
- `0x18005cf60`
- `0x18005ffb0`
- `0x18006f7d0`
- `0x18006f8b0`
- `0x180070d70`
- `0x1800999a4`
- `0x1800a2578`
- `0x1800c6120`
- `0x1800c6200`
- `0x1800c62e0`
- `0x1800c63c0`
- `0x1800c64a0`
- `0x1800c6580`
- `0x1800c6660`
- `0x1800c6740`
- `0x1800c6820`
- `0x1800c6900`
- `0x1800c69e0`
- `0x1800c6ac0`
- `0x1800c6ba0`
- `0x1800c6c80`
- `0x1800c6d60`
- `0x1800c6e40`
- `0x1800c6f20`
- `0x1800c7000`
- `0x1800c70e0`
- `0x1800c71c0`
- `0x1800c72a0`
- `0x1800c7350`
- `0x1800c7430`
- `0x1800c7510`
- `0x1800c75f0`
- `0x1800c76b0`
- `0x1800c7790`
- `0x1800c7870`
- `0x1800c7930`

## callees

- `0x1800089bc`
- `0x18000a710`
- `0x180036b64`
- `0x18006a710`
- `0x1800729c0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180036bf3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180036bf3`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180036c0d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180036c0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036dbc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036e0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036dbc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036e0a`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180036cae`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180036cae`
- `RPCRT4!RpcImpersonateClient` at `0x180036bdd`
- `RPCRT4!RpcImpersonateClient` at `0x180036bdd`
- `RPCRT4!RpcRevertToSelf` at `0x180036c3a`
- `RPCRT4!RpcRevertToSelf` at `0x180036c3a`
- `bcrypt!BCryptGetFipsAlgorithmMode` at `0x180036b99`
- `bcrypt!BCryptGetFipsAlgorithmMode` at `0x180036b99`
- `fwbase!FwCloseHandle` at `0x180036cca`
- `fwbase!FwCloseHandle` at `0x180036cca`

## string_xrefs

- `0x180036e70`: `mpssvc.dll`

## pseudocode

```c
__int64 __fastcall FwRpcAPIsSecModeAccessCheckForClient(unsigned int a1, int a2, void *a3)
{
  __int64 v3; // rbx
  __int64 v5; // rdi
  __int64 v6; // rcx
  DWORD v7; // r15d
  void *v8; // r14
  void *v9; // r12
  RPC_STATUS v10; // eax
  unsigned int v11; // ebx
  HANDLE CurrentThread; // rax
  __int64 v13; // rcx
  unsigned int v14; // eax
  __int64 v15; // rcx
  WINBOOL v16; // edi
  __int64 v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // rdx
  signed int LastError; // eax
  signed int v22; // eax
  void *TokenHandle; // [rsp+40h] [rbp-29h] BYREF
  BOOLEAN pfEnabled[4]; // [rsp+48h] [rbp-21h] BYREF
  WINBOOL AccessStatus; // [rsp+4Ch] [rbp-1Dh] BYREF
  DWORD GrantedAccess; // [rsp+50h] [rbp-19h] BYREF
  DWORD PrivilegeSetLength; // [rsp+54h] [rbp-15h] BYREF
  struct _PRIVILEGE_SET PrivilegeSet; // [rsp+58h] [rbp-11h] BYREF
  struct _GENERIC_MAPPING GenericMapping; // [rsp+70h] [rbp+7h] BYREF

  v3 = a1;
  v5 = a2;
  pfEnabled[0] = 0;
  if ( BCryptGetFipsAlgorithmMode(pfEnabled) >= 0 && pfEnabled[0] )
    v6 = 3;
  else
    v6 = 0;
  TokenHandle = 0;
  v7 = *((_DWORD *)&AccessCheckAccessRights + v5);
  v8 = 0;
  v9 = (void *)qword_180132A18[v6 + v3];
  v10 = RpcImpersonateClient(a3);
  v11 = v10;
  if ( !v10 )
  {
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    {
      v8 = TokenHandle;
      if ( !TokenHandle )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs(v13);
        v8 = TokenHandle;
      }
    }
    else
    {
      LastError = GetLastError();
      v11 = LastError;
      if ( LastError > 0 )
        v11 = (unsigned __int16)LastError | 0x80070000;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 35, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids, v11);
    }
    v14 = RpcRevertToSelf();
    if ( v14 )
      MicrosoftTelemetryAssertTriggeredArgs("mpssvc.dll", v14, 0);
    goto LABEL_10;
  }
  if ( v10 > 0 )
    v11 = (unsigned __int16)v10 | 0x80070000;
  v15 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 34, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids, v11);
LABEL_10:
    v15 = WPP_GLOBAL_Control;
  }
  if ( (v11 & 0x80000000) != 0 )
  {
    v16 = 0;
    if ( (_UNKNOWN *)v15 != &WPP_GLOBAL_Control && (*(_BYTE *)(v15 + 28) & 1) != 0 )
    {
      v20 = 36;
      goto LABEL_26;
    }
  }
  else
  {
    PrivilegeSetLength = 20;
    GrantedAccess = 0;
    AccessStatus = 0;
    GenericMapping = 0;
    memset(&PrivilegeSet, 0, sizeof(PrivilegeSet));
    if ( AccessCheck(v9, v8, v7, &GenericMapping, &PrivilegeSet, &PrivilegeSetLength, &GrantedAccess, &AccessStatus) )
    {
      v16 = AccessStatus;
      v11 = 0;
      goto LABEL_14;
    }
    v22 = GetLastError();
    v11 = v22;
    if ( v22 > 0 )
      v11 = (unsigned __int16)v22 | 0x80070000;
    v15 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 38, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids, v11);
      v15 = WPP_GLOBAL_Control;
    }
    v16 = 0;
    if ( (v11 & 0x80000000) != 0 && (_UNKNOWN *)v15 != &WPP_GLOBAL_Control && (*(_BYTE *)(v15 + 28) & 1) != 0 )
    {
      v20 = 37;
LABEL_26:
      WPP_SF_d(*(_QWORD *)(v15 + 16), v20, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids, v11);
    }
  }
LABEL_14:
  FwCloseHandle(v8);
  if ( (v11 & 0x80000000) != 0 )
  {
    v18 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v19 = 16;
      goto LABEL_20;
    }
  }
  else if ( !v16 )
  {
    v11 = -2147024891;
    v18 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v19 = 17;
LABEL_20:
      WPP_SF_d(*(_QWORD *)(v18 + 16), v19, WPP_bc95a2d00ecc337a62d9dd8dc7f02b78_Traceguids, v11);
    }
  }
  return v11;
}

```

## disassembly

```asm
0x180036b64  push    rbp
0x180036b66  push    rbx
0x180036b67  push    rsi
0x180036b68  push    rdi
0x180036b69  push    r12
0x180036b6b  push    r14
0x180036b6d  push    r15
0x180036b6f  lea     rbp, [rsp-27h]
0x180036b74  sub     rsp, 90h
0x180036b7b  mov     rax, cs:__security_cookie
0x180036b82  xor     rax, rsp
0x180036b85  mov     [rbp+57h+var_40], rax
0x180036b89  mov     ebx, ecx
0x180036b8b  mov     rsi, r8
0x180036b8e  lea     rcx, [rbp+57h+pfEnabled]; pfEnabled
0x180036b92  movsxd  rdi, edx
0x180036b95  mov     [rbp+57h+pfEnabled], 0
0x180036b99  call    cs:__imp_BCryptGetFipsAlgorithmMode
0x180036ba0  nop     dword ptr [rax+rax+00h]
0x180036ba5  test    eax, eax
0x180036ba7  js      short loc_180036BB3
0x180036ba9  cmp     [rbp+57h+pfEnabled], 0
0x180036bad  jnz     loc_180036D34
0x180036bb3  xor     ecx, ecx
0x180036bb5  add     rbx, rcx
0x180036bb8  mov     [rbp+57h+TokenHandle], 0
0x180036bc0  lea     r12, __ImageBase
0x180036bc7  mov     rcx, rsi; BindingHandle
0x180036bca  mov     r15d, ds:rva ?AccessCheckAccessRights@@3PAKA[r12+rdi*4]; ulong near * AccessCheckAccessRights ...
0x180036bd2  xor     r14d, r14d
0x180036bd5  mov     r12, rva qword_180132A18[r12+rbx*8]
0x180036bdd  call    cs:__imp_RpcImpersonateClient
0x180036be4  nop     dword ptr [rax+rax+00h]
0x180036be9  mov     ebx, eax
0x180036beb  test    eax, eax
0x180036bed  jnz     loc_180036D72
0x180036bf3  call    cs:__imp_GetCurrentThread
0x180036bfa  nop     dword ptr [rax+rax+00h]
0x180036bff  mov     rcx, rax; ThreadHandle
0x180036c02  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x180036c06  lea     edx, [rbx+8]; DesiredAccess
0x180036c09  lea     r8d, [r14+1]; OpenAsSelf
0x180036c0d  call    cs:__imp_OpenThreadToken
0x180036c14  nop     dword ptr [rax+rax+00h]
0x180036c19  mov     edi, 80070000h
0x180036c1e  lea     rsi, WPP_GLOBAL_Control
0x180036c25  test    eax, eax
0x180036c27  jz      loc_180036DBC
0x180036c2d  mov     r14, [rbp+57h+TokenHandle]
0x180036c31  test    r14, r14
0x180036c34  jz      loc_180036E5F
0x180036c3a  call    cs:__imp_RpcRevertToSelf
0x180036c41  nop     dword ptr [rax+rax+00h]
0x180036c46  test    eax, eax
0x180036c48  jnz     loc_180036E6D
0x180036c4e  mov     rcx, cs:WPP_GLOBAL_Control
0x180036c55  test    ebx, ebx
0x180036c57  js      loc_180036E83
0x180036c5d  xor     eax, eax
0x180036c5f  mov     [rbp+57h+var_6C], 14h
0x180036c66  mov     [rbp+57h+var_68.Privilege.Attributes], eax
0x180036c69  lea     r9, [rbp+57h+GenericMapping]; GenericMapping
0x180036c6d  mov     [rbp+57h+var_70], eax
0x180036c70  xorps   xmm0, xmm0
0x180036c73  mov     [rbp+57h+var_74], eax
0x180036c76  xorps   xmm1, xmm1
0x180036c79  lea     rax, [rbp+57h+var_74]
0x180036c7d  mov     r8d, r15d; DesiredAccess
0x180036c80  mov     [rsp+0C0h+AccessStatus], rax; AccessStatus
0x180036c85  mov     rdx, r14; ClientToken
0x180036c88  lea     rax, [rbp+57h+var_70]
0x180036c8c  mov     rcx, r12; pSecurityDescriptor
0x180036c8f  mov     [rsp+0C0h+GrantedAccess], rax; GrantedAccess
0x180036c94  lea     rax, [rbp+57h+var_6C]
0x180036c98  mov     [rsp+0C0h+PrivilegeSetLength], rax; PrivilegeSetLength
0x180036c9d  lea     rax, [rbp+57h+var_68]
0x180036ca1  mov     [rsp+0C0h+PrivilegeSet], rax; PrivilegeSet
0x180036ca6  movups  xmmword ptr [rbp+57h+GenericMapping.GenericRead], xmm0
0x180036caa  movups  xmmword ptr [rbp+57h+var_68.PrivilegeCount], xmm1
0x180036cae  call    cs:__imp_AccessCheck
0x180036cb5  nop     dword ptr [rax+rax+00h]
0x180036cba  test    eax, eax
0x180036cbc  jz      loc_180036E0A
0x180036cc2  mov     edi, [rbp+57h+var_74]
0x180036cc5  xor     ebx, ebx
0x180036cc7  mov     rcx, r14
0x180036cca  call    cs:__imp_FwCloseHandle
0x180036cd1  nop     dword ptr [rax+rax+00h]
0x180036cd6  test    ebx, ebx
0x180036cd8  js      loc_180036EA0
0x180036cde  test    edi, edi
0x180036ce0  jz      short loc_180036D03
0x180036ce2  mov     eax, ebx
0x180036ce4  mov     rcx, [rbp+57h+var_40]
0x180036ce8  xor     rcx, rsp; StackCookie
0x180036ceb  call    __security_check_cookie
0x180036cf0  add     rsp, 90h
0x180036cf7  pop     r15
0x180036cf9  pop     r14
0x180036cfb  pop     r12
0x180036cfd  pop     rdi
0x180036cfe  pop     rsi
0x180036cff  pop     rbx
0x180036d00  pop     rbp
0x180036d01  retn
0x180036d03  mov     ebx, 80070005h
0x180036d08  mov     rcx, cs:WPP_GLOBAL_Control
0x180036d0f  cmp     rcx, rsi
0x180036d12  jz      short loc_180036CE2
0x180036d14  test    byte ptr [rcx+1Ch], 1
0x180036d18  jz      short loc_180036CE2
0x180036d1a  mov     edx, 11h
0x180036d1f  mov     rcx, [rcx+10h]
0x180036d23  lea     r8, WPP_bc95a2d00ecc337a62d9dd8dc7f02b78_Traceguids
0x180036d2a  mov     r9d, ebx
0x180036d2d  call    WPP_SF_d
0x180036d32  jmp     short loc_180036CE2
0x180036d34  mov     ecx, 3
0x180036d39  jmp     loc_180036BB5
0x180036d3e  xor     edi, edi
0x180036d40  test    ebx, ebx
0x180036d42  jns     short loc_180036CC7
0x180036d44  cmp     rcx, rsi
0x180036d47  jz      loc_180036CC7
0x180036d4d  test    byte ptr [rcx+1Ch], 1
0x180036d51  jz      loc_180036CC7
0x180036d57  lea     edx, [rdi+25h]
0x180036d5a  mov     rcx, [rcx+10h]
0x180036d5e  lea     r8, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids
0x180036d65  mov     r9d, ebx
0x180036d68  call    WPP_SF_d
0x180036d6d  jmp     loc_180036CC7
0x180036d72  mov     edi, 80070000h
0x180036d77  jle     short loc_180036D7E
0x180036d79  movzx   ebx, ax
0x180036d7c  or      ebx, edi
0x180036d7e  mov     rcx, cs:WPP_GLOBAL_Control
0x180036d85  lea     rsi, WPP_GLOBAL_Control
0x180036d8c  cmp     rcx, rsi
0x180036d8f  jz      loc_180036C55
0x180036d95  test    byte ptr [rcx+1Ch], 1
0x180036d99  jz      loc_180036C55
0x180036d9f  mov     rcx, [rcx+10h]
0x180036da3  lea     r8, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids
0x180036daa  mov     edx, 22h ; '"'
0x180036daf  mov     r9d, ebx
0x180036db2  call    WPP_SF_d
0x180036db7  jmp     loc_180036C4E
0x180036dbc  call    cs:__imp_GetLastError
0x180036dc3  nop     dword ptr [rax+rax+00h]
0x180036dc8  mov     ebx, eax
0x180036dca  test    eax, eax
0x180036dcc  jle     short loc_180036DD3
0x180036dce  movzx   ebx, ax
0x180036dd1  or      ebx, edi
0x180036dd3  mov     rcx, cs:WPP_GLOBAL_Control
0x180036dda  cmp     rcx, rsi
0x180036ddd  jz      loc_180036C3A
0x180036de3  test    byte ptr [rcx+1Ch], 1
0x180036de7  jz      loc_180036C3A
0x180036ded  mov     rcx, [rcx+10h]
0x180036df1  lea     r8, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids
0x180036df8  mov     edx, 23h ; '#'
0x180036dfd  mov     r9d, ebx
0x180036e00  call    WPP_SF_d
0x180036e05  jmp     loc_180036C3A
0x180036e0a  call    cs:__imp_GetLastError
0x180036e11  nop     dword ptr [rax+rax+00h]
0x180036e16  mov     ebx, eax
0x180036e18  test    eax, eax
0x180036e1a  jle     short loc_180036E21
0x180036e1c  movzx   ebx, ax
0x180036e1f  or      ebx, edi
0x180036e21  mov     rcx, cs:WPP_GLOBAL_Control
0x180036e28  cmp     rcx, rsi
0x180036e2b  jz      loc_180036D3E
0x180036e31  test    byte ptr [rcx+1Ch], 1
0x180036e35  jz      loc_180036D3E
0x180036e3b  mov     rcx, [rcx+10h]
0x180036e3f  lea     r8, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids
0x180036e46  mov     edx, 26h ; '&'
0x180036e4b  mov     r9d, ebx
0x180036e4e  call    WPP_SF_d
0x180036e53  mov     rcx, cs:WPP_GLOBAL_Control
0x180036e5a  jmp     loc_180036D3E
0x180036e5f  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "localToken != NULL")
0x180036e64  mov     r14, [rbp+57h+TokenHandle]
0x180036e68  jmp     loc_180036C3A
0x180036e6d  xor     r8d, r8d; __annotation("Debug", "TelemetryAssert", "status == RPC_S_OK", "RpcRevertToSelf")
0x180036e70  lea     rcx, aMpssvcDll_1; "mpssvc.dll"
0x180036e77  mov     edx, eax
0x180036e79  call    MicrosoftTelemetryAssertTriggeredArgs
0x180036e7e  jmp     loc_180036C4E
0x180036e83  xor     edi, edi
0x180036e85  cmp     rcx, rsi
0x180036e88  jz      loc_180036CC7
0x180036e8e  test    byte ptr [rcx+1Ch], 1
0x180036e92  jz      loc_180036CC7
0x180036e98  lea     edx, [rdi+24h]
0x180036e9b  jmp     loc_180036D5A
0x180036ea0  mov     rcx, cs:WPP_GLOBAL_Control
0x180036ea7  cmp     rcx, rsi
0x180036eaa  jz      loc_180036CE2
0x180036eb0  test    byte ptr [rcx+1Ch], 1
0x180036eb4  jz      loc_180036CE2
0x180036eba  mov     edx, 10h
0x180036ebf  jmp     loc_180036D1F
```
