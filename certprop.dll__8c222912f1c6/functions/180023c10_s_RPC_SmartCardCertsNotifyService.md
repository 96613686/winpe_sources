# s_RPC_SmartCardCertsNotifyService

- ea: `0x180023c10`
- end: `0x180023e12`
- name: `s_RPC_SmartCardCertsNotifyService`
- size: `514`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x1800180f4`
- `0x180018b58`
- `0x180018bb4`
- `0x1800232c4`
- `0x1800238a4`
- `0x180023c10`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180023cb6`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180023cb6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180023ca3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180023ca3`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180023d0a`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180023d0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023cc0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023d14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023cc0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023d14`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023d85`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023d93`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023d85`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023d93`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180023daf`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180023daf`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180023d5e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180023d5e`
- `RPCRT4!RpcImpersonateClient` at `0x180023c8b`
- `RPCRT4!RpcImpersonateClient` at `0x180023d2d`
- `RPCRT4!RpcImpersonateClient` at `0x180023c8b`
- `RPCRT4!RpcImpersonateClient` at `0x180023d2d`
- `RPCRT4!RpcRevertToSelf` at `0x180023ccb`
- `RPCRT4!RpcRevertToSelf` at `0x180023d9e`
- `RPCRT4!RpcRevertToSelf` at `0x180023ccb`
- `RPCRT4!RpcRevertToSelf` at `0x180023d9e`

## pseudocode

```c
__int64 __fastcall s_RPC_SmartCardCertsNotifyService(__int64 a1, __int64 a2)
{
  int v2; // r15d
  HANDLE v4; // rdi
  DWORD v5; // ebx
  int v6; // esi
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  unsigned int v9; // eax
  int v10; // r14d
  void *v11; // rcx
  void *v12; // rcx
  RPC_STATUS v13; // eax
  DWORD ReturnLength; // [rsp+30h] [rbp-20h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-18h] BYREF
  HANDLE Token; // [rsp+40h] [rbp-10h] BYREF
  int v18; // [rsp+90h] [rbp+40h] BYREF
  unsigned int TokenInformation; // [rsp+98h] [rbp+48h] BYREF

  v2 = 0;
  TokenHandle = 0;
  TokenInformation = 0;
  v4 = 0;
  ReturnLength = 0;
  v18 = 0;
  Token = 0;
  WppTraceIndent(a1, 0);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 2) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_6bc86d6463543fa2cd93c11fe697381a_Traceguids, WPP_pszIndent);
  }
  v5 = RpcImpersonateClient(0);
  if ( v5 )
  {
    v6 = 0;
    goto LABEL_23;
  }
  v6 = 1;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xEu, 1, &TokenHandle) )
  {
    LastError = GetLastError();
LABEL_22:
    v5 = LastError;
    goto LABEL_23;
  }
  v5 = RpcRevertToSelf();
  if ( !v5 )
  {
    v6 = 0;
    v9 = CheckForLowIntegrityAndGenerateMediumIntegrityToken(TokenHandle, &Token, &v18);
    v4 = Token;
    v5 = v9;
    if ( !v9 )
    {
      v10 = v18;
      if ( v18 )
      {
        if ( !SetThreadToken(0, Token) )
        {
LABEL_13:
          v5 = GetLastError();
          goto LABEL_23;
        }
        v2 = 1;
LABEL_18:
        v11 = TokenHandle;
        if ( v10 )
          v11 = v4;
        if ( GetTokenInformation(v11, TokenSessionId, &TokenInformation, 4u, &ReturnLength) )
        {
          LastError = CertPropUpdateCertificatesRpcCallout(TokenInformation, a2);
          goto LABEL_22;
        }
        goto LABEL_13;
      }
      v5 = RpcImpersonateClient(0);
      if ( !v5 )
      {
        v6 = 1;
        goto LABEL_18;
      }
    }
  }
LABEL_23:
  v12 = TokenHandle;
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( v4 )
    CloseHandle(v4);
  if ( v6 == 1 )
  {
    v13 = RpcRevertToSelf();
    if ( v13 )
      v5 = v13;
  }
  if ( v2 == 1 )
    RevertToSelf();
  WppTraceIndent(v12, 1);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 2) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      14,
      (unsigned int)WPP_6bc86d6463543fa2cd93c11fe697381a_Traceguids,
      (_DWORD)WPP_pszIndent,
      v5);
  }
  return v5;
}

```

