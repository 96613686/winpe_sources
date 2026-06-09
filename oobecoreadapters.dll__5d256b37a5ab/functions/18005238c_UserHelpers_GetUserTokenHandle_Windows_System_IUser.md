# UserHelpers::GetUserTokenHandle(Windows::System::IUser *)

- ea: `0x18005238c`
- end: `0x18005251a`
- name: `?GetUserTokenHandle@UserHelpers@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@PEAUIUser@System@Windows@@@Z`
- size: `398`
- prototype: `__int64 __fastcall(PHANDLE TokenHandle, UserHelpers *this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800522d0`

## callees

- `0x180003a80`
- `0x180015544`
- `0x180052190`
- `0x18005238c`
- `0x180054340`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052430`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005246a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800524a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800524de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052430`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005246a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800524a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800524de`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180052460`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800524d0`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180052460`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800524d0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005244f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800524bf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005244f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800524bf`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180052422`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18005249f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180052422`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18005249f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005240f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005248a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005240f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005248a`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x1800523dd`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x1800523dd`

## string_xrefs

- `0x1800523f3`: `ShellCommon\internal\Shell\inc\helpers\UserHelpers.h`
- `0x1800524f9`: `ShellCommon\internal\Shell\inc\helpers\UserHelpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
PHANDLE __fastcall UserHelpers::GetUserTokenHandle(PHANDLE TokenHandle, UserHelpers *this)
{
  __int64 v4; // r8
  struct Windows::System::IUser *v5; // rdx
  unsigned __int64 UserContextToken; // rax
  int UserToken; // eax
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  HANDLE CurrentProcess; // rax
  __int64 v11; // r8
  HANDLE v12; // rax
  HANDLE v13; // rax
  bool v14; // sf
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  *TokenHandle = 0;
  if ( (unsigned __int8)IsUMgrGetConstrainedUserTokenPresent() && this )
  {
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      TokenHandle,
      0,
      v4);
    UserContextToken = UserHelpers::GetUserContextToken(this, v5);
    UserToken = UMgrQueryUserToken(UserContextToken, TokenHandle);
    if ( UserToken < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x66,
        (unsigned int)"ShellCommon\\internal\\Shell\\inc\\helpers\\UserHelpers.h",
        (const char *)(unsigned int)UserToken,
        1);
    return TokenHandle;
  }
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    TokenHandle,
    0,
    v4);
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 0, TokenHandle) )
    goto LABEL_18;
  LastError = GetLastError();
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  if ( LastError != -2147023888 )
    goto LABEL_21;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, TokenHandle) )
    goto LABEL_18;
  LastError = GetLastError();
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  if ( LastError != -2147023888 )
    goto LABEL_21;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    TokenHandle,
    0,
    v11);
  v12 = GetCurrentThread();
  if ( OpenThreadToken(v12, 8u, 1, TokenHandle) )
    goto LABEL_18;
  LastError = GetLastError();
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  if ( LastError != -2147023888 )
    goto LABEL_21;
  v13 = GetCurrentProcess();
  if ( OpenProcessToken(v13, 8u, TokenHandle) )
  {
LABEL_18:
    LastError = 0;
  }
  else
  {
    LastError = GetLastError();
    v14 = LastError < 0;
    if ( LastError <= 0 )
      goto LABEL_22;
    LastError = (unsigned __int16)LastError | 0x80070000;
  }
LABEL_21:
  v14 = LastError < 0;
LABEL_22:
  if ( v14 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x61,
      (unsigned int)"ShellCommon\\internal\\Shell\\inc\\helpers\\UserHelpers.h",
      (const char *)(unsigned int)LastError,
      1);
  return TokenHandle;
}

```

## disassembly

