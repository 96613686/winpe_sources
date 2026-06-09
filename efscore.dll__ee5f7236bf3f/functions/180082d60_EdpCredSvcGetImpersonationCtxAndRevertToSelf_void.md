# EdpCredSvcGetImpersonationCtxAndRevertToSelf(void * *)

- ea: `0x180082d60`
- end: `0x180082ee5`
- name: `?EdpCredSvcGetImpersonationCtxAndRevertToSelf@@YAJPEAPEAX@Z`
- size: `389`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `7`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180081bf8`
- `0x180082620`
- `0x180084508`
- `0x1800878ac`
- `0x18009ad00`
- `0x18009e880`
- `0x1800a0190`

## callees

- `0x180063698`
- `0x180063730`
- `0x1800637e8`
- `0x180082d60`
- `0x1800dca3c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082dfe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082dfe`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180082df4`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180082df4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180082ddd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180082ddd`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180082e40`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180082e40`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180082e93`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180082e93`

## pseudocode

```c
__int64 __fastcall EdpCredSvcGetImpersonationCtxAndRevertToSelf(void **a1)
{
  signed int v2; // ebx
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  __int64 v5; // rcx
  void *v6; // rcx
  void *TokenHandle; // [rsp+50h] [rbp+8h] BYREF

  TokenHandle = 0;
  fnEfsLogTrace1Strings((_DWORD)a1, (unsigned int)EFS_TRACE_ENTER_EVENT, (unsigned int)&sourceString, 38, 109);
  if ( a1 )
  {
    *a1 = 0;
    if ( !NtCurrentTeb()->IsImpersonating )
    {
      v2 = 1;
      fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_STATUS, 1, 38, 116);
      goto LABEL_11;
    }
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 4u, 1, &TokenHandle) )
    {
      v2 = 0;
      if ( !SetThreadToken(0, 0) )
        MicrosoftTelemetryAssertTriggeredNoArgs(v5);
      goto LABEL_11;
    }
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      v2 = (unsigned __int16)LastError | 0x80070000;
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v2, 38, 125);
    if ( v2 >= 0 )
    {
LABEL_11:
      v6 = 0;
      *a1 = TokenHandle;
      TokenHandle = 0;
      goto LABEL_14;
    }
  }
  else
  {
    v2 = -2147467261;
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -2147467261, 38, 112);
  }
  v6 = TokenHandle;
LABEL_14:
  if ( v6 )
  {
    CloseHandle(v6);
    TokenHandle = 0;
  }
  fnEfsLogTrace1String1Dword(
    g_hPublisher,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT_ERROR,
    (unsigned int)&sourceString,
    v2,
    38,
    149);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180082d60  mov     rax, rsp
0x180082d63  mov     [rax+10h], rbx
0x180082d67  mov     [rax+18h], rsi
0x180082d6b  push    rdi
0x180082d6c  sub     rsp, 40h
0x180082d70  mov     esi, 26h ; '&'
0x180082d75  mov     qword ptr [rax+8], 0
0x180082d7d  mov     r9d, esi
0x180082d80  mov     dword ptr [rax-28h], 26Dh
0x180082d87  lea     r8, sourceString
0x180082d8e  mov     rdi, rcx
0x180082d91  lea     rdx, EFS_TRACE_ENTER_EVENT
0x180082d98  call    fnEfsLogTrace1Strings
0x180082d9d  test    rdi, rdi
0x180082da0  jz      loc_180082E60
0x180082da6  xor     eax, eax
0x180082da8  mov     [rdi], rax
0x180082dab  mov     eax, gs:179Ch
0x180082db3  test    eax, eax
0x180082db5  jnz     short loc_180082DDD
0x180082db7  mov     rcx, cs:g_hPublisher
0x180082dbe  lea     ebx, [rsi-25h]
0x180082dc1  mov     r8d, ebx
0x180082dc4  mov     [rsp+48h+var_28], 274h
0x180082dcc  mov     r9d, esi
0x180082dcf  lea     rdx, EFS_TRACE_STATUS
0x180082dd6  call    fnEfsLogTrace1
0x180082ddb  jmp     short loc_180082E4F
0x180082ddd  call    cs:__imp_GetCurrentThread
0x180082de3  mov     edx, 4; DesiredAccess
0x180082de8  lea     r9, [rsp+48h+TokenHandle]; TokenHandle
0x180082ded  mov     rcx, rax; ThreadHandle
0x180082df0  lea     r8d, [rdx-3]; OpenAsSelf
0x180082df4  call    cs:__imp_OpenThreadToken
0x180082dfa  test    eax, eax
0x180082dfc  jnz     short loc_180082E3A
0x180082dfe  call    cs:__imp_GetLastError
0x180082e04  mov     ebx, eax
0x180082e06  test    eax, eax
0x180082e08  jle     short loc_180082E13
0x180082e0a  movzx   ebx, ax
0x180082e0d  or      ebx, 80070000h
0x180082e13  mov     rcx, cs:g_hPublisher
0x180082e1a  lea     rdx, EFS_TRACE_ERROR
0x180082e21  mov     r9d, esi
0x180082e24  mov     [rsp+48h+var_28], 27Dh
0x180082e2c  mov     r8d, ebx
0x180082e2f  call    fnEfsLogTrace1
0x180082e34  test    ebx, ebx
0x180082e36  jns     short loc_180082E4F
0x180082e38  jmp     short loc_180082E89
0x180082e3a  xor     edx, edx; Token
0x180082e3c  xor     ecx, ecx; Thread
0x180082e3e  xor     ebx, ebx
0x180082e40  call    cs:__imp_SetThreadToken
0x180082e46  test    eax, eax
0x180082e48  jnz     short loc_180082E4F
0x180082e4a  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "Success != FALSE")
0x180082e4f  mov     rax, [rsp+48h+TokenHandle]
0x180082e54  xor     ecx, ecx
0x180082e56  mov     [rdi], rax
0x180082e59  mov     [rsp+48h+TokenHandle], rcx
0x180082e5e  jmp     short loc_180082E8E
0x180082e60  mov     rcx, cs:g_hPublisher
0x180082e67  lea     rdx, EFS_TRACE_ERROR
0x180082e6e  mov     r9d, esi
0x180082e71  mov     [rsp+48h+var_28], 270h
0x180082e79  mov     r8d, 80004003h
0x180082e7f  mov     ebx, 80004003h
0x180082e84  call    fnEfsLogTrace1
0x180082e89  mov     rcx, [rsp+48h+TokenHandle]; hObject
0x180082e8e  test    rcx, rcx
0x180082e91  jz      short loc_180082EA2
0x180082e93  call    cs:__imp_CloseHandle
0x180082e99  mov     [rsp+48h+TokenHandle], 0
0x180082ea2  mov     rcx, cs:g_hPublisher
0x180082ea9  lea     r9, sourceString
0x180082eb0  mov     [rsp+48h+var_18], 295h
0x180082eb8  lea     r8, EFS_TRACE_LEAVE_HR_EVENT_ERROR
0x180082ebf  mov     [rsp+48h+var_20], esi
0x180082ec3  lea     rdx, EFS_TRACE_LEAVE_HR_EVENT
0x180082eca  mov     [rsp+48h+var_28], ebx
0x180082ece  call    fnEfsLogTrace1String1Dword
0x180082ed3  mov     rsi, [rsp+48h+arg_10]
0x180082ed8  mov     eax, ebx
0x180082eda  mov     rbx, [rsp+48h+arg_8]
0x180082edf  add     rsp, 40h
0x180082ee3  pop     rdi
0x180082ee4  retn
```
