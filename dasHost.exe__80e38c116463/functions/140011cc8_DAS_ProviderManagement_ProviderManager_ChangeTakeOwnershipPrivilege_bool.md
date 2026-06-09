# DAS::ProviderManagement::ProviderManager::ChangeTakeOwnershipPrivilege(bool)

- ea: `0x140011cc8`
- end: `0x140011e9b`
- name: `?ChangeTakeOwnershipPrivilege@ProviderManager@ProviderManagement@DAS@@CAJ_N@Z`
- size: `467`
- prototype: `__int64 __fastcall(unsigned __int8)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140011988`
- `0x1400138ac`

## callees

- `0x140001570`
- `0x140006cc4`
- `0x140006ce4`
- `0x140011cc8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011d0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011d38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011d0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011d38`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140011d4b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140011d4b`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x140011cff`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x140011cff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140011d59`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140011d59`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140011ced`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140011ced`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140011d6d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140011d6d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140011d43`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140011d9c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140011e7e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140011d43`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140011d9c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140011e7e`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x140011e5c`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x140011e5c`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x140011ddc`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x140011e02`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x140011ddc`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x140011e02`

## string_xrefs

- `0x140011dd3`: `SeTakeOwnershipPrivilege`
- `0x140011df9`: `SeRestorePrivilege`

## pseudocode

```c
__int64 __fastcall DAS::ProviderManagement::ProviderManager::ChangeTakeOwnershipPrivilege(unsigned __int8 a1)
{
  int v1; // esi
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  unsigned int v4; // ebx
  void *v5; // rdi
  DWORD v6; // ebx
  HANDLE CurrentThread; // rax
  const char *v8; // r9
  __int64 v9; // rdx
  int PreviousState; // [rsp+20h] [rbp-58h]
  void *TokenHandle; // [rsp+30h] [rbp-48h] BYREF
  _LUID Luid; // [rsp+38h] [rbp-40h] BYREF
  struct _LUID v14; // [rsp+40h] [rbp-38h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+48h] [rbp-30h] BYREF
  struct _LUID v16; // [rsp+58h] [rbp-20h]
  DWORD Attributes; // [rsp+60h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+20h]

  v1 = a1;
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 0x20u, &TokenHandle) )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( v4 == -2147024891 )
    {
      v5 = TokenHandle;
      if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      {
        v6 = GetLastError();
        CloseHandle(v5);
        SetLastError(v6);
      }
      TokenHandle = 0;
      CurrentThread = GetCurrentThread();
      if ( !OpenThreadToken(CurrentThread, 0x20u, 0, &TokenHandle) )
      {
        v9 = 965;
LABEL_9:
        v4 = wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)v9,
               (unsigned int)"onecore\\base\\devices\\association\\libs\\providermanagement\\providermanagement.cpp",
               v8);
LABEL_10:
        if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          CloseHandle(TokenHandle);
        return v4;
      }
    }
    else if ( (v4 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3C9,
        (unsigned int)"onecore\\base\\devices\\association\\libs\\providermanagement\\providermanagement.cpp",
        (const char *)v4,
        PreviousState);
      goto LABEL_10;
    }
  }
  Luid = 0;
  if ( !LookupPrivilegeValueW(0, L"SeTakeOwnershipPrivilege", &Luid) )
  {
    v9 = 974;
    goto LABEL_9;
  }
  v14 = 0;
  if ( !LookupPrivilegeValueW(0, L"SeRestorePrivilege", &v14) )
  {
    v9 = 976;
    goto LABEL_9;
  }
  NewState.Privileges[0].Luid = Luid;
  NewState.PrivilegeCount = 2;
  v16 = v14;
  NewState.Privileges[0].Attributes = 2 * (v1 ^ 1) + 2;
  Attributes = NewState.Privileges[0].Attributes;
  if ( !AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0, 0, 0) )
  {
    v9 = 989;
    goto LABEL_9;
  }
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(TokenHandle);
  return 0;
}

