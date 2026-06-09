# CUserProfile::NotifyCredMan(int,int)

- ea: `0x1800082b8`
- end: `0x1800084b3`
- name: `?NotifyCredMan@CUserProfile@@IEAAXHH@Z`
- size: `507`
- prototype: `void __fastcall(CUserProfile *__hidden this, int, int)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180008fa0`
- `0x180030744`

## callees

- `0x1800082b8`
- `0x1800084bc`
- `0x18002df48`
- `0x18002df68`
- `0x180030ad0`
- `0x180040bcc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008330`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008330`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180008320`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180008320`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800083a5`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800083a5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180008302`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180008302`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800083c2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800083c2`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180008355`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180008355`
- `api-ms-win-security-credentials-l2-1-0!CredProfileUnloaded` at `0x180008416`
- `api-ms-win-security-credentials-l2-1-0!CredProfileUnloaded` at `0x180008416`
- `api-ms-win-security-credentials-l2-1-0!CredProfileLoadedEx` at `0x180008380`
- `api-ms-win-security-credentials-l2-1-0!CredProfileLoadedEx` at `0x180008380`

## string_xrefs

- `0x180008400`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x180008483`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18000842b`: `onecore\ds\security\gina\profile\proflib\sid.cpp`
- `0x18000845d`: `onecore\ds\security\gina\profile\proflib\sid.cpp`
- `0x18000849d`: `onecore\ds\security\gina\profile\proflib\sid.cpp`

## pseudocode

```c
void __fastcall CUserProfile::NotifyCredMan(CUserProfile *this, int a2, unsigned int a3)
{
  void *v5; // rdi
  signed int v6; // ebx
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  const char *v9; // r9
  int v10; // eax
  const char *v11; // r9
  const char *v12; // r9
  HANDLE Token; // [rsp+20h] [rbp-10h]
  char v14; // [rsp+28h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  void *TokenHandle; // [rsp+50h] [rbp+20h] BYREF

  if ( (*((_BYTE *)this + 8) & 4) != 0 )
    return;
  v5 = (void *)*((_QWORD *)this + 3);
  v6 = -2147467259;
  Token = 0;
  v14 = 0;
  if ( !v5 )
    goto LABEL_20;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0x2000Cu, 1, &TokenHandle) )
    goto LABEL_28;
  LastError = GetLastError();
  v6 = LastError;
  if ( LastError > 0 )
    v6 = (unsigned __int16)LastError | 0x80070000;
  if ( v6 == -2147023888 || v6 >= 0 )
  {
LABEL_28:
    if ( ImpersonateLoggedOnUser(v5) )
    {
      Token = TokenHandle;
    }
    else
    {
      v6 = wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x2D,
             (unsigned int)"onecore\\ds\\security\\gina\\profile\\proflib\\sid.cpp",
             v9);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
      if ( v6 < 0 )
        goto LABEL_19;
    }
    v14 = 1;
    if ( a2 )
      v10 = CredProfileLoadedEx(a3);
    else
      v10 = CredProfileUnloaded();
    if ( !v10 )
      wil::details::in1diag3::_Log_GetLastError(
        retaddr,
        (void *)0xB9E,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
        v11);
    goto LABEL_13;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x2A,
    (unsigned int)"onecore\\ds\\security\\gina\\profile\\proflib\\sid.cpp",
    (const char *)(unsigned int)v6,
    0);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
LABEL_19:
  v14 = 0;
LABEL_20:
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0xB9C,
    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
    (const char *)(unsigned int)v6,
    (int)Token);
LABEL_13:
  if ( v14 )
  {
    if ( !SetThreadToken(0, Token) )
      wil::details::in1diag3::Return_GetLastError(
        retaddr,
        (void *)0x4F,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\proflib\\sid.cpp",
        v12);
    if ( Token )
      CloseHandle(Token);
  }
}

