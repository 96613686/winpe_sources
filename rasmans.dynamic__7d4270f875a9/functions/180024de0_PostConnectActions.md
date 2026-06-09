# PostConnectActions

- ea: `0x180024de0`
- end: `0x180025385`
- name: `PostConnectActions`
- size: `1445`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180037890`

## callees

- `0x180003154`
- `0x1800032e4`
- `0x180005bcc`
- `0x180005bfc`
- `0x180024de0`
- `0x180040998`
- `0x180043010`
- `0x180043870`
- `0x180043958`
- `0x180052b1c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180025088`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002517d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180025088`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002517d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025306`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025329`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025306`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025329`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024fba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025029`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800250a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002518d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024fba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025029`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800250a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002518d`
- `RPCRT4!RpcImpersonateClient` at `0x1800250e5`
- `RPCRT4!RpcImpersonateClient` at `0x1800250e5`
- `RPCRT4!RpcRevertToSelf` at `0x1800251df`
- `RPCRT4!RpcRevertToSelf` at `0x18002521d`
- `RPCRT4!RpcRevertToSelf` at `0x1800251df`
- `RPCRT4!RpcRevertToSelf` at `0x18002521d`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180025015`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180025015`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x180024f96`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x180024faa`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x180024f96`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x180024faa`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180024f7a`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180024f7a`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrFreeSessionUsers` at `0x180024f62`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrFreeSessionUsers` at `0x180024f62`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrEnumerateSessionUsers` at `0x180024f41`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrEnumerateSessionUsers` at `0x180024f41`

## pseudocode

```c
int __fastcall PostConnectActions(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v4; // rcx
  int v5; // r14d
  __int64 Connection; // rax
  __int64 v7; // rsi
  int v8; // edx
  __int64 v9; // rcx
  int v10; // ebx
  __int64 v11; // rbx
  int v12; // eax
  DWORD LastError; // eax
  DWORD v14; // eax
  DWORD v15; // eax
  struct _LIST_ENTRY *v16; // rcx
  __int64 v17; // r9
  __int64 v18; // rdx
  DWORD v19; // eax
  HANDLE hExistingToken; // [rsp+30h] [rbp-10h] BYREF
  __int64 *v22; // [rsp+38h] [rbp-8h] BYREF
  int v23; // [rsp+80h] [rbp+40h] BYREF
  void *TokenHandle; // [rsp+88h] [rbp+48h] BYREF

  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 413, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
  }
  v4 = *(_QWORD *)(a3 + 8);
  v5 = 0;
  hExistingToken = 0;
  TokenHandle = 0;
  Connection = FindConnection(v4);
  v7 = Connection;
  if ( !Connection || !*(_QWORD *)(Connection + 56) )
  {
    v10 = 668;
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
      || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
    {
      goto LABEL_89;
    }
    v18 = 414;
    v17 = 668;
    goto LABEL_59;
  }
  v8 = g_RasMobileCore;
  if ( !g_RasMobileCore && (*(_DWORD *)(Connection + 112) & 0x100) == 0 )
  {
    LODWORD(Connection) = IsSystemOwnedConnection(Connection);
    if ( (_DWORD)Connection
      || (LODWORD(Connection) = IsRASConnectionOnWinLogon(v7), (_DWORD)Connection)
      || (LODWORD(Connection) = IsDemandDialRASConnection(v7), (_DWORD)Connection) )
    {
      v10 = 0;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u )
      {
        LODWORD(Connection) = WPP_SF_(WPP_GLOBAL_Control[1].Flink, 415, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
      }
      goto LABEL_89;
    }
    v8 = g_RasMobileCore;
  }
  if ( *(_DWORD *)(v7 + 860) == 2 )
  {
    v9 = **(_QWORD **)(v7 + 56);
    if ( *(_QWORD *)(v9 + 1240) )
    {
      TokenHandle = *(void **)(v9 + 1240);
LABEL_72:
      LODWORD(Connection) = ApplyPostConnectionActions(v7, TokenHandle);
      v10 = Connection;
      if ( !(_DWORD)Connection )
        goto LABEL_89;
      if ( !g_RasMobileCore && (*(_DWORD *)(v7 + 112) & 0x100) != 0 && (_DWORD)Connection == 5 )
      {
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
        {
          LODWORD(Connection) = WPP_SF_d(
                                  WPP_GLOBAL_Control[1].Flink,
                                  423,
                                  WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids,
                                  5);
        }
        v10 = 0;
        goto LABEL_89;
      }
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
        || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      {
        goto LABEL_89;
      }
      v18 = 424;
      v17 = (unsigned int)Connection;
LABEL_59:
      LODWORD(Connection) = WPP_SF_d(v16[1].Flink, v18, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, v17);
      goto LABEL_89;
    }
  }
  if ( v8 )
  {
    if ( !(unsigned __int8)IsQueryUserTokenPresent() )
      goto LABEL_32;
    if ( !(unsigned __int8)IsUMgrEnumerateSessionUsersPresent() )
      goto LABEL_30;
    v23 = 0;
    v22 = 0;
    v11 = 0;
    if ( (int)UMgrEnumerateSessionUsers(&v23, &v22) >= 0 && v23 )
      v11 = *v22;
    if ( v22 )
      UMgrFreeSessionUsers(v22);
    if ( v11 )
      v12 = (int)UMgrQueryUserToken(v11, &hExistingToken) >= 0;
    else
LABEL_30:
      v12 = QueryUserToken(0, &hExistingToken);
    if ( !v12 )
    {
LABEL_32:
      LastError = GetLastError();
      if ( LastError
        && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 416, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, LastError);
      }
    }
    if ( !DuplicateTokenEx(hExistingToken, 6u, 0, SecurityImpersonation, TokenImpersonation, &TokenHandle) )
    {
      v14 = GetLastError();
      if ( v14 )
      {
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
        {
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 417, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, v14);
        }
      }
    }
    goto LABEL_72;
  }
  if ( OpenProcessToken(*(HANDLE *)(v7 + 80), 2u, &TokenHandle) )
  {
    v5 = 1;
    goto LABEL_72;
  }
  v15 = GetLastError();
  if ( v15
    && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 418, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, v15);
  }
  LODWORD(Connection) = RpcImpersonateClient(0);
  if ( (_DWORD)Connection )
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 3u )
    {
      LODWORD(Connection) = WPP_SF_d(
                              WPP_GLOBAL_Control[1].Flink,
                              419,
                              WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids,
                              (unsigned int)Connection);
      v16 = WPP_GLOBAL_Control;
    }
    v17 = 5;
    v10 = 5;
    if ( v16 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(v16[1].Blink) & 0x2000) != 0
      && BYTE1(v16[1].Blink) >= 2u )
    {
      v18 = 420;
      goto LABEL_59;
    }
  }
  else
  {
    if ( OpenProcessToken(*(HANDLE *)(v7 + 80), 2u, &TokenHandle) )
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u )
      {
        WPP_SF_(WPP_GLOBAL_Control[1].Flink, 422, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
      }
      RpcRevertToSelf();
      goto LABEL_72;
    }
    v19 = GetLastError();
    v10 = v19;
    if ( v19
      && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 421, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, v19);
    }
    LODWORD(Connection) = RpcRevertToSelf();
  }
