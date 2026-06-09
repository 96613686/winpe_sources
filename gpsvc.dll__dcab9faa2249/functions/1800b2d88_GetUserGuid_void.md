# GetUserGuid(void *)

- ea: `0x1800b2d88`
- end: `0x1800b309a`
- name: `?GetUserGuid@@YAPEAGPEAX@Z`
- size: `786`
- prototype: `unsigned __int16 *__fastcall(HANDLE hToken)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800b2850`
- `0x1800b397c`

## callees

- `0x18001ae60`
- `0x180033140`
- `0x18005334c`
- `0x180075ec0`
- `0x18007d320`
- `0x1800b2d88`
- `0x1800b323c`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2e1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2e56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2e9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2eca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2f72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2fae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2fda`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2fe7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b3009`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b3038`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2e1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2e56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2e9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2eca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2f72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2fae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2fda`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2fe7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b3009`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b3038`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b305e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b305e`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800b2ee0`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800b2ee0`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800b2df7`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800b2df7`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800b306d`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800b306d`

## string_xrefs

- `0x1800b2e20`: `GetUserGuid: Failed to initialize system sid.  Error = %d`
- `0x1800b2e5c`: `GetUserGuid: Failed to initialize system sid.  Error = %d`
- `0x1800b2ea4`: `GetUserGuid: Couldn't get user sid,  Error = %d`
- `0x1800b2ed0`: `GetUserGuid: Couldn't get user sid,  Error = %d`
- `0x1800b2f03`: `GetUserGuid: user sid matches local system, returning NULL`
- `0x1800b2f33`: `GetUserGuid: user sid matches local system, returning NULL`
- `0x1800b2f78`: `GetUserGuid: Failed to impersonate user with %d.`
- `0x1800b2fb4`: `GetUserGuid: Failed to impersonate user with %d.`

## pseudocode

```c
unsigned __int16 *__fastcall GetUserGuid(HANDLE hToken)
{
  unsigned __int16 *UserName; // rsi
  void (*v3)(unsigned int, const unsigned __int16 *, ...); // rbx
  DWORD v4; // eax
  const wchar_t *v5; // rdx
  DWORD v6; // eax
  void *UserSid; // rax
  void *v8; // rdi
  DWORD v9; // eax
  enum EXTENDED_NAME_FORMAT v10; // ecx
  void (*v11)(unsigned int, const unsigned __int16 *, ...); // rbx
  DWORD v12; // eax
  DWORD v13; // eax
  void (*v14)(unsigned int, const unsigned __int16 *, ...); // rbx
  DWORD LastError; // eax
  DWORD v16; // eax
  PSID pSid2; // [rsp+60h] [rbp-20h] BYREF
  void *TokenHandle; // [rsp+68h] [rbp-18h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+70h] [rbp-10h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  TokenHandle = 0;
  UserName = 0;
  pSid2 = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &pSid2) )
  {
    UserSid = GetUserSid(hToken);
    v8 = UserSid;
    if ( UserSid )
    {
      if ( EqualSid(UserSid, pSid2) )
      {
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(4u, L"GetUserGuid: user sid matches local system, returning NULL");
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(4u, L"GetUserGuid: user sid matches local system, returning NULL");
          }
        }
      }
      else if ( (unsigned int)ImpersonateUser(hToken, &TokenHandle) )
      {
        UserName = MyGetUserNameEx(v10);
        if ( !UserName && GetLastError() != 1351 && GetLastError() != 1332 && *(_DWORD *)&g_dwDebugLevel )
        {
          v14 = g_lpDebugMsg;
          if ( g_lpDebugMsg )
          {
            LastError = GetLastError();
            v14(2u, L"GetUserGuid: Failed to get user guid with %d.", LastError);
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            v16 = GetLastError();
            RedirectDebugMsg(2u, L"GetUserGuid: Failed to get user guid with %d.", v16);
          }
        }
        RevertToUser(&TokenHandle);
      }
      else if ( *(_DWORD *)&g_dwDebugLevel )
      {
        v11 = g_lpDebugMsg;
        if ( g_lpDebugMsg )
        {
          v12 = GetLastError();
          v11(2u, L"GetUserGuid: Failed to impersonate user with %d.", v12);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          v13 = GetLastError();
          RedirectDebugMsg(2u, L"GetUserGuid: Failed to impersonate user with %d.", v13);
        }
      }
      LocalFree(v8);
    }
    else if ( *(_DWORD *)&g_dwDebugLevel )
    {
      v3 = g_lpDebugMsg;
      if ( g_lpDebugMsg )
      {
        v4 = GetLastError();
        v5 = L"GetUserGuid: Couldn't get user sid,  Error = %d";
        goto LABEL_5;
      }
      if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        v9 = GetLastError();
        RedirectDebugMsg(2u, L"GetUserGuid: Couldn't get user sid,  Error = %d", v9);
      }
    }
  }
  else
  {
    if ( !*(_DWORD *)&g_dwDebugLevel )
      goto LABEL_42;
    v3 = g_lpDebugMsg;
    if ( g_lpDebugMsg )
    {
      v4 = GetLastError();
      v5 = L"GetUserGuid: Failed to initialize system sid.  Error = %d";
LABEL_5:
      v3(2u, v5, v4);
      goto LABEL_42;
    }
    if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      v6 = GetLastError();
      RedirectDebugMsg(2u, L"GetUserGuid: Failed to initialize system sid.  Error = %d", v6);
    }
  }
LABEL_42:
  if ( pSid2 )
    FreeSid(pSid2);
  return UserName;
}

```