## disassembly

```asm
0x180023c10  mov     [rsp-28h+arg_0], rbx
0x180023c15  mov     [rsp-28h+arg_8], rsi
0x180023c1a  push    rbp
0x180023c1b  push    rdi
0x180023c1c  push    r12
0x180023c1e  push    r14
0x180023c20  push    r15
0x180023c22  mov     rbp, rsp
0x180023c25  sub     rsp, 50h
0x180023c29  xor     r15d, r15d
0x180023c2c  mov     [rbp+TokenHandle], 0
0x180023c34  mov     r12, rdx
0x180023c37  mov     [rbp+TokenInformation], r15d
0x180023c3b  xor     edi, edi
0x180023c3d  mov     [rbp+var_20], r15d
0x180023c41  xor     edx, edx
0x180023c43  mov     [rbp+arg_10], r15d
0x180023c47  mov     [rbp+Token], rdi
0x180023c4b  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180023c50  mov     rcx, cs:WPP_GLOBAL_Control
0x180023c57  lea     r14, WPP_GLOBAL_Control
0x180023c5e  cmp     rcx, r14
0x180023c61  jz      short loc_180023C89
0x180023c63  test    byte ptr [rcx+1Ch], 2
0x180023c67  jz      short loc_180023C89
0x180023c69  cmp     byte ptr [rcx+19h], 5
0x180023c6d  jb      short loc_180023C89
0x180023c6f  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180023c76  lea     edx, [rdi+0Dh]
0x180023c79  mov     rcx, [rcx+10h]
0x180023c7d  lea     r8, WPP_6bc86d6463543fa2cd93c11fe697381a_Traceguids
0x180023c84  call    WPP_SF_s
0x180023c89  xor     ecx, ecx; BindingHandle
0x180023c8b  call    cs:__imp_RpcImpersonateClient
0x180023c91  mov     ebx, eax
0x180023c93  test    eax, eax
0x180023c95  jz      short loc_180023C9E
0x180023c97  xor     esi, esi
0x180023c99  jmp     loc_180023D7C
0x180023c9e  mov     esi, 1
0x180023ca3  call    cs:__imp_GetCurrentThread
0x180023ca9  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180023cad  mov     r8d, esi; OpenAsSelf
0x180023cb0  mov     rcx, rax; ThreadHandle
0x180023cb3  lea     edx, [rsi+0Dh]; DesiredAccess
0x180023cb6  call    cs:__imp_OpenThreadToken
0x180023cbc  test    eax, eax
0x180023cbe  jnz     short loc_180023CCB
0x180023cc0  call    cs:__imp_GetLastError
0x180023cc6  jmp     loc_180023D7A
0x180023ccb  call    cs:__imp_RpcRevertToSelf
0x180023cd1  mov     ebx, eax
0x180023cd3  test    eax, eax
0x180023cd5  jnz     loc_180023D7C
0x180023cdb  mov     rcx, [rbp+TokenHandle]; hExistingToken
0x180023cdf  lea     r8, [rbp+arg_10]; int *
0x180023ce3  lea     rdx, [rbp+Token]; void **
0x180023ce7  xor     esi, esi
0x180023ce9  call    ?CheckForLowIntegrityAndGenerateMediumIntegrityToken@@YAKPEAXPEAPEAXPEAH@Z; CheckForLowIntegrityAndGenerateMediumIntegrityToken(void *,void * *,int *)
0x180023cee  mov     rdi, [rbp+Token]
0x180023cf2  mov     ebx, eax
0x180023cf4  test    eax, eax
0x180023cf6  jnz     loc_180023D7C
0x180023cfc  mov     r14d, [rbp+arg_10]
0x180023d00  xor     ecx, ecx; BindingHandle
0x180023d02  test    r14d, r14d
0x180023d05  jz      short loc_180023D2D
0x180023d07  mov     rdx, rdi; Token
0x180023d0a  call    cs:__imp_SetThreadToken
0x180023d10  test    eax, eax
0x180023d12  jnz     short loc_180023D25
0x180023d14  call    cs:__imp_GetLastError
0x180023d1a  mov     ebx, eax
0x180023d1c  lea     r14, WPP_GLOBAL_Control
0x180023d23  jmp     short loc_180023D7C
0x180023d25  mov     r15d, 1
0x180023d2b  jmp     short loc_180023D3C
0x180023d2d  call    cs:__imp_RpcImpersonateClient
0x180023d33  mov     ebx, eax
0x180023d35  test    eax, eax
0x180023d37  jnz     short loc_180023D1C
0x180023d39  lea     esi, [rax+1]
0x180023d3c  mov     rcx, [rbp+TokenHandle]
0x180023d40  lea     rax, [rbp+var_20]
0x180023d44  mov     r9d, 4; TokenInformationLength
0x180023d4a  mov     [rsp+50h+ReturnLength], rax; ReturnLength
0x180023d4f  test    r14d, r14d
0x180023d52  lea     r8, [rbp+TokenInformation]; TokenInformation
0x180023d56  cmovnz  rcx, rdi; TokenHandle
0x180023d5a  lea     edx, [r9+8]; TokenInformationClass
0x180023d5e  call    cs:__imp_GetTokenInformation
0x180023d64  test    eax, eax
0x180023d66  jz      short loc_180023D14
0x180023d68  mov     ecx, [rbp+TokenInformation]
0x180023d6b  mov     rdx, r12
0x180023d6e  call    CertPropUpdateCertificatesRpcCallout
0x180023d73  lea     r14, WPP_GLOBAL_Control
0x180023d7a  mov     ebx, eax
0x180023d7c  mov     rcx, [rbp+TokenHandle]; hObject
0x180023d80  test    rcx, rcx
0x180023d83  jz      short loc_180023D8B
0x180023d85  call    cs:__imp_CloseHandle
0x180023d8b  test    rdi, rdi
0x180023d8e  jz      short loc_180023D99
0x180023d90  mov     rcx, rdi; hObject
0x180023d93  call    cs:__imp_CloseHandle
0x180023d99  cmp     esi, 1
0x180023d9c  jnz     short loc_180023DA9
0x180023d9e  call    cs:__imp_RpcRevertToSelf
0x180023da4  test    eax, eax
0x180023da6  cmovnz  ebx, eax
0x180023da9  cmp     r15d, 1
0x180023dad  jnz     short loc_180023DB5
0x180023daf  call    cs:__imp_RevertToSelf
0x180023db5  mov     edx, 1
0x180023dba  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180023dbf  mov     rcx, cs:WPP_GLOBAL_Control
0x180023dc6  cmp     rcx, r14
0x180023dc9  jz      short loc_180023DF7
0x180023dcb  test    byte ptr [rcx+1Ch], 2
0x180023dcf  jz      short loc_180023DF7
0x180023dd1  cmp     byte ptr [rcx+19h], 5
0x180023dd5  jb      short loc_180023DF7
0x180023dd7  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180023dde  lea     r8, WPP_6bc86d6463543fa2cd93c11fe697381a_Traceguids
0x180023de5  mov     rcx, [rcx+10h]
0x180023de9  mov     edx, 0Eh
0x180023dee  mov     dword ptr [rsp+50h+ReturnLength], ebx
0x180023df2  call    WPP_SF_sD
0x180023df7  lea     r11, [rsp+50h+var_s0]
0x180023dfc  mov     eax, ebx
0x180023dfe  mov     rbx, [r11+30h]
0x180023e02  mov     rsi, [r11+38h]
0x180023e06  mov     rsp, r11
0x180023e09  pop     r15
0x180023e0b  pop     r14
0x180023e0d  pop     r12
0x180023e0f  pop     rdi
0x180023e10  pop     rbp
0x180023e11  retn
```
