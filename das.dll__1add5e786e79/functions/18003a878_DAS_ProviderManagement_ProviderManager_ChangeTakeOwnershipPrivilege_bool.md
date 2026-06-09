# DAS::ProviderManagement::ProviderManager::ChangeTakeOwnershipPrivilege(bool)

- ea: `0x18003a878`
- end: `0x18003aa1e`
- name: `?ChangeTakeOwnershipPrivilege@ProviderManager@ProviderManagement@DAS@@CAJ_N@Z`
- size: `422`
- prototype: `__int64 __fastcall(unsigned __int8)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18003a3ac`
- `0x18003a3ec`

## callees

- `0x180005798`
- `0x180019cbc`
- `0x18002a948`
- `0x18002aa34`
- `0x18003a878`
- `0x18003bc80`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a8ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a8ca`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18003a906`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18003a906`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003a8f2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003a8f2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003a8ae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003a8ae`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003a8c0`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003a8c0`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18003a9df`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18003a9df`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x18003a94d`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x18003a988`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x18003a94d`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x18003a988`

## string_xrefs

- `0x18003a944`: `SeTakeOwnershipPrivilege`
- `0x18003a97f`: `SeRestorePrivilege`

## pseudocode

```c
__int64 __fastcall DAS::ProviderManagement::ProviderManager::ChangeTakeOwnershipPrivilege(unsigned __int8 a1)
{
  int v1; // edi
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  unsigned int v4; // ebx
  HANDLE CurrentThread; // rax
  const char *v6; // r9
  __int64 v7; // rdx
  int PreviousState; // [rsp+20h] [rbp-50h]
  void *TokenHandle; // [rsp+30h] [rbp-40h] BYREF
  _LUID Luid; // [rsp+38h] [rbp-38h] BYREF
  struct _LUID v12; // [rsp+40h] [rbp-30h] BYREF
  _TOKEN_PRIVILEGES NewState; // [rsp+48h] [rbp-28h] BYREF
  struct _LUID v14; // [rsp+58h] [rbp-18h]
  DWORD Attributes; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+8h]

  v1 = a1;
  TokenHandle = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &TokenHandle,
    0);
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0x20u, &TokenHandle) )
    goto LABEL_9;
  LastError = GetLastError();
  v4 = LastError;
  if ( LastError > 0 )
    v4 = (unsigned __int16)LastError | 0x80070000;
  if ( v4 == -2147024891 )
  {
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &TokenHandle,
      0);
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 0x20u, 0, &TokenHandle) )
    {
      v7 = 965;
LABEL_11:
      v4 = wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v7,
             (unsigned int)"onecore\\base\\devices\\association\\libs\\providermanagement\\providermanagement.cpp",
             v6);
      goto LABEL_17;
    }
LABEL_9:
    Luid = 0;
    if ( LookupPrivilegeValueW(0, L"SeTakeOwnershipPrivilege", &Luid) )
    {
      v12 = 0;
      if ( LookupPrivilegeValueW(0, L"SeRestorePrivilege", &v12) )
      {
        NewState.PrivilegeCount = 2;
        NewState.Privileges[0].Luid = Luid;
        NewState.Privileges[0].Attributes = 2 * (v1 ^ 1) + 2;
        v14 = v12;
        Attributes = NewState.Privileges[0].Attributes;
        if ( AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0, 0, 0) )
        {
          v4 = 0;
          goto LABEL_17;
        }
        v7 = 989;
      }
      else
      {
        v7 = 976;
      }
    }
    else
    {
      v7 = 974;
    }
    goto LABEL_11;
  }
  if ( (v4 & 0x80000000) == 0 )
    goto LABEL_9;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x3C9,
    (unsigned int)"onecore\\base\\devices\\association\\libs\\providermanagement\\providermanagement.cpp",
    (const char *)v4,
    PreviousState);
LABEL_17:
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  return v4;
}

```

## disassembly

