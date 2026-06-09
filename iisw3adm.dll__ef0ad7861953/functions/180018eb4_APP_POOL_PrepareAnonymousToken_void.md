# APP_POOL::PrepareAnonymousToken(void)

- ea: `0x180018eb4`
- end: `0x180019137`
- name: `?PrepareAnonymousToken@APP_POOL@@AEAAJXZ`
- size: `643`
- prototype: `__int64 __fastcall(APP_POOL *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800263a4`

## callees

- `0x180018eb4`
- `0x18005f250`
- `0x180061060`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018fdf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018fdf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800190fd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800190fd`
- `api-ms-win-security-base-l1-1-0!CreateRestrictedToken` at `0x180018fd5`
- `api-ms-win-security-base-l1-1-0!CreateRestrictedToken` at `0x180018fd5`
- `iisutil!PuDbgPrintError` at `0x180018f94`
- `iisutil!PuDbgPrintError` at `0x180018f94`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18001910b`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18001910b`
- `iisutil!AllocateAndCreateWellKnownSid` at `0x180018f45`
- `iisutil!AllocateAndCreateWellKnownSid` at `0x18001904e`
- `iisutil!AllocateAndCreateWellKnownSid` at `0x180018f45`
- `iisutil!AllocateAndCreateWellKnownSid` at `0x18001904e`
- `iisutil!GetTokenUserSID` at `0x180019004`
- `iisutil!GetTokenUserSID` at `0x180019004`
- `iisutil!DupTokenAddAccess` at `0x18001909a`
- `iisutil!DupTokenAddAccess` at `0x18001909a`
- `iisutil!FreeWellKnownSid` at `0x1800190c6`
- `iisutil!FreeWellKnownSid` at `0x1800190ea`
- `iisutil!FreeWellKnownSid` at `0x1800190c6`
- `iisutil!FreeWellKnownSid` at `0x1800190ea`
- `iisutil!FreeTokenUserSID` at `0x1800190da`
- `iisutil!FreeTokenUserSID` at `0x1800190da`

## string_xrefs

- `0x180018f89`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\app_pool.cxx`
- `0x180018f69`: `Error retrieving Service Sid to disable in anonymous user token\n`
- `0x180018f7d`: `APP_POOL::PrepareAnonymousToken`
- `0x180019028`: `Error retrieving user SID from anonymous user token\n`
- `0x18001906e`: `Error retrieving Administrators SID for anonymous user token\n`

## pseudocode

