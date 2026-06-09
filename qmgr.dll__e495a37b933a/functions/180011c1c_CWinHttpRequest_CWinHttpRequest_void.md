# CWinHttpRequest::~CWinHttpRequest(void)

- ea: `0x180011c1c`
- end: `0x180011d77`
- name: `??1CWinHttpRequest@@UEAA@XZ`
- size: `347`
- prototype: `void __fastcall(CWinHttpRequest *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, registry_config`

## callers

- `0x180011be0`

## callees

- `0x180011760`
- `0x180011c1c`
- `0x180086674`
- `0x1800959c0`
- `0x1800a3444`
- `0x1800de6bc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180011c4c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180011c4c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180011c63`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180011c63`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180011ca1`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180011ca1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011c6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011c6d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011d36`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011d36`
- `WINHTTP!WinHttpCloseHandle` at `0x180011ce1`
- `WINHTTP!WinHttpCloseHandle` at `0x180011d06`
- `WINHTTP!WinHttpCloseHandle` at `0x180011ce1`
- `WINHTTP!WinHttpCloseHandle` at `0x180011d06`

## string_xrefs

- `0x180011c84`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`

## pseudocode

```c
void __fastcall CWinHttpRequest::~CWinHttpRequest(CWinHttpRequest *this)
{
  __int64 v2; // rbx
  void *v3; // rsi
  HANDLE CurrentThread; // rax
  const char *v5; // r9
  __int64 v6; // rdx
  void *v7; // rdx
  CWinHttpRequest::HeaderOverride *v8; // rcx
  void *v9; // rcx
  void *v10; // rcx
  char *v11; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  void *TokenHandle; // [rsp+30h] [rbp+8h] BYREF

  TokenHandle = 0;
  *(_QWORD *)this = &CWinHttpRequest::`vftable';
  v2 = -1;
  v3 = (void *)**((_QWORD **)this + 1);
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xF01FFu, 1, &TokenHandle) && GetLastError() != 1008 )
  {
    v6 = 450;
LABEL_4:
    wil::details::in1diag3::Return_GetLastError(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
      v5);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    goto LABEL_9;
  }
  if ( !SetThreadToken(0, v3) )
  {
    v6 = 454;
    goto LABEL_4;
  }
  v2 = (__int64)TokenHandle;
  TokenHandle = 0;
LABEL_9:
  while ( 1 )
  {
    v8 = (CWinHttpRequest::HeaderOverride *)*((_QWORD *)this + 3);
    if ( !v8 )
      break;
    *((_QWORD *)this + 3) = *((_QWORD *)v8 + 2);
    CWinHttpRequest::HeaderOverride::`scalar deleting destructor'(v8, (unsigned int)v7);
  }
  v9 = (void *)*((_QWORD *)this + 2);
  if ( v9 )
  {
    WinHttpCloseHandle(v9);
    *((_QWORD *)this + 2) = 0;
  }
  if ( v2 != -1 )
    wil::details::RevertImpersonateToken((HANDLE)v2, v7);
  v10 = (void *)*((_QWORD *)this + 2);
  if ( v10 )
  {
    WinHttpCloseHandle(v10);
    *((_QWORD *)this + 2) = 0;
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)this + 1) + 8LL), 0xFFFFFFFF) == 1 )
  {
    v11 = (char *)**((_QWORD **)this + 1);
    if ( (unsigned __int64)(v11 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      CloseHandle(v11);
      **((_QWORD **)this + 1) = 0;
    }
    operator delete(*((void **)this + 1), 0x10u);
    *((_QWORD *)this + 1) = 0;
  }
  *(_QWORD *)this = &IHttpRequest::`vftable';
}

```

## disassembly

```asm
0x180011c1c  mov     [rsp+arg_8], rbx
0x180011c21  mov     [rsp+arg_10], rsi
0x180011c26  push    rdi
0x180011c27  sub     rsp, 20h
0x180011c2b  lea     rax, ??_7CWinHttpRequest@@6B@; const CWinHttpRequest::`vftable'
0x180011c32  mov     [rsp+28h+TokenHandle], 0
0x180011c3b  mov     [rcx], rax
0x180011c3e  mov     rdi, rcx
0x180011c41  mov     rax, [rcx+8]
0x180011c45  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180011c49  mov     rsi, [rax]
0x180011c4c  call    cs:__imp_GetCurrentThread
0x180011c52  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x180011c57  mov     edx, 0F01FFh; DesiredAccess
0x180011c5c  mov     rcx, rax; ThreadHandle
0x180011c5f  lea     r8d, [rbx+2]; OpenAsSelf
0x180011c63  call    cs:__imp_OpenThreadToken
0x180011c69  test    eax, eax
0x180011c6b  jnz     short loc_180011C9C
0x180011c6d  call    cs:__imp_GetLastError
0x180011c73  cmp     eax, 3F0h
0x180011c78  jz      short loc_180011C9C
0x180011c7a  mov     edx, 1C2h; void *
0x180011c7f  mov     rcx, [rsp+28h]; this
0x180011c84  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180011c8b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180011c90  lea     rcx, [rsp+28h+TokenHandle]
0x180011c95  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180011c9a  jmp     short loc_180011CCF
0x180011c9c  mov     rdx, rsi; Token
0x180011c9f  xor     ecx, ecx; Thread
0x180011ca1  call    cs:__imp_SetThreadToken
0x180011ca7  test    eax, eax
0x180011ca9  jnz     short loc_180011CB2
0x180011cab  mov     edx, 1C6h
0x180011cb0  jmp     short loc_180011C7F
0x180011cb2  mov     rbx, [rsp+28h+TokenHandle]
0x180011cb7  mov     [rsp+28h+TokenHandle], 0
0x180011cc0  jmp     short loc_180011CCF
0x180011cc2  mov     rax, [rcx+10h]
0x180011cc6  mov     [rdi+18h], rax
0x180011cca  call    ??_GHeaderOverride@CWinHttpRequest@@QEAAPEAXI@Z; CWinHttpRequest::HeaderOverride::`scalar deleting destructor'(uint)
0x180011ccf  mov     rcx, [rdi+18h]; this
0x180011cd3  test    rcx, rcx
0x180011cd6  jnz     short loc_180011CC2
0x180011cd8  mov     rcx, [rdi+10h]; hInternet
0x180011cdc  test    rcx, rcx
0x180011cdf  jz      short loc_180011CEF
0x180011ce1  call    cs:__imp_WinHttpCloseHandle
0x180011ce7  mov     qword ptr [rdi+10h], 0
0x180011cef  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180011cf3  jz      short loc_180011CFD
0x180011cf5  mov     rcx, rbx; Token
0x180011cf8  call    ?RevertImpersonateToken@details@wil@@YAXPEAX@Z; wil::details::RevertImpersonateToken(void *)
0x180011cfd  mov     rcx, [rdi+10h]; hInternet
0x180011d01  test    rcx, rcx
0x180011d04  jz      short loc_180011D14
0x180011d06  call    cs:__imp_WinHttpCloseHandle
0x180011d0c  mov     qword ptr [rdi+10h], 0
0x180011d14  mov     rcx, [rdi+8]
0x180011d18  or      eax, 0FFFFFFFFh
0x180011d1b  lock xadd [rcx+8], eax
0x180011d20  cmp     eax, 1
0x180011d23  jnz     short loc_180011D5D
0x180011d25  mov     rax, [rdi+8]
0x180011d29  mov     rcx, [rax]; hObject
0x180011d2c  lea     rax, [rcx-1]
0x180011d30  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180011d34  ja      short loc_180011D47
0x180011d36  call    cs:__imp_CloseHandle
0x180011d3c  mov     rax, [rdi+8]
0x180011d40  mov     qword ptr [rax], 0
0x180011d47  mov     rcx, [rdi+8]; void *
0x180011d4b  mov     edx, 10h; unsigned __int64
0x180011d50  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180011d55  mov     qword ptr [rdi+8], 0
0x180011d5d  mov     rbx, [rsp+28h+arg_8]
0x180011d62  lea     rax, ??_7IHttpRequest@@6B@; const IHttpRequest::`vftable'
0x180011d69  mov     rsi, [rsp+28h+arg_10]
0x180011d6e  mov     [rdi], rax
0x180011d71  add     rsp, 20h
0x180011d75  pop     rdi
0x180011d76  retn
```
