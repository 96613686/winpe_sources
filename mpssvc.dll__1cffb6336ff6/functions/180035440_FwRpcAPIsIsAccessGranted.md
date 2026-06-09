# FwRpcAPIsIsAccessGranted

- ea: `0x180035440`
- end: `0x1800356e5`
- name: `FwRpcAPIsIsAccessGranted`
- size: `677`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR pSecurityDescriptor, RPC_BINDING_HANDLE BindingHandle, DWORD DesiredAccess)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180034cb8`
- `0x180035384`
- `0x1800c5a88`

## callees

- `0x1800093b0`
- `0x18000af3c`
- `0x180035440`
- `0x1800670c0`
- `0x18006f520`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800354a4`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800354a4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003548b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003548b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800355fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035650`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800355fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035650`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180035547`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180035547`
- `RPCRT4!RpcRevertToSelf` at `0x1800354ca`
- `RPCRT4!RpcRevertToSelf` at `0x1800354ca`
- `RPCRT4!RpcImpersonateClient` at `0x18003547b`
- `RPCRT4!RpcImpersonateClient` at `0x18003547b`
- `fwbase!FwCloseHandle` at `0x180035561`
- `fwbase!FwCloseHandle` at `0x180035561`

## string_xrefs

- `0x1800356b5`: `mpssvc.dll`

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
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // r9
  unsigned int v15; // eax
  __int64 v16; // rcx
  __int64 v18; // rdx
  signed int LastError; // eax
  signed int v20; // eax
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
        MicrosoftTelemetryAssertTriggeredNoArgs(v12, v11, v13, v14);
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
    v15 = RpcRevertToSelf();
    if ( v15 )
      MicrosoftTelemetryAssertTriggeredArgs("mpssvc.dll", v15, 0);
    goto LABEL_7;
  }
  if ( v8 > 0 )
    v9 = (unsigned __int16)v8 | 0x80070000;
  v16 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 34, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids, v9);
LABEL_7:
    v16 = WPP_GLOBAL_Control;
  }
  if ( (v9 & 0x80000000) != 0 )
  {
    if ( (_UNKNOWN *)v16 != &WPP_GLOBAL_Control && (*(_BYTE *)(v16 + 28) & 1) != 0 )
    {
      v18 = 36;
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
    v20 = GetLastError();
    v9 = v20;
    if ( v20 > 0 )
      v9 = (unsigned __int16)v20 | 0x80070000;
    v16 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 38, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids, v9);
      v16 = WPP_GLOBAL_Control;
    }
    if ( (v9 & 0x80000000) != 0 && (_UNKNOWN *)v16 != &WPP_GLOBAL_Control && (*(_BYTE *)(v16 + 28) & 1) != 0 )
    {
      v18 = 37;
LABEL_16:
      WPP_SF_d(*(_QWORD *)(v16 + 16), v18, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids, v9);
    }
  }
LABEL_11:
  FwCloseHandle(v5);
  return v9;
}