```asm
0x18003a878  mov     [rsp-8+arg_0], rbx
0x18003a87d  mov     [rsp-8+arg_8], rdi
0x18003a882  push    rbp
0x18003a883  mov     rbp, rsp
0x18003a886  sub     rsp, 70h
0x18003a88a  mov     rax, cs:__security_cookie
0x18003a891  xor     rax, rsp
0x18003a894  mov     [rbp+var_8], rax
0x18003a898  movzx   edi, cl
0x18003a89b  mov     [rbp+TokenHandle], 0
0x18003a8a3  xor     edx, edx
0x18003a8a5  lea     rcx, [rbp+TokenHandle]
0x18003a8a9  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18003a8ae  call    cs:__imp_GetCurrentProcess
0x18003a8b4  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18003a8b8  mov     edx, 20h ; ' '; DesiredAccess
0x18003a8bd  mov     rcx, rax; ProcessHandle
0x18003a8c0  call    cs:__imp_OpenProcessToken
0x18003a8c6  test    eax, eax
0x18003a8c8  jnz     short loc_18003A938
0x18003a8ca  call    cs:__imp_GetLastError
0x18003a8d0  mov     ebx, eax
0x18003a8d2  test    eax, eax
0x18003a8d4  jle     short loc_18003A8DF
0x18003a8d6  movzx   ebx, ax
0x18003a8d9  or      ebx, 80070000h
0x18003a8df  cmp     ebx, 80070005h
0x18003a8e5  jnz     short loc_18003A917
0x18003a8e7  xor     edx, edx
0x18003a8e9  lea     rcx, [rbp+TokenHandle]
0x18003a8ed  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18003a8f2  call    cs:__imp_GetCurrentThread
0x18003a8f8  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18003a8fc  xor     r8d, r8d; OpenAsSelf
0x18003a8ff  lea     edx, [r8+20h]; DesiredAccess
0x18003a903  mov     rcx, rax; ThreadHandle
0x18003a906  call    cs:__imp_OpenThreadToken
0x18003a90c  test    eax, eax
0x18003a90e  jnz     short loc_18003A938
0x18003a910  mov     edx, 3C5h
0x18003a915  jmp     short loc_18003A95C
0x18003a917  test    ebx, ebx
0x18003a919  jns     short loc_18003A938
0x18003a91b  mov     rcx, [rbp+8]; this
0x18003a91f  mov     r9d, ebx; char *
0x18003a922  lea     r8, aOnecoreBaseDev_4; "onecore\\base\\devices\\association\\li"...
0x18003a929  mov     edx, 3C9h; void *
0x18003a92e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a933  jmp     loc_18003A9F5
0x18003a938  mov     qword ptr [rbp+Luid.LowPart], 0
0x18003a940  lea     r8, [rbp+Luid]; lpLuid
0x18003a944  lea     rdx, Name; "SeTakeOwnershipPrivilege"
0x18003a94b  xor     ecx, ecx; lpSystemName
0x18003a94d  call    cs:__imp_LookupPrivilegeValueW
0x18003a953  test    eax, eax
0x18003a955  jnz     short loc_18003A973
0x18003a957  mov     edx, 3CEh; void *
0x18003a95c  lea     r8, aOnecoreBaseDev_4; "onecore\\base\\devices\\association\\li"...
0x18003a963  mov     rcx, [rbp+8]; this
0x18003a967  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003a96c  mov     ebx, eax
0x18003a96e  jmp     loc_18003A9F5
0x18003a973  mov     qword ptr [rbp+var_30.LowPart], 0
0x18003a97b  lea     r8, [rbp+var_30]; lpLuid
0x18003a97f  lea     rdx, aSerestoreprivi; "SeRestorePrivilege"
0x18003a986  xor     ecx, ecx; lpSystemName
0x18003a988  call    cs:__imp_LookupPrivilegeValueW
0x18003a98e  test    eax, eax
0x18003a990  jnz     short loc_18003A999
0x18003a992  mov     edx, 3D0h
0x18003a997  jmp     short loc_18003A95C
0x18003a999  mov     [rbp+NewState.PrivilegeCount], 2
0x18003a9a0  mov     rax, qword ptr [rbp+Luid.LowPart]
0x18003a9a4  mov     qword ptr [rbp+NewState.Privileges.Luid.LowPart], rax
0x18003a9a8  xor     edi, 1
0x18003a9ab  lea     ecx, ds:2[rdi*2]
0x18003a9b2  mov     [rbp+NewState.Privileges.Attributes], ecx
0x18003a9b5  mov     rax, qword ptr [rbp+var_30.LowPart]
0x18003a9b9  mov     [rbp+var_18], rax
0x18003a9bd  mov     [rbp+var_10], ecx
0x18003a9c0  mov     [rsp+70h+ReturnLength], 0; ReturnLength
0x18003a9c9  mov     [rsp+70h+PreviousState], 0; PreviousState
0x18003a9d2  xor     r9d, r9d; BufferLength
0x18003a9d5  lea     r8, [rbp+NewState]; NewState
0x18003a9d9  xor     edx, edx; DisableAllPrivileges
0x18003a9db  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18003a9df  call    cs:__imp_AdjustTokenPrivileges
0x18003a9e5  test    eax, eax
0x18003a9e7  jnz     short loc_18003A9F3
0x18003a9e9  mov     edx, 3DDh
0x18003a9ee  jmp     loc_18003A95C
0x18003a9f3  xor     ebx, ebx
0x18003a9f5  lea     rcx, [rbp+TokenHandle]
0x18003a9f9  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18003a9fe  mov     eax, ebx
0x18003aa00  mov     rcx, [rbp+var_8]
0x18003aa04  xor     rcx, rsp; StackCookie
0x18003aa07  call    __security_check_cookie
0x18003aa0c  lea     r11, [rsp+70h+var_s0]
0x18003aa11  mov     rbx, [r11+10h]
0x18003aa15  mov     rdi, [r11+18h]
0x18003aa19  mov     rsp, r11
0x18003aa1c  pop     rbp
0x18003aa1d  retn
```
