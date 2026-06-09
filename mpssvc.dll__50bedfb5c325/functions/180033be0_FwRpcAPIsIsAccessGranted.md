# FwRpcAPIsIsAccessGranted

- ea: `0x180033be0`
- end: `0x180033eb6`
- name: `FwRpcAPIsIsAccessGranted`
- size: `726`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR pSecurityDescriptor, RPC_BINDING_HANDLE BindingHandle, DWORD DesiredAccess)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180033418`
- `0x180033b1c`
- `0x1800ccf38`

## callees

- `0x1800089bc`
- `0x18000a710`
- `0x180033be0`
- `0x18006a710`
- `0x1800729c0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180033c31`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180033c31`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180033c50`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180033c50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033dc2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033e1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033dc2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033e1b`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180033cff`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180033cff`
- `RPCRT4!RpcImpersonateClient` at `0x180033c1b`
- `RPCRT4!RpcImpersonateClient` at `0x180033c1b`
- `RPCRT4!RpcRevertToSelf` at `0x180033c7c`
- `RPCRT4!RpcRevertToSelf` at `0x180033c7c`
- `fwbase!FwCloseHandle` at `0x180033d1f`
- `fwbase!FwCloseHandle` at `0x180033d1f`

## string_xrefs

- `0x180033e86`: `mpssvc.dll`

## pseudocode

```c
__int64 __fastcall FwRpcAPIsIsAccessGranted(
        PSECURITY_DESCRIPTOR pSecurityDescriptor,
        RPC_BINDING_HANDLE BindingHandle,
        DWORD DesiredAccess,
        WINBOOL *a4)
{
  void *v5; // rdi
  RPC_STATUS v8; // eax
  unsigned int v9; // ebx
  HANDLE CurrentThread; // rax
  __int64 v11; // rcx
  unsigned int v12; // eax
  __int64 v13; // rcx
  __int64 v15; // rdx
  signed int LastError; // eax
  signed int v17; // eax
  void *TokenHandle; // [rsp+40h] [rbp-88h] BYREF
  WINBOOL AccessStatus; // [rsp+48h] [rbp-80h] BYREF
  DWORD GrantedAccess; // [rsp+4Ch] [rbp-7Ch] BYREF
  DWORD PrivilegeSetLength; // [rsp+50h] [rbp-78h] BYREF
  struct _GENERIC_MAPPING GenericMapping; // [rsp+58h] [rbp-70h] BYREF
  struct _PRIVILEGE_SET PrivilegeSet; // [rsp+68h] [rbp-60h] BYREF

  TokenHandle = 0;
  v5 = 0;
  v8 = RpcImpersonateClient(BindingHandle);
  v9 = v8;
  if ( !v8 )
  {
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    {
      v5 = TokenHandle;
      v9 = 0;
      if ( !TokenHandle )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs(v11);
        v5 = TokenHandle;
      }
    }
    else
    {
      LastError = GetLastError();
      v9 = LastError;
      if ( LastError > 0 )
        v9 = (unsigned __int16)LastError | 0x80070000;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 35, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids, v9);
    }
    v12 = RpcRevertToSelf();
    if ( v12 )
      MicrosoftTelemetryAssertTriggeredArgs("mpssvc.dll", v12, 0);
    goto LABEL_7;
  }
  if ( v8 > 0 )
    v9 = (unsigned __int16)v8 | 0x80070000;
  v13 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 34, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids, v9);
LABEL_7:
    v13 = WPP_GLOBAL_Control;
  }
  if ( (v9 & 0x80000000) != 0 )
  {
    if ( (_UNKNOWN *)v13 != &WPP_GLOBAL_Control && (*(_BYTE *)(v13 + 28) & 1) != 0 )
    {
      v15 = 36;
      goto LABEL_16;
    }
  }
  else
  {
    *(_QWORD *)&GenericMapping.GenericRead = 0;
    *(_QWORD *)&GenericMapping.GenericExecute = 0;
    PrivilegeSetLength = 20;
    GrantedAccess = 0;
    AccessStatus = 0;
    memset(&PrivilegeSet, 0, sizeof(PrivilegeSet));
    if ( AccessCheck(
           pSecurityDescriptor,
           v5,
           DesiredAccess,
           &GenericMapping,
           &PrivilegeSet,
           &PrivilegeSetLength,
           &GrantedAccess,
           &AccessStatus) )
    {
      v9 = 0;
      *a4 = AccessStatus;
      goto LABEL_11;
    }
    v17 = GetLastError();
    v9 = v17;
    if ( v17 > 0 )
      v9 = (unsigned __int16)v17 | 0x80070000;
    v13 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 38, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids, v9);
      v13 = WPP_GLOBAL_Control;
    }
    if ( (v9 & 0x80000000) != 0 && (_UNKNOWN *)v13 != &WPP_GLOBAL_Control && (*(_BYTE *)(v13 + 28) & 1) != 0 )
    {
      v15 = 37;
LABEL_16:
      WPP_SF_d(*(_QWORD *)(v13 + 16), v15, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids, v9);
    }
  }
LABEL_11:
  FwCloseHandle(v5);
  return v9;
}

```