```asm
0x18005238c  mov     rax, rsp
0x18005238f  mov     [rax+10h], rbx
0x180052393  mov     [rax+8], rcx
0x180052397  push    rdi
0x180052398  sub     rsp, 30h
0x18005239c  mov     rdi, rdx
0x18005239f  mov     rbx, rcx
0x1800523a2  mov     dword ptr [rax-18h], 0
0x1800523a9  mov     qword ptr [rcx], 0
0x1800523b0  mov     dword ptr [rax-18h], 1
0x1800523b7  call    IsUMgrGetConstrainedUserTokenPresent
0x1800523bc  test    al, al
0x1800523be  jz      short loc_180052405
0x1800523c0  test    rdi, rdi
0x1800523c3  jz      short loc_180052405
0x1800523c5  xor     edx, edx
0x1800523c7  mov     rcx, rbx
0x1800523ca  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800523cf  mov     rcx, rdi; this
0x1800523d2  call    ?GetUserContextToken@UserHelpers@@YA_KPEAUIUser@System@Windows@@@Z; UserHelpers::GetUserContextToken(Windows::System::IUser *)
0x1800523d7  mov     rdx, rbx
0x1800523da  mov     rcx, rax
0x1800523dd  call    cs:__imp_UMgrQueryUserToken
0x1800523e3  test    eax, eax
0x1800523e5  jns     loc_18005250B
0x1800523eb  mov     rcx, [rsp+38h]; this
0x1800523f0  mov     r9d, eax; char *
0x1800523f3  lea     r8, aShellcommonInt_0; "ShellCommon\\internal\\Shell\\inc\\help"...
0x1800523fa  mov     edx, 66h ; 'f'; void *
0x1800523ff  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180052405  xor     edx, edx
0x180052407  mov     rcx, rbx
0x18005240a  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18005240f  call    cs:__imp_GetCurrentThread
0x180052415  mov     rcx, rax; ThreadHandle
0x180052418  mov     r9, rbx; TokenHandle
0x18005241b  xor     r8d, r8d; OpenAsSelf
0x18005241e  lea     edx, [r8+8]; DesiredAccess
0x180052422  call    cs:__imp_OpenThreadToken
0x180052428  test    eax, eax
0x18005242a  jnz     loc_1800524DA
0x180052430  call    cs:__imp_GetLastError
0x180052436  mov     edi, 80070000h
0x18005243b  test    eax, eax
0x18005243d  jle     short loc_180052444
0x18005243f  movzx   eax, ax
0x180052442  or      eax, edi
0x180052444  cmp     eax, 800703F0h
0x180052449  jnz     loc_1800524ED
0x18005244f  call    cs:__imp_GetCurrentProcess
0x180052455  mov     rcx, rax; ProcessHandle
0x180052458  mov     r8, rbx; TokenHandle
0x18005245b  mov     edx, 8; DesiredAccess
0x180052460  call    cs:__imp_OpenProcessToken
0x180052466  test    eax, eax
0x180052468  jnz     short loc_1800524DA
0x18005246a  call    cs:__imp_GetLastError
0x180052470  test    eax, eax
0x180052472  jle     short loc_180052479
0x180052474  movzx   eax, ax
0x180052477  or      eax, edi
0x180052479  cmp     eax, 800703F0h
0x18005247e  jnz     short loc_1800524ED
0x180052480  xor     edx, edx
0x180052482  mov     rcx, rbx
0x180052485  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18005248a  call    cs:__imp_GetCurrentThread
0x180052490  mov     rcx, rax; ThreadHandle
0x180052493  mov     r9, rbx; TokenHandle
0x180052496  mov     edx, 8; DesiredAccess
0x18005249b  lea     r8d, [rdx-7]; OpenAsSelf
0x18005249f  call    cs:__imp_OpenThreadToken
0x1800524a5  test    eax, eax
0x1800524a7  jnz     short loc_1800524DA
0x1800524a9  call    cs:__imp_GetLastError
0x1800524af  test    eax, eax
0x1800524b1  jle     short loc_1800524B8
0x1800524b3  movzx   eax, ax
0x1800524b6  or      eax, edi
0x1800524b8  cmp     eax, 800703F0h
0x1800524bd  jnz     short loc_1800524ED
0x1800524bf  call    cs:__imp_GetCurrentProcess
0x1800524c5  mov     rcx, rax; ProcessHandle
0x1800524c8  mov     r8, rbx; TokenHandle
0x1800524cb  mov     edx, 8; DesiredAccess
0x1800524d0  call    cs:__imp_OpenProcessToken
0x1800524d6  test    eax, eax
0x1800524d8  jz      short loc_1800524DE
0x1800524da  xor     eax, eax
0x1800524dc  jmp     short loc_1800524ED
0x1800524de  call    cs:__imp_GetLastError
0x1800524e4  test    eax, eax
0x1800524e6  jle     short loc_1800524EF
0x1800524e8  movzx   eax, ax
0x1800524eb  or      eax, edi
0x1800524ed  test    eax, eax
0x1800524ef  jns     short loc_18005250B
0x1800524f1  mov     rcx, [rsp+38h]; this
0x1800524f6  mov     r9d, eax; char *
0x1800524f9  lea     r8, aShellcommonInt_0; "ShellCommon\\internal\\Shell\\inc\\help"...
0x180052500  mov     edx, 61h ; 'a'; void *
0x180052505  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005250b  mov     rax, rbx
0x18005250e  mov     rbx, [rsp+38h+arg_8]
0x180052513  add     rsp, 30h
0x180052517  pop     rdi
0x180052518  retn
```
