# IsSpoolerImpersonating

- ea: `0x1800e0d78`
- end: `0x1800e0f36`
- name: `IsSpoolerImpersonating`
- size: `446`
- prototype: `__int64()`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180066590`
- `0x180074780`
- `0x1800deab0`

## callees

- `0x1800df3e0`
- `0x1800df488`
- `0x1800e0d78`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e0dcf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e0df5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e0e12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e0e42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e0e4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e0ef9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e0dcf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e0df5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e0e12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e0e42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e0e4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e0ef9`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800e0dc5`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800e0dc5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800e0daf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800e0daf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800e0ddc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800e0ddc`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800e0deb`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800e0deb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e0e69`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e0ed4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e0f15`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e0e69`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e0ed4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e0f15`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800e0e38`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800e0e9e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800e0e38`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800e0e9e`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x1800e0eb0`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x1800e0eb0`
- `SPOOLSS!DllFreeSplMem` at `0x1800e0edd`
- `SPOOLSS!DllFreeSplMem` at `0x1800e0f1e`
- `SPOOLSS!DllFreeSplMem` at `0x1800e0edd`
- `SPOOLSS!DllFreeSplMem` at `0x1800e0f1e`
- `SPOOLSS!DllAllocSplMem` at `0x1800e0e77`
- `SPOOLSS!DllAllocSplMem` at `0x1800e0e77`

## string_xrefs

- `0x1800e0d8a`: `IsSpoolerImpersonating`
- `0x1800e0e18`: `OpenThreadToken failed, rc: %d`
- `0x1800e0dfb`: `OpenProcessToken failed, rc: %d`
- `0x1800e0eba`: `Spooler is running as Local System and not as an impersonated user`
- `0x1800e0e53`: `GetTokenInformation (1) failed, rc: %d`
- `0x1800e0ee3`: `Spooler is running impersonated and not as a Local System`
- `0x1800e0eff`: `GetTokenInformation (2) failed, rc: %d`

## pseudocode

```c
__int64 IsSpoolerImpersonating()
{
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  DWORD v2; // eax
  DWORD LastError; // eax
  DWORD v4; // eax
  void *v5; // rcx
  PSID *v6; // rax
  PSID *v7; // rbx
  DWORD v9; // eax
  DWORD TokenInformationLength; // [rsp+40h] [rbp+10h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp+18h] BYREF

  TokenInformationLength = 0;
  TokenHandle = 0;
  LocalMonTelemetry::WriteDbgTraceInfo("IsSpoolerImpersonating", L"Entering");
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle) )
  {
    if ( GetLastError() != 1008 )
    {
      LastError = GetLastError();
      LocalMonTelemetry::WriteDbgTraceError("IsSpoolerImpersonating", L"OpenThreadToken failed, rc: %d", LastError);
      return 0;
    }
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
    {
      v2 = GetLastError();
      LocalMonTelemetry::WriteDbgTraceError("IsSpoolerImpersonating", L"OpenProcessToken failed, rc: %d", v2);
      return 0;
    }
  }
  if ( !GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) && GetLastError() != 122 )
  {
    v4 = GetLastError();
    LocalMonTelemetry::WriteDbgTraceError("IsSpoolerImpersonating", L"GetTokenInformation (1) failed, rc: %d", v4);
    v5 = TokenHandle;
LABEL_10:
    CloseHandle(v5);
    return 0;
  }
  v6 = (PSID *)DllAllocSplMem(TokenInformationLength);
  v5 = TokenHandle;
  v7 = v6;
  if ( !v6 )
    goto LABEL_10;
  if ( !GetTokenInformation(TokenHandle, TokenUser, v6, TokenInformationLength, &TokenInformationLength) )
  {
    v9 = GetLastError();
    LocalMonTelemetry::WriteDbgTraceError("IsSpoolerImpersonating", L"GetTokenInformation (2) failed, rc: %d", v9);
    goto LABEL_19;
  }
  if ( IsWellKnownSid(*v7, WinLocalSystemSid) )
  {
    LocalMonTelemetry::WriteDbgTraceError(
      "IsSpoolerImpersonating",
      L"Spooler is running as Local System and not as an impersonated user");
LABEL_19:
    CloseHandle(TokenHandle);
    DllFreeSplMem(v7);
    return 0;
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  DllFreeSplMem(v7);
  LocalMonTelemetry::WriteDbgTraceInfo(
    "IsSpoolerImpersonating",
    L"Spooler is running impersonated and not as a Local System");
  return 1;
}

```

