# CAutoImpersonate::ImpersonateUser(void *)

- ea: `0x180005dd0`
- end: `0x180005f51`
- name: `?ImpersonateUser@CAutoImpersonate@@QEAAJPEAX@Z`
- size: `385`
- prototype: `int(CAutoImpersonate *__hidden this, void *)`
- caller_count: `15`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180005c80`
- `0x180006dbc`
- `0x180010734`
- `0x180012508`
- `0x1800156ec`
- `0x180016150`
- `0x18001bdd8`
- `0x18001ce78`
- `0x180038118`
- `0x1800393f8`
- `0x18003a24c`
- `0x18003b26c`
- `0x180045160`
- `0x18004ff88`
- `0x180050f9c`

## callees

- `0x180005dd0`
- `0x1800084bc`
- `0x18002df48`
- `0x180030ad0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005e63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005e63`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180005e53`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180005e53`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180005dfe`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180005dfe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180005e34`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180005e34`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005e1a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005e1a`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180005e80`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180005e80`

## string_xrefs

- `0x180005ed8`: `onecore\ds\security\gina\profile\proflib\sid.cpp`
- `0x180005f07`: `onecore\ds\security\gina\profile\proflib\sid.cpp`
- `0x180005f2f`: `onecore\ds\security\gina\profile\proflib\sid.cpp`

## pseudocode

```c
__int64 __fastcall CAutoImpersonate::ImpersonateUser(CAutoImpersonate *this, void *a2)
{
  const char *v4; // r9
  void *v5; // rcx
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  signed int v8; // edi
  const char *v9; // r9
  __int64 result; // rax
  int v11; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  void *TokenHandle; // [rsp+38h] [rbp+10h] BYREF

  if ( !a2 )
    return 2147500037LL;
  if ( *((_BYTE *)this + 8) )
  {
    if ( SetThreadToken(0, *(HANDLE *)this) )
    {
      v5 = *(void **)this;
      if ( !*(_QWORD *)this )
      {
LABEL_6:
        *((_BYTE *)this + 8) = 0;
        goto LABEL_7;
      }
    }
    else
    {
      wil::details::in1diag3::Return_GetLastError(
        retaddr,
        (void *)0x4F,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\proflib\\sid.cpp",
        v4);
      v5 = *(void **)this;
      if ( !*(_QWORD *)this )
        goto LABEL_6;
    }
    CloseHandle(v5);
    goto LABEL_6;
  }
LABEL_7:
  *(_QWORD *)this = 0;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0x2000Cu, 1, &TokenHandle) )
    goto LABEL_22;
  LastError = GetLastError();
  v8 = LastError;
  if ( LastError > 0 )
    v8 = (unsigned __int16)LastError | 0x80070000;
  if ( v8 == -2147023888 || v8 >= 0 )
  {
LABEL_22:
    if ( ImpersonateLoggedOnUser(a2) )
    {
      v8 = 0;
      *(_QWORD *)this = TokenHandle;
    }
    else
    {
      v8 = wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x2D,
             (unsigned int)"onecore\\ds\\security\\gina\\profile\\proflib\\sid.cpp",
             v9);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2A,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\proflib\\sid.cpp",
      (const char *)(unsigned int)v8,
      v11);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  }
  result = (unsigned int)v8;
  *((_BYTE *)this + 8) = v8 >= 0;
  return result;
}

