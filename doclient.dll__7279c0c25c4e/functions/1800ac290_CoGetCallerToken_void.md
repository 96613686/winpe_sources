# CoGetCallerToken(void * *)

- ea: `0x1800ac290`
- end: `0x1800ac4a3`
- name: `?CoGetCallerToken@@YAJPEAPEAX@Z`
- size: `531`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180016300`
- `0x180094310`
- `0x180094518`

## callees

- `0x180008618`
- `0x18000933c`
- `0x18000cea4`
- `0x1800ac290`
- `0x1800f82f0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ac313`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ac385`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ac3d1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ac43f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ac466`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ac313`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ac385`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ac3d1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ac43f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ac466`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800ac2cb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800ac2cb`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800ac2e2`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800ac2e2`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800ac319`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800ac38b`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800ac3d7`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800ac445`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800ac46c`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800ac319`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800ac38b`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800ac3d7`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800ac445`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800ac46c`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1800ac2af`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1800ac2af`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800ac354`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800ac354`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800ac40e`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800ac40e`

## string_xrefs

- `0x1800ac490`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CoGetCallerToken(void **a1)
{
  HRESULT v2; // eax
  HANDLE CurrentThread; // rax
  const char *v4; // r9
  unsigned int v5; // ebx
  const char *v6; // r9
  __int64 result; // rax
  const char *v8; // r9
  unsigned int v9; // ebx
  const char *v10; // r9
  unsigned int LastError; // ebx
  int ReturnLength; // [rsp+20h] [rbp-48h]
  int ReturnLengtha; // [rsp+20h] [rbp-48h]
  void *phNewToken; // [rsp+30h] [rbp-38h] BYREF
  DWORD v15; // [rsp+38h] [rbp-30h] BYREF
  void *TokenHandle; // [rsp+40h] [rbp-28h] BYREF
  int TokenInformation; // [rsp+48h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  *a1 = 0;
  v2 = CoImpersonateClient();
  if ( v2 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1262,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
      (const char *)(unsigned int)v2,
      ReturnLength);
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0xEu, 1, &TokenHandle) )
  {
    v15 = 0;
    TokenInformation = 0;
    if ( GetTokenInformation(TokenHandle, TokenImpersonationLevel, &TokenInformation, 4u, &v15) )
    {
      if ( (unsigned int)(TokenInformation - 2) <= 1 )
      {
        phNewToken = 0;
        if ( DuplicateTokenEx(TokenHandle, 0xEu, 0, SecurityImpersonation, TokenImpersonation, &phNewToken) )
        {
          *a1 = phNewToken;
          if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
            CloseHandle(TokenHandle);
          CoRevertToSelf();
          result = 0;
        }
        else
        {
          LastError = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0x2B2,
                        (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\GeneralUtils.cpp",
                        v10);
          if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
            CloseHandle(TokenHandle);
          CoRevertToSelf();
          result = LastError;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2A9,
          (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\GeneralUtils.cpp",
          (const char *)0x80010123LL,
          ReturnLengtha);
        if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          CloseHandle(TokenHandle);
        CoRevertToSelf();
        result = 2147549475LL;
      }
    }
    else
    {
      v9 = wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x2A6,
             (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\GeneralUtils.cpp",
             v8);
      if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(TokenHandle);
      CoRevertToSelf();
      result = v9;
    }
  }
  else
  {
    v5 = wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)0x2A2,
           (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\GeneralUtils.cpp",
           v4);
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(TokenHandle);
    CoRevertToSelf();
    result = v5;
  }
  while ( 2 )
  {
    try
    {
    }
    catch ( ... )
    {
      v15 = wil::details::in1diag3::Return_CaughtException(
              retaddr,
              (void *)0x2B6,
              (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\GeneralUtils.cpp",
              v6);
      result = v15;
      continue;
    }
    break;
  }
  return result;
}

```

## disassembly

