# CEfsTokenManager::ModifyCallerContext(ulong)

- ea: `0x180066d30`
- end: `0x180066fc7`
- name: `?ModifyCallerContext@CEfsTokenManager@@QEAAKK@Z`
- size: `663`
- prototype: `unsigned int __fastcall(CEfsTokenManager *__hidden this, unsigned int)`
- caller_count: `16`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000e0fc`
- `0x18001441c`
- `0x180017304`
- `0x18001f0fc`
- `0x180023154`
- `0x180025dbc`
- `0x1800392a0`
- `0x18004725c`
- `0x180070d88`
- `0x180071530`
- `0x180072714`
- `0x180072ae8`
- `0x18007b470`
- `0x18007ba08`
- `0x1800812f8`
- `0x180081634`

## callees

- `0x180063698`
- `0x180066888`
- `0x180066970`
- `0x180066c84`
- `0x180066d30`
- `0x1800d2320`
- `0x1800d937c`
- `0x1800d9544`
- `0x1800dca3c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066e0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066e62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066e7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066f3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066e0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066e62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066e7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066f3e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180066e00`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180066e00`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180066de9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180066de9`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180066f34`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180066f7c`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180066f34`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180066f7c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180066f8b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180066f9a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180066f8b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180066f9a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180066e72`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180066e72`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180066e58`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180066e58`
- `ntdll!RtlNtStatusToDosError` at `0x180066ef6`
- `ntdll!RtlNtStatusToDosError` at `0x180066ef6`

## pseudocode

```c
__int64 __fastcall CEfsTokenManager::ModifyCallerContext(CEfsTokenManager *this, char a2)
{
  int v2; // esi
  int v3; // edi
  unsigned int v6; // ebx
  int v7; // r15d
  unsigned int v8; // eax
  int v9; // r14d
  unsigned int v10; // eax
  int v11; // r12d
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  __int64 v14; // rcx
  CEfsTokenManager *v15; // rcx
  unsigned int v16; // eax
  HANDLE v17; // rsi
  int v18; // eax
  __int64 v19; // rbx
  NTSTATUS v20; // edi
  ULONG v21; // eax
  void *v22; // rcx
  char TokenType; // [rsp+20h] [rbp-20h]
  HANDLE Token; // [rsp+30h] [rbp-10h] BYREF
  __int64 v26; // [rsp+80h] [rbp+40h] BYREF
  int v27; // [rsp+90h] [rbp+50h] BYREF
  void *TokenHandle; // [rsp+98h] [rbp+58h] BYREF

  v2 = 0;
  Token = 0;
  v3 = 0;
  v27 = 0;
  LODWORD(v26) = 0;
  TokenHandle = 0;
  if ( *(_QWORD *)this )
    return 5023;
  v6 = 0;
  v7 = a2 & 1;
  if ( (a2 & 1) == 0 )
  {
LABEL_7:
    v9 = a2 & 2;
    if ( v9 )
    {
      v10 = CEfsTokenManager::CheckIsEdpCaller(&v27);
      v6 = v10;
      if ( v10 )
      {
        fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v10, 29, 122);
        goto LABEL_42;
      }
      v2 = v27;
    }
    if ( !v3 && !v2 )
      goto LABEL_42;
    v11 = 0;
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 0x86u, 1, &TokenHandle) )
    {
      if ( DuplicateTokenEx(TokenHandle, 0, 0, SecurityImpersonation, TokenImpersonation, &Token) )
      {
        if ( RevertToSelf() )
        {
          if ( v3 )
          {
            if ( v7 )
            {
              v16 = CEfsTokenManager::ElevateTokenToMediumIL(v15, Token);
              v6 = v16;
              if ( v16 )
              {
                fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v16, 29, 168);
                goto LABEL_39;
              }
            }
          }
          if ( v2 && v9 )
          {
            v17 = Token;
            v26 = 0;
            v18 = SrpCreateEnterpriseContext(1, 0, 0, &v26);
            v19 = v26;
            v20 = v18;
            if ( v18 >= 0 )
              v20 = SrpSetEnterpriseContextToken(v17);
            if ( v19 )
              SrpDeleteEnterpriseContext(v19);
            v21 = RtlNtStatusToDosError(v20);
            v6 = v21;
            if ( v21 )
            {
              fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v21, 29, 173);
              goto LABEL_39;
            }
          }
          v11 = 1;
          if ( SetThreadToken(0, Token) )
          {
            *(_QWORD *)this = TokenHandle;
            TokenHandle = 0;
            goto LABEL_37;
          }
          LastError = GetLastError();
          TokenType = -80;
        }
        else
        {
          LastError = GetLastError();
          TokenType = -100;
        }
      }
      else
      {
        LastError = GetLastError();
        TokenType = -107;
      }
    }
    else
    {
      LastError = GetLastError();
      TokenType = -118;
    }
    v6 = LastError;
    fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, LastError, 29, TokenType);
LABEL_37:
    if ( !v6 || !v11 )
      goto LABEL_42;
LABEL_39:
    if ( !TokenHandle )
      MicrosoftTelemetryAssertTriggeredNoArgs(v14);
    SetThreadToken(0, TokenHandle);
    goto LABEL_42;
  }
  v8 = CEfsTokenManager::CheckIsLowILCaller((int *)&v26);
  v6 = v8;
  if ( !v8 )
  {
    v3 = v26;
    goto LABEL_7;
  }
  fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v8, 29, 118);
LABEL_42:
  if ( Token )
    CloseHandle(Token);
  v22 = TokenHandle;
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( v6 == 1008 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v22);
  return v6;
}

```