```

## disassembly

```asm
0x180035440  push    rbx
0x180035442  push    rbp
0x180035443  push    rsi
0x180035444  push    rdi
0x180035445  push    r12
0x180035447  push    r14
0x180035449  push    r15
0x18003544b  sub     rsp, 90h
0x180035452  mov     rax, cs:__security_cookie
0x180035459  xor     rax, rsp
0x18003545c  mov     [rsp+0C8h+var_48], rax
0x180035464  mov     r14, rcx
0x180035467  xor     r12d, r12d
0x18003546a  mov     rcx, rdx; BindingHandle
0x18003546d  mov     [rsp+0C8h+TokenHandle], r12
0x180035472  mov     edi, r12d
0x180035475  mov     rsi, r9
0x180035478  mov     r15d, r8d
0x18003547b  call    cs:__imp_RpcImpersonateClient
0x180035481  mov     ebx, eax
0x180035483  test    eax, eax
0x180035485  jnz     loc_1800355B4
0x18003548b  call    cs:__imp_GetCurrentThread
0x180035491  lea     r9, [rsp+0C8h+TokenHandle]; TokenHandle
0x180035496  mov     edx, 8; DesiredAccess
0x18003549b  mov     rcx, rax; ThreadHandle
0x18003549e  mov     r8d, 1; OpenAsSelf
0x1800354a4  call    cs:__imp_OpenThreadToken
0x1800354aa  test    eax, eax
0x1800354ac  jz      loc_1800355FD
0x1800354b2  mov     rdi, [rsp+0C8h+TokenHandle]
0x1800354b7  mov     ebx, r12d
0x1800354ba  test    rdi, rdi
0x1800354bd  jz      loc_1800356A3
0x1800354c3  lea     rbp, WPP_GLOBAL_Control
0x1800354ca  call    cs:__imp_RpcRevertToSelf
0x1800354d0  test    eax, eax
0x1800354d2  jnz     loc_1800356B2
0x1800354d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800354df  test    ebx, ebx
0x1800354e1  js      loc_1800356C8
0x1800354e7  xor     eax, eax
0x1800354e9  mov     qword ptr [rsp+0C8h+GenericMapping.GenericRead], r12
0x1800354ee  mov     [rsp+0C8h+var_60.Privilege.Attributes], eax
0x1800354f2  lea     r9, [rsp+0C8h+GenericMapping]; GenericMapping
0x1800354f7  lea     rax, [rsp+0C8h+var_80]
0x1800354fc  mov     qword ptr [rsp+0C8h+GenericMapping.GenericExecute], r12
0x180035501  mov     [rsp+0C8h+AccessStatus], rax; AccessStatus
0x180035506  xorps   xmm0, xmm0
0x180035509  lea     rax, [rsp+0C8h+var_7C]
0x18003550e  mov     [rsp+0C8h+var_78], 14h
0x180035516  mov     [rsp+0C8h+GrantedAccess], rax; GrantedAccess
0x18003551b  mov     r8d, r15d; DesiredAccess
0x18003551e  lea     rax, [rsp+0C8h+var_78]
0x180035523  mov     [rsp+0C8h+var_7C], r12d
0x180035528  mov     [rsp+0C8h+PrivilegeSetLength], rax; PrivilegeSetLength
0x18003552d  mov     rdx, rdi; ClientToken
0x180035530  lea     rax, [rsp+0C8h+var_60]
0x180035535  mov     [rsp+0C8h+var_80], r12d
0x18003553a  mov     rcx, r14; pSecurityDescriptor
0x18003553d  mov     [rsp+0C8h+PrivilegeSet], rax; PrivilegeSet
0x180035542  movups  xmmword ptr [rsp+0C8h+var_60.PrivilegeCount], xmm0
0x180035547  call    cs:__imp_AccessCheck
0x18003554d  test    eax, eax
0x18003554f  jz      loc_180035650
0x180035555  mov     eax, [rsp+0C8h+var_80]
0x180035559  mov     ebx, r12d
0x18003555c  mov     [rsi], eax
0x18003555e  mov     rcx, rdi
0x180035561  call    cs:__imp_FwCloseHandle
0x180035567  mov     eax, ebx
0x180035569  mov     rcx, [rsp+0C8h+var_48]
0x180035571  xor     rcx, rsp; StackCookie
0x180035574  call    __security_check_cookie
0x180035579  add     rsp, 90h
0x180035580  pop     r15
0x180035582  pop     r14
0x180035584  pop     r12
0x180035586  pop     rdi
0x180035587  pop     rsi
0x180035588  pop     rbp
0x180035589  pop     rbx
0x18003558a  retn
0x18003558b  test    ebx, ebx
0x18003558d  jns     short loc_18003555E
0x18003558f  cmp     rcx, rbp
0x180035592  jz      short loc_18003555E
0x180035594  test    byte ptr [rcx+1Ch], 1
0x180035598  jz      short loc_18003555E
0x18003559a  mov     edx, 25h ; '%'
0x18003559f  mov     rcx, [rcx+10h]
0x1800355a3  lea     r8, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids
0x1800355aa  mov     r9d, ebx
0x1800355ad  call    WPP_SF_d
0x1800355b2  jmp     short loc_18003555E
0x1800355b4  jle     short loc_1800355BF
0x1800355b6  movzx   ebx, ax
0x1800355b9  or      ebx, 80070000h
0x1800355bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800355c6  lea     rbp, WPP_GLOBAL_Control
0x1800355cd  cmp     rcx, rbp
0x1800355d0  jz      loc_1800354DF
0x1800355d6  test    byte ptr [rcx+1Ch], 1
0x1800355da  jz      loc_1800354DF
0x1800355e0  mov     rcx, [rcx+10h]
0x1800355e4  lea     r8, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids
0x1800355eb  mov     edx, 22h ; '"'
0x1800355f0  mov     r9d, ebx
0x1800355f3  call    WPP_SF_d
0x1800355f8  jmp     loc_1800354D8
0x1800355fd  call    cs:__imp_GetLastError
0x180035603  mov     ebx, eax
0x180035605  test    eax, eax
0x180035607  jle     short loc_180035612
0x180035609  movzx   ebx, ax
0x18003560c  or      ebx, 80070000h
0x180035612  mov     rcx, cs:WPP_GLOBAL_Control
0x180035619  lea     rbp, WPP_GLOBAL_Control
0x180035620  cmp     rcx, rbp
0x180035623  jz      loc_1800354CA
0x180035629  test    byte ptr [rcx+1Ch], 1
0x18003562d  jz      loc_1800354CA
0x180035633  mov     rcx, [rcx+10h]
0x180035637  lea     r8, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids
0x18003563e  mov     edx, 23h ; '#'
0x180035643  mov     r9d, ebx
0x180035646  call    WPP_SF_d
0x18003564b  jmp     loc_1800354CA
0x180035650  call    cs:__imp_GetLastError
0x180035656  mov     ebx, eax
0x180035658  test    eax, eax
0x18003565a  jle     short loc_180035665
0x18003565c  movzx   ebx, ax
0x18003565f  or      ebx, 80070000h
0x180035665  mov     rcx, cs:WPP_GLOBAL_Control
0x18003566c  cmp     rcx, rbp
0x18003566f  jz      loc_18003558B
0x180035675  test    byte ptr [rcx+1Ch], 1
0x180035679  jz      loc_18003558B
0x18003567f  mov     rcx, [rcx+10h]
0x180035683  lea     r8, WPP_65bd1baa20cd3956fe3ec5870191be58_Traceguids
0x18003568a  mov     edx, 26h ; '&'
0x18003568f  mov     r9d, ebx
0x180035692  call    WPP_SF_d
0x180035697  mov     rcx, cs:WPP_GLOBAL_Control
0x18003569e  jmp     loc_18003558B
0x1800356a3  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800356a8  mov     rdi, [rsp+0C8h+TokenHandle]
0x1800356ad  jmp     loc_1800354C3
0x1800356b2  xor     r8d, r8d
0x1800356b5  lea     rcx, aMpssvcDll_1; "mpssvc.dll"
0x1800356bc  mov     edx, eax
0x1800356be  call    MicrosoftTelemetryAssertTriggeredArgs
0x1800356c3  jmp     loc_1800354D8
0x1800356c8  cmp     rcx, rbp
0x1800356cb  jz      loc_18003555E
0x1800356d1  test    byte ptr [rcx+1Ch], 1
0x1800356d5  jz      loc_18003555E
0x1800356db  mov     edx, 24h ; '$'
0x1800356e0  jmp     loc_18003559F
```
