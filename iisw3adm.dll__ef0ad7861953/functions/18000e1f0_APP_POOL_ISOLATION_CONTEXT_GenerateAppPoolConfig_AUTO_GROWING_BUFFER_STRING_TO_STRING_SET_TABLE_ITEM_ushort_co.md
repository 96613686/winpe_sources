# APP_POOL_ISOLATION_CONTEXT::GenerateAppPoolConfig(AUTO_GROWING_BUFFER *,STRING_TO_STRING_SET_TABLE_ITEM *,ushort const *,ulong *,STRU *)

- ea: `0x18000e1f0`
- end: `0x18000e4d5`
- name: `?GenerateAppPoolConfig@APP_POOL_ISOLATION_CONTEXT@@QEAAJPEAVAUTO_GROWING_BUFFER@@PEAVSTRING_TO_STRING_SET_TABLE_ITEM@@PEBGPEAKPEAVSTRU@@@Z`
- size: `741`
- prototype: `__int64 __fastcall(const unsigned __int16 **this, struct AUTO_GROWING_BUFFER *, struct STRING_TO_STRING_SET_TABLE_ITEM *, const unsigned __int16 *, unsigned int *, struct STRU *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000ca78`

## callees

- `0x180005878`
- `0x18000c4e4`
- `0x18000d6b8`
- `0x18000e01c`
- `0x18000e1f0`
- `0x18006101a`
- `0x180061060`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e360`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e371`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e360`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e371`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000e34b`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000e34b`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18000e442`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18000e442`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000e3da`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000e405`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000e3da`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000e405`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18000e3f7`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18000e3f7`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000e496`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000e4a0`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000e4aa`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000e496`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000e4a0`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000e4aa`
- `iisutil!PuDbgPrint` at `0x18000e307`
- `iisutil!PuDbgPrint` at `0x18000e307`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000e419`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000e419`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000e266`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000e28b`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000e2b1`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000e266`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000e28b`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000e2b1`

## string_xrefs

- `0x18000e2fb`: `Generating App Pool Config (pool: %S; wpsid: %S)\n`
- `0x18000e2cf`: `APP_POOL_ISOLATION_CONTEXT::GenerateAppPoolConfig`
- `0x18000e2dd`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\app_pool_isolation_context.cxx`

## pseudocode

```c
__int64 __fastcall APP_POOL_ISOLATION_CONTEXT::GenerateAppPoolConfig(
        const unsigned __int16 **this,
        struct AUTO_GROWING_BUFFER *a2,
        struct STRING_TO_STRING_SET_TABLE_ITEM *a3,
        const unsigned __int16 *a4,
        unsigned int *a5,
        struct STRU *a6)
{
  unsigned int *v7; // rdi
  const wchar_t **v10; // rbx
  unsigned __int16 *v11; // rsi
  const wchar_t *v12; // rax
  const unsigned __int16 *v13; // rdx
  int AppPoolFilePath; // ebx
  unsigned __int16 *v15; // rdi
  int v16; // r14d
  signed int LastError; // eax
  int v18; // eax
  unsigned __int16 *v20[2]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int *v21; // [rsp+50h] [rbp-B0h]
  struct AUTO_GROWING_BUFFER *v22; // [rsp+58h] [rbp-A8h]
  _BYTE v23[32]; // [rsp+60h] [rbp-A0h] BYREF
  LPCWSTR lpFileName; // [rsp+80h] [rbp-80h]
  _BYTE v25[32]; // [rsp+98h] [rbp-68h] BYREF
  LPCWSTR lpNewFileName; // [rsp+B8h] [rbp-48h]
  _BYTE v27[32]; // [rsp+D0h] [rbp-30h] BYREF
  LPCWSTR lpPathName; // [rsp+F0h] [rbp-10h]
  unsigned __int16 v29[264]; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int16 v30[264]; // [rsp+320h] [rbp+220h] BYREF
  unsigned __int16 v31[264]; // [rsp+530h] [rbp+430h] BYREF

