# CWinHttpSession::Connect(ushort const *,ushort)

- ea: `0x180082e00`
- end: `0x180082fb5`
- name: `?Connect@CWinHttpSession@@UEAAPEAVIHttpConnection@@PEBGG@Z`
- size: `437`
- prototype: `struct IHttpConnection *(CWinHttpSession *__hidden this, const unsigned __int16 *, unsigned __int16)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180006640`
- `0x180011760`
- `0x1800131f0`
- `0x180082e00`
- `0x180086674`
- `0x1800959c0`
- `0x1800f9948`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180082e39`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180082e39`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180082e4f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180082e4f`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180082e8d`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180082e8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082e59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082f00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082f0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082f12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082e59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082f00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082f0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082f12`
- `WINHTTP!WinHttpCloseHandle` at `0x180082f86`
- `WINHTTP!WinHttpCloseHandle` at `0x180082f86`
- `WINHTTP!WinHttpConnect` at `0x180082eee`
- `WINHTTP!WinHttpConnect` at `0x180082eee`

## string_xrefs

- `0x180082e6b`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
struct IHttpConnection *__fastcall CWinHttpSession::Connect(
        CWinHttpSession *this,
        const unsigned __int16 *a2,
        INTERNET_PORT a3)
{
  __int64 v6; // rdi
  void *v7; // rbx
  HANDLE CurrentThread; // rax
  const char *v9; // r9
  __int64 v10; // rdx
  int LastError; // ebx
  void *v12; // rbx
  unsigned int v13; // eax
  CWinHttpConnection *v14; // rax
  void *v15; // rdx
  CWinHttpConnection *v16; // rsi
  void **pExceptionObject; // [rsp+30h] [rbp-29h] BYREF
  __int128 v19; // [rsp+38h] [rbp-21h]
  unsigned int v20; // [rsp+48h] [rbp-11h]
  int v21; // [rsp+4Ch] [rbp-Dh]
  int v22; // [rsp+50h] [rbp-9h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]
  void *TokenHandle; // [rsp+C0h] [rbp+67h] BYREF
  __int64 v25; // [rsp+D8h] [rbp+7Fh]

  v6 = -1;
  v25 = -1;
  v7 = (void *)**((_QWORD **)this + 1);
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xF01FFu, 1, &TokenHandle) && GetLastError() != 1008 )
  {
    v10 = 450;
LABEL_4:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v10,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
                  v9);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    goto LABEL_8;
  }
  if ( !SetThreadToken(0, v7) )
  {
    v10 = 454;
    goto LABEL_4;
  }
  v6 = (__int64)TokenHandle;
  v25 = (__int64)TokenHandle;
  LastError = 0;
LABEL_8:
  if ( LastError < 0 )
  {
    v19 = 0;
    pExceptionObject = &ComError::`vftable';
    v20 = LastError;
    v21 = 2391;
    v22 = 1;
    throw (ComError *)&pExceptionObject;
  }
  v12 = WinHttpConnect(*((HINTERNET *)this + 2), a2, a3, 0);
  TokenHandle = v12;
  if ( !v12 )
  {
    if ( (int)GetLastError() > 0 )
      v13 = (unsigned __int16)GetLastError() | 0x80070000;
    else
      v13 = GetLastError();
    v19 = 0;
    pExceptionObject = &ComError::`vftable';
    v20 = v13;
    v21 = 2399;
    v22 = 1;
    throw (ComError *)&pExceptionObject;
  }
  v14 = (CWinHttpConnection *)operator new(0x18u);
  if ( v14 )
  {
    v16 = CWinHttpConnection::CWinHttpConnection(v14, (struct InternetHandleHolder *)&TokenHandle);
    v12 = TokenHandle;
  }
  else
  {
    v16 = 0;
  }
  if ( v12 )
    WinHttpCloseHandle(v12);
  if ( v6 != -1 )
    wil::details::RevertImpersonateToken((HANDLE)v6, v15);
  return v16;
}

```

## disassembly

```asm
0x180082e00  mov     [rsp-8+arg_8], rbx
0x180082e05  push    rbp
0x180082e06  push    rsi
0x180082e07  push    rdi
0x180082e08  push    r14
0x180082e0a  push    r15
0x180082e0c  lea     rbp, [rsp-37h]
0x180082e11  sub     rsp, 90h
0x180082e18  movzx   r14d, r8w
0x180082e1c  mov     r15, rdx
0x180082e1f  mov     rsi, rcx
0x180082e22  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180082e26  mov     [rbp+57h+arg_18], rdi
0x180082e2a  mov     rax, [rcx+8]
0x180082e2e  mov     rbx, [rax]
0x180082e31  mov     [rbp+57h+TokenHandle], 0
0x180082e39  call    cs:__imp_GetCurrentThread
0x180082e3f  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x180082e43  mov     edx, 0F01FFh; DesiredAccess
0x180082e48  lea     r8d, [rdi+2]; OpenAsSelf
0x180082e4c  mov     rcx, rax; ThreadHandle
0x180082e4f  call    cs:__imp_OpenThreadToken
0x180082e55  test    eax, eax
0x180082e57  jnz     short loc_180082E88
0x180082e59  call    cs:__imp_GetLastError
0x180082e5f  cmp     eax, 3F0h
0x180082e64  jz      short loc_180082E88
0x180082e66  mov     edx, 1C2h; void *
0x180082e6b  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180082e72  mov     rcx, [rbp+5Fh]; this
0x180082e76  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180082e7b  mov     ebx, eax
0x180082e7d  lea     rcx, [rbp+57h+TokenHandle]
0x180082e81  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180082e86  jmp     short loc_180082EA8
0x180082e88  mov     rdx, rbx; Token
0x180082e8b  xor     ecx, ecx; Thread
0x180082e8d  call    cs:__imp_SetThreadToken
0x180082e93  test    eax, eax
0x180082e95  jnz     short loc_180082E9E
0x180082e97  mov     edx, 1C6h
0x180082e9c  jmp     short loc_180082E6B
0x180082e9e  mov     rdi, [rbp+57h+TokenHandle]
0x180082ea2  mov     [rbp+57h+arg_18], rdi
0x180082ea6  xor     ebx, ebx
0x180082ea8  test    ebx, ebx
0x180082eaa  jns     short loc_180082EE0
0x180082eac  xorps   xmm0, xmm0
0x180082eaf  movups  [rbp+57h+var_78], xmm0
0x180082eb3  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x180082eba  mov     [rbp+57h+pExceptionObject], rcx
0x180082ebe  mov     [rbp+57h+var_68], ebx
0x180082ec1  mov     [rbp+57h+var_64], 957h
0x180082ec8  mov     [rbp+57h+var_60], 1
0x180082ecf  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180082ed6  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180082eda  call    _CxxThrowException_0
0x180082ee0  xor     r9d, r9d; dwReserved
0x180082ee3  movzx   r8d, r14w; nServerPort
0x180082ee7  mov     rdx, r15; pswzServerName
0x180082eea  mov     rcx, [rsi+10h]; hSession
0x180082eee  call    cs:__imp_WinHttpConnect
0x180082ef4  mov     rbx, rax
0x180082ef7  mov     [rbp+57h+TokenHandle], rax
0x180082efb  test    rax, rax
0x180082efe  jnz     short loc_180082F54
0x180082f00  call    cs:__imp_GetLastError
0x180082f06  test    eax, eax
0x180082f08  jg      short loc_180082F12
0x180082f0a  call    cs:__imp_GetLastError
0x180082f10  jmp     short loc_180082F20
0x180082f12  call    cs:__imp_GetLastError
0x180082f18  movzx   eax, ax
0x180082f1b  or      eax, 80070000h
0x180082f20  xorps   xmm0, xmm0
0x180082f23  movups  [rbp+57h+var_78], xmm0
0x180082f27  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x180082f2e  mov     [rbp+57h+pExceptionObject], rcx
0x180082f32  mov     [rbp+57h+var_68], eax
0x180082f35  mov     [rbp+57h+var_64], 95Fh
0x180082f3c  mov     [rbp+57h+var_60], 1
0x180082f43  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180082f4a  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180082f4e  call    _CxxThrowException_0
0x180082f54  mov     ecx, 18h; dwBytes
0x180082f59  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180082f5e  mov     [rbp+57h+var_90], rax
0x180082f62  test    rax, rax
0x180082f65  jz      short loc_180082F7C
0x180082f67  lea     rdx, [rbp+57h+TokenHandle]; struct InternetHandleHolder *
0x180082f6b  mov     rcx, rax; this
0x180082f6e  call    ??0CWinHttpConnection@@QEAA@AEAVInternetHandleHolder@@@Z; CWinHttpConnection::CWinHttpConnection(InternetHandleHolder &)
0x180082f73  mov     rsi, rax
0x180082f76  mov     rbx, [rbp+57h+TokenHandle]
0x180082f7a  jmp     short loc_180082F7E
0x180082f7c  xor     esi, esi
0x180082f7e  test    rbx, rbx
0x180082f81  jz      short loc_180082F8D
0x180082f83  mov     rcx, rbx; hInternet
0x180082f86  call    cs:__imp_WinHttpCloseHandle
0x180082f8c  nop
0x180082f8d  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180082f91  jz      short loc_180082F9B
0x180082f93  mov     rcx, rdi; Token
0x180082f96  call    ?RevertImpersonateToken@details@wil@@YAXPEAX@Z; wil::details::RevertImpersonateToken(void *)
0x180082f9b  mov     rax, rsi
0x180082f9e  mov     rbx, [rsp+0B0h+arg_8]
0x180082fa6  add     rsp, 90h
0x180082fad  pop     r15
0x180082faf  pop     r14
0x180082fb1  pop     rdi
0x180082fb2  pop     rsi
0x180082fb3  pop     rbp
0x180082fb4  retn
```