```asm
0x1800ac290  push    rbx
0x1800ac292  sub     rsp, 60h
0x1800ac296  mov     rax, cs:__security_cookie
0x1800ac29d  xor     rax, rsp
0x1800ac2a0  mov     [rsp+68h+var_18], rax
0x1800ac2a5  mov     rbx, rcx
0x1800ac2a8  mov     qword ptr [rcx], 0
0x1800ac2af  call    cs:__imp_CoImpersonateClient
0x1800ac2b5  mov     rcx, [rsp+68h]; this
0x1800ac2ba  test    eax, eax
0x1800ac2bc  js      loc_1800AC48D
0x1800ac2c2  mov     [rsp+68h+TokenHandle], 0
0x1800ac2cb  call    cs:__imp_GetCurrentThread
0x1800ac2d1  lea     r9, [rsp+68h+TokenHandle]; TokenHandle
0x1800ac2d6  mov     edx, 0Eh; DesiredAccess
0x1800ac2db  lea     r8d, [rdx-0Dh]; OpenAsSelf
0x1800ac2df  mov     rcx, rax; ThreadHandle
0x1800ac2e2  call    cs:__imp_OpenThreadToken
0x1800ac2e8  test    eax, eax
0x1800ac2ea  jnz     short loc_1800AC326
0x1800ac2ec  mov     rcx, [rsp+68h]; this
0x1800ac2f1  lea     r8, aCW1SSrcDeliver_8; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800ac2f8  mov     edx, 2A2h; void *
0x1800ac2fd  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800ac302  mov     ebx, eax
0x1800ac304  mov     rcx, [rsp+68h+TokenHandle]; hObject
0x1800ac309  lea     rdx, [rcx-1]
0x1800ac30d  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800ac311  ja      short loc_1800AC319
0x1800ac313  call    cs:__imp_CloseHandle
0x1800ac319  call    cs:__imp_CoRevertToSelf
0x1800ac31f  mov     eax, ebx
0x1800ac321  jmp     loc_1800AC47A
0x1800ac326  mov     [rsp+68h+var_30], 0
0x1800ac32e  mov     [rsp+68h+TokenInformation], 0
0x1800ac336  lea     rax, [rsp+68h+var_30]
0x1800ac33b  mov     [rsp+68h+ReturnLength], rax; int
0x1800ac340  mov     r9d, 4; TokenInformationLength
0x1800ac346  lea     r8, [rsp+68h+TokenInformation]; TokenInformation
0x1800ac34b  lea     edx, [r9+5]; TokenInformationClass
0x1800ac34f  mov     rcx, [rsp+68h+TokenHandle]; TokenHandle
0x1800ac354  call    cs:__imp_GetTokenInformation
0x1800ac35a  test    eax, eax
0x1800ac35c  jnz     short loc_1800AC398
0x1800ac35e  mov     rcx, [rsp+68h]; this
0x1800ac363  lea     r8, aCW1SSrcDeliver_8; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800ac36a  mov     edx, 2A6h; void *
0x1800ac36f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800ac374  mov     ebx, eax
0x1800ac376  mov     rcx, [rsp+68h+TokenHandle]; hObject
0x1800ac37b  lea     rdx, [rcx-1]
0x1800ac37f  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800ac383  ja      short loc_1800AC38B
0x1800ac385  call    cs:__imp_CloseHandle
0x1800ac38b  call    cs:__imp_CoRevertToSelf
0x1800ac391  mov     eax, ebx
0x1800ac393  jmp     loc_1800AC47A
0x1800ac398  mov     eax, [rsp+68h+TokenInformation]
0x1800ac39c  add     eax, 0FFFFFFFEh
0x1800ac39f  cmp     eax, 1
0x1800ac3a2  jbe     short loc_1800AC3E4
0x1800ac3a4  mov     rcx, [rsp+68h]; this
0x1800ac3a9  mov     ebx, 80010123h
0x1800ac3ae  mov     r9d, ebx; char *
0x1800ac3b1  lea     r8, aCW1SSrcDeliver_8; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800ac3b8  mov     edx, 2A9h; void *
0x1800ac3bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ac3c2  mov     rcx, [rsp+68h+TokenHandle]; hObject
0x1800ac3c7  lea     rdx, [rcx-1]
0x1800ac3cb  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800ac3cf  ja      short loc_1800AC3D7
0x1800ac3d1  call    cs:__imp_CloseHandle
0x1800ac3d7  call    cs:__imp_CoRevertToSelf
0x1800ac3dd  mov     eax, ebx
0x1800ac3df  jmp     loc_1800AC47A
0x1800ac3e4  mov     [rsp+68h+var_38], 0
0x1800ac3ed  lea     rax, [rsp+68h+var_38]
0x1800ac3f2  mov     [rsp+68h+phNewToken], rax; phNewToken
0x1800ac3f7  mov     r9d, 2; ImpersonationLevel
0x1800ac3fd  mov     dword ptr [rsp+68h+ReturnLength], r9d; TokenType
0x1800ac402  xor     r8d, r8d; lpTokenAttributes
0x1800ac405  lea     edx, [r9+0Ch]; dwDesiredAccess
0x1800ac409  mov     rcx, [rsp+68h+TokenHandle]; hExistingToken
0x1800ac40e  call    cs:__imp_DuplicateTokenEx
0x1800ac414  test    eax, eax
0x1800ac416  jnz     short loc_1800AC44F
0x1800ac418  mov     rcx, [rsp+68h]; this
0x1800ac41d  lea     r8, aCW1SSrcDeliver_8; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800ac424  mov     edx, 2B2h; void *
0x1800ac429  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800ac42e  mov     ebx, eax
0x1800ac430  mov     rcx, [rsp+68h+TokenHandle]; hObject
0x1800ac435  lea     rdx, [rcx-1]
0x1800ac439  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800ac43d  ja      short loc_1800AC445
0x1800ac43f  call    cs:__imp_CloseHandle
0x1800ac445  call    cs:__imp_CoRevertToSelf
0x1800ac44b  mov     eax, ebx
0x1800ac44d  jmp     short loc_1800AC47A
0x1800ac44f  mov     rax, [rsp+68h+var_38]
0x1800ac454  mov     [rbx], rax
0x1800ac457  mov     rcx, [rsp+68h+TokenHandle]; hObject
0x1800ac45c  lea     rax, [rcx-1]
0x1800ac460  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800ac464  ja      short loc_1800AC46C
0x1800ac466  call    cs:__imp_CloseHandle
0x1800ac46c  call    cs:__imp_CoRevertToSelf
0x1800ac472  xor     eax, eax
0x1800ac474  jmp     short loc_1800AC47A
0x1800ac476  mov     eax, [rsp+68h+var_30]
0x1800ac47a  mov     rcx, [rsp+68h+var_18]
0x1800ac47f  xor     rcx, rsp; StackCookie
0x1800ac482  call    __security_check_cookie
0x1800ac487  add     rsp, 60h
0x1800ac48b  pop     rbx
0x1800ac48c  retn
0x1800ac48d  mov     r9d, eax; char *
0x1800ac490  lea     r8, aCW1SPackagesMi_3; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x1800ac497  mov     edx, 1262h; void *
0x1800ac49c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