```c
__int64 __fastcall APP_POOL::PrepareAnonymousToken(APP_POOL *this)
{
  __int64 v2; // rax
  void *ImpersonationToken; // rdi
  int v4; // eax
  unsigned int v5; // ebx
  signed int LastError; // eax
  bool v7; // cc
  int TokenUserSID; // eax
  int v9; // eax
  void *v11; // [rsp+50h] [rbp-49h] BYREF
  void *v12; // [rsp+58h] [rbp-41h] BYREF
  struct _TOKEN_USER *v13; // [rsp+60h] [rbp-39h] BYREF
  HANDLE hObject; // [rsp+68h] [rbp-31h] BYREF
  void *v15; // [rsp+70h] [rbp-29h] BYREF
  struct _SID_AND_ATTRIBUTES SidsToDisable; // [rsp+78h] [rbp-21h] BYREF
  _BYTE v17[32]; // [rsp+88h] [rbp-11h] BYREF
  __int128 *v18; // [rsp+A8h] [rbp+Fh]
  int v19; // [rsp+B0h] [rbp+17h]
  __int16 v20; // [rsp+B4h] [rbp+1Bh]
  __int128 v21; // [rsp+B8h] [rbp+1Fh] BYREF
  void *v22; // [rsp+C8h] [rbp+2Fh]

  v19 = 24;
  v15 = 0;
  v22 = 0;
  v13 = 0;
  v18 = &v21;
  v2 = *((_QWORD *)this + 11);
  v21 = 0;
  v11 = 0;
  v20 = 256;
  hObject = 0;
  v12 = 0;
  *(_QWORD *)&v21 = *(_QWORD *)(v2 + 728);
  ImpersonationToken = TOKEN_CACHE_ENTRY::QueryImpersonationToken(*((TOKEN_CACHE_ENTRY **)g_pWebAdminService + 174));
  v4 = AllocateAndCreateWellKnownSid(WinServiceSid, &v12);
  v5 = v4;
  if ( v4 )
  {
    if ( v4 > 0 )
      v5 = (unsigned __int16)v4 | 0x80070000;
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\app_pool.cxx",
        1057,
        "APP_POOL::PrepareAnonymousToken",
        v5,
        "Error retrieving Service Sid to disable in anonymous user token\n");
    goto LABEL_23;
  }
  SidsToDisable.Sid = v12;
  SidsToDisable.Attributes = 0;
  if ( !CreateRestrictedToken(ImpersonationToken, 0, 1u, &SidsToDisable, 0, 0, 0, 0, &hObject) )
  {
    LastError = GetLastError();
    v5 = LastError;
    v7 = LastError <= 0;
LABEL_9:
    if ( !v7 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_23;
  }
  TokenUserSID = GetTokenUserSID(ImpersonationToken, &v13);
  v5 = TokenUserSID;
  if ( TokenUserSID )
  {
    if ( TokenUserSID > 0 )
      v5 = (unsigned __int16)TokenUserSID | 0x80070000;
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\app_pool.cxx",
        1089,
        "APP_POOL::PrepareAnonymousToken",
        v5,
        "Error retrieving user SID from anonymous user token\n");
  }
  else
  {
    *((_QWORD *)&v21 + 1) = v13->User.Sid;
    v9 = AllocateAndCreateWellKnownSid(WinBuiltinAdministratorsSid, &v11);
    v5 = v9;
    if ( !v9 )
    {
      v22 = v11;
      LastError = DupTokenAddAccess(hObject, (void **)&v21, 3u, &v15);
      v5 = LastError;
      v7 = LastError <= 0;
      if ( !LastError )
      {
        v5 = 0;
        *((_QWORD *)this + 43) = v15;
        v15 = 0;
        goto LABEL_23;
      }
      goto LABEL_9;
    }
    if ( v9 > 0 )
      v5 = (unsigned __int16)v9 | 0x80070000;
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\app_pool.cxx",
        1106,
        "APP_POOL::PrepareAnonymousToken",
        v5,
        "Error retrieving Administrators SID for anonymous user token\n");
  }
LABEL_23:
  if ( v11 )
  {
    FreeWellKnownSid(&v11);
    v11 = 0;
  }
  if ( v13 )
    FreeTokenUserSID(&v13);
  if ( v12 )
  {
    FreeWellKnownSid(&v12);
    v12 = 0;
  }
  if ( hObject )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
  BUFFER::~BUFFER((BUFFER *)v17);
  return v5;
}

```

## disassembly