```

## disassembly

```asm
0x140011cc8  push    rbp
0x140011cca  push    rbx
0x140011ccb  push    rsi
0x140011ccc  push    rdi
0x140011ccd  mov     rbp, rsp
0x140011cd0  sub     rsp, 78h
0x140011cd4  mov     rax, cs:__security_cookie
0x140011cdb  xor     rax, rsp
0x140011cde  mov     [rbp+var_10], rax
0x140011ce2  movzx   esi, cl
0x140011ce5  mov     [rbp+TokenHandle], 0
0x140011ced  call    cs:__imp_GetCurrentProcess
0x140011cf3  lea     r8, [rbp+TokenHandle]; TokenHandle
0x140011cf7  mov     edx, 20h ; ' '; DesiredAccess
0x140011cfc  mov     rcx, rax; ProcessHandle
0x140011cff  call    cs:__imp_OpenProcessToken
0x140011d05  test    eax, eax
0x140011d07  jnz     loc_140011DC7
0x140011d0d  call    cs:__imp_GetLastError
0x140011d13  mov     ebx, eax
0x140011d15  test    eax, eax
0x140011d17  jle     short loc_140011D22
0x140011d19  movzx   ebx, ax
0x140011d1c  or      ebx, 80070000h
0x140011d22  cmp     ebx, 80070005h
0x140011d28  jnz     short loc_140011DA9
0x140011d2a  mov     rdi, [rbp+TokenHandle]
0x140011d2e  lea     rax, [rdi-1]
0x140011d32  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140011d36  ja      short loc_140011D51
0x140011d38  call    cs:__imp_GetLastError
0x140011d3e  mov     rcx, rdi; hObject
0x140011d41  mov     ebx, eax
0x140011d43  call    cs:__imp_CloseHandle
0x140011d49  mov     ecx, ebx; dwErrCode
0x140011d4b  call    cs:__imp_SetLastError
0x140011d51  mov     [rbp+TokenHandle], 0
0x140011d59  call    cs:__imp_GetCurrentThread
0x140011d5f  xor     r8d, r8d; OpenAsSelf
0x140011d62  lea     r9, [rbp+TokenHandle]; TokenHandle
0x140011d66  mov     rcx, rax; ThreadHandle
0x140011d69  lea     edx, [r8+20h]; DesiredAccess
0x140011d6d  call    cs:__imp_OpenThreadToken
0x140011d73  test    eax, eax
0x140011d75  jnz     short loc_140011DC7
0x140011d77  mov     edx, 3C5h; void *
0x140011d7c  mov     rcx, [rbp+20h]; this
0x140011d80  lea     r8, aOnecoreBaseDev_0; "onecore\\base\\devices\\association\\li"...
0x140011d87  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140011d8c  mov     ebx, eax
0x140011d8e  mov     rcx, [rbp+TokenHandle]; hObject
0x140011d92  lea     rdx, [rcx-1]
0x140011d96  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x140011d9a  ja      short loc_140011DA2
0x140011d9c  call    cs:__imp_CloseHandle
0x140011da2  mov     eax, ebx
0x140011da4  jmp     loc_140011E86
0x140011da9  test    ebx, ebx
0x140011dab  jns     short loc_140011DC7
0x140011dad  mov     rcx, [rbp+20h]; this
0x140011db1  lea     r8, aOnecoreBaseDev_0; "onecore\\base\\devices\\association\\li"...
0x140011db8  mov     r9d, ebx; char *
0x140011dbb  mov     edx, 3C9h; void *
0x140011dc0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140011dc5  jmp     short loc_140011D8E
0x140011dc7  lea     r8, [rbp+Luid]; lpLuid
0x140011dcb  mov     qword ptr [rbp+Luid.LowPart], 0
0x140011dd3  lea     rdx, Name; "SeTakeOwnershipPrivilege"
0x140011dda  xor     ecx, ecx; lpSystemName
0x140011ddc  call    cs:__imp_LookupPrivilegeValueW
0x140011de2  test    eax, eax
0x140011de4  jnz     short loc_140011DED
0x140011de6  mov     edx, 3CEh
0x140011deb  jmp     short loc_140011D7C
0x140011ded  lea     r8, [rbp+var_38]; lpLuid
0x140011df1  mov     qword ptr [rbp+var_38.LowPart], 0
0x140011df9  lea     rdx, aSerestoreprivi; "SeRestorePrivilege"
0x140011e00  xor     ecx, ecx; lpSystemName
0x140011e02  call    cs:__imp_LookupPrivilegeValueW
0x140011e08  test    eax, eax
0x140011e0a  jnz     short loc_140011E16
0x140011e0c  mov     edx, 3D0h
0x140011e11  jmp     loc_140011D7C
0x140011e16  mov     rax, qword ptr [rbp+Luid.LowPart]
0x140011e1a  lea     r8, [rbp+NewState]; NewState
0x140011e1e  mov     qword ptr [rbp+NewState.Privileges.Luid.LowPart], rax
0x140011e22  xor     esi, 1
0x140011e25  mov     rax, qword ptr [rbp+var_38.LowPart]
0x140011e29  xor     r9d, r9d; BufferLength
0x140011e2c  mov     [rsp+78h+ReturnLength], 0; ReturnLength
0x140011e35  xor     edx, edx; DisableAllPrivileges
0x140011e37  mov     [rbp+NewState.PrivilegeCount], 2
0x140011e3e  lea     ecx, ds:2[rsi*2]
0x140011e45  mov     [rbp+var_20], rax
0x140011e49  mov     [rbp+NewState.Privileges.Attributes], ecx
0x140011e4c  mov     [rbp+var_18], ecx
0x140011e4f  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x140011e53  mov     [rsp+78h+PreviousState], 0; PreviousState
0x140011e5c  call    cs:__imp_AdjustTokenPrivileges
0x140011e62  test    eax, eax
0x140011e64  jnz     short loc_140011E70
0x140011e66  mov     edx, 3DDh
0x140011e6b  jmp     loc_140011D7C
0x140011e70  mov     rcx, [rbp+TokenHandle]; hObject
0x140011e74  lea     rax, [rcx-1]
0x140011e78  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140011e7c  ja      short loc_140011E84
0x140011e7e  call    cs:__imp_CloseHandle
0x140011e84  xor     eax, eax
0x140011e86  mov     rcx, [rbp+var_10]
0x140011e8a  xor     rcx, rsp; StackCookie
0x140011e8d  call    __security_check_cookie
0x140011e92  add     rsp, 78h
0x140011e96  pop     rdi
0x140011e97  pop     rsi
0x140011e98  pop     rbx
0x140011e99  pop     rbp
0x140011e9a  retn
```
