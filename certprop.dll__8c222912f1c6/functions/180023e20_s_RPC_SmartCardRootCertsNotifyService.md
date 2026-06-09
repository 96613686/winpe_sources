# s_RPC_SmartCardRootCertsNotifyService

- ea: `0x180023e20`
- end: `0x180024007`
- name: `s_RPC_SmartCardRootCertsNotifyService`
- size: `487`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x1800185d8`
- `0x180018b58`
- `0x180018bb4`
- `0x1800232c4`
- `0x1800238a4`
- `0x180023e20`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180023ec2`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180023ec2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180023ead`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180023ead`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180023f12`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180023f12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023ecc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023f1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023ecc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023f1c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023f87`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023f95`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023f87`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023f95`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180023fb0`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180023fb0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180023f63`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180023f63`
- `RPCRT4!RpcImpersonateClient` at `0x180023e91`
- `RPCRT4!RpcImpersonateClient` at `0x180023f32`
- `RPCRT4!RpcImpersonateClient` at `0x180023e91`
- `RPCRT4!RpcImpersonateClient` at `0x180023f32`
- `RPCRT4!RpcRevertToSelf` at `0x180023ed7`
- `RPCRT4!RpcRevertToSelf` at `0x180023fa0`
- `RPCRT4!RpcRevertToSelf` at `0x180023ed7`
- `RPCRT4!RpcRevertToSelf` at `0x180023fa0`

## pseudocode

```c
__int64 __fastcall s_RPC_SmartCardRootCertsNotifyService(__int64 a1)
{
  int v1; // r15d
  HANDLE v2; // rdi
  DWORD v3; // ebx
  int v4; // esi
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  unsigned int v7; // eax
  int v8; // r14d
  void *v9; // rcx
  void *v10; // rcx
  RPC_STATUS v11; // eax
  void *TokenHandle; // [rsp+30h] [rbp-10h] BYREF
  HANDLE Token; // [rsp+38h] [rbp-8h] BYREF
  int v15; // [rsp+88h] [rbp+48h] BYREF
  unsigned int TokenInformation; // [rsp+90h] [rbp+50h] BYREF
  DWORD ReturnLength; // [rsp+98h] [rbp+58h] BYREF

  v1 = 0;
  TokenHandle = 0;
  v2 = 0;
  TokenInformation = 0;
  ReturnLength = 0;
  v15 = 0;
  Token = 0;
  WppTraceIndent(a1, 0);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 2) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_6bc86d6463543fa2cd93c11fe697381a_Traceguids, WPP_pszIndent);
  }
  v3 = RpcImpersonateClient(0);
  if ( v3 )
  {
    v4 = 0;
    goto LABEL_23;
  }
  v4 = 1;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xEu, 1, &TokenHandle) )
  {
    LastError = GetLastError();
LABEL_22:
    v3 = LastError;
    goto LABEL_23;
  }
  v3 = RpcRevertToSelf();
  if ( !v3 )
  {
    v4 = 0;
    v7 = CheckForLowIntegrityAndGenerateMediumIntegrityToken(TokenHandle, &Token, &v15);
    v2 = Token;
    v3 = v7;
    if ( !v7 )
    {
      v8 = v15;
      if ( v15 )
      {
        if ( !SetThreadToken(0, Token) )
        {
LABEL_13:
          v3 = GetLastError();
          goto LABEL_23;
        }
        v1 = 1;
LABEL_18:
        v9 = TokenHandle;
        if ( v8 )
          v9 = v2;
        if ( GetTokenInformation(v9, TokenSessionId, &TokenInformation, 4u, &ReturnLength) )
        {
          LastError = CertPropUpdateRootCertificatesRpcCallout(TokenInformation);
          goto LABEL_22;
        }
        goto LABEL_13;
      }
      v3 = RpcImpersonateClient(0);
      if ( !v3 )
      {
        v4 = 1;
        goto LABEL_18;
      }
    }
  }
LABEL_23:
  v10 = TokenHandle;
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( v2 )
    CloseHandle(v2);
  if ( v4 == 1 )
  {
    v11 = RpcRevertToSelf();
    if ( v11 )
      v3 = v11;
  }
  if ( v1 == 1 )
    RevertToSelf();
  WppTraceIndent(v10, 1);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 2) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      16,
      (unsigned int)WPP_6bc86d6463543fa2cd93c11fe697381a_Traceguids,
      (_DWORD)WPP_pszIndent,
      v3);
  }
  return v3;
}

```

