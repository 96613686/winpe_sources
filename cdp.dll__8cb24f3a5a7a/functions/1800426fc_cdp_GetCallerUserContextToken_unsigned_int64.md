# cdp::GetCallerUserContextToken(unsigned __int64 &)

- ea: `0x1800426fc`
- end: `0x18004290e`
- name: `?GetCallerUserContextToken@cdp@@YAJAEA_K@Z`
- size: `530`
- prototype: `__int64 __fastcall(cdp *__hidden this, unsigned __int64 *)`
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180041880`
- `0x18005a380`
- `0x1800ec200`

## callees

- `0x1800426fc`
- `0x1800a29a0`
- `0x1800af0f0`
- `0x1800f504c`
- `0x18012d5cc`
- `0x1802093a8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180042769`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180042769`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180042753`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180042753`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004283a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004283a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800428b6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180042903`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800428b6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180042903`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18004271e`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18004271e`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x18004279a`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x18004279a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall cdp::GetCallerUserContextToken(cdp *this, unsigned __int64 *a2)
{
  HRESULT CurrentUserContextToken; // eax
  unsigned int v4; // ecx
  unsigned __int64 *v5; // rdx
  HANDLE CurrentThread; // rax
  void *v7; // rdi
  __int64 v8; // rdx
  __int64 v9; // rcx
  int UserContext; // eax
  int v11; // ecx
  int v12; // ecx
  signed int LastError; // eax
  int v15; // ecx
  signed int v16; // ebx
  _QWORD v17[2]; // [rsp+30h] [rbp-10h] BYREF
  int v18; // [rsp+60h] [rbp+20h] BYREF
  int v19; // [rsp+68h] [rbp+28h] BYREF
  int v20; // [rsp+70h] [rbp+30h] BYREF
  void *TokenHandle; // [rsp+78h] [rbp+38h] BYREF

  *(_QWORD *)this = 0;
  if ( !(unsigned __int8)IsUMgrQueryUserContextPresent(this, a2) )
    return 0;
  CurrentUserContextToken = CoImpersonateClient();
  v4 = 0x80000000;
  v5 = (unsigned __int64 *)(CurrentUserContextToken + 0x80000000);
  if ( (int)v5 >= 0 && CurrentUserContextToken != -2147417833 )
  {
    v19 = 187;
LABEL_14:
    v18 = CurrentUserContextToken;
    Log<long &,char const (&)[36],int>(
      v4,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"text\":\"Error:\"}",
      (unsigned int)&v18,
      (unsigned int)".\\platformutils.cpp",
      (__int64)&v19);
    return (unsigned int)v18;
  }
  if ( CurrentUserContextToken < 0 )
  {
    CurrentUserContextToken = cdp::GetCurrentUserContextToken(this, v5);
    if ( CurrentUserContextToken < 0 )
    {
      v19 = 212;
      goto LABEL_14;
    }
    return 0;
  }
  LOBYTE(v18) = 0;
  v17[0] = &v18;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle) )
  {
    ScopeWarden__lambda_2f66db1fdd6f01e0b9f89f17b55ae680___::_ScopeWarden__lambda_2f66db1fdd6f01e0b9f89f17b55ae680___(v17);
    v7 = TokenHandle;
    *(_QWORD *)this = 0;
    if ( (unsigned __int8)IsUMgrQueryUserContextPresent(v9, v8) )
    {
      UserContext = UMgrQueryUserContext(v7, this);
      if ( UserContext == -2147023584 )
      {
        *(_QWORD *)this = 0;
      }
      else if ( UserContext < 0 )
      {
        v18 = UserContext;
        v19 = 115;
        Log<long &,char const (&)[36],int>(
          v11,
          (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"text\":\"Error:\"}",
          (unsigned int)&v18,
          (unsigned int)".\\platformutils.cpp",
          (__int64)&v19);
        if ( v18 < 0 )
        {
          v19 = 208;
          Log<long &,char const (&)[36],int>(
            v12,
            (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"text\":\"Error:\"}",
            (unsigned int)&v18,
            (unsigned int)".\\platformutils.cpp",
            (__int64)&v19);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
          return (unsigned int)v18;
        }
      }
    }
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(TokenHandle);
    return 0;
  }
  LastError = GetLastError();
  v16 = LastError;
  if ( LastError > 0 )
    v16 = (unsigned __int16)LastError | 0x80070000;
  v19 = v16;
  if ( v16 < 0 )
  {
    v20 = 204;
    Log<long &,char const (&)[36],int>(
      v15,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"text\":\"Error:\"}",
      (unsigned int)&v19,
      (unsigned int)".\\platformutils.cpp",
      (__int64)&v20);
    v16 = v19;
  }
  ScopeWarden__lambda_2f66db1fdd6f01e0b9f89f17b55ae680___::_ScopeWarden__lambda_2f66db1fdd6f01e0b9f89f17b55ae680___(v17);
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(TokenHandle);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x1800426fc  push    rbp
0x1800426fe  push    rbx
0x1800426ff  push    rdi
0x180042700  mov     rbp, rsp
0x180042703  sub     rsp, 40h
0x180042707  mov     rbx, rcx
0x18004270a  mov     qword ptr [rcx], 0
0x180042711  call    IsUMgrQueryUserContextPresent
0x180042716  test    al, al
0x180042718  jz      loc_1800427F6
0x18004271e  call    cs:__imp_CoImpersonateClient
0x180042724  mov     ecx, 80000000h
0x180042729  lea     edx, [rax+rcx]; unsigned __int64 *
0x18004272c  test    ecx, edx
0x18004272e  jz      loc_180042800
0x180042734  shr     eax, 1Fh
0x180042737  xor     al, 1
0x180042739  jz      loc_18004286A
0x18004273f  mov     byte ptr [rbp+arg_0], 0
0x180042743  lea     rax, [rbp+arg_0]
0x180042747  mov     [rbp+var_10], rax
0x18004274b  mov     [rbp+TokenHandle], 0
0x180042753  call    cs:__imp_GetCurrentThread
0x180042759  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18004275d  mov     edx, 0Ch; DesiredAccess
0x180042762  lea     r8d, [rdx-0Bh]; OpenAsSelf
0x180042766  mov     rcx, rax; ThreadHandle
0x180042769  call    cs:__imp_OpenThreadToken
0x18004276f  test    eax, eax
0x180042771  jz      loc_18004283A
0x180042777  lea     rcx, [rbp+var_10]
0x18004277b  call    ScopeWarden__lambda_2f66db1fdd6f01e0b9f89f17b55ae680______ScopeWarden__lambda_2f66db1fdd6f01e0b9f89f17b55ae680___
0x180042780  mov     rdi, [rbp+TokenHandle]
0x180042784  mov     qword ptr [rbx], 0
0x18004278b  call    IsUMgrQueryUserContextPresent
0x180042790  test    al, al
0x180042792  jz      short loc_1800427E4
0x180042794  mov     rdx, rbx
0x180042797  mov     rcx, rdi
0x18004279a  call    cs:__imp_UMgrQueryUserContext
0x1800427a0  cmp     eax, 80070520h
0x1800427a5  jz      loc_1800428BE
0x1800427ab  test    eax, eax
0x1800427ad  jns     short loc_1800427E4
0x1800427af  mov     [rbp+arg_0], eax
0x1800427b2  mov     [rbp+arg_8], 73h ; 's'
0x1800427b9  lea     rax, [rbp+arg_8]
0x1800427bd  mov     [rsp+40h+var_20], rax
0x1800427c2  lea     r9, aPlatformutilsC; ".\\platformutils.cpp"
0x1800427c9  lea     r8, [rbp+arg_0]
0x1800427cd  lea     rdx, aHr0x08xFileSLi_93; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1800427d4  call    ??$Log@AEAJAEAY0CE@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CE@$$CBD$$QEAH@Z; Log<long &,char const (&)[36],int>(CDPLogLevel,char const *,long &,char const (&)[36],int &&)
0x1800427d9  mov     eax, [rbp+arg_0]
0x1800427dc  test    eax, eax
0x1800427de  js      loc_1800428CA
0x1800427e4  mov     rcx, [rbp+TokenHandle]; hObject
0x1800427e8  lea     rax, [rcx-1]
0x1800427ec  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800427f0  jbe     loc_180042903
0x1800427f6  xor     eax, eax
0x1800427f8  add     rsp, 40h
0x1800427fc  pop     rdi
0x1800427fd  pop     rbx
0x1800427fe  pop     rbp
0x1800427ff  retn
0x180042800  cmp     eax, 80010117h
0x180042805  jz      loc_180042734
0x18004280b  mov     [rbp+arg_8], 0BBh
0x180042812  mov     [rbp+arg_0], eax
0x180042815  lea     rax, [rbp+arg_8]
0x180042819  mov     [rsp+40h+var_20], rax
0x18004281e  lea     r9, aPlatformutilsC; ".\\platformutils.cpp"
0x180042825  lea     r8, [rbp+arg_0]
0x180042829  lea     rdx, aHr0x08xFileSLi_93; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x180042830  call    ??$Log@AEAJAEAY0CE@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CE@$$CBD$$QEAH@Z; Log<long &,char const (&)[36],int>(CDPLogLevel,char const *,long &,char const (&)[36],int &&)
0x180042835  mov     eax, [rbp+arg_0]
0x180042838  jmp     short loc_1800427F8
0x18004283a  call    cs:__imp_GetLastError
0x180042840  nop
0x180042841  mov     ebx, eax
0x180042843  test    eax, eax
0x180042845  jg      short loc_18004287F
0x180042847  mov     [rbp+arg_8], ebx
0x18004284a  test    ebx, ebx
0x18004284c  js      short loc_18004288A
0x18004284e  lea     rcx, [rbp+var_10]
0x180042852  call    ScopeWarden__lambda_2f66db1fdd6f01e0b9f89f17b55ae680______ScopeWarden__lambda_2f66db1fdd6f01e0b9f89f17b55ae680___
0x180042857  nop
0x180042858  mov     rcx, [rbp+TokenHandle]; hObject
0x18004285c  lea     rdx, [rcx-1]
0x180042860  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180042864  jbe     short loc_1800428B6
0x180042866  mov     eax, ebx
0x180042868  jmp     short loc_1800427F8
0x18004286a  mov     rcx, rbx; this
0x18004286d  call    ?GetCurrentUserContextToken@cdp@@YAJAEA_K@Z; cdp::GetCurrentUserContextToken(unsigned __int64 &)
0x180042872  test    eax, eax
0x180042874  jns     short loc_1800427F6
0x180042876  mov     [rbp+arg_8], 0D4h
0x18004287d  jmp     short loc_180042812
0x18004287f  movzx   ebx, ax
0x180042882  or      ebx, 80070000h
0x180042888  jmp     short loc_180042847
0x18004288a  mov     [rbp+arg_10], 0CCh
0x180042891  lea     rax, [rbp+arg_10]
0x180042895  mov     [rsp+40h+var_20], rax
0x18004289a  lea     r9, aPlatformutilsC; ".\\platformutils.cpp"
0x1800428a1  lea     r8, [rbp+arg_8]
0x1800428a5  lea     rdx, aHr0x08xFileSLi_93; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1800428ac  call    ??$Log@AEAJAEAY0CE@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CE@$$CBD$$QEAH@Z; Log<long &,char const (&)[36],int>(CDPLogLevel,char const *,long &,char const (&)[36],int &&)
0x1800428b1  mov     ebx, [rbp+arg_8]
0x1800428b4  jmp     short loc_18004284E
0x1800428b6  call    cs:__imp_CloseHandle
0x1800428bc  jmp     short loc_180042866
0x1800428be  mov     qword ptr [rbx], 0
0x1800428c5  jmp     loc_1800427E4
0x1800428ca  mov     [rbp+arg_0], eax
0x1800428cd  mov     [rbp+arg_8], 0D0h
0x1800428d4  lea     rax, [rbp+arg_8]
0x1800428d8  mov     [rsp+40h+var_20], rax
0x1800428dd  lea     r9, aPlatformutilsC; ".\\platformutils.cpp"
0x1800428e4  lea     r8, [rbp+arg_0]
0x1800428e8  lea     rdx, aHr0x08xFileSLi_93; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1800428ef  call    ??$Log@AEAJAEAY0CE@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CE@$$CBD$$QEAH@Z; Log<long &,char const (&)[36],int>(CDPLogLevel,char const *,long &,char const (&)[36],int &&)
0x1800428f4  nop
0x1800428f5  lea     rcx, [rbp+TokenHandle]
0x1800428f9  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800428fe  jmp     loc_180042835
0x180042903  call    cs:__imp_CloseHandle
0x180042909  jmp     loc_1800427F6
```