## disassembly

```asm
0x1800b2d88  mov     r11, rsp
0x1800b2d8b  mov     [r11+10h], rbx
0x1800b2d8f  mov     [r11+18h], rsi
0x1800b2d93  push    rbp
0x1800b2d94  push    rdi
0x1800b2d95  push    r14
0x1800b2d97  mov     rbp, rsp
0x1800b2d9a  sub     rsp, 80h
0x1800b2da1  mov     rax, cs:__security_cookie
0x1800b2da8  xor     rax, rsp
0x1800b2dab  mov     [rbp+var_8], rax
0x1800b2daf  xor     r14d, r14d
0x1800b2db2  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 500h
0x1800b2db8  lea     rax, [rbp+pSid2]
0x1800b2dbc  mov     [rbp+TokenHandle], r14
0x1800b2dc0  mov     [r11-48h], rax
0x1800b2dc4  mov     rbx, rcx
0x1800b2dc7  mov     [r11-50h], r14d
0x1800b2dcb  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x1800b2dcf  mov     [r11-58h], r14d
0x1800b2dd3  lea     r8d, [r14+12h]; nSubAuthority0
0x1800b2dd7  mov     [r11-60h], r14d
0x1800b2ddb  xor     r9d, r9d; nSubAuthority1
0x1800b2dde  mov     [r11-68h], r14d
0x1800b2de2  mov     dl, 1; nSubAuthorityCount
0x1800b2de4  mov     [r11-70h], r14d
0x1800b2de8  mov     esi, r14d
0x1800b2deb  mov     [r11-78h], r14d
0x1800b2def  mov     [rbp+pSid2], r14
0x1800b2df3  mov     dword ptr [rbp+pIdentifierAuthority.Value], r14d
0x1800b2df7  call    cs:__imp_AllocateAndInitializeSid
0x1800b2dfd  test    eax, eax
0x1800b2dff  jnz     short loc_1800B2E75
0x1800b2e01  cmp     cs:?g_dwDebugLevel@@3KA, r14d; ulong g_dwDebugLevel
0x1800b2e08  jz      loc_1800B3064
0x1800b2e0e  mov     rbx, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800b2e15  test    rbx, rbx
0x1800b2e18  jz      short loc_1800B2E3C
0x1800b2e1a  call    cs:__imp_GetLastError
0x1800b2e20  lea     rdx, aGetuserguidFai_0; "GetUserGuid: Failed to initialize syste"...
0x1800b2e27  mov     r8d, eax
0x1800b2e2a  mov     ecx, 2
0x1800b2e2f  mov     rax, rbx
0x1800b2e32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2e37  jmp     loc_1800B3064
0x1800b2e3c  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r14; void * g_lpDebugMsgContextInstance
0x1800b2e43  jz      loc_1800B3064
0x1800b2e49  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r14; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800b2e50  jz      loc_1800B3064
0x1800b2e56  call    cs:__imp_GetLastError
0x1800b2e5c  lea     rdx, aGetuserguidFai_0; "GetUserGuid: Failed to initialize syste"...
0x1800b2e63  mov     r8d, eax
0x1800b2e66  mov     ecx, 2; unsigned int
0x1800b2e6b  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800b2e70  jmp     loc_1800B3064
0x1800b2e75  mov     rcx, rbx; TokenHandle
0x1800b2e78  call    ?GetUserSid@@YAPEAXPEAX@Z; GetUserSid(void *)
0x1800b2e7d  mov     rdi, rax
0x1800b2e80  test    rax, rax
0x1800b2e83  jnz     short loc_1800B2ED9
0x1800b2e85  cmp     cs:?g_dwDebugLevel@@3KA, r14d; ulong g_dwDebugLevel
0x1800b2e8c  jz      loc_1800B3064
0x1800b2e92  mov     rbx, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800b2e99  test    rbx, rbx
0x1800b2e9c  jz      short loc_1800B2EB0
0x1800b2e9e  call    cs:__imp_GetLastError
0x1800b2ea4  lea     rdx, aGetuserguidCou; "GetUserGuid: Couldn't get user sid,  Er"...
0x1800b2eab  jmp     loc_1800B2E27
0x1800b2eb0  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r14; void * g_lpDebugMsgContextInstance
0x1800b2eb7  jz      loc_1800B3064
0x1800b2ebd  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r14; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800b2ec4  jz      loc_1800B3064
0x1800b2eca  call    cs:__imp_GetLastError
0x1800b2ed0  lea     rdx, aGetuserguidCou; "GetUserGuid: Couldn't get user sid,  Er"...
0x1800b2ed7  jmp     short loc_1800B2E63
0x1800b2ed9  mov     rdx, [rbp+pSid2]; pSid2
0x1800b2edd  mov     rcx, rdi; pSid1
0x1800b2ee0  call    cs:__imp_EqualSid
0x1800b2ee6  test    eax, eax
0x1800b2ee8  jz      short loc_1800B2F49
0x1800b2eea  cmp     cs:?g_dwDebugLevel@@3KA, r14d; ulong g_dwDebugLevel
0x1800b2ef1  jz      loc_1800B305B
0x1800b2ef7  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800b2efe  test    rax, rax
0x1800b2f01  jz      short loc_1800B2F19
0x1800b2f03  lea     rdx, aGetuserguidUse; "GetUserGuid: user sid matches local sys"...
0x1800b2f0a  mov     ecx, 4
0x1800b2f0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2f14  jmp     loc_1800B305B
0x1800b2f19  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r14; void * g_lpDebugMsgContextInstance
0x1800b2f20  jz      loc_1800B305B
0x1800b2f26  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r14; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800b2f2d  jz      loc_1800B305B
0x1800b2f33  lea     rdx, aGetuserguidUse; "GetUserGuid: user sid matches local sys"...
0x1800b2f3a  mov     ecx, 4; unsigned int
0x1800b2f3f  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800b2f44  jmp     loc_1800B305B
0x1800b2f49  lea     rdx, [rbp+TokenHandle]; TokenHandle
0x1800b2f4d  mov     rcx, rbx; hToken
0x1800b2f50  call    ?ImpersonateUser@@YAHPEAXPEAPEAX@Z; ImpersonateUser(void *,void * *)
0x1800b2f55  test    eax, eax
0x1800b2f57  jnz     short loc_1800B2FCD
0x1800b2f59  cmp     cs:?g_dwDebugLevel@@3KA, r14d; ulong g_dwDebugLevel
0x1800b2f60  jz      loc_1800B305B
0x1800b2f66  mov     rbx, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800b2f6d  test    rbx, rbx
0x1800b2f70  jz      short loc_1800B2F94
0x1800b2f72  call    cs:__imp_GetLastError
0x1800b2f78  lea     rdx, aGetuserguidFai_1; "GetUserGuid: Failed to impersonate user"...
0x1800b2f7f  mov     ecx, 2
0x1800b2f84  mov     r8d, eax
0x1800b2f87  mov     rax, rbx
0x1800b2f8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2f8f  jmp     loc_1800B305B
0x1800b2f94  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r14; void * g_lpDebugMsgContextInstance
0x1800b2f9b  jz      loc_1800B305B
0x1800b2fa1  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r14; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800b2fa8  jz      loc_1800B305B
0x1800b2fae  call    cs:__imp_GetLastError
0x1800b2fb4  lea     rdx, aGetuserguidFai_1; "GetUserGuid: Failed to impersonate user"...
0x1800b2fbb  mov     ecx, 2; unsigned int
0x1800b2fc0  mov     r8d, eax
0x1800b2fc3  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800b2fc8  jmp     loc_1800B305B
0x1800b2fcd  call    ?MyGetUserNameEx@@YAPEAGW4EXTENDED_NAME_FORMAT@@@Z; MyGetUserNameEx(EXTENDED_NAME_FORMAT)
0x1800b2fd2  mov     rsi, rax
0x1800b2fd5  test    rax, rax
0x1800b2fd8  jnz     short loc_1800B3052
0x1800b2fda  call    cs:__imp_GetLastError
0x1800b2fe0  cmp     eax, 547h
0x1800b2fe5  jz      short loc_1800B3052
0x1800b2fe7  call    cs:__imp_GetLastError
0x1800b2fed  cmp     eax, 534h
0x1800b2ff2  jz      short loc_1800B3052
0x1800b2ff4  cmp     cs:?g_dwDebugLevel@@3KA, r14d; ulong g_dwDebugLevel
0x1800b2ffb  jz      short loc_1800B3052
0x1800b2ffd  mov     rbx, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800b3004  test    rbx, rbx
0x1800b3007  jz      short loc_1800B3026
0x1800b3009  call    cs:__imp_GetLastError
0x1800b300f  mov     r8d, eax
0x1800b3012  lea     rdx, aGetuserguidFai; "GetUserGuid: Failed to get user guid wi"...
0x1800b3019  mov     rax, rbx
0x1800b301c  lea     ecx, [rsi+2]
0x1800b301f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3024  jmp     short loc_1800B3052
0x1800b3026  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r14; void * g_lpDebugMsgContextInstance
0x1800b302d  jz      short loc_1800B3052
0x1800b302f  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r14; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800b3036  jz      short loc_1800B3052
0x1800b3038  call    cs:__imp_GetLastError
0x1800b303e  lea     rdx, aGetuserguidFai; "GetUserGuid: Failed to get user guid wi"...
0x1800b3045  mov     ecx, 2; unsigned int
0x1800b304a  mov     r8d, eax
0x1800b304d  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800b3052  lea     rcx, [rbp+TokenHandle]; void **
0x1800b3056  call    ?RevertToUser@@YAHPEAPEAX@Z; RevertToUser(void * *)
0x1800b305b  mov     rcx, rdi; hMem
0x1800b305e  call    cs:__imp_LocalFree
0x1800b3064  mov     rcx, [rbp+pSid2]; pSid
0x1800b3068  test    rcx, rcx
0x1800b306b  jz      short loc_1800B3073
0x1800b306d  call    cs:__imp_FreeSid
0x1800b3073  mov     rax, rsi
0x1800b3076  mov     rcx, [rbp+var_8]
0x1800b307a  xor     rcx, rsp; StackCookie
0x1800b307d  call    __security_check_cookie
0x1800b3082  lea     r11, [rsp+80h+var_s0]
0x1800b308a  mov     rbx, [r11+28h]
0x1800b308e  mov     rsi, [r11+30h]
0x1800b3092  mov     rsp, r11
0x1800b3095  pop     r14
0x1800b3097  pop     rdi
0x1800b3098  pop     rbp
0x1800b3099  retn
```
