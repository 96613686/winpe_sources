# _CheckAdmin(void)

- ea: `0x18001db10`
- end: `0x18001dbf6`
- name: `?_CheckAdmin@@YAJXZ`
- size: `230`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004e150`
- `0x18004e3d0`
- `0x18004e5a0`

## callees

- `0x1800084bc`
- `0x18001db10`
- `0x18001dc00`
- `0x18002df48`
- `0x180030ad0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001db3c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001db3c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001db1d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001db1d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001dbaa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001dbe5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001dbaa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001dbe5`

## string_xrefs

- `0x18001db76`: `onecore\ds\security\gina\profile\profsvc\profrpc.cpp`
- `0x18001dbbd`: `onecore\ds\security\gina\profile\profsvc\profrpc.cpp`

## pseudocode

```c
__int64 _CheckAdmin(void)
{
  HANDLE CurrentThread; // rax
  const char *v1; // r9
  unsigned int LastError; // ebx
  int v4; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  void *TokenHandle; // [rsp+30h] [rbp+8h] BYREF

  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0x2000Eu, 1, &TokenHandle) )
  {
    if ( (unsigned int)IsUserAnAdminMember(TokenHandle) )
    {
      if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(TokenHandle);
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x33,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profrpc.cpp",
        (const char *)0x80070005LL,
        v4);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
      return 2147942405LL;
    }
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x31,
                  (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profrpc.cpp",
                  v1);
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(TokenHandle);
    return LastError;
  }
}

```

## disassembly

```asm
0x18001db10  sub     rsp, 28h
0x18001db14  mov     [rsp+28h+TokenHandle], 0
0x18001db1d  call    cs:__imp_GetCurrentThread
0x18001db24  nop     dword ptr [rax+rax+00h]
0x18001db29  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x18001db2e  mov     edx, 2000Eh; DesiredAccess
0x18001db33  mov     rcx, rax; ThreadHandle
0x18001db36  mov     r8d, 1; OpenAsSelf
0x18001db3c  call    cs:__imp_OpenThreadToken
0x18001db43  nop     dword ptr [rax+rax+00h]
0x18001db48  test    eax, eax
0x18001db4a  jz      short loc_18001DB71
0x18001db4c  mov     rcx, [rsp+28h+TokenHandle]; hExistingToken
0x18001db51  call    ?IsUserAnAdminMember@@YAHPEAX@Z; IsUserAnAdminMember(void *)
0x18001db56  test    eax, eax
0x18001db58  jz      short loc_18001DBB8
0x18001db5a  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x18001db5f  lea     rax, [rcx-1]
0x18001db63  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001db67  jbe     short loc_18001DBE5
0x18001db69  xor     eax, eax
0x18001db6b  add     rsp, 28h
0x18001db6f  retn
0x18001db71  mov     rcx, [rsp+28h]; this
0x18001db76  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001db7d  mov     edx, 31h ; '1'; void *
0x18001db82  mov     [rsp+28h+var_8], rbx
0x18001db87  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001db8c  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x18001db91  mov     ebx, eax
0x18001db93  lea     rdx, [rcx-1]
0x18001db97  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18001db9b  jbe     short loc_18001DBAA
0x18001db9d  mov     eax, ebx
0x18001db9f  mov     rbx, [rsp+28h+var_8]
0x18001dba4  add     rsp, 28h
0x18001dba8  retn
0x18001dbaa  call    cs:__imp_CloseHandle
0x18001dbb1  nop     dword ptr [rax+rax+00h]
0x18001dbb6  jmp     short loc_18001DB9D
0x18001dbb8  mov     rcx, [rsp+28h]; this
0x18001dbbd  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001dbc4  mov     r9d, 80070005h; char *
0x18001dbca  mov     edx, 33h ; '3'; void *
0x18001dbcf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001dbd4  lea     rcx, [rsp+28h+TokenHandle]
0x18001dbd9  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001dbde  mov     eax, 80070005h
0x18001dbe3  jmp     short loc_18001DB6B
0x18001dbe5  call    cs:__imp_CloseHandle
0x18001dbec  nop     dword ptr [rax+rax+00h]
0x18001dbf1  jmp     loc_18001DB69
```
