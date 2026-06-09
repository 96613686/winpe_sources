# CWinHttpRequest::ReceiveResponse(void)

- ea: `0x180010df0`
- end: `0x180010f20`
- name: `?ReceiveResponse@CWinHttpRequest@@UEAAHXZ`
- size: `304`
- prototype: `__int64 __fastcall(CWinHttpRequest *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180010df0`
- `0x180011400`
- `0x1800114c0`
- `0x180011760`
- `0x180086674`
- `0x1800959c0`
- `0x1800f9948`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180010e22`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180010e22`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180010e3a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180010e3a`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180010e78`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180010e78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010e44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010e44`
- `WINHTTP!WinHttpReceiveResponse` at `0x180010edf`
- `WINHTTP!WinHttpReceiveResponse` at `0x180010edf`

## string_xrefs

- `0x180010e56`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CWinHttpRequest::ReceiveResponse(CWinHttpRequest *this)
{
  __int64 v2; // rbx
  void *v3; // rdi
  HANDLE CurrentThread; // rax
  const char *v5; // r9
  __int64 v6; // rdx
  int LastError; // edi
  __int64 v8; // rsi
  void *v9; // rdx
  unsigned int v10; // r14d
  void **pExceptionObject; // [rsp+20h] [rbp-60h] BYREF
  __int128 v13; // [rsp+28h] [rbp-58h]
  int v14; // [rsp+38h] [rbp-48h]
  int v15; // [rsp+3Ch] [rbp-44h]
  int v16; // [rsp+40h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]
  void *TokenHandle; // [rsp+A0h] [rbp+20h] BYREF
  __int64 v19; // [rsp+A8h] [rbp+28h]

  v2 = -1;
  v19 = -1;
  v3 = (void *)**((_QWORD **)this + 1);
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xF01FFu, 1, &TokenHandle) && GetLastError() != 1008 )
  {
    v6 = 450;
LABEL_4:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v6,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
                  v5);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    goto LABEL_8;
  }
  if ( !SetThreadToken(0, v3) )
  {
    v6 = 454;
    goto LABEL_4;
  }
  v2 = (__int64)TokenHandle;
  v19 = (__int64)TokenHandle;
  LastError = 0;
LABEL_8:
  if ( LastError < 0 )
  {
    v13 = 0;
    pExceptionObject = &ComError::`vftable';
    v14 = LastError;
    v15 = 2131;
    v16 = 1;
    throw (ComError *)&pExceptionObject;
  }
  v8 = *((_QWORD *)this + 4);
  if ( v8 )
    ThreadMarker::MarkThread(*(ThreadMarker **)(v8 + 8));
  v10 = WinHttpReceiveResponse(*((HINTERNET *)this + 2), 0);
  if ( v8 )
    ThreadMarker::ClearThreadMarking(*(ThreadMarker **)(v8 + 8));
  if ( v2 != -1 )
    wil::details::RevertImpersonateToken((HANDLE)v2, v9);
  return v10;
}

```

## disassembly

```asm
0x180010df0  mov     [rsp-18h+arg_10], rbx
0x180010df5  mov     [rsp-18h+arg_18], rsi
0x180010dfa  push    rbp
0x180010dfb  push    rdi
0x180010dfc  push    r14
0x180010dfe  mov     rbp, rsp
0x180010e01  sub     rsp, 80h
0x180010e08  mov     r14, rcx
0x180010e0b  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180010e0f  mov     [rbp+arg_8], rbx
0x180010e13  mov     rax, [rcx+8]
0x180010e17  mov     rdi, [rax]
0x180010e1a  mov     [rbp+TokenHandle], 0
0x180010e22  call    cs:__imp_GetCurrentThread
0x180010e28  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180010e2c  lea     esi, [rbx+2]
0x180010e2f  mov     r8d, esi; OpenAsSelf
0x180010e32  mov     edx, 0F01FFh; DesiredAccess
0x180010e37  mov     rcx, rax; ThreadHandle
0x180010e3a  call    cs:__imp_OpenThreadToken
0x180010e40  test    eax, eax
0x180010e42  jnz     short loc_180010E73
0x180010e44  call    cs:__imp_GetLastError
0x180010e4a  cmp     eax, 3F0h
0x180010e4f  jz      short loc_180010E73
0x180010e51  mov     edx, 1C2h; void *
0x180010e56  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180010e5d  mov     rcx, [rbp+18h]; this
0x180010e61  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180010e66  mov     edi, eax
0x180010e68  lea     rcx, [rbp+TokenHandle]
0x180010e6c  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180010e71  jmp     short loc_180010E93
0x180010e73  mov     rdx, rdi; Token
0x180010e76  xor     ecx, ecx; Thread
0x180010e78  call    cs:__imp_SetThreadToken
0x180010e7e  test    eax, eax
0x180010e80  jnz     short loc_180010E89
0x180010e82  mov     edx, 1C6h
0x180010e87  jmp     short loc_180010E56
0x180010e89  mov     rbx, [rbp+TokenHandle]
0x180010e8d  mov     [rbp+arg_8], rbx
0x180010e91  xor     edi, edi
0x180010e93  test    edi, edi
0x180010e95  jns     short loc_180010EC7
0x180010e97  xorps   xmm0, xmm0
0x180010e9a  movups  [rbp+var_58], xmm0
0x180010e9e  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x180010ea5  mov     [rbp+pExceptionObject], rax
0x180010ea9  mov     [rbp+var_48], edi
0x180010eac  mov     [rbp+var_44], 853h
0x180010eb3  mov     [rbp+var_40], esi
0x180010eb6  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180010ebd  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180010ec1  call    _CxxThrowException_0
0x180010ec7  mov     rsi, [r14+20h]
0x180010ecb  test    rsi, rsi
0x180010ece  jz      short loc_180010ED9
0x180010ed0  mov     rcx, [rsi+8]; this
0x180010ed4  call    ?MarkThread@ThreadMarker@@QEAAXXZ; ThreadMarker::MarkThread(void)
0x180010ed9  xor     edx, edx; lpReserved
0x180010edb  mov     rcx, [r14+10h]; hRequest
0x180010edf  call    cs:__imp_WinHttpReceiveResponse
0x180010ee5  mov     r14d, eax
0x180010ee8  test    rsi, rsi
0x180010eeb  jz      short loc_180010EF7
0x180010eed  mov     rcx, [rsi+8]; this
0x180010ef1  call    ?ClearThreadMarking@ThreadMarker@@QEAAXXZ; ThreadMarker::ClearThreadMarking(void)
0x180010ef6  nop
0x180010ef7  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180010efb  jz      short loc_180010F05
0x180010efd  mov     rcx, rbx; Token
0x180010f00  call    ?RevertImpersonateToken@details@wil@@YAXPEAX@Z; wil::details::RevertImpersonateToken(void *)
0x180010f05  mov     eax, r14d
0x180010f08  lea     r11, [rsp+80h+var_s0]
0x180010f10  mov     rbx, [r11+30h]
0x180010f14  mov     rsi, [r11+38h]
0x180010f18  mov     rsp, r11
0x180010f1b  pop     r14
0x180010f1d  pop     rdi
0x180010f1e  pop     rbp
0x180010f1f  retn
```