```

## disassembly

```asm
0x1800082b8  mov     [rsp-18h+arg_8], rbx
0x1800082bd  mov     [rsp-18h+arg_10], rsi
0x1800082c2  push    rbp
0x1800082c3  push    rdi
0x1800082c4  push    r14
0x1800082c6  mov     rbp, rsp
0x1800082c9  sub     rsp, 30h
0x1800082cd  test    byte ptr [rcx+8], 4
0x1800082d1  mov     r14d, r8d
0x1800082d4  mov     esi, edx
0x1800082d6  jnz     loc_1800083D6
0x1800082dc  mov     rdi, [rcx+18h]
0x1800082e0  mov     ebx, 80004005h
0x1800082e5  mov     [rbp+Token], 0
0x1800082ed  mov     [rbp+var_8], 0
0x1800082f1  test    rdi, rdi
0x1800082f4  jz      loc_1800083FC
0x1800082fa  mov     [rbp+TokenHandle], 0
0x180008302  call    cs:__imp_GetCurrentThread
0x180008309  nop     dword ptr [rax+rax+00h]
0x18000830e  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180008312  mov     edx, 2000Ch; DesiredAccess
0x180008317  mov     rcx, rax; ThreadHandle
0x18000831a  mov     r8d, 1; OpenAsSelf
0x180008320  call    cs:__imp_OpenThreadToken
0x180008327  nop     dword ptr [rax+rax+00h]
0x18000832c  test    eax, eax
0x18000832e  jnz     short loc_180008352
0x180008330  call    cs:__imp_GetLastError
0x180008337  nop     dword ptr [rax+rax+00h]
0x18000833c  mov     ebx, eax
0x18000833e  test    eax, eax
0x180008340  jg      loc_1800083EA
0x180008346  cmp     ebx, 800703F0h
0x18000834c  jnz     loc_180008451
0x180008352  mov     rcx, rdi; hToken
0x180008355  call    cs:__imp_ImpersonateLoggedOnUser
0x18000835c  nop     dword ptr [rax+rax+00h]
0x180008361  test    eax, eax
0x180008363  jz      loc_180008427
0x180008369  mov     rax, [rbp+TokenHandle]
0x18000836d  mov     [rbp+Token], rax
0x180008371  mov     [rbp+var_8], 1
0x180008375  test    esi, esi
0x180008377  jz      loc_180008416
0x18000837d  mov     ecx, r14d
0x180008380  call    cs:__imp_CredProfileLoadedEx
0x180008387  nop     dword ptr [rax+rax+00h]
0x18000838c  test    eax, eax
0x18000838e  setz    cl
0x180008391  test    cl, cl
0x180008393  jnz     loc_18000847F
0x180008399  cmp     [rbp+var_8], 0
0x18000839d  jz      short loc_1800083D6
0x18000839f  mov     rdx, [rbp+Token]; Token
0x1800083a3  xor     ecx, ecx; Thread
0x1800083a5  call    cs:__imp_SetThreadToken
0x1800083ac  nop     dword ptr [rax+rax+00h]
0x1800083b1  test    eax, eax
0x1800083b3  jz      loc_180008499
0x1800083b9  mov     rcx, [rbp+Token]; hObject
0x1800083bd  test    rcx, rcx
0x1800083c0  jz      short loc_1800083D6
0x1800083c2  call    cs:__imp_CloseHandle
0x1800083c9  nop     dword ptr [rax+rax+00h]
0x1800083ce  mov     [rbp+Token], 0
0x1800083d6  mov     rbx, [rsp+30h+arg_8]
0x1800083db  mov     rsi, [rsp+30h+arg_10]
0x1800083e0  add     rsp, 30h
0x1800083e4  pop     r14
0x1800083e6  pop     rdi
0x1800083e7  pop     rbp
0x1800083e8  retn
0x1800083ea  movzx   ebx, ax
0x1800083ed  or      ebx, 80070000h
0x1800083f3  jmp     loc_180008346
0x1800083f8  mov     [rbp+var_8], 0
0x1800083fc  mov     rcx, [rbp+18h]; this
0x180008400  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x180008407  mov     r9d, ebx; char *
0x18000840a  mov     edx, 0B9Ch; void *
0x18000840f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180008414  jmp     short loc_180008399
0x180008416  call    cs:__imp_CredProfileUnloaded
0x18000841d  nop     dword ptr [rax+rax+00h]
0x180008422  jmp     loc_18000838C
0x180008427  mov     rcx, [rbp+18h]; this
0x18000842b  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\p"...
0x180008432  mov     edx, 2Dh ; '-'; void *
0x180008437  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000843c  lea     rcx, [rbp+TokenHandle]
0x180008440  mov     ebx, eax
0x180008442  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180008447  test    ebx, ebx
0x180008449  jns     loc_180008371
0x18000844f  jmp     short loc_1800083F8
0x180008451  test    ebx, ebx
0x180008453  jns     loc_180008352
0x180008459  mov     rcx, [rbp+18h]; this
0x18000845d  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\p"...
0x180008464  mov     r9d, ebx; char *
0x180008467  mov     edx, 2Ah ; '*'; void *
0x18000846c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008471  lea     rcx, [rbp+TokenHandle]
0x180008475  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18000847a  jmp     loc_1800083F8
0x18000847f  mov     rcx, [rbp+18h]; this
0x180008483  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000848a  mov     edx, 0B9Eh; void *
0x18000848f  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x180008494  jmp     loc_180008399
0x180008499  mov     rcx, [rbp+18h]; this
0x18000849d  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800084a4  mov     edx, 4Fh ; 'O'; void *
0x1800084a9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800084ae  jmp     loc_1800083B9
```