## disassembly

```asm
0x180023e20  push    rbp
0x180023e22  push    rbx
0x180023e23  push    rsi
0x180023e24  push    rdi
0x180023e25  push    r13
0x180023e27  push    r14
0x180023e29  push    r15
0x180023e2b  mov     rbp, rsp
0x180023e2e  sub     rsp, 40h
0x180023e32  xor     r15d, r15d
0x180023e35  mov     [rbp+TokenHandle], 0
0x180023e3d  xor     edi, edi
0x180023e3f  mov     [rbp+TokenInformation], r15d
0x180023e43  xor     edx, edx
0x180023e45  mov     [rbp+arg_18], r15d
0x180023e49  mov     [rbp+arg_8], r15d
0x180023e4d  mov     [rbp+Token], rdi
0x180023e51  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180023e56  mov     rcx, cs:WPP_GLOBAL_Control
0x180023e5d  lea     r14, WPP_GLOBAL_Control
0x180023e64  cmp     rcx, r14
0x180023e67  jz      short loc_180023E8F
0x180023e69  test    byte ptr [rcx+1Ch], 2
0x180023e6d  jz      short loc_180023E8F
0x180023e6f  cmp     byte ptr [rcx+19h], 5
0x180023e73  jb      short loc_180023E8F
0x180023e75  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180023e7c  lea     edx, [rdi+0Fh]
0x180023e7f  mov     rcx, [rcx+10h]
0x180023e83  lea     r8, WPP_6bc86d6463543fa2cd93c11fe697381a_Traceguids
0x180023e8a  call    WPP_SF_s
0x180023e8f  xor     ecx, ecx; BindingHandle
0x180023e91  call    cs:__imp_RpcImpersonateClient
0x180023e97  mov     ebx, eax
0x180023e99  mov     r13d, 1
0x180023e9f  test    eax, eax
0x180023ea1  jz      short loc_180023EAA
0x180023ea3  xor     esi, esi
0x180023ea5  jmp     loc_180023F7E
0x180023eaa  mov     esi, r13d
0x180023ead  call    cs:__imp_GetCurrentThread
0x180023eb3  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180023eb7  mov     r8d, r13d; OpenAsSelf
0x180023eba  mov     rcx, rax; ThreadHandle
0x180023ebd  mov     edx, 0Eh; DesiredAccess
0x180023ec2  call    cs:__imp_OpenThreadToken
0x180023ec8  test    eax, eax
0x180023eca  jnz     short loc_180023ED7
0x180023ecc  call    cs:__imp_GetLastError
0x180023ed2  jmp     loc_180023F7C
0x180023ed7  call    cs:__imp_RpcRevertToSelf
0x180023edd  mov     ebx, eax
0x180023edf  test    eax, eax
0x180023ee1  jnz     loc_180023F7E
0x180023ee7  mov     rcx, [rbp+TokenHandle]; hExistingToken
0x180023eeb  lea     r8, [rbp+arg_8]; int *
0x180023eef  lea     rdx, [rbp+Token]; void **
0x180023ef3  xor     esi, esi
0x180023ef5  call    ?CheckForLowIntegrityAndGenerateMediumIntegrityToken@@YAKPEAXPEAPEAXPEAH@Z; CheckForLowIntegrityAndGenerateMediumIntegrityToken(void *,void * *,int *)
0x180023efa  mov     rdi, [rbp+Token]
0x180023efe  mov     ebx, eax
0x180023f00  test    eax, eax
0x180023f02  jnz     short loc_180023F7E
0x180023f04  mov     r14d, [rbp+arg_8]
0x180023f08  xor     ecx, ecx; BindingHandle
0x180023f0a  test    r14d, r14d
0x180023f0d  jz      short loc_180023F32
0x180023f0f  mov     rdx, rdi; Token
0x180023f12  call    cs:__imp_SetThreadToken
0x180023f18  test    eax, eax
0x180023f1a  jnz     short loc_180023F2D
0x180023f1c  call    cs:__imp_GetLastError
0x180023f22  mov     ebx, eax
0x180023f24  lea     r14, WPP_GLOBAL_Control
0x180023f2b  jmp     short loc_180023F7E
0x180023f2d  mov     r15d, r13d
0x180023f30  jmp     short loc_180023F41
0x180023f32  call    cs:__imp_RpcImpersonateClient
0x180023f38  mov     ebx, eax
0x180023f3a  test    eax, eax
0x180023f3c  jnz     short loc_180023F24
0x180023f3e  mov     esi, r13d
0x180023f41  mov     rcx, [rbp+TokenHandle]
0x180023f45  lea     rax, [rbp+arg_18]
0x180023f49  mov     r9d, 4; TokenInformationLength
0x180023f4f  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x180023f54  test    r14d, r14d
0x180023f57  lea     r8, [rbp+TokenInformation]; TokenInformation
0x180023f5b  cmovnz  rcx, rdi; TokenHandle
0x180023f5f  lea     edx, [r9+8]; TokenInformationClass
0x180023f63  call    cs:__imp_GetTokenInformation
0x180023f69  test    eax, eax
0x180023f6b  jz      short loc_180023F1C
0x180023f6d  mov     ecx, [rbp+TokenInformation]
0x180023f70  call    CertPropUpdateRootCertificatesRpcCallout
0x180023f75  lea     r14, WPP_GLOBAL_Control
0x180023f7c  mov     ebx, eax
0x180023f7e  mov     rcx, [rbp+TokenHandle]; hObject
0x180023f82  test    rcx, rcx
0x180023f85  jz      short loc_180023F8D
0x180023f87  call    cs:__imp_CloseHandle
0x180023f8d  test    rdi, rdi
0x180023f90  jz      short loc_180023F9B
0x180023f92  mov     rcx, rdi; hObject
0x180023f95  call    cs:__imp_CloseHandle
0x180023f9b  cmp     esi, r13d
0x180023f9e  jnz     short loc_180023FAB
0x180023fa0  call    cs:__imp_RpcRevertToSelf
0x180023fa6  test    eax, eax
0x180023fa8  cmovnz  ebx, eax
0x180023fab  cmp     r15d, r13d
0x180023fae  jnz     short loc_180023FB6
0x180023fb0  call    cs:__imp_RevertToSelf
0x180023fb6  mov     edx, r13d
0x180023fb9  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180023fbe  mov     rcx, cs:WPP_GLOBAL_Control
0x180023fc5  cmp     rcx, r14
0x180023fc8  jz      short loc_180023FF6
0x180023fca  test    byte ptr [rcx+1Ch], 2
0x180023fce  jz      short loc_180023FF6
0x180023fd0  cmp     byte ptr [rcx+19h], 5
0x180023fd4  jb      short loc_180023FF6
0x180023fd6  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180023fdd  lea     r8, WPP_6bc86d6463543fa2cd93c11fe697381a_Traceguids
0x180023fe4  mov     rcx, [rcx+10h]
0x180023fe8  mov     edx, 10h
0x180023fed  mov     dword ptr [rsp+40h+ReturnLength], ebx
0x180023ff1  call    WPP_SF_sD
0x180023ff6  mov     eax, ebx
0x180023ff8  add     rsp, 40h
0x180023ffc  pop     r15
0x180023ffe  pop     r14
0x180024000  pop     r13
0x180024002  pop     rdi
0x180024003  pop     rsi
0x180024004  pop     rbx
0x180024005  pop     rbp
0x180024006  retn
```
