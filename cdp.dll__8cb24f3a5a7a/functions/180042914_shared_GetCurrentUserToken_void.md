# shared::GetCurrentUserToken(void * *)

- ea: `0x180042914`
- end: `0x180042a1f`
- name: `?GetCurrentUserToken@shared@@YAJPEAPEAX@Z`
- size: `267`
- prototype: `__int64 __fastcall(PHANDLE TokenHandle, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180042524`

## callees

- `0x180042914`
- `0x180042a28`
- `0x180149448`
- `0x18014946c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800429f4`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800429f4`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180042962`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180042962`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800429e3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800429e3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004294d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004294d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042985`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042985`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18004292a`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18004292a`

## pseudocode

```c
__int64 __fastcall shared::GetCurrentUserToken(PHANDLE TokenHandle, void **a2)
{
  HANDLE CurrentThread; // rax
  unsigned int v4; // ebx
  signed int LastError; // eax
  HANDLE CurrentProcess; // rax
  const char *v8; // r9
  int v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  bool v11; // [rsp+30h] [rbp+8h] BYREF
  bool *v12; // [rsp+38h] [rbp+10h] BYREF
  bool **v13; // [rsp+40h] [rbp+18h] BYREF

  if ( !TokenHandle )
  {
    v4 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x311,
      (unsigned int)".\\platformshared.cpp",
      (const char *)0x80004003LL,
      v9);
    return v4;
  }
  v11 = CoImpersonateClient() >= 0;
  v12 = &v11;
  v13 = &v12;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, TokenHandle) )
    goto LABEL_3;
  LastError = GetLastError();
  v4 = LastError;
  if ( LastError > 0 )
    v4 = (unsigned __int16)LastError | 0x80070000;
  if ( v4 != -2147023888 )
  {
    if ( (v4 & 0x80000000) != 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x321,
        (unsigned int)".\\platformshared.cpp",
        (const char *)v4,
        v9);
    goto LABEL_4;
  }
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, TokenHandle) )
LABEL_3:
    v4 = 0;
  else
    v4 = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0x324, (unsigned int)".\\platformshared.cpp", v8);
LABEL_4:
  ScopeWarden__lambda_7e17d7e9af6970eda98dfb5af36cea7c___::_ScopeWarden__lambda_7e17d7e9af6970eda98dfb5af36cea7c___(&v13);
  return v4;
}

```

## disassembly

```asm
0x180042914  mov     [rsp+arg_18], rbx
0x180042919  push    rdi; int
0x18004291a  sub     rsp, 20h
0x18004291e  mov     rdi, rcx
0x180042921  test    rcx, rcx
0x180042924  jz      loc_1800429B8
0x18004292a  call    cs:__imp_CoImpersonateClient
0x180042930  shr     eax, 1Fh
0x180042933  xor     al, 1
0x180042935  mov     [rsp+28h+arg_0], al
0x180042939  lea     rax, [rsp+28h+arg_0]
0x18004293e  mov     [rsp+28h+arg_8], rax
0x180042943  lea     rax, [rsp+28h+arg_8]
0x180042948  mov     [rsp+28h+arg_10], rax
0x18004294d  call    cs:__imp_GetCurrentThread
0x180042953  mov     edx, 8; DesiredAccess
0x180042958  mov     r9, rdi; TokenHandle
0x18004295b  mov     rcx, rax; ThreadHandle
0x18004295e  lea     r8d, [rdx-7]; OpenAsSelf
0x180042962  call    cs:__imp_OpenThreadToken
0x180042968  test    eax, eax
0x18004296a  jz      short loc_180042985
0x18004296c  xor     ebx, ebx
0x18004296e  lea     rcx, [rsp+28h+arg_10]
0x180042973  call    ScopeWarden__lambda_7e17d7e9af6970eda98dfb5af36cea7c______ScopeWarden__lambda_7e17d7e9af6970eda98dfb5af36cea7c___
0x180042978  mov     eax, ebx
0x18004297a  mov     rbx, [rsp+28h+arg_18]
0x18004297f  add     rsp, 20h
0x180042983  pop     rdi
0x180042984  retn
0x180042985  call    cs:__imp_GetLastError
0x18004298b  mov     ebx, eax
0x18004298d  test    eax, eax
0x18004298f  jg      short loc_1800429D8
0x180042991  cmp     ebx, 800703F0h
0x180042997  jz      short loc_1800429E3
0x180042999  test    ebx, ebx
0x18004299b  jns     short loc_18004296E
0x18004299d  mov     rcx, [rsp+28h]; this
0x1800429a2  lea     r8, aPlatformshared; ".\\platformshared.cpp"
0x1800429a9  mov     r9d, ebx; char *
0x1800429ac  mov     edx, 321h; void *
0x1800429b1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800429b6  jmp     short loc_18004296E
0x1800429b8  mov     rcx, [rsp+28h]; this
0x1800429bd  lea     r8, aPlatformshared; ".\\platformshared.cpp"
0x1800429c4  mov     ebx, 80004003h
0x1800429c9  mov     edx, 311h; void *
0x1800429ce  mov     r9d, ebx; char *
0x1800429d1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800429d6  jmp     short loc_180042978
0x1800429d8  movzx   ebx, ax
0x1800429db  or      ebx, 80070000h
0x1800429e1  jmp     short loc_180042991
0x1800429e3  call    cs:__imp_GetCurrentProcess
0x1800429e9  mov     r8, rdi; TokenHandle
0x1800429ec  mov     edx, 8; DesiredAccess
0x1800429f1  mov     rcx, rax; ProcessHandle
0x1800429f4  call    cs:__imp_OpenProcessToken
0x1800429fa  test    eax, eax
0x1800429fc  jnz     loc_18004296C
0x180042a02  mov     rcx, [rsp+28h]; this
0x180042a07  lea     r8, aPlatformshared; ".\\platformshared.cpp"
0x180042a0e  mov     edx, 324h; void *
0x180042a13  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180042a18  mov     ebx, eax
0x180042a1a  jmp     loc_18004296E
```