LABEL_89:
  if ( hExistingToken )
  {
    LODWORD(Connection) = CloseHandle(hExistingToken);
    hExistingToken = 0;
  }
  if ( TokenHandle && v5 == 1 )
  {
    LODWORD(Connection) = CloseHandle(TokenHandle);
    TokenHandle = 0;
  }
  *(_DWORD *)a3 = v10;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    LODWORD(Connection) = WPP_SF_(WPP_GLOBAL_Control[1].Flink, 425, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
  }
  return Connection;
}

```

## disassembly

```asm
0x180024de0  mov     [rsp-28h+arg_0], rbx
0x180024de5  mov     [rsp-28h+arg_8], rsi
0x180024dea  push    rbp
0x180024deb  push    rdi
0x180024dec  push    r13
0x180024dee  push    r14
0x180024df0  push    r15
0x180024df2  mov     rbp, rsp
0x180024df5  sub     rsp, 40h
0x180024df9  mov     r15, r8
0x180024dfc  mov     rcx, cs:WPP_GLOBAL_Control
0x180024e03  lea     rbx, WPP_GLOBAL_Control
0x180024e0a  mov     r13d, 2000h
0x180024e10  cmp     rcx, rbx
0x180024e13  jz      short loc_180024E36
0x180024e15  test    [rcx+1Ch], r13d
0x180024e19  jz      short loc_180024E36
0x180024e1b  cmp     byte ptr [rcx+19h], 6
0x180024e1f  jb      short loc_180024E36
0x180024e21  mov     rcx, [rcx+10h]
0x180024e25  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x180024e2c  mov     edx, 19Dh
0x180024e31  call    WPP_SF_
0x180024e36  mov     rcx, [r15+8]
0x180024e3a  xor     r14d, r14d
0x180024e3d  mov     [rbp+hExistingToken], r14
0x180024e41  mov     [rbp+TokenHandle], 0
0x180024e49  call    FindConnection
0x180024e4e  mov     rsi, rax
0x180024e51  test    rax, rax
0x180024e54  jz      loc_1800252C0
0x180024e5a  cmp     [rax+38h], r14
0x180024e5e  jz      loc_1800252C0
0x180024e64  mov     edx, cs:g_RasMobileCore
0x180024e6a  test    edx, edx
0x180024e6c  jnz     short loc_180024EA1
0x180024e6e  test    dword ptr [rax+70h], 100h
0x180024e75  jnz     short loc_180024EA1
0x180024e77  mov     rcx, rax
0x180024e7a  call    IsSystemOwnedConnection
0x180024e7f  test    eax, eax
0x180024e81  jnz     short loc_180024ECA
0x180024e83  mov     rcx, rsi
0x180024e86  call    IsRASConnectionOnWinLogon
0x180024e8b  test    eax, eax
0x180024e8d  jnz     short loc_180024ECA
0x180024e8f  mov     rcx, rsi
0x180024e92  call    IsDemandDialRASConnection
0x180024e97  test    eax, eax
0x180024e99  jnz     short loc_180024ECA
0x180024e9b  mov     edx, cs:g_RasMobileCore
0x180024ea1  mov     edi, 2
0x180024ea6  cmp     [rsi+35Ch], edi
0x180024eac  jnz     short loc_180024F11
0x180024eae  mov     rax, [rsi+38h]
0x180024eb2  mov     rcx, [rax]
0x180024eb5  mov     rax, [rcx+4D8h]
0x180024ebc  test    rax, rax
0x180024ebf  jz      short loc_180024F11
0x180024ec1  mov     [rbp+TokenHandle], rax
0x180024ec5  jmp     loc_180025229
0x180024eca  mov     rcx, cs:WPP_GLOBAL_Control
0x180024ed1  lea     rsi, WPP_GLOBAL_Control
0x180024ed8  xor     ebx, ebx
0x180024eda  cmp     rcx, rsi
0x180024edd  jz      loc_1800252FD
0x180024ee3  test    [rcx+1Ch], r13d
0x180024ee7  jz      loc_1800252FD
0x180024eed  cmp     byte ptr [rcx+19h], 4
0x180024ef1  jb      loc_1800252FD
0x180024ef7  mov     rcx, [rcx+10h]
0x180024efb  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x180024f02  mov     edx, 19Fh
0x180024f07  call    WPP_SF_
0x180024f0c  jmp     loc_1800252FD
0x180024f11  test    edx, edx
0x180024f13  jz      loc_18002507E
0x180024f19  call    IsQueryUserTokenPresent
0x180024f1e  test    al, al
0x180024f20  jz      loc_180024FBA
0x180024f26  call    IsUMgrEnumerateSessionUsersPresent
0x180024f2b  test    al, al
0x180024f2d  jz      short loc_180024FA4
0x180024f2f  lea     rdx, [rbp+var_8]
0x180024f33  mov     [rbp+arg_10], r14d
0x180024f37  lea     rcx, [rbp+arg_10]
0x180024f3b  mov     [rbp+var_8], r14
0x180024f3f  xor     ebx, ebx
0x180024f41  call    cs:__imp_UMgrEnumerateSessionUsers
0x180024f48  nop     dword ptr [rax+rax+00h]
0x180024f4d  mov     rcx, [rbp+var_8]
0x180024f51  test    eax, eax
0x180024f53  js      short loc_180024F5D
0x180024f55  cmp     [rbp+arg_10], ebx
0x180024f58  jbe     short loc_180024F5D
0x180024f5a  mov     rbx, [rcx]
0x180024f5d  test    rcx, rcx
0x180024f60  jz      short loc_180024F6E
0x180024f62  call    cs:__imp_UMgrFreeSessionUsers
0x180024f69  nop     dword ptr [rax+rax+00h]
0x180024f6e  lea     rdx, [rbp+hExistingToken]
0x180024f72  test    rbx, rbx
0x180024f75  jz      short loc_180024F94
0x180024f77  mov     rcx, rbx
0x180024f7a  call    cs:__imp_UMgrQueryUserToken
0x180024f81  nop     dword ptr [rax+rax+00h]
0x180024f86  not     eax
0x180024f88  shr     eax, 1Fh
0x180024f8b  lea     rbx, WPP_GLOBAL_Control
0x180024f92  jmp     short loc_180024FB6
0x180024f94  xor     ecx, ecx
0x180024f96  call    cs:__imp_QueryUserToken
0x180024f9d  nop     dword ptr [rax+rax+00h]
0x180024fa2  jmp     short loc_180024F8B
0x180024fa4  lea     rdx, [rbp+hExistingToken]
0x180024fa8  xor     ecx, ecx
0x180024faa  call    cs:__imp_QueryUserToken
0x180024fb1  nop     dword ptr [rax+rax+00h]
0x180024fb6  test    eax, eax
0x180024fb8  jnz     short loc_180024FFA
0x180024fba  call    cs:__imp_GetLastError
0x180024fc1  nop     dword ptr [rax+rax+00h]
0x180024fc6  test    eax, eax
0x180024fc8  jz      short loc_180024FFA
0x180024fca  mov     rcx, cs:WPP_GLOBAL_Control
0x180024fd1  cmp     rcx, rbx
0x180024fd4  jz      short loc_180024FFA
0x180024fd6  test    [rcx+1Ch], r13d
0x180024fda  jz      short loc_180024FFA
0x180024fdc  cmp     [rcx+19h], dil
0x180024fe0  jb      short loc_180024FFA
0x180024fe2  mov     rcx, [rcx+10h]
0x180024fe6  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x180024fed  mov     edx, 1A0h
0x180024ff2  mov     r9d, eax
0x180024ff5  call    WPP_SF_d
0x180024ffa  mov     rcx, [rbp+hExistingToken]; hExistingToken
0x180024ffe  lea     rax, [rbp+TokenHandle]
0x180025002  xor     r8d, r8d; lpTokenAttributes
0x180025005  mov     [rsp+40h+phNewToken], rax; phNewToken
0x18002500a  mov     r9d, edi; ImpersonationLevel
0x18002500d  mov     [rsp+40h+TokenType], edi; TokenType
0x180025011  lea     edx, [r8+6]; dwDesiredAccess
0x180025015  call    cs:__imp_DuplicateTokenEx
0x18002501c  nop     dword ptr [rax+rax+00h]
0x180025021  test    eax, eax
0x180025023  jnz     loc_180025229
0x180025029  call    cs:__imp_GetLastError
0x180025030  nop     dword ptr [rax+rax+00h]
0x180025035  test    eax, eax
0x180025037  jz      loc_180025229
0x18002503d  mov     rcx, cs:WPP_GLOBAL_Control
0x180025044  cmp     rcx, rbx
0x180025047  jz      loc_180025229
0x18002504d  test    [rcx+1Ch], r13d
0x180025051  jz      loc_180025229
0x180025057  cmp     [rcx+19h], dil
0x18002505b  jb      loc_180025229
0x180025061  mov     rcx, [rcx+10h]
0x180025065  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x18002506c  mov     edx, 1A1h
0x180025071  mov     r9d, eax
0x180025074  call    WPP_SF_d
0x180025079  jmp     loc_180025229
0x18002507e  mov     rcx, [rsi+50h]; ProcessHandle
0x180025082  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180025086  mov     edx, edi; DesiredAccess
0x180025088  call    cs:__imp_OpenProcessToken
0x18002508f  nop     dword ptr [rax+rax+00h]
0x180025094  test    eax, eax
0x180025096  jz      short loc_1800250A3
0x180025098  mov     r14d, 1
0x18002509e  jmp     loc_180025229
0x1800250a3  call    cs:__imp_GetLastError
0x1800250aa  nop     dword ptr [rax+rax+00h]
0x1800250af  test    eax, eax
0x1800250b1  jz      short loc_1800250E3
0x1800250b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800250ba  cmp     rcx, rbx
0x1800250bd  jz      short loc_1800250E3
0x1800250bf  test    [rcx+1Ch], r13d
0x1800250c3  jz      short loc_1800250E3
0x1800250c5  cmp     [rcx+19h], dil
0x1800250c9  jb      short loc_1800250E3
0x1800250cb  mov     rcx, [rcx+10h]
0x1800250cf  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x1800250d6  mov     edx, 1A2h
0x1800250db  mov     r9d, eax
0x1800250de  call    WPP_SF_d
0x1800250e3  xor     ecx, ecx; BindingHandle
0x1800250e5  call    cs:__imp_RpcImpersonateClient
0x1800250ec  nop     dword ptr [rax+rax+00h]
0x1800250f1  test    eax, eax
0x1800250f3  jz      short loc_180025173
0x1800250f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800250fc  cmp     rcx, rbx
0x1800250ff  jz      short loc_18002512C
0x180025101  test    [rcx+1Ch], r13d
0x180025105  jz      short loc_18002512C
0x180025107  cmp     byte ptr [rcx+19h], 3
0x18002510b  jb      short loc_18002512C
0x18002510d  mov     rcx, [rcx+10h]
0x180025111  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x180025118  mov     edx, 1A3h
0x18002511d  mov     r9d, eax
0x180025120  call    WPP_SF_d
0x180025125  mov     rcx, cs:WPP_GLOBAL_Control
0x18002512c  mov     r9d, 5
0x180025132  mov     ebx, r9d
0x180025135  lea     rsi, WPP_GLOBAL_Control
0x18002513c  cmp     rcx, rsi
0x18002513f  jz      loc_1800252FD
0x180025145  test    [rcx+1Ch], r13d
0x180025149  jz      loc_1800252FD
0x18002514f  cmp     [rcx+19h], dil
0x180025153  jb      loc_1800252FD
0x180025159  mov     edx, 1A4h
0x18002515e  mov     rcx, [rcx+10h]
0x180025162  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x180025169  call    WPP_SF_d
0x18002516e  jmp     loc_1800252FD
0x180025173  mov     rcx, [rsi+50h]; ProcessHandle
0x180025177  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18002517b  mov     edx, edi; DesiredAccess
0x18002517d  call    cs:__imp_OpenProcessToken
0x180025184  nop     dword ptr [rax+rax+00h]
0x180025189  test    eax, eax
0x18002518b  jnz     short loc_1800251F0
0x18002518d  call    cs:__imp_GetLastError
0x180025194  nop     dword ptr [rax+rax+00h]
0x180025199  mov     ebx, eax
0x18002519b  test    eax, eax
0x18002519d  jz      short loc_1800251D8
0x18002519f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800251a6  lea     rsi, WPP_GLOBAL_Control
0x1800251ad  cmp     rcx, rsi
0x1800251b0  jz      short loc_1800251DF
0x1800251b2  test    [rcx+1Ch], r13d
0x1800251b6  jz      short loc_1800251DF
0x1800251b8  cmp     [rcx+19h], dil
0x1800251bc  jb      short loc_1800251DF
0x1800251be  mov     rcx, [rcx+10h]
0x1800251c2  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x1800251c9  mov     edx, 1A5h
0x1800251ce  mov     r9d, eax
0x1800251d1  call    WPP_SF_d
0x1800251d6  jmp     short loc_1800251DF
0x1800251d8  lea     rsi, WPP_GLOBAL_Control
0x1800251df  call    cs:__imp_RpcRevertToSelf
0x1800251e6  nop     dword ptr [rax+rax+00h]
0x1800251eb  jmp     loc_1800252FD
0x1800251f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800251f7  cmp     rcx, rbx
0x1800251fa  jz      short loc_18002521D
0x1800251fc  test    [rcx+1Ch], r13d
0x180025200  jz      short loc_18002521D
0x180025202  cmp     byte ptr [rcx+19h], 4
0x180025206  jb      short loc_18002521D
0x180025208  mov     rcx, [rcx+10h]
0x18002520c  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x180025213  mov     edx, 1A6h
0x180025218  call    WPP_SF_
0x18002521d  call    cs:__imp_RpcRevertToSelf
0x180025224  nop     dword ptr [rax+rax+00h]
0x180025229  mov     rdx, [rbp+TokenHandle]
0x18002522d  mov     rcx, rsi
0x180025230  call    ApplyPostConnectionActions
0x180025235  mov     ebx, eax
0x180025237  test    eax, eax
0x180025239  jz      loc_1800252F6
0x18002523f  cmp     cs:g_RasMobileCore, 0
0x180025246  jnz     short loc_180025294
0x180025248  test    dword ptr [rsi+70h], 100h
0x18002524f  jz      short loc_180025294
0x180025251  mov     r9d, 5
0x180025257  cmp     eax, r9d
0x18002525a  jnz     short loc_180025294
0x18002525c  mov     rcx, cs:WPP_GLOBAL_Control
0x180025263  lea     rsi, WPP_GLOBAL_Control
0x18002526a  cmp     rcx, rsi
0x18002526d  jz      short loc_180025290
0x18002526f  test    [rcx+1Ch], r13d
0x180025273  jz      short loc_180025290
0x180025275  cmp     [rcx+19h], dil
0x180025279  jb      short loc_180025290
0x18002527b  mov     rcx, [rcx+10h]
0x18002527f  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x180025286  mov     edx, 1A7h
0x18002528b  call    WPP_SF_d
0x180025290  xor     ebx, ebx
0x180025292  jmp     short loc_1800252FD
0x180025294  mov     rcx, cs:WPP_GLOBAL_Control
0x18002529b  lea     rsi, WPP_GLOBAL_Control
0x1800252a2  cmp     rcx, rsi
0x1800252a5  jz      short loc_1800252FD
0x1800252a7  test    [rcx+1Ch], r13d
0x1800252ab  jz      short loc_1800252FD
0x1800252ad  cmp     [rcx+19h], dil
0x1800252b1  jb      short loc_1800252FD
0x1800252b3  mov     edx, 1A8h
  ... truncated ...
```