  v7 = a5;
  v22 = a2;
  v21 = a5;
  v20[0] = (unsigned __int16 *)a6;
  memset_0(v29, 0, 0x208u);
  STRU::STRU((STRU *)v27, v29, 0x104u);
  memset_0(v30, 0, 0x208u);
  STRU::STRU((STRU *)v25, v30, 0x104u);
  memset_0(v31, 0, 0x208u);
  STRU::STRU((STRU *)v23, v31, 0x104u);
  v10 = (const wchar_t **)((char *)a3 + 8);
  v11 = (unsigned __int16 *)&SourceString;
  if ( (g_dwDebugFlags & 3) != 0 )
  {
    v12 = &SourceString;
    if ( *v10 )
      v12 = *v10;
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\app_pool_isolation_context.cxx",
      116,
      "APP_POOL_ISOLATION_CONTEXT::GenerateAppPoolConfig",
      "Generating App Pool Config (pool: %S; wpsid: %S)\n",
      v12,
      a4);
  }
  v13 = &SourceString;
  if ( *v10 )
    v13 = *v10;
  AppPoolFilePath = APP_POOL_ISOLATION::MakeAppPoolFilePath(
                      this[2],
                      v13,
                      (struct STRU *)v27,
                      (struct STRU *)v25,
                      (struct STRU *)v23);
  if ( AppPoolFilePath >= 0 )
  {
    if ( CreateDirectoryW(lpPathName, 0) )
    {
      v16 = 1;
    }
    else
    {
      v15 = (unsigned __int16 *)&SourceString;
      if ( !GetLastError() )
      {
        AppPoolFilePath = -2147467259;
        goto LABEL_31;
      }
      v16 = 0;
      LastError = GetLastError();
      AppPoolFilePath = LastError;
      if ( LastError > 0 )
        AppPoolFilePath = (unsigned __int16)LastError | 0x80070000;
      if ( AppPoolFilePath != -2147024713 )
      {
        if ( AppPoolFilePath >= 0 )
          goto LABEL_36;
LABEL_28:
        if ( v16 )
          RemoveDirectoryW(lpPathName);
        goto LABEL_31;
      }
      v7 = v21;
    }
    AppPoolFilePath = APP_POOL_ISOLATION::CreateAndSetFileACL(lpFileName, a4);
    if ( AppPoolFilePath >= 0 )
    {
      v18 = APP_POOL_ISOLATION_CONTEXT::CustomizeForAppPool((APP_POOL_ISOLATION_CONTEXT *)this, v22, a3, lpFileName);
      AppPoolFilePath = v18;
      if ( v18 >= 0 )
      {
        if ( !MoveFileExW(lpFileName, lpNewFileName, 1u) )
        {
          DeleteFileW(lpFileName);
          goto LABEL_36;
        }
        AppPoolFilePath = STRU::Copy((STRU *)v20[0], lpNewFileName);
        if ( AppPoolFilePath >= 0 )
        {
          *v7 = *(_DWORD *)this;
          goto LABEL_36;
        }
        v15 = L"8";
      }
      else
      {
        if ( v18 == -2147467260 )
          DeleteFileW(lpFileName);
        v15 = L"4";
      }
    }
    else
    {
      v15 = L"5";
    }
    goto LABEL_28;
  }
  v15 = L"2";
LABEL_31:
  if ( *v15 != 52 || AppPoolFilePath != -2147467260 )
  {
    if ( *((_QWORD *)a3 + 1) )
      v11 = (unsigned __int16 *)*((_QWORD *)a3 + 1);
    v20[0] = v11;
    v20[1] = v15;
    WEB_ADMIN_SERVICE::LogEvent(
      g_pWebAdminService,
      0xC0001445,
      2u,
      (const unsigned __int16 **const)v20,
      AppPoolFilePath);
  }