```asm
0x180018eb4  mov     [rsp-8+arg_8], rbx
0x180018eb9  mov     [rsp-8+arg_10], rsi
0x180018ebe  push    rbp
0x180018ebf  push    rdi
0x180018ec0  push    r14
0x180018ec2  lea     rbp, [rsp-47h]
0x180018ec7  sub     rsp, 0E0h
0x180018ece  mov     rax, cs:__security_cookie
0x180018ed5  xor     rax, rsp
0x180018ed8  mov     [rbp+57h+var_20], rax
0x180018edc  xor     r14d, r14d
0x180018edf  mov     [rbp+57h+var_40], 18h
0x180018ee6  xor     eax, eax
0x180018ee8  mov     [rbp+57h+var_80], r14
0x180018eec  mov     [rbp+57h+var_28], rax
0x180018ef0  mov     rsi, rcx
0x180018ef3  lea     rax, [rbp+57h+var_38]
0x180018ef7  mov     [rbp+57h+var_90], r14
0x180018efb  mov     [rbp+57h+var_48], rax
0x180018eff  xorps   xmm0, xmm0
0x180018f02  mov     rax, [rcx+58h]
0x180018f06  movups  [rbp+57h+var_38], xmm0
0x180018f0a  mov     [rbp+57h+var_A0], r14
0x180018f0e  mov     [rbp+57h+var_3C], 100h
0x180018f14  mov     [rbp+57h+hObject], r14
0x180018f18  mov     [rbp+57h+var_98], r14
0x180018f1c  mov     rcx, [rax+2D8h]
0x180018f23  mov     qword ptr [rbp+57h+var_38], rcx
0x180018f27  mov     rcx, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; WEB_ADMIN_SERVICE * g_pWebAdminService
0x180018f2e  mov     rcx, [rcx+570h]; this
0x180018f35  call    ?QueryImpersonationToken@TOKEN_CACHE_ENTRY@@QEAAPEAXXZ; TOKEN_CACHE_ENTRY::QueryImpersonationToken(void)
0x180018f3a  lea     rdx, [rbp+57h+var_98]
0x180018f3e  mov     rdi, rax
0x180018f41  lea     ecx, [r14+0Ch]
0x180018f45  call    cs:__imp_?AllocateAndCreateWellKnownSid@@YAKW4WELL_KNOWN_SID_TYPE@@PEAPEAX@Z; AllocateAndCreateWellKnownSid(WELL_KNOWN_SID_TYPE,void * *)
0x180018f4b  mov     ebx, eax
0x180018f4d  test    eax, eax
0x180018f4f  jz      short loc_180018F9F
0x180018f51  jle     short loc_180018F5C
0x180018f53  movzx   ebx, ax
0x180018f56  or      ebx, 80070000h
0x180018f5c  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180018f63  jz      loc_1800190BC
0x180018f69  lea     rax, aErrorRetrievin_1; "Error retrieving Service Sid to disable"...
0x180018f70  mov     r8d, 421h
0x180018f76  mov     rcx, cs:g_pDebug
0x180018f7d  lea     r9, aAppPoolPrepare; "APP_POOL::PrepareAnonymousToken"
0x180018f84  mov     [rsp+0F0h+PrivilegesToDelete], rax
0x180018f89  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180018f90  mov     [rsp+0F0h+DeletePrivilegeCount], ebx
0x180018f94  call    cs:__imp_PuDbgPrintError
0x180018f9a  jmp     loc_1800190BC
0x180018f9f  mov     rax, [rbp+57h+var_98]
0x180018fa3  lea     r9, [rbp+57h+SidsToDisable]; SidsToDisable
0x180018fa7  mov     [rbp+57h+SidsToDisable.Sid], rax
0x180018fab  xor     edx, edx; Flags
0x180018fad  lea     rax, [rbp+57h+hObject]
0x180018fb1  mov     [rbp+57h+SidsToDisable.Attributes], r14d
0x180018fb5  mov     [rsp+0F0h+NewTokenHandle], rax; NewTokenHandle
0x180018fba  mov     rcx, rdi; ExistingTokenHandle
0x180018fbd  mov     [rsp+0F0h+SidsToRestrict], r14; SidsToRestrict
0x180018fc2  mov     [rsp+0F0h+RestrictedSidCount], r14d; RestrictedSidCount
0x180018fc7  lea     r8d, [rdx+1]; DisableSidCount
0x180018fcb  mov     [rsp+0F0h+PrivilegesToDelete], r14; PrivilegesToDelete
0x180018fd0  mov     [rsp+0F0h+DeletePrivilegeCount], r14d; DeletePrivilegeCount
0x180018fd5  call    cs:__imp_CreateRestrictedToken
0x180018fdb  test    eax, eax
0x180018fdd  jnz     short loc_180018FFD
0x180018fdf  call    cs:__imp_GetLastError
0x180018fe5  mov     ebx, eax
0x180018fe7  test    eax, eax
0x180018fe9  jle     loc_1800190BC
0x180018fef  movzx   ebx, ax
0x180018ff2  or      ebx, 80070000h
0x180018ff8  jmp     loc_1800190BC
0x180018ffd  lea     rdx, [rbp+57h+var_90]
0x180019001  mov     rcx, rdi
0x180019004  call    cs:__imp_?GetTokenUserSID@@YAKPEAXPEAPEAU_TOKEN_USER@@@Z; GetTokenUserSID(void *,_TOKEN_USER * *)
0x18001900a  mov     ebx, eax
0x18001900c  test    eax, eax
0x18001900e  jz      short loc_18001903A
0x180019010  jle     short loc_18001901B
0x180019012  movzx   ebx, ax
0x180019015  or      ebx, 80070000h
0x18001901b  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180019022  jz      loc_1800190BC
0x180019028  lea     rax, aErrorRetrievin; "Error retrieving user SID from anonymou"...
0x18001902f  mov     r8d, 441h
0x180019035  jmp     loc_180018F76
0x18001903a  mov     rax, [rbp+57h+var_90]
0x18001903e  lea     rdx, [rbp+57h+var_A0]
0x180019042  mov     rcx, [rax]
0x180019045  mov     qword ptr [rbp+57h+var_38+8], rcx
0x180019049  mov     ecx, 1Ah
0x18001904e  call    cs:__imp_?AllocateAndCreateWellKnownSid@@YAKW4WELL_KNOWN_SID_TYPE@@PEAPEAX@Z; AllocateAndCreateWellKnownSid(WELL_KNOWN_SID_TYPE,void * *)
0x180019054  mov     ebx, eax
0x180019056  test    eax, eax
0x180019058  jz      short loc_180019080
0x18001905a  jle     short loc_180019065
0x18001905c  movzx   ebx, ax
0x18001905f  or      ebx, 80070000h
0x180019065  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18001906c  jz      short loc_1800190BC
0x18001906e  lea     rax, aErrorRetrievin_0; "Error retrieving Administrators SID for"...
0x180019075  mov     r8d, 452h
0x18001907b  jmp     loc_180018F76
0x180019080  mov     rax, [rbp+57h+var_A0]
0x180019084  lea     r9, [rbp+57h+var_80]
0x180019088  mov     rcx, [rbp+57h+hObject]
0x18001908c  lea     rdx, [rbp+57h+var_38]
0x180019090  mov     r8d, 3
0x180019096  mov     [rbp+57h+var_28], rax
0x18001909a  call    cs:__imp_?DupTokenAddAccess@@YAKPEAXPEAPEAXK1@Z; DupTokenAddAccess(void *,void * *,ulong,void * *)
0x1800190a0  mov     ebx, eax
0x1800190a2  test    eax, eax
0x1800190a4  jnz     loc_180018FE9
0x1800190aa  mov     rax, [rbp+57h+var_80]
0x1800190ae  mov     ebx, r14d
0x1800190b1  mov     [rsi+158h], rax
0x1800190b8  mov     [rbp+57h+var_80], r14
0x1800190bc  cmp     [rbp+57h+var_A0], r14
0x1800190c0  jz      short loc_1800190D0
0x1800190c2  lea     rcx, [rbp+57h+var_A0]
0x1800190c6  call    cs:__imp_?FreeWellKnownSid@@YAXPEAPEAX@Z; FreeWellKnownSid(void * *)
0x1800190cc  mov     [rbp+57h+var_A0], r14
0x1800190d0  cmp     [rbp+57h+var_90], r14
0x1800190d4  jz      short loc_1800190E0
0x1800190d6  lea     rcx, [rbp+57h+var_90]
0x1800190da  call    cs:__imp_?FreeTokenUserSID@@YAXPEAPEAU_TOKEN_USER@@@Z; FreeTokenUserSID(_TOKEN_USER * *)
0x1800190e0  cmp     [rbp+57h+var_98], r14
0x1800190e4  jz      short loc_1800190F4
0x1800190e6  lea     rcx, [rbp+57h+var_98]
0x1800190ea  call    cs:__imp_?FreeWellKnownSid@@YAXPEAPEAX@Z; FreeWellKnownSid(void * *)
0x1800190f0  mov     [rbp+57h+var_98], r14
0x1800190f4  mov     rcx, [rbp+57h+hObject]; hObject
0x1800190f8  test    rcx, rcx
0x1800190fb  jz      short loc_180019107
0x1800190fd  call    cs:__imp_CloseHandle
0x180019103  mov     [rbp+57h+hObject], r14
0x180019107  lea     rcx, [rbp+57h+var_68]
0x18001910b  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180019111  mov     eax, ebx
0x180019113  mov     rcx, [rbp+57h+var_20]
0x180019117  xor     rcx, rsp; StackCookie
0x18001911a  call    __security_check_cookie
0x18001911f  lea     r11, [rsp+0F0h+var_10]
0x180019127  mov     rbx, [r11+28h]
0x18001912b  mov     rsi, [r11+30h]
0x18001912f  mov     rsp, r11
0x180019132  pop     r14
0x180019134  pop     rdi
0x180019135  pop     rbp
0x180019136  retn
```
