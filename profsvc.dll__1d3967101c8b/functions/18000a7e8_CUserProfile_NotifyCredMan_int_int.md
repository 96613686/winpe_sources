# CUserProfile::NotifyCredMan(int,int)

- ea: `0x18000a7e8`
- end: `0x18000a9af`
- name: `?NotifyCredMan@CUserProfile@@IEAAXHH@Z`
- size: `455`
- prototype: `void __fastcall(CUserProfile *__hidden this, int, int)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000b540`
- `0x18002bf94`

## callees

- `0x18000a7e8`
- `0x18000a9b8`
- `0x18002d2d8`
- `0x18002db38`
- `0x180030558`
- `0x18003f42c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a854`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a854`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000a84a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000a84a`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000a8b7`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000a8b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000a832`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000a832`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a8ce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a8ce`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18000a873`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18000a873`
- `api-ms-win-security-credentials-l2-1-0!CredProfileUnloaded` at `0x18000a91b`
- `api-ms-win-security-credentials-l2-1-0!CredProfileUnloaded` at `0x18000a91b`
- `api-ms-win-security-credentials-l2-1-0!CredProfileLoadedEx` at `0x18000a898`
- `api-ms-win-security-credentials-l2-1-0!CredProfileLoadedEx` at `0x18000a898`

## string_xrefs

- `0x18000a905`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18000a97f`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18000a92a`: `onecore\ds\security\gina\profile\proflib\sid.cpp`
- `0x18000a95c`: `onecore\ds\security\gina\profile\proflib\sid.cpp`
- `0x18000a999`: `onecore\ds\security\gina\profile\proflib\sid.cpp`

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
    (int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
    (const char *)(unsigned int)v6);
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
0x18000a7e8  mov     [rsp-18h+arg_8], rbx
0x18000a7ed  mov     [rsp-18h+arg_10], rsi
0x18000a7f2  push    rbp
0x18000a7f3  push    rdi
0x18000a7f4  push    r14
0x18000a7f6  mov     rbp, rsp
0x18000a7f9  sub     rsp, 30h
0x18000a7fd  test    byte ptr [rcx+8], 4
0x18000a801  mov     r14d, r8d
0x18000a804  mov     esi, edx
0x18000a806  jnz     loc_18000A8DC
0x18000a80c  mov     rdi, [rcx+18h]
0x18000a810  mov     ebx, 80004005h
0x18000a815  mov     [rbp+Token], 0
0x18000a81d  mov     [rbp+var_8], 0
0x18000a821  test    rdi, rdi
0x18000a824  jz      loc_18000A901
0x18000a82a  mov     [rbp+TokenHandle], 0
0x18000a832  call    cs:__imp_GetCurrentThread
0x18000a838  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18000a83c  mov     edx, 2000Ch; DesiredAccess
0x18000a841  mov     rcx, rax; ThreadHandle
0x18000a844  mov     r8d, 1; OpenAsSelf
0x18000a84a  call    cs:__imp_OpenThreadToken
0x18000a850  test    eax, eax
0x18000a852  jnz     short loc_18000A870
0x18000a854  call    cs:__imp_GetLastError
0x18000a85a  mov     ebx, eax
0x18000a85c  test    eax, eax
0x18000a85e  jg      loc_18000A8EF
0x18000a864  cmp     ebx, 800703F0h
0x18000a86a  jnz     loc_18000A950
0x18000a870  mov     rcx, rdi; hToken
0x18000a873  call    cs:__imp_ImpersonateLoggedOnUser
0x18000a879  test    eax, eax
0x18000a87b  jz      loc_18000A926
0x18000a881  mov     rax, [rbp+TokenHandle]
0x18000a885  mov     [rbp+Token], rax
0x18000a889  mov     [rbp+var_8], 1
0x18000a88d  test    esi, esi
0x18000a88f  jz      loc_18000A91B
0x18000a895  mov     ecx, r14d
0x18000a898  call    cs:__imp_CredProfileLoadedEx
0x18000a89e  test    eax, eax
0x18000a8a0  setz    cl
0x18000a8a3  test    cl, cl
0x18000a8a5  jnz     loc_18000A97B
0x18000a8ab  cmp     [rbp+var_8], 0
0x18000a8af  jz      short loc_18000A8DC
0x18000a8b1  mov     rdx, [rbp+Token]; Token
0x18000a8b5  xor     ecx, ecx; Thread
0x18000a8b7  call    cs:__imp_SetThreadToken
0x18000a8bd  test    eax, eax
0x18000a8bf  jz      loc_18000A995
0x18000a8c5  mov     rcx, [rbp+Token]; hObject
0x18000a8c9  test    rcx, rcx
0x18000a8cc  jz      short loc_18000A8DC
0x18000a8ce  call    cs:__imp_CloseHandle
0x18000a8d4  mov     [rbp+Token], 0
0x18000a8dc  mov     rbx, [rsp+30h+arg_8]
0x18000a8e1  mov     rsi, [rsp+30h+arg_10]
0x18000a8e6  add     rsp, 30h
0x18000a8ea  pop     r14
0x18000a8ec  pop     rdi
0x18000a8ed  pop     rbp
0x18000a8ee  retn
0x18000a8ef  movzx   ebx, ax
0x18000a8f2  or      ebx, 80070000h
0x18000a8f8  jmp     loc_18000A864
0x18000a8fd  mov     [rbp+var_8], 0
0x18000a901  mov     rcx, [rbp+18h]; this
0x18000a905  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000a90c  mov     r9d, ebx; char *
0x18000a90f  mov     edx, 0B9Ch; void *
0x18000a914  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000a919  jmp     short loc_18000A8AB
0x18000a91b  call    cs:__imp_CredProfileUnloaded
0x18000a921  jmp     loc_18000A89E
0x18000a926  mov     rcx, [rbp+18h]; this
0x18000a92a  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000a931  mov     edx, 2Dh ; '-'; void *
0x18000a936  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000a93b  lea     rcx, [rbp+TokenHandle]
0x18000a93f  mov     ebx, eax
0x18000a941  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18000a946  test    ebx, ebx
0x18000a948  jns     loc_18000A889
0x18000a94e  jmp     short loc_18000A8FD
0x18000a950  test    ebx, ebx
0x18000a952  jns     loc_18000A870
0x18000a958  mov     rcx, [rbp+18h]; this
0x18000a95c  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000a963  mov     r9d, ebx; char *
0x18000a966  mov     edx, 2Ah ; '*'; void *
0x18000a96b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a970  lea     rcx, [rbp+TokenHandle]
0x18000a974  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18000a979  jmp     short loc_18000A8FD
0x18000a97b  mov     rcx, [rbp+18h]; this
0x18000a97f  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000a986  mov     edx, 0B9Eh; void *
0x18000a98b  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18000a990  jmp     loc_18000A8AB
0x18000a995  mov     rcx, [rbp+18h]; this
0x18000a999  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000a9a0  mov     edx, 4Fh ; 'O'; void *
0x18000a9a5  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000a9aa  jmp     loc_18000A8C5
```
