# RevertToUser(void * *)

- ea: `0x180009b70`
- end: `0x180009be0`
- name: `?RevertToUser@@YAJPEAPEAX@Z`
- size: `112`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `5`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000659c`
- `0x1800080c8`
- `0x180008b30`
- `0x1800099f8`
- `0x180013048`

## callees

- `0x180009b70`
- `0x18002db38`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180009b7e`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180009b7e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009b90`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009bc8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009b90`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009bc8`

## string_xrefs

- `0x180009ba8`: `onecore\ds\security\gina\profile\proflib\sid.cpp`

## pseudocode

```c
__int64 __fastcall RevertToUser(void **a1)
{
  const char *v2; // r9
  unsigned int LastError; // edi
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( SetThreadToken(0, *a1) )
  {
    if ( *a1 )
    {
      CloseHandle(*a1);
      *a1 = 0;
    }
    return 0;
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x4F,
                  (unsigned int)"onecore\\ds\\security\\gina\\profile\\proflib\\sid.cpp",
                  v2);
    if ( *a1 )
    {
      CloseHandle(*a1);
      *a1 = 0;
    }
    return LastError;
  }
}

```

## disassembly

```asm
0x180009b70  push    rbx
0x180009b72  sub     rsp, 20h
0x180009b76  mov     rdx, [rcx]; Token
0x180009b79  mov     rbx, rcx
0x180009b7c  xor     ecx, ecx; Thread
0x180009b7e  call    cs:__imp_SetThreadToken
0x180009b84  test    eax, eax
0x180009b86  jz      short loc_180009BA3
0x180009b88  mov     rcx, [rbx]; hObject
0x180009b8b  test    rcx, rcx
0x180009b8e  jz      short loc_180009B9B
0x180009b90  call    cs:__imp_CloseHandle
0x180009b96  xor     ecx, ecx
0x180009b98  mov     [rbx], rcx
0x180009b9b  xor     eax, eax
0x180009b9d  add     rsp, 20h
0x180009ba1  pop     rbx
0x180009ba2  retn
0x180009ba3  mov     rcx, [rsp+28h]; this
0x180009ba8  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\p"...
0x180009baf  mov     edx, 4Fh ; 'O'; void *
0x180009bb4  mov     [rsp+28h+arg_0], rdi
0x180009bb9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180009bbe  mov     rcx, [rbx]; hObject
0x180009bc1  mov     edi, eax
0x180009bc3  test    rcx, rcx
0x180009bc6  jz      short loc_180009BD3
0x180009bc8  call    cs:__imp_CloseHandle
0x180009bce  xor     ecx, ecx
0x180009bd0  mov     [rbx], rcx
0x180009bd3  mov     eax, edi
0x180009bd5  mov     rdi, [rsp+28h+arg_0]
0x180009bda  add     rsp, 20h
0x180009bde  pop     rbx
0x180009bdf  retn
```
