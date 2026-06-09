# FwppGetTokenUserFromThread

- ea: `0x180039480`
- end: `0x180039665`
- name: `FwppGetTokenUserFromThread`
- size: `485`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180038dd8`

## callees

- `0x1800034e0`
- `0x18000438c`
- `0x180005fc8`
- `0x180007e38`
- `0x180012bd0`
- `0x180039480`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800394d0`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800394fd`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800394d0`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800394fd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800394b4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800394e4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800394b4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800394e4`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180039535`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180039535`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180039520`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180039520`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003950d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039545`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039568`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800395a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800395ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003950d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039545`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039568`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800395a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800395ff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039623`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039623`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180039594`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800395ef`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180039594`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800395ef`

## string_xrefs

- `0x180039551`: `OpenProcessToken`
- `0x180039574`: `OpenThreadToken`
- `0x1800395b5`: `FwppGetTokenUserFromThread`
- `0x18003963d`: `FwppGetTokenUserFromThread`
- `0x18003960b`: `GetTokenInformation`

## pseudocode

```c
__int64 __fastcall FwppGetTokenUserFromThread(LPVOID *a1)
{
  HANDLE CurrentThread; // rax
  HANDLE v3; // rax
  HANDLE CurrentProcess; // rax
  DWORD LastError; // eax
  __int64 v6; // rcx
  const char *v7; // rdx
  __int64 v8; // rbx
  LPVOID TokenInformation; // [rsp+30h] [rbp-28h] BYREF
  DWORD TokenInformationLength; // [rsp+38h] [rbp-20h] BYREF
  void *TokenHandle; // [rsp+40h] [rbp-18h] BYREF

  TokenInformationLength = 0;
  TokenInformation = 0;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle) )
  {
    v3 = GetCurrentThread();
    if ( !OpenThreadToken(v3, 8u, 1, &TokenHandle) )
    {
      if ( GetLastError() != 1008 )
      {
        LastError = GetLastError();
        v7 = "OpenThreadToken";
        goto LABEL_6;
      }
      CurrentProcess = GetCurrentProcess();
      if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
      {
        LastError = GetLastError();
        v7 = "OpenProcessToken";
LABEL_6:
        v8 = WfpReportSysErrorAsWinError(v6, v7, LastError);
        goto LABEL_15;
      }
    }
  }
  if ( !GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) )
  {
    LastError = GetLastError();
    if ( LastError != 122 )
    {
      v7 = "FwppGetTokenUserFromThread";
      goto LABEL_6;
    }
  }
  v8 = WfpMemAlloc(TokenInformationLength, 8u);
  if ( !v8 )
  {
    if ( !GetTokenInformation(TokenHandle, TokenUser, TokenInformation, TokenInformationLength, &TokenInformationLength) )
    {
      LastError = GetLastError();
      v7 = "GetTokenInformation";
      goto LABEL_6;
    }
    *a1 = TokenInformation;
  }
LABEL_15:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( v8 )
  {
    WfpMemFree(&TokenInformation);
    WfpReportError(v8, "FwppGetTokenUserFromThread");
  }
  return v8;
}