```

## disassembly

```asm
0x180005dd0  mov     [rsp+arg_18], rbx
0x180005dd5  push    rsi; int
0x180005dd6  sub     rsp, 20h
0x180005dda  mov     rsi, rdx
0x180005ddd  mov     rbx, rcx
0x180005de0  test    rdx, rdx
0x180005de3  jz      loc_180005ECC
0x180005de9  cmp     byte ptr [rcx+8], 0
0x180005ded  mov     [rsp+28h+arg_0], rbp
0x180005df2  mov     [rsp+28h+arg_10], rdi
0x180005df7  jz      short loc_180005E2A
0x180005df9  mov     rdx, [rcx]; Token
0x180005dfc  xor     ecx, ecx; Thread
0x180005dfe  call    cs:__imp_SetThreadToken
0x180005e05  nop     dword ptr [rax+rax+00h]
0x180005e0a  test    eax, eax
0x180005e0c  jz      loc_180005ED3
0x180005e12  mov     rcx, [rbx]; hObject
0x180005e15  test    rcx, rcx
0x180005e18  jz      short loc_180005E26
0x180005e1a  call    cs:__imp_CloseHandle
0x180005e21  nop     dword ptr [rax+rax+00h]
0x180005e26  mov     byte ptr [rbx+8], 0
0x180005e2a  xor     ebp, ebp
0x180005e2c  mov     [rbx], rbp
0x180005e2f  mov     [rsp+28h+TokenHandle], rbp
0x180005e34  call    cs:__imp_GetCurrentThread
0x180005e3b  nop     dword ptr [rax+rax+00h]
0x180005e40  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x180005e45  mov     edx, 2000Ch; DesiredAccess
0x180005e4a  mov     rcx, rax; ThreadHandle
0x180005e4d  mov     r8d, 1; OpenAsSelf
0x180005e53  call    cs:__imp_OpenThreadToken
0x180005e5a  nop     dword ptr [rax+rax+00h]
0x180005e5f  test    eax, eax
0x180005e61  jnz     short loc_180005E7D
0x180005e63  call    cs:__imp_GetLastError
0x180005e6a  nop     dword ptr [rax+rax+00h]
0x180005e6f  mov     edi, eax
0x180005e71  test    eax, eax
0x180005e73  jg      short loc_180005EC1
0x180005e75  cmp     edi, 800703F0h
0x180005e7b  jnz     short loc_180005EFA
0x180005e7d  mov     rcx, rsi; hToken
0x180005e80  call    cs:__imp_ImpersonateLoggedOnUser
0x180005e87  nop     dword ptr [rax+rax+00h]
0x180005e8c  test    eax, eax
0x180005e8e  jz      loc_180005F2A
0x180005e94  mov     rax, [rsp+28h+TokenHandle]
0x180005e99  mov     edi, ebp
0x180005e9b  mov     [rbx], rax
0x180005e9e  mov     rbp, [rsp+28h+arg_0]
0x180005ea3  mov     ecx, edi
0x180005ea5  shr     ecx, 1Fh
0x180005ea8  mov     eax, edi
0x180005eaa  mov     rdi, [rsp+28h+arg_10]
0x180005eaf  xor     cl, 1
0x180005eb2  mov     [rbx+8], cl
0x180005eb5  mov     rbx, [rsp+28h+arg_18]
0x180005eba  add     rsp, 20h
0x180005ebe  pop     rsi
0x180005ebf  retn
0x180005ec1  movzx   edi, ax
0x180005ec4  or      edi, 80070000h
0x180005eca  jmp     short loc_180005E75
0x180005ecc  mov     eax, 80004005h
0x180005ed1  jmp     short loc_180005EB5
0x180005ed3  mov     rcx, [rsp+28h]; this
0x180005ed8  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\p"...
0x180005edf  mov     edx, 4Fh ; 'O'; void *
0x180005ee4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180005ee9  mov     rcx, [rbx]
0x180005eec  test    rcx, rcx
0x180005eef  jz      loc_180005E26
0x180005ef5  jmp     loc_180005E1A
0x180005efa  test    edi, edi
0x180005efc  jns     loc_180005E7D
0x180005f02  mov     rcx, [rsp+28h]; this
0x180005f07  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\p"...
0x180005f0e  mov     r9d, edi; char *
0x180005f11  mov     edx, 2Ah ; '*'; void *
0x180005f16  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005f1b  lea     rcx, [rsp+28h+TokenHandle]
0x180005f20  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180005f25  jmp     loc_180005E9E
0x180005f2a  mov     rcx, [rsp+28h]; this
0x180005f2f  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\p"...
0x180005f36  mov     edx, 2Dh ; '-'; void *
0x180005f3b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180005f40  lea     rcx, [rsp+28h+TokenHandle]
0x180005f45  mov     edi, eax
0x180005f47  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180005f4c  jmp     loc_180005E9E
```