## disassembly

```asm
0x1800e0d78  mov     [rsp-8+arg_10], rbx
0x1800e0d7d  mov     [rsp-8+arg_18], rdi
0x1800e0d82  push    rbp
0x1800e0d83  mov     rbp, rsp
0x1800e0d86  sub     rsp, 30h
0x1800e0d8a  lea     rdi, aIsspoolerimper; "IsSpoolerImpersonating"
0x1800e0d91  mov     [rbp+TokenInformationLength], 0
0x1800e0d98  mov     rcx, rdi; char *
0x1800e0d9b  mov     [rbp+TokenHandle], 0
0x1800e0da3  lea     rdx, aEntering; "Entering"
0x1800e0daa  call    ?WriteDbgTraceInfo@LocalMonTelemetry@@SAXPEADPEAGZZ; LocalMonTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800e0daf  call    cs:__imp_GetCurrentThread
0x1800e0db5  xor     r8d, r8d; OpenAsSelf
0x1800e0db8  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800e0dbc  mov     rcx, rax; ThreadHandle
0x1800e0dbf  lea     ebx, [r8+8]
0x1800e0dc3  mov     edx, ebx; DesiredAccess
0x1800e0dc5  call    cs:__imp_OpenThreadToken
0x1800e0dcb  test    eax, eax
0x1800e0dcd  jnz     short loc_1800E0E21
0x1800e0dcf  call    cs:__imp_GetLastError
0x1800e0dd5  cmp     eax, 3F0h
0x1800e0dda  jnz     short loc_1800E0E12
0x1800e0ddc  call    cs:__imp_GetCurrentProcess
0x1800e0de2  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1800e0de6  mov     edx, ebx; DesiredAccess
0x1800e0de8  mov     rcx, rax; ProcessHandle
0x1800e0deb  call    cs:__imp_OpenProcessToken
0x1800e0df1  test    eax, eax
0x1800e0df3  jnz     short loc_1800E0E21
0x1800e0df5  call    cs:__imp_GetLastError
0x1800e0dfb  lea     rdx, aOpenprocesstok; "OpenProcessToken failed, rc: %d"
0x1800e0e02  mov     r8d, eax
0x1800e0e05  mov     rcx, rdi; char *
0x1800e0e08  call    ?WriteDbgTraceError@LocalMonTelemetry@@SAXPEADPEAGZZ; LocalMonTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800e0e0d  jmp     loc_1800E0F24
0x1800e0e12  call    cs:__imp_GetLastError
0x1800e0e18  lea     rdx, aOpenthreadtoke; "OpenThreadToken failed, rc: %d"
0x1800e0e1f  jmp     short loc_1800E0E02
0x1800e0e21  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800e0e25  lea     rax, [rbp+TokenInformationLength]
0x1800e0e29  xor     r9d, r9d; TokenInformationLength
0x1800e0e2c  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x1800e0e31  xor     r8d, r8d; TokenInformation
0x1800e0e34  lea     edx, [r9+1]; TokenInformationClass
0x1800e0e38  call    cs:__imp_GetTokenInformation
0x1800e0e3e  test    eax, eax
0x1800e0e40  jnz     short loc_1800E0E74
0x1800e0e42  call    cs:__imp_GetLastError
0x1800e0e48  cmp     eax, 7Ah ; 'z'
0x1800e0e4b  jz      short loc_1800E0E74
0x1800e0e4d  call    cs:__imp_GetLastError
0x1800e0e53  lea     rdx, aGettokeninform; "GetTokenInformation (1) failed, rc: %d"
0x1800e0e5a  mov     rcx, rdi; char *
0x1800e0e5d  mov     r8d, eax
0x1800e0e60  call    ?WriteDbgTraceError@LocalMonTelemetry@@SAXPEADPEAGZZ; LocalMonTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800e0e65  mov     rcx, [rbp+TokenHandle]; hObject
0x1800e0e69  call    cs:__imp_CloseHandle
0x1800e0e6f  jmp     loc_1800E0F24
0x1800e0e74  mov     ecx, [rbp+TokenInformationLength]
0x1800e0e77  call    cs:__imp_DllAllocSplMem
0x1800e0e7d  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800e0e81  mov     rbx, rax
0x1800e0e84  test    rax, rax
0x1800e0e87  jz      short loc_1800E0E69
0x1800e0e89  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x1800e0e8d  lea     rax, [rbp+TokenInformationLength]
0x1800e0e91  mov     r8, rbx; TokenInformation
0x1800e0e94  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x1800e0e99  mov     edx, 1; TokenInformationClass
0x1800e0e9e  call    cs:__imp_GetTokenInformation
0x1800e0ea4  test    eax, eax
0x1800e0ea6  jz      short loc_1800E0EF9
0x1800e0ea8  mov     rcx, [rbx]; pSid
0x1800e0eab  mov     edx, 16h; WellKnownSidType
0x1800e0eb0  call    cs:__imp_IsWellKnownSid
0x1800e0eb6  test    eax, eax
0x1800e0eb8  jz      short loc_1800E0ECB
0x1800e0eba  lea     rdx, aSpoolerIsRunni; "Spooler is running as Local System and "...
0x1800e0ec1  mov     rcx, rdi; char *
0x1800e0ec4  call    ?WriteDbgTraceError@LocalMonTelemetry@@SAXPEADPEAGZZ; LocalMonTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800e0ec9  jmp     short loc_1800E0F11
0x1800e0ecb  mov     rcx, [rbp+TokenHandle]; hObject
0x1800e0ecf  test    rcx, rcx
0x1800e0ed2  jz      short loc_1800E0EDA
0x1800e0ed4  call    cs:__imp_CloseHandle
0x1800e0eda  mov     rcx, rbx
0x1800e0edd  call    cs:__imp_DllFreeSplMem
0x1800e0ee3  lea     rdx, aSpoolerIsRunni_0; "Spooler is running impersonated and not"...
0x1800e0eea  mov     rcx, rdi; char *
0x1800e0eed  call    ?WriteDbgTraceInfo@LocalMonTelemetry@@SAXPEADPEAGZZ; LocalMonTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800e0ef2  mov     eax, 1
0x1800e0ef7  jmp     short loc_1800E0F26
0x1800e0ef9  call    cs:__imp_GetLastError
0x1800e0eff  lea     rdx, aGettokeninform_1; "GetTokenInformation (2) failed, rc: %d"
0x1800e0f06  mov     rcx, rdi; char *
0x1800e0f09  mov     r8d, eax
0x1800e0f0c  call    ?WriteDbgTraceError@LocalMonTelemetry@@SAXPEADPEAGZZ; LocalMonTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800e0f11  mov     rcx, [rbp+TokenHandle]; hObject
0x1800e0f15  call    cs:__imp_CloseHandle
0x1800e0f1b  mov     rcx, rbx
0x1800e0f1e  call    cs:__imp_DllFreeSplMem
0x1800e0f24  xor     eax, eax
0x1800e0f26  mov     rbx, [rsp+30h+arg_10]
0x1800e0f2b  mov     rdi, [rsp+30h+arg_18]
0x1800e0f30  add     rsp, 30h
0x1800e0f34  pop     rbp
0x1800e0f35  retn
```
