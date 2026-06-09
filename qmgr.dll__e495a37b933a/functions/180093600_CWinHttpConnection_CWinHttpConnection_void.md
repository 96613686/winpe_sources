# CWinHttpConnection::~CWinHttpConnection(void)

- ea: `0x180093600`
- end: `0x180093713`
- name: `??1CWinHttpConnection@@UEAA@XZ`
- size: `275`
- prototype: `void __fastcall(CWinHttpConnection *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180084a10`

## callees

- `0x180011760`
- `0x180014310`
- `0x18005bf80`
- `0x180086674`
- `0x180093600`
- `0x1800959c0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18009363f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18009363f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180093654`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180093654`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180093692`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180093692`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009365e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009365e`
- `WINHTTP!WinHttpCloseHandle` at `0x1800936ba`
- `WINHTTP!WinHttpCloseHandle` at `0x1800936df`
- `WINHTTP!WinHttpCloseHandle` at `0x1800936ba`
- `WINHTTP!WinHttpCloseHandle` at `0x1800936df`

## string_xrefs

- `0x180093675`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`

## pseudocode

```c
void __fastcall CWinHttpConnection::~CWinHttpConnection(CWinHttpConnection *this)
{
  __int64 v2; // rbx
  void *v3; // rbp
  void **v4; // rdi
  HANDLE CurrentThread; // rax
  const char *v6; // r9
  __int64 v7; // rdx
  void *v8; // rdx
  void *v9; // rcx
  void *v10; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  __int64 v12; // [rsp+40h] [rbp+8h] BYREF

  v12 = 0;
  *(_QWORD *)this = &CWinHttpConnection::`vftable';
  v2 = -1;
  v3 = (void *)**((_QWORD **)this + 1);
  v4 = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::put(&v12);
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xF01FFu, 1, v4) && GetLastError() != 1008 )
  {
    v7 = 450;
LABEL_4:
    wil::details::in1diag3::Return_GetLastError(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
      v6);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v12);
    goto LABEL_8;
  }
  if ( !SetThreadToken(0, v3) )
  {
    v7 = 454;
    goto LABEL_4;
  }
  v2 = v12;
  v12 = 0;
LABEL_8:
  v9 = (void *)*((_QWORD *)this + 2);
  if ( v9 )
  {
    WinHttpCloseHandle(v9);
    *((_QWORD *)this + 2) = 0;
  }
  if ( v2 != -1 )
    wil::details::RevertImpersonateToken((HANDLE)v2, v8);
  v10 = (void *)*((_QWORD *)this + 2);
  if ( v10 )
  {
    WinHttpCloseHandle(v10);
    *((_QWORD *)this + 2) = 0;
  }
  TokenHandle::Decrement((CWinHttpConnection *)((char *)this + 8));
  *(_QWORD *)this = &IHttpConnection::`vftable';
}

```

## disassembly

```asm
0x180093600  mov     r11, rsp
0x180093603  mov     [r11+10h], rbx
0x180093607  mov     [r11+18h], rbp
0x18009360b  push    rsi
0x18009360c  push    rdi
0x18009360d  push    r14
0x18009360f  sub     rsp, 20h
0x180093613  lea     rax, ??_7CWinHttpConnection@@6B@; const CWinHttpConnection::`vftable'
0x18009361a  mov     qword ptr [r11+8], 0
0x180093622  mov     [rcx], rax
0x180093625  mov     rsi, rcx
0x180093628  mov     rax, [rcx+8]
0x18009362c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180093630  lea     rcx, [r11+8]
0x180093634  mov     rbp, [rax]
0x180093637  call    ?put@?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::put(void)
0x18009363c  mov     rdi, rax
0x18009363f  call    cs:__imp_GetCurrentThread
0x180093645  mov     r9, rdi; TokenHandle
0x180093648  lea     r8d, [rbx+2]; OpenAsSelf
0x18009364c  mov     rcx, rax; ThreadHandle
0x18009364f  mov     edx, 0F01FFh; DesiredAccess
0x180093654  call    cs:__imp_OpenThreadToken
0x18009365a  test    eax, eax
0x18009365c  jnz     short loc_18009368D
0x18009365e  call    cs:__imp_GetLastError
0x180093664  cmp     eax, 3F0h
0x180093669  jz      short loc_18009368D
0x18009366b  mov     edx, 1C2h; void *
0x180093670  mov     rcx, [rsp+38h]; this
0x180093675  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18009367c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180093681  lea     rcx, [rsp+38h+arg_0]
0x180093686  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18009368b  jmp     short loc_1800936B1
0x18009368d  mov     rdx, rbp; Token
0x180093690  xor     ecx, ecx; Thread
0x180093692  call    cs:__imp_SetThreadToken
0x180093698  test    eax, eax
0x18009369a  jnz     short loc_1800936A3
0x18009369c  mov     edx, 1C6h
0x1800936a1  jmp     short loc_180093670
0x1800936a3  mov     rbx, [rsp+38h+arg_0]
0x1800936a8  mov     [rsp+38h+arg_0], 0
0x1800936b1  mov     rcx, [rsi+10h]; hInternet
0x1800936b5  test    rcx, rcx
0x1800936b8  jz      short loc_1800936C8
0x1800936ba  call    cs:__imp_WinHttpCloseHandle
0x1800936c0  mov     qword ptr [rsi+10h], 0
0x1800936c8  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800936cc  jz      short loc_1800936D6
0x1800936ce  mov     rcx, rbx; Token
0x1800936d1  call    ?RevertImpersonateToken@details@wil@@YAXPEAX@Z; wil::details::RevertImpersonateToken(void *)
0x1800936d6  mov     rcx, [rsi+10h]; hInternet
0x1800936da  test    rcx, rcx
0x1800936dd  jz      short loc_1800936ED
0x1800936df  call    cs:__imp_WinHttpCloseHandle
0x1800936e5  mov     qword ptr [rsi+10h], 0
0x1800936ed  lea     rcx, [rsi+8]; this
0x1800936f1  call    ?Decrement@TokenHandle@@AEAAXXZ; TokenHandle::Decrement(void)
0x1800936f6  mov     rbx, [rsp+38h+arg_8]
0x1800936fb  lea     rax, ??_7IHttpConnection@@6B@; const IHttpConnection::`vftable'
0x180093702  mov     rbp, [rsp+38h+arg_10]
0x180093707  mov     [rsi], rax
0x18009370a  add     rsp, 20h
0x18009370e  pop     r14
0x180093710  pop     rdi
0x180093711  pop     rsi
0x180093712  retn
```