## disassembly

```asm
0x180033be0  push    rbx
0x180033be2  push    rbp
0x180033be3  push    rsi
0x180033be4  push    rdi
0x180033be5  push    r12
0x180033be7  push    r14
0x180033be9  push    r15
0x180033beb  sub     rsp, 90h
0x180033bf2  mov     rax, cs:__security_cookie
0x180033bf9  xor     rax, rsp
0x180033bfc  mov     [rsp+0C8h+var_48], rax
0x180033c04  mov     r14, rcx
0x180033c07  xor     r12d, r12d
0x180033c0a  mov     rcx, rdx; BindingHandle
0x180033c0d  mov     [rsp+0C8h+TokenHandle], r12
0x180033c12  mov     edi, r12d
0x180033c15  mov     rsi, r9
0x180033c18  mov     r15d, r8d
0x180033c1b  call    cs:__imp_RpcImpersonateClient
0x180033c22  nop     dword ptr [rax+rax+00h]
0x180033c27  mov     ebx, eax
0x180033c29  test    eax, eax
0x180033c2b  jnz     loc_180033D79
0x180033c31  call    cs:__imp_GetCurrentThread
0x180033c38  nop     dword ptr [rax+rax+00h]
0x180033c3d  lea     r9, [rsp+0C8h+TokenHandle]; TokenHandle
0x180033c42  mov     edx, 8; DesiredAccess
0x180033c47  mov     rcx, rax; ThreadHandle
0x180033c4a  mov     r8d, 1; OpenAsSelf
0x180033c50  call    cs:__imp_OpenThreadToken
0x180033c57  nop     dword ptr [rax+rax+00h]
0x180033c5c  test    eax, eax
0x180033c5e  jz      loc_180033DC2
0x180033c64  mov     rdi, [rsp+0C8h+TokenHandle]
0x180033c69  mov     ebx, r12d
0x180033c6c  test    rdi, rdi
0x180033c6f  jz      loc_180033E74
0x180033c75  lea     rbp, WPP_GLOBAL_Control
0x180033c7c  call    cs:__imp_RpcRevertToSelf
0x180033c83  nop     dword ptr [rax+rax+00h]
0x180033c88  test    eax, eax
0x180033c8a  jnz     loc_180033E83
0x180033c90  mov     rcx, cs:WPP_GLOBAL_Control
0x180033c97  test    ebx, ebx
0x180033c99  js      loc_180033E99
0x180033c9f  xor     eax, eax
0x180033ca1  mov     qword ptr [rsp+0C8h+GenericMapping.GenericRead], r12
0x180033ca6  mov     [rsp+0C8h+var_60.Privilege.Attributes], eax
0x180033caa  lea     r9, [rsp+0C8h+GenericMapping]; GenericMapping
0x180033caf  lea     rax, [rsp+0C8h+var_80]
0x180033cb4  mov     qword ptr [rsp+0C8h+GenericMapping.GenericExecute], r12
0x180033cb9  mov     [rsp+0C8h+AccessStatus], rax; AccessStatus
0x180033cbe  xorps   xmm0, xmm0
0x180033cc1  lea     rax, [rsp+0C8h+var_7C]
0x180033cc6  mov     [rsp+0C8h+var_78], 14h
0x180033cce  mov     [rsp+0C8h+GrantedAccess], rax; GrantedAccess
0x180033cd3  mov     r8d, r15d; DesiredAccess
0x180033cd6  lea     rax, [rsp+0C8h+var_78]
0x180033cdb  mov     [rsp+0C8h+var_7C], r12d
0x180033ce0  mov     [rsp+0C8h+PrivilegeSetLength], rax; PrivilegeSetLength
0x180033ce5  mov     rdx, rdi; ClientToken
0x180033ce8  lea     rax, [rsp+0C8h+var_60]
0x180033ced  mov     [rsp+0C8h+var_80], r12d
0x180033cf2  mov     rcx, r14; pSecurityDescriptor
0x180033cf5  mov     [rsp+0C8h+PrivilegeSet], rax; PrivilegeSet
0x180033cfa  movups  xmmword ptr [rsp+0C8h+var_60.PrivilegeCount], xmm0
0x180033cff  call    cs:__imp_AccessCheck
0x180033d06  nop     dword ptr [rax+rax+00h]
0x180033d0b  test    eax, eax
0x180033d0d  jz      loc_180033E1B
0x180033d13  mov     eax, [rsp+0C8h+var_80]
0x180033d17  mov     ebx, r12d
0x180033d1a  mov     [rsi], eax
0x180033d1c  mov     rcx, rdi
0x180033d1f  call    cs:__imp_FwCloseHandle
0x180033d26  nop     dword ptr [rax+rax+00h]
0x180033d2b  mov     eax, ebx
0x180033d2d  mov     rcx, [rsp+0C8h+var_48]
0x180033d35  xor     rcx, rsp; StackCookie
0x180033d38  call    __security_check_cookie
0x180033d3d  add     rsp, 90h
0x180033d44  pop     r15
0x180033d46  pop     r14
0x180033d48  pop     r12
0x180033d4a  pop     rdi
0x180033d4b  pop     rsi
0x180033d4c  pop     rbp
0x180033d4d  pop     rbx
0x180033d4e  retn
0x180033d50  test    ebx, ebx
0x180033d52  jns     short loc_180033D1C
0x180033d54  cmp     rcx, rbp
0x180033d57  jz      short loc_180033D1C
0x180033d59  test    byte ptr [rcx+1Ch], 1
0x180033d5d  jz      short loc_180033D1C
0x180033d5f  mov     edx, 25h ; '%'
0x180033d64  mov     rcx, [rcx+10h]
0x180033d68  lea     r8, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids
0x180033d6f  mov     r9d, ebx
0x180033d72  call    WPP_SF_d
0x180033d77  jmp     short loc_180033D1C
0x180033d79  jle     short loc_180033D84
0x180033d7b  movzx   ebx, ax
0x180033d7e  or      ebx, 80070000h
0x180033d84  mov     rcx, cs:WPP_GLOBAL_Control
0x180033d8b  lea     rbp, WPP_GLOBAL_Control
0x180033d92  cmp     rcx, rbp
0x180033d95  jz      loc_180033C97
0x180033d9b  test    byte ptr [rcx+1Ch], 1
0x180033d9f  jz      loc_180033C97
0x180033da5  mov     rcx, [rcx+10h]
0x180033da9  lea     r8, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids
0x180033db0  mov     edx, 22h ; '"'
0x180033db5  mov     r9d, ebx
0x180033db8  call    WPP_SF_d
0x180033dbd  jmp     loc_180033C90
0x180033dc2  call    cs:__imp_GetLastError
0x180033dc9  nop     dword ptr [rax+rax+00h]
0x180033dce  mov     ebx, eax
0x180033dd0  test    eax, eax
0x180033dd2  jle     short loc_180033DDD
0x180033dd4  movzx   ebx, ax
0x180033dd7  or      ebx, 80070000h
0x180033ddd  mov     rcx, cs:WPP_GLOBAL_Control
0x180033de4  lea     rbp, WPP_GLOBAL_Control
0x180033deb  cmp     rcx, rbp
0x180033dee  jz      loc_180033C7C
0x180033df4  test    byte ptr [rcx+1Ch], 1
0x180033df8  jz      loc_180033C7C
0x180033dfe  mov     rcx, [rcx+10h]
0x180033e02  lea     r8, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids
0x180033e09  mov     edx, 23h ; '#'
0x180033e0e  mov     r9d, ebx
0x180033e11  call    WPP_SF_d
0x180033e16  jmp     loc_180033C7C
0x180033e1b  call    cs:__imp_GetLastError
0x180033e22  nop     dword ptr [rax+rax+00h]
0x180033e27  mov     ebx, eax
0x180033e29  test    eax, eax
0x180033e2b  jle     short loc_180033E36
0x180033e2d  movzx   ebx, ax
0x180033e30  or      ebx, 80070000h
0x180033e36  mov     rcx, cs:WPP_GLOBAL_Control
0x180033e3d  cmp     rcx, rbp
0x180033e40  jz      loc_180033D50
0x180033e46  test    byte ptr [rcx+1Ch], 1
0x180033e4a  jz      loc_180033D50
0x180033e50  mov     rcx, [rcx+10h]
0x180033e54  lea     r8, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids
0x180033e5b  mov     edx, 26h ; '&'
0x180033e60  mov     r9d, ebx
0x180033e63  call    WPP_SF_d
0x180033e68  mov     rcx, cs:WPP_GLOBAL_Control
0x180033e6f  jmp     loc_180033D50
0x180033e74  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "localToken != NULL")
0x180033e79  mov     rdi, [rsp+0C8h+TokenHandle]
0x180033e7e  jmp     loc_180033C75
0x180033e83  xor     r8d, r8d; __annotation("Debug", "TelemetryAssert", "status == RPC_S_OK", "RpcRevertToSelf")
0x180033e86  lea     rcx, aMpssvcDll_1; "mpssvc.dll"
0x180033e8d  mov     edx, eax
0x180033e8f  call    MicrosoftTelemetryAssertTriggeredArgs
0x180033e94  jmp     loc_180033C90
0x180033e99  cmp     rcx, rbp
0x180033e9c  jz      loc_180033D1C
0x180033ea2  test    byte ptr [rcx+1Ch], 1
0x180033ea6  jz      loc_180033D1C
0x180033eac  mov     edx, 24h ; '$'
0x180033eb1  jmp     loc_180033D64
```