```

## disassembly

```asm
0x180039480  push    rbp
0x180039482  push    rbx
0x180039483  push    rsi
0x180039484  push    rdi
0x180039485  mov     rbp, rsp
0x180039488  sub     rsp, 58h
0x18003948c  mov     rax, cs:__security_cookie
0x180039493  xor     rax, rsp
0x180039496  mov     [rbp+var_10], rax
0x18003949a  mov     rsi, rcx
0x18003949d  mov     [rbp+TokenInformationLength], 0
0x1800394a4  mov     [rbp+TokenInformation], 0
0x1800394ac  mov     [rbp+TokenHandle], 0
0x1800394b4  call    cs:__imp_GetCurrentThread
0x1800394bb  nop     dword ptr [rax+rax+00h]
0x1800394c0  xor     r8d, r8d; OpenAsSelf
0x1800394c3  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800394c7  mov     rcx, rax; ThreadHandle
0x1800394ca  lea     ebx, [r8+8]
0x1800394ce  mov     edx, ebx; DesiredAccess
0x1800394d0  call    cs:__imp_OpenThreadToken
0x1800394d7  nop     dword ptr [rax+rax+00h]
0x1800394dc  test    eax, eax
0x1800394de  jnz     loc_18003957D
0x1800394e4  call    cs:__imp_GetCurrentThread
0x1800394eb  nop     dword ptr [rax+rax+00h]
0x1800394f0  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800394f4  mov     edx, ebx; DesiredAccess
0x1800394f6  mov     rcx, rax; ThreadHandle
0x1800394f9  lea     r8d, [rbx-7]; OpenAsSelf
0x1800394fd  call    cs:__imp_OpenThreadToken
0x180039504  nop     dword ptr [rax+rax+00h]
0x180039509  test    eax, eax
0x18003950b  jnz     short loc_18003957D
0x18003950d  call    cs:__imp_GetLastError
0x180039514  nop     dword ptr [rax+rax+00h]
0x180039519  cmp     eax, 3F0h
0x18003951e  jnz     short loc_180039568
0x180039520  call    cs:__imp_GetCurrentProcess
0x180039527  nop     dword ptr [rax+rax+00h]
0x18003952c  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180039530  mov     edx, ebx; DesiredAccess
0x180039532  mov     rcx, rax; ProcessHandle
0x180039535  call    cs:__imp_OpenProcessToken
0x18003953c  nop     dword ptr [rax+rax+00h]
0x180039541  test    eax, eax
0x180039543  jnz     short loc_18003957D
0x180039545  call    cs:__imp_GetLastError
0x18003954c  nop     dword ptr [rax+rax+00h]
0x180039551  lea     rdx, aOpenprocesstok; "OpenProcessToken"
0x180039558  mov     r8d, eax
0x18003955b  call    WfpReportSysErrorAsWinError
0x180039560  mov     rbx, rax
0x180039563  jmp     loc_18003961A
0x180039568  call    cs:__imp_GetLastError
0x18003956f  nop     dword ptr [rax+rax+00h]
0x180039574  lea     rdx, aOpenthreadtoke; "OpenThreadToken"
0x18003957b  jmp     short loc_180039558
0x18003957d  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180039581  lea     rax, [rbp+TokenInformationLength]
0x180039585  xor     r9d, r9d; TokenInformationLength
0x180039588  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x18003958d  xor     r8d, r8d; TokenInformation
0x180039590  lea     edx, [r9+1]; TokenInformationClass
0x180039594  call    cs:__imp_GetTokenInformation
0x18003959b  nop     dword ptr [rax+rax+00h]
0x1800395a0  test    eax, eax
0x1800395a2  jnz     short loc_1800395BE
0x1800395a4  call    cs:__imp_GetLastError
0x1800395ab  nop     dword ptr [rax+rax+00h]
0x1800395b0  cmp     eax, 7Ah ; 'z'
0x1800395b3  jz      short loc_1800395BE
0x1800395b5  lea     rdx, aFwppgettokenus; "FwppGetTokenUserFromThread"
0x1800395bc  jmp     short loc_180039558
0x1800395be  mov     ecx, [rbp+TokenInformationLength]; dwBytes
0x1800395c1  lea     r8, [rbp+TokenInformation]
0x1800395c5  mov     edx, ebx; dwFlags
0x1800395c7  call    WfpMemAlloc
0x1800395cc  mov     rbx, rax
0x1800395cf  test    rax, rax
0x1800395d2  jnz     short loc_18003961A
0x1800395d4  mov     rdi, [rbp+TokenInformation]
0x1800395d8  lea     rax, [rbp+TokenInformationLength]
0x1800395dc  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x1800395e0  lea     edx, [rbx+1]; TokenInformationClass
0x1800395e3  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800395e7  mov     r8, rdi; TokenInformation
0x1800395ea  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x1800395ef  call    cs:__imp_GetTokenInformation
0x1800395f6  nop     dword ptr [rax+rax+00h]
0x1800395fb  test    eax, eax
0x1800395fd  jnz     short loc_180039617
0x1800395ff  call    cs:__imp_GetLastError
0x180039606  nop     dword ptr [rax+rax+00h]
0x18003960b  lea     rdx, aGettokeninform; "GetTokenInformation"
0x180039612  jmp     loc_180039558
0x180039617  mov     [rsi], rdi
0x18003961a  mov     rcx, [rbp+TokenHandle]; hObject
0x18003961e  test    rcx, rcx
0x180039621  jz      short loc_18003962F
0x180039623  call    cs:__imp_CloseHandle
0x18003962a  nop     dword ptr [rax+rax+00h]
0x18003962f  test    rbx, rbx
0x180039632  jz      short loc_18003964C
0x180039634  lea     rcx, [rbp+TokenInformation]
0x180039638  call    WfpMemFree
0x18003963d  lea     rdx, aFwppgettokenus; "FwppGetTokenUserFromThread"
0x180039644  mov     rcx, rbx
0x180039647  call    WfpReportError
0x18003964c  mov     rax, rbx
0x18003964f  mov     rcx, [rbp+var_10]
0x180039653  xor     rcx, rsp; StackCookie
0x180039656  call    __security_check_cookie
0x18003965b  add     rsp, 58h
0x18003965f  pop     rdi
0x180039660  pop     rsi
0x180039661  pop     rbx
0x180039662  pop     rbp
0x180039663  retn
```