LABEL_36:
  STRU::~STRU((STRU *)v23);
  STRU::~STRU((STRU *)v25);
  STRU::~STRU((STRU *)v27);
  return (unsigned int)AppPoolFilePath;
}

```

## disassembly

```asm
0x18000e1f0  push    rbp
0x18000e1f2  push    rbx
0x18000e1f3  push    rsi
0x18000e1f4  push    rdi
0x18000e1f5  push    r12
0x18000e1f7  push    r13
0x18000e1f9  push    r14
0x18000e1fb  push    r15
0x18000e1fd  lea     rbp, [rsp-658h]
0x18000e205  sub     rsp, 758h
0x18000e20c  mov     rax, cs:__security_cookie
0x18000e213  xor     rax, rsp
0x18000e216  mov     [rbp+690h+var_50], rax
0x18000e21d  mov     rax, [rbp+690h+arg_28]
0x18000e224  mov     r13, r8
0x18000e227  mov     rdi, [rbp+690h+arg_20]
0x18000e22e  mov     r15, rcx
0x18000e231  mov     [rsp+790h+var_738], rdx
0x18000e236  lea     rcx, [rbp+690h+var_680]; void *
0x18000e23a  mov     esi, 208h
0x18000e23f  mov     [rsp+790h+var_740], rdi
0x18000e244  mov     r8d, esi; Size
0x18000e247  mov     [rsp+790h+var_750], rax
0x18000e24c  xor     edx, edx; Val
0x18000e24e  mov     r12, r9
0x18000e251  call    memset_0
0x18000e256  mov     ebx, 104h
0x18000e25b  lea     rdx, [rbp+690h+var_680]
0x18000e25f  mov     r8d, ebx
0x18000e262  lea     rcx, [rbp+690h+var_6C0]
0x18000e266  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000e26c  mov     r8d, esi; Size
0x18000e26f  lea     rcx, [rbp+690h+var_470]; void *
0x18000e276  xor     edx, edx; Val
0x18000e278  call    memset_0
0x18000e27d  mov     r8d, ebx
0x18000e280  lea     rdx, [rbp+690h+var_470]
0x18000e287  lea     rcx, [rbp+690h+var_6F8]
0x18000e28b  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000e291  mov     r8d, esi; Size
0x18000e294  lea     rcx, [rbp+690h+var_260]; void *
0x18000e29b  xor     edx, edx; Val
0x18000e29d  call    memset_0
0x18000e2a2  mov     r8d, ebx
0x18000e2a5  lea     rdx, [rbp+690h+var_260]
0x18000e2ac  lea     rcx, [rsp+790h+var_730]
0x18000e2b1  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000e2b7  test    byte ptr cs:g_dwDebugFlags, 3
0x18000e2be  lea     rbx, [r13+8]
0x18000e2c2  lea     rsi, SourceString
0x18000e2c9  jz      short loc_18000E30D
0x18000e2cb  cmp     qword ptr [rbx], 0
0x18000e2cf  lea     r9, aAppPoolIsolati_2; "APP_POOL_ISOLATION_CONTEXT::GenerateApp"...
0x18000e2d6  mov     rcx, cs:g_pDebug
0x18000e2dd  lea     rdx, aServercommonIn_10; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000e2e4  mov     [rsp+790h+var_760], r12
0x18000e2e9  mov     rax, rsi
0x18000e2ec  cmovnz  rax, [rbx]
0x18000e2f0  mov     r8d, 74h ; 't'
0x18000e2f6  mov     [rsp+790h+var_768], rax
0x18000e2fb  lea     rax, aGeneratingAppP; "Generating App Pool Config (pool: %S; w"...
0x18000e302  mov     [rsp+790h+var_770], rax
0x18000e307  call    cs:__imp_PuDbgPrint
0x18000e30d  cmp     qword ptr [rbx], 0
0x18000e311  lea     rax, [rsp+790h+var_730]
0x18000e316  mov     rcx, [r15+10h]; unsigned __int16 *
0x18000e31a  lea     r9, [rbp+690h+var_6F8]; struct STRU *
0x18000e31e  mov     rdx, rsi
0x18000e321  mov     [rsp+790h+var_770], rax; struct STRU *
0x18000e326  cmovnz  rdx, [rbx]; unsigned __int16 *
0x18000e32a  lea     r8, [rbp+690h+var_6C0]; struct STRU *
0x18000e32e  call    ?MakeAppPoolFilePath@APP_POOL_ISOLATION@@SAJPEBG0PEAVSTRU@@11@Z; APP_POOL_ISOLATION::MakeAppPoolFilePath(ushort const *,ushort const *,STRU *,STRU *,STRU *)
0x18000e333  mov     ebx, eax
0x18000e335  test    eax, eax
0x18000e337  jns     short loc_18000E345
0x18000e339  lea     rdi, a2; "2"
0x18000e340  jmp     loc_18000E44F
0x18000e345  mov     rcx, [rbp+690h+lpPathName]; lpPathName
0x18000e349  xor     edx, edx; lpSecurityAttributes
0x18000e34b  call    cs:__imp_CreateDirectoryW
0x18000e351  test    eax, eax
0x18000e353  jz      short loc_18000E35D
0x18000e355  mov     r14d, 1
0x18000e35b  jmp     short loc_18000E397
0x18000e35d  mov     rdi, rsi
0x18000e360  call    cs:__imp_GetLastError
0x18000e366  test    eax, eax
0x18000e368  jz      loc_18000E44A
0x18000e36e  xor     r14d, r14d
0x18000e371  call    cs:__imp_GetLastError
0x18000e377  mov     ebx, eax
0x18000e379  test    eax, eax
0x18000e37b  jle     short loc_18000E386
0x18000e37d  movzx   ebx, ax
0x18000e380  or      ebx, 80070000h
0x18000e386  cmp     ebx, 800700B7h
0x18000e38c  jnz     loc_18000E435
0x18000e392  mov     rdi, [rsp+790h+var_740]
0x18000e397  mov     rcx, [rbp+690h+lpFileName]; lpFileName
0x18000e39b  mov     rdx, r12; unsigned __int16 *
0x18000e39e  call    ?CreateAndSetFileACL@APP_POOL_ISOLATION@@SAJPEBG0@Z; APP_POOL_ISOLATION::CreateAndSetFileACL(ushort const *,ushort const *)
0x18000e3a3  mov     ebx, eax
0x18000e3a5  test    eax, eax
0x18000e3a7  jns     short loc_18000E3B5
0x18000e3a9  lea     rdi, a5; "5"
0x18000e3b0  jmp     loc_18000E439
0x18000e3b5  mov     r9, [rbp+690h+lpFileName]; unsigned __int16 *
0x18000e3b9  mov     r8, r13; struct STRING_TO_STRING_SET_TABLE_ITEM *
0x18000e3bc  mov     rdx, [rsp+790h+var_738]; struct AUTO_GROWING_BUFFER *
0x18000e3c1  mov     rcx, r15; this
0x18000e3c4  call    ?CustomizeForAppPool@APP_POOL_ISOLATION_CONTEXT@@AEAAJPEAVAUTO_GROWING_BUFFER@@PEAVSTRING_TO_STRING_SET_TABLE_ITEM@@PEBG@Z; APP_POOL_ISOLATION_CONTEXT::CustomizeForAppPool(AUTO_GROWING_BUFFER *,STRING_TO_STRING_SET_TABLE_ITEM *,ushort const *)
0x18000e3c9  mov     ebx, eax
0x18000e3cb  test    eax, eax
0x18000e3cd  jns     short loc_18000E3E9
0x18000e3cf  cmp     eax, 80004004h
0x18000e3d4  jnz     short loc_18000E3E0
0x18000e3d6  mov     rcx, [rbp+690h+lpFileName]; lpFileName
0x18000e3da  call    cs:__imp_DeleteFileW
0x18000e3e0  lea     rdi, a4; "4"
0x18000e3e7  jmp     short loc_18000E439
0x18000e3e9  mov     rdx, [rbp+690h+lpNewFileName]; lpNewFileName
0x18000e3ed  mov     r8d, 1; dwFlags
0x18000e3f3  mov     rcx, [rbp+690h+lpFileName]; lpExistingFileName
0x18000e3f7  call    cs:__imp_MoveFileExW
0x18000e3fd  test    eax, eax
0x18000e3ff  jnz     short loc_18000E410
0x18000e401  mov     rcx, [rbp+690h+lpFileName]; lpFileName
0x18000e405  call    cs:__imp_DeleteFileW
0x18000e40b  jmp     loc_18000E491
0x18000e410  mov     rdx, [rbp+690h+lpNewFileName]
0x18000e414  mov     rcx, [rsp+790h+var_750]
0x18000e419  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000e41f  mov     ebx, eax
0x18000e421  test    eax, eax
0x18000e423  jns     short loc_18000E42E
0x18000e425  lea     rdi, a8; "8"
0x18000e42c  jmp     short loc_18000E439
0x18000e42e  mov     eax, [r15]
0x18000e431  mov     [rdi], eax
0x18000e433  jmp     short loc_18000E491
0x18000e435  test    ebx, ebx
0x18000e437  jns     short loc_18000E491
0x18000e439  test    r14d, r14d
0x18000e43c  jz      short loc_18000E44F
0x18000e43e  mov     rcx, [rbp+690h+lpPathName]; lpPathName
0x18000e442  call    cs:__imp_RemoveDirectoryW
0x18000e448  jmp     short loc_18000E44F
0x18000e44a  mov     ebx, 80004005h
0x18000e44f  cmp     word ptr [rdi], 34h ; '4'
0x18000e453  jnz     short loc_18000E45D
0x18000e455  cmp     ebx, 80004004h
0x18000e45b  jz      short loc_18000E491
0x18000e45d  cmp     qword ptr [r13+8], 0
0x18000e462  lea     r9, [rsp+790h+var_750]; unsigned __int16 **
0x18000e467  mov     rcx, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; this
0x18000e46e  mov     r8d, 2; unsigned __int16
0x18000e474  cmovnz  rsi, [r13+8]
0x18000e479  mov     edx, 0C0001445h; unsigned int
0x18000e47e  mov     [rsp+790h+var_750], rsi
0x18000e483  mov     [rsp+790h+var_748], rdi
0x18000e488  mov     dword ptr [rsp+790h+var_770], ebx; unsigned int
0x18000e48c  call    ?LogEvent@WEB_ADMIN_SERVICE@@QEAAXKGQEAPEBGK@Z; WEB_ADMIN_SERVICE::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x18000e491  lea     rcx, [rsp+790h+var_730]
0x18000e496  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000e49c  lea     rcx, [rbp+690h+var_6F8]
0x18000e4a0  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000e4a6  lea     rcx, [rbp+690h+var_6C0]
0x18000e4aa  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000e4b0  mov     eax, ebx
0x18000e4b2  mov     rcx, [rbp+690h+var_50]
0x18000e4b9  xor     rcx, rsp; StackCookie
0x18000e4bc  call    __security_check_cookie
0x18000e4c1  add     rsp, 758h
0x18000e4c8  pop     r15
0x18000e4ca  pop     r14
0x18000e4cc  pop     r13
0x18000e4ce  pop     r12
0x18000e4d0  pop     rdi
0x18000e4d1  pop     rsi
0x18000e4d2  pop     rbx
0x18000e4d3  pop     rbp
0x18000e4d4  retn
```