## disassembly

```asm
0x180066d30  mov     [rsp-38h+arg_8], rbx
0x180066d35  push    rbp
0x180066d36  push    rsi
0x180066d37  push    rdi
0x180066d38  push    r12
0x180066d3a  push    r13
0x180066d3c  push    r14
0x180066d3e  push    r15
0x180066d40  mov     rbp, rsp
0x180066d43  sub     rsp, 40h
0x180066d47  xor     esi, esi
0x180066d49  mov     [rbp+Token], 0
0x180066d51  xor     edi, edi
0x180066d53  mov     [rbp+arg_10], esi
0x180066d56  mov     r14d, edx
0x180066d59  mov     r13, rcx
0x180066d5c  mov     dword ptr [rbp+arg_0], edi
0x180066d5f  mov     [rbp+TokenHandle], rsi
0x180066d63  cmp     [rcx], rsi
0x180066d66  jz      short loc_180066D72
0x180066d68  mov     ebx, 139Fh
0x180066d6d  jmp     loc_180066FAD
0x180066d72  xor     ebx, ebx
0x180066d74  mov     r15d, r14d
0x180066d77  and     r15d, 1
0x180066d7b  jz      short loc_180066D99
0x180066d7d  lea     rcx, [rbp+arg_0]; int *
0x180066d81  call    ?CheckIsLowILCaller@CEfsTokenManager@@SAKPEAH@Z; CEfsTokenManager::CheckIsLowILCaller(int *)
0x180066d86  mov     ebx, eax
0x180066d88  test    eax, eax
0x180066d8a  jz      short loc_180066D96
0x180066d8c  mov     dword ptr [rsp+40h+TokenType], 76h ; 'v'
0x180066d94  jmp     short loc_180066DB6
0x180066d96  mov     edi, dword ptr [rbp+arg_0]
0x180066d99  and     r14d, 2
0x180066d9d  jz      short loc_180066DDA
0x180066d9f  lea     rcx, [rbp+arg_10]; int *
0x180066da3  call    ?CheckIsEdpCaller@CEfsTokenManager@@SAKPEAH@Z; CEfsTokenManager::CheckIsEdpCaller(int *)
0x180066da8  mov     ebx, eax
0x180066daa  test    eax, eax
0x180066dac  jz      short loc_180066DD7
0x180066dae  mov     dword ptr [rsp+40h+TokenType], 7Ah ; 'z'
0x180066db6  mov     rcx, cs:g_hPublisher
0x180066dbd  lea     rdx, EFS_API_ERROR
0x180066dc4  mov     r9d, 1Dh
0x180066dca  mov     r8d, eax
0x180066dcd  call    fnEfsLogTrace1
0x180066dd2  jmp     loc_180066F82
0x180066dd7  mov     esi, [rbp+arg_10]
0x180066dda  test    edi, edi
0x180066ddc  jnz     short loc_180066DE6
0x180066dde  test    esi, esi
0x180066de0  jz      loc_180066F82
0x180066de6  xor     r12d, r12d
0x180066de9  call    cs:__imp_GetCurrentThread
0x180066def  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180066df3  mov     edx, 86h; DesiredAccess
0x180066df8  mov     rcx, rax; ThreadHandle
0x180066dfb  lea     r8d, [r12+1]; OpenAsSelf
0x180066e00  call    cs:__imp_OpenThreadToken
0x180066e06  test    eax, eax
0x180066e08  jnz     short loc_180066E3B
0x180066e0a  call    cs:__imp_GetLastError
0x180066e10  mov     dword ptr [rsp+40h+TokenType], 8Ah
0x180066e18  mov     rcx, cs:g_hPublisher
0x180066e1f  lea     rdx, EFS_API_ERROR
0x180066e26  mov     r9d, 1Dh
0x180066e2c  mov     r8d, eax
0x180066e2f  mov     ebx, eax
0x180066e31  call    fnEfsLogTrace1
0x180066e36  jmp     loc_180066F61
0x180066e3b  mov     rcx, [rbp+TokenHandle]; hExistingToken
0x180066e3f  lea     rax, [rbp+Token]
0x180066e43  mov     r9d, 2; ImpersonationLevel
0x180066e49  mov     [rsp+40h+phNewToken], rax; phNewToken
0x180066e4e  xor     r8d, r8d; lpTokenAttributes
0x180066e51  mov     dword ptr [rsp+40h+TokenType], r9d; TokenType
0x180066e56  xor     edx, edx; dwDesiredAccess
0x180066e58  call    cs:__imp_DuplicateTokenEx
0x180066e5e  test    eax, eax
0x180066e60  jnz     short loc_180066E72
0x180066e62  call    cs:__imp_GetLastError
0x180066e68  mov     dword ptr [rsp+40h+TokenType], 95h
0x180066e70  jmp     short loc_180066E18
0x180066e72  call    cs:__imp_RevertToSelf
0x180066e78  test    eax, eax
0x180066e7a  jnz     short loc_180066E8C
0x180066e7c  call    cs:__imp_GetLastError
0x180066e82  mov     dword ptr [rsp+40h+TokenType], 9Ch
0x180066e8a  jmp     short loc_180066E18
0x180066e8c  test    edi, edi
0x180066e8e  jz      short loc_180066EAE
0x180066e90  test    r15d, r15d
0x180066e93  jz      short loc_180066EAE
0x180066e95  mov     rdx, [rbp+Token]; void *
0x180066e99  call    ?ElevateTokenToMediumIL@CEfsTokenManager@@AEAAKPEAX@Z; CEfsTokenManager::ElevateTokenToMediumIL(void *)
0x180066e9e  mov     ebx, eax
0x180066ea0  test    eax, eax
0x180066ea2  jz      short loc_180066EAE
0x180066ea4  mov     dword ptr [rsp+40h+TokenType], 0A8h
0x180066eac  jmp     short loc_180066F0A
0x180066eae  test    esi, esi
0x180066eb0  jz      short loc_180066F28
0x180066eb2  test    r14d, r14d
0x180066eb5  jz      short loc_180066F28
0x180066eb7  mov     rsi, [rbp+Token]
0x180066ebb  lea     r9, [rbp+arg_0]
0x180066ebf  xor     edx, edx
0x180066ec1  mov     [rbp+arg_0], r12
0x180066ec5  xor     r8d, r8d
0x180066ec8  lea     ecx, [rdx+1]
0x180066ecb  call    SrpCreateEnterpriseContext
0x180066ed0  mov     rbx, [rbp+arg_0]
0x180066ed4  mov     edi, eax
0x180066ed6  test    eax, eax
0x180066ed8  js      short loc_180066EE7
0x180066eda  mov     rdx, rbx
0x180066edd  mov     rcx, rsi; TokenHandle
0x180066ee0  call    SrpSetEnterpriseContextToken
0x180066ee5  mov     edi, eax
0x180066ee7  test    rbx, rbx
0x180066eea  jz      short loc_180066EF4
0x180066eec  mov     rcx, rbx
0x180066eef  call    SrpDeleteEnterpriseContext
0x180066ef4  mov     ecx, edi; Status
0x180066ef6  call    cs:__imp_RtlNtStatusToDosError
0x180066efc  mov     ebx, eax
0x180066efe  test    eax, eax
0x180066f00  jz      short loc_180066F28
0x180066f02  mov     dword ptr [rsp+40h+TokenType], 0ADh
0x180066f0a  mov     rcx, cs:g_hPublisher
0x180066f11  lea     rdx, EFS_API_ERROR
0x180066f18  mov     r9d, 1Dh
0x180066f1e  mov     r8d, eax
0x180066f21  call    fnEfsLogTrace1
0x180066f26  jmp     short loc_180066F6A
0x180066f28  mov     rdx, [rbp+Token]; Token
0x180066f2c  xor     ecx, ecx; Thread
0x180066f2e  mov     r12d, 1
0x180066f34  call    cs:__imp_SetThreadToken
0x180066f3a  test    eax, eax
0x180066f3c  jnz     short loc_180066F51
0x180066f3e  call    cs:__imp_GetLastError
0x180066f44  mov     dword ptr [rsp+40h+TokenType], 0B0h
0x180066f4c  jmp     loc_180066E18
0x180066f51  mov     rax, [rbp+TokenHandle]
0x180066f55  mov     [r13+0], rax
0x180066f59  mov     [rbp+TokenHandle], 0
0x180066f61  test    ebx, ebx
0x180066f63  jz      short loc_180066F82
0x180066f65  test    r12d, r12d
0x180066f68  jz      short loc_180066F82
0x180066f6a  cmp     [rbp+TokenHandle], 0
0x180066f6f  jnz     short loc_180066F76
0x180066f71  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "ThreadToken != NULL")
0x180066f76  mov     rdx, [rbp+TokenHandle]; Token
0x180066f7a  xor     ecx, ecx; Thread
0x180066f7c  call    cs:__imp_SetThreadToken
0x180066f82  mov     rcx, [rbp+Token]; hObject
0x180066f86  test    rcx, rcx
0x180066f89  jz      short loc_180066F91
0x180066f8b  call    cs:__imp_CloseHandle
0x180066f91  mov     rcx, [rbp+TokenHandle]; hObject
0x180066f95  test    rcx, rcx
0x180066f98  jz      short loc_180066FA0
0x180066f9a  call    cs:__imp_CloseHandle
0x180066fa0  cmp     ebx, 3F0h
0x180066fa6  jnz     short loc_180066FAD
0x180066fa8  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "rc != ERROR_NO_TOKEN")
0x180066fad  mov     eax, ebx
0x180066faf  mov     rbx, [rsp+40h+arg_8]
0x180066fb7  add     rsp, 40h
0x180066fbb  pop     r15
0x180066fbd  pop     r14
0x180066fbf  pop     r13
0x180066fc1  pop     r12
0x180066fc3  pop     rdi
0x180066fc4  pop     rsi
0x180066fc5  pop     rbp
0x180066fc6  retn
```
