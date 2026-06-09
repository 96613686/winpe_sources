# _CheckAdmin(void)

- ea: `0x18001a110`
- end: `0x18001a1d9`
- name: `?_CheckAdmin@@YAJXZ`
- size: `201`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002af20`
- `0x18002bb60`
- `0x180038a30`

## callees

- `0x18000a9b8`
- `0x18001a110`
- `0x18001a1e0`
- `0x18002d2d8`
- `0x18002db38`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001a136`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001a136`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001a11d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001a11d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a19c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a1d1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a19c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a1d1`

## string_xrefs

- `0x18001a169`: `onecore\ds\security\gina\profile\profsvc\profrpc.cpp`
- `0x18001a1a9`: `onecore\ds\security\gina\profile\profsvc\profrpc.cpp`

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
0x18001a110  sub     rsp, 28h
0x18001a114  mov     [rsp+28h+TokenHandle], 0
0x18001a11d  call    cs:__imp_GetCurrentThread
0x18001a123  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x18001a128  mov     edx, 2000Eh; DesiredAccess
0x18001a12d  mov     rcx, rax; ThreadHandle
0x18001a130  mov     r8d, 1; OpenAsSelf
0x18001a136  call    cs:__imp_OpenThreadToken
0x18001a13c  test    eax, eax
0x18001a13e  jz      short loc_18001A164
0x18001a140  mov     rcx, [rsp+28h+TokenHandle]; hExistingToken
0x18001a145  call    ?IsUserAnAdminMember@@YAHPEAX@Z; IsUserAnAdminMember(void *)
0x18001a14a  test    eax, eax
0x18001a14c  jz      short loc_18001A1A4
0x18001a14e  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x18001a153  lea     rax, [rcx-1]
0x18001a157  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001a15b  jbe     short loc_18001A1D1
0x18001a15d  xor     eax, eax
0x18001a15f  add     rsp, 28h
0x18001a163  retn
0x18001a164  mov     rcx, [rsp+28h]; this
0x18001a169  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001a170  mov     edx, 31h ; '1'; void *
0x18001a175  mov     [rsp+28h+var_8], rbx
0x18001a17a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001a17f  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x18001a184  mov     ebx, eax
0x18001a186  lea     rdx, [rcx-1]
0x18001a18a  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18001a18e  jbe     short loc_18001A19C
0x18001a190  mov     eax, ebx
0x18001a192  mov     rbx, [rsp+28h+var_8]
0x18001a197  add     rsp, 28h
0x18001a19b  retn
0x18001a19c  call    cs:__imp_CloseHandle
0x18001a1a2  jmp     short loc_18001A190
0x18001a1a4  mov     rcx, [rsp+28h]; this
0x18001a1a9  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001a1b0  mov     r9d, 80070005h; char *
0x18001a1b6  mov     edx, 33h ; '3'; void *
0x18001a1bb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a1c0  lea     rcx, [rsp+28h+TokenHandle]
0x18001a1c5  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001a1ca  mov     eax, 80070005h
0x18001a1cf  jmp     short loc_18001A15F
0x18001a1d1  call    cs:__imp_CloseHandle
0x18001a1d7  jmp     short loc_18001A15D
```
