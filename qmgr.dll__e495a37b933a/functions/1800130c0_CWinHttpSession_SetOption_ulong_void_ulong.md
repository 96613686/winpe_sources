# CWinHttpSession::SetOption(ulong,void *,ulong)

- ea: `0x1800130c0`
- end: `0x1800131e9`
- name: `?SetOption@CWinHttpSession@@UEAAHKPEAXK@Z`
- size: `297`
- prototype: `int(CWinHttpSession *__hidden this, unsigned int, void *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800de51c`

## callees

- `0x180011760`
- `0x1800130c0`
- `0x180086674`
- `0x1800959c0`
- `0x1800f9948`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180013101`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180013101`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180013117`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180013117`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180013155`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180013155`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013121`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013121`
- `WINHTTP!WinHttpSetOption` at `0x1800131b5`
- `WINHTTP!WinHttpSetOption` at `0x1800131b5`

## string_xrefs

- `0x180013133`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWinHttpSession::SetOption(CWinHttpSession *this, DWORD a2, void *a3, DWORD a4)
{
  __int64 v8; // rbx
  void *v9; // rdi
  HANDLE CurrentThread; // rax
  const char *v11; // r9
  __int64 v12; // rdx
  int LastError; // edi
  void *v14; // rdx
  unsigned int v15; // edi
  void **pExceptionObject; // [rsp+30h] [rbp-29h] BYREF
  __int128 v18; // [rsp+38h] [rbp-21h]
  int v19; // [rsp+48h] [rbp-11h]
  int v20; // [rsp+4Ch] [rbp-Dh]
  int v21; // [rsp+50h] [rbp-9h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]
  void *TokenHandle; // [rsp+C0h] [rbp+67h] BYREF

  v8 = -1;
  v9 = (void *)**((_QWORD **)this + 1);
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xF01FFu, 1, &TokenHandle) && GetLastError() != 1008 )
  {
    v12 = 450;
LABEL_4:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v12,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
                  v11);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    goto LABEL_8;
  }
  if ( !SetThreadToken(0, v9) )
  {
    v12 = 454;
    goto LABEL_4;
  }
  v8 = (__int64)TokenHandle;
  LastError = 0;
LABEL_8:
  if ( LastError < 0 )
  {
    v18 = 0;
    pExceptionObject = &ComError::`vftable';
    v19 = LastError;
    v20 = 2414;
    v21 = 1;
    throw (ComError *)&pExceptionObject;
  }
  v15 = WinHttpSetOption(*((HINTERNET *)this + 2), a2, a3, a4);
  if ( v8 != -1 )
    wil::details::RevertImpersonateToken((HANDLE)v8, v14);
  return v15;
}

```

## disassembly

```asm
0x1800130c0  mov     [rsp-8+arg_8], rbx
0x1800130c5  mov     [rsp-8+arg_10], rsi
0x1800130ca  push    rbp
0x1800130cb  push    rdi
0x1800130cc  push    r12
0x1800130ce  push    r14
0x1800130d0  push    r15
0x1800130d2  lea     rbp, [rsp-37h]
0x1800130d7  sub     rsp, 90h
0x1800130de  mov     r14d, r9d
0x1800130e1  mov     r15, r8
0x1800130e4  mov     r12d, edx
0x1800130e7  mov     rsi, rcx
0x1800130ea  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800130ee  mov     [rbp+57h+var_90], rbx
0x1800130f2  mov     rax, [rcx+8]
0x1800130f6  mov     rdi, [rax]
0x1800130f9  mov     [rbp+57h+TokenHandle], 0
0x180013101  call    cs:__imp_GetCurrentThread
0x180013107  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18001310b  mov     edx, 0F01FFh; DesiredAccess
0x180013110  lea     r8d, [rbx+2]; OpenAsSelf
0x180013114  mov     rcx, rax; ThreadHandle
0x180013117  call    cs:__imp_OpenThreadToken
0x18001311d  test    eax, eax
0x18001311f  jnz     short loc_180013150
0x180013121  call    cs:__imp_GetLastError
0x180013127  cmp     eax, 3F0h
0x18001312c  jz      short loc_180013150
0x18001312e  mov     edx, 1C2h; void *
0x180013133  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001313a  mov     rcx, [rbp+5Fh]; this
0x18001313e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180013143  mov     edi, eax
0x180013145  lea     rcx, [rbp+57h+TokenHandle]
0x180013149  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001314e  jmp     short loc_180013170
0x180013150  mov     rdx, rdi; Token
0x180013153  xor     ecx, ecx; Thread
0x180013155  call    cs:__imp_SetThreadToken
0x18001315b  test    eax, eax
0x18001315d  jnz     short loc_180013166
0x18001315f  mov     edx, 1C6h
0x180013164  jmp     short loc_180013133
0x180013166  mov     rbx, [rbp+57h+TokenHandle]
0x18001316a  mov     [rbp+57h+var_90], rbx
0x18001316e  xor     edi, edi
0x180013170  test    edi, edi
0x180013172  jns     short loc_1800131A8
0x180013174  xorps   xmm0, xmm0
0x180013177  movups  [rbp+57h+var_78], xmm0
0x18001317b  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x180013182  mov     [rbp+57h+pExceptionObject], rax
0x180013186  mov     [rbp+57h+var_68], edi
0x180013189  mov     [rbp+57h+var_64], 96Eh
0x180013190  mov     [rbp+57h+var_60], 1
0x180013197  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18001319e  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800131a2  call    _CxxThrowException_0
0x1800131a8  mov     r9d, r14d; dwBufferLength
0x1800131ab  mov     r8, r15; lpBuffer
0x1800131ae  mov     edx, r12d; dwOption
0x1800131b1  mov     rcx, [rsi+10h]; hInternet
0x1800131b5  call    cs:__imp_WinHttpSetOption
0x1800131bb  mov     edi, eax
0x1800131bd  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800131c1  jz      short loc_1800131CB
0x1800131c3  mov     rcx, rbx; Token
0x1800131c6  call    ?RevertImpersonateToken@details@wil@@YAXPEAX@Z; wil::details::RevertImpersonateToken(void *)
0x1800131cb  mov     eax, edi
0x1800131cd  lea     r11, [rsp+0B0h+var_20]
0x1800131d5  mov     rbx, [r11+38h]
0x1800131d9  mov     rsi, [r11+40h]
0x1800131dd  mov     rsp, r11
0x1800131e0  pop     r15
0x1800131e2  pop     r14
0x1800131e4  pop     r12
0x1800131e6  pop     rdi
0x1800131e7  pop     rbp
0x1800131e8  retn
```
