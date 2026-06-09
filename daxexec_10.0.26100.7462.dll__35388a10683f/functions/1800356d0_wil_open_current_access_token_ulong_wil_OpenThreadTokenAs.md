# wil::open_current_access_token(ulong,wil::OpenThreadTokenAs)

- ea: `0x1800356d0`
- end: `0x1800357a3`
- name: `?open_current_access_token@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@KW4OpenThreadTokenAs@1@@Z`
- size: `211`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180030600`
- `0x18003153c`
- `0x1800b97bc`

## callees

- `0x180010a84`
- `0x1800356d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035711`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035756`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035711`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035756`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180035701`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180035701`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180035746`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180035746`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180035730`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180035730`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800356e5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800356e5`

## string_xrefs

- `0x18003578e`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`

## pseudocode

```c
void **__fastcall wil::open_current_access_token(void **a1, DWORD a2)
{
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  HANDLE CurrentProcess; // rax
  bool v7; // sf
  int v9; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  void *TokenHandle; // [rsp+58h] [rbp+20h] BYREF

  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, a2, 1, &TokenHandle) )
    goto LABEL_10;
  LastError = GetLastError();
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  if ( LastError == -2147023888 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, a2, &TokenHandle) )
      goto LABEL_10;
    LastError = GetLastError();
    v7 = LastError < 0;
    if ( LastError <= 0 )
      goto LABEL_9;
    LastError = (unsigned __int16)LastError | 0x80070000;
  }
  v7 = LastError < 0;
LABEL_9:
  if ( v7 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xE1,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
      (const char *)(unsigned int)LastError,
      v9);
LABEL_10:
  *a1 = TokenHandle;
  return a1;
}

```

## disassembly

```asm
0x1800356d0  mov     [rsp+arg_0], rbx
0x1800356d5  push    rdi
0x1800356d6  sub     rsp, 30h
0x1800356da  and     [rsp+38h+TokenHandle], 0
0x1800356e0  mov     edi, edx
0x1800356e2  mov     rbx, rcx
0x1800356e5  call    cs:__imp_GetCurrentThread
0x1800356ec  nop     dword ptr [rax+rax+00h]
0x1800356f1  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x1800356f6  mov     r8d, 1; OpenAsSelf
0x1800356fc  mov     rcx, rax; ThreadHandle
0x1800356ff  mov     edx, edi; DesiredAccess
0x180035701  call    cs:__imp_OpenThreadToken
0x180035708  nop     dword ptr [rax+rax+00h]
0x18003570d  test    eax, eax
0x18003570f  jnz     short loc_180035772
0x180035711  call    cs:__imp_GetLastError
0x180035718  nop     dword ptr [rax+rax+00h]
0x18003571d  test    eax, eax
0x18003571f  jle     short loc_180035729
0x180035721  movzx   eax, ax
0x180035724  or      eax, 80070000h
0x180035729  cmp     eax, 800703F0h
0x18003572e  jnz     short loc_18003576E
0x180035730  call    cs:__imp_GetCurrentProcess
0x180035737  nop     dword ptr [rax+rax+00h]
0x18003573c  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x180035741  mov     edx, edi; DesiredAccess
0x180035743  mov     rcx, rax; ProcessHandle
0x180035746  call    cs:__imp_OpenProcessToken
0x18003574d  nop     dword ptr [rax+rax+00h]
0x180035752  test    eax, eax
0x180035754  jnz     short loc_180035772
0x180035756  call    cs:__imp_GetLastError
0x18003575d  nop     dword ptr [rax+rax+00h]
0x180035762  test    eax, eax
0x180035764  jle     short loc_180035770
0x180035766  movzx   eax, ax
0x180035769  or      eax, 80070000h
0x18003576e  test    eax, eax
0x180035770  js      short loc_180035789
0x180035772  mov     rax, [rsp+38h+TokenHandle]
0x180035777  mov     [rbx], rax
0x18003577a  mov     rax, rbx
0x18003577d  mov     rbx, [rsp+38h+arg_0]
0x180035782  add     rsp, 30h
0x180035786  pop     rdi
0x180035787  retn
0x180035789  mov     rcx, [rsp+38h]; this
0x18003578e  lea     r8, aOnecoreInterna_6; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180035795  mov     r9d, eax; char *
0x180035798  mov     edx, 0E1h; void *
0x18003579d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
